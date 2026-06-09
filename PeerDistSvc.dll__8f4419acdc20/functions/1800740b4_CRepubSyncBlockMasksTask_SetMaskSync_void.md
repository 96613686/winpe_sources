# CRepubSyncBlockMasksTask::SetMaskSync(void)

- ea: `0x1800740b4`
- end: `0x1800748db`
- name: `?SetMaskSync@CRepubSyncBlockMasksTask@@IEAAKXZ`
- size: `2087`
- prototype: `unsigned int __fastcall(CRepubSyncBlockMasksTask *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18006e540`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180004374`
- `0x180008290`
- `0x18001fc30`
- `0x1800521d8`
- `0x1800740b4`
- `0x180144876`
- `0x180144882`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180074775`
- `ESENT!JetPrepareUpdate` at `0x180074775`
- `ESENT!JetSetColumns` at `0x1800747d9`
- `ESENT!JetSetColumns` at `0x1800747d9`
- `ESENT!JetRetrieveColumns` at `0x18007425d`
- `ESENT!JetRetrieveColumns` at `0x18007425d`
- `ESENT!JetUpdate` at `0x180074825`
- `ESENT!JetUpdate` at `0x180074825`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubSyncBlockMasksTask::SetMaskSync(CRepubSyncBlockMasksTask *this)
{
  void *v2; // rbx
  void *v3; // rdi
  int v4; // edx
  int v5; // ecx
  __int64 v6; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rax
  unsigned int Columns; // r14d
  __int64 v15; // rdx
  unsigned int v16; // r15d
  char v17; // r12
  unsigned int v18; // r14d
  CHostedCacheMsgEncoding *v19; // rcx
  int v20; // eax
  __int64 i; // r9
  int v22; // eax
  unsigned __int64 v23; // rcx
  int v24; // eax
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // r14d
  __int64 v28; // r8
  int v29; // edx
  int v30; // ecx
  __int64 v31; // rax
  __int64 v32; // r9
  int v33; // edx
  int v34; // ecx
  __int64 v35; // r8
  __int64 v36; // rax
  char v37; // dl
  char v38; // dl
  int v39; // ecx
  __int64 v40; // rdx
  __int64 v41; // rax
  int v42; // ecx
  __int64 v43; // rdx
  __int64 v44; // rax
  unsigned int v45; // r12d
  unsigned int v46; // r15d
  CHostedCacheMsgEncoding *v47; // rcx
  __int64 v48; // rdx
  __int64 v50; // [rsp+30h] [rbp-18h] BYREF
  __int16 v51; // [rsp+38h] [rbp-10h]
  int v52; // [rsp+90h] [rbp+48h] BYREF
  __int64 v53; // [rsp+98h] [rbp+50h] BYREF
  void *v54; // [rsp+A0h] [rbp+58h]
  void *v55; // [rsp+A8h] [rbp+60h]

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 193, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
  }
  v2 = operator new[](*((unsigned int *)this + 114));
  v54 = v2;
  memset_0(v2, 0, *((unsigned int *)this + 114));
  v3 = operator new[](*((unsigned int *)this + 114));
  v55 = v3;
  memset_0(v3, 0, *((unsigned int *)this + 114));
  v52 = 0;
  v53 = 0;
  v4 = *((_DWORD *)this + 114);
  v5 = *(_DWORD *)(*((_QWORD *)this + 51) + 880LL);
  v6 = *((_QWORD *)this + 49);
  *(_OWORD *)v6 = 0;
  *(_OWORD *)(v6 + 16) = 0;
  *(_OWORD *)(v6 + 32) = 0;
  *(_DWORD *)v6 = v5;
  *(_DWORD *)(v6 + 16) = v4;
  *(_QWORD *)(v6 + 8) = v2;
  *(_DWORD *)(v6 + 32) = 1;
  v7 = *((_DWORD *)this + 114);
  v8 = *(_DWORD *)(*((_QWORD *)this + 51) + 884LL);
  v9 = *((_QWORD *)this + 49);
  *(_OWORD *)(v9 + 48) = 0;
  *(_OWORD *)(v9 + 64) = 0;
  *(_OWORD *)(v9 + 80) = 0;
  *(_DWORD *)(v9 + 48) = v8;
  *(_DWORD *)(v9 + 64) = v7;
  *(_QWORD *)(v9 + 56) = v3;
  *(_DWORD *)(v9 + 80) = 1;
  v10 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
  v11 = *((_QWORD *)this + 49);
  *(_OWORD *)(v11 + 96) = 0;
  *(_OWORD *)(v11 + 112) = 0;
  *(_OWORD *)(v11 + 128) = 0;
  *(_DWORD *)(v11 + 96) = v10;
  *(_DWORD *)(v11 + 112) = 4;
  *(_QWORD *)(v11 + 104) = &v52;
  *(_DWORD *)(v11 + 128) = 1;
  v12 = *(_DWORD *)(*((_QWORD *)this + 51) + 840LL);
  v13 = *((_QWORD *)this + 49);
  *(_OWORD *)(v13 + 144) = 0;
  *(_OWORD *)(v13 + 160) = 0;
  *(_OWORD *)(v13 + 176) = 0;
  *(_DWORD *)(v13 + 144) = v12;
  *(_DWORD *)(v13 + 160) = 8;
  *(_QWORD *)(v13 + 152) = &v53;
  *(_DWORD *)(v13 + 176) = 1;
  Columns = JetRetrieveColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_RETRIEVECOLUMN **)this + 49), 4u);
  if ( Columns )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 194, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, Columns);
    }
    v15 = Columns;
    goto LABEL_103;
  }
  v16 = 0;
  v17 = *((_BYTE *)this + 488);
  if ( v17
    || *((_BYTE *)this + 489)
    || (v18 = *((_DWORD *)this + 114), memcmp_0(*((const void **)this + 59), v2, v18))
    || memcmp_0(*((const void **)this + 60), v3, v18) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 115); i = (unsigned int)(i + 1) )
    {
      if ( v17 )
      {
        v22 = 1 << (i & 7);
        v23 = (unsigned __int64)(unsigned int)i >> 3;
        if ( ((unsigned __int8)v22 & *((_BYTE *)v2 + v23)) == 0
          && ((unsigned __int8)v22 & *(_BYTE *)(v23 + *((_QWORD *)this + 59))) != 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v26 = 196;
            goto LABEL_33;
          }
LABEL_34:
          v27 = 87;
          goto LABEL_105;
        }
      }
      if ( *((_BYTE *)this + 489) )
      {
        v24 = 1 << (i & 7);
        v25 = (unsigned __int64)(unsigned int)i >> 3;
        if ( ((unsigned __int8)v24 & *((_BYTE *)v2 + v25)) == 0
          && ((unsigned __int8)v24 & *(_BYTE *)(v25 + *((_QWORD *)this + 60))) != 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v26 = 197;
LABEL_33:
            WPP_SF_d(*((_QWORD *)v19 + 12), v26, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, i);
            v19 = WPP_GLOBAL_Control;
          }
          goto LABEL_34;
        }
      }
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      v50 = *((_QWORD *)this + 60);
      v51 = *((_WORD *)this + 228);
      WPP_SF__HEX_(*((_QWORD *)WPP_GLOBAL_Control + 12), 198, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, &v50);
      v19 = WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)this + 488) )
    {
      v28 = *((_QWORD *)this + 59);
      v29 = *((_DWORD *)this + 114);
      v30 = *(_DWORD *)(*((_QWORD *)this + 51) + 880LL);
      v31 = *((_QWORD *)this + 50);
      *(_DWORD *)(v31 + 4) = 0;
      *(_QWORD *)(v31 + 20) = 0;
      *(_QWORD *)(v31 + 32) = 0;
      *(_DWORD *)v31 = v30;
      *(_DWORD *)(v31 + 16) = v29;
      *(_QWORD *)(v31 + 8) = v28;
      *(_DWORD *)(v31 + 28) = 1;
      *(_DWORD *)(*((_QWORD *)this + 50) + 20LL) = 4;
      v16 = 1;
      v19 = WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)this + 489) )
    {
      v32 = *((_QWORD *)this + 60);
      v33 = *((_DWORD *)this + 114);
      v34 = *(_DWORD *)(*((_QWORD *)this + 51) + 884LL);
      v35 = 5LL * v16;
      v36 = *((_QWORD *)this + 50);
      *(_DWORD *)(v36 + 8 * v35 + 4) = 0;
      *(_QWORD *)(v36 + 8 * v35 + 20) = 0;
      *(_QWORD *)(v36 + 8 * v35 + 32) = 0;
      *(_DWORD *)(v36 + 8 * v35) = v34;
      *(_DWORD *)(v36 + 8 * v35 + 16) = v33;
      *(_QWORD *)(v36 + 8 * v35 + 8) = v32;
      *(_DWORD *)(v36 + 8 * v35 + 28) = 1;
      *(_DWORD *)(*((_QWORD *)this + 50) + 8 * v35 + 20) = 4;
      ++v16;
      v19 = WPP_GLOBAL_Control;
    }
    v20 = v52;
    if ( (v52 & 4) == 0 && *((_BYTE *)this + 464) )
    {
      *((_BYTE *)this + 465) = 1;
      v20 |= 4u;
      v52 = v20;
      v19 = WPP_GLOBAL_Control;
    }
    v37 = *((_BYTE *)this + 466);
    if ( (v20 & 0x10) != 0 )
    {
      if ( !v37 )
      {
        *((_BYTE *)this + 467) = 1;
        v20 &= ~0x10u;
        v52 = v20;
        goto LABEL_55;
      }
    }
    else if ( v37 )
    {
      *((_BYTE *)this + 467) = 1;
      v20 |= 0x10u;
      v52 = v20;
      v19 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 195, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
      v20 = v52;
LABEL_55:
      v19 = WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    v20 = v52;
  }
