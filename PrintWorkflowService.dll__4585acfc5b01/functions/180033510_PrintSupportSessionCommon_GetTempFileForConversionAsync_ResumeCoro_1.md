# PrintSupportSessionCommon::GetTempFileForConversionAsync$_ResumeCoro$1

- ea: `0x180033510`
- end: `0x18003397c`
- name: `PrintSupportSessionCommon::GetTempFileForConversionAsync$_ResumeCoro$1`
- size: `1132`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033984`

## callees

- `0x180003ca0`
- `0x180003cc4`
- `0x18000495c`
- `0x180004998`
- `0x1800097ec`
- `0x18000a6a0`
- `0x1800114a4`
- `0x1800127a4`
- `0x1800129dc`
- `0x1800129f8`
- `0x180012b10`
- `0x180012d40`
- `0x180025138`
- `0x180025494`
- `0x18002747c`
- `0x1800276d8`
- `0x180029bfc`
- `0x18002faa0`
- `0x180031168`
- `0x180032100`
- `0x180032528`
- `0x18003336c`
- `0x180033510`
- `0x180035968`
- `0x180036004`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800335e0`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800335e0`

## string_xrefs

- `0x1800335ad`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x180033706`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x1800336e2`: `PdlTempFile%d_%s.tmp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PrintSupportSessionCommon::GetTempFileForConversionAsync__ResumeCoro_1(__int64 a1)
{
  __int64 v2; // r15
  __int64 v3; // r13
  unsigned int Guid; // eax
  winrt::hstring *v5; // rax
  int v6; // eax
  __int64 FileAsync; // rax
  const struct winrt::impl::slim_source_location *v8; // rax
  enum AsyncStatus v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-D8h]
  int v13; // [rsp+20h] [rbp-D8h]
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-88h] BYREF
  int v15; // [rsp+88h] [rbp-70h]
  __int16 v16; // [rsp+8Ch] [rbp-6Ch]
  __int16 v17; // [rsp+8Eh] [rbp-6Ah]
  char v18; // [rsp+90h] [rbp-68h]
  char v19; // [rsp+91h] [rbp-67h]
  char v20; // [rsp+92h] [rbp-66h]
  char v21; // [rsp+93h] [rbp-65h]
  char v22; // [rsp+94h] [rbp-64h]
  char v23; // [rsp+95h] [rbp-63h]
  char v24; // [rsp+96h] [rbp-62h]
  char v25; // [rsp+97h] [rbp-61h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v2 = a1 + 8;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_12;
    case 2:
      v3 = *(_QWORD *)(a1 + 856);
      if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::Application>,winrt::Windows::Internal::StateRepository::Application>::Size(v3 + 48) > 0xA )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)0x8000000ELL,
          v12);
      PrintSupportSessionCommon::EnsureWorkflowTempFolder((__int64)retaddr, a1 + 16);
      *(_OWORD *)(a1 + 24) = 0;
      *(_DWORD *)(a1 + 40) = 0;
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 0;
      Guid = CoCreateGuid((GUID *)(a1 + 24));
      winrt::check_hresult(a1 + 64, Guid, a1 + 40);
      memset_0((void *)(a1 + 80), 0, 0x208u);
      v15 = *(_DWORD *)(a1 + 24);
      *(_DWORD *)(a1 + 608) = v15;
      v16 = *(_WORD *)(a1 + 28);
      *(_WORD *)(a1 + 612) = v16;
      v17 = *(_WORD *)(a1 + 30);
      *(_WORD *)(a1 + 614) = v17;
      v18 = *(_BYTE *)(a1 + 32);
      *(_BYTE *)(a1 + 616) = v18;
      v19 = *(_BYTE *)(a1 + 33);
      *(_BYTE *)(a1 + 617) = v19;
      v20 = *(_BYTE *)(a1 + 34);
      *(_BYTE *)(a1 + 618) = v20;
      v21 = *(_BYTE *)(a1 + 35);
      *(_BYTE *)(a1 + 619) = v21;
      v22 = *(_BYTE *)(a1 + 36);
      *(_BYTE *)(a1 + 620) = v22;
      v23 = *(_BYTE *)(a1 + 37);
      *(_BYTE *)(a1 + 621) = v23;
      v24 = *(_BYTE *)(a1 + 38);
      *(_BYTE *)(a1 + 622) = v24;
      v25 = *(_BYTE *)(a1 + 39);
      *(_BYTE *)(a1 + 623) = v25;
      v5 = (winrt::hstring *)winrt::to_hstring(a1 + 624, a1 + 608);
      v13 = (unsigned int)winrt::hstring::c_str(v5);
      v6 = StringCchPrintfW((unsigned __int16 *)(a1 + 80), 0x104u, L"PdlTempFile%d_%s.tmp", *(unsigned int *)(v3 + 192));
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)(unsigned int)v6,
          v13);
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 624);
      *(_QWORD *)(a1 + 736) = a1 - 112;
      *(_DWORD *)(a1 + 632) = 1;
      winrt::param::hstring::hstring((winrt::param::hstring *)(a1 + 640), (const unsigned __int16 *const)(a1 + 80));
      FileAsync = winrt::impl::consume_Windows_Storage_IStorageFolder<winrt::Windows::Storage::IStorageFolder>::CreateFileAsync(
                    a1 + 16,
                    a1 + 672,
                    a1 + 640,
                    a1 + 632);
      if ( *(_DWORD *)(a1 - 112 + 96) == 2 )
      {
        v8 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 752);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v8);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 688) = FileAsync;
      *(_QWORD *)(a1 + 696) = 0;
      *(_BYTE *)(a1 + 704) = 1;
      *(_WORD *)v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type>(
                              (__int64 *)(a1 + 680),
                              a1) )
        return;
      goto LABEL_11;
    case 4:
