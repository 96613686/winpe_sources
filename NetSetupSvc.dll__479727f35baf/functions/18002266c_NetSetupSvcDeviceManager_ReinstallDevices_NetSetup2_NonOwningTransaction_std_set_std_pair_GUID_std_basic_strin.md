# NetSetupSvcDeviceManager::ReinstallDevices(NetSetup2::NonOwningTransaction &,std::set<std::pair<_GUID,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,std::less<std::pair<_GUID,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>,std::allocator<std::pair<_GUID,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>> const &,void *,bool &)

- ea: `0x18002266c`
- end: `0x1800227f7`
- name: `?ReinstallDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@U?$less@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@V?$allocator@U?$pair@U_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@std@@PEAXAEA_N@Z`
- size: `395`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64 **, _QWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, installer_update`

## callers

- `0x180022fd4`

## callees

- `0x1800027c0`
- `0x1800082c0`
- `0x180008d94`
- `0x18000d954`
- `0x18000d974`
- `0x18000df60`
- `0x18001d8d8`
- `0x18001f2e4`
- `0x18002266c`
- `0x18002bba8`
- `0x18002c3e0`
- `0x18002c728`

## pseudocode

```c
__int64 __fastcall NetSetupSvcDeviceManager::ReinstallDevices(HKEY a1, __int64 a2, __int64 **a3, _QWORD *a4, _BYTE *a5)
{
  _QWORD *v5; // r15
  __int64 v6; // rsi
  HKEY v7; // r14
  __int64 result; // rax
  __int64 v9; // rdi
  bool v10; // bl
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // [rsp+0h] [rbp-F8h] BYREF
  _QWORD v18[2]; // [rsp+30h] [rbp-C8h] BYREF
  _BYTE *v19; // [rsp+40h] [rbp-B8h]
  HKEY v20; // [rsp+48h] [rbp-B0h]
  __int64 v21; // [rsp+50h] [rbp-A8h]
  _QWORD *v22; // [rsp+58h] [rbp-A0h]
  HResultException *v23; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v24[24]; // [rsp+68h] [rbp-90h] BYREF
  _BYTE v25[24]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v26[8]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v27[8]; // [rsp+A0h] [rbp-58h] BYREF
  _QWORD v28[4]; // [rsp+A8h] [rbp-50h] BYREF

  v5 = a4;
  v6 = a2;
  v7 = a1;
  v20 = a1;
  v21 = a2;
  v22 = a4;
  v19 = a5;
  result = **a3;
  v18[0] = result;
  while ( !*(_BYTE *)(result + 25) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v9 = result + 32;
      v18[1] = result + 32;
      NetSetup2::details::TransactionBase::GetNetworkInterfaceById(v6, v27, result + 32);
      v10 = HIDWORD(NetSetup2::ActiveObject::GetProperty(
                      (NetSetup2::ActiveObject *)v27,
                      (const struct _NETSETUPPROPKEY *)v24,
                      (unsigned int)NETSETUPPKEY_Interface_IfConnectorPresent).lpVtbl->Release) != 0;
      std::vector<unsigned char>::_Tidy((__int64)v25);
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_S(*(_QWORD *)(v12 + 16), 36, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v11);
        }
        std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v28);
      }
      else
      {
        v26[0] = 0;
        NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(
          v27,
          NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved,
          v26);
        NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)v27);
        NetSetupSvcDeviceManager::InstallNetworkInterfaces(v7, v6, v9 + 16, v5);
        std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v28);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &HResultException `RTTI Type Descriptor', &v23) )
      {
        v13 = &v17;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          WPP_SF_d_guid_S(*(_QWORD *)(v15 + 16), v16, v15, *((_DWORD *)v23 + 8), v16, v14);
        }
        *v19 = 0;
        v7 = v20;
        v6 = v21;
        v5 = v22;
        __eh34_try_continuation(0, &HResultException `RTTI Type Descriptor', &loc_1800227B5);
      }
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(
      v18,
      v13);
    result = v18[0];
  }
  return result;
}

