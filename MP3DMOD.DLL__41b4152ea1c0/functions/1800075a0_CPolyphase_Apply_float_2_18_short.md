# CPolyphase::Apply(float * (&)[2][18],short *)

- ea: `0x1800075a0`
- end: `0x180007836`
- name: `?Apply@CPolyphase@@QEAAPEAFAEAY11BC@PEAMPEAF@Z`
- size: `662`
- prototype: `__int16 *__fastcall(CPolyphase *this, float *(*)[2][18], __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180003b80`
- `0x18000d780`

## callees

- `0x180006b68`
- `0x180006f9c`
- `0x180007438`
- `0x1800075a0`
- `0x180007840`
- `0x180008490`
- `0x180008a70`
- `0x180008de0`

## pseudocode

```c
__int16 *__fastcall CPolyphase::Apply(CPolyphase *this, float *(*a2)[2][18], __int16 *a3, int a4)
{
  int v6; // r14d
  __int64 v7; // r15
  int v8; // r13d
  __int64 v9; // r12
  int v10; // ebp
  __int64 v11; // rsi
  int v12; // ecx
  __int64 v14; // rdx
  float v15; // xmm0_4
  float v16; // xmm0_4
  float v17; // xmm0_4
  float v18; // xmm0_4
  int v19; // ecx

  if ( *((_DWORD *)this + 12) )
    v6 = 1;
  else
    v6 = **((_DWORD **)this + 4);
  v7 = 0;
  v8 = 1 << (v6 - *((_BYTE *)this + 44) - *((_BYTE *)this + 40) + 4);
  v9 = 2LL * v8;
  do
  {
    v10 = 0;
    *(_DWORD *)this = ((unsigned __int16)*(_DWORD *)this - 32) & 0x1FF;
    if ( v6 > 0 )
    {
      v11 = 0;
      do
      {
        v12 = *((_DWORD *)this + 10);
        if ( v12 )
        {
          v19 = v12 - 1;
          if ( v19 )
          {
            if ( v19 == 1 )
              cost8((*a2)[v11][v7], *((_QWORD *)this + v11 + 1) + 4LL * *(int *)this);
          }
          else
          {
            cost16((*a2)[v11][v7], *((_QWORD *)this + v11 + 1) + 4LL * *(int *)this);
          }
        }
        else if ( v6 == 1 || *((_DWORD *)this + 11) == 1 )
        {
          cost32((*a2)[v11][v7], *((_QWORD *)this + v11 + 1) + 4LL * *(int *)this);
        }
        else
        {
          cost32_mod((*a2)[v11][v7], *((_QWORD *)this + v11 + 1), *(unsigned int *)this);
        }
        ++v10;
        ++v11;
      }
      while ( v10 < v6 );
      v9 = 2LL * v8;
    }
    if ( v6 == 1 )
    {
      CPolyphase::window_band_m(this, *(_DWORD *)this, a3, a4);
    }
    else if ( *((_DWORD *)this + 10) || *((_DWORD *)this + 11) == 1 )
    {
      CPolyphase::window_band_s(this, *(_DWORD *)this, a3, a4);
    }
    else
    {
      CPolyphase::window_band_s_mod(this, *(_DWORD *)this, a3, a4);
    }
    if ( *((_DWORD *)this + 11) == -1 )
    {
      v14 = (unsigned int)(v8 / 2 - 1);
      if ( (int)v14 >= 0 )
      {
        if ( v8 / 2 >= 5 )
        {
          do
          {
            v15 = (double)a3[v14] / 32767.0;
            *(float *)&a3[2 * v14] = v15;
            v16 = (double)a3[v14 - 1] / 32767.0;
            *(float *)&a3[2 * v14 - 2] = v16;
            v17 = (double)a3[v14 - 2] / 32767.0;
            *(float *)&a3[2 * v14 - 4] = v17;
            v18 = (double)a3[v14 - 3] / 32767.0;
            *(float *)&a3[2 * v14 - 6] = v18;
            *(float *)&a3[2 * v14 - 8] = (double)a3[v14 - 4] / 32767.0;
            v14 = (unsigned int)(v14 - 5);
          }
          while ( (int)v14 >= 4 );
        }
        for ( ; (int)v14 >= 0; v14 = (unsigned int)(v14 - 1) )
          *(float *)&a3[2 * v14] = (double)a3[v14] / 32767.0;
      }
    }
    a3 = (__int16 *)((char *)a3 + v9);
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (int)v7 < 18 );
  return a3;
}

```

## disassembly

