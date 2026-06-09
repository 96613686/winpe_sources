# CRepubCacheBackingStore::MoveDatabase(void *,unsigned __int64,ushort *,ushort *,bool *)

- ea: `0x180049ff0`
- end: `0x18004a139`
- name: `?MoveDatabase@CRepubCacheBackingStore@@AEAAKPEAX_KPEAG2PEA_N@Z`
- size: `329`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, HANDLE hTransaction, JET_SESID sesid, unsigned __int16 *, LPCWSTR lpNewFileName, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180042374`

## callees

- `0x1800094d4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180018340`
- `0x180049ff0`
- `0x18013ab7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0ce`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x18004a0c4`
- `api-ms-win-core-kernel32-legacy-l1-1-3!MoveFileTransactedW` at `0x18004a0c4`
- `ESENT!JetDetachDatabaseW` at `0x18004a04e`
- `ESENT!JetDetachDatabaseW` at `0x18004a04e`

## pseudocode

```c
__int64 __fastcall CRepubCacheBackingStore::MoveDatabase(
        CRepubCacheBackingStore *this,
        HANDLE hTransaction,
        JET_SESID sesid,
        unsigned __int16 *a4,
        LPCWSTR lpNewFileName,
        bool *a6)
{
  JET_ERR v10; // eax
  int v11; // ebx
  DWORD v12; // ebx
  DWORD LastError; // eax
  int v14; // eax

  *a6 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 437, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, a4);
  }
  v10 = JetDetachDatabaseW(sesid, a4);
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        438,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)a4,
        v10);
    }
    return TranslateJetError(v11);
  }
  else
  {
    *a6 = 1;
    if ( MoveFileTransactedW(a4, lpNewFileName, RepubCacheMoveDatabaseCallback, this, 2u, hTransaction) )
    {
      v12 = 0;
      v14 = StringCchCopyW(a4, 0x104u, lpNewFileName);
      if ( v14 < 0 )
        return (unsigned __int16)v14;
    }
    else
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          439,
          (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
          (_DWORD)lpNewFileName,
          (__int64)a4,
          LastError);
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180049ff0  push    rbx
0x180049ff2  push    rbp
0x180049ff3  push    rsi
0x180049ff4  push    rdi
0x180049ff5  push    r12
0x180049ff7  push    r14
0x180049ff9  sub     rsp, 38h
0x180049ffd  mov     rsi, [rsp+68h+arg_28]
0x18004a005  mov     rdi, r9
0x18004a008  mov     rbx, r8
0x18004a00b  mov     rbp, rdx
0x18004a00e  mov     r14, rcx
0x18004a011  mov     byte ptr [rsi], 0
0x18004a014  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a01b  lea     r12, WPP_GLOBAL_Control
0x18004a022  cmp     rcx, r12
0x18004a025  jz      short loc_18004A048
0x18004a027  test    byte ptr [rcx+6Ch], 4
0x18004a02b  jz      short loc_18004A048
0x18004a02d  cmp     byte ptr [rcx+69h], 4
0x18004a031  jb      short loc_18004A048
0x18004a033  mov     rcx, [rcx+60h]
0x18004a037  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a03e  mov     edx, 1B5h
0x18004a043  call    WPP_SF_S
0x18004a048  mov     rdx, rdi; szFilename
0x18004a04b  mov     rcx, rbx; sesid
0x18004a04e  call    cs:__imp_JetDetachDatabaseW
0x18004a054  mov     ebx, eax
0x18004a056  test    eax, eax
0x18004a058  jz      short loc_18004A09C
0x18004a05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a061  cmp     rcx, r12
0x18004a064  jz      short loc_18004A08E
0x18004a066  test    byte ptr [rcx+6Ch], 4
0x18004a06a  jz      short loc_18004A08E
0x18004a06c  cmp     byte ptr [rcx+69h], 1
0x18004a070  jb      short loc_18004A08E
0x18004a072  mov     rcx, [rcx+60h]
0x18004a076  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a07d  mov     edx, 1B6h
0x18004a082  mov     [rsp+68h+dwFlags], eax
0x18004a086  mov     r9, rdi
0x18004a089  call    WPP_SF_Sd
0x18004a08e  mov     ecx, ebx; int
0x18004a090  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18004a095  mov     ebx, eax
0x18004a097  jmp     loc_18004A12A
0x18004a09c  mov     byte ptr [rsi], 1
0x18004a09f  lea     r8, ?RepubCacheMoveDatabaseCallback@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x18004a0a6  mov     rsi, [rsp+68h+lpNewFileName]
0x18004a0ae  mov     r9, r14; lpData
0x18004a0b1  mov     rdx, rsi; lpNewFileName
0x18004a0b4  mov     [rsp+68h+hTransaction], rbp; hTransaction
0x18004a0b9  mov     rcx, rdi; lpExistingFileName
0x18004a0bc  mov     [rsp+68h+dwFlags], 2; dwFlags
0x18004a0c4  call    cs:__imp_MoveFileTransactedW
0x18004a0ca  test    eax, eax
0x18004a0cc  jnz     short loc_18004A111
0x18004a0ce  call    cs:__imp_GetLastError
0x18004a0d4  mov     ebx, eax
0x18004a0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0dd  cmp     rcx, r12
0x18004a0e0  jz      short loc_18004A12A
0x18004a0e2  test    byte ptr [rcx+6Ch], 4
0x18004a0e6  jz      short loc_18004A12A
0x18004a0e8  cmp     byte ptr [rcx+69h], 1
0x18004a0ec  jb      short loc_18004A12A
0x18004a0ee  mov     rcx, [rcx+60h]
0x18004a0f2  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004a0f9  mov     dword ptr [rsp+68h+hTransaction], eax
0x18004a0fd  mov     edx, 1B7h
0x18004a102  mov     r9, rsi
0x18004a105  mov     qword ptr [rsp+68h+dwFlags], rdi
0x18004a10a  call    WPP_SF_SSD
0x18004a10f  jmp     short loc_18004A12A
0x18004a111  mov     r8, rsi; unsigned __int16 *
0x18004a114  mov     edx, 104h; unsigned __int64
0x18004a119  mov     rcx, rdi; unsigned __int16 *
0x18004a11c  xor     ebx, ebx
0x18004a11e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004a123  test    eax, eax
0x18004a125  jns     short loc_18004A12A
0x18004a127  movzx   ebx, ax
0x18004a12a  mov     eax, ebx
0x18004a12c  add     rsp, 38h
0x18004a130  pop     r14
0x18004a132  pop     r12
0x18004a134  pop     rdi
0x18004a135  pop     rsi
0x18004a136  pop     rbp
0x18004a137  pop     rbx
0x18004a138  retn
```
