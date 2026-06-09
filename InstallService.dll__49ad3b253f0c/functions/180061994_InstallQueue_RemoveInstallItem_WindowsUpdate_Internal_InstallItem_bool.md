# InstallQueue::_RemoveInstallItem(WindowsUpdate::Internal::InstallItem *,bool)

- ea: `0x180061994`
- end: `0x180061e36`
- name: `?_RemoveInstallItem@InstallQueue@@AEAAXPEAVInstallItem@Internal@WindowsUpdate@@_N@Z`
- size: `1186`
- prototype: `void __fastcall(InstallQueue *__hidden this, struct WindowsUpdate::Internal::InstallItem *, bool)`
- caller_count: `4`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180052e60`
- `0x18005c338`
- `0x18005ca4c`
- `0x180061994`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180012368`
- `0x1800123f8`
- `0x18001c414`
- `0x18001cce0`
- `0x180022d94`
- `0x180028cd4`
- `0x18002a9e0`
- `0x18004d328`
- `0x18004d8ec`
- `0x18004d978`
- `0x180050a24`
- `0x180058230`
- `0x180061994`
- `0x180062da0`
- `0x1800661a0`
- `0x1800668c4`
- `0x1800d7528`
- `0x180146b44`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180061c2d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180061c2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061a81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180061a81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800619e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800619e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061bf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061bc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061bf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061c39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061df9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800619d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061d81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800619d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061a05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061c1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061cdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180061d81`

## string_xrefs

- `0x180061db7`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x180061a8f`: `InstallQueue::_RemoveInstallItem`
- `0x180061daa`: `InstallQueue::_RemoveInstallItem`
- `0x180061d96`: `Removing Linked Work Item. productId = %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall InstallQueue::_RemoveInstallItem(RTL_SRWLOCK *this, HSTRING *a2, char a3)
{
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v7; // rdx
  PVOID Ptr; // rdi
  __int64 (__fastcall *v9)(PVOID, _QWORD); // rbx
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  const char *v14; // r9
  _QWORD *v15; // rdi
  _QWORD *i; // rbx
  _QWORD *v17; // rdi
  _QWORD *j; // rbx
  HSTRING v19; // rbx
  void (__fastcall *v20)(HSTRING *, HSTRING *); // rbx
  HSTRING v21; // rdi
  int (__fastcall *v22)(HSTRING, HSTRING *); // rbx
  PCWSTR v23; // rax
  int v24; // edi
  const unsigned __int16 *v25; // rsi
  const unsigned __int16 *v26; // rbx
  WindowsUpdate::CommonTelemetry *v27; // rax
  const char **v28; // rdx
  HSTRING *v29; // rdi
  HSTRING *v30; // rsi
  HSTRING *v31; // rbx
  PCWSTR v32; // rax
  unsigned __int16 *v33; // [rsp+38h] [rbp-C8h]
  const char *v34; // [rsp+48h] [rbp-B8h]
  _BYTE v35[8]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v38; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+74h] [rbp-8Ch] BYREF
  HSTRING v41; // [rsp+78h] [rbp-88h] BYREF
  RTL_SRWLOCK **v42; // [rsp+80h] [rbp-80h] BYREF
  const char **v43; // [rsp+88h] [rbp-78h]
  const char **v44; // [rsp+90h] [rbp-70h]
  RTL_SRWLOCK *v45; // [rsp+A0h] [rbp-60h] BYREF
  const char *v46; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  __int64 v48[18]; // [rsp+D0h] [rbp-30h] BYREF

  StringRawBuffer = WindowsGetStringRawBuffer(a2[31], 0);
  DeleteCheckpoint(StringRawBuffer, v7);
  AcquireSRWLockExclusive(this + 24);
  Ptr = this[25].Ptr;
  v9 = *(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)Ptr + 88LL);
  v38 = (HSTRING)WindowsGetStringRawBuffer(a2[31], 0);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v46, &v38);
  v11 = v9(Ptr, *(_QWORD *)(v10 + 24));
  v39 = 0;
  v35[0] = 0;
  if ( (*(int (__fastcall **)(PVOID, HSTRING *, unsigned int *, _BYTE *))(*(_QWORD *)this[26].Ptr + 72LL))(
         this[26].Ptr,
         a2,
         &v39,
         v35) >= 0
    && v35[0] )
  {
    (*(void (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)this[26].Ptr + 96LL))(this[26].Ptr, v39);
  }
  ReleaseSRWLockExclusive(this + 24);
  if ( v11 >= 0 )
  {
    v46 = "InstallQueue::_RemoveInstallItem";
    v47 = 32;
    WindowsUpdate::Internal::InstallItem::LogState(a2, &v46);
    WindowsUpdate::Internal::InstallItem::ShowNotification((WindowsUpdate::Internal::InstallItem *)a2, v12, v13, v14);
    if ( a2[15] || a2[21] )
    {
      v15 = this[41].Ptr;
      for ( i = this[40].Ptr; i != v15; ++i )
        (*(void (__fastcall **)(_QWORD, PVOID, HSTRING *))(*(_QWORD *)*i + 48LL))(*i, this[46].Ptr, a2);
      v46 = (const char *)a2;
      v47 = 0;
      Microsoft::WRL::EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<InstallQueue *,InstallQueue::ProgressEventHandlerArgs>(
        &this[29],
        this,
        &v46);
      v17 = this[44].Ptr;
      for ( j = this[43].Ptr; j != v17; ++j )
        (*(void (__fastcall **)(_QWORD, PVOID, HSTRING *))(*(_QWORD *)*j + 56LL))(*j, this[46].Ptr, a2);
      v46 = (const char *)a2;
      v45 = this;
      string = 0;
      wil::AcquireSRWLockExclusive(&v42, &this[33]);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&string, &this[32]);
      Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&v42);
      v19 = string;
      if ( string )
      {
        v42 = &v45;
        v43 = &v46;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_a25df1447d23ef605e800164dddfeb30_,InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(
          &v42,
          string,
          &this[32]);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v19);
      }
    }
    v38 = 0;
    v20 = (void (__fastcall *)(HSTRING *, HSTRING *))*((_QWORD *)*a2 + 14);
    WindowsDeleteString(0);
    v38 = 0;
    v20(a2, &v38);
    string = 0;
    v21 = a2[11];
    v22 = *(int (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v21 + 160LL);
    WindowsDeleteString(0);
    string = 0;
    if ( v22(v21, &string) >= 0 )
    {
      v23 = WindowsGetStringRawBuffer(string, 0);
      _o_wcstombs(v48, v23, 129);
    }
    WindowsDeleteString(string);
    LODWORD(v37) = 0;
    (*((void (__fastcall **)(HSTRING *, unsigned __int16 **))*a2 + 13))(a2, &v37);
    v40 = 0;
    (*((void (__fastcall **)(HSTRING *, int *))*a2 + 8))(a2, &v40);
    if ( (int)v37 >= 0 && v40 == 5 )
      LODWORD(v37) = -2147467260;
    v41 = 0;
    WindowsDeleteString(0);
    v41 = 0;
    (*(void (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)a2[12] + 72LL))(a2[12], &v41);
    v24 = (int)v37;
    v25 = WindowsGetStringRawBuffer(v41, 0);
    v26 = WindowsGetStringRawBuffer(v38, 0);
    v27 = (WindowsUpdate::CommonTelemetry *)WindowsGetStringRawBuffer(a2[31], 0);
    LODWORD(v33) = v24;
    WindowsUpdate::CommonTelemetry::FulfillmentComplete(
      v27,
      v26,
      v25,
      0,
      0,
      1,
      (unsigned __int8)&dword_18023C12C,
      v33,
      (__int64)v48,
      v34);
    if ( a3 )
    {
      utl::vector<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>,utl::allocator<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>>>::vector<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>,utl::allocator<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>>>(
        &v46,
        a2[11]);
      v42 = (RTL_SRWLOCK **)this;
      v43 = v28;
      v44 = &v46;
      CollectionHelpers::ForeachMapValue_HSTRING_____WindowsUpdate::Internal::IInstallItem__lambda_b9ab0fa2453aa6adf308fc33d6618b8a___(
        this[25].Ptr,
        &v42);
      v29 = (HSTRING *)v46;
      v30 = (HSTRING *)v47;
      while ( v29 != v30 )
      {
        string = *v29;
        v31 = (HSTRING *)string;
        Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&string);
        WindowsUpdate::Internal::InstallItem::RefreshInstallState(v31);
        v32 = WindowsGetStringRawBuffer(v31[31], 0);
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          0x52Cu,
          "InstallQueue::_RemoveInstallItem",
          -1,
          L"Removing Linked Work Item. productId = %s",
          0,
          0,
          v32);
        InstallQueue::_RemoveInstallItem((InstallQueue *)this, (struct WindowsUpdate::Internal::InstallItem *)v31, 0);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&string);
        ++v29;
      }
      utl::vector<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>,utl::allocator<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>>>::_Uninit(&v46);
    }
    WindowsDeleteString(v41);
    v41 = 0;
    WindowsDeleteString(v38);
  }
}

```

