# ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)

- ea: `0x140010468`
- end: `0x140010523`
- name: `?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d780`
- `0x14001351c`

## callees

- `0x140009fc4`
- `0x140010468`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400104d8`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1400104d8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400104a5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1400104a5`

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
0x140010468  mov     [rsp+arg_8], rbx
0x14001046d  mov     [rsp+arg_10], rsi
0x140010472  mov     [rsp+plLbound], r9d
0x140010477  push    rdi
0x140010478  sub     rsp, 20h
0x14001047c  mov     rdi, rcx
0x14001047f  mov     rsi, r8
0x140010482  mov     rcx, [rcx]; psa
0x140010485  mov     ebx, edx
0x140010487  test    rcx, rcx
0x14001048a  jnz     short loc_140010493
0x14001048c  mov     eax, 80004005h
0x140010491  jmp     short loc_140010512
0x140010493  lea     r8, [rsp+28h+plLbound]; plLbound
0x140010498  mov     [rsp+28h+plLbound], 0
0x1400104a0  mov     edx, 1; nDim
0x1400104a5  call    cs:__imp_SafeArrayGetLBound
0x1400104ac  nop     dword ptr [rax+rax+00h]
0x1400104b1  test    eax, eax
0x1400104b3  jns     short loc_1400104BD
0x1400104b5  mov     ecx, eax; int
0x1400104b7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400104bc  int     3; Trap to Debugger
0x1400104bd  cmp     ebx, [rsp+28h+plLbound]
0x1400104c1  jl      short loc_14001050D
0x1400104c3  mov     rcx, [rdi]; psa
0x1400104c6  lea     r8, [rsp+28h+plUbound]; plUbound
0x1400104cb  mov     edx, 1; nDim
0x1400104d0  mov     [rsp+28h+plUbound], 0
0x1400104d8  call    cs:__imp_SafeArrayGetUBound
0x1400104df  nop     dword ptr [rax+rax+00h]
0x1400104e4  test    eax, eax
0x1400104e6  jns     short loc_1400104F0
0x1400104e8  mov     ecx, eax; int
0x1400104ea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400104ef  int     3; Trap to Debugger
0x1400104f0  cmp     ebx, [rsp+28h+plUbound]
0x1400104f4  jg      short loc_14001050D
0x1400104f6  mov     rax, [rdi]
0x1400104f9  sub     ebx, [rsp+28h+plLbound]
0x1400104fd  movsxd  rdx, ebx
0x140010500  mov     rcx, [rax+10h]
0x140010504  mov     al, [rsi]
0x140010506  mov     [rdx+rcx], al
0x140010509  xor     eax, eax
0x14001050b  jmp     short loc_140010512
0x14001050d  mov     eax, 80070057h
0x140010512  mov     rbx, [rsp+28h+arg_8]
0x140010517  mov     rsi, [rsp+28h+arg_10]
0x14001051c  add     rsp, 20h
0x140010520  pop     rdi
0x140010521  retn
```
