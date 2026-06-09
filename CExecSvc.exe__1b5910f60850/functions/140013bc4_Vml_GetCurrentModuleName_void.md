# Vml::GetCurrentModuleName(void)

- ea: `0x140013bc4`
- end: `0x140013cd1`
- name: `?GetCurrentModuleName@Vml@@YAPEBGXZ`
- size: `269`
- prototype: `const unsigned __int16 *__fastcall(Vml *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013914`
- `0x140013f10`

## callees

- `0x140002310`
- `0x14000e828`
- `0x140013bc4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140013c39`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140013c39`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140013bfc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140013bfc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140013c7e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140013c7e`

## string_xrefs

- `0x140013cbf`: `onecore\internal\sdk\inc\wil\opensource\wil\win32_helpers.h`
- `0x140013cad`: `onecore\vm\common\vml\VmModuleUtils.h`

## pseudocode

```c
const unsigned __int16 *__fastcall Vml::GetCurrentModuleName(Vml *this)
{
  const char *v1; // r9
  const char *v2; // r9
  __int64 v3; // rax
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  fPending = 0;
  if ( !InitOnceBeginInitialize(&Vml::Details::g_ModulePathInitOnce, 0, &fPending, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      v1);
  if ( fPending )
  {
    if ( !GetModuleFileNameW(&_ImageBase, &Vml::Details::g_ModulePath, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModuleUtils.h",
        v2);
    v3 = -1;
    do
      ++v3;
    while ( *(&Vml::Details::g_ModulePath + v3) );
    for ( ; v3; --v3 )
    {
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 47 )
        break;
      if ( *(&Vml::Details::g_ModulePath + v3 - 1) == 92 )
        break;
    }
    Vml::Details::g_ModuleName = &Vml::Details::g_ModulePath + v3;
    InitOnceComplete(&Vml::Details::g_ModulePathInitOnce, 0, 0);
  }
  return Vml::Details::g_ModuleName;
}

```

## disassembly

```asm
0x140013bc4  mov     [rsp+arg_0], rbx
0x140013bc9  mov     [rsp+arg_8], rsi
0x140013bce  push    rdi
0x140013bcf  sub     rsp, 40h
0x140013bd3  mov     rax, cs:__security_cookie
0x140013bda  xor     rax, rsp
0x140013bdd  mov     [rsp+48h+var_10], rax
0x140013be2  xor     ebx, ebx
0x140013be4  mov     [rsp+48h+fPending], ebx
0x140013be8  xor     r9d, r9d; lpContext
0x140013beb  lea     r8, [rsp+48h+fPending]; fPending
0x140013bf0  xor     edx, edx; dwFlags
0x140013bf2  lea     rsi, ?g_ModulePathInitOnce@Details@Vml@@3T_RTL_RUN_ONCE@@A; _RTL_RUN_ONCE Vml::Details::g_ModulePathInitOnce
0x140013bf9  mov     rcx, rsi; lpInitOnce
0x140013bfc  call    cs:__imp_InitOnceBeginInitialize
0x140013c02  mov     rcx, [rsp+48h]; this
0x140013c07  test    eax, eax
0x140013c09  jz      loc_140013CBF
0x140013c0f  cmp     [rsp+48h+fPending], ebx
0x140013c13  jz      short loc_140013C84
0x140013c15  mov     [rsp+48h+var_28], rsi
0x140013c1a  mov     [rsp+48h+var_20], 4
0x140013c22  mov     r8d, 104h; nSize
0x140013c28  lea     rdi, ?g_ModulePath@Details@Vml@@3PAGA; ushort near * Vml::Details::g_ModulePath
0x140013c2f  mov     rdx, rdi; lpFilename
0x140013c32  lea     rcx, __ImageBase; hModule
0x140013c39  call    cs:__imp_GetModuleFileNameW
0x140013c3f  test    eax, eax
0x140013c41  jz      short loc_140013CA8
0x140013c43  or      rax, 0FFFFFFFFFFFFFFFFh
0x140013c47  inc     rax
0x140013c4a  cmp     [rdi+rax*2], bx
0x140013c4e  jnz     short loc_140013C47
0x140013c50  test    rax, rax
0x140013c53  jz      short loc_140013C6B
0x140013c55  cmp     word ptr [rdi+rax*2-2], 2Fh ; '/'
0x140013c5b  jz      short loc_140013C6B
0x140013c5d  cmp     word ptr [rdi+rax*2-2], 5Ch ; '\'
0x140013c63  jz      short loc_140013C6B
0x140013c65  sub     rax, 1
0x140013c69  jnz     short loc_140013C55
0x140013c6b  lea     rax, [rdi+rax*2]
0x140013c6f  mov     cs:?g_ModuleName@Details@Vml@@3PEBGEB, rax; ushort const * const Vml::Details::g_ModuleName
0x140013c76  xor     r8d, r8d; lpContext
0x140013c79  xor     edx, edx; dwFlags
0x140013c7b  mov     rcx, rsi; lpInitOnce
0x140013c7e  call    cs:__imp_InitOnceComplete
0x140013c84  mov     rax, cs:?g_ModuleName@Details@Vml@@3PEBGEB; ushort const * const Vml::Details::g_ModuleName
0x140013c8b  mov     rcx, [rsp+48h+var_10]
0x140013c90  xor     rcx, rsp; StackCookie
0x140013c93  call    __security_check_cookie
0x140013c98  mov     rbx, [rsp+48h+arg_0]
0x140013c9d  mov     rsi, [rsp+48h+arg_8]
0x140013ca2  add     rsp, 40h
0x140013ca6  pop     rdi
0x140013ca7  retn
0x140013ca8  mov     rcx, [rsp+48h]; this
0x140013cad  lea     r8, aOnecoreVmCommo_0; "onecore\\vm\\common\\vml\\VmModuleUtils"...
0x140013cb4  mov     edx, 30h ; '0'; void *
0x140013cb9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140013cbf  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140013cc6  mov     edx, 3BCh; void *
0x140013ccb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
