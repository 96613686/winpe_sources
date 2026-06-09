# XC_WriteT1PStackValue

- ea: `0x180052f30`
- end: `0x180052fb3`
- name: `XC_WriteT1PStackValue`
- size: `131`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x18004e918`
- `0x18004eff8`
- `0x18004f944`
- `0x18004fa84`
- `0x18004fbc4`
- `0x18004fe44`
- `0x18004ff08`
- `0x18005017c`
- `0x180050620`
- `0x1800506a4`
- `0x180050770`
- `0x180050de0`
- `0x180050e84`
- `0x18005152c`
- `0x180052154`
- `0x180052370`

## callees

- `0x180050c90`
- `0x180052ed8`
- `0x180052f30`

## pseudocode

```c
__int64 __fastcall XC_WriteT1PStackValue(__int64 a1, _DWORD *a2, unsigned int a3)
{
  __int64 v5; // rdx
  int v8; // r14d
  int i; // ebp

  v5 = (unsigned int)a2[1];
  if ( !*a2 )
    return WriteFixed(a1, v5);
  WriteFixed(a1, v5);
  v8 = a2[1];
  for ( i = 1; i < *(_DWORD *)(a1 + 488); ++i )
    WriteFixed(a1, (unsigned int)(a2[i + 1] - v8));
  WriteFixed(a1, 393216);
  return XC_WriteT1OpCode(a1, 10, a3);
}

```

## disassembly

```asm
0x180052f30  push    rbx
0x180052f32  push    rbp
0x180052f33  push    rsi
0x180052f34  push    rdi
0x180052f35  push    r14
0x180052f37  sub     rsp, 20h
0x180052f3b  mov     rsi, rdx
0x180052f3e  mov     edi, r8d
0x180052f41  mov     edx, [rdx+4]
0x180052f44  mov     rbx, rcx
0x180052f47  cmp     dword ptr [rsi], 0
0x180052f4a  jnz     short loc_180052F53
0x180052f4c  call    WriteFixed
0x180052f51  jmp     short loc_180052FA8
0x180052f53  call    WriteFixed
0x180052f58  mov     r14d, [rsi+4]
0x180052f5c  mov     ebp, 1
0x180052f61  cmp     [rbx+1E8h], ebp
0x180052f67  jle     short loc_180052F88
0x180052f69  movsxd  rax, ebp
0x180052f6c  mov     r8d, edi
0x180052f6f  mov     rcx, rbx
0x180052f72  mov     edx, [rsi+rax*4+4]
0x180052f76  sub     edx, r14d
0x180052f79  call    WriteFixed
0x180052f7e  inc     ebp
0x180052f80  cmp     ebp, [rbx+1E8h]
0x180052f86  jl      short loc_180052F69
0x180052f88  mov     r8d, edi
0x180052f8b  mov     edx, 60000h
0x180052f90  mov     rcx, rbx
0x180052f93  call    WriteFixed
0x180052f98  mov     edx, 0Ah
0x180052f9d  mov     r8d, edi
0x180052fa0  mov     rcx, rbx
0x180052fa3  call    XC_WriteT1OpCode
0x180052fa8  add     rsp, 20h
0x180052fac  pop     r14
0x180052fae  pop     rdi
0x180052faf  pop     rsi
0x180052fb0  pop     rbp
0x180052fb1  pop     rbx
0x180052fb2  retn
```
