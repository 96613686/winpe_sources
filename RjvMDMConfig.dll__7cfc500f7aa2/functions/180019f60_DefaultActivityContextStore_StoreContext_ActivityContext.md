# DefaultActivityContextStore::StoreContext(ActivityContext &)

- ea: `0x180019f60`
- end: `0x18001a1fd`
- name: `?StoreContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x1800075e8`
- `0x180011828`
- `0x180017e2c`
- `0x1800188f8`
- `0x180018da8`
- `0x180019f60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a05f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a05f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a10d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a148`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a17f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a10d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a148`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a17f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a0a9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a0a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019fcf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180019fcf`

## string_xrefs

- `0x18001a13c`: `AttemptCounter`
- `0x18001a173`: `Rollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DefaultActivityContextStore::StoreContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  signed int v3; // edi
  const unsigned __int16 *EnrollmentsRootKey; // rax
  LSTATUS v5; // eax
  bool v6; // cc
  const unsigned __int16 *v7; // r8
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v11[4]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE v12[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v15[40]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  *(_DWORD *)Data = 32;
  *(_DWORD *)v11 = 0;
  *(_DWORD *)v12 = 0;
  hKey = 0;
  phkResult = 0;
  SubKey[0] = 0;
  v15[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, v15);
    if ( v3 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v15);
      if ( v3 >= 0 )
      {
        v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &phkResult);
        if ( v5 == 2 )
          v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        v6 = v5 <= 0;
        if ( v5
          || (wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
                &hKey,
                phkResult),
              *(_DWORD *)Data = *((_DWORD *)a2 + 8),
              v5 = RegSetValueExW(hKey, L"ActivityType", 0, 4u, Data, 4u),
              v6 = v5 <= 0,
              v5) )
        {
          if ( v6 )
            v3 = v5;
          else
            v3 = (unsigned __int16)v5 | 0x80070000;
        }
        else
        {
          *(_DWORD *)v11 = *((_DWORD *)a2 + 242);
          RegSetValueExW(hKey, L"AttemptCounter", 0, 4u, v11, 4u);
          *(_DWORD *)v12 = *((_DWORD *)a2 + 108);
          RegSetValueExW(hKey, L"Rollback", 0, 4u, v12, 4u);
          if ( a2 != (struct ActivityContext *)-448LL )
            v3 = WriteStringToRegistry(hKey, L"OrchestratorType", (const unsigned __int16 *)a2 + 224);
          v7 = (&off_180029118)[2 * *(int *)Data];
          if ( v7 )
            WriteStringToRegistry(hKey, L"ActivityTypeName", v7);
        }
      }
    }
  }
  else
  {
    v3 = -2147418113;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019f60  push    rbp
0x180019f62  push    rsi
0x180019f63  push    rdi
0x180019f64  push    r15
0x180019f66  lea     rbp, [rsp-238h]
0x180019f6e  sub     rsp, 338h
0x180019f75  mov     rax, cs:__security_cookie
0x180019f7c  xor     rax, rsp
0x180019f7f  mov     [rbp+250h+var_30], rax
0x180019f86  mov     rsi, rdx
0x180019f89  mov     dword ptr [rsp+350h+Data], 20h ; ' '
0x180019f91  mov     dword ptr [rsp+350h+var_2F0], 0
0x180019f99  mov     dword ptr [rsp+350h+var_2EC], 0
0x180019fa1  mov     [rsp+350h+hKey], 0
0x180019faa  mov     [rsp+350h+var_2E8], 0
0x180019fb3  xor     eax, eax
0x180019fb5  mov     [rbp+250h+SubKey], ax
0x180019fb9  mov     [rbp+250h+var_290], ax
0x180019fbd  mov     [rsp+350h+sz], ax
0x180019fc2  lea     rcx, [rdx+8]; rguid
0x180019fc6  lea     r8d, [rax+27h]; cchMax
0x180019fca  lea     rdx, [rsp+350h+sz]; lpsz
0x180019fcf  call    cs:__imp_StringFromGUID2
0x180019fd6  nop     dword ptr [rax+rax+00h]
0x180019fdb  cmp     eax, 27h ; '''
0x180019fde  jz      short loc_180019FEA
0x180019fe0  mov     edi, 8000FFFFh
0x180019fe5  jmp     loc_18001A1D4
0x180019fea  lea     rdx, [rbp+250h+var_290]; unsigned __int16 *
0x180019fee  lea     rcx, [rsp+350h+sz]; unsigned __int16 *
0x180019ff3  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180019ff8  mov     edi, eax
0x180019ffa  test    eax, eax
0x180019ffc  js      loc_18001A1D4
0x18001a002  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18001a007  lea     rcx, [rbp+250h+var_290]
0x18001a00b  mov     qword ptr [rsp+350h+samDesired], rcx
0x18001a010  lea     rcx, aContext; "Context"
0x18001a017  mov     [rsp+350h+phkResult], rcx
0x18001a01c  mov     r9, rax
0x18001a01f  lea     r8, aSSS; "%s\\%s\\%s"
0x18001a026  mov     edx, 104h; unsigned __int64
0x18001a02b  lea     rcx, [rbp+250h+SubKey]; unsigned __int16 *
0x18001a02f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a034  mov     edi, eax
0x18001a036  test    eax, eax
0x18001a038  js      loc_18001A1D4
0x18001a03e  lea     rax, [rsp+350h+var_2E8]
0x18001a043  mov     [rsp+350h+phkResult], rax; phkResult
0x18001a048  mov     r9d, 0F003Fh; samDesired
0x18001a04e  xor     r8d, r8d; ulOptions
0x18001a051  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18001a055  mov     r15, 0FFFFFFFF80000002h
0x18001a05c  mov     rcx, r15; hKey
0x18001a05f  call    cs:__imp_RegOpenKeyExW
0x18001a066  nop     dword ptr [rax+rax+00h]
0x18001a06b  cmp     eax, 2
0x18001a06e  jnz     short loc_18001A0B5
0x18001a070  mov     [rsp+350h+lpdwDisposition], 0; lpdwDisposition
0x18001a079  lea     rax, [rsp+350h+var_2E8]
0x18001a07e  mov     [rsp+350h+var_318], rax; phkResult
0x18001a083  mov     [rsp+350h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001a08c  mov     [rsp+350h+samDesired], 0F003Fh; samDesired
0x18001a094  mov     dword ptr [rsp+350h+phkResult], 0; dwOptions
0x18001a09c  xor     r9d, r9d; lpClass
0x18001a09f  xor     r8d, r8d; Reserved
0x18001a0a2  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18001a0a6  mov     rcx, r15; hKey
0x18001a0a9  call    cs:__imp_RegCreateKeyExW
0x18001a0b0  nop     dword ptr [rax+rax+00h]
0x18001a0b5  test    eax, eax
0x18001a0b7  jz      short loc_18001A0D0
0x18001a0b9  jg      short loc_18001A0C2
0x18001a0bb  mov     edi, eax
0x18001a0bd  jmp     loc_18001A1D4
0x18001a0c2  movzx   edi, ax
0x18001a0c5  or      edi, 80070000h
0x18001a0cb  jmp     loc_18001A1D4
0x18001a0d0  mov     rdx, [rsp+350h+var_2E8]
0x18001a0d5  lea     rcx, [rsp+350h+hKey]
0x18001a0da  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001a0df  mov     eax, [rsi+20h]
0x18001a0e2  mov     dword ptr [rsp+350h+Data], eax
0x18001a0e6  mov     r15d, 4
0x18001a0ec  mov     [rsp+350h+samDesired], r15d; cbData
0x18001a0f1  lea     rax, [rsp+350h+Data]
0x18001a0f6  mov     [rsp+350h+phkResult], rax; lpData
0x18001a0fb  mov     r9d, r15d; dwType
0x18001a0fe  xor     r8d, r8d; Reserved
0x18001a101  lea     rdx, aActivitytype; "ActivityType"
0x18001a108  mov     rcx, [rsp+350h+hKey]; hKey
0x18001a10d  call    cs:__imp_RegSetValueExW
0x18001a114  nop     dword ptr [rax+rax+00h]
0x18001a119  test    eax, eax
0x18001a11b  jnz     short loc_18001A0B9
0x18001a11d  mov     eax, [rsi+3C8h]
0x18001a123  mov     dword ptr [rsp+350h+var_2F0], eax
0x18001a127  mov     [rsp+350h+samDesired], r15d; cbData
0x18001a12c  lea     rax, [rsp+350h+var_2F0]
0x18001a131  mov     [rsp+350h+phkResult], rax; lpData
0x18001a136  mov     r9d, r15d; dwType
0x18001a139  xor     r8d, r8d; Reserved
0x18001a13c  lea     rdx, aAttemptcounter; "AttemptCounter"
0x18001a143  mov     rcx, [rsp+350h+hKey]; hKey
0x18001a148  call    cs:__imp_RegSetValueExW
0x18001a14f  nop     dword ptr [rax+rax+00h]
0x18001a154  mov     eax, [rsi+1B0h]
0x18001a15a  mov     dword ptr [rsp+350h+var_2EC], eax
0x18001a15e  mov     [rsp+350h+samDesired], r15d; cbData
0x18001a163  lea     rax, [rsp+350h+var_2EC]
0x18001a168  mov     [rsp+350h+phkResult], rax; lpData
0x18001a16d  mov     r9d, r15d; dwType
0x18001a170  xor     r8d, r8d; Reserved
0x18001a173  lea     rdx, aRollback; "Rollback"
0x18001a17a  mov     rcx, [rsp+350h+hKey]; hKey
0x18001a17f  call    cs:__imp_RegSetValueExW
0x18001a186  nop     dword ptr [rax+rax+00h]
0x18001a18b  lea     r8, [rsi+1C0h]; unsigned __int16 *
0x18001a192  test    r8, r8
0x18001a195  jz      short loc_18001A1AA
0x18001a197  lea     rdx, aOrchestratorty; "OrchestratorType"
0x18001a19e  mov     rcx, [rsp+350h+hKey]; hKey
0x18001a1a3  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18001a1a8  mov     edi, eax
0x18001a1aa  movsxd  rax, dword ptr [rsp+350h+Data]
0x18001a1af  add     rax, rax
0x18001a1b2  lea     r8, off_180029118; "AT_MDM_RENEWAL_DISCOVERY"
0x18001a1b9  mov     r8, [r8+rax*8]; unsigned __int16 *
0x18001a1bd  test    r8, r8
0x18001a1c0  jz      short loc_18001A1D4
0x18001a1c2  lea     rdx, aActivitytypena; "ActivityTypeName"
0x18001a1c9  mov     rcx, [rsp+350h+hKey]; hKey
0x18001a1ce  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18001a1d3  nop
0x18001a1d4  lea     rcx, [rsp+350h+hKey]
0x18001a1d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001a1de  mov     eax, edi
0x18001a1e0  mov     rcx, [rbp+250h+var_30]
0x18001a1e7  xor     rcx, rsp; StackCookie
0x18001a1ea  call    __security_check_cookie
0x18001a1ef  add     rsp, 338h
0x18001a1f6  pop     r15
0x18001a1f8  pop     rdi
0x18001a1f9  pop     rsi
0x18001a1fa  pop     rbp
0x18001a1fb  retn
```
