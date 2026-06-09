# Binary::IntegratedSelection::ComplexService::ExtractPureStrategy(int,int)

- ea: `0x18006a250`
- end: `0x18006a4e1`
- name: `?ExtractPureStrategy@ComplexService@IntegratedSelection@Binary@@QEBAXHH@Z`
- size: `657`
- prototype: `void __fastcall(Binary::IntegratedSelection::ComplexService *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006a0f0`
- `0x18006a110`
- `0x18006a130`
- `0x18006a150`

## callees

- `0x180053e00`
- `0x180054000`
- `0x18006a250`

## pseudocode

```c
void __fastcall Binary::IntegratedSelection::ComplexService::ExtractPureStrategy(
        Binary::IntegratedSelection::ComplexService *this,
        int a2,
        int a3)
{
  int v4; // eax
  int v5; // ecx
  int v6; // ebx
  int v7; // edi
  int v8; // ebx
  int v9; // eax
  int v10; // edi
  int v11; // ecx
  int v12; // ebp
  int v13; // r14d
  int v14; // ebp
  __int64 v15; // rax
  int v16; // r10d
  __int64 v17; // r11
  int v18; // r8d
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  _WORD *v22; // rdi
  int v23; // ecx
  __int64 v24; // rax
  int v25; // r9d
  int v26; // edi
  int v27; // ecx
  int v28; // r8d
  int v29; // edx
  int v30; // eax
  int v31; // r15d
  int v32; // r15d
  int v33; // edi
  int v34; // eax
  int v35; // ebp
  int v36; // ecx
  int v37; // ebp
  int v38; // r14d
  int v39; // r14d
  __int64 v40; // rax
  int v41; // r10d
  __int64 v42; // r11
  int v43; // r8d
  __int64 v44; // rdx
  __int64 v45; // r9
  __int64 v46; // rcx
  _WORD *v47; // rdi
  int v48; // ecx
  __int64 v49; // rax
  __int64 v50; // [rsp+30h] [rbp-68h]
  __int64 v51; // [rsp+38h] [rbp-60h]
  __int128 v52; // [rsp+40h] [rbp-58h] BYREF
  int v53; // [rsp+50h] [rbp-48h]
  char v54; // [rsp+54h] [rbp-44h]
  int v55; // [rsp+58h] [rbp-40h]
  char v56; // [rsp+5Ch] [rbp-3Ch]
  _QWORD v57[4]; // [rsp+60h] [rbp-38h] BYREF
  __int64 v58; // [rsp+B8h] [rbp+20h]

  if ( a2 == 1 && a3 == 1 && *((_DWORD *)this + 14) == 1 && *((_DWORD *)this + 15) == 1 )
  {
    v4 = *((_DWORD *)this + 8);
    v5 = *(_DWORD *)this;
    v6 = v5;
    if ( v5 < v4 )
      v6 = v4;
    v7 = *((_DWORD *)this + 2) - v4;
    v8 = v6 - v4;
    v9 = *((_DWORD *)this + 9);
    v10 = v5 + v7;
    v11 = *((_DWORD *)this + 1);
    v12 = v11;
    if ( v11 < v9 )
      v12 = *((_DWORD *)this + 9);
    v13 = v11 + *((_DWORD *)this + 3) - v9;
    v14 = v12 - v9;
    v15 = Data::CompleteResolution::ClickSlowTime(*((_DWORD *)this + 11), *((_DWORD *)this + 10));
    v16 = *((_DWORD *)this + 10);
    v17 = v15;
    if ( v16 <= 0 )
      v16 = 1;
    v18 = v8 % v16 + v16;
    if ( v8 % v16 >= 0 )
      v18 = v8 % v16;
    v19 = v15 * v18;
    if ( v8 < v10 )
    {
      v20 = (unsigned int)(v10 - v8);
      do
      {
        if ( v14 < v13 )
        {
          v21 = v13 - v14;
          v22 = (_WORD *)(*((_QWORD *)this + 6) + 2 * (v19 + v14));
          while ( v21 )
          {
            *v22++ = 0;
            --v21;
          }
        }
        v23 = v18 + 1;
        v18 = 0;
        v24 = v17 + v19;
        v19 = 0;
        if ( v23 < v16 )
        {
          v18 = v23;
          v19 = v24;
        }
        --v20;
      }
      while ( v20 );
    }
  }
  else
  {
    v25 = *((_DWORD *)this + 14);
    LODWORD(v52) = *((_DWORD *)this + 3);
    LODWORD(v51) = *((_DWORD *)this + 2);
    LODWORD(v50) = *((_DWORD *)this + 1);
    LODWORD(v58) = *(_DWORD *)this;
    BYTE4(v52) = 1;
    BYTE4(v58) = 1;
    v57[0] = v58;
    BYTE4(v50) = 1;
    v57[1] = v50;
    BYTE4(v51) = 1;
    v57[2] = v51;
    v57[3] = v52;
    Binary::Definition::ExportIntegratedTopic((unsigned int)&v52, a2, a3, v25, *((_DWORD *)this + 15), (__int64)v57);
    v26 = v52;
    v27 = DWORD2(v52);
    v28 = v53;
    v29 = v55;
    if ( !BYTE4(v52) || !BYTE12(v52) || !v54 || !v56 )
    {
      v26 = *((_DWORD *)this + 8);
      v28 = 0;
      v52 = *(_OWORD *)this;
      v29 = HIDWORD(v52);
      v27 = DWORD1(v52);
    }
    v30 = *((_DWORD *)this + 8);
    v31 = v26;
    if ( v26 < v30 )
      v31 = *((_DWORD *)this + 8);
    v32 = v31 - v30;
    v33 = v28 + v26 - v30;
    v34 = *((_DWORD *)this + 9);
    v35 = v34;
    if ( v27 >= v34 )
      v35 = v27;
    v36 = *((_DWORD *)this + 11);
    v37 = v35 - v34;
    v38 = v36;
    if ( v29 <= v36 )
      v38 = v29;
    v39 = v37 + v38;
    if ( v39 > v36 )
      v39 = *((_DWORD *)this + 11);
    v40 = Data::CompleteResolution::ClickSlowTime(v36, *((_DWORD *)this + 10));
    v41 = *((_DWORD *)this + 10);
    v42 = v40;
    if ( v41 <= 0 )
      v41 = 1;
    v43 = v41 + v32 % v41;
    if ( v32 % v41 >= 0 )
      v43 = v32 % v41;
    v44 = v40 * v43;
    if ( v32 < v33 )
    {
      v45 = (unsigned int)(v33 - v32);
      do
      {
        if ( v37 < v39 )
        {
          v46 = v39 - v37;
          v47 = (_WORD *)(*((_QWORD *)this + 6) + 2 * (v44 + v37));
          while ( v46 )
          {
            *v47++ = 0;
            --v46;
          }
        }
        v48 = v43 + 1;
        v43 = 0;
        v49 = v42 + v44;
        v44 = 0;
        if ( v48 < v41 )
        {
          v43 = v48;
          v44 = v49;
        }
        --v45;
      }
      while ( v45 );
    }
  }
}

```

