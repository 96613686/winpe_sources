# clt_compute_allocation

- ea: `0x18000b990`
- end: `0x18000bf3e`
- name: `clt_compute_allocation`
- size: `1454`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005aa0`

## callees

- `0x18000b990`
- `0x18000bf50`
- `0x18001afd0`

## pseudocode

```c
__int64 __fastcall clt_compute_allocation(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        int a14,
        int a15,
        __int64 a16,
        int a17,
        int a18,
        int a19)
{
  int v19; // r9d
  __int64 v20; // r10
  int v21; // r8d
  int v22; // ebx
  __int64 v23; // r15
  int v24; // eax
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // r11d
  int v28; // r8d
  int v29; // r11d
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rax
  void *v32; // rsp
  __int64 v33; // rax
  void *v34; // rsp
  __int64 v35; // rax
  void *v36; // rsp
  __int64 v37; // rax
  int *v38; // r8
  void *v39; // rsp
  int v40; // edi
  int v41; // r9d
  __int64 v42; // r10
  int v43; // eax
  int v44; // r8d
  int v45; // r12d
  int v46; // ecx
  int v47; // eax
  int v48; // r8d
  int v49; // esi
  __int64 v50; // r13
  int v51; // r11d
  __int64 v52; // r14
  int v53; // edx
  __int64 v54; // rax
  int v55; // eax
  int v56; // edx
  int v57; // eax
  int v58; // esi
  int v59; // r10d
  int v60; // r12d
  int *v61; // r13
  int v62; // r14d
  __int64 v63; // r9
  __int64 v64; // rax
  __int64 v65; // rdi
  __int64 v66; // r8
  int v67; // r11d
  __int64 v68; // r9
  int v69; // r11d
  int v70; // edx
  int v71; // r8d
  int v72; // eax
  int v73; // ecx
  int v74; // r8d
  int v75; // ecx
  int v76; // eax
  int v78; // [rsp+C0h] [rbp+0h] BYREF
  int v79; // [rsp+C4h] [rbp+4h]
  int v80; // [rsp+C8h] [rbp+8h]
  int v81; // [rsp+CCh] [rbp+Ch]
  int v82; // [rsp+D0h] [rbp+10h]
  int v83; // [rsp+D4h] [rbp+14h]
  int v84; // [rsp+D8h] [rbp+18h]
  int *v85; // [rsp+E0h] [rbp+20h]
  int *v86; // [rsp+E8h] [rbp+28h]
  int *v87; // [rsp+F0h] [rbp+30h]
  int *v88; // [rsp+F8h] [rbp+38h]
  int v93; // [rsp+190h] [rbp+D0h]
  int v94; // [rsp+1B8h] [rbp+F8h]

  v19 = a3;
  v20 = *(int *)(a1 + 8);
  v21 = 0;
  v22 = a14;
  v23 = a2;
  if ( a9 > 0 )
    v21 = a9;
  v78 = *(_DWORD *)(a1 + 8);
  v24 = 0;
  v81 = a2;
  v82 = 0;
  v25 = a1;
  v79 = 0;
  if ( v21 >= 8 )
    v24 = 8;
  v26 = v21 - v24;
  v84 = v24;
  v93 = v26;
  if ( a14 == 2 )
  {
    v27 = byte_18002D660[v19 - (int)v23];
    v79 = v27;
    if ( v27 <= v26 )
    {
      v28 = v26 - v27;
      v29 = 0;
      if ( v28 >= 8 )
        v29 = 8;
      v82 = v29;
      v93 = v28 - v29;
    }
    else
    {
      v79 = 0;
    }
  }
  v30 = 4 * v20;
  v31 = 4 * v20 + 15;
  if ( v31 <= 4 * v20 )
    v31 = 0xFFFFFFFFFFFFFF0LL;
  v32 = alloca(v31 & 0xFFFFFFFFFFFFFFF0uLL);
  v88 = &v78;
  v33 = v30 + 15;
  if ( v30 + 15 < v30 )
    v33 = 0xFFFFFFFFFFFFFF0LL;
  v34 = alloca(v33 & 0xFFFFFFFFFFFFFFF0uLL);
  v87 = &v78;
  v35 = v30 + 15;
  if ( v30 + 15 < v30 )
    v35 = 0xFFFFFFFFFFFFFF0LL;
  v36 = alloca(v35 & 0xFFFFFFFFFFFFFFF0uLL);
  v37 = v30 + 15;
  v38 = &v78;
  v85 = &v78;
  if ( v30 + 15 < v30 )
    v37 = 0xFFFFFFFFFFFFFF0LL;
  v39 = alloca(v37 & 0xFFFFFFFFFFFFFFF0uLL);
  v86 = &v78;
  if ( (int)v23 < v19 )
  {
    v40 = 8 * a14;
    v41 = v23;
    v42 = v23;
    do
    {
      v43 = 8 * a14;
      if ( v40 <= (8
                 * ((3
                   * (*(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42 + 2) - *(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42))) << a15)) >> 4 )
        v43 = (8
             * ((3 * (*(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42 + 2) - *(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42))) << a15)) >> 4;
      v38[v42] = v43;
      v44 = (a14
           * (a6 - a15 - 5)
           * (a3 - v41 - 1)
           * ((*(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42 + 2) - *(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42)) << (a15 + 3))) >> 6;
      *(&v78 + v42) = v44;
      if ( (*(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42 + 2) - *(__int16 *)(*(_QWORD *)(a1 + 32) + 2 * v42)) << a15 == 1 )
        *(&v78 + v42) = v44 - v40;
      v38 = v85;
      ++v41;
      ++v42;
    }
    while ( v41 < a3 );
    v22 = a14;
    LODWORD(v23) = a2;
    v19 = a3;
    v25 = a1;
  }
  v45 = 1;
  v46 = v93;
  v47 = *(_DWORD *)(v25 + 52) - 1;
  v94 = v47;
  v80 = 1;
  do
  {
    v48 = 0;
    v49 = (v47 + v45) >> 1;
    v83 = v49;
    if ( v19 > (int)v23 )
    {
      v50 = *(_QWORD *)(v25 + 56);
      v51 = 0;
      v52 = *(_QWORD *)(v25 + 32);
      do
      {
        v53 = v19;
        v54 = v19--;
        v55 = (v22
             * *(unsigned __int8 *)(v53 + v78 * v49 - 1 + v50)
             * (*(__int16 *)(v52 + 2 * v54) - *(__int16 *)(v52 + 2LL * v19))) << a15 >> 2;
        if ( v55 > 0 )
        {
          v55 += v86[v19];
          if ( v55 < 0 )
            v55 = 0;
        }
        v56 = v55 + *(_DWORD *)(a4 + 4LL * v19);
        if ( v56 >= v85[v19] || v51 )
        {
          v51 = 1;
          v57 = *(_DWORD *)(a5 + 4LL * v19);
          if ( v56 < v57 )
            v57 = v56;
          v48 += v57;
        }
        else if ( v56 >= 8 * v22 )
        {
          v48 += 8 * v22;
        }
      }
      while ( v19 > (int)v23 );
      v49 = v83;
      v45 = v80;
      v47 = v94;
      v19 = a3;
      v25 = a1;
      v46 = v93;
    }
    if ( v48 <= v46 )
    {
      v45 = v49 + 1;
      v80 = v49 + 1;
    }
    else
    {
      v47 = v49 - 1;
      v94 = v49 - 1;
    }
  }
  while ( v45 <= v47 );
  v58 = v45;
  v59 = v23;
  v60 = v45 - 1;
  if ( (int)v23 >= v19 )
  {
    v74 = v23;
  }
  else
  {
    v61 = v86;
    v62 = v78 * v60;
    v63 = (int)v23;
    while ( 1 )
    {
      v64 = *(_QWORD *)(v25 + 32);
      v65 = v63 + 1;
      v66 = *(_QWORD *)(v25 + 56);
      v67 = *(__int16 *)(v64 + 2 * (v63 + 1));
      LODWORD(v64) = *(__int16 *)(v64 + 2 * v63);
      v68 = v63;
      v69 = v67 - v64;
      v70 = (v22 * v69 * *(unsigned __int8 *)(v62 + v59 + v66)) << a15 >> 2;
      if ( v58 < *(_DWORD *)(a1 + 52) )
        v71 = (v22 * v69 * *(unsigned __int8 *)(v59 + v78 * v58 + v66)) << a15 >> 2;
      else
        v71 = *(_DWORD *)(v68 * 4 + a5);
      if ( v70 > 0 )
      {
        v70 += v61[v68];
        if ( v70 < 0 )
          v70 = 0;
      }
      if ( v71 > 0 )
      {
        v71 += v61[v68];
        if ( v71 < 0 )
          v71 = 0;
      }
      if ( v60 > 0 )
        v70 += *(_DWORD *)(v68 * 4 + a4);
      v72 = *(_DWORD *)(v68 * 4 + a4);
      v73 = v72 + v71;
      v74 = v81;
      if ( v72 > 0 )
        v74 = v59;
      v75 = v73 - v70;
      v81 = v74;
      v88[v68] = v70;
      v76 = 0;
      if ( v75 >= 0 )
        v76 = v75;
      ++v59;
      v87[v68] = v76;
      v63 = v65;
      if ( v59 >= a3 )
        break;
      v25 = a1;
    }
    LODWORD(v23) = a2;
  }
  return interp_bits2pulses(
           a1,
           v23,
           a3,
           v74,
           (__int64)v88,
           (__int64)v87,
           (__int64)v85,
           a5,
           v93,
           a10,
           v84,
           a7,
           v79,
           a8,
           v82,
           a11,
           a12,
           a13,
           v22,
           a15,
           a16,
           a17,
           a18,
           a19);
}

