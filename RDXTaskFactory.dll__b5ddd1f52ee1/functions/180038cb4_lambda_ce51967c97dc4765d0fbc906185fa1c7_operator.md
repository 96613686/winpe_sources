# _lambda_ce51967c97dc4765d0fbc906185fa1c7_::operator()

- ea: `0x180038cb4`
- end: `0x180038dcd`
- name: `_lambda_ce51967c97dc4765d0fbc906185fa1c7_::operator()`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800407b0`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x180038cb4`
- `0x18003f8b0`
- `0x180050010`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileW` at `0x180038d31`
- `SHCORE!SHCreateStreamOnFileW` at `0x180038d31`
- `SHLWAPI!PathFileExistsW` at `0x180038cc5`
- `SHLWAPI!PathFileExistsW` at `0x180038cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038d04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038d04`

## string_xrefs

- `0x180038d91`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180038da6`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x180038dba`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall lambda_ce51967c97dc4765d0fbc906185fa1c7_::operator()(__int64 a1)
{
  int result; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  HRESULT v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  int ppv; // [rsp+20h] [rbp-28h]
  wil::ResultException *v16; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  IStream *ppstm; // [rsp+58h] [rbp+10h] BYREF
  LPVOID v20; // [rsp+60h] [rbp+18h] BYREF

  result = PathFileExistsW(*(LPCWSTR *)(a1 + 8));
  if ( result )
  {
    v20 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20, v3, v4);
    v5 = CoCreateInstance(&CLSID_UserTileStore, 0, 1u, &GUID_fb69bc98_66a0_47ba_8b1d_f79b9e842bbc, &v20);
    try
    {
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A0,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v5,
          ppv);
      ppstm = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm, v6, v7);
      v8 = SHCreateStreamOnFileW(*(LPCWSTR *)(a1 + 8), 0, &ppstm);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A2,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v8,
          ppv);
      LOBYTE(v9) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask>::GetImpl'::`2'::impl,
        v9);
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IStream *))(*(_QWORD *)v20 + 168LL))(v20, 0, ppstm);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6A5,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v10,
          ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm, v11, v12);
      result = Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20, v13, v14);
    }
    catch ( wil::ResultException *v16 )
    {
      result = (int)v16;
      **(_DWORD **)(a1 + 16) = *((_DWORD *)v16 + 8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180038cb4  mov     [rsp+arg_0], rcx
0x180038cb9  push    rbx
0x180038cba  sub     rsp, 40h
0x180038cbe  mov     rbx, rcx
0x180038cc1  mov     rcx, [rcx+8]; pszPath
0x180038cc5  call    cs:__imp_PathFileExistsW
0x180038ccb  test    eax, eax
0x180038ccd  jz      loc_180038D88
0x180038cd3  mov     [rsp+48h+arg_10], 0
0x180038cdc  lea     rcx, [rsp+48h+arg_10]
0x180038ce1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038ce6  lea     rax, [rsp+48h+arg_10]
0x180038ceb  mov     qword ptr [rsp+48h+ppv], rax; int
0x180038cf0  lea     r9, _GUID_fb69bc98_66a0_47ba_8b1d_f79b9e842bbc; riid
0x180038cf7  xor     edx, edx; pUnkOuter
0x180038cf9  lea     r8d, [rdx+1]; dwClsContext
0x180038cfd  lea     rcx, CLSID_UserTileStore; rclsid
0x180038d04  call    cs:__imp_CoCreateInstance
0x180038d0a  mov     rcx, [rsp+48h]; this
0x180038d0f  test    eax, eax
0x180038d11  js      short loc_180038D8E
0x180038d13  mov     [rsp+48h+ppstm], 0
0x180038d1c  lea     rcx, [rsp+48h+ppstm]
0x180038d21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038d26  lea     r8, [rsp+48h+ppstm]; ppstm
0x180038d2b  xor     edx, edx; grfMode
0x180038d2d  mov     rcx, [rbx+8]; pszFile
0x180038d31  call    cs:__imp_SHCreateStreamOnFileW
0x180038d37  mov     rcx, [rsp+48h]; this
0x180038d3c  test    eax, eax
0x180038d3e  js      short loc_180038DA3
0x180038d40  mov     dl, 1
0x180038d42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask> `wil::Feature<__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask>::GetImpl(void)'::`2'::impl
0x180038d49  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_RDX_SetAccountPictureTask>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180038d4e  mov     rcx, [rsp+48h+arg_10]
0x180038d53  mov     rax, [rcx]
0x180038d56  mov     r8, [rsp+48h+ppstm]
0x180038d5b  xor     edx, edx
0x180038d5d  mov     rax, [rax+0A8h]
0x180038d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d69  mov     rcx, [rsp+48h]; this
0x180038d6e  test    eax, eax
0x180038d70  js      short loc_180038DB7
0x180038d72  lea     rcx, [rsp+48h+ppstm]
0x180038d77  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038d7c  nop
0x180038d7d  lea     rcx, [rsp+48h+arg_10]
0x180038d82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038d87  nop
0x180038d88  add     rsp, 40h
0x180038d8c  pop     rbx
0x180038d8d  retn
0x180038d8e  mov     r9d, eax; char *
0x180038d91  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038d98  mov     edx, 6A0h; void *
0x180038d9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038da3  mov     r9d, eax; char *
0x180038da6  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038dad  mov     edx, 6A2h; void *
0x180038db2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180038db7  mov     r9d, eax; char *
0x180038dba  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038dc1  mov     edx, 6A5h; void *
0x180038dc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
