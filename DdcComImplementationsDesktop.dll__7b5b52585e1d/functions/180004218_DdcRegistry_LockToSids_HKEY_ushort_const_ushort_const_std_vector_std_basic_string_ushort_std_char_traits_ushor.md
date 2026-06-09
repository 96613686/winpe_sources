# DdcRegistry::LockToSids(HKEY__ *,ushort const *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180004218`
- end: `0x180004505`
- name: `?LockToSids@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `749`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002f10`

## callees

- `0x1800026ac`
- `0x1800040b8`
- `0x180004218`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800043e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004428`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800043e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004428`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000449a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800042d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000449a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000426c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000426c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042a8`

## string_xrefs

- `0x18000425c`: `SYSTEM\CurrentControlSet\Control\Lsa\LockedDownSIDs`
- `0x1800043ab`: `SYSTEM\CurrentControlSet\Control\Lsa\LockedDownSIDs`
- `0x180004274`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`
- `0x180004306`: `CHR(DeleteKey(hKeyRoot, pwszRegistryKey))`
- `0x1800044cb`: `CHR(CreateKey(hKeyRoot, pwszRegistryKey, iter.c_str()))`

## pseudocode

```c
__int64 __fastcall DdcRegistry::LockToSids(__int64 a1, __int64 a2, const WCHAR *a3, __int64 *a4)
{
  int v6; // edi
  const unsigned __int16 *v7; // rdx
  int v8; // ecx
  int v9; // ebx
  LSTATUS v10; // eax
  int v11; // ecx
  HKEY v12; // rcx
  signed int v13; // ebx
  const unsigned __int16 *v14; // rdx
  HKEY v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // r14
  const WCHAR *v18; // rsi
  LSTATUS v19; // eax
  int v20; // ecx
  LSTATUS v21; // eax
  int v22; // ecx
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  v6 = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\LockedDownSIDs", 0, 0x20019u, &hKey);
  if ( v9 == 2 )
    goto LABEL_6;
  if ( v9 )
  {
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        (_DWORD)v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        56,
        (__int64)"CBR(dwResult == 0L)");
  }
  else
  {
    v10 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
    v9 = v10;
    if ( v10 == 2 )
    {
LABEL_6:
      v9 = 0;
      goto LABEL_7;
    }
    if ( !v10 )
    {
      v6 = 1;
      goto LABEL_6;
    }
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v11,
        (_DWORD)v7,
        v9,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        70,
        (__int64)"CBR(dwResult == 0L)");
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  v12 = phkResult;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v9 < 0 || (v13 = 0, !v6) )
  {
    v13 = DdcRegistry::DeleteKey(v12, v7);
    if ( v13 >= 0 )
    {
      v16 = *a4;
      v17 = a4[1];
      while ( v16 != v17 )
      {
        if ( *(_QWORD *)(v16 + 24) <= 7u )
          v18 = (const WCHAR *)v16;
        else
          v18 = *(const WCHAR **)v16;
        hKey = 0;
        phkResult = 0;
        v19 = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\LockedDownSIDs",
                0,
                0,
                0,
                4u,
                0,
                &hKey,
                0);
        v13 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v13 = (unsigned __int16)v19 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v20,
              (_DWORD)v14,
              v13,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
              187,
              (__int64)"CBR(dwResult == 0L)");
        }
        else
        {
          v21 = RegCreateKeyExW(hKey, v18, 0, 0, 0, 4u, 0, &phkResult, 0);
          v13 = v21;
          if ( v21 )
          {
            if ( v21 > 0 )
              v13 = (unsigned __int16)v21 | 0x80070000;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v22,
                (_DWORD)v14,
                v13,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
                200,
                (__int64)"CBR(dwResult == 0L)");
          }
        }
        if ( hKey )
          RegCloseKey(hKey);
        v15 = phkResult;
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( v13 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              (_DWORD)v15,
              (_DWORD)v14,
              v13,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
              111,
              (__int64)"CHR(CreateKey(hKeyRoot, pwszRegistryKey, iter.c_str()))");
          goto LABEL_49;
        }
        v16 += 32;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v15,
          (_DWORD)v14,
          v13,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          108,
          (__int64)"CHR(DeleteKey(hKeyRoot, pwszRegistryKey))");
LABEL_49:
      DdcRegistry::DeleteKey(v15, v14);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180004218  mov     r11, rsp
0x18000421b  mov     [r11+18h], rbx
0x18000421f  mov     [r11+10h], rdx
0x180004223  mov     [r11+8], rcx
0x180004227  push    rbp
0x180004228  push    rsi
0x180004229  push    rdi
0x18000422a  push    r13
0x18000422c  push    r14
0x18000422e  mov     rbp, rsp
0x180004231  sub     rsp, 50h
0x180004235  mov     r14, r9
0x180004238  mov     [rbp+hKey], 0
0x180004240  mov     rsi, r8
0x180004243  mov     [rbp+arg_0], 0
0x18000424b  lea     rax, [rbp+hKey]
0x18000424f  mov     r9d, 20019h; samDesired
0x180004255  xor     r8d, r8d; ulOptions
0x180004258  mov     [r11-58h], rax
0x18000425c  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x180004263  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000426a  xor     edi, edi
0x18000426c  call    cs:__imp_RegOpenKeyExW
0x180004272  mov     ebx, eax
0x180004274  lea     r13, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000427b  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x180004282  cmp     ebx, 2
0x180004285  jz      short loc_1800042BC
0x180004287  test    ebx, ebx
0x180004289  jnz     loc_180004349
0x18000428f  mov     rcx, [rbp+hKey]; hKey
0x180004293  lea     rax, [rbp+arg_0]
0x180004297  mov     r9d, 20019h; samDesired
0x18000429d  mov     [rsp+50h+phkResult], rax; phkResult
0x1800042a2  xor     r8d, r8d; ulOptions
0x1800042a5  mov     rdx, rsi; lpSubKey
0x1800042a8  call    cs:__imp_RegOpenKeyExW
0x1800042ae  mov     ebx, eax
0x1800042b0  cmp     eax, 2
0x1800042b3  jz      short loc_1800042BC
0x1800042b5  test    eax, eax
0x1800042b7  jnz     short loc_18000431F
0x1800042b9  lea     edi, [rax+1]
0x1800042bc  xor     ebx, ebx
0x1800042be  mov     rcx, [rbp+hKey]; hKey
0x1800042c2  test    rcx, rcx
0x1800042c5  jz      short loc_1800042CD
0x1800042c7  call    cs:__imp_RegCloseKey
0x1800042cd  mov     rcx, [rbp+arg_0]; hKey
0x1800042d1  test    rcx, rcx
0x1800042d4  jz      short loc_1800042DC
0x1800042d6  call    cs:__imp_RegCloseKey
0x1800042dc  test    ebx, ebx
0x1800042de  js      short loc_1800042EA
0x1800042e0  xor     ebx, ebx
0x1800042e2  test    edi, edi
0x1800042e4  jnz     loc_1800044EF
0x1800042ea  call    ?DeleteKey@DdcRegistry@@SAJPEAUHKEY__@@PEBG@Z; DdcRegistry::DeleteKey(HKEY__ *,ushort const *)
0x1800042ef  mov     ebx, eax
0x1800042f1  test    eax, eax
0x1800042f3  jns     loc_18000437E
0x1800042f9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004300  jz      loc_1800044EA
0x180004306  lea     rax, aChrDeletekeyHk; "CHR(DeleteKey(hKeyRoot, pwszRegistryKey"...
0x18000430d  mov     qword ptr [rsp+50h+samDesired], rax
0x180004312  mov     dword ptr [rsp+50h+phkResult], 36Ch
0x18000431a  jmp     loc_1800044DF
0x18000431f  jle     short loc_18000432A
0x180004321  movzx   ebx, ax
0x180004324  or      ebx, 80070000h
0x18000432a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004331  jz      short loc_1800042BE
0x180004333  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18000433a  mov     qword ptr [rsp+50h+samDesired], rax
0x18000433f  mov     dword ptr [rsp+50h+phkResult], 346h
0x180004347  jmp     short loc_18000436E
0x180004349  jle     short loc_180004354
0x18000434b  movzx   ebx, bx
0x18000434e  or      ebx, 80070000h
0x180004354  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000435b  jz      loc_1800042BE
0x180004361  mov     qword ptr [rsp+50h+samDesired], rax
0x180004366  mov     dword ptr [rsp+50h+phkResult], 338h
0x18000436e  mov     r9, r13
0x180004371  mov     r8d, ebx
0x180004374  call    McTemplateU0dsqs_EventWriteTransfer
0x180004379  jmp     loc_1800042BE
0x18000437e  mov     rdi, [r14]
0x180004381  mov     r14, [r14+8]
0x180004385  jmp     loc_1800044B7
0x18000438a  cmp     qword ptr [rdi+18h], 7
0x18000438f  jbe     short loc_180004396
0x180004391  mov     rsi, [rdi]
0x180004394  jmp     short loc_180004399
0x180004396  mov     rsi, rdi
0x180004399  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x1800043a2  lea     rax, [rbp+hKey]
0x1800043a6  mov     [rsp+50h+var_18], rax; phkResult
0x1800043ab  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800043b2  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800043bb  xor     r9d, r9d; lpClass
0x1800043be  mov     [rsp+50h+samDesired], 4; samDesired
0x1800043c6  xor     r8d, r8d; Reserved
0x1800043c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800043d0  mov     dword ptr [rsp+50h+phkResult], 0; dwOptions
0x1800043d8  mov     [rbp+hKey], 0
0x1800043e0  mov     [rbp+arg_0], 0
0x1800043e8  call    cs:__imp_RegCreateKeyExW
0x1800043ee  mov     ebx, eax
0x1800043f0  test    eax, eax
0x1800043f2  jnz     short loc_18000445E
0x1800043f4  mov     rcx, [rbp+hKey]; hKey
0x1800043f8  lea     rax, [rbp+arg_0]
0x1800043fc  mov     [rsp+50h+lpdwDisposition], 0; lpdwDisposition
0x180004405  xor     r9d, r9d; lpClass
0x180004408  mov     [rsp+50h+var_18], rax; phkResult
0x18000440d  xor     r8d, r8d; Reserved
0x180004410  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004419  mov     rdx, rsi; lpSubKey
0x18000441c  mov     [rsp+50h+samDesired], 4; samDesired
0x180004424  mov     dword ptr [rsp+50h+phkResult], ebx; dwOptions
0x180004428  call    cs:__imp_RegCreateKeyExW
0x18000442e  mov     ebx, eax
0x180004430  test    eax, eax
0x180004432  jz      short loc_180004491
0x180004434  jle     short loc_18000443F
0x180004436  movzx   ebx, ax
0x180004439  or      ebx, 80070000h
0x18000443f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004446  jz      short loc_180004491
0x180004448  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x18000444f  mov     qword ptr [rsp+50h+samDesired], rax
0x180004454  mov     dword ptr [rsp+50h+phkResult], 2C8h
0x18000445c  jmp     short loc_180004486
0x18000445e  jle     short loc_180004469
0x180004460  movzx   ebx, ax
0x180004463  or      ebx, 80070000h
0x180004469  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180004470  jz      short loc_180004491
0x180004472  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x180004479  mov     qword ptr [rsp+50h+samDesired], rax
0x18000447e  mov     dword ptr [rsp+50h+phkResult], 2BBh
0x180004486  mov     r9, r13
0x180004489  mov     r8d, ebx
0x18000448c  call    McTemplateU0dsqs_EventWriteTransfer
0x180004491  mov     rcx, [rbp+hKey]; hKey
0x180004495  test    rcx, rcx
0x180004498  jz      short loc_1800044A0
0x18000449a  call    cs:__imp_RegCloseKey
0x1800044a0  mov     rcx, [rbp+arg_0]; hKey
0x1800044a4  test    rcx, rcx
0x1800044a7  jz      short loc_1800044AF
0x1800044a9  call    cs:__imp_RegCloseKey
0x1800044af  test    ebx, ebx
0x1800044b1  js      short loc_1800044C2
0x1800044b3  add     rdi, 20h ; ' '
0x1800044b7  cmp     rdi, r14
0x1800044ba  jnz     loc_18000438A
0x1800044c0  jmp     short loc_1800044EF
0x1800044c2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800044c9  jz      short loc_1800044EA
0x1800044cb  lea     rax, aChrCreatekeyHk; "CHR(CreateKey(hKeyRoot, pwszRegistryKey"...
0x1800044d2  mov     qword ptr [rsp+50h+samDesired], rax
0x1800044d7  mov     dword ptr [rsp+50h+phkResult], 36Fh
0x1800044df  mov     r9, r13
0x1800044e2  mov     r8d, ebx
0x1800044e5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800044ea  call    ?DeleteKey@DdcRegistry@@SAJPEAUHKEY__@@PEBG@Z; DdcRegistry::DeleteKey(HKEY__ *,ushort const *)
0x1800044ef  mov     eax, ebx
0x1800044f1  mov     rbx, [rsp+50h+arg_10]
0x1800044f9  add     rsp, 50h
0x1800044fd  pop     r14
0x1800044ff  pop     r13
0x180004501  pop     rdi
0x180004502  pop     rsi
0x180004503  pop     rbp
0x180004504  retn
```
