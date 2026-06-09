# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800069e0`
- end: `0x180006afe`
- name: `?CreateInstance@FirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `286`
- prototype: `__int64 __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x180002c04`
- `0x180004d50`
- `0x1800069e0`
- `0x18000b5d0`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory::CreateInstance(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _QWORD *v6; // rbx
  __int64 (__fastcall ***v7)(_QWORD, unsigned int *, void **); // r14
  unsigned __int8 v8; // cl
  unsigned __int8 v9; // dl
  unsigned __int8 v10; // r9
  unsigned __int8 v11; // r10
  unsigned __int8 v12; // r11
  unsigned __int8 v13; // di
  unsigned __int8 v14; // si
  unsigned int v15; // ebx
  __int64 result; // rax
  _QWORD *v17; // [rsp+20h] [rbp-58h] BYREF
  unsigned int Data1; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int16 Data2; // [rsp+2Ch] [rbp-4Ch]
  unsigned __int16 Data3; // [rsp+2Eh] [rbp-4Ah]
  unsigned __int8 v21; // [rsp+30h] [rbp-48h]
  unsigned __int8 v22; // [rsp+31h] [rbp-47h]
  unsigned __int8 v23; // [rsp+32h] [rbp-46h]
  unsigned __int8 v24; // [rsp+33h] [rbp-45h]
  unsigned __int8 v25; // [rsp+34h] [rbp-44h]
  char v26; // [rsp+35h] [rbp-43h]
  unsigned __int8 v27; // [rsp+36h] [rbp-42h]
  unsigned __int8 v28; // [rsp+37h] [rbp-41h]

  try
  {
    v6 = operator new(0x1C8u);
    memset_0(v6, 0, 0x1C0u);
    v7 = (__int64 (__fastcall ***)(_QWORD, unsigned int *, void **))(v6 + 56);
    v6[56] = &winrt::impl::produce<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>::`vftable';
    winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::FirewallDialogBase((winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *)v6);
    *v6 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'};
    v6[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'};
    v17 = v6 + 56;
    v8 = a3->Data4[0];
    v9 = a3->Data4[1];
    v10 = a3->Data4[2];
    v11 = a3->Data4[3];
    v12 = a3->Data4[4];
    LOBYTE(v6) = a3->Data4[5];
    v13 = a3->Data4[6];
    v14 = a3->Data4[7];
    Data1 = a3->Data1;
    Data2 = a3->Data2;
    Data3 = a3->Data3;
    v21 = v8;
    v22 = v9;
    v23 = v10;
    v24 = v11;
    v25 = v12;
    v26 = (char)v6;
    v27 = v13;
    v28 = v14;
    v15 = (**v7)(v7, &Data1, a4);
    if ( v7 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v17);
    result = v15;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v17);
  }
  return result;
}

```

## disassembly

```asm
0x1800069e0  push    rbx
0x1800069e2  push    rsi
0x1800069e3  push    rdi
0x1800069e4  push    r12
0x1800069e6  push    r14
0x1800069e8  push    r15
0x1800069ea  sub     rsp, 48h
0x1800069ee  mov     rax, cs:__security_cookie
0x1800069f5  xor     rax, rsp
0x1800069f8  mov     [rsp+78h+var_40], rax
0x1800069fd  mov     r12, r9
0x180006a00  mov     r15, r8
0x180006a03  mov     ecx, 1C8h; Size
0x180006a08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a0d  mov     rbx, rax
0x180006a10  xor     edx, edx; Val
0x180006a12  mov     r8d, 1C0h; Size
0x180006a18  mov     rcx, rax; void *
0x180006a1b  call    memset_0
0x180006a20  lea     r14, [rbx+1C0h]
0x180006a27  lea     rax, ??_7?$produce@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallWarningDialog@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>::`vftable'
0x180006a2e  mov     [r14], rax
0x180006a31  mov     rcx, rbx; this
0x180006a34  call    ??0FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::FirewallDialogBase(void)
0x180006a39  lea     rax, ??_7?$heap_implements@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupXamlContentProvider@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'}
0x180006a40  mov     [rbx], rax
0x180006a43  lea     rax, ??_7?$heap_implements@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupXamlContentProvider@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'}
0x180006a4a  mov     [rbx+8], rax
0x180006a4e  mov     [rsp+78h+var_58], r14
0x180006a53  mov     cl, [r15+8]
0x180006a57  mov     dl, [r15+9]
0x180006a5b  mov     r9b, [r15+0Ah]
0x180006a5f  mov     r10b, [r15+0Bh]
0x180006a63  mov     r11b, [r15+0Ch]
0x180006a67  mov     bl, [r15+0Dh]
0x180006a6b  mov     dil, [r15+0Eh]
0x180006a6f  mov     sil, [r15+0Fh]
0x180006a73  mov     eax, [r15]
0x180006a76  mov     [rsp+78h+var_50], eax
0x180006a7a  movzx   eax, word ptr [r15+4]
0x180006a7f  mov     [rsp+78h+var_4C], ax
0x180006a84  movzx   eax, word ptr [r15+6]
0x180006a89  mov     [rsp+78h+var_4A], ax
0x180006a8e  mov     [rsp+78h+var_48], cl
0x180006a92  mov     [rsp+78h+var_47], dl
0x180006a96  mov     [rsp+78h+var_46], r9b
0x180006a9b  mov     [rsp+78h+var_45], r10b
0x180006aa0  mov     [rsp+78h+var_44], r11b
0x180006aa5  mov     [rsp+78h+var_43], bl
0x180006aa9  mov     [rsp+78h+var_42], dil
0x180006aae  mov     [rsp+78h+var_41], sil
0x180006ab3  mov     rax, [r14]
0x180006ab6  mov     r8, r12
0x180006ab9  lea     rdx, [rsp+78h+var_50]
0x180006abe  mov     rcx, r14
0x180006ac1  mov     rax, [rax]
0x180006ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac9  mov     ebx, eax
0x180006acb  test    r14, r14
0x180006ace  jz      short loc_180006ADA
0x180006ad0  lea     rcx, [rsp+78h+var_58]
0x180006ad5  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x180006ada  mov     eax, ebx
0x180006adc  jmp     short loc_180006AE2
0x180006ade  mov     eax, dword ptr [rsp+78h+var_58]
0x180006ae2  mov     rcx, [rsp+78h+var_40]
0x180006ae7  xor     rcx, rsp; StackCookie
0x180006aea  call    __security_check_cookie
0x180006aef  add     rsp, 48h
0x180006af3  pop     r15
0x180006af5  pop     r14
0x180006af7  pop     r12
0x180006af9  pop     rdi
0x180006afa  pop     rsi
0x180006afb  pop     rbx
0x180006afc  retn
```
