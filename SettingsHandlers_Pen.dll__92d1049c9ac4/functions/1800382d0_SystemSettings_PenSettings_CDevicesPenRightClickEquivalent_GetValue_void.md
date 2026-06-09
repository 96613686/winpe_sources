# SystemSettings::PenSettings::CDevicesPenRightClickEquivalent::GetValue(void)

- ea: `0x1800382d0`
- end: `0x18003833d`
- name: `?GetValue@CDevicesPenRightClickEquivalent@PenSettings@SystemSettings@@UEAA_NXZ`
- size: `109`
- prototype: `bool __fastcall(SystemSettings::PenSettings::CDevicesPenRightClickEquivalent *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a29c`
- `0x1800382d0`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800382ff`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1800382ff`

## string_xrefs

- `0x18003830e`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::CDevicesPenRightClickEquivalent::GetValue(
        SystemSettings::PenSettings::CDevicesPenRightClickEquivalent *this)
{
  const char *v1; // r9
  bool v2; // zf
  _OWORD pvParam[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  memset(pvParam, 0, 28);
  if ( SystemParametersInfoW(0x96u, 0x1Cu, pvParam, 0) )
    v2 = DWORD2(pvParam[1]) == 0;
  else
    v2 = (unsigned int)wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x241,
                         (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
                         v1) == 0;
  return !v2;
}

```

## disassembly

```asm
0x1800382d0  sub     rsp, 58h
0x1800382d4  mov     rax, cs:__security_cookie
0x1800382db  xor     rax, rsp
0x1800382de  mov     [rsp+58h+var_18], rax
0x1800382e3  xorps   xmm0, xmm0
0x1800382e6  lea     r8, [rsp+58h+pvParam]; pvParam
0x1800382eb  xor     r9d, r9d; fWinIni
0x1800382ee  movups  [rsp+58h+pvParam], xmm0
0x1800382f3  movups  [rsp+58h+pvParam+0Ch], xmm0
0x1800382f8  lea     edx, [r9+1Ch]; uiParam
0x1800382fc  lea     ecx, [rdx+7Ah]; uiAction
0x1800382ff  call    cs:__imp_SystemParametersInfoW
0x180038305  test    eax, eax
0x180038307  jnz     short loc_180038323
0x180038309  mov     rcx, [rsp+58h]; this
0x18003830e  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180038315  mov     edx, 241h; void *
0x18003831a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003831f  test    eax, eax
0x180038321  jmp     short loc_180038328
0x180038323  cmp     [rsp+58h+var_20], 0
0x180038328  setnz   al
0x18003832b  mov     rcx, [rsp+58h+var_18]
0x180038330  xor     rcx, rsp; StackCookie
0x180038333  call    __security_check_cookie
0x180038338  add     rsp, 58h
0x18003833c  retn
```
