# _Init_thread_header

- ea: `0x180002628`
- end: `0x18000268d`
- name: `_Init_thread_header`
- size: `101`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012e78`

## callees

- `0x180002628`
- `0x1800026dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002686`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002638`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002638`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180002628  push    rbx
0x18000262a  sub     rsp, 20h
0x18000262e  mov     rbx, rcx
0x180002631  lea     rcx, CriticalSection; lpCriticalSection
0x180002638  call    cs:__imp_EnterCriticalSection
0x18000263e  cmp     dword ptr [rbx], 0
0x180002641  jnz     short loc_180002652
0x180002643  mov     dword ptr [rbx], 0FFFFFFFFh
0x180002649  jmp     short loc_18000267A
0x18000264b  call    _Init_thread_wait_v2
0x180002650  jmp     short loc_18000263E
0x180002652  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180002655  jz      short loc_18000264B
0x180002657  mov     rax, gs:58h
0x180002660  mov     ecx, cs:_tls_index
0x180002666  mov     r8d, 4
0x18000266c  mov     rdx, [rax+rcx*8]
0x180002670  mov     eax, cs:_Init_global_epoch
0x180002676  mov     [r8+rdx], eax
0x18000267a  lea     rcx, CriticalSection
0x180002681  add     rsp, 20h
0x180002685  pop     rbx
0x180002686  jmp     cs:__imp_LeaveCriticalSection
```
