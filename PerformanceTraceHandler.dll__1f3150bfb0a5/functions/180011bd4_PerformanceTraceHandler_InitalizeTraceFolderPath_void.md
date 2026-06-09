# PerformanceTraceHandler::InitalizeTraceFolderPath(void)

- ea: `0x180011bd4`
- end: `0x180011cd0`
- name: `?InitalizeTraceFolderPath@PerformanceTraceHandler@@AEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011cd8`

## callees

- `0x1800045b8`
- `0x180004c88`
- `0x180007f3c`
- `0x18000b524`
- `0x180010a90`
- `0x180010ca4`
- `0x180011bd4`
- `0x180013400`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c3d`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011c66`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180011c66`
- `SHELL32!SHGetKnownFolderPath` at `0x180011c0e`
- `SHELL32!SHGetKnownFolderPath` at `0x180011c0e`

## string_xrefs

- `0x180011c7c`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::InitalizeTraceFolderPath(PerformanceTraceHandler *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  void *v5; // rdi
  const WCHAR *v6; // rcx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PWSTR ppszPath; // [rsp+38h] [rbp+10h] BYREF
  char v11; // [rsp+40h] [rbp+18h] BYREF

  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v2 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0x8400u, 0, &ppszPath);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v5 = (void *)*((_QWORD *)this + 21);
    if ( v5 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
      LocalFree(v5);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
    }
    v6 = ppszPath;
    *((_QWORD *)this + 21) = 0;
    v2 = PathAllocCombine(v6, L"Traces", 0, (PWSTR *)this + 21);
    v3 = v2;
    if ( v2 >= 0 )
    {
      *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                              (char *)this + 192,
                              &v11)
               + 273LL) = 1;
      tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(&v11);
      v3 = 0;
      goto LABEL_9;
    }
    v4 = 124;
  }
  else
  {
    v4 = 122;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
    (const char *)(unsigned int)v2,
    v8);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
  return v3;
}

```

## disassembly

```asm
0x180011bd4  mov     rax, rsp
0x180011bd7  mov     [rax+8], rbx
0x180011bdb  mov     [rax+20h], rsi
0x180011bdf  push    rdi; int
0x180011be0  sub     rsp, 20h
0x180011be4  mov     rsi, rcx
0x180011be7  mov     qword ptr [rax+10h], 0
0x180011bef  lea     rcx, [rax+10h]
0x180011bf3  xor     edx, edx
0x180011bf5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180011bfa  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180011bff  xor     r8d, r8d; hToken
0x180011c02  mov     edx, 8400h; dwFlags
0x180011c07  lea     rcx, FOLDERID_LocalAppData; rfid
0x180011c0e  call    cs:__imp_SHGetKnownFolderPath
0x180011c14  mov     ebx, eax
0x180011c16  test    eax, eax
0x180011c18  jns     short loc_180011C21
0x180011c1a  mov     edx, 7Ah ; 'z'
0x180011c1f  jmp     short loc_180011C77
0x180011c21  lea     rbx, [rsi+0A8h]
0x180011c28  mov     rdi, [rbx]
0x180011c2b  test    rdi, rdi
0x180011c2e  jz      short loc_180011C4D
0x180011c30  lea     rcx, [rsp+28h+arg_10]; this
0x180011c35  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011c3a  mov     rcx, rdi; hMem
0x180011c3d  call    cs:__imp_LocalFree
0x180011c43  lea     rcx, [rsp+28h+arg_10]; this
0x180011c48  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011c4d  mov     rcx, [rsp+28h+ppszPath]; pszPathIn
0x180011c52  lea     rdx, aTraces; "Traces"
0x180011c59  mov     r9, rbx; ppszPathOut
0x180011c5c  mov     qword ptr [rbx], 0
0x180011c63  xor     r8d, r8d; dwFlags
0x180011c66  call    cs:__imp_PathAllocCombine
0x180011c6c  mov     ebx, eax
0x180011c6e  test    eax, eax
0x180011c70  jns     short loc_180011C8D
0x180011c72  mov     edx, 7Ch ; '|'; void *
0x180011c77  mov     rcx, [rsp+28h]; this
0x180011c7c  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180011c83  mov     r9d, eax; char *
0x180011c86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011c8b  jmp     short loc_180011CB4
0x180011c8d  lea     rcx, [rsi+0C0h]
0x180011c94  lea     rdx, [rsp+28h+arg_10]
0x180011c99  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180011c9e  mov     rcx, [rax]
0x180011ca1  mov     byte ptr [rcx+111h], 1
0x180011ca8  lea     rcx, [rsp+28h+arg_10]
0x180011cad  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180011cb2  xor     ebx, ebx
0x180011cb4  lea     rcx, [rsp+28h+ppszPath]
0x180011cb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180011cbe  mov     rsi, [rsp+28h+arg_18]
0x180011cc3  mov     eax, ebx
0x180011cc5  mov     rbx, [rsp+28h+arg_0]
0x180011cca  add     rsp, 20h
0x180011cce  pop     rdi
0x180011ccf  retn
```
