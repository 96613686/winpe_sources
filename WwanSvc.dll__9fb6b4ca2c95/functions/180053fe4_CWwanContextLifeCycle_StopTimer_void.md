# CWwanContextLifeCycle::StopTimer(void)

- ea: `0x180053fe4`
- end: `0x180054068`
- name: `?StopTimer@CWwanContextLifeCycle@@AEAAKXZ`
- size: `132`
- prototype: `unsigned int __fastcall(CWwanContextLifeCycle *__hidden this)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18005462c`
- `0x180054a14`
- `0x180054b4c`
- `0x180054eec`
- `0x1800550a4`
- `0x1800553f4`
- `0x18005552c`
- `0x180055800`
- `0x180055a98`

## callees

- `0x180014f1c`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x180054023`
- `MobileNetworking!StopTimer` at `0x180054023`
- `MobileNetworking!AcquireWriteLock` at `0x18005400f`
- `MobileNetworking!AcquireWriteLock` at `0x18005400f`
- `MobileNetworking!ReleaseWriteLock` at `0x180054040`
- `MobileNetworking!ReleaseWriteLock` at `0x180054040`

## string_xrefs

- `0x180054046`: `Timer Stop Completed`

## pseudocode

```c
__int64 __fastcall CWwanContextLifeCycle::StopTimer(CWwanContextLifeCycle *this)
{
  char *v1; // rbx

  v1 = (char *)this + 2680;
  AcquireWriteLock(*((_QWORD *)this + 348), (char *)this + 2680, "CWwanContextLifeCycle::StopTimer", 1854);
  StopTimer(*((_QWORD *)this + 348), "CWwanContextLifeCycle::StopTimer");
  ReleaseWriteLock(*((_QWORD *)this + 348), v1, "CWwanContextLifeCycle::StopTimer", 1856);
  WwanLog::Info("CWwanContextLifeCycle::StopTimer", 0, L"Timer Stop Completed");
  return 0;
}

```

## disassembly

```asm
0x180053fe4  mov     [rsp+arg_0], rbx
0x180053fe9  push    rdi
0x180053fea  sub     rsp, 20h
0x180053fee  lea     rbx, [rcx+0A78h]
0x180053ff5  mov     rdi, rcx
0x180053ff8  mov     rcx, [rcx+0AE0h]
0x180053fff  lea     r8, aCwwancontextli_18; "CWwanContextLifeCycle::StopTimer"
0x180054006  mov     rdx, rbx
0x180054009  mov     r9d, 73Eh
0x18005400f  call    cs:__imp_AcquireWriteLock
0x180054015  mov     rcx, [rdi+0AE0h]
0x18005401c  lea     rdx, aCwwancontextli_18; "CWwanContextLifeCycle::StopTimer"
0x180054023  call    cs:__imp_StopTimer
0x180054029  mov     rcx, [rdi+0AE0h]
0x180054030  lea     r8, aCwwancontextli_18; "CWwanContextLifeCycle::StopTimer"
0x180054037  mov     r9d, 740h
0x18005403d  mov     rdx, rbx
0x180054040  call    cs:__imp_ReleaseWriteLock
0x180054046  lea     r8, aTimerStopCompl; "Timer Stop Completed"
0x18005404d  xor     edx, edx; struct _GUID *
0x18005404f  lea     rcx, aCwwancontextli_18; "CWwanContextLifeCycle::StopTimer"
0x180054056  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18005405b  mov     rbx, [rsp+28h+arg_0]
0x180054060  xor     eax, eax
0x180054062  add     rsp, 20h
0x180054066  pop     rdi
0x180054067  retn
```
