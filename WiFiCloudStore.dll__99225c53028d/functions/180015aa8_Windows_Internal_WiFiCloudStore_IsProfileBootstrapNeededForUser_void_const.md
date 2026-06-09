# Windows::Internal::WiFiCloudStore::IsProfileBootstrapNeededForUser(void * const)

- ea: `0x180015aa8`
- end: `0x180015b64`
- name: `?IsProfileBootstrapNeededForUser@WiFiCloudStore@Internal@Windows@@YA_NQEAX@Z`
- size: `188`
- prototype: `bool __fastcall(Windows::Internal::WiFiCloudStore *__hidden this, void *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014d70`

## callees

- `0x180015aa8`
- `0x180015b9c`
- `0x18001de24`
- `0x180031ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015b49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015afd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015afd`

## string_xrefs

- `0x180015aef`: `WlanSvcTaskBootstrapped`
- `0x180015b26`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::WiFiCloudStore::IsProfileBootstrapNeededForUser(
        Windows::Internal::WiFiCloudStore *this,
        void *const a2)
{
  unsigned int ValueW; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Windows::Internal::WiFiCloudStore *pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pvData = this;
  Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(&hkey);
  LODWORD(pvData) = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"WlanSvcTaskBootstrapped", 0x18u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 1;
  }
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)ValueW,
      pdwType);
  if ( (_DWORD)pvData != 1 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 0;
}

```

## disassembly

```asm
0x180015aa8  mov     [rsp+arg_0], rcx
0x180015aad  sub     rsp, 48h
0x180015ab1  lea     rcx, [rsp+48h+hkey]; phkResult
0x180015ab6  call    ?OpenSyncBaseKeyForUser@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::OpenSyncBaseKeyForUser(void * const)
0x180015abb  nop
0x180015abc  mov     dword ptr [rsp+48h+arg_0], 0
0x180015ac4  mov     [rsp+48h+arg_8], 4
0x180015acc  lea     rax, [rsp+48h+arg_8]
0x180015ad1  mov     [rsp+48h+pcbData], rax; pcbData
0x180015ad6  lea     rax, [rsp+48h+arg_0]
0x180015adb  mov     [rsp+48h+pvData], rax; pvData
0x180015ae0  mov     [rsp+48h+pdwType], 0; unsigned int
0x180015ae9  mov     r9d, 18h; dwFlags
0x180015aef  lea     r8, ValueName; "WlanSvcTaskBootstrapped"
0x180015af6  xor     edx, edx; lpSubKey
0x180015af8  mov     rcx, [rsp+48h+hkey]; hkey
0x180015afd  call    cs:__imp_RegGetValueW
0x180015b03  cmp     eax, 2
0x180015b06  jnz     short loc_180015B1A
0x180015b08  mov     rcx, [rsp+48h+hkey]; hKey
0x180015b0d  test    rcx, rcx
0x180015b10  jz      short loc_180015B5D
0x180015b12  call    cs:__imp_RegCloseKey
0x180015b18  jmp     short loc_180015B5D
0x180015b1a  test    eax, eax
0x180015b1c  jz      short loc_180015B38
0x180015b1e  mov     rcx, [rsp+48h]; this
0x180015b23  mov     r9d, eax; char *
0x180015b26  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x180015b2d  mov     edx, 132h; void *
0x180015b32  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180015b38  cmp     dword ptr [rsp+48h+arg_0], 1
0x180015b3d  jnz     short loc_180015B53
0x180015b3f  mov     rcx, [rsp+48h+hkey]; hKey
0x180015b44  test    rcx, rcx
0x180015b47  jz      short loc_180015B4F
0x180015b49  call    cs:__imp_RegCloseKey
0x180015b4f  xor     al, al
0x180015b51  jmp     short loc_180015B5F
0x180015b53  lea     rcx, [rsp+48h+hkey]
0x180015b58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015b5d  mov     al, 1
0x180015b5f  add     rsp, 48h
0x180015b63  retn
```
