# EfspMdmProvisionDpl(ushort const *)

- ea: `0x180040484`
- end: `0x18004095c`
- name: `?EfspMdmProvisionDpl@@YAJPEBG@Z`
- size: `1240`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180041c20`

## callees

- `0x1800124d8`
- `0x180015294`
- `0x180040054`
- `0x180040484`
- `0x180062860`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180082224`
- `0x180082508`
- `0x1800841d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040907`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040937`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040945`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040915`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040945`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040924`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004083b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18004083b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180040561`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180040561`

## string_xrefs

- `0x180040553`: `RequireProtectionUnderLockConfig`

## pseudocode

```c
__int64 __fastcall EfspMdmProvisionDpl(const unsigned __int16 *a1)
{
  int EdpEnforcementLevel; // ebx
  int v3; // ecx
  int v4; // esi
  unsigned int v5; // edi
  int PolicyInt; // ebx
  int AllIdentities; // ebx
  unsigned __int16 *v8; // rax
  int v9; // eax
  int v10; // ecx
  void *lpData; // rdi
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  HANDLE ProcessHeap; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 *v21; // [rsp+50h] [rbp-20h] BYREF
  LPCVOID v22; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+B8h] [rbp+48h] BYREF
  int v25; // [rsp+C0h] [rbp+50h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+58h] BYREF

  hKey = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  cbData = 0;
  v24 = 0;
  v25 = 0;
  lpMem = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 43);
  EdpEnforcementLevel = EdpGetEdpEnforcementLevel(&v25);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              EdpEnforcementLevel,
              32,
              43) >= 0 )
  {
    v4 = 0;
    v5 = 0;
    if ( v25 )
    {
      fnEfsLogTrace1Strings(v3, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 50);
      PolicyInt = PolicyManager_GetPolicyInt(L"DataProtection", L"RequireProtectionUnderLockConfig", &v24);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  PolicyInt,
                  32,
                  50) < 0 )
      {
        if ( (unsigned int)(PolicyInt + 2147024894) <= 1 || PolicyInt == -2147023728 )
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 32, 58);
        }
        else
        {
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_DPL_PROVISION_USER_ERROR, PolicyInt, 32, 67);
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 32, 68);
        }
      }
    }
    if ( v24 > 0 )
    {
      fnEfsLogTrace1Strings(v3, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 75);
      AllIdentities = MdmGetAllIdentities(&lpMem);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  AllIdentities,
                  32,
                  75) >= 0 )
      {
        v8 = (unsigned __int16 *)lpMem;
        if ( !lpMem )
          v24 = 0;
      }
      else
      {
        v24 = 0;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_DPL_PROVISION_USER_ERROR, AllIdentities, 32, 83);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 32, 84);
        v8 = (unsigned __int16 *)lpMem;
      }
      if ( v24 > 0 )
      {
        v21 = v8;
        v5 = 1;
        v4 = EdpCredSvcDplSetupProtector(a1);
      }
    }
    fnEfsLogTrace1Strings(v3, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 118);
    EdpEnforcementLevel = EfspMdmDplPolicyToConfig(&v21, v5, (unsigned __int8 **)&v22, &v23);
    v9 = fnEfsLogTrace1String1Dword(
           g_hPublisher,
           (unsigned int)EFS_TRACE_COMPLETE_EVENT,
           (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
           (unsigned int)&sourceString,
           EdpEnforcementLevel,
           32,
           118);
    lpData = (void *)v22;
    if ( v9 >= 0 )
    {
      fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 126);
      EdpEnforcementLevel = EdpCredSvcOpenUserCredStore(a1, 0xF003Fu, &hKey);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  EdpEnforcementLevel,
                  32,
                  126) >= 0 )
      {
        fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 128);
        EdpEnforcementLevel = ULongLongToULong(v23, &cbData);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    EdpEnforcementLevel,
                    32,
                    128) >= 0 )
        {
          EdpEnforcementLevel = RegSetKeyValueW(hKey, 0, L"DataProtectionUnderLockAccounts", 7u, lpData, cbData);
          fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 135);
          if ( EdpEnforcementLevel > 0 )
            EdpEnforcementLevel = (unsigned __int16)EdpEnforcementLevel | 0x80070000;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      EdpEnforcementLevel,
                      32,
                      135) >= 0 )
          {
            fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 137);
            EdpEnforcementLevel = v4;
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        v4,
                        32,
                        137) >= 0 )
              EdpCredSvcDplUserPolicyStateChange(a1);
          }
        }
      }
    }
    if ( lpData )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpData);
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
  }
  return (unsigned int)EdpEnforcementLevel;
}

