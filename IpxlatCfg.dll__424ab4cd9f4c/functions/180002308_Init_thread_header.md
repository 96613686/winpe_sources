# _Init_thread_header

- ea: `0x180002308`
- end: `0x18000236d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c314`

## callees

- `0x180002308`
- `0x1800023bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002318`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002318`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180023528);
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
  LeaveCriticalSection(&stru_180023528);
}

```

## disassembly

```asm
0x180002308  push    rbx
0x18000230a  sub     rsp, 20h
0x18000230e  mov     rbx, rcx
0x180002311  lea     rcx, stru_180023528; lpCriticalSection
0x180002318  call    cs:__imp_EnterCriticalSection
0x18000231e  cmp     dword ptr [rbx], 0
0x180002321  jnz     short loc_180002332
0x180002323  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002329  jmp     short loc_18000235A
0x18000232b  call    _Init_thread_wait_v2
0x180002330  jmp     short loc_18000231E
0x180002332  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002335  jz      short loc_18000232B
0x180002337  mov     rax, gs:58h
0x180002340  mov     ecx, cs:_tls_index
0x180002346  mov     r8d, 4
0x18000234c  mov     rdx, [rax+rcx*8]
0x180002350  mov     eax, cs:_Init_global_epoch
0x180002356  mov     [r8+rdx], eax
0x18000235a  lea     rcx, stru_180023528
0x180002361  add     rsp, 20h
0x180002365  pop     rbx
0x180002366  jmp     cs:__imp_LeaveCriticalSection
```
