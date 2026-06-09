# TieringPinnedSession::GetFilePinnedState(TE_FILE_ID_128 *,_STORAGE_TIER_CLASS *)

- ea: `0x14001f874`
- end: `0x14001fc98`
- name: `?GetFilePinnedState@TieringPinnedSession@@QEAAJPEAUTE_FILE_ID_128@@PEAW4_STORAGE_TIER_CLASS@@@Z`
- size: `1060`
- prototype: `__int64 __fastcall(TieringPinnedSession *__hidden this, struct TE_FILE_ID_128 *Source2, enum _STORAGE_TIER_CLASS *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400108e0`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x14001f744`
- `0x14001f874`
- `0x140020e1c`
- `0x140021018`
- `0x1400210c8`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14001f8d9`
- `ntdll!RtlCompareMemory` at `0x14001fb73`
- `ntdll!RtlCompareMemory` at `0x14001f8d9`
- `ntdll!RtlCompareMemory` at `0x14001fb73`
- `ESENT!JetMakeKey` at `0x14001f94a`
- `ESENT!JetMakeKey` at `0x14001f94a`
- `ESENT!JetSeek` at `0x14001fa19`
- `ESENT!JetSeek` at `0x14001fa19`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::GetFilePinnedState(
        TieringPinnedSession *this,
        struct TE_FILE_ID_128 *Source2,
        enum _STORAGE_TIER_CLASS *a3)
{
  unsigned int v6; // ebx
  JET_ERR Key; // eax
  JET_ERR v8; // r8d
  int v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  JET_ERR v12; // eax
  int v13; // eax
  JET_ERR CurrentPinnedRecord; // eax
  int v15; // eax
  int v17; // r8d
  unsigned __int8 v18[8]; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+60h] [rbp-20h]
  __int128 Source1; // [rsp+68h] [rbp-18h] BYREF

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringPinnedSession::GetFilePinnedState";
  CHResultImp::CHResultImp((CHResultImp *)v19);
  v18[0] = 0;
  if ( RtlCompareMemory(Source2, &NullGuid, 0x10u) == 16 )
  {
    v6 = -2138898428;
    v20 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids, 2156068868LL);
    }
    goto LABEL_56;
  }
  Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), Source2, 0x10u, 1u);
  v8 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v6 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v6 = -2147024882;
    }
    else
    {
      v9 = -Key;
      if ( v9 < 0 )
        LOWORD(v9) = v8;
      v6 = v8 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
    }
    v20 = v6;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_56;
    }
    v11 = 66;
    goto LABEL_20;
  }
  v12 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
  v8 = v12;
  if ( v12 == -1601 || v12 == 1039 )
  {
    *a3 = StorageTierClassUnspecified;
    CHResultImp::~CHResultImp((CHResultImp *)v19);
    return 0;
  }
  else
  {
    if ( v12 )
    {
      if ( v12 == -529 || v12 == -1092 || v12 == -1808 )
      {
        v6 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v12 == -1011 )
      {
        v6 = -2147024882;
      }
      else
      {
        v13 = -v12;
        if ( v13 < 0 )
          LOWORD(v13) = v8;
        v6 = v8 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
      }
      v20 = v6;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_56;
      }
      v11 = 67;
      goto LABEL_20;
    }
    Source1 = 0;
    CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(this, (struct TE_FILE_ID_128 *)&Source1, v18, 0);
    v8 = CurrentPinnedRecord;
    if ( CurrentPinnedRecord )
    {
      if ( CurrentPinnedRecord == -529 || CurrentPinnedRecord == -1092 || CurrentPinnedRecord == -1808 )
      {
        v6 = ATL::AtlHresultFromWin32(112);
      }
      else if ( CurrentPinnedRecord == -1011 )
      {
        v6 = -2147024882;
      }
      else
      {
        v15 = -CurrentPinnedRecord;
        if ( v15 < 0 )
          LOWORD(v15) = v8;
        v6 = v8 & 0x8E5E0000 | (unsigned __int16)v15 | 0xE5E0000;
      }
      v20 = v6;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_56;
      }
      v11 = 68;
LABEL_20:
      WPP_SF_iiSd(
        v10[2],
        v11,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
        v8);
LABEL_56:
      CHResultImp::~CHResultImp((CHResultImp *)v19);
      return v6;
    }
    if ( RtlCompareMemory(&Source1, Source2, 0x10u) != 16 )
    {
      v6 = -2147220986;
      v20 = -2147220986;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_iiiiSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          *((_QWORD *)Source2 + 1),
          *(_QWORD *)Source2,
          SBYTE8(Source1),
          Source1,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          0);
      }
      goto LABEL_56;
    }
    v17 = v18[0] & 1;
    *a3 = v17 + 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_iiDS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        v17,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    CHResultImp::~CHResultImp((CHResultImp *)v19);
    return v20;
  }
}

