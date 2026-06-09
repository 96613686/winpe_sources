# ZtFreeTrustedCa

- ea: `0x18000dc74`
- end: `0x18000dca7`
- name: `ZtFreeTrustedCa`
- size: `51`
- prototype: `void __fastcall(LPVOID *lpMem)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e00`
- `0x1800049b0`
- `0x180009808`
- `0x1800099a8`
- `0x180011b68`
- `0x180011d64`
- `0x180011e34`

## callees

- `0x18000dc74`
- `0x1800125d4`

## pseudocode

```c
void __fastcall ZtFreeTrustedCa(LPVOID *lpMem)
{
  if ( lpMem )
  {
    Dns_Free(lpMem[2]);
    lpMem[2] = 0;
    *((_DWORD *)lpMem + 6) = 0;
    Dns_Free(lpMem);
  }
}

```

## disassembly

```asm
0x18000dc74  test    rcx, rcx
0x18000dc77  jz      short locret_18000DCA6
0x18000dc79  push    rbx
0x18000dc7a  sub     rsp, 20h
0x18000dc7e  mov     rbx, rcx
0x18000dc81  mov     rcx, [rcx+10h]; lpMem
0x18000dc85  call    Dns_Free
0x18000dc8a  mov     rcx, rbx; lpMem
0x18000dc8d  mov     qword ptr [rbx+10h], 0
0x18000dc95  mov     dword ptr [rbx+18h], 0
0x18000dc9c  call    Dns_Free
0x18000dca1  add     rsp, 20h
0x18000dca5  pop     rbx
0x18000dca6  retn
```
