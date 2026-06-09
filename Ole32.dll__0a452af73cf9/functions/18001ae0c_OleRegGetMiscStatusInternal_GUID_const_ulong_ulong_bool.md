# OleRegGetMiscStatusInternal(_GUID const &,ulong,ulong *,bool)

- ea: `0x18001ae0c`
- end: `0x18001afc4`
- name: `?OleRegGetMiscStatusInternal@@YAJAEBU_GUID@@KPEAK_N@Z`
- size: `440`
- prototype: `HRESULT __fastcall(const _GUID *clsid, unsigned int dwAspect, unsigned int *pdwStatus, bool clsid)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ac90`
- `0x18001ae00`
- `0x18009fa80`

## callees

- `0x1800185ec`
- `0x18001a3c8`
- `0x18001aa8c`
- `0x18001ae0c`
- `0x18001afcc`
- `0x18001b0e4`
- `0x18004fe4c`
- `0x180098e04`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001afb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001aee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001afb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aec0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001aec0`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001ae93`
- `api-ms-win-core-com-private-l1-3-1!InternalRegOpenClassKey` at `0x18001ae93`

## string_xrefs

- `0x18001af2d`: `com\ole32\ole232\stdimpl\olereg.cpp`

## pseudocode

```c
__int64 __fastcall OleRegGetMiscStatusInternal(
        const _GUID *clsid,
        unsigned int dwAspect,
        unsigned int *pdwStatus,
        bool a4)
{
  HRESULT MiscStatus; // eax
  IOleClassInfo *m_ptr; // rcx
  HRESULT v9; // eax
  unsigned int Dword; // ebx
  void (*Release)(void); // rax
  wil::com_ptr_t<IOleClassInfo,wil::err_returncode_policy> oleClassInfo; // [rsp+30h] [rbp-28h] BYREF
  HKEY__ *hkeyMisc; // [rsp+38h] [rbp-20h] BYREF
  HKEY__ *hkeyClsid; // [rsp+40h] [rbp-18h] BYREF
  void *retaddr; // [rsp+78h] [rbp+20h]

  oleClassInfo.m_ptr = 0;
  hkeyClsid = 0;
  hkeyMisc = 0;
  if ( !pdwStatus )
    return (unsigned int)-2147024809;
  *pdwStatus = 0;
  MiscStatus = FusionpOleRegGetMiscStatus(clsid, dwAspect, pdwStatus);
  m_ptr = oleClassInfo.m_ptr;
  if ( MiscStatus )
  {
    oleClassInfo.m_ptr = 0;
    if ( m_ptr )
      ((void (__fastcall *)(IOleClassInfo *))m_ptr->lpVtbl->Release)(m_ptr);
    if ( GetClassInfoWithInprocOrLocalServer(
           clsid,
           0,
           &GUID_e942fe11_d674_da46_8c4f_c9568fc9d593,
           (void **)&oleClassInfo.m_ptr) >= 0 )
    {
      Dword = OleClassInfoRegGetMiscStatus(oleClassInfo.m_ptr, dwAspect, pdwStatus);
      wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>((wil::com_ptr_t<IProxyServerIdentity,wil::err_returncode_policy> *)&oleClassInfo);
      return Dword;
    }
    v9 = InternalRegOpenClassKey(clsid, 131097, &hkeyClsid);
    Dword = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x290u, "com\\ole32\\ole232\\stdimpl\\olereg.cpp", v9);
      if ( !oleClassInfo.m_ptr )
        return Dword;
      Release = (void (*)(void))oleClassInfo.m_ptr->lpVtbl->Release;
    }
    else
    {
      Dword = 0;
      if ( !RegOpenKeyExW(hkeyClsid, Com::Catalog::Constants::MiscStatus, 0, 0x20019u, &hkeyMisc)
        && OleRegGetDword_0(hkeyMisc, dwAspect, pdwStatus) )
      {
        Dword = OleRegGetDword(hkeyMisc, 0, pdwStatus);
      }
      if ( hkeyMisc )
      {
        RegCloseKey(hkeyMisc);
        hkeyMisc = 0;
      }
      if ( hkeyClsid )
      {
        RegCloseKey(hkeyClsid);
        hkeyClsid = 0;
      }
      if ( !oleClassInfo.m_ptr )
        return Dword;
      Release = (void (*)(void))oleClassInfo.m_ptr->lpVtbl->Release;
    }
    Release();
    return Dword;
  }
  if ( oleClassInfo.m_ptr )
    ((void (*)(void))oleClassInfo.m_ptr->lpVtbl->Release)();
  return 0;
}

```

## disassembly