LABEL_56:
  v27 = 0;
  v38 = 0;
  if ( (v20 & 2) == 0 && *((_BYTE *)this + 490) )
  {
    if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v19 + 108) & 4) != 0
      && *((_BYTE *)v19 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v19 + 12), 199, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
      v20 = v52;
      v19 = WPP_GLOBAL_Control;
    }
    v20 |= 2u;
    v52 = v20;
    v38 = 1;
  }
  if ( (v20 & 8) == 0 && !*((_BYTE *)this + 491) )
  {
    if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v19 + 108) & 4) != 0
      && *((_BYTE *)v19 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v19 + 12), 200, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
      v20 = v52;
      v19 = WPP_GLOBAL_Control;
    }
    v52 = v20 | 8;
    v38 = 1;
  }
  if ( *((_BYTE *)this + 467) || *((_BYTE *)this + 465) || v38 )
  {
    v39 = *(_DWORD *)(*((_QWORD *)this + 51) + 872LL);
    v40 = 5LL * v16;
    v41 = *((_QWORD *)this + 50);
    *(_DWORD *)(v41 + 8 * v40 + 4) = 0;
    *(_QWORD *)(v41 + 8 * v40 + 20) = 0;
    *(_QWORD *)(v41 + 8 * v40 + 32) = 0;
    *(_DWORD *)(v41 + 8 * v40) = v39;
    *(_DWORD *)(v41 + 8 * v40 + 16) = 4;
    *(_QWORD *)(v41 + 8 * v40 + 8) = &v52;
    *(_DWORD *)(v41 + 8 * v40 + 28) = 1;
    ++v16;
    v19 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 62) != v53 )
  {
    if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v19 + 108) & 4) != 0
      && *((_BYTE *)v19 + 105) >= 4u )
    {
      WPP_SF_qq(
        *((_QWORD *)v19 + 12),
        201,
        WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
        v53,
        *((_QWORD *)this + 62));
    }
    v42 = *(_DWORD *)(*((_QWORD *)this + 51) + 840LL);
    v43 = 5LL * v16;
    v44 = *((_QWORD *)this + 50);
    *(_DWORD *)(v44 + 8 * v43 + 4) = 0;
    *(_QWORD *)(v44 + 8 * v43 + 20) = 0;
    *(_QWORD *)(v44 + 8 * v43 + 32) = 0;
    *(_DWORD *)(v44 + 8 * v43) = v42;
    *(_DWORD *)(v44 + 8 * v43 + 16) = 8;
    *(_QWORD *)(v44 + 8 * v43 + 8) = (char *)this + 496;
    *(_DWORD *)(v44 + 8 * v43 + 28) = 1;
    ++v16;
    v19 = WPP_GLOBAL_Control;
  }
  if ( v16 )
  {
    if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v19 + 108) & 4) != 0
      && *((_BYTE *)v19 + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)v19 + 12), 202, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    }
    v45 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 2u);
    if ( v45 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 203, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v45);
      }
      v15 = v45;
      goto LABEL_103;
    }
    v46 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), v16);
    if ( v46 )
    {
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_102;
      }
      v48 = 204;
    }
    else
    {
      v46 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
      if ( !v46 )
      {
LABEL_104:
        v19 = WPP_GLOBAL_Control;
        goto LABEL_105;
      }
      v47 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        goto LABEL_102;
      }
      v48 = 205;
    }
    WPP_SF_d(*((_QWORD *)v47 + 12), v48, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v46);
