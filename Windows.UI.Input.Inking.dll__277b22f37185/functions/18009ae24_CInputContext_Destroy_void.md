# CInputContext::Destroy(void)

- ea: `0x18009ae24`
- end: `0x18009b03d`
- name: `?Destroy@CInputContext@@QEAAXXZ`
- size: `537`
- prototype: `void __fastcall(CInputContext *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180092c14`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x1800101bc`
- `0x1800328b0`
- `0x180098350`
- `0x18009839c`
- `0x180099f30`
- `0x18009a368`
- `0x18009ae24`
- `0x18009b148`
- `0x18009d31c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ae57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b01e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ae57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009b01e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009af5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009af5b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aeca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aeca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ae40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009aff5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009afcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009afcc`

## string_xrefs

- `0x18009af85`: `Wait failed on _InkThreadCleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CInputContext::Destroy(CInputContext *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  HANDLE EventW; // r14
  __int64 v4; // rax
  const wchar_t **v5; // rax
  const wchar_t *v6; // r15
  struct Windows::UI::Core::ICoreDispatcher *v7; // rdi
  int (__fastcall *v8)(struct Windows::UI::Core::ICoreDispatcher *, _QWORD, const wchar_t *, __int64 *); // rbx
  __int64 v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  _QWORD v13[2]; // [rsp+40h] [rbp-20h] BYREF
  const wchar_t *v14; // [rsp+50h] [rbp-10h] BYREF
  char v15; // [rsp+A0h] [rbp+40h] BYREF
  HANDLE v16; // [rsp+A8h] [rbp+48h] BYREF
  struct Windows::UI::Core::ICoreDispatcher *v17; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v18; // [rsp+B8h] [rbp+58h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  CObjLifetime::BeginDestroy((CObjLifetime *)&v2[1]);
  if ( v2 )
    LeaveCriticalSection(v2);
  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  if ( (int)CInputContextSharedData::GetDispatcher(v2, &v17) >= 0 )
  {
    if ( v17 )
    {
      v15 = 0;
      if ( (*(int (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, char *))(*(_QWORD *)v17 + 48LL))(
             v17,
             &v15) >= 0 )
      {
        if ( v15 )
        {
          CInputContext::_InkThreadCleanup(this);
        }
        else
        {
          EventW = CreateEventW(0, 1, 0, 0);
          v16 = EventW;
          if ( EventW )
          {
            v4 = lambda_167226766896c83e38dcd05680733880_::_lambda_167226766896c83e38dcd05680733880_(v13, this, &v16);
            v5 = (const wchar_t **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Core::IDispatchedHandler::___void__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::UI::Core::IDispatchedHandler_Microsoft::WRL::FtmBase___lambda_291043a1c994733a2ff90f3ccf33ae17___1___lambda_291043a1c994733a2ff90f3ccf33ae17___(
                                     &v16,
                                     v4);
            v6 = *v5;
            v14 = *v5;
            *v5 = 0;
            if ( v16 )
            {
              v16 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
            }
            v18 = 0;
            v7 = v17;
            v8 = *(int (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, _QWORD, const wchar_t *, __int64 *))(*(_QWORD *)v17 + 64LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
            if ( v8(v7, 0, v6, &v18) >= 0
              && WaitForSingleObject(EventW, 0xFFFFFFFF)
              && (unsigned int)dword_18015B128 > 2
              && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v9) )
            {
              v13[0] = L"Wait failed on _InkThreadCleanup";
              LODWORD(v16) = -2147418113;
              v14 = L"CInputContext::Destroy";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v10,
                (unsigned int)word_18013780A,
                v11,
                v12,
                (__int64)&v14,
                (__int64)&v16,
                (__int64)v13);
            }
            CloseHandle(EventW);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
            if ( v6 )
              (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v6 + 16LL))(v6);
          }
        }
      }
    }
  }
  EnterCriticalSection(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v2[2].LockSemaphore);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v2[2].SpinCount);
  CObjLifetime::EndDestroy((CObjLifetime *)&v2[1]);
  if ( v2 )
    LeaveCriticalSection(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
}

