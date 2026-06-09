# imp_MbbDeviceSendDeviceServiceSessionDataComplete

- ea: `0x14000ec40`
- end: `0x14000ecd6`
- name: `imp_MbbDeviceSendDeviceServiceSessionDataComplete`
- size: `150`
- prototype: `void __stdcall(WDFMEMORY Data, NTSTATUS NtStatus)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x14000ec40`
- `0x14001122c`
- `0x14001e250`
- `0x140047e90`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall imp_MbbDeviceSendDeviceServiceSessionDataComplete(WDFMEMORY Data, NTSTATUS NtStatus)
{
  int v2; // r8d
  int v3; // edi
  __int64 v4; // rbx
  __int64 v5; // rbp
  struct _MBB_OID_HANDLER_ENTRY *OidHandler; // rsi
  int v7; // edx

  v3 = v2;
  v4 = *(_QWORD *)&NtStatus;
  v5 = *(_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, NTSTATUS, __int64 *))(WdfFunctions_01031 + 1616))(
                    WdfDriverGlobals,
                    NtStatus,
                    off_14005E010);
  OidHandler = MbbNdisGetOidHandler(0xE010124u);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, v4);
  if ( OidHandler )
  {
    v7 = -1073741823;
    if ( (v3 & 0xC0000000) != 0xC0000000 )
      v7 = 0;
    MbbUtilCommonCIDResponse(v5, v7, 0, 0, 0, (__int64)OidHandler);
  }
}

```

## disassembly

```asm
0x14000ec40  push    rbx
0x14000ec42  push    rbp
0x14000ec43  push    rsi
0x14000ec44  push    rdi
0x14000ec45  sub     rsp, 38h
0x14000ec49  mov     rax, cs:WdfFunctions_01031
0x14000ec50  mov     edi, r8d
0x14000ec53  mov     r8, cs:off_14005E010
0x14000ec5a  mov     rbx, rdx
0x14000ec5d  mov     rcx, cs:WdfDriverGlobals
0x14000ec64  mov     rax, [rax+650h]
0x14000ec6b  call    _guard_dispatch_icall
0x14000ec70  mov     ecx, 0E010124h; unsigned int
0x14000ec75  mov     rbp, [rax]
0x14000ec78  call    ?MbbNdisGetOidHandler@@YAPEAU_MBB_OID_HANDLER_ENTRY@@K@Z; MbbNdisGetOidHandler(ulong)
0x14000ec7d  mov     rcx, cs:WdfFunctions_01031
0x14000ec84  mov     rsi, rax
0x14000ec87  mov     rdx, rbx
0x14000ec8a  mov     rax, [rcx+680h]
0x14000ec91  mov     rcx, cs:WdfDriverGlobals
0x14000ec98  call    _guard_dispatch_icall
0x14000ec9d  test    rsi, rsi
0x14000eca0  jz      short loc_14000ECCC
0x14000eca2  xor     eax, eax
0x14000eca4  mov     [rsp+58h+var_30], rsi
0x14000eca9  mov     ecx, 0C0000000h
0x14000ecae  mov     [rsp+58h+var_38], eax
0x14000ecb2  and     edi, ecx
0x14000ecb4  mov     edx, 0C0000001h
0x14000ecb9  cmp     edi, ecx
0x14000ecbb  mov     rcx, rbp
0x14000ecbe  cmovnz  edx, eax
0x14000ecc1  xor     r9d, r9d
0x14000ecc4  xor     r8d, r8d
0x14000ecc7  call    ?MbbUtilCommonCIDResponse@@YAXPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEKPEAU_MBB_OID_HANDLER_ENTRY@@@Z; MbbUtilCommonCIDResponse(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong,_MBB_OID_HANDLER_ENTRY *)
0x14000eccc  add     rsp, 38h
0x14000ecd0  pop     rdi
0x14000ecd1  pop     rsi
0x14000ecd2  pop     rbp
0x14000ecd3  pop     rbx
0x14000ecd4  retn
```