```

## disassembly

```asm
0x18000b990  mov     [rsp-8+arg_18], r9
0x18000b995  mov     [rsp-8+arg_10], r8d
0x18000b99a  mov     [rsp-8+arg_8], edx
0x18000b99e  mov     [rsp-8+arg_0], rcx
0x18000b9a3  push    rbp
0x18000b9a4  push    rbx
0x18000b9a5  push    rsi
0x18000b9a6  push    rdi
0x18000b9a7  push    r12
0x18000b9a9  push    r13
0x18000b9ab  push    r14
0x18000b9ad  push    r15
0x18000b9af  sub     rsp, 108h
0x18000b9b6  lea     rbp, [rsp+0C0h]
0x18000b9be  mov     eax, [rbp+80h+arg_40]
0x18000b9c4  mov     r9d, r8d
0x18000b9c7  movsxd  r10, dword ptr [rcx+8]
0x18000b9cb  xor     r8d, r8d
0x18000b9ce  mov     ebx, [rbp+80h+arg_68]
0x18000b9d4  test    eax, eax
0x18000b9d6  mov     edi, 8
0x18000b9db  movsxd  r15, edx
0x18000b9de  cmovg   r8d, eax
0x18000b9e2  mov     [rbp+80h+var_80], r10d
0x18000b9e6  xor     eax, eax
0x18000b9e8  mov     [rbp+80h+var_74], r15d
0x18000b9ec  cmp     r8d, edi
0x18000b9ef  mov     [rbp+80h+var_70], 0
0x18000b9f6  mov     rdx, rcx
0x18000b9f9  mov     [rbp+80h+var_7C], 0
0x18000ba00  cmovge  eax, edi
0x18000ba03  sub     r8d, eax
0x18000ba06  mov     [rbp+80h+var_68], eax
0x18000ba09  mov     [rbp+80h+arg_40], r8d
0x18000ba10  cmp     ebx, 2
0x18000ba13  jnz     short loc_18000BA57
0x18000ba15  mov     eax, r9d
0x18000ba18  sub     eax, r15d
0x18000ba1b  movsxd  rcx, eax
0x18000ba1e  lea     rax, byte_18002D660
0x18000ba25  movzx   r11d, byte ptr [rcx+rax]
0x18000ba2a  mov     [rbp+80h+var_7C], r11d
0x18000ba2e  cmp     r11d, r8d
0x18000ba31  jle     short loc_18000BA3C
0x18000ba33  mov     [rbp+80h+var_7C], 0
0x18000ba3a  jmp     short loc_18000BA57
0x18000ba3c  sub     r8d, r11d
0x18000ba3f  xor     r11d, r11d
0x18000ba42  cmp     r8d, edi
0x18000ba45  cmovge  r11d, edi
0x18000ba49  sub     r8d, r11d
0x18000ba4c  mov     [rbp+80h+var_70], r11d
0x18000ba50  mov     [rbp+80h+arg_40], r8d
0x18000ba57  mov     rcx, r10
0x18000ba5a  mov     rdi, 0FFFFFFFFFFFFFF0h
0x18000ba64  shl     rcx, 2
0x18000ba68  lea     rax, [rcx+0Fh]
0x18000ba6c  cmp     rax, rcx
0x18000ba6f  ja      short loc_18000BA74
0x18000ba71  mov     rax, rdi
0x18000ba74  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000ba78  call    _alloca_probe
0x18000ba7d  sub     rsp, rax
0x18000ba80  lea     rax, [rsp+140h+var_80]
0x18000ba88  mov     [rbp+80h+var_48], rax
0x18000ba8c  lea     rax, [rcx+0Fh]
0x18000ba90  cmp     rax, rcx
0x18000ba93  ja      short loc_18000BA98
0x18000ba95  mov     rax, rdi
0x18000ba98  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000ba9c  call    _alloca_probe
0x18000baa1  sub     rsp, rax
0x18000baa4  lea     rax, [rsp+140h+var_80]
0x18000baac  mov     [rbp+80h+var_50], rax
0x18000bab0  lea     rax, [rcx+0Fh]
0x18000bab4  cmp     rax, rcx
0x18000bab7  ja      short loc_18000BABC
0x18000bab9  mov     rax, rdi
0x18000babc  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000bac0  call    _alloca_probe
0x18000bac5  sub     rsp, rax
0x18000bac8  lea     rax, [rcx+0Fh]
0x18000bacc  lea     r8, [rsp+140h+var_80]
0x18000bad4  mov     [rbp+80h+var_60], r8
0x18000bad8  cmp     rax, rcx
0x18000badb  ja      short loc_18000BAE0
0x18000badd  mov     rax, rdi
0x18000bae0  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000bae4  call    _alloca_probe
0x18000bae9  sub     rsp, rax
0x18000baec  lea     r13, [rsp+140h+var_80]
0x18000baf4  mov     [rbp+80h+var_58], r13
0x18000baf8  cmp     r15d, r9d
0x18000bafb  jge     loc_18000BBED
0x18000bb01  mov     r11d, [rbp+80h+arg_28]
0x18000bb08  lea     edi, ds:0[rbx*8]
0x18000bb0f  mov     r12d, [rbp+80h+arg_70]
0x18000bb16  mov     r9d, r15d
0x18000bb19  sub     r11d, r12d
0x18000bb1c  mov     r10, r15
0x18000bb1f  mov     r15, [rbp+80h+arg_0]
0x18000bb26  sub     r11d, 5
0x18000bb2a  imul    r11d, ebx
0x18000bb2e  mov     ebx, [rbp+80h+arg_10]
0x18000bb34  nop     dword ptr [rax+00h]
0x18000bb38  nop     dword ptr [rax+rax+00000000h]
0x18000bb40  mov     rax, [r15+20h]
0x18000bb44  movsx   ecx, word ptr [rax+r10*2+2]
0x18000bb4a  movsx   eax, word ptr [rax+r10*2]
0x18000bb4f  sub     ecx, eax
0x18000bb51  mov     eax, edi
0x18000bb53  lea     edx, [rcx+rcx*2]
0x18000bb56  mov     ecx, r12d
0x18000bb59  shl     edx, cl
0x18000bb5b  lea     ecx, [r12+3]
0x18000bb60  shl     edx, 3
0x18000bb63  sar     edx, 4
0x18000bb66  cmp     edi, edx
0x18000bb68  cmovle  eax, edx
0x18000bb6b  mov     [r8+r10*4], eax
0x18000bb6f  mov     rax, [r15+20h]
0x18000bb73  movsx   r8d, word ptr [rax+r10*2+2]
0x18000bb79  movsx   eax, word ptr [rax+r10*2]
0x18000bb7e  sub     r8d, eax
0x18000bb81  mov     eax, ebx
0x18000bb83  shl     r8d, cl
0x18000bb86  sub     eax, r9d
0x18000bb89  dec     eax
0x18000bb8b  mov     ecx, r12d
0x18000bb8e  imul    r8d, eax
0x18000bb92  imul    r8d, r11d
0x18000bb96  sar     r8d, 6
0x18000bb9a  mov     [r13+r10*4+0], r8d
0x18000bb9f  mov     rax, [r15+20h]
0x18000bba3  movsx   edx, word ptr [rax+r10*2+2]
0x18000bba9  movsx   eax, word ptr [rax+r10*2]
0x18000bbae  sub     edx, eax
0x18000bbb0  shl     edx, cl
0x18000bbb2  cmp     edx, 1
0x18000bbb5  jnz     short loc_18000BBBF
0x18000bbb7  sub     r8d, edi
0x18000bbba  mov     [r13+r10*4+0], r8d
0x18000bbbf  mov     r8, [rbp+80h+var_60]
0x18000bbc3  inc     r9d
0x18000bbc6  inc     r10
0x18000bbc9  cmp     r9d, ebx
0x18000bbcc  jl      loc_18000BB40
0x18000bbd2  mov     ebx, [rbp+80h+arg_68]
0x18000bbd8  mov     r15d, [rbp+80h+arg_8]
0x18000bbdf  mov     r9d, [rbp+80h+arg_10]
0x18000bbe6  mov     rdx, [rbp+80h+arg_0]
0x18000bbed  mov     eax, [rdx+34h]
0x18000bbf0  mov     r12d, 1
0x18000bbf6  mov     ecx, [rbp+80h+arg_40]
0x18000bbfc  dec     eax
0x18000bbfe  mov     [rbp+80h+arg_68], eax
0x18000bc04  mov     [rbp+80h+var_78], r12d
0x18000bc08  nop     dword ptr [rax+rax+00000000h]
0x18000bc10  lea     esi, [rax+r12]
0x18000bc14  xor     r8d, r8d
0x18000bc17  sar     esi, 1
0x18000bc19  mov     [rbp+80h+var_6C], esi
0x18000bc1c  cmp     r9d, r15d
0x18000bc1f  jle     loc_18000BCF1
0x18000bc25  mov     r13, [rdx+38h]
0x18000bc29  mov     edi, esi
0x18000bc2b  imul    edi, [rbp+80h+var_80]
0x18000bc2f  xor     r11d, r11d
0x18000bc32  mov     r14, [rdx+20h]
0x18000bc36  mov     rsi, [rbp+80h+var_58]
0x18000bc3a  mov     r12d, [rbp+80h+arg_70]
0x18000bc41  dec     edi
0x18000bc43  mov     edx, r9d
0x18000bc46  movsxd  rax, r9d
0x18000bc49  dec     r9d
0x18000bc4c  movsxd  r10, r9d
0x18000bc4f  movsx   eax, word ptr [r14+rax*2]
0x18000bc54  movsx   ecx, word ptr [r14+r10*2]
0x18000bc59  sub     eax, ecx
0x18000bc5b  lea     ecx, [rdx+rdi]
0x18000bc5e  movsxd  rdx, ecx
0x18000bc61  movzx   ecx, byte ptr [rdx+r13]
0x18000bc66  imul    eax, ecx
0x18000bc69  mov     ecx, r12d
0x18000bc6c  imul    eax, ebx
0x18000bc6f  shl     eax, cl
0x18000bc71  sar     eax, 2
0x18000bc74  test    eax, eax
0x18000bc76  jle     short loc_18000BC81
0x18000bc78  xor     ecx, ecx
0x18000bc7a  add     eax, [rsi+r10*4]
0x18000bc7e  cmovs   eax, ecx
0x18000bc81  mov     rcx, [rbp+80h+arg_18]
0x18000bc88  mov     edx, [rcx+r10*4]
0x18000bc8c  add     edx, eax
0x18000bc8e  mov     rax, [rbp+80h+var_60]
0x18000bc92  cmp     edx, [rax+r10*4]
0x18000bc96  jge     short loc_18000BCAE
0x18000bc98  test    r11d, r11d
0x18000bc9b  jnz     short loc_18000BCAE
0x18000bc9d  lea     eax, ds:0[rbx*8]
0x18000bca4  cmp     edx, eax
0x18000bca6  jl      short loc_18000BCC7
0x18000bca8  lea     r8d, [r8+rbx*8]
0x18000bcac  jmp     short loc_18000BCC7
0x18000bcae  mov     rax, [rbp+80h+arg_20]
0x18000bcb5  mov     r11d, 1
0x18000bcbb  mov     eax, [rax+r10*4]
0x18000bcbf  cmp     edx, eax
0x18000bcc1  cmovl   eax, edx
0x18000bcc4  add     r8d, eax
0x18000bcc7  cmp     r9d, r15d
0x18000bcca  jg      loc_18000BC43
0x18000bcd0  mov     esi, [rbp+80h+var_6C]
0x18000bcd3  mov     r12d, [rbp+80h+var_78]
0x18000bcd7  mov     eax, [rbp+80h+arg_68]
0x18000bcdd  mov     r9d, [rbp+80h+arg_10]
0x18000bce4  mov     rdx, [rbp+80h+arg_0]
0x18000bceb  mov     ecx, [rbp+80h+arg_40]
0x18000bcf1  cmp     r8d, ecx
0x18000bcf4  jle     short loc_18000BD01
0x18000bcf6  lea     eax, [rsi-1]
0x18000bcf9  mov     [rbp+80h+arg_68], eax
0x18000bcff  jmp     short loc_18000BD09
0x18000bd01  lea     r12d, [rsi+1]
0x18000bd05  mov     [rbp+80h+var_78], r12d
0x18000bd09  cmp     r12d, eax
0x18000bd0c  jle     loc_18000BC10
0x18000bd12  mov     esi, r12d
0x18000bd15  mov     r10d, r15d
0x18000bd18  dec     r12d
0x18000bd1b  cmp     r15d, r9d
0x18000bd1e  jge     loc_18000BE33
0x18000bd24  mov     r13, [rbp+80h+var_58]
0x18000bd28  mov     r14d, r12d
0x18000bd2b  imul    r14d, [rbp+80h+var_80]
0x18000bd30  movsxd  r9, r15d
0x18000bd33  mov     r15d, [rbp+80h+arg_70]
0x18000bd3a  jmp     short loc_18000BD47
0x18000bd40  mov     rdx, [rbp+80h+arg_0]
0x18000bd47  mov     rax, [rdx+20h]
0x18000bd4b  lea     rdi, [r9+1]
0x18000bd4f  mov     r8, [rdx+38h]
0x18000bd53  movsx   r11d, word ptr [rax+rdi*2]
0x18000bd58  movsx   eax, word ptr [rax+r9*2]
0x18000bd5d  lea     r9, ds:0[r9*4]
0x18000bd65  sub     r11d, eax
0x18000bd68  lea     eax, [r14+r10]
0x18000bd6c  movsxd  rcx, eax
0x18000bd6f  mov     rax, [rbp+80h+arg_0]
0x18000bd76  movzx   edx, byte ptr [rcx+r8]
0x18000bd7b  mov     ecx, r15d
0x18000bd7e  imul    edx, r11d
0x18000bd82  imul    edx, ebx
0x18000bd85  shl     edx, cl
0x18000bd87  sar     edx, 2
0x18000bd8a  cmp     esi, [rax+34h]
0x18000bd8d  jl      short loc_18000BD9C
0x18000bd8f  mov     rax, [rbp+80h+arg_20]
0x18000bd96  mov     r8d, [r9+rax]
0x18000bd9a  jmp     short loc_18000BDBB
0x18000bd9c  mov     eax, esi
0x18000bd9e  imul    eax, [rbp+80h+var_80]
0x18000bda2  add     eax, r10d
0x18000bda5  cdqe
0x18000bda7  movzx   r8d, byte ptr [rax+r8]
0x18000bdac  imul    r8d, r11d
0x18000bdb0  imul    r8d, ebx
0x18000bdb4  shl     r8d, cl
0x18000bdb7  sar     r8d, 2
0x18000bdbb  test    edx, edx
0x18000bdbd  jle     short loc_18000BDC8
0x18000bdbf  xor     eax, eax
0x18000bdc1  add     edx, [r9+r13]
0x18000bdc5  cmovs   edx, eax
0x18000bdc8  test    r8d, r8d
0x18000bdcb  jle     short loc_18000BDD7
0x18000bdcd  xor     eax, eax
0x18000bdcf  add     r8d, [r9+r13]
0x18000bdd3  cmovs   r8d, eax
0x18000bdd7  mov     rax, [rbp+80h+arg_18]
0x18000bdde  test    r12d, r12d
0x18000bde1  jle     short loc_18000BDE7
0x18000bde3  add     edx, [r9+rax]
0x18000bde7  mov     eax, [r9+rax]
0x18000bdeb  test    eax, eax
0x18000bded  lea     ecx, [rax+r8]
0x18000bdf1  mov     rax, [rbp+80h+var_48]
0x18000bdf5  mov     r8d, [rbp+80h+var_74]
0x18000bdf9  cmovg   r8d, r10d
0x18000bdfd  sub     ecx, edx
0x18000bdff  mov     [rbp+80h+var_74], r8d
0x18000be03  mov     [r9+rax], edx
0x18000be07  mov     eax, 0
0x18000be0c  cmovns  eax, ecx
0x18000be0f  mov     rcx, [rbp+80h+var_50]
0x18000be13  inc     r10d
0x18000be16  mov     [r9+rcx], eax
0x18000be1a  mov     r9, rdi
0x18000be1d  cmp     r10d, [rbp+80h+arg_10]
  ... truncated ...
```
