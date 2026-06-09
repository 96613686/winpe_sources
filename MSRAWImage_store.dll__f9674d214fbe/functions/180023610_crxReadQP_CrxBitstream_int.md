# crxReadQP(CrxBitstream *,int)

- ea: `0x180023610`
- end: `0x180023c35`
- name: `?crxReadQP@@YAIPEAUCrxBitstream@@H@Z`
- size: `1573`
- prototype: `unsigned int __fastcall(struct CrxBitstream *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180015db0`
- `0x180022ba0`

## callees

- `0x180003e4c`
- `0x180020ab0`
- `0x180023610`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall crxReadQP(struct CrxBitstream *a1, int a2)
{
  unsigned int v2; // r8d
  unsigned int *v3; // r14
  __int64 v4; // rsi
  int v5; // r13d
  unsigned int v7; // edx
  int v8; // ebp
  unsigned int v9; // edi
  __int64 v10; // r8
  int i; // edi
  unsigned int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // r8d
  __int64 v18; // rcx
  __int64 v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rsi
  __int64 v29; // rax
  unsigned int v30; // ecx
  unsigned __int32 v31; // r15d
  unsigned int v32; // r8d
  char v33; // r15
  int v34; // edi
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rax
  unsigned int v41; // ecx
  unsigned __int32 v42; // r12d
  unsigned int v43; // eax
  unsigned __int32 v44; // r12d
  int v45; // ebp
  unsigned int v46; // r8d
  char v47; // r12
  int v48; // r13d
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r9
  int v52; // eax
  __int64 v53; // rcx
  int pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  int v56; // [rsp+78h] [rbp+10h]

  v56 = a2;
  v2 = *((_DWORD *)a1 + 16390);
  v3 = (unsigned int *)((char *)a1 + 65552);
  v4 = 0;
  pExceptionObject = 0;
  v5 = a2;
  if ( v2 )
  {
    _BitScanReverse(&v7, v2);
    v8 = v7 + *((_DWORD *)a1 + 16391) - 32;
    v9 = 31 - v7;
    *((_DWORD *)a1 + 16391) = v8;
    LODWORD(v10) = v2 << (32 - v7);
LABEL_25:
    LODWORD(v28) = v10;
  }
  else
  {
    for ( i = *((_DWORD *)a1 + 16391); ; i += 8 )
    {
      v12 = *v3;
      LODWORD(v13) = *((_DWORD *)a1 + 16389);
      if ( *v3 + 4 <= (unsigned int)v13 )
        break;
LABEL_14:
      v22 = v12 + 1;
      if ( (unsigned int)v13 < v12 + 1 )
        goto LABEL_24;
      v4 = *((unsigned __int8 *)a1 + v12);
      *v3 = v22;
      if ( (unsigned int)v13 <= v22 && *((_QWORD *)a1 + 0x2000) )
      {
        *((_QWORD *)a1 + 8193) += (unsigned int)v13;
        v23 = *((_QWORD *)a1 + 8196);
        *v3 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 96LL))(v23);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 8196) + 24LL))(
          *((_QWORD *)a1 + 8196),
          *((_QWORD *)a1 + 8193),
          0);
        v24 = 0x10000;
        if ( *((_QWORD *)a1 + 0x2000) < 0x10000u )
          v24 = *((_QWORD *)a1 + 0x2000);
        v25 = (*(__int64 (__fastcall **)(_QWORD, struct CrxBitstream *, __int64, __int64))(**((_QWORD **)a1 + 8196)
                                                                                         + 16LL))(
                *((_QWORD *)a1 + 8196),
                a1,
                1,
                v24);
        v26 = *((_QWORD *)a1 + 8196);
        *((_DWORD *)a1 + 16389) = v25;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 104LL))(v26);
        v27 = *((unsigned int *)a1 + 16389);
        if ( !(_DWORD)v27 )
        {
          pExceptionObject = 4;
          throw (LibRaw_exceptions *)&pExceptionObject;
        }
        *((_QWORD *)a1 + 0x2000) -= v27;
      }
      if ( v4 )
      {
LABEL_24:
        _BitScanReverse((unsigned int *)&v8, v4);
        *((_DWORD *)a1 + 16391) = v8;
        v9 = i - v8 + 7;
        v10 = v4 << (32 - (unsigned __int8)v8);
        goto LABEL_25;
      }
    }
    v14 = (unsigned int)v13;
    while ( 1 )
    {
      LODWORD(v13) = v14;
      v15 = *(_DWORD *)((char *)a1 + v12);
      v16 = v12 + 4;
      *v3 = v12 + 4;
      v17 = v14;
      v4 = _byteswap_ulong(v15);
      if ( v16 >= (unsigned int)v14 && *((_QWORD *)a1 + 0x2000) )
      {
        v18 = *((_QWORD *)a1 + 8196);
        *((_QWORD *)a1 + 8193) += (unsigned int)v14;
        *v3 = 0;
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v18 + 96LL))(v18, v14, (unsigned int)v14);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 8196) + 24LL))(
          *((_QWORD *)a1 + 8196),
          *((_QWORD *)a1 + 8193),
          0);
        v19 = 0x10000;
        if ( *((_QWORD *)a1 + 0x2000) < 0x10000u )
          v19 = *((_QWORD *)a1 + 0x2000);
        v20 = (*(__int64 (__fastcall **)(_QWORD, struct CrxBitstream *, __int64, __int64))(**((_QWORD **)a1 + 8196)
                                                                                         + 16LL))(
                *((_QWORD *)a1 + 8196),
                a1,
                1,
                v19);
        v21 = *((_QWORD *)a1 + 8196);
        *((_DWORD *)a1 + 16389) = v20;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 104LL))(v21);
        v13 = *((unsigned int *)a1 + 16389);
        v17 = v13;
        if ( !(_DWORD)v13 )
        {
          pExceptionObject = 4;
          throw (LibRaw_exceptions *)&pExceptionObject;
        }
        *((_QWORD *)a1 + 0x2000) -= v13;
      }
      v14 = v17;
      if ( (_DWORD)v4 )
        break;
      v12 = *v3;
      i += 32;
      if ( *v3 + 4 > (unsigned int)v13 )
        goto LABEL_14;
    }
    _BitScanReverse((unsigned int *)&v8, v4);
    *((_DWORD *)a1 + 16391) = v8;
    v9 = i - v8 + 31;
    v28 = (unsigned __int64)(unsigned int)v4 << (32 - (unsigned __int8)v8);
  }
  *((_DWORD *)a1 + 16390) = v28;
  if ( v9 < 0x17 )
  {
    if ( !v5 )
      return v9;
    if ( v8 < v5 )
    {
      v40 = *v3;
      v41 = *((_DWORD *)a1 + 16389);
      if ( (int)v40 + 4 <= v41 )
      {
        v42 = _byteswap_ulong(*(_DWORD *)((char *)a1 + v40));
        *v3 = v40 + 4;
        crxFillBuffer(a1);
        v43 = ((unsigned int)v28 | (v42 >> v8)) >> (32 - v5);
        v44 = v42 << (v5 - v8);
        v45 = v8 - v5 + 32;
LABEL_56:
        *((_DWORD *)a1 + 16391) = v45;
        v9 = v43 | (v9 << v5);
        *((_DWORD *)a1 + 16390) = v44;
        return v9;
      }
      v46 = *v3;
      if ( (unsigned int)v40 < v41 )
      {
        v47 = 32 - v8;
        do
        {
          v48 = *((unsigned __int8 *)a1 + v40);
          v8 += 8;
          v47 -= 8;
          *v3 = v46 + 1;
          v49 = v41;
          if ( v46 + 1 >= v41 && *((_QWORD *)a1 + 0x2000) )
          {
            *((_QWORD *)a1 + 8193) += v41;
            v50 = *((_QWORD *)a1 + 8196);
            *v3 = 0;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 96LL))(v50, v49);
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 8196) + 24LL))(
              *((_QWORD *)a1 + 8196),
              *((_QWORD *)a1 + 8193),
              0);
            v51 = 0x10000;
            if ( *((_QWORD *)a1 + 0x2000) < 0x10000u )
              v51 = *((_QWORD *)a1 + 0x2000);
            v52 = (*(__int64 (__fastcall **)(_QWORD, struct CrxBitstream *, __int64, __int64))(**((_QWORD **)a1 + 8196)
                                                                                             + 16LL))(
                    *((_QWORD *)a1 + 8196),
                    a1,
                    1,
                    v51);
            v53 = *((_QWORD *)a1 + 8196);
            *((_DWORD *)a1 + 16389) = v52;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 104LL))(v53);
            v49 = *((unsigned int *)a1 + 16389);
            if ( !(_DWORD)v49 )
            {
              pExceptionObject = 4;
              throw (LibRaw_exceptions *)&pExceptionObject;
            }
            *((_QWORD *)a1 + 0x2000) -= v49;
          }
          LODWORD(v28) = (v48 << v47) | v28;
          v5 = v56;
          if ( v8 >= v56 )
            break;
          v40 = *v3;
          v41 = v49;
          v46 = v40;
        }
        while ( (unsigned int)v40 < (unsigned int)v49 );
      }
    }
    v43 = (unsigned int)v28 >> (32 - v5);
    v44 = (_DWORD)v28 << v5;
    v45 = v8 - v5;
    goto LABEL_56;
  }
  if ( v8 >= 8 )
  {
LABEL_40:
    v9 = BYTE3(v28);
    *((_DWORD *)a1 + 16391) = v8 - 8;
    *((_DWORD *)a1 + 16390) = (_DWORD)v28 << 8;
    return v9;
  }
  v29 = *v3;
  v30 = *((_DWORD *)a1 + 16389);
  if ( (int)v29 + 4 > v30 )
  {
    v32 = *v3;
    if ( (unsigned int)v29 < v30 )
    {
      v33 = 32 - v8;
      do
      {
        v34 = *((unsigned __int8 *)a1 + v29);
        v8 += 8;
        v33 -= 8;
        *v3 = v32 + 1;
        v35 = v30;
        if ( v32 + 1 >= v30 && *((_QWORD *)a1 + 0x2000) )
        {
          *((_QWORD *)a1 + 8193) += v30;
          v36 = *((_QWORD *)a1 + 8196);
          *v3 = 0;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 96LL))(v36, v35);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)a1 + 8196) + 24LL))(
            *((_QWORD *)a1 + 8196),
            *((_QWORD *)a1 + 8193),
            0);
          v37 = 0x10000;
          if ( *((_QWORD *)a1 + 0x2000) < 0x10000u )
            v37 = *((_QWORD *)a1 + 0x2000);
          v38 = (*(__int64 (__fastcall **)(_QWORD, struct CrxBitstream *, __int64, __int64))(**((_QWORD **)a1 + 8196)
                                                                                           + 16LL))(
                  *((_QWORD *)a1 + 8196),
                  a1,
                  1,
                  v37);
          v39 = *((_QWORD *)a1 + 8196);
          *((_DWORD *)a1 + 16389) = v38;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 104LL))(v39);
          v35 = *((unsigned int *)a1 + 16389);
          if ( !(_DWORD)v35 )
          {
            pExceptionObject = 4;
            throw (LibRaw_exceptions *)&pExceptionObject;
          }
          *((_QWORD *)a1 + 0x2000) -= v35;
        }
        LODWORD(v28) = (v34 << v33) | v28;
        if ( v8 >= 8 )
          break;
        v29 = *v3;
        v30 = v35;
        v32 = v29;
      }
      while ( (unsigned int)v29 < (unsigned int)v35 );
    }
    goto LABEL_40;
  }
  v31 = _byteswap_ulong(*(_DWORD *)((char *)a1 + v29));
  *v3 = v29 + 4;
  crxFillBuffer(a1);
  v9 = ((unsigned int)v28 | (v31 >> v8)) >> 24;
  *((_DWORD *)a1 + 16391) = v8 + 24;
  *((_DWORD *)a1 + 16390) = v31 << (8 - v8);
  return v9;
}

