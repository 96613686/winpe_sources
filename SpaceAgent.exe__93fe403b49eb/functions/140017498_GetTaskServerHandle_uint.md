# GetTaskServerHandle(uint)

- ea: `0x140017498`
- end: `0x1400174b4`
- name: `?GetTaskServerHandle@@YAPEAXI@Z`
- size: `28`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140017b08`
- `0x140017c58`
- `0x1400180c8`
- `0x14001832c`

## callees

- `0x140017498`

## pseudocode

```c
__int64 __fastcall GetTaskServerHandle(unsigned int a1)
{
  if ( dword_140027D8C )
    return *((_QWORD *)&xmmword_140027AA0 + a1);
  else
    return -1;
}

```

## disassembly

```asm
0x140017498  cmp     cs:dword_140027D8C, 0
0x14001749f  jnz     short loc_1400174A6
0x1400174a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400174a5  retn
0x1400174a6  mov     eax, ecx
0x1400174a8  lea     rcx, xmmword_140027AA0
0x1400174af  mov     rax, [rcx+rax*8]
0x1400174b3  retn
```
