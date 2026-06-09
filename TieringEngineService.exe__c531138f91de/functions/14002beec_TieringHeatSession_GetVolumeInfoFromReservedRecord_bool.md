# TieringHeatSession::GetVolumeInfoFromReservedRecord(bool)

- ea: `0x14002beec`
- end: `0x14002c604`
- name: `?GetVolumeInfoFromReservedRecord@TieringHeatSession@@QEAAJ_N@Z`
- size: `1816`
- prototype: `__int64 __fastcall(TieringHeatSession *this, char)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000d5f0`
- `0x140010d1c`

## callees

- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009a04`
- `0x140009c08`
- `0x14002866c`
- `0x14002beec`
- `0x14002d13c`
- `0x14002d1f0`
- `0x14002d294`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14002c277`
- `ntdll!RtlCompareMemory` at `0x14002c277`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002c31f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002c572`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002c31f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002c572`
- `ESENT!JetMakeKey` at `0x14002bf72`
- `ESENT!JetMakeKey` at `0x14002c01c`
- `ESENT!JetMakeKey` at `0x14002bf72`
- `ESENT!JetMakeKey` at `0x14002c01c`
- `ESENT!JetSeek` at `0x14002c0d7`
- `ESENT!JetSeek` at `0x14002c0d7`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetVolumeInfoFromReservedRecord(TieringHeatSession *this, char a2)
{
  JET_TABLEID v4; // rdx
  JET_SESID v5; // rcx
  JET_ERR Key; // eax
  JET_ERR v7; // r8d
  unsigned int v8; // ebx
  int v9; // eax
  _QWORD *v10; // rcx
  int v11; // edx
  JET_ERR v12; // eax
  int v13; // eax
  JET_ERR v14; // eax
  int v15; // eax
  JET_ERR CurrentHeatRecord; // eax
  int v17; // eax
  int v19; // r8d
  __int64 **v20; // rsi
  __int64 v21; // rdx
  int v22; // r9d
  __int64 v23; // rax
  _QWORD *v24; // r10
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int8 v28; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int8 v29; // [rsp+51h] [rbp-48h] BYREF
  unsigned __int8 v30[2]; // [rsp+52h] [rbp-47h] BYREF
  unsigned __int16 v31; // [rsp+54h] [rbp-45h] BYREF
  _BYTE v32[8]; // [rsp+58h] [rbp-41h] BYREF
  int v33; // [rsp+60h] [rbp-39h]
  __int64 v34; // [rsp+68h] [rbp-31h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp-29h] BYREF
  __int64 v36; // [rsp+78h] [rbp-21h] BYREF
  __int64 v37; // [rsp+80h] [rbp-19h] BYREF
  __int128 pvData; // [rsp+88h] [rbp-11h] BYREF
  __int128 Source1; // [rsp+98h] [rbp-1h] BYREF
  unsigned __int16 v40[4]; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned __int16 v41[4]; // [rsp+B0h] [rbp+17h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::GetVolumeInfoFromReservedRecord";
  CHResultImp::CHResultImp((CHResultImp *)v32);
  v4 = *((_QWORD *)this + 3);
  v5 = *((_QWORD *)this + 1);
  v36 = 0;
  *(_QWORD *)v40 = 0;
  pvData = 0;
  *(_DWORD *)v41 = 0;
  v41[2] = 0;
  SystemTimeAsFileTime = 0;
  Key = JetMakeKey(v5, v4, &pvData, 0x10u, 1u);
  v7 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v8 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v9 = -Key;
      if ( v9 < 0 )
        LOWORD(v9) = v7;
      v8 = v7 & 0x8E5E0000 | (unsigned __int16)v9 | 0xE5E0000;
    }
    v33 = v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v11 = 10;
