# CRepubCreateSegmentTask::ReInitializeSegment(void)

- ea: `0x1800722a8`
- end: `0x180072859`
- name: `?ReInitializeSegment@CRepubCreateSegmentTask@@IEAAKXZ`
- size: `1457`
- prototype: `unsigned int __fastcall(CRepubCreateSegmentTask *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18006b590`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180004374`
- `0x180008290`
- `0x180011798`
- `0x180029404`
- `0x18006af5c`
- `0x1800722a8`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800726f7`
- `ESENT!JetPrepareUpdate` at `0x1800726f7`
- `ESENT!JetSetColumns` at `0x18007275e`
- `ESENT!JetSetColumns` at `0x18007275e`
- `ESENT!JetUpdate` at `0x1800727ab`
- `ESENT!JetUpdate` at `0x1800727ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubCreateSegmentTask::ReInitializeSegment(CRepubCreateSegmentTask *this)
{
  const unsigned __int8 *v2; // r12
  unsigned int v3; // r13d
  unsigned __int8 *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // r15
  int v7; // ebp
  unsigned int v8; // esi
  CHostedCacheMsgEncoding *v9; // rcx
  unsigned int v10; // r14d
  int v11; // r9d
  int *v12; // rsi
  int v13; // r8d
  char v14; // bp
  CHostedCacheMsgEncoding *v15; // rcx
  unsigned int v16; // esi
  void *v17; // rax
  __int64 v18; // r9
  CHostedCacheMsgEncoding *v19; // r10
  unsigned int v20; // r11d
  unsigned int i; // r9d
  const struct TnoHash *v22; // rdx
  unsigned int v23; // esi
  CHostedCacheMsgEncoding *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdx
  unsigned int v27; // ebp
  unsigned int Size; // [rsp+90h] [rbp+8h]
  unsigned int csetcolumn; // [rsp+98h] [rbp+10h] BYREF
  void *v31; // [rsp+A0h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 106, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v31 = 0;
  v5 = *((_QWORD *)this + 75);
  v6 = *(_QWORD *)(v5 + 16);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v5 + 24) + 72LL))(v5 + 24);
  Size = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 75) + 24LL) + 88LL))(*((_QWORD *)this + 75) + 24LL);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 75) + 24LL) + 80LL))(*((_QWORD *)this + 75) + 24LL);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        107,
        WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
        *((unsigned int *)this + 163));
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v9 + 108) & 4) != 0
      && *((_BYTE *)v9 + 105) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)v9 + 12),
        108,
        WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
        *((unsigned int *)this + 166));
    }
  }
  v10 = (v8 + v7 - 1) / v8;
  v11 = *((_DWORD *)this + 163);
  v12 = (int *)((char *)this + 664);
  v13 = *((_DWORD *)this + 166);
  if ( (v13 & 2) == 0 && (v11 & 2) != 0 )
  {
    v14 = 1;
    v13 |= 2u;
    *v12 = v13;
  }
  else
  {
    v14 = 0;
  }
  *((_BYTE *)this + 649) = 0;
  if ( (v11 & 1) != 0 && (v13 & 0x40) == 0 )
  {
    if ( v10 > 1 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 109, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
        v15 = WPP_GLOBAL_Control;
      }
      v16 = 87;
      goto LABEL_82;
    }
    v14 = 1;
    *v12 = v13 | 0x40;
    **((_BYTE **)this + 86) = -1;
    v3 = *((_DWORD *)this + 167);
    v2 = (const unsigned __int8 *)*((_QWORD *)this + 86);
  }
  if ( (*((_BYTE *)this + 652) & 5) == 0 && (*v12 & 0x100) != 0 )
  {
    v14 = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 110, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    }
    *v12 &= ~0x100u;
    v17 = operator new[](Size);
    std::auto_ptr<unsigned short>::reset(&v31, v17);
    v4 = (unsigned __int8 *)v31;
    memset_0(v31, 0, Size);
  }
  if ( *(_DWORD *)(v6 + 56) && *(char *)v12 < 0 )
  {
    v14 = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 111, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    }
    *v12 &= ~0x80u;
  }
  v18 = (unsigned int)*v12;
  if ( (*v12 & 0x200) != 0 && (*((_BYTE *)this + 652) & 8) == 0 )
  {
    v14 = 1;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 112, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    }
    *v12 &= ~0x200u;
    v18 = (unsigned int)*v12;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 113, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v18);
    v19 = WPP_GLOBAL_Control;
  }
  v20 = *v12;
  if ( (*v12 & 0x94) == 0x10 )
  {
    for ( i = 0; i < v10; ++i )
    {
      if ( ((unsigned __int8)(*(_BYTE *)(((unsigned __int64)i >> 3) + *((_QWORD *)this + 86))
                            & ~*(_BYTE *)(((unsigned __int64)i >> 3) + *((_QWORD *)this + 85)))
          & *(_BYTE *)(((unsigned __int64)i >> 3) + *((_QWORD *)this + 84))) != 0 )
      {
        *((_BYTE *)this + 649) = 1;
        v19 = WPP_GLOBAL_Control;
        break;
      }
    }
  }
  if ( v14 )
  {
    csetcolumn = *((_DWORD *)this + 96);
    v22 = (const struct TnoHash *)(v6 + 48);
    if ( !*(_DWORD *)(v6 + 56) )
      v22 = 0;
    CRepubCreateSegmentTask::InitializeCatalogTableSetColumns(
      this,
      v22,
      (unsigned int *)this + 166,
      v3,
      v2,
      Size,
      v4,
      *((struct JET_SETCOLUMN **)this + 50),
      &csetcolumn);
    v23 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 2u);
    if ( v23 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_68;
      }
      v25 = 115;
    }
    else
    {
      v23 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 62), *((JET_SETCOLUMN **)this + 50), csetcolumn);
      if ( !v23 )
      {
        v16 = 0;
        v27 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 62), 0, 0, 0);
        if ( !v27 )
        {
LABEL_81:
          v15 = WPP_GLOBAL_Control;
LABEL_82:
          if ( v15 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v15 + 108) & 4) != 0
            && *((_BYTE *)v15 + 105) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)v15 + 12), 118, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v16);
          }
          goto LABEL_86;
        }
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 117, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v27);
        }
        v26 = v27;
LABEL_80:
        v16 = (*(__int64 (__fastcall **)(CRepubCreateSegmentTask *, __int64))(*(_QWORD *)this + 48LL))(this, v26);
        goto LABEL_81;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
LABEL_68:
        v26 = v23;
        goto LABEL_80;
      }
      v25 = 116;
    }
    WPP_SF_d(*((_QWORD *)v24 + 12), v25, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v23);
    goto LABEL_68;
  }
  if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v19 + 108) & 4) != 0
    && *((_BYTE *)v19 + 105) >= 4u )
  {
    WPP_SF_DDd(
      *((_QWORD *)v19 + 12),
      114,
      WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
      v20,
      *((_DWORD *)this + 163),
      *(_DWORD *)(v6 + 56));
  }
  v16 = 0;
LABEL_86:
  operator delete(v4);
  return v16;
}

```

