# Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,Windows::Internal::WiFiCloudStore::RetryStatistics *)

- ea: `0x180011b94`
- end: `0x180011cf6`
- name: `?TryGetRetryCountForProfile@WiFiCloudStore@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEAURetryStatistics@123@@Z`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800119bc`
- `0x18001314c`

## callees

- `0x1800079f0`
- `0x18000ac14`
- `0x1800111a8`
- `0x180011b94`
- `0x18001de24`
- `0x18001e1a0`
- `0x180025308`
- `0x18002a030`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011c8d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011c4c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180011c4c`

## string_xrefs

- `0x180011ce4`: `onecore\net\wificloudstore\registry\lib\wificdsconsumerreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::WiFiCloudStore::TryGetRetryCountForProfile(
        __int64 a1,
        GUID *a2,
        int a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v9; // rax
  unsigned int ValueW; // ebx
  unsigned int pdwType; // [rsp+20h] [rbp-51h]
  DWORD pcbData; // [rsp+40h] [rbp-31h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-29h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-21h] BYREF
  __int64 pvData; // [rsp+58h] [rbp-19h] BYREF
  int v17; // [rsp+60h] [rbp-11h]
  void *v18; // [rsp+68h] [rbp-9h] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  *(_QWORD *)a5 = 0;
  *(_DWORD *)(a5 + 8) = 0;
  Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&hMem, a2);
  Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(&hkey, a2, a3, (const char *)a4, (__int64)hMem);
  pvData = 0;
  v17 = 0;
  pcbData = 12;
  v9 = Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(&v18, a1);
  if ( *(_QWORD *)(v9 + 24) > 7u )
    v9 = *(_QWORD *)v9;
  ValueW = RegGetValueW(hkey, 0, (LPCWSTR)v9, 8u, 0, &pvData, &pcbData);
  if ( v19 > 7 )
    std::_Deallocate<16>(v18, 2 * v19 + 2);
  if ( ValueW )
  {
    if ( ValueW != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdsconsumerreg.cpp",
        (const char *)ValueW,
        pdwType);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return 0;
  }
  else
  {
    *(_QWORD *)a5 = pvData;
    *(_DWORD *)(a5 + 8) = v17;
    if ( hkey )
      RegCloseKey(hkey);
    if ( hMem )
      LocalFree(hMem);
    return 1;
  }
}

```

## disassembly

