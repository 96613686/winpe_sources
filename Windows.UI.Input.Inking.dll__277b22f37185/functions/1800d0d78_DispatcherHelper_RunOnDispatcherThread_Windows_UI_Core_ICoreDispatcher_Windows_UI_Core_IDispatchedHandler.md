# DispatcherHelper::RunOnDispatcherThread(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IDispatchedHandler *)

- ea: `0x1800d0d78`
- end: `0x1800d0f84`
- name: `?RunOnDispatcherThread@DispatcherHelper@@SAJPEAUICoreDispatcher@Core@UI@Windows@@PEAUIDispatchedHandler@345@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct Windows::UI::Core::ICoreDispatcher *, struct Windows::UI::Core::IDispatchedHandler *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009df54`
- `0x1800bf60c`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x1800101bc`
- `0x180019248`
- `0x1800328b0`
- `0x1800d0bdc`
- `0x1800d0d78`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d0eb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800d0eb3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d0e00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800d0e00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0f2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d0f2e`

## string_xrefs

- `0x1800d0eef`: `DispatcherHelper::RunOnDispatcherThread`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DispatcherHelper::RunOnDispatcherThread(
        struct Windows::UI::Core::ICoreDispatcher *a1,
        struct Windows::UI::Core::IDispatchedHandler *a2)
{
  int v4; // edi
  HANDLE EventW; // r14
  const wchar_t **v6; // rax
  const wchar_t *v7; // rbx
  __int64 (__fastcall *v8)(struct Windows::UI::Core::ICoreDispatcher *, __int64, const wchar_t *, __int64 *); // rdi
  __int64 v9; // r8
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  struct Windows::UI::Core::ICoreDispatcher *v14; // [rsp+40h] [rbp-19h] BYREF
  struct Windows::UI::Core::IDispatchedHandler *v15; // [rsp+48h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+50h] [rbp-9h] BYREF
  const wchar_t *v17; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v18[2]; // [rsp+60h] [rbp+7h] BYREF
  struct Windows::UI::Core::IDispatchedHandler *v19; // [rsp+70h] [rbp+17h] BYREF
  char v20; // [rsp+C0h] [rbp+67h] BYREF
  int v21; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v22; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v23; // [rsp+D8h] [rbp+7Fh] BYREF

