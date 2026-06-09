# _Init_thread_header

- ea: `0x180046c54`
- end: `0x180046cb9`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006d8b0`

## callees

- `0x180046c54`
- `0x180046d08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046cb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046c64`

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
0x180046c54  push    rbx
0x180046c56  sub     rsp, 20h
0x180046c5a  mov     rbx, rcx
0x180046c5d  lea     rcx, CriticalSection; lpCriticalSection
0x180046c64  call    cs:__imp_EnterCriticalSection
0x180046c6a  cmp     dword ptr [rbx], 0
0x180046c6d  jnz     short loc_180046C7E
0x180046c6f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180046c75  jmp     short loc_180046CA6
0x180046c77  call    _Init_thread_wait_v2
0x180046c7c  jmp     short loc_180046C6A
0x180046c7e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180046c81  jz      short loc_180046C77
0x180046c83  mov     rax, gs:58h
0x180046c8c  mov     ecx, cs:_tls_index
0x180046c92  mov     r8d, 4
0x180046c98  mov     rdx, [rax+rcx*8]
0x180046c9c  mov     eax, cs:_Init_global_epoch
0x180046ca2  mov     [r8+rdx], eax
0x180046ca6  lea     rcx, CriticalSection
0x180046cad  add     rsp, 20h
0x180046cb1  pop     rbx
0x180046cb2  jmp     cs:__imp_LeaveCriticalSection
```
