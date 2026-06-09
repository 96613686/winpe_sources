# ApplicationSpecificEndpointInfo::ClearAllPersistedApplicationDefaultEndpoints(void)

- ea: `0x1800469b8`
- end: `0x180046a6d`
- name: `?ClearAllPersistedApplicationDefaultEndpoints@ApplicationSpecificEndpointInfo@@SAJXZ`
- size: `181`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044800`

## callees

- `0x180012844`
- `0x1800232a0`
- `0x18003a5fc`
- `0x1800469b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046a2d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046a1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046a1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046a5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046a5a`
- `RPCRT4!RpcRevertToSelf` at `0x180046a60`
- `RPCRT4!RpcRevertToSelf` at `0x180046a60`
- `RPCRT4!RpcImpersonateClient` at `0x1800469be`
- `RPCRT4!RpcImpersonateClient` at `0x1800469be`

## pseudocode

```c
__int64 ApplicationSpecificEndpointInfo::ClearAllPersistedApplicationDefaultEndpoints(void)
{
  unsigned int v0; // eax
  LSTATUS v2; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = RpcImpersonateClient(0);
  if ( v0 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x4E,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
             (const char *)v0,
             phkResult);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\Audio\\DefaultEndpoint", 0, 2u, &hKey) )
  {
    v2 = RegDeleteTreeW(hKey, 0);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
        (const char *)(unsigned int)v2,
        phkResulta);
  }
  if ( hKey )
    RegCloseKey(hKey);
  RpcRevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x1800469b8  sub     rsp, 38h
0x1800469bc  xor     ecx, ecx; BindingHandle
0x1800469be  call    cs:__imp_RpcImpersonateClient
0x1800469c4  test    eax, eax
0x1800469c6  jz      short loc_1800469E6
0x1800469c8  mov     rcx, [rsp+38h]; this
0x1800469cd  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x1800469d4  mov     r9d, eax; char *
0x1800469d7  mov     edx, 4Eh ; 'N'; void *
0x1800469dc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800469e1  jmp     loc_180046A68
0x1800469e6  xor     edx, edx
0x1800469e8  mov     [rsp+38h+hKey], 0
0x1800469f1  lea     rcx, [rsp+38h+hKey]
0x1800469f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800469fb  lea     rax, [rsp+38h+hKey]
0x180046a00  mov     r9d, 2; samDesired
0x180046a06  xor     r8d, r8d; ulOptions
0x180046a09  mov     qword ptr [rsp+38h+phkResult], rax; int
0x180046a0e  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Multimedia\\Audio"...
0x180046a15  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180046a1c  call    cs:__imp_RegOpenKeyExW
0x180046a22  test    eax, eax
0x180046a24  jnz     short loc_180046A50
0x180046a26  mov     rcx, [rsp+38h+hKey]; hKey
0x180046a2b  xor     edx, edx; lpSubKey
0x180046a2d  call    cs:__imp_RegDeleteTreeW
0x180046a33  test    eax, eax
0x180046a35  jns     short loc_180046A50
0x180046a37  mov     rcx, [rsp+38h]; this
0x180046a3c  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x180046a43  mov     r9d, eax; char *
0x180046a46  mov     edx, 5Ah ; 'Z'; void *
0x180046a4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180046a50  mov     rcx, [rsp+38h+hKey]; hKey
0x180046a55  test    rcx, rcx
0x180046a58  jz      short loc_180046A60
0x180046a5a  call    cs:__imp_RegCloseKey
0x180046a60  call    cs:__imp_RpcRevertToSelf
0x180046a66  xor     eax, eax
0x180046a68  add     rsp, 38h
0x180046a6c  retn
```
