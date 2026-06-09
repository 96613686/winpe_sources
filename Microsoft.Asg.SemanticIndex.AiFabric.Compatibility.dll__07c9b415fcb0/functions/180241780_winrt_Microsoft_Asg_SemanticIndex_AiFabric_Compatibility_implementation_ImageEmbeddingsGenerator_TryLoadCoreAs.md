# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync$_ResumeCoro$1

- ea: `0x180241780`
- end: `0x180242104`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync$_ResumeCoro$1`
- size: `2436`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006df00`
- `0x180241770`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x180003fb0`
- `0x180004050`
- `0x180004510`
- `0x18000d230`
- `0x18000e890`
- `0x18001b3c0`
- `0x180020e60`
- `0x180047520`
- `0x1800475c0`
- `0x18006d100`
- `0x180078d00`
- `0x180078d10`
- `0x1801d1e70`
- `0x1801d2ae0`
- `0x1801d2b20`
- `0x1801d2dc0`
- `0x1801d2e30`
- `0x1801d2e50`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180241780`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18024192b`
- `KERNEL32!CloseHandle` at `0x180241fc1`
- `KERNEL32!CloseHandle` at `0x18024192b`
- `KERNEL32!CloseHandle` at `0x180241fc1`

## string_xrefs

- `0x1802418c4`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18024182e`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x1802419d9`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x180241c8c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x180241d15`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\ImageEmbeddingsGenerator.cpp`
- `0x180241846`: `Cannot load ImageEmbeddingsGenerator models. Object is already closed.`
- `0x1802419f1`: `Cannot load ImageEmbeddingsGenerator models. Object is already closed.`
- `0x180241ca1`: `Cannot load ImageEmbeddingsGenerator models. Object is already closed.`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync__ResumeCoro_1(
        _WORD *a1)
{
  _WORD *v2; // r12
  __int64 v3; // rax
  unsigned int *v4; // rax
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rsi
  __int64 v8; // r15
  unsigned int *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  struct winrt::impl::hstring_header *v12; // rdx
  __int128 *Pipelines; // rax
  unsigned int *v14; // rax
  unsigned int *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rcx
  volatile signed __int32 *v19; // r15
  __int64 v20; // rax
  __int64 v21; // rcx
  volatile signed __int32 *v22; // r15
  bool v23; // al
  volatile signed __int32 *v24; // rsi
  volatile signed __int32 *v25; // rsi
  __int64 v26; // rcx
  void *v27; // rcx
  volatile signed __int32 *v29; // rsi
  int v30; // edi
  HANDLE ProcessHeap; // rax
  int v32; // [rsp+44h] [rbp-1C4h]
  int v33; // [rsp+48h] [rbp-1C0h]
  __int64 v34; // [rsp+60h] [rbp-1A8h]
  __int128 v35; // [rsp+78h] [rbp-190h]
  __int128 v36; // [rsp+78h] [rbp-190h]
  __int128 v37; // [rsp+88h] [rbp-180h]
  __int128 v38; // [rsp+88h] [rbp-180h]
  __int128 v39; // [rsp+98h] [rbp-170h]
  __int128 v40; // [rsp+98h] [rbp-170h]
  __int128 v41; // [rsp+A8h] [rbp-160h]
  _BYTE pExceptionObject[24]; // [rsp+D8h] [rbp-130h] BYREF
  _BYTE v43[24]; // [rsp+F0h] [rbp-118h] BYREF
  _BYTE v44[24]; // [rsp+108h] [rbp-100h] BYREF
  _BYTE v45[24]; // [rsp+120h] [rbp-E8h] BYREF
  _BYTE v46[24]; // [rsp+138h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+150h] [rbp-B8h]
  _OWORD v48[7]; // [rsp+160h] [rbp-A8h] BYREF

  v2 = a1 + 92;
  switch ( a1[92] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_64;
    case 2:
      v3 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 90) = v3;
      *((_QWORD *)a1 + 24) = v3;
      *((_QWORD *)a1 + 25) = v3;
      if ( *(_BYTE *)(v3 + 48) )
      {
        *((_DWORD *)a1 + 108) = 291;
        *((_QWORD *)a1 + 55) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 56) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 228),
          L"Cannot load ImageEmbeddingsGenerator models. Object is already closed.");
        v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 244), -2147483629);
        winrt::hresult_error::hresult_error(pExceptionObject, *v4, a1 + 228, a1 + 216);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      ImpersonationHelper::GetThreadImpersonationToken((void **)a1 + 26);
      *((_BYTE *)a1 + 216) = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 124) = 5672;
        *((_QWORD *)a1 + 63) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 64) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v43,
          (const struct winrt::impl::slim_source_location *)(a1 + 248));
        throw (winrt::hresult_canceled *)v43;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v5, a1);
      return;
    case 4:
      v7 = *((_QWORD *)a1 + 90);
      *((_QWORD *)a1 + 28) = v7 + 56;
      *((_BYTE *)a1 + 232) = 0;
      if ( Mtx_lock((_Mtx_t)(v7 + 56)) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v7 + 132) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v7 + 132) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      *((_BYTE *)a1 + 232) = 1;
      while ( *(_BYTE *)(v7 + 248) )
        Cnd_wait((_Cnd_t)(v7 + 136), (_Mtx_t)(v7 + 56));
      v8 = *((_QWORD *)a1 + 24);
      if ( *(_BYTE *)(v8 + 48) )
      {
        *((_DWORD *)a1 + 130) = 291;
        *((_QWORD *)a1 + 66) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 67) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 272),
          L"Cannot load ImageEmbeddingsGenerator models. Object is already closed.");
        v9 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 288), -2147483629);
        winrt::hresult_error::hresult_error(v44, *v9, a1 + 272, a1 + 260);
        throw (winrt::hresult_error *)v44;
      }
      *(_BYTE *)(v7 + 248) = 1;
      *((_QWORD *)a1 + 30) = v7;
      *((_BYTE *)a1 + 248) = 1;
      v34 = *(_QWORD *)(v7 + 240);
      v39 = *(_OWORD *)(v7 + 252);
      v33 = *(_DWORD *)(v7 + 268);
      v37 = *(_OWORD *)(v7 + 272);
      v32 = *(_DWORD *)(v7 + 288);
      v35 = *(_OWORD *)(v7 + 292);
      *((_QWORD *)a1 + 32) = 0;
      *((_QWORD *)a1 + 33) = 0;
      v10 = *(_QWORD *)(v7 + 216);
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
      *((_QWORD *)a1 + 32) = *(_QWORD *)(v7 + 208);
      *((_QWORD *)a1 + 33) = *(_QWORD *)(v7 + 216);
      *((_QWORD *)a1 + 34) = 0;
      *((_QWORD *)a1 + 35) = 0;
      v11 = *(_QWORD *)(v7 + 232);
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      *((_QWORD *)a1 + 34) = *(_QWORD *)(v7 + 224);
      *((_QWORD *)a1 + 35) = *(_QWORD *)(v7 + 232);
      if ( v7 == -56 )
        std::_Throw_system_error(1);
      Mtx_unlock((_Mtx_t)(v7 + 56));
      *((_BYTE *)a1 + 232) = 0;
      *((_QWORD *)a1 + 41) = a1 + 144;
      *((_BYTE *)a1 + 320) = 0;
      if ( *((_BYTE *)a1 + 176) )
      {
        *((_QWORD *)a1 + 36) = winrt::impl::duplicate_hstring(*((winrt::impl **)a1 + 18), v12);
        *(_OWORD *)(a1 + 148) = *(_OWORD *)(a1 + 76);
        *((_DWORD *)a1 + 78) = *((_DWORD *)a1 + 42);
        *((_BYTE *)a1 + 320) = 1;
      }
      *((_OWORD *)a1 + 26) = v35;
      *((_OWORD *)a1 + 24) = v37;
      *((_DWORD *)a1 + 100) = v32;
      *((_OWORD *)a1 + 22) = v39;
      *((_DWORD *)a1 + 92) = v33;
      Pipelines = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::LoadPipelines(
                    v48,
                    (struct winrt::impl::hstring_header *)(a1 + 128),
                    (_QWORD *)a1 + 34,
                    (__int64)(a1 + 144),
                    (__int128 *)a1 + 22,
                    (__int128 *)a1 + 24,
                    (_OWORD *)a1 + 26,
                    (void **)a1 + 26);
      v40 = *Pipelines;
      v38 = Pipelines[1];
      v36 = Pipelines[2];
      v41 = Pipelines[3];
      if ( Mtx_lock((_Mtx_t)(v7 + 56)) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(v7 + 132) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v7 + 132) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      *((_BYTE *)a1 + 232) = 1;
      if ( *(_BYTE *)(v8 + 48) )
      {
        *((_DWORD *)a1 + 146) = 291;
        *((_QWORD *)a1 + 74) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 75) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 308),
          L"Cannot load ImageEmbeddingsGenerator models. Object is already closed.");
        v14 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 304), -2147483629);
        winrt::hresult_error::hresult_error(v45, *v14, a1 + 308, a1 + 292);
        throw (winrt::hresult_error *)v45;
      }
      if ( *(_QWORD *)(*((_QWORD *)a1 + 25) + 240LL) != v34 )
      {
        *((_DWORD *)a1 + 162) = 299;
        *((_QWORD *)a1 + 82) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\ImageEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 83) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 336),
          L"Cannot load ImageEmbeddingsGenerator. Object has been changed.");
        v15 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 352), -2147483636);
        winrt::hresult_error::hresult_error(v46, *v15, a1 + 336, a1 + 324);
        throw (winrt::hresult_error *)v46;
      }
      v16 = *((_QWORD *)a1 + 17);
      _InterlockedIncrement64((volatile signed __int64 *)(v16 + 240));
      v17 = *((_QWORD *)a1 + 33);
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
      v18 = *((_QWORD *)a1 + 33);
      *(_QWORD *)(v16 + 208) = *((_QWORD *)a1 + 32);
      v19 = *(volatile signed __int32 **)(v16 + 216);
      *(_QWORD *)(v16 + 216) = v18;
      if ( v19 )
      {
        if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
      v20 = *((_QWORD *)a1 + 35);
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      v21 = *((_QWORD *)a1 + 35);
      *(_QWORD *)(v16 + 224) = *((_QWORD *)a1 + 34);
      v22 = *(volatile signed __int32 **)(v16 + 232);
      *(_QWORD *)(v16 + 232) = v21;
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      *(_OWORD *)(v16 + 308) = v40;
      *(_OWORD *)(v16 + 324) = v38;
      *(_OWORD *)(v16 + 340) = v36;
      *(_OWORD *)(v16 + 356) = v41;
      v23 = *(_QWORD *)(v16 + 208) && *(_QWORD *)(v16 + 224);
      *((_BYTE *)a1 + 120) = v23;
      v24 = (volatile signed __int32 *)*((_QWORD *)a1 + 35);
      if ( v24 )
      {
        if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      v25 = (volatile signed __int32 *)*((_QWORD *)a1 + 33);
      if ( v25 )
      {
        if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
      v26 = *((_QWORD *)a1 + 30);
      *(_BYTE *)(v26 + 248) = 0;
      v47 = v26;
      Cnd_signal((_Cnd_t)(v26 + 136));
      Mtx_unlock(*((_Mtx_t *)a1 + 28));
      v27 = (void *)*((_QWORD *)a1 + 26);
      if ( v27 && v27 != (void *)-1LL )
        CloseHandle(v27);
      *((_QWORD *)a1 + 42) = a1 + 8;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 168) )
        goto LABEL_64;
      return;
    case 5:
      v6 = (void *)*((_QWORD *)a1 + 26);
      if ( v6 && v6 != (void *)-1LL )
        CloseHandle(v6);
LABEL_64:
      if ( *((_QWORD *)a1 + 13) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 52);
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 48);
      __ExceptionPtrDestroy(a1 + 36);
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 8);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        goto LABEL_77;
      if ( *((_BYTE *)a1 + 176) )
      {
        v29 = (volatile signed __int32 *)*((_QWORD *)a1 + 18);
        if ( v29 )
        {
          v30 = _InterlockedDecrement(v29 + 6);
          if ( v30 )
          {
            if ( v30 < 0 )
LABEL_77:
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v29);
          }
          *((_QWORD *)a1 + 18) = 0;
        }
      }
      if ( a1[93] )
        operator delete(a1);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180241780  mov     [rsp+arg_8], rbx
0x180241785  mov     [rsp+arg_10], rsi
0x18024178a  mov     [rsp+Block], rcx
0x18024178f  push    rdi
0x180241790  push    r12
0x180241792  push    r13
0x180241794  push    r14
0x180241796  push    r15
0x180241798  sub     rsp, 1E0h
0x18024179f  mov     rax, cs:__security_cookie
0x1802417a6  xor     rax, rsp
0x1802417a9  mov     [rsp+208h+var_30], rax
0x1802417b1  mov     rbx, [rsp+208h+Block]
0x1802417b9  lea     r12, [rbx+0B8h]
0x1802417c0  mov     [rsp+208h+var_198], r12
0x1802417c5  movzx   eax, word ptr [r12]
0x1802417ca  mov     [rsp+208h+var_1C8], ax
0x1802417cf  inc     ax; switch 7 cases
0x1802417d2  cmp     ax, 6
0x1802417d6  ja      def_1802417F1; jumptable 00000001802417F1 default case, case 0
0x1802417dc  movsx   rax, ax
0x1802417e0  lea     rdx, cs:180000000h
0x1802417e7  mov     ecx, ds:(jpt_1802417F1 - 180000000h)[rdx+rax*4]
0x1802417ee  add     rcx, rdx
0x1802417f1  jmp     rcx; switch jump
0x1802417f3  xor     r14d, r14d; jumptable 00000001802417F1 case 3
0x1802417f6  mov     edi, 0FFFFFFFFh
0x1802417fb  jmp     loc_180242018
0x180241800  mov     rax, [rbx+88h]; jumptable 00000001802417F1 case 2
0x180241807  mov     [rbx+2D0h], rax
0x18024180e  mov     [rbx+0C0h], rax
0x180241815  mov     [rbx+0C8h], rax
0x18024181c  movzx   ecx, byte ptr [rax+30h]
0x180241820  test    cl, cl
0x180241822  jz      short loc_18024189B
0x180241824  mov     dword ptr [rbx+1B0h], 123h
0x18024182e  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180241835  mov     [rbx+1B8h], rax
0x18024183c  xor     r14d, r14d
0x18024183f  mov     [rbx+1C0h], r14
0x180241846  lea     rdx, aCannotLoadImag; "Cannot load ImageEmbeddingsGenerator mo"...
0x18024184d  lea     rcx, [rbx+1C8h]; this
0x180241854  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180241859  lea     rcx, [rbx+1E8h]; this
0x180241860  mov     edx, 80000013h; int
0x180241865  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024186a  lea     r9, [rbx+1B0h]
0x180241871  lea     r8, [rbx+1C8h]
0x180241878  mov     edx, [rax]
0x18024187a  lea     rcx, [rsp+208h+pExceptionObject]
0x180241882  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180241887  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024188e  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x180241896  call    _CxxThrowException
0x18024189b  lea     rcx, [rbx+0D0h]
0x1802418a2  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x1802418a7  nop
0x1802418a8  mov     byte ptr [rbx+0D8h], 0
0x1802418af  mov     eax, [rbx+70h]
0x1802418b2  cmp     eax, 2
0x1802418b5  jnz     short loc_1802418FD
0x1802418b7  lea     rdx, [rbx+1F0h]; struct winrt::impl::slim_source_location *
0x1802418be  mov     dword ptr [rdx], 1628h
0x1802418c4  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802418cb  mov     [rbx+1F8h], rax
0x1802418d2  xor     r14d, r14d
0x1802418d5  mov     [rbx+200h], r14
0x1802418dc  lea     rcx, [rsp+208h+var_118]; this
0x1802418e4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802418e9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802418f0  lea     rcx, [rsp+208h+var_118]; pExceptionObject
0x1802418f8  call    _CxxThrowException
0x1802418fd  mov     eax, 4
0x180241902  mov     [r12], ax
0x180241907  mov     rdx, rbx
0x18024190a  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18024190f  jmp     loc_1802420B9
0x180241914  mov     rcx, [rbx+0D0h]; jumptable 00000001802417F1 case 5
0x18024191b  test    rcx, rcx
0x18024191e  jz      short loc_180241932
0x180241920  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180241924  jz      short loc_180241932
0x180241926  mov     [rsp+208h+var_1A0], rcx
0x18024192b  call    cs:__imp_CloseHandle
0x180241931  nop
0x180241932  xor     r14d, r14d
0x180241935  mov     edi, 0FFFFFFFFh
0x18024193a  jmp     loc_180242018
0x18024193f  mov     rsi, [rbx+2D0h]; jumptable 00000001802417F1 case 4
0x180241946  lea     rdi, [rsi+38h]
0x18024194a  mov     [rbx+0E0h], rdi
0x180241951  mov     byte ptr [rbx+0E8h], 0
0x180241958  mov     rcx, rdi; _Mtx_t
0x18024195b  call    _Mtx_lock
0x180241960  test    eax, eax
0x180241962  jz      short loc_18024196E
0x180241964  mov     ecx, 5; int
0x180241969  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18024196e  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180241975  jnz     short loc_180241988
0x180241977  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18024197e  mov     ecx, 6; int
0x180241983  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180241988  mov     byte ptr [rbx+0E8h], 1
0x18024198f  movzx   eax, byte ptr [rsi+0F8h]
0x180241996  test    al, al
0x180241998  jz      short loc_1802419BF
0x18024199a  nop     word ptr [rax+rax+00h]
0x1802419a0  mov     [rsp+208h+var_1B8], rdi
0x1802419a5  mov     rdx, rdi; _Mtx_t
0x1802419a8  lea     rcx, [rsi+88h]; _Cnd_t
0x1802419af  call    _Cnd_wait
0x1802419b4  movzx   eax, byte ptr [rsi+0F8h]
0x1802419bb  test    al, al
0x1802419bd  jnz     short loc_1802419A0
0x1802419bf  mov     r15, [rbx+0C0h]
0x1802419c6  movzx   eax, byte ptr [r15+30h]
0x1802419cb  test    al, al
0x1802419cd  jz      short loc_180241A46
0x1802419cf  mov     dword ptr [rbx+208h], 123h
0x1802419d9  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802419e0  mov     [rbx+210h], rax
0x1802419e7  xor     r14d, r14d
0x1802419ea  mov     [rbx+218h], r14
0x1802419f1  lea     rdx, aCannotLoadImag; "Cannot load ImageEmbeddingsGenerator mo"...
0x1802419f8  lea     rcx, [rbx+220h]; this
0x1802419ff  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180241a04  lea     rcx, [rbx+240h]; this
0x180241a0b  mov     edx, 80000013h; int
0x180241a10  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180241a15  lea     r9, [rbx+208h]
0x180241a1c  lea     r8, [rbx+220h]
0x180241a23  mov     edx, [rax]
0x180241a25  lea     rcx, [rsp+208h+var_100]
0x180241a2d  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180241a32  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180241a39  lea     rcx, [rsp+208h+var_100]; pExceptionObject
0x180241a41  call    _CxxThrowException
0x180241a46  mov     eax, 1
0x180241a4b  xchg    al, [rsi+0F8h]
0x180241a51  mov     [rbx+0F0h], rsi
0x180241a58  mov     byte ptr [rbx+0F8h], 1
0x180241a5f  mov     rax, [rsi+0F0h]
0x180241a66  mov     [rsp+208h+var_1A8], rax
0x180241a6b  movups  xmm0, xmmword ptr [rsi+0FCh]
0x180241a72  movups  [rsp+208h+var_170], xmm0
0x180241a7a  mov     eax, [rsi+10Ch]
0x180241a80  mov     [rsp+208h+var_1C0], eax
0x180241a84  movups  xmm0, xmmword ptr [rsi+110h]
0x180241a8b  movups  [rsp+208h+var_180], xmm0
0x180241a93  mov     eax, [rsi+120h]
0x180241a99  mov     [rsp+208h+var_1C4], eax
0x180241a9d  movups  xmm0, xmmword ptr [rsi+124h]
0x180241aa4  movups  [rsp+208h+var_190], xmm0
0x180241aa9  xor     r14d, r14d
0x180241aac  mov     [rbx+100h], r14
0x180241ab3  mov     [rbx+108h], r14
0x180241aba  mov     rax, [rsi+0D8h]
0x180241ac1  test    rax, rax
0x180241ac4  jz      short loc_180241ACA
0x180241ac6  lock inc dword ptr [rax+8]
0x180241aca  mov     rax, [rsi+0D0h]
0x180241ad1  mov     [rbx+100h], rax
0x180241ad8  mov     rax, [rsi+0D8h]
0x180241adf  mov     [rbx+108h], rax
0x180241ae6  mov     [rbx+110h], r14
0x180241aed  mov     [rbx+118h], r14
0x180241af4  mov     rax, [rsi+0E8h]
0x180241afb  test    rax, rax
0x180241afe  jz      short loc_180241B04
0x180241b00  lock inc dword ptr [rax+8]
0x180241b04  mov     rax, [rsi+0E0h]
0x180241b0b  mov     [rbx+110h], rax
0x180241b12  mov     rax, [rsi+0E8h]
0x180241b19  mov     [rbx+118h], rax
0x180241b20  mov     [rsp+208h+var_1B8], rdi
0x180241b25  test    rdi, rdi
0x180241b28  jz      loc_180241FCA
0x180241b2e  mov     [rsp+208h+var_1B8], rdi
0x180241b33  mov     rcx, rdi; _Mtx_t
0x180241b36  call    _Mtx_unlock
0x180241b3b  mov     byte ptr [rbx+0E8h], 0
0x180241b42  lea     rsi, [rbx+120h]
0x180241b49  mov     [rbx+148h], rsi
0x180241b50  mov     byte ptr [rbx+140h], 0
0x180241b57  cmp     byte ptr [rbx+0B0h], 0
0x180241b5e  jz      short loc_180241B90
0x180241b60  mov     rcx, [rbx+90h]; this
0x180241b67  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180241b6c  mov     [rsi], rax
0x180241b6f  movups  xmm0, xmmword ptr [rbx+98h]
0x180241b76  movups  xmmword ptr [rbx+128h], xmm0
0x180241b7d  mov     eax, [rbx+0A8h]
0x180241b83  mov     [rbx+138h], eax
0x180241b89  mov     byte ptr [rbx+140h], 1
0x180241b90  lea     rdx, [rbx+1A0h]
0x180241b97  movups  xmm0, [rsp+208h+var_190]
0x180241b9c  movaps  xmmword ptr [rdx], xmm0
0x180241b9f  lea     rcx, [rbx+180h]
0x180241ba6  movups  xmm0, [rsp+208h+var_180]
0x180241bae  movaps  xmmword ptr [rcx], xmm0
0x180241bb1  mov     eax, [rsp+208h+var_1C4]
0x180241bb5  mov     [rcx+10h], eax
0x180241bb8  lea     rax, [rbx+160h]
0x180241bbf  movups  xmm0, [rsp+208h+var_170]
0x180241bc7  movaps  xmmword ptr [rax], xmm0
0x180241bca  mov     r8d, [rsp+208h+var_1C0]
0x180241bcf  mov     [rax+10h], r8d
0x180241bd3  lea     r8, [rbx+0D0h]
0x180241bda  mov     [rsp+208h+var_1D0], r8
0x180241bdf  mov     [rsp+208h+var_1D8], rdx
0x180241be4  mov     [rsp+208h+var_1E0], rcx
0x180241be9  mov     [rsp+208h+var_1E8], rax
0x180241bee  mov     r9, rsi
0x180241bf1  lea     r8, [rbx+110h]
0x180241bf8  lea     rdx, [rbx+100h]
0x180241bff  lea     rcx, [rsp+208h+var_A8]
0x180241c07  call    ?LoadPipelines@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@CA?AUGeneratorVectorSpaceInfo@2345678@AEAV?$shared_ptr@VSingleImageEmbeddingPipeline@SemanticPipelines@asg@@@std@@AEAV?$shared_ptr@VDualImageQueryEmbeddingPipeline@SemanticPipelines@asg@@@std@@V?$optional@UVectorSpaceResolutionOptions@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@V?$optional@UGuid@asg@@@std@@3Uguid@8@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::LoadPipelines(std::shared_ptr<asg::SemanticPipelines::SingleImageEmbeddingPipeline> &,std::shared_ptr<asg::SemanticPipelines::DualImageQueryEmbeddingPipeline> &,std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::VectorSpaceResolutionOptions>,std::optional<asg::Guid>,std::optional<asg::Guid>,winrt::guid,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180241c0c  movups  xmm0, xmmword ptr [rax]
0x180241c0f  movups  [rsp+208h+var_170], xmm0
0x180241c17  movups  xmm0, xmmword ptr [rax+10h]
0x180241c1b  movups  [rsp+208h+var_180], xmm0
0x180241c23  movups  xmm0, xmmword ptr [rax+20h]
0x180241c27  movups  [rsp+208h+var_190], xmm0
0x180241c2c  movups  xmm0, xmmword ptr [rax+30h]
0x180241c30  movups  [rsp+208h+var_160], xmm0
0x180241c38  mov     [rsp+208h+var_1B8], rdi
0x180241c3d  mov     rcx, rdi; _Mtx_t
0x180241c40  call    _Mtx_lock
0x180241c45  test    eax, eax
0x180241c47  jz      short loc_180241C53
0x180241c49  mov     ecx, 5; int
0x180241c4e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180241c53  mov     [rsp+208h+var_1B8], rdi
0x180241c58  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180241c5f  jnz     short loc_180241C72
0x180241c61  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180241c68  mov     ecx, 6; int
0x180241c6d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180241c72  mov     byte ptr [rbx+0E8h], 1
0x180241c79  movzx   eax, byte ptr [r15+30h]
0x180241c7e  test    al, al
0x180241c80  jz      short loc_180241CF6
0x180241c82  mov     dword ptr [rbx+248h], 123h
0x180241c8c  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180241c93  mov     [rbx+250h], rax
0x180241c9a  mov     [rbx+258h], r14
0x180241ca1  lea     rdx, aCannotLoadImag; "Cannot load ImageEmbeddingsGenerator mo"...
0x180241ca8  lea     rcx, [rbx+268h]; this
0x180241caf  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180241cb4  lea     rcx, [rbx+260h]; this
0x180241cbb  mov     edx, 80000013h; int
0x180241cc0  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180241cc5  lea     r9, [rbx+248h]
0x180241ccc  lea     r8, [rbx+268h]
0x180241cd3  mov     edx, [rax]
0x180241cd5  lea     rcx, [rsp+208h+var_E8]
0x180241cdd  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180241ce2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180241ce9  lea     rcx, [rsp+208h+var_E8]; pExceptionObject
0x180241cf1  call    _CxxThrowException
0x180241cf6  mov     rax, [rbx+0C8h]
0x180241cfd  mov     rcx, [rax+0F0h]
0x180241d04  cmp     rcx, [rsp+208h+var_1A8]
0x180241d09  jz      short loc_180241D7F
0x180241d0b  mov     dword ptr [rbx+288h], 12Bh
0x180241d15  lea     rax, aCW1SSrcSemanti_10; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180241d1c  mov     [rbx+290h], rax
0x180241d23  mov     [rbx+298h], r14
0x180241d2a  lea     rdx, aCannotLoadImag_0; "Cannot load ImageEmbeddingsGenerator. O"...
0x180241d31  lea     rcx, [rbx+2A0h]; this
0x180241d38  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180241d3d  lea     rcx, [rbx+2C0h]; this
0x180241d44  mov     edx, 8000000Ch; int
0x180241d49  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180241d4e  lea     r9, [rbx+288h]
0x180241d55  lea     r8, [rbx+2A0h]
0x180241d5c  mov     edx, [rax]
0x180241d5e  lea     rcx, [rsp+208h+var_D0]
0x180241d66  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180241d6b  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180241d72  lea     rcx, [rsp+208h+var_D0]; pExceptionObject
0x180241d7a  call    _CxxThrowException
0x180241d7f  mov     rsi, [rbx+88h]
0x180241d86  lock inc qword ptr [rsi+0F0h]
0x180241d8e  mov     rax, [rbx+108h]
0x180241d95  test    rax, rax
0x180241d98  jz      short loc_180241D9E
0x180241d9a  lock inc dword ptr [rax+8]
0x180241d9e  mov     rcx, [rbx+108h]
0x180241da5  mov     rax, [rbx+100h]
0x180241dac  mov     [rsp+208h+var_140], rax
0x180241db4  mov     [rsi+0D0h], rax
0x180241dbb  mov     r15, [rsi+0D8h]
0x180241dc2  mov     [rsi+0D8h], rcx
0x180241dc9  mov     edi, 0FFFFFFFFh
0x180241dce  test    r15, r15
0x180241dd1  jz      short loc_180241E0C
0x180241dd3  mov     eax, edi
0x180241dd5  lock xadd [r15+8], eax
  ... truncated ...
```