```

## disassembly

```asm
0x180040484  push    rbp
0x180040486  push    rbx
0x180040487  push    rsi
0x180040488  push    rdi
0x180040489  push    r12
0x18004048b  push    r13
0x18004048d  push    r14
0x18004048f  mov     rbp, rsp
0x180040492  sub     rsp, 70h
0x180040496  xor     r12d, r12d
0x180040499  lea     r8, sourceString
0x1800404a0  mov     edi, 42Bh
0x1800404a5  mov     [rbp+hKey], r12
0x1800404a9  lea     rdx, EFS_TRACE_START_EVENT
0x1800404b0  mov     [rbp+var_20], r12
0x1800404b4  mov     r14, rcx
0x1800404b7  mov     [rbp+var_18], r12
0x1800404bb  lea     r13d, [r12+20h]
0x1800404c0  mov     [rbp+var_10], r12
0x1800404c4  mov     r9d, r13d
0x1800404c7  mov     [rbp+arg_18], r12d
0x1800404cb  mov     [rbp+arg_8], r12d
0x1800404cf  mov     [rbp+arg_10], r12d
0x1800404d3  mov     [rbp+lpMem], r12
0x1800404d7  mov     dword ptr [rsp+70h+lpData], edi
0x1800404db  call    fnEfsLogTrace1Strings
0x1800404e0  lea     rcx, [rbp+arg_10]
0x1800404e4  call    EdpGetEdpEnforcementLevel
0x1800404e9  mov     rcx, cs:g_hPublisher
0x1800404f0  lea     r9, sourceString
0x1800404f7  mov     [rsp+70h+var_40], edi
0x1800404fb  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180040502  mov     [rsp+70h+cbData], r13d
0x180040507  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18004050e  mov     dword ptr [rsp+70h+lpData], eax
0x180040512  mov     ebx, eax
0x180040514  call    fnEfsLogTrace1String1Dword
0x180040519  test    eax, eax
0x18004051b  js      loc_18004091B
0x180040521  mov     esi, r12d
0x180040524  mov     edi, r12d
0x180040527  cmp     [rbp+arg_10], r12d
0x18004052b  jz      loc_1800405FE
0x180040531  mov     r9d, r13d
0x180040534  mov     dword ptr [rsp+70h+lpData], 432h
0x18004053c  lea     r8, sourceString
0x180040543  lea     rdx, EFS_TRACE_START_EVENT
0x18004054a  call    fnEfsLogTrace1Strings
0x18004054f  lea     r8, [rbp+arg_8]
0x180040553  lea     rdx, aRequireprotect; "RequireProtectionUnderLockConfig"
0x18004055a  lea     rcx, aDataprotection; "DataProtection"
0x180040561  call    cs:__imp_PolicyManager_GetPolicyInt
0x180040567  mov     rcx, cs:g_hPublisher
0x18004056e  lea     r9, sourceString
0x180040575  mov     [rsp+70h+var_40], 432h
0x18004057d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180040584  mov     [rsp+70h+cbData], r13d
0x180040589  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180040590  mov     ebx, eax
0x180040592  mov     dword ptr [rsp+70h+lpData], eax
0x180040596  call    fnEfsLogTrace1String1Dword
0x18004059b  test    eax, eax
0x18004059d  jns     short loc_1800405FE
0x18004059f  lea     ecx, [rbx+7FF8FFFEh]
0x1800405a5  cmp     ecx, 1
0x1800405a8  jbe     short loc_1800405DD
0x1800405aa  cmp     ebx, 80070490h
0x1800405b0  jz      short loc_1800405DD
0x1800405b2  mov     rcx, cs:g_hPublisher
0x1800405b9  lea     rdx, EFS_SERVICE_DPL_PROVISION_USER_ERROR
0x1800405c0  mov     r9d, r13d
0x1800405c3  mov     dword ptr [rsp+70h+lpData], 443h
0x1800405cb  mov     r8d, ebx
0x1800405ce  call    fnEfsLogTrace1
0x1800405d3  mov     dword ptr [rsp+70h+lpData], 444h
0x1800405db  jmp     short loc_1800405E5
0x1800405dd  mov     dword ptr [rsp+70h+lpData], 43Ah
0x1800405e5  mov     rcx, cs:g_hPublisher
0x1800405ec  lea     rdx, EFS_TRACE_STATUS
0x1800405f3  mov     r9d, r13d
0x1800405f6  xor     r8d, r8d
0x1800405f9  call    fnEfsLogTrace1
0x1800405fe  cmp     [rbp+arg_8], r12d
0x180040602  jle     loc_1800406D9
0x180040608  mov     r9d, r13d
0x18004060b  mov     dword ptr [rsp+70h+lpData], 44Bh
0x180040613  lea     r8, sourceString
0x18004061a  lea     rdx, EFS_TRACE_START_EVENT
0x180040621  call    fnEfsLogTrace1Strings
0x180040626  lea     rcx, [rbp+lpMem]
0x18004062a  call    MdmGetAllIdentities
0x18004062f  mov     rcx, cs:g_hPublisher
0x180040636  lea     r9, sourceString
0x18004063d  mov     [rsp+70h+var_40], 44Bh
0x180040645  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18004064c  mov     [rsp+70h+cbData], r13d
0x180040651  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180040658  mov     dword ptr [rsp+70h+lpData], eax
0x18004065c  mov     ebx, eax
0x18004065e  call    fnEfsLogTrace1String1Dword
0x180040663  test    eax, eax
0x180040665  jns     short loc_1800406B3
0x180040667  mov     rcx, cs:g_hPublisher
0x18004066e  lea     rdx, EFS_SERVICE_DPL_PROVISION_USER_ERROR
0x180040675  mov     r9d, r13d
0x180040678  mov     [rbp+arg_8], r12d
0x18004067c  mov     r8d, ebx
0x18004067f  mov     dword ptr [rsp+70h+lpData], 453h
0x180040687  call    fnEfsLogTrace1
0x18004068c  mov     rcx, cs:g_hPublisher
0x180040693  lea     rdx, EFS_TRACE_STATUS
0x18004069a  mov     r9d, r13d
0x18004069d  mov     dword ptr [rsp+70h+lpData], 454h
0x1800406a5  xor     r8d, r8d
0x1800406a8  call    fnEfsLogTrace1
0x1800406ad  mov     rax, [rbp+lpMem]
0x1800406b1  jmp     short loc_1800406C0
0x1800406b3  mov     rax, [rbp+lpMem]
0x1800406b7  test    rax, rax
0x1800406ba  jnz     short loc_1800406C0
0x1800406bc  mov     [rbp+arg_8], r12d
0x1800406c0  cmp     [rbp+arg_8], r12d
0x1800406c4  jle     short loc_1800406D9
0x1800406c6  mov     rcx, r14; unsigned __int16 *
0x1800406c9  mov     [rbp+var_20], rax
0x1800406cd  mov     edi, 1
0x1800406d2  call    ?EdpCredSvcDplSetupProtector@@YAJPEBG@Z; EdpCredSvcDplSetupProtector(ushort const *)
0x1800406d7  mov     esi, eax
0x1800406d9  mov     r9d, r13d
0x1800406dc  mov     dword ptr [rsp+70h+lpData], 476h
0x1800406e4  lea     r8, sourceString
0x1800406eb  lea     rdx, EFS_TRACE_START_EVENT
0x1800406f2  call    fnEfsLogTrace1Strings
0x1800406f7  lea     r9, [rbp+var_10]; unsigned __int64 *
0x1800406fb  mov     edx, edi; unsigned int
0x1800406fd  lea     r8, [rbp+var_18]; unsigned __int8 **
0x180040701  lea     rcx, [rbp+var_20]; unsigned __int16 **
0x180040705  call    ?EfspMdmDplPolicyToConfig@@YAJPEAPEAGKPEAPEAEPEA_K@Z; EfspMdmDplPolicyToConfig(ushort * *,ulong,uchar * *,unsigned __int64 *)
0x18004070a  mov     rcx, cs:g_hPublisher
0x180040711  lea     r9, sourceString
0x180040718  mov     [rsp+70h+var_40], 476h
0x180040720  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180040727  mov     [rsp+70h+cbData], r13d
0x18004072c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180040733  mov     dword ptr [rsp+70h+lpData], eax
0x180040737  mov     ebx, eax
0x180040739  call    fnEfsLogTrace1String1Dword
0x18004073e  mov     rdi, [rbp+var_18]
0x180040742  test    eax, eax
0x180040744  js      loc_180040902
0x18004074a  mov     r9d, r13d
0x18004074d  mov     dword ptr [rsp+70h+lpData], 47Eh
0x180040755  lea     r8, sourceString
0x18004075c  lea     rdx, EFS_TRACE_START_EVENT
0x180040763  call    fnEfsLogTrace1Strings
0x180040768  lea     r8, [rbp+hKey]; phkResult
0x18004076c  mov     edx, 0F003Fh; samDesired
0x180040771  mov     rcx, r14; unsigned __int16 *
0x180040774  call    ?EdpCredSvcOpenUserCredStore@@YAJPEBGKPEAPEAUHKEY__@@@Z; EdpCredSvcOpenUserCredStore(ushort const *,ulong,HKEY__ * *)
0x180040779  mov     rcx, cs:g_hPublisher
0x180040780  lea     r9, sourceString
0x180040787  mov     [rsp+70h+var_40], 47Eh
0x18004078f  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180040796  mov     [rsp+70h+cbData], r13d
0x18004079b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800407a2  mov     dword ptr [rsp+70h+lpData], eax
0x1800407a6  mov     ebx, eax
0x1800407a8  call    fnEfsLogTrace1String1Dword
0x1800407ad  test    eax, eax
0x1800407af  js      loc_180040902
0x1800407b5  mov     r9d, r13d
0x1800407b8  mov     dword ptr [rsp+70h+lpData], 480h
0x1800407c0  lea     r8, sourceString
0x1800407c7  lea     rdx, EFS_TRACE_START_EVENT
0x1800407ce  call    fnEfsLogTrace1Strings
0x1800407d3  mov     rcx, [rbp+var_10]; unsigned __int64
0x1800407d7  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800407db  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800407e0  mov     rcx, cs:g_hPublisher
0x1800407e7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800407ee  mov     [rsp+70h+var_40], 480h
0x1800407f6  lea     r9, sourceString
0x1800407fd  mov     [rsp+70h+cbData], r13d
0x180040802  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180040809  mov     dword ptr [rsp+70h+lpData], eax
0x18004080d  mov     ebx, eax
0x18004080f  call    fnEfsLogTrace1String1Dword
0x180040814  test    eax, eax
0x180040816  js      loc_180040902
0x18004081c  mov     eax, [rbp+arg_18]
0x18004081f  lea     r8, aDataprotection_0; "DataProtectionUnderLockAccounts"
0x180040826  mov     rcx, [rbp+hKey]; hKey
0x18004082a  mov     r9d, 7; dwType
0x180040830  mov     [rsp+70h+cbData], eax; cbData
0x180040834  xor     edx, edx; lpSubKey
0x180040836  mov     [rsp+70h+lpData], rdi; lpData
0x18004083b  call    cs:__imp_RegSetKeyValueW
0x180040841  mov     r9d, r13d
0x180040844  mov     dword ptr [rsp+70h+lpData], 487h
0x18004084c  lea     r8, sourceString
0x180040853  mov     ebx, eax
0x180040855  lea     rdx, EFS_TRACE_START_EVENT
0x18004085c  call    fnEfsLogTrace1Strings
0x180040861  test    ebx, ebx
0x180040863  jle     short loc_18004086E
0x180040865  movzx   ebx, bx
0x180040868  or      ebx, 80070000h
0x18004086e  mov     rcx, cs:g_hPublisher
0x180040875  lea     r9, sourceString
0x18004087c  mov     [rsp+70h+var_40], 487h
0x180040884  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18004088b  mov     [rsp+70h+cbData], r13d
0x180040890  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180040897  mov     dword ptr [rsp+70h+lpData], ebx
0x18004089b  call    fnEfsLogTrace1String1Dword
0x1800408a0  test    eax, eax
0x1800408a2  js      short loc_180040902
0x1800408a4  mov     r9d, r13d
0x1800408a7  mov     dword ptr [rsp+70h+lpData], 489h
0x1800408af  lea     r8, sourceString
0x1800408b6  lea     rdx, EFS_TRACE_START_EVENT
0x1800408bd  call    fnEfsLogTrace1Strings
0x1800408c2  mov     rcx, cs:g_hPublisher
0x1800408c9  lea     r9, sourceString
0x1800408d0  mov     [rsp+70h+var_40], 489h
0x1800408d8  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800408df  mov     [rsp+70h+cbData], r13d
0x1800408e4  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800408eb  mov     dword ptr [rsp+70h+lpData], esi
0x1800408ef  mov     ebx, esi
0x1800408f1  call    fnEfsLogTrace1String1Dword
0x1800408f6  test    eax, eax
0x1800408f8  js      short loc_180040902
0x1800408fa  mov     rcx, r14; unsigned __int16 *
0x1800408fd  call    ?EdpCredSvcDplUserPolicyStateChange@@YAXPEBG@Z; EdpCredSvcDplUserPolicyStateChange(ushort const *)
0x180040902  test    rdi, rdi
0x180040905  jz      short loc_18004091B
0x180040907  call    cs:__imp_GetProcessHeap
0x18004090d  mov     r8, rdi; lpMem
0x180040910  xor     edx, edx; dwFlags
0x180040912  mov     rcx, rax; hHeap
0x180040915  call    cs:__imp_HeapFree
0x18004091b  mov     rcx, [rbp+hKey]; hKey
0x18004091f  test    rcx, rcx
0x180040922  jz      short loc_18004092E
0x180040924  call    cs:__imp_RegCloseKey
0x18004092a  mov     [rbp+hKey], r12
0x18004092e  mov     rdi, [rbp+lpMem]
0x180040932  test    rdi, rdi
0x180040935  jz      short loc_18004094B
0x180040937  call    cs:__imp_GetProcessHeap
0x18004093d  mov     r8, rdi; lpMem
0x180040940  xor     edx, edx; dwFlags
0x180040942  mov     rcx, rax; hHeap
0x180040945  call    cs:__imp_HeapFree
0x18004094b  mov     eax, ebx
0x18004094d  add     rsp, 70h
0x180040951  pop     r14
0x180040953  pop     r13
0x180040955  pop     r12
0x180040957  pop     rdi
0x180040958  pop     rsi
0x180040959  pop     rbx
0x18004095a  pop     rbp
0x18004095b  retn
```
