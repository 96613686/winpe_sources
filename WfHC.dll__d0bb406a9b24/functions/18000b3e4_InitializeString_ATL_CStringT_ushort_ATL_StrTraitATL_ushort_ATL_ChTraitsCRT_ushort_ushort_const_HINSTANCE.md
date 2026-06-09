# InitializeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,HINSTANCE__ *)

- ea: `0x18000b3e4`
- end: `0x18000b47b`
- name: `?InitializeString@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAUHINSTANCE__@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000aab8`
- `0x18000bacc`
- `0x18000bd68`

## callees

- `0x18000b3e4`
- `0x18000b484`
- `0x18000b590`
- `0x18000b7a8`
- `0x18000b9a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b430`

## pseudocode

```c
__int64 __fastcall InitializeString(_QWORD *a1, unsigned __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  int StringW; // eax
  signed int LastError; // eax
  __int64 v8; // r8
  ATL::CAtlException *v9; // [rsp+20h] [rbp-18h] BYREF

  if ( *(int *)(*a1 - 16LL) > 0 )
    return 2147943647LL;
  try
  {
    v5 = 0;
    if ( a2 >= 0x10000 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(a2 + 2 * v8) );
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(a1);
    }
    else
    {
      if ( a3 )
        StringW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                    a1,
                    a3,
                    (unsigned int)a2);
      else
        StringW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
                    a1,
                    a2);
      if ( !StringW )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  catch ( ATL::CAtlException *v9 )
  {
    return *(unsigned int *)v9;
  }
  v5 = 0;
}

```

## disassembly

```asm
0x18000b3e4  mov     [rsp+arg_8], rbx
0x18000b3e9  mov     [rsp+arg_10], rsi
0x18000b3ee  push    rdi
0x18000b3ef  sub     rsp, 30h
0x18000b3f3  mov     r9, r8
0x18000b3f6  mov     rdi, rcx
0x18000b3f9  mov     rax, [rcx]
0x18000b3fc  xor     esi, esi
0x18000b3fe  cmp     [rax-10h], esi
0x18000b401  jle     short loc_18000B40A
0x18000b403  mov     eax, 800704DFh
0x18000b408  jmp     short loc_18000B46B
0x18000b40a  mov     ebx, esi
0x18000b40c  cmp     rdx, 10000h
0x18000b413  jnb     short loc_18000B447
0x18000b415  test    r9, r9
0x18000b418  jz      short loc_18000B427
0x18000b41a  mov     r8d, edx
0x18000b41d  mov     rdx, r9
0x18000b420  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x18000b425  jmp     short loc_18000B42C
0x18000b427  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000b42c  test    eax, eax
0x18000b42e  jnz     short loc_18000B463
0x18000b430  call    cs:__imp_GetLastError
0x18000b436  mov     ebx, eax
0x18000b438  test    eax, eax
0x18000b43a  jle     short loc_18000B463
0x18000b43c  movzx   ebx, ax
0x18000b43f  or      ebx, 80070000h
0x18000b445  jmp     short loc_18000B463
0x18000b447  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b44b  inc     r8
0x18000b44e  cmp     [rdx+r8*2], si
0x18000b453  jnz     short loc_18000B44B
0x18000b455  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000b45a  mov     rcx, rdi
0x18000b45d  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x18000b462  nop
0x18000b463  jmp     short loc_18000B469
0x18000b465  mov     ebx, [rsp+38h+arg_0]
0x18000b469  mov     eax, ebx
0x18000b46b  mov     rbx, [rsp+38h+arg_8]
0x18000b470  mov     rsi, [rsp+38h+arg_10]
0x18000b475  add     rsp, 30h
0x18000b479  pop     rdi
0x18000b47a  retn
```
