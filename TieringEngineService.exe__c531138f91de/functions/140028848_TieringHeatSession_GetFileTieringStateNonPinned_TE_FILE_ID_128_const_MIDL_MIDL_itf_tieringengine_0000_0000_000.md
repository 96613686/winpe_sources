# TieringHeatSession::GetFileTieringStateNonPinned(TE_FILE_ID_128 const *,__MIDL___MIDL_itf_tieringengine_0000_0000_0002 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0003 *)

- ea: `0x140028848`
- end: `0x140028e73`
- name: `?GetFileTieringStateNonPinned@TieringHeatSession@@QEAAJPEBUTE_FILE_ID_128@@PEAW4__MIDL___MIDL_itf_tieringengine_0000_0000_0002@@PEAW4__MIDL___MIDL_itf_tieringengine_0000_0000_0003@@@Z`
- size: `1579`
- prototype: `__int64 __fastcall(TieringHeatSession *__hidden this, const struct TE_FILE_ID_128 *Source2, enum __MIDL___MIDL_itf_tieringengine_0000_0000_0002 *, enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003cfb4`

## callees

- `0x140002db0`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140020ecc`
- `0x140021018`
- `0x14002670c`
- `0x14002866c`
- `0x140028848`
- `0x14002b9dc`
- `0x14003fbb0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1400288b6`
- `ntdll!RtlCompareMemory` at `0x140028b4e`
- `ntdll!RtlCompareMemory` at `0x1400288b6`
- `ntdll!RtlCompareMemory` at `0x140028b4e`
- `ESENT!JetMove` at `0x140028c0c`
- `ESENT!JetMove` at `0x140028c0c`
- `ESENT!JetMakeKey` at `0x14002892b`
- `ESENT!JetMakeKey` at `0x14002892b`
- `ESENT!JetSeek` at `0x1400289ce`
- `ESENT!JetSeek` at `0x1400289ce`

## pseudocode

```c
__int64 __fastcall TieringHeatSession::GetFileTieringStateNonPinned(
        TieringHeatSession *this,
        const struct TE_FILE_ID_128 *Source2,
        enum __MIDL___MIDL_itf_tieringengine_0000_0000_0002 *a3,
        enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *a4)
{
  PVOID ThreadLocalStoragePointer; // rax
  enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *v7; // rbx
  unsigned int v9; // ebx
  JET_ERR Key; // eax
  JET_ERR v11; // r8d
  int v12; // eax
  _QWORD *v13; // rcx
  int v14; // edx
  JET_ERR v15; // eax
  int v16; // eax
  int v18; // r12d
  JET_ERR CurrentHeatRecord; // eax
  int v20; // r8d
  JET_ERR v21; // eax
  int v22; // ebx
  int v23; // ebx
  int v24; // eax
  _QWORD *v25; // rcx
  int v26; // edx
  int v27; // eax
  char v28; // [rsp+60h] [rbp-59h] BYREF
  char v29; // [rsp+61h] [rbp-58h] BYREF
  unsigned __int8 v30[2]; // [rsp+62h] [rbp-57h] BYREF
  unsigned __int16 v31; // [rsp+64h] [rbp-55h] BYREF
  enum __MIDL___MIDL_itf_tieringengine_0000_0000_0003 *v32; // [rsp+68h] [rbp-51h]
  int v33; // [rsp+70h] [rbp-49h]
  int v34; // [rsp+74h] [rbp-45h]
  int v35; // [rsp+78h] [rbp-41h]
  unsigned int v36; // [rsp+7Ch] [rbp-3Dh] BYREF
  _BYTE v37[8]; // [rsp+80h] [rbp-39h] BYREF
  int v38; // [rsp+88h] [rbp-31h]
  int v39; // [rsp+90h] [rbp-29h] BYREF
  __int64 v40; // [rsp+98h] [rbp-21h] BYREF
  __int128 Source1; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int16 v42[4]; // [rsp+B0h] [rbp-9h] BYREF
  int v43; // [rsp+B8h] [rbp-1h]
  __int16 v44; // [rsp+BCh] [rbp+3h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v7 = a4;
  v32 = a4;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "TieringHeatSession::GetFileTieringStateNonPinned";
  CHResultImp::CHResultImp((CHResultImp *)v37);
  if ( RtlCompareMemory(Source2, &NullGuid, 0x10u) == 16 )
  {
    v9 = -2138898428;
    v38 = -2138898428;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids, 2156068868LL);
    }
    goto LABEL_37;
  }
  Key = JetMakeKey(*((_QWORD *)this + 1), *((_QWORD *)this + 3), Source2, 0x10u, 1u);
  v11 = Key;
  if ( Key )
  {
    if ( Key == -529 || Key == -1092 || Key == -1808 )
    {
      v9 = ATL::AtlHresultFromWin32(112);
    }
    else if ( Key == -1011 )
    {
      v9 = -2147024882;
    }
    else
    {
      v12 = -Key;
      if ( v12 < 0 )
        LOWORD(v12) = v11;
      v9 = v11 & 0x8E5E0000 | (unsigned __int16)v12 | 0xE5E0000;
    }
    v38 = v9;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v14 = 49;
    goto LABEL_36;
  }
  v15 = JetSeek(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 8u);
  v11 = v15;
  if ( ((v15 + 1603) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_iiS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
        *((_QWORD *)Source2 + 1),
        *(_QWORD *)Source2,
        *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
    }
    *(_DWORD *)a3 = 1;
    *(_DWORD *)v7 = 4;
    goto LABEL_99;
  }
  if ( v15 && v15 != 1039 )
  {
    if ( v15 == -529 || v15 == -1092 || v15 == -1808 )
    {
      v9 = ATL::AtlHresultFromWin32(112);
    }
    else if ( v15 == -1011 )
    {
      v9 = -2147024882;
    }
    else
    {
      v16 = -v15;
      if ( v16 < 0 )
        LOWORD(v16) = v11;
      v9 = v11 & 0x8E5E0000 | (unsigned __int16)v16 | 0xE5E0000;
    }
    v38 = v9;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_37;
    }
    v14 = 51;
