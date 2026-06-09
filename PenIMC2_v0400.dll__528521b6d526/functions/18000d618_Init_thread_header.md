# _Init_thread_header

- ea: `0x18000d618`
- end: `0x18000d67f`
- name: `_Init_thread_header`
- size: `103`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a49c`
- `0x18000a8f0`

## callees

- `0x18000d618`
- `0x18000d6c4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000d628`
- `KERNEL32!EnterCriticalSection` at `0x18000d628`
- `KERNEL32!LeaveCriticalSection` at `0x18000d678`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  EnterCriticalSection(&stru_1800188E8);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    Init_thread_wait(0x64u);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  LeaveCriticalSection(&stru_1800188E8);
}

```

## disassembly

```asm
0x18000d618  push    rbx
0x18000d61a  sub     rsp, 20h
0x18000d61e  mov     rbx, rcx
0x18000d621  lea     rcx, stru_1800188E8; lpCriticalSection
0x18000d628  call    cs:__imp_EnterCriticalSection
0x18000d62e  cmp     dword ptr [rbx], 0
0x18000d631  jnz     short loc_18000D644
0x18000d633  or      dword ptr [rbx], 0FFFFFFFFh
0x18000d636  jmp     short loc_18000D66C
0x18000d638  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000d63d  call    _Init_thread_wait
0x18000d642  jmp     short loc_18000D62E
0x18000d644  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000d647  jz      short loc_18000D638
0x18000d649  mov     rax, gs:58h
0x18000d652  mov     ecx, cs:_tls_index
0x18000d658  mov     r8d, 4
0x18000d65e  mov     rdx, [rax+rcx*8]
0x18000d662  mov     eax, cs:_Init_global_epoch
0x18000d668  mov     [r8+rdx], eax
0x18000d66c  lea     rcx, stru_1800188E8
0x18000d673  add     rsp, 20h
0x18000d677  pop     rbx
0x18000d678  jmp     cs:__imp_LeaveCriticalSection
```
