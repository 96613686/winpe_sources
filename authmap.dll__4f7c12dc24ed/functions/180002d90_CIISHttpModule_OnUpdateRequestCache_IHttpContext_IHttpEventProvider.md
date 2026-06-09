# CIISHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002d90`
- end: `0x180002da9`
- name: `?OnUpdateRequestCache@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005f04`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnUpdateRequestCache(__int64 a1, __int64 *a2, __int64 *a3)
{
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  return AUTH_PROVIDER::DoWork(a1, 512, a2, a3, v4, v5);
}

```

## disassembly

```asm
0x180002d90  sub     rsp, 38h
0x180002d94  mov     r9, r8
0x180002d97  mov     r8, rdx
0x180002d9a  mov     edx, 200h
0x180002d9f  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x180002da4  add     rsp, 38h
0x180002da8  retn
```