LABEL_29:
    WPP_SF_Sd(
      v10[2],
      v11,
      (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v7);
LABEL_71:
    CHResultImp::~CHResultImp((CHResultImp *)v32);
    return v8;
  }
  v12 = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), &v36, 8u, 0);
  v7 = v12;
  if ( v12 )
  {
    if ( v12 == -529 || v12 == -1092 || v12 == -1808 )
    {
      v8 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v12 == -1011 )
    {
      v8 = -2147024882;
    }
    else
    {
      v13 = -v12;
      if ( v13 < 0 )
        LOWORD(v13) = v7;
      v8 = v7 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
    }
    v33 = v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_71;
    }
    v11 = 11;
    goto LABEL_29;
  }
  v14 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1u);
  v7 = v14;
  if ( v14 == -1601 || v14 == 1039 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        &WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    *(_BYTE *)(**((_QWORD **)this + 5) + 328LL) = 1;
    *(_DWORD *)(**((_QWORD **)this + 5) + 224LL) = 0;
    *(_DWORD *)(**((_QWORD **)this + 5) + 228LL) = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v26 = *((_QWORD *)this + 5);
    v27 = *(_QWORD *)&SystemTimeAsFileTime - 36000000000LL;
    if ( *(_BYTE *)(*(_QWORD *)v26 + 162LL) )
      goto LABEL_98;
    *(_DWORD *)(*(_QWORD *)v26 + 168LL) = v27;
    *(_DWORD *)(**((_QWORD **)this + 5) + 172LL) = HIDWORD(v27);
    *(_QWORD *)(**((_QWORD **)this + 5) + 176LL) = v27;
    v25 = (__int64 *)*((_QWORD *)this + 5);
  }
  else
  {
    if ( v14 )
    {
      if ( v14 == -529 || v14 == -1092 || v14 == -1808 )
      {
        v8 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v14 == -1011 )
      {
        v8 = -2147024882;
      }
      else
      {
        v15 = -v14;
        if ( v15 < 0 )
          LOWORD(v15) = v7;
        v8 = v7 & 0x8E5E0000 | (unsigned __int16)v15 | 0xE5E0000;
      }
      v33 = v8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v11 = 13;
      goto LABEL_29;
    }
    v37 = 0;
    v28 = 0;
    v31 = 0;
    v30[0] = 0;
    v29 = 0;
    Source1 = 0;
    CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                          this,
                          1u,
                          (struct TE_FILE_ID_128 *)&Source1,
                          &v37,
                          &v29,
                          v30,
                          &v28,
                          &v31,
                          v40);
    v7 = CurrentHeatRecord;
    if ( CurrentHeatRecord )
    {
      if ( CurrentHeatRecord == -529 || CurrentHeatRecord == -1092 || CurrentHeatRecord == -1808 )
      {
        v8 = ATL::AtlHresultFromWin32(112);
      }
      else if ( CurrentHeatRecord == -1011 )
      {
        v8 = -2147024882;
      }
      else
      {
        v17 = -CurrentHeatRecord;
        if ( v17 < 0 )
          LOWORD(v17) = v7;
        v8 = v7 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      v33 = v8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_71;
      }
      v11 = 14;
      goto LABEL_29;
    }
    if ( RtlCompareMemory(&Source1, &pvData, 0x10u) != 16 )
    {
      v8 = -2147220986;
      v33 = -2147220986;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          0);
      }
      goto LABEL_71;
    }
    if ( v37 != v36 )
    {
      v8 = -2147220986;
      v33 = -2147220986;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_0be274611bac3644b34e961096a35a4e_Traceguids,
          *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
          6);
      }
      goto LABEL_71;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v34 = 0;
    if ( a2 )
    {
      ++v28;
      v20 = (__int64 **)((char *)this + 40);
    }
    else
    {
      v20 = (__int64 **)((char *)this + 40);
      v21 = **v20;
      if ( !*(_BYTE *)(v21 + 162) )
      {
        v22 = *(_DWORD *)v40;
        v19 = *(_DWORD *)&v40[2];
        v34 = *(_QWORD *)v40;
        v23 = 36000000000LL * v41[0] + *(_QWORD *)v40;
        *(_DWORD *)(v21 + 168) = v23;
        *(_DWORD *)(**v20 + 172) = HIDWORD(v23);
        *(_DWORD *)(**v20 + 176) = v22;
        *(_DWORD *)(**v20 + 180) = v19;
      }
    }
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, (unsigned int)*v20, *(_QWORD *)(**v20 + 176), (*v20)[14]);
        v24 = WPP_GLOBAL_Control;
      }
      if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
      {
        WPP_SF_DiS(v24[2], *(_QWORD *)(**v20 + 168), v19, v41[0], *(_QWORD *)(**v20 + 168), (*v20)[14]);
        v24 = WPP_GLOBAL_Control;
      }
    }
    if ( (unsigned __int8)(v28 - 1) > 0x7Fu )
      v28 = 1;
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 && *((_BYTE *)v24 + 25) >= 5u )
      WPP_SF_DDSl(v24[2], (unsigned int)*v20, v28, *(unsigned __int8 *)(**v20 + 328), v28, (*v20)[14], a2);
    *(_DWORD *)(**v20 + 228) = *(_DWORD *)&v41[1];
    *(_BYTE *)(**v20 + 328) = v28;
    *(_DWORD *)(**v20 + 224) = v31 + (v30[0] << 16) + (v29 << 24);
    v25 = *v20;
  }
  *(_BYTE *)(*v25 + 162) = 1;
