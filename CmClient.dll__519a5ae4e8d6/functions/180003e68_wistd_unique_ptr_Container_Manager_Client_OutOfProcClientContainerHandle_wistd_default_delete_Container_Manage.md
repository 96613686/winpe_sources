# wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)

- ea: `0x180003e68`
- end: `0x180003edb`
- name: `??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ`
- size: `115`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800071d0`
- `0x180007610`
- `0x180009a94`

## callees

- `0x180001944`
- `0x180003bc4`
- `0x180003e68`
- `0x1800048a0`

## string_xrefs

- `0x180003ec9`: `onecore\base\gendrv\silos\clem\core\inc\CmClientServerCommon.h`

## pseudocode

```c
void __fastcall wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // rbx
  void *v5; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
  {
    v5 = *(void **)(v4 + 40);
    *(_QWORD *)(v4 + 40) = 0;
    if ( v5 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v5);
      operator delete(v5, (const struct std::nothrow_t *)0x18);
    }
    if ( *(_DWORD *)(v4 + 20) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\inc\\CmClientServerCommon.h",
        a4);
    operator delete((void *)v4, (const struct std::nothrow_t *)0x30);
  }
}

```

## disassembly

```asm
0x180003e68  mov     [rsp+arg_0], rbx
0x180003e6d  push    rdi
0x180003e6e  sub     rsp, 20h
0x180003e72  mov     rbx, [rcx]
0x180003e75  mov     qword ptr [rcx], 0
0x180003e7c  test    rbx, rbx
0x180003e7f  jz      short loc_180003EB9
0x180003e81  mov     rdi, [rbx+28h]
0x180003e85  mov     qword ptr [rbx+28h], 0
0x180003e8d  test    rdi, rdi
0x180003e90  jz      short loc_180003EA7
0x180003e92  mov     rcx, rdi
0x180003e95  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180003e9a  mov     edx, 18h; struct std::nothrow_t *
0x180003e9f  mov     rcx, rdi; void *
0x180003ea2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003ea7  mov     eax, [rbx+14h]
0x180003eaa  test    eax, eax
0x180003eac  jnz     short loc_180003EC4
0x180003eae  lea     edx, [rax+30h]; struct std::nothrow_t *
0x180003eb1  mov     rcx, rbx; void *
0x180003eb4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003eb9  mov     rbx, [rsp+28h+arg_0]
0x180003ebe  add     rsp, 20h
0x180003ec2  pop     rdi
0x180003ec3  retn
0x180003ec4  mov     rcx, [rsp+28h]; this
0x180003ec9  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180003ed0  mov     edx, 35h ; '5'; void *
0x180003ed5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
