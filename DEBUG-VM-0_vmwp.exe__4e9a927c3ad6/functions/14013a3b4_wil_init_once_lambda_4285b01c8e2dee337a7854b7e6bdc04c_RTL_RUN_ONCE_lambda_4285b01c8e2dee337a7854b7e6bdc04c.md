# wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>(_RTL_RUN_ONCE &,_lambda_4285b01c8e2dee337a7854b7e6bdc04c_)

- ea: `0x14013a3b4`
- end: `0x14013a4d1`
- name: `??$init_once@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_4285b01c8e2dee337a7854b7e6bdc04c_@@@Z`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14013b470`
- `0x14013e9f0`
- `0x14013f3fc`
- `0x14017d838`

## callees

- `0x14005b628`
- `0x140132940`
- `0x14013a3b4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14013a441`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14013a441`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14013a4a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14013a4a1`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14013a3ec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14013a3ec`

## string_xrefs

- `0x14013a401`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`
- `0x14013a456`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char wil::init_once<_lambda_4285b01c8e2dee337a7854b7e6bdc04c_>()
{
  const char *v0; // r9
  const char *v1; // r9
  __int64 v2; // rdx
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      v0);
  if ( !fPending )
    return 0;
  if ( !GetModuleFileNameW(&_ImageBase, &Vml::Details::g_ModulePath, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\vm\\common\\vml\\VmModuleUtils.h",
      v1);
  v2 = -1;
  do
    ++v2;
  while ( *(&Vml::Details::g_ModulePath + v2) );
  for ( ; v2; --v2 )
  {
    if ( *(&Vml::Details::g_ModulePath + v2 - 1) == 47 )
      break;
    if ( *(&Vml::Details::g_ModulePath + v2 - 1) == 92 )
      break;
  }
  Vml::Details::g_ModuleName = &Vml::Details::g_ModulePath + v2;
  InitOnceComplete(&Vml::Details::g_ModulePathInitOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x14013a3b4  mov     [rsp+arg_0], rbx
0x14013a3b9  mov     [rsp+arg_8], rsi
0x14013a3be  push    rdi
0x14013a3bf  sub     rsp, 40h
0x14013a3c3  mov     rax, cs:__security_cookie
0x14013a3ca  xor     rax, rsp
0x14013a3cd  mov     [rsp+48h+var_10], rax
0x14013a3d2  xor     ebx, ebx
0x14013a3d4  mov     [rsp+48h+fPending], ebx
0x14013a3d8  xor     r9d, r9d; lpContext
0x14013a3db  lea     r8, [rsp+48h+fPending]; fPending
0x14013a3e0  xor     edx, edx; dwFlags
0x14013a3e2  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x14013a3e9  mov     rcx, rsi; lpInitOnce
0x14013a3ec  call    cs:__imp_InitOnceBeginInitialize
0x14013a3f3  nop     dword ptr [rax+rax+00h]
0x14013a3f8  mov     rcx, [rsp+48h]; this
0x14013a3fd  test    eax, eax
0x14013a3ff  jnz     short loc_14013A413
0x14013a401  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14013a408  mov     edx, 3BCh; void *
0x14013a40d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013a413  cmp     [rsp+48h+fPending], ebx
0x14013a417  jz      loc_14013A4B1
0x14013a41d  mov     [rsp+48h+var_28], rsi
0x14013a422  mov     [rsp+48h+var_20], 4
0x14013a42a  mov     r8d, 104h; nSize
0x14013a430  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x14013a437  mov     rdx, rdi; lpFilename
0x14013a43a  lea     rcx, __ImageBase; hModule
0x14013a441  call    cs:__imp_GetModuleFileNameW
0x14013a448  nop     dword ptr [rax+rax+00h]
0x14013a44d  test    eax, eax
0x14013a44f  jnz     short loc_14013A466
0x14013a451  mov     rcx, [rsp+48h]; this
0x14013a456  lea     r8, aOnecoreVmCommo_82; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x14013a45d  lea     edx, [rax+30h]; void *
0x14013a460  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14013a466  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14013a46a  inc     rdx
0x14013a46d  cmp     [rdi+rdx*2], bx
0x14013a471  jnz     short loc_14013A46A
0x14013a473  test    rdx, rdx
0x14013a476  jz      short loc_14013A48E
0x14013a478  cmp     word ptr [rdi+rdx*2-2], 2Fh ; '/'
0x14013a47e  jz      short loc_14013A48E
0x14013a480  cmp     word ptr [rdi+rdx*2-2], 5Ch ; '\'
0x14013a486  jz      short loc_14013A48E
0x14013a488  sub     rdx, 1
0x14013a48c  jnz     short loc_14013A478
0x14013a48e  lea     rdx, [rdi+rdx*2]
0x14013a492  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rdx; ushort const * const Vml::Details::g_ModuleName
0x14013a499  xor     r8d, r8d; lpContext
0x14013a49c  xor     edx, edx; dwFlags
0x14013a49e  mov     rcx, rsi; lpInitOnce
0x14013a4a1  call    cs:__imp_InitOnceComplete
0x14013a4a8  nop     dword ptr [rax+rax+00h]
0x14013a4ad  mov     al, 1
0x14013a4af  jmp     short loc_14013A4B3
0x14013a4b1  xor     al, al
0x14013a4b3  mov     rcx, [rsp+48h+var_10]
0x14013a4b8  xor     rcx, rsp; StackCookie
0x14013a4bb  call    __security_check_cookie
0x14013a4c0  mov     rbx, [rsp+48h+arg_0]
0x14013a4c5  mov     rsi, [rsp+48h+arg_8]
0x14013a4ca  add     rsp, 40h
0x14013a4ce  pop     rdi
0x14013a4cf  retn
```
