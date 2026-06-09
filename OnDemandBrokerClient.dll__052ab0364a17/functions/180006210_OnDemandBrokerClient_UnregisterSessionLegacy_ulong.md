# OnDemandBrokerClient::UnregisterSessionLegacy(ulong)

- ea: `0x180006210`
- end: `0x180006290`
- name: `?UnregisterSessionLegacy@OnDemandBrokerClient@@UEAAJK@Z`
- size: `128`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800027a0`
- `0x180004d44`
- `0x1800056d4`
- `0x180006210`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000626e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000626e`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18000623b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18000623b`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::UnregisterSessionLegacy(OnDemandBrokerClient *this, unsigned int a2)
{
  OnDemandBrokerClient *v4; // rcx
  int UserSid; // ebx
  HANDLE hObject; // [rsp+30h] [rbp+8h] BYREF
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  Block = 0;
  hObject = 0;
  QueryUserToken(0, &hObject);
  UserSid = OnDemandBrokerClient::GetUserSid(v4, hObject, &Block);
  if ( UserSid >= 0 )
    UserSid = OnDemandBrokerClient::UnregisterSessionInternal((OnDemandBrokerClient *)((char *)this - 8), Block, a2);
  CloseHandle(hObject);
  operator delete[](Block);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180006210  mov     rax, rsp
0x180006213  mov     [rax+10h], rbx
0x180006217  mov     [rax+20h], rsi
0x18000621b  push    rdi
0x18000621c  sub     rsp, 20h
0x180006220  mov     edi, edx
0x180006222  mov     qword ptr [rax+18h], 0
0x18000622a  mov     rsi, rcx
0x18000622d  mov     qword ptr [rax+8], 0
0x180006235  lea     rdx, [rax+8]
0x180006239  xor     ecx, ecx
0x18000623b  call    cs:__imp_QueryUserToken
0x180006241  mov     rdx, [rsp+28h+hObject]; void *
0x180006246  lea     r8, [rsp+28h+Block]; void **
0x18000624b  call    ?GetUserSid@OnDemandBrokerClient@@AEAAJPEAXPEAPEAX@Z; OnDemandBrokerClient::GetUserSid(void *,void * *)
0x180006250  mov     ebx, eax
0x180006252  test    eax, eax
0x180006254  js      short loc_180006269
0x180006256  mov     rdx, [rsp+28h+Block]; void *
0x18000625b  lea     rcx, [rsi-8]; this
0x18000625f  mov     r8d, edi; unsigned int
0x180006262  call    ?UnregisterSessionInternal@OnDemandBrokerClient@@AEAAJPEAXK@Z; OnDemandBrokerClient::UnregisterSessionInternal(void *,ulong)
0x180006267  mov     ebx, eax
0x180006269  mov     rcx, [rsp+28h+hObject]; hObject
0x18000626e  call    cs:__imp_CloseHandle
0x180006274  mov     rcx, [rsp+28h+Block]; Block
0x180006279  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000627e  mov     rsi, [rsp+28h+arg_18]
0x180006283  mov     eax, ebx
0x180006285  mov     rbx, [rsp+28h+arg_8]
0x18000628a  add     rsp, 20h
0x18000628e  pop     rdi
0x18000628f  retn
```
