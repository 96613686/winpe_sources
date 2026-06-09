# imp_MbbDeviceReceiveDeviceServiceSessionData

- ea: `0x14000eac0`
- end: `0x14000eb4a`
- name: `imp_MbbDeviceReceiveDeviceServiceSessionData`
- size: `138`
- prototype: `void __stdcall(WDFDEVICE Device, DSS_SESSION_ID SessionId, WDFMEMORY Data)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x14000fca8`
- `0x140047e90`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall imp_MbbDeviceReceiveDeviceServiceSessionData(WDFDEVICE Device, DSS_SESSION_ID SessionId, WDFMEMORY Data)
{
  __int64 v3; // r9
  int v4; // esi
  __int64 v5; // rdi
  unsigned __int8 *v6; // rbx
  __int64 v7; // rax
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (int)Data;
  v5 = *(_QWORD *)&SessionId;
  v8[0] = 0;
  v6 = (unsigned __int8 *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01031 + 1552))(
                            WdfDriverGlobals,
                            v3,
                            v8);
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         v5,
         off_14005DF70);
  MbbNdisDeviceServiceSessionReceive((struct _MINIPORT_ADAPTER_CONTEXT *)(v7 + 64), v4, v6, v8[0]);
}

```

## disassembly

```asm
0x14000eac0  mov     r11, rsp
0x14000eac3  mov     [r11+8], rbx
0x14000eac7  mov     [r11+10h], rsi
0x14000eacb  push    rdi
0x14000eacc  sub     rsp, 30h
0x14000ead0  mov     rax, cs:WdfFunctions_01031
0x14000ead7  mov     esi, r8d
0x14000eada  mov     rcx, cs:WdfDriverGlobals
0x14000eae1  lea     r8, [r11-18h]
0x14000eae5  mov     rdi, rdx
0x14000eae8  mov     qword ptr [r11-18h], 0
0x14000eaf0  mov     rdx, r9
0x14000eaf3  mov     rax, [rax+610h]
0x14000eafa  call    _guard_dispatch_icall
0x14000eaff  mov     rcx, cs:WdfFunctions_01031
0x14000eb06  mov     rbx, rax
0x14000eb09  mov     r8, cs:off_14005DF70
0x14000eb10  mov     rdx, rdi
0x14000eb13  mov     rax, [rcx+650h]
0x14000eb1a  mov     rcx, cs:WdfDriverGlobals
0x14000eb21  call    _guard_dispatch_icall
0x14000eb26  mov     r9d, dword ptr [rsp+38h+var_18]; unsigned int
0x14000eb2b  mov     r8, rbx; unsigned __int8 *
0x14000eb2e  mov     edx, esi; unsigned int
0x14000eb30  lea     rcx, [rax+40h]; struct _MINIPORT_ADAPTER_CONTEXT *
0x14000eb34  call    ?MbbNdisDeviceServiceSessionReceive@@YAHPEAU_MINIPORT_ADAPTER_CONTEXT@@KPEAEK@Z; MbbNdisDeviceServiceSessionReceive(_MINIPORT_ADAPTER_CONTEXT *,ulong,uchar *,ulong)
0x14000eb39  mov     rbx, [rsp+38h+arg_0]
0x14000eb3e  mov     rsi, [rsp+38h+arg_8]
0x14000eb43  add     rsp, 30h
0x14000eb47  pop     rdi
0x14000eb48  retn
```
