# AiSvcpGroupPolicyChangedCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180003590`
- end: `0x1800037d0`
- name: `?AiSvcpGroupPolicyChangedCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `576`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003268`
- `0x180003590`
- `0x1800048b4`
- `0x18000493c`
- `0x1800049a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800037ba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800037ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800036f2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800036f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000360f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000360f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003684`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003684`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003783`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003774`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003783`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003744`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003744`

## pseudocode

```c
void __fastcall AiSvcpGroupPolicyChangedCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  LSTATUS v4; // eax
  __int64 v5; // rdx
  int v6; // r8d
  _QWORD *v7; // rcx
  int v8; // edx
  LSTATUS v9; // eax
  int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // r8
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp+7h] BYREF
  HKEY v14; // [rsp+68h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+17h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids,
      "AiSvcpGroupPolicyChangedCallback");
  hKey = 0;
  v14 = 0;
  ftLastWriteTime = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\SrpV2", 0, 0x20019u, &hKey);
  if ( (v4 & 0xFFFFFFFD) != 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v8 = 35;
LABEL_8:
      WPP_SF_dS(v7[2], v8, v6, v4, (__int64)L"Software\\Policies\\Microsoft\\Windows\\SrpV2");
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  v9 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Srp\\GP\\",
         0,
         0,
         0,
         0x20006u,
         0,
         &v14,
         0);
  if ( v9 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      v10,
      v9,
      (__int64)L"System\\CurrentControlSet\\Control\\Srp\\GP\\");
  if ( !hKey )
  {
    ftLastWriteTime = (struct _FILETIME)1LL;
    goto LABEL_19;
  }
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
  if ( !v4 )
  {
LABEL_19:
    v11 = RegSetValueExW(v14, L"LastGpNotifyTime", 0, 0xBu, (const BYTE *)&ftLastWriteTime, 8u);
    if ( v11
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v12, v11);
    }
    goto LABEL_23;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    v8 = 37;
    goto LABEL_8;
  }
LABEL_23:
  if ( v14 )
    RegCloseKey(v14);
  if ( hKey )
    RegCloseKey(hKey);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)&AiSvcpBootDelayFired, 0, 0) == 1 )
    AiSvcpEnableRunTask(L"PolicyConverter", v5, 1);
  SetThreadpoolWait(AiSvcpGroupPolicyWaitObject, AiSvcpGroupPolicyChangeEvent, 0);
}

```

## disassembly

