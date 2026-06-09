# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18002fc74`
- end: `0x1800301eb`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1399`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002f450`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x180006360`
- `0x180016274`
- `0x18002f13c`
- `0x18002fc74`
- `0x180030438`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800300db`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030100`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180030100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ff6f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002ff87`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002ff87`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ff9e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ff9e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002fd6a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002fd6a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fe5b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002fe5b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002fe93`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002fe93`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002ff13`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002ff13`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002febe`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002febe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v7; // r15
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  WCHAR *v11; // rcx
  unsigned __int16 v12; // r9
  __int64 result; // rax
  WCHAR *v14; // rdx
  HANDLE FirstFileW; // r12
  int v16; // esi
  int v17; // edi
  __int64 v18; // rcx
  const unsigned __int16 *v19; // r8
  __int64 v20; // rdx
  WCHAR *v21; // rax
  unsigned __int16 v22; // r9
  WCHAR *v23; // rcx
  void *v24; // rbx
  HANDLE FileW; // rax
  int Error; // eax
  HANDLE FileMappingW; // r13
  int v28; // eax
  size_t v29; // r12
  char v30; // r13
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // eax
  void *v34; // rax
  _DWORD *v35; // rcx
  int v36; // eax
  unsigned int v37; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-ACh]
  HANDLE v39; // [rsp+58h] [rbp-A8h]
  LPVOID v40; // [rsp+60h] [rbp-A0h]
  DWORD FileSizeHigh[2]; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h]
  int v44; // [rsp+7Ch] [rbp-84h]
  int v45; // [rsp+80h] [rbp-80h]
  int v46; // [rsp+84h] [rbp-7Ch]
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v47; // [rsp+88h] [rbp-78h]
  LPVOID v48; // [rsp+90h] [rbp-70h] BYREF
  size_t Size; // [rsp+98h] [rbp-68h]
  HANDLE v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  int v52; // [rsp+B0h] [rbp-50h]
  HANDLE v53; // [rsp+B8h] [rbp-48h]
  char v54[16]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v55[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v56; // [rsp+D4h] [rbp-2Ch]
  char v57; // [rsp+D5h] [rbp-2Bh]
  __int16 v58; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v59; // [rsp+E0h] [rbp-20h]
  __int128 v60; // [rsp+E8h] [rbp-18h]
  LPVOID v61; // [rsp+118h] [rbp+18h]
  int v62; // [rsp+120h] [rbp+20h]
  int v63; // [rsp+124h] [rbp+24h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR v66[264]; // [rsp+590h] [rbp+490h] BYREF

  v45 = a4;
  v46 = a3;
  v7 = this;
  v47 = this;
  memset_0(FileName, 0, 0x208u);
  v8 = 2147483646;
  v9 = a5;
  v10 = 260;
  v11 = FileName;
  do
  {
    if ( !v8 )
      break;
    v12 = *v9;
    if ( !*v9 )
      break;
    ++v9;
    *v11++ = v12;
    --v8;
    --v10;
  }
  while ( v10 );
  result = v10 == 0 ? 0x8007007A : 0;
  v14 = v11 - 1;
  if ( v10 )
    v14 = v11;
  *v14 = 0;
  if ( !v10 )
    return result;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( (int)result < 0 )
    return result;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v39 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  v16 = v44;
  v17 = v44;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(v66, 0, 0x208u);
      v18 = 2147483646;
      v19 = a5;
      v20 = 260;
      v21 = v66;
      do
      {
        if ( !v18 )
          break;
        v22 = *v19;
        if ( !*v19 )
          break;
        ++v19;
        *v21++ = v22;
        --v18;
        --v20;
      }
      while ( v20 );
      v23 = v21 - 1;
      if ( v20 )
        v23 = v21;
      *v23 = 0;
      if ( v20 )
      {
        if ( (int)StringCchCatW(v66, 0x104u, FindFileData.cFileName) >= 0 )
        {
          v24 = 0;
          v53 = 0;
          v40 = 0;
          v48 = 0;
          v50 = 0;
          FileW = CreateFileW(v66, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            Error = ATL::AtlHresultFromLastError();
          }
          else
          {
            v24 = FileW;
            v53 = FileW;
            Error = 0;
          }
          if ( Error < 0 )
          {
LABEL_30:
            ATL::CAtlFileMappingBase::~CAtlFileMappingBase((ATL::CAtlFileMappingBase *)&v48);
            if ( !v24 )
              continue;
LABEL_31:
            CloseHandle(v24);
LABEL_32:
            FirstFileW = v39;
            continue;
          }
          *(_QWORD *)FileSizeHigh = 0;
          FileSizeHigh[0] = GetFileSize(v24, &FileSizeHigh[1]);
          FileMappingW = CreateFileMappingW(v24, 0, 2u, FileSizeHigh[1], FileSizeHigh[0], 0);
          v50 = FileMappingW;
          if ( FileMappingW )
          {
            v29 = *(_QWORD *)FileSizeHigh;
            Size = *(_QWORD *)FileSizeHigh;
            v52 = 4;
            v51 = 0;
            v40 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, *(SIZE_T *)FileSizeHigh, 0);
            v48 = v40;
            if ( v40 )
              goto LABEL_37;
            v38 = ATL::AtlHresultFromLastError();
            CloseHandle(FileMappingW);
            v50 = 0;
            v28 = v38;
          }
          else
          {
            v28 = ATL::AtlHresultFromLastError();
            v29 = Size;
          }
          if ( v28 < 0 )
          {
LABEL_29:
            FirstFileW = v39;
            goto LABEL_30;
          }
LABEL_37:
          if ( v29 > 0x100000 )
            goto LABEL_29;
          v37 = 0;
          if ( (unsigned int)v29 >= 4 )
          {
            v30 = *((_BYTE *)v7 + 104);
            if ( !v30 )
            {
              v33 = v29 - 4;
              v38 = v29 - 4;
              if ( *((_DWORD *)v7 + 34) < (unsigned int)(v29 - 4) )
              {
                free(*((void **)v7 + 16));
                *((_QWORD *)v7 + 16) = 0;
                *((_DWORD *)v7 + 34) = 0;
                v34 = malloc((unsigned int)v29);
                *((_QWORD *)v7 + 16) = v34;
                if ( !v34 )
                  goto LABEL_47;
                *((_DWORD *)v7 + 34) = v29;
                v33 = v38;
              }
              v35 = (_DWORD *)*((_QWORD *)v7 + 16);
              if ( !*((_QWORD *)v7 + 11)
                || (v36 = (*((__int64 (__fastcall **)(__int64, LPVOID, _QWORD, _DWORD *, unsigned int, int, unsigned int *, _QWORD))v7
                           + 11))(
                            258,
                            v40,
                            (unsigned int)v29,
                            v35 + 1,
                            v33,
                            4096,
                            &v37,
                            *((_QWORD *)v7 + 14)),
                    v35 = (_DWORD *)*((_QWORD *)v7 + 16),
                    v36)
                || v37 > v38 )
              {
                v30 = 1;
              }
              v37 += 4;
              *v35 = v29;
              if ( !v30 )
              {
                LODWORD(v29) = v37;
                v40 = (LPVOID)*((_QWORD *)v7 + 16);
                v42 = v40;
                v44 = v17;
                v31 = 56;
                v32 = v37;
LABEL_41:
                v43 = v29;
                if ( (unsigned __int64)(v32 + 48) <= 0xFFB8 )
                {
                  if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                                    (char *)v7 + v31,
                                    v54,
                                    &v42) == *(_QWORD *)((char *)v7 + v31) )
                  {
                    memset_0(v55, 0, 0x58u);
                    v55[0] = v45;
                    v59 = a2;
                    v60 = *(_OWORD *)PerfTrackMetadataGuid;
                    v56 = 33 - (v30 != 0);
                    v58 = 0;
                    v57 = 0;
                    v61 = v40;
                    v62 = v29;
                    v63 = v46;
                    v7 = v47;
                    (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v47 + 2) + 192LL))(
                      *((_QWORD *)v47 + 2),
                      v55,
                      0,
                      0);
                  }
                  else
                  {
                    v7 = v47;
                  }
                }
LABEL_47:
                ATL::CAtlFileMappingBase::~CAtlFileMappingBase((ATL::CAtlFileMappingBase *)&v48);
                if ( !v24 )
                  goto LABEL_32;
                goto LABEL_31;
              }
            }
          }
          else
          {
            v30 = 1;
          }
          v42 = v40;
          v44 = v16;
          v31 = 40;
          v32 = (unsigned int)v29;
          goto LABEL_41;
        }
      }
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  FindClose(FirstFileW);
  return 0;
}

