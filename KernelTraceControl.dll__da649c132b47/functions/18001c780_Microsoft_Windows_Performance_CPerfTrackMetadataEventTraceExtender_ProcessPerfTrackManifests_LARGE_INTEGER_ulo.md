# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18001c780`
- end: `0x18001cd2c`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1452`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this, union _LARGE_INTEGER, int, int, char *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x1800067f0`
- `0x18001c780`
- `0x18001d60c`
- `0x18001dd1c`
- `0x180026e30`
- `0x180026f6c`
- `0x180027910`

## import_xrefs

- `msvcrt!malloc` at `0x18001cab0`
- `msvcrt!malloc` at `0x18001cab0`
- `msvcrt!free` at `0x18001ca94`
- `msvcrt!free` at `0x18001ca94`
- `KERNEL32!FindClose` at `0x18001cd01`
- `KERNEL32!FindClose` at `0x18001cd01`
- `KERNEL32!FindNextFileW` at `0x18001ccf0`
- `KERNEL32!FindNextFileW` at `0x18001ccf0`
- `KERNEL32!GetFileSize` at `0x18001c99c`
- `KERNEL32!GetFileSize` at `0x18001c99c`
- `KERNEL32!FindFirstFileW` at `0x18001c880`
- `KERNEL32!FindFirstFileW` at `0x18001c880`
- `KERNEL32!CloseHandle` at `0x18001ca28`
- `KERNEL32!CloseHandle` at `0x18001caf2`
- `KERNEL32!CloseHandle` at `0x18001cb15`
- `KERNEL32!CloseHandle` at `0x18001ccb3`
- `KERNEL32!CloseHandle` at `0x18001ccd2`
- `KERNEL32!CloseHandle` at `0x18001ca28`
- `KERNEL32!CloseHandle` at `0x18001caf2`
- `KERNEL32!CloseHandle` at `0x18001cb15`
- `KERNEL32!CloseHandle` at `0x18001ccb3`
- `KERNEL32!CloseHandle` at `0x18001ccd2`
- `KERNEL32!UnmapViewOfFile` at `0x18001cad5`
- `KERNEL32!UnmapViewOfFile` at `0x18001cc96`
- `KERNEL32!UnmapViewOfFile` at `0x18001cad5`
- `KERNEL32!UnmapViewOfFile` at `0x18001cc96`
- `KERNEL32!MapViewOfFileEx` at `0x18001ca0b`
- `KERNEL32!MapViewOfFileEx` at `0x18001ca0b`
- `KERNEL32!CreateFileMappingW` at `0x18001c9c1`
- `KERNEL32!CreateFileMappingW` at `0x18001c9c1`
- `KERNEL32!CreateFileW` at `0x18001c96e`
- `KERNEL32!CreateFileW` at `0x18001c96e`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4,
        char *a5,
        unsigned __int16 *a6)
{
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  int v9; // r8d
  WCHAR v10; // ax
  __int64 result; // rax
  HANDLE FirstFileW; // r12
  __int64 v13; // rdx
  WCHAR *v14; // rcx
  int v15; // r9d
  WCHAR v16; // ax
  void *v17; // rdi
  const void *v18; // r14
  HANDLE FileMappingW; // r15
  HANDLE FileW; // rax
  int Error; // eax
  int v22; // r12d
  size_t v23; // rbx
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v24; // r10
  char v25; // r12
  unsigned int v26; // ebx
  unsigned int v27; // eax
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v28; // rcx
  void *v29; // rax
  int v30; // ebx
  int v31; // ecx
  __int128 v32; // xmm0
  __int64 v33; // rax
  char *v34; // rcx
  __int64 v35; // rbx
  int v36; // ebx
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v38; // [rsp+58h] [rbp-A8h]
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v39; // [rsp+60h] [rbp-A0h]
  HANDLE v40; // [rsp+68h] [rbp-98h]
  int v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+74h] [rbp-8Ch]
  DWORD FileSizeHigh[2]; // [rsp+78h] [rbp-88h] BYREF
  const void *v44; // [rsp+80h] [rbp-80h]
  size_t Size; // [rsp+88h] [rbp-78h]
  HANDLE v46; // [rsp+90h] [rbp-70h]
  __int64 v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+A0h] [rbp-60h]
  __int128 v49; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  char v53[8]; // [rsp+E8h] [rbp-18h] BYREF
  _WORD v54[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v55; // [rsp+F4h] [rbp-Ch]
  char v56; // [rsp+F5h] [rbp-Bh]
  __int16 v57; // [rsp+F6h] [rbp-Ah]
  union _LARGE_INTEGER v58; // [rsp+100h] [rbp+0h]
  __int128 v59; // [rsp+108h] [rbp+8h]
  __int64 v60; // [rsp+138h] [rbp+38h]
  int v61; // [rsp+140h] [rbp+40h]
  int v62; // [rsp+144h] [rbp+44h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+150h] [rbp+50h] BYREF
  WCHAR FileName[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  WCHAR v65[264]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v52 = -2;
  v41 = a4;
  v42 = a3;
  v39 = this;
  memset_0(FileName, 0, 0x208u);
  v7 = 260;
  v8 = FileName;
  v9 = 0;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v10 = *(WCHAR *)((char *)v8 + a5 - (char *)FileName);
    if ( !v10 )
      break;
    *v8++ = v10;
    --v7;
  }
  while ( v7 );
  if ( !v7 )
  {
    --v8;
    v9 = -2147024774;
  }
  *v8 = 0;
  if ( v9 < 0 )
    return (unsigned int)v9;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( (int)result >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    v38 = FirstFileW;
    if ( FirstFileW == (HANDLE)-1LL )
      return 0;
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        goto LABEL_73;
      memset_0(v65, 0, 0x208u);
      v13 = 260;
      v14 = v65;
      v15 = 0;
      do
      {
        if ( v13 == -2147483386 )
          break;
        v16 = *(WCHAR *)((char *)v14 + a5 - (char *)v65);
        if ( !v16 )
          break;
        *v14++ = v16;
        --v13;
      }
      while ( v13 );
      if ( !v13 )
      {
        --v14;
        v15 = -2147024774;
      }
      *v14 = 0;
      if ( v15 < 0 || (int)StringCchCatW(v65, 0x104u, FindFileData.cFileName) < 0 )
        goto LABEL_73;
      v17 = 0;
      v40 = 0;
      v18 = 0;
      v44 = 0;
      FileMappingW = 0;
      v46 = 0;
      FileW = CreateFileW(v65, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        Error = ATL::AtlHresultFromLastError();
      }
      else
      {
        v17 = FileW;
        v40 = FileW;
        Error = 0;
      }
      if ( Error < 0 )
        goto LABEL_61;
      FileSizeHigh[0] = GetFileSize(v17, &FileSizeHigh[1]);
      FileMappingW = CreateFileMappingW(v17, 0, 2u, FileSizeHigh[1], FileSizeHigh[0], 0);
      v46 = FileMappingW;
      if ( FileMappingW )
      {
        v23 = *(_QWORD *)FileSizeHigh;
        Size = *(_QWORD *)FileSizeHigh;
        v48 = 4;
        v47 = 0;
        v18 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, *(SIZE_T *)FileSizeHigh, 0);
        v44 = v18;
        if ( v18 )
        {
          v22 = 0;
        }
        else
        {
          v22 = ATL::AtlHresultFromLastError();
          CloseHandle(FileMappingW);
          FileMappingW = 0;
          v46 = 0;
        }
      }
      else
      {
        v22 = ATL::AtlHresultFromLastError();
        v23 = Size;
      }
      if ( v22 < 0 || v23 > 0x100000 )
      {
        FirstFileW = v38;
LABEL_61:
        v36 = 0;
        if ( v18 )
        {
          if ( !UnmapViewOfFile(v18) )
            v36 = ATL::AtlHresultFromLastError();
          v44 = 0;
        }
        if ( FileMappingW )
        {
          if ( !CloseHandle(FileMappingW) && v36 >= 0 )
            ATL::AtlHresultFromLastError();
          v46 = 0;
        }
        if ( v17 )
        {
          CloseHandle(v17);
          v40 = 0;
        }
        goto LABEL_73;
      }
      v24 = v39;
      v25 = *((_BYTE *)v39 + 128);
      v26 = Size;
      if ( (unsigned int)Size < 4 )
        v25 = 1;
      v27 = 0;
      v37 = 0;
      if ( v25 )
        goto LABEL_56;
      if ( *((_DWORD *)v39 + 40) >= (unsigned int)(Size - 4) )
        goto LABEL_48;
      free(*((void **)v39 + 19));
      v28 = v39;
      *((_QWORD *)v39 + 19) = 0;
      *((_DWORD *)v28 + 40) = 0;
      v29 = malloc(v26);
      v24 = v39;
      *((_QWORD *)v39 + 19) = v29;
      if ( v29 )
        break;
LABEL_36:
      v30 = 0;
      if ( v18 )
      {
        if ( !UnmapViewOfFile(v18) )
          v30 = ATL::AtlHresultFromLastError();
        v44 = 0;
      }
      if ( FileMappingW )
      {
        if ( !CloseHandle(FileMappingW) && v30 >= 0 )
          ATL::AtlHresultFromLastError();
        v46 = 0;
      }
      if ( v17 )
      {
        CloseHandle(v17);
        v40 = 0;
      }
      FirstFileW = v38;
LABEL_73:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        return 0;
      }
    }
    *((_DWORD *)v24 + 40) = v26;
    v27 = v37;
