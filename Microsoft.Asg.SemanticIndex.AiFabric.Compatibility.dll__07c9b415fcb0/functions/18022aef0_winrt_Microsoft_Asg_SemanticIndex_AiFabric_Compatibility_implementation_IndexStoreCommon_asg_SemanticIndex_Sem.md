# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync$_ResumeCoro$1_int_

- ea: `0x18022aef0`
- end: `0x18022b368`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync$_ResumeCoro$1_int_`
- size: `1144`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026a50`
- `0x180050970`
- `0x18022aed0`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x180010dd0`
- `0x180020670`
- `0x18002cd70`
- `0x18002f8e0`
- `0x180047520`
- `0x180078da0`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180229032`
- `0x18022aef0`
- `0x180242120`

## string_xrefs

- `0x18022b1f1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x18022b03e`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022b0aa`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::CancelMaintenanceAsync__ResumeCoro_1_int_(
        __int64 a1)
{
  _WORD *v2; // r15
  __int64 *v3; // rbx
  __int64 v4; // r13
  __int64 *v5; // rax
  __int64 v6; // r14
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  struct _TP_WAIT *v11; // rcx
  volatile __int64 *v12; // rbx
  struct _TP_WAIT *v13; // rcx
  volatile __int64 *v14; // rbx
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v16[112]; // [rsp+88h] [rbp-70h] BYREF

  v2 = (_WORD *)(a1 + 144);
  switch ( *(_WORD *)(a1 + 144) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_37;
    case 2:
      v3 = (__int64 *)(a1 + 152);
      *(_QWORD *)(a1 + 152) = 0;
      v4 = *(_QWORD *)(a1 + 128);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        v4,
        a1 + 160,
        0);
      if ( *(_BYTE *)(v4 + 203) )
      {
        v5 = (__int64 *)(v4 + 208);
        v6 = 0;
        if ( v3 != (__int64 *)(v4 + 208) )
        {
          v6 = *v5;
          *v3 = *v5;
          if ( v6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        }
        if ( *(_BYTE *)(a1 + 168) )
          Mtx_unlock(*(_Mtx_t *)(a1 + 160));
        if ( v6 )
        {
          *(_QWORD *)(a1 + 352) = 0;
          v7 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64))v6)(
                 v6,
                 &winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>,
                 a1 + 352);
          v8 = *(_QWORD *)(a1 + 352);
          *(_QWORD *)(a1 + 296) = v8;
          *(_DWORD *)(a1 + 304) = 207;
          *(_QWORD *)(a1 + 312) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
          *(_QWORD *)(a1 + 320) = 0;
          if ( v7 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v7, a1 + 304);
          }
          *(_DWORD *)(a1 + 328) = 209;
          *(_QWORD *)(a1 + 336) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
          *(_QWORD *)(a1 + 344) = 0;
          v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8);
          if ( v9 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v9, a1 + 328);
          }
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 296);
        }
        v10 = *(_QWORD *)(v4 + 216);
        *(_QWORD *)(a1 + 176) = 0;
        *(_QWORD *)(a1 + 184) = 0;
        *(_QWORD *)(a1 + 192) = 0;
        *(_QWORD *)(a1 + 200) = v10;
        *(_DWORD *)(a1 + 208) = 0;
        *(_QWORD *)(a1 + 216) = 0;
        *(_DWORD *)(a1 + 224) = 0;
        if ( *(_DWORD *)(a1 + 112) == 2 )
        {
          *(_DWORD *)(a1 + 248) = 5672;
          *(_QWORD *)(a1 + 256) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
          *(_QWORD *)(a1 + 264) = 0;
          winrt::hresult_canceled::hresult_canceled(
            (winrt::hresult_canceled *)pExceptionObject,
            (const struct winrt::impl::slim_source_location *)(a1 + 248));
          throw (winrt::hresult_canceled *)pExceptionObject;
        }
        if ( WaitForSingleObject_0(*(HANDLE *)(a1 + 200), 0) )
        {
          *v2 = 4;
          winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(
            (_QWORD *)(a1 + 176),
            a1);
          return;
        }
LABEL_27:
        if ( _InterlockedExchange((volatile __int32 *)(a1 + 224), 0) == 2 )
        {
          *(_DWORD *)(a1 + 272) = 9410;
          *(_QWORD *)(a1 + 280) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\base.h";
          *(_QWORD *)(a1 + 288) = 0;
          winrt::hresult_canceled::hresult_canceled(
            (winrt::hresult_canceled *)v16,
            (const struct winrt::impl::slim_source_location *)(a1 + 272));
          throw (winrt::hresult_canceled *)v16;
        }
        v13 = *(struct _TP_WAIT **)(a1 + 184);
        if ( v13 )
        {
          CloseThreadpoolWait_0(v13);
          *(_QWORD *)(a1 + 184) = 0;
        }
        v14 = *(volatile __int64 **)(a1 + 176);
        if ( v14 && _InterlockedExchange64(v14, 0) == 1 )
        {
          do
            Thrd_yield();
          while ( _InterlockedExchange64(v14, 0) == 1 );
        }
        if ( *(_QWORD *)(a1 + 152) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      }
      else if ( *(_BYTE *)(a1 + 168) )
      {
        Mtx_unlock(*(_Mtx_t *)(a1 + 160));
      }
      *(_QWORD *)(a1 + 232) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
      {
LABEL_37:
        if ( *(_QWORD *)(a1 + 104) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
        if ( *(_QWORD *)(a1 + 96) )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
        __ExceptionPtrDestroy((void *)(a1 + 72));
        winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 16);
        if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
          abort();
        if ( *(_WORD *)(a1 + 146) )
          operator delete((void *)a1);
      }
      return;
    case 4:
      goto LABEL_27;
    case 5:
      v11 = *(struct _TP_WAIT **)(a1 + 184);
      if ( v11 )
      {
        CloseThreadpoolWait_0(v11);
        *(_QWORD *)(a1 + 184) = 0;
      }
      v12 = *(volatile __int64 **)(a1 + 176);
      if ( v12 && _InterlockedExchange64(v12, 0) == 1 )
      {
        do
          Thrd_yield();
        while ( _InterlockedExchange64(v12, 0) == 1 );
      }
      if ( *(_QWORD *)(a1 + 152) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      goto LABEL_37;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x18022aef0  mov     [rsp+Block], rcx
0x18022aef5  push    rbx
0x18022aef6  push    rsi
0x18022aef7  push    rdi
0x18022aef8  push    r12
0x18022aefa  push    r13
0x18022aefc  push    r14
0x18022aefe  push    r15
0x18022af00  sub     rsp, 0C0h
0x18022af07  mov     rdi, [rsp+0F8h+Block]
0x18022af0f  lea     r15, [rdi+90h]
0x18022af16  mov     [rsp+0F8h+arg_10], r15
0x18022af1e  movzx   eax, word ptr [r15]
0x18022af22  mov     [rsp+0F8h+var_D8], ax
0x18022af27  inc     ax; switch 7 cases
0x18022af2a  cmp     ax, 6
0x18022af2e  ja      def_18022AF49; jumptable 000000018022AF49 default case, case 0
0x18022af34  movsx   rax, ax
0x18022af38  lea     rdx, cs:180000000h
0x18022af3f  mov     ecx, ds:(jpt_18022AF49 - 180000000h)[rdx+rax*4]
0x18022af46  add     rcx, rdx
0x18022af49  jmp     rcx; switch jump
0x18022af4b  jmp     loc_18022B2D0; jumptable 000000018022AF49 case 3
0x18022af50  xor     esi, esi; jumptable 000000018022AF49 case 2
0x18022af52  lea     rbx, [rdi+98h]
0x18022af59  mov     [rbx], rsi
0x18022af5c  mov     r13, [rdi+80h]
0x18022af63  xor     r8d, r8d
0x18022af66  lea     rdx, [rdi+0A0h]
0x18022af6d  mov     rcx, r13
0x18022af70  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18022af75  cmp     [r13+0CBh], sil
0x18022af7c  jnz     short loc_18022AFA4
0x18022af7e  movzx   eax, byte ptr [rdi+0A8h]
0x18022af85  mov     [rsp+0F8h+var_C8], al
0x18022af89  test    al, al
0x18022af8b  jz      short loc_18022AF9F
0x18022af8d  mov     rcx, [rdi+0A0h]; _Mtx_t
0x18022af94  mov     [rsp+0F8h+var_D0], rcx
0x18022af99  call    _Mtx_unlock
0x18022af9e  nop
0x18022af9f  jmp     loc_18022B2A9
0x18022afa4  lea     rax, [r13+0D0h]
0x18022afab  mov     r14, rsi
0x18022afae  cmp     rbx, rax
0x18022afb1  jz      short loc_18022AFCE
0x18022afb3  mov     r14, [rax]
0x18022afb6  mov     [rbx], r14
0x18022afb9  test    r14, r14
0x18022afbc  jz      short loc_18022AFCE
0x18022afbe  mov     rax, [r14]
0x18022afc1  mov     rcx, r14
0x18022afc4  mov     rax, [rax+8]
0x18022afc8  call    cs:__guard_dispatch_icall_fptr
0x18022afce  movzx   eax, byte ptr [rdi+0A8h]
0x18022afd5  mov     [rsp+0F8h+var_C8], al
0x18022afd9  test    al, al
0x18022afdb  jz      short loc_18022AFEE
0x18022afdd  mov     rcx, [rdi+0A0h]; _Mtx_t
0x18022afe4  mov     [rsp+0F8h+var_D0], rcx
0x18022afe9  call    _Mtx_unlock
0x18022afee  test    r14, r14
0x18022aff1  jz      loc_18022B0AA
0x18022aff7  mov     [rdi+160h], rsi
0x18022affe  mov     rax, [r14]
0x18022b001  lea     r8, [rdi+160h]
0x18022b008  lea     rdx, ??$guid_v@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IAsyncInfo>
0x18022b00f  mov     rcx, r14
0x18022b012  mov     rax, [rax]
0x18022b015  call    cs:__guard_dispatch_icall_fptr
0x18022b01b  mov     rcx, [rdi+160h]
0x18022b022  mov     [rsp+0F8h+arg_18], rcx
0x18022b02a  mov     [rdi+128h], rcx
0x18022b031  lea     rdx, [rdi+130h]
0x18022b038  mov     dword ptr [rdx], 0CFh
0x18022b03e  lea     rbx, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b045  mov     [rdi+138h], rbx
0x18022b04c  mov     [rdi+140h], rsi
0x18022b053  test    eax, eax
0x18022b055  jns     short loc_18022B061
0x18022b057  lfence
0x18022b05a  mov     ecx, eax
0x18022b05c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022b061  mov     dword ptr [rdi+148h], 0D1h
0x18022b06b  mov     [rdi+150h], rbx
0x18022b072  mov     [rdi+158h], rsi
0x18022b079  mov     rax, [rcx]
0x18022b07c  mov     rax, [rax+48h]
0x18022b080  call    cs:__guard_dispatch_icall_fptr
0x18022b086  test    eax, eax
0x18022b088  jns     short loc_18022B09C
0x18022b08a  lfence
0x18022b08d  lea     rdx, [rdi+148h]
0x18022b094  mov     ecx, eax
0x18022b096  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18022b09c  lea     rcx, [rdi+128h]
0x18022b0a3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b0a8  jmp     short loc_18022B0B1
0x18022b0aa  lea     rbx, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b0b1  mov     rax, [r13+0D8h]
0x18022b0b8  mov     [rdi+0B0h], rsi
0x18022b0bf  mov     [rdi+0B8h], rsi
0x18022b0c6  mov     [rdi+0C0h], rsi
0x18022b0cd  mov     [rdi+0C8h], rax
0x18022b0d4  mov     [rdi+0D0h], esi
0x18022b0da  mov     [rdi+0D8h], rsi
0x18022b0e1  mov     [rdi+0E0h], esi
0x18022b0e7  mov     eax, [rdi+70h]
0x18022b0ea  cmp     eax, 2
0x18022b0ed  jnz     short loc_18022B125
0x18022b0ef  lea     rdx, [rdi+0F8h]; struct winrt::impl::slim_source_location *
0x18022b0f6  mov     dword ptr [rdx], 1628h
0x18022b0fc  mov     [rdi+100h], rbx
0x18022b103  mov     [rdi+108h], rsi
0x18022b10a  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18022b10f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022b114  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022b11b  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18022b120  call    _CxxThrowException
0x18022b125  mov     rcx, [rdi+0C8h]; hHandle
0x18022b12c  mov     [rsp+0F8h+var_A8], rcx
0x18022b131  xor     edx, edx; dwMilliseconds
0x18022b133  call    WaitForSingleObject_0
0x18022b138  test    eax, eax
0x18022b13a  jz      loc_18022B1D7
0x18022b140  mov     eax, 4
0x18022b145  mov     [r15], ax
0x18022b149  mov     rdx, rdi
0x18022b14c  lea     rcx, [rdi+0B0h]
0x18022b153  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@H@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,int>::promise_type>)
0x18022b158  jmp     loc_18022B336
0x18022b15d  mov     rcx, [rdi+0B8h]; jumptable 000000018022AF49 case 5
0x18022b164  mov     [rsp+0F8h+var_B8], rcx
0x18022b169  test    rcx, rcx
0x18022b16c  jz      short loc_18022B183
0x18022b16e  mov     [rsp+0F8h+var_B8], rcx
0x18022b173  call    CloseThreadpoolWait_0
0x18022b178  xor     esi, esi
0x18022b17a  mov     [rdi+0B8h], rsi
0x18022b181  jmp     short loc_18022B185
0x18022b183  xor     esi, esi
0x18022b185  mov     rbx, [rdi+0B0h]
0x18022b18c  test    rbx, rbx
0x18022b18f  jz      short loc_18022B1B3
0x18022b191  mov     [rsp+0F8h+var_C0], rbx
0x18022b196  mov     rax, rsi
0x18022b199  xchg    rax, [rbx]
0x18022b19c  cmp     rax, 1
0x18022b1a0  jnz     short loc_18022B1B3
0x18022b1a2  call    _Thrd_yield
0x18022b1a7  mov     rax, rsi
0x18022b1aa  xchg    rax, [rbx]
0x18022b1ad  cmp     rax, 1
0x18022b1b1  jz      short loc_18022B1A2
0x18022b1b3  lea     rcx, [rdi+98h]
0x18022b1ba  mov     rax, [rcx]
0x18022b1bd  mov     [rsp+0F8h+arg_8], rax
0x18022b1c5  test    rax, rax
0x18022b1c8  jz      short loc_18022B1D0
0x18022b1ca  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b1cf  nop
0x18022b1d0  jmp     loc_18022B2D0; jumptable 000000018022AF49 cases -1,1
0x18022b1d5  xor     esi, esi; jumptable 000000018022AF49 case 4
0x18022b1d7  mov     eax, esi
0x18022b1d9  xchg    eax, [rdi+0E0h]
0x18022b1df  cmp     eax, 2
0x18022b1e2  jnz     short loc_18022B228
0x18022b1e4  lea     rdx, [rdi+110h]; struct winrt::impl::slim_source_location *
0x18022b1eb  mov     dword ptr [rdx], 24C2h
0x18022b1f1  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022b1f8  mov     [rdi+118h], rax
0x18022b1ff  mov     [rdi+120h], rsi
0x18022b206  lea     rcx, [rsp+0F8h+var_70]; this
0x18022b20e  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022b213  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022b21a  lea     rcx, [rsp+0F8h+var_70]; pExceptionObject
0x18022b222  call    _CxxThrowException
0x18022b228  mov     rcx, [rdi+0B8h]; pwa
0x18022b22f  mov     [rsp+0F8h+var_B8], rcx
0x18022b234  test    rcx, rcx
0x18022b237  jz      short loc_18022B24A
0x18022b239  mov     [rsp+0F8h+var_B8], rcx
0x18022b23e  call    CloseThreadpoolWait_0
0x18022b243  mov     [rdi+0B8h], rsi
0x18022b24a  mov     rbx, [rdi+0B0h]
0x18022b251  test    rbx, rbx
0x18022b254  jz      short loc_18022B278
0x18022b256  mov     [rsp+0F8h+var_C0], rbx
0x18022b25b  mov     rax, rsi
0x18022b25e  xchg    rax, [rbx]
0x18022b261  cmp     rax, 1
0x18022b265  jnz     short loc_18022B278
0x18022b267  call    _Thrd_yield
0x18022b26c  mov     rax, rsi
0x18022b26f  xchg    rax, [rbx]
0x18022b272  cmp     rax, 1
0x18022b276  jz      short loc_18022B267
0x18022b278  lea     rcx, [rdi+98h]
0x18022b27f  mov     rax, [rcx]
0x18022b282  mov     [rsp+0F8h+arg_8], rax
0x18022b28a  test    rax, rax
0x18022b28d  jz      short loc_18022B295
0x18022b28f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b294  nop
0x18022b295  jmp     short loc_18022B2A9
0x18022b297  xor     esi, esi
0x18022b299  mov     rdi, [rsp+0F8h+Block]
0x18022b2a1  mov     r15, [rsp+0F8h+arg_10]
0x18022b2a9  lea     rcx, [rdi+0E8h]
0x18022b2b0  lea     rax, [rdi+10h]
0x18022b2b4  mov     [rcx], rax
0x18022b2b7  xor     eax, eax
0x18022b2b9  mov     [r15], ax
0x18022b2bd  mov     [rdi], rsi
0x18022b2c0  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAU?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@U?$com_ptr@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@4@UCancellationTokenSource@asg@@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18022b2c5  test    al, al
0x18022b2c7  jnz     short loc_18022B336
0x18022b2c9  nop     dword ptr [rax+00000000h]
0x18022b2d0  lea     rcx, [rdi+68h]; jumptable 000000018022AF49 cases -1,1
0x18022b2d4  cmp     qword ptr [rcx], 0
0x18022b2d8  jz      short loc_18022B2DF
0x18022b2da  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b2df  lea     rcx, [rdi+60h]
0x18022b2e3  cmp     qword ptr [rcx], 0
0x18022b2e7  jz      short loc_18022B2EE
0x18022b2e9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022b2ee  lea     rcx, [rdi+48h]; void *
0x18022b2f2  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18022b2f7  lea     rcx, [rdi+10h]
0x18022b2fb  call    ?subtract_final_reference@?$root_implements@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@U12@V?$map@Uhstring@winrt@@U12@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@U12@@std@@@4@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@U12@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAIXZ; winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(void)
0x18022b300  mov     eax, 0FFFFFFFFh
0x18022b305  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022b30d  sub     eax, 1
0x18022b310  jz      short loc_18022B31C
0x18022b312  test    eax, eax
0x18022b314  jns     short loc_18022B31C
0x18022b316  call    abort
0x18022b31c  cmp     word ptr [rdi+92h], 0
0x18022b324  jz      short loc_18022B336
0x18022b326  mov     edx, 170h
0x18022b32b  mov     rcx, rdi; Block
0x18022b32e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022b333  jmp     short loc_18022B336
0x18022b335  int     3; Trap to Debugger
0x18022b336  add     rsp, 0C0h
0x18022b33d  pop     r15
0x18022b33f  pop     r14
0x18022b341  pop     r13
0x18022b343  pop     r12
0x18022b345  pop     rdi
0x18022b346  pop     rsi
0x18022b347  pop     rbx
0x18022b348  retn
```
