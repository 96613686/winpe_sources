# Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath(void *,ushort *,_BFS_ENTRY_TYPE,_BFS_POLICY,ulong)

- ea: `0x1400105c4`
- end: `0x14001064c`
- name: `?AddBfsPolicyEntryForTokenAndFilepath@BrokerUtils@Isolation@Security@Windows@@CAXPEAXPEAGW4_BFS_ENTRY_TYPE@@W4_BFS_POLICY@@K@Z`
- size: `136`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerCommon::Bfs *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010764`

## callees

- `0x140007a34`
- `0x140007d90`
- `0x140007df4`
- `0x1400105a8`
- `0x1400105c4`
- `0x140010884`

## string_xrefs

- `0x14001061f`: `onecoreuap\ds\security\isolation\broker\lib\brokerutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Security::Isolation::BrokerUtils::AddBfsPolicyEntryForTokenAndFilepath(
        Windows::Security::Isolation::FileDialogBrokerCommon::Bfs *a1,
        __int64 a2,
        unsigned int a3)
{
  void *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  signed int v10; // eax
  const char *v11; // r9
  int v13; // [rsp+20h] [rbp-28h]
  void *v14; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::OpenDevice(a1);
  try
  {
    v14 = v6;
    if ( v6 == (void *)-1LL )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, v7, v8, v9);
    v10 = Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::AddPolicy(v6, a1, a2, a3);
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
        (const char *)(unsigned int)v10,
        v13);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Throw_CaughtException(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\lib\\brokerutils.cpp",
      v11);
  }
  return wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::CloseDevice(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::CloseDevice(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
}

```

## disassembly

```asm
0x1400105c4  mov     [rsp+arg_0], rbx
0x1400105c9  mov     [rsp+arg_8], rsi
0x1400105ce  push    rdi
0x1400105cf  sub     rsp, 40h
0x1400105d3  mov     ebx, r8d
0x1400105d6  mov     rdi, rdx
0x1400105d9  mov     rsi, rcx
0x1400105dc  call    ?OpenDevice@Bfs@FileDialogBrokerCommon@Isolation@Security@Windows@@YAPEAXXZ; Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::OpenDevice(void)
0x1400105e1  mov     [rsp+48h+var_18], rax
0x1400105e6  mov     rcx, [rsp+48h]; this
0x1400105eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400105ef  jnz     short loc_1400105F6
0x1400105f1  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1400105f6  mov     r9d, ebx
0x1400105f9  mov     r8, rdi
0x1400105fc  mov     rdx, rsi
0x1400105ff  mov     rcx, rax
0x140010602  call    ?AddPolicy@Bfs@FileDialogBrokerCommon@Isolation@Security@Windows@@YAKPEAX0PEBGW4_BFS_ENTRY_TYPE@@W4_BFS_POLICY@@K@Z; Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::AddPolicy(void *,void *,ushort const *,_BFS_ENTRY_TYPE,_BFS_POLICY,ulong)
0x140010607  test    eax, eax
0x140010609  jle     short loc_140010613
0x14001060b  movzx   eax, ax
0x14001060e  or      eax, 80070000h
0x140010613  mov     rcx, [rsp+48h]; this
0x140010618  test    eax, eax
0x14001061a  jns     short loc_140010631
0x14001061c  mov     r9d, eax; char *
0x14001061f  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\isolation\\br"...
0x140010626  mov     edx, 40h ; '@'; void *
0x14001062b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140010631  lea     rcx, [rsp+48h+var_18]
0x140010636  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AKPEAX@Z$1?CloseDevice@Bfs@FileDialogBrokerCommon@Isolation@Security@Windows@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::CloseDevice(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,ulong (*)(void *),&Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::CloseDevice(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14001063b  nop
0x14001063c  mov     rbx, [rsp+48h+arg_0]
0x140010641  mov     rsi, [rsp+48h+arg_8]
0x140010646  add     rsp, 40h
0x14001064a  pop     rdi
0x14001064b  retn
```
