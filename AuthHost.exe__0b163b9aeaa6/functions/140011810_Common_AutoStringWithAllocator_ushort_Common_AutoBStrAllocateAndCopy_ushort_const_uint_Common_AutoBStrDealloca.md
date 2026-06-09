# Common::AutoStringWithAllocator<ushort,&Common::AutoBStrAllocateAndCopy(ushort const *,uint),&Common::AutoBStrDeallocate(ushort *)>::CopyFromString(ushort const *)

- ea: `0x140011810`
- end: `0x140011893`
- name: `?CopyFromString@?$AutoStringWithAllocator@G$1?AutoBStrAllocateAndCopy@Common@@YAPEAGPEBGI@Z$1?AutoBStrDeallocate@2@YAXPEAG@Z@Common@@QEAAJPEBG@Z`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011aa4`

## callees

- `0x14000b7d4`
- `0x140011810`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001186b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14001186b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001182a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001182a`

## pseudocode

```c
__int64 __fastcall Common::AutoStringWithAllocator<unsigned short,&unsigned short * Common::AutoBStrAllocateAndCopy(unsigned short const *,unsigned int),&void Common::AutoBStrDeallocate(unsigned short *)>::CopyFromString(
        BSTR *a1,
        const unsigned __int16 *a2)
{
  int v4; // ebx
  BSTR v5; // rax
  unsigned __int64 ui; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  SysFreeString(*a1);
  *a1 = 0;
  if ( a2 )
  {
    ui = 0;
    v4 = StringCchLengthW(a2, 0x7FFFFFFFu, &ui);
    if ( v4 >= 0 )
    {
      if ( (unsigned int)ui <= 0x3FFFFFFF )
      {
        v5 = SysAllocStringLen(a2, ui);
        *a1 = v5;
        return v5 == 0 ? 0x8007000E : 0;
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140011810  mov     [rsp+arg_8], rbx
0x140011815  mov     [rsp+arg_10], rsi
0x14001181a  push    rdi
0x14001181b  sub     rsp, 20h
0x14001181f  mov     rsi, rcx
0x140011822  mov     rdi, rdx
0x140011825  mov     rcx, [rcx]; bstrString
0x140011828  xor     ebx, ebx
0x14001182a  call    cs:__imp_SysFreeString
0x140011830  mov     [rsi], rbx
0x140011833  test    rdi, rdi
0x140011836  jz      short loc_140011881
0x140011838  lea     r8, [rsp+28h+ui]; unsigned __int64 *
0x14001183d  mov     [rsp+28h+ui], rbx
0x140011842  mov     edx, 7FFFFFFFh; unsigned __int64
0x140011847  mov     rcx, rdi; unsigned __int16 *
0x14001184a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001184f  mov     ebx, eax
0x140011851  test    eax, eax
0x140011853  js      short loc_140011881
0x140011855  mov     edx, dword ptr [rsp+28h+ui]; ui
0x140011859  cmp     edx, 3FFFFFFFh
0x14001185f  jbe     short loc_140011868
0x140011861  mov     ebx, 80070057h
0x140011866  jmp     short loc_140011881
0x140011868  mov     rcx, rdi; strIn
0x14001186b  call    cs:__imp_SysAllocStringLen
0x140011871  mov     [rsi], rax
0x140011874  neg     rax
0x140011877  sbb     ebx, ebx
0x140011879  not     ebx
0x14001187b  and     ebx, 8007000Eh
0x140011881  mov     rsi, [rsp+28h+arg_10]
0x140011886  mov     eax, ebx
0x140011888  mov     rbx, [rsp+28h+arg_8]
0x14001188d  add     rsp, 20h
0x140011891  pop     rdi
0x140011892  retn
```
