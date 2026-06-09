# CRepubCacheBackingStore::WriteDatabaseGuid(_BlockDatabaseDescriptor &)

- ea: `0x1800508f0`
- end: `0x180050cce`
- name: `?WriteDatabaseGuid@CRepubCacheBackingStore@@AEAAKAEAU_BlockDatabaseDescriptor@@@Z`
- size: `990`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, struct _BlockDatabaseDescriptor *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180046eec`

## callees

- `0x1800024f0`
- `0x1800024fc`
- `0x180004374`
- `0x180008290`
- `0x1800094d4`
- `0x18000cf48`
- `0x180011798`
- `0x1800508f0`
- `0x180051d5c`
- `0x1800520c8`
- `0x180052220`
- `0x180060fa0`
- `0x180114ae0`
- `0x1801448c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180050aad`
- `msvcrt!memcpy_s` at `0x180050aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050b93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050c5b`
- `KERNEL32!CloseHandle` at `0x180050c51`
- `KERNEL32!CloseHandle` at `0x180050c51`
- `KERNEL32!WriteFile` at `0x180050b89`
- `KERNEL32!WriteFile` at `0x180050b89`
- `KERNEL32!CreateFileW` at `0x180050b25`
- `KERNEL32!CreateFileW` at `0x180050b25`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheBackingStore::WriteDatabaseGuid(
        CRepubCacheBackingStore *this,
        struct _BlockDatabaseDescriptor *a2)
{
  _WORD *v3; // r15
  unsigned __int16 *v4; // rbx
  unsigned int LastError; // eax
  unsigned int v6; // edi
  CHostedCacheMsgEncoding *v7; // rcx
  int v8; // edx
  WCHAR *v9; // r9
  int v10; // eax
  CHostedCacheMsgEncoding *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int appended; // eax
  void *v15; // rax
  char *v16; // rsi
  errno_t v17; // eax
  int v18; // edx
  int v19; // r8d
  HANDLE FileW; // rax
  void *v21; // r14
  int v22; // r8d
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-B8h] BYREF
  void *Destination; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v30; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 154, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  v3 = 0;
  Destination = 0;
  NumberOfBytesWritten = 0;
  v4 = 0;
  v30 = 0;
  v28 = 0;
  LastError = ConstructRepubBlockFolderRoot((const unsigned __int16 *)a2 + 10, &v28, &v31);
  v6 = LastError;
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 155;
      LODWORD(v9) = (_DWORD)a2 + 20;
LABEL_10:
      WPP_SF_Sd(
        *((_QWORD *)v7 + 12),
        v8,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)v9,
        LastError);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  operator delete(0);
  v4 = v28;
  v30 = v28;
  v10 = StringCchCopyW(FileName, 0x104u, v28);
  if ( v10 < 0 )
  {
    v6 = (unsigned __int16)v10;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_54;
    }
    v12 = 156;
    v13 = (unsigned __int16)v10;
    goto LABEL_16;
  }
  appended = AppendFilePath(FileName, L"GUID.dat");
  v6 = appended;
  if ( appended )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_54;
    }
    v12 = 157;
    v13 = appended;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v11 + 12), v12, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v13);
    goto LABEL_54;
  }
  v15 = operator new[](0x12u);
  std::auto_ptr<unsigned short>::reset(&Destination, v15);
  v3 = Destination;
  v16 = (char *)a2 + 4;
  v17 = memcpy_s(Destination, 0x10u, (char *)a2 + 4, 0x10u);
  if ( v17 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF__guid_Sd(*((_QWORD *)WPP_GLOBAL_Control + 12), v18, v19, (_DWORD)a2 + 4, (__int64)FileName, v17);
    }
    v6 = 774;
  }
  else
  {
    v3[8] = *(_WORD *)a2;
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v21 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v6 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v8 = 159;
        v9 = FileName;
        goto LABEL_10;
      }
    }
    else
    {
      if ( WriteFile(FileW, v3, 0x12u, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten >= 0x12 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 162, v22, (unsigned int)FileName, (__int64)v16);
          }
        }
        else
        {
          v6 = 13;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_SDDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 161, v22, (unsigned int)FileName, NumberOfBytesWritten);
          }
        }
      }
      else
      {
        v23 = GetLastError();
        v6 = v23;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            160,
            (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
            (unsigned int)FileName,
            v23);
        }
      }
      if ( !CloseHandle(v21) )
      {
        v24 = GetLastError();
        v25 = v24;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 163, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v24);
        }
        if ( !v6 )
          v6 = v25;
      }
    }
  }
LABEL_54:
  operator delete(v4);
  operator delete(v3);
  return v6;
}

```

