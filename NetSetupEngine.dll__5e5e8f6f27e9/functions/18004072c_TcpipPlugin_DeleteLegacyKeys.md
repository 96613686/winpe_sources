# TcpipPlugin::DeleteLegacyKeys

- ea: `0x18004072c`
- end: `0x18004088f`
- name: `TcpipPlugin::DeleteLegacyKeys`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18007c420`

## callees

- `0x180017320`
- `0x180027b38`
- `0x18004072c`
- `0x180040898`
- `0x180040930`
- `0x1800409c8`
- `0x1800582f0`
- `0x18007c0e8`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040825`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040846`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040867`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040825`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040846`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180040867`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall TcpipPlugin::DeleteLegacyKeys(__int64 a1, __int64 a2, __int64 a3)
{
  LSTATUS result; // eax
  HKEY CurrentControlSetRegistryHandle; // rbx
  HKEY v7; // rcx
  HKEY v8; // rdi
  __int64 v9; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+30h] [rbp-D8h] BYREF
  int v11; // [rsp+38h] [rbp-D0h]
  __int128 v12; // [rsp+3Ch] [rbp-CCh]
  __int64 v13; // [rsp+50h] [rbp-B8h]
  WCHAR SubKey[264]; // [rsp+58h] [rbp-B0h] BYREF

  v13 = -2;
  result = TcpipPlugin::GetTcpipVer(a3);
  if ( result )
  {
    if ( result != 1 )
      return result;
    v9 = a1;
    v10 = 0;
    v11 = 9;
    v12 = 0;
    CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v9);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v10);
    TcpipPlugin::Getv6InterfacePathForAdapter(a2 + 20, SubKey);
    v7 = CurrentControlSetRegistryHandle;
  }
  else
  {
    v9 = a1;
    v10 = 0;
    v11 = 9;
    v12 = 0;
    v8 = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v9);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v10);
    TcpipPlugin::Getv4InterfacePathForAdapter(a2 + 20, SubKey);
    RegDeleteKeyExW(v8, SubKey, 0x100u, 0);
    TcpipPlugin::GetAdapterPathForAdapter(a2 + 20, SubKey);
    RegDeleteKeyExW(v8, SubKey, 0x100u, 0);
    TcpipPlugin::GetNetBTInterfacePathForAdapter(a2 + 20, SubKey);
    v7 = v8;
  }
  return RegDeleteKeyExW(v7, SubKey, 0x100u, 0);
}

```

## disassembly

```asm
0x18004072c  mov     rax, rsp
0x18004072f  push    rbp
0x180040730  push    rsi
0x180040731  push    rdi
0x180040732  lea     rbp, [rax-188h]
0x180040739  sub     rsp, 270h
0x180040740  mov     [rsp+280h+var_238], 0FFFFFFFFFFFFFFFEh
0x180040749  mov     [rax+8], rbx
0x18004074d  mov     rax, cs:__security_cookie
0x180040754  xor     rax, rsp
0x180040757  mov     [rbp+180h+var_20], rax
0x18004075e  mov     rsi, rdx
0x180040761  mov     rbx, rcx
0x180040764  mov     rcx, r8
0x180040767  call    TcpipPlugin__GetTcpipVer
0x18004076c  test    eax, eax
0x18004076e  jz      short loc_1800407CB
0x180040770  cmp     eax, 1
0x180040773  jnz     loc_18004086D
0x180040779  xorps   xmm0, xmm0
0x18004077c  mov     [rsp+280h+var_260], rbx
0x180040781  mov     qword ptr [rsp+280h+var_258], 0
0x18004078a  mov     dword ptr [rsp+280h+var_254+4], 9
0x180040792  movdqu  [rsp+280h+var_254+8], xmm0
0x180040798  lea     rcx, [rsp+280h+var_260]; this
0x18004079d  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x1800407a2  mov     rbx, rax
0x1800407a5  lea     rcx, [rsp+280h+var_258]
0x1800407aa  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x1800407af  lea     rcx, [rsi+14h]
0x1800407b3  lea     rdx, [rsp+280h+SubKey]
0x1800407b8  call    TcpipPlugin__Getv6InterfacePathForAdapter
0x1800407bd  mov     r8d, 100h
0x1800407c3  mov     rcx, rbx
0x1800407c6  jmp     loc_18004085F
0x1800407cb  xorps   xmm0, xmm0
0x1800407ce  mov     [rsp+280h+var_260], rbx
0x1800407d3  mov     qword ptr [rsp+280h+var_258], 0
0x1800407dc  mov     dword ptr [rsp+280h+var_254+4], 9
0x1800407e4  movdqu  [rsp+280h+var_254+8], xmm0
0x1800407ea  lea     rcx, [rsp+280h+var_260]; this
0x1800407ef  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x1800407f4  mov     rdi, rax
0x1800407f7  lea     rcx, [rsp+280h+var_258]
0x1800407fc  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180040801  lea     rbx, [rsi+14h]
0x180040805  lea     rdx, [rsp+280h+SubKey]
0x18004080a  mov     rcx, rbx
0x18004080d  call    TcpipPlugin__Getv4InterfacePathForAdapter
0x180040812  xor     r9d, r9d; Reserved
0x180040815  mov     esi, 100h
0x18004081a  mov     r8d, esi; samDesired
0x18004081d  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180040822  mov     rcx, rdi; hKey
0x180040825  call    cs:__imp_RegDeleteKeyExW
0x18004082b  lea     rdx, [rsp+280h+SubKey]
0x180040830  mov     rcx, rbx
0x180040833  call    TcpipPlugin__GetAdapterPathForAdapter
0x180040838  xor     r9d, r9d; Reserved
0x18004083b  mov     r8d, esi; samDesired
0x18004083e  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180040843  mov     rcx, rdi; hKey
0x180040846  call    cs:__imp_RegDeleteKeyExW
0x18004084c  lea     rdx, [rsp+280h+SubKey]
0x180040851  mov     rcx, rbx
0x180040854  call    TcpipPlugin__GetNetBTInterfacePathForAdapter
0x180040859  mov     r8d, esi; samDesired
0x18004085c  mov     rcx, rdi; hKey
0x18004085f  xor     r9d, r9d; Reserved
0x180040862  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180040867  call    cs:__imp_RegDeleteKeyExW
0x18004086d  mov     rcx, [rbp+180h+var_20]
0x180040874  xor     rcx, rsp; StackCookie
0x180040877  call    __security_check_cookie
0x18004087c  mov     rbx, [rsp+280h+arg_0]
0x180040884  add     rsp, 270h
0x18004088b  pop     rdi
0x18004088c  pop     rsi
0x18004088d  pop     rbp
0x18004088e  retn
```
