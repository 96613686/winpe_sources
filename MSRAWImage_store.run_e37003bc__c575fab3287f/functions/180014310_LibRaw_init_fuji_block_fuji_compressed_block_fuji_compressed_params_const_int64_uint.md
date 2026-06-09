# LibRaw::init_fuji_block(fuji_compressed_block *,fuji_compressed_params const *,__int64,uint)

- ea: `0x180014310`
- end: `0x18001468f`
- name: `?init_fuji_block@LibRaw@@IEAAXPEAUfuji_compressed_block@@PEBUfuji_compressed_params@@_JI@Z`
- size: `895`
- prototype: `void __usercall(LibRaw *__hidden this@<rcx>, struct fuji_compressed_block *@<rdx>, const struct fuji_compressed_params *@<r8>, __int64@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013a50`

## callees

- `0x180008f30`
- `0x180009470`
- `0x180013f40`
- `0x180014310`
- `0x1800b4010`

## pseudocode

```c
void __fastcall LibRaw::init_fuji_block(
        LibRaw *this,
        struct fuji_compressed_block *a2,
        const struct fuji_compressed_params *a3,
        __int64 a4,
        unsigned int a5)
{
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // r8
  char *v30; // r9
  int v31; // ecx
  _DWORD *v32; // rax
  __int64 v33; // rdx
  char *v34; // r9
  __int64 v35; // r11
  _DWORD *v36; // r10
  _DWORD *v37; // rax
  __int64 v38; // rdx
  int v39; // ecx

  *((_QWORD *)a2 + 342) = LibRaw::calloc(this, 2u, 18 * (*((unsigned __int16 *)a3 + 74) + 2LL));
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 47659) + 40LL))(*((_QWORD *)this + 47659));
  v10 = a5;
  v11 = v9 - a4;
  *((_DWORD *)a2 + 8) = 1;
  if ( v11 < a5 )
    v10 = v11;
  *((_DWORD *)a2 + 4) = v10;
  v12 = *((_QWORD *)a2 + 342);
  *((_QWORD *)a2 + 5) = *((_QWORD *)this + 47659);
  *((_QWORD *)a2 + 343) = v12;
  v13 = v12 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 344) = v13;
  v14 = v13 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 345) = v14;
  v15 = v14 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 346) = v15;
  v16 = v15 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 347) = v16;
  v17 = v16 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 348) = v17;
  v18 = v17 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 349) = v18;
  v19 = v18 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 350) = v19;
  v20 = v19 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 351) = v20;
  v21 = v20 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 352) = v21;
  v22 = v21 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 353) = v22;
  v23 = v22 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 354) = v23;
  v24 = v23 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 355) = v24;
  v25 = v24 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 356) = v25;
  v26 = v25 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 357) = v26;
  v27 = v26 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 358) = v27;
  v28 = v27 + 2 * (*((unsigned __int16 *)a3 + 74) + 2LL);
  *((_QWORD *)a2 + 359) = v28;
  *((_QWORD *)a2 + 360) = v28 + 2LL * *((unsigned __int16 *)a3 + 74) + 4;
  *((_QWORD *)a2 + 3) = LibRaw::malloc(this, 0x10000u);
  *((_QWORD *)a2 + 1) = a4;
  *(_QWORD *)a2 = 0;
  *((_DWORD *)a2 + 5) = 0;
  fuji_fill_buffer(a2);
  v29 = 3;
  if ( *((_DWORD *)this + 95396) )
  {
    v30 = (char *)a2 + 52;
    v31 = (*((_DWORD *)a3 + 3) + 32) >> 6;
    if ( v31 < 2 )
      v31 = 2;
    do
    {
      v32 = v30;
      v33 = 41;
      do
      {
        *(v32 - 1) = v31;
        *v32 = 1;
        v32[335] = v31;
        v32[336] = 1;
        v32 += 2;
        --v33;
      }
      while ( v33 );
      v30 += 448;
      --v29;
    }
    while ( v29 );
  }
  else
  {
    v34 = (char *)a2 + 380;
    v35 = 3;
    v36 = (_DWORD *)((char *)a3 + 44);
    do
    {
      v37 = v34;
      v38 = 3;
      v39 = (*v36 + 32) >> 6;
      if ( v39 < 2 )
        v39 = 2;
      do
      {
        *(v37 - 1) = v39;
        *v37 = 1;
        v37[335] = v39;
        v37[336] = 1;
        v37[1] = v39;
        v37[2] = 1;
        v37[337] = v39;
        v37[338] = 1;
        v37[3] = v39;
        v37[4] = 1;
        v37[339] = v39;
        v37[340] = 1;
        v37[5] = v39;
        v37[6] = 1;
        v37[341] = v39;
        v37[342] = 1;
        v37[7] = v39;
        v37[8] = 1;
        v37[343] = v39;
        v37[344] = 1;
        v37 += 112;
        --v38;
      }
      while ( v38 );
      v36 += 8;
      v34 += 40;
      --v35;
    }
    while ( v35 );
  }
}

```

