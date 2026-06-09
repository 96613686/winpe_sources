# CmsCloseActivity

- ea: `0x180007100`
- end: `0x1800071c9`
- name: `CmsCloseActivity`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180009ff0`
- `0x18000a660`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x180003bc4`
- `0x180003dfc`
- `0x1800066e4`
- `0x180007100`

## string_xrefs

- `0x180007141`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCloseActivity(__int64 a1)
{
  _QWORD *v1; // rbx
  int v3; // eax
  unsigned int v4; // edi
  void *v6; // rdi
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(_QWORD **)a1;
  v9 = *(_QWORD *)(*(_QWORD *)a1 + 8LL);
  v10 = &v9;
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CloseActivity,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v10 = 0;
    if ( v1 )
    {
      v6 = (void *)v1[3];
      v1[3] = 0;
      if ( v6 )
      {
        Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v6);
        operator delete(v6, (const struct std::nothrow_t *)0x18);
      }
      if ( *v1 )
        _InterlockedDecrement((volatile signed __int32 *)(*v1 + 20LL));
      operator delete(v1, (const struct std::nothrow_t *)0x20);
    }
    *(_QWORD *)a1 = 0;
    wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(&v10);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
}

```

## disassembly

```asm
0x180007100  mov     r11, rsp
0x180007103  mov     [r11+18h], rbx
0x180007107  mov     [r11+20h], rsi
0x18000710b  push    rdi; int
0x18000710c  sub     rsp, 20h
0x180007110  mov     rbx, [rcx]
0x180007113  lea     rdx, [r11+10h]
0x180007117  mov     rsi, rcx
0x18000711a  lea     rcx, CmsRpcClt_CloseActivity
0x180007121  mov     rax, [rbx+8]
0x180007125  mov     [r11+8], rax
0x180007129  lea     rax, [r11+8]
0x18000712d  mov     [r11+10h], rax
0x180007131  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007136  mov     edi, eax
0x180007138  test    eax, eax
0x18000713a  jns     short loc_180007159
0x18000713c  mov     rcx, [rsp+28h]; this
0x180007141  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007148  mov     r9d, eax; char *
0x18000714b  mov     edx, 2C9h; void *
0x180007150  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007155  mov     eax, edi
0x180007157  jmp     short loc_1800071B9
0x180007159  mov     [rsp+28h+arg_8], 0
0x180007162  test    rbx, rbx
0x180007165  jz      short loc_1800071A6
0x180007167  mov     rdi, [rbx+18h]
0x18000716b  mov     qword ptr [rbx+18h], 0
0x180007173  test    rdi, rdi
0x180007176  jz      short loc_18000718D
0x180007178  mov     rcx, rdi
0x18000717b  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180007180  mov     edx, 18h; struct std::nothrow_t *
0x180007185  mov     rcx, rdi; void *
0x180007188  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000718d  mov     rax, [rbx]
0x180007190  test    rax, rax
0x180007193  jz      short loc_180007199
0x180007195  lock dec dword ptr [rax+14h]
0x180007199  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000719e  mov     rcx, rbx; void *
0x1800071a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800071a6  lea     rcx, [rsp+28h+arg_8]
0x1800071ab  mov     qword ptr [rsi], 0
0x1800071b2  call    ??1?$unique_ptr@VOutOfProcClientActivity@Client@Manager@Container@@U?$default_delete@VOutOfProcClientActivity@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(void)
0x1800071b7  xor     eax, eax
0x1800071b9  mov     rbx, [rsp+28h+arg_10]
0x1800071be  mov     rsi, [rsp+28h+arg_18]
0x1800071c3  add     rsp, 20h
0x1800071c7  pop     rdi
0x1800071c8  retn
```
