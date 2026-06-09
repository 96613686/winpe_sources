# SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration::GetValue(IInspectable * *)

- ea: `0x180038350`
- end: `0x1800383e3`
- name: `?GetValue@CDevicesPenSetHandednessConfiguration@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `147`
- prototype: `int(SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a29c`
- `0x18000a2bc`
- `0x180012868`
- `0x180038350`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180038377`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x180038377`

## string_xrefs

- `0x180038386`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`
- `0x1800383c3`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration::GetValue(
        SystemSettings::PenSettings::CDevicesPenSetHandednessConfiguration *this,
        struct IInspectable **a2)
{
  const char *v3; // r9
  const unsigned __int16 *v5; // rcx
  int String; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int pvParam; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  pvParam = 0;
  if ( !SystemParametersInfoW(0x2024u, 0, &pvParam, 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x8F,
             (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
             v3);
  v5 = L"SystemSettings_Devices_Pen_RightHanded_Rejuv";
  if ( pvParam != 1 )
    v5 = L"SystemSettings_Devices_Pen_LeftHanded_Rejuv";
  String = SystemSettings::DataModel::PropValueHelper::CreateString(v5, a2);
  v7 = String;
  if ( String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x92,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
    (const char *)(unsigned int)String,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180038350  push    rbx; int
0x180038352  sub     rsp, 20h
0x180038356  mov     rbx, rdx
0x180038359  mov     qword ptr [rdx], 0
0x180038360  xor     edx, edx; uiParam
0x180038362  mov     [rsp+28h+pvParam], 0
0x18003836a  xor     r9d, r9d; fWinIni
0x18003836d  lea     r8, [rsp+28h+pvParam]; pvParam
0x180038372  mov     ecx, 2024h; uiAction
0x180038377  call    cs:__imp_SystemParametersInfoW
0x18003837d  test    eax, eax
0x18003837f  jnz     short loc_180038399
0x180038381  mov     rcx, [rsp+28h]; this
0x180038386  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x18003838d  mov     edx, 8Fh; void *
0x180038392  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038397  jmp     short loc_1800383DD
0x180038399  cmp     [rsp+28h+pvParam], 1
0x18003839e  lea     rax, aSystemsettings_71; "SystemSettings_Devices_Pen_LeftHanded_R"...
0x1800383a5  lea     rcx, sourceString; "SystemSettings_Devices_Pen_RightHanded_"...
0x1800383ac  mov     rdx, rbx; struct IInspectable **
0x1800383af  cmovnz  rcx, rax; unsigned __int16 *
0x1800383b3  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800383b8  mov     ebx, eax
0x1800383ba  test    eax, eax
0x1800383bc  jns     short loc_1800383DB
0x1800383be  mov     rcx, [rsp+28h]; this
0x1800383c3  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x1800383ca  mov     r9d, eax; char *
0x1800383cd  mov     edx, 92h; void *
0x1800383d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800383d7  mov     eax, ebx
0x1800383d9  jmp     short loc_1800383DD
0x1800383db  xor     eax, eax
0x1800383dd  add     rsp, 20h
0x1800383e1  pop     rbx
0x1800383e2  retn
```
