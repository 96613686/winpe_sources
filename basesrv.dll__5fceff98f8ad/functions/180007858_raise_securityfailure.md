# __raise_securityfailure

- ea: `0x180007858`
- end: `0x180007873`
- name: `__raise_securityfailure`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007a1c`

## callees

- `0x180007b64`
- `0x180007b94`

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
0x180007858  sub     rsp, 28h
0x18000785c  call    RtlUnhandledExceptionFilter_0
0x180007861  mov     edx, 0C0000409h; ExitStatus
0x180007866  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000786a  add     rsp, 28h
0x18000786e  jmp     NtTerminateProcess_0
```