LABEL_11:
      *(_DWORD *)(a1 + 776) = 0;
      *(_QWORD *)(a1 + 784) = 0;
      *(_QWORD *)(a1 + 792) = 0;
      winrt::check_hresult(a1 + 800, *(unsigned int *)(a1 + 700), a1 + 776);
      winrt::impl::check_status_canceled((winrt::impl *)*(unsigned int *)(a1 + 696), v9);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::GetResults(
        *(_QWORD *)(a1 + 688),
        a1 + 712);
      winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(a1 + 680);
      winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)(a1 + 672));
      v10 = *(_QWORD *)(*(_QWORD *)(v2 + 848) + 48LL);
      *(_DWORD *)(a1 + 808) = 0;
      *(_QWORD *)(a1 + 816) = 0;
      *(_QWORD *)(a1 + 824) = 0;
      v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 104LL))(v10);
      winrt::check_hresult(a1 + 832, v11, a1 + 808);
      winrt::Windows::Foundation::IUnknown::operator=(*(_QWORD *)(a1 + 736) + 104LL, a1 + 712);
      winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)(a1 + 712));
      winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)(a1 + 16));
      *(_QWORD *)(a1 + 720) = a1 - 112;
      *(_WORD *)v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_12;
      return;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(a1 + 680);
      winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)(a1 + 672));
      winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)(a1 + 16));
