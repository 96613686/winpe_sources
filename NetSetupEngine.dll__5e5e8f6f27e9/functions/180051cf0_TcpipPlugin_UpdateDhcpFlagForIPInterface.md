# TcpipPlugin::UpdateDhcpFlagForIPInterface

- ea: `0x180051cf0`
- end: `0x180051f8d`
- name: `TcpipPlugin::UpdateDhcpFlagForIPInterface`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007c500`

## callees

- `0x180005580`
- `0x180012108`
- `0x180017320`
- `0x180027b38`
- `0x180029d20`
- `0x18002ebdc`
- `0x180040898`
- `0x1800433c4`
- `0x18005097c`
- `0x180051cf0`
- `0x18005b53c`
- `0x18005e238`
- `0x18005fb54`
- `0x180064704`
- `0x180065035`
- `0x18007c0e8`
- `0x18007c6b4`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051eae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180051eae`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TcpipPlugin::UpdateDhcpFlagForIPInterface(int a1, void **a2, __int64 a3)
{
  wchar_t *v6; // rdx
  int v7; // r8d
  __int64 v8; // rdx
  __int64 result; // rax
  __int64 v10; // rcx
  void *v11; // rdx
  void *v12; // r8
  HKEY CurrentControlSetRegistryHandle; // r15
  bool IsRegistryStateSeparated; // bl
  __int64 v15; // rcx
  int v16; // eax
  signed int v17; // eax
  void *Block_8[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-A0h]
  void **v20; // [rsp+70h] [rbp-98h] BYREF
  __int64 v21; // [rsp+78h] [rbp-90h] BYREF
  int v22; // [rsp+80h] [rbp-88h]
  struct _GUID v23; // [rsp+84h] [rbp-84h]
  __int64 v24; // [rsp+98h] [rbp-70h]
  _BYTE pExceptionObject[208]; // [rsp+A0h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+170h] [rbp+68h] BYREF
  _BYTE v27[8]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v28[40]; // [rsp+180h] [rbp+78h] BYREF
  WCHAR SubKey[264]; // [rsp+1A8h] [rbp+A0h] BYREF

  v24 = -2;
  v6 = (wchar_t *)L"ms_tcpip";
  if ( a1 )
    v6 = (wchar_t *)L"ms_tcpip6";
  std::wstring::wstring(&v20, v6);
  NetSetup2::details::TryGetObjectByIdentifierInner<NetSetup2::ProtocolDriver>((__int64)v27, (int)a2, v7, &v20);
  LOBYTE(v8) = 1;
  result = std::wstring::_Tidy(&v20, v8, 0);
  if ( v28[32] )
  {
    NetSetup2::details::TransactionBase::GetAllEnabledBindingPathsBetween(a2, Block_8, a3, v27);
    v12 = Block_8[1];
    v11 = Block_8[0];
    if ( Block_8[0] == Block_8[1] )
    {
      if ( !Block_8[0] )
        return std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v28);
    }
    else
    {
      v20 = a2;
      v21 = 0;
      v22 = 9;
      v23 = 0;
      CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v20);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v21);
      v20 = a2;
      v21 = 0;
      v22 = 1;
      v23 = NETSETUP_GLOBAL_ID;
      IsRegistryStateSeparated = NetSetup2::SystemGlobal::get_IsRegistryStateSeparated((NetSetup2::SystemGlobal *)&v20);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v21);
      if ( IsRegistryStateSeparated )
      {
        TcpipPlugin::SetInterfaceDHCPConfigurationV2(a2, a3, a1);
      }
      else
      {
        v15 = a3 + 20;
        if ( a1 )
        {
          if ( a1 != 1 )
          {
            HResultException::HResultException((HResultException *)pExceptionObject, -2147418113);
            throw (HResultException *)pExceptionObject;
          }
          TcpipPlugin::Getv6InterfacePathForAdapter(v15, SubKey);
        }
        else
        {
          TcpipPlugin::Getv4InterfacePathForAdapter(v15, SubKey);
        }
        phkResult = 0;
        v16 = RegCreateKeyExW(CurrentControlSetRegistryHandle, SubKey, 0, 0, 0, 2u, 0, &phkResult, 0);
        if ( v16 )
        {
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          HResultException::HResultException((HResultException *)pExceptionObject, v16);
          throw (HResultException *)pExceptionObject;
        }
        v17 = TcpipPlugin::SetInterfaceDHCPConfigurationV1(a3, phkResult);
        if ( v17 )
        {
          if ( v17 > 0 )
            v17 = (unsigned __int16)v17 | 0x80070000;
          HResultException::HResultException((HResultException *)pExceptionObject, v17);
          throw (HResultException *)pExceptionObject;
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      }
      v11 = Block_8[0];
      if ( !Block_8[0] )
        return std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v28);
      v12 = Block_8[1];
    }
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Destroy(v10, v11, v12);
    operator delete(Block_8[0]);
    v19 = 0;
    *(_OWORD *)Block_8 = 0;
    return std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v28);
  }
  return result;
}

