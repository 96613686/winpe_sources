# PerfScenarioStop

- ea: `0x14004af80`
- end: `0x14004b00c`
- name: `PerfScenarioStop`
- size: `140`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400497bc`
- `0x14005d078`

## callees

- `0x1400079f0`
- `0x14004af80`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x14004afaa`
- `ntoskrnl!EtwEventEnabled` at `0x14004afaa`
- `ntoskrnl!EtwWrite` at `0x14004affe`
- `ntoskrnl!EtwWrite` at `0x14004affe`

## pseudocode

```c
void __fastcall PerfScenarioStop(PCEVENT_DESCRIPTOR EventDescriptor, int a2)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-28h] BYREF
  int v4; // [rsp+68h] [rbp+10h] BYREF

  v4 = a2;
  if ( AhcPerfTracingHandle )
  {
    if ( EtwEventEnabled(AhcPerfTracingHandle, EventDescriptor) )
    {
      UserData.Ptr = (ULONGLONG)&v4;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(AhcPerfTracingHandle, EventDescriptor, 0, 1u, &UserData);
    }
  }
}

```

## disassembly

```asm
0x14004af80  mov     [rsp+arg_8], edx
0x14004af84  push    rbx
0x14004af85  sub     rsp, 50h
0x14004af89  mov     rax, cs:__security_cookie
0x14004af90  xor     rax, rsp
0x14004af93  mov     [rsp+58h+var_18], rax
0x14004af98  mov     rbx, rcx
0x14004af9b  mov     rcx, cs:?AhcPerfTracingHandle@@3_KA; RegHandle
0x14004afa2  test    rcx, rcx
0x14004afa5  jz      short loc_14004AFBA
0x14004afa7  mov     rdx, rbx; EventDescriptor
0x14004afaa  call    cs:__imp_EtwEventEnabled
0x14004afb1  nop     dword ptr [rax+rax+00h]
0x14004afb6  test    al, al
0x14004afb8  jnz     short loc_14004AFCE
0x14004afba  mov     rcx, [rsp+58h+var_18]
0x14004afbf  xor     rcx, rsp; StackCookie
0x14004afc2  call    __security_check_cookie
0x14004afc7  add     rsp, 50h
0x14004afcb  pop     rbx
0x14004afcc  retn
0x14004afce  mov     rcx, cs:?AhcPerfTracingHandle@@3_KA; RegHandle
0x14004afd5  lea     rax, [rsp+58h+arg_8]
0x14004afda  mov     [rsp+58h+var_28.Ptr], rax
0x14004afdf  mov     r9d, 1; UserDataCount
0x14004afe5  lea     rax, [rsp+58h+var_28]
0x14004afea  mov     qword ptr [rsp+58h+var_28.Size], 4
0x14004aff3  xor     r8d, r8d; ActivityId
0x14004aff6  mov     [rsp+58h+UserData], rax; UserData
0x14004affb  mov     rdx, rbx; EventDescriptor
0x14004affe  call    cs:__imp_EtwWrite
0x14004b005  nop     dword ptr [rax+rax+00h]
0x14004b00a  jmp     short loc_14004AFBA
```
