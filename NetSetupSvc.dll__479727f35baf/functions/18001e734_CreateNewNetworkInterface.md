# CreateNewNetworkInterface

- ea: `0x18001e734`
- end: `0x18001e820`
- name: `CreateNewNetworkInterface`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001e3a8`
- `0x18001f2e4`
- `0x1800223a4`

## callees

- `0x1800027c0`
- `0x18000d954`
- `0x18001b168`
- `0x18001b1e8`
- `0x18001e734`
- `0x180024cdc`
- `0x18002ba68`

## pseudocode

```c
_OWORD *__fastcall CreateNewNetworkInterface(_OWORD *a1, _QWORD *a2, __int64 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  int v9; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+38h] [rbp-40h] BYREF
  char v11[8]; // [rsp+48h] [rbp-30h] BYREF

  v9 = 5;
  *a1 = 0;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)a3,
    (__int128 *)NETSETUPPKEY_Object_CreatedBy,
    (__int64)&v9);
  v11[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)a3,
    &NETSETUPPKEY_Interface_RemoveInterfaceWhenPnpDeviceRemoved,
    (__int64)v11);
  v11[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)a3,
    (__int128 *)NETSETUPPKEY_Interface_DeferredRemoveInterfaceWhenPnpDeviceRemoved,
    (__int64)v11);
  NetSetup2::ObjectCreationTemplate::Create(a3, &v10, a2);
  *a1 = v10;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    WPP_SF__guid_S(*(_QWORD *)(v7 + 16), 54, v7, (_DWORD)a1, v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18001e734  mov     [rsp+arg_0], rbx
0x18001e739  push    rbp
0x18001e73a  push    rsi
0x18001e73b  push    rdi
0x18001e73c  sub     rsp, 60h
0x18001e740  mov     rax, cs:__security_cookie
0x18001e747  xor     rax, rsp
0x18001e74a  mov     [rsp+78h+var_28], rax
0x18001e74f  mov     rdi, r8
0x18001e752  mov     [rsp+78h+var_48], 5
0x18001e75a  xorps   xmm0, xmm0
0x18001e75d  lea     r8, [rsp+78h+var_48]
0x18001e762  movups  xmmword ptr [rcx], xmm0
0x18001e765  mov     rbx, rdx
0x18001e768  mov     rsi, rcx
0x18001e76b  mov     rcx, rdi
0x18001e76e  lea     rdx, NETSETUPPKEY_Object_CreatedBy
0x18001e775  mov     rbp, r9
0x18001e778  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x18001e77d  lea     r8, [rsp+78h+var_30]
0x18001e782  mov     [rsp+78h+var_30], 1
0x18001e787  lea     rdx, NETSETUPPKEY_Interface_RemoveInterfaceWhenPnpDeviceRemoved
0x18001e78e  mov     rcx, rdi
0x18001e791  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18001e796  lea     r8, [rsp+78h+var_30]
0x18001e79b  mov     [rsp+78h+var_30], 1
0x18001e7a0  lea     rdx, NETSETUPPKEY_Interface_DeferredRemoveInterfaceWhenPnpDeviceRemoved
0x18001e7a7  mov     rcx, rdi
0x18001e7aa  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18001e7af  mov     r8, rbx
0x18001e7b2  lea     rdx, [rsp+78h+var_40]
0x18001e7b7  mov     rcx, rdi
0x18001e7ba  call    ?Create@ObjectCreationTemplate@NetSetup2@@QEAA?AU_GUID@@AEAVTransactionBase@details@2@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetup2::ObjectCreationTemplate::Create(NetSetup2::details::TransactionBase &,_NETSETUP_OBJECT_TYPE)
0x18001e7bf  movups  xmm0, [rsp+78h+var_40]
0x18001e7c4  movdqu  xmmword ptr [rsi], xmm0
0x18001e7c8  mov     r8, cs:WPP_GLOBAL_Control
0x18001e7cf  lea     rax, WPP_GLOBAL_Control
0x18001e7d6  cmp     r8, rax
0x18001e7d9  jz      short loc_18001E800
0x18001e7db  cmp     byte ptr [r8+19h], 4
0x18001e7e0  jb      short loc_18001E800
0x18001e7e2  mov     rcx, rbp
0x18001e7e5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001e7ea  mov     rcx, [r8+10h]
0x18001e7ee  mov     edx, 36h ; '6'
0x18001e7f3  mov     r9, rsi
0x18001e7f6  mov     [rsp+78h+var_58], rax
0x18001e7fb  call    WPP_SF__guid_S
0x18001e800  mov     rax, rsi
0x18001e803  mov     rcx, [rsp+78h+var_28]
0x18001e808  xor     rcx, rsp; StackCookie
0x18001e80b  call    __security_check_cookie
0x18001e810  mov     rbx, [rsp+78h+arg_0]
0x18001e818  add     rsp, 60h
0x18001e81c  pop     rdi
0x18001e81d  pop     rsi
0x18001e81e  pop     rbp
0x18001e81f  retn
```
