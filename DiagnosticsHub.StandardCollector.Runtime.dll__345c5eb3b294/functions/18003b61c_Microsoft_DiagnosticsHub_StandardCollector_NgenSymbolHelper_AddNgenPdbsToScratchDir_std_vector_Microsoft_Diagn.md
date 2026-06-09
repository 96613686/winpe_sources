# Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::AddNgenPdbsToScratchDir(std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails,std::allocator<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long &,long &)

- ea: `0x18003b61c`
- end: `0x18003ba46`
- name: `?AddNgenPdbsToScratchDir@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@QEAAJAEAV?$vector@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@V?$allocator@UModuleDetails@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@@std@@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAJ2@Z`
- size: `1066`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180038a24`

## callees

- `0x180002604`
- `0x18000288c`
- `0x18003ae24`
- `0x18003b478`
- `0x18003b61c`
- `0x18003c13c`
- `0x18003c9c4`
- `0x18003cdcc`
- `0x18003d864`
- `0x180049b50`
- `0x18004a03c`
- `0x18004b640`

## import_xrefs

- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003b946`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba11`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba1d`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba29`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003b946`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba11`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba1d`
- `MSVCP140!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003ba29`
- `MSVCP140!_Thrd_join` at `0x18003b8ec`
- `MSVCP140!_Thrd_join` at `0x18003b8ec`
- `MSVCP140!_Thrd_id` at `0x18003b8d0`
- `MSVCP140!_Thrd_id` at `0x18003b8d0`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18003b933`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18003ba05`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18003b933`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x18003ba05`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x18003b86c`
- `api-ms-win-crt-runtime-l1-1-0!_beginthreadex` at `0x18003b86c`

## string_xrefs

- `0x18003b6e0`: `Using %d threads to create ngen pdbs`
- `0x18003b709`: `NGEN Pdb caching enabled, using the symbol cache directory %s`
- `0x18003b717`: `NGEN Pdb caching not enabled - unable to get symbol cache path from VS or from the environment variable _NT_SYMCACHE_PATH.`
- `0x18003b9c7`: `Unable to revert impersonation after adding ngen pdbs to scratch dir`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::AddNgenPdbsToScratchDir(
        Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  _QWORD *v8; // rax
  char v9; // r14
  int v10; // esi
  struct ATL::IAtlStringMgr *Instance; // rax
  struct ATL::IAtlStringMgr *v12; // rax
  int DotNetFrameworkInstallPath; // ebx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  _Thrd_t *v22; // rsi
  _Thrd_id_t Id; // ebx
  _QWORD *v24; // rdx
  _QWORD *v25; // rdx
  _BYTE v26[16]; // [rsp+30h] [rbp-69h] BYREF
  _Thrd_t ThrdAddr; // [rsp+40h] [rbp-59h] BYREF
  _QWORD *v28; // [rsp+50h] [rbp-49h] BYREF
  Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *v29; // [rsp+58h] [rbp-41h]
  __int64 v30; // [rsp+60h] [rbp-39h]
  _DWORD *v31; // [rsp+68h] [rbp-31h]
  int v32; // [rsp+70h] [rbp-29h] BYREF
  __int64 v33; // [rsp+78h] [rbp-21h] BYREF
  __int64 v34; // [rsp+80h] [rbp-19h] BYREF
  __int128 v35; // [rsp+88h] [rbp-11h] BYREF
  __int128 v36; // [rsp+98h] [rbp-1h]
  __int64 v37; // [rsp+A8h] [rbp+Fh]

  v30 = a3;
  v29 = a1;
  v31 = a6;
  *a5 = 0;
  *a6 = 0;
  if ( *a2 != a2[1] )
  {
    v35 = 0;
    v36 = 0u;
    v37 = 0;
    _mm_lfence();
    v8 = operator new(0x10u);
    v8[1] = 0;
    *(_QWORD *)&v35 = v8;
    *v8 = &v35;
    anonymous_namespace_::GetRegistryOptions(&v28, v26);
    if ( v26[0] || (v9 = 1, !*(_DWORD *)(*a4 - 16LL)) )
      v9 = 0;
    v10 = (int)v28;
    if ( *(_QWORD *)_logger != *((_QWORD *)_logger + 1) )
    {
      DiagHubCommon::LogStream::Write(
        _logger,
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Using %d threads to create ngen pdbs",
        (unsigned int)v28);
      if ( v9 )
        DiagHubCommon::LogStream::Write(
          _logger,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
          L"NGEN Pdb caching enabled, using the symbol cache directory %s",
          *a4);
      else
        DiagHubCommon::LogStream::Write(
          _logger,
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
          L"NGEN Pdb caching not enabled - unable to get symbol cache path from VS or from the environment variable _NT_SYMCACHE_PATH.");
    }
    v34 = 0;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v34 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    v33 = 0;
    v12 = ATL::CAtlStringMgr::GetInstance();
    if ( v12 )
    {
      v33 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v12 + 24LL))(v12) + 24;
      DotNetFrameworkInstallPath = anonymous_namespace_::FindDotNetFrameworkInstallPath((__int64)&v33, (__int64)&v34);
      if ( DotNetFrameworkInstallPath < 0 )
      {
        _mm_lfence();
        v14 = (_QWORD *)(v33 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v33 - 24 + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 8LL))(*v14);
        }
        v15 = (_QWORD *)(v34 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 - 24 + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 8LL))(*v15);
        }
        std::deque<std::thread>::~deque<std::thread>(&v35);
        return (unsigned int)DotNetFrameworkInstallPath;
      }
      v32 = -1;
      v17 = 0;
      if ( v10 > 0 )
      {
        while ( 1 )
        {
          v18 = operator new(0x50u);
          *v18 = v31;
          v18[1] = a5;
          *((_BYTE *)v18 + 16) = v9;
          v18[3] = a4;
          v18[4] = &v33;
          v18[5] = &v34;
          v18[6] = v30;
          v18[7] = &v32;
          v18[8] = a2;
          v18[9] = v29;
          v28 = v18;
          ThrdAddr._Hnd = (void *)_beginthreadex(
                                    0,
                                    0,
                                    std::thread::_Invoke_std::tuple__lambda_cd7c352e63ccd45e2f936013ee1026a0__std::reference_wrapper_std::vector_Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails_std::allocator_Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails______std::reference_wrapper_long__std::reference_wrapper_ATL::CStringT_unsigned_short_ATL::StrTraitATL_unsigned_short_ATL::ChTraitsCRT_unsigned_short______const___std::reference_wrapper_ATL::CStringT_unsigned_short_ATL::StrTraitATL_unsigned_short_ATL::ChTraitsCRT_unsigned_short________std::reference_wrapper_ATL::CStringT_unsigned_short_ATL::StrTraitATL_unsigned_short_ATL::ChTraitsCRT_unsigned_short________std::reference_wrapper_ATL::CStringT_unsigned_short_ATL::StrTraitATL_unsigned_short_ATL::ChTraitsCRT_unsigned_short______const___bool_std::reference_wrapper_long__std::reference_wrapper_long____0_1_2_3_4_5_6_7_8_9_,
                                    v18,
                                    0,
                                    &ThrdAddr._Id);
          if ( !ThrdAddr._Hnd )
            break;
          std::deque<std::thread>::_Emplace_back_internal<std::thread>(&v35, (__int128 *)&ThrdAddr);
          if ( ThrdAddr._Id )
            terminate();
          v17 = (unsigned int)(v17 + 1);
          if ( (int)v17 >= v10 )
            goto LABEL_21;
        }
        ThrdAddr._Id = 0;
        std::_Throw_Cpp_error(6);
LABEL_31:
        *((_QWORD *)&v36 + 1) = v17;
        goto LABEL_32;
      }
LABEL_21:
      if ( !v37 )
      {
LABEL_32:
        v24 = (_QWORD *)(v33 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v33 - 24 + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
        }
        v25 = (_QWORD *)(v34 - 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v34 - 24 + 16), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
        }
        std::deque<std::thread>::~deque<std::thread>(&v35);
        goto LABEL_37;
      }
      v19 = *((_QWORD *)&v36 + 1);
      v20 = v36;
      v21 = *((_QWORD *)&v35 + 1);
      while ( 1 )
      {
        v22 = *(_Thrd_t **)(v21 + 8 * (v19 & (v20 - 1)));
        if ( !v22->_Id )
          break;
        Id = v22->_Id;
        if ( Id == _Thrd_id() )
        {
          std::_Throw_Cpp_error(5);
          __debugbreak();
        }
        ThrdAddr = *v22;
        v17 = 0;
        if ( _Thrd_join(&ThrdAddr, 0) )
        {
          std::_Throw_Cpp_error(2);
          __debugbreak();
        }
        *v22 = 0;
        v20 = v36;
        v21 = *((_QWORD *)&v35 + 1);
        if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v35 + 1) + 8 * (*((_QWORD *)&v36 + 1) & (v36 - 1))) + 8LL) )
          terminate();
        if ( !--v37 )
          goto LABEL_31;
        v19 = ++*((_QWORD *)&v36 + 1);
      }
      std::_Throw_Cpp_error(1);
    }
    ATL::AtlThrowImpl(-2147467259);
  }
LABEL_37:
  if ( !Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation(v29) )
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
      L"Unable to revert impersonation after adding ngen pdbs to scratch dir");
  return 0;
}

```

