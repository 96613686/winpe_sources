# RADC::_anonymous_namespace_::IsMstscUninstalled

- ea: `0x180078420`
- end: `0x180078577`
- name: `RADC::_anonymous_namespace_::IsMstscUninstalled`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180078e38`

## callees

- `0x18000b1d8`
- `0x18000ece0`
- `0x1800776d0`
- `0x180077704`
- `0x180077728`
- `0x18007789c`
- `0x180078420`
- `0x180079b0c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007845c`
- `ole32!CoTaskMemFree` at `0x18007845c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007850b`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18007850b`
- `SHLWAPI!PathFileExistsW` at `0x18007854d`
- `SHLWAPI!PathFileExistsW` at `0x18007854d`
- `SHELL32!SHGetKnownFolderPath` at `0x180078484`
- `SHELL32!SHGetKnownFolderPath` at `0x180078484`

## string_xrefs

- `0x1800784c5`: `SHGetKnownFolderPath(FOLDERID_System) failed`
- `0x180078540`: `PathAllocCombine failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool RADC::_anonymous_namespace_::IsMstscUninstalled()
{
  bool v0; // di
  HRESULT v1; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v3; // edx
  const char *v4; // rcx
  PWSTR *v5; // rax
  LPVOID pv; // [rsp+60h] [rbp+20h] BYREF
  LPCWSTR pszPath; // [rsp+68h] [rbp+28h] BYREF

  v0 = 0;
  pszPath = 0;
  pv = 0;
  v1 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, (PWSTR *)&pv);
  if ( v1 >= 0 )
  {
    v5 = (PWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszPath);
    v1 = PathAllocCombine((PCWSTR)pv, L"mstsc.exe", 0, v5);
    if ( v1 >= 0 )
    {
      v0 = !PathFileExistsW(pszPath);
      goto LABEL_13;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v3 = 46;
      v4 = "PathAllocCombine failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 45;
    v4 = "SHGetKnownFolderPath(FOLDERID_System) failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)WPP_8f87464425bd38a0257d033d5861bd18_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v4,
      v1,
      -2);
  }
LABEL_13:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
  return v0;
}

```

## disassembly

```asm
0x180078420  push    rbp
0x180078422  push    rbx
0x180078423  push    rdi
0x180078424  mov     rbp, rsp
0x180078427  sub     rsp, 40h
0x18007842b  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180078433  xor     dil, dil
0x180078436  mov     [rbp+pv], 0
0x18007843e  mov     [rbp+pszPath], 0
0x180078446  mov     rbx, [rbp+pv]
0x18007844a  test    rbx, rbx
0x18007844d  jz      short loc_18007846C
0x18007844f  lea     rcx, [rbp+arg_10]; this
0x180078453  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180078458  nop
0x180078459  mov     rcx, rbx; pv
0x18007845c  call    cs:__imp_CoTaskMemFree
0x180078462  nop
0x180078463  lea     rcx, [rbp+arg_10]; this
0x180078467  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007846c  mov     [rbp+pv], 0
0x180078474  lea     r9, [rbp+pv]; ppszPath
0x180078478  xor     r8d, r8d; hToken
0x18007847b  xor     edx, edx; dwFlags
0x18007847d  lea     rcx, FOLDERID_System; rfid
0x180078484  call    cs:__imp_SHGetKnownFolderPath
0x18007848a  mov     ebx, eax
0x18007848c  test    eax, eax
0x18007848e  jns     short loc_1800784F1
0x180078490  lea     rcx, WPP_GLOBAL_Control
0x180078497  mov     rax, cs:WPP_GLOBAL_Control
0x18007849e  cmp     rax, rcx
0x1800784a1  jz      loc_180078559
0x1800784a7  test    byte ptr [rax+1Ch], 8
0x1800784ab  jz      loc_180078559
0x1800784b1  cmp     byte ptr [rax+19h], 2
0x1800784b5  jb      loc_180078559
0x1800784bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800784c0  mov     edx, 2Dh ; '-'
0x1800784c5  lea     rcx, aShgetknownfold; "SHGetKnownFolderPath(FOLDERID_System) f"...
0x1800784cc  mov     [rsp+40h+var_18], ebx
0x1800784d0  mov     [rsp+40h+var_20], rcx
0x1800784d5  mov     r9d, eax
0x1800784d8  lea     r8, WPP_8f87464425bd38a0257d033d5861bd18_Traceguids
0x1800784df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800784e6  mov     rcx, [rcx+10h]
0x1800784ea  call    WPP_SF_DsD
0x1800784ef  jmp     short loc_180078559
0x1800784f1  lea     rcx, [rbp+pszPath]
0x1800784f5  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800784fa  mov     r9, rax; ppszPathOut
0x1800784fd  xor     r8d, r8d; dwFlags
0x180078500  lea     rdx, pszMore; "mstsc.exe"
0x180078507  mov     rcx, [rbp+pv]; pszPathIn
0x18007850b  call    cs:__imp_PathAllocCombine
0x180078511  mov     ebx, eax
0x180078513  test    eax, eax
0x180078515  jns     short loc_180078549
0x180078517  lea     rcx, WPP_GLOBAL_Control
0x18007851e  mov     rax, cs:WPP_GLOBAL_Control
0x180078525  cmp     rax, rcx
0x180078528  jz      short loc_180078559
0x18007852a  test    byte ptr [rax+1Ch], 8
0x18007852e  jz      short loc_180078559
0x180078530  cmp     byte ptr [rax+19h], 2
0x180078534  jb      short loc_180078559
0x180078536  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007853b  mov     edx, 2Eh ; '.'
0x180078540  lea     rcx, aPathalloccombi; "PathAllocCombine failed"
0x180078547  jmp     short loc_1800784CC
0x180078549  mov     rcx, [rbp+pszPath]; pszPath
0x18007854d  call    cs:__imp_PathFileExistsW
0x180078553  test    eax, eax
0x180078555  setz    dil
0x180078559  lea     rcx, [rbp+pszPath]
0x18007855d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180078562  nop
0x180078563  lea     rcx, [rbp+pv]
0x180078567  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007856c  mov     al, dil
0x18007856f  add     rsp, 40h
0x180078573  pop     rdi
0x180078574  pop     rbx
0x180078575  pop     rbp
0x180078576  retn
```
