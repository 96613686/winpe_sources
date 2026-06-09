# wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>(_RTL_RUN_ONCE &,_lambda_8e4368fb547587b2dd84ae7e04fbdf86_)

- ea: `0x18001fbd8`
- end: `0x18001fc5b`
- name: `??$init_once@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@wil@@YA_NAEAT_RTL_RUN_ONCE@@V_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@@Z`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026eb4`

## callees

- `0x180002b20`
- `0x180017008`
- `0x18001fbd8`
- `0x1800226ac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001fc04`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001fc04`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001fc26`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001fc26`

## string_xrefs

- `0x18001fc49`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
char wil::init_once<_lambda_8e4368fb547587b2dd84ae7e04fbdf86_>()
{
  const char *v0; // r9
  WINBOOL fPending; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  fPending = 0;
  if ( !__std_init_once_begin_initialize(&FlowEndpointBase::s_initDefaultTimeoutMsOnce, 0, &fPending, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x3BC,
      (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\win32_helpers.h",
      v0);
  if ( !fPending )
    return 0;
  _lambda_8e4368fb547587b2dd84ae7e04fbdf86_::operator()();
  InitOnceComplete(&FlowEndpointBase::s_initDefaultTimeoutMsOnce, 0, 0);
  return 1;
}

```

## disassembly

```asm
0x18001fbd8  sub     rsp, 38h
0x18001fbdc  mov     rax, cs:__security_cookie
0x18001fbe3  xor     rax, rsp
0x18001fbe6  mov     [rsp+38h+var_10], rax
0x18001fbeb  xor     r9d, r9d; lpContext
0x18001fbee  mov     [rsp+38h+fPending], 0
0x18001fbf6  lea     r8, [rsp+38h+fPending]; fPending
0x18001fbfb  xor     edx, edx; dwFlags
0x18001fbfd  lea     rcx, ?s_initDefaultTimeoutMsOnce@FlowEndpointBase@@1T_RTL_RUN_ONCE@@A; lpInitOnce
0x18001fc04  call    cs:__imp___std_init_once_begin_initialize
0x18001fc0a  test    eax, eax
0x18001fc0c  jz      short loc_18001FC44
0x18001fc0e  cmp     [rsp+38h+fPending], 0
0x18001fc13  jz      short loc_18001FC30
0x18001fc15  call    ??R_lambda_8e4368fb547587b2dd84ae7e04fbdf86_@@QEBA@XZ; _lambda_8e4368fb547587b2dd84ae7e04fbdf86_::operator()(void)
0x18001fc1a  xor     r8d, r8d; lpContext
0x18001fc1d  lea     rcx, ?s_initDefaultTimeoutMsOnce@FlowEndpointBase@@1T_RTL_RUN_ONCE@@A; lpInitOnce
0x18001fc24  xor     edx, edx; dwFlags
0x18001fc26  call    cs:__imp_InitOnceComplete
0x18001fc2c  mov     al, 1
0x18001fc2e  jmp     short loc_18001FC32
0x18001fc30  xor     al, al
0x18001fc32  mov     rcx, [rsp+38h+var_10]
0x18001fc37  xor     rcx, rsp; StackCookie
0x18001fc3a  call    __security_check_cookie
0x18001fc3f  add     rsp, 38h
0x18001fc43  retn
0x18001fc44  mov     rcx, [rsp+38h]; this
0x18001fc49  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18001fc50  mov     edx, 3BCh; void *
0x18001fc55  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
