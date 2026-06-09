# CreateNetworkInterfaces

- ea: `0x18001e3a8`
- end: `0x18001e72d`
- name: `CreateNetworkInterfaces`
- size: `901`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001f2e4`
- `0x180023718`

## callees

- `0x1800027c0`
- `0x180006e34`
- `0x180008348`
- `0x180008d94`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x180010284`
- `0x18001976c`
- `0x18001a994`
- `0x18001b168`
- `0x18001d258`
- `0x18001d780`
- `0x18001e3a8`
- `0x18001e734`
- `0x18001f1cc`
- `0x180021650`
- `0x180024cdc`
- `0x180026a10`
- `0x180026cb8`
- `0x1800271f0`
- `0x180027ef4`
- `0x18002d8e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LSTATUS __fastcall CreateNetworkInterfaces(__int64 a1, HKEY a2, HKEY *a3, __int64 a4, void *a5)
{
  unsigned int v8; // edi
  __int64 i; // rbx
  __int64 v10; // r12
  const wchar_t *v11; // rax
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // rax
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  const WCHAR *v17; // rax
  __int64 v19; // rax
  __int64 v20; // r8
  const wchar_t *v21; // rax
  __int64 v22; // [rsp+0h] [rbp-118h] BYREF
  HKEY v23; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-D0h] BYREF
  HKEY v25; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+60h] [rbp-B8h] BYREF
  __int128 v27; // [rsp+68h] [rbp-B0h] BYREF
  _QWORD v28[3]; // [rsp+78h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+90h] [rbp-88h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-78h]
  _BYTE v31[8]; // [rsp+A8h] [rbp-70h] BYREF
  _QWORD v32[4]; // [rsp+B0h] [rbp-68h] BYREF
  _BYTE v33[8]; // [rsp+D0h] [rbp-48h] BYREF

  v23 = a2;
  RegistryKey::OpenSubKey(a3, (RegistryKey *)&v25, L"NetworkInterface", 131101, a5);
  v8 = 0;
  RegistryKey::GetSubKeyNames(&v25, &v29);
  v10 = *((_QWORD *)&v29 + 1);
  for ( i = v29; ; i += 32 )
  {
    v26 = i;
    if ( i == v10 )
      break;
    NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate((NetSetup2::NetworkInterfaceTemplate *)v28);
    ReadNetworkInterfacePropertiesFromDriver(a1, (__int64)a2, (char *)a5, (__int64)v28);
    v27 = 0;
    if ( (unsigned __int8)GuidFromString(i, &v27) )
    {
      NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(a1, v31, &v27);
      if ( v33[0] )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF__guid_S(*(_QWORD *)(v15 + 16), 56, v15, (unsigned int)&v27, v14);
        }
        try
        {
          v24[0] = v28;
          NetSetup2::ActiveObject::ActiveObjectTmpl_NetSetup2::NetworkInterface_::BatchPropertyChanges__lambda_199237f52d822df65919a1d370e41654___(
            v33,
            v24,
            0xAAAAAAAAAAAAAAABuLL * ((__int64)(v28[1] - v28[0]) >> 4) + 5);
          ++v8;
        }
        catch ( ... )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
            WPP_SF__guid_S(*(_QWORD *)(v20 + 16), 57, v20, (unsigned int)&v22 + 104, v19);
          }
          NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)v31);
          v21 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          RegistryKey::DeleteSubKey((RegistryKey *)&v25, v21);
          throw;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, &v27);
        v16 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        RegistryKey::DeleteSubKey((RegistryKey *)&v25, v16);
      }
      if ( v33[0] )
      {
        std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v32);
        v33[0] = 0;
      }
    }
    else
    {
      v11 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      RegistryKey::DeleteSubKey((RegistryKey *)&v25, v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v12 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
        WPP_SF_S(*(_QWORD *)(v13 + 16), 55, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v12);
      }
    }
    NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate((NetSetup2::ObjectCreationTemplate *)v28);
  }
  while ( v8 < (unsigned __int64)(a4 - 1) )
  {
    NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate((NetSetup2::NetworkInterfaceTemplate *)v28);
    ReadNetworkInterfacePropertiesFromDriver(a1, (__int64)a2, (char *)a5, (__int64)v28);
    LODWORD(v26) = ++v8;
    NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
      (__int64)v28,
      (__int128 *)NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber,
      (__int64)&v26);
    v27 = *(_OWORD *)CreateNewNetworkInterface(v24, a1, v28, a2);
    StringFromGuid(v31, &v27);
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    RegistryKey::CreateSubKey(&v25, (RegistryKey *)&v23, v17, 2u, a5);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
    std::wstring::_Tidy_deallocate((__int64)v31);
    NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate((NetSetup2::ObjectCreationTemplate *)v28);
  }
  if ( (_QWORD)v29 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v29);
    std::_Deallocate<16>((_QWORD *)v29, (v30 - v29) & 0xFFFFFFFFFFFFFFE0uLL);
    v29 = 0;
    v30 = 0;
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
}

```

