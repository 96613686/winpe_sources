# FlowEndpointBase::OnCopyData(HWND__ *,tagCOPYDATASTRUCT const &)

- ea: `0x180013e04`
- end: `0x180013fa5`
- name: `?OnCopyData@FlowEndpointBase@@IEAAXPEAUHWND__@@AEBUtagCOPYDATASTRUCT@@@Z`
- size: `417`
- prototype: `void __fastcall(FlowEndpointBase *__hidden this, HWND, const struct tagCOPYDATASTRUCT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c8c0`

## callees

- `0x180002b20`
- `0x1800041c4`
- `0x180004240`
- `0x1800043a0`
- `0x180009848`
- `0x18000a428`
- `0x18000d670`
- `0x18000fde4`
- `0x180013e04`
- `0x180017024`
- `0x180017124`
- `0x18001c864`
- `0x18005a010`

## import_xrefs

- `USER32!ReplyMessage` at `0x180013f4f`
- `USER32!ReplyMessage` at `0x180013f4f`

## string_xrefs

- `0x180013f93`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall FlowEndpointBase::OnCopyData(FlowEndpointBase *this, HWND a2, const struct tagCOPYDATASTRUCT *a3)
{
  unsigned int dwData; // esi
  int v7; // r9d
  DWORD cbData; // ecx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  int v13; // [rsp+20h] [rbp-50h]
  _BYTE v14[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  int v16; // [rsp+40h] [rbp-30h] BYREF
  __int128 v17; // [rsp+48h] [rbp-28h]
  int v18[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( *((_DWORD *)this + 28) != 3 )
  {
    if ( (dwData = a3->dwData,
          !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl))
      || !a2
      || *((_DWORD *)this + 28) == 1 && dwData == 3
      || FlowEndpointBase::DoesWindowBelongToCallingProcess(this, a2) )
    {
      if ( *((_DWORD *)this + 28) == 4 || *((_DWORD *)this + 28) == 1 && dwData == 3 || a2 == *((HWND *)this + 5) )
      {
        v19 = 0;
        if ( !*((_BYTE *)this + 129) )
        {
          cbData = a3->cbData;
          if ( cbData )
          {
            *(_QWORD *)v18 = 0;
            LOBYTE(v7) = 0;
            v9 = Windows::Storage::Streams::MakeCBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_>(
                   cbData,
                   cbData,
                   a3->lpData,
                   v7,
                   (__int64)v18);
            if ( v9 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x226,
                (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
                (const char *)(unsigned int)v9,
                v13);
            winrt::impl::as<winrt::Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBuffer,0>(
              &v15,
              *(_QWORD *)v18);
            v10 = winrt::Windows::Foundation::Collections::ValueSet::ValueSet((winrt::Windows::Foundation::Collections::ValueSet *)v14);
            winrt::Windows::Foundation::IUnknown::operator=(&v19, v10);
            winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)v14);
            v11 = *((_QWORD *)this + 9);
            v16 = 0;
            v17 = 0;
            v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v11 + 56LL))(v11, v19, v15);
            winrt::check_hresult(v14, v12, &v16);
            winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v15);
            if ( *(_QWORD *)v18 )
              winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(v18);
          }
        }
        ReplyMessage(0);
        (*(void (__fastcall **)(_QWORD, HWND, _QWORD, __int64 *))(**((_QWORD **)this + 10) + 8LL))(
          *((_QWORD *)this + 10),
          a2,
          dwData,
          &v19);
        winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler((winrt::Microsoft::UI::Xaml::SizeChangedEventHandler *)&v19);
      }
    }
  }
}

