# _Init_thread_header

- ea: `0x140025048`
- end: `0x1400250af`
- name: `_Init_thread_header`
- size: `103`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14003f324`
- `0x1400a4b88`

## callees

- `0x140025048`
- `0x1400250f4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140025058`
- `KERNEL32!EnterCriticalSection` at `0x140025058`
- `KERNEL32!LeaveCriticalSection` at `0x1400250a8`

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
    Init_thread_wait(0x64u);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex) + 4LL) = dword_1400D6930;
LABEL_7:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140025048  push    rbx
0x14002504a  sub     rsp, 20h
0x14002504e  mov     rbx, rcx
0x140025051  lea     rcx, CriticalSection; lpCriticalSection
0x140025058  call    cs:EnterCriticalSection
0x14002505e  cmp     dword ptr [rbx], 0
0x140025061  jnz     short loc_140025074
0x140025063  or      dword ptr [rbx], 0FFFFFFFFh
0x140025066  jmp     short loc_14002509C
0x140025068  mov     ecx, 64h ; 'd'; dwMilliseconds
0x14002506d  call    _Init_thread_wait
0x140025072  jmp     short loc_14002505E
0x140025074  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140025077  jz      short loc_140025068
0x140025079  mov     rax, gs:58h
0x140025082  mov     ecx, cs:TlsIndex
0x140025088  mov     r8d, 4
0x14002508e  mov     rdx, [rax+rcx*8]
0x140025092  mov     eax, cs:dword_1400D6930
0x140025098  mov     [r8+rdx], eax
0x14002509c  lea     rcx, CriticalSection
0x1400250a3  add     rsp, 20h
0x1400250a7  pop     rbx
0x1400250a8  jmp     cs:LeaveCriticalSection
```
