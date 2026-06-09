# CDynamicArray<CReader>::Set(int,CReader *)

- ea: `0x180019a40`
- end: `0x180019b38`
- name: `?Set@?$CDynamicArray@VCReader@@@@QEAAPEAVCReader@@HPEAV2@@Z`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002680`
- `0x180029f78`

## callees

- `0x180019a40`
- `0x180023168`
- `0x180023174`
- `0x18003261b`

## pseudocode

```c
__int64 __fastcall CDynamicArray<CReader>::Set(__int64 a1, unsigned int a2, __int64 a3)
{
  int v3; // ebx
  __int64 v5; // rdi
  _QWORD *v6; // r14
  __int64 i; // r8
  unsigned int v8; // edx
  __int64 v9; // rcx
  ulong pExceptionObject; // [rsp+58h] [rbp+10h] BYREF

  v3 = qword_18004B0C8;
  v5 = a2;
  if ( a2 >= (unsigned int)qword_18004B0C8 )
  {
    if ( !(_DWORD)qword_18004B0C8 )
      v3 = 4;
    while ( (int)a2 >= v3 )
      v3 *= 2;
    v6 = operator new[](saturated_mul(v3, 8u));
    if ( !v6 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    for ( i = 0; (unsigned int)i < HIDWORD(qword_18004B0C8); i = (unsigned int)(i + 1) )
      v6[i] = *((_QWORD *)qword_18004B0D0 + i);
    if ( qword_18004B0D0 )
      operator delete[](qword_18004B0D0);
    qword_18004B0D0 = v6;
    LODWORD(qword_18004B0C8) = v3;
  }
  v8 = HIDWORD(qword_18004B0C8);
  if ( (unsigned int)v5 >= HIDWORD(qword_18004B0C8) )
  {
    if ( (unsigned int)v5 > HIDWORD(qword_18004B0C8) )
    {
      do
      {
        v9 = v8++;
        *((_QWORD *)qword_18004B0D0 + v9) = 0;
      }
      while ( v8 < (unsigned int)v5 );
    }
    HIDWORD(qword_18004B0C8) = v5 + 1;
  }
  *((_QWORD *)qword_18004B0D0 + v5) = a3;
  return a3;
}

```

## disassembly

```asm
0x180019a40  push    rbx
0x180019a42  push    rsi
0x180019a43  push    rdi
0x180019a44  push    r14
0x180019a46  sub     rsp, 28h
0x180019a4a  mov     ebx, dword ptr cs:qword_18004B0C8
0x180019a50  mov     rsi, r8
0x180019a53  mov     edi, edx
0x180019a55  cmp     edx, ebx
0x180019a57  jb      loc_180019AF4
0x180019a5d  test    ebx, ebx
0x180019a5f  mov     eax, 4
0x180019a64  cmovz   ebx, eax
0x180019a67  jmp     short loc_180019A6B
0x180019a69  add     ebx, ebx
0x180019a6b  cmp     edi, ebx
0x180019a6d  jge     short loc_180019A69
0x180019a6f  movsxd  rcx, ebx
0x180019a72  mov     eax, 8
0x180019a77  mul     rcx
0x180019a7a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180019a81  cmovb   rax, rcx
0x180019a85  mov     rcx, rax; unsigned __int64
0x180019a88  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019a8d  mov     r14, rax
0x180019a90  test    rax, rax
0x180019a93  jnz     short loc_180019AAF
0x180019a95  lea     rdx, _TI1K; pThrowInfo
0x180019a9c  mov     [rsp+48h+pExceptionObject], 0Eh
0x180019aa4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180019aa9  call    _CxxThrowException_0
0x180019aaf  xor     r8d, r8d
0x180019ab2  cmp     dword ptr cs:qword_18004B0C8+4, r8d
0x180019ab9  jbe     short loc_180019AD6
0x180019abb  mov     rax, cs:qword_18004B0D0
0x180019ac2  mov     rcx, [rax+r8*8]
0x180019ac6  mov     [r14+r8*8], rcx
0x180019aca  inc     r8d
0x180019acd  cmp     r8d, dword ptr cs:qword_18004B0C8+4
0x180019ad4  jb      short loc_180019ABB
0x180019ad6  mov     rcx, cs:qword_18004B0D0; Block
0x180019add  test    rcx, rcx
0x180019ae0  jz      short loc_180019AE7
0x180019ae2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180019ae7  mov     cs:qword_18004B0D0, r14
0x180019aee  mov     dword ptr cs:qword_18004B0C8, ebx
0x180019af4  mov     edx, dword ptr cs:qword_18004B0C8+4
0x180019afa  cmp     edi, edx
0x180019afc  jb      short loc_180019B20
0x180019afe  jbe     short loc_180019B17
0x180019b00  mov     rax, cs:qword_18004B0D0
0x180019b07  mov     ecx, edx
0x180019b09  inc     edx
0x180019b0b  mov     qword ptr [rax+rcx*8], 0
0x180019b13  cmp     edx, edi
0x180019b15  jb      short loc_180019B00
0x180019b17  lea     eax, [rdi+1]
0x180019b1a  mov     dword ptr cs:qword_18004B0C8+4, eax
0x180019b20  mov     rax, cs:qword_18004B0D0
0x180019b27  mov     [rax+rdi*8], rsi
0x180019b2b  mov     rax, rsi
0x180019b2e  add     rsp, 28h
0x180019b32  pop     r14
0x180019b34  pop     rdi
0x180019b35  pop     rsi
0x180019b36  pop     rbx
0x180019b37  retn
```
