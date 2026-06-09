# CVideoObjectDecoder::RenderFrame_Planar(uchar *,uchar *,uchar *)

- ea: `0x180032478`
- end: `0x180032743`
- name: `?RenderFrame_Planar@CVideoObjectDecoder@@AEAAXPEAE00@Z`
- size: `715`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e90`
- `0x180004f10`
- `0x180012114`
- `0x180035770`
- `0x180035e90`

## callees

- `0x180032478`
- `0x180046010`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::RenderFrame_Planar(
        CVideoObjectDecoder *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 v4; // rax
  unsigned int v6; // r15d
  unsigned __int8 *v7; // rdi
  __int64 v8; // rsi
  unsigned __int8 *v9; // rcx
  unsigned __int8 *v10; // rdx
  __int64 v11; // rbp
  _DWORD *v12; // r8
  __int64 v13; // r14
  unsigned int v14; // eax
  unsigned __int8 *v15; // r13
  unsigned int v16; // ecx
  unsigned __int8 *v17; // r12
  __int64 v18; // rsi
  __int64 v19; // rdi
  unsigned __int8 *v20; // rbp
  __int64 v21; // r14
  int v22; // ecx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int8 *v27; // [rsp+70h] [rbp-78h]
  __int64 v28; // [rsp+78h] [rbp-70h]
  __int64 v29; // [rsp+80h] [rbp-68h]
  __int64 v30; // [rsp+88h] [rbp-60h]
  __int64 v31; // [rsp+98h] [rbp-50h]
  unsigned int v32; // [rsp+F0h] [rbp+8h]
  _DWORD *v33; // [rsp+F8h] [rbp+10h]
  unsigned __int8 *v34; // [rsp+100h] [rbp+18h]
  unsigned __int8 *v35; // [rsp+108h] [rbp+20h]

  v4 = *((int *)this + 346);
  v6 = 0;
  v7 = &a2[*((int *)this + 345)];
  v34 = v7;
  v8 = *((_QWORD *)this + 952);
  v9 = &a3[v4];
  v10 = &a4[v4];
  v11 = v8 + *((int *)this + 624);
  v12 = (_DWORD *)*((_QWORD *)this + 941);
  v13 = v8 + *((int *)this + 620);
  v35 = v9;
  v27 = &a4[v4];
  v28 = v8;
  v29 = v11;
  v30 = v13;
  v33 = v12;
  if ( !*((_DWORD *)this + 223) )
    return;
  do
  {
    v14 = *((_DWORD *)this + 222);
    if ( !v14 )
      goto LABEL_19;
    v31 = v8;
    v15 = v9;
    v16 = 0;
    v17 = v7;
    v18 = v11;
    v32 = 0;
    v19 = v13;
    v20 = v10;
    v21 = v31;
    do
    {
      if ( !*v12 || *((_DWORD *)this + 599) )
      {
        if ( *((_DWORD *)this + 320) )
        {
LABEL_7:
          (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD))this
           + 323))(
            v21,
            v18,
            v19,
            v17,
            v15,
            v20,
            *((_DWORD *)this + 333),
            *((_DWORD *)this + 334),
            *((_DWORD *)this + 603),
            *((_DWORD *)this + 628));
LABEL_16:
          v16 = v32;
          goto LABEL_17;
        }
        if ( v16 == v14 - 1 )
        {
          v22 = *((_DWORD *)this + 314) - *((_DWORD *)this + 321) + 16;
        }
        else
        {
          if ( v6 != *((_DWORD *)this + 223) - 1 )
            goto LABEL_7;
          v22 = 16;
        }
        if ( v6 == *((_DWORD *)this + 223) - 1 )
          v23 = *((_DWORD *)this + 315) - *((_DWORD *)this + 323) + 16;
        else
          v23 = 16;
        (*((void (__fastcall **)(__int64, __int64, __int64, unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, _DWORD, _DWORD, _DWORD, _DWORD, int, int))this
         + 324))(
          v21,
          v18,
          v19,
          v17,
          v15,
          v20,
          *((_DWORD *)this + 333),
          *((_DWORD *)this + 334),
          *((_DWORD *)this + 603),
          *((_DWORD *)this + 628),
          v22,
          v23);
        goto LABEL_16;
      }
LABEL_17:
      ++v16;
      v33 += 28;
      v21 += *((int *)this + 606);
      v24 = *((int *)this + 630);
      v17 += 16;
      v12 = v33;
      v18 += v24;
      v19 += v24;
      v32 = v16;
      v14 = *((_DWORD *)this + 222);
      v15 += 8;
      v20 += 8;
    }
    while ( v16 < v14 );
    v7 = v34;
    v8 = v28;
    v11 = v29;
    v13 = v30;
    v9 = v35;
    v10 = v27;
LABEL_19:
    ++v6;
    v7 += *((int *)this + 1887);
    v25 = *((int *)this + 1888);
    v9 += v25;
    v34 = v7;
    v10 += v25;
    v35 = v9;
    v8 += *((int *)this + 608);
    v27 = v10;
    v26 = *((int *)this + 631);
    v11 += v26;
    v28 = v8;
    v13 += v26;
    v29 = v11;
    v30 = v13;
  }
  while ( v6 < *((_DWORD *)this + 223) );
}

```

