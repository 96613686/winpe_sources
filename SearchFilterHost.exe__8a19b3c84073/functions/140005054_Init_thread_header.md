# _Init_thread_header

- ea: `0x140005054`
- end: `0x1400050b9`
- name: `_Init_thread_header`
- size: `101`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400283a0`
- `0x14002dccc`
- `0x14002de18`
- `0x14002e0cc`
- `0x14002e360`
- `0x140033030`
- `0x1400361b8`
- `0x140036a80`
- `0x14003e5a4`
- `0x14003e844`
- `0x1400478a4`
- `0x140047c98`
- `0x140049388`
- `0x140049454`
- `0x140049520`

## callees

- `0x140005054`
- `0x140005108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400050b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005064`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140005064`

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
0x140005054  push    rbx
0x140005056  sub     rsp, 20h
0x14000505a  mov     rbx, rcx
0x14000505d  lea     rcx, CriticalSection; lpCriticalSection
0x140005064  call    cs:__imp_EnterCriticalSection
0x14000506a  cmp     dword ptr [rbx], 0
0x14000506d  jnz     short loc_14000507E
0x14000506f  mov     dword ptr [rbx], 0FFFFFFFFh
0x140005075  jmp     short loc_1400050A6
0x140005077  call    _Init_thread_wait_v2
0x14000507c  jmp     short loc_14000506A
0x14000507e  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140005081  jz      short loc_140005077
0x140005083  mov     rax, gs:58h
0x14000508c  mov     ecx, cs:_tls_index
0x140005092  mov     r8d, 4
0x140005098  mov     rdx, [rax+rcx*8]
0x14000509c  mov     eax, cs:_Init_global_epoch
0x1400050a2  mov     [r8+rdx], eax
0x1400050a6  lea     rcx, CriticalSection
0x1400050ad  add     rsp, 20h
0x1400050b1  pop     rbx
0x1400050b2  jmp     cs:__imp_LeaveCriticalSection
```
