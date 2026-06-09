# FSMUpdateLastGeneratedLiveKernelDumpTime(_FSM_REGPATHLOOKUPKEY)

- ea: `0x1800265ac`
- end: `0x18002684a`
- name: `?FSMUpdateLastGeneratedLiveKernelDumpTime@@YAJW4_FSM_REGPATHLOOKUPKEY@@@Z`
- size: `670`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007c84`

## callees

- `0x180006a98`
- `0x18000b388`
- `0x18000c684`
- `0x18000d3b0`
- `0x18000d3d8`
- `0x18000e6bc`
- `0x180017b98`
- `0x1800265ac`
- `0x180027a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002663e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002663e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002671f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002671f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800267b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800267b1`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026766`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026766`

## pseudocode

```c
__int64 FSMUpdateLastGeneratedLiveKernelDumpTime()
{
  struct _FSM_REGPATHLOOKUPREGPATHMAP near **v0; // rdi
  signed int v1; // ebx
  __int64 v2; // rdx
  int v3; // eax
  LSTATUS v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  LSTATUS v7; // eax
  __int64 v8; // rdx
  void **v10; // [rsp+50h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+28h] BYREF
  __int64 Data; // [rsp+A0h] [rbp+30h] BYREF

  hKey = 0;
  v0 = &g_regkeynumMap;
  Data = 0;
  do
  {
    if ( !*(_DWORD *)v0 )
      break;
    v0 += 4;
  }
  while ( v0 != (struct _FSM_REGPATHLOOKUPREGPATHMAP near **)&wil::details::g_processLocalData );
  if ( v0 == (struct _FSM_REGPATHLOOKUPREGPATHMAP near **)&wil::details::g_processLocalData )
  {
    v1 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_29;
    v2 = 64;
    goto LABEL_28;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v0[3], 0, 0x2001Fu, &hKey) )
  {
    v10 = &AutoSecurityAttributes::`vftable';
    memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
    v3 = AutoSecurityAttributes::Set(
           (AutoSecurityAttributes *)&v10,
           L"D:(A;;GASDWDWO;;;BA)(A;;GASDWDWO;;;SU)(A;;GASDWDWO;;;SY)");
    v1 = v3;
    if ( v3 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v3);
LABEL_11:
      v10 = &AutoSecurityAttributes::`vftable';
      AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v10);
      goto LABEL_29;
    }
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 66, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v0[3], 0, 0, 0, 0x2001Fu, &SecurityAttributes, &hKey, 0);
    v1 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v1 = (unsigned __int16)v4 | 0x80070000;
      if ( v1 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v1);
        goto LABEL_11;
      }
    }
    v10 = &AutoSecurityAttributes::`vftable';
    AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v10);
  }
  GetSystemTimePreciseAsFileTime(&Data);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 27), v5, v6, Data);
  v7 = RegSetValueExW(hKey, L"LastRecordedDuration", 0, 0xBu, (const BYTE *)&Data, 8u);
  v1 = v7;
  if ( v7 > 0 )
    v1 = (unsigned __int16)v7 | 0x80070000;
  if ( v1 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_29;
    v2 = 69;
LABEL_28:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v1);
LABEL_29:
    if ( byte_18005E5A5 )
    {
      v8 = 71;
LABEL_33:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v8,
        &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
        (unsigned int)v1);
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v8 = 70;
    goto LABEL_33;
  }
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800265ac  mov     [rsp-18h+arg_0], rbx
0x1800265b1  mov     [rsp-18h+arg_18], rdi
0x1800265b6  push    rbp
0x1800265b7  push    r14
0x1800265b9  push    r15
0x1800265bb  mov     rbp, rsp
0x1800265be  sub     rsp, 70h
0x1800265c2  mov     [rbp+hKey], 0
0x1800265ca  lea     rdi, ?g_regkeynumMap@@3PAU_FSM_REGPATHLOOKUPREGPATHMAP@@A; _FSM_REGPATHLOOKUPREGPATHMAP near * g_regkeynumMap
0x1800265d1  mov     [rbp+Data], 0
0x1800265d9  lea     rax, ?g_processLocalData@details@wil@@3V?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@2@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> wil::details::g_processLocalData
0x1800265e0  cmp     dword ptr [rdi], 0
0x1800265e3  jz      short loc_1800265EE
0x1800265e5  add     rdi, 20h ; ' '
0x1800265e9  cmp     rdi, rax
0x1800265ec  jnz     short loc_1800265E0
0x1800265ee  lea     r14, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x1800265f5  cmp     rdi, rax
0x1800265f8  jnz     short loc_180026616
0x1800265fa  mov     ebx, 80070057h
0x1800265ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026606  jb      loc_1800267F2
0x18002660c  mov     edx, 40h ; '@'
0x180026611  jmp     loc_1800267D8
0x180026616  xor     edx, edx
0x180026618  lea     rcx, [rbp+hKey]
0x18002661c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180026621  mov     rdx, [rdi+18h]; lpSubKey
0x180026625  lea     rax, [rbp+hKey]
0x180026629  mov     r9d, 2001Fh; samDesired
0x18002662f  mov     [rsp+70h+phkResult], rax; phkResult
0x180026634  xor     r8d, r8d; ulOptions
0x180026637  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002663e  call    cs:__imp_RegOpenKeyExW
0x180026644  test    eax, eax
0x180026646  jz      loc_180026762
0x18002664c  xorps   xmm0, xmm0
0x18002664f  lea     r15, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180026656  xor     eax, eax
0x180026658  mov     [rbp+var_20], r15
0x18002665c  lea     rdx, StringSecurityDescriptor; "D:(A;;GASDWDWO;;;BA)(A;;GASDWDWO;;;SU)("...
0x180026663  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180026667  lea     rcx, [rbp+var_20]; this
0x18002666b  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18002666f  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x180026674  mov     ebx, eax
0x180026676  test    eax, eax
0x180026678  jns     short loc_1800266B4
0x18002667a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026681  jb      short loc_1800266A2
0x180026683  mov     edx, 41h ; 'A'
0x180026688  mov     dword ptr [rsp+70h+phkResult], eax
0x18002668c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026693  xor     r9d, r9d
0x180026696  mov     r8, r14
0x180026699  mov     rcx, [rcx+10h]
0x18002669d  call    WPP_SF_qD
0x1800266a2  lea     rcx, [rbp+var_20]; this
0x1800266a6  mov     [rbp+var_20], r15
0x1800266aa  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x1800266af  jmp     loc_1800267F2
0x1800266b4  cmp     cs:byte_18005E5A5, 8
0x1800266bb  jb      short loc_1800266D8
0x1800266bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266c4  mov     edx, 42h ; 'B'
0x1800266c9  mov     r8, r14
0x1800266cc  mov     rcx, [rcx+0D8h]
0x1800266d3  call    WPP_SF_
0x1800266d8  xor     edx, edx
0x1800266da  lea     rcx, [rbp+hKey]
0x1800266de  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800266e3  mov     rdx, [rdi+18h]; lpSubKey
0x1800266e7  lea     rax, [rbp+hKey]
0x1800266eb  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x1800266f4  xor     r9d, r9d; lpClass
0x1800266f7  mov     [rsp+70h+var_38], rax; phkResult
0x1800266fc  xor     r8d, r8d; Reserved
0x1800266ff  lea     rax, [rbp+SecurityAttributes]
0x180026703  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002670a  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002670f  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180026717  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x18002671f  call    cs:__imp_RegCreateKeyExW
0x180026725  mov     ebx, eax
0x180026727  test    eax, eax
0x180026729  jz      short loc_180026755
0x18002672b  jle     short loc_180026736
0x18002672d  movzx   ebx, ax
0x180026730  or      ebx, 80070000h
0x180026736  test    ebx, ebx
0x180026738  jns     short loc_180026755
0x18002673a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026741  jb      loc_1800266A2
0x180026747  mov     edx, 43h ; 'C'
0x18002674c  mov     dword ptr [rsp+70h+phkResult], ebx
0x180026750  jmp     loc_18002668C
0x180026755  lea     rcx, [rbp+var_20]; this
0x180026759  mov     [rbp+var_20], r15
0x18002675d  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180026762  lea     rcx, [rbp+Data]
0x180026766  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18002676c  cmp     cs:byte_18005E5A5, 8
0x180026773  jb      short loc_18002678C
0x180026775  mov     rcx, cs:WPP_GLOBAL_Control
0x18002677c  mov     r9, [rbp+Data]
0x180026780  mov     rcx, [rcx+0D8h]
0x180026787  call    WPP_SF_i
0x18002678c  mov     rcx, [rbp+hKey]; hKey
0x180026790  lea     rax, [rbp+Data]
0x180026794  mov     [rsp+70h+samDesired], 8; cbData
0x18002679c  lea     rdx, ValueName; "LastRecordedDuration"
0x1800267a3  mov     r9d, 0Bh; dwType
0x1800267a9  mov     [rsp+70h+phkResult], rax; lpData
0x1800267ae  xor     r8d, r8d; Reserved
0x1800267b1  call    cs:__imp_RegSetValueExW
0x1800267b7  mov     ebx, eax
0x1800267b9  test    eax, eax
0x1800267bb  jle     short loc_1800267C6
0x1800267bd  movzx   ebx, ax
0x1800267c0  or      ebx, 80070000h
0x1800267c6  test    ebx, ebx
0x1800267c8  jns     short loc_180026802
0x1800267ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800267d1  jb      short loc_1800267F2
0x1800267d3  mov     edx, 45h ; 'E'
0x1800267d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267df  xor     r9d, r9d
0x1800267e2  mov     r8, r14
0x1800267e5  mov     dword ptr [rsp+70h+phkResult], ebx
0x1800267e9  mov     rcx, [rcx+10h]
0x1800267ed  call    WPP_SF_qD
0x1800267f2  cmp     cs:byte_18005E5A5, 1
0x1800267f9  jb      short loc_180026829
0x1800267fb  mov     edx, 47h ; 'G'
0x180026800  jmp     short loc_180026810
0x180026802  cmp     cs:byte_18005E5A5, 8
0x180026809  jb      short loc_180026829
0x18002680b  mov     edx, 46h ; 'F'
0x180026810  mov     rcx, cs:WPP_GLOBAL_Control
0x180026817  mov     r9d, ebx
0x18002681a  mov     r8, r14
0x18002681d  mov     rcx, [rcx+0D8h]
0x180026824  call    WPP_SF_d
0x180026829  lea     rcx, [rbp+hKey]
0x18002682d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026832  lea     r11, [rsp+70h+var_s0]
0x180026837  mov     eax, ebx
0x180026839  mov     rbx, [r11+20h]
0x18002683d  mov     rdi, [r11+38h]
0x180026841  mov     rsp, r11
0x180026844  pop     r15
0x180026846  pop     r14
0x180026848  pop     rbp
0x180026849  retn
```
