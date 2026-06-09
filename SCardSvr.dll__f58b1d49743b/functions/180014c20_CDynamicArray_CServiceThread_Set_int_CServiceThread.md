# CDynamicArray<CServiceThread>::Set(int,CServiceThread *)

- ea: `0x180014c20`
- end: `0x180014d2a`
- name: `?Set@?$CDynamicArray@VCServiceThread@@@@QEAAPEAVCServiceThread@@HPEAV2@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002fdf0`

## callees

- `0x180014c20`
- `0x180023168`
- `0x180023174`
- `0x18003261b`

## pseudocode

```c
__int64 __fastcall CDynamicArray<CServiceThread>::Set(__int64 a1, unsigned int a2, __int64 a3)
{
  int v3; // esi
  __int64 v5; // rbx
  unsigned int v6; // edx
  char *v8; // rbp
  __int64 i; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  ulong pExceptionObject; // [rsp+58h] [rbp+10h] BYREF

  v3 = qword_18004B0A8;
  v5 = a2;
  if ( a2 >= (unsigned int)qword_18004B0A8 )
  {
    if ( !(_DWORD)qword_18004B0A8 )
      v3 = 4;
    for ( ; (int)a2 >= v3; v3 *= 2 )
      ;
    v8 = (char *)operator new[](saturated_mul(v3, 8u));
    if ( !v8 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    for ( i = 0; (unsigned int)i < HIDWORD(qword_18004B0A8); *(_QWORD *)&v8[v10] = *(_QWORD *)((char *)Block + v10) )
    {
      v10 = 8 * i;
      i = (unsigned int)(i + 1);
    }
    if ( Block )
      operator delete[](Block);
    Block = v8;
    LODWORD(qword_18004B0A8) = v3;
  }
  v6 = HIDWORD(qword_18004B0A8);
  if ( (unsigned int)v5 >= HIDWORD(qword_18004B0A8) )
  {
    if ( (unsigned int)v5 > HIDWORD(qword_18004B0A8) )
    {
      do
      {
        v11 = v6++;
        *((_QWORD *)Block + v11) = 0;
      }
      while ( v6 < (unsigned int)v5 );
    }
    HIDWORD(qword_18004B0A8) = v5 + 1;
  }
  *((_QWORD *)Block + v5) = a3;
  return a3;
}

```

## disassembly

```asm
0x180014c20  push    rbx
0x180014c22  push    rbp
0x180014c23  push    rsi
0x180014c24  push    rdi
0x180014c25  sub     rsp, 28h
0x180014c29  mov     esi, dword ptr cs:qword_18004B0A8
0x180014c2f  mov     rdi, r8
0x180014c32  mov     ebx, edx
0x180014c34  cmp     edx, esi
0x180014c36  jnb     short loc_180014C5D
0x180014c38  mov     edx, dword ptr cs:qword_18004B0A8+4
0x180014c3e  cmp     ebx, edx
0x180014c40  jnb     loc_180014D03
0x180014c46  mov     rax, cs:Block
0x180014c4d  mov     [rax+rbx*8], rdi
0x180014c51  mov     rax, rdi
0x180014c54  add     rsp, 28h
0x180014c58  pop     rdi
0x180014c59  pop     rsi
0x180014c5a  pop     rbp
0x180014c5b  pop     rbx
0x180014c5c  retn
0x180014c5d  test    esi, esi
0x180014c5f  mov     eax, 4
0x180014c64  cmovz   esi, eax
0x180014c67  cmp     ebx, esi
0x180014c69  jl      short loc_180014C71
0x180014c6b  add     esi, esi
0x180014c6d  cmp     ebx, esi
0x180014c6f  jge     short loc_180014C6B
0x180014c71  movsxd  rcx, esi
0x180014c74  mov     eax, 8
0x180014c79  mul     rcx
0x180014c7c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180014c83  cmovb   rax, rcx
0x180014c87  mov     rcx, rax; unsigned __int64
0x180014c8a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014c8f  mov     rbp, rax
0x180014c92  test    rax, rax
0x180014c95  jnz     short loc_180014CB1
0x180014c97  lea     rdx, _TI1K; pThrowInfo
0x180014c9e  mov     [rsp+48h+pExceptionObject], 0Eh
0x180014ca6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180014cab  call    _CxxThrowException_0
0x180014cb1  xor     r8d, r8d
0x180014cb4  cmp     dword ptr cs:qword_18004B0A8+4, r8d
0x180014cbb  jbe     short loc_180014CE0
0x180014cbd  mov     rax, cs:Block
0x180014cc4  lea     rdx, ds:0[r8*8]
0x180014ccc  inc     r8d
0x180014ccf  mov     rcx, [rdx+rax]
0x180014cd3  mov     [rdx+rbp], rcx
0x180014cd7  cmp     r8d, dword ptr cs:qword_18004B0A8+4
0x180014cde  jb      short loc_180014CBD
0x180014ce0  mov     rcx, cs:Block; Block
0x180014ce7  test    rcx, rcx
0x180014cea  jz      short loc_180014CF1
0x180014cec  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180014cf1  mov     cs:Block, rbp
0x180014cf8  mov     dword ptr cs:qword_18004B0A8, esi
0x180014cfe  jmp     loc_180014C38
0x180014d03  jbe     short loc_180014D1C
0x180014d05  mov     rax, cs:Block
0x180014d0c  mov     ecx, edx
0x180014d0e  inc     edx
0x180014d10  mov     qword ptr [rax+rcx*8], 0
0x180014d18  cmp     edx, ebx
0x180014d1a  jb      short loc_180014D05
0x180014d1c  lea     eax, [rbx+1]
0x180014d1f  mov     dword ptr cs:qword_18004B0A8+4, eax
0x180014d25  jmp     loc_180014C46
```
