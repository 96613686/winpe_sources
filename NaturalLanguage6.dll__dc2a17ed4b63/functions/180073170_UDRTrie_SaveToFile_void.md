# UDRTrie::SaveToFile(void)

- ea: `0x180073170`
- end: `0x18007382e`
- name: `?SaveToFile@UDRTrie@@QEAAXXZ`
- size: `1726`
- prototype: `void __fastcall(UDRTrie *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180073ac8`
- `0x180073ba0`

## callees

- `0x18000b130`
- `0x180035640`
- `0x18003c078`
- `0x18003ed6c`
- `0x1800729fc`
- `0x180073170`
- `0x180074110`
- `0x1800758e0`
- `0x18009dc30`
- `0x18009e300`

## import_xrefs

- `msvcrt!_itow_s` at `0x180073374`
- `msvcrt!_itow_s` at `0x180073374`
- `msvcrt!_itoa_s` at `0x180073429`
- `msvcrt!_itoa_s` at `0x180073429`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800736ba`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800736ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800732de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007343a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800737d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800732de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073385`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007343a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800737d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073200`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180073200`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800737a2`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800737a2`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800737b3`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800737b3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007324a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18007324a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800732cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007335a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800733ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007340f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007349b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800734bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073513`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073558`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007357a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800735be`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800735e2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073624`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073654`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800736ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007370c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073730`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800732cd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007335a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800733ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007340f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007349b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800734bf`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073513`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073558`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007357a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800735be`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800735e2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073624`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073654`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800736ea`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18007370c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180073730`

## pseudocode

```c
void __fastcall UDRTrie::SaveToFile(UDRTrie *this)
{
  const WCHAR *v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rax
  HANDLE FileW; // rax
  char v6; // cl
  int *v7; // rdx
  int v8; // ecx
  int v9; // esi
  void *v10; // rcx
  errno_t v11; // eax
  void *v12; // rcx
  __int64 v13; // r8
  DWORD v14; // r8d
  const char *v15; // rdx
  errno_t v16; // eax
  void *v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rax
  void *v20; // rcx
  int v21; // r8d
  DWORD v22; // r8d
  const char *v23; // rdx
  int v24; // r8d
  __int64 v25; // rbx
  int v26; // ebx
  const void *v27; // rax
  DWORD v28; // r8d
  const char *v29; // rdx
  __int64 v30; // rbx
  const WCHAR *v31; // rax
  DWORD v32; // ebx
  int v33; // ecx
  char v34; // dl
  __int64 v35; // rax
  int v36; // eax
  UDRTrie *v37; // rbx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-678h] BYREF
  UDRTrie *v39; // [rsp+48h] [rbp-670h]
  __int64 v40; // [rsp+50h] [rbp-668h]
  _BYTE pExceptionObject[64]; // [rsp+58h] [rbp-660h] BYREF
  _BYTE v42[64]; // [rsp+98h] [rbp-620h] BYREF
  _BYTE v43[64]; // [rsp+D8h] [rbp-5E0h] BYREF
  _BYTE v44[64]; // [rsp+118h] [rbp-5A0h] BYREF
  _BYTE v45[64]; // [rsp+158h] [rbp-560h] BYREF
  _BYTE v46[72]; // [rsp+198h] [rbp-520h] BYREF
  _BYTE v47[1024]; // [rsp+1E0h] [rbp-4D8h] BYREF
  UDRTrie *v48; // [rsp+5E0h] [rbp-D8h]
  __int64 v49; // [rsp+5E8h] [rbp-D0h]
  char v50; // [rsp+5F2h] [rbp-C6h]
  char v51; // [rsp+5F3h] [rbp-C5h]
  char v52; // [rsp+5F4h] [rbp-C4h]
  __int64 v53; // [rsp+5F8h] [rbp-C0h]
  int v54; // [rsp+600h] [rbp-B8h]
  char v55; // [rsp+604h] [rbp-B4h]
  BOOL UsedDefaultChar[2]; // [rsp+610h] [rbp-A8h] BYREF
  wchar_t Buffer[12]; // [rsp+618h] [rbp-A0h] BYREF
  unsigned __int16 MultiByteStr[40]; // [rsp+630h] [rbp-88h] BYREF
  const void *retaddr; // [rsp+6B8h] [rbp+0h]

  v40 = -2;
  v39 = this;
  v2 = (const WCHAR *)((char *)this + 36);
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  if ( !v4 || !*((_BYTE *)this + 1096) )
    return;
  if ( ((*((_QWORD *)this + 133) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    FileW = CreateFileW(v2, 0xC0000000, 0, 0, 3u, 0x80u, 0);
    *((_QWORD *)this + 133) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      CNLException::CNLException((CNLException *)pExceptionObject, 3241213976LL, retaddr);
      throw (CNLException *)pExceptionObject;
    }
  }
  try
  {
    if ( SetFilePointer(*((HANDLE *)this + 133), 0, 0, 0) )
    {
      CNLException::CNLException((CNLException *)v42, 3241213975LL, retaddr);
      throw (CNLException *)v42;
    }
    NumberOfBytesWritten = 0;
    v6 = *((_BYTE *)this + 1097);
    if ( v6 || *((_DWORD *)this + 275) == 65001 )
    {
      v7 = (int *)byte_1800C6610;
      if ( !v6 )
        v7 = &dword_1800C6614;
      if ( !WriteFile(*((HANDLE *)this + 133), v7, 3 - (v6 != 0), &NumberOfBytesWritten, 0) )
      {
        CloseHandle(*((HANDLE *)this + 133));
        *((_QWORD *)this + 133) = 0;
        CNLException::CNLException((CNLException *)v43, 3241213975LL, retaddr);
        throw (CNLException *)v43;
      }
    }
    if ( IsLangidValid(*((_WORD *)this + 560)) )
    {
      v9 = v8;
      v10 = (void *)*((_QWORD *)this + 133);
      if ( *((_BYTE *)this + 1097) )
      {
        WriteFile(v10, L"#LID ", 0xAu, &NumberOfBytesWritten, 0);
        v11 = _itow_s(v9, Buffer, 6u, 10);
        v12 = (void *)*((_QWORD *)this + 133);
        if ( v11 )
        {
          CloseHandle(v12);
          *((_QWORD *)this + 133) = 0;
          CNLException::CNLException((CNLException *)v44, 3241213975LL, retaddr);
          throw (CNLException *)v44;
        }
        v13 = -1;
        do
          ++v13;
        while ( Buffer[v13] );
        WriteFile(v12, Buffer, 2 * v13, &NumberOfBytesWritten, 0);
        v14 = 4;
        v15 = (const char *)L"\r\n";
      }
      else
      {
        WriteFile(v10, "#LID ", 5u, &NumberOfBytesWritten, 0);
        v16 = _itoa_s(v9, (char *)UsedDefaultChar, 6u, 10);
        v17 = (void *)*((_QWORD *)this + 133);
        if ( v16 )
        {
          CloseHandle(v17);
          *((_QWORD *)this + 133) = 0;
          CNLException::CNLException((CNLException *)v45, 3241213975LL, retaddr);
          throw (CNLException *)v45;
        }
        v18 = -1;
        do
          ++v18;
        while ( *((_BYTE *)UsedDefaultChar + v18) );
        WriteFile(v17, UsedDefaultChar, v18, &NumberOfBytesWritten, 0);
        v14 = 2;
        v15 = "\r\n";
      }
      WriteFile(*((HANDLE *)this + 133), v15, v14, &NumberOfBytesWritten, 0);
    }
    v19 = *(_QWORD *)((char *)this + 1124) - *(_QWORD *)&GUID_NULL.Data1;
    if ( !v19 )
      v19 = *(_QWORD *)((char *)this + 1132) - *(_QWORD *)GUID_NULL.Data4;
    if ( v19 )
    {
      v20 = (void *)*((_QWORD *)this + 133);
      if ( *((_BYTE *)this + 1097) )
      {
        WriteFile(v20, L"#GUID ", 0xCu, &NumberOfBytesWritten, 0);
        GUIDToString((const struct _GUID *)((char *)this + 1124), MultiByteStr, v21);
        do
          ++v3;
        while ( MultiByteStr[v3] );
        WriteFile(*((HANDLE *)this + 133), MultiByteStr, 2 * v3, &NumberOfBytesWritten, 0);
        v22 = 4;
        v23 = (const char *)L"\r\n";
      }
      else
      {
        WriteFile(v20, "#GUID ", 6u, &NumberOfBytesWritten, 0);
        GUIDToString((const struct _GUID *)((char *)this + 1124), MultiByteStr, v24);
        do
          ++v3;
        while ( MultiByteStr[v3] );
        WriteFile(*((HANDLE *)this + 133), MultiByteStr, v3, &NumberOfBytesWritten, 0);
        v22 = 2;
        v23 = "\r\n";
      }
      WriteFile(*((HANDLE *)this + 133), v23, v22, &NumberOfBytesWritten, 0);
    }
    v25 = *((_QWORD *)this + 210);
    if ( v25 <= 1 )
      goto LABEL_46;
    if ( *((_BYTE *)this + 1097) )
    {
      WriteFile(*((HANDLE *)this + 133), L"#NAME ", 0xCu, &NumberOfBytesWritten, 0);
      v26 = *((_DWORD *)this + 420) - 1;
      v27 = (const void *)CArray<unsigned short,CArrayAllocator_malloc>::ElementAt((char *)this + 1672);
      WriteFile(*((HANDLE *)this + 133), v27, 2 * v26, &NumberOfBytesWritten, 0);
      v28 = 4;
      v29 = (const char *)L"\r\n";
    }
    else
    {
      UsedDefaultChar[0] = 0;
      v30 = v25 - 1;
      *(_QWORD *)Buffer = v30;
      v31 = (const WCHAR *)CArray<unsigned short,CArrayAllocator_malloc>::ElementAt((char *)this + 1672);
      v32 = WideCharToMultiByte(0, 0, v31, v30, (LPSTR)MultiByteStr, 40, 0, UsedDefaultChar);
      if ( UsedDefaultChar[0] )
        goto LABEL_46;
      WriteFile(*((HANDLE *)this + 133), "#NAME ", 6u, &NumberOfBytesWritten, 0);
      WriteFile(*((HANDLE *)this + 133), MultiByteStr, v32, &NumberOfBytesWritten, 0);
      v28 = 2;
      v29 = "\r\n";
    }
    WriteFile(*((HANDLE *)this + 133), v29, v28, &NumberOfBytesWritten, 0);
LABEL_46:
    v33 = *((_DWORD *)this + 275);
    v34 = *((_BYTE *)this + 1097);
    v35 = *((_QWORD *)this + 133);
    v48 = this;
    v51 = 0;
    v50 = 0;
    v52 = 0;
    v49 = 0;
    v53 = v35;
    v54 = v33;
    v55 = v34;
    v36 = CWriteEnum::run((CWriteEnum *)v47);
    ThrowIfFailed(v36);
    if ( !SetEndOfFile(*((HANDLE *)this + 133)) || !FlushFileBuffers(*((HANDLE *)this + 133)) )
    {
      CNLException::CNLException((CNLException *)v46, 3241213975LL, retaddr);
      throw (CNLException *)v46;
    }
    *((_BYTE *)this + 1096) = 0;
    UDRTrie::setDate(this);
  }
  catch ( ... )
  {
    ImxTraceCatch(3, 3134570718LL, retaddr);
    v37 = v39;
    CloseHandle(*((HANDLE *)v39 + 133));
    *((_QWORD *)v37 + 133) = 0;
    throw;
  }
  CloseHandle(*((HANDLE *)this + 133));
  *((_QWORD *)this + 133) = 0;
}

```

## disassembly

```asm
0x180073170  push    rbx
0x180073172  push    rsi
0x180073173  push    rdi
0x180073174  push    r14
0x180073176  sub     rsp, 698h
0x18007317d  mov     [rsp+6B8h+var_668], 0FFFFFFFFFFFFFFFEh
0x180073186  mov     rax, cs:__security_cookie
0x18007318d  xor     rax, rsp
0x180073190  mov     [rsp+6B8h+var_38], rax
0x180073198  mov     rdi, rcx
0x18007319b  mov     [rsp+6B8h+var_670], rcx
0x1800731a0  add     rcx, 24h ; '$'; lpFileName
0x1800731a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800731a8  mov     rax, rbx
0x1800731ab  xor     r14d, r14d
0x1800731ae  inc     rax
0x1800731b1  cmp     [rcx+rax*2], r14w
0x1800731b6  jnz     short loc_1800731AE
0x1800731b8  test    rax, rax
0x1800731bb  jz      loc_1800737E1
0x1800731c1  cmp     [rdi+448h], r14b
0x1800731c8  jz      loc_1800737E1
0x1800731ce  mov     rax, [rdi+428h]
0x1800731d5  inc     rax
0x1800731d8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800731de  jnz     short loc_18007323B
0x1800731e0  mov     [rsp+6B8h+hTemplateFile], r14; hTemplateFile
0x1800731e5  mov     [rsp+6B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800731ed  mov     [rsp+6B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800731f5  xor     r9d, r9d; lpSecurityAttributes
0x1800731f8  xor     r8d, r8d; dwShareMode
0x1800731fb  mov     edx, 0C0000000h; dwDesiredAccess
0x180073200  call    cs:__imp_CreateFileW
0x180073206  mov     [rdi+428h], rax
0x18007320d  cmp     rax, rbx
0x180073210  jnz     short loc_18007323B
0x180073212  mov     r8, [rsp+6B8h]; void *
0x18007321a  mov     edx, 0C1310018h; int
0x18007321f  lea     rcx, [rsp+6B8h+pExceptionObject]; this
0x180073224  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073229  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073230  lea     rcx, [rsp+6B8h+pExceptionObject]; pExceptionObject
0x180073235  call    _CxxThrowException_0
0x18007323b  xor     r9d, r9d; dwMoveMethod
0x18007323e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180073241  xor     edx, edx; lDistanceToMove
0x180073243  mov     rcx, [rdi+428h]; hFile
0x18007324a  call    cs:__imp_SetFilePointer
0x180073250  test    eax, eax
0x180073252  jz      short loc_180073282
0x180073254  mov     r8, [rsp+6B8h]; void *
0x18007325c  mov     edx, 0C1310017h; int
0x180073261  lea     rcx, [rsp+6B8h+var_620]; this
0x180073269  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18007326e  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073275  lea     rcx, [rsp+6B8h+var_620]; pExceptionObject
0x18007327d  call    _CxxThrowException_0
0x180073282  mov     [rsp+6B8h+NumberOfBytesWritten], r14d
0x180073287  mov     cl, [rdi+449h]
0x18007328d  test    cl, cl
0x18007328f  jnz     short loc_18007329D
0x180073291  cmp     dword ptr [rdi+44Ch], 0FDE9h
0x18007329b  jnz     short loc_180073319
0x18007329d  mov     al, cl
0x18007329f  neg     al
0x1800732a1  sbb     r8d, r8d
0x1800732a4  add     r8d, 3; nNumberOfBytesToWrite
0x1800732a8  lea     rax, dword_1800C6614
0x1800732af  lea     rdx, byte_1800C6610
0x1800732b6  test    cl, cl
0x1800732b8  cmovz   rdx, rax; lpBuffer
0x1800732bc  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800732c1  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800732c6  mov     rcx, [rdi+428h]; hFile
0x1800732cd  call    cs:__imp_WriteFile
0x1800732d3  test    eax, eax
0x1800732d5  jnz     short loc_180073319
0x1800732d7  mov     rcx, [rdi+428h]; hObject
0x1800732de  call    cs:__imp_CloseHandle
0x1800732e4  mov     [rdi+428h], r14
0x1800732eb  mov     r8, [rsp+6B8h]; void *
0x1800732f3  mov     edx, 0C1310017h; int
0x1800732f8  lea     rcx, [rsp+6B8h+var_5E0]; this
0x180073300  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073305  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18007330c  lea     rcx, [rsp+6B8h+var_5E0]; pExceptionObject
0x180073314  call    _CxxThrowException_0
0x180073319  movzx   ecx, word ptr [rdi+460h]; unsigned __int16
0x180073320  call    ?IsLangidValid@@YA_NG@Z; IsLangidValid(ushort)
0x180073325  test    al, al
0x180073327  jz      loc_1800734C5
0x18007332d  mov     esi, ecx
0x18007332f  mov     rcx, [rdi+428h]; hFile
0x180073336  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x18007333b  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180073340  cmp     [rdi+449h], r14b
0x180073347  jz      loc_180073402
0x18007334d  mov     r8d, 0Ah; nNumberOfBytesToWrite
0x180073353  lea     rdx, aLid_0; "#LID "
0x18007335a  call    cs:__imp_WriteFile
0x180073360  mov     r9d, 0Ah; Radix
0x180073366  lea     r8d, [r9-4]; BufferCount
0x18007336a  lea     rdx, [rsp+6B8h+Buffer]; Buffer
0x180073372  mov     ecx, esi; Value
0x180073374  call    cs:__imp__itow_s
0x18007337a  mov     rcx, [rdi+428h]; hFile
0x180073381  test    eax, eax
0x180073383  jz      short loc_1800733C0
0x180073385  call    cs:__imp_CloseHandle
0x18007338b  mov     [rdi+428h], r14
0x180073392  mov     r8, [rsp+6B8h]; void *
0x18007339a  mov     edx, 0C1310017h; int
0x18007339f  lea     rcx, [rsp+6B8h+var_5A0]; this
0x1800733a7  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800733ac  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800733b3  lea     rcx, [rsp+6B8h+var_5A0]; pExceptionObject
0x1800733bb  call    _CxxThrowException_0
0x1800733c0  lea     rax, [rsp+6B8h+Buffer]
0x1800733c8  mov     r8, rbx
0x1800733cb  inc     r8
0x1800733ce  cmp     [rax+r8*2], r14w
0x1800733d3  jnz     short loc_1800733CB
0x1800733d5  add     r8d, r8d; nNumberOfBytesToWrite
0x1800733d8  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800733dd  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800733e2  lea     rdx, [rsp+6B8h+Buffer]; lpBuffer
0x1800733ea  call    cs:__imp_WriteFile
0x1800733f0  mov     r8d, 4
0x1800733f6  lea     rdx, asc_1800C5D34; "\r\n"
0x1800733fd  jmp     loc_1800734AE
0x180073402  mov     r8d, 5; nNumberOfBytesToWrite
0x180073408  lea     rdx, aLid; "#LID "
0x18007340f  call    cs:__imp_WriteFile
0x180073415  mov     r9d, 0Ah; Radix
0x18007341b  lea     r8d, [r9-4]; BufferCount
0x18007341f  lea     rdx, [rsp+6B8h+UsedDefaultChar]; Buffer
0x180073427  mov     ecx, esi; Value
0x180073429  call    cs:__imp__itoa_s
0x18007342f  mov     rcx, [rdi+428h]; hFile
0x180073436  test    eax, eax
0x180073438  jz      short loc_180073475
0x18007343a  call    cs:__imp_CloseHandle
0x180073440  mov     [rdi+428h], r14
0x180073447  mov     r8, [rsp+6B8h]; void *
0x18007344f  mov     edx, 0C1310017h; int
0x180073454  lea     rcx, [rsp+6B8h+var_560]; this
0x18007345c  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180073461  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180073468  lea     rcx, [rsp+6B8h+var_560]; pExceptionObject
0x180073470  call    _CxxThrowException_0
0x180073475  lea     rax, [rsp+6B8h+UsedDefaultChar]
0x18007347d  mov     r8, rbx
0x180073480  inc     r8; nNumberOfBytesToWrite
0x180073483  cmp     [rax+r8], r14b
0x180073487  jnz     short loc_180073480
0x180073489  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x18007348e  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180073493  lea     rdx, [rsp+6B8h+UsedDefaultChar]; lpBuffer
0x18007349b  call    cs:__imp_WriteFile
0x1800734a1  mov     r8d, 2; nNumberOfBytesToWrite
0x1800734a7  lea     rdx, asc_1800C65E8; "\r\n"
0x1800734ae  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800734b3  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800734b8  mov     rcx, [rdi+428h]; hFile
0x1800734bf  call    cs:__imp_WriteFile
0x1800734c5  lea     rsi, [rdi+464h]
0x1800734cc  mov     rax, [rsi]
0x1800734cf  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800734d6  jnz     short loc_1800734E3
0x1800734d8  mov     rax, [rsi+8]
0x1800734dc  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800734e3  test    rax, rax
0x1800734e6  jz      loc_1800735E8
0x1800734ec  mov     rcx, [rdi+428h]; hFile
0x1800734f3  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800734f8  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800734fd  cmp     [rdi+449h], r14b
0x180073504  jz      short loc_18007356D
0x180073506  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x18007350c  lea     rdx, aGuid; "#GUID "
0x180073513  call    cs:__imp_WriteFile
0x180073519  lea     rdx, [rsp+6B8h+MultiByteStr]; unsigned __int16 *
0x180073521  mov     rcx, rsi; struct _GUID *
0x180073524  call    ?GUIDToString@@YAJAEBU_GUID@@PEAGH@Z; GUIDToString(_GUID const &,ushort *,int)
0x180073529  lea     rax, [rsp+6B8h+MultiByteStr]
0x180073531  inc     rbx
0x180073534  cmp     [rax+rbx*2], r14w
0x180073539  jnz     short loc_180073531
0x18007353b  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x18007353f  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x180073544  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180073549  lea     rdx, [rsp+6B8h+MultiByteStr]; lpBuffer
0x180073551  mov     rcx, [rdi+428h]; hFile
0x180073558  call    cs:__imp_WriteFile
0x18007355e  mov     r8d, 4
0x180073564  lea     rdx, asc_1800C5D34; "\r\n"
0x18007356b  jmp     short loc_1800735D1
0x18007356d  mov     r8d, 6; nNumberOfBytesToWrite
0x180073573  lea     rdx, aGuid_0; "#GUID "
0x18007357a  call    cs:__imp_WriteFile
0x180073580  lea     rdx, [rsp+6B8h+MultiByteStr]; unsigned __int16 *
0x180073588  mov     rcx, rsi; struct _GUID *
0x18007358b  call    ?GUIDToString@@YAJAEBU_GUID@@PEAGH@Z; GUIDToString(_GUID const &,ushort *,int)
0x180073590  lea     rax, [rsp+6B8h+MultiByteStr]
0x180073598  inc     rbx
0x18007359b  cmp     [rax+rbx*2], r14w
0x1800735a0  jnz     short loc_180073598
0x1800735a2  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800735a5  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800735aa  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800735af  lea     rdx, [rsp+6B8h+MultiByteStr]; lpBuffer
0x1800735b7  mov     rcx, [rdi+428h]; hFile
0x1800735be  call    cs:__imp_WriteFile
0x1800735c4  mov     r8d, 2; nNumberOfBytesToWrite
0x1800735ca  lea     rdx, asc_1800C65E8; "\r\n"
0x1800735d1  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800735d6  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800735db  mov     rcx, [rdi+428h]; hFile
0x1800735e2  call    cs:__imp_WriteFile
0x1800735e8  lea     rsi, [rdi+688h]
0x1800735ef  mov     rbx, [rsi+8]
0x1800735f3  cmp     rbx, 1
0x1800735f7  jle     loc_180073736
0x1800735fd  cmp     [rdi+449h], r14b
0x180073604  jz      short loc_18007366C
0x180073606  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x18007360b  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180073610  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x180073616  lea     rdx, aName_0; "#NAME "
0x18007361d  mov     rcx, [rdi+428h]; hFile
0x180073624  call    cs:__imp_WriteFile
0x18007362a  mov     ebx, [rdi+690h]
0x180073630  dec     ebx
0x180073632  xor     edx, edx
0x180073634  mov     rcx, rsi
0x180073637  call    ?ElementAt@?$CArray@GVCArrayAllocator_malloc@@@@QEBAAEAG_J@Z; CArray<ushort,CArrayAllocator_malloc>::ElementAt(__int64)
0x18007363c  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180073640  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x180073645  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18007364a  mov     rdx, rax; lpBuffer
0x18007364d  mov     rcx, [rdi+428h]; hFile
0x180073654  call    cs:__imp_WriteFile
0x18007365a  mov     r8d, 4
0x180073660  lea     rdx, asc_1800C5D34; "\r\n"
0x180073667  jmp     loc_18007371F
0x18007366c  mov     [rsp+6B8h+UsedDefaultChar], r14d
0x180073674  dec     rbx
0x180073677  mov     qword ptr [rsp+6B8h+Buffer], rbx
0x18007367f  xor     edx, edx
0x180073681  mov     rcx, rsi
0x180073684  call    ?ElementAt@?$CArray@GVCArrayAllocator_malloc@@@@QEBAAEAG_J@Z; CArray<ushort,CArrayAllocator_malloc>::ElementAt(__int64)
0x180073689  mov     r9d, ebx; cchWideChar
0x18007368c  lea     rcx, [rsp+6B8h+UsedDefaultChar]
0x180073694  mov     [rsp+6B8h+lpUsedDefaultChar], rcx; lpUsedDefaultChar
0x180073699  mov     [rsp+6B8h+hTemplateFile], r14; lpDefaultChar
0x18007369e  mov     [rsp+6B8h+dwFlagsAndAttributes], 28h ; '('; cbMultiByte
0x1800736a6  lea     rcx, [rsp+6B8h+MultiByteStr]
0x1800736ae  mov     qword ptr [rsp+6B8h+dwCreationDisposition], rcx; lpMultiByteStr
0x1800736b3  mov     r8, rax; lpWideCharStr
0x1800736b6  xor     edx, edx; dwFlags
0x1800736b8  xor     ecx, ecx; CodePage
0x1800736ba  call    cs:__imp_WideCharToMultiByte
0x1800736c0  mov     ebx, eax
0x1800736c2  cmp     [rsp+6B8h+UsedDefaultChar], r14d
0x1800736ca  jnz     short loc_180073736
0x1800736cc  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800736d1  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800736d6  mov     r8d, 6; nNumberOfBytesToWrite
0x1800736dc  lea     rdx, aName; "#NAME "
0x1800736e3  mov     rcx, [rdi+428h]; hFile
0x1800736ea  call    cs:__imp_WriteFile
0x1800736f0  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x1800736f5  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800736fa  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800736fd  lea     rdx, [rsp+6B8h+MultiByteStr]; lpBuffer
0x180073705  mov     rcx, [rdi+428h]; hFile
0x18007370c  call    cs:__imp_WriteFile
0x180073712  mov     r8d, 2; nNumberOfBytesToWrite
0x180073718  lea     rdx, asc_1800C65E8; "\r\n"
0x18007371f  mov     qword ptr [rsp+6B8h+dwCreationDisposition], r14; lpOverlapped
0x180073724  lea     r9, [rsp+6B8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180073729  mov     rcx, [rdi+428h]; hFile
0x180073730  call    cs:__imp_WriteFile
0x180073736  mov     ecx, [rdi+44Ch]
0x18007373c  mov     dl, [rdi+449h]
0x180073742  mov     rax, [rdi+428h]
0x180073749  mov     [rsp+6B8h+var_D8], rdi
0x180073751  mov     [rsp+6B8h+var_C5], r14b
0x180073759  mov     [rsp+6B8h+var_C6], r14b
0x180073761  mov     [rsp+6B8h+var_C4], r14b
0x180073769  mov     [rsp+6B8h+var_D0], r14
0x180073771  mov     [rsp+6B8h+var_C0], rax
0x180073779  mov     [rsp+6B8h+var_B8], ecx
0x180073780  mov     [rsp+6B8h+var_B4], dl
0x180073787  lea     rcx, [rsp+6B8h+var_4D8]; this
0x18007378f  call    ?run@CWriteEnum@@QEAAKXZ; CWriteEnum::run(void)
0x180073794  mov     ecx, eax; int
0x180073796  call    ?ThrowIfFailed@@YAXJ@Z; ThrowIfFailed(long)
0x18007379b  mov     rcx, [rdi+428h]; hFile
0x1800737a2  call    cs:__imp_SetEndOfFile
  ... truncated ...
```
