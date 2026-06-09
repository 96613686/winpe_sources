# Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<uchar *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ComputeEllipticPaper(void)

- ea: `0x1800680d0`
- end: `0x180068358`
- name: `?ComputeEllipticPaper@?$SlowLocation@V?$CoordinatedArea@V?$HighDescription@PEAE@Data@@$02$0A@@IntegratedSelection@Binary@@V?$MixedResponse@$02$0A@$07$0A@@23@@IntegratedSelection@Binary@@QEAAXXZ`
- size: `648`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006a170`
- `0x18006ab70`
- `0x18006ad80`
- `0x18006af90`
- `0x18006b1a0`
- `0x18006b3d0`
- `0x18006b600`
- `0x18006b810`

## callees

- `0x1800541e0`
- `0x180054440`
- `0x1800680d0`

## pseudocode

```c
__int64 __fastcall Binary::IntegratedSelection::SlowLocation<Binary::IntegratedSelection::CoordinatedArea<Data::HighDescription<unsigned char *>,3,0>,Binary::IntegratedSelection::MixedResponse<3,0,8,0>>::ComputeEllipticPaper(
        int *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  char v7; // al
  int v8; // edx
  __int64 v9; // rcx
  char v10; // al
  int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  char v16; // al
  int v17; // edx
  __int64 v18; // rcx
  char v19; // al
  char v20; // dl
  int v21; // r8d
  char v22; // r12
  int v23; // r15d
  int v24; // r14d
  bool v25; // zf
  int v26; // r14d
  int v27; // ecx
  int v28; // ebx
  __int64 result; // rax
  int v30; // ebx
  int v31; // [rsp+30h] [rbp-30h] BYREF
  char v32; // [rsp+34h] [rbp-2Ch]
  int v33; // [rsp+38h] [rbp-28h] BYREF
  char v34; // [rsp+3Ch] [rbp-24h]
  int v35; // [rsp+40h] [rbp-20h] BYREF
  char v36; // [rsp+44h] [rbp-1Ch]
  int v37; // [rsp+48h] [rbp-18h] BYREF
  char v38; // [rsp+4Ch] [rbp-14h]
  int v39; // [rsp+50h] [rbp-10h] BYREF
  char v40; // [rsp+54h] [rbp-Ch]
  int v41; // [rsp+58h] [rbp-8h] BYREF
  char v42; // [rsp+5Ch] [rbp-4h]

  Binary::Definition::GenerateAsyncServer((unsigned int)&v33, a1[12], a1[13], 0, *a1);
  v2 = v33;
  v3 = a1[12];
  v4 = v3 * v33;
  if ( (unsigned __int64)(v4 + 0x80000000LL) > 0xFFFFFFFF
    || (v5 = 2LL * (int)v4, (unsigned __int64)(v5 + 0x80000000LL) > 0xFFFFFFFF)
    || (v6 = v3 + (int)v5, (unsigned __int64)(v6 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    LODWORD(v6) = 0;
    v7 = 0;
  }
  else
  {
    v7 = 1;
  }
  v37 = v6;
  v8 = 0;
  v9 = 2LL * a1[13];
  v38 = v7;
  if ( (unsigned __int64)(v9 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v10 = 0;
  }
  else
  {
    v8 = v9;
    v10 = 1;
  }
  v35 = v8;
  v36 = v10;
  Data::FillClearSkill(&v39, &v37, &v35);
  Binary::Definition::GenerateAsyncServer((unsigned int)&v41, a1[10], a1[11], 0, a1[1]);
  v11 = v41;
  v12 = a1[10];
  v13 = v12 * v41;
  if ( (unsigned __int64)(v13 + 0x80000000LL) > 0xFFFFFFFF
    || (v14 = 2LL * (int)v13, (unsigned __int64)(v14 + 0x80000000LL) > 0xFFFFFFFF)
    || (v15 = v12 + (int)v14, (unsigned __int64)(v15 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    LODWORD(v15) = 0;
    v16 = 0;
  }
  else
  {
    v16 = 1;
  }
  v35 = v15;
  v17 = 0;
  v18 = 2LL * a1[11];
  v36 = v16;
  if ( (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v19 = 0;
  }
  else
  {
    v17 = v18;
    v19 = 1;
  }
  v37 = v17;
  v38 = v19;
  Data::FillClearSkill(&v31, &v35, &v37);
  v20 = v40;
  v21 = 0;
  if ( v40 )
  {
    if ( (unsigned __int64)(*a1 - (__int64)v39 + 0x80000000LL) > 0xFFFFFFFF )
    {
      v20 = 0;
    }
    else
    {
      v21 = *a1 - v39;
      v20 = 1;
    }
  }
  v22 = v32;
  v23 = 0;
  if ( v32 )
  {
    if ( (unsigned __int64)(a1[1] - (__int64)v31 + 0x80000000LL) > 0xFFFFFFFF )
    {
      v22 = 0;
    }
    else
    {
      v23 = a1[1] - v31;
      v22 = 1;
    }
  }
  v33 = a1[13];
  v24 = 0;
  v32 = 1;
  if ( !v20 )
    v21 = 0;
  v25 = v34 == 0;
  a1[4] = v21;
  if ( !v25 )
    v24 = v2;
  v34 = 1;
  v31 = v24;
  Data::FillClearSkill(&v39, &v31, &v33);
  if ( v40 == 1 )
  {
    v26 = v24 - a1[13] * v39;
    if ( v26 < 0 || v26 >= a1[7] )
    {
      v27 = a1[7];
      a1[5] = v26 % v27;
      if ( v26 % v27 < 0 )
        a1[5] = v26 % v27 + v27;
    }
    else
    {
      a1[5] = v26;
    }
  }
  else
  {
    a1[5] = 0;
  }
  v28 = 0;
  v41 = a1[11];
  v25 = v42 == 0;
  v42 = 1;
  if ( !v25 )
    v28 = v11;
  v34 = 1;
  v33 = v28;
  result = Data::FillClearSkill(&v31, &v33, &v41);
  if ( v32 == 1 )
  {
    result = (unsigned int)(a1[11] * v31);
    v30 = v28 - result;
  }
  else
  {
    v30 = 0;
  }
  a1[9] = v30;
  if ( !v22 )
    v23 = 0;
  a1[8] = v23;
  return result;
}

```

## disassembly

```asm
0x1800680d0  mov     [rsp-28h+arg_8], rbx
0x1800680d5  mov     [rsp-28h+arg_10], rsi
0x1800680da  mov     [rsp-28h+arg_18], rdi
0x1800680df  push    rbp
0x1800680e0  push    r12
0x1800680e2  push    r13
0x1800680e4  push    r14
0x1800680e6  push    r15
0x1800680e8  mov     rbp, rsp
0x1800680eb  sub     rsp, 60h
0x1800680ef  mov     eax, [rcx]
0x1800680f1  mov     rsi, rcx
0x1800680f4  mov     r8d, [rcx+34h]
0x1800680f8  xor     r9d, r9d
0x1800680fb  mov     edx, [rcx+30h]
0x1800680fe  lea     rcx, [rbp+var_28]
0x180068102  mov     [rsp+60h+var_40], eax
0x180068106  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x18006810b  mov     rbx, [rbp+var_28]
0x18006810f  mov     r14d, 80000000h
0x180068115  movsxd  rdx, dword ptr [rsi+30h]
0x180068119  mov     r15d, 0FFFFFFFFh
0x18006811f  movsxd  rcx, ebx
0x180068122  xor     r13d, r13d
0x180068125  imul    rcx, rdx
0x180068129  lea     rax, [rcx+r14]
0x18006812d  cmp     rax, r15
0x180068130  ja      short loc_180068154
0x180068132  movsxd  rcx, ecx
0x180068135  add     rcx, rcx
0x180068138  lea     rax, [rcx+r14]
0x18006813c  cmp     rax, r15
0x18006813f  ja      short loc_180068154
0x180068141  movsxd  rcx, ecx
0x180068144  add     rcx, rdx
0x180068147  lea     rax, [rcx+r14]
0x18006814b  cmp     rax, r15
0x18006814e  ja      short loc_180068154
0x180068150  mov     al, 1
0x180068152  jmp     short loc_180068159
0x180068154  mov     ecx, r13d
0x180068157  xor     al, al
0x180068159  mov     [rbp+var_18], ecx
0x18006815c  mov     edx, r13d
0x18006815f  movsxd  rcx, dword ptr [rsi+34h]
0x180068163  add     rcx, rcx
0x180068166  mov     [rbp+var_14], al
0x180068169  lea     rax, [rcx+r14]
0x18006816d  cmp     rax, r15
0x180068170  ja      short loc_180068178
0x180068172  mov     edx, ecx
0x180068174  mov     al, 1
0x180068176  jmp     short loc_18006817A
0x180068178  xor     al, al
0x18006817a  mov     [rbp+var_20], edx
0x18006817d  lea     r8, [rbp+var_20]
0x180068181  lea     rdx, [rbp+var_18]
0x180068185  mov     [rbp+var_1C], al
0x180068188  lea     rcx, [rbp+var_10]
0x18006818c  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180068191  mov     eax, [rsi+4]
0x180068194  lea     rcx, [rbp+var_8]
0x180068198  mov     r8d, [rsi+2Ch]
0x18006819c  xor     r9d, r9d
0x18006819f  mov     edx, [rsi+28h]
0x1800681a2  mov     [rsp+60h+var_40], eax
0x1800681a6  call    ?GenerateAsyncServer@Definition@Binary@@YA?AV?$NullDefinition@H@Data@@HHHH@Z; Binary::Definition::GenerateAsyncServer(int,int,int,int)
0x1800681ab  mov     rdi, [rbp+var_8]
0x1800681af  movsxd  rdx, dword ptr [rsi+28h]
0x1800681b3  movsxd  rcx, edi
0x1800681b6  imul    rcx, rdx
0x1800681ba  lea     rax, [rcx+r14]
0x1800681be  cmp     rax, r15
0x1800681c1  ja      short loc_1800681E5
0x1800681c3  movsxd  rcx, ecx
0x1800681c6  add     rcx, rcx
0x1800681c9  lea     rax, [rcx+r14]
0x1800681cd  cmp     rax, r15
0x1800681d0  ja      short loc_1800681E5
0x1800681d2  movsxd  rcx, ecx
0x1800681d5  add     rcx, rdx
0x1800681d8  lea     rax, [rcx+r14]
0x1800681dc  cmp     rax, r15
0x1800681df  ja      short loc_1800681E5
0x1800681e1  mov     al, 1
0x1800681e3  jmp     short loc_1800681EA
0x1800681e5  mov     ecx, r13d
0x1800681e8  xor     al, al
0x1800681ea  mov     [rbp+var_20], ecx
0x1800681ed  mov     edx, r13d
0x1800681f0  movsxd  rcx, dword ptr [rsi+2Ch]
0x1800681f4  add     rcx, rcx
0x1800681f7  mov     [rbp+var_1C], al
0x1800681fa  lea     rax, [rcx+r14]
0x1800681fe  cmp     rax, r15
0x180068201  ja      short loc_180068209
0x180068203  mov     edx, ecx
0x180068205  mov     al, 1
0x180068207  jmp     short loc_18006820B
0x180068209  xor     al, al
0x18006820b  mov     [rbp+var_18], edx
0x18006820e  lea     r8, [rbp+var_18]
0x180068212  lea     rdx, [rbp+var_20]
0x180068216  mov     [rbp+var_14], al
0x180068219  lea     rcx, [rbp+var_30]
0x18006821d  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180068222  movzx   edx, [rbp+var_C]
0x180068226  mov     r8d, r13d
0x180068229  test    dl, dl
0x18006822b  jz      short loc_180068249
0x18006822d  movsxd  rax, [rbp+var_10]
0x180068231  movsxd  rcx, dword ptr [rsi]
0x180068234  sub     rcx, rax
0x180068237  lea     rax, [rcx+r14]
0x18006823b  cmp     rax, r15
0x18006823e  ja      short loc_180068247
0x180068240  mov     r8d, ecx
0x180068243  mov     dl, 1
0x180068245  jmp     short loc_180068249
0x180068247  xor     dl, dl
0x180068249  movzx   r12d, [rbp+var_2C]
0x18006824e  mov     r15d, r13d
0x180068251  test    r12b, r12b
0x180068254  jz      short loc_18006827B
0x180068256  movsxd  rax, [rbp+var_30]
0x18006825a  mov     r9d, 0FFFFFFFFh
0x180068260  movsxd  rcx, dword ptr [rsi+4]
0x180068264  sub     rcx, rax
0x180068267  lea     rax, [rcx+r14]
0x18006826b  cmp     rax, r9
0x18006826e  ja      short loc_180068278
0x180068270  mov     r15d, ecx
0x180068273  mov     r12b, 1
0x180068276  jmp     short loc_18006827B
0x180068278  xor     r12b, r12b
0x18006827b  mov     eax, [rsi+34h]
0x18006827e  lea     rcx, [rbp+var_10]
0x180068282  test    dl, dl
0x180068284  mov     dword ptr [rbp+var_28], eax
0x180068287  mov     r14d, r13d
0x18006828a  mov     [rbp+var_2C], 1
0x18006828e  cmovz   r8d, r13d
0x180068292  lea     rdx, [rbp+var_30]
0x180068296  cmp     byte ptr [rbp+var_28+4], r13b
0x18006829a  mov     [rsi+10h], r8d
0x18006829e  lea     r8, [rbp+var_28]
0x1800682a2  cmovnz  r14d, ebx
0x1800682a6  mov     byte ptr [rbp+var_28+4], 1
0x1800682aa  mov     [rbp+var_30], r14d
0x1800682ae  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x1800682b3  cmp     [rbp+var_C], 1
0x1800682b7  jnz     short loc_1800682E9
0x1800682b9  mov     eax, [rbp+var_10]
0x1800682bc  imul    eax, [rsi+34h]
0x1800682c0  sub     r14d, eax
0x1800682c3  js      short loc_1800682D1
0x1800682c5  cmp     r14d, [rsi+1Ch]
0x1800682c9  jge     short loc_1800682D1
0x1800682cb  mov     [rsi+14h], r14d
0x1800682cf  jmp     short loc_1800682ED
0x1800682d1  mov     ecx, [rsi+1Ch]
0x1800682d4  mov     eax, r14d
0x1800682d7  cdq
0x1800682d8  idiv    ecx
0x1800682da  mov     [rsi+14h], edx
0x1800682dd  test    edx, edx
0x1800682df  jns     short loc_1800682ED
0x1800682e1  lea     eax, [rdx+rcx]
0x1800682e4  mov     [rsi+14h], eax
0x1800682e7  jmp     short loc_1800682ED
0x1800682e9  mov     [rsi+14h], r13d
0x1800682ed  mov     eax, [rsi+2Ch]
0x1800682f0  lea     r8, [rbp+var_8]
0x1800682f4  mov     ebx, r13d
0x1800682f7  mov     dword ptr [rbp+var_8], eax
0x1800682fa  cmp     byte ptr [rbp+var_8+4], bl
0x1800682fd  lea     rdx, [rbp+var_28]
0x180068301  lea     rcx, [rbp+var_30]
0x180068305  mov     byte ptr [rbp+var_8+4], 1
0x180068309  cmovnz  ebx, edi
0x18006830c  mov     byte ptr [rbp+var_28+4], 1
0x180068310  mov     dword ptr [rbp+var_28], ebx
0x180068313  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x180068318  cmp     [rbp+var_2C], 1
0x18006831c  jnz     short loc_180068329
0x18006831e  mov     eax, [rbp+var_30]
0x180068321  imul    eax, [rsi+2Ch]
0x180068325  sub     ebx, eax
0x180068327  jmp     short loc_18006832C
0x180068329  mov     ebx, r13d
0x18006832c  mov     [rsi+24h], ebx
0x18006832f  lea     r11, [rsp+60h+var_s0]
0x180068334  mov     rbx, [r11+38h]
0x180068338  test    r12b, r12b
0x18006833b  mov     rdi, [r11+48h]
0x18006833f  cmovz   r15d, r13d
0x180068343  mov     [rsi+20h], r15d
0x180068347  mov     rsi, [r11+40h]
0x18006834b  mov     rsp, r11
0x18006834e  pop     r15
0x180068350  pop     r14
0x180068352  pop     r13
0x180068354  pop     r12
0x180068356  pop     rbp
0x180068357  retn
```
