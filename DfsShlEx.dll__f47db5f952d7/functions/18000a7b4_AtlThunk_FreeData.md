# AtlThunk_FreeData

- ea: `0x18000a7b4`
- end: `0x18000a80b`
- name: `AtlThunk_FreeData`
- size: `87`
- prototype: `void __stdcall(AtlThunkData_t *Thunk)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800082c8`
- `0x180008390`

## callees

- `0x18000a3c4`
- `0x18000a7b4`
- `0x18000c010`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x18000a7d6`
- `KERNEL32!InterlockedPushEntrySList` at `0x18000a7d6`
- `KERNEL32!GetProcessHeap` at `0x18000a7f1`
- `KERNEL32!GetProcessHeap` at `0x18000a7f1`
- `KERNEL32!HeapFree` at `0x18000a7ff`
- `KERNEL32!HeapFree` at `0x18000a7ff`

## pseudocode

```c
void __stdcall AtlThunk_FreeData(AtlThunkData_t *Thunk)
{
  struct _SLIST_ENTRY *v1; // rdx
  void (__fastcall *ProcAddressAll_void____cdecl___AtlThunkData_t)(_QWORD); // rax
  HANDLE ProcessHeap; // rax

  if ( Thunk )
  {
    v1 = (struct _SLIST_ENTRY *)*((_QWORD *)Thunk + 1);
    if ( v1 )
    {
      if ( *(_DWORD *)Thunk )
      {
        InterlockedPushEntrySList(__AtlThunkPool, v1);
      }
      else
      {
        ProcAddressAll_void____cdecl___AtlThunkData_t = (void (__fastcall *)(_QWORD))GetProcAddressAll_void____cdecl___AtlThunkData_t____();
        if ( ProcAddressAll_void____cdecl___AtlThunkData_t )
          ProcAddressAll_void____cdecl___AtlThunkData_t(*((_QWORD *)Thunk + 1));
      }
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Thunk);
  }
}

```

## disassembly

```asm
0x18000a7b4  test    rcx, rcx
0x18000a7b7  jz      short locret_18000A80A
0x18000a7b9  push    rbx
0x18000a7ba  sub     rsp, 20h
0x18000a7be  mov     rdx, [rcx+8]; ListEntry
0x18000a7c2  mov     rbx, rcx
0x18000a7c5  test    rdx, rdx
0x18000a7c8  jz      short loc_18000A7F1
0x18000a7ca  cmp     dword ptr [rcx], 0
0x18000a7cd  jz      short loc_18000A7DE
0x18000a7cf  mov     rcx, cs:?__AtlThunkPool@@3PEAT_SLIST_HEADER@@EA; ListHead
0x18000a7d6  call    cs:__imp_InterlockedPushEntrySList
0x18000a7dc  jmp     short loc_18000A7F1
0x18000a7de  call    GetProcAddressAll_void____cdecl___AtlThunkData_t____
0x18000a7e3  test    rax, rax
0x18000a7e6  jz      short loc_18000A7F1
0x18000a7e8  mov     rcx, [rbx+8]
0x18000a7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f1  call    cs:__imp_GetProcessHeap
0x18000a7f7  mov     r8, rbx; lpMem
0x18000a7fa  xor     edx, edx; dwFlags
0x18000a7fc  mov     rcx, rax; hHeap
0x18000a7ff  call    cs:__imp_HeapFree
0x18000a805  add     rsp, 20h
0x18000a809  pop     rbx
0x18000a80a  retn
```
