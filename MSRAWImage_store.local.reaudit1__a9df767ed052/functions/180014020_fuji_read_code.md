# fuji_read_code

- ea: `0x180014020`
- end: `0x1800141ca`
- name: `fuji_read_code`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180013440`
- `0x180013770`

## callees

- `0x180003e4c`
- `0x180014020`
- `0x1800b0b00`
- `0x1800b4010`

## pseudocode

```c
char __fastcall fuji_read_code(__int64 a1, _DWORD *a2, int a3)
{
  __int64 v3; // rax
  unsigned __int8 v4; // bp
  unsigned __int8 v5; // r9
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edi
  int pExceptionObject; // [rsp+60h] [rbp+18h] BYREF

  LOBYTE(v3) = *(_BYTE *)a1 & 7;
  *a2 = 0;
  v4 = a3;
  v5 = 8 - v3;
  if ( a3 )
  {
    if ( a3 >= v5 )
    {
      do
      {
        v4 -= v5;
        *a2 <<= v5;
        *a2 |= ((1 << v5) - 1) & *(unsigned __int8 *)((int)(*(_DWORD *)(a1 + 4))++ + *(_QWORD *)(a1 + 24));
        v8 = *(int *)(a1 + 20);
        if ( *(_DWORD *)(a1 + 4) >= (int)v8 )
        {
          *(_QWORD *)(a1 + 8) += v8;
          v9 = *(_QWORD *)(a1 + 40);
          *(_DWORD *)(a1 + 4) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 40) + 24LL))(
            *(_QWORD *)(a1 + 40),
            *(_QWORD *)(a1 + 8),
            0);
          v10 = 0x10000;
          if ( *(_DWORD *)(a1 + 16) < 0x10000u )
            v10 = *(unsigned int *)(a1 + 16);
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(a1 + 40) + 16LL))(
                  *(_QWORD *)(a1 + 40),
                  *(_QWORD *)(a1 + 24),
                  1,
                  v10);
          v12 = *(_QWORD *)(a1 + 40);
          *(_DWORD *)(a1 + 20) = v11;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 104LL))(v12);
          if ( *(int *)(a1 + 20) < 1 )
          {
            v13 = *(_DWORD *)(a1 + 32);
            if ( v13 <= 0 )
            {
              pExceptionObject = 4;
              throw (LibRaw_exceptions *)&pExceptionObject;
            }
            v14 = 0x10000;
            if ( v13 < 0x10000 )
              v14 = *(_DWORD *)(a1 + 32);
            memset(*(void **)(a1 + 24), 0, v14);
            *(_DWORD *)(a1 + 32) -= v14;
          }
          *(_DWORD *)(a1 + 16) -= *(_DWORD *)(a1 + 20);
        }
        v5 = 8;
      }
      while ( v4 >= 8u );
    }
    if ( v4 )
    {
      *a2 <<= v4;
      v3 = *(_QWORD *)(a1 + 24);
      *a2 |= ((1 << v4) - 1) & (*(unsigned __int8 *)(*(int *)(a1 + 4) + v3) >> (v5 - v4));
      *(_DWORD *)a1 = -(unsigned __int8)(v5 - v4) & 7;
    }
    else
    {
      LODWORD(v3) = -v5 & 7;
      *(_DWORD *)a1 = v3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180014020  mov     [rsp+arg_18], rbx
0x180014025  push    rbp
0x180014026  push    rsi
0x180014027  push    r15
0x180014029  sub     rsp, 30h
0x18001402d  movzx   eax, byte ptr [rcx]
0x180014030  xor     r15d, r15d
0x180014033  and     al, 7
0x180014035  mov     [rdx], r15d
0x180014038  mov     r9d, 8
0x18001403e  mov     ebp, r8d
0x180014041  sub     r9b, al
0x180014044  mov     rsi, rdx
0x180014047  mov     rbx, rcx
0x18001404a  test    r8d, r8d
0x18001404d  jz      loc_1800141A2
0x180014053  mov     [rsp+48h+arg_8], r14
0x180014058  mov     r14d, 1
0x18001405e  movzx   eax, r9b
0x180014062  mov     [rsp+48h+arg_0], rdi
0x180014067  cmp     r8d, eax
0x18001406a  jl      loc_180014149
0x180014070  movzx   ecx, r9b
0x180014074  sub     bpl, r9b
0x180014077  shl     dword ptr [rsi], cl
0x180014079  mov     rax, [rbx+18h]
0x18001407d  movsxd  rdx, dword ptr [rbx+4]
0x180014081  movzx   r8d, byte ptr [rdx+rax]
0x180014086  mov     eax, r14d
0x180014089  shl     eax, cl
0x18001408b  dec     eax
0x18001408d  and     r8d, eax
0x180014090  or      [rsi], r8d
0x180014093  inc     dword ptr [rbx+4]
0x180014096  movsxd  rax, dword ptr [rbx+14h]
0x18001409a  cmp     [rbx+4], eax
0x18001409d  jl      loc_18001413D
0x1800140a3  add     [rbx+8], rax
0x1800140a7  mov     rcx, [rbx+28h]
0x1800140ab  mov     [rbx+4], r15d
0x1800140af  mov     rax, [rcx]
0x1800140b2  mov     rax, [rax+60h]
0x1800140b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140bb  mov     rcx, [rbx+28h]
0x1800140bf  xor     r8d, r8d
0x1800140c2  mov     rdx, [rbx+8]
0x1800140c6  mov     rax, [rcx]
0x1800140c9  mov     rax, [rax+18h]
0x1800140cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d2  mov     rcx, [rbx+28h]
0x1800140d6  mov     r9d, 10000h
0x1800140dc  cmp     [rbx+10h], r9d
0x1800140e0  mov     r8, r14
0x1800140e3  mov     rdx, [rbx+18h]
0x1800140e7  cmovb   r9d, [rbx+10h]
0x1800140ec  mov     rax, [rcx]
0x1800140ef  mov     rax, [rax+10h]
0x1800140f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140f8  mov     rcx, [rbx+28h]
0x1800140fc  mov     [rbx+14h], eax
0x1800140ff  mov     rax, [rcx]
0x180014102  mov     rax, [rax+68h]
0x180014106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001410b  cmp     [rbx+14h], r14d
0x18001410f  jge     short loc_180014137
0x180014111  mov     eax, [rbx+20h]
0x180014114  test    eax, eax
0x180014116  jle     loc_1800141B0
0x18001411c  mov     rcx, [rbx+18h]; void *
0x180014120  mov     edi, 10000h
0x180014125  cmp     eax, edi
0x180014127  cmovl   edi, eax
0x18001412a  xor     edx, edx; Val
0x18001412c  movsxd  r8, edi; Size
0x18001412f  call    memset
0x180014134  sub     [rbx+20h], edi
0x180014137  mov     eax, [rbx+14h]
0x18001413a  sub     [rbx+10h], eax
0x18001413d  mov     r9b, 8
0x180014140  cmp     bpl, r9b
0x180014143  jnb     loc_180014070
0x180014149  test    bpl, bpl
0x18001414c  jnz     short loc_18001415B
0x18001414e  movzx   eax, r9b
0x180014152  neg     eax
0x180014154  and     eax, 7
0x180014157  mov     [rbx], eax
0x180014159  jmp     short loc_180014198
0x18001415b  sub     r9b, bpl
0x18001415e  movzx   r8d, bpl
0x180014162  movzx   r10d, r9b
0x180014166  mov     ecx, r8d
0x180014169  shl     dword ptr [rsi], cl
0x18001416b  movzx   ecx, r10b
0x18001416f  movsxd  rdx, dword ptr [rbx+4]
0x180014173  neg     r10d
0x180014176  mov     rax, [rbx+18h]
0x18001417a  movzx   r9d, byte ptr [rdx+rax]
0x18001417f  shr     r9d, cl
0x180014182  mov     ecx, r8d
0x180014185  shl     r14d, cl
0x180014188  dec     r14d
0x18001418b  and     r9d, r14d
0x18001418e  or      [rsi], r9d
0x180014191  and     r10d, 7
0x180014195  mov     [rbx], r10d
0x180014198  mov     rdi, [rsp+48h+arg_0]
0x18001419d  mov     r14, [rsp+48h+arg_8]
0x1800141a2  mov     rbx, [rsp+48h+arg_18]
0x1800141a7  add     rsp, 30h
0x1800141ab  pop     r15
0x1800141ad  pop     rsi
0x1800141ae  pop     rbp
0x1800141af  retn
0x1800141b0  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x1800141b7  mov     [rsp+48h+pExceptionObject], 4
0x1800141bf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800141c4  call    _CxxThrowException
```
