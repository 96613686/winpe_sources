# _Init_thread_header

- ea: `0x140003708`
- end: `0x14000376d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400177b0`

## callees

- `0x140003708`
- `0x1400037bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140003766`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003718`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140003718`

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
0x140003708  push    rbx
0x14000370a  sub     rsp, 20h
0x14000370e  mov     rbx, rcx
0x140003711  lea     rcx, CriticalSection; lpCriticalSection
0x140003718  call    cs:__imp_EnterCriticalSection
0x14000371e  cmp     dword ptr [rbx], 0
0x140003721  jnz     short loc_140003732
0x140003723  mov     dword ptr [rbx], 0FFFFFFFFh
0x140003729  jmp     short loc_14000375A
0x14000372b  call    _Init_thread_wait_v2
0x140003730  jmp     short loc_14000371E
0x140003732  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140003735  jz      short loc_14000372B
0x140003737  mov     rax, gs:58h
0x140003740  mov     ecx, cs:_tls_index
0x140003746  mov     r8d, 4
0x14000374c  mov     rdx, [rax+rcx*8]
0x140003750  mov     eax, cs:_Init_global_epoch
0x140003756  mov     [r8+rdx], eax
0x14000375a  lea     rcx, CriticalSection
0x140003761  add     rsp, 20h
0x140003765  pop     rbx
0x140003766  jmp     cs:__imp_LeaveCriticalSection
```
