# Concurrency::details::Security::InitializeCookie(void)

- ea: `0x18030ff54`
- end: `0x18030ffb5`
- name: `?InitializeCookie@Security@details@Concurrency@@SA_KXZ`
- size: `97`
- prototype: `unsigned __int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002020`

## callees

- `0x18030ff54`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x18030ff6b`
- `KERNEL32!EncodePointer` at `0x18030ff6b`
- `KERNEL32!GetCurrentThread` at `0x18030ff7b`
- `KERNEL32!GetCurrentThread` at `0x18030ff7b`
- `KERNEL32!GetThreadTimes` at `0x18030ff9d`
- `KERNEL32!GetThreadTimes` at `0x18030ff9d`

## pseudocode

```c
uintptr_t Concurrency::details::Security::InitializeCookie(void)
{
  uintptr_t v0; // rbx
  HANDLE CurrentThread; // rax
  struct _FILETIME UserTime; // [rsp+40h] [rbp+8h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp+10h] BYREF

  Concurrency::details::Security::s_initialized = 1;
  v0 = _security_cookie ^ (unsigned __int64)EncodePointer(&Concurrency::details::Security::s_cookie);
  CurrentThread = GetCurrentThread();
  if ( GetThreadTimes(CurrentThread, &CreationTime, &UserTime, &UserTime, &UserTime) )
    v0 ^= *(_QWORD *)&CreationTime;
  return v0;
}

```

## disassembly

```asm
0x18030ff54  push    rbx
0x18030ff56  sub     rsp, 30h
0x18030ff5a  lea     rcx, ?s_cookie@Security@details@Concurrency@@2_KA; Ptr
0x18030ff61  mov     cs:?s_initialized@Security@details@Concurrency@@2JC, 1
0x18030ff6b  call    cs:__imp_EncodePointer
0x18030ff71  mov     rbx, rax
0x18030ff74  xor     rbx, cs:__security_cookie
0x18030ff7b  call    cs:__imp_GetCurrentThread
0x18030ff81  mov     rcx, rax; hThread
0x18030ff84  lea     r9, [rsp+38h+UserTime]; lpKernelTime
0x18030ff89  lea     rax, [rsp+38h+UserTime]
0x18030ff8e  lea     r8, [rsp+38h+UserTime]; lpExitTime
0x18030ff93  mov     [rsp+38h+lpUserTime], rax; lpUserTime
0x18030ff98  lea     rdx, [rsp+38h+CreationTime]; lpCreationTime
0x18030ff9d  call    cs:__imp_GetThreadTimes
0x18030ffa3  test    eax, eax
0x18030ffa5  jz      short loc_18030FFAC
0x18030ffa7  xor     rbx, qword ptr [rsp+38h+CreationTime.dwLowDateTime]
0x18030ffac  mov     rax, rbx
0x18030ffaf  add     rsp, 30h
0x18030ffb3  pop     rbx
0x18030ffb4  retn
```