```

## disassembly

```asm
0x14001f874  push    rbp
0x14001f876  push    rbx
0x14001f877  push    rsi
0x14001f878  push    r12
0x14001f87a  push    r14
0x14001f87c  mov     rbp, rsp
0x14001f87f  sub     rsp, 80h
0x14001f886  mov     rax, cs:__security_cookie
0x14001f88d  xor     rax, rsp
0x14001f890  mov     [rbp+var_8], rax
0x14001f894  mov     rax, gs:58h
0x14001f89d  mov     r14, rcx
0x14001f8a0  mov     rsi, rdx
0x14001f8a3  mov     ecx, 8
0x14001f8a8  mov     rbx, r8
0x14001f8ab  mov     rdx, [rax]
0x14001f8ae  lea     rax, aTieringpinneds_4; "TieringPinnedSession::GetFilePinnedStat"...
0x14001f8b5  mov     [rcx+rdx], rax
0x14001f8b9  lea     rcx, [rbp+var_28]; this
0x14001f8bd  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001f8c2  mov     r12d, 10h
0x14001f8c8  mov     [rbp+var_30], 0
0x14001f8cc  mov     r8d, r12d; Length
0x14001f8cf  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x14001f8d6  mov     rcx, rsi; Source1
0x14001f8d9  call    cs:__imp_RtlCompareMemory
0x14001f8df  cmp     rax, r12
0x14001f8e2  jnz     short loc_14001F934
0x14001f8e4  mov     ebx, 80830004h
0x14001f8e9  mov     [rbp+var_20], ebx
0x14001f8ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8f3  lea     rax, WPP_GLOBAL_Control
0x14001f8fa  cmp     rcx, rax
0x14001f8fd  jz      loc_14001FBED
0x14001f903  test    byte ptr [rcx+1Ch], 1
0x14001f907  jz      loc_14001FBED
0x14001f90d  cmp     byte ptr [rcx+19h], 2
0x14001f911  jb      loc_14001FBED
0x14001f917  mov     rcx, [rcx+10h]
0x14001f91b  lea     edx, [r12+31h]
0x14001f920  mov     r9d, ebx
0x14001f923  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001f92a  call    WPP_SF_d
0x14001f92f  jmp     loc_14001FBED
0x14001f934  mov     rdx, [r14+18h]; tableid
0x14001f938  mov     r9d, r12d; cbData
0x14001f93b  mov     rcx, [r14+8]; sesid
0x14001f93f  mov     r8, rsi; pvData
0x14001f942  mov     [rsp+80h+grbit], 1; grbit
0x14001f94a  call    cs:__imp_JetMakeKey
0x14001f950  mov     r8d, eax
0x14001f953  test    eax, eax
0x14001f955  jz      loc_14001FA0B
0x14001f95b  cmp     eax, 0FFFFFDEFh
0x14001f960  jz      short loc_14001F999
0x14001f962  cmp     eax, 0FFFFFBBCh
0x14001f967  jz      short loc_14001F999
0x14001f969  cmp     eax, 0FFFFF8F0h
0x14001f96e  jz      short loc_14001F999
0x14001f970  cmp     eax, 0FFFFFC0Dh
0x14001f975  jnz     short loc_14001F97E
0x14001f977  mov     ebx, 8007000Eh
0x14001f97c  jmp     short loc_14001F9A5
0x14001f97e  neg     eax
0x14001f980  cmovs   eax, r8d
0x14001f984  movzx   ebx, ax
0x14001f987  mov     eax, r8d
0x14001f98a  and     eax, 8E5E0000h
0x14001f98f  or      ebx, eax
0x14001f991  or      ebx, 0E5E0000h
0x14001f997  jmp     short loc_14001F9A5
0x14001f999  mov     ecx, 70h ; 'p'; unsigned int
0x14001f99e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001f9a3  mov     ebx, eax
0x14001f9a5  mov     [rbp+var_20], ebx
0x14001f9a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9af  lea     rax, WPP_GLOBAL_Control
0x14001f9b6  cmp     rcx, rax
0x14001f9b9  jz      loc_14001FBED
0x14001f9bf  test    byte ptr [rcx+1Ch], 1
0x14001f9c3  jz      loc_14001FBED
0x14001f9c9  cmp     byte ptr [rcx+19h], 2
0x14001f9cd  jb      loc_14001FBED
0x14001f9d3  mov     edx, 42h ; 'B'
0x14001f9d8  mov     rax, [r14+28h]
0x14001f9dc  mov     r9, [rsi+8]
0x14001f9e0  mov     rcx, [rcx+10h]
0x14001f9e4  mov     dword ptr [rsp+80h+var_50], r8d
0x14001f9e9  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001f9f0  mov     rax, [rax+70h]
0x14001f9f4  mov     [rsp+80h+var_58], rax
0x14001f9f9  mov     rax, [rsi]
0x14001f9fc  mov     qword ptr [rsp+80h+grbit], rax
0x14001fa01  call    WPP_SF_iiSd
0x14001fa06  jmp     loc_14001FBED
0x14001fa0b  mov     rdx, [r14+18h]; tableid
0x14001fa0f  mov     r8d, 1; grbit
0x14001fa15  mov     rcx, [r14+8]; sesid
0x14001fa19  call    cs:__imp_JetSeek
0x14001fa1f  mov     r8d, eax
0x14001fa22  cmp     eax, 0FFFFF9BFh
0x14001fa27  jz      loc_14001FC6C
0x14001fa2d  cmp     eax, 40Fh
0x14001fa32  jz      loc_14001FC6C
0x14001fa38  test    eax, eax
0x14001fa3a  jz      loc_14001FAC2
0x14001fa40  cmp     eax, 0FFFFFDEFh
0x14001fa45  jz      short loc_14001FA7E
0x14001fa47  cmp     eax, 0FFFFFBBCh
0x14001fa4c  jz      short loc_14001FA7E
0x14001fa4e  cmp     eax, 0FFFFF8F0h
0x14001fa53  jz      short loc_14001FA7E
0x14001fa55  cmp     eax, 0FFFFFC0Dh
0x14001fa5a  jnz     short loc_14001FA63
0x14001fa5c  mov     ebx, 8007000Eh
0x14001fa61  jmp     short loc_14001FA8A
0x14001fa63  neg     eax
0x14001fa65  cmovs   eax, r8d
0x14001fa69  movzx   ebx, ax
0x14001fa6c  mov     eax, r8d
0x14001fa6f  and     eax, 8E5E0000h
0x14001fa74  or      ebx, eax
0x14001fa76  or      ebx, 0E5E0000h
0x14001fa7c  jmp     short loc_14001FA8A
0x14001fa7e  mov     ecx, 70h ; 'p'; unsigned int
0x14001fa83  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001fa88  mov     ebx, eax
0x14001fa8a  mov     [rbp+var_20], ebx
0x14001fa8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa94  lea     rax, WPP_GLOBAL_Control
0x14001fa9b  cmp     rcx, rax
0x14001fa9e  jz      loc_14001FBED
0x14001faa4  test    byte ptr [rcx+1Ch], 1
0x14001faa8  jz      loc_14001FBED
0x14001faae  cmp     byte ptr [rcx+19h], 2
0x14001fab2  jb      loc_14001FBED
0x14001fab8  mov     edx, 43h ; 'C'
0x14001fabd  jmp     loc_14001F9D8
0x14001fac2  xorps   xmm0, xmm0
0x14001fac5  lea     r8, [rbp+var_30]; unsigned __int8 *
0x14001fac9  xor     r9d, r9d; unsigned __int8 *
0x14001facc  lea     rdx, [rbp+Source1]; struct TE_FILE_ID_128 *
0x14001fad0  mov     rcx, r14; this
0x14001fad3  movups  [rbp+Source1], xmm0
0x14001fad7  call    ?GetCurrentPinnedRecord@TieringPinnedSession@@QEAAJPEAUTE_FILE_ID_128@@PEAE1@Z; TieringPinnedSession::GetCurrentPinnedRecord(TE_FILE_ID_128 *,uchar *,uchar *)
0x14001fadc  mov     r8d, eax
0x14001fadf  test    eax, eax
0x14001fae1  jz      loc_14001FB69
0x14001fae7  cmp     eax, 0FFFFFDEFh
0x14001faec  jz      short loc_14001FB25
0x14001faee  cmp     eax, 0FFFFFBBCh
0x14001faf3  jz      short loc_14001FB25
0x14001faf5  cmp     eax, 0FFFFF8F0h
0x14001fafa  jz      short loc_14001FB25
0x14001fafc  cmp     eax, 0FFFFFC0Dh
0x14001fb01  jnz     short loc_14001FB0A
0x14001fb03  mov     ebx, 8007000Eh
0x14001fb08  jmp     short loc_14001FB31
0x14001fb0a  neg     eax
0x14001fb0c  cmovs   eax, r8d
0x14001fb10  movzx   ebx, ax
0x14001fb13  mov     eax, r8d
0x14001fb16  and     eax, 8E5E0000h
0x14001fb1b  or      ebx, eax
0x14001fb1d  or      ebx, 0E5E0000h
0x14001fb23  jmp     short loc_14001FB31
0x14001fb25  mov     ecx, 70h ; 'p'; unsigned int
0x14001fb2a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14001fb2f  mov     ebx, eax
0x14001fb31  mov     [rbp+var_20], ebx
0x14001fb34  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb3b  lea     rax, WPP_GLOBAL_Control
0x14001fb42  cmp     rcx, rax
0x14001fb45  jz      loc_14001FBED
0x14001fb4b  test    byte ptr [rcx+1Ch], 1
0x14001fb4f  jz      loc_14001FBED
0x14001fb55  cmp     byte ptr [rcx+19h], 2
0x14001fb59  jb      loc_14001FBED
0x14001fb5f  mov     edx, 44h ; 'D'
0x14001fb64  jmp     loc_14001F9D8
0x14001fb69  mov     r8, r12; Length
0x14001fb6c  lea     rcx, [rbp+Source1]; Source1
0x14001fb70  mov     rdx, rsi; Source2
0x14001fb73  call    cs:__imp_RtlCompareMemory
0x14001fb79  cmp     rax, r12
0x14001fb7c  jz      short loc_14001FBFD
0x14001fb7e  mov     ebx, 80040206h
0x14001fb83  mov     [rbp+var_20], ebx
0x14001fb86  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb8d  lea     rax, WPP_GLOBAL_Control
0x14001fb94  cmp     rcx, rax
0x14001fb97  jz      short loc_14001FBED
0x14001fb99  test    byte ptr [rcx+1Ch], 1
0x14001fb9d  jz      short loc_14001FBED
0x14001fb9f  cmp     byte ptr [rcx+19h], 2
0x14001fba3  jb      short loc_14001FBED
0x14001fba5  mov     rax, [r14+28h]
0x14001fba9  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001fbb0  mov     r9, [rsi+8]
0x14001fbb4  mov     edx, 45h ; 'E'
0x14001fbb9  mov     rcx, [rcx+10h]
0x14001fbbd  mov     [rsp+80h+var_40], 0
0x14001fbc5  mov     rax, [rax+70h]
0x14001fbc9  mov     [rsp+80h+var_48], rax
0x14001fbce  mov     rax, qword ptr [rbp+Source1]
0x14001fbd2  mov     [rsp+80h+var_50], rax
0x14001fbd7  mov     rax, qword ptr [rbp+Source1+8]
0x14001fbdb  mov     [rsp+80h+var_58], rax
0x14001fbe0  mov     rax, [rsi]
0x14001fbe3  mov     qword ptr [rsp+80h+grbit], rax
0x14001fbe8  call    WPP_SF_iiiiSd
0x14001fbed  lea     rcx, [rbp+var_28]; this
0x14001fbf1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001fbf6  mov     eax, ebx
0x14001fbf8  jmp     loc_14001FC7D
0x14001fbfd  movzx   r8d, [rbp+var_30]
0x14001fc02  and     r8d, 1
0x14001fc06  lea     eax, [r8+1]
0x14001fc0a  mov     [rbx], eax
0x14001fc0c  lea     rax, WPP_GLOBAL_Control
0x14001fc13  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc1a  cmp     rcx, rax
0x14001fc1d  jz      short loc_14001FC5E
0x14001fc1f  test    byte ptr [rcx+1Ch], 1
0x14001fc23  jz      short loc_14001FC5E
0x14001fc25  cmp     byte ptr [rcx+19h], 5
0x14001fc29  jb      short loc_14001FC5E
0x14001fc2b  mov     rax, [r14+28h]
0x14001fc2f  mov     edx, 46h ; 'F'
0x14001fc34  mov     r9, [rsi+8]
0x14001fc38  mov     rcx, [rcx+10h]
0x14001fc3c  mov     rax, [rax+70h]
0x14001fc40  mov     [rsp+80h+var_50], rax
0x14001fc45  mov     rax, [rsi]
0x14001fc48  mov     dword ptr [rsp+80h+var_58], r8d
0x14001fc4d  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x14001fc54  mov     qword ptr [rsp+80h+grbit], rax
0x14001fc59  call    WPP_SF_iiDS
0x14001fc5e  lea     rcx, [rbp+var_28]; this
0x14001fc62  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001fc67  mov     eax, [rbp+var_20]
0x14001fc6a  jmp     short loc_14001FC7D
0x14001fc6c  lea     rcx, [rbp+var_28]; this
0x14001fc70  mov     dword ptr [rbx], 0
0x14001fc76  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14001fc7b  xor     eax, eax
0x14001fc7d  mov     rcx, [rbp+var_8]
0x14001fc81  xor     rcx, rsp; StackCookie
0x14001fc84  call    __security_check_cookie
0x14001fc89  add     rsp, 80h
0x14001fc90  pop     r14
0x14001fc92  pop     r12
0x14001fc94  pop     rsi
0x14001fc95  pop     rbx
0x14001fc96  pop     rbp
0x14001fc97  retn
```
