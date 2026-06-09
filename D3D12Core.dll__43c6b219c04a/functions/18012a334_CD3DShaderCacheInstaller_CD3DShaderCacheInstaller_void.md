# CD3DShaderCacheInstaller::~CD3DShaderCacheInstaller(void)

- ea: `0x18012a334`
- end: `0x18012a43d`
- name: `??1CD3DShaderCacheInstaller@@UEAA@XZ`
- size: `265`
- prototype: `void __fastcall(CD3DShaderCacheInstaller *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18012a800`

## callees

- `0x18000bb58`
- `0x1800235dc`
- `0x180084d44`
- `0x180085d84`
- `0x1800ea6b8`
- `0x18012a130`
- `0x18012a334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18012a392`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18012a392`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18012a3af`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18012a3af`

## pseudocode

```c
void __fastcall CD3DShaderCacheInstaller::~CD3DShaderCacheInstaller(CD3DShaderCacheInstaller *this)
{
  const WCHAR *v2; // rdx
  LSTATUS v3; // eax
  __int64 v4; // rcx
  bool v5; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CD3DShaderCacheInstaller::`vftable';
  v5 = 0;
  if ( (int)RegistryReader::IsKeyEmpty(*((HKEY *)this + 11), &v5) >= 0 && v5 )
  {
    v2 = (const WCHAR *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) > 7u )
      v2 = *(const WCHAR **)v2;
    v3 = RegDeleteKeyExW((HKEY)((*((_DWORD *)this + 20) != 0) - 0x7FFFFFFFLL), v2, 0x100u, 0);
    if ( v3 )
      RegistryError(v3);
  }
  if ( *((_QWORD *)this + 17) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 17) = 0;
  }
  std::wstring::_Tidy_deallocate((char *)this + 104);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 96);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>((char *)this + 88);
  std::wstring::_Tidy_deallocate((char *)this + 48);
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    std::_Deallocate<16>(v4, 32 * ((*((_QWORD *)this + 5) - v4) >> 5));
    *((_QWORD *)this + 3) = 0;
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
  }
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18012a334  mov     [rsp+arg_8], rbx
0x18012a339  push    rdi
0x18012a33a  sub     rsp, 20h
0x18012a33e  mov     rbx, rcx
0x18012a341  lea     rax, ??_7CD3DShaderCacheInstaller@@6B@; const CD3DShaderCacheInstaller::`vftable'
0x18012a348  mov     [rcx], rax
0x18012a34b  mov     [rsp+28h+arg_0], 0
0x18012a350  lea     rdx, [rsp+28h+arg_0]; bool *
0x18012a355  mov     rcx, [rcx+58h]; HKEY
0x18012a359  call    ?IsKeyEmpty@RegistryReader@@SAJPEAUHKEY__@@PEA_N@Z; RegistryReader::IsKeyEmpty(HKEY__ *,bool *)
0x18012a35e  test    eax, eax
0x18012a360  js      short loc_18012A3A3
0x18012a362  cmp     [rsp+28h+arg_0], 0
0x18012a367  jz      short loc_18012A3A3
0x18012a369  lea     rdx, [rbx+30h]
0x18012a36d  cmp     qword ptr [rdx+18h], 7
0x18012a372  jbe     short loc_18012A377
0x18012a374  mov     rdx, [rdx]; lpSubKey
0x18012a377  mov     eax, [rbx+50h]
0x18012a37a  neg     eax
0x18012a37c  sbb     rcx, rcx
0x18012a37f  neg     rcx
0x18012a382  add     rcx, 0FFFFFFFF80000001h; hKey
0x18012a389  xor     r9d, r9d; Reserved
0x18012a38c  mov     r8d, 100h; samDesired
0x18012a392  call    cs:__imp_RegDeleteKeyExW
0x18012a398  test    eax, eax
0x18012a39a  jz      short loc_18012A3A3
0x18012a39c  mov     ecx, eax; int
0x18012a39e  call    ?RegistryError@@YAXJ@Z; RegistryError(long)
0x18012a3a3  mov     rcx, [rbx+88h]
0x18012a3aa  test    rcx, rcx
0x18012a3ad  jz      short loc_18012A3C0
0x18012a3af  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18012a3b5  mov     qword ptr [rbx+88h], 0
0x18012a3c0  lea     rcx, [rbx+68h]
0x18012a3c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a3c9  lea     rcx, [rbx+60h]
0x18012a3cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18012a3d2  lea     rcx, [rbx+58h]
0x18012a3d6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012a3db  lea     rcx, [rbx+30h]
0x18012a3df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012a3e4  mov     rcx, [rbx+18h]
0x18012a3e8  test    rcx, rcx
0x18012a3eb  jz      short loc_18012A42B
0x18012a3ed  mov     rax, [rbx+28h]
0x18012a3f1  sub     rax, rcx
0x18012a3f4  sar     rax, 5
0x18012a3f8  mov     rdx, 8E38E38E38E38E39h
0x18012a402  imul    rax, rdx
0x18012a406  lea     rdx, [rax+rax*8]
0x18012a40a  shl     rdx, 5
0x18012a40e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012a413  mov     qword ptr [rbx+18h], 0
0x18012a41b  mov     qword ptr [rbx+20h], 0
0x18012a423  mov     qword ptr [rbx+28h], 0
0x18012a42b  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18012a432  mov     rbx, [rsp+28h+arg_8]
0x18012a437  add     rsp, 20h
0x18012a43b  pop     rdi
0x18012a43c  retn
```