```asm
0x180003590  push    rbp
0x180003592  push    rbx
0x180003593  push    rsi
0x180003594  push    rdi
0x180003595  push    r13
0x180003597  push    r15
0x180003599  lea     rbp, [rsp-2Fh]
0x18000359e  sub     rsp, 88h
0x1800035a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035ac  lea     rsi, WPP_GLOBAL_Control
0x1800035b3  mov     edi, 400h
0x1800035b8  cmp     rcx, rsi
0x1800035bb  jz      short loc_1800035DE
0x1800035bd  test    [rcx+1Ch], edi
0x1800035c0  jz      short loc_1800035DE
0x1800035c2  mov     rcx, [rcx+10h]
0x1800035c6  lea     r9, aAisvcpgrouppol; "AiSvcpGroupPolicyChangedCallback"
0x1800035cd  mov     edx, 22h ; '"'
0x1800035d2  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x1800035d9  call    WPP_SF_s
0x1800035de  xor     ebx, ebx
0x1800035e0  lea     rax, [rbp+57h+hKey]
0x1800035e4  lea     r15, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800035eb  mov     [rbp+57h+hKey], rbx
0x1800035ef  mov     rdx, r15; lpSubKey
0x1800035f2  mov     [rbp+57h+var_48], rbx
0x1800035f6  mov     r9d, 20019h; samDesired
0x1800035fc  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], rbx
0x180003600  xor     r8d, r8d; ulOptions
0x180003603  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180003608  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000360f  call    cs:__imp_RegOpenKeyExW
0x180003615  test    eax, 0FFFFFFFDh
0x18000361a  jz      short loc_18000364E
0x18000361c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003623  cmp     rcx, rsi
0x180003626  jz      loc_18000376B
0x18000362c  test    [rcx+1Ch], edi
0x18000362f  jz      loc_18000376B
0x180003635  lea     edx, [rbx+23h]
0x180003638  mov     rcx, [rcx+10h]
0x18000363c  mov     r9d, eax
0x18000363f  mov     [rsp+0B0h+phkResult], r15
0x180003644  call    WPP_SF_dS
0x180003649  jmp     loc_18000376B
0x18000364e  mov     [rsp+0B0h+lpdwDisposition], rbx; lpdwDisposition
0x180003653  lea     rax, [rbp+57h+var_48]
0x180003657  mov     [rsp+0B0h+var_78], rax; phkResult
0x18000365c  lea     r13, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Srp"...
0x180003663  mov     [rsp+0B0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180003668  xor     r9d, r9d; lpClass
0x18000366b  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x180003673  xor     r8d, r8d; Reserved
0x180003676  mov     rdx, r13; lpSubKey
0x180003679  mov     dword ptr [rsp+0B0h+phkResult], ebx; dwOptions
0x18000367d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180003684  call    cs:__imp_RegCreateKeyExW
0x18000368a  test    eax, eax
0x18000368c  jz      short loc_1800036B5
0x18000368e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003695  cmp     rcx, rsi
0x180003698  jz      short loc_1800036B5
0x18000369a  test    [rcx+1Ch], edi
0x18000369d  jz      short loc_1800036B5
0x18000369f  mov     rcx, [rcx+10h]
0x1800036a3  mov     edx, 24h ; '$'
0x1800036a8  mov     r9d, eax
0x1800036ab  mov     [rsp+0B0h+phkResult], r13
0x1800036b0  call    WPP_SF_dS
0x1800036b5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800036b9  test    rcx, rcx
0x1800036bc  jz      short loc_180003717
0x1800036be  lea     rax, [rbp+57h+ftLastWriteTime]
0x1800036c2  xor     r9d, r9d; lpReserved
0x1800036c5  mov     [rsp+0B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800036ca  xor     r8d, r8d; lpcchClass
0x1800036cd  mov     [rsp+0B0h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x1800036d2  xor     edx, edx; lpClass
0x1800036d4  mov     [rsp+0B0h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x1800036d9  mov     [rsp+0B0h+lpdwDisposition], rbx; lpcbMaxValueNameLen
0x1800036de  mov     [rsp+0B0h+var_78], rbx; lpcValues
0x1800036e3  mov     [rsp+0B0h+lpSecurityAttributes], rbx; lpcbMaxClassLen
0x1800036e8  mov     qword ptr [rsp+0B0h+samDesired], rbx; lpcbMaxSubKeyLen
0x1800036ed  mov     [rsp+0B0h+phkResult], rbx; lpcSubKeys
0x1800036f2  call    cs:__imp_RegQueryInfoKeyW
0x1800036f8  test    eax, eax
0x1800036fa  jz      short loc_18000371F
0x1800036fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003703  cmp     rcx, rsi
0x180003706  jz      short loc_18000376B
0x180003708  test    [rcx+1Ch], edi
0x18000370b  jz      short loc_18000376B
0x18000370d  mov     edx, 25h ; '%'
0x180003712  jmp     loc_180003638
0x180003717  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], 1
0x18000371f  mov     rcx, [rbp+57h+var_48]; hKey
0x180003723  lea     rax, [rbp+57h+ftLastWriteTime]
0x180003727  mov     [rsp+0B0h+samDesired], 8; cbData
0x18000372f  lea     rdx, ValueName; "LastGpNotifyTime"
0x180003736  mov     r9d, 0Bh; dwType
0x18000373c  mov     [rsp+0B0h+phkResult], rax; lpData
0x180003741  xor     r8d, r8d; Reserved
0x180003744  call    cs:__imp_RegSetValueExW
0x18000374a  test    eax, eax
0x18000374c  jz      short loc_18000376B
0x18000374e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003755  cmp     rcx, rsi
0x180003758  jz      short loc_18000376B
0x18000375a  test    [rcx+1Ch], edi
0x18000375d  jz      short loc_18000376B
0x18000375f  mov     rcx, [rcx+10h]
0x180003763  mov     r9d, eax
0x180003766  call    WPP_SF_dSS
0x18000376b  mov     rcx, [rbp+57h+var_48]; hKey
0x18000376f  test    rcx, rcx
0x180003772  jz      short loc_18000377A
0x180003774  call    cs:__imp_RegCloseKey
0x18000377a  mov     rcx, [rbp+57h+hKey]; hKey
0x18000377e  test    rcx, rcx
0x180003781  jz      short loc_180003789
0x180003783  call    cs:__imp_RegCloseKey
0x180003789  mov     ecx, ebx
0x18000378b  xor     eax, eax
0x18000378d  lock cmpxchg cs:?AiSvcpBootDelayFired@@3KA, ecx; ulong AiSvcpBootDelayFired
0x180003795  cmp     eax, 1
0x180003798  jnz     short loc_1800037A9
0x18000379a  mov     r8d, eax; unsigned int
0x18000379d  lea     rcx, aPolicyconverte; "PolicyConverter"
0x1800037a4  call    ?AiSvcpEnableRunTask@@YAKPEBGKK@Z; AiSvcpEnableRunTask(ushort const *,ulong,ulong)
0x1800037a9  mov     rdx, cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA; h
0x1800037b0  xor     r8d, r8d; pftTimeout
0x1800037b3  mov     rcx, cs:?AiSvcpGroupPolicyWaitObject@@3PEAU_TP_WAIT@@EA; pwa
0x1800037ba  call    cs:__imp_SetThreadpoolWait
0x1800037c0  add     rsp, 88h
0x1800037c7  pop     r15
0x1800037c9  pop     r13
0x1800037cb  pop     rdi
0x1800037cc  pop     rsi
0x1800037cd  pop     rbx
0x1800037ce  pop     rbp
0x1800037cf  retn
```
