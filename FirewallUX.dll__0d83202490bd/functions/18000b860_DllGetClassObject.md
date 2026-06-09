# DllGetClassObject

- ea: `0x18000b860`
- end: `0x18000bb70`
- name: `DllGetClassObject`
- size: `784`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800021c0`
- `0x1800021e4`
- `0x180002db5`
- `0x180003d9d`
- `0x18000af78`
- `0x18000b4ac`
- `0x18000b5d0`
- `0x18000b5f0`
- `0x18000b860`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned __int8 v5; // r8
  unsigned __int8 v6; // r9
  unsigned __int8 v7; // r10
  unsigned __int8 v8; // r11
  unsigned __int8 v9; // dl
  unsigned __int8 v10; // cl
  unsigned __int8 v11; // bl
  unsigned __int8 v12; // di
  _QWORD *v13; // r15
  unsigned __int8 v14; // cl
  unsigned __int8 v15; // dl
  unsigned __int8 v16; // r9
  unsigned __int8 v17; // r10
  unsigned __int8 v18; // r11
  unsigned __int8 v19; // bl
  unsigned __int8 v20; // di
  unsigned __int8 v21; // si
  HRESULT v22; // ebx
  _QWORD *v24; // rsi
  unsigned __int8 v25; // cl
  unsigned __int8 v26; // dl
  unsigned __int8 v27; // r8
  unsigned __int8 v28; // r9
  unsigned __int8 v29; // r10
  unsigned __int8 v30; // r11
  unsigned __int8 v31; // bl
  unsigned __int8 v32; // di
  HRESULT v33; // ebx
  HRESULT v34; // ebx
  _QWORD *Buf1; // [rsp+20h] [rbp-88h] BYREF
  unsigned __int8 v36; // [rsp+28h] [rbp-80h]
  unsigned __int8 v37; // [rsp+29h] [rbp-7Fh]
  unsigned __int8 v38; // [rsp+2Ah] [rbp-7Eh]
  unsigned __int8 v39; // [rsp+2Bh] [rbp-7Dh]
  unsigned __int8 v40; // [rsp+2Ch] [rbp-7Ch]
  unsigned __int8 v41; // [rsp+2Dh] [rbp-7Bh]
  unsigned __int8 v42; // [rsp+2Eh] [rbp-7Ah]
  unsigned __int8 v43; // [rsp+2Fh] [rbp-79h]
  int v44; // [rsp+30h] [rbp-78h] BYREF
  __int128 v45; // [rsp+38h] [rbp-70h]
  BSTR bstrString; // [rsp+48h] [rbp-60h] BYREF
  int v47; // [rsp+50h] [rbp-58h]
  int v48; // [rsp+54h] [rbp-54h]
  __int64 v49; // [rsp+58h] [rbp-50h] BYREF

  *ppv = 0;
  v5 = rclsid->Data4[0];
  v6 = rclsid->Data4[1];
  v7 = rclsid->Data4[2];
  v8 = rclsid->Data4[3];
  v9 = rclsid->Data4[4];
  v10 = rclsid->Data4[5];
  v11 = rclsid->Data4[6];
  v12 = rclsid->Data4[7];
  Buf1 = *(_QWORD **)&rclsid->Data1;
  v36 = v5;
  v37 = v6;
  v38 = v7;
  v39 = v8;
  v40 = v9;
  v41 = v10;
  v42 = v11;
  v43 = v12;
  if ( !memcmp_0(
          &Buf1,
          &winrt::impl::guid_v<winrt::Windows::Internal::NetworkUX::Firewall::IFirewallNotificationDialog>,
          0x10u) )
  {
    v13 = operator new(0x18u);
    v13[1] = 0;
    v13[2] = 0;
    *v13 = &winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v13[2] = 1;
    *v13 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>'};
    v13[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>'};
    Buf1 = v13;
    v14 = riid->Data4[0];
    v15 = riid->Data4[1];
    v16 = riid->Data4[2];
    v17 = riid->Data4[3];
    v18 = riid->Data4[4];
    v19 = riid->Data4[5];
    v20 = riid->Data4[6];
    v21 = riid->Data4[7];
    bstrString = *(BSTR *)&riid->Data1;
    LOBYTE(v47) = v14;
    BYTE1(v47) = v15;
    BYTE2(v47) = v16;
    HIBYTE(v47) = v17;
    LOBYTE(v48) = v18;
    BYTE1(v48) = v19;
    BYTE2(v48) = v20;
    HIBYTE(v48) = v21;
    v22 = winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>'}();
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&Buf1);
    return v22;
  }
  else if ( !memcmp_0(
               &Buf1,
               &winrt::impl::guid_v<winrt::Windows::Internal::NetworkUX::Firewall::IFirewallWarningDialog>,
               0x10u) )
  {
    v24 = operator new(0x18u);
    v24[1] = 0;
    v24[2] = 0;
    *v24 = &winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v24[2] = 1;
    *v24 = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,std::tuple<IClassFactory>>'};
    v24[1] = &winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>'};
    Buf1 = v24;
    v25 = riid->Data4[0];
    v26 = riid->Data4[1];
    v27 = riid->Data4[2];
    v28 = riid->Data4[3];
    v29 = riid->Data4[4];
    v30 = riid->Data4[5];
    v31 = riid->Data4[6];
    v32 = riid->Data4[7];
    bstrString = *(BSTR *)&riid->Data1;
    LOBYTE(v47) = v25;
    BYTE1(v47) = v26;
    BYTE2(v47) = v27;
    HIBYTE(v47) = v28;
    LOBYTE(v48) = v29;
    BYTE1(v48) = v30;
    BYTE2(v48) = v31;
    HIBYTE(v48) = v32;
    v33 = winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,std::tuple<IClassFactory>>'}();
    winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(&Buf1);
    return v33;
  }
  else
  {
    v44 = 0;
    v45 = 0;
    bstrString = 0;
    v47 = -1430532899;
    v48 = -2147221231;
    v49 = 0;
    winrt::hresult_error::originate(&bstrString, 2147746065LL, 0, &v44);
    v34 = *(_DWORD *)winrt::hresult_error::to_abi(&bstrString, &Buf1);
    if ( v49 )
      winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(&v49);
    if ( bstrString )
      WINRT_IMPL_SysFreeString(bstrString);
    return v34;
  }
}

```

