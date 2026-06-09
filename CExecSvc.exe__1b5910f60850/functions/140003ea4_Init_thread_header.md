# _Init_thread_header

- ea: `0x140003ea4`
- end: `0x140003f09`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001ce88`

## callees

- `0x140003ea4`
- `0x140003f58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003eb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003f02`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_140039DB8);
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
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_140039DB8);
}

```

## disassembly

```asm
0x140003ea4  push    rbx
0x140003ea6  sub     rsp, 20h
0x140003eaa  mov     rbx, rcx
0x140003ead  lea     rcx, stru_140039DB8; lpCriticalSection
0x140003eb4  call    cs:__imp_EnterCriticalSection
0x140003eba  cmp     dword ptr [rbx], 0
0x140003ebd  jnz     short loc_140003ECE
0x140003ebf  mov     dword ptr [rbx], 0FFFFFFFFh
0x140003ec5  jmp     short loc_140003EF6
0x140003ec7  call    _Init_thread_wait_v2
0x140003ecc  jmp     short loc_140003EBA
0x140003ece  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140003ed1  jz      short loc_140003EC7
0x140003ed3  mov     rax, gs:58h
0x140003edc  mov     ecx, cs:_tls_index
0x140003ee2  mov     r8d, 10h
0x140003ee8  mov     rdx, [rax+rcx*8]
0x140003eec  mov     eax, cs:_Init_global_epoch
0x140003ef2  mov     [r8+rdx], eax
0x140003ef6  lea     rcx, stru_140039DB8
0x140003efd  add     rsp, 20h
0x140003f01  pop     rbx
0x140003f02  jmp     cs:__imp_LeaveCriticalSection
```
