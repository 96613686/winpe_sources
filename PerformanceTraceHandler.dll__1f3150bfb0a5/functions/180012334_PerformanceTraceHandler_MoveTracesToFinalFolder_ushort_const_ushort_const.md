# PerformanceTraceHandler::MoveTracesToFinalFolder(ushort const *,ushort const *)

- ea: `0x180012334`
- end: `0x1800125bd`
- name: `?MoveTracesToFinalFolder@PerformanceTraceHandler@@AEAAJPEBG0@Z`
- size: `649`
- prototype: `__int64 __fastcall(PerformanceTraceHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001124c`

## callees

- `0x180007f3c`
- `0x18000b544`
- `0x18000f2cc`
- `0x180010a6c`
- `0x180010a90`
- `0x180010ca4`
- `0x180012334`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800123b1`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800123b1`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180012364`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180012420`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x1800124b9`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180012364`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x180012420`
- `ext-ms-win-winrt-storage-l1-1-0!CreateStorageItemFromPath_FullTrustCaller` at `0x1800124b9`

## string_xrefs

- `0x180012377`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x1800123c2`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x180012466`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x1800124cc`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`
- `0x18001251d`: `pcshell\shell\performancetracehandler\dll\performancetracehandler.cpp`

## pseudocode

```c
__int64 __fastcall PerformanceTraceHandler::MoveTracesToFinalFolder(
        PerformanceTraceHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT v7; // eax
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  PWSTR ppszPathOut; // [rsp+20h] [rbp-38h] BYREF
  __int64 v19; // [rsp+28h] [rbp-30h] BYREF
  __int64 v20; // [rsp+30h] [rbp-28h] BYREF
  __int64 *v21; // [rsp+38h] [rbp-20h] BYREF
  __int64 v22; // [rsp+40h] [rbp-18h] BYREF
  _BYTE v23[16]; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  _QWORD *v25; // [rsp+98h] [rbp+40h] BYREF

  v22 = 0;
  v5 = CreateStorageItemFromPath_FullTrustCaller(a3, 0x2000, &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b, &v22);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v25 = 0;
    ppszPathOut = 0;
    v7 = PathAllocCombine(a2, L"diagnostics.zip", 1u, &ppszPathOut);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 185;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
        (const char *)(unsigned int)v7,
        (int)ppszPathOut);
LABEL_6:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
      wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v25);
      goto LABEL_26;
    }
    v9 = v25;
    v25 = 0;
    if ( v9 )
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    v7 = CreateStorageItemFromPath_FullTrustCaller(
           ppszPathOut,
           0x2000,
           &GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea,
           &v25);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 186;
      goto LABEL_5;
    }
    v19 = 0;
    v10 = *v25;
    v19 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v10 + 112))(v25, v22, &v19);
    v6 = v11;
    if ( v11 >= 0 )
    {
      v11 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v19);
      v6 = v11;
      if ( v11 >= 0 )
      {
        v21 = 0;
        v13 = CreateStorageItemFromPath_FullTrustCaller(a2, 0x2000, &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30, &v21);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v20 = 0;
          v14 = *v21;
          v20 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v14 + 72))(v21, 1, &v20);
          v6 = v15;
          if ( v15 >= 0 )
          {
            v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(v20);
            v6 = v15;
            if ( v15 >= 0 )
            {
              *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(
                                      (char *)this + 192,
                                      v23)
                       + 280LL) = 1;
              tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(v23);
              wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v20);
              wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v21);
              wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v19);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
              wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v25);
              v6 = 0;
              goto LABEL_26;
            }
            v16 = 198;
          }
          else
          {
            v16 = 197;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
            (const char *)(unsigned int)v15,
            (int)ppszPathOut);
          wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v20);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC3,
            (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
            (const char *)(unsigned int)v13,
            (int)ppszPathOut);
        }
        wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v21);
        goto LABEL_14;
      }
      v12 = 191;
    }
    else
    {
      v12 = 190;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
      (const char *)(unsigned int)v11,
      (int)ppszPathOut);