## disassembly

```asm
0x18003b61c  mov     [rsp-8+arg_8], rbx
0x18003b621  mov     [rsp-8+arg_10], rsi
0x18003b626  push    rbp
0x18003b627  push    r12
0x18003b629  push    r13
0x18003b62b  push    r14
0x18003b62d  push    r15
0x18003b62f  lea     rbp, [rsp-27h]
0x18003b634  sub     rsp, 0C0h
0x18003b63b  mov     rax, cs:__security_cookie
0x18003b642  xor     rax, rsp
0x18003b645  mov     [rbp+47h+var_30], rax
0x18003b649  mov     r15, r9
0x18003b64c  mov     [rbp+47h+var_80], r8
0x18003b650  mov     r13, rdx
0x18003b653  mov     [rbp+47h+var_88], rcx
0x18003b657  mov     r12, [rbp+47h+arg_20]
0x18003b65b  mov     rax, [rbp+47h+arg_28]
0x18003b65f  mov     [rbp+47h+var_78], rax
0x18003b663  xor     ebx, ebx
0x18003b665  mov     [r12], ebx
0x18003b669  mov     [rax], ebx
0x18003b66b  mov     rax, [rdx+8]
0x18003b66f  cmp     [rdx], rax
0x18003b672  jz      loc_18003B9AC
0x18003b678  xorps   xmm0, xmm0
0x18003b67b  movups  [rbp+47h+var_48], xmm0
0x18003b67f  movdqu  [rbp+47h+var_58], xmm0
0x18003b684  mov     qword ptr [rbp+47h+var_48], rbx
0x18003b688  mov     qword ptr [rbp+47h+var_48+8], rbx
0x18003b68c  mov     [rbp+47h+var_38], rbx
0x18003b690  lfence
0x18003b693  lea     ecx, [rbx+10h]; Size
0x18003b696  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b69b  mov     [rax+8], rbx
0x18003b69f  mov     qword ptr [rbp+47h+var_58], rax
0x18003b6a3  lea     rcx, [rbp+47h+var_58]
0x18003b6a7  mov     [rax], rcx
0x18003b6aa  lea     rdx, [rbp+47h+var_B0]
0x18003b6ae  lea     rcx, [rbp+47h+var_90]
0x18003b6b2  call    _anonymous_namespace___GetRegistryOptions
0x18003b6b7  cmp     [rbp+47h+var_B0], bl
0x18003b6ba  jnz     short loc_18003B6C7
0x18003b6bc  mov     rax, [r15]
0x18003b6bf  cmp     [rax-10h], ebx
0x18003b6c2  mov     r14b, 1
0x18003b6c5  jnz     short loc_18003B6CA
0x18003b6c7  mov     r14b, bl
0x18003b6ca  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18003b6d1  mov     rax, [rcx+8]
0x18003b6d5  mov     esi, dword ptr [rbp+47h+var_90]
0x18003b6d8  cmp     [rcx], rax
0x18003b6db  jz      short loc_18003B723
0x18003b6dd  mov     r9d, esi
0x18003b6e0  lea     r8, aUsingDThreadsT; "Using %d threads to create ngen pdbs"
0x18003b6e7  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b6ee  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b6f3  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b6fa  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18003b701  test    r14b, r14b
0x18003b704  jz      short loc_18003B717
0x18003b706  mov     r9, [r15]
0x18003b709  lea     r8, aNgenPdbCaching_0; "NGEN Pdb caching enabled, using the sym"...
0x18003b710  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b715  jmp     short loc_18003B723
0x18003b717  lea     r8, aNgenPdbCaching_1; "NGEN Pdb caching not enabled - unable t"...
0x18003b71e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b723  mov     [rbp+47h+var_60], rbx
0x18003b727  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18003b72c  mov     rcx, rax
0x18003b72f  test    rax, rax
0x18003b732  jz      loc_18003BA3B
0x18003b738  mov     rax, [rax]
0x18003b73b  mov     rax, [rax+18h]
0x18003b73f  call    cs:__guard_dispatch_icall_fptr
0x18003b745  add     rax, 18h
0x18003b749  mov     [rbp+47h+var_60], rax
0x18003b74d  mov     [rbp+47h+var_68], rbx
0x18003b751  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18003b756  mov     rcx, rax
0x18003b759  test    rax, rax
0x18003b75c  jz      loc_18003BA30
0x18003b762  mov     rax, [rax]
0x18003b765  mov     rax, [rax+18h]
0x18003b769  call    cs:__guard_dispatch_icall_fptr
0x18003b76f  add     rax, 18h
0x18003b773  mov     [rbp+47h+var_68], rax
0x18003b777  lea     rdx, [rbp+47h+var_60]
0x18003b77b  lea     rcx, [rbp+47h+var_68]
0x18003b77f  call    _anonymous_namespace___FindDotNetFrameworkInstallPath
0x18003b784  mov     ebx, eax
0x18003b786  test    eax, eax
0x18003b788  jns     short loc_18003B7EF
0x18003b78a  lfence
0x18003b78d  mov     rdx, [rbp+47h+var_68]
0x18003b791  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003b795  or      ecx, 0FFFFFFFFh
0x18003b798  lock xadd [rdx+10h], ecx
0x18003b79d  sub     ecx, 1
0x18003b7a0  jg      short loc_18003B7B6
0x18003b7a2  lfence
0x18003b7a5  mov     rcx, [rdx]
0x18003b7a8  mov     rax, [rcx]
0x18003b7ab  mov     rax, [rax+8]
0x18003b7af  call    cs:__guard_dispatch_icall_fptr
0x18003b7b5  nop
0x18003b7b6  mov     rdx, [rbp+47h+var_60]
0x18003b7ba  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003b7be  or      eax, 0FFFFFFFFh
0x18003b7c1  lock xadd [rdx+10h], eax
0x18003b7c6  sub     eax, 1
0x18003b7c9  jg      short loc_18003B7DF
0x18003b7cb  lfence
0x18003b7ce  mov     rcx, [rdx]
0x18003b7d1  mov     rax, [rcx]
0x18003b7d4  mov     rax, [rax+8]
0x18003b7d8  call    cs:__guard_dispatch_icall_fptr
0x18003b7de  nop
0x18003b7df  lea     rcx, [rbp+47h+var_58]
0x18003b7e3  call    ??1?$deque@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAA@XZ; std::deque<std::thread>::~deque<std::thread>(void)
0x18003b7e8  mov     eax, ebx
0x18003b7ea  jmp     loc_18003B9DC
0x18003b7ef  mov     [rbp+47h+var_70], 0FFFFFFFFh
0x18003b7f6  xor     ebx, ebx
0x18003b7f8  test    esi, esi
0x18003b7fa  jle     loc_18003B8A1
0x18003b800  mov     ecx, 50h ; 'P'; Size
0x18003b805  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b80a  mov     rcx, [rbp+47h+var_78]
0x18003b80e  mov     [rax], rcx
0x18003b811  mov     [rax+8], r12
0x18003b815  mov     [rax+10h], r14b
0x18003b819  mov     [rax+18h], r15
0x18003b81d  lea     rcx, [rbp+47h+var_68]
0x18003b821  mov     [rax+20h], rcx
0x18003b825  lea     rcx, [rbp+47h+var_60]
0x18003b829  mov     [rax+28h], rcx
0x18003b82d  mov     rcx, [rbp+47h+var_80]
0x18003b831  mov     [rax+30h], rcx
0x18003b835  lea     rcx, [rbp+47h+var_70]
0x18003b839  mov     [rax+38h], rcx
0x18003b83d  mov     [rax+40h], r13
0x18003b841  mov     rcx, [rbp+47h+var_88]
0x18003b845  mov     [rax+48h], rcx
0x18003b849  mov     [rbp+47h+var_90], rax
0x18003b84d  lea     rcx, [rbp+47h+var_A0._Id]
0x18003b851  mov     [rsp+0E0h+ThrdAddr], rcx; ThrdAddr
0x18003b856  mov     [rsp+0E0h+InitFlag], 0; InitFlag
0x18003b85e  mov     r9, rax; ArgList
0x18003b861  lea     r8, std__thread___Invoke_std__tuple__lambda_cd7c352e63ccd45e2f936013ee1026a0__std__reference_wrapper_std__vector_Microsoft__DiagnosticsHub__StandardCollector__NgenSymbolHelper__ModuleDetails_std__allocator_Microsoft__DiagnosticsHub__StandardCollector__NgenSymbolHelper__ModuleDetails______std__reference_wrapper_long__std__reference_wrapper_ATL__CStringT_unsigned_short_ATL__StrTraitATL_unsigned_short_ATL__ChTraitsCRT_unsigned_short______const___std__reference_wrapper_ATL__CStringT_unsigned_short_ATL__StrTraitATL_unsigned_short_ATL__ChTraitsCRT_unsigned_short________std__reference_wrapper_ATL__CStringT_unsigned_short_ATL__StrTraitATL_unsigned_short_ATL__ChTraitsCRT_unsigned_short________std__reference_wrapper_ATL__CStringT_unsigned_short_ATL__StrTraitATL_unsigned_short_ATL__ChTraitsCRT_unsigned_short______const___bool_std__reference_wrapper_long__std__reference_wrapper_long____0_1_2_3_4_5_6_7_8_9_; StartAddress
0x18003b868  xor     edx, edx; StackSize
0x18003b86a  xor     ecx, ecx; Security
0x18003b86c  call    cs:__imp__beginthreadex
0x18003b872  mov     [rbp+47h+var_A0._Hnd], rax
0x18003b876  test    rax, rax
0x18003b879  jz      loc_18003B93A
0x18003b87f  lea     rdx, [rbp+47h+var_A0]
0x18003b883  lea     rcx, [rbp+47h+var_58]
0x18003b887  call    ??$_Emplace_back_internal@Vthread@std@@@?$deque@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@AEAAX$$QEAVthread@1@@Z; std::deque<std::thread>::_Emplace_back_internal<std::thread>(std::thread &&)
0x18003b88c  nop
0x18003b88d  cmp     [rbp+47h+var_A0._Id], 0
0x18003b891  jnz     loc_18003B933
0x18003b897  inc     ebx
0x18003b899  cmp     ebx, esi
0x18003b89b  jl      loc_18003B800
0x18003b8a1  xor     ebx, ebx
0x18003b8a3  cmp     [rbp+47h+var_38], rbx
0x18003b8a7  jz      loc_18003B951
0x18003b8ad  mov     rcx, qword ptr [rbp+47h+var_48+8]
0x18003b8b1  mov     rdx, qword ptr [rbp+47h+var_48]
0x18003b8b5  mov     r8, qword ptr [rbp+47h+var_58+8]
0x18003b8b9  lea     rax, [rdx-1]
0x18003b8bd  and     rax, rcx
0x18003b8c0  mov     rsi, [r8+rax*8]
0x18003b8c4  cmp     [rsi+8], ebx
0x18003b8c7  jz      loc_18003BA24
0x18003b8cd  mov     ebx, [rsi+8]
0x18003b8d0  call    cs:__imp__Thrd_id
0x18003b8d6  cmp     ebx, eax
0x18003b8d8  jz      loc_18003BA18
0x18003b8de  movups  xmm0, xmmword ptr [rsi]
0x18003b8e1  movdqu  xmmword ptr [rbp+47h+var_A0._Hnd], xmm0
0x18003b8e6  xor     edx, edx; int *
0x18003b8e8  lea     rcx, [rbp+47h+var_A0]; _Thrd_t
0x18003b8ec  call    cs:__imp__Thrd_join
0x18003b8f2  xor     ebx, ebx
0x18003b8f4  test    eax, eax
0x18003b8f6  jnz     loc_18003BA0C
0x18003b8fc  xorps   xmm0, xmm0
0x18003b8ff  movdqu  xmmword ptr [rsi], xmm0
0x18003b903  mov     rdx, qword ptr [rbp+47h+var_48]
0x18003b907  lea     rax, [rdx-1]
0x18003b90b  mov     rcx, qword ptr [rbp+47h+var_48+8]
0x18003b90f  and     rax, rcx
0x18003b912  mov     r8, qword ptr [rbp+47h+var_58+8]
0x18003b916  mov     rax, [r8+rax*8]
0x18003b91a  cmp     [rax+8], ebx
0x18003b91d  jnz     loc_18003BA05
0x18003b923  sub     [rbp+47h+var_38], 1
0x18003b928  jz      short loc_18003B94D
0x18003b92a  inc     rcx
0x18003b92d  mov     qword ptr [rbp+47h+var_48+8], rcx
0x18003b931  jmp     short loc_18003B8B9
0x18003b933  call    cs:__imp_terminate
0x18003b93a  mov     [rbp+47h+var_A0._Id], 0
0x18003b941  mov     ecx, 6
0x18003b946  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003b94c  nop
0x18003b94d  mov     qword ptr [rbp+47h+var_48+8], rbx
0x18003b951  mov     rdx, [rbp+47h+var_68]
0x18003b955  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003b959  or      eax, 0FFFFFFFFh
0x18003b95c  lock xadd [rdx+10h], eax
0x18003b961  sub     eax, 1
0x18003b964  jg      short loc_18003B97A
0x18003b966  lfence
0x18003b969  mov     rcx, [rdx]
0x18003b96c  mov     rax, [rcx]
0x18003b96f  mov     rax, [rax+8]
0x18003b973  call    cs:__guard_dispatch_icall_fptr
0x18003b979  nop
0x18003b97a  mov     rdx, [rbp+47h+var_60]
0x18003b97e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18003b982  or      eax, 0FFFFFFFFh
0x18003b985  lock xadd [rdx+10h], eax
0x18003b98a  sub     eax, 1
0x18003b98d  jg      short loc_18003B9A3
0x18003b98f  lfence
0x18003b992  mov     rcx, [rdx]
0x18003b995  mov     rax, [rcx]
0x18003b998  mov     rax, [rax+8]
0x18003b99c  call    cs:__guard_dispatch_icall_fptr
0x18003b9a2  nop
0x18003b9a3  lea     rcx, [rbp+47h+var_58]
0x18003b9a7  call    ??1?$deque@Vthread@std@@V?$allocator@Vthread@std@@@2@@std@@QEAA@XZ; std::deque<std::thread>::~deque<std::thread>(void)
0x18003b9ac  mov     rcx, [rbp+47h+var_88]; this
0x18003b9b0  call    ?RevertImpersonation@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation(void)
0x18003b9b5  test    al, al
0x18003b9b7  jnz     short loc_18003B9DA
0x18003b9b9  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003b9c0  add     rcx, 0A8h; this
0x18003b9c7  lea     r8, aUnableToRevert_0; "Unable to revert impersonation after ad"...
0x18003b9ce  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003b9d5  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003b9da  xor     eax, eax
0x18003b9dc  mov     rcx, [rbp+47h+var_30]
0x18003b9e0  xor     rcx, rsp; StackCookie
0x18003b9e3  call    __security_check_cookie
0x18003b9e8  lea     r11, [rsp+0E0h+var_20]
0x18003b9f0  mov     rbx, [r11+38h]
0x18003b9f4  mov     rsi, [r11+40h]
0x18003b9f8  mov     rsp, r11
0x18003b9fb  pop     r15
0x18003b9fd  pop     r14
0x18003b9ff  pop     r13
0x18003ba01  pop     r12
0x18003ba03  pop     rbp
0x18003ba04  retn
0x18003ba05  call    cs:__imp_terminate
0x18003ba0c  mov     ecx, 2
0x18003ba11  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003ba17  int     3; Trap to Debugger
0x18003ba18  mov     ecx, 5
0x18003ba1d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003ba23  int     3; Trap to Debugger
0x18003ba24  mov     ecx, 1
0x18003ba29  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003ba2f  nop
0x18003ba30  mov     ecx, 80004005h; int
0x18003ba35  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003ba3b  mov     ecx, 80004005h; int
0x18003ba40  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
