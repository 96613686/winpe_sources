# WpnUserService::OnStarted(void)

- ea: `0x180009d40`
- end: `0x180009da2`
- name: `?OnStarted@WpnUserService@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(WpnUserService *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180007e58`
- `0x180007efc`
- `0x180009d40`
- `0x180009da8`

## pseudocode

```c
__int64 __fastcall WpnUserService::OnStarted(WpnUserService *this)
{
  char *v1; // rbx
  int v2; // edi
  int v4; // [rsp+30h] [rbp+8h] BYREF
  char *v5; // [rsp+38h] [rbp+10h] BYREF
  char *v6; // [rsp+40h] [rbp+18h] BYREF

  v1 = (char *)this + 8;
  v4 = WpnUserService::OnStartedHelper(this);
  v5 = v1;
  v2 = v4;
  ServiceHostTelemetry::ServiceStarted<unsigned short const *,long &>((__int64 *)&v5, &v4);
  if ( v2 < 0 )
  {
    LODWORD(v5) = 16;
    v6 = v1;
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const *,long &,unsigned int>(
      (__int64 *)&v6,
      &v4,
      (int *)&v5);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180009d40  mov     [rsp+arg_18], rbx
0x180009d45  push    rdi
0x180009d46  sub     rsp, 20h
0x180009d4a  mov     rbx, rcx
0x180009d4d  call    ?OnStartedHelper@WpnUserService@@AEAAJXZ; WpnUserService::OnStartedHelper(void)
0x180009d52  add     rbx, 8
0x180009d56  mov     [rsp+28h+arg_0], eax
0x180009d5a  lea     rdx, [rsp+28h+arg_0]
0x180009d5f  mov     [rsp+28h+arg_8], rbx
0x180009d64  lea     rcx, [rsp+28h+arg_8]
0x180009d69  mov     edi, eax
0x180009d6b  call    ??$ServiceStarted@PEBGAEAJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ@Z; ServiceHostTelemetry::ServiceStarted<ushort const *,long &>(ushort const * &&,long &)
0x180009d70  test    edi, edi
0x180009d72  jns     short loc_180009D95
0x180009d74  lea     r8, [rsp+28h+arg_8]
0x180009d79  mov     dword ptr [rsp+28h+arg_8], 10h
0x180009d81  lea     rdx, [rsp+28h+arg_0]
0x180009d86  mov     [rsp+28h+arg_10], rbx
0x180009d8b  lea     rcx, [rsp+28h+arg_10]
0x180009d90  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x180009d95  mov     rbx, [rsp+28h+arg_18]
0x180009d9a  mov     eax, edi
0x180009d9c  add     rsp, 20h
0x180009da0  pop     rdi
0x180009da1  retn
```
