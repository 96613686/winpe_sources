# CRepubWriteSegmentRangesTask::CreateNewValidRanges(void)

- ea: `0x180067614`
- end: `0x180067988`
- name: `?CreateNewValidRanges@CRepubWriteSegmentRangesTask@@IEAAKXZ`
- size: `884`
- prototype: `unsigned int __fastcall(CRepubWriteSegmentRangesTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18006e870`

## callees

- `0x180008290`
- `0x1800082d0`
- `0x180029404`
- `0x180067614`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800677df`
- `ESENT!JetPrepareUpdate` at `0x1800677df`
- `ESENT!JetSetColumns` at `0x180067809`
- `ESENT!JetSetColumns` at `0x180067809`
- `ESENT!JetUpdate` at `0x180067833`
- `ESENT!JetUpdate` at `0x180067833`

## pseudocode

```c
__int64 __fastcall CRepubWriteSegmentRangesTask::CreateNewValidRanges(CRepubWriteSegmentRangesTask *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  unsigned int *v3; // rdi
  unsigned int v4; // ebp
  __int64 v5; // r9
  _DWORD *v6; // rsi
  int v7; // r8d
  unsigned int v8; // r8d
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // r14d
  unsigned int v17; // eax
  unsigned int v18; // esi
  __int64 v19; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 559, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = (unsigned int *)*((_QWORD *)this + 57);
  v4 = 0;
  while ( 1 )
  {
    if ( !v3 )
      goto LABEL_44;
    v5 = *v3;
    v6 = v3 + 1;
    if ( !(_DWORD)v5 )
    {
      v7 = *((_DWORD *)this + 112);
      if ( *v6 == v7 )
        break;
    }
    v8 = *((_DWORD *)this + 113);
    if ( (unsigned int)v5 % v8 || *v6 % v8 )
    {
      if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)v2 + 108) & 4) != 0
        && *((_BYTE *)v2 + 105) >= 4u )
      {
        WPP_SF_DDd(*((_QWORD *)v2 + 12), 562, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v5, *v6, v8);
      }
      v9 = *((_QWORD *)this + 50);
      v10 = *(_DWORD *)(*((_QWORD *)this + 51) + 1072LL);
      *(_DWORD *)(v9 + 4) = 0;
      *(_QWORD *)(v9 + 20) = 0;
      *(_QWORD *)(v9 + 32) = 0;
      *(_DWORD *)v9 = v10;
      *(_DWORD *)(v9 + 16) = 8;
      *(_QWORD *)(v9 + 8) = (char *)this + 432;
      *(_DWORD *)(v9 + 28) = 1;
      v11 = *(_DWORD *)(*((_QWORD *)this + 51) + 1076LL);
      v12 = *((_QWORD *)this + 50);
      *(_DWORD *)(v12 + 44) = 0;
      *(_QWORD *)(v12 + 60) = 0;
      *(_QWORD *)(v12 + 72) = 0;
      *(_DWORD *)(v12 + 40) = v11;
      *(_DWORD *)(v12 + 56) = 4;
      *(_QWORD *)(v12 + 48) = v3;
      *(_DWORD *)(v12 + 68) = 1;
      v13 = *(_DWORD *)(*((_QWORD *)this + 51) + 1080LL);
      v14 = *((_QWORD *)this + 50);
      *(_DWORD *)(v14 + 84) = 0;
      *(_QWORD *)(v14 + 100) = 0;
      *(_QWORD *)(v14 + 112) = 0;
      *(_DWORD *)(v14 + 80) = v13;
      *(_DWORD *)(v14 + 96) = 4;
      *(_QWORD *)(v14 + 88) = v6;
      *(_DWORD *)(v14 + 108) = 1;
      v15 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0);
      v16 = v15;
      if ( v15 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 563, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v15);
        }
LABEL_41:
        v19 = v16;
LABEL_42:
        v4 = (*(__int64 (__fastcall **)(CRepubWriteSegmentRangesTask *, __int64))(*(_QWORD *)this + 48LL))(this, v19);
