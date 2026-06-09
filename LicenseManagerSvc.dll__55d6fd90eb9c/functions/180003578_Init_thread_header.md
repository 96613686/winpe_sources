# _Init_thread_header

- ea: `0x180003578`
- end: `0x1800035dd`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800060f4`

## callees

- `0x180003578`
- `0x18000362c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800035d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003588`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003588`

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
0x180003578  push    rbx
0x18000357a  sub     rsp, 20h
0x18000357e  mov     rbx, rcx
0x180003581  lea     rcx, CriticalSection; lpCriticalSection
0x180003588  call    cs:__imp_EnterCriticalSection
0x18000358e  cmp     dword ptr [rbx], 0
0x180003591  jnz     short loc_1800035A2
0x180003593  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003599  jmp     short loc_1800035CA
0x18000359b  call    _Init_thread_wait_v2
0x1800035a0  jmp     short loc_18000358E
0x1800035a2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800035a5  jz      short loc_18000359B
0x1800035a7  mov     rax, gs:58h
0x1800035b0  mov     ecx, cs:_tls_index
0x1800035b6  mov     r8d, 4
0x1800035bc  mov     rdx, [rax+rcx*8]
0x1800035c0  mov     eax, cs:_Init_global_epoch
0x1800035c6  mov     [r8+rdx], eax
0x1800035ca  lea     rcx, CriticalSection
0x1800035d1  add     rsp, 20h
0x1800035d5  pop     rbx
0x1800035d6  jmp     cs:__imp_LeaveCriticalSection
```
