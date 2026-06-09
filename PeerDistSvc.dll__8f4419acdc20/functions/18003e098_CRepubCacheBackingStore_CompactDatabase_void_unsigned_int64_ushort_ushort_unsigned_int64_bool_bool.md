# CRepubCacheBackingStore::CompactDatabase(void *,unsigned __int64,ushort *,ushort *,unsigned __int64,bool,bool *)

- ea: `0x18003e098`
- end: `0x18003e47b`
- name: `?CompactDatabase@CRepubCacheBackingStore@@AEAAKPEAX_KPEAG21_NPEA_N@Z`
- size: `995`
- prototype: `__int64 __fastcall(CRepubCacheBackingStore *this, void *, JET_SESID, unsigned __int16 *, unsigned __int16 *szDatabaseDest, unsigned __int64, bool, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180042374`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800094d4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180018340`
- `0x18003e098`
- `0x18013ab7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e37b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e42f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003e425`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003e425`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003e306`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003e306`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x18003e371`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x18003e371`
- `ESENT!JetDetachDatabaseW` at `0x18003e129`
- `ESENT!JetDetachDatabaseW` at `0x18003e2ac`
- `ESENT!JetDetachDatabaseW` at `0x18003e129`
- `ESENT!JetDetachDatabaseW` at `0x18003e2ac`
- `ESENT!JetAttachDatabase2W` at `0x18003e1a8`
- `ESENT!JetAttachDatabase2W` at `0x18003e1a8`
- `ESENT!JetCompactW` at `0x18003e22a`
- `ESENT!JetCompactW` at `0x18003e22a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepubCacheBackingStore::CompactDatabase(
        CRepubCacheBackingStore *this,
        void *a2,
        JET_SESID a3,
        unsigned __int16 *a4,
        unsigned __int16 *szDatabaseDest,
        unsigned __int64 a6,
        bool a7,
        bool *a8)
{
  char v11; // r13
  JET_ERR v12; // ebx
  CHostedCacheMsgEncoding *v13; // r10
  int v14; // edx
  unsigned int v15; // eax
  DWORD LastError; // ebx
  CHostedCacheMsgEncoding *v17; // r10
  int v18; // eax
  char v19; // al

  v11 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 424, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  *a8 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 425, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, a4);
  }
  v12 = JetDetachDatabaseW(a3, a4);
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_22;
    }
    v14 = 426;
LABEL_14:
    WPP_SF_Sd(
      *((_QWORD *)v13 + 12),
      v14,
      (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
      (_DWORD)a4,
      v12);
LABEL_22:
    LastError = TranslateJetError(v12);
    goto LABEL_51;
  }
  *a8 = 1;
  v15 = JetAttachDatabase2W(a3, a4, a6 >> 15, 0);
  v12 = v15;
  if ( v15 && v15 != 1007 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 427, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v15);
    }
    goto LABEL_22;
  }
  v12 = JetCompactW(a3, a4, szDatabaseDest, CRepubBackgroundPruneCatalogTask::OnBeginPruning, 0, 0);
  v11 = 1;
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_22;
    }
    v14 = 428;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 429, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, a4);
  }
  v12 = JetDetachDatabaseW(a3, a4);
  if ( v12 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_22;
    }
    v14 = 430;
    goto LABEL_14;
  }
  LastError = 0;
  *a8 = 1;
  if ( a7 )
  {
    if ( MoveFileExW(szDatabaseDest, a4, 1u) )
      return LastError;
    LastError = GetLastError();
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        431,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)szDatabaseDest,
        (__int64)a4,
        LastError);
LABEL_50:
      v17 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    if ( DeleteFileTransactedW(a4, a2) )
    {
      v18 = StringCchCopyW(a4, 0x104u, szDatabaseDest);
      if ( v18 >= 0 )
        return LastError;
      LastError = (unsigned __int16)v18;
      goto LABEL_50;
    }
    LastError = GetLastError();
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        432,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)a4,
        LastError);
      goto LABEL_50;
    }
  }
LABEL_51:
  if ( LastError && v11 )
  {
    if ( v17 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)v17 + 108) & 4) != 0
      && *((_BYTE *)v17 + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)v17 + 12),
        433,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)szDatabaseDest,
        LastError);
    }
    if ( !DeleteFileW(szDatabaseDest) )
    {
      v19 = GetLastError();
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          434,
          (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
          (_DWORD)szDatabaseDest,
          v19);
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18003e098  push    rbx
0x18003e09a  push    rbp
0x18003e09b  push    rsi
0x18003e09c  push    r12
0x18003e09e  push    r13
0x18003e0a0  push    r14
0x18003e0a2  push    r15
0x18003e0a4  sub     rsp, 30h
0x18003e0a8  mov     rsi, r9
0x18003e0ab  mov     rbp, r8
0x18003e0ae  mov     r12, rdx
0x18003e0b1  xor     r13b, r13b
0x18003e0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0bb  lea     rbx, WPP_GLOBAL_Control
0x18003e0c2  cmp     rcx, rbx
0x18003e0c5  jz      short loc_18003E0E8
0x18003e0c7  test    byte ptr [rcx+6Ch], 4
0x18003e0cb  jz      short loc_18003E0E8
0x18003e0cd  cmp     byte ptr [rcx+69h], 4
0x18003e0d1  jb      short loc_18003E0E8
0x18003e0d3  mov     rcx, [rcx+60h]
0x18003e0d7  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e0de  mov     edx, 1A8h
0x18003e0e3  call    WPP_SF_
0x18003e0e8  mov     r14, [rsp+68h+arg_38]
0x18003e0f0  mov     [r14], r13b
0x18003e0f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0fa  cmp     rcx, rbx
0x18003e0fd  jz      short loc_18003E123
0x18003e0ff  test    byte ptr [rcx+6Ch], 4
0x18003e103  jz      short loc_18003E123
0x18003e105  cmp     byte ptr [rcx+69h], 4
0x18003e109  jb      short loc_18003E123
0x18003e10b  mov     rcx, [rcx+60h]
0x18003e10f  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e116  mov     edx, 1A9h
0x18003e11b  mov     r9, rsi
0x18003e11e  call    WPP_SF_S
0x18003e123  mov     rdx, rsi; szFilename
0x18003e126  mov     rcx, rbp; sesid
0x18003e129  call    cs:__imp_JetDetachDatabaseW
0x18003e12f  mov     r15, [rsp+68h+szDatabaseDest]
0x18003e137  mov     ebx, eax
0x18003e139  test    eax, eax
0x18003e13b  jz      short loc_18003E18F
0x18003e13d  mov     r10, cs:WPP_GLOBAL_Control
0x18003e144  lea     rax, WPP_GLOBAL_Control
0x18003e14b  cmp     r10, rax
0x18003e14e  jz      short loc_18003E181
0x18003e150  test    byte ptr [r10+6Ch], 4
0x18003e155  jz      short loc_18003E181
0x18003e157  cmp     byte ptr [r10+69h], 1
0x18003e15c  jb      short loc_18003E181
0x18003e15e  mov     edx, 1AAh
0x18003e163  mov     rcx, [r10+60h]
0x18003e167  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e16e  mov     r9, rsi
0x18003e171  mov     dword ptr [rsp+68h+pconvert], ebx
0x18003e175  call    WPP_SF_Sd
0x18003e17a  mov     r10, cs:WPP_GLOBAL_Control
0x18003e181  mov     ecx, ebx; int
0x18003e183  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003e188  mov     ebx, eax
0x18003e18a  jmp     loc_18003E3E3
0x18003e18f  mov     r8, [rsp+68h+arg_28]
0x18003e197  xor     r9d, r9d; grbit
0x18003e19a  shr     r8, 0Fh; cpgDatabaseSizeMax
0x18003e19e  mov     rdx, rsi; szFilename
0x18003e1a1  mov     rcx, rbp; sesid
0x18003e1a4  mov     byte ptr [r14], 1
0x18003e1a8  call    cs:__imp_JetAttachDatabase2W
0x18003e1ae  mov     ebx, eax
0x18003e1b0  test    eax, eax
0x18003e1b2  jz      short loc_18003E209
0x18003e1b4  cmp     eax, 3EFh
0x18003e1b9  jz      short loc_18003E209
0x18003e1bb  mov     r10, cs:WPP_GLOBAL_Control
0x18003e1c2  lea     rsi, WPP_GLOBAL_Control
0x18003e1c9  cmp     r10, rsi
0x18003e1cc  jz      short loc_18003E1FB
0x18003e1ce  test    byte ptr [r10+6Ch], 4
0x18003e1d3  jz      short loc_18003E1FB
0x18003e1d5  cmp     byte ptr [r10+69h], 1
0x18003e1da  jb      short loc_18003E1FB
0x18003e1dc  mov     rcx, [r10+60h]
0x18003e1e0  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e1e7  mov     edx, 1ABh
0x18003e1ec  mov     r9d, eax
0x18003e1ef  call    WPP_SF_d
0x18003e1f4  mov     r10, cs:WPP_GLOBAL_Control
0x18003e1fb  mov     ecx, ebx; int
0x18003e1fd  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18003e202  mov     ebx, eax
0x18003e204  jmp     loc_18003E3EA
0x18003e209  mov     [rsp+68h+grbit], 0; grbit
0x18003e211  lea     r9, ?OnBeginPruning@CRepubBackgroundPruneCatalogTask@@MEAAKXZ; pfnStatus
0x18003e218  mov     r8, r15; szDatabaseDest
0x18003e21b  mov     [rsp+68h+pconvert], 0; pconvert
0x18003e224  mov     rdx, rsi; szDatabaseSrc
0x18003e227  mov     rcx, rbp; sesid
0x18003e22a  call    cs:__imp_JetCompactW
0x18003e230  mov     ebx, eax
0x18003e232  mov     r13b, 1
0x18003e235  test    eax, eax
0x18003e237  jz      short loc_18003E26F
0x18003e239  mov     r10, cs:WPP_GLOBAL_Control
0x18003e240  lea     rax, WPP_GLOBAL_Control
0x18003e247  cmp     r10, rax
0x18003e24a  jz      loc_18003E181
0x18003e250  test    byte ptr [r10+6Ch], 4
0x18003e255  jz      loc_18003E181
0x18003e25b  cmp     [r10+69h], r13b
0x18003e25f  jb      loc_18003E181
0x18003e265  mov     edx, 1ACh
0x18003e26a  jmp     loc_18003E163
0x18003e26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e276  lea     rax, WPP_GLOBAL_Control
0x18003e27d  cmp     rcx, rax
0x18003e280  jz      short loc_18003E2A6
0x18003e282  test    byte ptr [rcx+6Ch], 4
0x18003e286  jz      short loc_18003E2A6
0x18003e288  cmp     byte ptr [rcx+69h], 4
0x18003e28c  jb      short loc_18003E2A6
0x18003e28e  mov     rcx, [rcx+60h]
0x18003e292  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e299  mov     edx, 1ADh
0x18003e29e  mov     r9, rsi
0x18003e2a1  call    WPP_SF_S
0x18003e2a6  mov     rdx, rsi; szFilename
0x18003e2a9  mov     rcx, rbp; sesid
0x18003e2ac  call    cs:__imp_JetDetachDatabaseW
0x18003e2b2  mov     ebx, eax
0x18003e2b4  test    eax, eax
0x18003e2b6  jz      short loc_18003E2EE
0x18003e2b8  mov     r10, cs:WPP_GLOBAL_Control
0x18003e2bf  lea     rax, WPP_GLOBAL_Control
0x18003e2c6  cmp     r10, rax
0x18003e2c9  jz      loc_18003E181
0x18003e2cf  test    byte ptr [r10+6Ch], 4
0x18003e2d4  jz      loc_18003E181
0x18003e2da  cmp     [r10+69h], r13b
0x18003e2de  jb      loc_18003E181
0x18003e2e4  mov     edx, 1AEh
0x18003e2e9  jmp     loc_18003E163
0x18003e2ee  xor     ebx, ebx
0x18003e2f0  mov     [r14], r13b
0x18003e2f3  cmp     [rsp+68h+arg_30], bl
0x18003e2fa  jz      short loc_18003E36B
0x18003e2fc  lea     r8d, [rbx+1]; dwFlags
0x18003e300  mov     rdx, rsi; lpNewFileName
0x18003e303  mov     rcx, r15; lpExistingFileName
0x18003e306  call    cs:__imp_MoveFileExW
0x18003e30c  test    eax, eax
0x18003e30e  jnz     loc_18003E469
0x18003e314  call    cs:__imp_GetLastError
0x18003e31a  mov     ebx, eax
0x18003e31c  mov     r10, cs:WPP_GLOBAL_Control
0x18003e323  lea     rax, WPP_GLOBAL_Control
0x18003e32a  cmp     r10, rax
0x18003e32d  jz      loc_18003E3E3
0x18003e333  test    byte ptr [r10+6Ch], 4
0x18003e338  jz      loc_18003E3E3
0x18003e33e  cmp     [r10+69h], r13b
0x18003e342  jb      loc_18003E3E3
0x18003e348  mov     rcx, [r10+60h]
0x18003e34c  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e353  mov     edx, 1AFh
0x18003e358  mov     [rsp+68h+grbit], ebx
0x18003e35c  mov     r9, r15
0x18003e35f  mov     [rsp+68h+pconvert], rsi
0x18003e364  call    WPP_SF_SSD
0x18003e369  jmp     short loc_18003E3DC
0x18003e36b  mov     rdx, r12; hTransaction
0x18003e36e  mov     rcx, rsi; lpFileName
0x18003e371  call    cs:__imp_DeleteFileTransactedW
0x18003e377  test    eax, eax
0x18003e379  jnz     short loc_18003E3C1
0x18003e37b  call    cs:__imp_GetLastError
0x18003e381  mov     ebx, eax
0x18003e383  mov     r10, cs:WPP_GLOBAL_Control
0x18003e38a  lea     rax, WPP_GLOBAL_Control
0x18003e391  cmp     r10, rax
0x18003e394  jz      short loc_18003E3E3
0x18003e396  test    byte ptr [r10+6Ch], 4
0x18003e39b  jz      short loc_18003E3E3
0x18003e39d  cmp     [r10+69h], r13b
0x18003e3a1  jb      short loc_18003E3E3
0x18003e3a3  mov     rcx, [r10+60h]
0x18003e3a7  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e3ae  mov     edx, 1B0h
0x18003e3b3  mov     dword ptr [rsp+68h+pconvert], ebx
0x18003e3b7  mov     r9, rsi
0x18003e3ba  call    WPP_SF_Sd
0x18003e3bf  jmp     short loc_18003E3DC
0x18003e3c1  mov     r8, r15; unsigned __int16 *
0x18003e3c4  mov     edx, 104h; unsigned __int64
0x18003e3c9  mov     rcx, rsi; unsigned __int16 *
0x18003e3cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e3d1  test    eax, eax
0x18003e3d3  jns     loc_18003E469
0x18003e3d9  movzx   ebx, ax
0x18003e3dc  mov     r10, cs:WPP_GLOBAL_Control
0x18003e3e3  lea     rsi, WPP_GLOBAL_Control
0x18003e3ea  test    ebx, ebx
0x18003e3ec  jz      short loc_18003E469
0x18003e3ee  test    r13b, r13b
0x18003e3f1  jz      short loc_18003E469
0x18003e3f3  cmp     r10, rsi
0x18003e3f6  jz      short loc_18003E422
0x18003e3f8  test    byte ptr [r10+6Ch], 4
0x18003e3fd  jz      short loc_18003E422
0x18003e3ff  cmp     byte ptr [r10+69h], 1
0x18003e404  jb      short loc_18003E422
0x18003e406  mov     rcx, [r10+60h]
0x18003e40a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e411  mov     edx, 1B1h
0x18003e416  mov     dword ptr [rsp+68h+pconvert], ebx
0x18003e41a  mov     r9, r15
0x18003e41d  call    WPP_SF_Sd
0x18003e422  mov     rcx, r15; lpFileName
0x18003e425  call    cs:__imp_DeleteFileW
0x18003e42b  test    eax, eax
0x18003e42d  jnz     short loc_18003E469
0x18003e42f  call    cs:__imp_GetLastError
0x18003e435  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e43c  cmp     rcx, rsi
0x18003e43f  jz      short loc_18003E469
0x18003e441  test    byte ptr [rcx+6Ch], 4
0x18003e445  jz      short loc_18003E469
0x18003e447  cmp     byte ptr [rcx+69h], 1
0x18003e44b  jb      short loc_18003E469
0x18003e44d  mov     rcx, [rcx+60h]
0x18003e451  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003e458  mov     edx, 1B2h
0x18003e45d  mov     dword ptr [rsp+68h+pconvert], eax
0x18003e461  mov     r9, r15
0x18003e464  call    WPP_SF_Sd
0x18003e469  mov     eax, ebx
0x18003e46b  add     rsp, 30h
0x18003e46f  pop     r15
0x18003e471  pop     r14
0x18003e473  pop     r13
0x18003e475  pop     r12
0x18003e477  pop     rsi
0x18003e478  pop     rbp
0x18003e479  pop     rbx
0x18003e47a  retn
```