```

## disassembly

```asm
0x18009ae24  push    rbp
0x18009ae26  push    rbx
0x18009ae27  push    rsi
0x18009ae28  push    rdi
0x18009ae29  push    r12
0x18009ae2b  push    r14
0x18009ae2d  push    r15
0x18009ae2f  mov     rbp, rsp
0x18009ae32  sub     rsp, 60h
0x18009ae36  mov     rbx, rcx
0x18009ae39  lea     rsi, [rcx+8]
0x18009ae3d  mov     rcx, rsi; lpCriticalSection
0x18009ae40  call    cs:__imp_EnterCriticalSection
0x18009ae46  lea     rcx, [rsi+28h]; this
0x18009ae4a  call    ?BeginDestroy@CObjLifetime@@QEAAXXZ; CObjLifetime::BeginDestroy(void)
0x18009ae4f  test    rsi, rsi
0x18009ae52  jz      short loc_18009AE5D
0x18009ae54  mov     rcx, rsi; lpCriticalSection
0x18009ae57  call    cs:__imp_LeaveCriticalSection
0x18009ae5d  mov     [rbp+arg_10], 0
0x18009ae65  lea     rcx, [rbp+arg_10]
0x18009ae69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009ae6e  lea     rdx, [rbp+arg_10]; struct Windows::UI::Core::ICoreDispatcher **
0x18009ae72  mov     rcx, rsi; lpCriticalSection
0x18009ae75  call    ?GetDispatcher@CInputContextSharedData@@QEAAJPEAPEAUICoreDispatcher@Core@UI@Windows@@@Z; CInputContextSharedData::GetDispatcher(Windows::UI::Core::ICoreDispatcher * *)
0x18009ae7a  test    eax, eax
0x18009ae7c  js      loc_18009AFF2
0x18009ae82  mov     rcx, [rbp+arg_10]
0x18009ae86  test    rcx, rcx
0x18009ae89  jz      loc_18009AFF2
0x18009ae8f  mov     [rbp+arg_0], 0
0x18009ae93  mov     rax, [rcx]
0x18009ae96  lea     rdx, [rbp+arg_0]
0x18009ae9a  mov     rax, [rax+30h]
0x18009ae9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aea3  test    eax, eax
0x18009aea5  js      loc_18009AFF2
0x18009aeab  cmp     [rbp+arg_0], 0
0x18009aeaf  jz      short loc_18009AEBE
0x18009aeb1  mov     rcx, rbx; this
0x18009aeb4  call    ?_InkThreadCleanup@CInputContext@@IEAAXXZ; CInputContext::_InkThreadCleanup(void)
0x18009aeb9  jmp     loc_18009AFF2
0x18009aebe  xor     r9d, r9d; lpName
0x18009aec1  xor     r8d, r8d; bInitialState
0x18009aec4  lea     edx, [r9+1]; bManualReset
0x18009aec8  xor     ecx, ecx; lpEventAttributes
0x18009aeca  call    cs:__imp_CreateEventW
0x18009aed0  mov     r14, rax
0x18009aed3  mov     [rbp+arg_8], rax
0x18009aed7  test    rax, rax
0x18009aeda  jz      loc_18009AFF2
0x18009aee0  lea     r8, [rbp+arg_8]
0x18009aee4  mov     rdx, rbx
0x18009aee7  lea     rcx, [rbp+var_20]
0x18009aeeb  call    _lambda_167226766896c83e38dcd05680733880____lambda_167226766896c83e38dcd05680733880_
0x18009aef0  mov     rdx, rax
0x18009aef3  lea     rcx, [rbp+arg_8]
0x18009aef7  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Core__IDispatchedHandler_____void____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__UI__Core__IDispatchedHandler_Microsoft__WRL__FtmBase___lambda_291043a1c994733a2ff90f3ccf33ae17___1___lambda_291043a1c994733a2ff90f3ccf33ae17___
0x18009aefc  mov     r15, [rax]
0x18009aeff  mov     [rbp+var_10], r15
0x18009af03  mov     qword ptr [rax], 0
0x18009af0a  mov     rcx, [rbp+arg_8]
0x18009af0e  test    rcx, rcx
0x18009af11  jz      short loc_18009AF21
0x18009af13  mov     [rbp+arg_8], 0
0x18009af1b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18009af20  nop
0x18009af21  mov     [rbp+arg_18], 0
0x18009af29  mov     rdi, [rbp+arg_10]
0x18009af2d  mov     rax, [rdi]
0x18009af30  mov     rbx, [rax+40h]
0x18009af34  lea     rcx, [rbp+arg_18]
0x18009af38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009af3d  lea     r9, [rbp+arg_18]
0x18009af41  mov     r8, r15
0x18009af44  xor     edx, edx
0x18009af46  mov     rcx, rdi
0x18009af49  mov     rax, rbx
0x18009af4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009af51  test    eax, eax
0x18009af53  js      short loc_18009AFC9
0x18009af55  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009af58  mov     rcx, r14; hHandle
0x18009af5b  call    cs:__imp_WaitForSingleObject
0x18009af61  test    eax, eax
0x18009af63  jz      short loc_18009AFC9
0x18009af65  mov     eax, cs:dword_18015B128
0x18009af6b  cmp     eax, 2
0x18009af6e  jbe     short loc_18009AFC9
0x18009af70  mov     edx, 100h
0x18009af75  lea     rcx, dword_18015B128
0x18009af7c  call    _tlgKeywordOn
0x18009af81  test    al, al
0x18009af83  jz      short loc_18009AFC9
0x18009af85  lea     rax, aWaitFailedOnIn; "Wait failed on _InkThreadCleanup"
0x18009af8c  mov     [rbp+var_20], rax
0x18009af90  mov     dword ptr [rbp+arg_8], 8000FFFFh
0x18009af97  lea     rax, aCinputcontextD_1; "CInputContext::Destroy"
0x18009af9e  mov     [rbp+var_10], rax
0x18009afa2  lea     rax, [rbp+var_20]
0x18009afa6  mov     [rsp+60h+var_30], rax
0x18009afab  lea     rax, [rbp+arg_8]
0x18009afaf  mov     [rsp+60h+var_38], rax
0x18009afb4  lea     rax, [rbp+var_10]
0x18009afb8  mov     [rsp+60h+var_40], rax
0x18009afbd  lea     rdx, word_18013780A
0x18009afc4  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009afc9  mov     rcx, r14; hObject
0x18009afcc  call    cs:__imp_CloseHandle
0x18009afd2  nop
0x18009afd3  lea     rcx, [rbp+arg_18]
0x18009afd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009afdc  nop
0x18009afdd  test    r15, r15
0x18009afe0  jz      short loc_18009AFF2
0x18009afe2  mov     rax, [r15]
0x18009afe5  mov     rcx, r15
0x18009afe8  mov     rax, [rax+10h]
0x18009afec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009aff1  nop
0x18009aff2  mov     rcx, rsi; lpCriticalSection
0x18009aff5  call    cs:__imp_EnterCriticalSection
0x18009affb  lea     rcx, [rsi+68h]
0x18009afff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b004  lea     rcx, [rsi+70h]
0x18009b008  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b00d  lea     rcx, [rsi+28h]; this
0x18009b011  call    ?EndDestroy@CObjLifetime@@QEAAXXZ; CObjLifetime::EndDestroy(void)
0x18009b016  test    rsi, rsi
0x18009b019  jz      short loc_18009B025
0x18009b01b  mov     rcx, rsi; lpCriticalSection
0x18009b01e  call    cs:__imp_LeaveCriticalSection
0x18009b024  nop
0x18009b025  lea     rcx, [rbp+arg_10]
0x18009b029  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009b02e  add     rsp, 60h
0x18009b032  pop     r15
0x18009b034  pop     r14
0x18009b036  pop     r12
0x18009b038  pop     rdi
0x18009b039  pop     rsi
0x18009b03a  pop     rbx
0x18009b03b  pop     rbp
0x18009b03c  retn
```
