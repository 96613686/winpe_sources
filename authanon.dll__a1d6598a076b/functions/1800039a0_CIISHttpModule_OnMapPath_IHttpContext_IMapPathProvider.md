# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x1800039a0`
- end: `0x1800039b9`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001030`

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
0x1800039a0  sub     rsp, 38h
0x1800039a4  mov     r9, r8
0x1800039a7  mov     r8, rdx
0x1800039aa  mov     edx, 80000000h
0x1800039af  call    ?DoWork@AUTH_PROVIDER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@KPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAXPEAVIHttpServer@@@Z; AUTH_PROVIDER::DoWork(ulong,IHttpContext *,IHttpEventProvider *,void *,IHttpServer *)
0x1800039b4  add     rsp, 38h
0x1800039b8  retn
```
