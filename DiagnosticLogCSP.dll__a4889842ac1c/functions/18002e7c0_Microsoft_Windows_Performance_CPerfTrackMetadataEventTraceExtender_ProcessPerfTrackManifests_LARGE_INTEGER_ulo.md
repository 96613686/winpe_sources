# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18002e7c0`
- end: `0x18002ed5d`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1437`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002e020`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x1800063e0`
- `0x180015710`
- `0x18002e7c0`
- `0x18002ef78`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002eadb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002eadb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002eafe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002eafe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ea62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002eb5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ed37`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002eb70`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002eb70`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002eb81`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002eb81`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002e8b4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002e8b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e997`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e997`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002e9c9`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002e9c9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002eb24`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002ed1c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002eb24`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002ed1c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002ea44`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x18002ea44`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002e9ee`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002e9ee`

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
  __int64 v7; // rax
  const unsigned __int16 *v8; // rdx
  __int64 v9; // r8
  WCHAR *v10; // rcx
  signed int v11; // r12d
  unsigned __int16 v12; // r9
  __int64 result; // rax
  WCHAR *v14; // rdx
  HANDLE FirstFileW; // rax
  int v16; // edi
  int v17; // esi
  void *v18; // rbx
  __int64 v19; // rcx
  const unsigned __int16 *v20; // r8
  __int64 v21; // rdx
  WCHAR *v22; // rax
  unsigned __int16 v23; // r9
  WCHAR *v24; // rcx
  void *v25; // rbx
  const void *v26; // r13
  HANDLE FileMappingW; // r15
  HANDLE FileW; // rax
  signed int Error; // eax
  signed int v30; // eax
  const void *v31; // rcx
  size_t v32; // r12
  const void *v33; // rax
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v34; // r10
  unsigned int v35; // eax
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v36; // rcx
  void *v37; // rax
  bool v38; // zf
  _DWORD *v39; // rcx
  int v40; // eax
  char v41; // al
  __int64 v42; // rcx
  __int64 v43; // rax
  signed int v44; // r15d
  char v45; // [rsp+50h] [rbp-B0h]
  unsigned int v46; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v47; // [rsp+58h] [rbp-A8h]
  DWORD FileSizeHigh[2]; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v49; // [rsp+68h] [rbp-98h]
  HANDLE v50; // [rsp+70h] [rbp-90h]
  size_t v51; // [rsp+78h] [rbp-88h] BYREF
  int v52; // [rsp+80h] [rbp-80h]
  int v53; // [rsp+84h] [rbp-7Ch]
  int v54; // [rsp+88h] [rbp-78h]
  int v55; // [rsp+8Ch] [rbp-74h]
  HANDLE hObject; // [rsp+90h] [rbp-70h]
  HANDLE v57; // [rsp+98h] [rbp-68h]
  const void *v58; // [rsp+A0h] [rbp-60h]
  size_t Size; // [rsp+A8h] [rbp-58h]
  HANDLE v60; // [rsp+B0h] [rbp-50h]
  __int64 v61; // [rsp+B8h] [rbp-48h]
  int v62; // [rsp+C0h] [rbp-40h]
  _BYTE v63[8]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v64[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v65; // [rsp+D4h] [rbp-2Ch]
  char v66; // [rsp+D5h] [rbp-2Bh]
  __int16 v67; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v68; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+E8h] [rbp-18h]
  size_t v70; // [rsp+118h] [rbp+18h]
  int v71; // [rsp+120h] [rbp+20h]
  int v72; // [rsp+124h] [rbp+24h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR v75[264]; // [rsp+590h] [rbp+490h] BYREF

  v54 = a4;
  v55 = a3;
  v49 = this;
  memset_0(FileName, 0, 0x208u);
  v7 = 2147483646;
  v8 = a5;
  v9 = 260;
  v10 = FileName;
  v11 = 0;
  do
  {
    if ( !v7 )
      break;
    v12 = *v8;
    if ( !*v8 )
      break;
    ++v8;
    *v10++ = v12;
    --v7;
    --v9;
  }
  while ( v9 );
  result = v9 == 0 ? 0x8007007A : 0;
  v14 = v10 - 1;
  if ( v9 )
    v14 = v10;
  *v14 = 0;
  if ( !v9 )
    return result;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( (int)result < 0 )
    return result;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v50 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  v16 = v53;
  v17 = v53;
  v18 = FirstFileW;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(v75, 0, 0x208u);
      v19 = 2147483646;
      v20 = a5;
      v21 = 260;
      v22 = v75;
      do
      {
        if ( !v19 )
          break;
        v23 = *v20;
        if ( !*v20 )
          break;
        ++v20;
        *v22++ = v23;
        --v19;
        --v21;
      }
      while ( v21 );
      v24 = v22 - 1;
      if ( v21 )
        v24 = v22;
      *v24 = 0;
      if ( v21 )
      {
        if ( (int)StringCchCatW(v75, 0x104u, FindFileData.cFileName) >= 0 )
        {
          v25 = 0;
          v57 = 0;
          v26 = 0;
          v58 = 0;
          FileMappingW = 0;
          FileW = CreateFileW(v75, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            Error = ATL::AtlHresultFromLastError();
          }
          else
          {
            v25 = FileW;
            v57 = FileW;
            Error = 0;
          }
          if ( Error < 0 )
          {
            v31 = 0;
            goto LABEL_75;
          }
          *(_QWORD *)FileSizeHigh = 0;
          FileSizeHigh[0] = GetFileSize(v25, &FileSizeHigh[1]);
          FileMappingW = CreateFileMappingW(v25, 0, 2u, FileSizeHigh[1], FileSizeHigh[0], 0);
          hObject = FileMappingW;
          v60 = FileMappingW;
          if ( FileMappingW )
          {
            v32 = *(_QWORD *)FileSizeHigh;
            Size = *(_QWORD *)FileSizeHigh;
            v62 = 4;
            v61 = 0;
            v33 = MapViewOfFileEx(FileMappingW, 4u, 0, 0, *(SIZE_T *)FileSizeHigh, 0);
            v26 = v33;
            v58 = v33;
            if ( v33 )
            {
              v31 = v33;
              goto LABEL_31;
            }
            v47 = ATL::AtlHresultFromLastError();
            CloseHandle(FileMappingW);
            FileMappingW = 0;
            hObject = 0;
            v60 = 0;
            v31 = 0;
            v30 = v47;
          }
          else
          {
            v30 = ATL::AtlHresultFromLastError();
            v31 = 0;
            v32 = Size;
          }
          if ( v30 < 0 )
          {
LABEL_29:
            v11 = 0;
LABEL_75:
            v38 = v31 == 0;
LABEL_38:
            if ( !v38 && !UnmapViewOfFile(v26) )
              v11 = ATL::AtlHresultFromLastError();
            if ( FileMappingW && !CloseHandle(FileMappingW) && v11 >= 0 )
              ATL::AtlHresultFromLastError();
            v11 = 0;
LABEL_46:
            if ( v25 )
              CloseHandle(v25);
            v18 = v50;
            continue;
          }
LABEL_31:
          if ( v32 > 0x100000 )
            goto LABEL_29;
          v46 = 0;
          v34 = v49;
          if ( (unsigned int)v32 >= 4 )
          {
            v45 = *((_BYTE *)v49 + 104);
            if ( v45 )
            {
              v45 = *((_BYTE *)v49 + 104);
            }
            else
            {
              v35 = v32 - 4;
              v47 = v32 - 4;
              if ( *((_DWORD *)v49 + 34) < (unsigned int)(v32 - 4) )
              {
                free(*((void **)v49 + 16));
                v36 = v49;
                *((_QWORD *)v49 + 16) = 0;
                *((_DWORD *)v36 + 34) = 0;
                v37 = malloc((unsigned int)v32);
                v34 = v49;
                *((_QWORD *)v49 + 16) = v37;
                if ( !v37 )
                {
LABEL_37:
                  v11 = 0;
                  v38 = v26 == 0;
                  goto LABEL_38;
                }
                *((_DWORD *)v34 + 34) = v32;
                v35 = v47;
              }
              v39 = (_DWORD *)*((_QWORD *)v34 + 16);
              if ( !*((_QWORD *)v34 + 11)
                || (v40 = (*((__int64 (__fastcall **)(__int64, const void *, _QWORD, _DWORD *, unsigned int, int, unsigned int *, _QWORD))v34
                           + 11))(
                            258,
                            v26,
                            (unsigned int)v32,
                            v39 + 1,
                            v35,
                            4096,
                            &v46,
                            *((_QWORD *)v34 + 14)),
                    v34 = v49,
                    v39 = (_DWORD *)*((_QWORD *)v49 + 16),
                    v40)
                || v46 > v47 )
              {
                v41 = 1;
                v45 = 1;
              }
              else
              {
                v41 = 0;
              }
              v46 += 4;
              *v39 = v32;
              if ( !v41 )
              {
                LODWORD(v32) = v46;
                *(_QWORD *)FileSizeHigh = *((_QWORD *)v34 + 16);
                v51 = *(_QWORD *)FileSizeHigh;
                v53 = v17;
                v42 = 56;
                v43 = v46;
                goto LABEL_63;
              }
            }
          }
          else
          {
            v45 = 1;
          }
          *(_QWORD *)FileSizeHigh = v26;
          v51 = (size_t)v26;
          v53 = v16;
          v42 = 40;
          v43 = (unsigned int)v32;
LABEL_63:
          v52 = v32;
          if ( (unsigned __int64)(v43 + 48) <= 0xFFB8 )
          {
            if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                              (char *)v34 + v42,
                              v63,
                              &v51) == *(_QWORD *)((char *)v34 + v42) )
            {
              memset_0(v64, 0, 0x58u);
              v64[0] = v54;
              v68 = a2;
              v69 = *(_OWORD *)PerfTrackMetadataGuid;
              v65 = 33 - (v45 != 0);
              v67 = 0;
              v66 = 0;
              v70 = *(_QWORD *)FileSizeHigh;
              v71 = v32;
              v72 = v55;
              (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v49 + 2) + 192LL))(
                *((_QWORD *)v49 + 2),
                v64,
                0,
                0);
            }
            v11 = 0;
            v44 = 0;
            if ( v26 && !UnmapViewOfFile(v26) )
              v44 = ATL::AtlHresultFromLastError();
            if ( hObject && !CloseHandle(hObject) && v44 >= 0 )
              ATL::AtlHresultFromLastError();
            goto LABEL_46;
          }
          goto LABEL_37;
        }
      }
    }
  }
  while ( FindNextFileW(v18, &FindFileData) );
  FindClose(v18);
  return 0;
}

```

