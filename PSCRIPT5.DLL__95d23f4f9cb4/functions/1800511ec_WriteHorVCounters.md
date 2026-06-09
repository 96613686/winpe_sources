# WriteHorVCounters

- ea: `0x1800511ec`
- end: `0x180051523`
- name: `WriteHorVCounters`
- size: `823`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800506a4`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004e048`
- `0x18004f41c`
- `0x18004f464`
- `0x18004f538`
- `0x1800511ec`
- `0x18005152c`
- `0x18005d010`

## pseudocode

```c
__int64 __fastcall WriteHorVCounters(__int64 a1, __int16 a2, int a3, unsigned int a4)
{
  int v4; // esi
  __int16 v5; // r12
  unsigned int v7; // r14d
  _QWORD *v8; // rdi
  __int64 v9; // rdx
  int v10; // ecx
  unsigned int v11; // esi
  __int64 v12; // r15
  unsigned int v13; // r13d
  __int64 v14; // r14
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // r11
  __int64 v18; // r11
  int v19; // edi
  int v20; // r13d
  __int64 v21; // r15
  __int64 v22; // r12
  __int64 v23; // r14
  bool v24; // zf
  int v27; // [rsp+24h] [rbp-DCh]
  __int64 v29; // [rsp+30h] [rbp-D0h]
  _QWORD v31[10]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v32[10]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v33[20]; // [rsp+E0h] [rbp-20h] BYREF

  v4 = a3;
  v5 = a2;
  v7 = a4;
  memset_0(v31, 0, 0x44u);
  memset_0(v33, 0, 0x44u);
  memset_0(v32, 0, 0x44u);
  v8 = (_QWORD *)(a1 + 26080);
  if ( !*(_QWORD *)(a1 + 26080) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD))(a1 + 304))(
            a1 + 26080,
            18432,
            *(_QWORD *)(a1 + 312)) )
      XCF_FatalErrorHandler(a1, 7);
    (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 352))(*v8, 0, 18432);
  }
  v9 = *v8;
  v10 = v4;
  v29 = *v8;
  v27 = v4;
  if ( v4 )
  {
    v11 = v7;
    do
    {
      v12 = 0;
      v31[0] = 0;
      if ( *(_WORD *)(a1 + 25816) )
      {
        v13 = v10 - 1;
        v14 = 0;
        do
        {
          if ( *(_WORD *)(a1 + 24 * v14 + 22760) == v5 )
          {
            v15 = *(_DWORD *)(a1 + 24 * v14 + 22764);
            if ( _bittest(&v15, v13) )
            {
              v16 = v29 + 144 * v12;
              PSVCopy(a1, v16, *(_QWORD *)(a1 + 24 * v14 + 22744));
              PSVCopy(a1, v16 + 68, *(_QWORD *)(a1 + 8 * v17 + 22752));
              *(_WORD *)(v16 + 136) = *(_WORD *)(a1 + 8 * v18 + 22760);
              *(_DWORD *)(v16 + 140) = *(_DWORD *)(a1 + 8 * v18 + 22764);
              if ( *(_DWORD *)(a1 + 488) )
              {
                PStackValueAdd(a1, v33, v29 + 144 * v12, v16 + 68);
              }
              else
              {
                v33[1] = *(_DWORD *)(v16 + 4) + *(_DWORD *)(v16 + 72);
                v33[0] = 0;
              }
              PSVCopy(a1, v32, v29 + 144 * v12);
              PSVSubtract(a1, v29 + 144 * v12, v32, v31);
              PSVCopy(a1, v31, v33);
              v5 = a2;
              v12 = (unsigned int)(v12 + 1);
            }
          }
          v14 = (unsigned int)(v14 + 1);
        }
        while ( (unsigned int)v14 < *(unsigned __int16 *)(a1 + 25816) );
        v11 = a4;
        v10 = v27;
        v9 = v29;
      }
      v19 = v12 - 1;
      v20 = 1;
      if ( (int)v12 - 1 >= 0 )
      {
        v21 = v19;
        do
        {
          v22 = 144 * v21 + v9 + 68;
          v23 = 144 * v21 + v9;
          if ( v20 )
          {
            v32[0] = 0;
            PSVSubtract(a1, v31, v32, 144 * v21 + v9 + 68);
            WriteReversedCounterArg(a1, v31, v11);
            if ( *(_DWORD *)(a1 + 488) )
            {
              PStackValueAdd(a1, v31, v23, v22);
            }
            else
            {
              HIDWORD(v31[0]) = *(_DWORD *)(v23 + 4) + *(_DWORD *)(v23 + 72);
              LODWORD(v31[0]) = 0;
            }
            WriteReversedCounterArg(a1, v31, v11);
            v20 = 0;
          }
          else
          {
            WriteReversedCounterArg(a1, 144 * v21 + v9 + 68, v11);
            WriteReversedCounterArg(a1, v23, v11);
          }
          v9 = v29;
          --v21;
          --v19;
        }
        while ( v19 >= 0 );
        v10 = v27;
      }
      v9 = v29;
      v24 = v10-- == 1;
      v5 = a2;
      v27 = v10;
    }
    while ( !v24 );
    v4 = a3;
    v7 = a4;
  }
  HIDWORD(v31[0]) = v4 << 16;
  LODWORD(v31[0]) = 0;
  return WriteReversedCounterArg(a1, v31, v7);
}

```

