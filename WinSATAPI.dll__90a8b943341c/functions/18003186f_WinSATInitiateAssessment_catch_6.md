# WinSATInitiateAssessment$catch$6

- ea: `0x18003186f`
- end: `0x1800318aa`
- name: `WinSATInitiateAssessment$catch$6`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001bf9c`
- `0x18001cc8c`
- `0x18003186f`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18003188a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18003188a`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *WinSATInitiateAssessment_catch_6()
{
  if ( hThread )
    TerminateThread(hThread, 0);
  ResetGlobalState();
  return &loc_18001D2DA;
}

```

## disassembly

```asm
0x18003186f  mov     [rsp+arg_8], rdx
0x180031874  push    rbp
0x180031875  sub     rsp, 30h
0x180031879  mov     rbp, rdx
0x18003187c  mov     rcx, cs:hThread; hThread
0x180031883  test    rcx, rcx
0x180031886  jz      short loc_180031896
0x180031888  xor     edx, edx; dwExitCode
0x18003188a  call    cs:__imp_TerminateThread
0x180031891  nop     dword ptr [rax+rax+00h]
0x180031896  call    ResetGlobalState
0x18003189b  nop
0x18003189c  lea     rax, loc_18001D2DA
0x1800318a3  add     rsp, 30h
0x1800318a7  pop     rbp
0x1800318a8  retn
```
