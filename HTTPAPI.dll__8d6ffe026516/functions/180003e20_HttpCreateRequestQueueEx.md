# HttpCreateRequestQueueEx

- ea: `0x180003e20`
- end: `0x180003fff`
- name: `HttpCreateRequestQueueEx`
- size: `479`
- prototype: `__int64 __fastcall(int, STRSAFE_LPCWSTR, __int64, int, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003660`
- `0x1800082a0`

## callees

- `0x180003e20`
- `0x180004010`
- `0x180004090`

## pseudocode

```c
__int64 __fastcall HttpCreateRequestQueueEx(
        unsigned int a1,
        STRSAFE_LPCWSTR a2,
        __int64 a3,
        int a4,
        int a5,
        _DWORD *a6,
        _QWORD *a7)
{
  __int64 result; // rax
  ULONG v12; // edx
  int v13; // ecx
  int v14; // eax
  int v15; // r8d
  ULONG v16; // eax
  int v17[2]; // [rsp+60h] [rbp-38h] BYREF

  *(_QWORD *)v17 = 0;
  if ( !a7 )
    return 87;
  *a7 = 0;
  if ( (a4 & 0xFFFFFFE0) != 0 )
    return 87;
  if ( (a4 & 4) != 0 && (a4 & 1) == 0 )
    return 87;
  if ( (a4 & 8) != 0 && (a4 & 1) == 0 || (a4 & 2) != 0 && (a4 & 1) != 0 || a6 && (a5 != 1 || *a6 != 1 || (a4 & 1) == 0) )
    return 87;
  if ( !(unsigned int)HttpIsInitialized(1) )
    return 1114;
  if ( (a4 & 1) != 0 )
  {
    if ( !a2 || !*a2 || a3 )
      return 87;
    v12 = 1;
    v13 = -2146435072;
  }
  else
  {
    v13 = -1072693248;
    v12 = 2;
    if ( a2 )
      v13 = -1071906816;
  }
  v14 = v13 | 0x20;
  if ( (a4 & 4) == 0 )
    v14 = v13;
  v15 = v14 | 0x40000000;
  if ( (a4 & 8) == 0 )
    v15 = v14;
  if ( (a4 & 0x10) != 0 )
  {
    if ( (a4 & 1) == 0 || (a4 & 2) != 0 || (a4 & 4) != 0 || (a4 & 8) != 0 )
      return 87;
    v16 = 0x4000;
    v15 = 917504;
  }
  else
  {
    v16 = 0;
  }
  result = HttpApiCreateHandleHelper((int)v17, a1, v15, 1, a2, a4, v12, v16, a3, a5, (__int64)a6);
  if ( !(_DWORD)result )
    *a7 = *(_QWORD *)v17;
  return result;
}

```

## disassembly

