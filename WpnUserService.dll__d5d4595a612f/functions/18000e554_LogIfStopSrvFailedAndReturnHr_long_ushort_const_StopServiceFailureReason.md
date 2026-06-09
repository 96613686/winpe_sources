# LogIfStopSrvFailedAndReturnHr(long,ushort const *,StopServiceFailureReason)

- ea: `0x18000e554`
- end: `0x18000e586`
- name: `?LogIfStopSrvFailedAndReturnHr@@YAJJPEBGW4StopServiceFailureReason@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(int, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000a450`
- `0x18000edbc`

## callees

- `0x18000d884`
- `0x18000e554`

## pseudocode

```c
__int64 __fastcall LogIfStopSrvFailedAndReturnHr(int a1, __int64 a2, int a3)
{
  int v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF
  int v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = a3;
  v6 = a2;
  v5 = a1;
  if ( a1 < 0 )
    ServiceHostTelemetry::ServiceStopFailure<unsigned short const * &,long &,enum StopServiceFailureReason &>(
      &v6,
      &v5,
      &v7);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x18000e554  mov     rax, rsp
0x18000e557  mov     [rax+18h], r8d
0x18000e55b  mov     [rax+10h], rdx
0x18000e55f  mov     [rax+8], ecx
0x18000e562  push    rbx
0x18000e563  sub     rsp, 20h
0x18000e567  mov     ebx, ecx
0x18000e569  test    ecx, ecx
0x18000e56b  jns     short loc_18000E57E
0x18000e56d  lea     r8, [rax+18h]
0x18000e571  lea     rdx, [rax+8]
0x18000e575  lea     rcx, [rax+10h]
0x18000e579  call    ??$ServiceStopFailure@AEAPEBGAEAJAEAW4StopServiceFailureReason@@@ServiceHostTelemetry@@SAXAEAPEBGAEAJAEAW4StopServiceFailureReason@@@Z; ServiceHostTelemetry::ServiceStopFailure<ushort const * &,long &,StopServiceFailureReason &>(ushort const * &,long &,StopServiceFailureReason &)
0x18000e57e  mov     eax, ebx
0x18000e580  add     rsp, 20h
0x18000e584  pop     rbx
0x18000e585  retn
```
