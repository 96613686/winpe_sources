# OnDemandBrokerClient::RegisterSessionLegacy(ulong,IBackgroundSessionCallbacksLegacy *,ulong *)

- ea: `0x180005f60`
- end: `0x180006008`
- name: `?RegisterSessionLegacy@OnDemandBrokerClient@@UEAAJKPEAUIBackgroundSessionCallbacksLegacy@@PEAK@Z`
- size: `168`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this, unsigned int, struct IBackgroundSessionCallbacksLegacy *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001270`
- `0x180004d44`
- `0x1800056d4`
- `0x180005f60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005feb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005feb`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005f98`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180005f98`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::RegisterSessionLegacy(
        OnDemandBrokerClient *this,
        unsigned int a2,
        struct IBackgroundSessionCallbacksLegacy *a3,
        unsigned int *a4)
{
  void *v4; // rbx
  int UserSid; // edi
  OnDemandBrokerClient *v10; // rcx
  HANDLE hObject[9]; // [rsp+30h] [rbp-48h] BYREF
  void *v13; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  v13 = 0;
  hObject[0] = 0;
  if ( a3 )
  {
    QueryUserToken(0, hObject);
    UserSid = OnDemandBrokerClient::GetUserSid(v10, hObject[0], &v13);
    v4 = v13;
    if ( UserSid >= 0 )
      UserSid = OnDemandBrokerClient::RegisterSessionInternal(
                  (OnDemandBrokerClient *)((char *)this - 8),
                  v13,
                  a2,
                  a3,
                  0,
                  a4);
  }
  else
  {
    UserSid = -2147024809;
  }
  CloseHandle(hObject[0]);
  operator delete[](v4);
  return (unsigned int)UserSid;
}

```

## disassembly

```asm
0x180005f60  mov     rax, rsp
0x180005f63  push    rbx
0x180005f64  push    rbp
0x180005f65  push    rsi
0x180005f66  push    rdi
0x180005f67  push    r14
0x180005f69  push    r15
0x180005f6b  sub     rsp, 48h
0x180005f6f  xor     ebx, ebx
0x180005f71  mov     rbp, r9
0x180005f74  mov     [rax+18h], rbx
0x180005f78  mov     rsi, r8
0x180005f7b  mov     [rax-48h], rbx
0x180005f7f  mov     r14d, edx
0x180005f82  mov     r15, rcx
0x180005f85  test    r8, r8
0x180005f88  jnz     short loc_180005F91
0x180005f8a  mov     edi, 80070057h
0x180005f8f  jmp     short loc_180005FE6
0x180005f91  lea     rdx, [rsp+78h+hObject]
0x180005f96  xor     ecx, ecx
0x180005f98  call    cs:__imp_QueryUserToken
0x180005f9e  mov     rdx, [rsp+78h+hObject]; void *
0x180005fa3  lea     r8, [rsp+78h+arg_10]; void **
0x180005fab  call    ?GetUserSid@OnDemandBrokerClient@@AEAAJPEAXPEAPEAX@Z; OnDemandBrokerClient::GetUserSid(void *,void * *)
0x180005fb0  mov     edi, eax
0x180005fb2  test    eax, eax
0x180005fb4  js      short loc_180005FDE
0x180005fb6  mov     [rsp+78h+var_50], rbp; unsigned int *
0x180005fbb  lea     rcx, [r15-8]; this
0x180005fbf  mov     [rsp+78h+var_58], rbx; struct IBackgroundSessionCallbacks *
0x180005fc4  mov     r9, rsi; struct IBackgroundSessionCallbacksLegacy *
0x180005fc7  mov     rbx, [rsp+78h+arg_10]
0x180005fcf  mov     r8d, r14d; unsigned int
0x180005fd2  mov     rdx, rbx; void *
0x180005fd5  call    ?RegisterSessionInternal@OnDemandBrokerClient@@AEAAJPEAXKPEAUIBackgroundSessionCallbacksLegacy@@PEAUIBackgroundSessionCallbacks@@PEAK@Z; OnDemandBrokerClient::RegisterSessionInternal(void *,ulong,IBackgroundSessionCallbacksLegacy *,IBackgroundSessionCallbacks *,ulong *)
0x180005fda  mov     edi, eax
0x180005fdc  jmp     short loc_180005FE6
0x180005fde  mov     rbx, [rsp+78h+arg_10]
0x180005fe6  mov     rcx, [rsp+78h+hObject]; hObject
0x180005feb  call    cs:__imp_CloseHandle
0x180005ff1  mov     rcx, rbx; Block
0x180005ff4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180005ff9  mov     eax, edi
0x180005ffb  add     rsp, 48h
0x180005fff  pop     r15
0x180006001  pop     r14
0x180006003  pop     rdi
0x180006004  pop     rsi
0x180006005  pop     rbp
0x180006006  pop     rbx
0x180006007  retn
```
