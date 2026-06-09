# NetSetup2::NetworkInterface::get_ConfigurationPath(void)

- ea: `0x18000edd0`
- end: `0x18000ee37`
- name: `?get_ConfigurationPath@NetworkInterface@NetSetup2@@QEBA?AUConfigurationPath_Value@Aggregate@2@XZ`
- size: `103`
- prototype: `__int64 __fastcall(NetSetup2::ActiveObject *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18000e0d8`

## callees

- `0x180005558`
- `0x18000ec70`
- `0x180011500`

## pseudocode

```c
__int64 __fastcall NetSetup2::NetworkInterface::get_ConfigurationPath(NetSetup2::ActiveObject *a1, __int64 a2)
{
  HRESULT (__stdcall **p_GetTypeInfoCount)(ADOProperty *, UINT *); // rdx
  const unsigned __int8 *v4; // r8
  _BYTE v6[24]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+48h] [rbp-20h] BYREF

  *(_QWORD *)(a2 + 32) = 7;
  *(_QWORD *)(a2 + 24) = 0;
  *(_WORD *)(a2 + 8) = 0;
  p_GetTypeInfoCount = &NetSetup2::ActiveObject::GetProperty(a1, (const struct _NETSETUPPROPKEY *)v6).lpVtbl->GetTypeInfoCount;
  NetSetup2::Aggregate::ConfigurationPath_Value::Deserialize(a2, (__int64)p_GetTypeInfoCount, v4);
  std::vector<unsigned char>::_Tidy((__int64)v7);
  return a2;
}

```

## disassembly

```asm
0x18000edd0  mov     [rsp+arg_8], rdx
0x18000edd5  push    rbx
0x18000edd6  sub     rsp, 60h
0x18000edda  mov     [rsp+68h+var_40], 0FFFFFFFFFFFFFFFEh
0x18000ede3  mov     rbx, rdx
0x18000ede6  xor     eax, eax
0x18000ede8  mov     [rsp+68h+var_48], eax
0x18000edec  mov     qword ptr [rdx+20h], 7
0x18000edf4  mov     [rdx+18h], rax
0x18000edf8  mov     [rdx+8], ax
0x18000edfc  mov     [rsp+68h+var_48], 1
0x18000ee04  lea     r8, NETSETUPPKEY_Interface_ConfigurationPath
0x18000ee0b  lea     rdx, [rsp+68h+var_38]; struct _NETSETUPPROPKEY *
0x18000ee10  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18000ee15  nop
0x18000ee16  lea     rdx, [rax+18h]
0x18000ee1a  mov     rcx, rbx
0x18000ee1d  call    ?Deserialize@ConfigurationPath_Value@Aggregate@NetSetup2@@QEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; NetSetup2::Aggregate::ConfigurationPath_Value::Deserialize(std::vector<uchar> const &)
0x18000ee22  nop
0x18000ee23  lea     rcx, [rsp+68h+var_20]
0x18000ee28  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000ee2d  mov     rax, rbx
0x18000ee30  add     rsp, 60h
0x18000ee34  pop     rbx
0x18000ee35  retn
```