LABEL_12:
      std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::~promise_type(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0x3D0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180033510  mov     r11, rsp
0x180033513  mov     [r11+10h], rbx
0x180033517  mov     [r11+18h], rsi
0x18003351b  mov     [r11+8], rcx
0x18003351f  push    rdi
0x180033520  push    r12
0x180033522  push    r13
0x180033524  push    r14
0x180033526  push    r15
0x180033528  sub     rsp, 0D0h
0x18003352f  mov     rax, cs:__security_cookie
0x180033536  xor     rax, rsp
0x180033539  mov     [rsp+0F8h+var_38], rax
0x180033541  mov     rsi, rcx
0x180033544  mov     [rsp+0F8h+var_C0], rcx
0x180033549  lea     r15, [rsi+8]
0x18003354d  mov     [rsp+0F8h+var_B0], r15
0x180033552  movzx   eax, word ptr [r15]
0x180033556  mov     [rsp+0F8h+var_C8], ax
0x18003355b  inc     ax; switch 7 cases
0x18003355e  cmp     ax, 6
0x180033562  ja      def_18003357D; jumptable 000000018003357D default case, case 0
0x180033568  movsx   rax, ax
0x18003356c  lea     rdx, __ImageBase
0x180033573  mov     ecx, ds:(jpt_18003357D - 180000000h)[rdx+rax*4]
0x18003357a  add     rcx, rdx
0x18003357d  jmp     rcx; switch jump
0x18003357f  xor     r14d, r14d; jumptable 000000018003357D case 3
0x180033582  jmp     loc_180033910
0x180033587  xor     r14d, r14d; jumptable 000000018003357D case 2
0x18003358a  mov     r13, [r15+350h]
0x180033591  lea     rcx, [r13+30h]
0x180033595  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UApplication@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UApplication@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::StateRepository::Application>,winrt::Windows::Internal::StateRepository::Application>::Size(void)
0x18003359a  mov     rcx, [rsp+0F8h]; this
0x1800335a2  cmp     eax, 0Ah
0x1800335a5  jbe     short loc_1800335BD
0x1800335a7  mov     r9d, 8000000Eh; char *
0x1800335ad  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800335b4  lea     edx, [r14+4Ah]; void *
0x1800335b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800335bd  lea     rdx, [rsi+10h]
0x1800335c1  call    ?EnsureWorkflowTempFolder@PrintSupportSessionCommon@@IEAA?AUStorageFolder@Storage@Windows@winrt@@XZ; PrintSupportSessionCommon::EnsureWorkflowTempFolder(void)
0x1800335c6  nop
0x1800335c7  lea     rdi, [rsi+18h]
0x1800335cb  xorps   xmm0, xmm0
0x1800335ce  movups  xmmword ptr [rdi], xmm0
0x1800335d1  mov     [rsi+28h], r14d
0x1800335d5  mov     [rsi+30h], r14
0x1800335d9  mov     [rsi+38h], r14
0x1800335dd  mov     rcx, rdi; pguid
0x1800335e0  call    cs:__imp_CoCreateGuid
0x1800335e6  lea     rcx, [rsi+40h]
0x1800335ea  lea     r8, [rsi+28h]
0x1800335ee  mov     edx, eax
0x1800335f0  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800335f5  xor     edx, edx; Val
0x1800335f7  mov     r8d, 208h; Size
0x1800335fd  lea     rcx, [rsi+50h]; void *
0x180033601  call    memset_0
0x180033606  lea     rdx, [rsi+260h]
0x18003360d  mov     eax, [rdi]
0x18003360f  mov     [rsp+0F8h+var_70], eax
0x180033616  mov     [rdx], eax
0x180033618  movzx   eax, word ptr [rsi+1Ch]
0x18003361c  mov     [rsp+0F8h+var_6C], ax
0x180033624  mov     [rsi+264h], ax
0x18003362b  movzx   eax, word ptr [rsi+1Eh]
0x18003362f  mov     [rsp+0F8h+var_6A], ax
0x180033637  mov     [rsi+266h], ax
0x18003363e  mov     al, [rsi+20h]
0x180033641  mov     [rsp+0F8h+var_68], al
0x180033648  mov     [rsi+268h], al
0x18003364e  mov     al, [rsi+21h]
0x180033651  mov     [rsp+0F8h+var_67], al
0x180033658  mov     [rsi+269h], al
0x18003365e  mov     al, [rsi+22h]
0x180033661  mov     [rsp+0F8h+var_66], al
0x180033668  mov     [rsi+26Ah], al
0x18003366e  mov     al, [rsi+23h]
0x180033671  mov     [rsp+0F8h+var_65], al
0x180033678  mov     [rsi+26Bh], al
0x18003367e  mov     al, [rsi+24h]
0x180033681  mov     [rsp+0F8h+var_64], al
0x180033688  mov     [rsi+26Ch], al
0x18003368e  mov     al, [rsi+25h]
0x180033691  mov     [rsp+0F8h+var_63], al
0x180033698  mov     [rsi+26Dh], al
0x18003369e  mov     al, [rsi+26h]
0x1800336a1  mov     [rsp+0F8h+var_62], al
0x1800336a8  mov     [rsi+26Eh], al
0x1800336ae  mov     al, [rsi+27h]
0x1800336b1  mov     [rsp+0F8h+var_61], al
0x1800336b8  mov     [rsi+26Fh], al
0x1800336be  lea     rdi, [rsi+270h]
0x1800336c5  mov     rcx, rdi
0x1800336c8  call    ?to_hstring@winrt@@YA?AUhstring@1@AEBUguid@1@@Z; winrt::to_hstring(winrt::guid const &)
0x1800336cd  nop
0x1800336ce  mov     rcx, rax; this
0x1800336d1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800336d6  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x1800336db  mov     r9d, [r13+0C0h]
0x1800336e2  lea     r8, aPdltempfileDST; "PdlTempFile%d_%s.tmp"
0x1800336e9  mov     edx, 104h; unsigned __int64
0x1800336ee  lea     rcx, [rsi+50h]; unsigned __int16 *
0x1800336f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800336f7  mov     rcx, [rsp+0F8h]; this
0x1800336ff  test    eax, eax
0x180033701  jns     short loc_180033718
0x180033703  mov     r9d, eax; char *
0x180033706  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x18003370d  mov     edx, 53h ; 'S'; void *
0x180033712  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033718  mov     rcx, rdi
0x18003371b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180033720  lea     r13, [rsi-70h]
0x180033724  mov     [rsi+2E0h], r13
0x18003372b  lea     rdi, [rsi+278h]
0x180033732  mov     dword ptr [rdi], 1
0x180033738  lea     rbx, [rsi+280h]
0x18003373f  lea     rdx, [rsi+50h]; unsigned __int16 *
0x180033743  mov     rcx, rbx; this
0x180033746  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18003374b  lea     rdx, [rsi+2A0h]
0x180033752  mov     r9, rdi
0x180033755  mov     r8, rbx
0x180033758  lea     rcx, [rsi+10h]
0x18003375c  call    ?CreateFileAsync@?$consume_Windows_Storage_IStorageFolder@UIStorageFolder@Storage@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBW4CreationCollisionOption@Storage@Windows@3@@Z; winrt::impl::consume_Windows_Storage_IStorageFolder<winrt::Windows::Storage::IStorageFolder>::CreateFileAsync(winrt::param::hstring const &,winrt::Windows::Storage::CreationCollisionOption const &)
0x180033761  nop
0x180033762  mov     ecx, [r13+60h]
0x180033766  nop
0x180033767  cmp     ecx, 2
0x18003376a  jnz     short loc_180033796
0x18003376c  lea     rcx, [rsi+2F0h]
0x180033773  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180033778  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18003377b  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180033780  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180033785  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003378c  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180033791  call    _CxxThrowException_0
0x180033796  lea     rcx, [rsi+2A8h]
0x18003379d  mov     [rcx], r14
0x1800337a0  mov     [rsi+2B0h], rax
0x1800337a7  mov     [rsi+2B8h], r14
0x1800337ae  mov     byte ptr [rsi+2C0h], 1
0x1800337b5  mov     eax, 4
0x1800337ba  mov     [r15], ax
0x1800337be  mov     rdx, rsi
0x1800337c1  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAVPrintSupportSessionCommon@@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAVPrintSupportSessionCommon@@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,PrintSupportSessionCommon *>::promise_type>)
0x1800337c6  test    al, al
0x1800337c8  jz      short loc_1800337FE
0x1800337ca  jmp     loc_180033931
0x1800337cf  lea     rcx, [rsi+2A8h]; jumptable 000000018003357D case 5
0x1800337d6  call    ??1?$cancellable_awaiter@Usignal_awaiter@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(void)
0x1800337db  nop
0x1800337dc  lea     rcx, [rsi+2A0h]; this
0x1800337e3  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x1800337e8  nop
0x1800337e9  lea     rcx, [rsi+10h]; this
0x1800337ed  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x1800337f2  nop
0x1800337f3  xor     r14d, r14d
0x1800337f6  jmp     loc_180033910
0x1800337fb  xor     r14d, r14d; jumptable 000000018003357D case 4
0x1800337fe  lea     r8, [rsi+308h]
0x180033805  mov     [r8], r14d
0x180033808  mov     [rsi+310h], r14
0x18003380f  mov     [rsi+318h], r14
0x180033816  mov     edx, [rsi+2BCh]
0x18003381c  mov     [rsp+0F8h+var_94], edx
0x180033820  lea     rcx, [rsi+320h]
0x180033827  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003382c  mov     ecx, [rsi+2B8h]; this
0x180033832  mov     [rsp+0F8h+var_98], ecx
0x180033836  call    ?check_status_canceled@impl@winrt@@YAXW4AsyncStatus@Foundation@Windows@2@@Z; winrt::impl::check_status_canceled(winrt::Windows::Foundation::AsyncStatus)
0x18003383b  lea     rdi, [rsi+2C8h]
0x180033842  mov     rcx, [rsi+2B0h]
0x180033849  mov     [rsp+0F8h+var_A0], rcx
0x18003384e  mov     rdx, rdi
0x180033851  call    ?GetResults@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFile@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::GetResults(void)
0x180033856  nop
0x180033857  lea     rcx, [rsi+2A8h]
0x18003385e  call    ??1?$cancellable_awaiter@Usignal_awaiter@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::signal_awaiter>::~cancellable_awaiter<winrt::impl::signal_awaiter>(void)
0x180033863  nop
0x180033864  lea     rcx, [rsi+2A0h]; this
0x18003386b  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x180033870  mov     rax, [r15+350h]
0x180033877  mov     rcx, [rax+30h]
0x18003387b  lea     rbx, [rsi+328h]
0x180033882  mov     [rbx], r14d
0x180033885  mov     [rsi+330h], r14
0x18003388c  mov     [rsi+338h], r14
0x180033893  mov     rax, [rcx]
0x180033896  mov     rdx, [rdi]
0x180033899  mov     [rsp+0F8h+var_B8], rdx
0x18003389e  mov     rax, [rax+68h]
0x1800338a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338a7  lea     rcx, [rsi+340h]
0x1800338ae  mov     r8, rbx
0x1800338b1  mov     edx, eax
0x1800338b3  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800338b8  mov     rcx, [rsi+2E0h]
0x1800338bf  add     rcx, 68h ; 'h'
0x1800338c3  mov     rdx, rdi
0x1800338c6  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800338cb  nop
0x1800338cc  mov     rcx, rdi; this
0x1800338cf  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x1800338d4  nop
0x1800338d5  lea     rcx, [rsi+10h]; this
0x1800338d9  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x1800338de  nop
0x1800338df  jmp     short loc_1800338EE
0x1800338e1  xor     r14d, r14d
0x1800338e4  mov     r15, [rsp+0F8h+var_B0]
0x1800338e9  mov     rsi, [rsp+0F8h+var_C0]
0x1800338ee  lea     rcx, [rsi+2D0h]
0x1800338f5  lea     rax, [rsi-70h]
0x1800338f9  mov     [rcx], rax
0x1800338fc  xor     eax, eax
0x1800338fe  mov     [r15], ax
0x180033902  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4PrintWorkflowUICompletionStatusPriv@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintWorkflowUICompletionStatusPriv>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x180033907  test    al, al
0x180033909  jz      short loc_180033910
0x18003390b  jmp     short loc_180033931
0x18003390d  xor     r14d, r14d; jumptable 000000018003357D cases -1,1
0x180033910  lea     rcx, [rsi-70h]
0x180033914  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UEAA@XZ; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession *>::promise_type::~promise_type(void)
0x180033919  cmp     [rsi+0Ah], r14w
0x18003391e  jz      short loc_180033931
0x180033920  mov     edx, 3D0h; unsigned __int64
0x180033925  lea     rcx, [rsi-70h]; void *
0x180033929  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003392e  jmp     short loc_180033931
0x180033930  int     3; Trap to Debugger
0x180033931  mov     rcx, [rsp+0F8h+var_38]
0x180033939  xor     rcx, rsp; StackCookie
0x18003393c  call    __security_check_cookie
0x180033941  lea     r11, [rsp+0F8h+var_28]
0x180033949  mov     rbx, [r11+38h]
0x18003394d  mov     rsi, [r11+40h]
0x180033951  mov     rsp, r11
0x180033954  pop     r15
0x180033956  pop     r14
0x180033958  pop     r13
0x18003395a  pop     r12
0x18003395c  pop     rdi
0x18003395d  retn
```