## disassembly

```asm
0x18000b860  push    rbx
0x18000b862  push    rsi
0x18000b863  push    rdi
0x18000b864  push    r12
0x18000b866  push    r14
0x18000b868  push    r15
0x18000b86a  sub     rsp, 78h
0x18000b86e  mov     rax, cs:__security_cookie
0x18000b875  xor     rax, rsp
0x18000b878  mov     [rsp+0A8h+var_48], rax
0x18000b87d  mov     r12, r8
0x18000b880  mov     r14, rdx
0x18000b883  mov     rsi, rcx
0x18000b886  mov     qword ptr [r8], 0
0x18000b88d  mov     r8b, [rcx+8]
0x18000b891  mov     r9b, [rcx+9]
0x18000b895  mov     r10b, [rcx+0Ah]
0x18000b899  mov     r11b, [rcx+0Bh]
0x18000b89d  mov     dl, [rcx+0Ch]
0x18000b8a0  mov     cl, [rcx+0Dh]
0x18000b8a3  mov     bl, [rsi+0Eh]
0x18000b8a6  mov     dil, [rsi+0Fh]
0x18000b8aa  mov     eax, [rsi]
0x18000b8ac  mov     dword ptr [rsp+0A8h+Buf1], eax
0x18000b8b0  movzx   eax, word ptr [rsi+4]
0x18000b8b4  mov     word ptr [rsp+0A8h+Buf1+4], ax
0x18000b8b9  movzx   eax, word ptr [rsi+6]
0x18000b8bd  mov     word ptr [rsp+0A8h+Buf1+6], ax
0x18000b8c2  mov     [rsp+0A8h+var_80], r8b
0x18000b8c7  mov     [rsp+0A8h+var_7F], r9b
0x18000b8cc  mov     [rsp+0A8h+var_7E], r10b
0x18000b8d1  mov     [rsp+0A8h+var_7D], r11b
0x18000b8d6  mov     [rsp+0A8h+var_7C], dl
0x18000b8da  mov     [rsp+0A8h+var_7B], cl
0x18000b8de  mov     [rsp+0A8h+var_7A], bl
0x18000b8e2  mov     [rsp+0A8h+var_79], dil
0x18000b8e7  mov     ebx, 10h
0x18000b8ec  mov     r8d, ebx; Size
0x18000b8ef  lea     rdx, ??$guid_v@UIFirewallNotificationDialog@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000b8f6  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x18000b8fb  call    memcmp_0
0x18000b900  test    eax, eax
0x18000b902  jnz     loc_18000B9E0
0x18000b908  lea     ecx, [rbx+8]; Size
0x18000b90b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b910  mov     r15, rax
0x18000b913  mov     qword ptr [rax+8], 0
0x18000b91b  mov     qword ptr [rax+10h], 0
0x18000b923  lea     rax, ??_7?$producers_base@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>::`vftable'
0x18000b92a  mov     [r15], rax
0x18000b92d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000b934  mov     qword ptr [r15+10h], 1
0x18000b93c  lea     rax, ??_7?$heap_implements@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>'}
0x18000b943  mov     [r15], rax
0x18000b946  lea     rax, ??_7?$heap_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIClassFactory@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>'}
0x18000b94d  mov     [r15+8], rax
0x18000b951  mov     [rsp+0A8h+Buf1], r15
0x18000b956  mov     cl, [r14+8]
0x18000b95a  mov     dl, [r14+9]
0x18000b95e  mov     r9b, [r14+0Ah]
0x18000b962  mov     r10b, [r14+0Bh]
0x18000b966  mov     r11b, [r14+0Ch]
0x18000b96a  mov     bl, [r14+0Dh]
0x18000b96e  mov     dil, [r14+0Eh]
0x18000b972  mov     sil, [r14+0Fh]
0x18000b976  mov     eax, [r14]
0x18000b979  mov     dword ptr [rsp+0A8h+bstrString], eax
0x18000b97d  movzx   eax, word ptr [r14+4]
0x18000b982  mov     word ptr [rsp+0A8h+bstrString+4], ax
0x18000b987  movzx   eax, word ptr [r14+6]
0x18000b98c  mov     word ptr [rsp+0A8h+bstrString+6], ax
0x18000b991  mov     byte ptr [rsp+0A8h+var_58], cl
0x18000b995  mov     byte ptr [rsp+0A8h+var_58+1], dl
0x18000b999  mov     byte ptr [rsp+0A8h+var_58+2], r9b
0x18000b99e  mov     byte ptr [rsp+0A8h+var_58+3], r10b
0x18000b9a3  mov     byte ptr [rsp+0A8h+var_54], r11b
0x18000b9a8  mov     byte ptr [rsp+0A8h+var_54+1], bl
0x18000b9ac  mov     byte ptr [rsp+0A8h+var_54+2], dil
0x18000b9b1  mov     byte ptr [rsp+0A8h+var_54+3], sil
0x18000b9b6  mov     r8, r12
0x18000b9b9  lea     rdx, [rsp+0A8h+bstrString]
0x18000b9be  mov     rcx, r15
0x18000b9c1  mov     rax, cs:??_7?$heap_implements@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>'}
0x18000b9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9cd  mov     ebx, eax
0x18000b9cf  lea     rcx, [rsp+0A8h+Buf1]
0x18000b9d4  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18000b9d9  mov     eax, ebx
0x18000b9db  jmp     loc_18000BB54
0x18000b9e0  mov     r8, rbx; Size
0x18000b9e3  lea     rdx, ??$guid_v@UIFirewallWarningDialog@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; Buf2
0x18000b9ea  lea     rcx, [rsp+0A8h+Buf1]; Buf1
0x18000b9ef  call    memcmp_0
0x18000b9f4  test    eax, eax
0x18000b9f6  jnz     loc_18000BAD4
0x18000b9fc  lea     ecx, [rax+18h]; Size
0x18000b9ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba04  mov     rsi, rax
0x18000ba07  mov     qword ptr [rax+8], 0
0x18000ba0f  mov     qword ptr [rax+10h], 0
0x18000ba17  lea     rax, ??_7?$producers_base@UFirewallNotificationDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialogFactory,std::tuple<IClassFactory>>::`vftable'
0x18000ba1e  mov     [rsi], rax
0x18000ba21  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000ba28  mov     qword ptr [rsi+10h], 1
0x18000ba30  lea     rax, ??_7?$heap_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,std::tuple<IClassFactory>>'}
0x18000ba37  mov     [rsi], rax
0x18000ba3a  lea     rax, ??_7?$heap_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$root_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIClassFactory@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>'}
0x18000ba41  mov     [rsi+8], rax
0x18000ba45  mov     [rsp+0A8h+Buf1], rsi
0x18000ba4a  mov     cl, [r14+8]
0x18000ba4e  mov     dl, [r14+9]
0x18000ba52  mov     r8b, [r14+0Ah]
0x18000ba56  mov     r9b, [r14+0Bh]
0x18000ba5a  mov     r10b, [r14+0Ch]
0x18000ba5e  mov     r11b, [r14+0Dh]
0x18000ba62  mov     bl, [r14+0Eh]
0x18000ba66  mov     dil, [r14+0Fh]
0x18000ba6a  mov     eax, [r14]
0x18000ba6d  mov     dword ptr [rsp+0A8h+bstrString], eax
0x18000ba71  movzx   eax, word ptr [r14+4]
0x18000ba76  mov     word ptr [rsp+0A8h+bstrString+4], ax
0x18000ba7b  movzx   eax, word ptr [r14+6]
0x18000ba80  mov     word ptr [rsp+0A8h+bstrString+6], ax
0x18000ba85  mov     byte ptr [rsp+0A8h+var_58], cl
0x18000ba89  mov     byte ptr [rsp+0A8h+var_58+1], dl
0x18000ba8d  mov     byte ptr [rsp+0A8h+var_58+2], r8b
0x18000ba92  mov     byte ptr [rsp+0A8h+var_58+3], r9b
0x18000ba97  mov     byte ptr [rsp+0A8h+var_54], r10b
0x18000ba9c  mov     byte ptr [rsp+0A8h+var_54+1], r11b
0x18000baa1  mov     byte ptr [rsp+0A8h+var_54+2], bl
0x18000baa5  mov     byte ptr [rsp+0A8h+var_54+3], dil
0x18000baaa  mov     r8, r12
0x18000baad  lea     rdx, [rsp+0A8h+bstrString]
0x18000bab2  mov     rcx, rsi
0x18000bab5  mov     rax, cs:??_7?$heap_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@impl@winrt@@6B?$producers_base@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@V?$tuple@UIClassFactory@@@std@@@12@@; const winrt::impl::heap_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory>::`vftable'{for `winrt::impl::producers_base<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,std::tuple<IClassFactory>>'}
0x18000babc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac1  mov     ebx, eax
0x18000bac3  lea     rcx, [rsp+0A8h+Buf1]
0x18000bac8  call    ?unconditional_release_ref@?$com_ptr@UINetFwPolicy2@@@winrt@@AEAAXXZ; winrt::com_ptr<INetFwPolicy2>::unconditional_release_ref(void)
0x18000bacd  mov     eax, ebx
0x18000bacf  jmp     loc_18000BB54
0x18000bad4  mov     [rsp+0A8h+var_78], 0
0x18000badc  xorps   xmm0, xmm0
0x18000badf  movdqu  [rsp+0A8h+var_70], xmm0
0x18000bae5  mov     edx, 80040111h
0x18000baea  mov     [rsp+0A8h+bstrString], 0
0x18000baf3  mov     [rsp+0A8h+var_58], 0AABBCCDDh
0x18000bafb  mov     [rsp+0A8h+var_54], edx
0x18000baff  mov     [rsp+0A8h+var_50], 0
0x18000bb08  lea     r9, [rsp+0A8h+var_78]
0x18000bb0d  xor     r8d, r8d
0x18000bb10  lea     rcx, [rsp+0A8h+bstrString]
0x18000bb15  call    ?originate@hresult_error@winrt@@AEAAXUhresult@2@PEAXAEBUslim_source_location@impl@2@@Z; winrt::hresult_error::originate(winrt::hresult,void *,winrt::impl::slim_source_location const &)
0x18000bb1a  lea     rdx, [rsp+0A8h+Buf1]
0x18000bb1f  lea     rcx, [rsp+0A8h+bstrString]
0x18000bb24  call    ?to_abi@hresult_error@winrt@@QEBA?AUhresult@2@XZ; winrt::hresult_error::to_abi(void)
0x18000bb29  mov     ebx, [rax]
0x18000bb2b  cmp     [rsp+0A8h+var_50], 0
0x18000bb31  jz      short loc_18000BB3D
0x18000bb33  lea     rcx, [rsp+0A8h+var_50]
0x18000bb38  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000bb3d  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18000bb42  test    rcx, rcx
0x18000bb45  jz      short loc_18000BB4C
0x18000bb47  call    WINRT_IMPL_SysFreeString
0x18000bb4c  mov     eax, ebx
0x18000bb4e  jmp     short loc_18000BB54
0x18000bb50  mov     eax, dword ptr [rsp+0A8h+Buf1]
0x18000bb54  mov     rcx, [rsp+0A8h+var_48]
0x18000bb59  xor     rcx, rsp; StackCookie
0x18000bb5c  call    __security_check_cookie
0x18000bb61  add     rsp, 78h
0x18000bb65  pop     r15
0x18000bb67  pop     r14
0x18000bb69  pop     r12
0x18000bb6b  pop     rdi
0x18000bb6c  pop     rsi
0x18000bb6d  pop     rbx
0x18000bb6e  retn
```
