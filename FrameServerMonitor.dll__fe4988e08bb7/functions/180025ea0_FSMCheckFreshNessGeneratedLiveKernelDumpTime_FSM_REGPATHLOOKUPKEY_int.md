# FSMCheckFreshNessGeneratedLiveKernelDumpTime(_FSM_REGPATHLOOKUPKEY,int &)

- ea: `0x180025ea0`
- end: `0x180026155`
- name: `?FSMCheckFreshNessGeneratedLiveKernelDumpTime@@YAJW4_FSM_REGPATHLOOKUPKEY@@AEAH@Z`
- size: `693`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007c84`

## callees

- `0x180006a98`
- `0x18000d3d8`
- `0x18000e6bc`
- `0x180017b98`
- `0x180025ea0`
- `0x180027aa8`
- `0x180027b00`
- `0x180027b54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025f83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025fca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025f83`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180025fca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f43`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026011`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180026011`

## pseudocode

```c
__int64 __fastcall FSMCheckFreshNessGeneratedLiveKernelDumpTime(__int64 a1, _DWORD *a2)
{
  struct _FSM_REGPATHLOOKUPREGPATHMAP near **v3; // rbx
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  const WCHAR *v7; // r8
  int ValueW; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  unsigned __int64 v13; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+80h] [rbp+30h] BYREF
  struct _FSM_REGPATHLOOKUPREGPATHMAP near *pvData; // [rsp+88h] [rbp+38h] BYREF

  hkey = 0;
  pvData = 0;
  v3 = &g_regkeynumMap;
  v13 = 0;
  pcbData = 0;
  v14 = 0;
  do
  {
    if ( !*(_DWORD *)v3 )
      break;
    v3 += 4;
  }
  while ( v3 != (struct _FSM_REGPATHLOOKUPREGPATHMAP near **)&wil::details::g_processLocalData );
  if ( v3 == (struct _FSM_REGPATHLOOKUPREGPATHMAP near **)&wil::details::g_processLocalData )
  {
    v4 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_23;
    v5 = 57;
    goto LABEL_22;
  }
  *a2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v3[3], 0, 0x20019u, &hkey);
  if ( v6 )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        61,
        &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
        (unsigned int)v6);
    }
    goto LABEL_29;
  }
  v7 = (const WCHAR *)v3[2];
  pcbData = 8;
  if ( RegGetValueW(hkey, 0, v7, 0x40u, 0, &pvData, &pcbData) )
    pvData = v3[1];
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"LastRecordedDuration", 0x40u, 0, &v13, &pcbData);
  if ( ValueW )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      WPP_SF_iD(*((_QWORD *)WPP_GLOBAL_Control + 27), v9, v10, pvData, ValueW);
    }
LABEL_29:
    v4 = 0;
    *a2 = 0;
    goto LABEL_30;
  }
  GetSystemTimePreciseAsFileTime(&v14);
  if ( v14 < v13 )
  {
    v4 = -2147024362;
    if ( !g_wppLevels )
      goto LABEL_23;
    v5 = 59;
LABEL_22:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, 0, v4);
LABEL_23:
    if ( byte_18005E5A5 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 63, &WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids, v4);
    goto LABEL_34;
  }
  v4 = 0;
  if ( v14 - v13 >= (unsigned __int64)pvData )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 27));
    *a2 = 0;
  }
LABEL_30:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v11 = "yes";
    if ( !*a2 )
      v11 = "no";
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      62,
      (unsigned int)&WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids,
      (_DWORD)v11,
      0);
  }
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v4;
}

```

## disassembly

