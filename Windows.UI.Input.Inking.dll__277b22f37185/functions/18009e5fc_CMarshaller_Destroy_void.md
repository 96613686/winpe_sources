# CMarshaller::Destroy(void)

- ea: `0x18009e5fc`
- end: `0x18009e7dc`
- name: `?Destroy@CMarshaller@@QEAAXXZ`
- size: `480`
- prototype: `void __fastcall(CMarshaller *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180092c14`

## callees

- `0x180001b9c`
- `0x18000354c`
- `0x1800101bc`
- `0x1800328b0`
- `0x18009a368`
- `0x18009e174`
- `0x18009e5fc`
- `0x18009e838`
- `0x18009ea68`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e64e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e64e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e730`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e730`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e66e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009e66e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e60d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e632`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e60d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e7c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e7c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMarshaller::Destroy(struct _RTL_CRITICAL_SECTION *this)
{
  char DebugInfo; // bl
  char v3; // si
  HANDLE EventW; // r14
  CInkThread *v5; // rcx
  __int64 v6; // rax
  const wchar_t **v7; // rax
  const wchar_t *v8; // rsi
  struct Windows::UI::Core::ICoreDispatcher *v9; // rdi
  int (__fastcall *v10)(struct Windows::UI::Core::ICoreDispatcher *, _QWORD, const wchar_t *, HANDLE *); // rbx
  __int64 v11; // r8
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  _QWORD v15[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  struct Windows::UI::Core::ICoreDispatcher *v17; // [rsp+88h] [rbp+38h] BYREF
  HANDLE v18; // [rsp+90h] [rbp+40h] BYREF
  const wchar_t *v19; // [rsp+98h] [rbp+48h] BYREF

  EnterCriticalSection(this);
  DebugInfo = (char)this[1].DebugInfo;
  LOBYTE(this[1].DebugInfo) = 0;
  v3 = BYTE1(this[1].DebugInfo);
  LeaveCriticalSection(this);
  if ( DebugInfo )
  {
    EnterCriticalSection(&CriticalSection);
    PtrList::CPtrList::Remove((PtrList::CPtrList *)&qword_18015BF58, this);
    LeaveCriticalSection(&CriticalSection);
  }
  else if ( !v3 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    v18 = EventW;
    if ( EventW )
    {
      v17 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      if ( (int)CInkThread::GetInkDispatcher(v5, &v17, (unsigned int *)&v16) >= 0 && v17 )
      {
        v6 = lambda_167226766896c83e38dcd05680733880_::_lambda_167226766896c83e38dcd05680733880_(v15, this, &v18);
        v7 = (const wchar_t **)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::UI::Core::IDispatchedHandler::___void__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::UI::Core::IDispatchedHandler_Microsoft::WRL::FtmBase___lambda_167226766896c83e38dcd05680733880___1___lambda_167226766896c83e38dcd05680733880___(
                                 &v16,
                                 v6);
        v8 = *v7;
        v19 = *v7;
        *v7 = 0;
        if ( v16 )
        {
          v16 = 0;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release();
        }
        v18 = 0;
        v9 = v17;
        v10 = *(int (__fastcall **)(struct Windows::UI::Core::ICoreDispatcher *, _QWORD, const wchar_t *, HANDLE *))(*(_QWORD *)v17 + 64LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        if ( v10(v9, 0, v8, &v18) >= 0
          && WaitForSingleObject(EventW, 0xFFFFFFFF)
          && (unsigned int)dword_18015B128 > 2
          && (unsigned __int8)tlgKeywordOn(&dword_18015B128, 256, v11) )
        {
          v19 = L"Wait failed on CMarshaller::Destroy";
          LODWORD(v16) = -2147418113;
          v15[0] = L"CMarshell::Destroy";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
            v12,
            (unsigned int)word_18013780A,
            v13,
            v14,
            (__int64)v15,
            (__int64)&v16,
            (__int64)&v19);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
        if ( v8 )
          (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v8 + 16LL))(v8);
      }
      CloseHandle(EventW);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    }
  }
}

```

## disassembly

