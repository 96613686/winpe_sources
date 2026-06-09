# CStencilsBranch::AddStencil(Windows::UI::Input::Inking::IInkPresenterStencil *,bool)

- ea: `0x1800e3a0c`
- end: `0x1800e3cfb`
- name: `?AddStencil@CStencilsBranch@@QEAAJPEAUIInkPresenterStencil@Inking@Input@UI@Windows@@_N@Z`
- size: `751`
- prototype: `__int64 __fastcall(CStencilsBranch *__hidden this, struct Windows::UI::Input::Inking::IInkPresenterStencil *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800deeb0`

## callees

- `0x1800062a0`
- `0x1800101bc`
- `0x180019248`
- `0x18001f73c`
- `0x1800328b0`
- `0x18009e838`
- `0x18009f2f8`
- `0x1800d0f8c`
- `0x1800e37e0`
- `0x1800e389c`
- `0x1800e3a0c`
- `0x1800e3ea0`
- `0x1800e403c`
- `0x1800e4190`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3c1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3ccf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3a3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3be7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3a3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e3be7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e3b26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e3b26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e3b3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800e3b3e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e3b4a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e3b4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CStencilsBranch::AddStencil(
        struct _RTL_CRITICAL_SECTION *this,
        struct Windows::UI::Input::Inking::IInkPresenterStencil *a2,
        char a3)
{
  signed int updated; // edi
  unsigned int i; // r15d
  ULONG_PTR SpinCount; // rdi
  __int64 (__fastcall *v9)(ULONG_PTR, _QWORD, struct Windows::UI::Core::ICoreDispatcher **); // rbx
  int v10; // ecx
  CStencilsBranch *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  CInkThread *v14; // rcx
  __int64 v15; // rax
  struct Windows::UI::Core::IDispatchedHandler **v16; // rax
  struct Windows::UI::Core::IDispatchedHandler *v17; // rbx
  struct Windows::Foundation::IAsyncAction **v18; // r8
  struct Windows::UI::Core::ICoreDispatcher *v20; // [rsp+20h] [rbp-50h] BYREF
  UINT32 length[2]; // [rsp+28h] [rbp-48h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v23[2]; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-20h] BYREF

  EnterCriticalSection(this);
  v23[1] = this;
  if ( LOBYTE(this[1].DebugInfo) )
  {
    LODWORD(v23[0]) = 0;
    updated = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD *))(*(_QWORD *)this[1].SpinCount + 56LL))(
                this[1].SpinCount,
                v23);
    if ( updated >= 0 )
    {
      LODWORD(v22) = 0;
      updated = (*(__int64 (__fastcall **)(struct Windows::UI::Input::Inking::IInkPresenterStencil *, __int64 *))(*(_QWORD *)a2 + 48LL))(
                  a2,
                  &v22);
      if ( updated < 0 )
        goto LABEL_11;
      v20 = 0;
      length[0] = 0;
      for ( i = 0; i < LODWORD(v23[0]); ++i )
      {
        SpinCount = this[1].SpinCount;
        v9 = *(__int64 (__fastcall **)(ULONG_PTR, _QWORD, struct Windows::UI::Core::ICoreDispatcher **))(*(_QWORD *)SpinCount + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        updated = v9(SpinCount, i, &v20);
        if ( updated >= 0 )
        {
          updated = (*(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, UINT32 *))(*(_QWORD *)v20 + 48LL))(
                      v20,
                      length);
          if ( length[0] == (_DWORD)v22 )
          {
            updated = -2147483634;
            break;
          }
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      if ( updated >= 0 )
      {
        *(_QWORD *)length = a2;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(length);
        updated = CStencilsBranch::_InitializeStencil((CStencilsBranch *)this, a2);
        if ( updated < 0 )
          goto LABEL_31;
        v20 = 0;
        updated = Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkPresenterStencil>::As<Windows::UI::Input::Inking::IInkPresenterStencilPrivate>(
                    length,
                    &v20);
        if ( updated >= 0 )
        {
          LOBYTE(v12) = a3;
          updated = (*(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, __int64))(*(_QWORD *)v20 + 56LL))(
                      v20,
                      v12);
          if ( updated >= 0 )
            updated = CStencilsBranch::_UpdateInkArea((CStencilsBranch *)this, a2);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
        if ( updated < 0 )
          goto LABEL_31;
        if ( BYTE1(this[1].DebugInfo) )
        {
          v20 = 0;
          v13 = *(_QWORD *)&this[1].LockCount;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
          EnterCriticalSection((LPCRITICAL_SECTION)v13);
          if ( *(_BYTE *)(v13 + 41) )
          {
            updated = *(_BYTE *)(v13 + 40) != 0 ? 0x8000000A : 0;
            if ( !*(_BYTE *)(v13 + 40) )
              updated = CInkThread::GetInkDispatcher(v14, &v20, 0);
          }
          else
          {
            updated = -2147483634;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)v13);
          if ( updated >= 0 )
          {
            v15 = lambda_d25311c38d5ef589a5fabedeb4764253_::_lambda_d25311c38d5ef589a5fabedeb4764253_(
                    &string,
                    this,
                    length);
            v16 = (struct Windows::UI::Core::IDispatchedHandler **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Core::IDispatchedHandler::___void__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::UI::Core::IDispatchedHandler_Microsoft::WRL::FtmBase___lambda_d25311c38d5ef589a5fabedeb4764253___1___lambda_d25311c38d5ef589a5fabedeb4764253___(
                                                                     &v22,
                                                                     v15);
            v17 = *v16;
            v23[0] = *v16;
            *v16 = 0;
            if ( v22 )
            {
              v22 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
            updated = DispatcherHelper::RunOnDispatcherThreadAsync(v20, v17, v18);
            if ( v17 )
              (*(void (__fastcall **)(struct Windows::UI::Core::IDispatchedHandler *))(*(_QWORD *)v17 + 16LL))(v17);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
          if ( updated < 0 )
            goto LABEL_31;
        }
        updated = (*(__int64 (__fastcall **)(ULONG_PTR, struct Windows::UI::Input::Inking::IInkPresenterStencil *))(*(_QWORD *)this[1].SpinCount + 104LL))(
                    this[1].SpinCount,
                    a2);
        if ( updated < 0 )
LABEL_31:
          CStencilsBranch::_DestroyStencil(v11, a2);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(length);
      }
      else
      {
LABEL_11:
        length[0] = 0;
        if ( (int)ULongLongToUInt(0x6Fu, length) < 0 )
          RaiseException(0xC000000D, v10 - 110, 0, 0);
        WindowsCreateStringReference(
          L"Only one ruler and one protractor are allowed for                             the same instance of InkPresenter",
          length[0],
          &hstringHeader,
          &string);
        RoOriginateError((unsigned int)updated, string);
      }
    }
  }
  else
  {
    updated = -2147483634;
  }
  LeaveCriticalSection(this);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800e3a0c  mov     [rsp-38h+arg_18], rbx
0x1800e3a11  push    rbp
0x1800e3a12  push    rsi
0x1800e3a13  push    rdi
0x1800e3a14  push    r12
0x1800e3a16  push    r13
0x1800e3a18  push    r14
0x1800e3a1a  push    r15
0x1800e3a1c  mov     rbp, rsp
0x1800e3a1f  sub     rsp, 70h
0x1800e3a23  mov     rax, cs:__security_cookie
0x1800e3a2a  xor     rax, rsp
0x1800e3a2d  mov     [rbp+var_8], rax
0x1800e3a31  mov     r12b, r8b
0x1800e3a34  mov     r14, rdx
0x1800e3a37  mov     rsi, rcx
0x1800e3a3a  call    cs:__imp_EnterCriticalSection
0x1800e3a40  mov     [rbp+var_30], rsi
0x1800e3a44  xor     r13d, r13d
0x1800e3a47  cmp     [rsi+28h], r13b
0x1800e3a4b  jz      loc_1800E3CC7
0x1800e3a51  mov     dword ptr [rbp+var_38], r13d
0x1800e3a55  mov     rcx, [rsi+48h]
0x1800e3a59  mov     rax, [rcx]
0x1800e3a5c  lea     rdx, [rbp+var_38]
0x1800e3a60  mov     rax, [rax+38h]
0x1800e3a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3a69  mov     edi, eax
0x1800e3a6b  test    eax, eax
0x1800e3a6d  js      loc_1800E3CCC
0x1800e3a73  mov     dword ptr [rbp+var_40], r13d
0x1800e3a77  mov     rax, [r14]
0x1800e3a7a  lea     rdx, [rbp+var_40]
0x1800e3a7e  mov     rcx, r14
0x1800e3a81  mov     rax, [rax+30h]
0x1800e3a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3a8a  mov     edi, eax
0x1800e3a8c  test    eax, eax
0x1800e3a8e  js      short loc_1800E3B02
0x1800e3a90  mov     [rbp+var_50], r13
0x1800e3a94  mov     [rbp+length], r13d
0x1800e3a98  mov     r15d, r13d
0x1800e3a9b  cmp     r15d, dword ptr [rbp+var_38]
0x1800e3a9f  jnb     short loc_1800E3AF5
0x1800e3aa1  mov     rdi, [rsi+48h]
0x1800e3aa5  mov     rax, [rdi]
0x1800e3aa8  mov     rbx, [rax+30h]
0x1800e3aac  lea     rcx, [rbp+var_50]
0x1800e3ab0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3ab5  lea     r8, [rbp+var_50]
0x1800e3ab9  mov     edx, r15d
0x1800e3abc  mov     rcx, rdi
0x1800e3abf  mov     rax, rbx
0x1800e3ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3ac7  mov     edi, eax
0x1800e3ac9  test    eax, eax
0x1800e3acb  js      short loc_1800E3AEB
0x1800e3acd  mov     rcx, [rbp+var_50]
0x1800e3ad1  mov     rax, [rcx]
0x1800e3ad4  lea     rdx, [rbp+length]
0x1800e3ad8  mov     rax, [rax+30h]
0x1800e3adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3ae1  mov     edi, eax
0x1800e3ae3  mov     eax, dword ptr [rbp+var_40]
0x1800e3ae6  cmp     [rbp+length], eax
0x1800e3ae9  jz      short loc_1800E3AF0
0x1800e3aeb  inc     r15d
0x1800e3aee  jmp     short loc_1800E3A9B
0x1800e3af0  mov     edi, 8000000Eh
0x1800e3af5  lea     rcx, [rbp+var_50]
0x1800e3af9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3afe  test    edi, edi
0x1800e3b00  jns     short loc_1800E3B58
0x1800e3b02  mov     [rbp+length], r13d
0x1800e3b06  lea     rdx, [rbp+length]; unsigned int *
0x1800e3b0a  mov     ecx, 6Fh ; 'o'; unsigned __int64
0x1800e3b0f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800e3b14  test    eax, eax
0x1800e3b16  jns     short loc_1800E3B2C
0x1800e3b18  xor     r9d, r9d; lpArguments
0x1800e3b1b  xor     r8d, r8d; nNumberOfArguments
0x1800e3b1e  lea     edx, [rcx-6Eh]; dwExceptionFlags
0x1800e3b21  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800e3b26  call    cs:__imp_RaiseException
0x1800e3b2c  lea     r9, [rbp+string]; string
0x1800e3b30  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800e3b34  mov     edx, [rbp+length]; length
0x1800e3b37  lea     rcx, aOnlyOneRulerAn; "Only one ruler and one protractor are a"...
0x1800e3b3e  call    cs:__imp_WindowsCreateStringReference
0x1800e3b44  mov     rdx, [rbp+string]
0x1800e3b48  mov     ecx, edi
0x1800e3b4a  call    cs:__imp_RoOriginateError
0x1800e3b50  test    edi, edi
0x1800e3b52  js      loc_1800E3CCC
0x1800e3b58  mov     qword ptr [rbp+length], r14
0x1800e3b5c  lea     rcx, [rbp+length]
0x1800e3b60  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800e3b65  nop
0x1800e3b66  mov     rdx, r14; struct Windows::UI::Input::Inking::IInkPresenterStencil *
0x1800e3b69  mov     rcx, rsi; this
0x1800e3b6c  call    ?_InitializeStencil@CStencilsBranch@@IEAAJPEAUIInkPresenterStencil@Inking@Input@UI@Windows@@@Z; CStencilsBranch::_InitializeStencil(Windows::UI::Input::Inking::IInkPresenterStencil *)
0x1800e3b71  mov     edi, eax
0x1800e3b73  test    eax, eax
0x1800e3b75  js      loc_1800E3CB3
0x1800e3b7b  mov     [rbp+var_50], r13
0x1800e3b7f  lea     rdx, [rbp+var_50]
0x1800e3b83  lea     rcx, [rbp+length]
0x1800e3b87  call    ??$As@UIInkPresenterStencilPrivate@Inking@Input@UI@Windows@@@?$ComPtr@UIInkPresenterStencil@Inking@Input@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInkPresenterStencilPrivate@Inking@Input@UI@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkPresenterStencil>::As<Windows::UI::Input::Inking::IInkPresenterStencilPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::Input::Inking::IInkPresenterStencilPrivate>>)
0x1800e3b8c  mov     edi, eax
0x1800e3b8e  test    eax, eax
0x1800e3b90  js      short loc_1800E3BB8
0x1800e3b92  mov     rcx, [rbp+var_50]
0x1800e3b96  mov     rax, [rcx]
0x1800e3b99  mov     dl, r12b
0x1800e3b9c  mov     rax, [rax+38h]
0x1800e3ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3ba5  mov     edi, eax
0x1800e3ba7  test    eax, eax
0x1800e3ba9  js      short loc_1800E3BB8
0x1800e3bab  mov     rdx, r14; struct Windows::UI::Input::Inking::IInkPresenterStencil *
0x1800e3bae  mov     rcx, rsi; this
0x1800e3bb1  call    ?_UpdateInkArea@CStencilsBranch@@IEAAJPEAUIInkPresenterStencil@Inking@Input@UI@Windows@@@Z; CStencilsBranch::_UpdateInkArea(Windows::UI::Input::Inking::IInkPresenterStencil *)
0x1800e3bb6  mov     edi, eax
0x1800e3bb8  lea     rcx, [rbp+var_50]
0x1800e3bbc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3bc1  test    edi, edi
0x1800e3bc3  js      loc_1800E3CB3
0x1800e3bc9  cmp     [rsi+29h], r13b
0x1800e3bcd  jz      loc_1800E3C9A
0x1800e3bd3  mov     [rbp+var_50], r13
0x1800e3bd7  mov     rbx, [rsi+30h]
0x1800e3bdb  lea     rcx, [rbp+var_50]
0x1800e3bdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3be4  mov     rcx, rbx; lpCriticalSection
0x1800e3be7  call    cs:__imp_EnterCriticalSection
0x1800e3bed  cmp     [rbx+29h], r13b
0x1800e3bf1  jz      short loc_1800E3C16
0x1800e3bf3  mov     al, [rbx+28h]
0x1800e3bf6  neg     al
0x1800e3bf8  sbb     edi, edi
0x1800e3bfa  and     edi, 8000000Ah
0x1800e3c00  cmp     [rbx+28h], r13b
0x1800e3c04  jnz     short loc_1800E3C1B
0x1800e3c06  xor     r8d, r8d; unsigned int *
0x1800e3c09  lea     rdx, [rbp+var_50]; struct Windows::UI::Core::ICoreDispatcher **
0x1800e3c0d  call    ?GetInkDispatcher@CInkThread@@QEAAJPEAPEAUICoreDispatcher@Core@UI@Windows@@PEAK@Z; CInkThread::GetInkDispatcher(Windows::UI::Core::ICoreDispatcher * *,ulong *)
0x1800e3c12  mov     edi, eax
0x1800e3c14  jmp     short loc_1800E3C1B
0x1800e3c16  mov     edi, 8000000Eh
0x1800e3c1b  mov     rcx, rbx; lpCriticalSection
0x1800e3c1e  call    cs:__imp_LeaveCriticalSection
0x1800e3c24  test    edi, edi
0x1800e3c26  js      short loc_1800E3C8D
0x1800e3c28  lea     r8, [rbp+length]
0x1800e3c2c  mov     rdx, rsi
0x1800e3c2f  lea     rcx, [rbp+string]
0x1800e3c33  call    _lambda_d25311c38d5ef589a5fabedeb4764253____lambda_d25311c38d5ef589a5fabedeb4764253_
0x1800e3c38  mov     rdx, rax
0x1800e3c3b  lea     rcx, [rbp+var_40]
0x1800e3c3f  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Core__IDispatchedHandler_____void____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__UI__Core__IDispatchedHandler_Microsoft__WRL__FtmBase___lambda_d25311c38d5ef589a5fabedeb4764253___1___lambda_d25311c38d5ef589a5fabedeb4764253___
0x1800e3c44  mov     rbx, [rax]
0x1800e3c47  mov     [rbp+var_38], rbx
0x1800e3c4b  mov     [rax], r13
0x1800e3c4e  mov     rcx, [rbp+var_40]
0x1800e3c52  test    rcx, rcx
0x1800e3c55  jz      short loc_1800E3C61
0x1800e3c57  mov     [rbp+var_40], r13
0x1800e3c5b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x1800e3c60  nop
0x1800e3c61  lea     rcx, [rbp+hstringHeader]
0x1800e3c65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3c6a  mov     rdx, rbx; struct Windows::UI::Core::IDispatchedHandler *
0x1800e3c6d  mov     rcx, [rbp+var_50]; struct Windows::UI::Core::ICoreDispatcher *
0x1800e3c71  call    ?RunOnDispatcherThreadAsync@DispatcherHelper@@SAJPEAUICoreDispatcher@Core@UI@Windows@@PEAUIDispatchedHandler@345@PEAPEAUIAsyncAction@Foundation@5@@Z; DispatcherHelper::RunOnDispatcherThreadAsync(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IDispatchedHandler *,Windows::Foundation::IAsyncAction * *)
0x1800e3c76  mov     edi, eax
0x1800e3c78  test    rbx, rbx
0x1800e3c7b  jz      short loc_1800E3C8D
0x1800e3c7d  mov     rax, [rbx]
0x1800e3c80  mov     rcx, rbx
0x1800e3c83  mov     rax, [rax+10h]
0x1800e3c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3c8c  nop
0x1800e3c8d  lea     rcx, [rbp+var_50]
0x1800e3c91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3c96  test    edi, edi
0x1800e3c98  js      short loc_1800E3CB3
0x1800e3c9a  mov     rcx, [rsi+48h]
0x1800e3c9e  mov     rax, [rcx]
0x1800e3ca1  mov     rdx, r14
0x1800e3ca4  mov     rax, [rax+68h]
0x1800e3ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3cad  mov     edi, eax
0x1800e3caf  test    eax, eax
0x1800e3cb1  jns     short loc_1800E3CBC
0x1800e3cb3  mov     rdx, r14; struct Windows::UI::Input::Inking::IInkPresenterStencil *
0x1800e3cb6  call    ?_DestroyStencil@CStencilsBranch@@IEAAJPEAUIInkPresenterStencil@Inking@Input@UI@Windows@@@Z; CStencilsBranch::_DestroyStencil(Windows::UI::Input::Inking::IInkPresenterStencil *)
0x1800e3cbb  nop
0x1800e3cbc  lea     rcx, [rbp+length]
0x1800e3cc0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3cc5  jmp     short loc_1800E3CCC
0x1800e3cc7  mov     edi, 8000000Eh
0x1800e3ccc  mov     rcx, rsi; lpCriticalSection
0x1800e3ccf  call    cs:__imp_LeaveCriticalSection
0x1800e3cd5  mov     eax, edi
0x1800e3cd7  mov     rcx, [rbp+var_8]
0x1800e3cdb  xor     rcx, rsp; StackCookie
0x1800e3cde  call    __security_check_cookie
0x1800e3ce3  mov     rbx, [rsp+70h+arg_18]
0x1800e3ceb  add     rsp, 70h
0x1800e3cef  pop     r15
0x1800e3cf1  pop     r14
0x1800e3cf3  pop     r13
0x1800e3cf5  pop     r12
0x1800e3cf7  pop     rdi
0x1800e3cf8  pop     rsi
0x1800e3cf9  pop     rbp
0x1800e3cfa  retn
```