```

## disassembly

```asm
0x180023610  mov     [rsp+arg_8], edx
0x180023614  push    rbx
0x180023615  push    rbp
0x180023616  push    rsi
0x180023617  push    rdi
0x180023618  push    r13
0x18002361a  push    r14
0x18002361c  push    r15
0x18002361e  sub     rsp, 30h
0x180023622  mov     r8d, [rcx+10018h]
0x180023629  lea     r14, [rcx+10010h]
0x180023630  xor     esi, esi
0x180023632  mov     [rsp+68h+pExceptionObject], 0
0x18002363a  mov     r13d, edx
0x18002363d  mov     rbx, rcx
0x180023640  test    r8d, r8d
0x180023643  jz      short loc_180023674
0x180023645  mov     ebp, [rcx+1001Ch]
0x18002364b  mov     r15d, 20h ; ' '
0x180023651  bsr     edx, r8d
0x180023655  add     ebp, 0FFFFFFE0h
0x180023658  mov     edi, 1Fh
0x18002365d  add     ebp, edx
0x18002365f  sub     edi, edx
0x180023661  mov     [rcx+1001Ch], ebp
0x180023667  mov     ecx, r15d
0x18002366a  sub     ecx, edx
0x18002366c  shl     r8d, cl
0x18002366f  jmp     loc_18002389F
0x180023674  mov     edi, [rcx+1001Ch]
0x18002367a  nop     word ptr [rax+rax+00h]
0x180023680  mov     r8d, [r14]
0x180023683  mov     ecx, [rbx+10014h]
0x180023689  lea     eax, [r8+4]
0x18002368d  cmp     eax, ecx
0x18002368f  ja      loc_18002378C
0x180023695  mov     edx, ecx
0x180023697  nop     word ptr [rax+rax+00000000h]
0x1800236a0  mov     eax, r8d
0x1800236a3  mov     ecx, edx
0x1800236a5  mov     esi, [rax+rbx]
0x1800236a8  lea     eax, [r8+4]
0x1800236ac  mov     [r14], eax
0x1800236af  mov     r8d, edx
0x1800236b2  bswap   esi
0x1800236b4  mov     esi, esi
0x1800236b6  cmp     eax, edx
0x1800236b8  jb      loc_18002376E
0x1800236be  cmp     qword ptr [rbx+10000h], 0
0x1800236c6  jz      loc_18002376E
0x1800236cc  mov     rcx, [rbx+10020h]
0x1800236d3  mov     eax, edx
0x1800236d5  add     [rbx+10008h], rax
0x1800236dc  mov     dword ptr [r14], 0
0x1800236e3  mov     rax, [rcx]
0x1800236e6  mov     rax, [rax+60h]
0x1800236ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236ef  mov     rcx, [rbx+10020h]
0x1800236f6  xor     r8d, r8d
0x1800236f9  mov     rdx, [rbx+10008h]
0x180023700  mov     rax, [rcx]
0x180023703  mov     rax, [rax+18h]
0x180023707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002370c  mov     rax, [rbx+10000h]
0x180023713  mov     r9d, 10000h
0x180023719  mov     rcx, [rbx+10020h]
0x180023720  cmp     rax, r9
0x180023723  mov     r8d, 1
0x180023729  mov     rdx, rbx
0x18002372c  cmovb   r9, rax
0x180023730  mov     rax, [rcx]
0x180023733  mov     rax, [rax+10h]
0x180023737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002373c  mov     rcx, [rbx+10020h]
0x180023743  mov     [rbx+10014h], eax
0x180023749  mov     rax, [rcx]
0x18002374c  mov     rax, [rax+68h]
0x180023750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023755  mov     ecx, [rbx+10014h]
0x18002375b  mov     r8d, ecx
0x18002375e  cmp     ecx, 1
0x180023761  jb      loc_180023BE7
0x180023767  sub     [rbx+10000h], rcx
0x18002376e  mov     edx, r8d
0x180023771  test    rsi, rsi
0x180023774  jnz     loc_180023862
0x18002377a  mov     r8d, [r14]
0x18002377d  add     edi, 20h ; ' '
0x180023780  lea     eax, [r8+4]
0x180023784  cmp     eax, ecx
0x180023786  jbe     loc_1800236A0
0x18002378c  lea     edx, [r8+1]
0x180023790  cmp     ecx, edx
0x180023792  jb      loc_180023880
0x180023798  mov     eax, r8d
0x18002379b  movzx   esi, byte ptr [rax+rbx]
0x18002379f  mov     [r14], edx
0x1800237a2  ja      loc_180023855
0x1800237a8  cmp     qword ptr [rbx+10000h], 0
0x1800237b0  jz      loc_180023855
0x1800237b6  mov     eax, ecx
0x1800237b8  add     [rbx+10008h], rax
0x1800237bf  mov     rcx, [rbx+10020h]
0x1800237c6  mov     dword ptr [r14], 0
0x1800237cd  mov     rax, [rcx]
0x1800237d0  mov     rax, [rax+60h]
0x1800237d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237d9  mov     rcx, [rbx+10020h]
0x1800237e0  xor     r8d, r8d
0x1800237e3  mov     rdx, [rbx+10008h]
0x1800237ea  mov     rax, [rcx]
0x1800237ed  mov     rax, [rax+18h]
0x1800237f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f6  mov     rax, [rbx+10000h]
0x1800237fd  mov     r9d, 10000h
0x180023803  mov     rcx, [rbx+10020h]
0x18002380a  cmp     rax, r9
0x18002380d  mov     r8d, 1
0x180023813  mov     rdx, rbx
0x180023816  cmovb   r9, rax
0x18002381a  mov     rax, [rcx]
0x18002381d  mov     rax, [rax+10h]
0x180023821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023826  mov     rcx, [rbx+10020h]
0x18002382d  mov     [rbx+10014h], eax
0x180023833  mov     rax, [rcx]
0x180023836  mov     rax, [rax+68h]
0x18002383a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002383f  mov     eax, [rbx+10014h]
0x180023845  cmp     eax, 1
0x180023848  jb      loc_180023C01
0x18002384e  sub     [rbx+10000h], rax
0x180023855  test    rsi, rsi
0x180023858  jnz     short loc_180023880
0x18002385a  add     edi, 8
0x18002385d  jmp     loc_180023680
0x180023862  bsr     ebp, esi
0x180023865  mov     r15d, 20h ; ' '
0x18002386b  sub     edi, ebp
0x18002386d  mov     [rbx+1001Ch], ebp
0x180023873  mov     ecx, r15d
0x180023876  add     edi, 1Fh
0x180023879  sub     ecx, ebp
0x18002387b  shl     rsi, cl
0x18002387e  jmp     short loc_1800238A2
0x180023880  bsr     ebp, esi
0x180023883  mov     r15d, 20h ; ' '
0x180023889  mov     r8, rsi
0x18002388c  sub     edi, ebp
0x18002388e  mov     [rbx+1001Ch], ebp
0x180023894  mov     ecx, r15d
0x180023897  add     edi, 7
0x18002389a  sub     ecx, ebp
0x18002389c  shl     r8, cl
0x18002389f  mov     esi, r8d
0x1800238a2  mov     [rsp+68h+arg_10], r12
0x1800238aa  mov     [rbx+10018h], esi
0x1800238b0  cmp     edi, 17h
0x1800238b3  jb      loc_180023A28
0x1800238b9  cmp     ebp, 8
0x1800238bc  jge     loc_180023A07
0x1800238c2  mov     eax, [r14]
0x1800238c5  mov     ecx, [rbx+10014h]
0x1800238cb  lea     edx, [rax+4]
0x1800238ce  cmp     edx, ecx
0x1800238d0  ja      short loc_18002390F
0x1800238d2  mov     r15d, [rax+rbx]
0x1800238d6  mov     rcx, rbx
0x1800238d9  bswap   r15d
0x1800238dc  mov     [r14], edx
0x1800238df  call    crxFillBuffer
0x1800238e4  mov     ecx, ebp
0x1800238e6  mov     edi, r15d
0x1800238e9  shr     edi, cl
0x1800238eb  mov     ecx, 8
0x1800238f0  sub     ecx, ebp
0x1800238f2  or      edi, esi
0x1800238f4  shl     r15d, cl
0x1800238f7  shr     edi, 18h
0x1800238fa  add     ebp, 18h
0x1800238fd  mov     [rbx+1001Ch], ebp
0x180023903  mov     [rbx+10018h], r15d
0x18002390a  jmp     loc_180023BB4
0x18002390f  mov     r8d, eax
0x180023912  cmp     eax, ecx
0x180023914  jnb     loc_180023A07
0x18002391a  sub     r15d, ebp
0x18002391d  nop     dword ptr [rax]
0x180023920  movzx   edi, byte ptr [rax+rbx]
0x180023924  add     ebp, 8
0x180023927  lea     eax, [r8+1]
0x18002392b  sub     r15d, 8
0x18002392f  mov     [r14], eax
0x180023932  mov     edx, ecx
0x180023934  cmp     eax, ecx
0x180023936  jb      loc_1800239E9
0x18002393c  cmp     qword ptr [rbx+10000h], 0
0x180023944  jz      loc_1800239E9
0x18002394a  mov     eax, ecx
0x18002394c  add     [rbx+10008h], rax
0x180023953  mov     rcx, [rbx+10020h]
0x18002395a  mov     dword ptr [r14], 0
0x180023961  mov     rax, [rcx]
0x180023964  mov     rax, [rax+60h]
0x180023968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002396d  mov     rcx, [rbx+10020h]
0x180023974  xor     r8d, r8d
0x180023977  mov     rdx, [rbx+10008h]
0x18002397e  mov     rax, [rcx]
0x180023981  mov     rax, [rax+18h]
0x180023985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002398a  mov     rax, [rbx+10000h]
0x180023991  mov     r9d, 10000h
0x180023997  mov     rcx, [rbx+10020h]
0x18002399e  cmp     rax, r9
0x1800239a1  mov     r8d, 1
0x1800239a7  mov     rdx, rbx
0x1800239aa  cmovb   r9, rax
0x1800239ae  mov     rax, [rcx]
0x1800239b1  mov     rax, [rax+10h]
0x1800239b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239ba  mov     rcx, [rbx+10020h]
0x1800239c1  mov     [rbx+10014h], eax
0x1800239c7  mov     rax, [rcx]
0x1800239ca  mov     rax, [rax+68h]
0x1800239ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239d3  mov     edx, [rbx+10014h]
0x1800239d9  cmp     edx, 1
0x1800239dc  jb      loc_180023C1B
0x1800239e2  sub     [rbx+10000h], rdx
0x1800239e9  mov     eax, edi
0x1800239eb  mov     ecx, r15d
0x1800239ee  shl     eax, cl
0x1800239f0  or      esi, eax
0x1800239f2  cmp     ebp, 8
0x1800239f5  jge     short loc_180023A07
0x1800239f7  mov     eax, [r14]
0x1800239fa  mov     ecx, edx
0x1800239fc  mov     r8d, eax
0x1800239ff  cmp     eax, edx
0x180023a01  jb      loc_180023920
0x180023a07  mov     edi, esi
0x180023a09  mov     r15d, esi
0x180023a0c  shl     r15d, 8
0x180023a10  shr     edi, 18h
0x180023a13  add     ebp, 0FFFFFFF8h
0x180023a16  mov     [rbx+1001Ch], ebp
0x180023a1c  mov     [rbx+10018h], r15d
0x180023a23  jmp     loc_180023BB4
0x180023a28  test    r13d, r13d
0x180023a2b  jz      loc_180023BB4
0x180023a31  cmp     ebp, r13d
0x180023a34  jge     loc_180023B89
0x180023a3a  mov     eax, [r14]
0x180023a3d  mov     ecx, [rbx+10014h]
0x180023a43  lea     edx, [rax+4]
0x180023a46  cmp     edx, ecx
0x180023a48  ja      short loc_180023A81
0x180023a4a  mov     r12d, [rax+rbx]
0x180023a4e  mov     rcx, rbx
0x180023a51  bswap   r12d
0x180023a54  mov     [r14], edx
0x180023a57  call    crxFillBuffer
0x180023a5c  mov     ecx, ebp
0x180023a5e  mov     eax, r12d
0x180023a61  shr     eax, cl
0x180023a63  sub     r15d, r13d
0x180023a66  or      eax, esi
0x180023a68  movzx   ecx, r15b
0x180023a6c  shr     eax, cl
0x180023a6e  mov     ecx, r13d
0x180023a71  sub     ecx, ebp
0x180023a73  sub     ebp, r13d
0x180023a76  shl     r12d, cl
0x180023a79  add     ebp, 20h ; ' '
0x180023a7c  jmp     loc_180023BA0
0x180023a81  mov     r8d, eax
0x180023a84  cmp     eax, ecx
0x180023a86  jnb     loc_180023B89
0x180023a8c  mov     r12d, r15d
0x180023a8f  sub     r12d, ebp
0x180023a92  nop     dword ptr [rax+00h]
0x180023a96  nop     word ptr [rax+rax+00000000h]
0x180023aa0  movzx   r13d, byte ptr [rax+rbx]
0x180023aa5  add     ebp, 8
0x180023aa8  lea     eax, [r8+1]
0x180023aac  sub     r12d, 8
0x180023ab0  mov     [r14], eax
0x180023ab3  mov     edx, ecx
0x180023ab5  cmp     eax, ecx
0x180023ab7  jb      loc_180023B66
0x180023abd  cmp     qword ptr [rbx+10000h], 0
0x180023ac5  jz      loc_180023B66
0x180023acb  mov     eax, ecx
0x180023acd  add     [rbx+10008h], rax
0x180023ad4  mov     rcx, [rbx+10020h]
0x180023adb  mov     dword ptr [r14], 0
0x180023ae2  mov     rax, [rcx]
0x180023ae5  mov     rax, [rax+60h]
0x180023ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
