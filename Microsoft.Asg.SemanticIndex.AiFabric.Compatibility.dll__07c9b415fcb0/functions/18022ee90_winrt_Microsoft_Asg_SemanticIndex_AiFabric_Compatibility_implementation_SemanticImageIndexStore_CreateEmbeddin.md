# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorAsync$_ResumeCoro$1

- ea: `0x18022ee90`
- end: `0x18022f4bc`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorAsync$_ResumeCoro$1`
- size: `1580`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001c660`
- `0x18022ee80`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180003fb0`
- `0x180004510`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bb20`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18006cfd0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022ee90`
- `0x180242120`
- `0x180242ca0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18022ef76`
- `KERNEL32!CloseHandle` at `0x18022f0ed`
- `KERNEL32!CloseHandle` at `0x18022f10b`
- `KERNEL32!CloseHandle` at `0x18022f292`
- `KERNEL32!CloseHandle` at `0x18022f40e`
- `KERNEL32!CloseHandle` at `0x18022ef76`
- `KERNEL32!CloseHandle` at `0x18022f0ed`
- `KERNEL32!CloseHandle` at `0x18022f10b`
- `KERNEL32!CloseHandle` at `0x18022f292`
- `KERNEL32!CloseHandle` at `0x18022f40e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18022f0d5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18022f0d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18022f097`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18022f097`

## string_xrefs

- `0x18022ef13`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022f127`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022f1a1`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`
- `0x18022f349`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorAsync__ResumeCoro_1(
        __int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  _QWORD *v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  void *v8; // rdi
  __int64 v9; // rdi
  void *v10; // r14
  unsigned int v11; // r8d
  const char *v12; // r9
  wil::details::in1diag3 *v13; // rcx
  void *v14; // rcx
  volatile __int64 *v15; // rdi
  void *v16; // rcx
  char v17; // r14
  volatile __int64 *v18; // rdi
  unsigned int *v19; // rax
  _QWORD *v20; // r14
  void *v21; // rcx
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-110h] BYREF
  _BYTE v23[24]; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE v24[24]; // [rsp+68h] [rbp-E0h] BYREF
  _BYTE v25[24]; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+98h] [rbp-B0h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 152) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_69;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 160);
      *(_BYTE *)(a1 + 168) = 0;
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 384) = 5672;
        *(_QWORD *)(a1 + 392) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 400) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 384));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_WORD *)(a1 + 152) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      *(_OWORD *)(a1 + 368) = *(_OWORD *)(a1 + 132);
      if ( memcmp(
             (const void *)(a1 + 368),
             &winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId,
             0x10u) )
      {
        *(_DWORD *)(a1 + 296) = 177;
        *(_QWORD *)(a1 + 304) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
        *(_QWORD *)(a1 + 312) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 320),
          L"Model id is not currently supported by SemanticImageIndexStore");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v24,
          (const struct winrt::param::hstring *)(a1 + 320),
          (const struct winrt::impl::slim_source_location *)(a1 + 296));
        throw (winrt::hresult_invalid_argument *)v24;
      }
      v4 = operator new(0x1B8u);
      *(_QWORD *)(a1 + 416) = v4;
      *(_OWORD *)(a1 + 432) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::ImageEmbeddingsGenerator(v4);
      *v4 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator>::`vftable';
      v5 = v4 + 2;
      if ( !v4 )
        v5 = 0;
      *(_QWORD *)(a1 + 408) = v5;
      v6 = (_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 176) = v5;
      if ( !*(_BYTE *)(a1 + 148) )
        goto LABEL_57;
      v7 = *(_QWORD *)(a1 + 408);
      *(_QWORD *)(a1 + 184) = v7;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      v8 = *(void **)(a1 + 160);
      if ( v8 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 456);
        v10 = *(void **)(a1 + 456);
        *(_QWORD *)(a1 + 456) = 0;
        *(_QWORD *)(a1 + 448) = v10;
        if ( !ImpersonateLoggedOnUser(v8) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v11, v12);
        v9 = a1 + 192;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorAsync_::_8_::_lambda_1_::operator()(
          a1 + 184,
          a1 + 192);
        if ( v10 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v10) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
          if ( v10 )
            CloseHandle(v10);
        }
        v14 = *(void **)(a1 + 456);
        if ( v14 && v14 != (void *)-1LL )
          CloseHandle(v14);
      }
      else
      {
        v9 = a1 + 192;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateEmbeddingsGeneratorAsync_::_8_::_lambda_1_::operator()(
          a1 + 184,
          a1 + 192);
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 464) = 5672;
        *(_QWORD *)(a1 + 472) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 480) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v23,
          (const struct winrt::impl::slim_source_location *)(a1 + 464));
        throw (winrt::hresult_canceled *)v23;
      }
      *(_QWORD *)(a1 + 200) = 0;
      *(_QWORD *)(a1 + 208) = v9;
      *(_QWORD *)(a1 + 216) = 0;
      *(_BYTE *)(a1 + 224) = 1;
      *(_WORD *)(a1 + 152) = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                               (_QWORD *)(a1 + 200),
                               a1) )
      {
LABEL_47:
        v17 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 200);
        v18 = *(volatile __int64 **)(a1 + 200);
        if ( v18 )
        {
          v26 = *(_QWORD *)(a1 + 200);
          while ( _InterlockedExchange64(v18, 0) == 1 )
            Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 192) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
        if ( *(_QWORD *)(a1 + 184) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 184);
        if ( !v17 )
        {
          *(_DWORD *)(a1 + 232) = 168;
          *(_QWORD *)(a1 + 240) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticIm"
                                  "ageIndexStore.cpp";
          *(_QWORD *)(a1 + 248) = 0;
          winrt::param::hstring::hstring(
            (winrt::param::hstring *)(a1 + 256),
            L"Failed to load image embedding model - migration of underlying index may be required");
          v19 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 288), -2081706723);
          winrt::hresult_error::hresult_error(v25, *v19, a1 + 256, a1 + 232);
          throw (winrt::hresult_error *)v25;
        }
        v6 = (_QWORD *)(a1 + 176);