## disassembly

```asm
0x1800508f0  push    rbp
0x1800508f2  push    rbx
0x1800508f3  push    rsi
0x1800508f4  push    rdi
0x1800508f5  push    r12
0x1800508f7  push    r13
0x1800508f9  push    r14
0x1800508fb  push    r15
0x1800508fd  lea     rbp, [rsp-198h]
0x180050905  sub     rsp, 298h
0x18005090c  mov     rax, cs:__security_cookie
0x180050913  xor     rax, rsp
0x180050916  mov     [rbp+1D0h+var_50], rax
0x18005091d  mov     r14, rdx
0x180050920  lea     r13, WPP_GLOBAL_Control
0x180050927  mov     r12b, 4
0x18005092a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050931  cmp     rcx, r13
0x180050934  jz      short loc_180050957
0x180050936  test    [rcx+6Ch], r12b
0x18005093a  jz      short loc_180050957
0x18005093c  cmp     [rcx+69h], r12b
0x180050940  jb      short loc_180050957
0x180050942  mov     edx, 9Ah
0x180050947  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18005094e  mov     rcx, [rcx+60h]
0x180050952  call    WPP_SF_
0x180050957  xor     r15d, r15d
0x18005095a  mov     [rsp+2D0h+Destination], r15
0x18005095f  mov     [rsp+2D0h+NumberOfBytesWritten], r15d
0x180050964  xor     ebx, ebx
0x180050966  mov     [rsp+2D0h+var_278], rbx
0x18005096b  mov     [rsp+2D0h+var_288], rbx
0x180050970  lea     r8, [rsp+2D0h+var_270]; unsigned __int64 *
0x180050975  lea     rdx, [rsp+2D0h+var_288]; unsigned __int16 **
0x18005097a  lea     rcx, [r14+14h]; unsigned __int16 *
0x18005097e  call    ?ConstructRepubBlockFolderRoot@@YAKPEBGPEAPEAGPEA_K@Z; ConstructRepubBlockFolderRoot(ushort const *,ushort * *,unsigned __int64 *)
0x180050983  mov     edi, eax
0x180050985  test    eax, eax
0x180050987  jz      short loc_1800509CF
0x180050989  mov     rcx, cs:WPP_GLOBAL_Control
0x180050990  cmp     rcx, r13
0x180050993  jz      loc_180050C98
0x180050999  test    [rcx+6Ch], r12b
0x18005099d  jz      loc_180050C98
0x1800509a3  cmp     byte ptr [rcx+69h], 1
0x1800509a7  jb      loc_180050C98
0x1800509ad  mov     edx, 9Bh
0x1800509b2  lea     r9, [r14+14h]
0x1800509b6  mov     [rsp+2D0h+dwCreationDisposition], eax
0x1800509ba  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x1800509c1  mov     rcx, [rcx+60h]
0x1800509c5  call    WPP_SF_Sd
0x1800509ca  jmp     loc_180050C98
0x1800509cf  xor     ecx, ecx; Block
0x1800509d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800509d6  mov     rbx, [rsp+2D0h+var_288]
0x1800509db  mov     [rsp+2D0h+var_278], rbx
0x1800509e0  mov     r8, rbx; unsigned __int16 *
0x1800509e3  mov     edx, 104h; unsigned __int64
0x1800509e8  lea     rcx, [rsp+2D0h+FileName]; unsigned __int16 *
0x1800509ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800509f2  test    eax, eax
0x1800509f4  jns     short loc_180050A3A
0x1800509f6  movzx   edi, ax
0x1800509f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a00  cmp     rcx, r13
0x180050a03  jz      loc_180050C98
0x180050a09  test    [rcx+6Ch], r12b
0x180050a0d  jz      loc_180050C98
0x180050a13  cmp     byte ptr [rcx+69h], 1
0x180050a17  jb      loc_180050C98
0x180050a1d  mov     edx, 9Ch
0x180050a22  mov     r9d, edi
0x180050a25  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180050a2c  mov     rcx, [rcx+60h]
0x180050a30  call    WPP_SF_d
0x180050a35  jmp     loc_180050C98
0x180050a3a  lea     rdx, ?c_wszRepubBlockDatabaseGuidFile@@3QBGB; "GUID.dat"
0x180050a41  lea     rcx, [rsp+2D0h+FileName]; unsigned __int16 *
0x180050a46  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x180050a4b  mov     edi, eax
0x180050a4d  test    eax, eax
0x180050a4f  jz      short loc_180050A7F
0x180050a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a58  cmp     rcx, r13
0x180050a5b  jz      loc_180050C98
0x180050a61  test    [rcx+6Ch], r12b
0x180050a65  jz      loc_180050C98
0x180050a6b  cmp     byte ptr [rcx+69h], 1
0x180050a6f  jb      loc_180050C98
0x180050a75  mov     edx, 9Dh
0x180050a7a  mov     r9d, eax
0x180050a7d  jmp     short loc_180050A25
0x180050a7f  mov     ecx, 12h; unsigned __int64
0x180050a84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180050a89  mov     rdx, rax
0x180050a8c  lea     rcx, [rsp+2D0h+Destination]
0x180050a91  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x180050a96  mov     r15, [rsp+2D0h+Destination]
0x180050a9b  lea     rsi, [r14+4]
0x180050a9f  mov     edx, 10h; DestinationSize
0x180050aa4  mov     r9d, edx; SourceSize
0x180050aa7  mov     r8, rsi; Source
0x180050aaa  mov     rcx, r15; Destination
0x180050aad  call    cs:__imp_memcpy_s
0x180050ab3  test    eax, eax
0x180050ab5  jz      short loc_180050AF3
0x180050ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180050abe  cmp     rcx, r13
0x180050ac1  jz      short loc_180050AE9
0x180050ac3  test    [rcx+6Ch], r12b
0x180050ac7  jz      short loc_180050AE9
0x180050ac9  cmp     byte ptr [rcx+69h], 1
0x180050acd  jb      short loc_180050AE9
0x180050acf  mov     [rsp+2D0h+dwFlagsAndAttributes], eax
0x180050ad3  lea     rax, [rsp+2D0h+FileName]
0x180050ad8  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax
0x180050add  mov     r9, rsi
0x180050ae0  mov     rcx, [rcx+60h]
0x180050ae4  call    WPP_SF__guid_Sd
0x180050ae9  mov     edi, 306h
0x180050aee  jmp     loc_180050C98
0x180050af3  movzx   eax, word ptr [r14]
0x180050af7  mov     [r15+10h], ax
0x180050afc  mov     [rsp+2D0h+hTemplateFile], 0; hTemplateFile
0x180050b05  mov     [rsp+2D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180050b0d  mov     [rsp+2D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180050b15  xor     r9d, r9d; lpSecurityAttributes
0x180050b18  xor     r8d, r8d; dwShareMode
0x180050b1b  mov     edx, 40000000h; dwDesiredAccess
0x180050b20  lea     rcx, [rsp+2D0h+FileName]; lpFileName
0x180050b25  call    cs:__imp_CreateFileW
0x180050b2b  mov     r14, rax
0x180050b2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180050b32  jnz     short loc_180050B6F
0x180050b34  call    cs:__imp_GetLastError
0x180050b3a  mov     edi, eax
0x180050b3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050b43  cmp     rcx, r13
0x180050b46  jz      loc_180050C98
0x180050b4c  test    [rcx+6Ch], r12b
0x180050b50  jz      loc_180050C98
0x180050b56  cmp     byte ptr [rcx+69h], 1
0x180050b5a  jb      loc_180050C98
0x180050b60  mov     edx, 9Fh
0x180050b65  lea     r9, [rsp+2D0h+FileName]
0x180050b6a  jmp     loc_1800509B6
0x180050b6f  mov     qword ptr [rsp+2D0h+dwCreationDisposition], 0; lpOverlapped
0x180050b78  lea     r9, [rsp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180050b7d  mov     r8d, 12h; nNumberOfBytesToWrite
0x180050b83  mov     rdx, r15; lpBuffer
0x180050b86  mov     rcx, r14; hFile
0x180050b89  call    cs:__imp_WriteFile
0x180050b8f  test    eax, eax
0x180050b91  jnz     short loc_180050BDF
0x180050b93  call    cs:__imp_GetLastError
0x180050b99  mov     edi, eax
0x180050b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050ba2  cmp     rcx, r13
0x180050ba5  jz      loc_180050C4E
0x180050bab  test    [rcx+6Ch], r12b
0x180050baf  jz      loc_180050C4E
0x180050bb5  cmp     byte ptr [rcx+69h], 1
0x180050bb9  jb      loc_180050C4E
0x180050bbf  mov     edx, 0A0h
0x180050bc4  mov     [rsp+2D0h+dwCreationDisposition], eax
0x180050bc8  lea     r9, [rsp+2D0h+FileName]
0x180050bcd  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180050bd4  mov     rcx, [rcx+60h]
0x180050bd8  call    WPP_SF_Sd
0x180050bdd  jmp     short loc_180050C4E
0x180050bdf  mov     eax, [rsp+2D0h+NumberOfBytesWritten]
0x180050be3  cmp     eax, 12h
0x180050be6  jnb     short loc_180050C1E
0x180050be8  mov     edi, 0Dh
0x180050bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180050bf4  cmp     rcx, r13
0x180050bf7  jz      short loc_180050C4E
0x180050bf9  test    [rcx+6Ch], r12b
0x180050bfd  jz      short loc_180050C4E
0x180050bff  cmp     byte ptr [rcx+69h], 1
0x180050c03  jb      short loc_180050C4E
0x180050c05  mov     edx, 0A1h
0x180050c0a  mov     [rsp+2D0h+dwCreationDisposition], eax
0x180050c0e  lea     r9, [rsp+2D0h+FileName]
0x180050c13  mov     rcx, [rcx+60h]
0x180050c17  call    WPP_SF_SDDD
0x180050c1c  jmp     short loc_180050C4E
0x180050c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c25  cmp     rcx, r13
0x180050c28  jz      short loc_180050C4E
0x180050c2a  test    [rcx+6Ch], r12b
0x180050c2e  jz      short loc_180050C4E
0x180050c30  cmp     [rcx+69h], r12b
0x180050c34  jb      short loc_180050C4E
0x180050c36  mov     edx, 0A2h
0x180050c3b  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rsi
0x180050c40  lea     r9, [rsp+2D0h+FileName]
0x180050c45  mov     rcx, [rcx+60h]
0x180050c49  call    WPP_SF_S_guid_
0x180050c4e  mov     rcx, r14; hObject
0x180050c51  call    cs:__imp_CloseHandle
0x180050c57  test    eax, eax
0x180050c59  jnz     short loc_180050C98
0x180050c5b  call    cs:__imp_GetLastError
0x180050c61  mov     esi, eax
0x180050c63  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c6a  cmp     rcx, r13
0x180050c6d  jz      short loc_180050C93
0x180050c6f  test    [rcx+6Ch], r12b
0x180050c73  jz      short loc_180050C93
0x180050c75  cmp     byte ptr [rcx+69h], 1
0x180050c79  jb      short loc_180050C93
0x180050c7b  mov     edx, 0A3h
0x180050c80  mov     r9d, eax
0x180050c83  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x180050c8a  mov     rcx, [rcx+60h]
0x180050c8e  call    WPP_SF_d
0x180050c93  test    edi, edi
0x180050c95  cmovz   edi, esi
0x180050c98  mov     rcx, rbx; Block
0x180050c9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050ca0  nop
0x180050ca1  mov     rcx, r15; Block
0x180050ca4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180050ca9  mov     eax, edi
0x180050cab  mov     rcx, [rbp+1D0h+var_50]
0x180050cb2  xor     rcx, rsp; StackCookie
0x180050cb5  call    __security_check_cookie
0x180050cba  add     rsp, 298h
0x180050cc1  pop     r15
0x180050cc3  pop     r14
0x180050cc5  pop     r13
0x180050cc7  pop     r12
0x180050cc9  pop     rdi
0x180050cca  pop     rsi
0x180050ccb  pop     rbx
0x180050ccc  pop     rbp
0x180050ccd  retn
```
