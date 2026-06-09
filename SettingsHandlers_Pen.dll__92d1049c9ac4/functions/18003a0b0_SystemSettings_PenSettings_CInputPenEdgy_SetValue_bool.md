# SystemSettings::PenSettings::CInputPenEdgy::SetValue(bool)

- ea: `0x18003a0b0`
- end: `0x18003a16a`
- name: `?SetValue@CInputPenEdgy@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CInputPenEdgy *__hidden this, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a29c`
- `0x18003a0b0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a0f1`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a13f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a0f1`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003a13f`

## string_xrefs

- `0x18003a105`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CInputPenEdgy::SetValue(
        SystemSettings::PenSettings::CInputPenEdgy *this,
        char a2)
{
  __int64 v4; // r8
  const char *v5; // r9
  __int64 v6; // rdx
  _OWORD pvParam[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9 = 0;
  memset(pvParam, 0, sizeof(pvParam));
  if ( !SystemParametersInfoW(0x94u, 0x28u, pvParam, 0) )
  {
    v6 = 1442;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v5);
  }
  LOBYTE(v4) = a2;
  (*(void (__fastcall **)(SystemSettings::PenSettings::CInputPenEdgy *, _OWORD *, __int64))(*(_QWORD *)this + 272LL))(
    this,
    pvParam,
    v4);
  if ( !SystemParametersInfoW(0x95u, 0x28u, pvParam, 3u) )
  {
    v6 = 1451;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v5);
  }
  return 0;
}

```

## disassembly

```asm
0x18003a0b0  mov     [rsp+arg_10], rbx
0x18003a0b5  push    rdi
0x18003a0b6  sub     rsp, 50h
0x18003a0ba  mov     rax, cs:__security_cookie
0x18003a0c1  xor     rax, rsp
0x18003a0c4  mov     [rsp+58h+var_10], rax
0x18003a0c9  xor     eax, eax
0x18003a0cb  lea     r8, [rsp+58h+pvParam]; pvParam
0x18003a0d0  xorps   xmm0, xmm0
0x18003a0d3  mov     [rsp+58h+var_18], rax
0x18003a0d8  mov     dil, dl
0x18003a0db  mov     rbx, rcx
0x18003a0de  xor     r9d, r9d; fWinIni
0x18003a0e1  lea     edx, [rax+28h]; uiParam
0x18003a0e4  lea     ecx, [rdx+6Ch]; uiAction
0x18003a0e7  movups  [rsp+58h+pvParam], xmm0
0x18003a0ec  movups  [rsp+58h+var_28], xmm0
0x18003a0f1  call    cs:__imp_SystemParametersInfoW
0x18003a0f7  test    eax, eax
0x18003a0f9  jnz     short loc_18003A113
0x18003a0fb  mov     edx, 5A2h; void *
0x18003a100  mov     rcx, [rsp+58h]; this
0x18003a105  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x18003a10c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003a111  jmp     short loc_18003A152
0x18003a113  mov     rax, [rbx]
0x18003a116  lea     rdx, [rsp+58h+pvParam]
0x18003a11b  mov     r8b, dil
0x18003a11e  mov     rcx, rbx
0x18003a121  mov     rax, [rax+110h]
0x18003a128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a12d  mov     r9d, 3; fWinIni
0x18003a133  lea     r8, [rsp+58h+pvParam]; pvParam
0x18003a138  lea     edx, [r9+25h]; uiParam
0x18003a13c  lea     ecx, [rdx+6Dh]; uiAction
0x18003a13f  call    cs:__imp_SystemParametersInfoW
0x18003a145  test    eax, eax
0x18003a147  jnz     short loc_18003A150
0x18003a149  mov     edx, 5ABh
0x18003a14e  jmp     short loc_18003A100
0x18003a150  xor     eax, eax
0x18003a152  mov     rcx, [rsp+58h+var_10]
0x18003a157  xor     rcx, rsp; StackCookie
0x18003a15a  call    __security_check_cookie
0x18003a15f  mov     rbx, [rsp+58h+arg_10]
0x18003a164  add     rsp, 50h
0x18003a168  pop     rdi
0x18003a169  retn
```
