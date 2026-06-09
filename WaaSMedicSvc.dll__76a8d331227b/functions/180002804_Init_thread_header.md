# _Init_thread_header

- ea: `0x180002804`
- end: `0x180002869`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f58`
- `0x18000b900`
- `0x18000b9d0`
- `0x18000bac0`

## callees

- `0x180002804`
- `0x1800028b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002862`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002814`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002814`

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
0x180002804  push    rbx
0x180002806  sub     rsp, 20h
0x18000280a  mov     rbx, rcx
0x18000280d  lea     rcx, CriticalSection; lpCriticalSection
0x180002814  call    cs:__imp_EnterCriticalSection
0x18000281a  cmp     dword ptr [rbx], 0
0x18000281d  jnz     short loc_18000282E
0x18000281f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002825  jmp     short loc_180002856
0x180002827  call    _Init_thread_wait_v2
0x18000282c  jmp     short loc_18000281A
0x18000282e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002831  jz      short loc_180002827
0x180002833  mov     rax, gs:58h
0x18000283c  mov     ecx, cs:_tls_index
0x180002842  mov     r8d, 4
0x180002848  mov     rdx, [rax+rcx*8]
0x18000284c  mov     eax, cs:_Init_global_epoch
0x180002852  mov     [r8+rdx], eax
0x180002856  lea     rcx, CriticalSection
0x18000285d  add     rsp, 20h
0x180002861  pop     rbx
0x180002862  jmp     cs:__imp_LeaveCriticalSection
```