```asm
0x180011b94  push    rbp
0x180011b96  push    rbx
0x180011b97  push    rsi
0x180011b98  push    rdi
0x180011b99  push    r14
0x180011b9b  push    r15
0x180011b9d  lea     rbp, [rsp-27h]
0x180011ba2  sub     rsp, 98h
0x180011ba9  mov     rax, cs:__security_cookie
0x180011bb0  xor     rax, rsp
0x180011bb3  mov     [rbp+4Fh+var_38], rax
0x180011bb7  mov     esi, r9d
0x180011bba  mov     edi, r8d
0x180011bbd  mov     rbx, rdx
0x180011bc0  mov     r14, rcx
0x180011bc3  mov     r15, [rbp+4Fh+arg_20]
0x180011bc7  mov     qword ptr [r15], 0
0x180011bce  mov     dword ptr [r15+8], 0
0x180011bd6  lea     rcx, [rbp+4Fh+hMem]; StringSid
0x180011bda  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x180011bdf  nop
0x180011be0  mov     rax, [rbp+4Fh+hMem]
0x180011be4  mov     [rsp+0C0h+pdwType], rax
0x180011be9  mov     r9d, esi
0x180011bec  mov     r8d, edi
0x180011bef  mov     rdx, rbx
0x180011bf2  lea     rcx, [rbp+4Fh+hkey]
0x180011bf6  call    ?OpenProfileSyncRetryKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBU_GUID@@W4ProfileModificationType@123@W4ProfileGeneration@123@PEBG@Z; Windows::Internal::WiFiCloudStore::OpenProfileSyncRetryKeyForUser(_GUID const &,Windows::Internal::WiFiCloudStore::ProfileModificationType,Windows::Internal::WiFiCloudStore::ProfileGeneration,ushort const *)
0x180011bfb  nop
0x180011bfc  xor     eax, eax
0x180011bfe  mov     [rbp+4Fh+var_68], rax
0x180011c02  mov     [rbp+4Fh+var_60], eax
0x180011c05  mov     [rbp+4Fh+var_80], 0Ch
0x180011c0c  mov     rdx, r14
0x180011c0f  lea     rcx, [rbp+4Fh+var_58]
0x180011c13  call    ?ProfileNameToCDSReferenceId@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; Windows::Internal::WiFiCloudStore::ProfileNameToCDSReferenceId(std::wstring const &)
0x180011c18  cmp     qword ptr [rax+18h], 7
0x180011c1d  jbe     short loc_180011C22
0x180011c1f  mov     rax, [rax]
0x180011c22  lea     rcx, [rbp+4Fh+var_80]
0x180011c26  mov     [rsp+0C0h+pcbData], rcx; pcbData
0x180011c2b  lea     rcx, [rbp+4Fh+var_68]
0x180011c2f  mov     [rsp+0C0h+pvData], rcx; pvData
0x180011c34  mov     [rsp+0C0h+pdwType], 0; unsigned int
0x180011c3d  mov     r9d, 8; dwFlags
0x180011c43  mov     r8, rax; lpValue
0x180011c46  xor     edx, edx; lpSubKey
0x180011c48  mov     rcx, [rbp+4Fh+hkey]; hkey
0x180011c4c  call    cs:__imp_RegGetValueW
0x180011c52  mov     ebx, eax
0x180011c54  mov     rdx, [rbp+4Fh+var_40]
0x180011c58  cmp     rdx, 7
0x180011c5c  jbe     short loc_180011C6F
0x180011c5e  lea     rdx, ds:2[rdx*2]
0x180011c66  mov     rcx, [rbp+4Fh+var_58]
0x180011c6a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011c6f  test    ebx, ebx
0x180011c71  jnz     short loc_180011CC1
0x180011c73  movsd   xmm0, [rbp+4Fh+var_68]
0x180011c78  movsd   qword ptr [r15], xmm0
0x180011c7d  mov     eax, [rbp+4Fh+var_60]
0x180011c80  mov     [r15+8], eax
0x180011c84  mov     rcx, [rbp+4Fh+hkey]; hKey
0x180011c88  test    rcx, rcx
0x180011c8b  jz      short loc_180011C94
0x180011c8d  call    cs:__imp_RegCloseKey
0x180011c93  nop
0x180011c94  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180011c98  test    rcx, rcx
0x180011c9b  jz      short loc_180011CA3
0x180011c9d  call    cs:__imp_LocalFree
0x180011ca3  mov     al, 1
0x180011ca5  mov     rcx, [rbp+4Fh+var_38]
0x180011ca9  xor     rcx, rsp; StackCookie
0x180011cac  call    __security_check_cookie
0x180011cb1  add     rsp, 98h
0x180011cb8  pop     r15
0x180011cba  pop     r14
0x180011cbc  pop     rdi
0x180011cbd  pop     rsi
0x180011cbe  pop     rbx
0x180011cbf  pop     rbp
0x180011cc0  retn
0x180011cc1  cmp     ebx, 2
0x180011cc4  jnz     short loc_180011CDD
0x180011cc6  lea     rcx, [rbp+4Fh+hkey]
0x180011cca  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180011ccf  nop
0x180011cd0  lea     rcx, [rbp+4Fh+hMem]
0x180011cd4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011cd9  xor     al, al
0x180011cdb  jmp     short loc_180011CA5
0x180011cdd  mov     rcx, [rbp+57h]; this
0x180011ce1  mov     r9d, ebx; char *
0x180011ce4  lea     r8, aOnecoreNetWifi; "onecore\\net\\wificloudstore\\registry"...
0x180011ceb  mov     edx, 81h; void *
0x180011cf0  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