## disassembly

```asm
0x180014310  mov     [rsp+arg_0], rbx
0x180014315  mov     [rsp+arg_8], rbp
0x18001431a  mov     [rsp+arg_10], rsi
0x18001431f  mov     [rsp+arg_18], rdi
0x180014324  push    r14
0x180014326  sub     rsp, 20h
0x18001432a  movzx   eax, word ptr [r8+94h]
0x180014332  mov     rbp, r8
0x180014335  add     rax, 2
0x180014339  mov     rsi, rdx
0x18001433c  mov     r14d, 2
0x180014342  mov     rbx, r9
0x180014345  mov     edx, r14d; unsigned __int64
0x180014348  mov     rdi, rcx
0x18001434b  lea     r8, [rax+rax*8]
0x18001434f  add     r8, r8; unsigned __int64
0x180014352  call    ?calloc@LibRaw@@IEAAPEAX_K0@Z; LibRaw::calloc(unsigned __int64,unsigned __int64)
0x180014357  mov     [rsi+0AB0h], rax
0x18001435e  mov     rcx, [rdi+5D158h]
0x180014365  mov     rax, [rcx]
0x180014368  mov     rax, [rax+28h]
0x18001436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014371  mov     ecx, [rsp+28h+arg_20]
0x180014375  sub     eax, ebx
0x180014377  cmp     eax, ecx
0x180014379  mov     dword ptr [rsi+20h], 1
0x180014380  cmovb   ecx, eax
0x180014383  mov     [rsi+10h], ecx
0x180014386  mov     rax, [rdi+5D158h]
0x18001438d  mov     rcx, [rsi+0AB0h]
0x180014394  mov     [rsi+28h], rax
0x180014398  mov     [rsi+0AB8h], rcx
0x18001439f  movzx   eax, word ptr [rbp+94h]
0x1800143a6  add     rax, r14
0x1800143a9  lea     rdx, [rcx+rax*2]
0x1800143ad  mov     [rsi+0AC0h], rdx
0x1800143b4  movzx   eax, word ptr [rbp+94h]
0x1800143bb  add     rax, r14
0x1800143be  lea     rcx, [rdx+rax*2]
0x1800143c2  mov     [rsi+0AC8h], rcx
0x1800143c9  movzx   eax, word ptr [rbp+94h]
0x1800143d0  add     rax, r14
0x1800143d3  lea     rdx, [rcx+rax*2]
0x1800143d7  mov     [rsi+0AD0h], rdx
0x1800143de  movzx   eax, word ptr [rbp+94h]
0x1800143e5  add     rax, r14
0x1800143e8  lea     rcx, [rdx+rax*2]
0x1800143ec  mov     [rsi+0AD8h], rcx
0x1800143f3  movzx   eax, word ptr [rbp+94h]
0x1800143fa  add     rax, r14
0x1800143fd  lea     rdx, [rcx+rax*2]
0x180014401  mov     [rsi+0AE0h], rdx
0x180014408  movzx   eax, word ptr [rbp+94h]
0x18001440f  add     rax, r14
0x180014412  lea     rcx, [rdx+rax*2]
0x180014416  mov     [rsi+0AE8h], rcx
0x18001441d  movzx   eax, word ptr [rbp+94h]
0x180014424  add     rax, r14
0x180014427  lea     rdx, [rcx+rax*2]
0x18001442b  mov     [rsi+0AF0h], rdx
0x180014432  movzx   eax, word ptr [rbp+94h]
0x180014439  add     rax, r14
0x18001443c  lea     rcx, [rdx+rax*2]
0x180014440  mov     [rsi+0AF8h], rcx
0x180014447  movzx   eax, word ptr [rbp+94h]
0x18001444e  add     rax, r14
0x180014451  lea     rdx, [rcx+rax*2]
0x180014455  mov     [rsi+0B00h], rdx
0x18001445c  movzx   eax, word ptr [rbp+94h]
0x180014463  add     rax, r14
0x180014466  lea     rcx, [rdx+rax*2]
0x18001446a  mov     [rsi+0B08h], rcx
0x180014471  movzx   eax, word ptr [rbp+94h]
0x180014478  add     rax, r14
0x18001447b  lea     rdx, [rcx+rax*2]
0x18001447f  mov     [rsi+0B10h], rdx
0x180014486  movzx   eax, word ptr [rbp+94h]
0x18001448d  add     rax, r14
0x180014490  lea     rcx, [rdx+rax*2]
0x180014494  mov     [rsi+0B18h], rcx
0x18001449b  movzx   eax, word ptr [rbp+94h]
0x1800144a2  add     rax, r14
0x1800144a5  lea     rdx, [rcx+rax*2]
0x1800144a9  mov     [rsi+0B20h], rdx
0x1800144b0  movzx   eax, word ptr [rbp+94h]
0x1800144b7  add     rax, r14
0x1800144ba  lea     rcx, [rdx+rax*2]
0x1800144be  mov     [rsi+0B28h], rcx
0x1800144c5  movzx   eax, word ptr [rbp+94h]
0x1800144cc  add     rax, r14
0x1800144cf  lea     rdx, [rcx+rax*2]
0x1800144d3  mov     [rsi+0B30h], rdx
0x1800144da  movzx   eax, word ptr [rbp+94h]
0x1800144e1  add     rax, r14
0x1800144e4  lea     rcx, [rdx+rax*2]
0x1800144e8  mov     edx, 10000h; unsigned __int64
0x1800144ed  mov     [rsi+0B38h], rcx
0x1800144f4  movzx   eax, word ptr [rbp+94h]
0x1800144fb  lea     rcx, [rcx+rax*2]
0x1800144ff  add     rcx, 4
0x180014503  mov     [rsi+0B40h], rcx
0x18001450a  mov     rcx, rdi; this
0x18001450d  call    ?malloc@LibRaw@@IEAAPEAX_K@Z; LibRaw::malloc(unsigned __int64)
0x180014512  mov     [rsi+18h], rax
0x180014516  mov     rcx, rsi
0x180014519  xor     eax, eax
0x18001451b  mov     [rsi+8], rbx
0x18001451f  mov     [rsi], rax
0x180014522  mov     [rsi+14h], eax
0x180014525  call    fuji_fill_buffer
0x18001452a  cmp     dword ptr [rdi+5D290h], 0
0x180014531  mov     r8d, 3
0x180014537  jz      short loc_180014595
0x180014539  mov     ecx, [rbp+0Ch]
0x18001453c  lea     r9, [rsi+34h]
0x180014540  add     ecx, 20h ; ' '
0x180014543  sar     ecx, 6
0x180014546  cmp     ecx, r14d
0x180014549  cmovl   ecx, r14d
0x18001454d  nop     dword ptr [rax]
0x180014550  mov     rax, r9
0x180014553  mov     edx, 29h ; ')'
0x180014558  nop     dword ptr [rax+rax+00000000h]
0x180014560  mov     [rax-4], ecx
0x180014563  mov     dword ptr [rax], 1
0x180014569  mov     [rax+53Ch], ecx
0x18001456f  mov     dword ptr [rax+540h], 1
0x180014579  lea     rax, [rax+8]
0x18001457d  sub     rdx, 1
0x180014581  jnz     short loc_180014560
0x180014583  add     r9, 1C0h
0x18001458a  sub     r8, 1
0x18001458e  jnz     short loc_180014550
0x180014590  jmp     loc_180014674
0x180014595  lea     r9, [rsi+17Ch]
0x18001459c  mov     r11, r8
0x18001459f  lea     r10, [rbp+2Ch]
0x1800145a3  nop     dword ptr [rax+00h]
0x1800145a7  nop     word ptr [rax+rax+00000000h]
0x1800145b0  mov     ecx, [r10]
0x1800145b3  mov     rax, r9
0x1800145b6  add     ecx, 20h ; ' '
0x1800145b9  mov     rdx, r8
0x1800145bc  sar     ecx, 6
0x1800145bf  cmp     ecx, r14d
0x1800145c2  cmovl   ecx, r14d
0x1800145c6  nop     word ptr [rax+rax+00000000h]
0x1800145d0  mov     [rax-4], ecx
0x1800145d3  mov     dword ptr [rax], 1
0x1800145d9  mov     [rax+53Ch], ecx
0x1800145df  mov     dword ptr [rax+540h], 1
0x1800145e9  mov     [rax+4], ecx
0x1800145ec  mov     dword ptr [rax+8], 1
0x1800145f3  mov     [rax+544h], ecx
0x1800145f9  mov     dword ptr [rax+548h], 1
0x180014603  mov     [rax+0Ch], ecx
0x180014606  mov     dword ptr [rax+10h], 1
0x18001460d  mov     [rax+54Ch], ecx
0x180014613  mov     dword ptr [rax+550h], 1
0x18001461d  mov     [rax+14h], ecx
0x180014620  mov     dword ptr [rax+18h], 1
0x180014627  mov     [rax+554h], ecx
0x18001462d  mov     dword ptr [rax+558h], 1
0x180014637  mov     [rax+1Ch], ecx
0x18001463a  mov     dword ptr [rax+20h], 1
0x180014641  mov     [rax+55Ch], ecx
0x180014647  mov     dword ptr [rax+560h], 1
0x180014651  lea     rax, [rax+1C0h]
0x180014658  sub     rdx, 1
0x18001465c  jnz     loc_1800145D0
0x180014662  add     r10, 20h ; ' '
0x180014666  add     r9, 28h ; '('
0x18001466a  sub     r11, 1
0x18001466e  jnz     loc_1800145B0
0x180014674  mov     rbx, [rsp+28h+arg_0]
0x180014679  mov     rbp, [rsp+28h+arg_8]
0x18001467e  mov     rsi, [rsp+28h+arg_10]
0x180014683  mov     rdi, [rsp+28h+arg_18]
0x180014688  add     rsp, 20h
0x18001468c  pop     r14
0x18001468e  retn
```
