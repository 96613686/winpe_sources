# SystemSettings::PenSettings::CDevicesPenEraseInk::GetValue(void)

- ea: `0x180038040`
- end: `0x1800380ad`
- name: `?GetValue@CDevicesPenEraseInk@PenSettings@SystemSettings@@UEAA_NXZ`
- size: `109`
- prototype: `bool __fastcall(SystemSettings::PenSettings::CDevicesPenEraseInk *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a29c`
- `0x180038040`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003806f`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18003806f`

## string_xrefs

- `0x18003807e`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::CDevicesPenEraseInk::GetValue(
        SystemSettings::PenSettings::CDevicesPenEraseInk *this)
{
  const char *v1; // r9
  bool v2; // zf
  _OWORD pvParam[2]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  memset(pvParam, 0, 28);
  if ( SystemParametersInfoW(0x96u, 0x1Cu, pvParam, 0) )
    v2 = DWORD1(pvParam[1]) == 0;
  else
    v2 = (unsigned int)wil::details::in1diag3::Return_GetLastError(
                         retaddr,
                         (void *)0x27C,
                         (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
                         v1) == 0;
  return !v2;
}

```

## disassembly

```asm
0x180038040  sub     rsp, 58h
0x180038044  mov     rax, cs:__security_cookie
0x18003804b  xor     rax, rsp
0x18003804e  mov     [rsp+58h+var_18], rax
0x180038053  xorps   xmm0, xmm0
0x180038056  lea     r8, [rsp+58h+pvParam]; pvParam
0x18003805b  xor     r9d, r9d; fWinIni
0x18003805e  movups  [rsp+58h+pvParam], xmm0
0x180038063  movups  [rsp+58h+pvParam+0Ch], xmm0
0x180038068  lea     edx, [r9+1Ch]; uiParam
0x18003806c  lea     ecx, [rdx+7Ah]; uiAction
0x18003806f  call    cs:__imp_SystemParametersInfoW
0x180038075  test    eax, eax
0x180038077  jnz     short loc_180038093
0x180038079  mov     rcx, [rsp+58h]; this
0x18003807e  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180038085  mov     edx, 27Ch; void *
0x18003808a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003808f  test    eax, eax
0x180038091  jmp     short loc_180038098
0x180038093  cmp     [rsp+58h+var_24], 0
0x180038098  setnz   al
0x18003809b  mov     rcx, [rsp+58h+var_18]
0x1800380a0  xor     rcx, rsp; StackCookie
0x1800380a3  call    __security_check_cookie
0x1800380a8  add     rsp, 58h
0x1800380ac  retn
```
