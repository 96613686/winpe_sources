# HookProcessNotify

- ea: `0x14000ac48`
- end: `0x14000ac98`
- name: `HookProcessNotify`
- size: `80`
- prototype: `__int64 __fastcall(char, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000c614`

## callees

- `0x140001118`
- `0x1400011b0`

## import_xrefs

- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14000ac6d`
- `ntoskrnl!PsSetCreateProcessNotifyRoutineEx` at `0x14000ac6d`

## pseudocode

```c
__int64 __fastcall HookProcessNotify(char a1, __int64 a2, __int64 a3)
{
  unsigned int ProcessNotifyRoutine; // ebx

  DbgTrace(2, "UevFilter.HookProcessNotify: Entry\n", a3);
  ProcessNotifyRoutine = PsSetCreateProcessNotifyRoutineEx(
                           (PCREATE_PROCESS_NOTIFY_ROUTINE_EX)ProcessNotification,
                           a1 == 0);
  DbgTraceFrmt(2u, "UevFilter.HookProcessNotify: Exit, retStatus = 0x%X\n", ProcessNotifyRoutine);
  return ProcessNotifyRoutine;
}

```

## disassembly

```asm
0x14000ac48  push    rbx
0x14000ac4a  sub     rsp, 20h
0x14000ac4e  mov     bl, cl
0x14000ac50  lea     rdx, aUevfilterHookp; "UevFilter.HookProcessNotify: Entry\n"
0x14000ac57  mov     ecx, 2
0x14000ac5c  call    DbgTrace
0x14000ac61  test    bl, bl
0x14000ac63  lea     rcx, ProcessNotification; NotifyRoutine
0x14000ac6a  setz    dl; Remove
0x14000ac6d  call    cs:__imp_PsSetCreateProcessNotifyRoutineEx
0x14000ac74  nop     dword ptr [rax+rax+00h]
0x14000ac79  lea     rdx, aUevfilterHookp_0; "UevFilter.HookProcessNotify: Exit, retS"...
0x14000ac80  mov     ecx, 2
0x14000ac85  mov     r8d, eax
0x14000ac88  mov     ebx, eax
0x14000ac8a  call    DbgTraceFrmt
0x14000ac8f  mov     eax, ebx
0x14000ac91  add     rsp, 20h
0x14000ac95  pop     rbx
0x14000ac96  retn
```
