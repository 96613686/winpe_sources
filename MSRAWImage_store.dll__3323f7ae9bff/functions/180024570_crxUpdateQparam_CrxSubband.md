# crxUpdateQparam(CrxSubband *)

- ea: `0x180024570`
- end: `0x180024c2d`
- name: `?crxUpdateQparam@@YAHPEAUCrxSubband@@@Z`
- size: `1725`
- prototype: `__int64 __fastcall(struct CrxSubband *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001c700`

## callees

- `0x180003e4c`
- `0x180020ab0`
- `0x180024570`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall crxUpdateQparam(struct CrxSubband *a1)
{
  __int64 v1; // rbx
  int v2; // r12d
  struct CrxSubband *v3; // r14
  __int64 v4; // rsi
  unsigned int v5; // r8d
  unsigned int v6; // edx
  int v7; // edi
  __int64 v8; // r8
  int i; // edi
  unsigned int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rcx
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // eax
  unsigned __int64 v27; // rsi
  unsigned int v28; // eax
  __int64 v29; // rbx
  int v30; // esi
  unsigned int v31; // r14d
  __int64 v32; // rax
  unsigned int v33; // ecx
  unsigned __int32 v34; // ebp
  unsigned int v35; // edi
  unsigned __int32 v36; // ebp
  int v37; // esi
  int v38; // r8d
  char v39; // bp
  int v40; // edi
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r9
  int v44; // eax
  __int64 v45; // rcx
  int *v46; // r13
  int v47; // r15d
  __int64 v48; // rbx
  int v49; // esi
  unsigned int v50; // r12d
  __int64 v51; // rax
  unsigned int v52; // ecx
  __int64 v53; // rcx
  unsigned __int32 v54; // r14d
  unsigned int v55; // eax
  unsigned __int32 v56; // r14d
  int v57; // esi
  int v58; // r8d
  char v59; // r14
  int v60; // r13d
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r9
  int v64; // eax
  __int64 v65; // rcx
  int v66; // r10d
  int v67; // edx
  struct CrxSubband *pExceptionObject; // [rsp+70h] [rbp+8h] BYREF
  int *v70; // [rsp+78h] [rbp+10h]

  pExceptionObject = a1;
  v1 = *(_QWORD *)a1;
  v2 = 0;
  v3 = a1;
  LODWORD(v70) = 0;
  v4 = 0;
  v5 = *(_DWORD *)(v1 + 65560);
  if ( v5 )
  {
    _BitScanReverse(&v6, v5);
    v7 = 31 - v6;
    *(_DWORD *)(v1 + 65564) = v6 + *(_DWORD *)(v1 + 65564) - 32;
    LODWORD(v8) = v5 << (32 - v6);
LABEL_25:
    LODWORD(v27) = v8;
  }
  else
  {
    for ( i = *(_DWORD *)(v1 + 65564); ; i += 8 )
    {
      v10 = *(_DWORD *)(v1 + 65552);
      LODWORD(v11) = *(_DWORD *)(v1 + 65556);
      if ( v10 + 4 <= (unsigned int)v11 )
        break;
LABEL_14:
      v20 = v10 + 1;
      if ( (unsigned int)v11 < v10 + 1 )
        goto LABEL_24;
      v4 = *(unsigned __int8 *)(v10 + v1);
      *(_DWORD *)(v1 + 65552) = v20;
      if ( (unsigned int)v11 <= v20 && *(_QWORD *)(v1 + 0x10000) )
      {
        *(_QWORD *)(v1 + 65544) += (unsigned int)v11;
        v21 = *(_QWORD *)(v1 + 65568);
        *(_DWORD *)(v1 + 65552) = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 96LL))(v21);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v1 + 65568) + 24LL))(
          *(_QWORD *)(v1 + 65568),
          *(_QWORD *)(v1 + 65544),
          0);
        v22 = 0x10000;
        if ( *(_QWORD *)(v1 + 0x10000) < 0x10000u )
          v22 = *(_QWORD *)(v1 + 0x10000);
        v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v1 + 65568) + 16LL))(
                *(_QWORD *)(v1 + 65568),
                v1,
                1,
                v22);
        v24 = *(_QWORD *)(v1 + 65568);
        *(_DWORD *)(v1 + 65556) = v23;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 104LL))(v24);
        v25 = *(unsigned int *)(v1 + 65556);
        if ( !(_DWORD)v25 )
        {
          LODWORD(pExceptionObject) = 4;
          throw (LibRaw_exceptions *)&pExceptionObject;
        }
        *(_QWORD *)(v1 + 0x10000) -= v25;
      }
      if ( v4 )
      {
LABEL_24:
        _BitScanReverse(&v28, v4);
        *(_DWORD *)(v1 + 65564) = v28;
        v7 = i - v28 + 7;
        v8 = v4 << (32 - (unsigned __int8)v28);
        goto LABEL_25;
      }
    }
    v12 = (unsigned int)v11;
    while ( 1 )
    {
      LODWORD(v11) = v12;
      v13 = *(_DWORD *)(v10 + v1);
      v14 = v10 + 4;
      *(_DWORD *)(v1 + 65552) = v10 + 4;
      v15 = v12;
      v4 = _byteswap_ulong(v13);
      if ( v14 >= (unsigned int)v12 && *(_QWORD *)(v1 + 0x10000) )
      {
        v16 = *(_QWORD *)(v1 + 65568);
        *(_QWORD *)(v1 + 65544) += (unsigned int)v12;
        *(_DWORD *)(v1 + 65552) = 0;
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v16 + 96LL))(v16, v12, (unsigned int)v12);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v1 + 65568) + 24LL))(
          *(_QWORD *)(v1 + 65568),
          *(_QWORD *)(v1 + 65544),
          0);
        v17 = 0x10000;
        if ( *(_QWORD *)(v1 + 0x10000) < 0x10000u )
          v17 = *(_QWORD *)(v1 + 0x10000);
        v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v1 + 65568) + 16LL))(
                *(_QWORD *)(v1 + 65568),
                v1,
                1,
                v17);
        v19 = *(_QWORD *)(v1 + 65568);
        *(_DWORD *)(v1 + 65556) = v18;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 104LL))(v19);
        v11 = *(unsigned int *)(v1 + 65556);
        v15 = v11;
        if ( !(_DWORD)v11 )
        {
          LODWORD(pExceptionObject) = 4;
          throw (LibRaw_exceptions *)&pExceptionObject;
        }
        *(_QWORD *)(v1 + 0x10000) -= v11;
      }
      v12 = v15;
      if ( (_DWORD)v4 )
        break;
      v10 = *(_DWORD *)(v1 + 65552);
      i += 32;
      if ( v10 + 4 > (unsigned int)v11 )
        goto LABEL_14;
    }
    _BitScanReverse(&v26, v4);
    *(_DWORD *)(v1 + 65564) = v26;
    v7 = i - v26 + 31;
    v27 = (unsigned __int64)(unsigned int)v4 << (32 - (unsigned __int8)v26);
  }
  *(_DWORD *)(v1 + 65560) = v27;
  if ( (unsigned int)v7 < 0x17 )
  {
    v47 = *((_DWORD *)v3 + 8);
    v46 = (int *)((char *)v3 + 32);
    v70 = (int *)((char *)v3 + 32);
    if ( !v47 )
      goto LABEL_59;
    v48 = *(_QWORD *)v3;
    v49 = *(_DWORD *)(*(_QWORD *)v3 + 65564LL);
    v50 = *(_DWORD *)(*(_QWORD *)v3 + 65560LL);
    if ( v49 < v47 )
    {
      v51 = *(unsigned int *)(v48 + 65552);
      v52 = *(_DWORD *)(v48 + 65556);
      if ( (int)v51 + 4 <= v52 )
      {
        v53 = *(_QWORD *)v3;
        v54 = _byteswap_ulong(*(_DWORD *)(v51 + v48));
        *(_DWORD *)(v48 + 65552) = v51 + 4;
        crxFillBuffer(v53);
        v55 = (v50 | (v54 >> v49)) >> (32 - v47);
        v56 = v54 << (v47 - v49);
        v57 = v49 - v47 + 32;
LABEL_58:
        *(_DWORD *)(v48 + 65564) = v57;
        *(_DWORD *)(v48 + 65560) = v56;
        v3 = pExceptionObject;
        v7 = v55 | (v7 << *v46);
        v2 = 0;
        goto LABEL_59;
      }
      v58 = *(_DWORD *)(v48 + 65552);
      if ( (unsigned int)v51 < v52 )
      {
        v59 = 32 - v49;
        do
        {
          v60 = *(unsigned __int8 *)(v51 + v48);
          v49 += 8;
          v59 -= 8;
          *(_DWORD *)(v48 + 65552) = v58 + 1;
          v61 = v52;
          if ( v58 + 1 >= v52 && *(_QWORD *)(v48 + 0x10000) )
          {
            *(_QWORD *)(v48 + 65544) += v52;
            v62 = *(_QWORD *)(v48 + 65568);
            *(_DWORD *)(v48 + 65552) = 0;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 96LL))(v62, v61);
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v48 + 65568) + 24LL))(
              *(_QWORD *)(v48 + 65568),
              *(_QWORD *)(v48 + 65544),
              0);
            v63 = 0x10000;
            if ( *(_QWORD *)(v48 + 0x10000) < 0x10000u )
              v63 = *(_QWORD *)(v48 + 0x10000);
            v64 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v48 + 65568) + 16LL))(
                    *(_QWORD *)(v48 + 65568),
                    v48,
                    1,
                    v63);
            v65 = *(_QWORD *)(v48 + 65568);
            *(_DWORD *)(v48 + 65556) = v64;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 104LL))(v65);
            v61 = *(unsigned int *)(v48 + 65556);
            if ( !(_DWORD)v61 )
            {
              LODWORD(pExceptionObject) = 4;
              throw (LibRaw_exceptions *)&pExceptionObject;
            }
            *(_QWORD *)(v48 + 0x10000) -= v61;
          }
          v50 |= v60 << v59;
          if ( v49 >= v47 )
            break;
          v51 = *(unsigned int *)(v48 + 65552);
          v52 = v61;
          v58 = v51;
        }
        while ( (unsigned int)v51 < (unsigned int)v61 );
        v46 = v70;
      }
    }
    v55 = v50 >> (32 - v47);
    v56 = v50 << v47;
    v57 = v49 - v47;
    goto LABEL_58;
  }
  v29 = *(_QWORD *)v3;
  v30 = *(_DWORD *)(*(_QWORD *)v3 + 65564LL);
  v31 = *(_DWORD *)(*(_QWORD *)v3 + 65560LL);
  if ( v30 >= 8 )
  {
LABEL_40:
    v7 = (unsigned __int64)v31 >> 24;
    v36 = v31 << 8;
    v37 = v30 - 8;
    goto LABEL_41;
  }
  v32 = *(unsigned int *)(v29 + 65552);
  v33 = *(_DWORD *)(v29 + 65556);
  if ( (int)v32 + 4 > v33 )
  {
    v38 = *(_DWORD *)(v29 + 65552);
    if ( (unsigned int)v32 < v33 )
    {
      v39 = 32 - v30;
      do
      {
        v40 = *(unsigned __int8 *)(v32 + v29);
        v30 += 8;
        v39 -= 8;
        *(_DWORD *)(v29 + 65552) = v38 + 1;
        v41 = v33;
        if ( v38 + 1 >= v33 && *(_QWORD *)(v29 + 0x10000) )
        {
          *(_QWORD *)(v29 + 65544) += v33;
          v42 = *(_QWORD *)(v29 + 65568);
          *(_DWORD *)(v29 + 65552) = 0;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 96LL))(v42, v41);
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v29 + 65568) + 24LL))(
            *(_QWORD *)(v29 + 65568),
            *(_QWORD *)(v29 + 65544),
            0);
          v43 = 0x10000;
          if ( *(_QWORD *)(v29 + 0x10000) < 0x10000u )
            v43 = *(_QWORD *)(v29 + 0x10000);
          v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v29 + 65568) + 16LL))(
                  *(_QWORD *)(v29 + 65568),
                  v29,
                  1,
                  v43);
          v45 = *(_QWORD *)(v29 + 65568);
          *(_DWORD *)(v29 + 65556) = v44;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
          v41 = *(unsigned int *)(v29 + 65556);
          if ( !(_DWORD)v41 )
          {
            LODWORD(pExceptionObject) = 4;
            throw (LibRaw_exceptions *)&pExceptionObject;
          }
          *(_QWORD *)(v29 + 0x10000) -= v41;
        }
        v31 |= v40 << v39;
        if ( v30 >= 8 )
          break;
        v32 = *(unsigned int *)(v29 + 65552);
        v33 = v41;
        v38 = v32;
      }
      while ( (unsigned int)v32 < (unsigned int)v41 );
    }
    goto LABEL_40;
  }
  v34 = _byteswap_ulong(*(_DWORD *)(v32 + v29));
  *(_DWORD *)(v29 + 65552) = v32 + 4;
  crxFillBuffer(v29);
  v35 = v31 | (v34 >> v30);
  v36 = v34 << (8 - v30);
  v7 = HIBYTE(v35);
  v37 = v30 + 24;