LABEL_43:
        v2 = WPP_GLOBAL_Control;
        goto LABEL_44;
      }
      v16 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 53), *((JET_SETCOLUMN **)this + 50), 3u);
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_DDd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            564,
            WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids,
            *v3,
            *v6,
            v16);
        }
        goto LABEL_41;
      }
      v17 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 53), 0, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 565, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v17);
        }
        v19 = v18;
        goto LABEL_42;
      }
      goto LABEL_22;
    }
    if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v2 + 108) & 4) != 0
      && *((_BYTE *)v2 + 105) >= 4u )
    {
      WPP_SF_DDd(*((_QWORD *)v2 + 12), 561, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v5, *v6, v8);
LABEL_22:
      v2 = WPP_GLOBAL_Control;
    }
    v3 = (unsigned int *)*((_QWORD *)v3 + 1);
  }
  if ( v2 == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)v2 + 108) & 4) != 0 && *((_BYTE *)v2 + 105) >= 4u )
  {
    WPP_SF_DDd(*((_QWORD *)v2 + 12), 560, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, 0, *v6, v7);
    goto LABEL_43;
  }
LABEL_44:
  if ( v2 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v2 + 108) & 4) != 0
    && *((_BYTE *)v2 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 566, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180067614  push    rbx
0x180067616  push    rbp
0x180067617  push    rsi
0x180067618  push    rdi
0x180067619  push    r13
0x18006761b  push    r14
0x18006761d  push    r15
0x18006761f  sub     rsp, 30h
0x180067623  mov     rbx, rcx
0x180067626  mov     rcx, cs:WPP_GLOBAL_Control
0x18006762d  lea     r13, WPP_GLOBAL_Control
0x180067634  mov     r15d, 4
0x18006763a  cmp     rcx, r13
0x18006763d  jz      short loc_18006766E
0x18006763f  test    [rcx+6Ch], r15b
0x180067643  jz      short loc_18006766E
0x180067645  cmp     [rcx+69h], r15b
0x180067649  jb      short loc_18006766E
0x18006764b  mov     r9, [rbx+1B0h]
0x180067652  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180067659  mov     rcx, [rcx+60h]
0x18006765d  mov     edx, 22Fh
0x180067662  call    WPP_SF_q
0x180067667  mov     rcx, cs:WPP_GLOBAL_Control
0x18006766e  mov     rdi, [rbx+1C8h]
0x180067675  xor     ebp, ebp
0x180067677  test    rdi, rdi
0x18006767a  jz      loc_18006794E
0x180067680  mov     r9d, [rdi]
0x180067683  lea     rsi, [rdi+4]
0x180067687  test    r9d, r9d
0x18006768a  jnz     short loc_18006769E
0x18006768c  mov     eax, [rsi]
0x18006768e  mov     r8d, [rbx+1C0h]
0x180067695  cmp     eax, r8d
0x180067698  jz      loc_18006784F
0x18006769e  mov     r8d, [rbx+1C4h]
0x1800676a5  xor     edx, edx
0x1800676a7  mov     eax, r9d
0x1800676aa  div     r8d
0x1800676ad  test    edx, edx
0x1800676af  jnz     short loc_180067701
0x1800676b1  mov     r10d, [rsi]
0x1800676b4  xor     edx, edx
0x1800676b6  mov     eax, r10d
0x1800676b9  div     r8d
0x1800676bc  test    edx, edx
0x1800676be  jnz     short loc_180067701
0x1800676c0  cmp     rcx, r13
0x1800676c3  jz      loc_180067846
0x1800676c9  test    [rcx+6Ch], r15b
0x1800676cd  jz      loc_180067846
0x1800676d3  cmp     [rcx+69h], r15b
0x1800676d7  jb      loc_180067846
0x1800676dd  mov     rcx, [rcx+60h]
0x1800676e1  mov     edx, 231h
0x1800676e6  mov     [rsp+68h+var_40], r8d
0x1800676eb  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800676f2  mov     dword ptr [rsp+68h+pcbActual], r10d
0x1800676f7  call    WPP_SF_DDd
0x1800676fc  jmp     loc_18006783F
0x180067701  cmp     rcx, r13
0x180067704  jz      short loc_180067732
0x180067706  test    [rcx+6Ch], r15b
0x18006770a  jz      short loc_180067732
0x18006770c  cmp     [rcx+69h], r15b
0x180067710  jb      short loc_180067732
0x180067712  mov     eax, [rsi]
0x180067714  mov     edx, 232h
0x180067719  mov     rcx, [rcx+60h]
0x18006771d  mov     [rsp+68h+var_40], r8d
0x180067722  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180067729  mov     dword ptr [rsp+68h+pcbActual], eax
0x18006772d  call    WPP_SF_DDd
0x180067732  mov     rax, [rbx+198h]
0x180067739  xor     r8d, r8d; prep
0x18006773c  mov     rdx, [rbx+190h]
0x180067743  mov     ecx, [rax+430h]
0x180067749  lea     rax, [rbx+1B0h]
0x180067750  mov     [rdx+4], ebp
0x180067753  mov     [rdx+14h], rbp
0x180067757  mov     [rdx+20h], rbp
0x18006775b  mov     [rdx], ecx
0x18006775d  mov     dword ptr [rdx+10h], 8
0x180067764  mov     [rdx+8], rax
0x180067768  mov     dword ptr [rdx+1Ch], 1
0x18006776f  mov     rax, [rbx+198h]
0x180067776  mov     ecx, [rax+434h]
0x18006777c  mov     rax, [rbx+190h]
0x180067783  mov     [rax+2Ch], ebp
0x180067786  mov     [rax+3Ch], rbp
0x18006778a  mov     [rax+48h], rbp
0x18006778e  mov     [rax+28h], ecx
0x180067791  mov     [rax+38h], r15d
0x180067795  mov     [rax+30h], rdi
0x180067799  mov     dword ptr [rax+44h], 1
0x1800677a0  mov     rax, [rbx+198h]
0x1800677a7  mov     ecx, [rax+438h]
0x1800677ad  mov     rax, [rbx+190h]
0x1800677b4  mov     [rax+54h], ebp
0x1800677b7  mov     [rax+64h], rbp
0x1800677bb  mov     [rax+70h], rbp
0x1800677bf  mov     [rax+50h], ecx
0x1800677c2  mov     [rax+60h], r15d
0x1800677c6  mov     [rax+58h], rsi
0x1800677ca  mov     dword ptr [rax+6Ch], 1
0x1800677d1  mov     rdx, [rbx+1A8h]; tableid
0x1800677d8  mov     rcx, [rbx+178h]; sesid
0x1800677df  call    cs:__imp_JetPrepareUpdate
0x1800677e5  mov     r14d, eax
0x1800677e8  test    eax, eax
0x1800677ea  jnz     loc_180067903
0x1800677f0  mov     r8, [rbx+190h]; psetcolumn
0x1800677f7  lea     r9d, [rax+3]; csetcolumn
0x1800677fb  mov     rdx, [rbx+1A8h]; tableid
0x180067802  mov     rcx, [rbx+178h]; sesid
0x180067809  call    cs:__imp_JetSetColumns
0x18006780f  mov     r14d, eax
0x180067812  test    eax, eax
0x180067814  jnz     loc_1800678C6
0x18006781a  mov     rdx, [rbx+1A8h]; tableid
0x180067821  xor     r9d, r9d; cbBookmark
0x180067824  mov     rcx, [rbx+178h]; sesid
0x18006782b  xor     r8d, r8d; pvBookmark
0x18006782e  mov     [rsp+68h+pcbActual], rbp; pcbActual
0x180067833  call    cs:__imp_JetUpdate
0x180067839  mov     esi, eax
0x18006783b  test    eax, eax
0x18006783d  jnz     short loc_180067892
0x18006783f  mov     rcx, cs:WPP_GLOBAL_Control
0x180067846  mov     rdi, [rdi+8]
0x18006784a  jmp     loc_180067677
0x18006784f  cmp     rcx, r13
0x180067852  jz      loc_180067977
0x180067858  test    [rcx+6Ch], r15b
0x18006785c  jz      loc_18006794E
0x180067862  cmp     [rcx+69h], r15b
0x180067866  jb      loc_18006794E
0x18006786c  mov     rcx, [rcx+60h]
0x180067870  mov     edx, 230h
0x180067875  mov     [rsp+68h+var_40], r8d
0x18006787a  xor     r9d, r9d
0x18006787d  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180067884  mov     dword ptr [rsp+68h+pcbActual], eax
0x180067888  call    WPP_SF_DDd
0x18006788d  jmp     loc_180067947
0x180067892  mov     rcx, cs:WPP_GLOBAL_Control
0x180067899  cmp     rcx, r13
0x18006789c  jz      short loc_1800678C2
0x18006789e  test    [rcx+6Ch], r15b
0x1800678a2  jz      short loc_1800678C2
0x1800678a4  cmp     byte ptr [rcx+69h], 1
0x1800678a8  jb      short loc_1800678C2
0x1800678aa  mov     rcx, [rcx+60h]
0x1800678ae  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800678b5  mov     edx, 235h
0x1800678ba  mov     r9d, esi
0x1800678bd  call    WPP_SF_d
0x1800678c2  mov     edx, esi
0x1800678c4  jmp     short loc_180067936
0x1800678c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800678cd  cmp     rcx, r13
0x1800678d0  jz      short loc_180067933
0x1800678d2  test    [rcx+6Ch], r15b
0x1800678d6  jz      short loc_180067933
0x1800678d8  cmp     byte ptr [rcx+69h], 1
0x1800678dc  jb      short loc_180067933
0x1800678de  mov     eax, [rsi]
0x1800678e0  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x1800678e7  mov     r9d, [rdi]
0x1800678ea  mov     edx, 234h
0x1800678ef  mov     rcx, [rcx+60h]
0x1800678f3  mov     [rsp+68h+var_40], r14d
0x1800678f8  mov     dword ptr [rsp+68h+pcbActual], eax
0x1800678fc  call    WPP_SF_DDd
0x180067901  jmp     short loc_180067933
0x180067903  mov     rcx, cs:WPP_GLOBAL_Control
0x18006790a  cmp     rcx, r13
0x18006790d  jz      short loc_180067933
0x18006790f  test    [rcx+6Ch], r15b
0x180067913  jz      short loc_180067933
0x180067915  cmp     byte ptr [rcx+69h], 1
0x180067919  jb      short loc_180067933
0x18006791b  mov     rcx, [rcx+60h]
0x18006791f  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x180067926  mov     edx, 233h
0x18006792b  mov     r9d, r14d
0x18006792e  call    WPP_SF_d
0x180067933  mov     edx, r14d
0x180067936  mov     rax, [rbx]
0x180067939  mov     rcx, rbx
0x18006793c  mov     rax, [rax+30h]
0x180067940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067945  mov     ebp, eax
0x180067947  mov     rcx, cs:WPP_GLOBAL_Control
0x18006794e  cmp     rcx, r13
0x180067951  jz      short loc_180067977
0x180067953  test    [rcx+6Ch], r15b
0x180067957  jz      short loc_180067977
0x180067959  cmp     [rcx+69h], r15b
0x18006795d  jb      short loc_180067977
0x18006795f  mov     rcx, [rcx+60h]
0x180067963  lea     r8, WPP_1f2b276da42e3b6f4616fda568e9cc5c_Traceguids
0x18006796a  mov     edx, 236h
0x18006796f  mov     r9d, ebp
0x180067972  call    WPP_SF_d
0x180067977  mov     eax, ebp
0x180067979  add     rsp, 30h
0x18006797d  pop     r15
0x18006797f  pop     r14
0x180067981  pop     r13
0x180067983  pop     rdi
0x180067984  pop     rsi
0x180067985  pop     rbp
0x180067986  pop     rbx
0x180067987  retn
```
