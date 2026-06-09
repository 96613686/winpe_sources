# CUACSettingsPage::OnDestroy(void)

- ea: `0x1800078f4`
- end: `0x180007a41`
- name: `?OnDestroy@CUACSettingsPage@@QEAAXXZ`
- size: `333`
- prototype: `void __fastcall(CUACSettingsPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800063a0`

## callees

- `0x1800078f4`
- `0x180007c4c`
- `0x18000881c`
- `0x1800088dc`
- `0x18000b710`
- `0x18000c010`

## import_xrefs

- `DUI70!?GetThumbPosition@CCTrackBar@DirectUI@@QEAAHXZ` at `0x18000792a`
- `DUI70!?GetThumbPosition@CCTrackBar@DirectUI@@QEAAHXZ` at `0x18000792a`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180007978`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180007978`

## pseudocode

```c
void __fastcall CUACSettingsPage::OnDestroy(CUACSettingsPage *this)
{
  DirectUI::CCTrackBar *v2; // r15
  int v3; // ebx
  unsigned int ThumbPosition; // esi
  __int64 v5; // rcx
  unsigned int *v6; // rcx
  __int64 v7; // rcx
  USPTelemetry *v8; // rcx
  __int64 v9; // rsi
  void (__fastcall *v10)(__int64, __int64, __int64, _QWORD, GUID *, int); // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  GUID v13; // [rsp+40h] [rbp-38h] BYREF

  v2 = (DirectUI::CCTrackBar *)*((_QWORD *)this + 6);
  v3 = -(*((_DWORD *)this + 43) != 0);
  ThumbPosition = DirectUI::CCTrackBar::GetThumbPosition(v2);
  v6 = (unsigned int *)wil::details::static_lazy<USPTelemetry>::get(
                         v5,
                         (void (__cdecl *)())_lambda_01a44b42ce22f61d9e0423afe166f833_::_lambda_invoker_cdecl_)[1];
  if ( v6 )
  {
    v7 = *v6;
    if ( (_DWORD)v7 )
    {
      wil::details::static_lazy<USPTelemetry>::get(
        v7,
        (void (__cdecl *)())_lambda_01a44b42ce22f61d9e0423afe166f833_::_lambda_invoker_cdecl_);
      USPTelemetry::PageExit_(v8, *((_DWORD *)this + 42), ThumbPosition, v3 + 2);
    }
  }
  if ( *((_BYTE *)this + 24) )
  {
    DirectUI::Element::RemoveListener(*((DirectUI::Element **)this + 6), this);
    *((_BYTE *)this + 24) = 0;
  }
  v9 = *((_QWORD *)this + 22);
  if ( v9 )
  {
    v13 = PROPID_ACC_VALUEMAP;
    v10 = *(void (__fastcall **)(__int64, __int64, __int64, _QWORD, GUID *, int))(*(_QWORD *)v9 + 72LL);
    v11 = (*(__int64 (__fastcall **)(DirectUI::CCTrackBar *))(*(_QWORD *)v2 + 360LL))(v2);
    v10(v9, v11, 4294967292LL, 0, &v13, 1);
    wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset((char *)this + 176);
  }
  v12 = *((_QWORD *)this + 19);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 24LL))(v12);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 16LL))(*((_QWORD *)this + 19));
    *((_QWORD *)this + 19) = 0;
  }
}

```

## disassembly

