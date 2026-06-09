# _Init_thread_header

- ea: `0x140003684`
- end: `0x1400036fa`
- name: `_Init_thread_header`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001e5c8`
- `0x14001e648`

## callees

- `0x140003684`
- `0x140003700`
- `0x14000370c`
- `0x140003724`

## pseudocode

```c
__int64 __fastcall Init_thread_header(_DWORD *a1)
{
  RtlAcquireSRWLockExclusive_0(&qword_140052B50);
  while ( *a1 )
  {
    if ( *a1 != -1 )
    {
      *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
      return RtlReleaseSRWLockExclusive_0(&qword_140052B50);
    }
    RtlSleepConditionVariableSRW_0(&qword_140052B58, &qword_140052B50, 0, 0);
  }
  *a1 = -1;
  return RtlReleaseSRWLockExclusive_0(&qword_140052B50);
}

```

## disassembly

```asm
0x140003684  push    rbx
0x140003686  sub     rsp, 20h
0x14000368a  mov     rbx, rcx
0x14000368d  lea     rcx, qword_140052B50
0x140003694  call    RtlAcquireSRWLockExclusive_0
0x140003699  jmp     short loc_1400036B4
0x14000369b  xor     r9d, r9d
0x14000369e  lea     rdx, qword_140052B50
0x1400036a5  xor     r8d, r8d
0x1400036a8  lea     rcx, qword_140052B58
0x1400036af  call    RtlSleepConditionVariableSRW_0
0x1400036b4  cmp     dword ptr [rbx], 0
0x1400036b7  jz      short loc_1400036E3
0x1400036b9  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1400036bc  jz      short loc_14000369B
0x1400036be  mov     rax, gs:58h
0x1400036c7  mov     ecx, cs:_tls_index
0x1400036cd  mov     r8d, 4
0x1400036d3  mov     rdx, [rax+rcx*8]
0x1400036d7  mov     eax, cs:_Init_global_epoch
0x1400036dd  mov     [r8+rdx], eax
0x1400036e1  jmp     short loc_1400036E9
0x1400036e3  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400036e9  lea     rcx, qword_140052B50
0x1400036f0  add     rsp, 20h
0x1400036f4  pop     rbx
0x1400036f5  jmp     RtlReleaseSRWLockExclusive_0
```
