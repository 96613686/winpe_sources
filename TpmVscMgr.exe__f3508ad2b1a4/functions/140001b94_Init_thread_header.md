# _Init_thread_header

- ea: `0x140001b94`
- end: `0x140001bf9`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f54c`
- `0x140010de0`

## callees

- `0x140001b94`
- `0x140001c48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140001bf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001ba4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140001ba4`

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
0x140001b94  push    rbx
0x140001b96  sub     rsp, 20h
0x140001b9a  mov     rbx, rcx
0x140001b9d  lea     rcx, CriticalSection; lpCriticalSection
0x140001ba4  call    cs:__imp_EnterCriticalSection
0x140001baa  cmp     dword ptr [rbx], 0
0x140001bad  jnz     short loc_140001BBE
0x140001baf  mov     dword ptr [rbx], 0FFFFFFFFh
0x140001bb5  jmp     short loc_140001BE6
0x140001bb7  call    _Init_thread_wait_v2
0x140001bbc  jmp     short loc_140001BAA
0x140001bbe  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140001bc1  jz      short loc_140001BB7
0x140001bc3  mov     rax, gs:58h
0x140001bcc  mov     ecx, cs:_tls_index
0x140001bd2  mov     r8d, 4
0x140001bd8  mov     rdx, [rax+rcx*8]
0x140001bdc  mov     eax, cs:_Init_global_epoch
0x140001be2  mov     [r8+rdx], eax
0x140001be6  lea     rcx, CriticalSection
0x140001bed  add     rsp, 20h
0x140001bf1  pop     rbx
0x140001bf2  jmp     cs:__imp_LeaveCriticalSection
```