```asm
0x180025ea0  mov     [rsp-18h+arg_0], ecx
0x180025ea4  push    rbp
0x180025ea5  push    rbx
0x180025ea6  push    rsi
0x180025ea7  mov     rbp, rsp
0x180025eaa  sub     rsp, 50h
0x180025eae  mov     rsi, rdx
0x180025eb1  mov     [rbp+hkey], 0
0x180025eb9  mov     [rbp+arg_18], 0
0x180025ec1  lea     rbx, ?g_regkeynumMap@@3PAU_FSM_REGPATHLOOKUPREGPATHMAP@@A; _FSM_REGPATHLOOKUPREGPATHMAP near * g_regkeynumMap
0x180025ec8  mov     [rbp+var_10], 0
0x180025ed0  lea     rax, ?g_processLocalData@details@wil@@3V?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@2@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> wil::details::g_processLocalData
0x180025ed7  mov     [rbp+arg_0], 0
0x180025ede  mov     [rbp+var_8], 0
0x180025ee6  cmp     dword ptr [rbx], 0
0x180025ee9  jz      short loc_180025EF4
0x180025eeb  add     rbx, 20h ; ' '
0x180025eef  cmp     rbx, rax
0x180025ef2  jnz     short loc_180025EE6
0x180025ef4  cmp     rbx, rax
0x180025ef7  jnz     short loc_180025F15
0x180025ef9  mov     ebx, 80070057h
0x180025efe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025f05  jb      loc_18002608D
0x180025f0b  mov     edx, 39h ; '9'
0x180025f10  jmp     loc_18002606F
0x180025f15  mov     dword ptr [rdx], 1
0x180025f1b  lea     rcx, [rbp+hkey]
0x180025f1f  xor     edx, edx
0x180025f21  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180025f26  mov     rdx, [rbx+18h]; lpSubKey
0x180025f2a  lea     rax, [rbp+hkey]
0x180025f2e  mov     r9d, 20019h; samDesired
0x180025f34  mov     [rsp+50h+phkResult], rax; phkResult
0x180025f39  xor     r8d, r8d; ulOptions
0x180025f3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025f43  call    cs:__imp_RegOpenKeyExW
0x180025f49  test    eax, eax
0x180025f4b  jnz     loc_1800260C1
0x180025f51  mov     r8, [rbx+10h]; lpValue
0x180025f55  lea     rax, [rbp+arg_0]
0x180025f59  mov     rcx, [rbp+hkey]; hkey
0x180025f5d  mov     r9d, 40h ; '@'; dwFlags
0x180025f63  mov     [rsp+50h+pcbData], rax; pcbData
0x180025f68  xor     edx, edx; lpSubKey
0x180025f6a  lea     rax, [rbp+arg_18]
0x180025f6e  mov     [rbp+arg_0], 8
0x180025f75  mov     [rsp+50h+pvData], rax; pvData
0x180025f7a  mov     [rsp+50h+phkResult], 0; pdwType
0x180025f83  call    cs:__imp_RegGetValueW
0x180025f89  test    eax, eax
0x180025f8b  jz      short loc_180025F95
0x180025f8d  mov     rax, [rbx+8]
0x180025f91  mov     [rbp+arg_18], rax
0x180025f95  mov     rcx, [rbp+hkey]; hkey
0x180025f99  lea     rax, [rbp+arg_0]
0x180025f9d  mov     [rsp+50h+pcbData], rax; pcbData
0x180025fa2  lea     r8, ValueName; "LastRecordedDuration"
0x180025fa9  lea     rax, [rbp+var_10]
0x180025fad  mov     [rbp+arg_0], 8
0x180025fb4  mov     [rsp+50h+pvData], rax; pvData
0x180025fb9  mov     r9d, 40h ; '@'; dwFlags
0x180025fbf  xor     edx, edx; lpSubKey
0x180025fc1  mov     [rsp+50h+phkResult], 0; pdwType
0x180025fca  call    cs:__imp_RegGetValueW
0x180025fd0  test    eax, eax
0x180025fd2  jz      short loc_18002600D
0x180025fd4  cmp     cs:byte_18005E5A5, 8
0x180025fdb  jb      loc_1800260F8
0x180025fe1  test    eax, eax
0x180025fe3  jle     short loc_180025FED
0x180025fe5  movzx   eax, ax
0x180025fe8  or      eax, 80070000h
0x180025fed  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ff4  mov     r9, [rbp+arg_18]
0x180025ff8  mov     dword ptr [rsp+50h+phkResult], eax
0x180025ffc  mov     rcx, [rcx+0D8h]
0x180026003  call    WPP_SF_iD
0x180026008  jmp     loc_1800260F8
0x18002600d  lea     rcx, [rbp+var_8]
0x180026011  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180026017  mov     r9, [rbp+var_8]
0x18002601b  cmp     r9, [rbp+var_10]
0x18002601f  jb      short loc_18002605C
0x180026021  sub     r9, [rbp+var_10]
0x180026025  xor     ebx, ebx
0x180026027  mov     rax, [rbp+arg_18]
0x18002602b  cmp     r9, rax
0x18002602e  jb      loc_180026101
0x180026034  cmp     cs:byte_18005E5A5, 8
0x18002603b  jb      short loc_180026055
0x18002603d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026044  mov     [rsp+50h+phkResult], rax
0x180026049  mov     rcx, [rcx+0D8h]
0x180026050  call    WPP_SF_ii
0x180026055  mov     [rsi], ebx
0x180026057  jmp     loc_180026101
0x18002605c  mov     ebx, 80070216h
0x180026061  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180026068  jb      short loc_18002608D
0x18002606a  mov     edx, 3Bh ; ';'
0x18002606f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026076  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x18002607d  xor     r9d, r9d
0x180026080  mov     dword ptr [rsp+50h+phkResult], ebx
0x180026084  mov     rcx, [rcx+10h]
0x180026088  call    WPP_SF_qD
0x18002608d  cmp     cs:byte_18005E5A5, 1
0x180026094  jb      loc_180026142
0x18002609a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260a1  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x1800260a8  mov     edx, 3Fh ; '?'
0x1800260ad  mov     r9d, ebx
0x1800260b0  mov     rcx, [rcx+0D8h]
0x1800260b7  call    WPP_SF_d
0x1800260bc  jmp     loc_180026142
0x1800260c1  cmp     cs:byte_18005E5A5, 8
0x1800260c8  jb      short loc_1800260F8
0x1800260ca  test    eax, eax
0x1800260cc  jle     short loc_1800260D6
0x1800260ce  movzx   eax, ax
0x1800260d1  or      eax, 80070000h
0x1800260d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260dd  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x1800260e4  mov     edx, 3Dh ; '='
0x1800260e9  mov     r9d, eax
0x1800260ec  mov     rcx, [rcx+0D8h]
0x1800260f3  call    WPP_SF_d
0x1800260f8  xor     ebx, ebx
0x1800260fa  mov     rcx, rsi
0x1800260fd  xor     eax, eax
0x1800260ff  mov     [rcx], eax
0x180026101  cmp     cs:byte_18005E5A5, 8
0x180026108  jb      short loc_180026142
0x18002610a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026111  lea     rax, aNo; "no"
0x180026118  cmp     dword ptr [rsi], 0
0x18002611b  lea     r9, aYes; "yes"
0x180026122  mov     edx, 3Eh ; '>'
0x180026127  mov     dword ptr [rsp+50h+phkResult], ebx
0x18002612b  cmovz   r9, rax
0x18002612f  lea     r8, WPP_b99fe746eab2377d4e74f881e2eae996_Traceguids
0x180026136  mov     rcx, [rcx+0D8h]
0x18002613d  call    WPP_SF_sD
0x180026142  lea     rcx, [rbp+hkey]
0x180026146  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002614b  mov     eax, ebx
0x18002614d  add     rsp, 50h
0x180026151  pop     rsi
0x180026152  pop     rbx
0x180026153  pop     rbp
0x180026154  retn
```