LABEL_14:
    wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v19);
    goto LABEL_6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\performancetracehandler.cpp",
    (const char *)(unsigned int)v5,
    (int)ppszPathOut);
LABEL_26:
  wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(&v22);
  return v6;
}

```

## disassembly

```asm
0x180012334  push    rbp
0x180012336  push    rbx
0x180012337  push    rsi
0x180012338  push    rdi
0x180012339  mov     rbp, rsp
0x18001233c  sub     rsp, 58h
0x180012340  mov     rax, r8
0x180012343  mov     rdi, rdx
0x180012346  mov     rsi, rcx
0x180012349  mov     [rbp+var_18], 0
0x180012351  lea     r9, [rbp+var_18]
0x180012355  lea     r8, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18001235c  mov     edx, 2000h
0x180012361  mov     rcx, rax
0x180012364  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x18001236a  mov     ebx, eax
0x18001236c  test    eax, eax
0x18001236e  jns     short loc_18001238D
0x180012370  mov     rcx, [rbp+20h]; this
0x180012374  mov     r9d, eax; char *
0x180012377  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001237e  mov     edx, 0B4h; void *
0x180012383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012388  jmp     loc_1800125A9
0x18001238d  mov     [rbp+arg_18], 0
0x180012395  mov     [rbp+ppszPathOut], 0
0x18001239d  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x1800123a1  mov     r8d, 1; dwFlags
0x1800123a7  lea     rdx, aDiagnosticsZip; "diagnostics.zip"
0x1800123ae  mov     rcx, rdi; pszPathIn
0x1800123b1  call    cs:__imp_PathAllocCombine
0x1800123b7  mov     ebx, eax
0x1800123b9  test    eax, eax
0x1800123bb  jns     short loc_1800123EE
0x1800123bd  mov     edx, 0B9h; void *
0x1800123c2  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x1800123c9  mov     r9d, eax; char *
0x1800123cc  mov     rcx, [rbp+20h]; this
0x1800123d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123d5  nop
0x1800123d6  lea     rcx, [rbp+ppszPathOut]
0x1800123da  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800123df  nop
0x1800123e0  lea     rcx, [rbp+arg_18]
0x1800123e4  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800123e9  jmp     loc_1800125A9
0x1800123ee  mov     rcx, [rbp+arg_18]
0x1800123f2  mov     [rbp+arg_18], 0
0x1800123fa  test    rcx, rcx
0x1800123fd  jz      short loc_18001240C
0x1800123ff  mov     rax, [rcx]
0x180012402  mov     rax, [rax+10h]
0x180012406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001240b  nop
0x18001240c  lea     r9, [rbp+arg_18]
0x180012410  lea     r8, _GUID_fa3f6186_4214_428c_a64c_14c9ac7315ea
0x180012417  mov     edx, 2000h
0x18001241c  mov     rcx, [rbp+ppszPathOut]
0x180012420  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x180012426  mov     ebx, eax
0x180012428  test    eax, eax
0x18001242a  jns     short loc_180012433
0x18001242c  mov     edx, 0BAh
0x180012431  jmp     short loc_1800123C2
0x180012433  mov     [rbp+var_30], 0
0x18001243b  mov     rcx, [rbp+arg_18]
0x18001243f  mov     rax, [rcx]
0x180012442  mov     [rbp+var_30], 0
0x18001244a  lea     r8, [rbp+var_30]
0x18001244e  mov     rdx, [rbp+var_18]
0x180012452  mov     rax, [rax+70h]
0x180012456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001245b  mov     ebx, eax
0x18001245d  test    eax, eax
0x18001245f  jns     short loc_180012488
0x180012461  mov     edx, 0BEh; void *
0x180012466  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x18001246d  mov     r9d, eax; char *
0x180012470  mov     rcx, [rbp+20h]; this
0x180012474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012479  nop
0x18001247a  lea     rcx, [rbp+var_30]
0x18001247e  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x180012483  jmp     loc_1800123D6
0x180012488  mov     rcx, [rbp+var_30]
0x18001248c  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012491  mov     ebx, eax
0x180012493  test    eax, eax
0x180012495  jns     short loc_18001249E
0x180012497  mov     edx, 0BFh
0x18001249c  jmp     short loc_180012466
0x18001249e  mov     [rbp+var_20], 0
0x1800124a6  lea     r9, [rbp+var_20]
0x1800124aa  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x1800124b1  mov     edx, 2000h
0x1800124b6  mov     rcx, rdi
0x1800124b9  call    cs:__imp_CreateStorageItemFromPath_FullTrustCaller
0x1800124bf  mov     ebx, eax
0x1800124c1  test    eax, eax
0x1800124c3  jns     short loc_1800124E9
0x1800124c5  mov     rcx, [rbp+20h]; this
0x1800124c9  mov     r9d, eax; char *
0x1800124cc  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x1800124d3  mov     edx, 0C3h; void *
0x1800124d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800124dd  nop
0x1800124de  lea     rcx, [rbp+var_20]
0x1800124e2  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800124e7  jmp     short loc_18001247A
0x1800124e9  mov     [rbp+var_28], 0
0x1800124f1  mov     rcx, [rbp+var_20]
0x1800124f5  mov     rax, [rcx]
0x1800124f8  mov     [rbp+var_28], 0
0x180012500  lea     r8, [rbp+var_28]
0x180012504  mov     edx, 1
0x180012509  mov     rax, [rax+48h]
0x18001250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012512  mov     ebx, eax
0x180012514  test    eax, eax
0x180012516  jns     short loc_18001253C
0x180012518  mov     edx, 0C5h; void *
0x18001251d  lea     r8, aPcshellShellPe_3; "pcshell\\shell\\performancetracehandler"...
0x180012524  mov     r9d, eax; char *
0x180012527  mov     rcx, [rbp+20h]; this
0x18001252b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012530  nop
0x180012531  lea     rcx, [rbp+var_28]
0x180012535  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x18001253a  jmp     short loc_1800124DE
0x18001253c  mov     rcx, [rbp+var_28]
0x180012540  call    ??$WaitForCompletion@PEAUIAsyncAction@Foundation@Windows@@@details@wil@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncAction *>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,ulong,bool *)
0x180012545  mov     ebx, eax
0x180012547  test    eax, eax
0x180012549  jns     short loc_180012552
0x18001254b  mov     edx, 0C6h
0x180012550  jmp     short loc_18001251D
0x180012552  lea     rcx, [rsi+0C0h]
0x180012559  lea     rdx, [rbp+var_10]
0x18001255d  call    ??C?$tip_test@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::operator->(void)
0x180012562  mov     rcx, [rax]
0x180012565  mov     byte ptr [rcx+118h], 1
0x18001256c  lea     rcx, [rbp+var_10]
0x180012570  call    ??1?$test_data_control@V?$merged_data@U_tip_PerformanceTraceHandlerTIP@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>::~test_data_control<tip2::details::merged_data<_tip_PerformanceTraceHandlerTIP,_tip_PerformanceTraceHandlerTIP>>(void)
0x180012575  nop
0x180012576  lea     rcx, [rbp+var_28]
0x18001257a  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x18001257f  nop
0x180012580  lea     rcx, [rbp+var_20]
0x180012584  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x180012589  nop
0x18001258a  lea     rcx, [rbp+var_30]
0x18001258e  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x180012593  nop
0x180012594  lea     rcx, [rbp+ppszPathOut]
0x180012598  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001259d  nop
0x18001259e  lea     rcx, [rbp+arg_18]
0x1800125a2  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800125a7  xor     ebx, ebx
0x1800125a9  lea     rcx, [rbp+var_18]
0x1800125ad  call    ??1?$com_ptr_t@UIStorageItem@Storage@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>::~com_ptr_t<Windows::Storage::IStorageItem,wil::err_returncode_policy>(void)
0x1800125b2  mov     eax, ebx
0x1800125b4  add     rsp, 58h
0x1800125b8  pop     rdi
0x1800125b9  pop     rsi
0x1800125ba  pop     rbx
0x1800125bb  pop     rbp
0x1800125bc  retn
```
