# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync$_ResumeCoro$1

- ea: `0x18003ed20`
- end: `0x18003efac`
- name: `winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync$_ResumeCoro$1`
- size: `652`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003efb4`

## callees

- `0x180003ca0`
- `0x180003cc4`
- `0x180004998`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x1800129a8`
- `0x1800129dc`
- `0x180012b10`
- `0x180012d40`
- `0x1800147fc`
- `0x180014868`
- `0x1800228c0`
- `0x180025138`
- `0x180025360`
- `0x180027618`
- `0x18002762c`
- `0x18002ce9c`
- `0x18003b194`
- `0x18003ed20`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18003ee89`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x18003ee89`

## string_xrefs

- `0x18003ee52`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`
- `0x18003ee9e`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession::ReadPrinterPdcAsync__ResumeCoro_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _WORD *v5; // rsi
  __int64 v6; // rcx
  const struct winrt::impl::slim_source_location *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r13
  const unsigned __int16 *v10; // rax
  int PdcFilePath; // eax
  _QWORD *v12; // r14
  const WCHAR *v13; // rax
  HRESULT v14; // eax
  __int64 *HStringFromStream; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int pstmTemplate; // [rsp+20h] [rbp-98h]
  int pstmTemplatea; // [rsp+20h] [rbp-98h]
  _BYTE pExceptionObject[48]; // [rsp+58h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v5 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_19;
    case 2:
      winrt::implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_strong(
        *(_QWORD *)(a1 + 120),
        a1 + 16);
      *(_BYTE *)(a1 + 24) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 88);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v7);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v5 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v6, a1);
      return;
    case 4:
      *(_OWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 48) = 0;
      *(_QWORD *)(a1 + 56) = 7;
      *(_WORD *)(a1 + 32) = 0;
      v9 = *(_QWORD *)(a1 + 120);
      v10 = winrt::hstring::c_str((winrt::hstring *)(v9 + 88));
      PdcFilePath = GetPdcFilePath((__int64)v10, a1 + 32);
      if ( PdcFilePath < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
          (const char *)(unsigned int)PdcFilePath,
          pstmTemplate);
      v12 = (_QWORD *)(a1 + 64);
      *(_QWORD *)(a1 + 64) = 0;
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 32);
      v14 = SHCreateStreamOnFileEx(v13, 0x40u, 0, 0, 0, (IStream **)(a1 + 64));
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsession.cpp",
          (const char *)(unsigned int)v14,
          pstmTemplatea);
      HStringFromStream = (__int64 *)StreamUtils::GetHStringFromStream(a1 + 72, *v12);
      if ( (__int64 *)(v9 + 552) != HStringFromStream )
      {
        v16 = *HStringFromStream;
        *HStringFromStream = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::attach(v9 + 552, v16);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(a1 + 72);
      if ( *v12 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(a1 + 64);
      std::wstring::_Tidy_deallocate(a1 + 32);
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(
          a1 + 16,
          v17,
          v18,
          v19);
      *(_QWORD *)(a1 + 80) = a1 - 112;
      *v5 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(
                               a1 + 80,
                               v17,
                               v18,
                               v19) )
        goto LABEL_19;
      return;
    case 5:
      v8 = a1 + 16;
      if ( *(_QWORD *)(a1 + 16) )
        winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(
          v8,
          &_ImageBase,
          a3,
          a4);
LABEL_19:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0xF0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18003ed20  mov     r11, rsp
0x18003ed23  mov     [r11+10h], rbx
0x18003ed27  mov     [r11+18h], rsi
0x18003ed2b  mov     [r11+8], rcx
0x18003ed2f  push    rdi
0x18003ed30  push    r12
0x18003ed32  push    r13
0x18003ed34  push    r14
0x18003ed36  push    r15
0x18003ed38  sub     rsp, 90h
0x18003ed3f  mov     rax, cs:__security_cookie
0x18003ed46  xor     rax, rsp
0x18003ed49  mov     [rsp+0B8h+var_30], rax
0x18003ed51  mov     rbx, rcx
0x18003ed54  mov     [rsp+0B8h+var_80], rcx
0x18003ed59  lea     rsi, [rbx+8]
0x18003ed5d  mov     [rsp+0B8h+var_68], rsi
0x18003ed62  movzx   eax, word ptr [rsi]
0x18003ed65  mov     [rsp+0B8h+var_88], ax
0x18003ed6a  inc     ax; switch 7 cases
0x18003ed6d  cmp     ax, 6
0x18003ed71  ja      def_18003ED8C; jumptable 000000018003ED8C default case, case 0
0x18003ed77  movsx   rax, ax
0x18003ed7b  lea     rdx, __ImageBase
0x18003ed82  mov     ecx, ds:(jpt_18003ED8C - 180000000h)[rdx+rax*4]
0x18003ed89  add     rcx, rdx
0x18003ed8c  jmp     rcx; switch jump
0x18003ed8e  xor     edi, edi; jumptable 000000018003ED8C case 3
0x18003ed90  jmp     loc_18003EF42
0x18003ed95  lea     rdx, [rbx+10h]; jumptable 000000018003ED8C case 2
0x18003ed99  mov     rcx, [rsi+70h]
0x18003ed9d  call    ?get_strong@?$implements@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@U1345678@@winrt@@QEAA?AU?$com_ptr@UPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession,winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSession>::get_strong(void)
0x18003eda2  nop
0x18003eda3  xor     edi, edi
0x18003eda5  mov     [rbx+18h], dil
0x18003eda9  mov     eax, [rbx-10h]
0x18003edac  nop
0x18003edad  cmp     eax, 2
0x18003edb0  jnz     short loc_18003EDD9
0x18003edb2  lea     rcx, [rbx+58h]
0x18003edb6  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18003edbb  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18003edbe  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x18003edc3  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18003edc8  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18003edcf  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x18003edd4  call    _CxxThrowException_0
0x18003edd9  mov     eax, 4
0x18003edde  mov     [rsi], ax
0x18003ede1  mov     rdx, rbx
0x18003ede4  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003ede9  jmp     loc_18003EF62
0x18003edee  lea     rcx, [rbx+10h]; jumptable 000000018003ED8C case 5
0x18003edf2  mov     rax, [rcx]
0x18003edf5  mov     [rsp+0B8h+var_70], rax
0x18003edfa  xor     edi, edi
0x18003edfc  test    rax, rax
0x18003edff  jz      short loc_18003EE07
0x18003ee01  call    ?unconditional_release_ref@?$com_ptr@UPrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(void)
0x18003ee06  nop
0x18003ee07  jmp     loc_18003EF42
0x18003ee0c  lea     r15, [rbx+20h]; jumptable 000000018003ED8C case 4
0x18003ee10  xorps   xmm0, xmm0
0x18003ee13  movups  xmmword ptr [r15], xmm0
0x18003ee17  xor     edi, edi
0x18003ee19  mov     [rbx+30h], rdi
0x18003ee1d  mov     qword ptr [rbx+38h], 7
0x18003ee25  xor     eax, eax
0x18003ee27  mov     [r15], ax
0x18003ee2b  mov     r13, [rsi+70h]
0x18003ee2f  lea     rcx, [r13+58h]; this
0x18003ee33  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18003ee38  mov     rcx, rax
0x18003ee3b  mov     rdx, r15
0x18003ee3e  call    ?GetPdcFilePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPdcFilePath(ushort const *,std::wstring &)
0x18003ee43  mov     rcx, [rsp+0B8h]; this
0x18003ee4b  test    eax, eax
0x18003ee4d  jns     short loc_18003EE63
0x18003ee4f  mov     r9d, eax; char *
0x18003ee52  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003ee59  mov     edx, 2EAh; void *
0x18003ee5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ee63  lea     r14, [rbx+40h]
0x18003ee67  mov     [r14], rdi
0x18003ee6a  mov     rcx, r15
0x18003ee6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ee72  mov     rcx, rax; pszFile
0x18003ee75  mov     [rsp+0B8h+ppstm], r14; ppstm
0x18003ee7a  mov     [rsp+0B8h+pstmTemplate], rdi; int
0x18003ee7f  xor     r9d, r9d; fCreate
0x18003ee82  xor     r8d, r8d; dwAttributes
0x18003ee85  lea     edx, [r9+40h]; grfMode
0x18003ee89  call    cs:__imp_SHCreateStreamOnFileEx
0x18003ee8f  mov     rcx, [rsp+0B8h]; this
0x18003ee97  test    eax, eax
0x18003ee99  jns     short loc_18003EEAF
0x18003ee9b  mov     r9d, eax; char *
0x18003ee9e  lea     r8, aOnecoreuapPrin_16; "onecoreuap\\printscan\\print\\workflow"...
0x18003eea5  mov     edx, 2F2h; void *
0x18003eeaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003eeaf  mov     rdx, [r14]
0x18003eeb2  mov     [rsp+0B8h+var_78], rdx
0x18003eeb7  lea     rcx, [rbx+48h]
0x18003eebb  call    ?GetHStringFromStream@StreamUtils@@YA?AUhstring@winrt@@PEAUIStream@@@Z; StreamUtils::GetHStringFromStream(IStream *)
0x18003eec0  lea     rcx, [r13+228h]
0x18003eec7  cmp     rcx, rax
0x18003eeca  jz      short loc_18003EED7
0x18003eecc  mov     rdx, [rax]
0x18003eecf  mov     [rax], rdi
0x18003eed2  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18003eed7  lea     rcx, [rbx+48h]
0x18003eedb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003eee0  nop
0x18003eee1  mov     rax, [r14]
0x18003eee4  mov     [rsp+0B8h+var_78], rax
0x18003eee9  test    rax, rax
0x18003eeec  jz      short loc_18003EEF7
0x18003eeee  mov     rcx, r14
0x18003eef1  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18003eef6  nop
0x18003eef7  mov     rcx, r15
0x18003eefa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003eeff  nop
0x18003ef00  lea     rcx, [rbx+10h]
0x18003ef04  mov     rax, [rcx]
0x18003ef07  mov     [rsp+0B8h+var_70], rax
0x18003ef0c  test    rax, rax
0x18003ef0f  jz      short loc_18003EF17
0x18003ef11  call    ?unconditional_release_ref@?$com_ptr@UPrintSupportExtensionBrokerSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportExtensionBrokerSession>::unconditional_release_ref(void)
0x18003ef16  nop
0x18003ef17  jmp     short loc_18003EF25
0x18003ef19  xor     edi, edi
0x18003ef1b  mov     rsi, [rsp+0B8h+var_68]
0x18003ef20  mov     rbx, [rsp+0B8h+var_80]
0x18003ef25  lea     rcx, [rbx+50h]
0x18003ef29  lea     rax, [rbx-70h]
0x18003ef2d  mov     [rcx], rax
0x18003ef30  xor     eax, eax
0x18003ef32  mov     [rsi], ax
0x18003ef35  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18003ef3a  test    al, al
0x18003ef3c  jz      short loc_18003EF42
0x18003ef3e  jmp     short loc_18003EF62
0x18003ef40  xor     edi, edi; jumptable 000000018003ED8C cases -1,1
0x18003ef42  lea     rcx, [rbx-70h]
0x18003ef46  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUPrintSupportSettingsBroker@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@U?$IAsyncOperation@UPrintSupportSettingsBrokerResult@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSettingsBroker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Internal::Printing::PrintSupport::PrintSupportSettingsBrokerResult>,void>(void)
0x18003ef4b  cmp     [rbx+0Ah], di
0x18003ef4f  jz      short loc_18003EF62
0x18003ef51  mov     edx, 0F0h; unsigned __int64
0x18003ef56  lea     rcx, [rbx-70h]; void *
0x18003ef5a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003ef5f  jmp     short loc_18003EF62
0x18003ef61  int     3; Trap to Debugger
0x18003ef62  mov     rcx, [rsp+0B8h+var_30]
0x18003ef6a  xor     rcx, rsp; StackCookie
0x18003ef6d  call    __security_check_cookie
0x18003ef72  lea     r11, [rsp+0B8h+var_28]
0x18003ef7a  mov     rbx, [r11+38h]
0x18003ef7e  mov     rsi, [r11+40h]
0x18003ef82  mov     rsp, r11
0x18003ef85  pop     r15
0x18003ef87  pop     r14
0x18003ef89  pop     r13
0x18003ef8b  pop     r12
0x18003ef8d  pop     rdi
0x18003ef8e  retn
```