## disassembly

```asm
0x18002e7c0  push    rbp
0x18002e7c2  push    rbx
0x18002e7c3  push    rsi
0x18002e7c4  push    rdi
0x18002e7c5  push    r12
0x18002e7c7  push    r13
0x18002e7c9  push    r14
0x18002e7cb  push    r15
0x18002e7cd  lea     rbp, [rsp-6B8h]
0x18002e7d5  sub     rsp, 7B8h
0x18002e7dc  mov     rax, cs:__security_cookie
0x18002e7e3  xor     rax, rsp
0x18002e7e6  mov     [rbp+6F0h+var_50], rax
0x18002e7ed  mov     [rbp+6F0h+var_768], r9d
0x18002e7f1  mov     [rbp+6F0h+var_764], r8d
0x18002e7f5  mov     r14, rdx
0x18002e7f8  mov     [rsp+7F0h+var_788], rcx
0x18002e7fd  mov     rbx, [rbp+6F0h+arg_28]
0x18002e804  xor     edx, edx; Val
0x18002e806  mov     r8d, 208h; Size
0x18002e80c  lea     rcx, [rbp+6F0h+FileName]; void *
0x18002e813  call    memset_0
0x18002e818  mov     eax, 7FFFFFFEh
0x18002e81d  mov     rdx, [rbp+6F0h+arg_20]
0x18002e824  mov     r8d, 104h
0x18002e82a  lea     rcx, [rbp+6F0h+FileName]
0x18002e831  xor     r12d, r12d
0x18002e834  test    rax, rax
0x18002e837  jz      short loc_18002E858
0x18002e839  movzx   r9d, word ptr [rdx]
0x18002e83d  test    r9w, r9w
0x18002e841  jz      short loc_18002E858
0x18002e843  add     rdx, 2
0x18002e847  mov     [rcx], r9w
0x18002e84b  add     rcx, 2
0x18002e84f  dec     rax
0x18002e852  sub     r8, 1
0x18002e856  jnz     short loc_18002E834
0x18002e858  mov     rax, r8
0x18002e85b  neg     rax
0x18002e85e  sbb     eax, eax
0x18002e860  not     eax
0x18002e862  and     eax, 8007007Ah
0x18002e867  lea     rdx, [rcx-2]
0x18002e86b  test    r8, r8
0x18002e86e  cmovnz  rdx, rcx
0x18002e872  mov     [rdx], r12w
0x18002e876  jz      loc_18002EB89
0x18002e87c  mov     r8, rbx; unsigned __int16 *
0x18002e87f  mov     edx, 104h; unsigned __int64
0x18002e884  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18002e88b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e890  test    eax, eax
0x18002e892  js      loc_18002EB89
0x18002e898  xor     edx, edx; Val
0x18002e89a  mov     r8d, 250h; Size
0x18002e8a0  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x18002e8a4  call    memset_0
0x18002e8a9  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002e8ad  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x18002e8b4  call    cs:__imp_FindFirstFileW
0x18002e8ba  mov     [rsp+7F0h+var_780], rax
0x18002e8bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e8c3  jz      loc_18002EB87
0x18002e8c9  mov     edi, [rbp+6F0h+var_76C]
0x18002e8cc  mov     esi, [rbp+6F0h+var_76C]
0x18002e8cf  mov     rbx, rax
0x18002e8d2  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x18002e8d6  jnz     loc_18002EB69
0x18002e8dc  xor     edx, edx; Val
0x18002e8de  mov     r8d, 208h; Size
0x18002e8e4  lea     rcx, [rbp+6F0h+var_260]; void *
0x18002e8eb  call    memset_0
0x18002e8f0  mov     ecx, 7FFFFFFEh
0x18002e8f5  mov     r8, [rbp+6F0h+arg_20]
0x18002e8fc  mov     edx, 104h
0x18002e901  lea     rax, [rbp+6F0h+var_260]
0x18002e908  test    rcx, rcx
0x18002e90b  jz      short loc_18002E92C
0x18002e90d  movzx   r9d, word ptr [r8]
0x18002e911  test    r9w, r9w
0x18002e915  jz      short loc_18002E92C
0x18002e917  add     r8, 2
0x18002e91b  mov     [rax], r9w
0x18002e91f  add     rax, 2
0x18002e923  dec     rcx
0x18002e926  sub     rdx, 1
0x18002e92a  jnz     short loc_18002E908
0x18002e92c  lea     rcx, [rax-2]
0x18002e930  test    rdx, rdx
0x18002e933  cmovnz  rcx, rax
0x18002e937  mov     [rcx], r12w
0x18002e93b  jz      loc_18002EB69
0x18002e941  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x18002e945  mov     edx, 104h; unsigned __int64
0x18002e94a  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18002e951  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e956  test    eax, eax
0x18002e958  js      loc_18002EB69
0x18002e95e  mov     rbx, r12
0x18002e961  mov     [rbp+6F0h+var_758], rbx
0x18002e965  mov     r13, r12
0x18002e968  mov     [rbp+6F0h+var_750], r12
0x18002e96c  mov     r15, r12
0x18002e96f  mov     [rsp+7F0h+hTemplateFile], r12; hTemplateFile
0x18002e974  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002e97c  mov     [rsp+7F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18002e984  xor     r9d, r9d; lpSecurityAttributes
0x18002e987  mov     edx, 80000000h; dwDesiredAccess
0x18002e98c  lea     r8d, [r9+1]; dwShareMode
0x18002e990  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x18002e997  call    cs:__imp_CreateFileW
0x18002e99d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e9a1  jnz     short loc_18002E9AA
0x18002e9a3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002e9a8  jmp     short loc_18002E9B4
0x18002e9aa  mov     rbx, rax
0x18002e9ad  mov     [rbp+6F0h+var_758], rax
0x18002e9b1  mov     eax, r12d
0x18002e9b4  test    eax, eax
0x18002e9b6  js      loc_18002ED51
0x18002e9bc  mov     qword ptr [rsp+7F0h+FileSizeHigh], r12
0x18002e9c1  lea     rdx, [rsp+7F0h+FileSizeHigh+4]; lpFileSizeHigh
0x18002e9c6  mov     rcx, rbx; hFile
0x18002e9c9  call    cs:__imp_GetFileSize
0x18002e9cf  mov     [rsp+7F0h+FileSizeHigh], eax
0x18002e9d3  mov     r9, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002e9d8  shr     r9, 20h; dwMaximumSizeHigh
0x18002e9dc  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], r12; lpName
0x18002e9e1  mov     [rsp+7F0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18002e9e5  xor     edx, edx; lpFileMappingAttributes
0x18002e9e7  lea     r8d, [rdx+2]; flProtect
0x18002e9eb  mov     rcx, rbx; hFile
0x18002e9ee  call    cs:__imp_CreateFileMappingW
0x18002e9f4  mov     r15, rax
0x18002e9f7  mov     [rbp+6F0h+hObject], rax
0x18002e9fb  mov     [rbp+6F0h+var_740], rax
0x18002e9ff  test    rax, rax
0x18002ea02  jnz     short loc_18002EA12
0x18002ea04  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002ea09  mov     rcx, r12
0x18002ea0c  mov     r12, [rbp+6F0h+Size]
0x18002ea10  jmp     short loc_18002EA79
0x18002ea12  mov     r12, qword ptr [rsp+7F0h+FileSizeHigh]
0x18002ea17  mov     [rbp+6F0h+Size], r12
0x18002ea1b  mov     eax, 4
0x18002ea20  mov     [rbp+6F0h+var_730], eax
0x18002ea23  mov     [rbp+6F0h+var_738], 0
0x18002ea2b  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], 0; lpBaseAddress
0x18002ea34  mov     qword ptr [rsp+7F0h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x18002ea39  xor     r9d, r9d; dwFileOffsetLow
0x18002ea3c  xor     r8d, r8d; dwFileOffsetHigh
0x18002ea3f  mov     edx, eax; dwDesiredAccess
0x18002ea41  mov     rcx, r15; hFileMappingObject
0x18002ea44  call    cs:__imp_MapViewOfFileEx
0x18002ea4a  mov     r13, rax
0x18002ea4d  mov     [rbp+6F0h+var_750], rax
0x18002ea51  test    rax, rax
0x18002ea54  jnz     short loc_18002EA85
0x18002ea56  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002ea5b  mov     [rsp+7F0h+var_798], eax
0x18002ea5f  mov     rcx, r15; hObject
0x18002ea62  call    cs:__imp_CloseHandle
0x18002ea68  xor     r15d, r15d
0x18002ea6b  mov     [rbp+6F0h+hObject], r15
0x18002ea6f  mov     [rbp+6F0h+var_740], r15
0x18002ea73  xor     ecx, ecx
0x18002ea75  mov     eax, [rsp+7F0h+var_798]
0x18002ea79  test    eax, eax
0x18002ea7b  jns     short loc_18002EA88
0x18002ea7d  xor     r12d, r12d
0x18002ea80  jmp     loc_18002ED54
0x18002ea85  mov     rcx, rax
0x18002ea88  cmp     r12, 100000h
0x18002ea8f  ja      short loc_18002EA7D
0x18002ea91  mov     [rsp+7F0h+var_79C], 0
0x18002ea99  mov     r10, [rsp+7F0h+var_788]
0x18002ea9e  cmp     r12d, 4
0x18002eaa2  jnb     short loc_18002EAAE
0x18002eaa4  mov     [rsp+7F0h+var_7A0], 1
0x18002eaa9  jmp     loc_18002EC55
0x18002eaae  mov     al, [r10+68h]
0x18002eab2  mov     [rsp+7F0h+var_7A0], al
0x18002eab6  test    al, al
0x18002eab8  jnz     loc_18002EC51
0x18002eabe  lea     eax, [r12-4]
0x18002eac3  mov     [rsp+7F0h+var_798], eax
0x18002eac7  cmp     [r10+88h], eax
0x18002eace  jnb     loc_18002EBB7
0x18002ead4  mov     rcx, [r10+80h]; Block
0x18002eadb  call    cs:__imp_free
0x18002eae1  mov     rcx, [rsp+7F0h+var_788]
0x18002eae6  mov     qword ptr [rcx+80h], 0
0x18002eaf1  mov     dword ptr [rcx+88h], 0
0x18002eafb  mov     ecx, r12d; Size
0x18002eafe  call    cs:__imp_malloc
0x18002eb04  mov     r10, [rsp+7F0h+var_788]
0x18002eb09  mov     [r10+80h], rax
0x18002eb10  test    rax, rax
0x18002eb13  jnz     loc_18002EBAC
0x18002eb19  xor     r12d, r12d
0x18002eb1c  test    r13, r13
0x18002eb1f  jz      short loc_18002EB36
0x18002eb21  mov     rcx, r13; lpBaseAddress
0x18002eb24  call    cs:__imp_UnmapViewOfFile
0x18002eb2a  test    eax, eax
0x18002eb2c  jnz     short loc_18002EB36
0x18002eb2e  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002eb33  mov     r12d, eax
0x18002eb36  test    r15, r15
0x18002eb39  jz      short loc_18002EB53
0x18002eb3b  mov     rcx, r15; hObject
0x18002eb3e  call    cs:__imp_CloseHandle
0x18002eb44  test    eax, eax
0x18002eb46  jnz     short loc_18002EB53
0x18002eb48  test    r12d, r12d
0x18002eb4b  js      short loc_18002EB53
0x18002eb4d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002eb52  nop
0x18002eb53  xor     r12d, r12d
0x18002eb56  test    rbx, rbx
0x18002eb59  jz      short loc_18002EB64
0x18002eb5b  mov     rcx, rbx; hObject
0x18002eb5e  call    cs:__imp_CloseHandle
0x18002eb64  mov     rbx, [rsp+7F0h+var_780]
0x18002eb69  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002eb6d  mov     rcx, rbx; hFindFile
0x18002eb70  call    cs:__imp_FindNextFileW
0x18002eb76  test    eax, eax
0x18002eb78  jnz     loc_18002E8D2
0x18002eb7e  mov     rcx, rbx; hFindFile
0x18002eb81  call    cs:__imp_FindClose
0x18002eb87  xor     eax, eax
0x18002eb89  mov     rcx, [rbp+6F0h+var_50]
0x18002eb90  xor     rcx, rsp; StackCookie
0x18002eb93  call    __security_check_cookie
0x18002eb98  add     rsp, 7B8h
0x18002eb9f  pop     r15
0x18002eba1  pop     r14
0x18002eba3  pop     r13
0x18002eba5  pop     r12
0x18002eba7  pop     rdi
0x18002eba8  pop     rsi
0x18002eba9  pop     rbx
0x18002ebaa  pop     rbp
0x18002ebab  retn
0x18002ebac  mov     [r10+88h], r12d
0x18002ebb3  mov     eax, [rsp+7F0h+var_798]
0x18002ebb7  mov     rcx, [r10+80h]
0x18002ebbe  cmp     qword ptr [r10+58h], 0
0x18002ebc3  jz      short loc_18002EC1C
0x18002ebc5  lea     r9, [rcx+4]
0x18002ebc9  mov     ecx, 102h
0x18002ebce  mov     rdx, [r10+70h]
0x18002ebd2  mov     [rsp+7F0h+var_7B8], rdx
0x18002ebd7  lea     rdx, [rsp+7F0h+var_79C]
0x18002ebdc  mov     [rsp+7F0h+hTemplateFile], rdx
0x18002ebe1  mov     [rsp+7F0h+dwFlagsAndAttributes], 1000h
0x18002ebe9  mov     [rsp+7F0h+dwCreationDisposition], eax
0x18002ebed  mov     r8d, r12d
0x18002ebf0  mov     rdx, r13
0x18002ebf3  mov     rax, [r10+58h]
0x18002ebf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebfc  mov     r10, [rsp+7F0h+var_788]
0x18002ec01  mov     rcx, [r10+80h]
0x18002ec08  test    eax, eax
0x18002ec0a  jnz     short loc_18002EC1C
0x18002ec0c  mov     eax, [rsp+7F0h+var_798]
0x18002ec10  cmp     [rsp+7F0h+var_79C], eax
0x18002ec14  ja      short loc_18002EC1C
0x18002ec16  mov     al, [rsp+7F0h+var_7A0]
0x18002ec1a  jmp     short loc_18002EC22
0x18002ec1c  mov     al, 1
0x18002ec1e  mov     [rsp+7F0h+var_7A0], al
0x18002ec22  add     [rsp+7F0h+var_79C], 4
0x18002ec27  mov     [rcx], r12d
0x18002ec2a  test    al, al
0x18002ec2c  jnz     short loc_18002EC55
0x18002ec2e  mov     r12d, [rsp+7F0h+var_79C]
0x18002ec33  mov     rcx, [r10+80h]
0x18002ec3a  mov     qword ptr [rsp+7F0h+FileSizeHigh], rcx
0x18002ec3f  mov     [rsp+7F0h+var_778], rcx
0x18002ec44  mov     [rbp+6F0h+var_76C], esi
0x18002ec47  mov     ecx, 38h ; '8'
0x18002ec4c  mov     eax, r12d
0x18002ec4f  jmp     short loc_18002EC6D
0x18002ec51  mov     [rsp+7F0h+var_7A0], al
0x18002ec55  mov     rax, r13
0x18002ec58  mov     qword ptr [rsp+7F0h+FileSizeHigh], rax
0x18002ec5d  mov     [rsp+7F0h+var_778], rax
0x18002ec62  mov     [rbp+6F0h+var_76C], edi
0x18002ec65  mov     ecx, 28h ; '('
0x18002ec6a  mov     eax, r12d
0x18002ec6d  mov     [rbp+6F0h+var_770], r12d
0x18002ec71  add     rax, 30h ; '0'
0x18002ec75  cmp     rax, 0FFB8h
0x18002ec7b  ja      loc_18002EB19
0x18002ec81  lea     r15, [r10+rcx]
0x18002ec85  lea     r8, [rsp+7F0h+var_778]
0x18002ec8a  lea     rdx, [rbp+6F0h+var_728]
  ... truncated ...
```
