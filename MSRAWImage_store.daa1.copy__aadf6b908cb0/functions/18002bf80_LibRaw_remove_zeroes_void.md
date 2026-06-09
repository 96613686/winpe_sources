# LibRaw::remove_zeroes(void)

- ea: `0x18002bf80`
- end: `0x18002c1f5`
- name: `?remove_zeroes@LibRaw@@IEAAXXZ`
- size: `629`
- prototype: `void __fastcall(LibRaw *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008330`

## callees

- `0x180003e4c`
- `0x18002bf80`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::remove_zeroes(LibRaw *this)
{
  unsigned int (__fastcall *v1)(_QWORD, __int64, _QWORD, __int64); // rax
  _QWORD *v2; // rdi
  int v4; // r13d
  int v5; // esi
  unsigned __int8 v6; // al
  unsigned int v7; // edx
  unsigned int v8; // r14d
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rcx
  bool v12; // zf
  unsigned int v13; // r11d
  unsigned int v14; // edi
  int v15; // r9d
  int v16; // edx
  char v17; // bp
  int v18; // r8d
  unsigned int (__fastcall *v19)(_QWORD, __int64, __int64, __int64); // rax
  int pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  _WORD *v21; // [rsp+78h] [rbp+10h]

  v1 = (unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, __int64))*((_QWORD *)this + 95882);
  v2 = (_QWORD *)((char *)this + 767064);
  if ( v1 && v1(*v2, 32, 0, 2) )
  {
    pExceptionObject = 6;
    throw (LibRaw_exceptions *)&pExceptionObject;
  }
  if ( *((_WORD *)this + 10) )
  {
    v4 = 2;
    do
    {
      if ( *((_WORD *)this + 11) )
      {
        v5 = 2;
        v6 = (2 * v4 - 3) & 0xE;
        v7 = v4 - 2;
        pExceptionObject = v6;
        do
        {
          v8 = *((_DWORD *)this + 136);
          v9 = (v8 >> (2 * (v6 | v5 & 1))) & 3;
          v10 = *((_QWORD *)this + 1);
          v11 = v9
              + 4LL
              * (((unsigned int)(v5 - 2) >> *((_WORD *)this + 190674))
               + *((unsigned __int16 *)this + 15) * (v7 >> *((_WORD *)this + 190674)));
          v12 = *(_WORD *)(v10 + 2 * v11) == 0;
          v21 = (_WORD *)(v10 + 2 * v11);
          if ( v12 )
          {
            v13 = 0;
            v14 = 0;
            v15 = v4 - 4;
            if ( v4 - 4 < v4 )
            {
              do
              {
                v16 = v5 - 4;
                if ( v5 - 4 <= v5 )
                {
                  v17 = 2 * (v15 & 7);
                  do
                  {
                    if ( v15 >= 0
                      && v15 < *((unsigned __int16 *)this + 10)
                      && v16 >= 0
                      && v16 < *((unsigned __int16 *)this + 11)
                      && ((v8 >> (2 * (v17 | v16 & 1))) & 3) == (_DWORD)v9 )
                    {
                      v18 = *(unsigned __int16 *)(*((_QWORD *)this + 1)
                                                + 2
                                                * ((((unsigned __int64)*((unsigned int *)this + 136) >> (2 * (v17 | (unsigned __int8)(v16 & 1))))
                                                  & 3)
                                                 + 4LL
                                                 * ((v16 >> *((_WORD *)this + 190674))
                                                  + *((unsigned __int16 *)this + 15)
                                                  * (v15 >> *((_WORD *)this + 190674)))));
                      if ( (_WORD)v18 )
                      {
                        ++v13;
                        v14 += v18;
                      }
                    }
                    ++v16;
                  }
                  while ( v16 <= v5 );
                }
                ++v15;
              }
              while ( v15 <= v4 );
              if ( v13 )
                *v21 = v14 / v13;
            }
          }
          v7 = v4 - 2;
          ++v5;
          v6 = pExceptionObject;
        }
        while ( v5 - 2 < (unsigned int)*((unsigned __int16 *)this + 11) );
      }
      ++v4;
    }
    while ( v4 - 2 < (unsigned int)*((unsigned __int16 *)this + 10) );
    v2 = (_QWORD *)((char *)this + 767064);
  }
  v19 = (unsigned int (__fastcall *)(_QWORD, __int64, __int64, __int64))*((_QWORD *)this + 95882);
  if ( v19 )
  {
    if ( v19(*v2, 32, 1, 2) )
    {
      pExceptionObject = 6;
      throw (LibRaw_exceptions *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x18002bf80  push    rbx
0x18002bf82  push    rdi
0x18002bf83  sub     rsp, 58h
0x18002bf87  mov     rax, [rcx+0BB450h]
0x18002bf8e  lea     rdi, [rcx+0BB458h]
0x18002bf95  mov     rbx, rcx
0x18002bf98  test    rax, rax
0x18002bf9b  jz      short loc_18002BFBB
0x18002bf9d  mov     rcx, [rdi]
0x18002bfa0  mov     r9d, 2
0x18002bfa6  xor     r8d, r8d
0x18002bfa9  mov     edx, 20h ; ' '
0x18002bfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfb3  test    eax, eax
0x18002bfb5  jnz     loc_18002C1C1
0x18002bfbb  xor     r9d, r9d
0x18002bfbe  cmp     r9w, [rbx+14h]
0x18002bfc3  jnb     loc_18002C191
0x18002bfc9  mov     [rsp+68h+arg_10], rbp
0x18002bfd1  mov     [rsp+68h+var_18], rsi
0x18002bfd6  mov     [rsp+68h+var_20], r12
0x18002bfdb  mov     [rsp+68h+var_28], r13
0x18002bfe0  mov     r13d, 2
0x18002bfe6  mov     [rsp+68h+var_30], r14
0x18002bfeb  mov     [rsp+68h+var_38], r15
0x18002bff0  cmp     r9w, [rbx+16h]
0x18002bff5  jnb     loc_18002C156
0x18002bffb  lea     eax, ds:0FFFFFFFFFFFFFFFDh[r13*2]
0x18002c003  mov     esi, 2
0x18002c008  and     eax, 0Eh
0x18002c00b  lea     edx, [r13-2]
0x18002c00f  mov     [rsp+68h+pExceptionObject], eax
0x18002c013  mov     r14d, [rbx+220h]
0x18002c01a  mov     ecx, esi
0x18002c01c  movzx   r8d, word ptr [rbx+5D1A4h]
0x18002c024  and     ecx, 1
0x18002c027  or      ecx, eax
0x18002c029  mov     r15d, r14d
0x18002c02c  movzx   eax, word ptr [rbx+1Eh]
0x18002c030  add     ecx, ecx
0x18002c032  shr     r15d, cl
0x18002c035  mov     ecx, r8d
0x18002c038  shr     edx, cl
0x18002c03a  and     r15d, 3
0x18002c03e  imul    edx, eax
0x18002c041  lea     eax, [rsi-2]
0x18002c044  shr     eax, cl
0x18002c046  add     edx, eax
0x18002c048  mov     rax, [rbx+8]
0x18002c04c  lea     rcx, [r15+rdx*4]
0x18002c050  cmp     word ptr [rax+rcx*2], 0
0x18002c055  lea     rax, [rax+rcx*2]
0x18002c059  mov     [rsp+68h+arg_8], rax
0x18002c05e  jnz     loc_18002C13D
0x18002c064  mov     r11d, r9d
0x18002c067  mov     edi, r9d
0x18002c06a  lea     r9d, [r13-4]
0x18002c06e  cmp     r9d, r13d
0x18002c071  jg      loc_18002C13A
0x18002c077  lea     r12d, [rsi-4]
0x18002c07b  nop     dword ptr [rax+rax+00h]
0x18002c080  mov     edx, r12d
0x18002c083  cmp     r12d, esi
0x18002c086  jg      loc_18002C11A
0x18002c08c  mov     eax, r9d
0x18002c08f  and     eax, 7
0x18002c092  lea     ebp, [rax+rax]
0x18002c095  test    r9d, r9d
0x18002c098  js      short loc_18002C110
0x18002c09a  movzx   eax, word ptr [rbx+14h]
0x18002c09e  cmp     r9d, eax
0x18002c0a1  jge     short loc_18002C110
0x18002c0a3  test    edx, edx
0x18002c0a5  js      short loc_18002C110
0x18002c0a7  movzx   eax, word ptr [rbx+16h]
0x18002c0ab  cmp     edx, eax
0x18002c0ad  jge     short loc_18002C110
0x18002c0af  mov     ecx, edx
0x18002c0b1  mov     eax, r14d
0x18002c0b4  and     ecx, 1
0x18002c0b7  or      ecx, ebp
0x18002c0b9  add     ecx, ecx
0x18002c0bb  shr     eax, cl
0x18002c0bd  mov     r10d, ecx
0x18002c0c0  and     eax, 3
0x18002c0c3  cmp     eax, r15d
0x18002c0c6  jnz     short loc_18002C110
0x18002c0c8  movzx   ecx, word ptr [rbx+5D1A4h]
0x18002c0cf  mov     r8d, r9d
0x18002c0d2  movzx   eax, word ptr [rbx+1Eh]
0x18002c0d6  sar     r8d, cl
0x18002c0d9  imul    r8d, eax
0x18002c0dd  mov     eax, edx
0x18002c0df  sar     eax, cl
0x18002c0e1  movzx   ecx, r10b
0x18002c0e5  add     r8d, eax
0x18002c0e8  mov     eax, [rbx+220h]
0x18002c0ee  shr     rax, cl
0x18002c0f1  and     eax, 3
0x18002c0f4  movsxd  r8, r8d
0x18002c0f7  lea     rcx, [rax+r8*4]
0x18002c0fb  mov     rax, [rbx+8]
0x18002c0ff  movzx   r8d, word ptr [rax+rcx*2]
0x18002c104  test    r8w, r8w
0x18002c108  jz      short loc_18002C110
0x18002c10a  inc     r11d
0x18002c10d  add     edi, r8d
0x18002c110  inc     edx
0x18002c112  cmp     edx, esi
0x18002c114  jle     loc_18002C095
0x18002c11a  inc     r9d
0x18002c11d  cmp     r9d, r13d
0x18002c120  jle     loc_18002C080
0x18002c126  test    r11d, r11d
0x18002c129  jz      short loc_18002C13A
0x18002c12b  mov     rcx, [rsp+68h+arg_8]
0x18002c130  xor     edx, edx
0x18002c132  mov     eax, edi
0x18002c134  div     r11d
0x18002c137  mov     [rcx], ax
0x18002c13a  xor     r9d, r9d
0x18002c13d  movzx   eax, word ptr [rbx+16h]
0x18002c141  lea     edx, [r13-2]
0x18002c145  inc     esi
0x18002c147  lea     ecx, [rsi-2]
0x18002c14a  cmp     ecx, eax
0x18002c14c  mov     eax, [rsp+68h+pExceptionObject]
0x18002c150  jb      loc_18002C013
0x18002c156  movzx   eax, word ptr [rbx+14h]
0x18002c15a  inc     r13d
0x18002c15d  lea     ecx, [r13-2]
0x18002c161  cmp     ecx, eax
0x18002c163  jb      loc_18002BFF0
0x18002c169  mov     r15, [rsp+68h+var_38]
0x18002c16e  lea     rdi, [rbx+0BB458h]
0x18002c175  mov     r14, [rsp+68h+var_30]
0x18002c17a  mov     r13, [rsp+68h+var_28]
0x18002c17f  mov     r12, [rsp+68h+var_20]
0x18002c184  mov     rsi, [rsp+68h+var_18]
0x18002c189  mov     rbp, [rsp+68h+arg_10]
0x18002c191  mov     rax, [rbx+0BB450h]
0x18002c198  test    rax, rax
0x18002c19b  jz      short loc_18002C1BA
0x18002c19d  mov     rcx, [rdi]
0x18002c1a0  mov     edx, 20h ; ' '
0x18002c1a5  mov     r9d, 2
0x18002c1ab  mov     r8d, 1
0x18002c1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1b6  test    eax, eax
0x18002c1b8  jnz     short loc_18002C1DB
0x18002c1ba  add     rsp, 58h
0x18002c1be  pop     rdi
0x18002c1bf  pop     rbx
0x18002c1c0  retn
0x18002c1c1  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x18002c1c8  mov     [rsp+68h+pExceptionObject], 6
0x18002c1d0  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002c1d5  call    _CxxThrowException
0x18002c1db  lea     rdx, _TI1?AW4LibRaw_exceptions@@; pThrowInfo
0x18002c1e2  mov     [rsp+68h+pExceptionObject], 6
0x18002c1ea  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18002c1ef  call    _CxxThrowException
```
