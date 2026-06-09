# EffectPack::OpenAudioSystemEffectsPropertyStore(HKEY__ *,uint,ulong,_GUID *,IAudioSystemEffectsPropertyStore * *)

- ea: `0x18014e5c4`
- end: `0x18014e771`
- name: `?OpenAudioSystemEffectsPropertyStore@EffectPack@@SAJPEAUHKEY__@@IKPEAU_GUID@@PEAPEAUIAudioSystemEffectsPropertyStore@@@Z`
- size: `429`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, DWORD dwIndex@<edx>, unsigned int@<r8d>, struct _GUID *@<r9>, struct IAudioSystemEffectsPropertyStore **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180141e94`

## callees

- `0x18001280c`
- `0x1800a4af8`
- `0x1800befa8`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x18014e5c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014e6cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18014e6cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18014e65a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18014e65a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014e67d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18014e67d`
- `MMDevAPI!__imp_MMDeviceCreateAudioSystemEffectsPropertyStore` at `0x18014e709`
- `MMDevAPI!__imp_MMDeviceCreateAudioSystemEffectsPropertyStore` at `0x18014e709`

## string_xrefs

- `0x18014e690`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18014e6e0`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`
- `0x18014e71c`: `avcore\audiocore\server\lib\audioserviceutil\effectpack.cpp`

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
0x18014e5c4  push    rbp
0x18014e5c6  push    rbx
0x18014e5c7  push    rsi
0x18014e5c8  push    rdi
0x18014e5c9  push    r14
0x18014e5cb  lea     rbp, [rsp-180h]
0x18014e5d3  sub     rsp, 280h
0x18014e5da  mov     rax, cs:__security_cookie
0x18014e5e1  xor     rax, rsp
0x18014e5e4  mov     [rbp+1A0h+var_30], rax
0x18014e5eb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18014e5f2  mov     rsi, [rbp+1A0h+arg_20]
0x18014e5f9  mov     ebx, edx
0x18014e5fb  mov     r14, rcx
0x18014e5fe  xor     edx, edx; Val
0x18014e600  movdqu  xmmword ptr [r9], xmm0
0x18014e605  mov     r8d, 208h; Size
0x18014e60b  lea     rcx, [rsp+2A0h+Name]; void *
0x18014e610  mov     qword ptr [rsi], 0
0x18014e617  mov     rdi, r9
0x18014e61a  call    memset_0
0x18014e61f  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18014e628  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x18014e62d  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x18014e636  lea     r8, [rsp+2A0h+Name]; lpName
0x18014e63b  mov     [rsp+2A0h+lpClass], 0; lpClass
0x18014e644  mov     edx, ebx; dwIndex
0x18014e646  mov     rcx, r14; hKey
0x18014e649  mov     [rsp+2A0h+lpReserved], 0; int
0x18014e652  mov     [rsp+2A0h+cchName], 104h
0x18014e65a  call    cs:__imp_RegEnumKeyExW
0x18014e660  cmp     eax, 103h
0x18014e665  jz      loc_18014E752
0x18014e66b  xorps   xmm0, xmm0
0x18014e66e  lea     rdx, [rsp+2A0h+pclsid]; pclsid
0x18014e673  lea     rcx, [rsp+2A0h+Name]; lpsz
0x18014e678  movups  xmmword ptr [rsp+2A0h+pclsid.Data1], xmm0
0x18014e67d  call    cs:__imp_CLSIDFromString
0x18014e683  mov     ebx, eax
0x18014e685  test    eax, eax
0x18014e687  jns     short loc_18014E6AB
0x18014e689  mov     rcx, [rbp+1A8h]; this
0x18014e690  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014e697  mov     r9d, eax; char *
0x18014e69a  mov     edx, 162h; void *
0x18014e69f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014e6a4  mov     eax, ebx
0x18014e6a6  jmp     loc_18014E754
0x18014e6ab  lea     rax, [rsp+2A0h+phkResult]
0x18014e6b0  mov     [rsp+2A0h+phkResult], 0
0x18014e6b9  mov     r9d, 20019h; samDesired
0x18014e6bf  mov     [rsp+2A0h+lpReserved], rax; int
0x18014e6c4  xor     r8d, r8d; ulOptions
0x18014e6c7  lea     rdx, [rsp+2A0h+Name]; lpSubKey
0x18014e6cc  mov     rcx, r14; hKey
0x18014e6cf  call    cs:__imp_RegOpenKeyExW
0x18014e6d5  test    eax, eax
0x18014e6d7  jz      short loc_18014E6F8
0x18014e6d9  mov     rcx, [rbp+1A8h]; this
0x18014e6e0  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014e6e7  mov     r9d, eax; char *
0x18014e6ea  mov     edx, 166h; void *
0x18014e6ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18014e6f4  mov     ebx, eax
0x18014e6f6  jmp     short loc_18014E730
0x18014e6f8  mov     rcx, [rsp+2A0h+phkResult]
0x18014e6fd  mov     rdx, rsi
0x18014e700  mov     [rsp+2A0h+phkResult], 0
0x18014e709  call    cs:__imp_MMDeviceCreateAudioSystemEffectsPropertyStore
0x18014e70f  mov     ebx, eax
0x18014e711  test    eax, eax
0x18014e713  jns     short loc_18014E73F
0x18014e715  mov     rcx, [rbp+1A8h]; this
0x18014e71c  lea     r8, aAvcoreAudiocor_9; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014e723  mov     r9d, eax; char *
0x18014e726  mov     edx, 169h; void *
0x18014e72b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014e730  lea     rcx, [rsp+2A0h+phkResult]
0x18014e735  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014e73a  jmp     loc_18014E6A4
0x18014e73f  movups  xmm0, xmmword ptr [rsp+2A0h+pclsid.Data1]
0x18014e744  lea     rcx, [rsp+2A0h+phkResult]
0x18014e749  movdqu  xmmword ptr [rdi], xmm0
0x18014e74d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18014e752  xor     eax, eax
0x18014e754  mov     rcx, [rbp+1A0h+var_30]
0x18014e75b  xor     rcx, rsp; StackCookie
0x18014e75e  call    __security_check_cookie
0x18014e763  add     rsp, 280h
0x18014e76a  pop     r14
0x18014e76c  pop     rdi
0x18014e76d  pop     rsi
0x18014e76e  pop     rbx
0x18014e76f  pop     rbp
0x18014e770  retn
```