```

## disassembly

```asm
0x18002266c  push    rbx
0x18002266e  push    rsi
0x18002266f  push    rdi
0x180022670  push    r14
0x180022672  push    r15
0x180022674  sub     rsp, 0D0h
0x18002267b  mov     rax, cs:__security_cookie
0x180022682  xor     rax, rsp
0x180022685  mov     [rsp+0F8h+var_30], rax
0x18002268d  mov     r15, r9
0x180022690  mov     rsi, rdx
0x180022693  mov     r14, rcx
0x180022696  mov     [rsp+0F8h+var_B0], rcx
0x18002269b  mov     [rsp+0F8h+var_A8], rdx
0x1800226a0  mov     [rsp+0F8h+var_A0], r9
0x1800226a5  mov     rax, [rsp+0F8h+arg_20]
0x1800226ad  mov     [rsp+0F8h+var_B8], rax
0x1800226b2  mov     rax, [r8]
0x1800226b5  mov     rax, [rax]
0x1800226b8  mov     [rsp+0F8h+var_C8], rax
0x1800226bd  cmp     byte ptr [rax+19h], 0
0x1800226c1  jnz     loc_1800227D8
0x1800226c7  lea     rdi, [rax+20h]
0x1800226cb  mov     [rsp+0F8h+var_C0], rdi
0x1800226d0  mov     r8, rdi
0x1800226d3  lea     rdx, [rsp+0F8h+var_58]
0x1800226db  mov     rcx, rsi
0x1800226de  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x1800226e3  nop
0x1800226e4  lea     r8, NETSETUPPKEY_Interface_IfConnectorPresent
0x1800226eb  lea     rdx, [rsp+0F8h+var_90]; struct _NETSETUPPROPKEY *
0x1800226f0  lea     rcx, [rsp+0F8h+var_58]; this
0x1800226f8  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x1800226fd  cmp     dword ptr [rax+14h], 0
0x180022701  setnz   bl
0x180022704  lea     rcx, [rsp+0F8h+var_78]
0x18002270c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180022711  test    bl, bl
0x180022713  jz      short loc_180022761
0x180022715  lea     rax, WPP_GLOBAL_Control
0x18002271c  mov     r10, cs:WPP_GLOBAL_Control
0x180022723  cmp     r10, rax
0x180022726  jz      short loc_180022751
0x180022728  cmp     byte ptr [r10+19h], 2
0x18002272d  jb      short loc_180022751
0x18002272f  lea     rcx, [rdi+10h]
0x180022733  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180022738  mov     edx, 24h ; '$'
0x18002273d  mov     r9, rax
0x180022740  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x180022747  mov     rcx, [r10+10h]
0x18002274b  call    WPP_SF_S
0x180022750  nop
0x180022751  lea     rcx, [rsp+0F8h+var_50]
0x180022759  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x18002275e  nop
0x18002275f  jmp     short loc_1800227C4
0x180022761  mov     [rsp+0F8h+var_60], 0
0x180022769  lea     r8, [rsp+0F8h+var_60]
0x180022771  lea     rdx, NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved
0x180022778  lea     rcx, [rsp+0F8h+var_58]
0x180022780  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x180022785  lea     rcx, [rsp+0F8h+var_58]; this
0x18002278d  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x180022792  lea     r8, [rdi+10h]
0x180022796  mov     r9, r15
0x180022799  mov     rdx, rsi
0x18002279c  mov     rcx, r14
0x18002279f  call    ?InstallNetworkInterfaces@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@Z; NetSetupSvcDeviceManager::InstallNetworkInterfaces(NetSetup2::NonOwningTransaction &,std::wstring const &,void *)
0x1800227a4  nop
0x1800227a5  lea     rcx, [rsp+0F8h+var_50]
0x1800227ad  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x1800227b2  nop
0x1800227b3  jmp     short loc_1800227C4
0x1800227b5  mov     r14, [rsp+0F8h+var_B0]
0x1800227ba  mov     rsi, [rsp+0F8h+var_A8]
0x1800227bf  mov     r15, [rsp+0F8h+var_A0]
0x1800227c4  lea     rcx, [rsp+0F8h+var_C8]
0x1800227c9  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(void)
0x1800227ce  mov     rax, [rsp+0F8h+var_C8]
0x1800227d3  jmp     loc_1800226BD
0x1800227d8  mov     rcx, [rsp+0F8h+var_30]
0x1800227e0  xor     rcx, rsp; StackCookie
0x1800227e3  call    __security_check_cookie
0x1800227e8  add     rsp, 0D0h
0x1800227ef  pop     r15
0x1800227f1  pop     r14
0x1800227f3  pop     rdi
0x1800227f4  pop     rsi
0x1800227f5  pop     rbx
0x1800227f6  retn
```
