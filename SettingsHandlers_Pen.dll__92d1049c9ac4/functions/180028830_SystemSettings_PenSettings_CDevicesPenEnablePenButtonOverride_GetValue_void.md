# SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride::GetValue(void)

- ea: `0x180028830`
- end: `0x18002889c`
- name: `?GetValue@CDevicesPenEnablePenButtonOverride@PenSettings@SystemSettings@@UEAA_NXZ`
- size: `108`
- prototype: `bool __fastcall(SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180028830`
- `0x1800288b0`
- `0x18002c44c`
- `0x18003103c`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180028859`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180028859`

## string_xrefs

- `0x180028868`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
bool __fastcall SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride::GetValue(
        SystemSettings::PenSettings::CDevicesPenEnablePenButtonOverride *this)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pvParam; // [rsp+38h] [rbp+10h] BYREF

  if ( !SystemSettings::PenSettings::IsDesktop(this) )
    return SystemSettings::DataModel::CRegBoolSetting::GetValue(this);
  pvParam = 0;
  if ( SystemParametersInfoW(0x1052u, 0, &pvParam, 0) )
    return pvParam == 0;
  wil::details::in1diag3::_Log_GetLastError(
    retaddr,
    (void *)0x28E,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
    v2);
  return 0;
}

```

## disassembly

```asm
0x180028830  push    rbx
0x180028832  sub     rsp, 20h
0x180028836  mov     rbx, rcx
0x180028839  call    ?IsDesktop@PenSettings@SystemSettings@@YA_NXZ; SystemSettings::PenSettings::IsDesktop(void)
0x18002883e  test    al, al
0x180028840  jz      short loc_18002888F
0x180028842  xor     r9d, r9d; fWinIni
0x180028845  mov     [rsp+28h+pvParam], 0
0x18002884d  lea     r8, [rsp+28h+pvParam]; pvParam
0x180028852  xor     edx, edx; uiParam
0x180028854  mov     ecx, 1052h; uiAction
0x180028859  call    cs:__imp_SystemParametersInfoW
0x18002885f  test    eax, eax
0x180028861  jnz     short loc_180028881
0x180028863  mov     rcx, [rsp+28h]; this
0x180028868  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002886f  mov     edx, 28Eh; void *
0x180028874  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180028879  xor     al, al
0x18002887b  add     rsp, 20h
0x18002887f  pop     rbx
0x180028880  retn
0x180028881  cmp     [rsp+28h+pvParam], 0
0x180028886  setz    al
0x180028889  add     rsp, 20h
0x18002888d  pop     rbx
0x18002888e  retn
0x18002888f  mov     rcx, rbx; this
0x180028892  add     rsp, 20h
0x180028896  pop     rbx
0x180028897  jmp     ?GetValue@CRegBoolSetting@DataModel@SystemSettings@@UEAA_NXZ; SystemSettings::DataModel::CRegBoolSetting::GetValue(void)
```