LABEL_48:
    if ( *((_QWORD *)v24 + 14) )
    {
      v31 = (*((__int64 (__fastcall **)(__int64, const void *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD))v24
             + 14))(
              258,
              v18,
              v26,
              *((_QWORD *)v24 + 19) + 4LL,
              v26 - 4,
              4096,
              &v37,
              *((_QWORD *)v24 + 17));
      v27 = v37;
      v24 = v39;
    }
    else
    {
      v31 = -1073741822;
    }
    if ( v31 || v27 > v26 - 4 )
      v25 = 1;
    v37 = v27 + 4;
    **((_DWORD **)v24 + 19) = v26;
    if ( v25 )
    {
LABEL_56:
      *(_QWORD *)&v51 = v18;
      DWORD2(v51) = v26;
      v32 = v51;
      v33 = 40;
    }
    else
    {
      *(_QWORD *)&v50 = *((_QWORD *)v24 + 19);
      DWORD2(v50) = v37;
      v32 = v50;
      v33 = 64;
    }
    v49 = v32;
    v34 = (char *)v24 + v33;
    if ( (unsigned __int64)DWORD2(v32) + 48 <= 0xFFB8 )
    {
      v35 = *((_QWORD *)v34 + 1);
      if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                        v34,
                        v53,
                        &v49) == v35 )
      {
        memset_0(v54, 0, 0x58u);
        v54[0] = v41;
        v58 = a2;
        v59 = *(_OWORD *)PerfTrackMetadataGuid;
        v55 = 33 - (v25 != 0);
        v57 = 0;
        v56 = 0;
        v60 = v49;
        v61 = DWORD2(v32);
        v62 = v42;
        (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v39 + 2) + 192LL))(
          *((_QWORD *)v39 + 2),
          v54,
          0,
          0);
      }
    }
    goto LABEL_36;
  }
  return result;
}

