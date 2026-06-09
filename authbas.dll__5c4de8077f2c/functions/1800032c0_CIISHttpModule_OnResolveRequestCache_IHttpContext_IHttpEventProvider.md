# CIISHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800032c0`
- end: `0x1800032d9`
- name: `?OnResolveRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004c74`

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
0x1800032c0  sub     rsp, 38h
0x1800032c4  mov     r9, r8
0x1800032c7  mov     r8, rdx
0x1800032ca  mov     edx, 8
0x1800032cf  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x1800032d4  add     rsp, 38h
0x1800032d8  retn
```