LABEL_98:
  CHResultImp::~CHResultImp((CHResultImp *)v32);
  return 0;
}

```

## disassembly

```asm
0x14002beec  push    rbp
0x14002beee  push    rbx
0x14002beef  push    rsi
0x14002bef0  push    rdi
0x14002bef1  push    r14
0x14002bef3  push    r15
0x14002bef5  lea     rbp, [rsp-2Fh]
0x14002befa  sub     rsp, 0C8h
0x14002bf01  mov     rax, cs:__security_cookie
0x14002bf08  xor     rax, rsp
0x14002bf0b  mov     [rbp+57h+var_38], rax
0x14002bf0f  mov     rax, gs:58h
0x14002bf18  mov     rsi, rcx
0x14002bf1b  mov     ecx, 8
0x14002bf20  movzx   ebx, dl
0x14002bf23  mov     r8, [rax]
0x14002bf26  lea     rax, aTieringheatses; "TieringHeatSession::GetVolumeInfoFromRe"...
0x14002bf2d  mov     [rcx+r8], rax
0x14002bf31  lea     rcx, [rbp+57h+var_98]; this
0x14002bf35  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14002bf3a  mov     rdx, [rsi+18h]; tableid
0x14002bf3e  lea     r8, [rbp+57h+pvData]; pvData
0x14002bf42  mov     rcx, [rsi+8]; sesid
0x14002bf46  xor     r15d, r15d
0x14002bf49  xor     eax, eax
0x14002bf4b  mov     [rbp+57h+var_78], r15
0x14002bf4f  xorps   xmm0, xmm0
0x14002bf52  mov     qword ptr [rbp+57h+var_48], rax
0x14002bf56  movups  [rbp+57h+pvData], xmm0
0x14002bf5a  lea     r14d, [r15+1]
0x14002bf5e  mov     dword ptr [rbp+57h+var_40], eax
0x14002bf61  lea     r9d, [r15+10h]; cbData
0x14002bf65  mov     [rsp+0F0h+grbit], r14d; grbit
0x14002bf6a  mov     [rbp+57h+var_40+4], ax
0x14002bf6e  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r15
0x14002bf72  call    cs:__imp_JetMakeKey
0x14002bf78  mov     r8d, eax
0x14002bf7b  test    eax, eax
0x14002bf7d  jz      loc_14002C005
0x14002bf83  cmp     eax, 0FFFFFDEFh
0x14002bf88  jz      short loc_14002BFC1
0x14002bf8a  cmp     eax, 0FFFFFBBCh
0x14002bf8f  jz      short loc_14002BFC1
0x14002bf91  cmp     eax, 0FFFFF8F0h
0x14002bf96  jz      short loc_14002BFC1
0x14002bf98  cmp     eax, 0FFFFFC0Dh
0x14002bf9d  jnz     short loc_14002BFA6
0x14002bf9f  mov     ebx, 8007000Eh
0x14002bfa4  jmp     short loc_14002BFCD
0x14002bfa6  neg     eax
0x14002bfa8  cmovs   eax, r8d
0x14002bfac  movzx   ebx, ax
0x14002bfaf  mov     eax, r8d
0x14002bfb2  and     eax, 8E5E0000h
0x14002bfb7  or      ebx, eax
0x14002bfb9  or      ebx, 0E5E0000h
0x14002bfbf  jmp     short loc_14002BFCD
0x14002bfc1  mov     ecx, 70h ; 'p'; unsigned int
0x14002bfc6  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002bfcb  mov     ebx, eax
0x14002bfcd  mov     [rbp+57h+var_90], ebx
0x14002bfd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bfd7  lea     rdi, WPP_GLOBAL_Control
0x14002bfde  cmp     rcx, rdi
0x14002bfe1  jz      loc_14002C30B
0x14002bfe7  test    [rcx+1Ch], r14b
0x14002bfeb  jz      loc_14002C30B
0x14002bff1  cmp     byte ptr [rcx+19h], 2
0x14002bff5  jb      loc_14002C30B
0x14002bffb  mov     edx, 0Ah
0x14002c000  jmp     loc_14002C0AA
0x14002c005  mov     rdx, [rsi+18h]; tableid
0x14002c009  lea     r8, [rbp+57h+var_78]; pvData
0x14002c00d  mov     rcx, [rsi+8]; sesid
0x14002c011  mov     r9d, 8; cbData
0x14002c017  mov     [rsp+0F0h+grbit], r15d; grbit
0x14002c01c  call    cs:__imp_JetMakeKey
0x14002c022  mov     r8d, eax
0x14002c025  test    eax, eax
0x14002c027  jz      loc_14002C0CC
0x14002c02d  cmp     eax, 0FFFFFDEFh
0x14002c032  jz      short loc_14002C06B
0x14002c034  cmp     eax, 0FFFFFBBCh
0x14002c039  jz      short loc_14002C06B
0x14002c03b  cmp     eax, 0FFFFF8F0h
0x14002c040  jz      short loc_14002C06B
0x14002c042  cmp     eax, 0FFFFFC0Dh
0x14002c047  jnz     short loc_14002C050
0x14002c049  mov     ebx, 8007000Eh
0x14002c04e  jmp     short loc_14002C077
0x14002c050  neg     eax
0x14002c052  cmovs   eax, r8d
0x14002c056  movzx   ebx, ax
0x14002c059  mov     eax, r8d
0x14002c05c  and     eax, 8E5E0000h
0x14002c061  or      ebx, eax
0x14002c063  or      ebx, 0E5E0000h
0x14002c069  jmp     short loc_14002C077
0x14002c06b  mov     ecx, 70h ; 'p'; unsigned int
0x14002c070  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c075  mov     ebx, eax
0x14002c077  mov     [rbp+57h+var_90], ebx
0x14002c07a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c081  lea     rdi, WPP_GLOBAL_Control
0x14002c088  cmp     rcx, rdi
0x14002c08b  jz      loc_14002C30B
0x14002c091  test    [rcx+1Ch], r14b
0x14002c095  jz      loc_14002C30B
0x14002c09b  cmp     byte ptr [rcx+19h], 2
0x14002c09f  jb      loc_14002C30B
0x14002c0a5  mov     edx, 0Bh
0x14002c0aa  mov     [rsp+0F0h+grbit], r8d
0x14002c0af  mov     r9, [rsi+28h]
0x14002c0b3  lea     r8, WPP_0be274611bac3644b34e961096a35a4e_Traceguids
0x14002c0ba  mov     rcx, [rcx+10h]
0x14002c0be  mov     r9, [r9+70h]
0x14002c0c2  call    WPP_SF_Sd
0x14002c0c7  jmp     loc_14002C30B
0x14002c0cc  mov     rdx, [rsi+18h]; tableid
0x14002c0d0  mov     r8d, r14d; grbit
0x14002c0d3  mov     rcx, [rsi+8]; sesid
0x14002c0d7  call    cs:__imp_JetSeek
0x14002c0dd  mov     r8d, eax
0x14002c0e0  cmp     eax, 0FFFFF9BFh
0x14002c0e5  jz      loc_14002C508
0x14002c0eb  cmp     eax, 40Fh
0x14002c0f0  jz      loc_14002C508
0x14002c0f6  test    eax, eax
0x14002c0f8  jz      loc_14002C180
0x14002c0fe  cmp     eax, 0FFFFFDEFh
0x14002c103  jz      short loc_14002C13C
0x14002c105  cmp     eax, 0FFFFFBBCh
0x14002c10a  jz      short loc_14002C13C
0x14002c10c  cmp     eax, 0FFFFF8F0h
0x14002c111  jz      short loc_14002C13C
0x14002c113  cmp     eax, 0FFFFFC0Dh
0x14002c118  jnz     short loc_14002C121
0x14002c11a  mov     ebx, 8007000Eh
0x14002c11f  jmp     short loc_14002C148
0x14002c121  neg     eax
0x14002c123  cmovs   eax, r8d
0x14002c127  movzx   ebx, ax
0x14002c12a  mov     eax, r8d
0x14002c12d  and     eax, 8E5E0000h
0x14002c132  or      ebx, eax
0x14002c134  or      ebx, 0E5E0000h
0x14002c13a  jmp     short loc_14002C148
0x14002c13c  mov     ecx, 70h ; 'p'; unsigned int
0x14002c141  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c146  mov     ebx, eax
0x14002c148  mov     [rbp+57h+var_90], ebx
0x14002c14b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c152  lea     rdi, WPP_GLOBAL_Control
0x14002c159  cmp     rcx, rdi
0x14002c15c  jz      loc_14002C30B
0x14002c162  test    [rcx+1Ch], r14b
0x14002c166  jz      loc_14002C30B
0x14002c16c  cmp     byte ptr [rcx+19h], 2
0x14002c170  jb      loc_14002C30B
0x14002c176  mov     edx, 0Dh
0x14002c17b  jmp     loc_14002C0AA
0x14002c180  lea     rax, [rbp+57h+var_48]
0x14002c184  mov     [rbp+57h+var_70], r15
0x14002c188  mov     [rsp+0F0h+var_B0], rax; unsigned __int16 *
0x14002c18d  lea     r9, [rbp+57h+var_70]; __int64 *
0x14002c191  lea     rax, [rbp+57h+var_9C]
0x14002c195  mov     [rbp+57h+var_A0], r15b
0x14002c199  mov     [rsp+0F0h+var_B8], rax; unsigned __int16 *
0x14002c19e  lea     r8, [rbp+57h+Source1]; struct TE_FILE_ID_128 *
0x14002c1a2  lea     rax, [rbp+57h+var_A0]
0x14002c1a6  mov     [rbp+57h+var_9C], r15w
0x14002c1ab  mov     [rsp+0F0h+var_C0], rax; unsigned __int8 *
0x14002c1b0  xorps   xmm0, xmm0
0x14002c1b3  lea     rax, [rbp+57h+var_9E]
0x14002c1b7  mov     [rbp+57h+var_9E], r15b
0x14002c1bb  mov     [rsp+0F0h+var_C8], rax; unsigned __int8 *
0x14002c1c0  mov     dl, r14b; bool
0x14002c1c3  lea     rax, [rbp+57h+var_9F]
0x14002c1c7  mov     [rbp+57h+var_9F], r15b
0x14002c1cb  mov     rcx, rsi; this
0x14002c1ce  mov     qword ptr [rsp+0F0h+grbit], rax; unsigned __int8 *
0x14002c1d3  movups  [rbp+57h+Source1], xmm0
0x14002c1d7  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x14002c1dc  mov     r8d, eax
0x14002c1df  test    eax, eax
0x14002c1e1  jz      loc_14002C269
0x14002c1e7  cmp     eax, 0FFFFFDEFh
0x14002c1ec  jz      short loc_14002C225
0x14002c1ee  cmp     eax, 0FFFFFBBCh
0x14002c1f3  jz      short loc_14002C225
0x14002c1f5  cmp     eax, 0FFFFF8F0h
0x14002c1fa  jz      short loc_14002C225
0x14002c1fc  cmp     eax, 0FFFFFC0Dh
0x14002c201  jnz     short loc_14002C20A
0x14002c203  mov     ebx, 8007000Eh
0x14002c208  jmp     short loc_14002C231
0x14002c20a  neg     eax
0x14002c20c  cmovs   eax, r8d
0x14002c210  movzx   ebx, ax
0x14002c213  mov     eax, r8d
0x14002c216  and     eax, 8E5E0000h
0x14002c21b  or      ebx, eax
0x14002c21d  or      ebx, 0E5E0000h
0x14002c223  jmp     short loc_14002C231
0x14002c225  mov     ecx, 70h ; 'p'; unsigned int
0x14002c22a  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14002c22f  mov     ebx, eax
0x14002c231  mov     [rbp+57h+var_90], ebx
0x14002c234  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c23b  lea     rdi, WPP_GLOBAL_Control
0x14002c242  cmp     rcx, rdi
0x14002c245  jz      loc_14002C30B
0x14002c24b  test    [rcx+1Ch], r14b
0x14002c24f  jz      loc_14002C30B
0x14002c255  cmp     byte ptr [rcx+19h], 2
0x14002c259  jb      loc_14002C30B
0x14002c25f  mov     edx, 0Eh
0x14002c264  jmp     loc_14002C0AA
0x14002c269  mov     r8d, 10h; Length
0x14002c26f  lea     rdx, [rbp+57h+pvData]; Source2
0x14002c273  lea     rcx, [rbp+57h+Source1]; Source1
0x14002c277  call    cs:__imp_RtlCompareMemory
0x14002c27d  cmp     rax, 10h
0x14002c281  jz      short loc_14002C2B9
0x14002c283  mov     ebx, 80040206h
0x14002c288  mov     [rbp+57h+var_90], ebx
0x14002c28b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c292  lea     rdi, WPP_GLOBAL_Control
0x14002c299  cmp     rcx, rdi
0x14002c29c  jz      short loc_14002C30B
0x14002c29e  test    [rcx+1Ch], r14b
0x14002c2a2  jz      short loc_14002C30B
0x14002c2a4  cmp     byte ptr [rcx+19h], 2
0x14002c2a8  jb      short loc_14002C30B
0x14002c2aa  mov     edx, 0Fh
0x14002c2af  mov     [rsp+0F0h+grbit], r15d
0x14002c2b4  jmp     loc_14002C0AF
0x14002c2b9  mov     rax, [rbp+57h+var_78]
0x14002c2bd  cmp     [rbp+57h+var_70], rax
0x14002c2c1  jz      short loc_14002C31B
0x14002c2c3  mov     ebx, 80040206h
0x14002c2c8  mov     [rbp+57h+var_90], ebx
0x14002c2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c2d2  lea     rdi, WPP_GLOBAL_Control
0x14002c2d9  cmp     rcx, rdi
0x14002c2dc  jz      short loc_14002C30B
0x14002c2de  test    [rcx+1Ch], r14b
0x14002c2e2  jz      short loc_14002C30B
0x14002c2e4  cmp     byte ptr [rcx+19h], 2
0x14002c2e8  jb      short loc_14002C30B
0x14002c2ea  mov     r9, [rsi+28h]
0x14002c2ee  lea     r8, WPP_0be274611bac3644b34e961096a35a4e_Traceguids
0x14002c2f5  mov     rcx, [rcx+10h]
0x14002c2f9  mov     edx, 10h
0x14002c2fe  mov     [rsp+0F0h+grbit], ebx
0x14002c302  mov     r9, [r9+70h]
0x14002c306  call    WPP_SF_Sd
0x14002c30b  lea     rcx, [rbp+57h+var_98]; this
0x14002c30f  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14002c314  mov     eax, ebx
0x14002c316  jmp     loc_14002C5E8
0x14002c31b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002c31f  call    cs:__imp_GetSystemTimeAsFileTime
0x14002c325  mov     [rbp+57h+var_88], r15
0x14002c329  test    bl, bl
0x14002c32b  jz      short loc_14002C33A
0x14002c32d  add     [rbp+57h+var_A0], r14b
0x14002c331  add     rsi, 28h ; '('
0x14002c335  jmp     loc_14002C3BE
0x14002c33a  add     rsi, 28h ; '('
0x14002c33e  mov     rax, [rsi]
0x14002c341  mov     rdx, [rax]
0x14002c344  cmp     [rdx+0A2h], r15b
0x14002c34b  jnz     short loc_14002C3BE
0x14002c34d  movzx   eax, [rbp+57h+var_48]
0x14002c351  mov     r10, 861C46800h
0x14002c35b  movzx   ecx, [rbp+57h+var_40]
0x14002c35f  movzx   r9d, [rbp+57h+var_48+2]
0x14002c364  movzx   r8d, [rbp+57h+var_48+6]
0x14002c369  imul    rcx, r10
0x14002c36d  shl     r9d, 10h
0x14002c371  or      r9d, eax
0x14002c374  shl     r8d, 10h
0x14002c378  movzx   eax, [rbp+57h+var_48+4]
0x14002c37c  or      r8d, eax
0x14002c37f  mov     dword ptr [rbp+57h+var_88], r9d
0x14002c383  mov     dword ptr [rbp+57h+var_88+4], r8d
0x14002c387  mov     rax, [rbp+57h+var_88]
0x14002c38b  add     rax, rcx
0x14002c38e  mov     [rdx+0A8h], eax
0x14002c394  mov     rcx, [rsi]
0x14002c397  shr     rax, 20h
0x14002c39b  mov     rdx, [rcx]
0x14002c39e  mov     [rdx+0ACh], eax
0x14002c3a4  mov     rax, [rsi]
0x14002c3a7  mov     rcx, [rax]
0x14002c3aa  mov     [rcx+0B0h], r9d
0x14002c3b1  mov     rax, [rsi]
0x14002c3b4  mov     rcx, [rax]
0x14002c3b7  mov     [rcx+0B4h], r8d
  ... truncated ...
```