## disassembly

```asm
0x180032478  push    rbx
0x18003247a  push    rbp
0x18003247b  push    rsi
0x18003247c  push    rdi
0x18003247d  push    r12
0x18003247f  push    r13
0x180032481  push    r14
0x180032483  push    r15
0x180032485  sub     rsp, 0A8h
0x18003248c  movsxd  rax, dword ptr [rcx+568h]
0x180032493  mov     rbx, rcx
0x180032496  movsxd  rdi, dword ptr [rcx+564h]
0x18003249d  xor     r15d, r15d
0x1800324a0  add     rdi, rdx
0x1800324a3  mov     [rsp+0E8h+arg_10], rdi
0x1800324ab  mov     rsi, [rbx+1DC0h]
0x1800324b2  lea     rcx, [rax+r8]
0x1800324b6  movsxd  rbp, dword ptr [rbx+9C0h]
0x1800324bd  lea     rdx, [rax+r9]
0x1800324c1  movsxd  r14, dword ptr [rbx+9B0h]
0x1800324c8  add     rbp, rsi
0x1800324cb  mov     r8, [rbx+1D68h]
0x1800324d2  add     r14, rsi
0x1800324d5  mov     [rsp+0E8h+arg_18], rcx
0x1800324dd  mov     [rsp+0E8h+var_78], rdx
0x1800324e2  mov     [rsp+0E8h+var_70], rsi
0x1800324e7  mov     [rsp+0E8h+var_68], rbp
0x1800324ef  mov     [rsp+0E8h+var_60], r14
0x1800324f7  mov     [rsp+0E8h+arg_8], r8
0x1800324ff  cmp     [rbx+37Ch], r15d
0x180032506  jbe     loc_18003272F
0x18003250c  mov     eax, [rbx+378h]
0x180032512  test    eax, eax
0x180032514  jz      loc_1800326C7
0x18003251a  mov     [rsp+0E8h+var_50], rsi
0x180032522  mov     r13, rcx
0x180032525  xor     ecx, ecx
0x180032527  mov     r12, rdi
0x18003252a  mov     rsi, rbp
0x18003252d  mov     [rsp+0E8h+arg_0], ecx
0x180032534  mov     rdi, r14
0x180032537  mov     rbp, rdx
0x18003253a  mov     r14, [rsp+0E8h+var_50]
0x180032542  cmp     dword ptr [r8], 0
0x180032546  jz      short loc_180032555
0x180032548  cmp     dword ptr [rbx+95Ch], 0
0x18003254f  jz      loc_180032652
0x180032555  cmp     dword ptr [rbx+500h], 0
0x18003255c  jz      short loc_1800325AD
0x18003255e  mov     ecx, [rbx+9D0h]
0x180032564  mov     r9, r12
0x180032567  mov     rax, [rbx+0A18h]
0x18003256e  mov     r8, rdi
0x180032571  mov     [rsp+0E8h+var_A0], ecx
0x180032575  mov     rdx, rsi
0x180032578  mov     ecx, [rbx+96Ch]
0x18003257e  mov     [rsp+0E8h+var_A8], ecx
0x180032582  mov     ecx, [rbx+538h]
0x180032588  mov     [rsp+0E8h+var_B0], ecx
0x18003258c  mov     ecx, [rbx+534h]
0x180032592  mov     [rsp+0E8h+var_B8], ecx
0x180032596  mov     rcx, r14
0x180032599  mov     [rsp+0E8h+var_C0], rbp
0x18003259e  mov     [rsp+0E8h+var_C8], r13
0x1800325a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325a8  jmp     loc_18003264B
0x1800325ad  dec     eax
0x1800325af  cmp     ecx, eax
0x1800325b1  jz      short loc_1800325C7
0x1800325b3  mov     eax, [rbx+37Ch]
0x1800325b9  dec     eax
0x1800325bb  cmp     r15d, eax
0x1800325be  jnz     short loc_18003255E
0x1800325c0  mov     ecx, 10h
0x1800325c5  jmp     short loc_1800325D6
0x1800325c7  mov     ecx, [rbx+4E8h]
0x1800325cd  sub     ecx, [rbx+504h]
0x1800325d3  add     ecx, 10h
0x1800325d6  mov     eax, [rbx+37Ch]
0x1800325dc  dec     eax
0x1800325de  cmp     r15d, eax
0x1800325e1  jz      short loc_1800325EA
0x1800325e3  mov     eax, 10h
0x1800325e8  jmp     short loc_1800325F9
0x1800325ea  mov     eax, [rbx+4ECh]
0x1800325f0  sub     eax, [rbx+50Ch]
0x1800325f6  add     eax, 10h
0x1800325f9  mov     [rsp+0E8h+var_90], eax
0x1800325fd  mov     r9, r12
0x180032600  mov     rax, [rbx+0A20h]
0x180032607  mov     r8, rdi
0x18003260a  mov     [rsp+0E8h+var_98], ecx
0x18003260e  mov     rdx, rsi
0x180032611  mov     ecx, [rbx+9D0h]
0x180032617  mov     [rsp+0E8h+var_A0], ecx
0x18003261b  mov     ecx, [rbx+96Ch]
0x180032621  mov     [rsp+0E8h+var_A8], ecx
0x180032625  mov     ecx, [rbx+538h]
0x18003262b  mov     [rsp+0E8h+var_B0], ecx
0x18003262f  mov     ecx, [rbx+534h]
0x180032635  mov     [rsp+0E8h+var_B8], ecx
0x180032639  mov     rcx, r14
0x18003263c  mov     [rsp+0E8h+var_C0], rbp
0x180032641  mov     [rsp+0E8h+var_C8], r13
0x180032646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003264b  mov     ecx, [rsp+0E8h+arg_0]
0x180032652  movsxd  rax, dword ptr [rbx+978h]
0x180032659  inc     ecx
0x18003265b  add     [rsp+0E8h+arg_8], 70h ; 'p'
0x180032664  add     r14, rax
0x180032667  movsxd  rax, dword ptr [rbx+9D8h]
0x18003266e  add     r12, 10h
0x180032672  mov     r8, [rsp+0E8h+arg_8]
0x18003267a  add     rsi, rax
0x18003267d  add     rdi, rax
0x180032680  mov     [rsp+0E8h+arg_0], ecx
0x180032687  mov     eax, [rbx+378h]
0x18003268d  add     r13, 8
0x180032691  add     rbp, 8
0x180032695  cmp     ecx, eax
0x180032697  jb      loc_180032542
0x18003269d  mov     rdi, [rsp+0E8h+arg_10]
0x1800326a5  mov     rsi, [rsp+0E8h+var_70]
0x1800326aa  mov     rbp, [rsp+0E8h+var_68]
0x1800326b2  mov     r14, [rsp+0E8h+var_60]
0x1800326ba  mov     rcx, [rsp+0E8h+arg_18]
0x1800326c2  mov     rdx, [rsp+0E8h+var_78]
0x1800326c7  movsxd  rax, dword ptr [rbx+1D7Ch]
0x1800326ce  inc     r15d
0x1800326d1  add     rdi, rax
0x1800326d4  movsxd  rax, dword ptr [rbx+1D80h]
0x1800326db  add     rcx, rax
0x1800326de  mov     [rsp+0E8h+arg_10], rdi
0x1800326e6  add     rdx, rax
0x1800326e9  mov     [rsp+0E8h+arg_18], rcx
0x1800326f1  movsxd  rax, dword ptr [rbx+980h]
0x1800326f8  add     rsi, rax
0x1800326fb  mov     [rsp+0E8h+var_78], rdx
0x180032700  movsxd  rax, dword ptr [rbx+9DCh]
0x180032707  add     rbp, rax
0x18003270a  mov     [rsp+0E8h+var_70], rsi
0x18003270f  add     r14, rax
0x180032712  mov     [rsp+0E8h+var_68], rbp
0x18003271a  mov     [rsp+0E8h+var_60], r14
0x180032722  cmp     r15d, [rbx+37Ch]
0x180032729  jb      loc_18003250C
0x18003272f  add     rsp, 0A8h
0x180032736  pop     r15
0x180032738  pop     r14
0x18003273a  pop     r13
0x18003273c  pop     r12
0x18003273e  pop     rdi
0x18003273f  pop     rsi
0x180032740  pop     rbp
0x180032741  pop     rbx
0x180032742  retn
```
