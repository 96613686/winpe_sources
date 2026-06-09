# CPubCacheBackingStore::MovePublicationStore(void *,bool,bool,ushort *,bool *)

- ea: `0x18005ab08`
- end: `0x18005ae7c`
- name: `?MovePublicationStore@CPubCacheBackingStore@@AEAAKPEAX_N1PEAGPEA_N@Z`
- size: `884`
- prototype: `__int64 __fastcall(CPubCacheBackingStore *this, HANDLE hTransaction, char, char, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180054250`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18000cf48`
- `0x18000cfc0`
- `0x180015c28`
- `0x180018170`
- `0x180018340`
- `0x1800576ac`
- `0x18005a434`
- `0x18005a7b8`
- `0x18005ab08`
- `0x18013ab7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acf6`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x18005acec`
- `api-ms-win-core-kernel32-legacy-l1-1-3!DeleteFileTransactedW` at `0x18005acec`
- `ESENT!JetTerm2` at `0x18005ac2c`
- `ESENT!JetTerm2` at `0x18005ac2c`

## string_xrefs

- `0x18005adc5`: `TempHashStore`
- `0x18005adff`: `TempHashStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPubCacheBackingStore::MovePublicationStore(
        CPubCacheBackingStore *this,
        HANDLE hTransaction,
        char a3,
        char a4,
        unsigned __int16 *a5,
        bool *a6)
{
  unsigned int v10; // ebx
  const wchar_t *v11; // r9
  JET_ERR v12; // eax
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v14; // rcx
  int v15; // edx
  const unsigned __int16 *v16; // r9
  unsigned __int16 *v17; // r9
  _BYTE v19[72]; // [rsp+30h] [rbp-48h] BYREF

  v10 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v11 = L"Y";
    if ( !a3 )
      v11 = (const wchar_t *)L"N";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 243, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v11);
  }
  *a6 = 0;
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(v19, (char *)this + 16);
  if ( *((_QWORD *)this + 33) != -1 )
  {
    v10 = CPubCacheBackingStore::DetachAllDatabases(this);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 244, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v10);
      }
LABEL_13:
      LockSentry<ReadersWriterLock,0>::Unlock(v19);
      return v10;
    }
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 245, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
    }
    v12 = JetTerm2(*((_QWORD *)this + 33), 2u);
    if ( v12 )
    {
      v10 = TranslateJetError(v12);
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 246, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
      }
      goto LABEL_13;
    }
    *((_QWORD *)this + 33) = -1;
    *((_DWORD *)this + 49) = 4;
    *a6 = 1;
  }
  LockSentry<ReadersWriterLock,0>::Unlock(v19);
  if ( !a4 )
    goto LABEL_35;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 247, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  if ( DeleteFileTransactedW((LPCWSTR)this + 1944, hTransaction) )
  {
LABEL_35:
    if ( a3 )
      return v10;
    LastError = CPubCacheBackingStore::MoveHashStore(
                  this,
                  (unsigned __int16 *)this + 1420,
                  a5,
                  L"PrimaryHashStore",
                  hTransaction,
                  1);
    v10 = LastError;
    if ( LastError )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v15 = 249;
        v16 = L"PrimaryHashStore";
        goto LABEL_34;
      }
    }
    else
    {
      LastError = CPubCacheBackingStore::MoveHashStore(
                    this,
                    (unsigned __int16 *)this + 1680,
                    a5,
                    L"TempHashStore",
                    hTransaction,
                    0);
      v10 = LastError;
      if ( LastError )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v15 = 250;
          v16 = L"TempHashStore";
          goto LABEL_34;
        }
      }
      else
      {
        v10 = CPubCacheBackingStore::MoveCacheFolder(this, (unsigned __int16 *)this + 1160, a5, v17, hTransaction);
        if ( v10
          && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            251,
            (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
            (_DWORD)this + 2320,
            (__int64)a5,
            v10);
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v15 = 248;
      LODWORD(v16) = (_DWORD)this + 3888;
LABEL_34:
      WPP_SF_Sd(
        *((_QWORD *)v14 + 12),
        v15,
        (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
        (_DWORD)v16,
        LastError);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18005ab08  push    rbx
0x18005ab0a  push    rbp
0x18005ab0b  push    rsi
0x18005ab0c  push    rdi
0x18005ab0d  push    r12
0x18005ab0f  push    r14
0x18005ab11  push    r15
0x18005ab13  sub     rsp, 40h
0x18005ab17  mov     bpl, r9b
0x18005ab1a  mov     r15b, r8b
0x18005ab1d  mov     r14, rdx
0x18005ab20  mov     rdi, rcx
0x18005ab23  xor     ebx, ebx
0x18005ab25  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ab2c  lea     rax, WPP_GLOBAL_Control
0x18005ab33  lea     r12d, [rbx+4]
0x18005ab37  cmp     rcx, rax
0x18005ab3a  jz      short loc_18005AB72
0x18005ab3c  test    [rcx+6Ch], r12b
0x18005ab40  jz      short loc_18005AB72
0x18005ab42  cmp     [rcx+69h], r12b
0x18005ab46  jb      short loc_18005AB72
0x18005ab48  mov     rcx, [rcx+60h]
0x18005ab4c  lea     rax, aN; "N"
0x18005ab53  test    r8b, r8b
0x18005ab56  lea     r9, aY; "Y"
0x18005ab5d  mov     edx, 0F3h
0x18005ab62  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005ab69  cmovz   r9, rax
0x18005ab6d  call    WPP_SF_S
0x18005ab72  mov     rsi, [rsp+78h+arg_28]
0x18005ab7a  lea     rdx, [rdi+10h]
0x18005ab7e  lea     rcx, [rsp+78h+var_48]
0x18005ab83  mov     [rsi], bl
0x18005ab85  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18005ab8a  cmp     qword ptr [rdi+108h], 0FFFFFFFFFFFFFFFFh
0x18005ab92  jz      loc_18005AC98
0x18005ab98  mov     rcx, rdi; this
0x18005ab9b  call    ?DetachAllDatabases@CPubCacheBackingStore@@AEAAKXZ; CPubCacheBackingStore::DetachAllDatabases(void)
0x18005aba0  mov     ebx, eax
0x18005aba2  test    eax, eax
0x18005aba4  jz      short loc_18005ABEC
0x18005aba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005abad  lea     rax, WPP_GLOBAL_Control
0x18005abb4  cmp     rcx, rax
0x18005abb7  jz      short loc_18005ABDD
0x18005abb9  test    [rcx+6Ch], r12b
0x18005abbd  jz      short loc_18005ABDD
0x18005abbf  cmp     byte ptr [rcx+69h], 1
0x18005abc3  jb      short loc_18005ABDD
0x18005abc5  mov     rcx, [rcx+60h]
0x18005abc9  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005abd0  mov     edx, 0F4h
0x18005abd5  mov     r9d, ebx
0x18005abd8  call    WPP_SF_d
0x18005abdd  lea     rcx, [rsp+78h+var_48]
0x18005abe2  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18005abe7  jmp     loc_18005AE6B
0x18005abec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005abf3  lea     rax, WPP_GLOBAL_Control
0x18005abfa  cmp     rcx, rax
0x18005abfd  jz      short loc_18005AC20
0x18005abff  test    [rcx+6Ch], r12b
0x18005ac03  jz      short loc_18005AC20
0x18005ac05  cmp     [rcx+69h], r12b
0x18005ac09  jb      short loc_18005AC20
0x18005ac0b  mov     rcx, [rcx+60h]
0x18005ac0f  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005ac16  mov     edx, 0F5h
0x18005ac1b  call    WPP_SF_
0x18005ac20  mov     rcx, [rdi+108h]; instance
0x18005ac27  mov     edx, 2; grbit
0x18005ac2c  call    cs:__imp_JetTerm2
0x18005ac32  mov     r9d, eax
0x18005ac35  test    eax, eax
0x18005ac37  jz      short loc_18005AC83
0x18005ac39  mov     ecx, eax; int
0x18005ac3b  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x18005ac40  mov     ebx, eax
0x18005ac42  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ac49  lea     rax, WPP_GLOBAL_Control
0x18005ac50  cmp     rcx, rax
0x18005ac53  jz      short loc_18005ABDD
0x18005ac55  test    [rcx+6Ch], r12b
0x18005ac59  jz      short loc_18005ABDD
0x18005ac5b  cmp     byte ptr [rcx+69h], 1
0x18005ac5f  jb      loc_18005ABDD
0x18005ac65  mov     rcx, [rcx+60h]
0x18005ac69  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005ac70  mov     edx, 0F6h
0x18005ac75  mov     dword ptr [rsp+78h+hTransaction], ebx
0x18005ac79  call    WPP_SF_Dd
0x18005ac7e  jmp     loc_18005ABDD
0x18005ac83  mov     qword ptr [rdi+108h], 0FFFFFFFFFFFFFFFFh
0x18005ac8e  mov     [rdi+0C4h], r12d
0x18005ac95  mov     byte ptr [rsi], 1
0x18005ac98  lea     rcx, [rsp+78h+var_48]
0x18005ac9d  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18005aca2  test    bpl, bpl
0x18005aca5  jz      loc_18005AD43
0x18005acab  mov     rcx, cs:WPP_GLOBAL_Control
0x18005acb2  lea     rbp, WPP_GLOBAL_Control
0x18005acb9  cmp     rcx, rbp
0x18005acbc  jz      short loc_18005ACDF
0x18005acbe  test    [rcx+6Ch], r12b
0x18005acc2  jz      short loc_18005ACDF
0x18005acc4  cmp     [rcx+69h], r12b
0x18005acc8  jb      short loc_18005ACDF
0x18005acca  mov     rcx, [rcx+60h]
0x18005acce  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005acd5  mov     edx, 0F7h
0x18005acda  call    WPP_SF_
0x18005acdf  lea     rsi, [rdi+0F30h]
0x18005ace6  mov     rdx, r14; hTransaction
0x18005ace9  mov     rcx, rsi; lpFileName
0x18005acec  call    cs:__imp_DeleteFileTransactedW
0x18005acf2  test    eax, eax
0x18005acf4  jnz     short loc_18005AD4A
0x18005acf6  call    cs:__imp_GetLastError
0x18005acfc  mov     ebx, eax
0x18005acfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad05  cmp     rcx, rbp
0x18005ad08  jz      loc_18005AE6B
0x18005ad0e  test    [rcx+6Ch], r12b
0x18005ad12  jz      loc_18005AE6B
0x18005ad18  cmp     byte ptr [rcx+69h], 1
0x18005ad1c  jb      loc_18005AE6B
0x18005ad22  mov     edx, 0F8h
0x18005ad27  mov     r9, rsi
0x18005ad2a  mov     rcx, [rcx+60h]
0x18005ad2e  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005ad35  mov     dword ptr [rsp+78h+hTransaction], eax
0x18005ad39  call    WPP_SF_Sd
0x18005ad3e  jmp     loc_18005AE6B
0x18005ad43  lea     rbp, WPP_GLOBAL_Control
0x18005ad4a  test    r15b, r15b
0x18005ad4d  jnz     loc_18005AE6B
0x18005ad53  mov     rsi, [rsp+78h+arg_20]
0x18005ad5b  lea     rdx, [rdi+0B18h]; unsigned __int16 *
0x18005ad62  mov     r8, rsi; unsigned __int16 *
0x18005ad65  mov     [rsp+78h+var_50], 1; bool
0x18005ad6a  lea     r9, ?c_wszPubPrimaryHashStoreName@@3QBGB; "PrimaryHashStore"
0x18005ad71  mov     [rsp+78h+hTransaction], r14; hTransaction
0x18005ad76  mov     rcx, rdi; this
0x18005ad79  call    ?MoveHashStore@CPubCacheBackingStore@@AEAAKPEAG0PEBGPEAX_N@Z; CPubCacheBackingStore::MoveHashStore(ushort *,ushort *,ushort const *,void *,bool)
0x18005ad7e  mov     ebx, eax
0x18005ad80  test    eax, eax
0x18005ad82  jz      short loc_18005ADB9
0x18005ad84  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad8b  cmp     rcx, rbp
0x18005ad8e  jz      loc_18005AE6B
0x18005ad94  test    [rcx+6Ch], r12b
0x18005ad98  jz      loc_18005AE6B
0x18005ad9e  cmp     byte ptr [rcx+69h], 1
0x18005ada2  jb      loc_18005AE6B
0x18005ada8  mov     edx, 0F9h
0x18005adad  lea     r9, ?c_wszPubPrimaryHashStoreName@@3QBGB; "PrimaryHashStore"
0x18005adb4  jmp     loc_18005AD2A
0x18005adb9  lea     rdx, [rdi+0D20h]; unsigned __int16 *
0x18005adc0  mov     [rsp+78h+var_50], 0; bool
0x18005adc5  lea     r9, ?c_wszPubTempHashStoreName@@3QBGB; "TempHashStore"
0x18005adcc  mov     [rsp+78h+hTransaction], r14; hTransaction
0x18005add1  mov     r8, rsi; unsigned __int16 *
0x18005add4  mov     rcx, rdi; this
0x18005add7  call    ?MoveHashStore@CPubCacheBackingStore@@AEAAKPEAG0PEBGPEAX_N@Z; CPubCacheBackingStore::MoveHashStore(ushort *,ushort *,ushort const *,void *,bool)
0x18005addc  mov     ebx, eax
0x18005adde  test    eax, eax
0x18005ade0  jz      short loc_18005AE0B
0x18005ade2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ade9  cmp     rcx, rbp
0x18005adec  jz      short loc_18005AE6B
0x18005adee  test    [rcx+6Ch], r12b
0x18005adf2  jz      short loc_18005AE6B
0x18005adf4  cmp     byte ptr [rcx+69h], 1
0x18005adf8  jb      short loc_18005AE6B
0x18005adfa  mov     edx, 0FAh
0x18005adff  lea     r9, ?c_wszPubTempHashStoreName@@3QBGB; "TempHashStore"
0x18005ae06  jmp     loc_18005AD2A
0x18005ae0b  lea     rbp, [rdi+910h]
0x18005ae12  mov     [rsp+78h+hTransaction], r14; void *
0x18005ae17  mov     rdx, rbp; unsigned __int16 *
0x18005ae1a  mov     r8, rsi; unsigned __int16 *
0x18005ae1d  mov     rcx, rdi; this
0x18005ae20  call    ?MoveCacheFolder@CPubCacheBackingStore@@AEAAKPEAG00PEAX@Z; CPubCacheBackingStore::MoveCacheFolder(ushort *,ushort *,ushort *,void *)
0x18005ae25  mov     ebx, eax
0x18005ae27  test    eax, eax
0x18005ae29  jz      short loc_18005AE6B
0x18005ae2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae32  lea     rax, WPP_GLOBAL_Control
0x18005ae39  cmp     rcx, rax
0x18005ae3c  jz      short loc_18005AE6B
0x18005ae3e  test    [rcx+6Ch], r12b
0x18005ae42  jz      short loc_18005AE6B
0x18005ae44  cmp     byte ptr [rcx+69h], 1
0x18005ae48  jb      short loc_18005AE6B
0x18005ae4a  mov     rcx, [rcx+60h]
0x18005ae4e  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005ae55  mov     edx, 0FBh
0x18005ae5a  mov     dword ptr [rsp+78h+var_50], ebx
0x18005ae5e  mov     r9, rbp
0x18005ae61  mov     [rsp+78h+hTransaction], rsi
0x18005ae66  call    WPP_SF_SSD
0x18005ae6b  mov     eax, ebx
0x18005ae6d  add     rsp, 40h
0x18005ae71  pop     r15
0x18005ae73  pop     r14
0x18005ae75  pop     r12
0x18005ae77  pop     rdi
0x18005ae78  pop     rsi
0x18005ae79  pop     rbp
0x18005ae7a  pop     rbx
0x18005ae7b  retn
```
