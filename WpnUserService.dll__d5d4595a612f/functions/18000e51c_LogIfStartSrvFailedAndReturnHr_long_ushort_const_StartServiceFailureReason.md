# LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)

- ea: `0x18000e51c`
- end: `0x18000e54e`
- name: `?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(int, __int64, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009da8`
- `0x18000a1d8`
- `0x18000e9e8`
- `0x180010444`

## callees

- `0x18000d73c`
- `0x18000e51c`

## pseudocode

```c
__int64 __fastcall LogIfStartSrvFailedAndReturnHr(int a1, __int64 a2, int a3)
{
  int v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = a3;
  v6 = a2;
  v5 = a1;
  if ( a1 < 0 )
    ServiceHostTelemetry::ServiceStartFailure<unsigned short const * &,long &,enum StartServiceFailureReason &>(
      &v6,
      &v5,
      &v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000e51c  mov     rax, rsp
0x18000e51f  mov     [rax+18h], r8d
0x18000e523  mov     [rax+10h], rdx
0x18000e527  mov     [rax+8], ecx
0x18000e52a  push    rbx
0x18000e52b  sub     rsp, 20h
0x18000e52f  mov     ebx, ecx
0x18000e531  test    ecx, ecx
0x18000e533  jns     short loc_18000E546
0x18000e535  lea     r8, [rax+18h]
0x18000e539  lea     rdx, [rax+8]
0x18000e53d  lea     rcx, [rax+10h]
0x18000e541  call    ??$ServiceStartFailure@AEAPEBGAEAJAEAW4StartServiceFailureReason@@@ServiceHostTelemetry@@SAXAEAPEBGAEAJAEAW4StartServiceFailureReason@@@Z; ServiceHostTelemetry::ServiceStartFailure<ushort const * &,long &,StartServiceFailureReason &>(ushort const * &,long &,StartServiceFailureReason &)
0x18000e546  mov     eax, ebx
0x18000e548  add     rsp, 20h
0x18000e54c  pop     rbx
0x18000e54d  retn
```