```asm
0x18009e5fc  push    rbp
0x18009e5fe  push    rbx
0x18009e5ff  push    rsi
0x18009e600  push    rdi
0x18009e601  push    r14
0x18009e603  mov     rbp, rsp
0x18009e606  sub     rsp, 50h
0x18009e60a  mov     rdi, rcx
0x18009e60d  call    cs:__imp_EnterCriticalSection
0x18009e613  mov     bl, [rdi+28h]
0x18009e616  mov     byte ptr [rdi+28h], 0
0x18009e61a  mov     sil, [rdi+29h]
0x18009e61e  mov     rcx, rdi; lpCriticalSection
0x18009e621  call    cs:__imp_LeaveCriticalSection
0x18009e627  test    bl, bl
0x18009e629  jz      short loc_18009E659
0x18009e62b  lea     rcx, CriticalSection; lpCriticalSection
0x18009e632  call    cs:__imp_EnterCriticalSection
0x18009e638  mov     rdx, rdi; void *
0x18009e63b  lea     rcx, qword_18015BF58; this
0x18009e642  call    ?Remove@CPtrList@PtrList@@QEAA_NPEAX@Z; PtrList::CPtrList::Remove(void *)
0x18009e647  lea     rcx, CriticalSection; lpCriticalSection
0x18009e64e  call    cs:__imp_LeaveCriticalSection
0x18009e654  jmp     loc_18009E7D1
0x18009e659  test    sil, sil
0x18009e65c  jnz     loc_18009E7D1
0x18009e662  xor     r9d, r9d; lpName
0x18009e665  xor     r8d, r8d; bInitialState
0x18009e668  lea     edx, [r9+1]; bManualReset
0x18009e66c  xor     ecx, ecx; lpEventAttributes
0x18009e66e  call    cs:__imp_CreateEventW
0x18009e674  mov     r14, rax
0x18009e677  mov     [rbp+arg_10], rax
0x18009e67b  test    rax, rax
0x18009e67e  jz      loc_18009E7D1
0x18009e684  mov     [rbp+arg_8], 0
0x18009e68c  lea     rcx, [rbp+arg_8]
0x18009e690  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009e695  lea     r8, [rbp+arg_0]; unsigned int *
0x18009e699  lea     rdx, [rbp+arg_8]; struct Windows::UI::Core::ICoreDispatcher **
0x18009e69d  call    ?GetInkDispatcher@CInkThread@@QEAAJPEAPEAUICoreDispatcher@Core@UI@Windows@@PEAK@Z; CInkThread::GetInkDispatcher(Windows::UI::Core::ICoreDispatcher * *,ulong *)
0x18009e6a2  test    eax, eax
0x18009e6a4  js      loc_18009E7BE
0x18009e6aa  cmp     [rbp+arg_8], 0
0x18009e6af  jz      loc_18009E7BE
0x18009e6b5  lea     r8, [rbp+arg_10]
0x18009e6b9  mov     rdx, rdi
0x18009e6bc  lea     rcx, [rbp+var_10]
0x18009e6c0  call    _lambda_167226766896c83e38dcd05680733880____lambda_167226766896c83e38dcd05680733880_
0x18009e6c5  mov     rdx, rax
0x18009e6c8  lea     rcx, [rbp+arg_0]
0x18009e6cc  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__UI__Core__IDispatchedHandler_____void____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__UI__Core__IDispatchedHandler_Microsoft__WRL__FtmBase___lambda_167226766896c83e38dcd05680733880___1___lambda_167226766896c83e38dcd05680733880___
0x18009e6d1  mov     rsi, [rax]
0x18009e6d4  mov     [rbp+arg_18], rsi
0x18009e6d8  mov     qword ptr [rax], 0
0x18009e6df  mov     rcx, [rbp+arg_0]
0x18009e6e3  test    rcx, rcx
0x18009e6e6  jz      short loc_18009E6F6
0x18009e6e8  mov     [rbp+arg_0], 0
0x18009e6f0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>>::Release(void)
0x18009e6f5  nop
0x18009e6f6  mov     [rbp+arg_10], 0
0x18009e6fe  mov     rdi, [rbp+arg_8]
0x18009e702  mov     rax, [rdi]
0x18009e705  mov     rbx, [rax+40h]
0x18009e709  lea     rcx, [rbp+arg_10]
0x18009e70d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009e712  lea     r9, [rbp+arg_10]
0x18009e716  mov     r8, rsi
0x18009e719  xor     edx, edx
0x18009e71b  mov     rcx, rdi
0x18009e71e  mov     rax, rbx
0x18009e721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e726  test    eax, eax
0x18009e728  js      short loc_18009E79F
0x18009e72a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009e72d  mov     rcx, r14; hHandle
0x18009e730  call    cs:__imp_WaitForSingleObject
0x18009e736  test    eax, eax
0x18009e738  jz      short loc_18009E79F
0x18009e73a  mov     eax, cs:dword_18015B128
0x18009e740  cmp     eax, 2
0x18009e743  jbe     short loc_18009E79F
0x18009e745  mov     edx, 100h
0x18009e74a  lea     rcx, dword_18015B128
0x18009e751  call    _tlgKeywordOn
0x18009e756  test    al, al
0x18009e758  jz      short loc_18009E79F
0x18009e75a  lea     rax, aWaitFailedOnCm; "Wait failed on CMarshaller::Destroy"
0x18009e761  mov     [rbp+arg_18], rax
0x18009e765  mov     dword ptr [rbp+arg_0], 8000FFFFh
0x18009e76c  lea     rax, aCmarshellDestr; "CMarshell::Destroy"
0x18009e773  mov     [rbp+var_10], rax
0x18009e777  lea     rax, [rbp+arg_18]
0x18009e77b  mov     [rsp+50h+var_20], rax
0x18009e780  lea     rax, [rbp+arg_0]
0x18009e784  mov     [rsp+50h+var_28], rax
0x18009e789  lea     rax, [rbp+var_10]
0x18009e78d  mov     [rsp+50h+var_30], rax
0x18009e792  lea     rdx, word_18013780A
0x18009e799  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18009e79e  nop
0x18009e79f  lea     rcx, [rbp+arg_10]
0x18009e7a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009e7a8  nop
0x18009e7a9  test    rsi, rsi
0x18009e7ac  jz      short loc_18009E7BE
0x18009e7ae  mov     rax, [rsi]
0x18009e7b1  mov     rcx, rsi
0x18009e7b4  mov     rax, [rax+10h]
0x18009e7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e7bd  nop
0x18009e7be  mov     rcx, r14; hObject
0x18009e7c1  call    cs:__imp_CloseHandle
0x18009e7c7  nop
0x18009e7c8  lea     rcx, [rbp+arg_8]
0x18009e7cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009e7d1  add     rsp, 50h
0x18009e7d5  pop     r14
0x18009e7d7  pop     rdi
0x18009e7d8  pop     rsi
0x18009e7d9  pop     rbx
0x18009e7da  pop     rbp
0x18009e7db  retn
```