LABEL_36:
    WPP_SF_iiSd(
      v13[2],
      v14,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)Source2 + 1),
      *(_QWORD *)Source2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v11);
LABEL_37:
    CHResultImp::~CHResultImp((CHResultImp *)v37);
    return v9;
  }
  v35 = 0;
  v18 = 0;
  v33 = 0;
  v34 = 0;
  while ( 1 )
  {
    v30[0] = 0;
    *(_QWORD *)v42 = 0;
    v43 = 0;
    v44 = 0;
    v28 = 0;
    v29 = 0;
    v40 = 0;
    Source1 = 0;
    v31 = 0;
    v36 = 0;
    CurrentHeatRecord = TieringHeatSession::GetCurrentHeatRecord(
                          this,
                          1u,
                          (struct TE_FILE_ID_128 *)&Source1,
                          &v40,
                          v30,
                          (unsigned __int8 *)&v28,
                          (unsigned __int8 *)&v29,
                          &v31,
                          v42);
    v20 = CurrentHeatRecord;
    if ( CurrentHeatRecord != -1017 )
      break;
LABEL_53:
    v21 = JetMove(*((_QWORD *)this + 1), *((_QWORD *)this + 3), 1, 0);
    v20 = v21;
    if ( v21 == -1603 )
      goto LABEL_84;
    if ( v21 && v21 != -1017 )
    {
      if ( v21 == -529 || v21 == -1092 || v21 == -1808 )
      {
        v22 = ATL::AtlHresultFromWin32(112);
      }
      else if ( v21 == -1011 )
      {
        v22 = -2147024882;
      }
      else
      {
        v27 = -v21;
        if ( v27 < 0 )
          LOWORD(v27) = v20;
        v22 = v20 & 0x8E5E0000 | (unsigned __int16)v27 | 0xE5E0000;
      }
      v38 = v22;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = 53;
        goto LABEL_82;
      }
      goto LABEL_83;
    }
  }
  switch ( CurrentHeatRecord )
  {
    case 0:
      if ( RtlCompareMemory(&Source1, Source2, 0x10u) != 16 )
        goto LABEL_84;
      v39 = 0;
      TieringHeatSession::AddCurrentCountAndAgeHistory(
        this,
        (const struct TE_FILE_ID_128 *)&Source1,
        v40,
        0,
        v29,
        v31,
        v28,
        v42,
        &v39,
        &v36,
        0);
      if ( ((v28 & 0x20) == 0 || v31)
        && ((v30[0] & 0x10) == 0 || v36 <= *(_DWORD *)(**((_QWORD **)this + 5) + 228LL))
        && ((v30[0] & 0x20) == 0 || v36 >= *(_DWORD *)(**((_QWORD **)this + 5) + 224LL)) )
      {
        if ( (v30[0] & 0x80u) == 0 )
        {
          ++v33;
LABEL_52:
          ++v35;
          goto LABEL_53;
        }
        ++v34;
      }
      ++v18;
      goto LABEL_52;
    case -529:
    case -1092:
    case -1808:
      v23 = ATL::AtlHresultFromWin32(112);
      break;
    case -1011:
      v23 = -2147024882;
      break;
    default:
      v24 = -CurrentHeatRecord;
      if ( v20 > 0 )
        LOWORD(v24) = v20;
      v23 = v20 & 0x8E5E0000 | (unsigned __int16)v24 | 0xE5E0000;
      break;
  }
  v38 = v23;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = 52;
