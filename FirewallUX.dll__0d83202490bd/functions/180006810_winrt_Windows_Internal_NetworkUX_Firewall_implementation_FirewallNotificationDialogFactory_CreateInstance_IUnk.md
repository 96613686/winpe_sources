# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006810`
- end: `0x1800069d6`
- name: `?CreateInstance@FirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `454`
- prototype: `__int64 __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x180002c04`
- `0x180004d50`
- `0x180006810`
- `0x18000b5d0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800068e9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800068e9`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory::CreateInstance(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory *this,
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
  _QWORD *v17; // [rsp+20h] [rbp-48h] BYREF
  unsigned int Data1; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int16 Data2; // [rsp+2Ch] [rbp-3Ch]
  unsigned __int16 Data3; // [rsp+2Eh] [rbp-3Ah]
  unsigned __int8 v21; // [rsp+30h] [rbp-38h]
  unsigned __int8 v22; // [rsp+31h] [rbp-37h]
  unsigned __int8 v23; // [rsp+32h] [rbp-36h]
  unsigned __int8 v24; // [rsp+33h] [rbp-35h]
  unsigned __int8 v25; // [rsp+34h] [rbp-34h]
  char v26; // [rsp+35h] [rbp-33h]
  unsigned __int8 v27; // [rsp+36h] [rbp-32h]
  unsigned __int8 v28; // [rsp+37h] [rbp-31h]

  try
  {
    v6 = operator new(0x260u);
    memset_0(v6, 0, 0x260u);
    v7 = (__int64 (__fastcall ***)(_QWORD, unsigned int *, void **))(v6 + 56);
    v6[56] = &winrt::impl::produce<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>::`vftable';
    winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::FirewallDialogBase((winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase *)v6);
    *v6 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'};
    v6[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'};
    v6[57] = 0;
    v6[58] = 0;
    v6[59] = 0;
    v6[60] = 0;
    v6[61] = 0;
    v6[62] = 0;
    v6[63] = 0;
    v6[64] = 0;
    v6[65] = 0;
    v6[66] = 0;
    v6[67] = 0;
    v6[68] = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v6 + 69), 0, 0);
    *((_DWORD *)v6 + 148) = 0x1000000;
    *((_BYTE *)v6 + 596) = 0;
    v6[75] = 0;
    *v6 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'};
    v6[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'};
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
0x180006810  mov     [rsp+arg_0], rbx
0x180006815  mov     [rsp+arg_8], rsi
0x18000681a  push    rdi
0x18000681b  push    r12
0x18000681d  push    r13
0x18000681f  push    r14
0x180006821  push    r15
0x180006823  sub     rsp, 40h
0x180006827  mov     rax, cs:__security_cookie
0x18000682e  xor     rax, rsp
0x180006831  mov     [rsp+68h+var_30], rax
0x180006836  mov     r12, r9
0x180006839  mov     r15, r8
0x18000683c  xor     r13d, r13d
0x18000683f  mov     edi, 260h
0x180006844  mov     ecx, edi; Size
0x180006846  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000684b  mov     rbx, rax
0x18000684e  mov     r8d, edi; Size
0x180006851  xor     edx, edx; Val
0x180006853  mov     rcx, rax; void *
0x180006856  call    memset_0
0x18000685b  lea     r14, [rbx+1C0h]
0x180006862  lea     rax, ??_7?$produce@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIFirewallNotificationDialog@34567@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog,winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>::`vftable'
0x180006869  mov     [r14], rax
0x18000686c  mov     rcx, rbx; this
0x18000686f  call    ??0FirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase::FirewallDialogBase(void)
0x180006874  lea     rax, ??_7?$heap_implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupXamlContentProvider@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'}
0x18000687b  mov     [rbx], rax
0x18000687e  lea     rax, ??_7?$heap_implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupXamlContentProvider@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'}
0x180006885  mov     [rbx+8], rax
0x180006889  mov     [rbx+1C8h], r13
0x180006890  mov     [rbx+1D0h], r13
0x180006897  mov     [rbx+1D8h], r13
0x18000689e  mov     [rbx+1E0h], r13
0x1800068a5  mov     [rbx+1E8h], r13
0x1800068ac  mov     [rbx+1F0h], r13
0x1800068b3  mov     [rbx+1F8h], r13
0x1800068ba  mov     [rbx+200h], r13
0x1800068c1  mov     [rbx+208h], r13
0x1800068c8  mov     [rbx+210h], r13
0x1800068cf  mov     [rbx+218h], r13
0x1800068d6  mov     [rbx+220h], r13
0x1800068dd  lea     rcx, [rbx+228h]; lpCriticalSection
0x1800068e4  xor     r8d, r8d; Flags
0x1800068e7  xor     edx, edx; dwSpinCount
0x1800068e9  call    cs:__imp_InitializeCriticalSectionEx
0x1800068ef  mov     dword ptr [rbx+250h], 1000000h
0x1800068f9  mov     [rbx+254h], r13b
0x180006900  mov     [rbx+258h], r13
0x180006907  lea     rax, ??_7?$heap_implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIPopupXamlContentProvider@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,std::tuple<IPopupXamlContentProvider>>'}
0x18000690e  mov     [rbx], rax
0x180006911  lea     rax, ??_7?$heap_implements@UFirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UFirewallDialogBase@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIPopupXamlContentProvider@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallDialogBase,IPopupXamlContentProvider>'}
0x180006918  mov     [rbx+8], rax
0x18000691c  mov     [rsp+68h+var_48], r14
0x180006921  mov     cl, [r15+8]
0x180006925  mov     dl, [r15+9]
0x180006929  mov     r9b, [r15+0Ah]
0x18000692d  mov     r10b, [r15+0Bh]
0x180006931  mov     r11b, [r15+0Ch]
0x180006935  mov     bl, [r15+0Dh]
0x180006939  mov     dil, [r15+0Eh]
0x18000693d  mov     sil, [r15+0Fh]
0x180006941  mov     eax, [r15]
0x180006944  mov     [rsp+68h+var_40], eax
0x180006948  movzx   eax, word ptr [r15+4]
0x18000694d  mov     [rsp+68h+var_3C], ax
0x180006952  movzx   eax, word ptr [r15+6]
0x180006957  mov     [rsp+68h+var_3A], ax
0x18000695c  mov     [rsp+68h+var_38], cl
0x180006960  mov     [rsp+68h+var_37], dl
0x180006964  mov     [rsp+68h+var_36], r9b
0x180006969  mov     [rsp+68h+var_35], r10b
0x18000696e  mov     [rsp+68h+var_34], r11b
0x180006973  mov     [rsp+68h+var_33], bl
0x180006977  mov     [rsp+68h+var_32], dil
0x18000697c  mov     [rsp+68h+var_31], sil
0x180006981  mov     rax, [r14]
0x180006984  mov     r8, r12
0x180006987  lea     rdx, [rsp+68h+var_40]
0x18000698c  mov     rcx, r14
0x18000698f  mov     rax, [rax]
0x180006992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006997  mov     ebx, eax
0x180006999  test    r14, r14
0x18000699c  jz      short loc_1800069A8
0x18000699e  lea     rcx, [rsp+68h+var_48]
0x1800069a3  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x1800069a8  mov     eax, ebx
0x1800069aa  jmp     short loc_1800069B0
0x1800069ac  mov     eax, dword ptr [rsp+68h+var_48]
0x1800069b0  mov     rcx, [rsp+68h+var_30]
0x1800069b5  xor     rcx, rsp; StackCookie
0x1800069b8  call    __security_check_cookie
0x1800069bd  mov     rbx, [rsp+68h+arg_0]
0x1800069c2  mov     rsi, [rsp+68h+arg_8]
0x1800069c7  add     rsp, 40h
0x1800069cb  pop     r15
0x1800069cd  pop     r14
0x1800069cf  pop     r13
0x1800069d1  pop     r12
0x1800069d3  pop     rdi
0x1800069d4  retn
```
