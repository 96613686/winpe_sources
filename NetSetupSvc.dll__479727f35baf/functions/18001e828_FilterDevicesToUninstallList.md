# FilterDevicesToUninstallList

- ea: `0x18001e828`
- end: `0x18001ea3e`
- name: `FilterDevicesToUninstallList`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update`

## callers

- `0x18001eb14`

## callees

- `0x1800027c0`
- `0x180006e34`
- `0x180008d94`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x180010284`
- `0x1800182b0`
- `0x18001c384`
- `0x18001c6b4`
- `0x18001d0d8`
- `0x18001d6f4`
- `0x18001e828`
- `0x18001f1cc`
- `0x180023e7c`
- `0x1800244a4`
- `0x180027d2c`
- `0x1800286d8`
- `0x180029528`
- `0x1800295e0`
- `0x180029840`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FilterDevicesToUninstallList(__int64 a1, _QWORD *a2)
{
  char *KtmHandle; // r15
  __int64 *v4; // rdi
  __int64 *v5; // r14
  __int64 ValueString; // rax
  char v7; // bl
  __int64 v8; // rax
  __int64 v9; // r10
  __int64 v10; // rbx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  _BYTE v13[16]; // [rsp+30h] [rbp-99h] BYREF
  __int64 v14; // [rsp+40h] [rbp-89h]
  HKEY v15; // [rsp+50h] [rbp-79h] BYREF
  __int128 v16; // [rsp+58h] [rbp-71h] BYREF
  __int64 v17; // [rsp+68h] [rbp-61h] BYREF
  __int64 v18; // [rsp+70h] [rbp-59h] BYREF
  int v19; // [rsp+78h] [rbp-51h]
  __int128 v20; // [rsp+7Ch] [rbp-4Dh]
  NetSetupDevice *v21; // [rsp+90h] [rbp-39h] BYREF
  NetSetupDevice *v22; // [rsp+98h] [rbp-31h]

  v17 = a1;
  v18 = 0;
  v19 = 9;
  v20 = 0;
  KtmHandle = (char *)NetSetup2::TransactionObject::get_KtmHandle((NetSetup2::TransactionObject *)&v17);
  std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(&v18);
  NetDevices::NetDevices((NetDevices *)&v21);
  v4 = (__int64 *)v21;
  v5 = (__int64 *)v22;
  if ( v21 != v22 )
  {
    do
    {
      if ( NetSetupDevice::IsAvailable((NetSetupDevice *)v4)
        && NetSetupDevice::IsPnpSoftwareKeyAvailable((NetSetupDevice *)v4) )
      {
        std::wstring::wstring((__int64)&v17, v4[1]);
        NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v4, (RegistryKey *)&v15, 1u, KtmHandle);
        if ( RegistryKey::ValueExists((RegistryKey *)&v15, L"NetSetupAnticipatedInstanceId") )
        {
          v16 = 0;
          ValueString = RegistryKey::GetValueString(&v15, (__int64)v13, L"NetSetupAnticipatedInstanceId", 0);
          v7 = GuidFromString(ValueString, &v16);
          std::wstring::_Tidy_deallocate((__int64)v13);
          if ( v7 )
          {
            std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Find_lower_bound<_GUID>(
              a2,
              v13,
              &v16);
            v10 = v14;
            if ( (unsigned __int8)std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Lower_bound_duplicate<_GUID>(
                                    v11,
                                    v14,
                                    &v16)
              && v10 != *a2 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                WPP_SF__guid_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  WPP_ebd892180d513f9593fffe48317335f2_Traceguids,
                  &v16);
              v12 = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Extract(a2, v10);
              std::_Deallocate<16>(v12, 0x30u);
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
            WPP_SF_S(*(_QWORD *)(v9 + 16), 13, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v8);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
        std::wstring::_Tidy_deallocate((__int64)&v17);
      }
      v4 += 2;
    }
    while ( v4 != v5 );
  }
  NetDevices::~NetDevices((NetDevices *)&v21);
}

```

## disassembly

```asm
0x18001e828  mov     [rsp-8+arg_0], rbx
0x18001e82d  mov     [rsp-8+arg_10], rsi
0x18001e832  push    rbp
0x18001e833  push    rdi
0x18001e834  push    r12
0x18001e836  push    r14
0x18001e838  push    r15
0x18001e83a  lea     rbp, [rsp-37h]
0x18001e83f  sub     rsp, 100h
0x18001e846  mov     rax, cs:__security_cookie
0x18001e84d  xor     rax, rsp
0x18001e850  mov     [rbp+57h+var_30], rax
0x18001e854  mov     rsi, rdx
0x18001e857  xorps   xmm0, xmm0
0x18001e85a  mov     [rbp+57h+var_B8], rcx
0x18001e85e  mov     [rbp+57h+var_B0], 0
0x18001e866  mov     [rbp+57h+var_A8], 9
0x18001e86d  movdqu  [rbp+57h+var_A4], xmm0
0x18001e872  lea     rcx, [rbp+57h+var_B8]; this
0x18001e876  call    ?get_KtmHandle@TransactionObject@NetSetup2@@QEBAPEAXXZ; NetSetup2::TransactionObject::get_KtmHandle(void)
0x18001e87b  mov     r15, rax
0x18001e87e  lea     rcx, [rbp+57h+var_B0]
0x18001e882  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18001e887  lea     rcx, [rbp+57h+var_90]; this
0x18001e88b  call    ??0NetDevices@@QEAA@XZ; NetDevices::NetDevices(void)
0x18001e890  nop
0x18001e891  mov     rdi, [rbp+57h+var_90]
0x18001e895  mov     r14, [rbp+57h+var_88]
0x18001e899  cmp     rdi, r14
0x18001e89c  jz      loc_18001EA0D
0x18001e8a2  lea     r12, WPP_GLOBAL_Control
0x18001e8a9  mov     rcx, rdi; this
0x18001e8ac  call    ?IsAvailable@NetSetupDevice@@QEAA_NXZ; NetSetupDevice::IsAvailable(void)
0x18001e8b1  test    al, al
0x18001e8b3  jz      loc_18001EA00
0x18001e8b9  mov     rcx, rdi; this
0x18001e8bc  call    ?IsPnpSoftwareKeyAvailable@NetSetupDevice@@QEAA_NXZ; NetSetupDevice::IsPnpSoftwareKeyAvailable(void)
0x18001e8c1  test    al, al
0x18001e8c3  jz      loc_18001EA00
0x18001e8c9  mov     rdx, [rdi+8]
0x18001e8cd  lea     rcx, [rbp+57h+var_B8]
0x18001e8d1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001e8d6  nop
0x18001e8d7  mov     r9, r15
0x18001e8da  mov     r8d, 1
0x18001e8e0  lea     rdx, [rbp+57h+var_D0]
0x18001e8e4  mov     rcx, rdi
0x18001e8e7  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x18001e8ec  nop
0x18001e8ed  lea     rdx, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001e8f4  lea     rcx, [rbp+57h+var_D0]; this
0x18001e8f8  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001e8fd  test    al, al
0x18001e8ff  jz      loc_18001E9ED
0x18001e905  xorps   xmm0, xmm0
0x18001e908  movups  [rbp+57h+var_C8], xmm0
0x18001e90c  xor     r9d, r9d
0x18001e90f  lea     r8, aNetsetupantici; "NetSetupAnticipatedInstanceId"
0x18001e916  lea     rdx, [rsp+120h+var_F0]
0x18001e91b  lea     rcx, [rbp+57h+var_D0]
0x18001e91f  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001e924  lea     rdx, [rbp+57h+var_C8]
0x18001e928  mov     rcx, rax
0x18001e92b  call    ?GuidFromString@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z; GuidFromString(std::wstring const &,_GUID &)
0x18001e930  mov     bl, al
0x18001e932  lea     rcx, [rsp+120h+var_F0]
0x18001e937  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e93c  test    bl, bl
0x18001e93e  jnz     short loc_18001E97E
0x18001e940  mov     r10, cs:WPP_GLOBAL_Control
0x18001e947  cmp     r10, r12
0x18001e94a  jz      loc_18001E9ED
0x18001e950  cmp     byte ptr [r10+19h], 2
0x18001e955  jb      loc_18001E9ED
0x18001e95b  lea     rcx, [rbp+57h+var_B8]
0x18001e95f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e964  mov     r9, rax
0x18001e967  mov     edx, 0Dh
0x18001e96c  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001e973  mov     rcx, [r10+10h]
0x18001e977  call    WPP_SF_S
0x18001e97c  jmp     short loc_18001E9ED
0x18001e97e  lea     r8, [rbp+57h+var_C8]
0x18001e982  lea     rdx, [rsp+120h+var_F0]
0x18001e987  mov     rcx, rsi
0x18001e98a  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18001e98f  lea     r8, [rbp+57h+var_C8]
0x18001e993  mov     rbx, [rsp+120h+var_E0]
0x18001e998  mov     rdx, rbx
0x18001e99b  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U_GUID@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<_GUID,void *> * const,_GUID const &)
0x18001e9a0  test    al, al
0x18001e9a2  jz      short loc_18001E9ED
0x18001e9a4  cmp     rbx, [rsi]
0x18001e9a7  jz      short loc_18001E9ED
0x18001e9a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9b0  cmp     rcx, r12
0x18001e9b3  jz      short loc_18001E9D4
0x18001e9b5  cmp     byte ptr [rcx+19h], 4
0x18001e9b9  jb      short loc_18001E9D4
0x18001e9bb  mov     edx, 0Eh
0x18001e9c0  lea     r9, [rbp+57h+var_C8]
0x18001e9c4  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001e9cb  mov     rcx, [rcx+10h]
0x18001e9cf  call    WPP_SF__guid_
0x18001e9d4  mov     rdx, rbx
0x18001e9d7  mov     rcx, rsi
0x18001e9da  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@QEAAPEAU?$_Tree_node@U_GUID@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<_GUID>>,std::_Iterator_base0>)
0x18001e9df  mov     edx, 30h ; '0'
0x18001e9e4  mov     rcx, rax
0x18001e9e7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e9ec  nop
0x18001e9ed  lea     rcx, [rbp+57h+var_D0]
0x18001e9f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001e9f6  nop
0x18001e9f7  lea     rcx, [rbp+57h+var_B8]
0x18001e9fb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ea00  add     rdi, 10h
0x18001ea04  cmp     rdi, r14
0x18001ea07  jnz     loc_18001E8A9
0x18001ea0d  lea     rcx, [rbp+57h+var_90]; this
0x18001ea11  call    ??1NetDevices@@QEAA@XZ; NetDevices::~NetDevices(void)
0x18001ea16  mov     rcx, [rbp+57h+var_30]
0x18001ea1a  xor     rcx, rsp; StackCookie
0x18001ea1d  call    __security_check_cookie
0x18001ea22  lea     r11, [rsp+120h+var_20]
0x18001ea2a  mov     rbx, [r11+30h]
0x18001ea2e  mov     rsi, [r11+40h]
0x18001ea32  mov     rsp, r11
0x18001ea35  pop     r15
0x18001ea37  pop     r14
0x18001ea39  pop     r12
0x18001ea3b  pop     rdi
0x18001ea3c  pop     rbp
0x18001ea3d  retn
```
