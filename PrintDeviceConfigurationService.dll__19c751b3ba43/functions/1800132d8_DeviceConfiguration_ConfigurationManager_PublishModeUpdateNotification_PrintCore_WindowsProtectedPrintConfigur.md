# DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(PrintCore::WindowsProtectedPrintConfigurationState,long)

- ea: `0x1800132d8`
- end: `0x18001335a`
- name: `?_PublishModeUpdateNotification@ConfigurationManager@DeviceConfiguration@@AEAAXW4WindowsProtectedPrintConfigurationState@PrintCore@@J@Z`
- size: `130`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180011c38`

## callees

- `0x1800020c0`
- `0x18000dc94`
- `0x1800132d8`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180013321`
- `ntdll!RtlPublishWnfStateData` at `0x180013321`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_PublishModeUpdateNotification(
        __int64 a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  _DWORD v4[4]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4[1] = a2;
  v4[3] = a3;
  v4[2] = 0;
  v4[0] = 1;
  result = (unsigned int)RtlPublishWnfStateData(WNF_PRNC_WPP_MODE_CHANGED, 0, v4, 16) | 0x10000000;
  if ( (int)result < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
      (const char *)(unsigned int)result,
      0);
  return result;
}

```

## disassembly

```asm
0x1800132d8  sub     rsp, 58h
0x1800132dc  mov     rax, cs:__security_cookie
0x1800132e3  xor     rax, rsp
0x1800132e6  mov     [rsp+58h+var_18], rax
0x1800132eb  mov     rcx, cs:WNF_PRNC_WPP_MODE_CHANGED
0x1800132f2  mov     r9d, 10h
0x1800132f8  mov     [rsp+58h+var_24], edx
0x1800132fc  xor     edx, edx
0x1800132fe  mov     [rsp+58h+var_1C], r8d
0x180013303  lea     r8, [rsp+58h+var_28]
0x180013308  mov     [rsp+58h+var_20], 0
0x180013310  mov     [rsp+58h+var_28], 1
0x180013318  mov     qword ptr [rsp+58h+var_38], 0; int
0x180013321  call    cs:__imp_RtlPublishWnfStateData
0x180013327  or      eax, 10000000h
0x18001332c  jge     short loc_180013348
0x18001332e  mov     rcx, [rsp+58h]; this
0x180013333  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x18001333a  mov     r9d, eax; char *
0x18001333d  mov     edx, 361h; void *
0x180013342  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013348  mov     rcx, [rsp+58h+var_18]
0x18001334d  xor     rcx, rsp; StackCookie
0x180013350  call    __security_check_cookie
0x180013355  add     rsp, 58h
0x180013359  retn
```
