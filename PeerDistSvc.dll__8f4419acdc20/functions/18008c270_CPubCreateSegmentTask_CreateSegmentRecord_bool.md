# CPubCreateSegmentTask::CreateSegmentRecord(bool)

- ea: `0x18008c270`
- end: `0x18008c6c9`
- name: `?CreateSegmentRecord@CPubCreateSegmentTask@@IEAAK_N@Z`
- size: `1113`
- prototype: `unsigned int __fastcall(CPubCreateSegmentTask *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18008ee90`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800082d0`
- `0x18000ceac`
- `0x180018340`
- `0x18008c270`
- `0x18008def8`
- `0x18012d944`
- `0x180159010`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x18008c4e8`
- `ESENT!JetPrepareUpdate` at `0x18008c628`
- `ESENT!JetPrepareUpdate` at `0x18008c4e8`
- `ESENT!JetPrepareUpdate` at `0x18008c628`
- `ESENT!JetSetColumns` at `0x18008c552`
- `ESENT!JetSetColumns` at `0x18008c552`
- `ESENT!JetUpdate` at `0x18008c5bc`
- `ESENT!JetUpdate` at `0x18008c5bc`

## pseudocode

```c
__int64 __fastcall CPubCreateSegmentTask::CreateSegmentRecord(CPubCreateSegmentTask *this, unsigned __int8 a2)
{
  int v2; // ebp
  const wchar_t *v4; // r9
  __int64 v5; // rax
  __int64 v6; // r14
  unsigned int v7; // eax
  __int64 v8; // rcx
  CHostedCacheMsgEncoding *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int csetcolumn; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v19; // [rsp+A8h] [rbp+10h] BYREF
  unsigned int v20; // [rsp+B0h] [rbp+18h] BYREF

  v2 = a2;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v4 = L"Y";
    if ( !a2 )
      v4 = (const wchar_t *)L"N";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 159, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids, v4);
  }
  v5 = *((_QWORD *)this + 60);
  v6 = *(_QWORD *)(v5 + 16);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v5 + 24) + 72LL))(v5 + 24);
  v8 = *((_QWORD *)this + 60);
  v19 = v7;
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + 24) + 80LL))(v8 + 24);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 160, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
      {
        WPP_SF_q(*((_QWORD *)v9 + 12), 161, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
        {
          WPP_SF_q(*((_QWORD *)v9 + 12), 162, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
          v9 = WPP_GLOBAL_Control;
        }
        if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)v9 + 12), 163, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids, v19);
            v9 = WPP_GLOBAL_Control;
          }
          if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v9 + 108) & 4) != 0 && *((_BYTE *)v9 + 105) >= 3u )
            {
              WPP_SF_q(*((_QWORD *)v9 + 12), 164, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v9 + 108) & 4) != 0
              && *((_BYTE *)v9 + 105) >= 3u )
            {
              WPP_SF_(*((_QWORD *)v9 + 12), 165, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
            }
          }
        }
      }
    }
  }
  PeerDistTelemetryPublishSegment(**((_QWORD **)this + 61), *((_QWORD *)this + 63), v19, *((_QWORD *)this + 64));
  csetcolumn = *((_DWORD *)this + 96);
  CPubCreateSegmentTask::InitializeSegmentTableSetColumns(
    this,
    *((unsigned __int64 **)this + 61),
    (unsigned __int64 *)this + 63,
    (unsigned __int64 *)this + 62,
    (unsigned __int64 *)this + 64,
    (const struct TnoHash *)(v6 + 48),
    (const struct TnoHashKey *)(v6 + 80),
    &v19,
    &v20,
    *((struct JET_SETCOLUMN **)this + 50),
    &csetcolumn);
  v10 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 55), 2 * v2);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(CPubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v10);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v13 = 166;
LABEL_56:
      WPP_SF_Dd(*((_QWORD *)v12 + 12), v13, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
    }
  }
  else
  {
    v14 = JetSetColumns(*((_QWORD *)this + 47), *((_QWORD *)this + 55), *((JET_SETCOLUMN **)this + 50), csetcolumn);
    if ( v14 )
    {
      v11 = (*(__int64 (__fastcall **)(CPubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v14);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v13 = 167;
        goto LABEL_56;
      }
    }
    else
    {
      v15 = JetUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 55), 0, 0, 0);
      if ( v15 == -1605 )
      {
        v11 = (*(__int64 (__fastcall **)(CPubCreateSegmentTask *, __int64))(*(_QWORD *)this + 24LL))(this, 4294965691LL);
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 168, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids);
        }
        v16 = JetPrepareUpdate(*((_QWORD *)this + 47), *((_QWORD *)this + 55), 3u);
        if ( v16 )
        {
          v11 = (*(__int64 (__fastcall **)(CPubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v16);
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v13 = 169;
            goto LABEL_56;
          }
        }
      }
      else
      {
        v11 = 0;
        if ( v15 )
        {
          v11 = (*(__int64 (__fastcall **)(CPubCreateSegmentTask *, _QWORD))(*(_QWORD *)this + 24LL))(this, v15);
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            v13 = 170;
            goto LABEL_56;
          }
        }
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18008c270  mov     [rsp+arg_18], rbx
0x18008c275  push    rbp
0x18008c276  push    rsi
0x18008c277  push    rdi
0x18008c278  push    r12
0x18008c27a  push    r13
0x18008c27c  push    r14
0x18008c27e  push    r15
0x18008c280  sub     rsp, 60h
0x18008c284  movzx   ebp, dl
0x18008c287  mov     rsi, rcx
0x18008c28a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c291  lea     r13, WPP_GLOBAL_Control
0x18008c298  lea     r12, WPP_44a976264dd93922b20292445dd7a2ed_Traceguids
0x18008c29f  mov     r15b, 4
0x18008c2a2  cmp     rcx, r13
0x18008c2a5  jz      short loc_18008C2D8
0x18008c2a7  test    [rcx+6Ch], r15b
0x18008c2ab  jz      short loc_18008C2D8
0x18008c2ad  cmp     [rcx+69h], r15b
0x18008c2b1  jb      short loc_18008C2D8
0x18008c2b3  mov     rcx, [rcx+60h]
0x18008c2b7  lea     rax, aN; "N"
0x18008c2be  test    dl, dl
0x18008c2c0  lea     r9, aY; "Y"
0x18008c2c7  mov     edx, 9Fh
0x18008c2cc  mov     r8, r12
0x18008c2cf  cmovz   r9, rax
0x18008c2d3  call    WPP_SF_S
0x18008c2d8  mov     rax, [rsi+1E0h]
0x18008c2df  mov     r14, [rax+10h]
0x18008c2e3  lea     rcx, [rax+18h]
0x18008c2e7  mov     rax, [rcx]
0x18008c2ea  mov     rax, [rax+48h]
0x18008c2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2f3  mov     rcx, [rsi+1E0h]
0x18008c2fa  mov     [rsp+98h+arg_8], eax
0x18008c301  add     rcx, 18h
0x18008c305  mov     rax, [rcx]
0x18008c308  mov     rax, [rax+50h]
0x18008c30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c311  mov     [rsp+98h+arg_10], eax
0x18008c318  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c31f  mov     ebx, 3
0x18008c324  cmp     rcx, r13
0x18008c327  jz      loc_18008C439
0x18008c32d  test    [rcx+6Ch], r15b
0x18008c331  jz      short loc_18008C350
0x18008c333  cmp     [rcx+69h], bl
0x18008c336  jb      short loc_18008C350
0x18008c338  mov     rcx, [rcx+60h]
0x18008c33c  mov     edx, 0A0h
0x18008c341  mov     r8, r12
0x18008c344  call    WPP_SF_
0x18008c349  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c350  cmp     rcx, r13
0x18008c353  jz      loc_18008C439
0x18008c359  test    [rcx+6Ch], r15b
0x18008c35d  jz      short loc_18008C386
0x18008c35f  cmp     [rcx+69h], bl
0x18008c362  jb      short loc_18008C386
0x18008c364  mov     r9, [rsi+1E8h]
0x18008c36b  mov     edx, 0A1h
0x18008c370  mov     rcx, [rcx+60h]
0x18008c374  mov     r8, r12
0x18008c377  mov     r9, [r9]
0x18008c37a  call    WPP_SF_q
0x18008c37f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c386  cmp     rcx, r13
0x18008c389  jz      loc_18008C439
0x18008c38f  test    [rcx+6Ch], r15b
0x18008c393  jz      short loc_18008C3B9
0x18008c395  cmp     [rcx+69h], bl
0x18008c398  jb      short loc_18008C3B9
0x18008c39a  mov     r9, [rsi+1F8h]
0x18008c3a1  mov     edx, 0A2h
0x18008c3a6  mov     rcx, [rcx+60h]
0x18008c3aa  mov     r8, r12
0x18008c3ad  call    WPP_SF_q
0x18008c3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c3b9  cmp     rcx, r13
0x18008c3bc  jz      short loc_18008C439
0x18008c3be  test    [rcx+6Ch], r15b
0x18008c3c2  jz      short loc_18008C3E9
0x18008c3c4  cmp     [rcx+69h], bl
0x18008c3c7  jb      short loc_18008C3E9
0x18008c3c9  mov     r9d, [rsp+98h+arg_8]
0x18008c3d1  mov     edx, 0A3h
0x18008c3d6  mov     rcx, [rcx+60h]
0x18008c3da  mov     r8, r12
0x18008c3dd  call    WPP_SF_d
0x18008c3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c3e9  cmp     rcx, r13
0x18008c3ec  jz      short loc_18008C439
0x18008c3ee  test    [rcx+6Ch], r15b
0x18008c3f2  jz      short loc_18008C418
0x18008c3f4  cmp     [rcx+69h], bl
0x18008c3f7  jb      short loc_18008C418
0x18008c3f9  mov     r9, [rsi+200h]
0x18008c400  mov     edx, 0A4h
0x18008c405  mov     rcx, [rcx+60h]
0x18008c409  mov     r8, r12
0x18008c40c  call    WPP_SF_q
0x18008c411  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c418  cmp     rcx, r13
0x18008c41b  jz      short loc_18008C439
0x18008c41d  test    [rcx+6Ch], r15b
0x18008c421  jz      short loc_18008C439
0x18008c423  cmp     [rcx+69h], bl
0x18008c426  jb      short loc_18008C439
0x18008c428  mov     rcx, [rcx+60h]
0x18008c42c  mov     edx, 0A5h
0x18008c431  mov     r8, r12
0x18008c434  call    WPP_SF_
0x18008c439  mov     rcx, [rsi+1E8h]
0x18008c440  lea     rbx, [rsi+200h]
0x18008c447  mov     r9, [rbx]; unsigned __int64
0x18008c44a  lea     rdi, [rsi+1F8h]
0x18008c451  mov     r8d, [rsp+98h+arg_8]; unsigned int
0x18008c459  mov     rdx, [rdi]; unsigned __int64
0x18008c45c  mov     rcx, [rcx]; unsigned __int64
0x18008c45f  call    ?PeerDistTelemetryPublishSegment@@YAX_K0K0@Z; PeerDistTelemetryPublishSegment(unsigned __int64,unsigned __int64,ulong,unsigned __int64)
0x18008c464  mov     eax, [rsi+180h]
0x18008c46a  lea     rcx, [r14+50h]
0x18008c46e  mov     [rsp+98h+csetcolumn], eax
0x18008c475  lea     rdx, [r14+30h]
0x18008c479  lea     rax, [rsp+98h+csetcolumn]
0x18008c481  mov     r8, rdi; unsigned __int64 *
0x18008c484  mov     [rsp+98h+var_48], rax; unsigned int *
0x18008c489  lea     r9, [rsi+1F0h]; unsigned __int64 *
0x18008c490  mov     rax, [rsi+190h]
0x18008c497  mov     [rsp+98h+var_50], rax; struct JET_SETCOLUMN *
0x18008c49c  lea     rax, [rsp+98h+arg_10]
0x18008c4a4  mov     [rsp+98h+var_58], rax; unsigned int *
0x18008c4a9  lea     rax, [rsp+98h+arg_8]
0x18008c4b1  mov     [rsp+98h+var_60], rax; unsigned int *
0x18008c4b6  mov     [rsp+98h+var_68], rcx; struct TnoHashKey *
0x18008c4bb  mov     rcx, rsi; this
0x18008c4be  mov     [rsp+98h+var_70], rdx; struct TnoHash *
0x18008c4c3  mov     rdx, [rsi+1E8h]; unsigned __int64 *
0x18008c4ca  mov     [rsp+98h+pcbActual], rbx; unsigned __int64 *
0x18008c4cf  call    ?InitializeSegmentTableSetColumns@CPubCreateSegmentTask@@IEAAXPEA_K000PEBVTnoHash@@PEBVTnoHashKey@@PEAK3PEAUJET_SETCOLUMN@@3@Z; CPubCreateSegmentTask::InitializeSegmentTableSetColumns(unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,TnoHash const *,TnoHashKey const *,ulong *,ulong *,JET_SETCOLUMN *,ulong *)
0x18008c4d4  mov     rdx, [rsi+1B8h]; tableid
0x18008c4db  mov     r8d, ebp
0x18008c4de  mov     rcx, [rsi+178h]; sesid
0x18008c4e5  add     r8d, r8d; prep
0x18008c4e8  call    cs:__imp_JetPrepareUpdate
0x18008c4ee  mov     edi, eax
0x18008c4f0  test    eax, eax
0x18008c4f2  jz      short loc_18008C535
0x18008c4f4  mov     rcx, [rsi]
0x18008c4f7  mov     edx, edi
0x18008c4f9  mov     rax, [rcx+18h]
0x18008c4fd  mov     rcx, rsi
0x18008c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c505  mov     ebx, eax
0x18008c507  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c50e  cmp     rcx, r13
0x18008c511  jz      loc_18008C6AF
0x18008c517  test    [rcx+6Ch], r15b
0x18008c51b  jz      loc_18008C6AF
0x18008c521  cmp     byte ptr [rcx+69h], 1
0x18008c525  jb      loc_18008C6AF
0x18008c52b  mov     edx, 0A6h
0x18008c530  jmp     loc_18008C69C
0x18008c535  mov     r9d, [rsp+98h+csetcolumn]; csetcolumn
0x18008c53d  mov     r8, [rsi+190h]; psetcolumn
0x18008c544  mov     rdx, [rsi+1B8h]; tableid
0x18008c54b  mov     rcx, [rsi+178h]; sesid
0x18008c552  call    cs:__imp_JetSetColumns
0x18008c558  mov     edi, eax
0x18008c55a  test    eax, eax
0x18008c55c  jz      short loc_18008C59F
0x18008c55e  mov     rcx, [rsi]
0x18008c561  mov     edx, edi
0x18008c563  mov     rax, [rcx+18h]
0x18008c567  mov     rcx, rsi
0x18008c56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c56f  mov     ebx, eax
0x18008c571  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c578  cmp     rcx, r13
0x18008c57b  jz      loc_18008C6AF
0x18008c581  test    [rcx+6Ch], r15b
0x18008c585  jz      loc_18008C6AF
0x18008c58b  cmp     byte ptr [rcx+69h], 1
0x18008c58f  jb      loc_18008C6AF
0x18008c595  mov     edx, 0A7h
0x18008c59a  jmp     loc_18008C69C
0x18008c59f  mov     rdx, [rsi+1B8h]; tableid
0x18008c5a6  xor     r9d, r9d; cbBookmark
0x18008c5a9  mov     rcx, [rsi+178h]; sesid
0x18008c5b0  xor     r8d, r8d; pvBookmark
0x18008c5b3  mov     [rsp+98h+pcbActual], 0; pcbActual
0x18008c5bc  call    cs:__imp_JetUpdate
0x18008c5c2  mov     ebp, 0FFFFF9BBh
0x18008c5c7  mov     edi, eax
0x18008c5c9  cmp     eax, ebp
0x18008c5cb  jnz     loc_18008C666
0x18008c5d1  mov     rax, [rsi]
0x18008c5d4  mov     edx, ebp
0x18008c5d6  mov     rcx, rsi
0x18008c5d9  mov     rax, [rax+18h]
0x18008c5dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c5e2  mov     ebx, eax
0x18008c5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c5eb  cmp     rcx, r13
0x18008c5ee  jz      short loc_18008C614
0x18008c5f0  test    [rcx+6Ch], r15b
0x18008c5f4  jz      short loc_18008C614
0x18008c5f6  cmp     [rcx+69h], r15b
0x18008c5fa  jb      short loc_18008C614
0x18008c5fc  mov     rcx, [rcx+60h]
0x18008c600  mov     edx, 0A8h
0x18008c605  mov     r9d, ebp
0x18008c608  mov     dword ptr [rsp+98h+pcbActual], eax
0x18008c60c  mov     r8, r12
0x18008c60f  call    WPP_SF_Dd
0x18008c614  mov     rdx, [rsi+1B8h]; tableid
0x18008c61b  mov     r8d, 3; prep
0x18008c621  mov     rcx, [rsi+178h]; sesid
0x18008c628  call    cs:__imp_JetPrepareUpdate
0x18008c62e  mov     edi, eax
0x18008c630  test    eax, eax
0x18008c632  jz      short loc_18008C6AF
0x18008c634  mov     rcx, [rsi]
0x18008c637  mov     edx, edi
0x18008c639  mov     rax, [rcx+18h]
0x18008c63d  mov     rcx, rsi
0x18008c640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c645  mov     ebx, eax
0x18008c647  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c64e  cmp     rcx, r13
0x18008c651  jz      short loc_18008C6AF
0x18008c653  test    [rcx+6Ch], r15b
0x18008c657  jz      short loc_18008C6AF
0x18008c659  cmp     byte ptr [rcx+69h], 1
0x18008c65d  jb      short loc_18008C6AF
0x18008c65f  mov     edx, 0A9h
0x18008c664  jmp     short loc_18008C69C
0x18008c666  xor     ebx, ebx
0x18008c668  test    edi, edi
0x18008c66a  jz      short loc_18008C6AF
0x18008c66c  mov     rax, [rsi]
0x18008c66f  mov     edx, edi
0x18008c671  mov     rcx, rsi
0x18008c674  mov     rax, [rax+18h]
0x18008c678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c67d  mov     ebx, eax
0x18008c67f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008c686  cmp     rcx, r13
0x18008c689  jz      short loc_18008C6AF
0x18008c68b  test    [rcx+6Ch], r15b
0x18008c68f  jz      short loc_18008C6AF
0x18008c691  cmp     byte ptr [rcx+69h], 1
0x18008c695  jb      short loc_18008C6AF
0x18008c697  mov     edx, 0AAh
0x18008c69c  mov     rcx, [rcx+60h]
0x18008c6a0  mov     r9d, edi
0x18008c6a3  mov     r8, r12
0x18008c6a6  mov     dword ptr [rsp+98h+pcbActual], eax
0x18008c6aa  call    WPP_SF_Dd
0x18008c6af  mov     eax, ebx
0x18008c6b1  mov     rbx, [rsp+98h+arg_18]
0x18008c6b9  add     rsp, 60h
0x18008c6bd  pop     r15
0x18008c6bf  pop     r14
0x18008c6c1  pop     r13
0x18008c6c3  pop     r12
0x18008c6c5  pop     rdi
0x18008c6c6  pop     rsi
0x18008c6c7  pop     rbp
0x18008c6c8  retn
```