## disassembly

```asm
0x18001e3a8  push    rbx
0x18001e3aa  push    rsi
0x18001e3ab  push    rdi
0x18001e3ac  push    r12
0x18001e3ae  push    r13
0x18001e3b0  push    r14
0x18001e3b2  push    r15
0x18001e3b4  sub     rsp, 0E0h
0x18001e3bb  mov     rax, cs:__security_cookie
0x18001e3c2  xor     rax, rsp
0x18001e3c5  mov     [rsp+118h+var_40], rax
0x18001e3cd  mov     r13, r9
0x18001e3d0  mov     rax, r8
0x18001e3d3  mov     rsi, rdx
0x18001e3d6  mov     r14, rcx
0x18001e3d9  mov     [rsp+118h+var_D8], rdx
0x18001e3de  mov     r15, [rsp+118h+arg_20]
0x18001e3e6  mov     [rsp+118h+var_F8], r15
0x18001e3eb  mov     r9d, 2001Dh
0x18001e3f1  lea     r8, aNetworkinterfa_2; "NetworkInterface"
0x18001e3f8  lea     rdx, [rsp+118h+var_C0]
0x18001e3fd  mov     rcx, rax
0x18001e400  call    ?OpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::OpenSubKey(wchar_t const *,ulong,void *)
0x18001e405  nop
0x18001e406  xor     edi, edi
0x18001e408  lea     rdx, [rsp+118h+var_88]
0x18001e410  lea     rcx, [rsp+118h+var_C0]
0x18001e415  call    ?GetSubKeyNames@RegistryKey@@QEBA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@XZ; RegistryKey::GetSubKeyNames(void)
0x18001e41a  nop
0x18001e41b  mov     rbx, qword ptr [rsp+118h+var_88]
0x18001e423  mov     r12, qword ptr [rsp+118h+var_88+8]
0x18001e42b  mov     [rsp+118h+var_B8], rbx
0x18001e430  cmp     rbx, r12
0x18001e433  jz      loc_18001E5E6
0x18001e439  lea     rcx, [rsp+118h+var_A0]; this
0x18001e43e  call    ??0NetworkInterfaceTemplate@NetSetup2@@QEAA@XZ; NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate(void)
0x18001e443  nop
0x18001e444  lea     r9, [rsp+118h+var_A0]
0x18001e449  mov     r8, r15
0x18001e44c  mov     rdx, rsi
0x18001e44f  mov     rcx, r14
0x18001e452  call    ReadNetworkInterfacePropertiesFromDriver
0x18001e457  xorps   xmm0, xmm0
0x18001e45a  movups  [rsp+118h+var_B0], xmm0
0x18001e45f  lea     rdx, [rsp+118h+var_B0]
0x18001e464  mov     rcx, rbx
0x18001e467  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001e46c  test    al, al
0x18001e46e  jnz     short loc_18001E4CC
0x18001e470  mov     rcx, rbx
0x18001e473  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e478  mov     rdx, rax; wchar_t *
0x18001e47b  lea     rcx, [rsp+118h+var_C0]; this
0x18001e480  call    ?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteSubKey(wchar_t const *)
0x18001e485  mov     r10, cs:WPP_GLOBAL_Control
0x18001e48c  lea     rax, WPP_GLOBAL_Control
0x18001e493  cmp     r10, rax
0x18001e496  jz      loc_18001E5D3
0x18001e49c  cmp     byte ptr [r10+19h], 3
0x18001e4a1  jb      loc_18001E5D3
0x18001e4a7  mov     rcx, rbx
0x18001e4aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e4af  mov     edx, 37h ; '7'
0x18001e4b4  mov     r9, rax
0x18001e4b7  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001e4be  mov     rcx, [r10+10h]
0x18001e4c2  call    WPP_SF_S
0x18001e4c7  jmp     loc_18001E5D3
0x18001e4cc  lea     r8, [rsp+118h+var_B0]
0x18001e4d1  lea     rdx, [rsp+118h+var_70]
0x18001e4d9  mov     rcx, r14
0x18001e4dc  call    ?TryGetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AV?$Optional@VNetworkInterface@NetSetup2@@@23@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::TryGetNetworkInterfaceById(_GUID const &)
0x18001e4e1  nop
0x18001e4e2  cmp     [rsp+118h+var_48], 0
0x18001e4ea  jz      short loc_18001E56B
0x18001e4ec  mov     r8, cs:WPP_GLOBAL_Control
0x18001e4f3  lea     rax, WPP_GLOBAL_Control
0x18001e4fa  cmp     r8, rax
0x18001e4fd  jz      short loc_18001E527
0x18001e4ff  cmp     byte ptr [r8+19h], 4
0x18001e504  jb      short loc_18001E527
0x18001e506  mov     rcx, rsi
0x18001e509  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e50e  mov     edx, 38h ; '8'
0x18001e513  mov     [rsp+118h+var_F8], rax
0x18001e518  lea     r9, [rsp+118h+var_B0]
0x18001e51d  mov     rcx, [r8+10h]
0x18001e521  call    WPP_SF__guid_S
0x18001e526  nop
0x18001e527  lea     rax, [rsp+118h+var_A0]
0x18001e52c  mov     [rsp+118h+var_D0], rax
0x18001e531  mov     r8, [rsp+118h+var_98]
0x18001e539  sub     r8, [rsp+118h+var_A0]
0x18001e53e  sar     r8, 4
0x18001e542  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001e54c  imul    r8, rax
0x18001e550  add     r8, 5
0x18001e554  lea     rdx, [rsp+118h+var_D0]
0x18001e559  lea     rcx, [rsp+118h+var_48]
0x18001e561  call    NetSetup2__ActiveObject__ActiveObjectTmpl_NetSetup2__NetworkInterface___BatchPropertyChanges__lambda_199237f52d822df65919a1d370e41654___
0x18001e566  nop
0x18001e567  inc     edi
0x18001e569  jmp     short loc_18001E5B4
0x18001e56b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e572  lea     rax, WPP_GLOBAL_Control
0x18001e579  cmp     rcx, rax
0x18001e57c  jz      short loc_18001E59E
0x18001e57e  cmp     byte ptr [rcx+19h], 3
0x18001e582  jb      short loc_18001E59E
0x18001e584  mov     edx, 3Ah ; ':'
0x18001e589  lea     r9, [rsp+118h+var_B0]
0x18001e58e  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001e595  mov     rcx, [rcx+10h]
0x18001e599  call    WPP_SF__guid_
0x18001e59e  mov     rcx, rbx
0x18001e5a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e5a6  mov     rdx, rax; wchar_t *
0x18001e5a9  lea     rcx, [rsp+118h+var_C0]; this
0x18001e5ae  call    ?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteSubKey(wchar_t const *)
0x18001e5b3  nop
0x18001e5b4  cmp     [rsp+118h+var_48], 0
0x18001e5bc  jz      short loc_18001E5D3
0x18001e5be  lea     rcx, [rsp+118h+var_68]
0x18001e5c6  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001e5cb  mov     [rsp+118h+var_48], 0
0x18001e5d3  lea     rcx, [rsp+118h+var_A0]; this
0x18001e5d8  call    ??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)
0x18001e5dd  add     rbx, 20h ; ' '
0x18001e5e1  jmp     loc_18001E42B
0x18001e5e6  lea     rbx, [r13-1]
0x18001e5ea  jmp     loc_18001E6A7
0x18001e5ef  lea     rcx, [rsp+118h+var_A0]; this
0x18001e5f4  call    ??0NetworkInterfaceTemplate@NetSetup2@@QEAA@XZ; NetSetup2::NetworkInterfaceTemplate::NetworkInterfaceTemplate(void)
0x18001e5f9  nop
0x18001e5fa  lea     r9, [rsp+118h+var_A0]
0x18001e5ff  mov     r8, r15
0x18001e602  mov     rdx, rsi
0x18001e605  mov     rcx, r14
0x18001e608  call    ReadNetworkInterfacePropertiesFromDriver
0x18001e60d  inc     edi
0x18001e60f  mov     dword ptr [rsp+118h+var_B8], edi
0x18001e613  lea     r8, [rsp+118h+var_B8]
0x18001e618  lea     rdx, NETSETUPPKEY_Interface_PnpDeviceInterfaceNumber
0x18001e61f  lea     rcx, [rsp+118h+var_A0]
0x18001e624  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x18001e629  mov     r9, rsi
0x18001e62c  lea     r8, [rsp+118h+var_A0]
0x18001e631  mov     rdx, r14
0x18001e634  lea     rcx, [rsp+118h+var_D0]
0x18001e639  call    CreateNewNetworkInterface
0x18001e63e  movups  xmm0, xmmword ptr [rax]
0x18001e641  movdqu  [rsp+118h+var_B0], xmm0
0x18001e647  lea     rdx, [rsp+118h+var_B0]
0x18001e64c  lea     rcx, [rsp+118h+var_70]
0x18001e654  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x18001e659  nop
0x18001e65a  lea     rcx, [rsp+118h+var_70]
0x18001e662  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e667  mov     r8, rax
0x18001e66a  mov     [rsp+118h+var_F8], r15
0x18001e66f  mov     r9d, 2
0x18001e675  lea     rdx, [rsp+118h+var_D8]
0x18001e67a  lea     rcx, [rsp+118h+var_C0]
0x18001e67f  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x18001e684  lea     rcx, [rsp+118h+var_D8]
0x18001e689  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e68e  nop
0x18001e68f  lea     rcx, [rsp+118h+var_70]
0x18001e697  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e69c  nop
0x18001e69d  lea     rcx, [rsp+118h+var_A0]; this
0x18001e6a2  call    ??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)
0x18001e6a7  mov     eax, edi
0x18001e6a9  cmp     rax, rbx
0x18001e6ac  jb      loc_18001E5EF
0x18001e6b2  mov     rcx, qword ptr [rsp+118h+var_88]
0x18001e6ba  test    rcx, rcx
0x18001e6bd  jz      short loc_18001E700
0x18001e6bf  mov     rdx, qword ptr [rsp+118h+var_88+8]
0x18001e6c7  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18001e6cc  mov     rcx, qword ptr [rsp+118h+var_88]
0x18001e6d4  mov     rdx, [rsp+118h+var_78]
0x18001e6dc  sub     rdx, rcx
0x18001e6df  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001e6e3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e6e8  xorps   xmm0, xmm0
0x18001e6eb  movdqu  [rsp+118h+var_88], xmm0
0x18001e6f4  mov     [rsp+118h+var_78], 0
0x18001e700  lea     rcx, [rsp+118h+var_C0]
0x18001e705  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e70a  mov     rcx, [rsp+118h+var_40]
0x18001e712  xor     rcx, rsp; StackCookie
0x18001e715  call    __security_check_cookie
0x18001e71a  add     rsp, 0E0h
0x18001e721  pop     r15
0x18001e723  pop     r14
0x18001e725  pop     r13
0x18001e727  pop     r12
0x18001e729  pop     rdi
0x18001e72a  pop     rsi
0x18001e72b  pop     rbx
0x18001e72c  retn
```
