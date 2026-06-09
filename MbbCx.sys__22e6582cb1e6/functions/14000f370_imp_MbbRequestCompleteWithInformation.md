# imp_MbbRequestCompleteWithInformation

- ea: `0x14000f370`
- end: `0x14000f3e5`
- name: `imp_MbbRequestCompleteWithInformation`
- size: `117`
- prototype: `void __stdcall(MBBREQUEST Request, NTSTATUS NtStatus, ULONG_PTR Information)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000efa4`
- `0x140047e90`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall imp_MbbRequestCompleteWithInformation(MBBREQUEST Request, NTSTATUS NtStatus, ULONG_PTR Information)
{
  __int64 v3; // r9
  int v4; // edi
  __int64 v5; // rbx
  __int64 v6; // rsi
  MbxRequest *v7; // rax

  v4 = Information;
  v5 = v3;
  v6 = *(_QWORD *)&NtStatus;
  v7 = (MbxRequest *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, NTSTATUS, __int64 *))(WdfFunctions_01031 + 1616))(
                       WdfDriverGlobals,
                       NtStatus,
                       off_14005DFE8);
  *((_QWORD *)v7 + 10) = v5;
  MbxRequest::Complete(v7, v4);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, v6);
}

```

## disassembly

```asm
0x14000f370  mov     [rsp+arg_0], rbx
0x14000f375  mov     [rsp+arg_8], rsi
0x14000f37a  push    rdi
0x14000f37b  sub     rsp, 20h
0x14000f37f  mov     rax, cs:WdfFunctions_01031
0x14000f386  mov     edi, r8d
0x14000f389  mov     r8, cs:off_14005DFE8
0x14000f390  mov     rbx, r9
0x14000f393  mov     rcx, cs:WdfDriverGlobals
0x14000f39a  mov     rsi, rdx
0x14000f39d  mov     rax, [rax+650h]
0x14000f3a4  call    _guard_dispatch_icall
0x14000f3a9  mov     edx, edi; int
0x14000f3ab  mov     rcx, rax; this
0x14000f3ae  mov     [rax+50h], rbx
0x14000f3b2  call    ?Complete@MbxRequest@@QEAAXJ@Z; MbxRequest::Complete(long)
0x14000f3b7  mov     rax, cs:WdfFunctions_01031
0x14000f3be  mov     rdx, rsi
0x14000f3c1  mov     rcx, cs:WdfDriverGlobals
0x14000f3c8  mov     rax, [rax+680h]
0x14000f3cf  call    _guard_dispatch_icall
0x14000f3d4  mov     rbx, [rsp+28h+arg_0]
0x14000f3d9  mov     rsi, [rsp+28h+arg_8]
0x14000f3de  add     rsp, 20h
0x14000f3e2  pop     rdi
0x14000f3e3  retn
```
