# `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton(void)'::`2'::_lambda_1_::operator()(winrt::Windows::UI::Xaml::Controls::IHyperlinkButtonFactory const &)

- ea: `0x18000f3bc`
- end: `0x18000f466`
- name: `??R_lambda_1_@?1???0HyperlinkButton@Controls@Xaml@UI@Windows@winrt@@QEAA@XZ@QEBA@AEBUIHyperlinkButtonFactory@23456@@Z`
- size: `170`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64 *)`
- caller_count: `14`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ca50`
- `0x18000cba4`
- `0x18000ccf8`
- `0x18000ec84`
- `0x18000ed88`
- `0x180011b80`
- `0x18001bb50`
- `0x18001bca4`
- `0x18001bdf8`
- `0x18001bf4c`
- `0x18001c978`
- `0x18001ca68`
- `0x18001e0b0`
- `0x180021d68`

## callees

- `0x18000b24c`
- `0x18000b5d0`
- `0x18000f3bc`
- `0x18002d010`

## pseudocode

```c
_QWORD *__fastcall `winrt::Windows::UI::Xaml::Controls::HyperlinkButton::HyperlinkButton'::`2'::_lambda_1_::operator()(
        _QWORD *a1,
        _QWORD *a2,
        __int64 *a3)
{
  __int64 v3; // rsi
  char *v4; // rbx
  _QWORD *v6; // r14
  __int64 (__fastcall *v7)(__int64, _QWORD, char *, __int64 *); // rbp
  int v8; // eax
  char v10; // [rsp+38h] [rbp-40h] BYREF
  int v11; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+48h] [rbp-30h]
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF

  v3 = *a3;
  v4 = (char *)a1[1];
  v6 = (_QWORD *)*a1;
  v13 = 0;
  v11 = 0;
  v12 = 0;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, char *, __int64 *))(*(_QWORD *)v3 + 48LL);
  if ( v4 != &v10 )
  {
    if ( *(_QWORD *)v4 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v4);
    *(_QWORD *)v4 = 0;
  }
  v8 = v7(v3, *v6, v4, &v13);
  if ( v8 < 0 )
    winrt::throw_hresult((unsigned int)v8, &v11);
  *a2 = v13;
  return a2;
}

```

## disassembly

```asm
0x18000f3bc  mov     rax, rsp
0x18000f3bf  mov     [rax+10h], rbx
0x18000f3c3  mov     [rax+18h], rbp
0x18000f3c7  push    rsi
0x18000f3c8  push    rdi
0x18000f3c9  push    r14
0x18000f3cb  sub     rsp, 60h
0x18000f3cf  mov     rsi, [r8]
0x18000f3d2  xorps   xmm0, xmm0
0x18000f3d5  mov     rbx, [rcx+8]
0x18000f3d9  mov     rdi, rdx
0x18000f3dc  mov     r14, [rcx]
0x18000f3df  mov     qword ptr [rax+8], 0
0x18000f3e7  mov     dword ptr [rax-38h], 0
0x18000f3ee  movdqu  xmmword ptr [rax-30h], xmm0
0x18000f3f3  mov     rax, [rsi]
0x18000f3f6  mov     rbp, [rax+30h]
0x18000f3fa  lea     rax, [rsp+78h+var_40]
0x18000f3ff  cmp     rbx, rax
0x18000f402  jz      short loc_18000F419
0x18000f404  cmp     qword ptr [rbx], 0
0x18000f408  jz      short loc_18000F412
0x18000f40a  mov     rcx, rbx
0x18000f40d  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000f412  mov     qword ptr [rbx], 0
0x18000f419  mov     rdx, [r14]
0x18000f41c  lea     r9, [rsp+78h+arg_0]
0x18000f424  mov     r8, rbx
0x18000f427  mov     rcx, rsi
0x18000f42a  mov     rax, rbp
0x18000f42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f432  test    eax, eax
0x18000f434  js      short loc_18000F459
0x18000f436  mov     rax, [rsp+78h+arg_0]
0x18000f43e  lea     r11, [rsp+78h+var_18]
0x18000f443  mov     rbx, [r11+28h]
0x18000f447  mov     rbp, [r11+30h]
0x18000f44b  mov     [rdi], rax
0x18000f44e  mov     rax, rdi
0x18000f451  mov     rsp, r11
0x18000f454  pop     r14
0x18000f456  pop     rdi
0x18000f457  pop     rsi
0x18000f458  retn
0x18000f459  lea     rdx, [rsp+78h+var_38]
0x18000f45e  mov     ecx, eax
0x18000f460  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
