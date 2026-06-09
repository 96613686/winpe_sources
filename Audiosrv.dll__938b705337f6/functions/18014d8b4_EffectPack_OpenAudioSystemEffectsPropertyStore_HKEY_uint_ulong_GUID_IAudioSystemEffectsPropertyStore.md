# EffectPack::OpenAudioSystemEffectsPropertyStore(HKEY__ *,uint,ulong,_GUID *,IAudioSystemEffectsPropertyStore * *)

- ea: `0x18014d8b4`
- end: `0x18014da61`
- name: `?OpenAudioSystemEffectsPropertyStore@EffectPack@@SAJPEAUHKEY__@@IKPEAU_GUID@@PEAPEAUIAudioSystemEffectsPropertyStore@@@Z`
- size: `429`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, DWORD dwIndex@<edx>, unsigned int@<r8d>, struct _GUID *@<r9>, struct IAudioSystemEffectsPropertyStore **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180141580`

## callees

- `0x1800126bc`
- `0x1800a5358`
- `0x1800c0af8`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x18014d8b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014d9bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014d9bf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18014d94a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18014d94a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014d96d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014d96d`
- `MMDevAPI!__imp_MMDeviceCreateAudioSystemEffectsPropertyStore` at `0x18014d9f9`
- `MMDevAPI!__imp_MMDeviceCreateAudioSystemEffectsPropertyStore` at `0x18014d9f9`

## string_xrefs

- `0x18014d980`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18014d9d0`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18014da0c`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

## pseudocode

```c
__int64 __fastcall EffectPack::OpenAudioSystemEffectsPropertyStore(
        HKEY hKey,
        DWORD dwIndex,
        __int64 a3,
        struct _GUID *a4,
        struct IAudioSystemEffectsPropertyStore **a5)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // eax
  HKEY v12; // rcx
  int AudioSystemEffectsPropertyStore; // eax
  int lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *a4 = GUID_00000000_0000_0000_0000_000000000000;
  *a5 = 0;
  memset_0(Name, 0, 0x208u);
  cchName = 260;
  if ( RegEnumKeyExW(hKey, dwIndex, Name, &cchName, 0, 0, 0, 0) != 259 )
  {
    pclsid = 0;
    v8 = CLSIDFromString(Name, &pclsid);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
        (const char *)(unsigned int)v8,
        lpReserved);
      return v9;
    }
    phkResult = 0;
    v11 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
    if ( v11 )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x166,
             (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
             (const char *)v11,
             lpReserveda);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return v9;
    }
    v12 = phkResult;
    phkResult = 0;
    AudioSystemEffectsPropertyStore = MMDeviceCreateAudioSystemEffectsPropertyStore(v12, a5);
    v9 = AudioSystemEffectsPropertyStore;
    if ( AudioSystemEffectsPropertyStore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x169,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\effectpack.cpp",
        (const char *)(unsigned int)AudioSystemEffectsPropertyStore,
        lpReserveda);
      goto LABEL_9;
    }
    *a4 = pclsid;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  return 0;
}

```

## disassembly

