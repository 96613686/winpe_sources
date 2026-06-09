# _Init_thread_header

- ea: `0x1400031b8`
- end: `0x14000321d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400269f0`
- `0x140026ad4`

## callees

- `0x1400031b8`
- `0x14000326c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400031c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400031c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003216`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_140052288);
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
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 304LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_140052288);
}

```

## disassembly

```asm
0x1400031b8  push    rbx
0x1400031ba  sub     rsp, 20h
0x1400031be  mov     rbx, rcx
0x1400031c1  lea     rcx, stru_140052288; lpCriticalSection
0x1400031c8  call    cs:__imp_EnterCriticalSection
0x1400031ce  cmp     dword ptr [rbx], 0
0x1400031d1  jnz     short loc_1400031E2
0x1400031d3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400031d9  jmp     short loc_14000320A
0x1400031db  call    _Init_thread_wait_v2
0x1400031e0  jmp     short loc_1400031CE
0x1400031e2  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1400031e5  jz      short loc_1400031DB
0x1400031e7  mov     rax, gs:58h
0x1400031f0  mov     ecx, cs:_tls_index
0x1400031f6  mov     r8d, 130h
0x1400031fc  mov     rdx, [rax+rcx*8]
0x140003200  mov     eax, cs:_Init_global_epoch
0x140003206  mov     [r8+rdx], eax
0x14000320a  lea     rcx, stru_140052288
0x140003211  add     rsp, 20h
0x140003215  pop     rbx
0x140003216  jmp     cs:__imp_LeaveCriticalSection
```