```asm
0x180003e20  push    rbx
0x180003e22  push    rbp
0x180003e23  push    rsi
0x180003e24  push    rdi
0x180003e25  push    r14
0x180003e27  sub     rsp, 70h
0x180003e2b  mov     rdi, [rsp+98h+arg_30]
0x180003e33  xor     eax, eax
0x180003e35  mov     qword ptr [rsp+98h+var_38], rax
0x180003e3a  mov     esi, r9d
0x180003e3d  mov     r14, r8
0x180003e40  mov     rbp, rdx
0x180003e43  mov     ebx, ecx
0x180003e45  test    rdi, rdi
0x180003e48  jnz     short loc_180003E5A
0x180003e4a  mov     eax, 57h ; 'W'
0x180003e4f  add     rsp, 70h
0x180003e53  pop     r14
0x180003e55  pop     rdi
0x180003e56  pop     rsi
0x180003e57  pop     rbp
0x180003e58  pop     rbx
0x180003e59  retn
0x180003e5a  mov     [rdi], rax
0x180003e5d  test    esi, 0FFFFFFE0h
0x180003e63  jnz     short loc_180003E4A
0x180003e65  mov     [rsp+98h+arg_0], r12
0x180003e6d  mov     r12d, esi
0x180003e70  mov     [rsp+98h+arg_10], r15
0x180003e78  mov     r15d, esi
0x180003e7b  and     r15d, 1
0x180003e7f  and     r12d, 4
0x180003e83  jz      short loc_180003E94
0x180003e85  test    r15d, r15d
0x180003e88  jnz     short loc_180003E94
0x180003e8a  mov     eax, 57h ; 'W'
0x180003e8f  jmp     loc_180003FE4
0x180003e94  mov     [rsp+98h+arg_8], r13
0x180003e9c  mov     r13d, esi
0x180003e9f  and     r13d, 8
0x180003ea3  jz      short loc_180003EAE
0x180003ea5  test    r15d, r15d
0x180003ea8  jz      loc_180003F7A
0x180003eae  mov     eax, esi
0x180003eb0  and     eax, 2
0x180003eb3  mov     dword ptr [rsp+98h+arg_30], eax
0x180003eba  jz      short loc_180003EC5
0x180003ebc  test    r15d, r15d
0x180003ebf  jnz     loc_180003F7A
0x180003ec5  mov     rax, [rsp+98h+arg_28]
0x180003ecd  test    rax, rax
0x180003ed0  jz      short loc_180003EF2
0x180003ed2  cmp     [rsp+98h+arg_20], 1
0x180003eda  jnz     loc_180003F7A
0x180003ee0  cmp     dword ptr [rax], 1
0x180003ee3  jnz     loc_180003F7A
0x180003ee9  test    r15d, r15d
0x180003eec  jz      loc_180003F7A
0x180003ef2  mov     ecx, 1
0x180003ef7  call    HttpIsInitialized
0x180003efc  test    eax, eax
0x180003efe  jnz     short loc_180003F0A
0x180003f00  mov     eax, 45Ah
0x180003f05  jmp     loc_180003FDC
0x180003f0a  test    r15d, r15d
0x180003f0d  jz      short loc_180003F2C
0x180003f0f  test    rbp, rbp
0x180003f12  jz      short loc_180003F7A
0x180003f14  cmp     word ptr [rbp+0], 0
0x180003f19  jz      short loc_180003F7A
0x180003f1b  test    r14, r14
0x180003f1e  jnz     short loc_180003F7A
0x180003f20  mov     edx, 1
0x180003f25  mov     ecx, 80100000h
0x180003f2a  jmp     short loc_180003F41
0x180003f2c  test    rbp, rbp
0x180003f2f  mov     ecx, 0C0100000h
0x180003f34  mov     eax, 0C01C0000h
0x180003f39  mov     edx, 2
0x180003f3e  cmovnz  ecx, eax
0x180003f41  mov     eax, ecx
0x180003f43  or      eax, 20h
0x180003f46  test    r12d, r12d
0x180003f49  cmovz   eax, ecx
0x180003f4c  mov     r8d, eax
0x180003f4f  bts     r8d, 1Eh
0x180003f54  test    r13d, r13d
0x180003f57  cmovz   r8d, eax; int
0x180003f5b  test    sil, 10h
0x180003f5f  jz      short loc_180003F8E
0x180003f61  test    r15d, r15d
0x180003f64  jz      short loc_180003F7A
0x180003f66  cmp     dword ptr [rsp+98h+arg_30], 0
0x180003f6e  jnz     short loc_180003F7A
0x180003f70  test    r12d, r12d
0x180003f73  jnz     short loc_180003F7A
0x180003f75  test    r13d, r13d
0x180003f78  jz      short loc_180003F81
0x180003f7a  mov     eax, 57h ; 'W'
0x180003f7f  jmp     short loc_180003FDC
0x180003f81  mov     eax, 4000h
0x180003f86  mov     r8d, 0E0000h
0x180003f8c  jmp     short loc_180003F90
0x180003f8e  xor     eax, eax
0x180003f90  mov     rcx, [rsp+98h+arg_28]
0x180003f98  mov     r9d, 1; int
0x180003f9e  mov     [rsp+98h+var_48], rcx; __int64
0x180003fa3  mov     ecx, [rsp+98h+arg_20]
0x180003faa  mov     [rsp+98h+var_50], ecx; int
0x180003fae  lea     rcx, [rsp+98h+var_38]; int
0x180003fb3  mov     [rsp+98h+var_58], r14; __int64
0x180003fb8  mov     [rsp+98h+var_60], eax; ULONG
0x180003fbc  mov     [rsp+98h+var_68], edx; ULONG
0x180003fc0  mov     edx, ebx; int
0x180003fc2  mov     [rsp+98h+var_70], esi; int
0x180003fc6  mov     [rsp+98h+var_78], rbp; STRSAFE_LPCWSTR
0x180003fcb  call    HttpApiCreateHandleHelper
0x180003fd0  test    eax, eax
0x180003fd2  jnz     short loc_180003FDC
0x180003fd4  mov     rcx, qword ptr [rsp+98h+var_38]
0x180003fd9  mov     [rdi], rcx
0x180003fdc  mov     r13, [rsp+98h+arg_8]
0x180003fe4  mov     r12, [rsp+98h+arg_0]
0x180003fec  mov     r15, [rsp+98h+arg_10]
0x180003ff4  add     rsp, 70h
0x180003ff8  pop     r14
0x180003ffa  pop     rdi
0x180003ffb  pop     rsi
0x180003ffc  pop     rbp
0x180003ffd  pop     rbx
0x180003ffe  retn
```
