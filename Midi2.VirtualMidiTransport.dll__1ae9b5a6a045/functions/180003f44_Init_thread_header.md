# _Init_thread_header

- ea: `0x180003f44`
- end: `0x180003fa9`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001adc4`

## callees

- `0x180003f44`
- `0x180003ff8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003fa2`

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
0x180003f44  push    rbx
0x180003f46  sub     rsp, 20h
0x180003f4a  mov     rbx, rcx
0x180003f4d  lea     rcx, CriticalSection; lpCriticalSection
0x180003f54  call    cs:__imp_EnterCriticalSection
0x180003f5a  cmp     dword ptr [rbx], 0
0x180003f5d  jnz     short loc_180003F6E
0x180003f5f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003f65  jmp     short loc_180003F96
0x180003f67  call    _Init_thread_wait_v2
0x180003f6c  jmp     short loc_180003F5A
0x180003f6e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003f71  jz      short loc_180003F67
0x180003f73  mov     rax, gs:58h
0x180003f7c  mov     ecx, cs:_tls_index
0x180003f82  mov     r8d, 4
0x180003f88  mov     rdx, [rax+rcx*8]
0x180003f8c  mov     eax, cs:_Init_global_epoch
0x180003f92  mov     [r8+rdx], eax
0x180003f96  lea     rcx, CriticalSection
0x180003f9d  add     rsp, 20h
0x180003fa1  pop     rbx
0x180003fa2  jmp     cs:__imp_LeaveCriticalSection
```