```

## disassembly

```asm
0x18002fc74  push    rbp
0x18002fc76  push    rbx
0x18002fc77  push    rsi
0x18002fc78  push    rdi
0x18002fc79  push    r12
0x18002fc7b  push    r13
0x18002fc7d  push    r14
0x18002fc7f  push    r15
0x18002fc81  lea     rbp, [rsp-6B8h]
0x18002fc89  sub     rsp, 7B8h
0x18002fc90  mov     rax, cs:__security_cookie
0x18002fc97  xor     rax, rsp
0x18002fc9a  mov     [rbp+6F0h+var_50], rax
0x18002fca1  mov     [rbp+6F0h+var_770], r9d
0x18002fca5  mov     [rbp+6F0h+var_76C], r8d
0x18002fca9  mov     r14, rdx
0x18002fcac  mov     r15, rcx
0x18002fcaf  mov     [rbp+6F0h+var_768], rcx
0x18002fcb3  mov     rbx, [rbp+6F0h+arg_28]
0x18002fcba  xor     edx, edx; Val
0x18002fcbc  mov     r8d, 208h; Size
0x18002fcc2  lea     rcx, [rbp+6F0h+FileName]; void *
0x18002fcc9  call    memset_0
0x18002fcce  mov     eax, 7FFFFFFEh
0x18002fcd3  mov     rdx, [rbp+6F0h+arg_20]
0x18002fcda  mov     r8d, 104h
0x18002fce0  lea     rcx, [rbp+6F0h+FileName]
0x18002fce7  xor     r13d, r13d
0x18002fcea  test    rax, rax
0x18002fced  jz      short loc_18002FD0E
0x18002fcef  movzx   r9d, word ptr [rdx]
0x18002fcf3  test    r9w, r9w
0x18002fcf7  jz      short loc_18002FD0E
0x18002fcf9  add     rdx, 2
0x18002fcfd  mov     [rcx], r9w
0x18002fd01  add     rcx, 2
0x18002fd05  dec     rax
0x18002fd08  sub     r8, 1
0x18002fd0c  jnz     short loc_18002FCEA
0x18002fd0e  mov     rax, r8
0x18002fd11  neg     rax
0x18002fd14  sbb     eax, eax
0x18002fd16  not     eax
0x18002fd18  and     eax, 8007007Ah
0x18002fd1d  lea     rdx, [rcx-2]
0x18002fd21  test    r8, r8
0x18002fd24  cmovnz  rdx, rcx
0x18002fd28  mov     [rdx], r13w
0x18002fd2c  jz      loc_18002FFAC
0x18002fd32  mov     r8, rbx; unsigned __int16 *
0x18002fd35  mov     edx, 104h; unsigned __int64
0x18002fd3a  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18002fd41  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fd46  test    eax, eax
0x18002fd48  js      loc_18002FFAC
0x18002fd4e  xor     edx, edx; Val
0x18002fd50  mov     r8d, 250h; Size
0x18002fd56  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x18002fd5a  call    memset_0
0x18002fd5f  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002fd63  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x18002fd6a  call    cs:__imp_FindFirstFileW
0x18002fd71  nop     dword ptr [rax+rax+00h]
0x18002fd76  mov     r12, rax
0x18002fd79  mov     [rsp+7F0h+var_798], rax
0x18002fd7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fd82  jz      loc_18002FFAA
0x18002fd88  mov     esi, [rsp+7F0h+var_774]
0x18002fd8c  mov     edi, [rsp+7F0h+var_774]
0x18002fd90  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x18002fd94  jnz     loc_18002FF80
0x18002fd9a  xor     edx, edx; Val
0x18002fd9c  mov     r8d, 208h; Size
0x18002fda2  lea     rcx, [rbp+6F0h+var_260]; void *
0x18002fda9  call    memset_0
0x18002fdae  mov     ecx, 7FFFFFFEh
0x18002fdb3  mov     r8, [rbp+6F0h+arg_20]
0x18002fdba  mov     edx, 104h
0x18002fdbf  lea     rax, [rbp+6F0h+var_260]
0x18002fdc6  test    rcx, rcx
0x18002fdc9  jz      short loc_18002FDEA
0x18002fdcb  movzx   r9d, word ptr [r8]
0x18002fdcf  test    r9w, r9w
0x18002fdd3  jz      short loc_18002FDEA
0x18002fdd5  add     r8, 2
0x18002fdd9  mov     [rax], r9w
0x18002fddd  add     rax, 2
0x18002fde1  dec     rcx
0x18002fde4  sub     rdx, 1
0x18002fde8  jnz     short loc_18002FDC6
0x18002fdea  lea     rcx, [rax-2]
0x18002fdee  test    rdx, rdx
0x18002fdf1  cmovnz  rcx, rax
0x18002fdf5  mov     [rcx], r13w
0x18002fdf9  jz      loc_18002FF80
0x18002fdff  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002fe03  mov     edx, 104h; unsigned __int64
0x18002fe08  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18002fe0f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002fe14  test    eax, eax
0x18002fe16  js      loc_18002FF80
0x18002fe1c  mov     rbx, r13
0x18002fe1f  mov     [rbp+6F0h+var_738], rbx
0x18002fe23  mov     rax, r13
0x18002fe26  mov     [rsp+7F0h+var_790], rax
0x18002fe2b  mov     [rbp+6F0h+var_760], rax
0x18002fe2f  mov     [rbp+6F0h+var_750], r13
0x18002fe33  mov     [rsp+7F0h+hTemplateFile], r13; hTemplateFile
0x18002fe38  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002fe40  mov     [rsp+7F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002fe48  xor     r9d, r9d; lpSecurityAttributes
0x18002fe4b  mov     edx, 80000000h; dwDesiredAccess
0x18002fe50  lea     r8d, [r9+1]; dwShareMode
0x18002fe54  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x18002fe5b  call    cs:__imp_CreateFileW
0x18002fe62  nop     dword ptr [rax+rax+00h]
0x18002fe67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002fe6b  jnz     short loc_18002FE74
0x18002fe6d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002fe72  jmp     short loc_18002FE7E
0x18002fe74  mov     rbx, rax
0x18002fe77  mov     [rbp+6F0h+var_738], rax
0x18002fe7b  mov     eax, r13d
0x18002fe7e  test    eax, eax
0x18002fe80  js      loc_18002FF5D
0x18002fe86  mov     qword ptr [rsp+7F0h+FileSizeHigh], r13
0x18002fe8b  lea     rdx, [rsp+7F0h+FileSizeHigh+4]; lpFileSizeHigh
0x18002fe90  mov     rcx, rbx; hFile
0x18002fe93  call    cs:__imp_GetFileSize
0x18002fe9a  nop     dword ptr [rax+rax+00h]
0x18002fe9f  mov     [rsp+7F0h+FileSizeHigh], eax
0x18002fea3  mov     r9, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002fea8  shr     r9, 20h; dwMaximumSizeHigh
0x18002feac  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], r13; lpName
0x18002feb1  mov     [rsp+7F0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18002feb5  xor     edx, edx; lpFileMappingAttributes
0x18002feb7  lea     r8d, [rdx+2]; flProtect
0x18002febb  mov     rcx, rbx; hFile
0x18002febe  call    cs:__imp_CreateFileMappingW
0x18002fec5  nop     dword ptr [rax+rax+00h]
0x18002feca  mov     r13, rax
0x18002fecd  mov     [rbp+6F0h+var_750], rax
0x18002fed1  test    rax, rax
0x18002fed4  jnz     short loc_18002FEE1
0x18002fed6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002fedb  mov     r12, [rbp+6F0h+Size]
0x18002fedf  jmp     short loc_18002FF54
0x18002fee1  mov     r12, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002fee6  mov     [rbp+6F0h+Size], r12
0x18002feea  mov     eax, 4
0x18002feef  mov     [rbp+6F0h+var_740], eax
0x18002fef2  mov     [rbp+6F0h+var_748], 0
0x18002fefa  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], 0; lpBaseAddress
0x18002ff03  mov     qword ptr [rsp+7F0h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x18002ff08  xor     r9d, r9d; dwFileOffsetLow
0x18002ff0b  xor     r8d, r8d; dwFileOffsetHigh
0x18002ff0e  mov     edx, eax; dwDesiredAccess
0x18002ff10  mov     rcx, r13; hFileMappingObject
0x18002ff13  call    cs:__imp_MapViewOfFileEx
0x18002ff1a  nop     dword ptr [rax+rax+00h]
0x18002ff1f  mov     [rsp+7F0h+var_790], rax
0x18002ff24  mov     [rbp+6F0h+var_760], rax
0x18002ff28  test    rax, rax
0x18002ff2b  jnz     loc_18002FFD0
0x18002ff31  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002ff36  mov     [rsp+7F0h+var_79C], eax
0x18002ff3a  mov     rcx, r13; hObject
0x18002ff3d  call    cs:__imp_CloseHandle
0x18002ff44  nop     dword ptr [rax+rax+00h]
0x18002ff49  xor     r13d, r13d
0x18002ff4c  mov     [rbp+6F0h+var_750], r13
0x18002ff50  mov     eax, [rsp+7F0h+var_79C]
0x18002ff54  test    eax, eax
0x18002ff56  jns     short loc_18002FFD3
0x18002ff58  mov     r12, [rsp+7F0h+var_798]
0x18002ff5d  lea     rcx, [rbp+6F0h+var_760]; this
0x18002ff61  call    ??1CAtlFileMappingBase@ATL@@QEAA@XZ; ATL::CAtlFileMappingBase::~CAtlFileMappingBase(void)
0x18002ff66  nop
0x18002ff67  test    rbx, rbx
0x18002ff6a  jz      short loc_18002FF80
0x18002ff6c  mov     rcx, rbx; hObject
0x18002ff6f  call    cs:__imp_CloseHandle
0x18002ff76  nop     dword ptr [rax+rax+00h]
0x18002ff7b  mov     r12, [rsp+7F0h+var_798]
0x18002ff80  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002ff84  mov     rcx, r12; hFindFile
0x18002ff87  call    cs:__imp_FindNextFileW
0x18002ff8e  nop     dword ptr [rax+rax+00h]
0x18002ff93  test    eax, eax
0x18002ff95  jnz     loc_18002FD90
0x18002ff9b  mov     rcx, r12; hFindFile
0x18002ff9e  call    cs:__imp_FindClose
0x18002ffa5  nop     dword ptr [rax+rax+00h]
0x18002ffaa  xor     eax, eax
0x18002ffac  mov     rcx, [rbp+6F0h+var_50]
0x18002ffb3  xor     rcx, rsp; StackCookie
0x18002ffb6  call    __security_check_cookie
0x18002ffbb  add     rsp, 7B8h
0x18002ffc2  pop     r15
0x18002ffc4  pop     r14
0x18002ffc6  pop     r13
0x18002ffc8  pop     r12
0x18002ffca  pop     rdi
0x18002ffcb  pop     rsi
0x18002ffcc  pop     rbx
0x18002ffcd  pop     rbp
0x18002ffce  retn
0x18002ffd0  xor     r13d, r13d
0x18002ffd3  cmp     r12, 100000h
0x18002ffda  ja      loc_18002FF58
0x18002ffe0  mov     [rsp+7F0h+var_7A0], 0
0x18002ffe8  cmp     r12d, 4
0x18002ffec  jnb     loc_1800300B5
0x18002fff2  mov     r13b, 1
0x18002fff5  mov     rax, [rsp+7F0h+var_790]
0x18002fffa  mov     [rsp+7F0h+var_780], rax
0x18002ffff  mov     [rsp+7F0h+var_774], esi
0x180030003  mov     ecx, 28h ; '('
0x180030008  mov     eax, r12d
0x18003000b  mov     [rsp+7F0h+var_778], r12d
0x180030010  add     rax, 30h ; '0'
0x180030014  cmp     rax, 0FFB8h
0x18003001a  ja      loc_180030118
0x180030020  add     r15, rcx
0x180030023  lea     r8, [rsp+7F0h+var_780]
0x180030028  lea     rdx, [rbp+6F0h+var_730]
0x18003002c  mov     rcx, r15
0x18003002f  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@2@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x180030034  mov     rcx, [r15]
0x180030037  cmp     [rax], rcx
0x18003003a  jnz     loc_1800301D5
0x180030040  xor     edx, edx; Val
0x180030042  lea     r8d, [rdx+58h]; Size
0x180030046  lea     rcx, [rbp+6F0h+var_720]; void *
0x18003004a  call    memset_0
0x18003004f  mov     eax, [rbp+6F0h+var_770]
0x180030052  mov     [rbp+6F0h+var_720], ax
0x180030056  mov     [rbp+6F0h+var_710], r14
0x18003005a  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid
0x180030061  movdqu  [rbp+6F0h+var_708], xmm0
0x180030066  neg     r13b
0x180030069  sbb     al, al
0x18003006b  add     al, 21h ; '!'
0x18003006d  mov     [rbp+6F0h+var_71C], al
0x180030070  xor     r13d, r13d
0x180030073  mov     [rbp+6F0h+var_71A], r13w
0x180030078  mov     [rbp+6F0h+var_71B], r13b
0x18003007c  mov     rax, [rsp+7F0h+var_790]
0x180030081  mov     [rbp+6F0h+var_6D8], rax
0x180030085  mov     [rbp+6F0h+var_6D0], r12d
0x180030089  mov     eax, [rbp+6F0h+var_76C]
0x18003008c  mov     [rbp+6F0h+var_6CC], eax
0x18003008f  mov     r15, [rbp+6F0h+var_768]
0x180030093  mov     rcx, [r15+10h]
0x180030097  mov     rax, [rcx]
0x18003009a  xor     r9d, r9d
0x18003009d  xor     r8d, r8d
0x1800300a0  lea     rdx, [rbp+6F0h+var_720]
0x1800300a4  mov     rax, [rax+0C0h]
0x1800300ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300b0  jmp     loc_1800301DC
0x1800300b5  mov     r13b, [r15+68h]
0x1800300b9  test    r13b, r13b
0x1800300bc  jnz     loc_18002FFF5
0x1800300c2  lea     eax, [r12-4]
0x1800300c7  mov     [rsp+7F0h+var_79C], eax
0x1800300cb  cmp     [r15+88h], eax
0x1800300d2  jnb     short loc_18003013E
0x1800300d4  mov     rcx, [r15+80h]; Block
0x1800300db  call    cs:__imp_free
0x1800300e2  nop     dword ptr [rax+rax+00h]
0x1800300e7  mov     qword ptr [r15+80h], 0
0x1800300f2  mov     dword ptr [r15+88h], 0
0x1800300fd  mov     ecx, r12d; Size
0x180030100  call    cs:__imp_malloc
0x180030107  nop     dword ptr [rax+rax+00h]
0x18003010c  mov     [r15+80h], rax
0x180030113  test    rax, rax
0x180030116  jnz     short loc_180030133
0x180030118  lea     rcx, [rbp+6F0h+var_760]; this
0x18003011c  call    ??1CAtlFileMappingBase@ATL@@QEAA@XZ; ATL::CAtlFileMappingBase::~CAtlFileMappingBase(void)
0x180030121  nop
0x180030122  xor     r13d, r13d
0x180030125  test    rbx, rbx
0x180030128  jnz     loc_18002FF6C
0x18003012e  jmp     loc_18002FF7B
0x180030133  mov     [r15+88h], r12d
0x18003013a  mov     eax, [rsp+7F0h+var_79C]
0x18003013e  mov     rcx, [r15+80h]
0x180030145  cmp     qword ptr [r15+58h], 0
0x18003014a  jz      short loc_18003019A
0x18003014c  lea     r9, [rcx+4]
0x180030150  mov     ecx, 102h
0x180030155  mov     rdx, [r15+70h]
0x180030159  mov     [rsp+7F0h+var_7B8], rdx
0x18003015e  lea     rdx, [rsp+7F0h+var_7A0]
0x180030163  mov     [rsp+7F0h+hTemplateFile], rdx
0x180030168  mov     [rsp+7F0h+dwFlagsAndAttributes], 1000h
0x180030170  mov     [rsp+7F0h+dwCreationDisposition], eax
0x180030174  mov     r8d, r12d
  ... truncated ...
```
