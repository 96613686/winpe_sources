# CRepubCacheBackingStore::ReadExistingDatabaseGuid(_BlockDatabaseDescriptor &,bool &)

- ea: `0x18004bcb0`
- end: `0x18004c13c`
- name: `?ReadExistingDatabaseGuid@CRepubCacheBackingStore@@AEAAKAEAU_BlockDatabaseDescriptor@@AEA_N@Z`
- size: `1164`
- prototype: `unsigned int __fastcall(CRepubCacheBackingStore *__hidden this, struct _BlockDatabaseDescriptor *, bool *)`
- caller_count: `1`
- callee_count: `13`
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
- `0x18004bcb0`
- `0x180051d5c`
- `0x1800520c8`
- `0x180060fa0`
- `0x180114ae0`
- `0x1801448c0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18004c023`
- `msvcrt!memcpy_s` at `0x18004c023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c0c2`
- `KERNEL32!CloseHandle` at `0x18004c0b8`
- `KERNEL32!CloseHandle` at `0x18004c0b8`
- `KERNEL32!ReadFile` at `0x18004bf5d`
- `KERNEL32!ReadFile` at `0x18004bf5d`
- `KERNEL32!CreateFileW` at `0x18004be8a`
- `KERNEL32!CreateFileW` at `0x18004be8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepubCacheBackingStore::ReadExistingDatabaseGuid(
        CRepubCacheBackingStore *this,
        struct _BlockDatabaseDescriptor *a2,
        bool *a3)
{
  _WORD *v5; // r13
  unsigned __int16 *v6; // rbx
  unsigned int LastError; // eax
  unsigned int v8; // edi
  CHostedCacheMsgEncoding *v9; // rcx
  int v10; // edx
  WCHAR *v11; // r9
  int v12; // eax
  CHostedCacheMsgEncoding *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int appended; // eax
  HANDLE FileW; // r12
  void *v18; // rax
  int v19; // r8d
  DWORD v20; // eax
  errno_t v21; // eax
  int v22; // r8d
  DWORD v23; // eax
  DWORD v24; // esi
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v27; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 143, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids);
  }
  v5 = 0;
  lpBuffer = 0;
  NumberOfBytesRead = 0;
  *a3 = 0;
  v6 = 0;
  v29 = 0;
  v27 = 0;
  LastError = ConstructRepubBlockFolderRoot((const unsigned __int16 *)a2 + 10, &v27, &v30);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v10 = 144;
      LODWORD(v11) = (_DWORD)a2 + 20;
LABEL_10:
      WPP_SF_Sd(
        *((_QWORD *)v9 + 12),
        v10,
        (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
        (_DWORD)v11,
        LastError);
      goto LABEL_60;
    }
    goto LABEL_60;
  }
  operator delete(0);
  v6 = v27;
  v29 = v27;
  v12 = StringCchCopyW(FileName, 0x104u, v27);
  if ( v12 < 0 )
  {
    v8 = (unsigned __int16)v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_60;
    }
    v14 = 145;
    v15 = (unsigned __int16)v12;
    goto LABEL_16;
  }
  appended = AppendFilePath(FileName, L"GUID.dat");
  v8 = appended;
  if ( appended )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_60;
    }
    v14 = 146;
    v15 = appended;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v13 + 12), v14, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v15);
    goto LABEL_60;
  }
  FileW = CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError == 2 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          147,
          (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
          (unsigned int)FileName,
          2);
      }
      v8 = 0;
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v10 = 148;
        v11 = FileName;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v18 = operator new[](0x12u);
    std::auto_ptr<unsigned short>::reset(&lpBuffer, v18);
    v5 = lpBuffer;
    if ( ReadFile(FileW, lpBuffer, 0x12u, &NumberOfBytesRead, 0) )
    {
      if ( NumberOfBytesRead >= 0x12 )
      {
        v21 = memcpy_s((char *)a2 + 4, 0x10u, v5, 0x10u);
        if ( v21 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              151,
              (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
              (unsigned int)FileName,
              v21);
          }
          v8 = 774;
        }
        else
        {
          *(_WORD *)a2 = v5[8];
          *a3 = 1;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_S_guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 152, v22, (unsigned int)FileName, (__int64)a2 + 4);
          }
        }
      }
      else
      {
        v8 = 13;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_SDDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 150, v19, (unsigned int)FileName, NumberOfBytesRead);
        }
      }
    }
    else
    {
      v20 = GetLastError();
      v8 = v20;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          149,
          (unsigned int)WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids,
          (unsigned int)FileName,
          v20);
      }
    }
    if ( !CloseHandle(FileW) )
    {
      v23 = GetLastError();
      v24 = v23;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 153, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v23);
      }
      if ( !v8 )
        v8 = v24;
    }
  }
LABEL_60:
  operator delete(v6);
  operator delete(v5);
  return v8;
}

```

