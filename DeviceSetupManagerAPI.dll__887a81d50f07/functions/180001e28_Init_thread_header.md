# _Init_thread_header

- ea: `0x180001e28`
- end: `0x180001e8d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a934`

## callees

- `0x180001e28`
- `0x180001edc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e38`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001e38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001e86`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180017668);
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
  LeaveCriticalSection(&stru_180017668);
}

```

## disassembly

```asm
0x180001e28  push    rbx
0x180001e2a  sub     rsp, 20h
0x180001e2e  mov     rbx, rcx
0x180001e31  lea     rcx, stru_180017668; lpCriticalSection
0x180001e38  call    cs:__imp_EnterCriticalSection
0x180001e3e  cmp     dword ptr [rbx], 0
0x180001e41  jnz     short loc_180001E52
0x180001e43  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001e49  jmp     short loc_180001E7A
0x180001e4b  call    _Init_thread_wait_v2
0x180001e50  jmp     short loc_180001E3E
0x180001e52  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001e55  jz      short loc_180001E4B
0x180001e57  mov     rax, gs:58h
0x180001e60  mov     ecx, cs:_tls_index
0x180001e66  mov     r8d, 4
0x180001e6c  mov     rdx, [rax+rcx*8]
0x180001e70  mov     eax, cs:_Init_global_epoch
0x180001e76  mov     [r8+rdx], eax
0x180001e7a  lea     rcx, stru_180017668
0x180001e81  add     rsp, 20h
0x180001e85  pop     rbx
0x180001e86  jmp     cs:__imp_LeaveCriticalSection
```
