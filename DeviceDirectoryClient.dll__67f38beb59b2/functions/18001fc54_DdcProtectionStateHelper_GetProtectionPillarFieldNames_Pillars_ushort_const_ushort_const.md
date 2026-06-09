# DdcProtectionStateHelper::GetProtectionPillarFieldNames(Pillars,ushort const * *,ushort const * *)

- ea: `0x18001fc54`
- end: `0x18001fd6d`
- name: `?GetProtectionPillarFieldNames@DdcProtectionStateHelper@@CAJW4Pillars@@PEAPEBG1@Z`
- size: `281`
- prototype: `__int64 __fastcall(int, const wchar_t **, const wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fd74`

## callees

- `0x1800050b8`
- `0x18001fc54`

## string_xrefs

- `0x18001fc89`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001fc75`: `CPR(ppwszJsonHealth)`
- `0x18001fcb5`: `CPR(ppwszJsonStatus)`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetProtectionPillarFieldNames(
        int a1,
        const wchar_t **a2,
        const wchar_t **a3)
{
  unsigned int v3; // ebx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  const wchar_t *v8; // rax
  const wchar_t *v9; // rcx

  if ( !a2 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        94,
        "CPR(ppwszJsonHealth)");
    return v3;
  }
  if ( !a3 )
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        95,
        "CPR(ppwszJsonStatus)");
    return v3;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v8 = L"ThreatProtectionStatus";
    v9 = L"ThreatProtectionHealth";
    goto LABEL_20;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = L"DefenderStatus";
    v9 = L"DefenderHealth";
    goto LABEL_20;
  }
  v6 = v5 - 2;
  if ( !v6 )
  {
    v8 = L"NetworkProtectionStatus";
    v9 = L"NetworkProtectionHealth";
    goto LABEL_20;
  }
  v7 = v6 - 4;
  if ( !v7 )
  {
    v8 = L"HealthAdvisorStatus";
    v9 = L"HealthAdvisorHealth";
    goto LABEL_20;
  }
  if ( v7 == 8 )
  {
    v8 = L"AppsAndBrowserStatus";
    v9 = L"AppsAndBrowserHealth";
LABEL_20:
    *a2 = v9;
    v3 = 0;
    *a3 = v8;
    return v3;
  }
  v3 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      (_DWORD)a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
      125,
      "CHR(((HRESULT)0x80070057L))");
  return v3;
}

```

## disassembly

```asm
0x18001fc54  push    rbx
0x18001fc56  sub     rsp, 30h
0x18001fc5a  test    rdx, rdx
0x18001fc5d  jnz     short loc_18001FC9A
0x18001fc5f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fc66  mov     r8d, 80070057h
0x18001fc6c  mov     ebx, r8d
0x18001fc6f  jz      loc_18001FD65
0x18001fc75  lea     rax, aCprPpwszjsonhe; "CPR(ppwszJsonHealth)"
0x18001fc7c  mov     [rsp+38h+var_10], rax
0x18001fc81  mov     [rsp+38h+var_18], 25Eh
0x18001fc89  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001fc90  call    McTemplateU0dsqs_EventWriteTransfer
0x18001fc95  jmp     loc_18001FD65
0x18001fc9a  test    r8, r8
0x18001fc9d  jnz     short loc_18001FCCB
0x18001fc9f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fca6  mov     r8d, 80070057h
0x18001fcac  mov     ebx, r8d
0x18001fcaf  jz      loc_18001FD65
0x18001fcb5  lea     rax, aCprPpwszjsonst; "CPR(ppwszJsonStatus)"
0x18001fcbc  mov     [rsp+38h+var_10], rax
0x18001fcc1  mov     [rsp+38h+var_18], 25Fh
0x18001fcc9  jmp     short loc_18001FC89
0x18001fccb  sub     ecx, 1
0x18001fcce  jz      short loc_18001FD4F
0x18001fcd0  sub     ecx, 1
0x18001fcd3  jz      short loc_18001FD3F
0x18001fcd5  sub     ecx, 2
0x18001fcd8  jz      short loc_18001FD2F
0x18001fcda  sub     ecx, 4
0x18001fcdd  jz      short loc_18001FD1F
0x18001fcdf  cmp     ecx, 8
0x18001fce2  jz      short loc_18001FD0F
0x18001fce4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001fceb  mov     r8d, 80070057h
0x18001fcf1  mov     ebx, r8d
0x18001fcf4  jz      short loc_18001FD65
0x18001fcf6  lea     rax, aChrHresult0x80; "CHR(((HRESULT)0x80070057L))"
0x18001fcfd  mov     [rsp+38h+var_10], rax
0x18001fd02  mov     [rsp+38h+var_18], 27Dh
0x18001fd0a  jmp     loc_18001FC89
0x18001fd0f  lea     rax, aAppsandbrowser_0; "AppsAndBrowserStatus"
0x18001fd16  lea     rcx, aAppsandbrowser; "AppsAndBrowserHealth"
0x18001fd1d  jmp     short loc_18001FD5D
0x18001fd1f  lea     rax, aHealthadvisors; "HealthAdvisorStatus"
0x18001fd26  lea     rcx, aHealthadvisorh; "HealthAdvisorHealth"
0x18001fd2d  jmp     short loc_18001FD5D
0x18001fd2f  lea     rax, aNetworkprotect_3; "NetworkProtectionStatus"
0x18001fd36  lea     rcx, aNetworkprotect_1; "NetworkProtectionHealth"
0x18001fd3d  jmp     short loc_18001FD5D
0x18001fd3f  lea     rax, aDefenderstatus; "DefenderStatus"
0x18001fd46  lea     rcx, aDefenderhealth; "DefenderHealth"
0x18001fd4d  jmp     short loc_18001FD5D
0x18001fd4f  lea     rax, aThreatprotecti; "ThreatProtectionStatus"
0x18001fd56  lea     rcx, aThreatprotecti_1; "ThreatProtectionHealth"
0x18001fd5d  mov     [rdx], rcx
0x18001fd60  xor     ebx, ebx
0x18001fd62  mov     [r8], rax
0x18001fd65  mov     eax, ebx
0x18001fd67  add     rsp, 30h
0x18001fd6b  pop     rbx
0x18001fd6c  retn
```