LABEL_82:
    WPP_SF_iiSd(
      v25[2],
      v26,
      (unsigned int)&WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids,
      *((_QWORD *)Source2 + 1),
      *(_QWORD *)Source2,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v20);
  }
LABEL_83:
  v7 = v32;
LABEL_84:
  if ( v33 )
  {
    *(_DWORD *)v7 = 2;
    *(_DWORD *)a3 = 3 - (v18 != 0);
  }
  else if ( v18 && v34 )
  {
    *(_DWORD *)a3 = 0;
    *(_DWORD *)v7 = 0;
  }
  else
  {
    *(_DWORD *)a3 = 1;
    *(_DWORD *)v7 = 1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_iiDDDS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL),
      v20,
      *((_QWORD *)Source2 + 1),
      *(_QWORD *)Source2,
      *(_DWORD *)a3,
      *(_DWORD *)v7,
      v35,
      *(_QWORD *)(*((_QWORD *)this + 5) + 112LL));
  }
LABEL_99:
  CHResultImp::~CHResultImp((CHResultImp *)v37);
  return 0;
}

```

## disassembly

```asm
0x140028848  push    rbp
0x14002884a  push    rbx
0x14002884b  push    rsi
0x14002884c  push    rdi
0x14002884d  push    r12
0x14002884f  push    r13
0x140028851  push    r14
0x140028853  push    r15
0x140028855  lea     rbp, [rsp-1Fh]
0x14002885a  sub     rsp, 0D8h
0x140028861  mov     rax, cs:__security_cookie
0x140028868  xor     rax, rsp
0x14002886b  mov     [rbp+57h+var_50], rax
0x14002886f  mov     rax, gs:58h
0x140028878  mov     r15, rcx
0x14002887b  mov     r14, rdx
0x14002887e  mov     ecx, 8
0x140028883  mov     rbx, r9
0x140028886  mov     r13, r8
0x140028889  mov     [rbp+57h+var_A8], rbx
0x14002888d  mov     rdx, [rax]
0x140028890  lea     rax, aTieringheatses_8; "TieringHeatSession::GetFileTieringState"...
0x140028897  mov     [rcx+rdx], rax
0x14002889b  lea     rcx, [rbp+57h+var_90]; this
0x14002889f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400288a4  mov     esi, 10h
0x1400288a9  lea     rdx, ?NullGuid@@3U_GUID@@A; Source2
0x1400288b0  mov     r8d, esi; Length
0x1400288b3  mov     rcx, r14; Source1
0x1400288b6  call    cs:__imp_RtlCompareMemory
0x1400288bc  cmp     rax, rsi
0x1400288bf  jnz     short loc_140028914
0x1400288c1  mov     ebx, 80830004h
0x1400288c6  mov     [rbp+57h+var_88], ebx
0x1400288c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400288d0  lea     rsi, WPP_GLOBAL_Control
0x1400288d7  cmp     rcx, rsi
0x1400288da  jz      loc_140028A9B
0x1400288e0  mov     edi, 1
0x1400288e5  test    [rcx+1Ch], dil
0x1400288e9  jz      loc_140028A9B
0x1400288ef  cmp     byte ptr [rcx+19h], 2
0x1400288f3  jb      loc_140028A9B
0x1400288f9  mov     rcx, [rcx+10h]
0x1400288fd  lea     edx, [rdi+2Fh]
0x140028900  mov     r9d, ebx
0x140028903  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x14002890a  call    WPP_SF_d
0x14002890f  jmp     loc_140028A9B
0x140028914  mov     rdx, [r15+18h]; tableid
0x140028918  mov     edi, 1
0x14002891d  mov     rcx, [r15+8]; sesid
0x140028921  mov     r9d, esi; cbData
0x140028924  mov     r8, r14; pvData
0x140028927  mov     [rsp+110h+grbit], edi; grbit
0x14002892b  call    cs:__imp_JetMakeKey
0x140028931  xor     esi, esi
0x140028933  mov     r8d, eax
0x140028936  test    eax, eax
0x140028938  jz      loc_1400289C0
0x14002893e  cmp     eax, 0FFFFFDEFh
0x140028943  jz      short loc_14002897C
0x140028945  cmp     eax, 0FFFFFBBCh
0x14002894a  jz      short loc_14002897C
0x14002894c  cmp     eax, 0FFFFF8F0h
0x140028951  jz      short loc_14002897C
0x140028953  cmp     eax, 0FFFFFC0Dh
0x140028958  jnz     short loc_140028961
0x14002895a  mov     ebx, 8007000Eh
0x14002895f  jmp     short loc_140028988
0x140028961  neg     eax
0x140028963  cmovs   eax, r8d
0x140028967  movzx   ebx, ax
0x14002896a  mov     eax, r8d
0x14002896d  and     eax, 8E5E0000h
0x140028972  or      ebx, eax
0x140028974  or      ebx, 0E5E0000h
0x14002897a  jmp     short loc_140028988
0x14002897c  mov     ecx, 70h ; 'p'; unsigned int
0x140028981  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028986  mov     ebx, eax
0x140028988  mov     [rbp+57h+var_88], ebx
0x14002898b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028992  lea     rsi, WPP_GLOBAL_Control
0x140028999  cmp     rcx, rsi
0x14002899c  jz      loc_140028A9B
0x1400289a2  test    [rcx+1Ch], dil
0x1400289a6  jz      loc_140028A9B
0x1400289ac  cmp     byte ptr [rcx+19h], 2
0x1400289b0  jb      loc_140028A9B
0x1400289b6  mov     edx, 31h ; '1'
0x1400289bb  jmp     loc_140028A6D
0x1400289c0  mov     rdx, [r15+18h]; tableid
0x1400289c4  mov     r8d, 8; grbit
0x1400289ca  mov     rcx, [r15+8]; sesid
0x1400289ce  call    cs:__imp_JetSeek
0x1400289d4  mov     r8d, eax
0x1400289d7  lea     ecx, [rax+643h]
0x1400289dd  test    ecx, 0FFFFFFFDh
0x1400289e3  jz      loc_140028DF1
0x1400289e9  test    eax, eax
0x1400289eb  jz      loc_140028AAB
0x1400289f1  cmp     eax, 40Fh
0x1400289f6  jz      loc_140028AAB
0x1400289fc  cmp     eax, 0FFFFFDEFh
0x140028a01  jz      short loc_140028A3A
0x140028a03  cmp     eax, 0FFFFFBBCh
0x140028a08  jz      short loc_140028A3A
0x140028a0a  cmp     eax, 0FFFFF8F0h
0x140028a0f  jz      short loc_140028A3A
0x140028a11  cmp     eax, 0FFFFFC0Dh
0x140028a16  jnz     short loc_140028A1F
0x140028a18  mov     ebx, 8007000Eh
0x140028a1d  jmp     short loc_140028A46
0x140028a1f  neg     eax
0x140028a21  cmovs   eax, r8d
0x140028a25  movzx   ebx, ax
0x140028a28  mov     eax, r8d
0x140028a2b  and     eax, 8E5E0000h
0x140028a30  or      ebx, eax
0x140028a32  or      ebx, 0E5E0000h
0x140028a38  jmp     short loc_140028A46
0x140028a3a  mov     ecx, 70h ; 'p'; unsigned int
0x140028a3f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028a44  mov     ebx, eax
0x140028a46  mov     [rbp+57h+var_88], ebx
0x140028a49  mov     rcx, cs:WPP_GLOBAL_Control
0x140028a50  lea     rsi, WPP_GLOBAL_Control
0x140028a57  cmp     rcx, rsi
0x140028a5a  jz      short loc_140028A9B
0x140028a5c  test    [rcx+1Ch], dil
0x140028a60  jz      short loc_140028A9B
0x140028a62  cmp     byte ptr [rcx+19h], 2
0x140028a66  jb      short loc_140028A9B
0x140028a68  mov     edx, 33h ; '3'
0x140028a6d  mov     rax, [r15+28h]
0x140028a71  mov     r9, [r14+8]
0x140028a75  mov     rcx, [rcx+10h]
0x140028a79  mov     dword ptr [rsp+110h+var_E0], r8d
0x140028a7e  lea     r8, WPP_13c161b4e9ab39dc8123a15d238dcb36_Traceguids
0x140028a85  mov     rax, [rax+70h]
0x140028a89  mov     [rsp+110h+var_E8], rax
0x140028a8e  mov     rax, [r14]
0x140028a91  mov     qword ptr [rsp+110h+grbit], rax
0x140028a96  call    WPP_SF_iiSd
0x140028a9b  lea     rcx, [rbp+57h+var_90]; this
0x140028a9f  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140028aa4  mov     eax, ebx
0x140028aa6  jmp     loc_140028E53
0x140028aab  mov     [rbp+57h+var_98], esi
0x140028aae  mov     r12d, esi
0x140028ab1  mov     [rbp+57h+var_A0], esi
0x140028ab4  mov     [rbp+57h+var_9C], esi
0x140028ab7  jmp     short loc_140028ABB
0x140028ab9  xor     esi, esi
0x140028abb  xor     eax, eax
0x140028abd  mov     [rbp+57h+var_AE], sil
0x140028ac1  mov     qword ptr [rbp+57h+var_60], rax
0x140028ac5  lea     r9, [rbp+57h+var_78]; __int64 *
0x140028ac9  mov     [rbp+57h+var_58], eax
0x140028acc  lea     r8, [rbp+57h+Source1]; struct TE_FILE_ID_128 *
0x140028ad0  mov     [rbp+57h+var_54], ax
0x140028ad4  xorps   xmm0, xmm0
0x140028ad7  lea     rax, [rbp+57h+var_60]
0x140028adb  mov     [rbp+57h+var_B0], sil
0x140028adf  mov     [rsp+110h+var_D0], rax; unsigned __int16 *
0x140028ae4  mov     dl, dil; bool
0x140028ae7  lea     rax, [rbp+57h+var_AC]
0x140028aeb  mov     [rbp+57h+var_AF], sil
0x140028aef  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x140028af4  mov     rcx, r15; this
0x140028af7  lea     rax, [rbp+57h+var_AF]
0x140028afb  mov     [rbp+57h+var_78], rsi
0x140028aff  mov     [rsp+110h+var_E0], rax; unsigned __int8 *
0x140028b04  lea     rax, [rbp+57h+var_B0]
0x140028b08  mov     [rsp+110h+var_E8], rax; unsigned __int8 *
0x140028b0d  lea     rax, [rbp+57h+var_AE]
0x140028b11  mov     qword ptr [rsp+110h+grbit], rax; unsigned __int8 *
0x140028b16  movups  [rbp+57h+Source1], xmm0
0x140028b1a  mov     [rbp+57h+var_AC], si
0x140028b1e  mov     [rbp+57h+var_94], esi
0x140028b21  call    ?GetCurrentHeatRecord@TieringHeatSession@@QEAAJ_NPEAUTE_FILE_ID_128@@PEA_JPEAE33PEAG4@Z; TieringHeatSession::GetCurrentHeatRecord(bool,TE_FILE_ID_128 *,__int64 *,uchar *,uchar *,uchar *,ushort *,ushort *)
0x140028b26  lea     rsi, WPP_GLOBAL_Control
0x140028b2d  mov     r8d, eax
0x140028b30  cmp     eax, 0FFFFFC07h
0x140028b35  jz      loc_140028BFE
0x140028b3b  test    eax, eax
0x140028b3d  jnz     loc_140028C69
0x140028b43  lea     r8d, [rax+10h]; Length
0x140028b47  mov     rdx, r14; Source2
0x140028b4a  lea     rcx, [rbp+57h+Source1]; Source1
0x140028b4e  call    cs:__imp_RtlCompareMemory
0x140028b54  cmp     rax, 10h
0x140028b58  jnz     loc_140028D61
0x140028b5e  mov     r8, [rbp+57h+var_78]; __int64
0x140028b62  lea     rdx, [rbp+57h+Source1]; struct TE_FILE_ID_128 *
0x140028b66  xor     eax, eax
0x140028b68  xor     r9d, r9d; unsigned int
0x140028b6b  mov     [rsp+110h+var_C0], rax; unsigned int *
0x140028b70  mov     rcx, r15; this
0x140028b73  mov     [rbp+57h+var_80], eax
0x140028b76  lea     rax, [rbp+57h+var_94]
0x140028b7a  mov     [rsp+110h+var_C8], rax; unsigned int *
0x140028b7f  lea     rax, [rbp+57h+var_80]
0x140028b83  mov     [rsp+110h+var_D0], rax; int *
0x140028b88  lea     rax, [rbp+57h+var_60]
0x140028b8c  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x140028b91  mov     al, [rbp+57h+var_B0]
0x140028b94  mov     byte ptr [rsp+110h+var_E0], al; char
0x140028b98  movzx   eax, [rbp+57h+var_AC]
0x140028b9c  mov     word ptr [rsp+110h+var_E8], ax; unsigned __int16
0x140028ba1  mov     al, [rbp+57h+var_AF]
0x140028ba4  mov     byte ptr [rsp+110h+grbit], al; char
0x140028ba8  call    ?AddCurrentCountAndAgeHistory@TieringHeatSession@@QEAAXPEBUTE_FILE_ID_128@@_JKEGEPEAGPEAHPEAK4@Z; TieringHeatSession::AddCurrentCountAndAgeHistory(TE_FILE_ID_128 const *,__int64,ulong,uchar,ushort,uchar,ushort *,int *,ulong *,ulong *)
0x140028bad  test    [rbp+57h+var_B0], 20h
0x140028bb1  jz      short loc_140028BBB
0x140028bb3  xor     eax, eax
0x140028bb5  cmp     [rbp+57h+var_AC], ax
0x140028bb9  jz      short loc_140028BF8
0x140028bbb  mov     dl, [rbp+57h+var_AE]
0x140028bbe  mov     r8d, [rbp+57h+var_94]
0x140028bc2  test    dl, 10h
0x140028bc5  jz      short loc_140028BD7
0x140028bc7  mov     rax, [r15+28h]
0x140028bcb  mov     rcx, [rax]
0x140028bce  cmp     r8d, [rcx+0E4h]
0x140028bd5  ja      short loc_140028BF8
0x140028bd7  test    dl, 20h
0x140028bda  jz      short loc_140028BEC
0x140028bdc  mov     rax, [r15+28h]
0x140028be0  mov     rcx, [rax]
0x140028be3  cmp     r8d, [rcx+0E0h]
0x140028bea  jb      short loc_140028BF8
0x140028bec  test    dl, dl
0x140028bee  js      short loc_140028BF5
0x140028bf0  add     [rbp+57h+var_A0], edi
0x140028bf3  jmp     short loc_140028BFB
0x140028bf5  add     [rbp+57h+var_9C], edi
0x140028bf8  add     r12d, edi
0x140028bfb  add     [rbp+57h+var_98], edi
0x140028bfe  mov     rdx, [r15+18h]; tableid
0x140028c02  xor     r9d, r9d; grbit
0x140028c05  mov     rcx, [r15+8]; sesid
0x140028c09  mov     r8d, edi; cRow
0x140028c0c  call    cs:__imp_JetMove
0x140028c12  mov     r8d, eax
0x140028c15  cmp     eax, 0FFFFF9BDh
0x140028c1a  jz      loc_140028D61
0x140028c20  test    eax, eax
0x140028c22  jz      loc_140028AB9
0x140028c28  cmp     eax, 0FFFFFC07h
0x140028c2d  jz      loc_140028AB9
0x140028c33  cmp     eax, 0FFFFFDEFh
0x140028c38  jz      loc_140028D03
0x140028c3e  cmp     eax, 0FFFFFBBCh
0x140028c43  jz      loc_140028D03
0x140028c49  cmp     eax, 0FFFFF8F0h
0x140028c4e  jz      loc_140028D03
0x140028c54  cmp     eax, 0FFFFFC0Dh
0x140028c59  jnz     loc_140028CE8
0x140028c5f  mov     ebx, 8007000Eh
0x140028c64  jmp     loc_140028D0F
0x140028c69  cmp     r8d, 0FFFFFDEFh
0x140028c70  jz      short loc_140028CB2
0x140028c72  cmp     r8d, 0FFFFFBBCh
0x140028c79  jz      short loc_140028CB2
0x140028c7b  cmp     r8d, 0FFFFF8F0h
0x140028c82  jz      short loc_140028CB2
0x140028c84  cmp     r8d, 0FFFFFC0Dh
0x140028c8b  jnz     short loc_140028C94
0x140028c8d  mov     ebx, 8007000Eh
0x140028c92  jmp     short loc_140028CBE
0x140028c94  mov     eax, r8d
0x140028c97  neg     eax
0x140028c99  cmovs   eax, r8d
0x140028c9d  movzx   ebx, ax
0x140028ca0  mov     eax, r8d
0x140028ca3  and     eax, 8E5E0000h
0x140028ca8  or      ebx, eax
0x140028caa  or      ebx, 0E5E0000h
0x140028cb0  jmp     short loc_140028CBE
0x140028cb2  mov     ecx, 70h ; 'p'; unsigned int
0x140028cb7  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x140028cbc  mov     ebx, eax
0x140028cbe  mov     [rbp+57h+var_88], ebx
0x140028cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140028cc8  cmp     rcx, rsi
0x140028ccb  jz      loc_140028D5D
0x140028cd1  test    [rcx+1Ch], dil
0x140028cd5  jz      loc_140028D5D
0x140028cdb  cmp     byte ptr [rcx+19h], 2
0x140028cdf  jb      short loc_140028D5D
0x140028ce1  mov     edx, 34h ; '4'
0x140028ce6  jmp     short loc_140028D2F
0x140028ce8  neg     eax
0x140028cea  cmovs   eax, r8d
0x140028cee  movzx   ebx, ax
0x140028cf1  mov     eax, r8d
0x140028cf4  and     eax, 8E5E0000h
0x140028cf9  or      ebx, eax
  ... truncated ...
```
