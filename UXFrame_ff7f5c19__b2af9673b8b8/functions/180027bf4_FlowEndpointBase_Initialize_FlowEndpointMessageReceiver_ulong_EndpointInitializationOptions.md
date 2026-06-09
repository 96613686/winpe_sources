# FlowEndpointBase::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)

- ea: `0x180027bf4`
- end: `0x180027ccd`
- name: `?Initialize@FlowEndpointBase@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027aec`
- `0x18002bf60`
- `0x1800447bc`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x180017024`
- `0x18001c864`
- `0x18001e80c`
- `0x1800236f4`
- `0x180027bf4`

## import_xrefs

- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180027c4a`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x180027c4a`

## string_xrefs

- `0x180027ca9`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`
- `0x180027cbb`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FlowEndpointBase::Initialize(__int64 a1, HWND a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  const char *v5; // r9
  int v6; // eax
  int v7; // [rsp+20h] [rbp-38h]
  _BYTE v8[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)(a1 + 80) = a2;
  *(_DWORD *)(a1 + 88) = -1;
  CImpWorkerWndProc::CreateWorkerWindow((CImpWorkerWndProc *)a1, a2);
  v5 = *(_QWORD *)(a1 + 8) == 0 ? (const char *)0x8007000ELL : 0LL;
  if ( !*(_QWORD *)(a1 + 8) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
      v5,
      v7);
  v9 = 0;
  v6 = RoCreatePropertySetSerializer(&v9, v3, v4, v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
      (const char *)(unsigned int)v6,
      v7);
  winrt::impl::as<winrt::Windows::Storage::Streams::IPropertySetSerializer,Windows::Storage::Streams::IPropertySetSerializer,0>(
    v8,
    v9);
  winrt::Windows::Foundation::IUnknown::operator=(a1 + 72, v8);
  winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v8);
  if ( v9 )
    winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(&v9);
}

```

## disassembly

```asm
0x180027bf4  push    rbx
0x180027bf6  sub     rsp, 50h
0x180027bfa  mov     rax, cs:__security_cookie
0x180027c01  xor     rax, rsp
0x180027c04  mov     [rsp+58h+var_18], rax
0x180027c09  mov     rbx, rcx
0x180027c0c  mov     [rcx+50h], rdx
0x180027c10  mov     dword ptr [rcx+58h], 0FFFFFFFFh
0x180027c17  call    ?CreateWorkerWindow@CImpWorkerWndProc@@IEAAPEAUHWND__@@PEAU2@KKPEAUHMENU__@@@Z; CImpWorkerWndProc::CreateWorkerWindow(HWND__ *,ulong,ulong,HMENU__ *)
0x180027c1c  mov     rax, [rbx+8]
0x180027c20  neg     rax
0x180027c23  sbb     r9d, r9d
0x180027c26  not     r9d
0x180027c29  and     r9d, 8007000Eh; char *
0x180027c30  mov     rcx, [rsp+58h]; this
0x180027c35  cmp     qword ptr [rbx+8], 0
0x180027c3a  jz      short loc_180027CBB
0x180027c3c  mov     [rsp+58h+var_20], 0
0x180027c45  lea     rcx, [rsp+58h+var_20]
0x180027c4a  call    cs:__imp_RoCreatePropertySetSerializer
0x180027c50  mov     rcx, [rsp+58h]; this
0x180027c55  test    eax, eax
0x180027c57  js      short loc_180027CA6
0x180027c59  mov     rdx, [rsp+58h+var_20]
0x180027c5e  lea     rcx, [rsp+58h+var_28]
0x180027c63  call    ??$as@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@U1234@$0A@@impl@winrt@@YA?AUIPropertySetSerializer@Streams@Storage@Windows@1@PEAU2345@@Z; winrt::impl::as<winrt::Windows::Storage::Streams::IPropertySetSerializer,Windows::Storage::Streams::IPropertySetSerializer,0>(Windows::Storage::Streams::IPropertySetSerializer *)
0x180027c68  lea     rcx, [rbx+48h]
0x180027c6c  lea     rdx, [rsp+58h+var_28]
0x180027c71  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180027c76  lea     rcx, [rsp+58h+var_28]; this
0x180027c7b  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180027c80  nop
0x180027c81  cmp     [rsp+58h+var_20], 0
0x180027c87  jz      short loc_180027C93
0x180027c89  lea     rcx, [rsp+58h+var_20]
0x180027c8e  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x180027c93  mov     rcx, [rsp+58h+var_18]
0x180027c98  xor     rcx, rsp; StackCookie
0x180027c9b  call    __security_check_cookie
0x180027ca0  add     rsp, 50h
0x180027ca4  pop     rbx
0x180027ca5  retn
0x180027ca6  mov     r9d, eax; char *
0x180027ca9  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180027cb0  mov     edx, 5Ch ; '\'; void *
0x180027cb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180027cbb  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180027cc2  mov     edx, 59h ; 'Y'; void *
0x180027cc7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