```asm
0x1800075a0  mov     [rsp+arg_10], rbx
0x1800075a5  mov     [rsp+arg_8], rdx
0x1800075aa  push    rbp
0x1800075ab  push    rsi
0x1800075ac  push    rdi
0x1800075ad  push    r12
0x1800075af  push    r13
0x1800075b1  push    r14
0x1800075b3  push    r15
0x1800075b5  sub     rsp, 30h
0x1800075b9  cmp     dword ptr [rcx+30h], 0
0x1800075bd  mov     rbx, r8
0x1800075c0  movaps  [rsp+68h+var_48], xmm6
0x1800075c5  mov     rdi, rcx
0x1800075c8  mov     r13d, 1
0x1800075ce  jnz     loc_18000782E
0x1800075d4  mov     rax, [rcx+20h]
0x1800075d8  mov     r14d, [rax]
0x1800075db  movsd   xmm6, cs:__real@40dfffc000000000
0x1800075e3  mov     ecx, r14d
0x1800075e6  sub     ecx, [rdi+2Ch]
0x1800075e9  xor     r15d, r15d
0x1800075ec  sub     ecx, [rdi+28h]
0x1800075ef  add     ecx, 4
0x1800075f2  shl     r13d, cl
0x1800075f5  movsxd  r12, r13d
0x1800075f8  add     r12, r12
0x1800075fb  mov     [rsp+68h+arg_0], r12
0x180007600  mov     eax, [rdi]
0x180007602  xor     ebp, ebp
0x180007604  sub     eax, 20h ; ' '
0x180007607  and     eax, 1FFh
0x18000760c  mov     [rdi], eax
0x18000760e  test    r14d, r14d
0x180007611  jle     short loc_180007661
0x180007613  mov     r12, [rsp+68h+arg_8]
0x180007618  xor     esi, esi
0x18000761a  mov     ecx, [rdi+28h]
0x18000761d  test    ecx, ecx
0x18000761f  jnz     loc_1800077CA
0x180007625  cmp     r14d, 1
0x180007629  jz      loc_1800077A8
0x18000762f  cmp     dword ptr [rdi+2Ch], 1
0x180007633  jz      loc_1800077A8
0x180007639  mov     r8d, [rdi]
0x18000763c  lea     rcx, [rsi+rsi*8]
0x180007640  mov     rdx, [rdi+rsi*8+8]
0x180007645  lea     rcx, [r15+rcx*2]
0x180007649  mov     rcx, [r12+rcx*8]
0x18000764d  call    cost32_mod
0x180007652  inc     ebp
0x180007654  inc     rsi
0x180007657  cmp     ebp, r14d
0x18000765a  jl      short loc_18000761A
0x18000765c  mov     r12, [rsp+68h+arg_0]
0x180007661  cmp     r14d, 1
0x180007665  jz      short loc_1800076BE
0x180007667  cmp     dword ptr [rdi+28h], 0
0x18000766b  jnz     loc_18000781C
0x180007671  cmp     dword ptr [rdi+2Ch], 1
0x180007675  jz      loc_18000781C
0x18000767b  mov     edx, [rdi]; int
0x18000767d  mov     r8, rbx; __int16 *
0x180007680  mov     rcx, rdi; this
0x180007683  call    ?window_band_s_mod@CPolyphase@@IEAAXHPEAFH@Z; CPolyphase::window_band_s_mod(int,short *,int)
0x180007688  cmp     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x18000768c  jz      short loc_1800076CD
0x18000768e  add     rbx, r12
0x180007691  inc     r15d
0x180007694  cmp     r15d, 12h
0x180007698  jl      loc_180007600
0x18000769e  movaps  xmm6, [rsp+68h+var_48]
0x1800076a3  mov     rax, rbx
0x1800076a6  mov     rbx, [rsp+68h+arg_10]
0x1800076ae  add     rsp, 30h
0x1800076b2  pop     r15
0x1800076b4  pop     r14
0x1800076b6  pop     r13
0x1800076b8  pop     r12
0x1800076ba  pop     rdi
0x1800076bb  pop     rsi
0x1800076bc  pop     rbp
0x1800076bd  retn
0x1800076be  mov     edx, [rdi]; int
0x1800076c0  mov     r8, rbx; __int16 *
0x1800076c3  mov     rcx, rdi; this
0x1800076c6  call    ?window_band_m@CPolyphase@@IEAAXHPEAFH@Z; CPolyphase::window_band_m(int,short *,int)
0x1800076cb  jmp     short loc_180007688
0x1800076cd  mov     eax, r13d
0x1800076d0  test    r13d, r13d
0x1800076d3  jns     short loc_1800076D9
0x1800076d5  lea     eax, [r13+1]
0x1800076d9  sar     eax, 1
0x1800076db  lea     edx, [rax-1]
0x1800076de  test    edx, edx
0x1800076e0  js      short loc_18000768E
0x1800076e2  cmp     eax, 5
0x1800076e5  jl      loc_18000777C
0x1800076eb  nop     dword ptr [rax+rax+00h]
0x1800076f0  movsx   eax, word ptr [rbx+rdx*2]
0x1800076f4  xorps   xmm0, xmm0
0x1800076f7  cvtsi2sd xmm0, eax
0x1800076fb  divsd   xmm0, xmm6
0x1800076ff  cvtpd2ps xmm0, xmm0
0x180007703  movss   dword ptr [rbx+rdx*4], xmm0
0x180007708  xorps   xmm0, xmm0
0x18000770b  movsx   eax, word ptr [rbx+rdx*2-2]
0x180007710  cvtsi2sd xmm0, eax
0x180007714  divsd   xmm0, xmm6
0x180007718  cvtpd2ps xmm0, xmm0
0x18000771c  movss   dword ptr [rbx+rdx*4-4], xmm0
0x180007722  xorps   xmm0, xmm0
0x180007725  movsx   eax, word ptr [rbx+rdx*2-4]
0x18000772a  cvtsi2sd xmm0, eax
0x18000772e  divsd   xmm0, xmm6
0x180007732  cvtpd2ps xmm0, xmm0
0x180007736  movss   dword ptr [rbx+rdx*4-8], xmm0
0x18000773c  xorps   xmm0, xmm0
0x18000773f  movsx   eax, word ptr [rbx+rdx*2-6]
0x180007744  cvtsi2sd xmm0, eax
0x180007748  divsd   xmm0, xmm6
0x18000774c  cvtpd2ps xmm0, xmm0
0x180007750  movss   dword ptr [rbx+rdx*4-0Ch], xmm0
0x180007756  xorps   xmm0, xmm0
0x180007759  movsx   eax, word ptr [rbx+rdx*2-8]
0x18000775e  cvtsi2sd xmm0, eax
0x180007762  divsd   xmm0, xmm6
0x180007766  cvtpd2ps xmm0, xmm0
0x18000776a  movss   dword ptr [rbx+rdx*4-10h], xmm0
0x180007770  sub     edx, 5
0x180007773  cmp     edx, 4
0x180007776  jge     loc_1800076F0
0x18000777c  test    edx, edx
0x18000777e  js      loc_18000768E
0x180007784  movsx   eax, word ptr [rbx+rdx*2]
0x180007788  movd    xmm0, eax
0x18000778c  cvtdq2pd xmm0, xmm0
0x180007790  divsd   xmm0, xmm6
0x180007794  cvtpd2ps xmm0, xmm0
0x180007798  movss   dword ptr [rbx+rdx*4], xmm0
0x18000779d  sub     edx, 1
0x1800077a0  js      loc_18000768E
0x1800077a6  jmp     short loc_180007784
0x1800077a8  movsxd  rcx, dword ptr [rdi]
0x1800077ab  mov     rax, [rdi+rsi*8+8]
0x1800077b0  lea     rdx, [rax+rcx*4]
0x1800077b4  lea     rcx, [rsi+rsi*8]
0x1800077b8  lea     rcx, [r15+rcx*2]
0x1800077bc  mov     rcx, [r12+rcx*8]
0x1800077c0  call    cost32
0x1800077c5  jmp     loc_180007652
0x1800077ca  sub     ecx, 1
0x1800077cd  jz      short loc_1800077FA
0x1800077cf  cmp     ecx, 1
0x1800077d2  jnz     loc_180007652
0x1800077d8  movsxd  rcx, dword ptr [rdi]
0x1800077db  mov     rax, [rdi+rsi*8+8]
0x1800077e0  lea     rdx, [rax+rcx*4]
0x1800077e4  lea     rcx, [rsi+rsi*8]
0x1800077e8  lea     rcx, [r15+rcx*2]
0x1800077ec  mov     rcx, [r12+rcx*8]
0x1800077f0  call    cost8
0x1800077f5  jmp     loc_180007652
0x1800077fa  movsxd  rcx, dword ptr [rdi]
0x1800077fd  mov     rax, [rdi+rsi*8+8]
0x180007802  lea     rdx, [rax+rcx*4]
0x180007806  lea     rcx, [rsi+rsi*8]
0x18000780a  lea     rcx, [r15+rcx*2]
0x18000780e  mov     rcx, [r12+rcx*8]
0x180007812  call    cost16
0x180007817  jmp     loc_180007652
0x18000781c  mov     edx, [rdi]; int
0x18000781e  mov     r8, rbx; __int16 *
0x180007821  mov     rcx, rdi; this
0x180007824  call    ?window_band_s@CPolyphase@@IEAAXHPEAFH@Z; CPolyphase::window_band_s(int,short *,int)
0x180007829  jmp     loc_180007688
0x18000782e  mov     r14d, r13d
0x180007831  jmp     loc_1800075DB
```
