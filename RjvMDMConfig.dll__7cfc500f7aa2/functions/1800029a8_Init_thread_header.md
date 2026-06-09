# _Init_thread_header

- ea: `0x1800029a8`
- end: `0x180002a0d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b9d8`

## callees

- `0x1800029a8`
- `0x180002a5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800029b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002a06`

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
0x1800029a8  push    rbx
0x1800029aa  sub     rsp, 20h
0x1800029ae  mov     rbx, rcx
0x1800029b1  lea     rcx, CriticalSection; lpCriticalSection
0x1800029b8  call    cs:__imp_EnterCriticalSection
0x1800029be  cmp     dword ptr [rbx], 0
0x1800029c1  jnz     short loc_1800029D2
0x1800029c3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800029c9  jmp     short loc_1800029FA
0x1800029cb  call    _Init_thread_wait_v2
0x1800029d0  jmp     short loc_1800029BE
0x1800029d2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800029d5  jz      short loc_1800029CB
0x1800029d7  mov     rax, gs:58h
0x1800029e0  mov     ecx, cs:_tls_index
0x1800029e6  mov     r8d, 4
0x1800029ec  mov     rdx, [rax+rcx*8]
0x1800029f0  mov     eax, cs:_Init_global_epoch
0x1800029f6  mov     [r8+rdx], eax
0x1800029fa  lea     rcx, CriticalSection
0x180002a01  add     rsp, 20h
0x180002a05  pop     rbx
0x180002a06  jmp     cs:__imp_LeaveCriticalSection
```
