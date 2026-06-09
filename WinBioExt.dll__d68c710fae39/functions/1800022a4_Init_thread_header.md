# _Init_thread_header

- ea: `0x1800022a4`
- end: `0x180002309`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006edc`

## callees

- `0x1800022a4`
- `0x180002358`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002302`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022b4`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_1800103E8);
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
  LeaveCriticalSection(&stru_1800103E8);
}

```

## disassembly

```asm
0x1800022a4  push    rbx
0x1800022a6  sub     rsp, 20h
0x1800022aa  mov     rbx, rcx
0x1800022ad  lea     rcx, stru_1800103E8; lpCriticalSection
0x1800022b4  call    cs:__imp_EnterCriticalSection
0x1800022ba  cmp     dword ptr [rbx], 0
0x1800022bd  jnz     short loc_1800022CE
0x1800022bf  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800022c5  jmp     short loc_1800022F6
0x1800022c7  call    _Init_thread_wait_v2
0x1800022cc  jmp     short loc_1800022BA
0x1800022ce  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800022d1  jz      short loc_1800022C7
0x1800022d3  mov     rax, gs:58h
0x1800022dc  mov     ecx, cs:_tls_index
0x1800022e2  mov     r8d, 4
0x1800022e8  mov     rdx, [rax+rcx*8]
0x1800022ec  mov     eax, cs:_Init_global_epoch
0x1800022f2  mov     [r8+rdx], eax
0x1800022f6  lea     rcx, stru_1800103E8
0x1800022fd  add     rsp, 20h
0x180002301  pop     rbx
0x180002302  jmp     cs:__imp_LeaveCriticalSection
```
