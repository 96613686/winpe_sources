# _Thrd_current

- ea: `0x18030a15c`
- end: `0x18030a1dc`
- name: `_Thrd_current`
- size: `128`
- prototype: `_Thrd_t *__cdecl(_Thrd_t *__return_ptr __struct_ptr retstr)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18030a2ac`

## callees

- `0x18030a15c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18030a1b4`
- `KERNEL32!CloseHandle` at `0x18030a1b4`
- `KERNEL32!GetCurrentProcess` at `0x18030a16e`
- `KERNEL32!GetCurrentProcess` at `0x18030a180`
- `KERNEL32!GetCurrentProcess` at `0x18030a16e`
- `KERNEL32!GetCurrentProcess` at `0x18030a180`
- `KERNEL32!GetCurrentThreadId` at `0x18030a1c0`
- `KERNEL32!GetCurrentThreadId` at `0x18030a1c0`
- `KERNEL32!DuplicateHandle` at `0x18030a1a7`
- `KERNEL32!DuplicateHandle` at `0x18030a1a7`
- `KERNEL32!GetCurrentThread` at `0x18030a177`
- `KERNEL32!GetCurrentThread` at `0x18030a177`

## pseudocode

```c
_Thrd_t *__cdecl Thrd_current(_Thrd_t *__return_ptr retstr)
{
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v4; // rax

  CurrentProcess = GetCurrentProcess();
  CurrentThread = GetCurrentThread();
  v4 = GetCurrentProcess();
  if ( DuplicateHandle(v4, CurrentThread, CurrentProcess, &retstr->_Hnd, 2u, 1, 0) )
    CloseHandle(retstr->_Hnd);
  else
    retstr->_Hnd = 0;
  retstr->_Id = GetCurrentThreadId();
  return retstr;
}

```

## disassembly

```asm
0x18030a15c  mov     [rsp+arg_0], rbx
0x18030a161  mov     [rsp+arg_8], rsi
0x18030a166  push    rdi
0x18030a167  sub     rsp, 40h
0x18030a16b  mov     rsi, rcx
0x18030a16e  call    cs:__imp_GetCurrentProcess
0x18030a174  mov     rdi, rax
0x18030a177  call    cs:__imp_GetCurrentThread
0x18030a17d  mov     rbx, rax
0x18030a180  call    cs:__imp_GetCurrentProcess
0x18030a186  and     [rsp+48h+var_18], 0
0x18030a18b  mov     r9, rsi; lpTargetHandle
0x18030a18e  mov     rcx, rax; hSourceProcessHandle
0x18030a191  mov     [rsp+48h+bInheritHandle], 1; bInheritHandle
0x18030a199  mov     r8, rdi; hTargetProcessHandle
0x18030a19c  mov     [rsp+48h+dwDesiredAccess], 2; dwDesiredAccess
0x18030a1a4  mov     rdx, rbx; hSourceHandle
0x18030a1a7  call    cs:__imp_DuplicateHandle
0x18030a1ad  test    eax, eax
0x18030a1af  jz      short loc_18030A1BC
0x18030a1b1  mov     rcx, [rsi]; hObject
0x18030a1b4  call    cs:__imp_CloseHandle
0x18030a1ba  jmp     short loc_18030A1C0
0x18030a1bc  and     qword ptr [rsi], 0
0x18030a1c0  call    cs:__imp_GetCurrentThreadId
0x18030a1c6  mov     rbx, [rsp+48h+arg_0]
0x18030a1cb  mov     [rsi+8], eax
0x18030a1ce  mov     rax, rsi
0x18030a1d1  mov     rsi, [rsp+48h+arg_8]
0x18030a1d6  add     rsp, 40h
0x18030a1da  pop     rdi
0x18030a1db  retn
```