```asm
0x1800078f4  mov     [rsp+arg_8], rbx
0x1800078f9  mov     [rsp+arg_10], rsi
0x1800078fe  push    rdi
0x1800078ff  push    r14
0x180007901  push    r15
0x180007903  sub     rsp, 60h
0x180007907  mov     rax, cs:__security_cookie
0x18000790e  xor     rax, rsp
0x180007911  mov     [rsp+78h+var_28], rax
0x180007916  mov     eax, [rcx+0ACh]
0x18000791c  mov     rdi, rcx
0x18000791f  mov     r15, [rcx+30h]
0x180007923  neg     eax
0x180007925  mov     rcx, r15
0x180007928  sbb     ebx, ebx
0x18000792a  call    cs:__imp_?GetThumbPosition@CCTrackBar@DirectUI@@QEAAHXZ; DirectUI::CCTrackBar::GetThumbPosition(void)
0x180007930  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_01a44b42ce22f61d9e0423afe166f833_@@CA@XZ; _lambda_01a44b42ce22f61d9e0423afe166f833_::_lambda_invoker_cdecl_(void)
0x180007937  mov     esi, eax
0x180007939  call    ?get@?$static_lazy@VUSPTelemetry@@@details@wil@@QEAAPEAVUSPTelemetry@@P6AXXZ@Z; wil::details::static_lazy<USPTelemetry>::get(void (*)(void))
0x18000793e  mov     rcx, [rax+8]
0x180007942  test    rcx, rcx
0x180007945  jz      short loc_18000796B
0x180007947  mov     ecx, [rcx]
0x180007949  test    ecx, ecx
0x18000794b  jz      short loc_18000796B
0x18000794d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_01a44b42ce22f61d9e0423afe166f833_@@CA@XZ; _lambda_01a44b42ce22f61d9e0423afe166f833_::_lambda_invoker_cdecl_(void)
0x180007954  call    ?get@?$static_lazy@VUSPTelemetry@@@details@wil@@QEAAPEAVUSPTelemetry@@P6AXXZ@Z; wil::details::static_lazy<USPTelemetry>::get(void (*)(void))
0x180007959  mov     edx, [rdi+0A8h]; unsigned int
0x18000795f  lea     r9d, [rbx+2]; unsigned int
0x180007963  mov     r8d, esi; unsigned int
0x180007966  call    ?PageExit_@USPTelemetry@@QEAAXKKK@Z; USPTelemetry::PageExit_(ulong,ulong,ulong)
0x18000796b  cmp     byte ptr [rdi+18h], 0
0x18000796f  jz      short loc_180007982
0x180007971  mov     rcx, [rdi+30h]
0x180007975  mov     rdx, rdi
0x180007978  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x18000797e  mov     byte ptr [rdi+18h], 0
0x180007982  lea     r14, [rdi+0B0h]
0x180007989  mov     rsi, [r14]
0x18000798c  test    rsi, rsi
0x18000798f  jz      short loc_1800079E8
0x180007991  movups  xmm0, xmmword ptr cs:PROPID_ACC_VALUEMAP.Data1
0x180007998  mov     rcx, r15
0x18000799b  movdqu  [rsp+78h+var_38], xmm0
0x1800079a1  mov     rax, [rsi]
0x1800079a4  mov     rbx, [rax+48h]
0x1800079a8  mov     rax, [r15]
0x1800079ab  mov     rax, [rax+168h]
0x1800079b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079b7  lea     rcx, [rsp+78h+var_38]
0x1800079bc  mov     [rsp+78h+var_50], 1
0x1800079c4  mov     [rsp+78h+var_58], rcx
0x1800079c9  mov     rdx, rax
0x1800079cc  mov     rcx, rsi
0x1800079cf  xor     r9d, r9d
0x1800079d2  mov     r8d, 0FFFFFFFCh
0x1800079d8  mov     rax, rbx
0x1800079db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e0  mov     rcx, r14
0x1800079e3  call    ?reset@?$com_ptr_t@UIAccPropServices@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAccPropServices,wil::err_returncode_policy>::reset(void)
0x1800079e8  mov     rcx, [rdi+98h]
0x1800079ef  test    rcx, rcx
0x1800079f2  jz      short loc_180007A1E
0x1800079f4  mov     rax, [rcx]
0x1800079f7  mov     rax, [rax+18h]
0x1800079fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a00  mov     rcx, [rdi+98h]
0x180007a07  mov     rax, [rcx]
0x180007a0a  mov     rax, [rax+10h]
0x180007a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a13  mov     qword ptr [rdi+98h], 0
0x180007a1e  mov     rcx, [rsp+78h+var_28]
0x180007a23  xor     rcx, rsp; StackCookie
0x180007a26  call    __security_check_cookie
0x180007a2b  lea     r11, [rsp+78h+var_18]
0x180007a30  mov     rbx, [r11+28h]
0x180007a34  mov     rsi, [r11+30h]
0x180007a38  mov     rsp, r11
0x180007a3b  pop     r15
0x180007a3d  pop     r14
0x180007a3f  pop     rdi
0x180007a40  retn
```
