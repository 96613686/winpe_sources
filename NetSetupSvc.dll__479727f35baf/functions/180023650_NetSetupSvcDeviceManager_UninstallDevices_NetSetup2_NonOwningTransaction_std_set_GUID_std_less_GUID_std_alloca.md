# NetSetupSvcDeviceManager::UninstallDevices(NetSetup2::NonOwningTransaction &,std::set<_GUID,std::less<_GUID>,std::allocator<_GUID>> const &,bool &)

- ea: `0x180023650`
- end: `0x180023710`
- name: `?UninstallDevices@NetSetupSvcDeviceManager@@AEAAXAEAVNonOwningTransaction@NetSetup2@@AEBV?$set@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@@std@@AEA_N@Z`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x180022fd4`

## callees

- `0x1800027c0`
- `0x1800082c0`
- `0x180008d94`
- `0x18001d92c`
- `0x180023650`
- `0x18002459c`
- `0x18002bba8`
- `0x18002c3e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NetSetupSvcDeviceManager::UninstallDevices(__int64 a1, __int64 a2, __int64 **a3, _BYTE *a4)
{
  __int64 v4; // rbx
  __int64 result; // rax
  _BYTE *v6; // rdx
  int v7; // r8d
  _BYTE v8[48]; // [rsp+0h] [rbp-98h] BYREF
  __int64 v9; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+38h] [rbp-60h]
  _BYTE *v11; // [rsp+40h] [rbp-58h]
  __int64 v12; // [rsp+48h] [rbp-50h]
  HResultException *v13; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v14[8]; // [rsp+58h] [rbp-40h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-38h] BYREF
  _QWORD v16[4]; // [rsp+68h] [rbp-30h] BYREF

  v4 = a2;
  v12 = a2;
  v11 = a4;
  result = **a3;
  v9 = result;
  while ( !*(_BYTE *)(result + 25) )
  {
    try
    {
      v10 = result + 28;
      NetSetup2::details::TransactionBase::GetNetworkInterfaceById(v4, v15, result + 28);
      v14[0] = 0;
      NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(
        v15,
        NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved,
        v14);
      if ( NetSetup2::NetworkInterface::get_RemoveInterfaceWhenPnpDeviceRemoved((NetSetup2::NetworkInterface *)v15) )
        NetSetup2::ActiveObject::Delete((NetSetup2::ActiveObject *)v15);
      std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(v16);
    }
    catch ( HResultException *v13 )
    {
      v6 = v8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_D_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)v8, v7, *((_DWORD *)v13 + 8), v10);
      *v11 = 0;
      v4 = v12;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<_GUID>>,std::_Iterator_base0>::operator++(
      &v9,
      v6);
    result = v9;
  }
  return result;
}

```

## disassembly

```asm
0x180023650  push    rbx
0x180023652  sub     rsp, 90h
0x180023659  mov     rax, cs:__security_cookie
0x180023660  xor     rax, rsp
0x180023663  mov     [rsp+98h+var_10], rax
0x18002366b  mov     rbx, rdx
0x18002366e  mov     [rsp+98h+var_50], rdx
0x180023673  mov     [rsp+98h+var_58], r9
0x180023678  mov     rax, [r8]
0x18002367b  mov     rax, [rax]
0x18002367e  mov     [rsp+98h+var_68], rax
0x180023683  cmp     byte ptr [rax+19h], 0
0x180023687  jnz     short loc_1800236F7
0x180023689  lea     r8, [rax+1Ch]
0x18002368d  mov     [rsp+98h+var_60], r8
0x180023692  lea     rdx, [rsp+98h+var_38]
0x180023697  mov     rcx, rbx
0x18002369a  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x18002369f  nop
0x1800236a0  mov     [rsp+98h+var_40], 0
0x1800236a5  lea     r8, [rsp+98h+var_40]
0x1800236aa  lea     rdx, NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved
0x1800236b1  lea     rcx, [rsp+98h+var_38]
0x1800236b6  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x1800236bb  lea     rcx, [rsp+98h+var_38]; this
0x1800236c0  call    ?get_RemoveInterfaceWhenPnpDeviceRemoved@NetworkInterface@NetSetup2@@QEBA_NXZ; NetSetup2::NetworkInterface::get_RemoveInterfaceWhenPnpDeviceRemoved(void)
0x1800236c5  test    al, al
0x1800236c7  jz      short loc_1800236D4
0x1800236c9  lea     rcx, [rsp+98h+var_38]; this
0x1800236ce  call    ?Delete@ActiveObject@NetSetup2@@QEAAXXZ; NetSetup2::ActiveObject::Delete(void)
0x1800236d3  nop
0x1800236d4  lea     rcx, [rsp+98h+var_30]
0x1800236d9  call    ??1?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::vector<NetSetup2::Property>>::~unique_ptr<std::vector<NetSetup2::Property>>(void)
0x1800236de  nop
0x1800236df  jmp     short loc_1800236E6
0x1800236e1  mov     rbx, [rsp+98h+var_50]
0x1800236e6  lea     rcx, [rsp+98h+var_68]
0x1800236eb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<_GUID>>,std::_Iterator_base0>::operator++(void)
0x1800236f0  mov     rax, [rsp+98h+var_68]
0x1800236f5  jmp     short loc_180023683
0x1800236f7  mov     rcx, [rsp+98h+var_10]
0x1800236ff  xor     rcx, rsp; StackCookie
0x180023702  call    __security_check_cookie
0x180023707  add     rsp, 90h
0x18002370e  pop     rbx
0x18002370f  retn
```
