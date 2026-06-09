# PrintSupportExtensionManager::RemoveSessionOnTimeOutAsync(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x1800474c8`
- end: `0x18004764e`
- name: `?RemoveSessionOnTimeOutAsync@PrintSupportExtensionManager@@AEAA?AUIAsyncAction@Foundation@Windows@winrt@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `390`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004697c`
- `0x180046fc0`
- `0x180047654`

## callees

- `0x180003ca0`
- `0x180003cd0`
- `0x18000495c`
- `0x18000874c`
- `0x1800097ec`
- `0x180012820`
- `0x180012940`
- `0x180046fc0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800475ce`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800475ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall PrintSupportExtensionManager::RemoveSessionOnTimeOutAsync(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rax
  char *v7; // r14
  _QWORD *v8; // rsi
  _QWORD v10[5]; // [rsp+28h] [rbp-70h] BYREF

  v10[1] = a2;
  v10[2] = a3;
  v6 = operator new(0x220u);
  v7 = (char *)(v6 + 14);
  v6[63] = a1;
  *((_OWORD *)v6 + 32) = 0;
  v6[66] = 0;
  v6[67] = 0;
  *((_OWORD *)v6 + 32) = *(_OWORD *)a3;
  *((_OWORD *)v6 + 33) = *(_OWORD *)(a3 + 16);
  *(_QWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 24) = 7;
  *(_WORD *)a3 = 0;
  v6[14] = PrintSupportExtensionManager::RemoveSessionOnTimeOutAsync__ResumeCoro_1;
  *((_DWORD *)v6 + 30) = 65538;
  v8 = v6;
  memset_0(v6, 0, 0x68u);
  v8[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
  v8[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  winrt::impl::module_lock_updater<1>::module_lock_updater<1>((__int64)(v8 + 1));
  v8[1] = 1;
  v8[4] = 0;
  v8[5] = 0;
  *((_BYTE *)v8 + 48) = 0;
  *v8 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  v8[7] = 0;
  v8[8] = 0;
  __ExceptionPtrCreate(v8 + 7);
  v8[9] = 0;
  v8[10] = 0;
  v8[11] = 0;
  *((_DWORD *)v8 + 24) = 0;
  *((_BYTE *)v8 + 100) = 0;
  *v8 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
  *a2 = v8 + 2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(a2);
  v10[0] = 0;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v10);
  v7[384] = 0;
  PrintSupportExtensionManager::RemoveSessionOnTimeOutAsync__ResumeCoro_1(v7);
  std::wstring::_Tidy_deallocate(a3);
  return a2;
}

```

## disassembly

```asm
0x1800474c8  mov     [rsp+arg_0], rbx
0x1800474cd  push    rbp
0x1800474ce  push    rsi
0x1800474cf  push    rdi
0x1800474d0  push    r12
0x1800474d2  push    r13
0x1800474d4  push    r14
0x1800474d6  push    r15
0x1800474d8  sub     rsp, 60h
0x1800474dc  mov     rax, cs:__security_cookie
0x1800474e3  xor     rax, rsp
0x1800474e6  mov     [rsp+98h+var_48], rax
0x1800474eb  mov     r15, r8
0x1800474ee  mov     rbp, rdx
0x1800474f1  mov     rbx, rcx
0x1800474f4  mov     [rsp+98h+var_68], rdx
0x1800474f9  mov     [rsp+98h+var_60], r8
0x1800474fe  mov     r13d, 180h
0x180047504  lea     rcx, [r13+0A0h]; Size
0x18004750b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180047510  mov     [rsp+98h+var_78], rax
0x180047515  lea     r14, [rax+70h]
0x180047519  mov     [rsp+98h+var_78], r14
0x18004751e  mov     [r14+r13+8], rbx
0x180047523  xorps   xmm0, xmm0
0x180047526  movups  xmmword ptr [r14+r13+10h], xmm0
0x18004752c  xor     r12d, r12d
0x18004752f  mov     [r14+r13+20h], r12
0x180047534  mov     [r14+r13+28h], r12
0x180047539  movups  xmm0, xmmword ptr [r15]
0x18004753d  movups  xmmword ptr [r14+r13+10h], xmm0
0x180047543  movups  xmm1, xmmword ptr [r15+10h]
0x180047548  movups  xmmword ptr [r14+r13+20h], xmm1
0x18004754e  mov     [r15+10h], r12
0x180047552  mov     qword ptr [r15+18h], 7
0x18004755a  mov     [r15], r12w
0x18004755e  lea     rax, PrintSupportExtensionManager__RemoveSessionOnTimeOutAsync$_ResumeCoro$1
0x180047565  mov     [r14], rax
0x180047568  mov     dword ptr [r14+8], 10002h
0x180047570  lea     rsi, [r14-70h]
0x180047574  xor     edx, edx; Val
0x180047576  lea     r8d, [r12+68h]; Size
0x18004757b  mov     rcx, rsi; void *
0x18004757e  call    memset_0
0x180047583  lea     rdi, [rsi+10h]
0x180047587  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x18004758e  mov     [rdi], rax
0x180047591  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUPrintSupportSession@implementation@PrintSupport@Printing@Internal@Graphics@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportSession *>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180047598  mov     [rdi+8], rax
0x18004759c  lea     rcx, [rsi+8]
0x1800475a0  call    ??0?$module_lock_updater@$00@impl@winrt@@QEAA@XZ; winrt::impl::module_lock_updater<1>::module_lock_updater<1>(void)
0x1800475a5  mov     qword ptr [rsi+8], 1
0x1800475ad  mov     [rsi+20h], r12
0x1800475b1  mov     [rsi+28h], r12
0x1800475b5  mov     [rsi+30h], r12b
0x1800475b9  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x1800475c0  mov     [rsi], rax
0x1800475c3  lea     rcx, [rsi+38h]
0x1800475c7  mov     [rcx], r12
0x1800475ca  mov     [rcx+8], r12
0x1800475ce  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800475d4  mov     [rsi+48h], r12
0x1800475d8  mov     [rsi+50h], r12
0x1800475dc  mov     [rsi+58h], r12
0x1800475e0  xor     eax, eax
0x1800475e2  mov     [rsi+60h], eax
0x1800475e5  mov     [rsi+64h], r12b
0x1800475e9  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAVPrintSupportExtensionManager@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,PrintSupportExtensionManager *,std::wstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x1800475f0  mov     [rsi], rax
0x1800475f3  mov     [rbp+0], rdi
0x1800475f7  mov     rcx, rbp
0x1800475fa  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800475ff  mov     [rsp+98h+var_70], r12
0x180047604  lea     rcx, [rsp+98h+var_70]; this
0x180047609  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18004760e  nop
0x18004760f  xor     eax, eax
0x180047611  mov     [r14+r13], al
0x180047615  mov     rcx, r14
0x180047618  call    PrintSupportExtensionManager__RemoveSessionOnTimeOutAsync$_ResumeCoro$1
0x18004761d  nop
0x18004761e  mov     rcx, r15
0x180047621  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047626  mov     rax, rbp
0x180047629  mov     rcx, [rsp+98h+var_48]
0x18004762e  xor     rcx, rsp; StackCookie
0x180047631  call    __security_check_cookie
0x180047636  mov     rbx, [rsp+98h+arg_0]
0x18004763e  add     rsp, 60h
0x180047642  pop     r15
0x180047644  pop     r14
0x180047646  pop     r13
0x180047648  pop     r12
0x18004764a  pop     rdi
0x18004764b  pop     rsi
0x18004764c  pop     rbp
0x18004764d  retn
```