```

## disassembly

```asm
0x18001c780  push    rbp
0x18001c782  push    rbx
0x18001c783  push    rsi
0x18001c784  push    rdi
0x18001c785  push    r12
0x18001c787  push    r13
0x18001c789  push    r14
0x18001c78b  push    r15
0x18001c78d  lea     rbp, [rsp-6D8h]
0x18001c795  sub     rsp, 7D8h
0x18001c79c  mov     [rbp+710h+var_730], 0FFFFFFFFFFFFFFFEh
0x18001c7a4  mov     rax, cs:__security_cookie
0x18001c7ab  xor     rax, rsp
0x18001c7ae  mov     [rbp+710h+var_50], rax
0x18001c7b5  mov     [rsp+810h+var_7A0], r9d
0x18001c7ba  mov     [rsp+810h+var_79C], r8d
0x18001c7bf  mov     rsi, rdx
0x18001c7c2  mov     [rsp+810h+var_7B0], rcx
0x18001c7c7  xor     edx, edx; Val
0x18001c7c9  mov     r8d, 208h; Size
0x18001c7cf  lea     rcx, [rbp+710h+FileName]; void *
0x18001c7d6  call    memset_0
0x18001c7db  mov     edx, 104h
0x18001c7e0  lea     rcx, [rbp+710h+FileName]
0x18001c7e7  xor     r13d, r13d
0x18001c7ea  mov     r8d, r13d
0x18001c7ed  lea     rax, [rbp+710h+FileName]
0x18001c7f4  mov     r9, [rbp+710h+arg_20]
0x18001c7fb  sub     r9, rax
0x18001c7fe  lea     ebx, [r13+1]
0x18001c802  lea     rax, [rdx+7FFFFEFAh]
0x18001c809  test    rax, rax
0x18001c80c  jz      short loc_18001C824
0x18001c80e  movzx   eax, word ptr [rcx+r9]
0x18001c813  test    ax, ax
0x18001c816  jz      short loc_18001C824
0x18001c818  mov     [rcx], ax
0x18001c81b  add     rcx, 2
0x18001c81f  sub     rdx, rbx
0x18001c822  jnz     short loc_18001C802
0x18001c824  test    rdx, rdx
0x18001c827  jnz     short loc_18001C833
0x18001c829  sub     rcx, 2
0x18001c82d  mov     r8d, 8007007Ah
0x18001c833  mov     [rcx], r13w
0x18001c837  test    r8d, r8d
0x18001c83a  jns     short loc_18001C844
0x18001c83c  mov     eax, r8d
0x18001c83f  jmp     loc_18001CD09
0x18001c844  mov     r8, [rbp+710h+arg_28]; unsigned __int16 *
0x18001c84b  mov     edx, 104h; unsigned __int64
0x18001c850  lea     rcx, [rbp+710h+FileName]; unsigned __int16 *
0x18001c857  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c85c  test    eax, eax
0x18001c85e  js      loc_18001CD09
0x18001c864  xor     edx, edx; Val
0x18001c866  mov     r8d, 250h; Size
0x18001c86c  lea     rcx, [rbp+710h+FindFileData]; void *
0x18001c870  call    memset_0
0x18001c875  lea     rdx, [rbp+710h+FindFileData]; lpFindFileData
0x18001c879  lea     rcx, [rbp+710h+FileName]; lpFileName
0x18001c880  call    cs:__imp_FindFirstFileW
0x18001c886  mov     r12, rax
0x18001c889  mov     [rsp+810h+var_7B8], rax
0x18001c88e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c892  jz      loc_18001CD07
0x18001c898  test    byte ptr [rbp+710h+FindFileData.dwFileAttributes], 10h
0x18001c89c  jnz     loc_18001CCE9
0x18001c8a2  xor     edx, edx; Val
0x18001c8a4  mov     r8d, 208h; Size
0x18001c8aa  lea     rcx, [rbp+710h+var_260]; void *
0x18001c8b1  call    memset_0
0x18001c8b6  mov     edx, 104h
0x18001c8bb  lea     rcx, [rbp+710h+var_260]
0x18001c8c2  mov     r9d, r13d
0x18001c8c5  lea     rax, [rbp+710h+var_260]
0x18001c8cc  mov     r8, [rbp+710h+arg_20]
0x18001c8d3  sub     r8, rax
0x18001c8d6  lea     rax, [rdx+7FFFFEFAh]
0x18001c8dd  test    rax, rax
0x18001c8e0  jz      short loc_18001C8F8
0x18001c8e2  movzx   eax, word ptr [rcx+r8]
0x18001c8e7  test    ax, ax
0x18001c8ea  jz      short loc_18001C8F8
0x18001c8ec  mov     [rcx], ax
0x18001c8ef  add     rcx, 2
0x18001c8f3  sub     rdx, rbx
0x18001c8f6  jnz     short loc_18001C8D6
0x18001c8f8  test    rdx, rdx
0x18001c8fb  jnz     short loc_18001C907
0x18001c8fd  sub     rcx, 2
0x18001c901  mov     r9d, 8007007Ah
0x18001c907  mov     [rcx], r13w
0x18001c90b  test    r9d, r9d
0x18001c90e  js      loc_18001CCE9
0x18001c914  lea     r8, [rbp+710h+FindFileData.cFileName]; unsigned __int16 *
0x18001c918  mov     edx, 104h; unsigned __int64
0x18001c91d  lea     rcx, [rbp+710h+var_260]; unsigned __int16 *
0x18001c924  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001c929  test    eax, eax
0x18001c92b  js      loc_18001CCE9
0x18001c931  mov     rdi, r13
0x18001c934  mov     [rsp+810h+var_7A8], r13
0x18001c939  mov     r14, r13
0x18001c93c  mov     [rbp+710h+var_790], r13
0x18001c940  mov     r15, r13
0x18001c943  mov     [rbp+710h+var_780], r13
0x18001c947  mov     [rsp+810h+hTemplateFile], r13; hTemplateFile
0x18001c94c  mov     [rsp+810h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001c954  mov     [rsp+810h+dwCreationDisposition], 3; dwCreationDisposition
0x18001c95c  xor     r9d, r9d; lpSecurityAttributes
0x18001c95f  mov     r8d, ebx; dwShareMode
0x18001c962  mov     edx, 80000000h; dwDesiredAccess
0x18001c967  lea     rcx, [rbp+710h+var_260]; lpFileName
0x18001c96e  call    cs:__imp_CreateFileW
0x18001c974  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c978  jnz     short loc_18001C981
0x18001c97a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001c97f  jmp     short loc_18001C98C
0x18001c981  mov     rdi, rax
0x18001c984  mov     [rsp+810h+var_7A8], rax
0x18001c989  mov     eax, r13d
0x18001c98c  test    eax, eax
0x18001c98e  js      loc_18001CC8B
0x18001c994  lea     rdx, [rsp+810h+FileSizeHigh+4]; lpFileSizeHigh
0x18001c999  mov     rcx, rdi; hFile
0x18001c99c  call    cs:__imp_GetFileSize
0x18001c9a2  mov     [rsp+810h+FileSizeHigh], eax
0x18001c9a6  mov     r9, qword ptr [rsp+810h+FileSizeHigh]
0x18001c9ab  shr     r9, 20h; dwMaximumSizeHigh
0x18001c9af  mov     qword ptr [rsp+810h+dwFlagsAndAttributes], r13; lpName
0x18001c9b4  mov     [rsp+810h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18001c9b8  xor     edx, edx; lpFileMappingAttributes
0x18001c9ba  lea     r8d, [rdx+2]; flProtect
0x18001c9be  mov     rcx, rdi; hFile
0x18001c9c1  call    cs:__imp_CreateFileMappingW
0x18001c9c7  mov     r15, rax
0x18001c9ca  mov     [rbp+710h+var_780], rax
0x18001c9ce  test    rax, rax
0x18001c9d1  jnz     short loc_18001C9E1
0x18001c9d3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001c9d8  mov     r12d, eax
0x18001c9db  mov     rbx, [rbp+710h+Size]
0x18001c9df  jmp     short loc_18001CA3A
0x18001c9e1  mov     rbx, qword ptr [rsp+810h+FileSizeHigh]
0x18001c9e6  mov     [rbp+710h+Size], rbx
0x18001c9ea  mov     eax, 4
0x18001c9ef  mov     [rbp+710h+var_770], eax
0x18001c9f2  mov     [rbp+710h+var_778], r13
0x18001c9f6  mov     qword ptr [rsp+810h+dwFlagsAndAttributes], r13; lpBaseAddress
0x18001c9fb  mov     qword ptr [rsp+810h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x18001ca00  xor     r9d, r9d; dwFileOffsetLow
0x18001ca03  xor     r8d, r8d; dwFileOffsetHigh
0x18001ca06  mov     edx, eax; dwDesiredAccess
0x18001ca08  mov     rcx, r15; hFileMappingObject
0x18001ca0b  call    cs:__imp_MapViewOfFileEx
0x18001ca11  mov     r14, rax
0x18001ca14  mov     [rbp+710h+var_790], rax
0x18001ca18  test    rax, rax
0x18001ca1b  jnz     short loc_18001CA37
0x18001ca1d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ca22  mov     r12d, eax
0x18001ca25  mov     rcx, r15; hObject
0x18001ca28  call    cs:__imp_CloseHandle
0x18001ca2e  mov     r15, r13
0x18001ca31  mov     [rbp+710h+var_780], r13
0x18001ca35  jmp     short loc_18001CA3A
0x18001ca37  mov     r12d, r13d
0x18001ca3a  test    r12d, r12d
0x18001ca3d  js      loc_18001CC86
0x18001ca43  cmp     rbx, 100000h
0x18001ca4a  ja      loc_18001CC86
0x18001ca50  mov     r10, [rsp+810h+var_7B0]
0x18001ca55  movzx   r12d, byte ptr [r10+80h]
0x18001ca5d  mov     ebx, dword ptr [rbp+710h+Size]
0x18001ca60  cmp     ebx, 4
0x18001ca63  mov     eax, 1
0x18001ca68  cmovb   r12d, eax
0x18001ca6c  mov     eax, r13d
0x18001ca6f  mov     [rsp+810h+var_7C0], eax
0x18001ca73  test    r12b, r12b
0x18001ca76  jnz     loc_18001CBCA
0x18001ca7c  lea     r13d, [rbx-4]
0x18001ca80  cmp     [r10+0A0h], r13d
0x18001ca87  jnb     loc_18001CB30
0x18001ca8d  mov     rcx, [r10+98h]; Block
0x18001ca94  call    cs:__imp_free
0x18001ca9a  mov     rcx, [rsp+810h+var_7B0]
0x18001ca9f  and     qword ptr [rcx+98h], 0
0x18001caa7  and     dword ptr [rcx+0A0h], 0
0x18001caae  mov     ecx, ebx; Size
0x18001cab0  call    cs:__imp_malloc
0x18001cab6  mov     r10, [rsp+810h+var_7B0]
0x18001cabb  mov     [r10+98h], rax
0x18001cac2  test    rax, rax
0x18001cac5  jnz     short loc_18001CB25
0x18001cac7  xor     r13d, r13d
0x18001caca  mov     ebx, r13d
0x18001cacd  test    r14, r14
0x18001cad0  jz      short loc_18001CAEA
0x18001cad2  mov     rcx, r14; lpBaseAddress
0x18001cad5  call    cs:__imp_UnmapViewOfFile
0x18001cadb  test    eax, eax
0x18001cadd  jnz     short loc_18001CAE6
0x18001cadf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001cae4  mov     ebx, eax
0x18001cae6  mov     [rbp+710h+var_790], r13
0x18001caea  test    r15, r15
0x18001caed  jz      short loc_18001CB09
0x18001caef  mov     rcx, r15; hObject
0x18001caf2  call    cs:__imp_CloseHandle
0x18001caf8  test    eax, eax
0x18001cafa  jnz     short loc_18001CB05
0x18001cafc  test    ebx, ebx
0x18001cafe  js      short loc_18001CB05
0x18001cb00  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001cb05  mov     [rbp+710h+var_780], r13
0x18001cb09  test    rdi, rdi
0x18001cb0c  jz      loc_18001CCDF
0x18001cb12  mov     rcx, rdi; hObject
0x18001cb15  call    cs:__imp_CloseHandle
0x18001cb1b  mov     [rsp+810h+var_7A8], r13
0x18001cb20  jmp     loc_18001CCDF
0x18001cb25  mov     [r10+0A0h], ebx
0x18001cb2c  mov     eax, [rsp+810h+var_7C0]
0x18001cb30  mov     rdx, [r10+88h]
0x18001cb37  mov     r9, [r10+98h]
0x18001cb3e  cmp     qword ptr [r10+70h], 0
0x18001cb43  jz      short loc_18001CB87
0x18001cb45  add     r9, 4
0x18001cb49  mov     ecx, 102h
0x18001cb4e  mov     [rsp+810h+var_7D8], rdx
0x18001cb53  lea     rax, [rsp+810h+var_7C0]
0x18001cb58  mov     [rsp+810h+hTemplateFile], rax
0x18001cb5d  mov     [rsp+810h+dwFlagsAndAttributes], 1000h
0x18001cb65  mov     [rsp+810h+dwCreationDisposition], r13d
0x18001cb6a  mov     r8d, ebx
0x18001cb6d  mov     rdx, r14
0x18001cb70  mov     rax, [r10+70h]
0x18001cb74  call    cs:__guard_dispatch_icall_fptr
0x18001cb7a  mov     ecx, eax
0x18001cb7c  mov     eax, [rsp+810h+var_7C0]
0x18001cb80  mov     r10, [rsp+810h+var_7B0]
0x18001cb85  jmp     short loc_18001CB8C
0x18001cb87  mov     ecx, 0C0000002h
0x18001cb8c  test    ecx, ecx
0x18001cb8e  jnz     short loc_18001CB95
0x18001cb90  cmp     eax, r13d
0x18001cb93  jbe     short loc_18001CB98
0x18001cb95  mov     r12b, 1
0x18001cb98  add     eax, 4
0x18001cb9b  mov     [rsp+810h+var_7C0], eax
0x18001cb9f  mov     rax, [r10+98h]
0x18001cba6  mov     [rax], ebx
0x18001cba8  test    r12b, r12b
0x18001cbab  jnz     short loc_18001CBCA
0x18001cbad  mov     rax, [r10+98h]
0x18001cbb4  mov     qword ptr [rbp+710h+var_750], rax
0x18001cbb8  mov     eax, [rsp+810h+var_7C0]
0x18001cbbc  mov     dword ptr [rbp+710h+var_750+8], eax
0x18001cbbf  movaps  xmm0, [rbp+710h+var_750]
0x18001cbc3  mov     eax, 40h ; '@'
0x18001cbc8  jmp     short loc_18001CBDA
0x18001cbca  mov     qword ptr [rbp+710h+var_740], r14
0x18001cbce  mov     dword ptr [rbp+710h+var_740+8], ebx
0x18001cbd1  movaps  xmm0, [rbp+710h+var_740]
0x18001cbd5  mov     eax, 28h ; '('
0x18001cbda  movdqa  [rbp+710h+var_760], xmm0
0x18001cbdf  lea     rcx, [rax+r10]
0x18001cbe3  mov     r13d, dword ptr [rbp+710h+var_760+8]
0x18001cbe7  lea     rax, [r13+30h]
0x18001cbeb  cmp     rax, 0FFB8h
0x18001cbf1  ja      loc_18001CAC7
0x18001cbf7  mov     rbx, [rcx+8]
0x18001cbfb  lea     r8, [rbp+710h+var_760]
0x18001cbff  lea     rdx, [rbp+710h+var_728]
0x18001cc03  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AViterator@12@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x18001cc08  cmp     [rax], rbx
0x18001cc0b  jnz     loc_18001CAC7
0x18001cc11  xor     edx, edx; Val
0x18001cc13  lea     r8d, [rdx+58h]; Size
0x18001cc17  lea     rcx, [rbp+710h+var_720]; void *
0x18001cc1b  call    memset_0
0x18001cc20  mov     eax, [rsp+810h+var_7A0]
0x18001cc24  mov     [rbp+710h+var_720], ax
0x18001cc28  mov     [rbp+710h+var_710], rsi
0x18001cc2c  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid
0x18001cc33  movdqu  [rbp+710h+var_708], xmm0
0x18001cc38  neg     r12b
0x18001cc3b  sbb     al, al
0x18001cc3d  add     al, 21h ; '!'
0x18001cc3f  mov     [rbp+710h+var_71C], al
0x18001cc42  xor     eax, eax
0x18001cc44  mov     [rbp+710h+var_71A], ax
0x18001cc48  mov     [rbp+710h+var_71B], al
0x18001cc4b  mov     rax, qword ptr [rbp+710h+var_760]
0x18001cc4f  mov     [rbp+710h+var_6D8], rax
0x18001cc53  mov     [rbp+710h+var_6D0], r13d
0x18001cc57  mov     eax, [rsp+810h+var_79C]
0x18001cc5b  mov     [rbp+710h+var_6CC], eax
  ... truncated ...
```
