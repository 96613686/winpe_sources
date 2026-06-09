# _Init_thread_header

- ea: `0x1400037a8`
- end: `0x14000380d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001848c`

## callees

- `0x1400037a8`
- `0x14000385c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400037b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400037b8`

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
0x1400037a8  push    rbx
0x1400037aa  sub     rsp, 20h
0x1400037ae  mov     rbx, rcx
0x1400037b1  lea     rcx, CriticalSection; lpCriticalSection
0x1400037b8  call    cs:__imp_EnterCriticalSection
0x1400037be  cmp     dword ptr [rbx], 0
0x1400037c1  jnz     short loc_1400037D2
0x1400037c3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400037c9  jmp     short loc_1400037FA
0x1400037cb  call    _Init_thread_wait_v2
0x1400037d0  jmp     short loc_1400037BE
0x1400037d2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1400037d5  jz      short loc_1400037CB
0x1400037d7  mov     rax, gs:58h
0x1400037e0  mov     ecx, cs:_tls_index
0x1400037e6  mov     r8d, 4
0x1400037ec  mov     rdx, [rax+rcx*8]
0x1400037f0  mov     eax, cs:_Init_global_epoch
0x1400037f6  mov     [r8+rdx], eax
0x1400037fa  lea     rcx, CriticalSection
0x140003801  add     rsp, 20h
0x140003805  pop     rbx
0x140003806  jmp     cs:__imp_LeaveCriticalSection
```
