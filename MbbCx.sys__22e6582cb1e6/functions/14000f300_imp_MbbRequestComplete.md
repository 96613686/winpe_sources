# imp_MbbRequestComplete

- ea: `0x14000f300`
- end: `0x14000f364`
- name: `imp_MbbRequestComplete`
- size: `100`
- prototype: `void __stdcall(MBBREQUEST Request, NTSTATUS NtStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000efa4`
- `0x140047e90`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall imp_MbbRequestComplete(MBBREQUEST Request, NTSTATUS NtStatus)
{
  int v2; // r8d
  int v3; // ebx
  __int64 v4; // rdi
  MbxRequest *v5; // rax

  v3 = v2;
  v4 = *(_QWORD *)&NtStatus;
  v5 = (MbxRequest *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, NTSTATUS, __int64 *))(WdfFunctions_01031 + 1616))(
                       WdfDriverGlobals,
                       NtStatus,
                       off_14005DFE8);
  MbxRequest::Complete(v5, v3);
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 1664))(WdfDriverGlobals, v4);
}

```

## disassembly

```asm
0x14000f300  mov     [rsp+arg_0], rbx
0x14000f305  push    rdi
0x14000f306  sub     rsp, 20h
0x14000f30a  mov     rax, cs:WdfFunctions_01031
0x14000f311  mov     ebx, r8d
0x14000f314  mov     r8, cs:off_14005DFE8
0x14000f31b  mov     rdi, rdx
0x14000f31e  mov     rcx, cs:WdfDriverGlobals
0x14000f325  mov     rax, [rax+650h]
0x14000f32c  call    _guard_dispatch_icall
0x14000f331  mov     edx, ebx; int
0x14000f333  mov     rcx, rax; this
0x14000f336  call    ?Complete@MbxRequest@@QEAAXJ@Z; MbxRequest::Complete(long)
0x14000f33b  mov     rax, cs:WdfFunctions_01031
0x14000f342  mov     rdx, rdi
0x14000f345  mov     rcx, cs:WdfDriverGlobals
0x14000f34c  mov     rax, [rax+680h]
0x14000f353  call    _guard_dispatch_icall
0x14000f358  mov     rbx, [rsp+28h+arg_0]
0x14000f35d  add     rsp, 20h
0x14000f361  pop     rdi
0x14000f362  retn
```
