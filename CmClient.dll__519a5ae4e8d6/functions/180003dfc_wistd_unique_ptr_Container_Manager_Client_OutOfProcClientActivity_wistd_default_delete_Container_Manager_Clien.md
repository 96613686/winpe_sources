# wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(void)

- ea: `0x180003dfc`
- end: `0x180003e5f`
- name: `??1?$unique_ptr@VOutOfProcClientActivity@Client@Manager@Container@@U?$default_delete@VOutOfProcClientActivity@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007100`
- `0x180007490`

## callees

- `0x180001944`
- `0x180003bc4`
- `0x180003dfc`

## pseudocode

```c
void __fastcall wistd::unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>::~unique_ptr<Container::Manager::Client::OutOfProcClientActivity,wistd::default_delete<Container::Manager::Client::OutOfProcClientActivity>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rdi

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    v2 = (void *)v1[3];
    v1[3] = 0;
    if ( v2 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v2);
      operator delete(v2, (const struct std::nothrow_t *)0x18);
    }
    if ( *v1 )
      _InterlockedDecrement((volatile signed __int32 *)(*v1 + 20LL));
    operator delete(v1, (const struct std::nothrow_t *)0x20);
  }
}

```

## disassembly

```asm
0x180003dfc  mov     [rsp+arg_0], rbx
0x180003e01  push    rdi
0x180003e02  sub     rsp, 20h
0x180003e06  mov     rbx, [rcx]
0x180003e09  mov     qword ptr [rcx], 0
0x180003e10  test    rbx, rbx
0x180003e13  jz      short loc_180003E54
0x180003e15  mov     rdi, [rbx+18h]
0x180003e19  mov     qword ptr [rbx+18h], 0
0x180003e21  test    rdi, rdi
0x180003e24  jz      short loc_180003E3B
0x180003e26  mov     rcx, rdi
0x180003e29  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x180003e2e  mov     edx, 18h; struct std::nothrow_t *
0x180003e33  mov     rcx, rdi; void *
0x180003e36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003e3b  mov     rax, [rbx]
0x180003e3e  test    rax, rax
0x180003e41  jz      short loc_180003E47
0x180003e43  lock dec dword ptr [rax+14h]
0x180003e47  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x180003e4c  mov     rcx, rbx; void *
0x180003e4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180003e54  mov     rbx, [rsp+28h+arg_0]
0x180003e59  add     rsp, 20h
0x180003e5d  pop     rdi
0x180003e5e  retn
```
