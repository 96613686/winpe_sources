# WpnUserService::OnStarting(void)

- ea: `0x18000a170`
- end: `0x18000a1d2`
- name: `?OnStarting@WpnUserService@@UEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180007e58`
- `0x180007f84`
- `0x18000a170`
- `0x18000a1d8`

## pseudocode

```c
__int64 __fastcall WpnUserService::OnStarting(LPVOID *this)
{
  char *v1; // rbx
  int v2; // edi
  int v4; // [rsp+30h] [rbp+8h] BYREF
  char *v5; // [rsp+38h] [rbp+10h] BYREF
  char *v6; // [rsp+40h] [rbp+18h] BYREF

  v1 = (char *)(this + 1);
  v4 = WpnUserService::OnStartingHelper(this);
  v5 = v1;
  v2 = v4;
  ServiceHostTelemetry::StartingService<unsigned short const *,long &>((__int64 *)&v5, &v4);
  if ( v2 < 0 )
  {
    LODWORD(v5) = 11;
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
0x18000a170  mov     [rsp+arg_18], rbx
0x18000a175  push    rdi
0x18000a176  sub     rsp, 20h
0x18000a17a  mov     rbx, rcx
0x18000a17d  call    ?OnStartingHelper@WpnUserService@@AEAAJXZ; WpnUserService::OnStartingHelper(void)
0x18000a182  add     rbx, 8
0x18000a186  mov     [rsp+28h+arg_0], eax
0x18000a18a  lea     rdx, [rsp+28h+arg_0]
0x18000a18f  mov     [rsp+28h+arg_8], rbx
0x18000a194  lea     rcx, [rsp+28h+arg_8]
0x18000a199  mov     edi, eax
0x18000a19b  call    ??$StartingService@PEBGAEAJ@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ@Z; ServiceHostTelemetry::StartingService<ushort const *,long &>(ushort const * &&,long &)
0x18000a1a0  test    edi, edi
0x18000a1a2  jns     short loc_18000A1C5
0x18000a1a4  lea     r8, [rsp+28h+arg_8]
0x18000a1a9  mov     dword ptr [rsp+28h+arg_8], 0Bh
0x18000a1b1  lea     rdx, [rsp+28h+arg_0]
0x18000a1b6  mov     [rsp+28h+arg_10], rbx
0x18000a1bb  lea     rcx, [rsp+28h+arg_10]
0x18000a1c0  call    ??$ServiceStartFailure@PEBGAEAJI@ServiceHostTelemetry@@SAX$$QEAPEBGAEAJ$$QEAI@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const *,long &,uint>(ushort const * &&,long &,uint &&)
0x18000a1c5  mov     rbx, [rsp+28h+arg_18]
0x18000a1ca  mov     eax, edi
0x18000a1cc  add     rsp, 20h
0x18000a1d0  pop     rdi
0x18000a1d1  retn
```
