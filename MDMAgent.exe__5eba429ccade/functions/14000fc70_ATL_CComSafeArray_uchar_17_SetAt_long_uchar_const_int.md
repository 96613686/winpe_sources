# ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)

- ea: `0x14000fc70`
- end: `0x14000fd1e`
- name: `?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z`
- size: `174`
- prototype: `__int64 __fastcall(SAFEARRAY **, LONG, _BYTE *, LONG)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d0fc`
- `0x140012bd0`

## callees

- `0x140009b90`
- `0x14000fc70`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000fcda`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000fcda`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000fcad`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000fcad`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeArray<unsigned char,17>::SetAt(SAFEARRAY **a1, LONG a2, _BYTE *a3, LONG a4)
{
  SAFEARRAY *v6; // rcx
  HRESULT LBound; // eax
  SAFEARRAY *v10; // rcx
  HRESULT UBound; // eax
  LONG plUbound; // [rsp+30h] [rbp+8h] BYREF
  LONG plLbound; // [rsp+48h] [rbp+20h] BYREF

  plLbound = a4;
  v6 = *a1;
  if ( !v6 )
    return 2147500037LL;
  plLbound = 0;
  LBound = SafeArrayGetLBound(v6, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::AtlThrowImpl(LBound);
  if ( a2 < plLbound )
    return 2147942487LL;
  v10 = *a1;
  plUbound = 0;
  UBound = SafeArrayGetUBound(v10, 1u, &plUbound);
  if ( UBound < 0 )
    ATL::AtlThrowImpl(UBound);
  if ( a2 > plUbound )
    return 2147942487LL;
  *((_BYTE *)(*a1)->pvData + a2 - plLbound) = *a3;
  return 0;
}

```

## disassembly

```asm
0x14000fc70  mov     [rsp+arg_8], rbx
0x14000fc75  mov     [rsp+arg_10], rsi
0x14000fc7a  mov     [rsp+plLbound], r9d
0x14000fc7f  push    rdi
0x14000fc80  sub     rsp, 20h
0x14000fc84  mov     rdi, rcx
0x14000fc87  mov     rsi, r8
0x14000fc8a  mov     rcx, [rcx]; psa
0x14000fc8d  mov     ebx, edx
0x14000fc8f  test    rcx, rcx
0x14000fc92  jnz     short loc_14000FC9B
0x14000fc94  mov     eax, 80004005h
0x14000fc99  jmp     short loc_14000FD0E
0x14000fc9b  lea     r8, [rsp+28h+plLbound]; plLbound
0x14000fca0  mov     [rsp+28h+plLbound], 0
0x14000fca8  mov     edx, 1; nDim
0x14000fcad  call    cs:__imp_SafeArrayGetLBound
0x14000fcb3  test    eax, eax
0x14000fcb5  jns     short loc_14000FCBF
0x14000fcb7  mov     ecx, eax; int
0x14000fcb9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000fcbf  cmp     ebx, [rsp+28h+plLbound]
0x14000fcc3  jl      short loc_14000FD09
0x14000fcc5  mov     rcx, [rdi]; psa
0x14000fcc8  lea     r8, [rsp+28h+plUbound]; plUbound
0x14000fccd  mov     edx, 1; nDim
0x14000fcd2  mov     [rsp+28h+plUbound], 0
0x14000fcda  call    cs:__imp_SafeArrayGetUBound
0x14000fce0  test    eax, eax
0x14000fce2  jns     short loc_14000FCEC
0x14000fce4  mov     ecx, eax; int
0x14000fce6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000fcec  cmp     ebx, [rsp+28h+plUbound]
0x14000fcf0  jg      short loc_14000FD09
0x14000fcf2  mov     rax, [rdi]
0x14000fcf5  sub     ebx, [rsp+28h+plLbound]
0x14000fcf9  movsxd  rdx, ebx
0x14000fcfc  mov     rcx, [rax+10h]
0x14000fd00  mov     al, [rsi]
0x14000fd02  mov     [rdx+rcx], al
0x14000fd05  xor     eax, eax
0x14000fd07  jmp     short loc_14000FD0E
0x14000fd09  mov     eax, 80070057h
0x14000fd0e  mov     rbx, [rsp+28h+arg_8]
0x14000fd13  mov     rsi, [rsp+28h+arg_10]
0x14000fd18  add     rsp, 20h
0x14000fd1c  pop     rdi
0x14000fd1d  retn
```