```

## disassembly

```asm
0x180013e04  push    rbp
0x180013e06  push    rbx
0x180013e07  push    rsi
0x180013e08  push    rdi
0x180013e09  push    r14
0x180013e0b  mov     rbp, rsp
0x180013e0e  sub     rsp, 70h
0x180013e12  mov     rax, cs:__security_cookie
0x180013e19  xor     rax, rsp
0x180013e1c  mov     [rbp+var_8], rax
0x180013e20  mov     r14, r8
0x180013e23  mov     rdi, rdx
0x180013e26  mov     rbx, rcx
0x180013e29  cmp     dword ptr [rcx+70h], 3
0x180013e2d  jz      loc_180013F79
0x180013e33  mov     esi, [r8]
0x180013e36  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x180013e3d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x180013e42  test    al, al
0x180013e44  jz      short loc_180013E69
0x180013e46  test    rdi, rdi
0x180013e49  jz      short loc_180013E69
0x180013e4b  cmp     dword ptr [rbx+70h], 1
0x180013e4f  jnz     short loc_180013E56
0x180013e51  cmp     esi, 3
0x180013e54  jz      short loc_180013E69
0x180013e56  mov     rdx, rdi; HWND
0x180013e59  mov     rcx, rbx; this
0x180013e5c  call    ?DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z; FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)
0x180013e61  test    al, al
0x180013e63  jz      loc_180013F79
0x180013e69  cmp     dword ptr [rbx+70h], 4
0x180013e6d  jz      short loc_180013E84
0x180013e6f  cmp     dword ptr [rbx+70h], 1
0x180013e73  jnz     short loc_180013E7A
0x180013e75  cmp     esi, 3
0x180013e78  jz      short loc_180013E84
0x180013e7a  cmp     rdi, [rbx+28h]
0x180013e7e  jnz     loc_180013F79
0x180013e84  mov     [rbp+var_10], 0
0x180013e8c  cmp     byte ptr [rbx+81h], 0
0x180013e93  jnz     loc_180013F4D
0x180013e99  mov     ecx, [r14+8]
0x180013e9d  test    ecx, ecx
0x180013e9f  jz      loc_180013F4D
0x180013ea5  mov     qword ptr [rbp+var_18], 0
0x180013ead  xor     r9b, r9b
0x180013eb0  lea     rax, [rbp+var_18]
0x180013eb4  mov     qword ptr [rsp+70h+var_50], rax; int
0x180013eb9  mov     r8, [r14+10h]
0x180013ebd  mov     edx, ecx
0x180013ebf  call    ??$MakeCBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@@Streams@Storage@Windows@@YAJIIPEAEV_lambda_8fcabb03306c9f8765c03020018d7da6_@@PEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_>(uint,uint,uchar *,_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::IBuffer * *)
0x180013ec4  mov     rcx, [rbp+28h]; this
0x180013ec8  test    eax, eax
0x180013eca  js      loc_180013F90
0x180013ed0  mov     rdx, qword ptr [rbp+var_18]
0x180013ed4  lea     rcx, [rbp+var_38]
0x180013ed8  call    ??$as@UIBuffer@Streams@Storage@Windows@winrt@@U1234@$0A@@impl@winrt@@YA?AUIBuffer@Streams@Storage@Windows@1@PEAU2345@@Z; winrt::impl::as<winrt::Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBuffer,0>(Windows::Storage::Streams::IBuffer *)
0x180013edd  nop
0x180013ede  lea     rcx, [rbp+var_40]; this
0x180013ee2  call    ??0ValueSet@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x180013ee7  mov     rdx, rax
0x180013eea  lea     rcx, [rbp+var_10]
0x180013eee  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x180013ef3  lea     rcx, [rbp+var_40]; this
0x180013ef7  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180013efc  mov     rcx, [rbx+48h]
0x180013f00  mov     [rbp+var_30], 0
0x180013f07  xorps   xmm0, xmm0
0x180013f0a  movdqu  [rbp+var_28], xmm0
0x180013f0f  mov     rax, [rcx]
0x180013f12  mov     r8, [rbp+var_38]
0x180013f16  mov     rdx, [rbp+var_10]
0x180013f1a  mov     rax, [rax+38h]
0x180013f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f23  lea     r8, [rbp+var_30]
0x180013f27  mov     edx, eax
0x180013f29  lea     rcx, [rbp+var_40]
0x180013f2d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180013f32  nop
0x180013f33  lea     rcx, [rbp+var_38]; this
0x180013f37  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180013f3c  nop
0x180013f3d  cmp     qword ptr [rbp+var_18], 0
0x180013f42  jz      short loc_180013F4D
0x180013f44  lea     rcx, [rbp+var_18]
0x180013f48  call    ?unconditional_release_ref@?$com_ptr@UIDesktopWindowXamlSourceNative@@@winrt@@AEAAXXZ; winrt::com_ptr<IDesktopWindowXamlSourceNative>::unconditional_release_ref(void)
0x180013f4d  xor     ecx, ecx; lResult
0x180013f4f  call    cs:__imp_ReplyMessage
0x180013f55  mov     rcx, [rbx+50h]
0x180013f59  mov     rax, [rcx]
0x180013f5c  lea     r9, [rbp+var_10]
0x180013f60  mov     r8d, esi
0x180013f63  mov     rdx, rdi
0x180013f66  mov     rax, [rax+8]
0x180013f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f6f  nop
0x180013f70  lea     rcx, [rbp+var_10]; this
0x180013f74  call    ??1SizeChangedEventHandler@Xaml@UI@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::UI::Xaml::SizeChangedEventHandler::~SizeChangedEventHandler(void)
0x180013f79  mov     rcx, [rbp+var_8]
0x180013f7d  xor     rcx, rsp; StackCookie
0x180013f80  call    __security_check_cookie
0x180013f85  add     rsp, 70h
0x180013f89  pop     r14
0x180013f8b  pop     rdi
0x180013f8c  pop     rsi
0x180013f8d  pop     rbx
0x180013f8e  pop     rbp
0x180013f8f  retn
0x180013f90  mov     r9d, eax; char *
0x180013f93  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180013f9a  mov     edx, 226h; void *
0x180013f9f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
