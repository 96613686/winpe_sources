# _Init_thread_header

- ea: `0x18000f808`
- end: `0x18000f86d`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e5e0`
- `0x1800170a0`

## callees

- `0x18000f808`
- `0x18000f8bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f866`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f818`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f818`

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
0x18000f808  push    rbx
0x18000f80a  sub     rsp, 20h
0x18000f80e  mov     rbx, rcx
0x18000f811  lea     rcx, CriticalSection; lpCriticalSection
0x18000f818  call    cs:__imp_EnterCriticalSection
0x18000f81e  cmp     dword ptr [rbx], 0
0x18000f821  jnz     short loc_18000F832
0x18000f823  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000f829  jmp     short loc_18000F85A
0x18000f82b  call    _Init_thread_wait_v2
0x18000f830  jmp     short loc_18000F81E
0x18000f832  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000f835  jz      short loc_18000F82B
0x18000f837  mov     rax, gs:58h
0x18000f840  mov     ecx, cs:_tls_index
0x18000f846  mov     r8d, 4
0x18000f84c  mov     rdx, [rax+rcx*8]
0x18000f850  mov     eax, cs:_Init_global_epoch
0x18000f856  mov     [r8+rdx], eax
0x18000f85a  lea     rcx, CriticalSection
0x18000f861  add     rsp, 20h
0x18000f865  pop     rbx
0x18000f866  jmp     cs:__imp_LeaveCriticalSection
```
