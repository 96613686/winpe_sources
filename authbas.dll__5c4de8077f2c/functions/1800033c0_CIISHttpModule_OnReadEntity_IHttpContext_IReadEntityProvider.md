# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800033c0`
- end: `0x1800033d9`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004c74`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(__int64 a1, __int64 *a2, __int64 *a3)
{
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  return AUTH_PROVIDER::DoWork(a1, 0x40000000, a2, a3, v4, v5);
}

```

## disassembly

```asm
0x1800033c0  sub     rsp, 38h
0x1800033c4  mov     r9, r8
0x1800033c7  mov     r8, rdx
0x1800033ca  mov     edx, 40000000h
0x1800033cf  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x1800033d4  add     rsp, 38h
0x1800033d8  retn
```
