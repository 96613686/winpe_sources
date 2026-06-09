# _Init_thread_header

- ea: `0x1800224d8`
- end: `0x18002253d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001dc14`

## callees

- `0x1800224d8`
- `0x18002258c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022536`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800224e8`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_180040230);
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
  LeaveCriticalSection(&stru_180040230);
}

```

## disassembly

```asm
0x1800224d8  push    rbx
0x1800224da  sub     rsp, 20h
0x1800224de  mov     rbx, rcx
0x1800224e1  lea     rcx, stru_180040230; lpCriticalSection
0x1800224e8  call    cs:__imp_EnterCriticalSection
0x1800224ee  cmp     dword ptr [rbx], 0
0x1800224f1  jnz     short loc_180022502
0x1800224f3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800224f9  jmp     short loc_18002252A
0x1800224fb  call    _Init_thread_wait_v2
0x180022500  jmp     short loc_1800224EE
0x180022502  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180022505  jz      short loc_1800224FB
0x180022507  mov     rax, gs:58h
0x180022510  mov     ecx, cs:_tls_index
0x180022516  mov     r8d, 4
0x18002251c  mov     rdx, [rax+rcx*8]
0x180022520  mov     eax, cs:_Init_global_epoch
0x180022526  mov     [r8+rdx], eax
0x18002252a  lea     rcx, stru_180040230
0x180022531  add     rsp, 20h
0x180022535  pop     rbx
0x180022536  jmp     cs:__imp_LeaveCriticalSection
```
