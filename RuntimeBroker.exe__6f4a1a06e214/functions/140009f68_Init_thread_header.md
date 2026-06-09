# _Init_thread_header

- ea: `0x140009f68`
- end: `0x140009fcd`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e7cc`

## callees

- `0x140009f68`
- `0x14000a01c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140009fc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140009f78`

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
0x140009f68  push    rbx
0x140009f6a  sub     rsp, 20h
0x140009f6e  mov     rbx, rcx
0x140009f71  lea     rcx, CriticalSection; lpCriticalSection
0x140009f78  call    cs:__imp_EnterCriticalSection
0x140009f7e  cmp     dword ptr [rbx], 0
0x140009f81  jnz     short loc_140009F92
0x140009f83  mov     dword ptr [rbx], 0FFFFFFFFh
0x140009f89  jmp     short loc_140009FBA
0x140009f8b  call    _Init_thread_wait_v2
0x140009f90  jmp     short loc_140009F7E
0x140009f92  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140009f95  jz      short loc_140009F8B
0x140009f97  mov     rax, gs:58h
0x140009fa0  mov     ecx, cs:_tls_index
0x140009fa6  mov     r8d, 4
0x140009fac  mov     rdx, [rax+rcx*8]
0x140009fb0  mov     eax, cs:_Init_global_epoch
0x140009fb6  mov     [r8+rdx], eax
0x140009fba  lea     rcx, CriticalSection
0x140009fc1  add     rsp, 20h
0x140009fc5  pop     rbx
0x140009fc6  jmp     cs:__imp_LeaveCriticalSection
```