```

## disassembly

```asm
0x180051cf0  mov     rax, rsp
0x180051cf3  push    rbp
0x180051cf4  push    rsi
0x180051cf5  push    rdi
0x180051cf6  push    r14
0x180051cf8  push    r15
0x180051cfa  lea     rbp, [rax-2E8h]
0x180051d01  sub     rsp, 3C0h
0x180051d08  mov     [rbp+2E0h+var_350], 0FFFFFFFFFFFFFFFEh
0x180051d10  mov     [rax+20h], rbx
0x180051d14  mov     rax, cs:__security_cookie
0x180051d1b  xor     rax, rsp
0x180051d1e  mov     [rbp+2E0h+var_30], rax
0x180051d25  mov     rsi, r8
0x180051d28  mov     r14, rdx
0x180051d2b  mov     edi, ecx
0x180051d2d  lea     rax, aMsTcpip6; "ms_tcpip6"
0x180051d34  lea     rdx, aMsTcpip; "ms_tcpip"
0x180051d3b  test    ecx, ecx
0x180051d3d  cmovnz  rdx, rax
0x180051d41  lea     rcx, [rsp+3E0h+var_378]
0x180051d46  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180051d4b  nop
0x180051d4c  lea     r9, [rsp+3E0h+var_378]
0x180051d51  mov     rdx, r14
0x180051d54  lea     rcx, [rbp+2E0h+var_270]
0x180051d58  call    ??$TryGetObjectByIdentifierInner@VProtocolDriver@NetSetup2@@@details@NetSetup2@@YA?AV?$Optional@VProtocolDriver@NetSetup2@@@01@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NetSetup2::details::TryGetObjectByIdentifierInner<NetSetup2::ProtocolDriver>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,std::wstring const &)
0x180051d5d  nop
0x180051d5e  xor     r8d, r8d
0x180051d61  mov     dl, 1
0x180051d63  lea     rcx, [rsp+3E0h+var_378]
0x180051d68  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180051d6d  cmp     [rbp+2E0h+var_248], 0
0x180051d74  jnz     short loc_180051D7B
0x180051d76  jmp     loc_180051F67
0x180051d7b  lea     r9, [rbp+2E0h+var_270]
0x180051d7f  mov     r8, rsi
0x180051d82  lea     rdx, [rsp+3E0h+Block+8]
0x180051d87  mov     rcx, r14
0x180051d8a  call    ?GetAllEnabledBindingPathsBetween@TransactionBase@details@NetSetup2@@QEAA?AV?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEBVActiveObject@3@0@Z; NetSetup2::details::TransactionBase::GetAllEnabledBindingPathsBetween(NetSetup2::ActiveObject const &,NetSetup2::ActiveObject const &)
0x180051d8f  nop
0x180051d90  mov     rdx, [rsp+3E0h+Block+8]
0x180051d95  mov     r8, [rsp+3E0h+var_388]
0x180051d9a  cmp     rdx, r8
0x180051d9d  jnz     short loc_180051DAD
0x180051d9f  test    rdx, rdx
0x180051da2  jz      loc_180051F5E
0x180051da8  jmp     loc_180051F3D
0x180051dad  xorps   xmm0, xmm0
0x180051db0  mov     [rsp+3E0h+var_378], r14
0x180051db5  mov     qword ptr [rsp+3E0h+var_370], 0
0x180051dbe  mov     dword ptr [rsp+3E0h+var_36C+4], 9
0x180051dc6  movdqu  xmmword ptr [rsp+3E0h+var_36C+8], xmm0
0x180051dcc  lea     rcx, [rsp+3E0h+var_378]; this
0x180051dd1  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180051dd6  mov     r15, rax
0x180051dd9  lea     rcx, [rsp+3E0h+var_370]
0x180051dde  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180051de3  mov     [rsp+3E0h+var_378], r14
0x180051de8  mov     qword ptr [rsp+3E0h+var_370], 0
0x180051df1  mov     dword ptr [rsp+3E0h+var_36C+4], 1
0x180051df9  movups  xmm0, xmmword ptr cs:NETSETUP_GLOBAL_ID.Data1
0x180051e00  movdqu  xmmword ptr [rsp+3E0h+var_36C+8], xmm0
0x180051e06  lea     rcx, [rsp+3E0h+var_378]; this
0x180051e0b  call    ?get_IsRegistryStateSeparated@SystemGlobal@NetSetup2@@QEBA_NXZ; NetSetup2::SystemGlobal::get_IsRegistryStateSeparated(void)
0x180051e10  mov     bl, al
0x180051e12  lea     rcx, [rsp+3E0h+var_370]
0x180051e17  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180051e1c  test    bl, bl
0x180051e1e  jnz     loc_180051F1F
0x180051e24  lea     rcx, [rsi+14h]
0x180051e28  test    edi, edi
0x180051e2a  jz      short loc_180051E5E
0x180051e2c  cmp     edi, 1
0x180051e2f  jz      short loc_180051E50
0x180051e31  mov     edx, 8000FFFFh; int
0x180051e36  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x180051e3a  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180051e3f  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180051e46  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x180051e4a  call    _CxxThrowException_0
0x180051e50  lea     rdx, [rbp+2E0h+SubKey]
0x180051e57  call    TcpipPlugin__Getv6InterfacePathForAdapter
0x180051e5c  jmp     short loc_180051E6B
0x180051e5e  lea     rdx, [rbp+2E0h+SubKey]
0x180051e65  call    TcpipPlugin__Getv4InterfacePathForAdapter
0x180051e6a  nop
0x180051e6b  mov     [rbp+2E0h+var_278], 0
0x180051e73  mov     qword ptr [rsp+40h], 0; lpdwDisposition
0x180051e7c  lea     rax, [rbp+2E0h+var_278]
0x180051e80  mov     [rsp+3E0h+phkResult], rax; phkResult
0x180051e85  mov     [rsp+3E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180051e8e  mov     [rsp+3E0h+samDesired], 2; samDesired
0x180051e96  mov     [rsp+3E0h+dwOptions], 0; dwOptions
0x180051e9e  xor     r9d, r9d; lpClass
0x180051ea1  xor     r8d, r8d; Reserved
0x180051ea4  lea     rdx, [rbp+2E0h+SubKey]; lpSubKey
0x180051eab  mov     rcx, r15; hKey
0x180051eae  call    cs:__imp_RegCreateKeyExW
0x180051eb4  test    eax, eax
0x180051eb6  jz      short loc_180051EDE
0x180051eb8  jle     short loc_180051EC2
0x180051eba  movzx   eax, ax
0x180051ebd  or      eax, 80070000h
0x180051ec2  mov     edx, eax; int
0x180051ec4  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x180051ec8  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180051ecd  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180051ed4  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x180051ed8  call    _CxxThrowException_0
0x180051ede  mov     rdx, [rbp+2E0h+var_278]
0x180051ee2  mov     rcx, rsi
0x180051ee5  call    TcpipPlugin__SetInterfaceDHCPConfigurationV1
0x180051eea  test    eax, eax
0x180051eec  jz      short loc_180051F14
0x180051eee  jle     short loc_180051EF8
0x180051ef0  movzx   eax, ax
0x180051ef3  or      eax, 80070000h
0x180051ef8  mov     edx, eax; int
0x180051efa  lea     rcx, [rbp+2E0h+pExceptionObject]; this
0x180051efe  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180051f03  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180051f0a  lea     rcx, [rbp+2E0h+pExceptionObject]; pExceptionObject
0x180051f0e  call    _CxxThrowException_0
0x180051f14  lea     rcx, [rbp+2E0h+var_278]
0x180051f18  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051f1d  jmp     short loc_180051F2E
0x180051f1f  mov     r8d, edi
0x180051f22  mov     rdx, rsi
0x180051f25  mov     rcx, r14
0x180051f28  call    TcpipPlugin__SetInterfaceDHCPConfigurationV2
0x180051f2d  nop
0x180051f2e  mov     rdx, [rsp+3E0h+Block+8]
0x180051f33  test    rdx, rdx
0x180051f36  jz      short loc_180051F5E
0x180051f38  mov     r8, [rsp+3E0h+var_388]
0x180051f3d  call    ?_Destroy@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Destroy(std::unique_ptr<NetSetup2::BindingPath> *,std::unique_ptr<NetSetup2::BindingPath> *)
0x180051f42  mov     rcx, [rsp+3E0h+Block+8]; Block
0x180051f47  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180051f4c  xorps   xmm0, xmm0
0x180051f4f  mov     [rsp+3E0h+var_380], 0
0x180051f58  movdqu  xmmword ptr [rsp+3E0h+Block+8], xmm0
0x180051f5e  lea     rcx, [rbp+2E0h+var_268]
0x180051f62  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180051f67  mov     rcx, [rbp+2E0h+var_30]
0x180051f6e  xor     rcx, rsp; StackCookie
0x180051f71  call    __security_check_cookie
0x180051f76  mov     rbx, [rsp+3E0h+arg_18]
0x180051f7e  add     rsp, 3C0h
0x180051f85  pop     r15
0x180051f87  pop     r14
0x180051f89  pop     rdi
0x180051f8a  pop     rsi
0x180051f8b  pop     rbp
0x180051f8c  retn
```
