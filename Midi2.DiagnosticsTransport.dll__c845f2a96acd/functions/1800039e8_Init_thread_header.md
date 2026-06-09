# _Init_thread_header

- ea: `0x1800039e8`
- end: `0x180003a4d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011190`

## callees

- `0x1800039e8`
- `0x180003a9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800039f8`

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
0x1800039e8  push    rbx
0x1800039ea  sub     rsp, 20h
0x1800039ee  mov     rbx, rcx
0x1800039f1  lea     rcx, CriticalSection; lpCriticalSection
0x1800039f8  call    cs:__imp_EnterCriticalSection
0x1800039fe  cmp     dword ptr [rbx], 0
0x180003a01  jnz     short loc_180003A12
0x180003a03  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003a09  jmp     short loc_180003A3A
0x180003a0b  call    _Init_thread_wait_v2
0x180003a10  jmp     short loc_1800039FE
0x180003a12  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003a15  jz      short loc_180003A0B
0x180003a17  mov     rax, gs:58h
0x180003a20  mov     ecx, cs:_tls_index
0x180003a26  mov     r8d, 4
0x180003a2c  mov     rdx, [rax+rcx*8]
0x180003a30  mov     eax, cs:_Init_global_epoch
0x180003a36  mov     [r8+rdx], eax
0x180003a3a  lea     rcx, CriticalSection
0x180003a41  add     rsp, 20h
0x180003a45  pop     rbx
0x180003a46  jmp     cs:__imp_LeaveCriticalSection
```
