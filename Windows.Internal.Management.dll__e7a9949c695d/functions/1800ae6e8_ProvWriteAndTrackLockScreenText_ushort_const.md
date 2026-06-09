# ProvWriteAndTrackLockScreenText(ushort const *)

- ea: `0x1800ae6e8`
- end: `0x1800ae914`
- name: `?ProvWriteAndTrackLockScreenText@@YAJPEBG@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077640`

## callees

- `0x18000a2a4`
- `0x180015f70`
- `0x1800169b8`
- `0x180019ae4`
- `0x18003446c`
- `0x180079d34`
- `0x1800926e0`
- `0x1800ae6e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae7ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae8a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae8e2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae7ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae8a8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ae8e2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae7bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae85c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae7bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ae85c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ProvWriteAndTrackLockScreenText(const unsigned __int16 *a1, unsigned __int64 a2)
{
  int v3; // ebx
  __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  unsigned int Key; // eax
  __int64 v10; // rdx
  DWORD v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  int dwOptions; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-40h]
  HKEY hKey[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int64 cbData; // [rsp+88h] [rbp+28h] BYREF
  int Data; // [rsp+90h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  cbData = 0;
  v3 = StringCbLengthW(a1, a2, &cbData);
  if ( v3 >= 0 )
  {
    v5 = cbData;
    if ( !cbData )
      return 0;
    LODWORD(cbData) = 0;
    v3 = ULongLongToULong(v5, (unsigned int *)&cbData);
    if ( v3 < 0 )
    {
      v4 = 28;
      goto LABEL_3;
    }
    hKey[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v8 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\";
    if ( !IsStateSeparationEnabled )
      v8 = L"SOFTWARE\\Microsoft\\Provisioning\\";
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0x2001Fu, 0, hKey, 0);
    if ( Key )
    {
      v10 = 34;
    }
    else
    {
      v11 = cbData;
      Key = RegSetValueExW(hKey[0], L"LostModeMessage", 0, 1u, (const BYTE *)a1, cbData);
      if ( !Key )
      {
        phkResult = 0;
        v12 = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\LostMode",
                0,
                0,
                0,
                0x20006u,
                0,
                &phkResult,
                0);
        if ( v12 )
        {
          v13 = 42;
        }
        else
        {
          v12 = RegSetValueExW(phkResult, L"LostModeMessage", 0, 1u, (const BYTE *)a1, v11);
          if ( v12 )
          {
            v13 = 45;
          }
          else
          {
            Data = 1;
            v12 = RegSetValueExW(phkResult, L"EnableLostMode", 0, 4u, (const BYTE *)&Data, 4u);
            if ( !v12 )
            {
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
              v3 = 0;
              goto LABEL_23;
            }
            v13 = 49;
          }
        }
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v13,
               (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
               (const char *)v12,
               dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_23:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
        return (unsigned int)v3;
      }
      v10 = 37;
    }
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
           (const char *)Key,
           dwOptionsa);
    goto LABEL_23;
  }
  v4 = 20;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\admin\\prov\\lib\\lockscreenstatus.cpp",
    (const char *)(unsigned int)v3,
    dwOptions);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ae6e8  push    rbp
0x1800ae6ea  push    rbx
0x1800ae6eb  push    rdi
0x1800ae6ec  mov     rbp, rsp
0x1800ae6ef  sub     rsp, 60h
0x1800ae6f3  lea     r8, [rbp+cbData]; unsigned __int64 *
0x1800ae6f7  mov     [rbp+cbData], 0
0x1800ae6ff  mov     rdi, rcx
0x1800ae702  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800ae707  mov     ebx, eax
0x1800ae709  test    eax, eax
0x1800ae70b  jns     short loc_1800AE72A
0x1800ae70d  mov     edx, 14h; void *
0x1800ae712  mov     rcx, [rbp+18h]; this
0x1800ae716  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800ae71d  mov     r9d, ebx; char *
0x1800ae720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae725  jmp     loc_1800AE90A
0x1800ae72a  mov     rcx, [rbp+cbData]; unsigned __int64
0x1800ae72e  test    rcx, rcx
0x1800ae731  jnz     short loc_1800AE73A
0x1800ae733  xor     eax, eax
0x1800ae735  jmp     loc_1800AE90C
0x1800ae73a  lea     rdx, [rbp+cbData]; unsigned int *
0x1800ae73e  mov     dword ptr [rbp+cbData], 0
0x1800ae745  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800ae74a  mov     ebx, eax
0x1800ae74c  test    eax, eax
0x1800ae74e  jns     short loc_1800AE757
0x1800ae750  mov     edx, 1Ch
0x1800ae755  jmp     short loc_1800AE712
0x1800ae757  xor     edx, edx
0x1800ae759  mov     [rbp+hKey], 0
0x1800ae761  lea     rcx, [rbp+hKey]
0x1800ae765  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ae76a  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800ae76f  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800ae778  lea     rcx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Provisioning\\"
0x1800ae77f  test    al, al
0x1800ae781  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800ae788  lea     rax, [rbp+hKey]
0x1800ae78c  mov     [rsp+60h+phkResult], rax; phkResult
0x1800ae791  cmovz   rdx, rcx; lpSubKey
0x1800ae795  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ae79e  xor     r9d, r9d; lpClass
0x1800ae7a1  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800ae7a9  xor     r8d, r8d; Reserved
0x1800ae7ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae7b3  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800ae7bb  call    cs:__imp_RegCreateKeyExW
0x1800ae7c1  test    eax, eax
0x1800ae7c3  jz      short loc_1800AE7CC
0x1800ae7c5  mov     edx, 22h ; '"'
0x1800ae7ca  jmp     short loc_1800AE7FB
0x1800ae7cc  mov     ebx, dword ptr [rbp+cbData]
0x1800ae7cf  lea     rdx, aLostmodemessag; "LostModeMessage"
0x1800ae7d6  mov     rcx, [rbp+hKey]; hKey
0x1800ae7da  mov     r9d, 1; dwType
0x1800ae7e0  mov     [rsp+60h+samDesired], ebx; cbData
0x1800ae7e4  xor     r8d, r8d; Reserved
0x1800ae7e7  mov     qword ptr [rsp+60h+dwOptions], rdi; unsigned int
0x1800ae7ec  call    cs:__imp_RegSetValueExW
0x1800ae7f2  test    eax, eax
0x1800ae7f4  jz      short loc_1800AE815
0x1800ae7f6  mov     edx, 25h ; '%'; void *
0x1800ae7fb  mov     rcx, [rbp+18h]; this
0x1800ae7ff  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800ae806  mov     r9d, eax; char *
0x1800ae809  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ae80e  mov     ebx, eax
0x1800ae810  jmp     loc_1800AE901
0x1800ae815  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800ae81e  lea     rax, [rbp+arg_18]
0x1800ae822  mov     [rsp+60h+phkResult], rax; phkResult
0x1800ae827  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800ae82e  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ae837  xor     r9d, r9d; lpClass
0x1800ae83a  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800ae842  xor     r8d, r8d; Reserved
0x1800ae845  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ae84c  mov     [rsp+60h+dwOptions], 0; unsigned int
0x1800ae854  mov     [rbp+arg_18], 0
0x1800ae85c  call    cs:__imp_RegCreateKeyExW
0x1800ae862  test    eax, eax
0x1800ae864  jz      short loc_1800AE88B
0x1800ae866  mov     edx, 2Ah ; '*'; void *
0x1800ae86b  mov     rcx, [rbp+18h]; this
0x1800ae86f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800ae876  mov     r9d, eax; char *
0x1800ae879  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ae87e  lea     rcx, [rbp+arg_18]
0x1800ae882  mov     ebx, eax
0x1800ae884  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ae889  jmp     short loc_1800AE901
0x1800ae88b  mov     rcx, [rbp+arg_18]; hKey
0x1800ae88f  lea     rdx, aLostmodemessag; "LostModeMessage"
0x1800ae896  mov     [rsp+60h+samDesired], ebx; cbData
0x1800ae89a  mov     r9d, 1; dwType
0x1800ae8a0  xor     r8d, r8d; Reserved
0x1800ae8a3  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800ae8a8  call    cs:__imp_RegSetValueExW
0x1800ae8ae  test    eax, eax
0x1800ae8b0  jz      short loc_1800AE8B9
0x1800ae8b2  mov     edx, 2Dh ; '-'
0x1800ae8b7  jmp     short loc_1800AE86B
0x1800ae8b9  mov     rcx, [rbp+arg_18]; hKey
0x1800ae8bd  lea     rax, [rbp+Data]
0x1800ae8c1  mov     r9d, 4; dwType
0x1800ae8c7  mov     [rbp+Data], 1
0x1800ae8ce  mov     [rsp+60h+samDesired], r9d; cbData
0x1800ae8d3  lea     rdx, aEnablelostmode; "EnableLostMode"
0x1800ae8da  xor     r8d, r8d; Reserved
0x1800ae8dd  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800ae8e2  call    cs:__imp_RegSetValueExW
0x1800ae8e8  test    eax, eax
0x1800ae8ea  jz      short loc_1800AE8F6
0x1800ae8ec  mov     edx, 31h ; '1'
0x1800ae8f1  jmp     loc_1800AE86B
0x1800ae8f6  lea     rcx, [rbp+arg_18]
0x1800ae8fa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ae8ff  xor     ebx, ebx
0x1800ae901  lea     rcx, [rbp+hKey]
0x1800ae905  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ae90a  mov     eax, ebx
0x1800ae90c  add     rsp, 60h
0x1800ae910  pop     rdi
0x1800ae911  pop     rbx
0x1800ae912  pop     rbp
0x1800ae913  retn
```