## disassembly

```asm
0x18004bcb0  mov     [rsp-8+arg_0], rbx
0x18004bcb5  push    rbp
0x18004bcb6  push    rsi
0x18004bcb7  push    rdi
0x18004bcb8  push    r12
0x18004bcba  push    r13
0x18004bcbc  push    r14
0x18004bcbe  push    r15
0x18004bcc0  lea     rbp, [rsp-190h]
0x18004bcc8  sub     rsp, 290h
0x18004bccf  mov     rax, cs:__security_cookie
0x18004bcd6  xor     rax, rsp
0x18004bcd9  mov     [rbp+1C0h+var_40], rax
0x18004bce0  mov     r15, r8
0x18004bce3  mov     r14, rdx
0x18004bce6  lea     rax, WPP_GLOBAL_Control
0x18004bced  mov     r12b, 4
0x18004bcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bcf7  cmp     rcx, rax
0x18004bcfa  jz      short loc_18004BD1D
0x18004bcfc  test    [rcx+6Ch], r12b
0x18004bd00  jz      short loc_18004BD1D
0x18004bd02  cmp     [rcx+69h], r12b
0x18004bd06  jb      short loc_18004BD1D
0x18004bd08  mov     edx, 8Fh
0x18004bd0d  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bd14  mov     rcx, [rcx+60h]
0x18004bd18  call    WPP_SF_
0x18004bd1d  xor     eax, eax
0x18004bd1f  mov     r13d, eax
0x18004bd22  mov     [rsp+2C0h+lpBuffer], rax
0x18004bd27  mov     [rsp+2C0h+NumberOfBytesRead], eax
0x18004bd2b  mov     [r15], al
0x18004bd2e  mov     ebx, eax
0x18004bd30  mov     [rsp+2C0h+var_268], rax
0x18004bd35  mov     [rsp+2C0h+var_278], rax
0x18004bd3a  lea     rsi, [r14+14h]
0x18004bd3e  lea     r8, [rsp+2C0h+var_260]; unsigned __int64 *
0x18004bd43  lea     rdx, [rsp+2C0h+var_278]; unsigned __int16 **
0x18004bd48  mov     rcx, rsi; unsigned __int16 *
0x18004bd4b  call    ?ConstructRepubBlockFolderRoot@@YAKPEBGPEAPEAGPEA_K@Z; ConstructRepubBlockFolderRoot(ushort const *,ushort * *,unsigned __int64 *)
0x18004bd50  mov     edi, eax
0x18004bd52  test    eax, eax
0x18004bd54  jz      short loc_18004BDA2
0x18004bd56  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd5d  lea     r14, WPP_GLOBAL_Control
0x18004bd64  cmp     rcx, r14
0x18004bd67  jz      loc_18004C0FF
0x18004bd6d  test    [rcx+6Ch], r12b
0x18004bd71  jz      loc_18004C0FF
0x18004bd77  cmp     byte ptr [rcx+69h], 1
0x18004bd7b  jb      loc_18004C0FF
0x18004bd81  mov     edx, 90h
0x18004bd86  mov     r9, rsi
0x18004bd89  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18004bd8d  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bd94  mov     rcx, [rcx+60h]
0x18004bd98  call    WPP_SF_Sd
0x18004bd9d  jmp     loc_18004C0FF
0x18004bda2  xor     ecx, ecx; Block
0x18004bda4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004bda9  mov     rbx, [rsp+2C0h+var_278]
0x18004bdae  mov     [rsp+2C0h+var_268], rbx
0x18004bdb3  mov     r8, rbx; unsigned __int16 *
0x18004bdb6  mov     edx, 104h; unsigned __int64
0x18004bdbb  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x18004bdc0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bdc5  test    eax, eax
0x18004bdc7  jns     short loc_18004BE14
0x18004bdc9  movzx   edi, ax
0x18004bdcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bdd3  lea     r14, WPP_GLOBAL_Control
0x18004bdda  cmp     rcx, r14
0x18004bddd  jz      loc_18004C0FF
0x18004bde3  test    [rcx+6Ch], r12b
0x18004bde7  jz      loc_18004C0FF
0x18004bded  cmp     byte ptr [rcx+69h], 1
0x18004bdf1  jb      loc_18004C0FF
0x18004bdf7  mov     edx, 91h
0x18004bdfc  mov     r9d, edi
0x18004bdff  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004be06  mov     rcx, [rcx+60h]
0x18004be0a  call    WPP_SF_d
0x18004be0f  jmp     loc_18004C0FF
0x18004be14  lea     rdx, ?c_wszRepubBlockDatabaseGuidFile@@3QBGB; "GUID.dat"
0x18004be1b  lea     rcx, [rsp+2C0h+FileName]; unsigned __int16 *
0x18004be20  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x18004be25  mov     edi, eax
0x18004be27  test    eax, eax
0x18004be29  jz      short loc_18004BE60
0x18004be2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be32  lea     r14, WPP_GLOBAL_Control
0x18004be39  cmp     rcx, r14
0x18004be3c  jz      loc_18004C0FF
0x18004be42  test    [rcx+6Ch], r12b
0x18004be46  jz      loc_18004C0FF
0x18004be4c  cmp     byte ptr [rcx+69h], 1
0x18004be50  jb      loc_18004C0FF
0x18004be56  mov     edx, 92h
0x18004be5b  mov     r9d, eax
0x18004be5e  jmp     short loc_18004BDFF
0x18004be60  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x18004be69  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004be71  mov     [rsp+2C0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004be79  xor     r9d, r9d; lpSecurityAttributes
0x18004be7c  mov     edx, 80000000h; dwDesiredAccess
0x18004be81  lea     r8d, [r9+1]; dwShareMode
0x18004be85  lea     rcx, [rsp+2C0h+FileName]; lpFileName
0x18004be8a  call    cs:__imp_CreateFileW
0x18004be90  mov     r12, rax
0x18004be93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004be97  jnz     loc_18004BF28
0x18004be9d  call    cs:__imp_GetLastError
0x18004bea3  mov     edi, eax
0x18004bea5  cmp     eax, 2
0x18004bea8  jnz     short loc_18004BEEE
0x18004beaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004beb1  lea     r14, WPP_GLOBAL_Control
0x18004beb8  cmp     rcx, r14
0x18004bebb  jz      short loc_18004BEE7
0x18004bebd  test    byte ptr [rcx+6Ch], 4
0x18004bec1  jz      short loc_18004BEE7
0x18004bec3  cmp     byte ptr [rcx+69h], 4
0x18004bec7  jb      short loc_18004BEE7
0x18004bec9  mov     edx, 93h
0x18004bece  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18004bed2  lea     r9, [rsp+2C0h+FileName]
0x18004bed7  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bede  mov     rcx, [rcx+60h]
0x18004bee2  call    WPP_SF_Sd
0x18004bee7  xor     edi, edi
0x18004bee9  jmp     loc_18004C0FF
0x18004beee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bef5  lea     r14, WPP_GLOBAL_Control
0x18004befc  cmp     rcx, r14
0x18004beff  jz      loc_18004C0FF
0x18004bf05  test    byte ptr [rcx+6Ch], 4
0x18004bf09  jz      loc_18004C0FF
0x18004bf0f  cmp     byte ptr [rcx+69h], 1
0x18004bf13  jb      loc_18004C0FF
0x18004bf19  mov     edx, 94h
0x18004bf1e  lea     r9, [rsp+2C0h+FileName]
0x18004bf23  jmp     loc_18004BD89
0x18004bf28  mov     esi, 12h
0x18004bf2d  mov     ecx, esi; unsigned __int64
0x18004bf2f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004bf34  mov     rdx, rax
0x18004bf37  lea     rcx, [rsp+2C0h+lpBuffer]
0x18004bf3c  call    ?reset@?$auto_ptr@G@std@@QEAAXPEAG@Z; std::auto_ptr<ushort>::reset(ushort *)
0x18004bf41  mov     qword ptr [rsp+2C0h+dwCreationDisposition], 0; lpOverlapped
0x18004bf4a  lea     r9, [rsp+2C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18004bf4f  mov     r8d, esi; nNumberOfBytesToRead
0x18004bf52  mov     r13, [rsp+2C0h+lpBuffer]
0x18004bf57  mov     rdx, r13; lpBuffer
0x18004bf5a  mov     rcx, r12; hFile
0x18004bf5d  call    cs:__imp_ReadFile
0x18004bf63  test    eax, eax
0x18004bf65  jnz     short loc_18004BFBD
0x18004bf67  call    cs:__imp_GetLastError
0x18004bf6d  mov     edi, eax
0x18004bf6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf76  lea     r14, WPP_GLOBAL_Control
0x18004bf7d  cmp     rcx, r14
0x18004bf80  jz      loc_18004C0B5
0x18004bf86  test    byte ptr [rcx+6Ch], 4
0x18004bf8a  jz      loc_18004C0B5
0x18004bf90  cmp     byte ptr [rcx+69h], 1
0x18004bf94  jb      loc_18004C0B5
0x18004bf9a  mov     edx, 95h
0x18004bf9f  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18004bfa3  lea     r9, [rsp+2C0h+FileName]
0x18004bfa8  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004bfaf  mov     rcx, [rcx+60h]
0x18004bfb3  call    WPP_SF_Sd
0x18004bfb8  jmp     loc_18004C0B5
0x18004bfbd  mov     eax, [rsp+2C0h+NumberOfBytesRead]
0x18004bfc1  cmp     eax, esi
0x18004bfc3  jnb     short loc_18004C011
0x18004bfc5  mov     edi, 0Dh
0x18004bfca  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bfd1  lea     r14, WPP_GLOBAL_Control
0x18004bfd8  cmp     rcx, r14
0x18004bfdb  jz      loc_18004C0B5
0x18004bfe1  test    byte ptr [rcx+6Ch], 4
0x18004bfe5  jz      loc_18004C0B5
0x18004bfeb  cmp     byte ptr [rcx+69h], 1
0x18004bfef  jb      loc_18004C0B5
0x18004bff5  mov     edx, 96h
0x18004bffa  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18004bffe  lea     r9, [rsp+2C0h+FileName]
0x18004c003  mov     rcx, [rcx+60h]
0x18004c007  call    WPP_SF_SDDD
0x18004c00c  jmp     loc_18004C0B5
0x18004c011  lea     rsi, [r14+4]
0x18004c015  mov     edx, 10h; DestinationSize
0x18004c01a  mov     r9d, edx; SourceSize
0x18004c01d  mov     r8, r13; Source
0x18004c020  mov     rcx, rsi; Destination
0x18004c023  call    cs:__imp_memcpy_s
0x18004c029  test    eax, eax
0x18004c02b  jz      short loc_18004C071
0x18004c02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c034  lea     r14, WPP_GLOBAL_Control
0x18004c03b  cmp     rcx, r14
0x18004c03e  jz      short loc_18004C06A
0x18004c040  test    byte ptr [rcx+6Ch], 4
0x18004c044  jz      short loc_18004C06A
0x18004c046  cmp     byte ptr [rcx+69h], 1
0x18004c04a  jb      short loc_18004C06A
0x18004c04c  mov     edx, 97h
0x18004c051  mov     [rsp+2C0h+dwCreationDisposition], eax
0x18004c055  lea     r9, [rsp+2C0h+FileName]
0x18004c05a  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004c061  mov     rcx, [rcx+60h]
0x18004c065  call    WPP_SF_Sd
0x18004c06a  mov     edi, 306h
0x18004c06f  jmp     short loc_18004C0B5
0x18004c071  movzx   eax, word ptr [r13+10h]
0x18004c076  mov     [r14], ax
0x18004c07a  mov     byte ptr [r15], 1
0x18004c07e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c085  lea     r14, WPP_GLOBAL_Control
0x18004c08c  cmp     rcx, r14
0x18004c08f  jz      short loc_18004C0B5
0x18004c091  test    byte ptr [rcx+6Ch], 4
0x18004c095  jz      short loc_18004C0B5
0x18004c097  cmp     byte ptr [rcx+69h], 4
0x18004c09b  jb      short loc_18004C0B5
0x18004c09d  mov     edx, 98h
0x18004c0a2  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rsi
0x18004c0a7  lea     r9, [rsp+2C0h+FileName]
0x18004c0ac  mov     rcx, [rcx+60h]
0x18004c0b0  call    WPP_SF_S_guid_
0x18004c0b5  mov     rcx, r12; hObject
0x18004c0b8  call    cs:__imp_CloseHandle
0x18004c0be  test    eax, eax
0x18004c0c0  jnz     short loc_18004C0FF
0x18004c0c2  call    cs:__imp_GetLastError
0x18004c0c8  mov     esi, eax
0x18004c0ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0d1  cmp     rcx, r14
0x18004c0d4  jz      short loc_18004C0FA
0x18004c0d6  test    byte ptr [rcx+6Ch], 4
0x18004c0da  jz      short loc_18004C0FA
0x18004c0dc  cmp     byte ptr [rcx+69h], 1
0x18004c0e0  jb      short loc_18004C0FA
0x18004c0e2  mov     edx, 99h
0x18004c0e7  mov     r9d, eax
0x18004c0ea  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18004c0f1  mov     rcx, [rcx+60h]
0x18004c0f5  call    WPP_SF_d
0x18004c0fa  test    edi, edi
0x18004c0fc  cmovz   edi, esi
0x18004c0ff  mov     rcx, rbx; Block
0x18004c102  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c107  nop
0x18004c108  mov     rcx, r13; Block
0x18004c10b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004c110  mov     eax, edi
0x18004c112  mov     rcx, [rbp+1C0h+var_40]
0x18004c119  xor     rcx, rsp; StackCookie
0x18004c11c  call    __security_check_cookie
0x18004c121  mov     rbx, [rsp+2C0h+arg_0]
0x18004c129  add     rsp, 290h
0x18004c130  pop     r15
0x18004c132  pop     r14
0x18004c134  pop     r13
0x18004c136  pop     r12
0x18004c138  pop     rdi
0x18004c139  pop     rsi
0x18004c13a  pop     rbp
0x18004c13b  retn
```
