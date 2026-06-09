# TaskDialogIndirect

- ea: `0x180012d6c`
- end: `0x180012dce`
- name: `TaskDialogIndirect`
- size: `98`
- prototype: `HRESULT __stdcall(const TASKDIALOGCONFIG *pTaskConfig, int *pnButton, int *pnRadioButton, BOOL *pfVerificationFlagChecked)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007ba8`

## callees

- `0x180012d6c`
- `0x180012dd4`
- `0x180014010`

## string_xrefs

- `0x180012d8e`: `TaskDialogIndirect`

## pseudocode

```c
HRESULT __stdcall TaskDialogIndirect(
        const TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton,
        int *pnRadioButton,
        BOOL *pfVerificationFlagChecked)
{
  __int64 (__fastcall *v4)(const TASKDIALOGCONFIG *, int *, int *, BOOL *); // rax

  v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18001C0E8;
  if ( qword_18001C0E8 == -1 )
  {
    GetProcFromComCtl32(&qword_18001C0E8, "TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18001C0E8;
  }
  if ( v4 )
    return v4(pTaskConfig, pnButton, pnRadioButton, pfVerificationFlagChecked);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180012d6c  push    rbx
0x180012d6e  push    rbp
0x180012d6f  push    rsi
0x180012d70  push    rdi
0x180012d71  sub     rsp, 38h
0x180012d75  mov     rax, cs:qword_18001C0E8
0x180012d7c  mov     rbx, r9
0x180012d7f  mov     rdi, r8
0x180012d82  mov     rsi, rdx
0x180012d85  mov     rbp, rcx
0x180012d88  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012d8c  jnz     short loc_180012DA8
0x180012d8e  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180012d95  lea     rcx, qword_18001C0E8
0x180012d9c  call    _GetProcFromComCtl32
0x180012da1  mov     rax, cs:qword_18001C0E8
0x180012da8  test    rax, rax
0x180012dab  jz      short loc_180012DC0
0x180012dad  mov     r9, rbx
0x180012db0  mov     r8, rdi
0x180012db3  mov     rdx, rsi
0x180012db6  mov     rcx, rbp
0x180012db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dbe  jmp     short loc_180012DC5
0x180012dc0  mov     eax, 80004005h
0x180012dc5  add     rsp, 38h
0x180012dc9  pop     rdi
0x180012dca  pop     rsi
0x180012dcb  pop     rbp
0x180012dcc  pop     rbx
0x180012dcd  retn
```