LABEL_41:
  *(_DWORD *)(v29 + 65564) = v37;
  *(_DWORD *)(v29 + 65560) = v36;
  v3 = pExceptionObject;
  v46 = (int *)((char *)pExceptionObject + 32);
LABEL_59:
  v66 = *v46;
  *((_DWORD *)v3 + 7) += -(v7 & 1) ^ ((unsigned int)v7 >> 1);
  v67 = v66 + (v7 >> v66 > 5) - (v7 < 1 << v66 >> 1) + (v7 >> v66 > 2);
  *v46 = v67;
  LOBYTE(v2) = v67 <= 7;
  return (unsigned int)(v2 - 1);
}

```

## disassembly

```asm
0x180024570  mov     [rsp+pExceptionObject], rcx
0x180024575  push    rbx
0x180024576  push    rbp
0x180024577  push    rsi
0x180024578  push    rdi
0x180024579  push    r12
0x18002457b  push    r14
0x18002457d  push    r15
0x18002457f  sub     rsp, 30h
0x180024583  mov     rbx, [rcx]
0x180024586  xor     r12d, r12d
0x180024589  mov     r14, rcx
0x18002458c  mov     dword ptr [rsp+68h+arg_8], r12d
0x180024591  mov     esi, r12d
0x180024594  mov     r15d, 1
0x18002459a  mov     r8d, [rbx+10018h]
0x1800245a1  test    r8d, r8d
0x1800245a4  jz      short loc_1800245D3
0x1800245a6  mov     ecx, [rbx+1001Ch]
0x1800245ac  mov     ebp, 20h ; ' '
0x1800245b1  bsr     edx, r8d
0x1800245b5  add     ecx, 0FFFFFFE0h
0x1800245b8  mov     edi, 1Fh
0x1800245bd  add     ecx, edx
0x1800245bf  sub     edi, edx
0x1800245c1  mov     [rbx+1001Ch], ecx
0x1800245c7  mov     ecx, ebp
0x1800245c9  sub     ecx, edx
0x1800245cb  shl     r8d, cl
0x1800245ce  jmp     loc_1800247FD
0x1800245d3  mov     edi, [rbx+1001Ch]
0x1800245d9  nop     dword ptr [rax+00000000h]
0x1800245e0  mov     r8d, [rbx+10010h]
0x1800245e7  mov     ecx, [rbx+10014h]
0x1800245ed  lea     eax, [r8+4]
0x1800245f1  cmp     eax, ecx
0x1800245f3  ja      loc_1800246EF
0x1800245f9  mov     edx, ecx
0x1800245fb  nop     dword ptr [rax+rax+00h]
0x180024600  mov     eax, r8d
0x180024603  mov     ecx, edx
0x180024605  mov     esi, [rax+rbx]
0x180024608  lea     eax, [r8+4]
0x18002460c  mov     [rbx+10010h], eax
0x180024612  mov     r8d, edx
0x180024615  bswap   esi
0x180024617  mov     esi, esi
0x180024619  cmp     eax, edx
0x18002461b  jb      loc_1800246CD
0x180024621  cmp     [rbx+10000h], r12
0x180024628  jz      loc_1800246CD
0x18002462e  mov     rcx, [rbx+10020h]
0x180024635  mov     eax, edx
0x180024637  add     [rbx+10008h], rax
0x18002463e  mov     [rbx+10010h], r12d
0x180024645  mov     rax, [rcx]
0x180024648  mov     rax, [rax+60h]
0x18002464c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024651  mov     rcx, [rbx+10020h]
0x180024658  xor     r8d, r8d
0x18002465b  mov     rdx, [rbx+10008h]
0x180024662  mov     rax, [rcx]
0x180024665  mov     rax, [rax+18h]
0x180024669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002466e  mov     rax, [rbx+10000h]
0x180024675  mov     r9d, 10000h
0x18002467b  mov     rcx, [rbx+10020h]
0x180024682  cmp     rax, r9
0x180024685  mov     r8, r15
0x180024688  mov     rdx, rbx
0x18002468b  cmovb   r9, rax
0x18002468f  mov     rax, [rcx]
0x180024692  mov     rax, [rax+10h]
0x180024696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002469b  mov     rcx, [rbx+10020h]
0x1800246a2  mov     [rbx+10014h], eax
0x1800246a8  mov     rax, [rcx]
0x1800246ab  mov     rax, [rax+68h]
0x1800246af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246b4  mov     ecx, [rbx+10014h]
0x1800246ba  mov     r8d, ecx
0x1800246bd  cmp     ecx, r15d
0x1800246c0  jb      loc_180024BDF
0x1800246c6  sub     [rbx+10000h], rcx
0x1800246cd  mov     edx, r8d
0x1800246d0  test    rsi, rsi
0x1800246d3  jnz     loc_1800247C4
0x1800246d9  mov     r8d, [rbx+10010h]
0x1800246e0  add     edi, 20h ; ' '
0x1800246e3  lea     eax, [r8+4]
0x1800246e7  cmp     eax, ecx
0x1800246e9  jbe     loc_180024600
0x1800246ef  lea     edx, [r8+1]
0x1800246f3  cmp     ecx, edx
0x1800246f5  jb      loc_1800247E0
0x1800246fb  mov     eax, r8d
0x1800246fe  movzx   esi, byte ptr [rax+rbx]
0x180024702  mov     [rbx+10010h], edx
0x180024708  ja      loc_1800247B7
0x18002470e  cmp     [rbx+10000h], r12
0x180024715  jz      loc_1800247B7
0x18002471b  mov     eax, ecx
0x18002471d  add     [rbx+10008h], rax
0x180024724  mov     rcx, [rbx+10020h]
0x18002472b  mov     [rbx+10010h], r12d
0x180024732  mov     rax, [rcx]
0x180024735  mov     rax, [rax+60h]
0x180024739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002473e  mov     rcx, [rbx+10020h]
0x180024745  xor     r8d, r8d
0x180024748  mov     rdx, [rbx+10008h]
0x18002474f  mov     rax, [rcx]
0x180024752  mov     rax, [rax+18h]
0x180024756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002475b  mov     rax, [rbx+10000h]
0x180024762  mov     r9d, 10000h
0x180024768  mov     rcx, [rbx+10020h]
0x18002476f  cmp     rax, r9
0x180024772  mov     r8, r15
0x180024775  mov     rdx, rbx
0x180024778  cmovb   r9, rax
0x18002477c  mov     rax, [rcx]
0x18002477f  mov     rax, [rax+10h]
0x180024783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024788  mov     rcx, [rbx+10020h]
0x18002478f  mov     [rbx+10014h], eax
0x180024795  mov     rax, [rcx]
0x180024798  mov     rax, [rax+68h]
0x18002479c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247a1  mov     eax, [rbx+10014h]
0x1800247a7  cmp     eax, r15d
0x1800247aa  jb      loc_180024BF9
0x1800247b0  sub     [rbx+10000h], rax
0x1800247b7  test    rsi, rsi
0x1800247ba  jnz     short loc_1800247E0
0x1800247bc  add     edi, 8
0x1800247bf  jmp     loc_1800245E0
0x1800247c4  bsr     eax, esi
0x1800247c7  mov     ebp, 20h ; ' '
0x1800247cc  sub     edi, eax
0x1800247ce  mov     [rbx+1001Ch], eax
0x1800247d4  mov     ecx, ebp
0x1800247d6  add     edi, 1Fh
0x1800247d9  sub     ecx, eax
0x1800247db  shl     rsi, cl
0x1800247de  jmp     short loc_180024800
0x1800247e0  bsr     eax, esi
0x1800247e3  mov     ebp, 20h ; ' '
0x1800247e8  mov     r8, rsi
0x1800247eb  sub     edi, eax
0x1800247ed  mov     [rbx+1001Ch], eax
0x1800247f3  mov     ecx, ebp
0x1800247f5  add     edi, 7
0x1800247f8  sub     ecx, eax
0x1800247fa  shl     r8, cl
0x1800247fd  mov     esi, r8d
0x180024800  mov     [rsp+68h+arg_10], r13
0x180024808  mov     [rbx+10018h], esi
0x18002480e  cmp     edi, 17h
0x180024811  jb      loc_180024991
0x180024817  mov     rbx, [r14]
0x18002481a  mov     esi, [rbx+1001Ch]
0x180024820  mov     r14d, [rbx+10018h]
0x180024827  cmp     esi, 8
0x18002482a  jge     loc_180024968
0x180024830  mov     eax, [rbx+10010h]
0x180024836  mov     ecx, [rbx+10014h]
0x18002483c  lea     edx, [rax+4]
0x18002483f  cmp     edx, ecx
0x180024841  ja      short loc_180024873
0x180024843  mov     ebp, [rax+rbx]
0x180024846  mov     rcx, rbx
0x180024849  bswap   ebp
0x18002484b  mov     [rbx+10010h], edx
0x180024851  call    crxFillBuffer
0x180024856  mov     ecx, esi
0x180024858  mov     edi, ebp
0x18002485a  shr     edi, cl
0x18002485c  mov     ecx, 8
0x180024861  sub     ecx, esi
0x180024863  or      edi, r14d
0x180024866  shl     ebp, cl
0x180024868  shr     edi, 18h
0x18002486b  add     esi, 18h
0x18002486e  jmp     loc_180024977
0x180024873  mov     r8d, eax
0x180024876  cmp     eax, ecx
0x180024878  jnb     loc_180024968
0x18002487e  sub     ebp, esi
0x180024880  movzx   edi, byte ptr [rax+rbx]
0x180024884  add     esi, 8
0x180024887  lea     eax, [r8+1]
0x18002488b  sub     ebp, 8
0x18002488e  mov     [rbx+10010h], eax
0x180024894  mov     edx, ecx
0x180024896  cmp     eax, ecx
0x180024898  jb      loc_180024947
0x18002489e  cmp     [rbx+10000h], r12
0x1800248a5  jz      loc_180024947
0x1800248ab  mov     eax, ecx
0x1800248ad  add     [rbx+10008h], rax
0x1800248b4  mov     rcx, [rbx+10020h]
0x1800248bb  mov     [rbx+10010h], r12d
0x1800248c2  mov     rax, [rcx]
0x1800248c5  mov     rax, [rax+60h]
0x1800248c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248ce  mov     rcx, [rbx+10020h]
0x1800248d5  xor     r8d, r8d
0x1800248d8  mov     rdx, [rbx+10008h]
0x1800248df  mov     rax, [rcx]
0x1800248e2  mov     rax, [rax+18h]
0x1800248e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248eb  mov     rax, [rbx+10000h]
0x1800248f2  mov     r9d, 10000h
0x1800248f8  mov     rcx, [rbx+10020h]
0x1800248ff  cmp     rax, r9
0x180024902  mov     r8, r15
0x180024905  mov     rdx, rbx
0x180024908  cmovb   r9, rax
0x18002490c  mov     rax, [rcx]
0x18002490f  mov     rax, [rax+10h]
0x180024913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024918  mov     rcx, [rbx+10020h]
0x18002491f  mov     [rbx+10014h], eax
0x180024925  mov     rax, [rcx]
0x180024928  mov     rax, [rax+68h]
0x18002492c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024931  mov     edx, [rbx+10014h]
0x180024937  cmp     edx, r15d
0x18002493a  jb      loc_180024C13
0x180024940  sub     [rbx+10000h], rdx
0x180024947  mov     eax, edi
0x180024949  mov     ecx, ebp
0x18002494b  shl     eax, cl
0x18002494d  or      r14d, eax
0x180024950  cmp     esi, 8
0x180024953  jge     short loc_180024968
0x180024955  mov     eax, [rbx+10010h]
0x18002495b  mov     ecx, edx
0x18002495d  mov     r8d, eax
0x180024960  cmp     eax, edx
0x180024962  jb      loc_180024880
0x180024968  mov     edi, r14d
0x18002496b  mov     ebp, r14d
0x18002496e  shr     edi, 18h
0x180024971  shl     ebp, 8
0x180024974  add     esi, 0FFFFFFF8h
0x180024977  mov     [rbx+1001Ch], esi
0x18002497d  mov     [rbx+10018h], ebp
0x180024983  mov     r14, [rsp+68h+pExceptionObject]
0x180024988  lea     r13, [r14+20h]
0x18002498c  jmp     loc_180024B53
0x180024991  mov     r15d, [r14+20h]
0x180024995  lea     r13, [r14+20h]
0x180024999  mov     [rsp+68h+arg_8], r13
0x18002499e  test    r15d, r15d
0x1800249a1  jz      loc_180024B4D
0x1800249a7  mov     rbx, [r14]
0x1800249aa  mov     esi, [rbx+1001Ch]
0x1800249b0  mov     r12d, [rbx+10018h]
0x1800249b7  cmp     esi, r15d
0x1800249ba  jge     loc_180024B18
0x1800249c0  mov     eax, [rbx+10010h]
0x1800249c6  mov     ecx, [rbx+10014h]
0x1800249cc  lea     edx, [rax+4]
0x1800249cf  cmp     edx, ecx
0x1800249d1  ja      short loc_180024A0E
0x1800249d3  mov     r14d, [rax+rbx]
0x1800249d7  mov     rcx, rbx
0x1800249da  bswap   r14d
0x1800249dd  mov     [rbx+10010h], edx
0x1800249e3  call    crxFillBuffer
0x1800249e8  mov     ecx, esi
0x1800249ea  mov     eax, r14d
0x1800249ed  shr     eax, cl
0x1800249ef  sub     ebp, r15d
0x1800249f2  or      eax, r12d
0x1800249f5  movzx   ecx, bpl
0x1800249f9  shr     eax, cl
0x1800249fb  mov     ecx, r15d
0x1800249fe  sub     ecx, esi
0x180024a00  sub     esi, r15d
0x180024a03  shl     r14d, cl
0x180024a06  add     esi, 20h ; ' '
0x180024a09  jmp     loc_180024B30
0x180024a0e  mov     r8d, eax
0x180024a11  cmp     eax, ecx
0x180024a13  jnb     loc_180024B18
0x180024a19  mov     r14d, ebp
0x180024a1c  sub     r14d, esi
0x180024a1f  nop
0x180024a20  movzx   r13d, byte ptr [rax+rbx]
0x180024a25  add     esi, 8
0x180024a28  lea     eax, [r8+1]
0x180024a2c  sub     r14d, 8
0x180024a30  mov     [rbx+10010h], eax
0x180024a36  mov     edx, ecx
0x180024a38  cmp     eax, ecx
0x180024a3a  jb      loc_180024AF0
0x180024a40  cmp     qword ptr [rbx+10000h], 0
  ... truncated ...
```
