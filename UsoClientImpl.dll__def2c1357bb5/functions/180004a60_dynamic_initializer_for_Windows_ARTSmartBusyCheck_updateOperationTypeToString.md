# _dynamic_initializer_for__Windows::ARTSmartBusyCheck::updateOperationTypeToString__

- ea: `0x180004a60`
- end: `0x180004bcf`
- name: `_dynamic_initializer_for__Windows::ARTSmartBusyCheck::updateOperationTypeToString__`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004a60`
- `0x18000a1f8`
- `0x180031ab0`
- `0x1800544c8`
- `0x180056568`
- `0x1800569e8`

## string_xrefs

- `0x180004aba`: `Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int dynamic_initializer_for__Windows::ARTSmartBusyCheck::updateOperationTypeToString__()
{
  __int64 v0; // rcx
  __int64 v1; // rdi
  int *v2; // rbx
  int v4; // [rsp+20h] [rbp-79h] BYREF
  __int128 v5; // [rsp+28h] [rbp-71h] BYREF
  __int64 v6; // [rsp+38h] [rbp-61h]
  __int64 v7; // [rsp+40h] [rbp-59h]
  int v8; // [rsp+48h] [rbp-51h]
  _OWORD v9[2]; // [rsp+50h] [rbp-49h] BYREF
  int v10; // [rsp+70h] [rbp-29h]
  __int128 v11; // [rsp+78h] [rbp-21h] BYREF
  __int64 v12; // [rsp+88h] [rbp-11h]
  __int64 v13; // [rsp+90h] [rbp-9h]
  int v14; // [rsp+98h] [rbp-1h]
  _OWORD v15[2]; // [rsp+A0h] [rbp+7h] BYREF
  int v16; // [rsp+C0h] [rbp+27h]
  __int128 v17; // [rsp+C8h] [rbp+2Fh] BYREF
  __int64 v18; // [rsp+D8h] [rbp+3Fh]
  __int64 v19; // [rsp+E0h] [rbp+47h]
  char v20; // [rsp+E8h] [rbp+4Fh] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  std::string::_Construct<1,char const *>(&v5, "Download", 8);
  v8 = 1;
  memset(v9, 0, sizeof(v9));
  std::string::_Construct<1,char const *>(v9, "Install", 7);
  v10 = 2;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  std::string::_Construct<1,char const *>(&v11, "Reboot", 6);
  v14 = 3;
  memset(v15, 0, sizeof(v15));
  std::string::_Construct<1,char const *>(v15, "Model Validation", 16);
  v16 = 4;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  std::string::_Construct<1,char const *>(&v17, "Test Purpose", 12);
  Windows::ARTSmartBusyCheck::updateOperationTypeToString = 0;
  v1 = std::_Allocate<16,std::_Default_allocate_traits>(72);
  *(_QWORD *)v1 = v1;
  *(_QWORD *)(v1 + 8) = v1;
  *(_QWORD *)(v1 + 16) = v1;
  *(_WORD *)(v1 + 24) = 257;
  *(_QWORD *)&Windows::ARTSmartBusyCheck::updateOperationTypeToString = v1;
  v2 = &v4;
  do
  {
    std::_Tree<std::_Tmap_traits<enum Windows::UpdateOperationType,std::string,std::less<enum Windows::UpdateOperationType>,std::allocator<std::pair<enum Windows::UpdateOperationType const,std::string>>,0>>::_Emplace_hint<std::pair<enum Windows::UpdateOperationType const,std::string> const &>(
      v0,
      v1,
      v2);
    v2 += 10;
  }
  while ( v2 != (int *)&v20 );
  `eh vector destructor iterator'(
    &v4,
    0x28u,
    5u,
    std::pair<enum Windows::UpdateOperationType const,std::string>::~pair<enum Windows::UpdateOperationType const,std::string>);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__Windows::ARTSmartBusyCheck::updateOperationTypeToString__);
}

```

## disassembly

```asm
0x180004a60  mov     [rsp-8+arg_0], rbx
0x180004a65  mov     [rsp-8+arg_8], rdi
0x180004a6a  push    rbp
0x180004a6b  lea     rbp, [rsp-57h]
0x180004a70  sub     rsp, 0F0h
0x180004a77  xor     ebx, ebx
0x180004a79  mov     [rbp+57h+var_D0], ebx
0x180004a7c  xorps   xmm0, xmm0
0x180004a7f  movups  [rbp+57h+var_C8], xmm0
0x180004a83  mov     [rbp+57h+var_B8], rbx
0x180004a87  mov     [rbp+57h+var_B0], rbx
0x180004a8b  lea     r8d, [rbx+8]
0x180004a8f  lea     rdx, aDownload; "Download"
0x180004a96  lea     rcx, [rbp+57h+var_C8]
0x180004a9a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004a9f  nop
0x180004aa0  mov     [rbp+57h+var_A8], 1
0x180004aa7  xorps   xmm0, xmm0
0x180004aaa  movups  [rbp+57h+var_A0], xmm0
0x180004aae  xorps   xmm1, xmm1
0x180004ab1  movdqa  [rbp+57h+var_90], xmm1
0x180004ab6  lea     r8d, [rbx+7]
0x180004aba  lea     rdx, aInstall; "Install"
0x180004ac1  lea     rcx, [rbp+57h+var_A0]
0x180004ac5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004aca  nop
0x180004acb  mov     [rbp+57h+var_80], 2
0x180004ad2  xorps   xmm0, xmm0
0x180004ad5  movups  [rbp+57h+var_78], xmm0
0x180004ad9  mov     [rbp+57h+var_68], rbx
0x180004add  mov     [rbp+57h+var_60], rbx
0x180004ae1  lea     r8d, [rbx+6]
0x180004ae5  lea     rdx, aReboot; "Reboot"
0x180004aec  lea     rcx, [rbp+57h+var_78]
0x180004af0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004af5  nop
0x180004af6  mov     [rbp+57h+var_58], 3
0x180004afd  xorps   xmm0, xmm0
0x180004b00  movups  [rbp+57h+var_50], xmm0
0x180004b04  xorps   xmm1, xmm1
0x180004b07  movdqa  [rbp+57h+var_40], xmm1
0x180004b0c  lea     r8d, [rbx+10h]
0x180004b10  lea     rdx, aModelValidatio; "Model Validation"
0x180004b17  lea     rcx, [rbp+57h+var_50]
0x180004b1b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004b20  nop
0x180004b21  mov     [rbp+57h+var_30], 4
0x180004b28  xorps   xmm0, xmm0
0x180004b2b  movups  [rbp+57h+var_28], xmm0
0x180004b2f  mov     [rbp+57h+var_18], rbx
0x180004b33  mov     [rbp+57h+var_10], rbx
0x180004b37  lea     r8d, [rbx+0Ch]
0x180004b3b  lea     rdx, aTestPurpose; "Test Purpose"
0x180004b42  lea     rcx, [rbp+57h+var_28]
0x180004b46  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180004b4b  nop
0x180004b4c  xorps   xmm0, xmm0
0x180004b4f  movdqu  cs:?updateOperationTypeToString@ARTSmartBusyCheck@Windows@@2V?$map@W4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4UpdateOperationType@Windows@@@4@V?$allocator@U?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@4@@std@@B, xmm0; std::map<Windows::UpdateOperationType,std::string> const Windows::ARTSmartBusyCheck::updateOperationTypeToString
0x180004b57  lea     ecx, [rbx+48h]
0x180004b5a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180004b5f  mov     rdi, rax
0x180004b62  mov     [rax], rax
0x180004b65  mov     [rax+8], rax
0x180004b69  mov     [rax+10h], rax
0x180004b6d  mov     word ptr [rax+18h], 101h
0x180004b73  mov     qword ptr cs:?updateOperationTypeToString@ARTSmartBusyCheck@Windows@@2V?$map@W4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4UpdateOperationType@Windows@@@4@V?$allocator@U?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@4@@std@@B, rax; std::map<Windows::UpdateOperationType,std::string> const Windows::ARTSmartBusyCheck::updateOperationTypeToString
0x180004b7a  lea     rbx, [rbp+57h+var_D0]
0x180004b7e  mov     r8, rbx
0x180004b81  mov     rdx, rdi
0x180004b84  call    ??$_Emplace_hint@AEBU?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@?$_Tree@V?$_Tmap_traits@W4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@W4UpdateOperationType@Windows@@@4@V?$allocator@U?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@4@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@1@QEAU21@AEBU?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<Windows::UpdateOperationType,std::string,std::less<Windows::UpdateOperationType>,std::allocator<std::pair<Windows::UpdateOperationType const,std::string>>,0>>::_Emplace_hint<std::pair<Windows::UpdateOperationType const,std::string> const &>(std::_Tree_node<std::pair<Windows::UpdateOperationType const,std::string>,void *> * const,std::pair<Windows::UpdateOperationType const,std::string> const &)
0x180004b89  add     rbx, 28h ; '('
0x180004b8d  lea     rax, [rbp+57h+var_8]
0x180004b91  cmp     rbx, rax
0x180004b94  jnz     short loc_180004B7E
0x180004b96  lea     r9, ??1?$pair@$$CBW4UpdateOperationType@Windows@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@QEAA@XZ; void (*)(void *)
0x180004b9d  mov     edx, 28h ; '('; unsigned __int64
0x180004ba2  lea     r8d, [rdx-23h]; unsigned __int64
0x180004ba6  lea     rcx, [rbp+57h+var_D0]; void *
0x180004baa  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004baf  lea     rcx, _dynamic_atexit_destructor_for__Windows__ARTSmartBusyCheck__updateOperationTypeToString__
0x180004bb6  lea     r11, [rsp+0F0h+var_s0]
0x180004bbe  mov     rbx, [r11+10h]
0x180004bc2  mov     rdi, [r11+18h]
0x180004bc6  mov     rsp, r11
0x180004bc9  pop     rbp
0x180004bca  jmp     atexit
```