## disassembly

```asm
0x180061994  mov     [rsp-8+arg_10], rbx
0x180061999  push    rbp
0x18006199a  push    rsi
0x18006199b  push    rdi
0x18006199c  push    r12
0x18006199e  push    r13
0x1800619a0  push    r14
0x1800619a2  push    r15
0x1800619a4  lea     rbp, [rsp-70h]
0x1800619a9  sub     rsp, 170h
0x1800619b0  mov     rax, cs:__security_cookie
0x1800619b7  xor     rax, rsp
0x1800619ba  mov     [rbp+0A0h+var_40], rax
0x1800619be  mov     r12b, r8b
0x1800619c1  mov     r14, rdx
0x1800619c4  mov     r15, rcx
0x1800619c7  xor     edx, edx; length
0x1800619c9  mov     rcx, [r14+0F8h]; string
0x1800619d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800619d6  mov     rcx, rax; unsigned __int16 *
0x1800619d9  call    ?DeleteCheckpoint@@YAJPEBG@Z; DeleteCheckpoint(ushort const *)
0x1800619de  lea     rsi, [r15+0C0h]
0x1800619e5  mov     rcx, rsi; SRWLock
0x1800619e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800619ee  mov     rdi, [r15+0C8h]
0x1800619f5  mov     rax, [rdi]
0x1800619f8  mov     rbx, [rax+58h]
0x1800619fc  xor     edx, edx; length
0x1800619fe  mov     rcx, [r14+0F8h]; string
0x180061a05  call    cs:__imp_WindowsGetStringRawBuffer
0x180061a0b  mov     [rsp+1A0h+var_138], rax
0x180061a10  lea     rdx, [rsp+1A0h+var_138]
0x180061a15  lea     rcx, [rbp+0A0h+var_F0]
0x180061a19  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180061a1e  mov     rdx, [rax+18h]
0x180061a22  mov     rcx, rdi
0x180061a25  mov     rax, rbx
0x180061a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a2d  mov     ebx, eax
0x180061a2f  xor     r13d, r13d
0x180061a32  mov     [rsp+1A0h+var_130], r13d
0x180061a37  mov     [rsp+1A0h+var_150], r13b
0x180061a3c  mov     rcx, [r15+0D0h]
0x180061a43  mov     rdx, [rcx]
0x180061a46  mov     rax, [rdx+48h]
0x180061a4a  lea     r9, [rsp+1A0h+var_150]
0x180061a4f  lea     r8, [rsp+1A0h+var_130]
0x180061a54  mov     rdx, r14
0x180061a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a5c  test    eax, eax
0x180061a5e  js      short loc_180061A7E
0x180061a60  cmp     [rsp+1A0h+var_150], r13b
0x180061a65  jz      short loc_180061A7E
0x180061a67  mov     rcx, [r15+0D0h]
0x180061a6e  mov     rax, [rcx]
0x180061a71  mov     edx, [rsp+1A0h+var_130]
0x180061a75  mov     rax, [rax+60h]
0x180061a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061a7e  mov     rcx, rsi; SRWLock
0x180061a81  call    cs:__imp_ReleaseSRWLockExclusive
0x180061a87  test    ebx, ebx
0x180061a89  js      loc_180061E0F
0x180061a8f  lea     rax, aInstallqueueRe_2; "InstallQueue::_RemoveInstallItem"
0x180061a96  mov     [rbp+0A0h+var_F0], rax
0x180061a9a  mov     [rbp+0A0h+var_E8], 20h ; ' '
0x180061aa2  lea     rdx, [rbp+0A0h+var_F0]
0x180061aa6  mov     rcx, r14
0x180061aa9  call    ?LogState@InstallItem@Internal@WindowsUpdate@@QEAAXAEBV?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; WindowsUpdate::Internal::InstallItem::LogState(std::string_view const &)
0x180061aae  mov     rcx, r14; this
0x180061ab1  call    ?ShowNotification@InstallItem@Internal@WindowsUpdate@@QEAAJXZ; WindowsUpdate::Internal::InstallItem::ShowNotification(void)
0x180061ab6  cmp     [r14+78h], r13
0x180061aba  jnz     short loc_180061AC9
0x180061abc  cmp     [r14+0A8h], r13
0x180061ac3  jz      loc_180061BB6
0x180061ac9  mov     rdi, [r15+148h]
0x180061ad0  mov     rbx, [r15+140h]
0x180061ad7  jmp     short loc_180061AF6
0x180061ad9  mov     rcx, [rbx]
0x180061adc  mov     rax, [rcx]
0x180061adf  mov     r8, r14
0x180061ae2  mov     rdx, [r15+170h]
0x180061ae9  mov     rax, [rax+30h]
0x180061aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061af2  add     rbx, 8
0x180061af6  cmp     rbx, rdi
0x180061af9  jnz     short loc_180061AD9
0x180061afb  mov     [rbp+0A0h+var_F0], r14
0x180061aff  mov     [rbp+0A0h+var_E8], r13
0x180061b03  lea     rcx, [r15+0E8h]
0x180061b0a  lea     r8, [rbp+0A0h+var_F0]
0x180061b0e  mov     rdx, r15
0x180061b11  call    ??$InvokeAll@PEAVInstallQueue@@UProgressEventHandlerArgs@1@@?$EventSource@UIProgressEventHandler@InstallQueue@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVInstallQueue@@UProgressEventHandlerArgs@3@@Z; Microsoft::WRL::EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<InstallQueue *,InstallQueue::ProgressEventHandlerArgs>(InstallQueue *,InstallQueue::ProgressEventHandlerArgs)
0x180061b16  mov     rdi, [r15+160h]
0x180061b1d  mov     rbx, [r15+158h]
0x180061b24  jmp     short loc_180061B43
0x180061b26  mov     rcx, [rbx]
0x180061b29  mov     rax, [rcx]
0x180061b2c  mov     r8, r14
0x180061b2f  mov     rdx, [r15+170h]
0x180061b36  mov     rax, [rax+38h]
0x180061b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b3f  add     rbx, 8
0x180061b43  cmp     rbx, rdi
0x180061b46  jnz     short loc_180061B26
0x180061b48  lea     rdi, [r15+100h]
0x180061b4f  mov     [rbp+0A0h+var_F0], r14
0x180061b53  mov     [rbp+0A0h+var_100], r15
0x180061b57  mov     [rsp+1A0h+string], r13
0x180061b5c  lea     rdx, [rdi+8]
0x180061b60  lea     rcx, [rbp+0A0h+var_120]
0x180061b64  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180061b69  mov     rdx, rdi
0x180061b6c  lea     rcx, [rsp+1A0h+string]
0x180061b71  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x180061b76  lea     rcx, [rbp+0A0h+var_120]; this
0x180061b7a  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x180061b7f  mov     rbx, [rsp+1A0h+string]
0x180061b84  test    rbx, rbx
0x180061b87  jz      short loc_180061BB6
0x180061b89  lea     rax, [rbp+0A0h+var_100]
0x180061b8d  mov     [rbp+0A0h+var_120], rax
0x180061b91  lea     rax, [rbp+0A0h+var_F0]
0x180061b95  mov     [rbp+0A0h+var_118], rax
0x180061b99  mov     r8, rdi
0x180061b9c  mov     rdx, rbx
0x180061b9f  lea     rcx, [rbp+0A0h+var_120]
0x180061ba3  call    ??$InvokeDelegates@V_lambda_a25df1447d23ef605e800164dddfeb30_@@UIProgressEventHandler@InstallQueue@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_a25df1447d23ef605e800164dddfeb30_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@UIProgressEventHandler@InstallQueue@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_a25df1447d23ef605e800164dddfeb30_,InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_a25df1447d23ef605e800164dddfeb30_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<InstallQueue::IProgressEventHandler,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x180061ba8  test    rbx, rbx
0x180061bab  jz      short loc_180061BB6
0x180061bad  mov     rcx, rbx
0x180061bb0  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180061bb5  nop
0x180061bb6  mov     [rsp+1A0h+var_138], r13
0x180061bbb  mov     rax, [r14]
0x180061bbe  mov     rbx, [rax+70h]
0x180061bc2  xor     ecx, ecx; string
0x180061bc4  call    cs:__imp_WindowsDeleteString
0x180061bca  mov     [rsp+1A0h+var_138], r13
0x180061bcf  lea     rdx, [rsp+1A0h+var_138]
0x180061bd4  mov     rcx, r14
0x180061bd7  mov     rax, rbx
0x180061bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bdf  mov     [rsp+1A0h+string], r13
0x180061be4  mov     rdi, [r14+58h]
0x180061be8  mov     rax, [rdi]
0x180061beb  mov     rbx, [rax+0A0h]
0x180061bf2  xor     ecx, ecx; string
0x180061bf4  call    cs:__imp_WindowsDeleteString
0x180061bfa  mov     [rsp+1A0h+string], r13
0x180061bff  lea     rdx, [rsp+1A0h+string]
0x180061c04  mov     rcx, rdi
0x180061c07  mov     rax, rbx
0x180061c0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c0f  test    eax, eax
0x180061c11  js      short loc_180061C34
0x180061c13  xor     edx, edx; length
0x180061c15  mov     rcx, [rsp+1A0h+string]; string
0x180061c1a  call    cs:__imp_WindowsGetStringRawBuffer
0x180061c20  mov     r8d, 81h
0x180061c26  mov     rdx, rax
0x180061c29  lea     rcx, [rbp+0A0h+var_D0]
0x180061c2d  call    cs:__imp__o_wcstombs
0x180061c33  nop
0x180061c34  mov     rcx, [rsp+1A0h+string]; string
0x180061c39  call    cs:__imp_WindowsDeleteString
0x180061c3f  mov     dword ptr [rsp+1A0h+var_140], r13d
0x180061c44  mov     rax, [r14]
0x180061c47  lea     rdx, [rsp+1A0h+var_140]
0x180061c4c  mov     rcx, r14
0x180061c4f  mov     rax, [rax+68h]
0x180061c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c58  mov     [rsp+1A0h+var_12C], r13d
0x180061c5d  mov     rax, [r14]
0x180061c60  lea     rdx, [rsp+1A0h+var_12C]
0x180061c65  mov     rcx, r14
0x180061c68  mov     rax, [rax+40h]
0x180061c6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c71  cmp     dword ptr [rsp+1A0h+var_140], r13d
0x180061c76  jl      short loc_180061C87
0x180061c78  cmp     [rsp+1A0h+var_12C], 5
0x180061c7d  jnz     short loc_180061C87
0x180061c7f  mov     dword ptr [rsp+1A0h+var_140], 80004004h
0x180061c87  mov     [rsp+1A0h+var_128], r13
0x180061c8c  xor     ecx, ecx; string
0x180061c8e  call    cs:__imp_WindowsDeleteString
0x180061c94  mov     [rsp+1A0h+var_128], r13
0x180061c99  mov     rcx, [r14+60h]
0x180061c9d  mov     rax, [rcx]
0x180061ca0  lea     rdx, [rsp+1A0h+var_128]
0x180061ca5  mov     rax, [rax+48h]
0x180061ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061cae  mov     edi, dword ptr [rsp+1A0h+var_140]
0x180061cb2  xor     edx, edx; length
0x180061cb4  mov     rcx, [rsp+1A0h+var_128]; string
0x180061cb9  call    cs:__imp_WindowsGetStringRawBuffer
0x180061cbf  mov     rsi, rax
0x180061cc2  xor     edx, edx; length
0x180061cc4  mov     rcx, [rsp+1A0h+var_138]; string
0x180061cc9  call    cs:__imp_WindowsGetStringRawBuffer
0x180061ccf  mov     rbx, rax
0x180061cd2  xor     edx, edx; length
0x180061cd4  mov     rcx, [r14+0F8h]; string
0x180061cdb  call    cs:__imp_WindowsGetStringRawBuffer
0x180061ce1  lea     rcx, [rbp+0A0h+var_D0]
0x180061ce5  mov     [rsp+1A0h+var_160], rcx; __int64
0x180061cea  mov     dword ptr [rsp+1A0h+var_168], edi; unsigned __int16 *
0x180061cee  lea     rcx, dword_18023C12C
0x180061cf5  mov     [rsp+1A0h+var_170], rcx; unsigned __int8
0x180061cfa  mov     byte ptr [rsp+1A0h+var_178], 1; char
0x180061cff  mov     qword ptr [rsp+1A0h+var_180], r13; unsigned __int8
0x180061d04  xor     r9d, r9d; unsigned __int16 *
0x180061d07  mov     r8, rsi; unsigned __int16 *
0x180061d0a  mov     rdx, rbx; unsigned __int16 *
0x180061d0d  mov     rcx, rax; this
0x180061d10  call    ?FulfillmentComplete@CommonTelemetry@WindowsUpdate@@YAXPEBG00E_KE0JPEBD@Z; WindowsUpdate::CommonTelemetry::FulfillmentComplete(ushort const *,ushort const *,ushort const *,uchar,unsigned __int64,uchar,ushort const *,long,char const *)
0x180061d15  test    r12b, r12b
0x180061d18  jz      loc_180061DF4
0x180061d1e  mov     rdx, [r14+58h]
0x180061d22  lea     rcx, [rbp+0A0h+var_F0]
0x180061d26  call    ??0?$vector@V?$unique_ptr@UImage@ProductDocument@@U?$default_delete@UImage@ProductDocument@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@UImage@ProductDocument@@U?$default_delete@UImage@ProductDocument@@@wistd@@@wistd@@@utl@@@utl@@QEAA@XZ; utl::vector<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>,utl::allocator<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>>>::vector<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>,utl::allocator<wistd::unique_ptr<ProductDocument::Image,wistd::default_delete<ProductDocument::Image>>>>(void)
0x180061d2b  nop
0x180061d2c  mov     [rbp+0A0h+var_120], r15
0x180061d30  mov     [rbp+0A0h+var_118], rdx
0x180061d34  lea     rax, [rbp+0A0h+var_F0]
0x180061d38  mov     [rbp+0A0h+var_110], rax
0x180061d3c  lea     rdx, [rbp+0A0h+var_120]
0x180061d40  mov     rcx, [r15+0C8h]
0x180061d47  call    CollectionHelpers__ForeachMapValue_HSTRING_____WindowsUpdate__Internal__IInstallItem__lambda_b9ab0fa2453aa6adf308fc33d6618b8a___
0x180061d4c  mov     rdi, [rbp+0A0h+var_F0]
0x180061d50  mov     rsi, [rbp+0A0h+var_E8]
0x180061d54  cmp     rdi, rsi
0x180061d57  jz      loc_180061DEA
0x180061d5d  mov     rbx, [rdi]
0x180061d60  mov     [rsp+1A0h+string], rbx
0x180061d65  lea     rcx, [rsp+1A0h+string]
0x180061d6a  call    ?InternalAddRef@?$ComPtr@VAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(void)
0x180061d6f  nop
0x180061d70  mov     rcx, rbx
0x180061d73  call    ?RefreshInstallState@InstallItem@Internal@WindowsUpdate@@QEAA?AW4InstallState@23@XZ; WindowsUpdate::Internal::InstallItem::RefreshInstallState(void)
0x180061d78  xor     edx, edx; length
0x180061d7a  mov     rcx, [rbx+0F8h]; string
0x180061d81  call    cs:__imp_WindowsGetStringRawBuffer
0x180061d87  mov     [rsp+1A0h+var_160], rax
0x180061d8c  mov     [rsp+1A0h+var_168], r13; unsigned __int16 *
0x180061d91  mov     [rsp+1A0h+var_170], r13; char *
0x180061d96  lea     rax, aRemovingLinked; "Removing Linked Work Item. productId = "...
0x180061d9d  mov     [rsp+1A0h+var_178], rax; unsigned __int16 *
0x180061da2  mov     dword ptr [rsp+1A0h+var_180], 0FFFFFFFFh; int
0x180061daa  lea     r9, aInstallqueueRe_2; "InstallQueue::_RemoveInstallItem"
0x180061db1  mov     r8d, 52Ch; unsigned int
0x180061db7  lea     rdx, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x180061dbe  mov     ecx, 3; unsigned int
0x180061dc3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180061dc8  xor     r8d, r8d; bool
0x180061dcb  mov     rdx, rbx; struct WindowsUpdate::Internal::InstallItem *
0x180061dce  mov     rcx, r15; this
0x180061dd1  call    ?_RemoveInstallItem@InstallQueue@@AEAAXPEAVInstallItem@Internal@WindowsUpdate@@_N@Z; InstallQueue::_RemoveInstallItem(WindowsUpdate::Internal::InstallItem *,bool)
0x180061dd6  nop
0x180061dd7  lea     rcx, [rsp+1A0h+string]
0x180061ddc  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180061de1  add     rdi, 8
0x180061de5  jmp     loc_180061D54
0x180061dea  lea     rcx, [rbp+0A0h+var_F0]
0x180061dee  call    ?_Uninit@?$vector@V?$ComPtr@VAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@WRL@Microsoft@@@utl@@@utl@@AEAAXXZ; utl::vector<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>,utl::allocator<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData>>>::_Uninit(void)
0x180061df3  nop
0x180061df4  mov     rcx, [rsp+1A0h+var_128]; string
0x180061df9  call    cs:__imp_WindowsDeleteString
0x180061dff  mov     [rsp+1A0h+var_128], r13
0x180061e04  mov     rcx, [rsp+1A0h+var_138]; string
0x180061e09  call    cs:__imp_WindowsDeleteString
0x180061e0f  mov     rcx, [rbp+0A0h+var_40]
0x180061e13  xor     rcx, rsp; StackCookie
0x180061e16  call    __security_check_cookie
0x180061e1b  mov     rbx, [rsp+1A0h+arg_10]
0x180061e23  add     rsp, 170h
0x180061e2a  pop     r15
0x180061e2c  pop     r14
0x180061e2e  pop     r13
0x180061e30  pop     r12
0x180061e32  pop     rdi
0x180061e33  pop     rsi
0x180061e34  pop     rbp
0x180061e35  retn
```
