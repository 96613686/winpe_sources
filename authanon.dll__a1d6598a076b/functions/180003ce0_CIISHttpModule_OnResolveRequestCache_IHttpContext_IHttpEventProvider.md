# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180003ce0`
- end: `0x180003cf9`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001030`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnResolveRequestCache(__int64 a1, __int64 *a2, __int64 *a3)
{
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  return AUTH_PROVIDER::DoWork(a1, 8, a2, a3, v4, v5);
}

```

## disassembly

```asm
0x180003ce0  sub     rsp, 38h
0x180003ce4  mov     r9, r8
0x180003ce7  mov     r8, rdx
0x180003cea  mov     edx, 8
0x180003cef  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x180003cf4  add     rsp, 38h
0x180003cf8  retn
```