LABEL_102:
    v15 = v46;
LABEL_103:
    v27 = (*(__int64 (__fastcall **)(CRepubSyncBlockMasksTask *, __int64))(*(_QWORD *)this + 48LL))(this, v15);
    goto LABEL_104;
  }
LABEL_105:
  if ( v19 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v19 + 108) & 4) != 0
    && *((_BYTE *)v19 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v19 + 12), 206, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v27);
  }
  operator delete(v3);
  operator delete(v2);
  return v27;
}

```

## disassembly

```asm
0x1800740b4  push    rbp
0x1800740b6  push    rbx
0x1800740b7  push    rsi
0x1800740b8  push    rdi
0x1800740b9  push    r12
0x1800740bb  push    r13
0x1800740bd  push    r14
0x1800740bf  push    r15
0x1800740c1  mov     rbp, rsp
0x1800740c4  sub     rsp, 48h
0x1800740c8  mov     rsi, rcx
0x1800740cb  lea     rax, WPP_GLOBAL_Control
0x1800740d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800740d9  cmp     rcx, rax
0x1800740dc  jz      short loc_1800740FF
0x1800740de  test    byte ptr [rcx+6Ch], 4
0x1800740e2  jz      short loc_1800740FF
0x1800740e4  cmp     byte ptr [rcx+69h], 4
0x1800740e8  jb      short loc_1800740FF
0x1800740ea  mov     edx, 0C1h
0x1800740ef  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800740f6  mov     rcx, [rcx+60h]
0x1800740fa  call    WPP_SF_
0x1800740ff  mov     ecx, [rsi+1C8h]; unsigned __int64
0x180074105  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007410a  mov     rbx, rax
0x18007410d  mov     [rbp+arg_10], rax
0x180074111  mov     r8d, [rsi+1C8h]; Size
0x180074118  xor     edx, edx; Val
0x18007411a  mov     rcx, rax; void *
0x18007411d  call    memset_0
0x180074122  mov     ecx, [rsi+1C8h]; unsigned __int64
0x180074128  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007412d  mov     rdi, rax
0x180074130  mov     [rbp+arg_18], rax
0x180074134  mov     r8d, [rsi+1C8h]; Size
0x18007413b  xor     edx, edx; Val
0x18007413d  mov     rcx, rax; void *
0x180074140  call    memset_0
0x180074145  xor     r13d, r13d
0x180074148  mov     [rbp+arg_0], r13d
0x18007414c  mov     [rbp+arg_8], r13
0x180074150  mov     edx, [rsi+1C8h]
0x180074156  mov     rax, [rsi+198h]
0x18007415d  mov     ecx, [rax+370h]
0x180074163  mov     rax, [rsi+188h]
0x18007416a  xorps   xmm0, xmm0
0x18007416d  movups  xmmword ptr [rax], xmm0
0x180074170  movups  xmmword ptr [rax+10h], xmm0
0x180074174  movups  xmmword ptr [rax+20h], xmm0
0x180074178  mov     [rax], ecx
0x18007417a  mov     [rax+10h], edx
0x18007417d  mov     [rax+8], rbx
0x180074181  lea     r15d, [r13+1]
0x180074185  mov     [rax+20h], r15d
0x180074189  mov     edx, [rsi+1C8h]
0x18007418f  mov     rax, [rsi+198h]
0x180074196  mov     ecx, [rax+374h]
0x18007419c  mov     rax, [rsi+188h]
0x1800741a3  movups  xmmword ptr [rax+30h], xmm0
0x1800741a7  movups  xmmword ptr [rax+40h], xmm0
0x1800741ab  movups  xmmword ptr [rax+50h], xmm0
0x1800741af  mov     [rax+30h], ecx
0x1800741b2  mov     [rax+40h], edx
0x1800741b5  mov     [rax+38h], rdi
0x1800741b9  mov     [rax+50h], r15d
0x1800741bd  mov     rax, [rsi+198h]
0x1800741c4  mov     ecx, [rax+368h]
0x1800741ca  mov     rax, [rsi+188h]
0x1800741d1  movups  xmmword ptr [rax+60h], xmm0
0x1800741d5  movups  xmmword ptr [rax+70h], xmm0
0x1800741d9  movups  xmmword ptr [rax+80h], xmm0
0x1800741e0  mov     [rax+60h], ecx
0x1800741e3  mov     dword ptr [rax+70h], 4
0x1800741ea  lea     rcx, [rbp+arg_0]
0x1800741ee  mov     [rax+68h], rcx
0x1800741f2  mov     [rax+80h], r15d
0x1800741f9  mov     rax, [rsi+198h]
0x180074200  mov     ecx, [rax+348h]
0x180074206  mov     rax, [rsi+188h]
0x18007420d  movups  xmmword ptr [rax+90h], xmm0
0x180074214  movups  xmmword ptr [rax+0A0h], xmm0
0x18007421b  movups  xmmword ptr [rax+0B0h], xmm0
0x180074222  mov     [rax+90h], ecx
0x180074228  mov     dword ptr [rax+0A0h], 8
0x180074232  lea     rcx, [rbp+arg_8]
0x180074236  mov     [rax+98h], rcx
0x18007423d  mov     [rax+0B0h], r15d
0x180074244  lea     r9d, [r13+4]; cretrievecolumn
0x180074248  mov     r8, [rsi+188h]; pretrievecolumn
0x18007424f  mov     rdx, [rsi+1A8h]; tableid
0x180074256  mov     rcx, [rsi+178h]; sesid
0x18007425d  call    cs:__imp_JetRetrieveColumns
0x180074263  mov     r14d, eax
0x180074266  test    eax, eax
0x180074268  jz      short loc_1800742A9
0x18007426a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074271  lea     rax, WPP_GLOBAL_Control
0x180074278  cmp     rcx, rax
0x18007427b  jz      short loc_1800742A1
0x18007427d  test    byte ptr [rcx+6Ch], 4
0x180074281  jz      short loc_1800742A1
0x180074283  cmp     [rcx+69h], r15b
0x180074287  jb      short loc_1800742A1
0x180074289  mov     edx, 0C2h
0x18007428e  mov     r9d, r14d
0x180074291  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180074298  mov     rcx, [rcx+60h]
0x18007429c  call    WPP_SF_d
0x1800742a1  mov     edx, r14d
0x1800742a4  jmp     loc_18007486C
0x1800742a9  mov     r15d, r13d
0x1800742ac  mov     r12b, [rsi+1E8h]
0x1800742b3  test    r12b, r12b
0x1800742b6  jnz     loc_18007433C
0x1800742bc  cmp     [rsi+1E9h], r13b
0x1800742c3  jnz     short loc_18007433C
0x1800742c5  mov     r14d, [rsi+1C8h]
0x1800742cc  mov     r8d, r14d; Size
0x1800742cf  mov     rdx, rbx; Buf2
0x1800742d2  mov     rcx, [rsi+1D8h]; Buf1
0x1800742d9  call    memcmp_0
0x1800742de  test    eax, eax
0x1800742e0  jnz     short loc_18007433C
0x1800742e2  mov     r8d, r14d; Size
0x1800742e5  mov     rdx, rdi; Buf2
0x1800742e8  mov     rcx, [rsi+1E0h]; Buf1
0x1800742ef  call    memcmp_0
0x1800742f4  test    eax, eax
0x1800742f6  jnz     short loc_18007433C
0x1800742f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800742ff  lea     r8, WPP_GLOBAL_Control
0x180074306  cmp     rcx, r8
0x180074309  jz      short loc_180074334
0x18007430b  test    byte ptr [rcx+6Ch], 4
0x18007430f  jz      short loc_180074334
0x180074311  cmp     byte ptr [rcx+69h], 4
0x180074315  jb      short loc_180074334
0x180074317  mov     edx, 0C3h
0x18007431c  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180074323  mov     rcx, [rcx+60h]
0x180074327  call    WPP_SF_
0x18007432c  mov     eax, [rbp+arg_0]
0x18007432f  jmp     loc_18007458E
0x180074334  mov     eax, [rbp+arg_0]
0x180074337  jmp     loc_18007459C
0x18007433c  mov     r9d, r13d
0x18007433f  mov     r8, [rsi+1D8h]
0x180074346  mov     rdx, [rsi+1E0h]
0x18007434d  mov     r14d, 1
0x180074353  cmp     r9d, [rsi+1CCh]
0x18007435a  jnb     loc_180074418
0x180074360  test    r12b, r12b
0x180074363  jz      short loc_180074382
0x180074365  mov     ecx, r9d
0x180074368  and     ecx, 7
0x18007436b  mov     eax, r14d
0x18007436e  shl     eax, cl
0x180074370  mov     ecx, r9d
0x180074373  shr     rcx, 3
0x180074377  test    [rcx+rbx], al
0x18007437a  jnz     short loc_180074382
0x18007437c  test    [rcx+r8], al
0x180074380  jnz     short loc_1800743AC
0x180074382  cmp     [rsi+1E9h], r13b
0x180074389  jz      short loc_1800743A7
0x18007438b  mov     ecx, r9d
0x18007438e  and     ecx, 7
0x180074391  mov     eax, r14d
0x180074394  shl     eax, cl
0x180074396  mov     ecx, r9d
0x180074399  shr     rcx, 3
0x18007439d  test    [rcx+rbx], al
0x1800743a0  jnz     short loc_1800743A7
0x1800743a2  test    [rcx+rdx], al
0x1800743a5  jnz     short loc_1800743F2
0x1800743a7  add     r9d, r14d
0x1800743aa  jmp     short loc_180074353
0x1800743ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743b3  lea     rax, WPP_GLOBAL_Control
0x1800743ba  cmp     rcx, rax
0x1800743bd  jz      short loc_1800743E7
0x1800743bf  test    byte ptr [rcx+6Ch], 4
0x1800743c3  jz      short loc_1800743E7
0x1800743c5  cmp     [rcx+69h], r14b
0x1800743c9  jb      short loc_1800743E7
0x1800743cb  mov     edx, 0C4h
0x1800743d0  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800743d7  mov     rcx, [rcx+60h]
0x1800743db  call    WPP_SF_d
0x1800743e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743e7  mov     r14d, 57h ; 'W'
0x1800743ed  jmp     loc_180074885
0x1800743f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800743f9  lea     rax, WPP_GLOBAL_Control
0x180074400  cmp     rcx, rax
0x180074403  jz      short loc_1800743E7
0x180074405  test    byte ptr [rcx+6Ch], 4
0x180074409  jz      short loc_1800743E7
0x18007440b  cmp     [rcx+69h], r14b
0x18007440f  jb      short loc_1800743E7
0x180074411  mov     edx, 0C5h
0x180074416  jmp     short loc_1800743D0
0x180074418  mov     rcx, cs:WPP_GLOBAL_Control
0x18007441f  lea     rax, WPP_GLOBAL_Control
0x180074426  cmp     rcx, rax
0x180074429  jz      short loc_180074466
0x18007442b  test    byte ptr [rcx+6Ch], 4
0x18007442f  jz      short loc_180074466
0x180074431  cmp     byte ptr [rcx+69h], 3
0x180074435  jb      short loc_180074466
0x180074437  mov     [rbp+var_18], rdx
0x18007443b  movzx   eax, word ptr [rsi+1C8h]
0x180074442  mov     [rbp+var_10], ax
0x180074446  mov     edx, 0C6h
0x18007444b  lea     r9, [rbp+var_18]
0x18007444f  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180074456  mov     rcx, [rcx+60h]
0x18007445a  call    WPP_SF__HEX_
0x18007445f  mov     rcx, cs:WPP_GLOBAL_Control
0x180074466  cmp     [rsi+1E8h], r13b
0x18007446d  jz      short loc_1800744C1
0x18007446f  mov     r8, [rsi+1D8h]
0x180074476  mov     edx, [rsi+1C8h]
0x18007447c  mov     rax, [rsi+198h]
0x180074483  mov     ecx, [rax+370h]
0x180074489  mov     rax, [rsi+190h]
0x180074490  mov     [rax+4], r13d
0x180074494  mov     [rax+14h], r13
0x180074498  mov     [rax+20h], r13
0x18007449c  mov     [rax], ecx
0x18007449e  mov     [rax+10h], edx
0x1800744a1  mov     [rax+8], r8
0x1800744a5  mov     [rax+1Ch], r14d
0x1800744a9  mov     rax, [rsi+190h]
0x1800744b0  mov     dword ptr [rax+14h], 4
0x1800744b7  mov     r15d, r14d
0x1800744ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800744c1  cmp     [rsi+1E9h], r13b
0x1800744c8  jz      short loc_18007452E
0x1800744ca  mov     r9, [rsi+1E0h]
0x1800744d1  mov     edx, [rsi+1C8h]
0x1800744d7  mov     rax, [rsi+198h]
0x1800744de  mov     ecx, [rax+374h]
0x1800744e4  mov     eax, r15d
0x1800744e7  lea     r8, [rax+rax*4]
0x1800744eb  mov     rax, [rsi+190h]
0x1800744f2  mov     [rax+r8*8+4], r13d
0x1800744f7  mov     [rax+r8*8+14h], r13
0x1800744fc  mov     [rax+r8*8+20h], r13
0x180074501  mov     [rax+r8*8], ecx
0x180074505  mov     [rax+r8*8+10h], edx
0x18007450a  mov     [rax+r8*8+8], r9
0x18007450f  mov     [rax+r8*8+1Ch], r14d
0x180074514  mov     rax, [rsi+190h]
0x18007451b  mov     dword ptr [rax+r8*8+14h], 4
0x180074524  add     r15d, r14d
0x180074527  mov     rcx, cs:WPP_GLOBAL_Control
0x18007452e  mov     eax, [rbp+arg_0]
0x180074531  test    al, 4
0x180074533  jnz     short loc_180074552
0x180074535  cmp     [rsi+1D0h], r13b
0x18007453c  jz      short loc_180074552
0x18007453e  mov     [rsi+1D1h], r14b
0x180074545  or      eax, 4
0x180074548  mov     [rbp+arg_0], eax
0x18007454b  mov     rcx, cs:WPP_GLOBAL_Control
0x180074552  mov     dl, [rsi+1D2h]
0x180074558  test    al, 10h
0x18007455a  jnz     short loc_18007457D
0x18007455c  lea     r8, WPP_GLOBAL_Control
0x180074563  test    dl, dl
0x180074565  jz      short loc_18007459C
0x180074567  mov     [rsi+1D3h], r14b
0x18007456e  or      eax, 10h
0x180074571  mov     [rbp+arg_0], eax
0x180074574  mov     rcx, cs:WPP_GLOBAL_Control
0x18007457b  jmp     short loc_18007459C
0x18007457d  test    dl, dl
0x18007457f  jnz     short loc_180074595
0x180074581  mov     [rsi+1D3h], r14b
0x180074588  and     eax, 0FFFFFFEFh
0x18007458b  mov     [rbp+arg_0], eax
0x18007458e  mov     rcx, cs:WPP_GLOBAL_Control
0x180074595  lea     r8, WPP_GLOBAL_Control
0x18007459c  mov     r14d, r13d
0x18007459f  mov     dl, r13b
0x1800745a2  test    al, 2
0x1800745a4  jnz     short loc_1800745EE
0x1800745a6  cmp     [rsi+1EAh], r13b
0x1800745ad  jz      short loc_1800745EE
0x1800745af  cmp     rcx, r8
0x1800745b2  jz      short loc_1800745E6
0x1800745b4  test    byte ptr [rcx+6Ch], 4
0x1800745b8  jz      short loc_1800745E6
0x1800745ba  cmp     byte ptr [rcx+69h], 4
0x1800745be  jb      short loc_1800745E6
0x1800745c0  mov     edx, 0C7h
0x1800745c5  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800745cc  mov     rcx, [rcx+60h]
  ... truncated ...
```