## disassembly

```asm
0x18006a250  mov     [rsp+arg_8], rbx
0x18006a255  mov     [rsp+arg_10], rbp
0x18006a25a  push    rsi
0x18006a25b  push    rdi
0x18006a25c  push    r14
0x18006a25e  sub     rsp, 80h
0x18006a265  mov     rsi, rcx
0x18006a268  cmp     edx, 1
0x18006a26b  jnz     loc_18006A345
0x18006a271  cmp     r8d, edx
0x18006a274  jnz     loc_18006A345
0x18006a27a  cmp     [rcx+38h], edx
0x18006a27d  jnz     loc_18006A345
0x18006a283  cmp     [rcx+3Ch], edx
0x18006a286  jnz     loc_18006A345
0x18006a28c  mov     eax, [rcx+20h]
0x18006a28f  mov     ecx, [rcx]
0x18006a291  mov     ebx, ecx
0x18006a293  mov     edi, [rsi+8]
0x18006a296  cmp     ecx, eax
0x18006a298  mov     r14d, [rsi+0Ch]
0x18006a29c  mov     edx, [rsi+28h]; int
0x18006a29f  cmovl   ebx, eax
0x18006a2a2  sub     edi, eax
0x18006a2a4  sub     ebx, eax
0x18006a2a6  mov     eax, [rsi+24h]
0x18006a2a9  add     edi, ecx
0x18006a2ab  mov     ecx, [rsi+4]
0x18006a2ae  cmp     ecx, eax
0x18006a2b0  mov     ebp, ecx
0x18006a2b2  cmovl   ebp, eax
0x18006a2b5  sub     r14d, eax
0x18006a2b8  add     r14d, ecx
0x18006a2bb  sub     ebp, eax
0x18006a2bd  mov     ecx, [rsi+2Ch]; int
0x18006a2c0  call    ?ClickSlowTime@CompleteResolution@Data@@SA_JHH@Z; Data::CompleteResolution::ClickSlowTime(int,int)
0x18006a2c5  mov     r10d, [rsi+28h]
0x18006a2c9  mov     r11, rax
0x18006a2cc  test    r10d, r10d
0x18006a2cf  mov     eax, 1
0x18006a2d4  cmovle  r10d, eax
0x18006a2d8  mov     eax, ebx
0x18006a2da  cdq
0x18006a2db  idiv    r10d
0x18006a2de  test    edx, edx
0x18006a2e0  lea     r8d, [rdx+r10]
0x18006a2e4  cmovns  r8d, edx
0x18006a2e8  movsxd  rdx, r8d
0x18006a2eb  imul    rdx, r11
0x18006a2ef  cmp     ebx, edi
0x18006a2f1  jge     loc_18006A4C9
0x18006a2f7  sub     edi, ebx
0x18006a2f9  mov     r9d, edi
0x18006a2fc  xor     ebx, ebx
0x18006a2fe  xchg    ax, ax
0x18006a300  mov     rdi, [rsi+30h]
0x18006a304  cmp     ebp, r14d
0x18006a307  jge     short loc_18006A321
0x18006a309  mov     eax, r14d
0x18006a30c  sub     eax, ebp
0x18006a30e  movsxd  rcx, eax
0x18006a311  movsxd  rax, ebp
0x18006a314  add     rax, rdx
0x18006a317  lea     rdi, [rdi+rax*2]
0x18006a31b  movzx   eax, bx
0x18006a31e  rep stosw
0x18006a321  lea     ecx, [r8+1]
0x18006a325  mov     r8d, ebx
0x18006a328  cmp     ecx, r10d
0x18006a32b  lea     rax, [r11+rdx]
0x18006a32f  mov     rdx, rbx
0x18006a332  cmovl   r8d, ecx
0x18006a336  cmovl   rdx, rax
0x18006a33a  sub     r9, 1
0x18006a33e  jnz     short loc_18006A300
0x18006a340  jmp     loc_18006A4C9
0x18006a345  mov     eax, [rcx+0Ch]
0x18006a348  mov     r9d, [rcx+38h]
0x18006a34c  mov     dword ptr [rsp+98h+var_58], eax
0x18006a350  mov     eax, [rcx+8]
0x18006a353  mov     dword ptr [rsp+98h+var_60], eax
0x18006a357  mov     eax, [rcx+4]
0x18006a35a  mov     dword ptr [rsp+98h+var_68], eax
0x18006a35e  mov     eax, [rcx]
0x18006a360  mov     dword ptr [rsp+98h+arg_18], eax
0x18006a367  mov     byte ptr [rsp+98h+var_58+4], 1
0x18006a36c  mov     byte ptr [rsp+98h+arg_18+4], 1
0x18006a374  mov     rax, [rsp+98h+arg_18]
0x18006a37c  mov     [rsp+98h+var_38], rax
0x18006a381  mov     byte ptr [rsp+98h+var_68+4], 1
0x18006a386  mov     rax, [rsp+98h+var_68]
0x18006a38b  mov     [rsp+98h+var_30], rax
0x18006a390  mov     byte ptr [rsp+98h+var_60+4], 1
0x18006a395  mov     rax, [rsp+98h+var_60]
0x18006a39a  mov     [rsp+98h+var_28], rax
0x18006a39f  mov     rax, qword ptr [rsp+98h+var_58]
0x18006a3a4  mov     [rsp+98h+var_20], rax
0x18006a3a9  lea     rax, [rsp+98h+var_38]
0x18006a3ae  mov     [rsp+98h+var_70], rax
0x18006a3b3  mov     eax, [rcx+3Ch]
0x18006a3b6  lea     rcx, [rsp+98h+var_58]
0x18006a3bb  mov     [rsp+98h+arg_0], r15
0x18006a3c3  mov     [rsp+98h+var_78], eax
0x18006a3c7  call    ?ExportIntegratedTopic@Definition@Binary@@YA?AV?$ShortTermResolution@V?$NullDefinition@H@Data@@@Data@@HHHHAEBV34@@Z; Binary::Definition::ExportIntegratedTopic(int,int,int,int,Data::ShortTermResolution<Data::NullDefinition<int>> const &)
0x18006a3cc  mov     edi, dword ptr [rsp+98h+var_58]
0x18006a3d0  xor     ebx, ebx
0x18006a3d2  mov     ecx, dword ptr [rsp+98h+var_58+8]
0x18006a3d6  mov     r8d, [rsp+98h+var_48]
0x18006a3db  mov     edx, [rsp+98h+var_40]
0x18006a3df  cmp     byte ptr [rsp+98h+var_58+4], bl
0x18006a3e3  jz      short loc_18006A3F7
0x18006a3e5  cmp     byte ptr [rsp+98h+var_58+0Ch], bl
0x18006a3e9  jz      short loc_18006A3F7
0x18006a3eb  cmp     [rsp+98h+var_44], bl
0x18006a3ef  jz      short loc_18006A3F7
0x18006a3f1  cmp     [rsp+98h+var_3C], bl
0x18006a3f5  jnz     short loc_18006A40D
0x18006a3f7  movups  xmm0, xmmword ptr [rsi]
0x18006a3fa  mov     edi, [rsi+20h]
0x18006a3fd  mov     r8d, ebx
0x18006a400  movups  [rsp+98h+var_58], xmm0
0x18006a405  mov     edx, dword ptr [rsp+98h+var_58+0Ch]
0x18006a409  mov     ecx, dword ptr [rsp+98h+var_58+4]
0x18006a40d  mov     eax, [rsi+20h]
0x18006a410  mov     r15d, edi
0x18006a413  cmp     edi, eax
0x18006a415  cmovl   r15d, eax
0x18006a419  sub     edi, eax
0x18006a41b  sub     r15d, eax
0x18006a41e  add     edi, r8d
0x18006a421  mov     eax, [rsi+24h]
0x18006a424  cmp     ecx, eax
0x18006a426  mov     ebp, eax
0x18006a428  cmovge  ebp, ecx
0x18006a42b  mov     ecx, [rsi+2Ch]; int
0x18006a42e  sub     ebp, eax
0x18006a430  mov     r14d, ecx
0x18006a433  cmp     edx, ecx
0x18006a435  cmovle  r14d, edx
0x18006a439  mov     edx, [rsi+28h]; int
0x18006a43c  add     r14d, ebp
0x18006a43f  cmp     r14d, ecx
0x18006a442  cmovg   r14d, ecx
0x18006a446  call    ?ClickSlowTime@CompleteResolution@Data@@SA_JHH@Z; Data::CompleteResolution::ClickSlowTime(int,int)
0x18006a44b  mov     r10d, [rsi+28h]
0x18006a44f  mov     r11, rax
0x18006a452  test    r10d, r10d
0x18006a455  mov     eax, 1
0x18006a45a  cmovle  r10d, eax
0x18006a45e  mov     eax, r15d
0x18006a461  cdq
0x18006a462  idiv    r10d
0x18006a465  test    edx, edx
0x18006a467  lea     r8d, [r10+rdx]
0x18006a46b  cmovns  r8d, edx
0x18006a46f  movsxd  rdx, r8d
0x18006a472  imul    rdx, r11
0x18006a476  cmp     r15d, edi
0x18006a479  jge     short loc_18006A4C1
0x18006a47b  sub     edi, r15d
0x18006a47e  mov     r9d, edi
0x18006a481  mov     rdi, [rsi+30h]
0x18006a485  cmp     ebp, r14d
0x18006a488  jge     short loc_18006A4A2
0x18006a48a  mov     eax, r14d
0x18006a48d  sub     eax, ebp
0x18006a48f  movsxd  rcx, eax
0x18006a492  movsxd  rax, ebp
0x18006a495  add     rax, rdx
0x18006a498  lea     rdi, [rdi+rax*2]
0x18006a49c  movzx   eax, bx
0x18006a49f  rep stosw
0x18006a4a2  lea     ecx, [r8+1]
0x18006a4a6  mov     r8d, ebx
0x18006a4a9  cmp     ecx, r10d
0x18006a4ac  lea     rax, [r11+rdx]
0x18006a4b0  mov     rdx, rbx
0x18006a4b3  cmovl   r8d, ecx
0x18006a4b7  cmovl   rdx, rax
0x18006a4bb  sub     r9, 1
0x18006a4bf  jnz     short loc_18006A481
0x18006a4c1  mov     r15, [rsp+98h+arg_0]
0x18006a4c9  lea     r11, [rsp+98h+var_18]
0x18006a4d1  mov     rbx, [r11+28h]
0x18006a4d5  mov     rbp, [r11+30h]
0x18006a4d9  mov     rsp, r11
0x18006a4dc  pop     r14
0x18006a4de  pop     rdi
0x18006a4df  pop     rsi
0x18006a4e0  retn
```
