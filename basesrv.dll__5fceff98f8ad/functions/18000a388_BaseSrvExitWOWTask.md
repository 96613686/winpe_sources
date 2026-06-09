# BaseSrvExitWOWTask

- ea: `0x18000a388`
- end: `0x18000a41b`
- name: `BaseSrvExitWOWTask`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000a2a0`

## callees

- `0x180009a08`
- `0x18000a388`
- `0x18000a764`
- `0x18000c16c`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000a3ac`
- `ntdll!RtlEnterCriticalSection` at `0x18000a3ac`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a3fc`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a3fc`

## pseudocode

```c
__int64 __fastcall BaseSrvExitWOWTask(__int64 a1, int a2)
{
  __int64 v4; // rcx
  int SharedWowRecordByConsoleHandle; // ebx
  int v6; // eax
  _QWORD *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
  SharedWowRecordByConsoleHandle = BaseSrvFindSharedWowRecordByConsoleHandle(v4, *(_QWORD *)a1, &v8);
  if ( SharedWowRecordByConsoleHandle >= 0 )
  {
    if ( a2 == *((_DWORD *)v8 + 20) )
    {
      if ( *(_DWORD *)(a1 + 8) == -1 )
        v6 = BaseSrvDeleteSharedWowRecord((__int64)v8, v8);
      else
        v6 = BaseSrvRemoveWOWRecordByTaskId();
      SharedWowRecordByConsoleHandle = v6;
    }
    else
    {
      SharedWowRecordByConsoleHandle = -1073741811;
    }
  }
  RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
  return (unsigned int)SharedWowRecordByConsoleHandle;
}

```

## disassembly

```asm
0x18000a388  mov     [rsp+arg_8], rbx
0x18000a38d  mov     [rsp+arg_10], rsi
0x18000a392  push    rdi
0x18000a393  sub     rsp, 20h
0x18000a397  mov     rdi, rcx
0x18000a39a  mov     [rsp+28h+arg_0], 0
0x18000a3a3  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a3aa  mov     esi, edx
0x18000a3ac  call    cs:__imp_RtlEnterCriticalSection
0x18000a3b3  nop     dword ptr [rax+rax+00h]
0x18000a3b8  mov     rdx, [rdi]
0x18000a3bb  lea     r8, [rsp+28h+arg_0]
0x18000a3c0  call    BaseSrvFindSharedWowRecordByConsoleHandle
0x18000a3c5  mov     ebx, eax
0x18000a3c7  test    eax, eax
0x18000a3c9  js      short loc_18000A3F5
0x18000a3cb  mov     rcx, [rsp+28h+arg_0]
0x18000a3d0  cmp     esi, [rcx+50h]
0x18000a3d3  jz      short loc_18000A3DC
0x18000a3d5  mov     ebx, 0C000000Dh
0x18000a3da  jmp     short loc_18000A3F5
0x18000a3dc  mov     edx, [rdi+8]
0x18000a3df  cmp     edx, 0FFFFFFFFh
0x18000a3e2  jnz     short loc_18000A3EE
0x18000a3e4  mov     rdx, rcx
0x18000a3e7  call    BaseSrvDeleteSharedWowRecord
0x18000a3ec  jmp     short loc_18000A3F3
0x18000a3ee  call    BaseSrvRemoveWOWRecordByTaskId
0x18000a3f3  mov     ebx, eax
0x18000a3f5  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a3fc  call    cs:__imp_RtlLeaveCriticalSection
0x18000a403  nop     dword ptr [rax+rax+00h]
0x18000a408  mov     rsi, [rsp+28h+arg_10]
0x18000a40d  mov     eax, ebx
0x18000a40f  mov     rbx, [rsp+28h+arg_8]
0x18000a414  add     rsp, 20h
0x18000a418  pop     rdi
0x18000a419  retn
```
