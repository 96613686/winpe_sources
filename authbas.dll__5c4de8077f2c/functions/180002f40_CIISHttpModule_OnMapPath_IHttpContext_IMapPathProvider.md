# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002f40`
- end: `0x180002f59`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004c74`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(__int64 a1, __int64 *a2, __int64 *a3)
{
  int v4; // [rsp+20h] [rbp-18h]
  int v5; // [rsp+28h] [rbp-10h]

  return AUTH_PROVIDER::DoWork(a1, 0x80000000, a2, a3, v4, v5);
}

```

## disassembly

```asm
0x180002f40  sub     rsp, 38h
0x180002f44  mov     r9, r8
0x180002f47  mov     r8, rdx
0x180002f4a  mov     edx, 80000000h
0x180002f4f  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x180002f54  add     rsp, 38h
0x180002f58  retn
```