  v20 = 0;
  v14 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v14);
  v15 = a2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v15);
  v23 = 0;
  v4 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, char *))(*(_QWORD *)a1 + 48LL))(a1, &v20);
  if ( v4 >= 0 )
  {
    if ( v20 )
    {
      v4 = (*(__int64 (__fastcall **)(struct Windows::UI::Core::IDispatchedHandler *))(*(_QWORD *)a2 + 24LL))(a2);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( EventW )
      {
        v21 = -2147467259;
        v18[0] = &v21;
        v18[1] = EventW;
        v19 = a2;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(&v19);
        v6 = (const wchar_t **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Core::IDispatchedHandler::___void__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::UI::Core::IDispatchedHandler_Microsoft::WRL::FtmBase___lambda_062062da4727761205bb5a11077e0aad___1___lambda_062062da4727761205bb5a11077e0aad___(
                                 &v22,
                                 v18);
        v7 = *v6;
        v17 = *v6;
        *v6 = 0;
        if ( v22 )
        {
          v22 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
        }
        if ( v19 )
          (*(void (__fastcall **)(struct Windows::UI::Core::IDispatchedHandler *))(*(_QWORD *)v19 + 16LL))(v19);
        v8 = *(__int64 (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, __int64, const wchar_t *, __int64 *))(*(_QWORD *)a1 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        v4 = v8(a1, 1, v7, &v23);
        if ( v4 >= 0 )
        {
          if ( WaitForSingleObject(EventW, 0x3E8u) )
          {
            if ( (unsigned int)dword_18015B128 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v9) )
            {
              v16 = L"Wait failed";
              LODWORD(v22) = -2147418113;
              v17 = L"DispatcherHelper::RunOnDispatcherThread";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                v10,
                (unsigned int)word_18013780A,
                v11,
                v12,
                (__int64)&v17,
                (__int64)&v22,
                (__int64)&v16);
            }
            v4 = -2147418113;
          }
          else
          {
            v4 = v21;
          }
        }
        CloseHandle(EventW);
        if ( v7 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  if ( a2 )
    (*(void (__fastcall **)(struct Windows::UI::Core::IDispatchedHandler *))(*(_QWORD *)a2 + 16LL))(a2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800d0d78  push    rbp
0x1800d0d7a  push    rbx
0x1800d0d7b  push    rsi
0x1800d0d7c  push    rdi
0x1800d0d7d  push    r14
0x1800d0d7f  push    r15
0x1800d0d81  lea     rbp, [rsp-2Fh]
0x1800d0d86  sub     rsp, 88h
0x1800d0d8d  mov     rsi, rdx
0x1800d0d90  mov     r15, rcx
0x1800d0d93  mov     [rbp+57h+arg_0], 0
0x1800d0d97  mov     [rbp+57h+var_70], rcx
0x1800d0d9b  lea     rcx, [rbp+57h+var_70]
0x1800d0d9f  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800d0da4  nop
0x1800d0da5  mov     [rbp+57h+var_68], rsi
0x1800d0da9  lea     rcx, [rbp+57h+var_68]
0x1800d0dad  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800d0db2  nop
0x1800d0db3  mov     [rbp+57h+arg_18], 0
0x1800d0dbb  mov     rax, [r15]
0x1800d0dbe  lea     rdx, [rbp+57h+arg_0]
0x1800d0dc2  mov     rcx, r15
0x1800d0dc5  mov     rax, [rax+30h]
0x1800d0dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0dce  mov     edi, eax
0x1800d0dd0  test    eax, eax
0x1800d0dd2  js      loc_1800D0F4A
0x1800d0dd8  cmp     [rbp+57h+arg_0], 0
0x1800d0ddc  jz      short loc_1800D0DF4
0x1800d0dde  mov     rax, [rsi]
0x1800d0de1  mov     rcx, rsi
0x1800d0de4  mov     rax, [rax+18h]
0x1800d0de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ded  mov     edi, eax
0x1800d0def  jmp     loc_1800D0F4A
0x1800d0df4  xor     r9d, r9d; lpName
0x1800d0df7  xor     r8d, r8d; bInitialState
0x1800d0dfa  lea     edx, [r9+1]; bManualReset
0x1800d0dfe  xor     ecx, ecx; lpEventAttributes
0x1800d0e00  call    cs:__imp_CreateEventW
0x1800d0e06  mov     r14, rax
0x1800d0e09  test    rax, rax
0x1800d0e0c  jz      loc_1800D0F4A
0x1800d0e12  mov     [rbp+57h+arg_8], 80004005h
0x1800d0e19  lea     rax, [rbp+57h+arg_8]
0x1800d0e1d  mov     [rbp+57h+var_50], rax
0x1800d0e21  mov     [rbp+57h+var_48], r14
0x1800d0e25  mov     [rbp+57h+var_40], rsi
0x1800d0e29  lea     rcx, [rbp+57h+var_40]
0x1800d0e2d  call    ?InternalAddRef@?$ComPtr@U?$IMapView@PEAVInkStroke@Inking@Input@UI@Windows@@UEventRegistrationToken@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMapView<Windows::UI::Input::Inking::InkStroke *,EventRegistrationToken>>::InternalAddRef(void)
0x1800d0e32  lea     rdx, [rbp+57h+var_50]
0x1800d0e36  lea     rcx, [rbp+57h+arg_10]
0x1800d0e3a  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Core__IDispatchedHandler_____void____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__UI__Core__IDispatchedHandler_Microsoft__WRL__FtmBase___lambda_062062da4727761205bb5a11077e0aad___1___lambda_062062da4727761205bb5a11077e0aad___
0x1800d0e3f  mov     rbx, [rax]
0x1800d0e42  mov     [rbp+57h+var_58], rbx
0x1800d0e46  mov     qword ptr [rax], 0
0x1800d0e4d  mov     rcx, [rbp+57h+arg_10]
0x1800d0e51  test    rcx, rcx
0x1800d0e54  jz      short loc_1800D0E64
0x1800d0e56  mov     [rbp+57h+arg_10], 0
0x1800d0e5e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x1800d0e63  nop
0x1800d0e64  mov     rcx, [rbp+57h+var_40]
0x1800d0e68  test    rcx, rcx
0x1800d0e6b  jz      short loc_1800D0E7A
0x1800d0e6d  mov     rax, [rcx]
0x1800d0e70  mov     rax, [rax+10h]
0x1800d0e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0e79  nop
0x1800d0e7a  mov     rax, [r15]
0x1800d0e7d  mov     rdi, [rax+40h]
0x1800d0e81  lea     rcx, [rbp+57h+arg_18]
0x1800d0e85  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0e8a  lea     r9, [rbp+57h+arg_18]
0x1800d0e8e  mov     r8, rbx
0x1800d0e91  mov     edx, 1
0x1800d0e96  mov     rcx, r15
0x1800d0e99  mov     rax, rdi
0x1800d0e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0ea1  mov     edi, eax
0x1800d0ea3  test    eax, eax
0x1800d0ea5  js      loc_1800D0F2B
0x1800d0eab  mov     edx, 3E8h; dwMilliseconds
0x1800d0eb0  mov     rcx, r14; hHandle
0x1800d0eb3  call    cs:__imp_WaitForSingleObject
0x1800d0eb9  test    eax, eax
0x1800d0ebb  jz      short loc_1800D0F28
0x1800d0ebd  mov     eax, cs:dword_18015B128
0x1800d0ec3  cmp     eax, 2
0x1800d0ec6  jbe     short loc_1800D0F21
0x1800d0ec8  mov     edx, 100h
0x1800d0ecd  lea     rcx, dword_18015B128
0x1800d0ed4  call    _tlgKeywordOn
0x1800d0ed9  test    al, al
0x1800d0edb  jz      short loc_1800D0F21
0x1800d0edd  lea     rax, aWaitFailed; "Wait failed"
0x1800d0ee4  mov     [rbp+57h+var_60], rax
0x1800d0ee8  mov     dword ptr [rbp+57h+arg_10], 8000FFFFh
0x1800d0eef  lea     rax, aDispatcherhelp; "DispatcherHelper::RunOnDispatcherThread"
0x1800d0ef6  mov     [rbp+57h+var_58], rax
0x1800d0efa  lea     rax, [rbp+57h+var_60]
0x1800d0efe  mov     [rsp+0B0h+var_80], rax
0x1800d0f03  lea     rax, [rbp+57h+arg_10]
0x1800d0f07  mov     [rsp+0B0h+var_88], rax
0x1800d0f0c  lea     rax, [rbp+57h+var_58]
0x1800d0f10  mov     [rsp+0B0h+var_90], rax
0x1800d0f15  lea     rdx, word_18013780A
0x1800d0f1c  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800d0f21  mov     edi, 8000FFFFh
0x1800d0f26  jmp     short loc_1800D0F2B
0x1800d0f28  mov     edi, [rbp+57h+arg_8]
0x1800d0f2b  mov     rcx, r14; hObject
0x1800d0f2e  call    cs:__imp_CloseHandle
0x1800d0f34  nop
0x1800d0f35  test    rbx, rbx
0x1800d0f38  jz      short loc_1800D0F4A
0x1800d0f3a  mov     rax, [rbx]
0x1800d0f3d  mov     rcx, rbx
0x1800d0f40  mov     rax, [rax+10h]
0x1800d0f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0f49  nop
0x1800d0f4a  lea     rcx, [rbp+57h+arg_18]
0x1800d0f4e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0f53  nop
0x1800d0f54  test    rsi, rsi
0x1800d0f57  jz      short loc_1800D0F69
0x1800d0f59  mov     rax, [rsi]
0x1800d0f5c  mov     rcx, rsi
0x1800d0f5f  mov     rax, [rax+10h]
0x1800d0f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0f68  nop
0x1800d0f69  lea     rcx, [rbp+57h+var_70]
0x1800d0f6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800d0f72  mov     eax, edi
0x1800d0f74  add     rsp, 88h
0x1800d0f7b  pop     r15
0x1800d0f7d  pop     r14
0x1800d0f7f  pop     rdi
0x1800d0f80  pop     rsi
0x1800d0f81  pop     rbx
0x1800d0f82  pop     rbp
0x1800d0f83  retn
```