LABEL_57:
        v20 = (_QWORD *)(a1 + 120);
        if ( (_QWORD *)(a1 + 120) != v6 )
        {
          if ( *v20 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
          *v6 = 0;
          *v20 = *(_QWORD *)(a1 + 408);
        }
        if ( *v6 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v6);
        v21 = *(void **)(a1 + 160);
        if ( v21 && v21 != (void *)-1LL )
          CloseHandle(v21);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        *(_QWORD *)(a1 + 352) = a1 + 16;
        *(_WORD *)(a1 + 152) = 0;
        *(_QWORD *)a1 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 352) )
        {
LABEL_69:
          std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 16);
          if ( *(_WORD *)(a1 + 154) )
            operator delete((void *)a1);
        }
      }
      return;
    case 5:
      v3 = *(void **)(a1 + 160);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_69;
    case 6:
      goto LABEL_47;
    case 7:
      v15 = *(volatile __int64 **)(a1 + 200);
      if ( v15 )
      {
        v26 = *(_QWORD *)(a1 + 200);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 192) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
      if ( *(_QWORD *)(a1 + 184) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 184);
      if ( *(_QWORD *)(a1 + 408) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
      v16 = *(void **)(a1 + 160);
      if ( v16 && v16 != (void *)-1LL )
        CloseHandle(v16);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_69;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18022ee90  mov     [rsp+Block], rcx
0x18022ee95  push    rbx
0x18022ee96  push    rsi
0x18022ee97  push    rdi
0x18022ee98  push    r12
0x18022ee9a  push    r14
0x18022ee9c  push    r15
0x18022ee9e  sub     rsp, 118h
0x18022eea5  mov     rsi, [rsp+148h+Block]
0x18022eead  movzx   eax, word ptr [rsi+98h]
0x18022eeb4  mov     [rsp+148h+var_128], ax
0x18022eeb9  inc     ax; switch 9 cases
0x18022eebc  cmp     ax, 8
0x18022eec0  ja      def_18022EEDB; jumptable 000000018022EEDB default case, case 0
0x18022eec6  movsx   rax, ax
0x18022eeca  lea     rdx, cs:180000000h
0x18022eed1  mov     ecx, ds:(jpt_18022EEDB - 180000000h)[rdx+rax*4]
0x18022eed8  add     rcx, rdx
0x18022eedb  jmp     rcx; switch jump
0x18022eedd  jmp     loc_18022F460; jumptable 000000018022EEDB case 3
0x18022eee2  xor     ebx, ebx; jumptable 000000018022EEDB case 2
0x18022eee4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022eeeb  lea     rcx, [rsi+0A0h]
0x18022eef2  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18022eef7  nop
0x18022eef8  mov     [rsi+0A8h], bl
0x18022eefe  mov     eax, [rsi+70h]
0x18022ef01  cmp     eax, 2
0x18022ef04  jnz     short loc_18022EF43
0x18022ef06  lea     rdx, [rsi+180h]; struct winrt::impl::slim_source_location *
0x18022ef0d  mov     dword ptr [rdx], 1628h
0x18022ef13  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022ef1a  mov     [rsi+188h], rax
0x18022ef21  mov     [rsi+190h], rbx
0x18022ef28  lea     rcx, [rsp+148h+pExceptionObject]; this
0x18022ef2d  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022ef32  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022ef39  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x18022ef3e  call    _CxxThrowException
0x18022ef43  mov     eax, 4
0x18022ef48  mov     [rsi+98h], ax
0x18022ef4f  mov     rdx, rsi
0x18022ef52  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18022ef57  jmp     loc_18022F483
0x18022ef5c  mov     rcx, [rsi+0A0h]; jumptable 000000018022EEDB case 5
0x18022ef63  test    rcx, rcx
0x18022ef66  jz      short loc_18022EF7D
0x18022ef68  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022ef6c  jz      short loc_18022EF7D
0x18022ef6e  mov     [rsp+148h+arg_8], rcx
0x18022ef76  call    cs:__imp_CloseHandle
0x18022ef7c  nop
0x18022ef7d  mov     eax, 0FFFFFFFFh
0x18022ef82  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022ef8a  sub     eax, 1
0x18022ef8d  jz      short loc_18022EF99
0x18022ef8f  test    eax, eax
0x18022ef91  jns     short loc_18022EF99
0x18022ef93  call    abort
0x18022ef99  jmp     loc_18022F460; jumptable 000000018022EEDB cases -1,1
0x18022ef9e  lea     rcx, [rsi+170h]; jumptable 000000018022EEDB case 4
0x18022efa5  movups  xmm0, xmmword ptr [rsi+84h]
0x18022efac  movaps  xmmword ptr [rcx], xmm0
0x18022efaf  mov     r8d, 10h; Size
0x18022efb5  lea     rdx, ?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; Buf2
0x18022efbc  call    memcmp
0x18022efc1  test    eax, eax
0x18022efc3  jnz     loc_18022F197
0x18022efc9  mov     ecx, 1B8h; Size
0x18022efce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022efd3  mov     rdi, rax
0x18022efd6  mov     [rsi+1A0h], rax
0x18022efdd  lea     rdx, [rsi+1B0h]
0x18022efe4  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x18022efeb  movaps  xmmword ptr [rdx], xmm0
0x18022efee  mov     rcx, rax
0x18022eff1  call    ??0ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@UGuid@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::ImageEmbeddingsGenerator(asg::Guid)
0x18022eff6  lea     rax, ??_7?$heap_implements@UImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator>::`vftable'
0x18022effd  mov     [rdi], rax
0x18022f000  lea     rax, [rdi+10h]
0x18022f004  xor     ebx, ebx
0x18022f006  test    rdi, rdi
0x18022f009  cmovz   rax, rbx
0x18022f00d  mov     [rsi+198h], rax
0x18022f014  lea     rdi, [rsi+0B0h]
0x18022f01b  mov     [rdi], rax
0x18022f01e  cmp     [rsi+94h], bl
0x18022f024  jz      loc_18022F3BA
0x18022f02a  mov     rcx, [rsi+198h]
0x18022f031  mov     [rsi+0B8h], rcx
0x18022f038  test    rcx, rcx
0x18022f03b  jz      short loc_18022F04B
0x18022f03d  mov     rax, [rcx]
0x18022f040  mov     rax, [rax+8]
0x18022f044  call    cs:__guard_dispatch_icall_fptr
0x18022f04a  nop
0x18022f04b  mov     rdi, [rsi+0A0h]
0x18022f052  test    rdi, rdi
0x18022f055  jnz     short loc_18022F072
0x18022f057  lea     rdi, [rsi+0C0h]
0x18022f05e  mov     rdx, rdi
0x18022f061  lea     rcx, [rsi+0B8h]
0x18022f068  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateEmbeddingsGeneratorAsync____8____lambda_1___operator__
0x18022f06d  jmp     loc_18022F112
0x18022f072  lea     rcx, [rsi+1C8h]
0x18022f079  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x18022f07e  nop
0x18022f07f  mov     r14, [rsi+1C8h]
0x18022f086  mov     [rsi+1C8h], rbx
0x18022f08d  mov     [rsi+1C0h], r14
0x18022f094  mov     rcx, rdi; hToken
0x18022f097  call    cs:__imp_ImpersonateLoggedOnUser
0x18022f09d  mov     rcx, [rsp+148h]; this
0x18022f0a5  test    eax, eax
0x18022f0a7  jnz     short loc_18022F0B3
0x18022f0a9  mov     edx, 1Ch; void *
0x18022f0ae  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18022f0b3  lea     rdi, [rsi+0C0h]
0x18022f0ba  mov     rdx, rdi
0x18022f0bd  lea     rcx, [rsi+0B8h]
0x18022f0c4  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__CreateEmbeddingsGeneratorAsync____8____lambda_1___operator__
0x18022f0c9  nop
0x18022f0ca  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18022f0ce  jz      short loc_18022F0F4
0x18022f0d0  mov     rdx, r14; Token
0x18022f0d3  xor     ecx, ecx; Thread
0x18022f0d5  call    cs:__imp_SetThreadToken
0x18022f0db  test    eax, eax
0x18022f0dd  jnz     short loc_18022F0E5
0x18022f0df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18022f0e5  test    r14, r14
0x18022f0e8  jz      short loc_18022F0F4
0x18022f0ea  mov     rcx, r14; hObject
0x18022f0ed  call    cs:__imp_CloseHandle
0x18022f0f3  nop
0x18022f0f4  mov     rcx, [rsi+1C8h]; hObject
0x18022f0fb  test    rcx, rcx
0x18022f0fe  jz      short loc_18022F112
0x18022f100  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022f104  jz      short loc_18022F112
0x18022f106  mov     [rsp+148h+var_120], rcx
0x18022f10b  call    cs:__imp_CloseHandle
0x18022f111  nop
0x18022f112  mov     eax, [rsi+70h]
0x18022f115  cmp     eax, 2
0x18022f118  jnz     short loc_18022F157
0x18022f11a  lea     rdx, [rsi+1D0h]; struct winrt::impl::slim_source_location *
0x18022f121  mov     dword ptr [rdx], 1628h
0x18022f127  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022f12e  mov     [rsi+1D8h], rax
0x18022f135  mov     [rsi+1E0h], rbx
0x18022f13c  lea     rcx, [rsp+148h+var_F8]; this
0x18022f141  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022f146  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022f14d  lea     rcx, [rsp+148h+var_F8]; pExceptionObject
0x18022f152  call    _CxxThrowException
0x18022f157  lea     rcx, [rsi+0C8h]
0x18022f15e  mov     [rcx], rbx
0x18022f161  mov     [rsi+0D0h], rdi
0x18022f168  mov     [rsi+0D8h], rbx
0x18022f16f  mov     byte ptr [rsi+0E0h], 1
0x18022f176  mov     eax, 6
0x18022f17b  mov     [rsi+98h], ax
0x18022f182  mov     rdx, rsi
0x18022f185  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18022f18a  test    al, al
0x18022f18c  jz      loc_18022F2BC
0x18022f192  jmp     loc_18022F483
0x18022f197  mov     dword ptr [rsi+128h], 0B1h
0x18022f1a1  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022f1a8  mov     [rsi+130h], rax
0x18022f1af  xor     ebx, ebx
0x18022f1b1  mov     [rsi+138h], rbx
0x18022f1b8  lea     rdx, aModelIdIsNotCu; "Model id is not currently supported by "...
0x18022f1bf  lea     rcx, [rsi+140h]; this
0x18022f1c6  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022f1cb  lea     r8, [rsi+128h]; struct winrt::impl::slim_source_location *
0x18022f1d2  lea     rdx, [rsi+140h]; struct winrt::param::hstring *
0x18022f1d9  lea     rcx, [rsp+148h+var_E0]; this
0x18022f1de  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022f1e3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18022f1ea  lea     rcx, [rsp+148h+var_E0]; pExceptionObject
0x18022f1ef  call    _CxxThrowException
0x18022f1f5  mov     rdi, [rsi+0C8h]; jumptable 000000018022EEDB case 7
0x18022f1fc  test    rdi, rdi
0x18022f1ff  jz      short loc_18022F227
0x18022f201  mov     [rsp+148h+var_B0], rdi
0x18022f209  xor     ebx, ebx
0x18022f20b  mov     eax, ebx
0x18022f20d  xchg    rax, [rdi]
0x18022f210  cmp     rax, 1
0x18022f214  jnz     short loc_18022F227
0x18022f216  call    _Thrd_yield
0x18022f21b  mov     rax, rbx
0x18022f21e  xchg    rax, [rdi]
0x18022f221  cmp     rax, 1
0x18022f225  jz      short loc_18022F216
0x18022f227  lea     rcx, [rsi+0C0h]
0x18022f22e  mov     rax, [rcx]
0x18022f231  mov     [rsp+148h+arg_10], rax
0x18022f239  test    rax, rax
0x18022f23c  jz      short loc_18022F244
0x18022f23e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f243  nop
0x18022f244  lea     rcx, [rsi+0B8h]
0x18022f24b  mov     rax, [rcx]
0x18022f24e  mov     [rsp+148h+arg_18], rax
0x18022f256  test    rax, rax
0x18022f259  jz      short loc_18022F261
0x18022f25b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f260  nop
0x18022f261  cmp     qword ptr [rsi+198h], 0
0x18022f269  jz      short loc_18022F278
0x18022f26b  lea     rcx, [rsi+0B0h]
0x18022f272  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f277  nop
0x18022f278  mov     rcx, [rsi+0A0h]; hObject
0x18022f27f  test    rcx, rcx
0x18022f282  jz      short loc_18022F299
0x18022f284  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18022f288  jz      short loc_18022F299
0x18022f28a  mov     [rsp+148h+arg_8], rcx
0x18022f292  call    cs:__imp_CloseHandle
0x18022f298  nop
0x18022f299  mov     eax, 0FFFFFFFFh
0x18022f29e  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022f2a6  sub     eax, 1
0x18022f2a9  jz      short loc_18022F2B5
0x18022f2ab  test    eax, eax
0x18022f2ad  jns     short loc_18022F2B5
0x18022f2af  call    abort
0x18022f2b5  jmp     loc_18022F460; jumptable 000000018022EEDB cases -1,1
0x18022f2ba  xor     ebx, ebx; jumptable 000000018022EEDB case 6
0x18022f2bc  lea     rcx, [rsi+0C8h]
0x18022f2c3  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18022f2c8  movzx   r14d, al
0x18022f2cc  mov     rdi, [rsi+0C8h]
0x18022f2d3  test    rdi, rdi
0x18022f2d6  jz      short loc_18022F301
0x18022f2d8  mov     [rsp+148h+var_B0], rdi
0x18022f2e0  mov     rcx, rbx
0x18022f2e3  xchg    rcx, [rdi]
0x18022f2e6  cmp     rcx, 1
0x18022f2ea  jnz     short loc_18022F301
0x18022f2ec  nop     dword ptr [rax+00h]
0x18022f2f0  call    _Thrd_yield
0x18022f2f5  mov     rax, rbx
0x18022f2f8  xchg    rax, [rdi]
0x18022f2fb  cmp     rax, 1
0x18022f2ff  jz      short loc_18022F2F0
0x18022f301  lea     rcx, [rsi+0C0h]
0x18022f308  mov     rax, [rcx]
0x18022f30b  mov     [rsp+148h+arg_10], rax
0x18022f313  test    rax, rax
0x18022f316  jz      short loc_18022F31E
0x18022f318  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f31d  nop
0x18022f31e  lea     rcx, [rsi+0B8h]
0x18022f325  mov     rax, [rcx]
0x18022f328  mov     [rsp+148h+arg_18], rax
0x18022f330  test    rax, rax
0x18022f333  jz      short loc_18022F33A
0x18022f335  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f33a  test    r14b, r14b
0x18022f33d  jnz     short loc_18022F3B3
0x18022f33f  mov     dword ptr [rsi+0E8h], 0A8h
0x18022f349  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022f350  mov     [rsi+0F0h], rax
0x18022f357  mov     [rsi+0F8h], rbx
0x18022f35e  lea     rdx, aFailedToLoadIm; "Failed to load image embedding model - "...
0x18022f365  lea     rcx, [rsi+100h]; this
0x18022f36c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022f371  lea     rcx, [rsi+120h]; this
0x18022f378  mov     edx, 83EBAD1Dh; int
0x18022f37d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18022f382  lea     r9, [rsi+0E8h]
0x18022f389  lea     r8, [rsi+100h]
0x18022f390  mov     edx, [rax]
0x18022f392  lea     rcx, [rsp+148h+var_C8]
0x18022f39a  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022f39f  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18022f3a6  lea     rcx, [rsp+148h+var_C8]; pExceptionObject
0x18022f3ae  call    _CxxThrowException
0x18022f3b3  lea     rdi, [rsi+0B0h]
0x18022f3ba  lea     r14, [rsi+78h]
0x18022f3be  cmp     r14, rdi
0x18022f3c1  jz      short loc_18022F3DE
0x18022f3c3  cmp     qword ptr [r14], 0
0x18022f3c7  jz      short loc_18022F3D1
0x18022f3c9  mov     rcx, r14
0x18022f3cc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022f3d1  mov     [rdi], rbx
0x18022f3d4  mov     rax, [rsi+198h]
0x18022f3db  mov     [r14], rax
0x18022f3de  mov     rax, [rdi]
0x18022f3e1  mov     [rsp+148h+var_118], rax
0x18022f3e6  test    rax, rax
0x18022f3e9  jz      short loc_18022F3F4
0x18022f3eb  mov     rcx, rdi
0x18022f3ee  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
  ... truncated ...
```
