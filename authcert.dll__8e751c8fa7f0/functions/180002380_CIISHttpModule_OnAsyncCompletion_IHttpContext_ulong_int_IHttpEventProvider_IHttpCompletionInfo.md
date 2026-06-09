# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002380`
- end: `0x180002392`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003048`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(__int64 a1, __int64 *a2, int a3, __int64 a4, __int64 *a5, int a6)
{
  return AUTH_PROVIDER::DoWork(a1, a3, a2, a5, (int)a5, a6);
}

```

## disassembly

```asm
0x180002380  mov     r9, [rsp+arg_20]
0x180002385  mov     eax, r8d
0x180002388  mov     r8, rdx
0x18000238b  mov     edx, eax
0x18000238d  jmp     ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
```
