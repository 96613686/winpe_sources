# BampTempBoostRemoveCallback

- ea: `0x14000c3f0`
- end: `0x14000c45b`
- name: `BampTempBoostRemoveCallback`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x14000c3f0`
- `0x140010760`
- `0x1400107a0`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!PsGetProcessSessionId` at `0x14000c404`
- `ntoskrnl!PsGetProcessSessionId` at `0x14000c404`

## pseudocode

```c
char __fastcall BampTempBoostRemoveCallback(__int64 a1, __int64 a2)
{
  int v2; // ebx
  unsigned int v5; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a2 + 24);
  if ( v2 == (unsigned int)PsGetProcessSessionId(*(_QWORD *)(a1 + 8)) )
  {
    BampAcquireThrottledProcessLock(a1);
    v5 = *(_DWORD *)(a1 + 280) & 0xFFFFFFEF;
    BampUpdateThrottledProcessState(a1, &v5, 0, 0, 0);
    BampReleaseThrottledProcessLock(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x14000c3f0  mov     [rsp+arg_8], rbx
0x14000c3f5  push    rdi
0x14000c3f6  sub     rsp, 30h
0x14000c3fa  mov     ebx, [rdx+18h]
0x14000c3fd  mov     rdi, rcx
0x14000c400  mov     rcx, [rcx+8]
0x14000c404  call    cs:__imp_PsGetProcessSessionId
0x14000c40b  nop     dword ptr [rax+rax+00h]
0x14000c410  cmp     ebx, eax
0x14000c412  jnz     short loc_14000C44D
0x14000c414  mov     rcx, rdi
0x14000c417  call    BampAcquireThrottledProcessLock
0x14000c41c  mov     eax, [rdi+118h]
0x14000c422  lea     rdx, [rsp+38h+arg_0]
0x14000c427  and     eax, 0FFFFFFEFh
0x14000c42a  mov     [rsp+38h+var_18], 0
0x14000c433  xor     r9d, r9d
0x14000c436  mov     [rsp+38h+arg_0], eax
0x14000c43a  xor     r8d, r8d
0x14000c43d  mov     rcx, rdi
0x14000c440  call    BampUpdateThrottledProcessState
0x14000c445  mov     rcx, rdi
0x14000c448  call    BampReleaseThrottledProcessLock
0x14000c44d  mov     rbx, [rsp+38h+arg_8]
0x14000c452  mov     al, 1
0x14000c454  add     rsp, 30h
0x14000c458  pop     rdi
0x14000c459  retn
```
