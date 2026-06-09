# WixQueryOsWellKnownSID

- ea: `0x10002f38`
- end: `0x10002fe3`
- name: `WixQueryOsWellKnownSID`
- size: `171`
- prototype: `int __stdcall(MSIHANDLE hInstall)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update`

## callees

- `0x100026eb`
- `0x10002f38`
- `0x1000d4ae`
- `0x1000d51f`
- `0x1000da66`

## string_xrefs

- `0x10002f3d`: `WixQueryOsWellKnownSID`
- `0x10002f52`: `WixQueryOsWellKnownSID failed to initialize`
- `0x10002f73`: `WIX_ACCOUNT_LOCALSERVICE`
- `0x10002f80`: `WIX_ACCOUNT_NETWORKSERVICE`

## pseudocode

```c
int __stdcall WixQueryOsWellKnownSID(MSIHANDLE hInstall)
{
  int v1; // edi
  int v2; // eax
  int v3; // esi

  v1 = 0;
  v2 = sub_1000D51F(hInstall, (int)"WixQueryOsWellKnownSID");
  v3 = v2;
  if ( v2 >= 0 )
  {
    sub_100026EB(WinLocalSystemSid, L"WIX_ACCOUNT_LOCALSYSTEM", 1);
    sub_100026EB(WinLocalServiceSid, L"WIX_ACCOUNT_LOCALSERVICE", 1);
    sub_100026EB(WinNetworkServiceSid, L"WIX_ACCOUNT_NETWORKSERVICE", 1);
    sub_100026EB(WinBuiltinAdministratorsSid, L"WIX_ACCOUNT_ADMINISTRATORS", 1);
    sub_100026EB(WinBuiltinUsersSid, L"WIX_ACCOUNT_USERS", 1);
    sub_100026EB(WinBuiltinGuestsSid, L"WIX_ACCOUNT_GUESTS", 1);
    sub_100026EB(WinBuiltinPerfLoggingUsersSid, L"WIX_ACCOUNT_PERFLOGUSERS", 1);
    sub_100026EB(WinBuiltinPerfLoggingUsersSid, L"WIX_ACCOUNT_PERFLOGUSERS_NODOMAIN", 0);
  }
  else
  {
    sub_1000DA66(v2, "WixQueryOsWellKnownSID failed to initialize");
  }
  if ( v3 < 0 )
    v1 = 1603;
  return sub_1000D4AE(v1);
}

```

## disassembly

```asm
0x10002f38  push    ebp
0x10002f39  mov     ebp, esp
0x10002f3b  push    esi
0x10002f3c  push    edi
0x10002f3d  push    offset aWixqueryoswell_0; "WixQueryOsWellKnownSID"
0x10002f42  push    [ebp+hInstall]; hInstall
0x10002f45  xor     edi, edi
0x10002f47  call    sub_1000D51F
0x10002f4c  mov     esi, eax
0x10002f4e  test    esi, esi
0x10002f50  jns     short loc_10002F61
0x10002f52  push    offset aWixqueryoswell_1; "WixQueryOsWellKnownSID failed to initia"...
0x10002f57  push    esi
0x10002f58  call    sub_1000DA66
0x10002f5d  pop     ecx
0x10002f5e  pop     ecx
0x10002f5f  jmp     short loc_10002FCE
0x10002f61  push    ebx
0x10002f62  xor     ebx, ebx
0x10002f64  inc     ebx
0x10002f65  push    ebx; int
0x10002f66  push    offset aWixAccountLoca; "WIX_ACCOUNT_LOCALSYSTEM"
0x10002f6b  push    16h; WellKnownSidType
0x10002f6d  call    sub_100026EB
0x10002f72  push    ebx; int
0x10002f73  push    offset aWixAccountLoca_0; "WIX_ACCOUNT_LOCALSERVICE"
0x10002f78  push    17h; WellKnownSidType
0x10002f7a  call    sub_100026EB
0x10002f7f  push    ebx; int
0x10002f80  push    offset aWixAccountNetw; "WIX_ACCOUNT_NETWORKSERVICE"
0x10002f85  push    18h; WellKnownSidType
0x10002f87  call    sub_100026EB
0x10002f8c  push    ebx; int
0x10002f8d  push    offset aWixAccountAdmi; "WIX_ACCOUNT_ADMINISTRATORS"
0x10002f92  push    1Ah; WellKnownSidType
0x10002f94  call    sub_100026EB
0x10002f99  push    ebx; int
0x10002f9a  push    offset aWixAccountUser; "WIX_ACCOUNT_USERS"
0x10002f9f  push    1Bh; WellKnownSidType
0x10002fa1  call    sub_100026EB
0x10002fa6  push    ebx; int
0x10002fa7  push    offset aWixAccountGues; "WIX_ACCOUNT_GUESTS"
0x10002fac  push    1Ch; WellKnownSidType
0x10002fae  call    sub_100026EB
0x10002fb3  push    ebx; int
0x10002fb4  push    offset aWixAccountPerf; "WIX_ACCOUNT_PERFLOGUSERS"
0x10002fb9  push    3Ah ; ':'; WellKnownSidType
0x10002fbb  call    sub_100026EB
0x10002fc0  push    edi; int
0x10002fc1  push    offset aWixAccountPerf_0; "WIX_ACCOUNT_PERFLOGUSERS_NODOMAIN"
0x10002fc6  push    3Ah ; ':'; WellKnownSidType
0x10002fc8  call    sub_100026EB
0x10002fcd  pop     ebx
0x10002fce  test    esi, esi
0x10002fd0  jns     short loc_10002FD7
0x10002fd2  mov     edi, 643h
0x10002fd7  push    edi
0x10002fd8  call    sub_1000D4AE
0x10002fdd  pop     edi
0x10002fde  pop     esi
0x10002fdf  pop     ebp
0x10002fe0  retn    4
```
