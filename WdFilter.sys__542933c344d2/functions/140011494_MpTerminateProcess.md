# MpTerminateProcess

- ea: `0x140011494`
- end: `0x14001153b`
- name: `MpTerminateProcess`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d8f4`

## callees

- `0x140011494`
- `0x1400118d0`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400114e7`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400114e7`
- `ntoskrnl!PsProcessType` at `0x1400114cb`
- `ntoskrnl!ZwTerminateProcess` at `0x140011506`
- `ntoskrnl!ZwTerminateProcess` at `0x140011506`
- `ntoskrnl!ZwClose` at `0x140011519`
- `ntoskrnl!ZwClose` at `0x140011519`

## pseudocode

```c
NTSTATUS __fastcall MpTerminateProcess(void *a1)
{
  NTSTATUS result; // eax
  NTSTATUS v2; // ebx
  HANDLE ProcessHandle; // [rsp+40h] [rbp-18h] BYREF

  if ( !a1 )
    return -1073741816;
  ProcessHandle = 0;
  result = ObOpenObjectByPointer(a1, 0x200u, 0, 0, (POBJECT_TYPE)PsProcessType, 0, &ProcessHandle);
  if ( result >= 0 )
  {
    v2 = ZwTerminateProcess(ProcessHandle, -1073741790);
    ZwClose(ProcessHandle);
    return v2;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x140011494  push    rbx
0x140011496  sub     rsp, 50h
0x14001149a  mov     rax, cs:__security_cookie
0x1400114a1  xor     rax, rsp
0x1400114a4  mov     [rsp+58h+var_10], rax
0x1400114a9  test    rcx, rcx
0x1400114ac  jnz     short loc_1400114B5
0x1400114ae  mov     eax, 0C0000008h
0x1400114b3  jmp     short loc_140011527
0x1400114b5  lea     rax, [rsp+58h+ProcessHandle]
0x1400114ba  mov     [rsp+58h+ProcessHandle], 0
0x1400114c3  mov     [rsp+58h+Handle], rax; Handle
0x1400114c8  xor     r9d, r9d; DesiredAccess
0x1400114cb  mov     rax, cs:__imp_PsProcessType
0x1400114d2  xor     r8d, r8d; PassedAccessState
0x1400114d5  mov     [rsp+58h+AccessMode], 0; AccessMode
0x1400114da  mov     rdx, [rax]
0x1400114dd  mov     [rsp+58h+ObjectType], rdx; ObjectType
0x1400114e2  mov     edx, 200h; HandleAttributes
0x1400114e7  call    cs:__imp_ObOpenObjectByPointer
0x1400114ee  nop     dword ptr [rax+rax+00h]
0x1400114f3  test    eax, eax
0x1400114f5  jns     short loc_1400114FC
0x1400114f7  lfence
0x1400114fa  jmp     short loc_140011527
0x1400114fc  mov     rcx, [rsp+58h+ProcessHandle]; ProcessHandle
0x140011501  mov     edx, 0C0000022h; ExitStatus
0x140011506  call    cs:__imp_ZwTerminateProcess
0x14001150d  nop     dword ptr [rax+rax+00h]
0x140011512  mov     rcx, [rsp+58h+ProcessHandle]; Handle
0x140011517  mov     ebx, eax
0x140011519  call    cs:__imp_ZwClose
0x140011520  nop     dword ptr [rax+rax+00h]
0x140011525  mov     eax, ebx
0x140011527  mov     rcx, [rsp+58h+var_10]
0x14001152c  xor     rcx, rsp; StackCookie
0x14001152f  call    __security_check_cookie
0x140011534  add     rsp, 50h
0x140011538  pop     rbx
0x140011539  retn
```
