# UXFrame::HandleValueSetEncodedCommandsFromContent(winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x1800444f4`
- end: `0x180044635`
- name: `?HandleValueSetEncodedCommandsFromContent@UXFrame@@AEAAXAEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `321`
- prototype: `void __fastcall(UXFrame *__hidden this, const struct winrt::Windows::Foundation::Collections::ValueSet *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800487e0`

## callees

- `0x18000436c`
- `0x1800043f4`
- `0x1800049ac`
- `0x180006698`
- `0x1800089c0`
- `0x18000d810`
- `0x180013460`
- `0x180013bc0`
- `0x180020cdc`
- `0x18003d090`
- `0x1800444f4`
- `0x180044e9c`
- `0x180049bf8`
- `0x18005a010`

## string_xrefs

- `0x1800445a3`: `AccessibleName`
- `0x1800445c3`: `AccessibleName`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UXFrame::HandleValueSetEncodedCommandsFromContent(
        UXFrame *this,
        const struct winrt::Windows::Foundation::Collections::ValueSet *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  UXFrame *v7; // rax
  __int64 v8; // rdx
  _BYTE v9[32]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  int v11; // [rsp+58h] [rbp+18h] BYREF
  char v12; // [rsp+5Ch] [rbp+1Ch]

  v10 = *(_QWORD *)a2;
  winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v10);
  FlowEndpointBase::InvokeMessage((__int64)this + 312, 2u, (winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v10);
  v4 = *((_QWORD *)this + 26);
  if ( v4 )
    (*(void (__fastcall **)(__int64, const struct winrt::Windows::Foundation::Collections::ValueSet *))(*(_QWORD *)v4 + 56LL))(
      v4,
      a2);
  v5 = *((_QWORD *)this + 24);
  if ( v5 )
    (*(void (__fastcall **)(__int64, const struct winrt::Windows::Foundation::Collections::ValueSet *))(*(_QWORD *)v5 + 72LL))(
      v5,
      a2);
  winrt::hstring::hstring((winrt::hstring *)&v10, L"RequestLifecycleEvent");
  try_get_enum_from_valueset<enum UXFrameHelpers::PropertyKeys::LifecycleEventName>(&v11, &v10, a2);
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v10);
  if ( v12 )
    UXFrame::RequestLifecycleEvent(this, v11);
  winrt::param::hstring::hstring((winrt::param::hstring *)v9, L"AccessibleName");
  if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(
                          a2,
                          v9) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v9, L"AccessibleName");
    v6 = winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(
           a2,
           &v10,
           v9);
    v7 = (UXFrame *)winrt::unbox_value<winrt::hstring>(&v11, v6);
    if ( (UXFrame *)((char *)this + 288) != v7 )
    {
      v8 = *(_QWORD *)v7;
      *(_QWORD *)v7 = 0;
      winrt::handle_type<winrt::impl::hstring_traits>::attach((char *)this + 288, v8);
    }
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v11);
    if ( v10 )
      winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(&v10);
  }
}

```

## disassembly

```asm
0x1800444f4  mov     [rsp-8+arg_10], rbx
0x1800444f9  mov     [rsp-8+arg_18], rdi
0x1800444fe  push    rbp
0x1800444ff  mov     rbp, rsp
0x180044502  sub     rsp, 40h
0x180044506  mov     rbx, rdx
0x180044509  mov     rdi, rcx
0x18004450c  mov     rax, [rdx]
0x18004450f  mov     [rbp+arg_0], rax
0x180044513  lea     rcx, [rbp+arg_0]; this
0x180044517  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18004451c  lea     rcx, [rdi+138h]
0x180044523  lea     r8, [rbp+arg_0]
0x180044527  mov     edx, 2
0x18004452c  call    ?InvokeMessage@FlowEndpointBase@@QEAAXW4StandardMessage@@UValueSet@Collections@Foundation@Windows@winrt@@@Z; FlowEndpointBase::InvokeMessage(StandardMessage,winrt::Windows::Foundation::Collections::ValueSet)
0x180044531  mov     rcx, [rdi+0D0h]
0x180044538  test    rcx, rcx
0x18004453b  jz      short loc_18004454C
0x18004453d  mov     rax, [rcx]
0x180044540  mov     rdx, rbx
0x180044543  mov     rax, [rax+38h]
0x180044547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004454c  mov     rcx, [rdi+0C0h]
0x180044553  test    rcx, rcx
0x180044556  jz      short loc_180044567
0x180044558  mov     rax, [rcx]
0x18004455b  mov     rdx, rbx
0x18004455e  mov     rax, [rax+48h]
0x180044562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044567  lea     rdx, aRequestlifecyc; "RequestLifecycleEvent"
0x18004456e  lea     rcx, [rbp+arg_0]; this
0x180044572  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x180044577  nop
0x180044578  mov     r8, rbx
0x18004457b  lea     rdx, [rbp+arg_0]
0x18004457f  lea     rcx, [rbp+arg_8]
0x180044583  call    ??$try_get_enum_from_valueset@W4LifecycleEventName@PropertyKeys@UXFrameHelpers@@@@YA?AV?$optional@W4LifecycleEventName@PropertyKeys@UXFrameHelpers@@@std@@AEBUhstring@winrt@@AEBUValueSet@Collections@Foundation@Windows@3@@Z; try_get_enum_from_valueset<UXFrameHelpers::PropertyKeys::LifecycleEventName>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &)
0x180044588  nop
0x180044589  lea     rcx, [rbp+arg_0]
0x18004458d  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180044592  cmp     [rbp+arg_C], 0
0x180044596  jz      short loc_1800445A3
0x180044598  mov     edx, [rbp+arg_8]
0x18004459b  mov     rcx, rdi
0x18004459e  call    ?RequestLifecycleEvent@UXFrame@@AEAAXW4LifecycleEventName@PropertyKeys@UXFrameHelpers@@@Z; UXFrame::RequestLifecycleEvent(UXFrameHelpers::PropertyKeys::LifecycleEventName)
0x1800445a3  lea     rdx, aAccessiblename; "AccessibleName"
0x1800445aa  lea     rcx, [rbp+var_20]; this
0x1800445ae  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800445b3  lea     rdx, [rbp+var_20]
0x1800445b7  mov     rcx, rbx
0x1800445ba  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::HasKey(winrt::param::hstring const &)
0x1800445bf  test    al, al
0x1800445c1  jz      short loc_180044625
0x1800445c3  lea     rdx, aAccessiblename; "AccessibleName"
0x1800445ca  lea     rcx, [rbp+var_20]; this
0x1800445ce  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800445d3  lea     r8, [rbp+var_20]
0x1800445d7  lea     rdx, [rbp+arg_0]
0x1800445db  mov     rcx, rbx
0x1800445de  call    ?Lookup@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Lookup(winrt::param::hstring const &)
0x1800445e3  nop
0x1800445e4  mov     rdx, rax
0x1800445e7  lea     rcx, [rbp+arg_8]
0x1800445eb  call    ??$unbox_value@Uhstring@winrt@@@winrt@@YA?AUhstring@0@AEBUIInspectable@Foundation@Windows@0@@Z; winrt::unbox_value<winrt::hstring>(winrt::Windows::Foundation::IInspectable const &)
0x1800445f0  lea     rcx, [rdi+120h]
0x1800445f7  cmp     rcx, rax
0x1800445fa  jz      short loc_18004460B
0x1800445fc  mov     rdx, [rax]
0x1800445ff  mov     qword ptr [rax], 0
0x180044606  call    ?attach@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXPEAUhstring_header@impl@2@@Z; winrt::handle_type<winrt::impl::hstring_traits>::attach(winrt::impl::hstring_header *)
0x18004460b  lea     rcx, [rbp+arg_8]
0x18004460f  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180044614  nop
0x180044615  cmp     [rbp+arg_0], 0
0x18004461a  jz      short loc_180044625
0x18004461c  lea     rcx, [rbp+arg_0]
0x180044620  call    ?unconditional_release_ref@?$com_ptr@VWindowUIAProvider@@@winrt@@AEAAXXZ; winrt::com_ptr<WindowUIAProvider>::unconditional_release_ref(void)
0x180044625  mov     rbx, [rsp+40h+arg_10]
0x18004462a  mov     rdi, [rsp+40h+arg_18]
0x18004462f  add     rsp, 40h
0x180044633  pop     rbp
0x180044634  retn
```