## disassembly

```asm
0x1800511ec  push    rbp
0x1800511ee  push    rbx
0x1800511ef  push    rsi
0x1800511f0  push    rdi
0x1800511f1  push    r12
0x1800511f3  push    r13
0x1800511f5  push    r14
0x1800511f7  push    r15
0x1800511f9  lea     rbp, [rsp-48h]
0x1800511fe  sub     rsp, 148h
0x180051205  mov     rax, cs:__security_cookie
0x18005120c  xor     rax, rsp
0x18005120f  mov     [rbp+80h+var_50], rax
0x180051213  mov     esi, r8d
0x180051216  mov     [rsp+180h+var_148], r8d
0x18005121b  movzx   r12d, dx
0x18005121f  mov     [rsp+180h+var_160], dx
0x180051224  mov     rbx, rcx
0x180051227  mov     [rsp+180h+var_158], r9d
0x18005122c  mov     edi, 44h ; 'D'
0x180051231  lea     rcx, [rsp+180h+var_140]; void *
0x180051236  mov     r8d, edi; Size
0x180051239  xor     edx, edx; Val
0x18005123b  mov     r14d, r9d
0x18005123e  call    memset_0
0x180051243  mov     r8d, edi; Size
0x180051246  lea     rcx, [rbp+80h+var_A0]; void *
0x18005124a  xor     edx, edx; Val
0x18005124c  call    memset_0
0x180051251  mov     r8d, edi; Size
0x180051254  lea     rcx, [rbp+80h+var_F0]; void *
0x180051258  xor     edx, edx; Val
0x18005125a  call    memset_0
0x18005125f  lea     rdi, [rbx+65E0h]
0x180051266  cmp     qword ptr [rdi], 0
0x18005126a  jnz     short loc_1800512A7
0x18005126c  mov     r8, [rbx+138h]
0x180051273  mov     r15d, 4800h
0x180051279  mov     rax, [rbx+130h]
0x180051280  mov     edx, r15d
0x180051283  mov     rcx, rdi
0x180051286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005128b  test    eax, eax
0x18005128d  jz      loc_180051515
0x180051293  mov     rcx, [rdi]
0x180051296  mov     r8d, r15d
0x180051299  mov     rax, [rbx+160h]
0x1800512a0  xor     edx, edx
0x1800512a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800512a7  mov     rdx, [rdi]
0x1800512aa  mov     ecx, esi
0x1800512ac  mov     [rsp+180h+var_150], rdx
0x1800512b1  mov     [rsp+180h+var_15C], ecx
0x1800512b5  test    esi, esi
0x1800512b7  jz      loc_1800514D6
0x1800512bd  mov     esi, r14d
0x1800512c0  xor     r15d, r15d
0x1800512c3  mov     [rsp+180h+var_140], 0
0x1800512cc  xor     eax, eax
0x1800512ce  cmp     ax, [rbx+64D8h]
0x1800512d5  jnb     loc_1800513E7
0x1800512db  mov     rsi, [rsp+180h+var_150]
0x1800512e0  lea     r13d, [rcx-1]
0x1800512e4  xor     r14d, r14d
0x1800512e7  lea     r11, [r14+r14*2]
0x1800512eb  cmp     [rbx+r11*8+58E8h], r12w
0x1800512f4  jnz     loc_1800513C7
0x1800512fa  mov     eax, [rbx+r11*8+58ECh]
0x180051302  bt      eax, r13d
0x180051306  jnb     loc_1800513C7
0x18005130c  mov     r8, [rbx+r11*8+58D8h]
0x180051314  lea     rdi, [r15+r15*8]
0x180051318  shl     rdi, 4
0x18005131c  mov     rcx, rbx
0x18005131f  add     rdi, rsi
0x180051322  mov     rdx, rdi
0x180051325  call    PSVCopy
0x18005132a  mov     r8, [rbx+r11*8+58E0h]
0x180051332  lea     rdx, [rdi+44h]
0x180051336  mov     rcx, rbx
0x180051339  call    PSVCopy
0x18005133e  movzx   edx, word ptr [rbx+r11*8+58E8h]
0x180051347  mov     [rdi+88h], dx
0x18005134e  mov     eax, [rbx+r11*8+58ECh]
0x180051356  mov     [rdi+8Ch], eax
0x18005135c  cmp     dword ptr [rbx+1E8h], 0
0x180051363  jnz     short loc_180051377
0x180051365  mov     eax, [rdi+48h]
0x180051368  add     eax, [rdi+4]
0x18005136b  mov     [rbp+80h+var_9C], eax
0x18005136e  mov     [rbp+80h+var_A0], 0
0x180051375  jmp     short loc_18005138A
0x180051377  lea     r9, [rdi+44h]
0x18005137b  mov     r8, rdi
0x18005137e  lea     rdx, [rbp+80h+var_A0]
0x180051382  mov     rcx, rbx
0x180051385  call    PStackValueAdd
0x18005138a  mov     r8, rdi
0x18005138d  lea     rdx, [rbp+80h+var_F0]
0x180051391  mov     rcx, rbx
0x180051394  call    PSVCopy
0x180051399  lea     r9, [rsp+180h+var_140]
0x18005139e  mov     rcx, rbx
0x1800513a1  lea     r8, [rbp+80h+var_F0]
0x1800513a5  mov     rdx, rdi
0x1800513a8  call    PSVSubtract
0x1800513ad  lea     r8, [rbp+80h+var_A0]
0x1800513b1  mov     rcx, rbx
0x1800513b4  lea     rdx, [rsp+180h+var_140]
0x1800513b9  call    PSVCopy
0x1800513be  movzx   r12d, [rsp+180h+var_160]
0x1800513c4  inc     r15d
0x1800513c7  movzx   eax, word ptr [rbx+64D8h]
0x1800513ce  inc     r14d
0x1800513d1  cmp     r14d, eax
0x1800513d4  jb      loc_1800512E7
0x1800513da  mov     esi, [rsp+180h+var_158]
0x1800513de  mov     ecx, [rsp+180h+var_15C]
0x1800513e2  mov     rdx, [rsp+180h+var_150]
0x1800513e7  lea     edi, [r15-1]
0x1800513eb  mov     r13d, 1
0x1800513f1  test    edi, edi
0x1800513f3  js      loc_1800514B5
0x1800513f9  movsxd  r15, edi
0x1800513fc  lea     rax, [r15+r15*8]
0x180051400  mov     rcx, rbx
0x180051403  shl     rax, 4
0x180051407  lea     r12, [rdx+44h]
0x18005140b  add     r12, rax
0x18005140e  lea     r14, [rax+rdx]
0x180051412  test    r13d, r13d
0x180051415  jz      short loc_180051487
0x180051417  mov     r9, r12
0x18005141a  mov     [rbp+80h+var_F0], 0
0x180051422  lea     r8, [rbp+80h+var_F0]
0x180051426  lea     rdx, [rsp+180h+var_140]
0x18005142b  call    PSVSubtract
0x180051430  mov     r8d, esi
0x180051433  lea     rdx, [rsp+180h+var_140]
0x180051438  mov     rcx, rbx
0x18005143b  call    WriteReversedCounterArg
0x180051440  cmp     dword ptr [rbx+1E8h], 0
0x180051447  jnz     short loc_18005145F
0x180051449  mov     eax, [r14+48h]
0x18005144d  add     eax, [r14+4]
0x180051451  mov     dword ptr [rsp+180h+var_140+4], eax
0x180051455  mov     dword ptr [rsp+180h+var_140], 0
0x18005145d  jmp     short loc_180051472
0x18005145f  mov     r9, r12
0x180051462  lea     rdx, [rsp+180h+var_140]
0x180051467  mov     r8, r14
0x18005146a  mov     rcx, rbx
0x18005146d  call    PStackValueAdd
0x180051472  mov     r8d, esi
0x180051475  lea     rdx, [rsp+180h+var_140]
0x18005147a  mov     rcx, rbx
0x18005147d  call    WriteReversedCounterArg
0x180051482  xor     r13d, r13d
0x180051485  jmp     short loc_1800514A0
0x180051487  mov     r8d, esi
0x18005148a  mov     rdx, r12
0x18005148d  call    WriteReversedCounterArg
0x180051492  mov     r8d, esi
0x180051495  mov     rdx, r14
0x180051498  mov     rcx, rbx
0x18005149b  call    WriteReversedCounterArg
0x1800514a0  mov     rdx, [rsp+180h+var_150]
0x1800514a5  dec     r15
0x1800514a8  sub     edi, 1
0x1800514ab  jns     loc_1800513FC
0x1800514b1  mov     ecx, [rsp+180h+var_15C]
0x1800514b5  mov     rdx, [rsp+180h+var_150]
0x1800514ba  add     ecx, 0FFFFFFFFh
0x1800514bd  movzx   r12d, [rsp+180h+var_160]
0x1800514c3  mov     [rsp+180h+var_15C], ecx
0x1800514c7  jnz     loc_1800512C0
0x1800514cd  mov     esi, [rsp+180h+var_148]
0x1800514d1  mov     r14d, [rsp+180h+var_158]
0x1800514d6  shl     esi, 10h
0x1800514d9  lea     rdx, [rsp+180h+var_140]
0x1800514de  mov     r8d, r14d
0x1800514e1  mov     dword ptr [rsp+180h+var_140+4], esi
0x1800514e5  mov     rcx, rbx
0x1800514e8  mov     dword ptr [rsp+180h+var_140], 0
0x1800514f0  call    WriteReversedCounterArg
0x1800514f5  mov     rcx, [rbp+80h+var_50]
0x1800514f9  xor     rcx, rsp; StackCookie
0x1800514fc  call    __security_check_cookie
0x180051501  add     rsp, 148h
0x180051508  pop     r15
0x18005150a  pop     r14
0x18005150c  pop     r13
0x18005150e  pop     r12
0x180051510  pop     rdi
0x180051511  pop     rsi
0x180051512  pop     rbx
0x180051513  pop     rbp
0x180051514  retn
0x180051515  mov     edx, 7
0x18005151a  mov     rcx, rbx
0x18005151d  call    XCF_FatalErrorHandler
```