## disassembly

```asm
0x1800722a8  mov     [rsp+arg_18], rbx
0x1800722ad  push    rbp
0x1800722ae  push    rsi
0x1800722af  push    rdi
0x1800722b0  push    r12
0x1800722b2  push    r13
0x1800722b4  push    r14
0x1800722b6  push    r15
0x1800722b8  sub     rsp, 50h
0x1800722bc  mov     rdi, rcx
0x1800722bf  lea     rax, WPP_GLOBAL_Control
0x1800722c6  mov     r14b, 4
0x1800722c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722d0  cmp     rcx, rax
0x1800722d3  jz      short loc_1800722F6
0x1800722d5  test    [rcx+6Ch], r14b
0x1800722d9  jz      short loc_1800722F6
0x1800722db  cmp     [rcx+69h], r14b
0x1800722df  jb      short loc_1800722F6
0x1800722e1  mov     edx, 6Ah ; 'j'
0x1800722e6  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800722ed  mov     rcx, [rcx+60h]
0x1800722f1  call    WPP_SF_
0x1800722f6  xor     r12d, r12d
0x1800722f9  xor     r13d, r13d
0x1800722fc  xor     ebx, ebx
0x1800722fe  mov     [rsp+88h+arg_10], rbx
0x180072306  mov     rax, [rdi+258h]
0x18007230d  mov     r15, [rax+10h]
0x180072311  lea     rcx, [rax+18h]
0x180072315  mov     rax, [rcx]
0x180072318  mov     rax, [rax+48h]
0x18007231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072321  mov     ebp, eax
0x180072323  mov     rcx, [rdi+258h]
0x18007232a  add     rcx, 18h
0x18007232e  mov     rdx, [rcx]
0x180072331  mov     rax, [rdx+58h]
0x180072335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007233a  mov     dword ptr [rsp+88h+Size], eax
0x180072341  mov     rcx, [rdi+258h]
0x180072348  add     rcx, 18h
0x18007234c  mov     rdx, [rcx]
0x18007234f  mov     rax, [rdx+50h]
0x180072353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072358  mov     esi, eax
0x18007235a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072361  lea     r10, WPP_GLOBAL_Control
0x180072368  cmp     rcx, r10
0x18007236b  jz      short loc_1800723D5
0x18007236d  test    [rcx+6Ch], r14b
0x180072371  jz      short loc_1800723A1
0x180072373  cmp     byte ptr [rcx+69h], 3
0x180072377  jb      short loc_1800723A1
0x180072379  lea     edx, [rbx+6Bh]
0x18007237c  mov     r9d, [rdi+28Ch]
0x180072383  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18007238a  mov     rcx, [rcx+60h]
0x18007238e  call    WPP_SF_d
0x180072393  mov     rcx, cs:WPP_GLOBAL_Control
0x18007239a  lea     r10, WPP_GLOBAL_Control
0x1800723a1  cmp     rcx, r10
0x1800723a4  jz      short loc_1800723D5
0x1800723a6  test    [rcx+6Ch], r14b
0x1800723aa  jz      short loc_1800723D5
0x1800723ac  cmp     byte ptr [rcx+69h], 3
0x1800723b0  jb      short loc_1800723D5
0x1800723b2  mov     edx, 6Ch ; 'l'
0x1800723b7  mov     r9d, [rdi+298h]
0x1800723be  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800723c5  mov     rcx, [rcx+60h]
0x1800723c9  call    WPP_SF_d
0x1800723ce  lea     r10, WPP_GLOBAL_Control
0x1800723d5  lea     eax, [rbp-1]
0x1800723d8  add     eax, esi
0x1800723da  xor     edx, edx
0x1800723dc  div     esi
0x1800723de  mov     r14d, eax
0x1800723e1  mov     r9d, [rdi+28Ch]
0x1800723e8  lea     rsi, [rdi+298h]
0x1800723ef  mov     r8d, [rsi]
0x1800723f2  test    r8b, 2
0x1800723f6  setz    dl
0x1800723f9  test    r9b, 2
0x1800723fd  setnz   cl
0x180072400  test    cl, dl
0x180072402  jz      short loc_180072410
0x180072404  mov     bpl, 1
0x180072407  or      r8d, 2
0x18007240b  mov     [rsi], r8d
0x18007240e  jmp     short loc_180072413
0x180072410  xor     bpl, bpl
0x180072413  mov     byte ptr [rdi+289h], 0
0x18007241a  test    r9b, 1
0x18007241e  jz      short loc_18007248C
0x180072420  test    r8b, 40h
0x180072424  jnz     short loc_18007248C
0x180072426  cmp     r14d, 1
0x18007242a  jbe     short loc_18007246A
0x18007242c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072433  cmp     rcx, r10
0x180072436  jz      short loc_180072460
0x180072438  test    byte ptr [rcx+6Ch], 4
0x18007243c  jz      short loc_180072460
0x18007243e  cmp     byte ptr [rcx+69h], 1
0x180072442  jb      short loc_180072460
0x180072444  mov     edx, 6Dh ; 'm'
0x180072449  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180072450  mov     rcx, [rcx+60h]
0x180072454  call    WPP_SF_
0x180072459  mov     rcx, cs:WPP_GLOBAL_Control
0x180072460  mov     esi, 57h ; 'W'
0x180072465  jmp     loc_180072806
0x18007246a  mov     bpl, 1
0x18007246d  or      r8d, 40h
0x180072471  mov     [rsi], r8d
0x180072474  mov     rax, [rdi+2B0h]
0x18007247b  mov     byte ptr [rax], 0FFh
0x18007247e  mov     r13d, [rdi+29Ch]
0x180072485  mov     r12, [rdi+2B0h]
0x18007248c  test    byte ptr [rdi+28Ch], 5
0x180072493  setz    cl
0x180072496  test    dword ptr [rsi], 100h
0x18007249c  setnz   al
0x18007249f  test    al, cl
0x1800724a1  jz      short loc_18007250A
0x1800724a3  mov     bpl, 1
0x1800724a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724ad  cmp     rcx, r10
0x1800724b0  jz      short loc_1800724D3
0x1800724b2  test    byte ptr [rcx+6Ch], 4
0x1800724b6  jz      short loc_1800724D3
0x1800724b8  cmp     byte ptr [rcx+69h], 4
0x1800724bc  jb      short loc_1800724D3
0x1800724be  mov     edx, 6Eh ; 'n'
0x1800724c3  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800724ca  mov     rcx, [rcx+60h]
0x1800724ce  call    WPP_SF_
0x1800724d3  btr     dword ptr [rsi], 8
0x1800724d7  mov     ebx, dword ptr [rsp+88h+Size]
0x1800724de  mov     ecx, ebx; unsigned __int64
0x1800724e0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800724e5  mov     rdx, rax
0x1800724e8  lea     rcx, [rsp+88h+arg_10]
0x1800724f0  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x1800724f5  mov     r8d, ebx; Size
0x1800724f8  xor     edx, edx; Val
0x1800724fa  mov     rbx, [rsp+88h+arg_10]
0x180072502  mov     rcx, rbx; void *
0x180072505  call    memset_0
0x18007250a  cmp     dword ptr [r15+38h], 0
0x18007250f  jbe     short loc_180072551
0x180072511  test    byte ptr [rsi], 80h
0x180072514  jz      short loc_180072551
0x180072516  mov     bpl, 1
0x180072519  mov     rcx, cs:WPP_GLOBAL_Control
0x180072520  lea     rax, WPP_GLOBAL_Control
0x180072527  cmp     rcx, rax
0x18007252a  jz      short loc_18007254D
0x18007252c  test    byte ptr [rcx+6Ch], 4
0x180072530  jz      short loc_18007254D
0x180072532  cmp     byte ptr [rcx+69h], 4
0x180072536  jb      short loc_18007254D
0x180072538  mov     edx, 6Fh ; 'o'
0x18007253d  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180072544  mov     rcx, [rcx+60h]
0x180072548  call    WPP_SF_
0x18007254d  btr     dword ptr [rsi], 7
0x180072551  mov     r9d, [rsi]
0x180072554  bt      r9d, 9
0x180072559  setb    cl
0x18007255c  test    byte ptr [rdi+28Ch], 8
0x180072563  setz    al
0x180072566  test    al, cl
0x180072568  jz      short loc_1800725A8
0x18007256a  mov     bpl, 1
0x18007256d  mov     rcx, cs:WPP_GLOBAL_Control
0x180072574  lea     rax, WPP_GLOBAL_Control
0x18007257b  cmp     rcx, rax
0x18007257e  jz      short loc_1800725A1
0x180072580  test    byte ptr [rcx+6Ch], 4
0x180072584  jz      short loc_1800725A1
0x180072586  cmp     byte ptr [rcx+69h], 4
0x18007258a  jb      short loc_1800725A1
0x18007258c  mov     edx, 70h ; 'p'
0x180072591  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180072598  mov     rcx, [rcx+60h]
0x18007259c  call    WPP_SF_
0x1800725a1  btr     dword ptr [rsi], 9
0x1800725a5  mov     r9d, [rsi]
0x1800725a8  mov     r10, cs:WPP_GLOBAL_Control
0x1800725af  lea     rax, WPP_GLOBAL_Control
0x1800725b6  cmp     r10, rax
0x1800725b9  jz      short loc_1800725E5
0x1800725bb  test    byte ptr [r10+6Ch], 4
0x1800725c0  jz      short loc_1800725E5
0x1800725c2  cmp     byte ptr [r10+69h], 3
0x1800725c7  jb      short loc_1800725E5
0x1800725c9  mov     edx, 71h ; 'q'
0x1800725ce  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800725d5  mov     rcx, [r10+60h]
0x1800725d9  call    WPP_SF_d
0x1800725de  mov     r10, cs:WPP_GLOBAL_Control
0x1800725e5  mov     r11d, [rsi]
0x1800725e8  mov     eax, r11d
0x1800725eb  and     al, 94h
0x1800725ed  cmp     al, 10h
0x1800725ef  jnz     short loc_18007263C
0x1800725f1  xor     r9d, r9d
0x1800725f4  cmp     r9d, r14d
0x1800725f7  jnb     short loc_18007263C
0x1800725f9  mov     r8d, r9d
0x1800725fc  shr     r8, 3
0x180072600  mov     rax, [rdi+2A8h]
0x180072607  movzx   edx, byte ptr [r8+rax]
0x18007260c  not     edx
0x18007260e  mov     rax, [rdi+2B0h]
0x180072615  movzx   ecx, byte ptr [r8+rax]
0x18007261a  and     edx, ecx
0x18007261c  mov     rax, [rdi+2A0h]
0x180072623  test    [r8+rax], dl
0x180072627  jnz     short loc_18007262E
0x180072629  inc     r9d
0x18007262c  jmp     short loc_1800725F4
0x18007262e  mov     byte ptr [rdi+289h], 1
0x180072635  mov     r10, cs:WPP_GLOBAL_Control
0x18007263c  test    bpl, bpl
0x18007263f  jnz     short loc_18007268C
0x180072641  lea     rax, WPP_GLOBAL_Control
0x180072648  cmp     r10, rax
0x18007264b  jz      short loc_180072685
0x18007264d  test    byte ptr [r10+6Ch], 4
0x180072652  jz      short loc_180072685
0x180072654  cmp     byte ptr [r10+69h], 4
0x180072659  jb      short loc_180072685
0x18007265b  mov     edx, 72h ; 'r'
0x180072660  mov     eax, [r15+38h]
0x180072664  mov     [rsp+88h+var_60], eax
0x180072668  mov     eax, [rdi+28Ch]
0x18007266e  mov     dword ptr [rsp+88h+pcbActual], eax
0x180072672  mov     r9d, r11d
0x180072675  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18007267c  mov     rcx, [r10+60h]
0x180072680  call    WPP_SF_DDd
0x180072685  xor     esi, esi
0x180072687  jmp     loc_180072837
0x18007268c  mov     eax, [rdi+180h]
0x180072692  mov     [rsp+88h+csetcolumn], eax
0x180072699  lea     rdx, [r15+30h]
0x18007269d  xor     eax, eax
0x18007269f  cmp     [r15+38h], eax
0x1800726a3  cmovbe  rdx, rax; struct TnoHash *
0x1800726a7  lea     rax, [rsp+88h+csetcolumn]
0x1800726af  mov     [rsp+88h+var_48], rax; unsigned int *
0x1800726b4  mov     rax, [rdi+190h]
0x1800726bb  mov     [rsp+88h+var_50], rax; struct JET_SETCOLUMN *
0x1800726c0  mov     [rsp+88h+var_58], rbx; unsigned __int8 *
0x1800726c5  mov     eax, dword ptr [rsp+88h+Size]
0x1800726cc  mov     [rsp+88h+var_60], eax; unsigned int
0x1800726d0  mov     [rsp+88h+pcbActual], r12; unsigned __int8 *
0x1800726d5  mov     r9d, r13d; unsigned int
0x1800726d8  mov     r8, rsi; unsigned int *
0x1800726db  mov     rcx, rdi; this
0x1800726de  call    ?InitializeCatalogTableSetColumns@CRepubCreateSegmentTask@@IEAAXPEBVTnoHash@@PEAKKPEBEK2PEAUJET_SETCOLUMN@@1@Z; CRepubCreateSegmentTask::InitializeCatalogTableSetColumns(TnoHash const *,ulong *,ulong,uchar const *,ulong,uchar const *,JET_SETCOLUMN *,ulong *)
0x1800726e3  mov     r8d, 2; prep
0x1800726e9  mov     rdx, [rdi+1F0h]; tableid
0x1800726f0  mov     rcx, [rdi+178h]; sesid
0x1800726f7  call    cs:__imp_JetPrepareUpdate
0x1800726fd  mov     esi, eax
0x1800726ff  test    eax, eax
0x180072701  jz      short loc_180072741
0x180072703  mov     rcx, cs:WPP_GLOBAL_Control
0x18007270a  lea     rax, WPP_GLOBAL_Control
0x180072711  cmp     rcx, rax
0x180072714  jz      short loc_18007273A
0x180072716  test    byte ptr [rcx+6Ch], 4
0x18007271a  jz      short loc_18007273A
0x18007271c  cmp     byte ptr [rcx+69h], 1
0x180072720  jb      short loc_18007273A
0x180072722  mov     edx, 73h ; 's'
0x180072727  mov     r9d, esi
0x18007272a  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180072731  mov     rcx, [rcx+60h]
0x180072735  call    WPP_SF_d
0x18007273a  mov     edx, esi
0x18007273c  jmp     loc_1800727EE
0x180072741  mov     r9d, [rsp+88h+csetcolumn]; csetcolumn
0x180072749  mov     r8, [rdi+190h]; psetcolumn
0x180072750  mov     rdx, [rdi+1F0h]; tableid
0x180072757  mov     rcx, [rdi+178h]; sesid
0x18007275e  call    cs:__imp_JetSetColumns
0x180072764  mov     esi, eax
0x180072766  test    eax, eax
0x180072768  jz      short loc_180072790
0x18007276a  mov     rcx, cs:WPP_GLOBAL_Control
0x180072771  lea     rax, WPP_GLOBAL_Control
0x180072778  cmp     rcx, rax
0x18007277b  jz      short loc_18007273A
0x18007277d  test    byte ptr [rcx+6Ch], 4
0x180072781  jz      short loc_18007273A
  ... truncated ...
```
