# CIISHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002c40`
- end: `0x180002c50`
- name: `?OnAsyncCompletion@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800036ec`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnAsyncCompletion(__int64 a1, __int64 *a2, unsigned int a3, __int64 a4, __int64 *a5)
{
  return RequestDoWork(a3, (__int64)a2, a2, a5);
}

```

## disassembly

```asm
0x180002c40  mov     r9, [rsp+arg_20]
0x180002c45  mov     ecx, r8d
0x180002c48  mov     r8, rdx
0x180002c4b  jmp     ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
```
