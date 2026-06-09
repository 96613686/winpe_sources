# ProvWriteAndTrackLockScreenText(ushort const *)

- ea: `0x1800b19d0`
- end: `0x1800b1c1e`
- name: `?ProvWriteAndTrackLockScreenText@@YAJPEBG@Z`
- size: `590`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078de0`

## callees

- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x1800184c0`
- `0x180033500`
- `0x18007b580`
- `0x180094e40`
- `0x1800b19d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ada`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ba5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1be5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ada`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1ba5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b1be5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1aa3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1b50`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1aa3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b1b50`

## pseudocode

```c
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
0x1800b19d0  push    rbp
0x1800b19d2  push    rbx
0x1800b19d3  push    rdi
0x1800b19d4  mov     rbp, rsp
0x1800b19d7  sub     rsp, 60h
0x1800b19db  lea     r8, [rbp+cbData]; unsigned __int64 *
0x1800b19df  mov     [rbp+cbData], 0
0x1800b19e7  mov     rdi, rcx
0x1800b19ea  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b19ef  mov     ebx, eax
0x1800b19f1  test    eax, eax
0x1800b19f3  jns     short loc_1800B1A12
0x1800b19f5  mov     edx, 14h; void *
0x1800b19fa  mov     rcx, [rbp+18h]; this
0x1800b19fe  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800b1a05  mov     r9d, ebx; char *
0x1800b1a08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1a0d  jmp     loc_1800B1C13
0x1800b1a12  mov     rcx, [rbp+cbData]; unsigned __int64
0x1800b1a16  test    rcx, rcx
0x1800b1a19  jnz     short loc_1800B1A22
0x1800b1a1b  xor     eax, eax
0x1800b1a1d  jmp     loc_1800B1C15
0x1800b1a22  lea     rdx, [rbp+cbData]; unsigned int *
0x1800b1a26  mov     dword ptr [rbp+cbData], 0
0x1800b1a2d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800b1a32  mov     ebx, eax
0x1800b1a34  test    eax, eax
0x1800b1a36  jns     short loc_1800B1A3F
0x1800b1a38  mov     edx, 1Ch
0x1800b1a3d  jmp     short loc_1800B19FA
0x1800b1a3f  xor     edx, edx
0x1800b1a41  mov     [rbp+hKey], 0
0x1800b1a49  lea     rcx, [rbp+hKey]
0x1800b1a4d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b1a52  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800b1a57  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800b1a60  lea     rcx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Provisioning\\"
0x1800b1a67  test    al, al
0x1800b1a69  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800b1a70  lea     rax, [rbp+hKey]
0x1800b1a74  mov     [rsp+60h+phkResult], rax; phkResult
0x1800b1a79  cmovz   rdx, rcx; lpSubKey
0x1800b1a7d  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b1a86  xor     r9d, r9d; lpClass
0x1800b1a89  mov     [rsp+60h+samDesired], 2001Fh; samDesired
0x1800b1a91  xor     r8d, r8d; Reserved
0x1800b1a94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b1a9b  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800b1aa3  call    cs:__imp_RegCreateKeyExW
0x1800b1aaa  nop     dword ptr [rax+rax+00h]
0x1800b1aaf  test    eax, eax
0x1800b1ab1  jz      short loc_1800B1ABA
0x1800b1ab3  mov     edx, 22h ; '"'
0x1800b1ab8  jmp     short loc_1800B1AEF
0x1800b1aba  mov     ebx, dword ptr [rbp+cbData]
0x1800b1abd  lea     rdx, aLostmodemessag; "LostModeMessage"
0x1800b1ac4  mov     rcx, [rbp+hKey]; hKey
0x1800b1ac8  mov     r9d, 1; dwType
0x1800b1ace  mov     [rsp+60h+samDesired], ebx; cbData
0x1800b1ad2  xor     r8d, r8d; Reserved
0x1800b1ad5  mov     qword ptr [rsp+60h+dwOptions], rdi; unsigned int
0x1800b1ada  call    cs:__imp_RegSetValueExW
0x1800b1ae1  nop     dword ptr [rax+rax+00h]
0x1800b1ae6  test    eax, eax
0x1800b1ae8  jz      short loc_1800B1B09
0x1800b1aea  mov     edx, 25h ; '%'; void *
0x1800b1aef  mov     rcx, [rbp+18h]; this
0x1800b1af3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800b1afa  mov     r9d, eax; char *
0x1800b1afd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b1b02  mov     ebx, eax
0x1800b1b04  jmp     loc_1800B1C0A
0x1800b1b09  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800b1b12  lea     rax, [rbp+arg_18]
0x1800b1b16  mov     [rsp+60h+phkResult], rax; phkResult
0x1800b1b1b  lea     rdx, aSoftwareMicros_16; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800b1b22  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800b1b2b  xor     r9d, r9d; lpClass
0x1800b1b2e  mov     [rsp+60h+samDesired], 20006h; samDesired
0x1800b1b36  xor     r8d, r8d; Reserved
0x1800b1b39  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b1b40  mov     [rsp+60h+dwOptions], 0; unsigned int
0x1800b1b48  mov     [rbp+arg_18], 0
0x1800b1b50  call    cs:__imp_RegCreateKeyExW
0x1800b1b57  nop     dword ptr [rax+rax+00h]
0x1800b1b5c  test    eax, eax
0x1800b1b5e  jz      short loc_1800B1B88
0x1800b1b60  mov     edx, 2Ah ; '*'; void *
0x1800b1b65  mov     rcx, [rbp+18h]; this
0x1800b1b69  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\lib\\lockscree"...
0x1800b1b70  mov     r9d, eax; char *
0x1800b1b73  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b1b78  lea     rcx, [rbp+arg_18]
0x1800b1b7c  mov     ebx, eax
0x1800b1b7e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b1b83  jmp     loc_1800B1C0A
0x1800b1b88  mov     rcx, [rbp+arg_18]; hKey
0x1800b1b8c  lea     rdx, aLostmodemessag; "LostModeMessage"
0x1800b1b93  mov     [rsp+60h+samDesired], ebx; cbData
0x1800b1b97  mov     r9d, 1; dwType
0x1800b1b9d  xor     r8d, r8d; Reserved
0x1800b1ba0  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x1800b1ba5  call    cs:__imp_RegSetValueExW
0x1800b1bac  nop     dword ptr [rax+rax+00h]
0x1800b1bb1  test    eax, eax
0x1800b1bb3  jz      short loc_1800B1BBC
0x1800b1bb5  mov     edx, 2Dh ; '-'
0x1800b1bba  jmp     short loc_1800B1B65
0x1800b1bbc  mov     rcx, [rbp+arg_18]; hKey
0x1800b1bc0  lea     rax, [rbp+Data]
0x1800b1bc4  mov     r9d, 4; dwType
0x1800b1bca  mov     [rbp+Data], 1
0x1800b1bd1  mov     [rsp+60h+samDesired], r9d; cbData
0x1800b1bd6  lea     rdx, aEnablelostmode; "EnableLostMode"
0x1800b1bdd  xor     r8d, r8d; Reserved
0x1800b1be0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800b1be5  call    cs:__imp_RegSetValueExW
0x1800b1bec  nop     dword ptr [rax+rax+00h]
0x1800b1bf1  test    eax, eax
0x1800b1bf3  jz      short loc_1800B1BFF
0x1800b1bf5  mov     edx, 31h ; '1'
0x1800b1bfa  jmp     loc_1800B1B65
0x1800b1bff  lea     rcx, [rbp+arg_18]
0x1800b1c03  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b1c08  xor     ebx, ebx
0x1800b1c0a  lea     rcx, [rbp+hKey]
0x1800b1c0e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b1c13  mov     eax, ebx
0x1800b1c15  add     rsp, 60h
0x1800b1c19  pop     rdi
0x1800b1c1a  pop     rbx
0x1800b1c1b  pop     rbp
0x1800b1c1c  retn
```
