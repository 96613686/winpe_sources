# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateDefaultEmbeddingsGeneratorAsync$_ResumeCoro$1

- ea: `0x180239660`
- end: `0x180239bfc`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateDefaultEmbeddingsGeneratorAsync$_ResumeCoro$1`
- size: `1436`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004b140`
- `0x180239650`

## callees

- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000d230`
- `0x18000d4b0`
- `0x18001b1f0`
- `0x18001b3c0`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020e60`
- `0x180047120`
- `0x180047520`
- `0x1800475c0`
- `0x18004b4c0`
- `0x1800611a0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x180239660`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180239746`
- `KERNEL32!CloseHandle` at `0x180239892`
- `KERNEL32!CloseHandle` at `0x1802398b0`
- `KERNEL32!CloseHandle` at `0x1802399dc`
- `KERNEL32!CloseHandle` at `0x180239b4e`
- `KERNEL32!CloseHandle` at `0x180239746`
- `KERNEL32!CloseHandle` at `0x180239892`
- `KERNEL32!CloseHandle` at `0x1802398b0`
- `KERNEL32!CloseHandle` at `0x1802399dc`
- `KERNEL32!CloseHandle` at `0x180239b4e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023987a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18023987a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023983c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18023983c`

## string_xrefs

- `0x1802396e3`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802398cc`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180239a8f`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateDefaultEmbeddingsGeneratorAsync__ResumeCoro_1(
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
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-F0h] BYREF
  _BYTE v23[24]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v24[24]; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+80h] [rbp-A8h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 132) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_67;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      ImpersonationHelper::GetThreadImpersonationToken(a1 + 144);
      *(_BYTE *)(a1 + 152) = 0;
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 288) = 5672;
        *(_QWORD *)(a1 + 296) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 304) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 288));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_WORD *)(a1 + 132) = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v2, a1);
      return;
    case 4:
      v4 = operator new(0x1B8u);
      *(_QWORD *)(a1 + 312) = v4;
      *(_OWORD *)(a1 + 336) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(v4);
      *v4 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable';
      v5 = v4 + 2;
      if ( !v4 )
        v5 = 0;
      *(_QWORD *)(a1 + 320) = v5;
      v6 = (_QWORD *)(a1 + 160);
      *(_QWORD *)(a1 + 160) = v5;
      if ( !*(_BYTE *)(a1 + 129) )
        goto LABEL_55;
      v7 = *(_QWORD *)(a1 + 320);
      *(_QWORD *)(a1 + 168) = v7;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      v8 = *(void **)(a1 + 144);
      if ( v8 )
      {
        ImpersonationHelper::GetThreadImpersonationToken(a1 + 360);
        v10 = *(void **)(a1 + 360);
        *(_QWORD *)(a1 + 360) = 0;
        *(_QWORD *)(a1 + 352) = v10;
        if ( !ImpersonateLoggedOnUser(v8) )
          wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x1C, v11, v12);
        v9 = a1 + 176;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateDefaultEmbeddingsGeneratorAsync_::_5_::_lambda_1_::operator()(
          a1 + 168,
          a1 + 176);
        if ( v10 != (void *)-1LL )
        {
          if ( !SetThreadToken(0, v10) )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
          if ( v10 )
            CloseHandle(v10);
        }
        v14 = *(void **)(a1 + 360);
        if ( v14 && v14 != (void *)-1LL )
          CloseHandle(v14);
      }
      else
      {
        v9 = a1 + 176;
        winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateDefaultEmbeddingsGeneratorAsync_::_5_::_lambda_1_::operator()(
          a1 + 168,
          a1 + 176);
      }
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 368) = 5672;
        *(_QWORD *)(a1 + 376) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 384) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v23,
          (const struct winrt::impl::slim_source_location *)(a1 + 368));
        throw (winrt::hresult_canceled *)v23;
      }
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 192) = v9;
      *(_QWORD *)(a1 + 200) = 0;
      *(_BYTE *)(a1 + 208) = 1;
      *(_WORD *)(a1 + 132) = 6;
      if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                               (_QWORD *)(a1 + 184),
                               a1) )
      {
LABEL_45:
        v17 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 184);
        v18 = *(volatile __int64 **)(a1 + 184);
        if ( v18 )
        {
          v25 = *(_QWORD *)(a1 + 184);
          while ( _InterlockedExchange64(v18, 0) == 1 )
            Thrd_yield();
        }
        if ( *(_QWORD *)(a1 + 176) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
        if ( *(_QWORD *)(a1 + 168) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
        if ( !v17 )
        {
          *(_DWORD *)(a1 + 216) = 287;
          *(_QWORD *)(a1 + 224) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
          *(_QWORD *)(a1 + 232) = 0;
          winrt::param::hstring::hstring(
            (winrt::param::hstring *)(a1 + 240),
            L"Failed to load text embedding model - migration of underlying index may be required");
          v19 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 272), -2081706723);
          winrt::hresult_error::hresult_error(v24, *v19, a1 + 240, a1 + 216);
          throw (winrt::hresult_error *)v24;
        }
        v6 = (_QWORD *)(a1 + 160);
LABEL_55:
        v20 = (_QWORD *)(a1 + 120);
        if ( (_QWORD *)(a1 + 120) != v6 )
        {
          if ( *v20 )
            winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
          *v6 = 0;
          *v20 = *(_QWORD *)(a1 + 320);
        }
        if ( *v6 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v6);
        v21 = *(void **)(a1 + 144);
        if ( v21 && v21 != (void *)-1LL )
          CloseHandle(v21);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        *(_QWORD *)(a1 + 280) = a1 + 16;
        *(_WORD *)(a1 + 132) = 0;
        *(_QWORD *)a1 = 0;
        if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(a1 + 280) )
        {
LABEL_67:
          std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 16);
          if ( *(_WORD *)(a1 + 134) )
            operator delete((void *)a1);
        }
      }
      return;
    case 5:
      v3 = *(void **)(a1 + 144);
      if ( v3 && v3 != (void *)-1LL )
        CloseHandle(v3);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_67;
    case 6:
      goto LABEL_45;
    case 7:
      v15 = *(volatile __int64 **)(a1 + 184);
      if ( v15 )
      {
        v25 = *(_QWORD *)(a1 + 184);
        while ( _InterlockedExchange64(v15, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 176) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
      if ( *(_QWORD *)(a1 + 168) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
      if ( *(_QWORD *)(a1 + 320) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 160);
      v16 = *(void **)(a1 + 144);
      if ( v16 && v16 != (void *)-1LL )
        CloseHandle(v16);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_67;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180239660  mov     [rsp+Block], rcx
0x180239665  push    rbx
0x180239666  push    rsi
0x180239667  push    rdi
0x180239668  push    r12
0x18023966a  push    r14
0x18023966c  push    r15
0x18023966e  sub     rsp, 0F8h
0x180239675  mov     rsi, [rsp+128h+Block]
0x18023967d  movzx   eax, word ptr [rsi+84h]
0x180239684  mov     [rsp+128h+var_108], ax
0x180239689  inc     ax; switch 9 cases
0x18023968c  cmp     ax, 8
0x180239690  ja      def_1802396AB; jumptable 00000001802396AB default case, case 0
0x180239696  movsx   rax, ax
0x18023969a  lea     rdx, cs:180000000h
0x1802396a1  mov     ecx, ds:(jpt_1802396AB - 180000000h)[rdx+rax*4]
0x1802396a8  add     rcx, rdx
0x1802396ab  jmp     rcx; switch jump
0x1802396ad  jmp     loc_180239BA0; jumptable 00000001802396AB case 3
0x1802396b2  xor     ebx, ebx; jumptable 00000001802396AB case 2
0x1802396b4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802396bb  lea     rcx, [rsi+90h]
0x1802396c2  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x1802396c7  nop
0x1802396c8  mov     [rsi+98h], bl
0x1802396ce  mov     eax, [rsi+70h]
0x1802396d1  cmp     eax, 2
0x1802396d4  jnz     short loc_180239713
0x1802396d6  lea     rdx, [rsi+120h]; struct winrt::impl::slim_source_location *
0x1802396dd  mov     dword ptr [rdx], 1628h
0x1802396e3  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802396ea  mov     [rsi+128h], rax
0x1802396f1  mov     [rsi+130h], rbx
0x1802396f8  lea     rcx, [rsp+128h+pExceptionObject]; this
0x1802396fd  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180239702  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180239709  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18023970e  call    _CxxThrowException
0x180239713  mov     eax, 4
0x180239718  mov     [rsi+84h], ax
0x18023971f  mov     rdx, rsi
0x180239722  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180239727  jmp     loc_180239BC3
0x18023972c  mov     rcx, [rsi+90h]; jumptable 00000001802396AB case 5
0x180239733  test    rcx, rcx
0x180239736  jz      short loc_18023974D
0x180239738  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18023973c  jz      short loc_18023974D
0x18023973e  mov     [rsp+128h+arg_8], rcx
0x180239746  call    cs:__imp_CloseHandle
0x18023974c  nop
0x18023974d  mov     eax, 0FFFFFFFFh
0x180239752  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023975a  sub     eax, 1
0x18023975d  jz      short loc_180239769
0x18023975f  test    eax, eax
0x180239761  jns     short loc_180239769
0x180239763  call    abort
0x180239769  jmp     loc_180239BA0; jumptable 00000001802396AB cases -1,1
0x18023976e  mov     ecx, 1B8h; jumptable 00000001802396AB case 4
0x180239773  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180239778  mov     rdi, rax
0x18023977b  mov     [rsi+138h], rax
0x180239782  lea     rdx, [rsi+150h]
0x180239789  movups  xmm0, cs:?VectorSpaceId@SpaceV6@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId
0x180239790  movaps  xmmword ptr [rdx], xmm0
0x180239793  mov     rcx, rax
0x180239796  call    ??0TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@UGuid@asg@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TextEmbeddingsGenerator(asg::Guid)
0x18023979b  lea     rax, ??_7?$heap_implements@UTextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::`vftable'
0x1802397a2  mov     [rdi], rax
0x1802397a5  lea     rax, [rdi+10h]
0x1802397a9  xor     ebx, ebx
0x1802397ab  test    rdi, rdi
0x1802397ae  cmovz   rax, rbx
0x1802397b2  mov     [rsi+140h], rax
0x1802397b9  lea     rdi, [rsi+0A0h]
0x1802397c0  mov     [rdi], rax
0x1802397c3  cmp     [rsi+81h], bl
0x1802397c9  jz      loc_180239AFA
0x1802397cf  mov     rcx, [rsi+140h]
0x1802397d6  mov     [rsi+0A8h], rcx
0x1802397dd  test    rcx, rcx
0x1802397e0  jz      short loc_1802397F0
0x1802397e2  mov     rax, [rcx]
0x1802397e5  mov     rax, [rax+8]
0x1802397e9  call    cs:__guard_dispatch_icall_fptr
0x1802397ef  nop
0x1802397f0  mov     rdi, [rsi+90h]
0x1802397f7  test    rdi, rdi
0x1802397fa  jnz     short loc_180239817
0x1802397fc  lea     rdi, [rsi+0B0h]
0x180239803  mov     rdx, rdi
0x180239806  lea     rcx, [rsi+0A8h]
0x18023980d  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__CreateDefaultEmbeddingsGeneratorAsync____5____lambda_1___operator__
0x180239812  jmp     loc_1802398B7
0x180239817  lea     rcx, [rsi+168h]
0x18023981e  call    ?GetThreadImpersonationToken@ImpersonationHelper@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; ImpersonationHelper::GetThreadImpersonationToken(void)
0x180239823  nop
0x180239824  mov     r14, [rsi+168h]
0x18023982b  mov     [rsi+168h], rbx
0x180239832  mov     [rsi+160h], r14
0x180239839  mov     rcx, rdi; hToken
0x18023983c  call    cs:__imp_ImpersonateLoggedOnUser
0x180239842  mov     rcx, [rsp+128h]; this
0x18023984a  test    eax, eax
0x18023984c  jnz     short loc_180239858
0x18023984e  mov     edx, 1Ch; void *
0x180239853  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180239858  lea     rdi, [rsi+0B0h]
0x18023985f  mov     rdx, rdi
0x180239862  lea     rcx, [rsi+0A8h]
0x180239869  call    _winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__CreateDefaultEmbeddingsGeneratorAsync____5____lambda_1___operator__
0x18023986e  nop
0x18023986f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180239873  jz      short loc_180239899
0x180239875  mov     rdx, r14; Token
0x180239878  xor     ecx, ecx; Thread
0x18023987a  call    cs:__imp_SetThreadToken
0x180239880  test    eax, eax
0x180239882  jnz     short loc_18023988A
0x180239884  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18023988a  test    r14, r14
0x18023988d  jz      short loc_180239899
0x18023988f  mov     rcx, r14; hObject
0x180239892  call    cs:__imp_CloseHandle
0x180239898  nop
0x180239899  mov     rcx, [rsi+168h]; hObject
0x1802398a0  test    rcx, rcx
0x1802398a3  jz      short loc_1802398B7
0x1802398a5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802398a9  jz      short loc_1802398B7
0x1802398ab  mov     [rsp+128h+var_100], rcx
0x1802398b0  call    cs:__imp_CloseHandle
0x1802398b6  nop
0x1802398b7  mov     eax, [rsi+70h]
0x1802398ba  cmp     eax, 2
0x1802398bd  jnz     short loc_1802398FC
0x1802398bf  lea     rdx, [rsi+170h]; struct winrt::impl::slim_source_location *
0x1802398c6  mov     dword ptr [rdx], 1628h
0x1802398cc  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802398d3  mov     [rsi+178h], rax
0x1802398da  mov     [rsi+180h], rbx
0x1802398e1  lea     rcx, [rsp+128h+var_D8]; this
0x1802398e6  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802398eb  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802398f2  lea     rcx, [rsp+128h+var_D8]; pExceptionObject
0x1802398f7  call    _CxxThrowException
0x1802398fc  lea     rcx, [rsi+0B8h]
0x180239903  mov     [rcx], rbx
0x180239906  mov     [rsi+0C0h], rdi
0x18023990d  mov     [rsi+0C8h], rbx
0x180239914  mov     byte ptr [rsi+0D0h], 1
0x18023991b  mov     eax, 6
0x180239920  mov     [rsi+84h], ax
0x180239927  mov     rdx, rsi
0x18023992a  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18023992f  test    al, al
0x180239931  jz      loc_180239A06
0x180239937  jmp     loc_180239BC3
0x18023993c  mov     rdi, [rsi+0B8h]; jumptable 00000001802396AB case 7
0x180239943  test    rdi, rdi
0x180239946  jz      short loc_180239971
0x180239948  mov     [rsp+128h+var_A8], rdi
0x180239950  xor     ebx, ebx
0x180239952  mov     eax, ebx
0x180239954  xchg    rax, [rdi]
0x180239957  cmp     rax, 1
0x18023995b  jnz     short loc_180239971
0x18023995d  nop     dword ptr [rax]
0x180239960  call    _Thrd_yield
0x180239965  mov     rax, rbx
0x180239968  xchg    rax, [rdi]
0x18023996b  cmp     rax, 1
0x18023996f  jz      short loc_180239960
0x180239971  lea     rcx, [rsi+0B0h]
0x180239978  mov     rax, [rcx]
0x18023997b  mov     [rsp+128h+arg_10], rax
0x180239983  test    rax, rax
0x180239986  jz      short loc_18023998E
0x180239988  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023998d  nop
0x18023998e  lea     rcx, [rsi+0A8h]
0x180239995  mov     rax, [rcx]
0x180239998  mov     [rsp+128h+arg_18], rax
0x1802399a0  test    rax, rax
0x1802399a3  jz      short loc_1802399AB
0x1802399a5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802399aa  nop
0x1802399ab  cmp     qword ptr [rsi+140h], 0
0x1802399b3  jz      short loc_1802399C2
0x1802399b5  lea     rcx, [rsi+0A0h]
0x1802399bc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802399c1  nop
0x1802399c2  mov     rcx, [rsi+90h]; hObject
0x1802399c9  test    rcx, rcx
0x1802399cc  jz      short loc_1802399E3
0x1802399ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1802399d2  jz      short loc_1802399E3
0x1802399d4  mov     [rsp+128h+arg_8], rcx
0x1802399dc  call    cs:__imp_CloseHandle
0x1802399e2  nop
0x1802399e3  mov     eax, 0FFFFFFFFh
0x1802399e8  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802399f0  sub     eax, 1
0x1802399f3  jz      short loc_1802399FF
0x1802399f5  test    eax, eax
0x1802399f7  jns     short loc_1802399FF
0x1802399f9  call    abort
0x1802399ff  jmp     loc_180239BA0; jumptable 00000001802396AB cases -1,1
0x180239a04  xor     ebx, ebx; jumptable 00000001802396AB case 6
0x180239a06  lea     rcx, [rsi+0B8h]
0x180239a0d  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x180239a12  movzx   r14d, al
0x180239a16  mov     rdi, [rsi+0B8h]
0x180239a1d  test    rdi, rdi
0x180239a20  jz      short loc_180239A47
0x180239a22  mov     [rsp+128h+var_A8], rdi
0x180239a2a  mov     rcx, rbx
0x180239a2d  xchg    rcx, [rdi]
0x180239a30  cmp     rcx, 1
0x180239a34  jnz     short loc_180239A47
0x180239a36  call    _Thrd_yield
0x180239a3b  mov     rax, rbx
0x180239a3e  xchg    rax, [rdi]
0x180239a41  cmp     rax, 1
0x180239a45  jz      short loc_180239A36
0x180239a47  lea     rcx, [rsi+0B0h]
0x180239a4e  mov     rax, [rcx]
0x180239a51  mov     [rsp+128h+arg_10], rax
0x180239a59  test    rax, rax
0x180239a5c  jz      short loc_180239A64
0x180239a5e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239a63  nop
0x180239a64  lea     rcx, [rsi+0A8h]
0x180239a6b  mov     rax, [rcx]
0x180239a6e  mov     [rsp+128h+arg_18], rax
0x180239a76  test    rax, rax
0x180239a79  jz      short loc_180239A80
0x180239a7b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239a80  test    r14b, r14b
0x180239a83  jnz     short loc_180239AF3
0x180239a85  mov     dword ptr [rsi+0D8h], 11Fh
0x180239a8f  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180239a96  mov     [rsi+0E0h], rax
0x180239a9d  mov     [rsi+0E8h], rbx
0x180239aa4  lea     rdx, aFailedToLoadTe_0; "Failed to load text embedding model - m"...
0x180239aab  lea     rcx, [rsi+0F0h]; this
0x180239ab2  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180239ab7  lea     rcx, [rsi+110h]; this
0x180239abe  mov     edx, 83EBAD1Dh; int
0x180239ac3  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180239ac8  lea     r9, [rsi+0D8h]
0x180239acf  lea     r8, [rsi+0F0h]
0x180239ad6  mov     edx, [rax]
0x180239ad8  lea     rcx, [rsp+128h+var_C0]
0x180239add  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180239ae2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180239ae9  lea     rcx, [rsp+128h+var_C0]; pExceptionObject
0x180239aee  call    _CxxThrowException
0x180239af3  lea     rdi, [rsi+0A0h]
0x180239afa  lea     r14, [rsi+78h]
0x180239afe  cmp     r14, rdi
0x180239b01  jz      short loc_180239B1E
0x180239b03  cmp     qword ptr [r14], 0
0x180239b07  jz      short loc_180239B11
0x180239b09  mov     rcx, r14
0x180239b0c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239b11  mov     [rdi], rbx
0x180239b14  mov     rax, [rsi+140h]
0x180239b1b  mov     [r14], rax
0x180239b1e  mov     rax, [rdi]
0x180239b21  mov     [rsp+128h+var_F8], rax
0x180239b26  test    rax, rax
0x180239b29  jz      short loc_180239B34
0x180239b2b  mov     rcx, rdi
0x180239b2e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180239b33  nop
0x180239b34  mov     rcx, [rsi+90h]; hObject
0x180239b3b  test    rcx, rcx
0x180239b3e  jz      short loc_180239B55
0x180239b40  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180239b44  jz      short loc_180239B55
0x180239b46  mov     [rsp+128h+arg_8], rcx
0x180239b4e  call    cs:__imp_CloseHandle
0x180239b54  nop
0x180239b55  mov     eax, 0FFFFFFFFh
0x180239b5a  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180239b62  sub     eax, 1
0x180239b65  jz      short loc_180239B71
0x180239b67  test    eax, eax
0x180239b69  jns     short loc_180239B71
0x180239b6b  call    abort
0x180239b71  jmp     short loc_180239B7D
0x180239b73  xor     ebx, ebx
0x180239b75  mov     rsi, [rsp+128h+Block]
0x180239b7d  lea     rax, [rsi+10h]
0x180239b81  lea     rcx, [rsi+118h]
0x180239b88  mov     [rcx], rax
0x180239b8b  xor     eax, eax
  ... truncated ...
```
