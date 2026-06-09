# ParsePubsubString(ushort const *,ushort * *,ushort * *)

- ea: `0x180006008`
- end: `0x1800060b9`
- name: `?ParsePubsubString@@YAJPEBGPEAPEAG1@Z`
- size: `177`
- prototype: `int(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800059e8`

## callees

- `0x180006008`

## import_xrefs

- `msvcrt!wcstok_s` at `0x180006038`
- `msvcrt!wcstok_s` at `0x18000604b`
- `msvcrt!wcstok_s` at `0x18000605e`
- `msvcrt!wcstok_s` at `0x180006038`
- `msvcrt!wcstok_s` at `0x18000604b`
- `msvcrt!wcstok_s` at `0x18000605e`
- `ole32!CoTaskMemFree` at `0x18000609d`
- `ole32!CoTaskMemFree` at `0x18000609d`
- `SHLWAPI!SHStrDupW` at `0x18000607c`
- `SHLWAPI!SHStrDupW` at `0x18000608e`
- `SHLWAPI!SHStrDupW` at `0x18000607c`
- `SHLWAPI!SHStrDupW` at `0x18000608e`

## pseudocode

```c
__int64 __fastcall ParsePubsubString(wchar_t *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  wchar_t *v6; // rbp
  wchar_t *v7; // r14
  wchar_t *v8; // rax
  const WCHAR *v9; // rsi
  wchar_t *Context; // [rsp+78h] [rbp+20h] BYREF

  Context = 0;
  v5 = -2147024809;
  v6 = wcstok_s(a1, L"/:", &Context);
  v7 = wcstok_s(0, L"/:", &Context);
  v8 = wcstok_s(0, L"/:", &Context);
  v9 = v8;
  if ( v6 )
  {
    if ( v7 )
    {
      if ( v8 )
      {
        v5 = SHStrDupW(v6, a2);
        if ( v5 >= 0 )
        {
          v5 = SHStrDupW(v9, a3);
          if ( v5 < 0 )
          {
            CoTaskMemFree(*a2);
            *a2 = 0;
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180006008  push    rbx
0x18000600a  push    rbp
0x18000600b  push    rsi
0x18000600c  push    rdi
0x18000600d  push    r14
0x18000600f  push    r15
0x180006011  sub     rsp, 28h
0x180006015  mov     r15, r8
0x180006018  mov     [rsp+58h+Context], 0
0x180006021  mov     rdi, rdx
0x180006024  lea     rsi, Delimiter; "/:"
0x18000602b  mov     rdx, rsi; Delimiter
0x18000602e  lea     r8, [rsp+58h+Context]; Context
0x180006033  mov     ebx, 80070057h
0x180006038  call    cs:__imp_wcstok_s
0x18000603e  lea     r8, [rsp+58h+Context]; Context
0x180006043  mov     rdx, rsi; Delimiter
0x180006046  xor     ecx, ecx; String
0x180006048  mov     rbp, rax
0x18000604b  call    cs:__imp_wcstok_s
0x180006051  lea     r8, [rsp+58h+Context]; Context
0x180006056  mov     rdx, rsi; Delimiter
0x180006059  xor     ecx, ecx; String
0x18000605b  mov     r14, rax
0x18000605e  call    cs:__imp_wcstok_s
0x180006064  mov     rsi, rax
0x180006067  test    rbp, rbp
0x18000606a  jz      short loc_1800060AA
0x18000606c  test    r14, r14
0x18000606f  jz      short loc_1800060AA
0x180006071  test    rax, rax
0x180006074  jz      short loc_1800060AA
0x180006076  mov     rdx, rdi; ppwsz
0x180006079  mov     rcx, rbp; psz
0x18000607c  call    cs:__imp_SHStrDupW
0x180006082  mov     ebx, eax
0x180006084  test    eax, eax
0x180006086  js      short loc_1800060AA
0x180006088  mov     rdx, r15; ppwsz
0x18000608b  mov     rcx, rsi; psz
0x18000608e  call    cs:__imp_SHStrDupW
0x180006094  mov     ebx, eax
0x180006096  test    eax, eax
0x180006098  jns     short loc_1800060AA
0x18000609a  mov     rcx, [rdi]; pv
0x18000609d  call    cs:__imp_CoTaskMemFree
0x1800060a3  mov     qword ptr [rdi], 0
0x1800060aa  mov     eax, ebx
0x1800060ac  add     rsp, 28h
0x1800060b0  pop     r15
0x1800060b2  pop     r14
0x1800060b4  pop     rdi
0x1800060b5  pop     rsi
0x1800060b6  pop     rbp
0x1800060b7  pop     rbx
0x1800060b8  retn
```
