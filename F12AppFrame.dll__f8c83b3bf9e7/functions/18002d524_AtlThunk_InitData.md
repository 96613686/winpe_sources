# AtlThunk_InitData

- ea: `0x18002d524`
- end: `0x18002d59d`
- name: `AtlThunk_InitData`
- size: `121`
- prototype: `void __stdcall(AtlThunkData_t *Thunk, void *Proc, size_t FirstParameter)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800075d8`
- `0x1800091d0`
- `0x18000e20c`
- `0x180011158`

## callees

- `0x18002d1d0`
- `0x18002d524`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18002d561`
- `KERNEL32!GetCurrentProcess` at `0x18002d561`
- `KERNEL32!FlushInstructionCache` at `0x18002d573`
- `KERNEL32!FlushInstructionCache` at `0x18002d573`

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
0x18002d524  test    rcx, rcx
0x18002d527  jz      short locret_18002D59C
0x18002d529  push    rbx
0x18002d52a  push    rbp
0x18002d52b  push    rsi
0x18002d52c  push    rdi
0x18002d52d  sub     rsp, 28h
0x18002d531  mov     rbx, [rcx+8]
0x18002d535  mov     rsi, r8
0x18002d538  mov     rbp, rdx
0x18002d53b  mov     rdi, rcx
0x18002d53e  test    rbx, rbx
0x18002d541  jz      short loc_18002D594
0x18002d543  cmp     dword ptr [rcx], 0
0x18002d546  jz      short loc_18002D57B
0x18002d548  mov     word ptr [rbx], 0B948h
0x18002d54d  mov     [rbx+2], r8
0x18002d551  mov     word ptr [rbx+0Ah], 0B848h
0x18002d557  mov     [rbx+0Ch], rdx
0x18002d55b  mov     word ptr [rbx+14h], 0E0FFh
0x18002d561  call    cs:__imp_GetCurrentProcess
0x18002d567  mov     r8d, 16h; dwSize
0x18002d56d  mov     rdx, rbx; lpBaseAddress
0x18002d570  mov     rcx, rax; hProcess
0x18002d573  call    cs:__imp_FlushInstructionCache
0x18002d579  jmp     short loc_18002D594
0x18002d57b  call    GetProcAddressAll_void____cdecl___AtlThunkData_t___void___unsigned___int64__
0x18002d580  test    rax, rax
0x18002d583  jz      short loc_18002D594
0x18002d585  mov     rcx, [rdi+8]
0x18002d589  mov     r8, rsi
0x18002d58c  mov     rdx, rbp
0x18002d58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d594  add     rsp, 28h
0x18002d598  pop     rdi
0x18002d599  pop     rsi
0x18002d59a  pop     rbp
0x18002d59b  pop     rbx
0x18002d59c  retn
```
