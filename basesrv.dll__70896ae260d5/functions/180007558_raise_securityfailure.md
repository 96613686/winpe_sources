# __raise_securityfailure

- ea: `0x180007558`
- end: `0x180007573`
- name: `__raise_securityfailure`
- size: `27`
- prototype: `NTSTATUS __fastcall(struct _EXCEPTION_POINTERS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007718`

## callees

- `0x180007860`
- `0x180007890`

## pseudocode

```c
NTSTATUS __fastcall _raise_securityfailure(struct _EXCEPTION_POINTERS *a1)
{
  RtlUnhandledExceptionFilter_0(a1);
  return NtTerminateProcess_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, -1073740791);
}

```

## disassembly

```asm
0x180007558  sub     rsp, 28h
0x18000755c  call    RtlUnhandledExceptionFilter_0
0x180007561  mov     edx, 0C0000409h; ExitStatus
0x180007566  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000756a  add     rsp, 28h
0x18000756e  jmp     NtTerminateProcess_0
```
