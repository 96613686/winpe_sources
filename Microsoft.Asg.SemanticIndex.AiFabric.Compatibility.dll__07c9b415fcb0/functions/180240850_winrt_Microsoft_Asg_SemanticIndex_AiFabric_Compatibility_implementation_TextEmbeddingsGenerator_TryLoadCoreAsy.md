# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync$_ResumeCoro$1

- ea: `0x180240850`
- end: `0x1802411d4`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync$_ResumeCoro$1`
- size: `2436`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180062570`
- `0x180240840`

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
- `0x1800617d0`
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
- `0x180240850`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1802409fb`
- `KERNEL32!CloseHandle` at `0x180241091`
- `KERNEL32!CloseHandle` at `0x1802409fb`
- `KERNEL32!CloseHandle` at `0x180241091`

## string_xrefs

- `0x180240994`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802408fe`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x180240aa9`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x180240d5c`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x180240de5`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextEmbeddingsGenerator.cpp`
- `0x180240916`: `Cannot load TextEmbeddingsGenerator. Object is already closed.`
- `0x180240ac1`: `Cannot load TextEmbeddingsGenerator. Object is already closed.`
- `0x180240d71`: `Cannot load TextEmbeddingsGenerator. Object is already closed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync__ResumeCoro_1(
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
  __m256i *Pipelines; // rax
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
  __m256i v48[3]; // [rsp+160h] [rbp-A8h] BYREF

  v2 = a1 + 92;
  switch ( a1[92] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_63;
    case 2:
      v3 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 90) = v3;
      *((_QWORD *)a1 + 24) = v3;
      *((_QWORD *)a1 + 25) = v3;
      if ( *(_BYTE *)(v3 + 48) )
      {
        *((_DWORD *)a1 + 108) = 426;
        *((_QWORD *)a1 + 55) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 56) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 228),
          L"Cannot load TextEmbeddingsGenerator. Object is already closed.");
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
        *((_DWORD *)a1 + 130) = 426;
        *((_QWORD *)a1 + 66) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 67) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 272),
          L"Cannot load TextEmbeddingsGenerator. Object is already closed.");
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
      Pipelines = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::LoadPipelines(
                    v48,
                    (struct winrt::impl::hstring_header *)(a1 + 128),
                    (_QWORD *)a1 + 34,
                    (__int64)(a1 + 144),
                    (__int128 *)a1 + 22,
                    (__int128 *)a1 + 24,
                    (_OWORD *)a1 + 26,
                    (void **)a1 + 26);
      v40 = *(_OWORD *)Pipelines->m256i_i8;
      v38 = *(_OWORD *)&Pipelines->m256i_u64[2];
      v36 = *(_OWORD *)Pipelines[1].m256i_i8;
      v41 = *(_OWORD *)&Pipelines[1].m256i_u64[2];
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
        *((_DWORD *)a1 + 146) = 426;
        *((_QWORD *)a1 + 74) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 75) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 308),
          L"Cannot load TextEmbeddingsGenerator. Object is already closed.");
        v14 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 304), -2147483629);
        winrt::hresult_error::hresult_error(v45, *v14, a1 + 308, a1 + 292);
        throw (winrt::hresult_error *)v45;
      }
      if ( *(_QWORD *)(*((_QWORD *)a1 + 25) + 240LL) != v34 )
      {
        *((_DWORD *)a1 + 162) = 434;
        *((_QWORD *)a1 + 82) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextEmbeddingsGenerator.cpp";
        *((_QWORD *)a1 + 83) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 336),
          L"Cannot load TextEmbeddingsGenerator models. Object has been changed.");
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
        goto LABEL_63;
      return;
    case 5:
      v6 = (void *)*((_QWORD *)a1 + 26);
      if ( v6 && v6 != (void *)-1LL )
        CloseHandle(v6);
LABEL_63:
      if ( *((_QWORD *)a1 + 13) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 52);
      if ( *((_QWORD *)a1 + 12) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 48);
      __ExceptionPtrDestroy(a1 + 36);
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 8);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        goto LABEL_76;
      if ( *((_BYTE *)a1 + 176) )
      {
        v29 = (volatile signed __int32 *)*((_QWORD *)a1 + 18);
        if ( v29 )
        {
          v30 = _InterlockedDecrement(v29 + 6);
          if ( v30 )
          {
            if ( v30 < 0 )
LABEL_76:
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
0x180240850  mov     [rsp+arg_8], rbx
0x180240855  mov     [rsp+arg_10], rsi
0x18024085a  mov     [rsp+Block], rcx
0x18024085f  push    rdi
0x180240860  push    r12
0x180240862  push    r13
0x180240864  push    r14
0x180240866  push    r15
0x180240868  sub     rsp, 1E0h
0x18024086f  mov     rax, cs:__security_cookie
0x180240876  xor     rax, rsp
0x180240879  mov     [rsp+208h+var_30], rax
0x180240881  mov     rbx, [rsp+208h+Block]
0x180240889  lea     r12, [rbx+0B8h]
0x180240890  mov     [rsp+208h+var_198], r12
0x180240895  movzx   eax, word ptr [r12]
0x18024089a  mov     [rsp+208h+var_1C8], ax
0x18024089f  inc     ax; switch 7 cases
0x1802408a2  cmp     ax, 6
0x1802408a6  ja      def_1802408C1; jumptable 00000001802408C1 default case, case 0
0x1802408ac  movsx   rax, ax
0x1802408b0  lea     rdx, cs:180000000h
0x1802408b7  mov     ecx, ds:(jpt_1802408C1 - 180000000h)[rdx+rax*4]
0x1802408be  add     rcx, rdx
0x1802408c1  jmp     rcx; switch jump
0x1802408c3  xor     r14d, r14d; jumptable 00000001802408C1 case 3
0x1802408c6  mov     edi, 0FFFFFFFFh
0x1802408cb  jmp     loc_1802410E8
0x1802408d0  mov     rax, [rbx+88h]; jumptable 00000001802408C1 case 2
0x1802408d7  mov     [rbx+2D0h], rax
0x1802408de  mov     [rbx+0C0h], rax
0x1802408e5  mov     [rbx+0C8h], rax
0x1802408ec  movzx   ecx, byte ptr [rax+30h]
0x1802408f0  test    cl, cl
0x1802408f2  jz      short loc_18024096B
0x1802408f4  mov     dword ptr [rbx+1B0h], 1AAh
0x1802408fe  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180240905  mov     [rbx+1B8h], rax
0x18024090c  xor     r14d, r14d
0x18024090f  mov     [rbx+1C0h], r14
0x180240916  lea     rdx, aCannotLoadText_0; "Cannot load TextEmbeddingsGenerator. Ob"...
0x18024091d  lea     rcx, [rbx+1C8h]; this
0x180240924  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180240929  lea     rcx, [rbx+1E8h]; this
0x180240930  mov     edx, 80000013h; int
0x180240935  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18024093a  lea     r9, [rbx+1B0h]
0x180240941  lea     r8, [rbx+1C8h]
0x180240948  mov     edx, [rax]
0x18024094a  lea     rcx, [rsp+208h+pExceptionObject]
0x180240952  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180240957  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18024095e  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x180240966  call    _CxxThrowException
0x18024096b  lea     rcx, [rbx+0D0h]
0x180240972  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180240977  nop
0x180240978  mov     byte ptr [rbx+0D8h], 0
0x18024097f  mov     eax, [rbx+70h]
0x180240982  cmp     eax, 2
0x180240985  jnz     short loc_1802409CD
0x180240987  lea     rdx, [rbx+1F0h]; struct winrt::impl::slim_source_location *
0x18024098e  mov     dword ptr [rdx], 1628h
0x180240994  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18024099b  mov     [rbx+1F8h], rax
0x1802409a2  xor     r14d, r14d
0x1802409a5  mov     [rbx+200h], r14
0x1802409ac  lea     rcx, [rsp+208h+var_118]; this
0x1802409b4  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802409b9  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802409c0  lea     rcx, [rsp+208h+var_118]; pExceptionObject
0x1802409c8  call    _CxxThrowException
0x1802409cd  mov     eax, 4
0x1802409d2  mov     [r12], ax
0x1802409d7  mov     rdx, rbx
0x1802409da  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x1802409df  jmp     loc_180241189
0x1802409e4  mov     rcx, [rbx+0D0h]; jumptable 00000001802408C1 case 5
0x1802409eb  test    rcx, rcx
0x1802409ee  jz      short loc_180240A02
0x1802409f0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802409f4  jz      short loc_180240A02
0x1802409f6  mov     [rsp+208h+var_1A0], rcx
0x1802409fb  call    cs:__imp_CloseHandle
0x180240a01  nop
0x180240a02  xor     r14d, r14d
0x180240a05  mov     edi, 0FFFFFFFFh
0x180240a0a  jmp     loc_1802410E8
0x180240a0f  mov     rsi, [rbx+2D0h]; jumptable 00000001802408C1 case 4
0x180240a16  lea     rdi, [rsi+38h]
0x180240a1a  mov     [rbx+0E0h], rdi
0x180240a21  mov     byte ptr [rbx+0E8h], 0
0x180240a28  mov     rcx, rdi; _Mtx_t
0x180240a2b  call    _Mtx_lock
0x180240a30  test    eax, eax
0x180240a32  jz      short loc_180240A3E
0x180240a34  mov     ecx, 5; int
0x180240a39  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180240a3e  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180240a45  jnz     short loc_180240A58
0x180240a47  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180240a4e  mov     ecx, 6; int
0x180240a53  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180240a58  mov     byte ptr [rbx+0E8h], 1
0x180240a5f  movzx   eax, byte ptr [rsi+0F8h]
0x180240a66  test    al, al
0x180240a68  jz      short loc_180240A8F
0x180240a6a  nop     word ptr [rax+rax+00h]
0x180240a70  mov     [rsp+208h+var_1B8], rdi
0x180240a75  mov     rdx, rdi; _Mtx_t
0x180240a78  lea     rcx, [rsi+88h]; _Cnd_t
0x180240a7f  call    _Cnd_wait
0x180240a84  movzx   eax, byte ptr [rsi+0F8h]
0x180240a8b  test    al, al
0x180240a8d  jnz     short loc_180240A70
0x180240a8f  mov     r15, [rbx+0C0h]
0x180240a96  movzx   eax, byte ptr [r15+30h]
0x180240a9b  test    al, al
0x180240a9d  jz      short loc_180240B16
0x180240a9f  mov     dword ptr [rbx+208h], 1AAh
0x180240aa9  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180240ab0  mov     [rbx+210h], rax
0x180240ab7  xor     r14d, r14d
0x180240aba  mov     [rbx+218h], r14
0x180240ac1  lea     rdx, aCannotLoadText_0; "Cannot load TextEmbeddingsGenerator. Ob"...
0x180240ac8  lea     rcx, [rbx+220h]; this
0x180240acf  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180240ad4  lea     rcx, [rbx+240h]; this
0x180240adb  mov     edx, 80000013h; int
0x180240ae0  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180240ae5  lea     r9, [rbx+208h]
0x180240aec  lea     r8, [rbx+220h]
0x180240af3  mov     edx, [rax]
0x180240af5  lea     rcx, [rsp+208h+var_100]
0x180240afd  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180240b02  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180240b09  lea     rcx, [rsp+208h+var_100]; pExceptionObject
0x180240b11  call    _CxxThrowException
0x180240b16  mov     eax, 1
0x180240b1b  xchg    al, [rsi+0F8h]
0x180240b21  mov     [rbx+0F0h], rsi
0x180240b28  mov     byte ptr [rbx+0F8h], 1
0x180240b2f  mov     rax, [rsi+0F0h]
0x180240b36  mov     [rsp+208h+var_1A8], rax
0x180240b3b  movups  xmm0, xmmword ptr [rsi+0FCh]
0x180240b42  movups  [rsp+208h+var_170], xmm0
0x180240b4a  mov     eax, [rsi+10Ch]
0x180240b50  mov     [rsp+208h+var_1C0], eax
0x180240b54  movups  xmm0, xmmword ptr [rsi+110h]
0x180240b5b  movups  [rsp+208h+var_180], xmm0
0x180240b63  mov     eax, [rsi+120h]
0x180240b69  mov     [rsp+208h+var_1C4], eax
0x180240b6d  movups  xmm0, xmmword ptr [rsi+124h]
0x180240b74  movups  [rsp+208h+var_190], xmm0
0x180240b79  xor     r14d, r14d
0x180240b7c  mov     [rbx+100h], r14
0x180240b83  mov     [rbx+108h], r14
0x180240b8a  mov     rax, [rsi+0D8h]
0x180240b91  test    rax, rax
0x180240b94  jz      short loc_180240B9A
0x180240b96  lock inc dword ptr [rax+8]
0x180240b9a  mov     rax, [rsi+0D0h]
0x180240ba1  mov     [rbx+100h], rax
0x180240ba8  mov     rax, [rsi+0D8h]
0x180240baf  mov     [rbx+108h], rax
0x180240bb6  mov     [rbx+110h], r14
0x180240bbd  mov     [rbx+118h], r14
0x180240bc4  mov     rax, [rsi+0E8h]
0x180240bcb  test    rax, rax
0x180240bce  jz      short loc_180240BD4
0x180240bd0  lock inc dword ptr [rax+8]
0x180240bd4  mov     rax, [rsi+0E0h]
0x180240bdb  mov     [rbx+110h], rax
0x180240be2  mov     rax, [rsi+0E8h]
0x180240be9  mov     [rbx+118h], rax
0x180240bf0  mov     [rsp+208h+var_1B8], rdi
0x180240bf5  test    rdi, rdi
0x180240bf8  jz      loc_18024109A
0x180240bfe  mov     [rsp+208h+var_1B8], rdi
0x180240c03  mov     rcx, rdi; _Mtx_t
0x180240c06  call    _Mtx_unlock
0x180240c0b  mov     byte ptr [rbx+0E8h], 0
0x180240c12  lea     rsi, [rbx+120h]
0x180240c19  mov     [rbx+148h], rsi
0x180240c20  mov     byte ptr [rbx+140h], 0
0x180240c27  cmp     byte ptr [rbx+0B0h], 0
0x180240c2e  jz      short loc_180240C60
0x180240c30  mov     rcx, [rbx+90h]; this
0x180240c37  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180240c3c  mov     [rsi], rax
0x180240c3f  movups  xmm0, xmmword ptr [rbx+98h]
0x180240c46  movups  xmmword ptr [rbx+128h], xmm0
0x180240c4d  mov     eax, [rbx+0A8h]
0x180240c53  mov     [rbx+138h], eax
0x180240c59  mov     byte ptr [rbx+140h], 1
0x180240c60  lea     rdx, [rbx+1A0h]
0x180240c67  movups  xmm0, [rsp+208h+var_190]
0x180240c6c  movaps  xmmword ptr [rdx], xmm0
0x180240c6f  lea     rcx, [rbx+180h]
0x180240c76  movups  xmm0, [rsp+208h+var_180]
0x180240c7e  movaps  xmmword ptr [rcx], xmm0
0x180240c81  mov     eax, [rsp+208h+var_1C4]
0x180240c85  mov     [rcx+10h], eax
0x180240c88  lea     rax, [rbx+160h]
0x180240c8f  movups  xmm0, [rsp+208h+var_170]
0x180240c97  movaps  xmmword ptr [rax], xmm0
0x180240c9a  mov     r8d, [rsp+208h+var_1C0]
0x180240c9f  mov     [rax+10h], r8d
0x180240ca3  lea     r8, [rbx+0D0h]
0x180240caa  mov     [rsp+208h+var_1D0], r8
0x180240caf  mov     [rsp+208h+var_1D8], rdx
0x180240cb4  mov     [rsp+208h+var_1E0], rcx
0x180240cb9  mov     [rsp+208h+var_1E8], rax
0x180240cbe  mov     r9, rsi
0x180240cc1  lea     r8, [rbx+110h]
0x180240cc8  lea     rdx, [rbx+100h]
0x180240ccf  lea     rcx, [rsp+208h+var_A8]
0x180240cd7  call    ?LoadPipelines@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@CA?AUGeneratorVectorSpaceInfo@2345678@AEAV?$shared_ptr@VSingleTextEmbeddingPipeline@SemanticPipelines@asg@@@std@@AEAV?$shared_ptr@VDualTextQueryEmbeddingPipeline@SemanticPipelines@asg@@@std@@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@V?$optional@UGuid@asg@@@std@@3Uguid@8@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::LoadPipelines(std::shared_ptr<asg::SemanticPipelines::SingleTextEmbeddingPipeline> &,std::shared_ptr<asg::SemanticPipelines::DualTextQueryEmbeddingPipeline> &,std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>,std::optional<asg::Guid>,std::optional<asg::Guid>,winrt::guid,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180240cdc  movups  xmm0, xmmword ptr [rax]
0x180240cdf  movups  [rsp+208h+var_170], xmm0
0x180240ce7  movups  xmm0, xmmword ptr [rax+10h]
0x180240ceb  movups  [rsp+208h+var_180], xmm0
0x180240cf3  movups  xmm0, xmmword ptr [rax+20h]
0x180240cf7  movups  [rsp+208h+var_190], xmm0
0x180240cfc  movups  xmm0, xmmword ptr [rax+30h]
0x180240d00  movups  [rsp+208h+var_160], xmm0
0x180240d08  mov     [rsp+208h+var_1B8], rdi
0x180240d0d  mov     rcx, rdi; _Mtx_t
0x180240d10  call    _Mtx_lock
0x180240d15  test    eax, eax
0x180240d17  jz      short loc_180240D23
0x180240d19  mov     ecx, 5; int
0x180240d1e  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180240d23  mov     [rsp+208h+var_1B8], rdi
0x180240d28  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180240d2f  jnz     short loc_180240D42
0x180240d31  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180240d38  mov     ecx, 6; int
0x180240d3d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180240d42  mov     byte ptr [rbx+0E8h], 1
0x180240d49  movzx   eax, byte ptr [r15+30h]
0x180240d4e  test    al, al
0x180240d50  jz      short loc_180240DC6
0x180240d52  mov     dword ptr [rbx+248h], 1AAh
0x180240d5c  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180240d63  mov     [rbx+250h], rax
0x180240d6a  mov     [rbx+258h], r14
0x180240d71  lea     rdx, aCannotLoadText_0; "Cannot load TextEmbeddingsGenerator. Ob"...
0x180240d78  lea     rcx, [rbx+268h]; this
0x180240d7f  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180240d84  lea     rcx, [rbx+260h]; this
0x180240d8b  mov     edx, 80000013h; int
0x180240d90  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180240d95  lea     r9, [rbx+248h]
0x180240d9c  lea     r8, [rbx+268h]
0x180240da3  mov     edx, [rax]
0x180240da5  lea     rcx, [rsp+208h+var_E8]
0x180240dad  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180240db2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180240db9  lea     rcx, [rsp+208h+var_E8]; pExceptionObject
0x180240dc1  call    _CxxThrowException
0x180240dc6  mov     rax, [rbx+0C8h]
0x180240dcd  mov     rcx, [rax+0F0h]
0x180240dd4  cmp     rcx, [rsp+208h+var_1A8]
0x180240dd9  jz      short loc_180240E4F
0x180240ddb  mov     dword ptr [rbx+288h], 1B2h
0x180240de5  lea     rax, aCW1SSrcSemanti_1; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180240dec  mov     [rbx+290h], rax
0x180240df3  mov     [rbx+298h], r14
0x180240dfa  lea     rdx, aCannotLoadText; "Cannot load TextEmbeddingsGenerator mod"...
0x180240e01  lea     rcx, [rbx+2A0h]; this
0x180240e08  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180240e0d  lea     rcx, [rbx+2C0h]; this
0x180240e14  mov     edx, 8000000Ch; int
0x180240e19  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180240e1e  lea     r9, [rbx+288h]
0x180240e25  lea     r8, [rbx+2A0h]
0x180240e2c  mov     edx, [rax]
0x180240e2e  lea     rcx, [rsp+208h+var_D0]
0x180240e36  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180240e3b  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180240e42  lea     rcx, [rsp+208h+var_D0]; pExceptionObject
0x180240e4a  call    _CxxThrowException
0x180240e4f  mov     rsi, [rbx+88h]
0x180240e56  lock inc qword ptr [rsi+0F0h]
0x180240e5e  mov     rax, [rbx+108h]
0x180240e65  test    rax, rax
0x180240e68  jz      short loc_180240E6E
0x180240e6a  lock inc dword ptr [rax+8]
0x180240e6e  mov     rcx, [rbx+108h]
0x180240e75  mov     rax, [rbx+100h]
0x180240e7c  mov     [rsp+208h+var_140], rax
0x180240e84  mov     [rsi+0D0h], rax
0x180240e8b  mov     r15, [rsi+0D8h]
0x180240e92  mov     [rsi+0D8h], rcx
0x180240e99  mov     edi, 0FFFFFFFFh
0x180240e9e  test    r15, r15
0x180240ea1  jz      short loc_180240EDC
0x180240ea3  mov     eax, edi
0x180240ea5  lock xadd [r15+8], eax
  ... truncated ...
```
