# GetFirstItemInList(ushort const *,ushort * *)

- ea: `0x180018888`
- end: `0x180018941`
- name: `?GetFirstItemInList@@YAJPEBGPEAPEAG@Z`
- size: `185`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009180`
- `0x180009d40`

## callees

- `0x180006e28`
- `0x180018888`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001891a`
- `msvcrt!wcsncpy_s` at `0x18001891a`
- `msvcrt!wcstok_s` at `0x1800188d5`
- `msvcrt!wcstok_s` at `0x1800188d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018928`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800188f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800188f9`

## pseudocode

```c
__int64 __fastcall GetFirstItemInList(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned int v4; // edi
  wchar_t *v5; // rbx
  __int64 v6; // rax
  rsize_t v7; // rsi
  wchar_t *v8; // rax
  unsigned __int16 *v9; // rbp
  wchar_t *String; // [rsp+50h] [rbp+8h] BYREF
  wchar_t *Context; // [rsp+60h] [rbp+18h] BYREF

  Context = 0;
  String = 0;
  v4 = 0;
  CSpDynamicString::operator=((LPVOID *)&String, a1);
  if ( a1 )
  {
    if ( a2 )
    {
      v5 = wcstok_s(String, L" ;:,", &Context);
      if ( v5 )
      {
        v6 = -1;
        do
          ++v6;
        while ( v5[v6] );
        v7 = v6 + 1;
        v8 = (wchar_t *)CoTaskMemAlloc(2 * (v6 + 1));
        v9 = v8;
        if ( v8 )
        {
          wcsncpy_s(v8, v7, v5, v7);
          *a2 = v9;
        }
        else
        {
          v4 = -2147024882;
        }
      }
    }
  }
  CoTaskMemFree(String);
  return v4;
}

```

## disassembly

```asm
0x180018888  mov     rax, rsp
0x18001888b  mov     [rax+10h], rbx
0x18001888f  push    rbp
0x180018890  push    rsi
0x180018891  push    rdi
0x180018892  push    r14
0x180018894  push    r15
0x180018896  sub     rsp, 20h
0x18001889a  xor     r15d, r15d
0x18001889d  mov     r14, rdx
0x1800188a0  mov     rdx, rcx
0x1800188a3  mov     [rax+18h], r15
0x1800188a7  mov     rbx, rcx
0x1800188aa  mov     [rax+8], r15
0x1800188ae  lea     rcx, [rax+8]
0x1800188b2  mov     edi, r15d
0x1800188b5  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x1800188ba  test    rbx, rbx
0x1800188bd  jz      short loc_180018923
0x1800188bf  test    r14, r14
0x1800188c2  jz      short loc_180018923
0x1800188c4  mov     rcx, [rsp+48h+String]; String
0x1800188c9  lea     r8, [rsp+48h+Context]; Context
0x1800188ce  lea     rdx, Delimiter; " ;:,"
0x1800188d5  call    cs:__imp_wcstok_s
0x1800188db  mov     rbx, rax
0x1800188de  test    rax, rax
0x1800188e1  jz      short loc_180018923
0x1800188e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800188e7  inc     rax
0x1800188ea  cmp     [rbx+rax*2], r15w
0x1800188ef  jnz     short loc_1800188E7
0x1800188f1  lea     rsi, [rax+1]
0x1800188f5  lea     rcx, [rsi+rsi]; cb
0x1800188f9  call    cs:__imp_CoTaskMemAlloc
0x1800188ff  mov     rbp, rax
0x180018902  test    rax, rax
0x180018905  jnz     short loc_18001890E
0x180018907  mov     edi, 8007000Eh
0x18001890c  jmp     short loc_180018923
0x18001890e  mov     r9, rsi; MaxCount
0x180018911  mov     r8, rbx; Source
0x180018914  mov     rdx, rsi; SizeInWords
0x180018917  mov     rcx, rbp; Destination
0x18001891a  call    cs:__imp_wcsncpy_s
0x180018920  mov     [r14], rbp
0x180018923  mov     rcx, [rsp+48h+String]; pv
0x180018928  call    cs:__imp_CoTaskMemFree
0x18001892e  mov     rbx, [rsp+48h+arg_8]
0x180018933  mov     eax, edi
0x180018935  add     rsp, 20h
0x180018939  pop     r15
0x18001893b  pop     r14
0x18001893d  pop     rdi
0x18001893e  pop     rsi
0x18001893f  pop     rbp
0x180018940  retn
```
