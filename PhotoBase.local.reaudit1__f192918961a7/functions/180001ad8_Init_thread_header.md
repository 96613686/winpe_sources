# _Init_thread_header

- ea: `0x180001ad8`
- end: `0x180001b3d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047e4`

## callees

- `0x180001ad8`
- `0x180001b8c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180001b36`
- `KERNEL32!EnterCriticalSection` at `0x180001ae8`
- `KERNEL32!EnterCriticalSection` at `0x180001ae8`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&CriticalSection);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait_v2();
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180001ad8  push    rbx
0x180001ada  sub     rsp, 20h
0x180001ade  mov     rbx, rcx
0x180001ae1  lea     rcx, CriticalSection; lpCriticalSection
0x180001ae8  call    cs:__imp_EnterCriticalSection
0x180001aee  cmp     dword ptr [rbx], 0
0x180001af1  jnz     short loc_180001B02
0x180001af3  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001af9  jmp     short loc_180001B2A
0x180001afb  call    _Init_thread_wait_v2
0x180001b00  jmp     short loc_180001AEE
0x180001b02  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001b05  jz      short loc_180001AFB
0x180001b07  mov     rax, gs:58h
0x180001b10  mov     ecx, cs:_tls_index
0x180001b16  mov     r8d, 4
0x180001b1c  mov     rdx, [rax+rcx*8]
0x180001b20  mov     eax, cs:_Init_global_epoch
0x180001b26  mov     [r8+rdx], eax
0x180001b2a  lea     rcx, CriticalSection
0x180001b31  add     rsp, 20h
0x180001b35  pop     rbx
0x180001b36  jmp     cs:__imp_LeaveCriticalSection
```