```asm
0x18001ae0c  push    rbp
0x18001ae0e  push    rbx
0x18001ae0f  push    rsi
0x18001ae10  push    rdi
0x18001ae11  mov     rbp, rsp
0x18001ae14  sub     rsp, 58h
0x18001ae18  mov     [rbp+oleClassInfo.m_ptr], 0
0x18001ae20  mov     rdi, pdwStatus
0x18001ae23  mov     [rbp+hkeyClsid], 0
0x18001ae2b  mov     esi, dwAspect
0x18001ae2d  mov     [rbp+hkeyMisc], 0
0x18001ae35  mov     rbx, clsid
0x18001ae38  test    pdwStatus, pdwStatus
0x18001ae3b  jz      loc_18001AF53
0x18001ae41  mov     dword ptr [pdwStatus], 0
0x18001ae48  call    FusionpOleRegGetMiscStatus
0x18001ae4d  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18001ae51  test    eax, eax
0x18001ae53  jz      loc_18001AF14
0x18001ae59  mov     [rbp+oleClassInfo.m_ptr], 0
0x18001ae61  test    clsid, clsid
0x18001ae64  jnz     loc_18001AF5A
0x18001ae6a  lea     r9, [rbp+oleClassInfo]; ppv
0x18001ae6e  xor     dwAspect, dwAspect; pComCatalog
0x18001ae70  lea     pdwStatus, _GUID_e942fe11_d674_da46_8c4f_c9568fc9d593; riid
0x18001ae77  mov     clsid, rbx; clsid
0x18001ae7a  call    ?GetClassInfoWithInprocOrLocalServer@@YAJAEBU_GUID@@PEAUIComCatalogSCM@@0PEAPEAX@Z; GetClassInfoWithInprocOrLocalServer(_GUID const &,IComCatalogSCM *,_GUID const &,void * *)
0x18001ae7f  test    eax, eax
0x18001ae81  jns     loc_18001AF6B
0x18001ae87  lea     pdwStatus, [rbp+hkeyClsid]
0x18001ae8b  mov     dwAspect, 20019h
0x18001ae90  mov     clsid, rbx
0x18001ae93  call    cs:__imp_InternalRegOpenClassKey
0x18001ae99  mov     ebx, eax
0x18001ae9b  test    eax, eax
0x18001ae9d  js      loc_18001AF29
0x18001aea3  mov     clsid, [rbp+hkeyClsid]; hKey
0x18001aea7  lea     rax, [rbp+hkeyMisc]
0x18001aeab  mov     r9d, 20019h; samDesired
0x18001aeb1  mov     [rsp+58h+phkResult], rax; phkResult
0x18001aeb6  xor     r8d, r8d; ulOptions
0x18001aeb9  lea     rdx, ?MiscStatus@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18001aec0  call    cs:__imp_RegOpenKeyExW
0x18001aec6  xor     ebx, ebx
0x18001aec8  test    eax, eax
0x18001aeca  jz      loc_18001AF86
0x18001aed0  mov     clsid, [rbp+hkeyMisc]; hKey
0x18001aed4  test    clsid, clsid
0x18001aed7  jnz     loc_18001AFB1
0x18001aedd  mov     clsid, [rbp+hkeyClsid]; hKey
0x18001aee1  test    clsid, clsid
0x18001aee4  jz      short $safeRtn_0
0x18001aee6  call    cs:__imp_RegCloseKey
0x18001aeec  mov     [rbp+hkeyClsid], 0
0x18001aef4  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18001aef8  test    clsid, clsid
0x18001aefb  jz      short loc_18001AF09
0x18001aefd  mov     rax, [clsid]
0x18001af00  mov     rax, [rax+10h]
0x18001af04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af09  mov     eax, ebx
0x18001af0b  add     rsp, 58h
0x18001af0f  pop     rdi
0x18001af10  pop     rsi
0x18001af11  pop     rbx
0x18001af12  pop     rbp
0x18001af13  retn
0x18001af14  test    clsid, clsid
0x18001af17  jz      short loc_18001AF25
0x18001af19  mov     rax, [clsid]
0x18001af1c  mov     rax, [rax+10h]
0x18001af20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af25  xor     eax, eax
0x18001af27  jmp     short loc_18001AF0B
0x18001af29  mov     clsid, [rbp+20h]; callerReturnAddress
0x18001af2d  lea     pdwStatus, aComOle32Ole232_5; "com\\ole32\\ole232\\stdimpl\\olereg.cpp"
0x18001af34  mov     r9d, ebx; hr
0x18001af37  mov     dwAspect, 290h; lineNumber
0x18001af3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af41  mov     clsid, [rbp+oleClassInfo.m_ptr]
0x18001af45  test    clsid, clsid
0x18001af48  jz      short loc_18001AF09
0x18001af4a  mov     rdx, [clsid]
0x18001af4d  mov     rax, [rdx+10h]
0x18001af51  jmp     short loc_18001AF04
0x18001af53  mov     ebx, 80070057h
0x18001af58  jmp     short loc_18001AF09
0x18001af5a  mov     rax, [clsid]
0x18001af5d  mov     rax, [rax+10h]
0x18001af61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af66  jmp     loc_18001AE6A
0x18001af6b  mov     clsid, [rbp+oleClassInfo.m_ptr]; pOleClassInfo
0x18001af6f  mov     pdwStatus, rdi; pdwStatus
0x18001af72  mov     dwAspect, esi; dwAspect
0x18001af74  call    OleClassInfoRegGetMiscStatus
0x18001af79  lea     clsid, [rbp+oleClassInfo]; this
0x18001af7d  mov     ebx, eax
0x18001af7f  call    ??1?$com_ptr_t@UICallFrameEvents@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>::~com_ptr_t<ICallFrameEvents,wil::err_returncode_policy>(void)
0x18001af84  jmp     short loc_18001AF09
0x18001af86  mov     clsid, [rbp+hkeyMisc]; hkey
0x18001af8a  mov     pdwStatus, rdi; pdw
0x18001af8d  mov     dwAspect, esi; dwKey
0x18001af8f  call    OleRegGetDword_0
0x18001af94  test    eax, eax
0x18001af96  jz      $errRtn_10
0x18001af9c  mov     clsid, [rbp+hkeyMisc]; hkey
0x18001afa0  mov     pdwStatus, rdi; pdw
0x18001afa3  xor     dwAspect, dwAspect; szKey
0x18001afa5  call    OleRegGetDword
0x18001afaa  mov     ebx, eax
0x18001afac  jmp     $errRtn_10
0x18001afb1  call    cs:__imp_RegCloseKey
0x18001afb7  mov     [rbp+hkeyMisc], 0
0x18001afbf  jmp     loc_18001AEDD
```
