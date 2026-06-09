# Windows::Internal::CapabilityAccess::Private::IsProcessRunningInRemoteSession(uint)

- ea: `0x180044664`
- end: `0x1800447bd`
- name: `?IsProcessRunningInRemoteSession@Private@CapabilityAccess@Internal@Windows@@YA_NI@Z`
- size: `345`
- prototype: `bool __fastcall(DWORD dwProcessId, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18006874c`

## callees

- `0x18002392c`
- `0x1800299c4`
- `0x18002f280`
- `0x180039e9c`
- `0x18003ce34`
- `0x180044664`
- `0x180058dfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800446bf`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800446bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004473a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004473a`
- `ntdll!RtlIsMultiSessionSku` at `0x180044675`
- `ntdll!RtlIsMultiSessionSku` at `0x180044675`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004469f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18004469f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::CapabilityAccess::Private::IsProcessRunningInRemoteSession(DWORD dwProcessId)
{
  const char *v3; // r9
  unsigned int v4; // eax
  unsigned int Uint32Value; // eax
  bool v6; // bl
  DWORD dwOptions; // [rsp+20h] [rbp-38h]
  bool *dwOptionsa; // [rsp+20h] [rbp-38h]
  DWORD dwOptionsb; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int16 v11; // [rsp+68h] [rbp+10h] BYREF
  DWORD pSessionId; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x818,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      dwOptions);
  if ( GetSystemMetrics(4096) )
    return 1;
  pSessionId = 0;
  if ( !ProcessIdToSessionId(dwProcessId, &pSessionId) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x822,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v3);
  phkResult = 0;
  LOBYTE(v11) = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v4 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\",
         0,
         0,
         0,
         0x20119u,
         0,
         &phkResult,
         0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x827,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)v4,
      (unsigned int)dwOptionsa);
  Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                  (Windows::Internal::CapabilityAccess::Private *)phkResult,
                  0,
                  L"GlassSessionId",
                  &v11,
                  dwOptionsa);
  if ( !(_BYTE)v11 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      dwOptionsb);
  v6 = pSessionId != Uint32Value;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return v6;
}

```

## disassembly

```asm
0x180044664  mov     [rsp+arg_0], rbx
0x180044669  push    rdi
0x18004466a  sub     rsp, 50h
0x18004466e  mov     edi, ecx
0x180044670  mov     rbx, [rsp+58h]
0x180044675  call    cs:__imp_RtlIsMultiSessionSku
0x18004467b  test    al, al
0x18004467d  jnz     short loc_18004469A
0x18004467f  mov     r9d, 8000FFFFh; char *
0x180044685  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004468c  mov     edx, 818h; void *
0x180044691  mov     rcx, rbx; this
0x180044694  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004469a  mov     ecx, 1000h; nIndex
0x18004469f  call    cs:__imp_GetSystemMetrics
0x1800446a5  test    eax, eax
0x1800446a7  jz      short loc_1800446B0
0x1800446a9  mov     al, 1
0x1800446ab  jmp     loc_1800447B2
0x1800446b0  mov     [rsp+58h+pSessionId], 0
0x1800446b8  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x1800446bd  mov     ecx, edi; dwProcessId
0x1800446bf  call    cs:__imp_ProcessIdToSessionId
0x1800446c5  mov     rcx, [rsp+58h]; this
0x1800446ca  test    eax, eax
0x1800446cc  jnz     short loc_1800446E0
0x1800446ce  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800446d5  mov     edx, 822h; void *
0x1800446da  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800446e0  mov     [rsp+58h+arg_18], 0
0x1800446e9  mov     byte ptr [rsp+58h+arg_8], 0
0x1800446ee  xor     edx, edx
0x1800446f0  lea     rcx, [rsp+58h+arg_18]
0x1800446f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800446fa  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180044703  lea     rax, [rsp+58h+arg_18]
0x180044708  mov     [rsp+58h+phkResult], rax; phkResult
0x18004470d  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180044716  mov     [rsp+58h+samDesired], 20119h; samDesired
0x18004471e  mov     dword ptr [rsp+58h+dwOptions], 0; int
0x180044726  xor     r9d, r9d; lpClass
0x180044729  xor     r8d, r8d; Reserved
0x18004472c  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180044733  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004473a  call    cs:__imp_RegCreateKeyExW
0x180044740  mov     rcx, [rsp+58h]; this
0x180044745  test    eax, eax
0x180044747  jz      short loc_18004475E
0x180044749  mov     r9d, eax; char *
0x18004474c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044753  mov     edx, 827h; void *
0x180044758  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004475e  lea     r9, [rsp+58h+arg_8]; unsigned __int16 *
0x180044763  lea     r8, aGlasssessionid; "GlassSessionId"
0x18004476a  xor     edx, edx; HKEY
0x18004476c  mov     rcx, [rsp+58h+arg_18]; this
0x180044771  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180044776  cmp     byte ptr [rsp+58h+arg_8], 0
0x18004477b  setz    dl
0x18004477e  mov     rcx, [rsp+58h]; this
0x180044783  test    dl, dl
0x180044785  jz      short loc_18004479F
0x180044787  mov     r9d, 8000FFFFh; char *
0x18004478d  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044794  mov     edx, 82Ah; void *
0x180044799  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004479f  cmp     [rsp+58h+pSessionId], eax
0x1800447a3  setnz   bl
0x1800447a6  lea     rcx, [rsp+58h+arg_18]
0x1800447ab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800447b0  mov     al, bl
0x1800447b2  mov     rbx, [rsp+58h+arg_0]
0x1800447b7  add     rsp, 50h
0x1800447bb  pop     rdi
0x1800447bc  retn
```