```asm
0x18014d8b4  push    rbp
0x18014d8b6  push    rbx
0x18014d8b7  push    rsi
0x18014d8b8  push    rdi
0x18014d8b9  push    r14
0x18014d8bb  lea     rbp, [rsp-180h]
0x18014d8c3  sub     rsp, 280h
0x18014d8ca  mov     rax, cs:__security_cookie
0x18014d8d1  xor     rax, rsp
0x18014d8d4  mov     [rbp+1A0h+var_30], rax
0x18014d8db  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18014d8e2  mov     rsi, [rbp+1A0h+arg_20]
0x18014d8e9  mov     ebx, edx
0x18014d8eb  mov     r14, rcx
0x18014d8ee  xor     edx, edx; Val
0x18014d8f0  movdqu  xmmword ptr [r9], xmm0
0x18014d8f5  mov     r8d, 208h; Size
0x18014d8fb  lea     rcx, [rsp+2A0h+Name]; void *
0x18014d900  mov     qword ptr [rsi], 0
0x18014d907  mov     rdi, r9
0x18014d90a  call    memset_0
0x18014d90f  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18014d918  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18014d91d  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x18014d926  lea     r8, [rsp+2A0h+Name]; lpName
0x18014d92b  mov     [rsp+2A0h+lpClass], 0; lpClass
0x18014d934  mov     edx, ebx; dwIndex
0x18014d936  mov     rcx, r14; hKey
0x18014d939  mov     [rsp+2A0h+lpReserved], 0; int
0x18014d942  mov     [rsp+2A0h+cchName], 104h
0x18014d94a  call    cs:__imp_RegEnumKeyExW
0x18014d950  cmp     eax, 103h
0x18014d955  jz      loc_18014DA42
0x18014d95b  xorps   xmm0, xmm0
0x18014d95e  lea     rdx, [rsp+2A0h+pclsid]; pclsid
0x18014d963  lea     rcx, [rsp+2A0h+Name]; lpsz
0x18014d968  movups  xmmword ptr [rsp+2A0h+pclsid.Data1], xmm0
0x18014d96d  call    cs:__imp_CLSIDFromString
0x18014d973  mov     ebx, eax
0x18014d975  test    eax, eax
0x18014d977  jns     short loc_18014D99B
0x18014d979  mov     rcx, [rbp+1A8h]; this
0x18014d980  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014d987  mov     r9d, eax; char *
0x18014d98a  mov     edx, 162h; void *
0x18014d98f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014d994  mov     eax, ebx
0x18014d996  jmp     loc_18014DA44
0x18014d99b  lea     rax, [rsp+2A0h+phkResult]
0x18014d9a0  mov     [rsp+2A0h+phkResult], 0
0x18014d9a9  mov     r9d, 20019h; samDesired
0x18014d9af  mov     [rsp+2A0h+lpReserved], rax; int
0x18014d9b4  xor     r8d, r8d; ulOptions
0x18014d9b7  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x18014d9bc  mov     rcx, r14; hKey
0x18014d9bf  call    cs:__imp_RegOpenKeyExW
0x18014d9c5  test    eax, eax
0x18014d9c7  jz      short loc_18014D9E8
0x18014d9c9  mov     rcx, [rbp+1A8h]; this
0x18014d9d0  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014d9d7  mov     r9d, eax; char *
0x18014d9da  mov     edx, 166h; void *
0x18014d9df  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18014d9e4  mov     ebx, eax
0x18014d9e6  jmp     short loc_18014DA20
0x18014d9e8  mov     rcx, [rsp+2A0h+phkResult]
0x18014d9ed  mov     rdx, rsi
0x18014d9f0  mov     [rsp+2A0h+phkResult], 0
0x18014d9f9  call    cs:__imp_MMDeviceCreateAudioSystemEffectsPropertyStore
0x18014d9ff  mov     ebx, eax
0x18014da01  test    eax, eax
0x18014da03  jns     short loc_18014DA2F
0x18014da05  mov     rcx, [rbp+1A8h]; this
0x18014da0c  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014da13  mov     r9d, eax; char *
0x18014da16  mov     edx, 169h; void *
0x18014da1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014da20  lea     rcx, [rsp+2A0h+phkResult]
0x18014da25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014da2a  jmp     loc_18014D994
0x18014da2f  movups  xmm0, xmmword ptr [rsp+2A0h+pclsid.Data1]
0x18014da34  lea     rcx, [rsp+2A0h+phkResult]
0x18014da39  movdqu  xmmword ptr [rdi], xmm0
0x18014da3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014da42  xor     eax, eax
0x18014da44  mov     rcx, [rbp+1A0h+var_30]
0x18014da4b  xor     rcx, rsp; StackCookie
0x18014da4e  call    __security_check_cookie
0x18014da53  add     rsp, 280h
0x18014da5a  pop     r14
0x18014da5c  pop     rdi
0x18014da5d  pop     rsi
0x18014da5e  pop     rbx
0x18014da5f  pop     rbp
0x18014da60  retn
```
