# CTieredVolume::UpgradePinnedDataDatabaseToDscAttribute(void)

- ea: `0x140017120`
- end: `0x140017423`
- name: `?UpgradePinnedDataDatabaseToDscAttribute@CTieredVolume@@AEAAJXZ`
- size: `771`
- prototype: `__int64 __fastcall(CTieredVolume *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400127dc`

## callees

- `0x140004ef0`
- `0x140005420`
- `0x14000b7f8`
- `0x140017120`
- `0x140017ee8`
- `0x1400188b8`
- `0x1400194ec`
- `0x1400197b0`
- `0x14001a1d4`
- `0x14001b328`
- `0x14001cb24`
- `0x14001cb9c`
- `0x140020390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400173e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400173a6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400173a6`

## pseudocode

```c
__int64 __fastcall CTieredVolume::UpgradePinnedDataDatabaseToDscAttribute(CTieredVolume *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  int v5; // edx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  bool v9; // dl
  int v10; // eax
  int v11; // eax
  const WCHAR *v12; // rcx
  char LastError; // al
  int v14; // r8d
  signed int v15; // eax
  _BYTE v17[8]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-48h]
  JET_SESID v19[4]; // [rsp+40h] [rbp-40h] BYREF
  __int16 v20; // [rsp+60h] [rbp-20h]
  char v21; // [rsp+62h] [rbp-1Eh]
  __int64 v22; // [rsp+68h] [rbp-18h]
  char v23; // [rsp+70h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieredVolume::UpgradePinnedDataDatabaseToDscAttribute";
  CHResultImp::CHResultImp((CHResultImp *)v17);
  LOBYTE(v19[0]) = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v2 = TieringJetSession::Initialize((TieringJetSession *)v19, (RTL_SRWLOCK **)this + 168);
  v18 = v2;
  v3 = v2;
  if ( v2 >= 0 )
  {
    v2 = TieringJetSession::OpenJetTable((TieringJetSession *)v19, 0);
    v18 = v2;
    v3 = v2;
    if ( v2 >= 0 )
    {
      v6 = TieringPinnedSession::MigratePinnedDatabaseToDscAttribute(v19);
      v18 = v6;
      v3 = v6;
      if ( v6 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          160,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v6);
      }
      v7 = TieringJetSession::CloseJetTable((TieringJetSession *)v19, 1);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v7);
      }
      v8 = TieringJetDatabase::CloseDatabase((CTieredVolume *)((char *)this + 1344), 0, 0);
      if ( v8 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          162,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v8);
      }
      v10 = TieringJetDatabase::WaitForDatabaseClose((CTieredVolume *)((char *)this + 1344), v9);
      if ( v10 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v10);
      }
      v11 = CTieredVolume::UninitializeJetInstance(this, (unsigned __int64 *)this + 145);
      if ( v11 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          164,
          (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          (_DWORD)this + 672,
          v11);
      }
      v12 = (const WCHAR *)*((_QWORD *)this + 108);
      *((_BYTE *)this + 1152) = 0;
      if ( !DeleteFileW(v12) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_ZD(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, v14, (_DWORD)this + 672, LastError);
        }
        v15 = GetLastError();
        v3 = v15;
        if ( v15 > 0 )
          v3 = (unsigned __int16)v15 | 0x80070000;
        v18 = v3;
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 159;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 158;
LABEL_11:
      WPP_SF_Zd(v4[2], v5, (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, (_DWORD)this + 672, v2);
    }
  }
  TieringJetSession::~TieringJetSession((TieringJetSession *)v19);
  CHResultImp::~CHResultImp((CHResultImp *)v17);
  return v3;
}

```

## disassembly

