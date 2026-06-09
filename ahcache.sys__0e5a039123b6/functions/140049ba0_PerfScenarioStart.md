# PerfScenarioStart

- ea: `0x140049ba0`
- end: `0x140049bf6`
- name: `PerfScenarioStart`
- size: `86`
- prototype: `__int64 __fastcall(PCEVENT_DESCRIPTOR EventDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400497bc`
- `0x14005d078`

## callees

- `0x140049ba0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140049bb8`
- `ntoskrnl!EtwEventEnabled` at `0x140049bb8`
- `ntoskrnl!EtwWrite` at `0x140049be8`
- `ntoskrnl!EtwWrite` at `0x140049be8`

## pseudocode

```c
void __fastcall PerfScenarioStart(PCEVENT_DESCRIPTOR EventDescriptor)
{
  if ( AhcPerfTracingHandle )
  {
    if ( EtwEventEnabled(AhcPerfTracingHandle, EventDescriptor) )
      EtwWrite(AhcPerfTracingHandle, EventDescriptor, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x140049ba0  push    rbx
0x140049ba2  sub     rsp, 30h
0x140049ba6  mov     rbx, rcx
0x140049ba9  mov     rcx, cs:?AhcPerfTracingHandle@@3_KA; RegHandle
0x140049bb0  test    rcx, rcx
0x140049bb3  jz      short loc_140049BC8
0x140049bb5  mov     rdx, rbx; EventDescriptor
0x140049bb8  call    cs:__imp_EtwEventEnabled
0x140049bbf  nop     dword ptr [rax+rax+00h]
0x140049bc4  test    al, al
0x140049bc6  jnz     short loc_140049BCF
0x140049bc8  add     rsp, 30h
0x140049bcc  pop     rbx
0x140049bcd  retn
0x140049bcf  mov     rcx, cs:?AhcPerfTracingHandle@@3_KA; RegHandle
0x140049bd6  xor     r9d, r9d; UserDataCount
0x140049bd9  xor     r8d, r8d; ActivityId
0x140049bdc  mov     [rsp+38h+UserData], 0; UserData
0x140049be5  mov     rdx, rbx; EventDescriptor
0x140049be8  call    cs:__imp_EtwWrite
0x140049bef  nop     dword ptr [rax+rax+00h]
0x140049bf4  jmp     short loc_140049BC8
```
