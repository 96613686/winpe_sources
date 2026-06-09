# XLOutput::Path(_PATHOBJ *,_DEVOBJ *)

- ea: `0x180014040`
- end: `0x1800144b1`
- name: `?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z`
- size: `1137`
- prototype: `__int64 __fastcall(XLOutput *__hidden this, PATHOBJ *ppo, struct _DEVOBJ *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ee10`
- `0x180012850`
- `0x180012ac0`
- `0x180012f00`
- `0x180043980`

## callees

- `0x180011ed0`
- `0x180012160`
- `0x180014040`
- `0x1800144c0`
- `0x180014b40`
- `0x180032c74`
- `0x1800461b4`

## import_xrefs

- `GDI32!PATHOBJ_bEnum` at `0x1800140c9`
- `GDI32!PATHOBJ_bEnum` at `0x1800140c9`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800140b0`
- `GDI32!PATHOBJ_vEnumStart` at `0x1800140b0`

## pseudocode

```c
__int64 __fastcall XLOutput::Path(XLOutput *this, PATHOBJ *ppo, struct _DEVOBJ *a3)
{
  PATHOBJ *v3; // r15
  __int64 v5; // rcx
  unsigned int v6; // esi
  BOOL v7; // eax
  signed int count; // edi
  BOOL v9; // ebp
  POINTFIX *pptfx; // r14
  unsigned int v11; // eax
  FIX v13; // r13d
  FIX v14; // esi
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  FIX v22; // r15d
  FIX v23; // r12d
  int v24; // esi
  __int16 v25; // dx
  __int16 v26; // r8
  FIX v27; // [rsp+20h] [rbp-58h]
  PATHDATA ppd; // [rsp+28h] [rbp-50h] BYREF
  int v31; // [rsp+98h] [rbp+20h]

  v3 = ppo;
  ppd = 0;
  if ( !ppo )
    return 2147549183LL;
  v5 = *((unsigned int *)this + 7);
  if ( (int)v5 + 1 >= (unsigned int)v5
    && (*((unsigned int *)this + 6) >= (unsigned __int64)(v5 + 8) || !(unsigned int)XLWrite::IncreaseBuffer(this, 8))
    && *((_QWORD *)this + 1) )
  {
    *(_BYTE *)(*((_QWORD *)this + 2))++ = -123;
    ++*((_DWORD *)this + 7);
  }
  v6 = 0;
  PATHOBJ_vEnumStart(v3);
  do
  {
    v7 = PATHOBJ_bEnum(v3, &ppd);
    count = ppd.count;
    v9 = v7;
    if ( ppd.count )
    {
      pptfx = ppd.pptfx;
      if ( (ppd.flags & 1) != 0 )
      {
        if ( !v6 )
        {
          v13 = ppd.pptfx->x >> 4;
          v14 = ppd.pptfx->y >> 4;
          v27 = v14;
          if ( (unsigned int)(v13 + 0x8000) > 0xFFFF || (unsigned int)(v14 + 0x8000) > 0xFFFF )
          {
            v22 = ppd.pptfx->y >> 4;
            v23 = ppd.pptfx->x >> 4;
            v24 = 1;
            while ( v23 || v22 )
            {
              v31 = v24;
              if ( v23 <= 0x7FFF )
              {
                if ( v23 >= -32768 )
                {
                  v25 = v23;
                  v23 = 0;
                }
                else
                {
                  v25 = 0x8000;
                  v23 += 0x8000;
                }
              }
              else
              {
                v25 = 0x7FFF;
                v23 -= 0x7FFF;
              }
              if ( v22 <= 0x7FFF )
              {
                if ( v22 >= -32768 )
                {
                  v26 = v22;
                  v22 = 0;
                }
                else
                {
                  v26 = 0x8000;
                  v22 += 0x8000;
                }
              }
              else
              {
                v26 = 0x7FFF;
                v22 -= 0x7FFF;
              }
              XLOutput::Send_sint16_xy(this, v25, v26);
              XLOutput::Send_attr_ubyte((__int64)this, 76);
              v24 = 0;
              XLWrite::WriteByte(this, (v31 == 0) + 107);
            }
            v3 = ppo;
            v14 = v27;
          }
          else
          {
            v15 = *((unsigned int *)this + 7);
            if ( (int)v15 + 1 >= (unsigned int)v15
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v15 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = -45;
              ++*((_DWORD *)this + 7);
            }
            v16 = *((_DWORD *)this + 7);
            if ( v16 + 2 >= v16
              && (*((_DWORD *)this + 6) >= v16 + 2 || !(unsigned int)XLWrite::IncreaseBuffer(this, 2))
              && *((_QWORD *)this + 1) )
            {
              **((_WORD **)this + 2) = v13;
              *((_QWORD *)this + 2) += 2LL;
              *((_DWORD *)this + 7) += 2;
            }
            v17 = *((_DWORD *)this + 7);
            if ( v17 + 2 >= v17
              && (*((_DWORD *)this + 6) >= v17 + 2 || !(unsigned int)XLWrite::IncreaseBuffer(this, 2))
              && *((_QWORD *)this + 1) )
            {
              **((_WORD **)this + 2) = v14;
              *((_QWORD *)this + 2) += 2LL;
              *((_DWORD *)this + 7) += 2;
            }
            v18 = *((unsigned int *)this + 7);
            if ( (int)v18 + 1 >= (unsigned int)v18
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v18 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = -8;
              ++*((_DWORD *)this + 7);
            }
            v19 = *((unsigned int *)this + 7);
            if ( (int)v19 + 1 >= (unsigned int)v19
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v19 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = 76;
              ++*((_DWORD *)this + 7);
            }
            v20 = *((unsigned int *)this + 7);
            if ( (int)v20 + 1 >= (unsigned int)v20
              && (*((unsigned int *)this + 6) >= (unsigned __int64)(v20 + 8)
               || !(unsigned int)XLWrite::IncreaseBuffer(this, 8))
              && *((_QWORD *)this + 1) )
            {
              *(_BYTE *)(*((_QWORD *)this + 2))++ = 107;
              ++*((_DWORD *)this + 7);
            }
          }
          *((_DWORD *)this + 73) = v14;
          v6 = 0;
          *((_DWORD *)this + 72) = v13;
        }
        ++pptfx;
        --count;
      }
      if ( count > 0 && !v6 )
      {
        if ( (ppd.flags & 0x10) != 0 )
          v11 = XLOutput::BezierPath(this, pptfx, count);
        else
          v11 = XLOutput::LinePath(this, pptfx, count);
        v6 = v11;
      }
      if ( (ppd.flags & 8) != 0 && !v6 )
      {
        v21 = *((unsigned int *)this + 7);
        if ( (int)v21 + 1 >= (unsigned int)v21
          && (*((unsigned int *)this + 6) >= (unsigned __int64)(v21 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer(this, 8)) )
        {
          if ( *((_QWORD *)this + 1) )
          {
            *(_BYTE *)(*((_QWORD *)this + 2))++ = -124;
            ++*((_DWORD *)this + 7);
          }
        }
        v6 = 0;
      }
    }
    else
    {
      v6 = 1;
    }
  }
  while ( v9 );
  *((_QWORD *)a3 + 1) = *((_QWORD *)a3 + 522);
  return v6;
}

```

## disassembly

```asm
0x180014040  mov     rax, rsp
0x180014043  mov     [rax+18h], r8
0x180014047  mov     [rax+10h], rdx
0x18001404b  push    rbx
0x18001404c  push    r15
0x18001404e  sub     rsp, 68h
0x180014052  xorps   xmm0, xmm0
0x180014055  mov     r15, rdx
0x180014058  mov     rbx, rcx
0x18001405b  movups  xmmword ptr [rax-50h], xmm0
0x18001405f  test    rdx, rdx
0x180014062  jz      loc_180014309
0x180014068  mov     ecx, [rcx+1Ch]
0x18001406b  mov     [rax+8], rbp
0x18001406f  mov     [rax-18h], rsi
0x180014073  mov     [rax-20h], rdi
0x180014077  mov     [rax-28h], r12
0x18001407b  mov     [rax-38h], r14
0x18001407f  lea     eax, [rcx+1]
0x180014082  cmp     eax, ecx
0x180014084  jb      short loc_1800140AB
0x180014086  mov     eax, [rbx+18h]
0x180014089  add     rcx, 8
0x18001408d  cmp     rax, rcx
0x180014090  jb      loc_180014399
0x180014096  cmp     qword ptr [rbx+8], 0
0x18001409b  jz      short loc_1800140AB
0x18001409d  mov     rax, [rbx+10h]
0x1800140a1  mov     byte ptr [rax], 85h
0x1800140a4  inc     qword ptr [rbx+10h]
0x1800140a8  inc     dword ptr [rbx+1Ch]
0x1800140ab  xor     esi, esi
0x1800140ad  mov     rcx, r15; ppo
0x1800140b0  call    cs:__imp_PATHOBJ_vEnumStart
0x1800140b7  nop     dword ptr [rax+rax+00h]
0x1800140bc  mov     [rsp+78h+var_30], r13
0x1800140c1  lea     rdx, [rsp+78h+ppd]; ppd
0x1800140c6  mov     rcx, r15; ppo
0x1800140c9  call    cs:__imp_PATHOBJ_bEnum
0x1800140d0  nop     dword ptr [rax+rax+00h]
0x1800140d5  mov     edi, [rsp+78h+ppd.count]
0x1800140d9  mov     ebp, eax
0x1800140db  test    edi, edi
0x1800140dd  jz      loc_1800143B3
0x1800140e3  test    byte ptr [rsp+78h+ppd.flags], 1
0x1800140e8  mov     r14, [rsp+78h+ppd.pptfx]
0x1800140ed  jnz     short loc_180014163
0x1800140ef  test    edi, edi
0x1800140f1  jle     short loc_18001410E
0x1800140f3  test    esi, esi
0x1800140f5  jnz     short loc_18001410E
0x1800140f7  test    byte ptr [rsp+78h+ppd.flags], 10h
0x1800140fc  mov     r8d, edi; int
0x1800140ff  mov     rdx, r14; struct _POINTFIX *
0x180014102  mov     rcx, rbx; this
0x180014105  jz      short loc_18001415C
0x180014107  call    ?BezierPath@XLOutput@@QEAAJPEAU_POINTFIX@@J@Z; XLOutput::BezierPath(_POINTFIX *,long)
0x18001410c  mov     esi, eax
0x18001410e  test    byte ptr [rsp+78h+ppd.flags], 8
0x180014113  jnz     loc_1800142CB
0x180014119  test    ebp, ebp
0x18001411b  jnz     short loc_1800140C1
0x18001411d  mov     r14, [rsp+78h+arg_10]
0x180014125  mov     r13, [rsp+78h+var_30]
0x18001412a  mov     r12, [rsp+78h+var_28]
0x18001412f  mov     rdi, [rsp+78h+var_20]
0x180014134  mov     rax, [r14+1050h]
0x18001413b  mov     rbp, [rsp+78h+arg_0]
0x180014143  mov     [r14+8], rax
0x180014147  mov     eax, esi
0x180014149  mov     rsi, [rsp+78h+var_18]
0x18001414e  mov     r14, [rsp+78h+var_38]
0x180014153  add     rsp, 68h
0x180014157  pop     r15
0x180014159  pop     rbx
0x18001415a  retn
0x18001415c  call    ?LinePath@XLOutput@@QEAAJPEAU_POINTFIX@@J@Z; XLOutput::LinePath(_POINTFIX *,long)
0x180014161  jmp     short loc_18001410C
0x180014163  test    esi, esi
0x180014165  jnz     loc_1800142C0
0x18001416b  mov     r13d, [r14]
0x18001416e  mov     esi, [r14+4]
0x180014172  sar     r13d, 4
0x180014176  sar     esi, 4
0x180014179  mov     [rsp+78h+var_58], esi
0x18001417d  lea     eax, [r13+8000h]
0x180014184  cmp     eax, 0FFFFh
0x180014189  ja      loc_1800143F1
0x18001418f  lea     eax, [rsi+8000h]
0x180014195  cmp     eax, 0FFFFh
0x18001419a  ja      loc_1800143F1
0x1800141a0  mov     ecx, [rbx+1Ch]
0x1800141a3  lea     eax, [rcx+1]
0x1800141a6  cmp     eax, ecx
0x1800141a8  jb      short loc_1800141CF
0x1800141aa  mov     eax, [rbx+18h]
0x1800141ad  add     rcx, 8
0x1800141b1  cmp     rax, rcx
0x1800141b4  jb      loc_180014317
0x1800141ba  cmp     qword ptr [rbx+8], 0
0x1800141bf  jz      short loc_1800141CF
0x1800141c1  mov     rax, [rbx+10h]
0x1800141c5  mov     byte ptr [rax], 0D3h
0x1800141c8  inc     qword ptr [rbx+10h]
0x1800141cc  inc     dword ptr [rbx+1Ch]
0x1800141cf  mov     eax, [rbx+1Ch]
0x1800141d2  lea     ecx, [rax+2]
0x1800141d5  cmp     ecx, eax
0x1800141d7  jb      short loc_1800141FA
0x1800141d9  cmp     [rbx+18h], ecx
0x1800141dc  jb      loc_1800143BD
0x1800141e2  cmp     qword ptr [rbx+8], 0
0x1800141e7  jz      short loc_1800141FA
0x1800141e9  mov     rax, [rbx+10h]
0x1800141ed  mov     [rax], r13w
0x1800141f1  add     qword ptr [rbx+10h], 2
0x1800141f6  add     dword ptr [rbx+1Ch], 2
0x1800141fa  mov     eax, [rbx+1Ch]
0x1800141fd  lea     ecx, [rax+2]
0x180014200  cmp     ecx, eax
0x180014202  jb      short loc_180014224
0x180014204  cmp     [rbx+18h], ecx
0x180014207  jb      loc_1800143D7
0x18001420d  cmp     qword ptr [rbx+8], 0
0x180014212  jz      short loc_180014224
0x180014214  mov     rax, [rbx+10h]
0x180014218  mov     [rax], si
0x18001421b  add     qword ptr [rbx+10h], 2
0x180014220  add     dword ptr [rbx+1Ch], 2
0x180014224  mov     ecx, [rbx+1Ch]
0x180014227  lea     eax, [rcx+1]
0x18001422a  cmp     eax, ecx
0x18001422c  jb      short loc_180014253
0x18001422e  mov     eax, [rbx+18h]
0x180014231  add     rcx, 8
0x180014235  cmp     rax, rcx
0x180014238  jb      loc_180014331
0x18001423e  cmp     qword ptr [rbx+8], 0
0x180014243  jz      short loc_180014253
0x180014245  mov     rax, [rbx+10h]
0x180014249  mov     byte ptr [rax], 0F8h
0x18001424c  inc     qword ptr [rbx+10h]
0x180014250  inc     dword ptr [rbx+1Ch]
0x180014253  mov     ecx, [rbx+1Ch]
0x180014256  lea     eax, [rcx+1]
0x180014259  cmp     eax, ecx
0x18001425b  jb      short loc_180014282
0x18001425d  mov     eax, [rbx+18h]
0x180014260  add     rcx, 8
0x180014264  cmp     rax, rcx
0x180014267  jb      loc_18001434B
0x18001426d  cmp     qword ptr [rbx+8], 0
0x180014272  jz      short loc_180014282
0x180014274  mov     rax, [rbx+10h]
0x180014278  mov     byte ptr [rax], 4Ch ; 'L'
0x18001427b  inc     qword ptr [rbx+10h]
0x18001427f  inc     dword ptr [rbx+1Ch]
0x180014282  mov     ecx, [rbx+1Ch]
0x180014285  lea     eax, [rcx+1]
0x180014288  cmp     eax, ecx
0x18001428a  jb      short loc_1800142B1
0x18001428c  mov     eax, [rbx+18h]
0x18001428f  add     rcx, 8
0x180014293  cmp     rax, rcx
0x180014296  jb      loc_180014365
0x18001429c  cmp     qword ptr [rbx+8], 0
0x1800142a1  jz      short loc_1800142B1
0x1800142a3  mov     rax, [rbx+10h]
0x1800142a7  mov     byte ptr [rax], 6Bh ; 'k'
0x1800142aa  inc     qword ptr [rbx+10h]
0x1800142ae  inc     dword ptr [rbx+1Ch]
0x1800142b1  mov     [rbx+124h], esi
0x1800142b7  xor     esi, esi
0x1800142b9  mov     [rbx+120h], r13d
0x1800142c0  add     r14, 8
0x1800142c4  dec     edi
0x1800142c6  jmp     loc_1800140EF
0x1800142cb  test    esi, esi
0x1800142cd  jnz     loc_180014119
0x1800142d3  mov     ecx, [rbx+1Ch]
0x1800142d6  lea     eax, [rcx+1]
0x1800142d9  cmp     eax, ecx
0x1800142db  jb      short loc_180014302
0x1800142dd  mov     eax, [rbx+18h]
0x1800142e0  add     rcx, 8
0x1800142e4  cmp     rax, rcx
0x1800142e7  jb      loc_18001437F
0x1800142ed  cmp     qword ptr [rbx+8], 0
0x1800142f2  jz      short loc_180014302
0x1800142f4  mov     rax, [rbx+10h]
0x1800142f8  mov     byte ptr [rax], 84h
0x1800142fb  inc     qword ptr [rbx+10h]
0x1800142ff  inc     dword ptr [rbx+1Ch]
0x180014302  xor     esi, esi
0x180014304  jmp     loc_180014119
0x180014309  mov     eax, 8000FFFFh
0x18001430e  add     rsp, 68h
0x180014312  pop     r15
0x180014314  pop     rbx
0x180014315  retn
0x180014317  mov     edx, 8; unsigned int
0x18001431c  mov     rcx, rbx; this
0x18001431f  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014324  test    eax, eax
0x180014326  jnz     loc_1800141CF
0x18001432c  jmp     loc_1800141BA
0x180014331  mov     edx, 8; unsigned int
0x180014336  mov     rcx, rbx; this
0x180014339  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x18001433e  test    eax, eax
0x180014340  jnz     loc_180014253
0x180014346  jmp     loc_18001423E
0x18001434b  mov     edx, 8; unsigned int
0x180014350  mov     rcx, rbx; this
0x180014353  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014358  test    eax, eax
0x18001435a  jnz     loc_180014282
0x180014360  jmp     loc_18001426D
0x180014365  mov     edx, 8; unsigned int
0x18001436a  mov     rcx, rbx; this
0x18001436d  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x180014372  test    eax, eax
0x180014374  jnz     loc_1800142B1
0x18001437a  jmp     loc_18001429C
0x18001437f  mov     edx, 8; unsigned int
0x180014384  mov     rcx, rbx; this
0x180014387  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x18001438c  test    eax, eax
0x18001438e  jnz     loc_180014302
0x180014394  jmp     loc_1800142ED
0x180014399  mov     edx, 8; unsigned int
0x18001439e  mov     rcx, rbx; this
0x1800143a1  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x1800143a6  test    eax, eax
0x1800143a8  jnz     loc_1800140AB
0x1800143ae  jmp     loc_180014096
0x1800143b3  mov     esi, 1
0x1800143b8  jmp     loc_180014119
0x1800143bd  mov     edx, 2; unsigned int
0x1800143c2  mov     rcx, rbx; this
0x1800143c5  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x1800143ca  test    eax, eax
0x1800143cc  jnz     loc_1800141FA
0x1800143d2  jmp     loc_1800141E2
0x1800143d7  mov     edx, 2; unsigned int
0x1800143dc  mov     rcx, rbx; this
0x1800143df  call    ?IncreaseBuffer@XLWrite@@AEAAJK@Z; XLWrite::IncreaseBuffer(ulong)
0x1800143e4  test    eax, eax
0x1800143e6  jnz     loc_180014224
0x1800143ec  jmp     loc_18001420D
0x1800143f1  mov     r15d, esi
0x1800143f4  mov     r12d, r13d
0x1800143f7  mov     esi, 1
0x1800143fc  test    r12d, r12d
0x1800143ff  jnz     short loc_180014417
0x180014401  test    r15d, r15d
0x180014404  jnz     short loc_180014417
0x180014406  mov     r15, [rsp+78h+arg_8]
0x18001440e  mov     esi, [rsp+78h+var_58]
0x180014412  jmp     loc_1800142B1
0x180014417  mov     [rsp+78h+arg_18], esi
0x18001441e  cmp     r12d, 7FFFh
0x180014425  jle     short loc_180014431
0x180014427  mov     edx, 7FFFh
0x18001442c  sub     r12d, edx
0x18001442f  jmp     short loc_18001444E
0x180014431  cmp     r12d, 0FFFF8000h
0x180014438  jge     short loc_180014448
0x18001443a  mov     edx, 0FFFF8000h
0x18001443f  add     r12d, 8000h
0x180014446  jmp     short loc_18001444E
0x180014448  mov     edx, r12d; __int16
0x18001444b  xor     r12d, r12d
0x18001444e  cmp     r15d, 7FFFh
0x180014455  jle     short loc_180014462
0x180014457  mov     r8d, 7FFFh
0x18001445d  sub     r15d, r8d
0x180014460  jmp     short loc_180014480
0x180014462  cmp     r15d, 0FFFF8000h
0x180014469  jge     short loc_18001447A
0x18001446b  mov     r8d, 0FFFF8000h
0x180014471  add     r15d, 8000h
0x180014478  jmp     short loc_180014480
0x18001447a  mov     r8d, r15d; __int16
0x18001447d  xor     r15d, r15d
0x180014480  mov     rcx, rbx; this
0x180014483  call    ?Send_sint16_xy@XLOutput@@QEAAJFF@Z; XLOutput::Send_sint16_xy(short,short)
0x180014488  mov     edx, 4Ch ; 'L'
0x18001448d  mov     rcx, rbx
0x180014490  call    ?Send_attr_ubyte@XLOutput@@QEAAJW4Attribute@@@Z; XLOutput::Send_attr_ubyte(Attribute)
0x180014495  xor     esi, esi
0x180014497  mov     rcx, rbx; this
0x18001449a  cmp     [rsp+78h+arg_18], esi
0x1800144a1  setz    dl
0x1800144a4  add     dl, 6Bh ; 'k'; unsigned __int8
0x1800144a7  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800144ac  jmp     loc_1800143FC
```