```asm
0x140017120  push    rbp
0x140017122  push    rbx
0x140017123  push    r13
0x140017125  push    r14
0x140017127  push    r15
0x140017129  mov     rbp, rsp
0x14001712c  sub     rsp, 80h
0x140017133  mov     rax, gs:58h
0x14001713c  mov     r15, rcx
0x14001713f  mov     ecx, 8
0x140017144  mov     rdx, [rax]
0x140017147  lea     rax, aCtieredvolumeU_0; "CTieredVolume::UpgradePinnedDataDatabas"...
0x14001714e  mov     [rcx+rdx], rax
0x140017152  lea     rcx, [rbp+var_50]; this
0x140017156  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14001715b  lea     r13, [r15+540h]
0x140017162  mov     byte ptr [rbp+var_40], 0
0x140017166  mov     rdx, r13; struct TieringJetDatabase *
0x140017169  mov     [rbp+var_20], 0
0x14001716f  lea     rcx, [rbp+var_40]; this
0x140017173  mov     [rbp+var_1E], 0
0x140017177  mov     [rbp+var_18], 0
0x14001717f  mov     [rbp+var_10], 0
0x140017183  call    ?Initialize@TieringJetSession@@QEAAJPEAVTieringJetDatabase@@@Z; TieringJetSession::Initialize(TieringJetDatabase *)
0x140017188  mov     [rbp+var_48], eax
0x14001718b  mov     ebx, eax
0x14001718d  test    eax, eax
0x14001718f  jns     short loc_1400171C3
0x140017191  mov     rcx, cs:WPP_GLOBAL_Control
0x140017198  lea     r14, WPP_GLOBAL_Control
0x14001719f  cmp     rcx, r14
0x1400171a2  jz      loc_1400173FF
0x1400171a8  test    byte ptr [rcx+1Ch], 1
0x1400171ac  jz      loc_1400173FF
0x1400171b2  cmp     byte ptr [rcx+19h], 2
0x1400171b6  jb      loc_1400173FF
0x1400171bc  mov     edx, 9Eh
0x1400171c1  jmp     short loc_140017207
0x1400171c3  xor     edx, edx; bool
0x1400171c5  lea     rcx, [rbp+var_40]; this
0x1400171c9  call    ?OpenJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::OpenJetTable(bool)
0x1400171ce  mov     [rbp+var_48], eax
0x1400171d1  mov     ebx, eax
0x1400171d3  test    eax, eax
0x1400171d5  jns     short loc_140017227
0x1400171d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171de  lea     r14, WPP_GLOBAL_Control
0x1400171e5  cmp     rcx, r14
0x1400171e8  jz      loc_1400173FF
0x1400171ee  test    byte ptr [rcx+1Ch], 1
0x1400171f2  jz      loc_1400173FF
0x1400171f8  cmp     byte ptr [rcx+19h], 2
0x1400171fc  jb      loc_1400173FF
0x140017202  mov     edx, 9Fh
0x140017207  mov     rcx, [rcx+10h]
0x14001720b  lea     r9, [r15+2A0h]
0x140017212  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140017219  mov     [rsp+80h+var_60], eax
0x14001721d  call    WPP_SF_Zd
0x140017222  jmp     loc_1400173FF
0x140017227  lea     rcx, [rbp+var_40]; this
0x14001722b  call    ?MigratePinnedDatabaseToDscAttribute@TieringPinnedSession@@QEAAJXZ; TieringPinnedSession::MigratePinnedDatabaseToDscAttribute(void)
0x140017230  mov     [rbp+var_48], eax
0x140017233  mov     ebx, eax
0x140017235  lea     r14, WPP_GLOBAL_Control
0x14001723c  test    eax, eax
0x14001723e  jns     short loc_140017278
0x140017240  mov     rcx, cs:WPP_GLOBAL_Control
0x140017247  cmp     rcx, r14
0x14001724a  jz      short loc_140017278
0x14001724c  test    byte ptr [rcx+1Ch], 1
0x140017250  jz      short loc_140017278
0x140017252  cmp     byte ptr [rcx+19h], 2
0x140017256  jb      short loc_140017278
0x140017258  mov     rcx, [rcx+10h]
0x14001725c  lea     r9, [r15+2A0h]
0x140017263  mov     edx, 0A0h
0x140017268  mov     [rsp+80h+var_60], eax
0x14001726c  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140017273  call    WPP_SF_Zd
0x140017278  mov     dl, 1; bool
0x14001727a  lea     rcx, [rbp+var_40]; this
0x14001727e  call    ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x140017283  test    eax, eax
0x140017285  jns     short loc_1400172BF
0x140017287  mov     rcx, cs:WPP_GLOBAL_Control
0x14001728e  cmp     rcx, r14
0x140017291  jz      short loc_1400172BF
0x140017293  test    byte ptr [rcx+1Ch], 1
0x140017297  jz      short loc_1400172BF
0x140017299  cmp     byte ptr [rcx+19h], 2
0x14001729d  jb      short loc_1400172BF
0x14001729f  mov     rcx, [rcx+10h]
0x1400172a3  lea     r9, [r15+2A0h]
0x1400172aa  mov     edx, 0A1h
0x1400172af  mov     [rsp+80h+var_60], eax
0x1400172b3  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400172ba  call    WPP_SF_Zd
0x1400172bf  xor     r8d, r8d; bool
0x1400172c2  xor     edx, edx; bool
0x1400172c4  mov     rcx, r13; this
0x1400172c7  call    ?CloseDatabase@TieringJetDatabase@@QEAAJ_N0@Z; TieringJetDatabase::CloseDatabase(bool,bool)
0x1400172cc  test    eax, eax
0x1400172ce  jns     short loc_140017308
0x1400172d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172d7  cmp     rcx, r14
0x1400172da  jz      short loc_140017308
0x1400172dc  test    byte ptr [rcx+1Ch], 1
0x1400172e0  jz      short loc_140017308
0x1400172e2  cmp     byte ptr [rcx+19h], 2
0x1400172e6  jb      short loc_140017308
0x1400172e8  mov     rcx, [rcx+10h]
0x1400172ec  lea     r9, [r15+2A0h]
0x1400172f3  mov     edx, 0A2h
0x1400172f8  mov     [rsp+80h+var_60], eax
0x1400172fc  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140017303  call    WPP_SF_Zd
0x140017308  mov     rcx, r13; this
0x14001730b  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x140017310  test    eax, eax
0x140017312  jns     short loc_14001734C
0x140017314  mov     rcx, cs:WPP_GLOBAL_Control
0x14001731b  cmp     rcx, r14
0x14001731e  jz      short loc_14001734C
0x140017320  test    byte ptr [rcx+1Ch], 1
0x140017324  jz      short loc_14001734C
0x140017326  cmp     byte ptr [rcx+19h], 2
0x14001732a  jb      short loc_14001734C
0x14001732c  mov     rcx, [rcx+10h]
0x140017330  lea     r9, [r15+2A0h]
0x140017337  mov     edx, 0A3h
0x14001733c  mov     [rsp+80h+var_60], eax
0x140017340  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140017347  call    WPP_SF_Zd
0x14001734c  lea     rdx, [r15+488h]; unsigned __int64 *
0x140017353  mov     rcx, r15; this
0x140017356  call    ?UninitializeJetInstance@CTieredVolume@@QEAAJPEA_K@Z; CTieredVolume::UninitializeJetInstance(unsigned __int64 *)
0x14001735b  test    eax, eax
0x14001735d  jns     short loc_140017397
0x14001735f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017366  cmp     rcx, r14
0x140017369  jz      short loc_140017397
0x14001736b  test    byte ptr [rcx+1Ch], 1
0x14001736f  jz      short loc_140017397
0x140017371  cmp     byte ptr [rcx+19h], 2
0x140017375  jb      short loc_140017397
0x140017377  mov     rcx, [rcx+10h]
0x14001737b  lea     r9, [r15+2A0h]
0x140017382  mov     edx, 0A4h
0x140017387  mov     [rsp+80h+var_60], eax
0x14001738b  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140017392  call    WPP_SF_Zd
0x140017397  mov     rcx, [r15+360h]; lpFileName
0x14001739e  mov     byte ptr [r15+480h], 0
0x1400173a6  call    cs:__imp_DeleteFileW
0x1400173ac  test    eax, eax
0x1400173ae  jnz     short loc_1400173FF
0x1400173b0  call    cs:__imp_GetLastError
0x1400173b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173bd  cmp     rcx, r14
0x1400173c0  jz      short loc_1400173E7
0x1400173c2  test    byte ptr [rcx+1Ch], 1
0x1400173c6  jz      short loc_1400173E7
0x1400173c8  cmp     byte ptr [rcx+19h], 2
0x1400173cc  jb      short loc_1400173E7
0x1400173ce  mov     rcx, [rcx+10h]
0x1400173d2  lea     r9, [r15+2A0h]
0x1400173d9  mov     edx, 0A5h
0x1400173de  mov     [rsp+80h+var_60], eax
0x1400173e2  call    WPP_SF_ZD
0x1400173e7  call    cs:__imp_GetLastError
0x1400173ed  mov     ebx, eax
0x1400173ef  test    eax, eax
0x1400173f1  jle     short loc_1400173FC
0x1400173f3  movzx   ebx, ax
0x1400173f6  or      ebx, 80070000h
0x1400173fc  mov     [rbp+var_48], ebx
0x1400173ff  lea     rcx, [rbp+var_40]; this
0x140017403  call    ??1TieringJetSession@@QEAA@XZ; TieringJetSession::~TieringJetSession(void)
0x140017408  lea     rcx, [rbp+var_50]; this
0x14001740c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140017411  mov     eax, ebx
0x140017413  add     rsp, 80h
0x14001741a  pop     r15
0x14001741c  pop     r14
0x14001741e  pop     r13
0x140017420  pop     rbx
0x140017421  pop     rbp
0x140017422  retn
```
