# AtlThunk_InitData

- ea: `0x18000a814`
- end: `0x18000a88d`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009600`

## callees

- `0x18000a4c0`
- `0x18000a814`
- `0x18000c010`

## import_xrefs

- `KERNEL32!FlushInstructionCache` at `0x18000a863`
- `KERNEL32!FlushInstructionCache` at `0x18000a863`
- `KERNEL32!GetCurrentProcess` at `0x18000a851`
- `KERNEL32!GetCurrentProcess` at `0x18000a851`

## pseudocode

```c
void __stdcall AtlThunk_InitData(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)
{
  char *v3; // rbx
  HANDLE CurrentProcess; // rax
  void (__fastcall *ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64)(_QWORD, void *, size_t); // rax

  if ( Thunk )
  {
    v3 = (char *)*((_QWORD *)Thunk + 1);
    if ( v3 )
    {
      if ( *(_DWORD *)Thunk )
      {
        *(_WORD *)v3 = -18104;
        *(_QWORD *)(v3 + 2) = FirstParameter;
        *((_WORD *)v3 + 5) = -18360;
        *(_QWORD *)(v3 + 12) = Proc;
        *((_WORD *)v3 + 10) = -7937;
        CurrentProcess = GetCurrentProcess();
        FlushInstructionCache(CurrentProcess, v3, 0x16u);
      }
      else
      {
        ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 = (void (__fastcall *)(_QWORD, void *, size_t))GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__();
        if ( ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64 )
          ProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64(
            *((_QWORD *)Thunk + 1),
            Proc,
            FirstParameter);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a814  test    rcx, rcx
0x18000a817  jz      short locret_18000A88C
0x18000a819  push    rbx
0x18000a81a  push    rbp
0x18000a81b  push    rsi
0x18000a81c  push    rdi
0x18000a81d  sub     rsp, 28h
0x18000a821  mov     rbx, [rcx+8]
0x18000a825  mov     rsi, r8
0x18000a828  mov     rbp, rdx
0x18000a82b  mov     rdi, rcx
0x18000a82e  test    rbx, rbx
0x18000a831  jz      short loc_18000A884
0x18000a833  cmp     dword ptr [rcx], 0
0x18000a836  jz      short loc_18000A86B
0x18000a838  mov     word ptr [rbx], 0B948h
0x18000a83d  mov     [rbx+2], r8
0x18000a841  mov     word ptr [rbx+0Ah], 0B848h
0x18000a847  mov     [rbx+0Ch], rdx
0x18000a84b  mov     word ptr [rbx+14h], 0E0FFh
0x18000a851  call    cs:__imp_GetCurrentProcess
0x18000a857  mov     r8d, 16h; dwSize
0x18000a85d  mov     rdx, rbx; lpBaseAddress
0x18000a860  mov     rcx, rax; hProcess
0x18000a863  call    cs:__imp_FlushInstructionCache
0x18000a869  jmp     short loc_18000A884
0x18000a86b  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x18000a870  test    rax, rax
0x18000a873  jz      short loc_18000A884
0x18000a875  mov     rcx, [rdi+8]
0x18000a879  mov     r8, rsi
0x18000a87c  mov     rdx, rbp
0x18000a87f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a884  add     rsp, 28h
0x18000a888  pop     rdi
0x18000a889  pop     rsi
0x18000a88a  pop     rbp
0x18000a88b  pop     rbx
0x18000a88c  retn
```
