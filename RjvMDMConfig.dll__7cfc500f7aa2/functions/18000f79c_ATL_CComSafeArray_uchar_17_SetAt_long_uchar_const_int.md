# ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)

- ea: `0x18000f79c`
- end: `0x18000f857`
- name: `?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c980`

## callees

- `0x180008484`
- `0x18000f79c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000f80c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000f80c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000f7d9`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000f7d9`

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
  {
    ATL::AtlThrowImpl(LBound);
    __debugbreak();
  }
  if ( a2 < plLbound )
    return 2147942487LL;
  v10 = *a1;
  plUbound = 0;
  UBound = SafeArrayGetUBound(v10, 1u, &plUbound);
  if ( UBound < 0 )
  {
    ATL::AtlThrowImpl(UBound);
    __debugbreak();
  }
  if ( a2 > plUbound )
    return 2147942487LL;
  *((_BYTE *)(*a1)->pvData + a2 - plLbound) = *a3;
  return 0;
}

```

## disassembly

```asm
0x18000f79c  mov     [rsp+arg_8], rbx
0x18000f7a1  mov     [rsp+arg_10], rsi
0x18000f7a6  mov     [rsp+plLbound], r9d
0x18000f7ab  push    rdi
0x18000f7ac  sub     rsp, 20h
0x18000f7b0  mov     rdi, rcx
0x18000f7b3  mov     rsi, r8
0x18000f7b6  mov     rcx, [rcx]; psa
0x18000f7b9  mov     ebx, edx
0x18000f7bb  test    rcx, rcx
0x18000f7be  jnz     short loc_18000F7C7
0x18000f7c0  mov     eax, 80004005h
0x18000f7c5  jmp     short loc_18000F846
0x18000f7c7  lea     r8, [rsp+28h+plLbound]; plLbound
0x18000f7cc  mov     [rsp+28h+plLbound], 0
0x18000f7d4  mov     edx, 1; nDim
0x18000f7d9  call    cs:__imp_SafeArrayGetLBound
0x18000f7e0  nop     dword ptr [rax+rax+00h]
0x18000f7e5  test    eax, eax
0x18000f7e7  jns     short loc_18000F7F1
0x18000f7e9  mov     ecx, eax; int
0x18000f7eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f7f0  int     3; Trap to Debugger
0x18000f7f1  cmp     ebx, [rsp+28h+plLbound]
0x18000f7f5  jl      short loc_18000F841
0x18000f7f7  mov     rcx, [rdi]; psa
0x18000f7fa  lea     r8, [rsp+28h+plUbound]; plUbound
0x18000f7ff  mov     edx, 1; nDim
0x18000f804  mov     [rsp+28h+plUbound], 0
0x18000f80c  call    cs:__imp_SafeArrayGetUBound
0x18000f813  nop     dword ptr [rax+rax+00h]
0x18000f818  test    eax, eax
0x18000f81a  jns     short loc_18000F824
0x18000f81c  mov     ecx, eax; int
0x18000f81e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f823  int     3; Trap to Debugger
0x18000f824  cmp     ebx, [rsp+28h+plUbound]
0x18000f828  jg      short loc_18000F841
0x18000f82a  mov     rax, [rdi]
0x18000f82d  sub     ebx, [rsp+28h+plLbound]
0x18000f831  movsxd  rdx, ebx
0x18000f834  mov     rcx, [rax+10h]
0x18000f838  mov     al, [rsi]
0x18000f83a  mov     [rdx+rcx], al
0x18000f83d  xor     eax, eax
0x18000f83f  jmp     short loc_18000F846
0x18000f841  mov     eax, 80070057h
0x18000f846  mov     rbx, [rsp+28h+arg_8]
0x18000f84b  mov     rsi, [rsp+28h+arg_10]
0x18000f850  add     rsp, 20h
0x18000f854  pop     rdi
0x18000f855  retn
```
