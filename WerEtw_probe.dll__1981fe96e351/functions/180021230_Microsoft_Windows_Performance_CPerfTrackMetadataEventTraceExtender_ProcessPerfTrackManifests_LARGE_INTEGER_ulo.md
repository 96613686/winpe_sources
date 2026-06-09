# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x180021230`
- end: `0x1800217cb`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1435`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x180001870`
- `0x1800023d8`
- `0x1800023e4`
- `0x180002420`
- `0x180004670`
- `0x18001f020`
- `0x180021230`
- `0x1800219e8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800215ef`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800215ef`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021439`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180021439`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021407`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021407`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800215de`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800215de`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180021324`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180021324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800214d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800217a5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180021592`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002178a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180021592`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002178a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800214b4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1800214b4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002145e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002145e`

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
  int v11; // r12d
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
  int Error; // eax
  int v30; // eax
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
  int v44; // r15d
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
  char v63[8]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v64[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v65; // [rsp+D4h] [rbp-2Ch]
  char v66; // [rsp+D5h] [rbp-2Bh]
  __int16 v67; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v68; // [rsp+E0h] [rbp-20h]
  __int128 v69; // [rsp+E8h] [rbp-18h]
  size_t v70; // [rsp+118h] [rbp+18h]
  int v71; // [rsp+120h] [rbp+20h]
  int v72; // [rsp+124h] [rbp+24h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
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
                v37 = o_malloc_0((unsigned int)v32);
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
              v69 = PerfTrackMetadataGuid;
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
0x180021230  push    rbp
0x180021232  push    rbx
0x180021233  push    rsi
0x180021234  push    rdi
0x180021235  push    r12
0x180021237  push    r13
0x180021239  push    r14
0x18002123b  push    r15
0x18002123d  lea     rbp, [rsp-6B8h]
0x180021245  sub     rsp, 7B8h
0x18002124c  mov     rax, cs:__security_cookie
0x180021253  xor     rax, rsp
0x180021256  mov     [rbp+6F0h+var_50], rax
0x18002125d  mov     [rbp+6F0h+var_768], r9d
0x180021261  mov     [rbp+6F0h+var_764], r8d
0x180021265  mov     r14, rdx
0x180021268  mov     [rsp+7F0h+var_788], rcx
0x18002126d  mov     rbx, [rbp+6F0h+arg_28]
0x180021274  xor     edx, edx; Val
0x180021276  mov     r8d, 208h; Size
0x18002127c  lea     rcx, [rbp+6F0h+FileName]; void *
0x180021283  call    memset_0
0x180021288  mov     eax, 7FFFFFFEh
0x18002128d  mov     rdx, [rbp+6F0h+arg_20]
0x180021294  mov     r8d, 104h
0x18002129a  lea     rcx, [rbp+6F0h+FileName]
0x1800212a1  xor     r12d, r12d
0x1800212a4  test    rax, rax
0x1800212a7  jz      short loc_1800212C8
0x1800212a9  movzx   r9d, word ptr [rdx]
0x1800212ad  test    r9w, r9w
0x1800212b1  jz      short loc_1800212C8
0x1800212b3  add     rdx, 2
0x1800212b7  mov     [rcx], r9w
0x1800212bb  add     rcx, 2
0x1800212bf  dec     rax
0x1800212c2  sub     r8, 1
0x1800212c6  jnz     short loc_1800212A4
0x1800212c8  mov     rax, r8
0x1800212cb  neg     rax
0x1800212ce  sbb     eax, eax
0x1800212d0  not     eax
0x1800212d2  and     eax, 8007007Ah
0x1800212d7  lea     rdx, [rcx-2]
0x1800212db  test    r8, r8
0x1800212de  cmovnz  rdx, rcx
0x1800212e2  mov     [rdx], r12w
0x1800212e6  jz      loc_1800215F7
0x1800212ec  mov     r8, rbx; unsigned __int16 *
0x1800212ef  mov     edx, 104h; unsigned __int64
0x1800212f4  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x1800212fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021300  test    eax, eax
0x180021302  js      loc_1800215F7
0x180021308  xor     edx, edx; Val
0x18002130a  mov     r8d, 250h; Size
0x180021310  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x180021314  call    memset_0
0x180021319  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18002131d  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x180021324  call    cs:__imp_FindFirstFileW
0x18002132a  mov     [rsp+7F0h+var_780], rax
0x18002132f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021333  jz      loc_1800215F5
0x180021339  mov     edi, [rbp+6F0h+var_76C]
0x18002133c  mov     esi, [rbp+6F0h+var_76C]
0x18002133f  mov     rbx, rax
0x180021342  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x180021346  jnz     loc_1800215D7
0x18002134c  xor     edx, edx; Val
0x18002134e  mov     r8d, 208h; Size
0x180021354  lea     rcx, [rbp+6F0h+var_260]; void *
0x18002135b  call    memset_0
0x180021360  mov     ecx, 7FFFFFFEh
0x180021365  mov     r8, [rbp+6F0h+arg_20]
0x18002136c  mov     edx, 104h
0x180021371  lea     rax, [rbp+6F0h+var_260]
0x180021378  test    rcx, rcx
0x18002137b  jz      short loc_18002139C
0x18002137d  movzx   r9d, word ptr [r8]
0x180021381  test    r9w, r9w
0x180021385  jz      short loc_18002139C
0x180021387  add     r8, 2
0x18002138b  mov     [rax], r9w
0x18002138f  add     rax, 2
0x180021393  dec     rcx
0x180021396  sub     rdx, 1
0x18002139a  jnz     short loc_180021378
0x18002139c  lea     rcx, [rax-2]
0x1800213a0  test    rdx, rdx
0x1800213a3  cmovnz  rcx, rax
0x1800213a7  mov     [rcx], r12w
0x1800213ab  jz      loc_1800215D7
0x1800213b1  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x1800213b5  mov     edx, 104h; unsigned __int64
0x1800213ba  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x1800213c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800213c6  test    eax, eax
0x1800213c8  js      loc_1800215D7
0x1800213ce  mov     rbx, r12
0x1800213d1  mov     [rbp+6F0h+var_758], rbx
0x1800213d5  mov     r13, r12
0x1800213d8  mov     [rbp+6F0h+var_750], r12
0x1800213dc  mov     r15, r12
0x1800213df  mov     [rsp+7F0h+hTemplateFile], r12; hTemplateFile
0x1800213e4  mov     [rsp+7F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800213ec  mov     [rsp+7F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800213f4  xor     r9d, r9d; lpSecurityAttributes
0x1800213f7  mov     edx, 80000000h; dwDesiredAccess
0x1800213fc  lea     r8d, [r9+1]; dwShareMode
0x180021400  lea     rcx, [rbp+6F0h+var_260]; lpFileName
0x180021407  call    cs:__imp_CreateFileW
0x18002140d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021411  jnz     short loc_18002141A
0x180021413  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180021418  jmp     short loc_180021424
0x18002141a  mov     rbx, rax
0x18002141d  mov     [rbp+6F0h+var_758], rax
0x180021421  mov     eax, r12d
0x180021424  test    eax, eax
0x180021426  js      loc_1800217BF
0x18002142c  mov     qword ptr [rsp+7F0h+FileSizeHigh], r12
0x180021431  lea     rdx, [rsp+7F0h+FileSizeHigh+4]; lpFileSizeHigh
0x180021436  mov     rcx, rbx; hFile
0x180021439  call    cs:__imp_GetFileSize
0x18002143f  mov     [rsp+7F0h+FileSizeHigh], eax
0x180021443  mov     r9, qword ptr [rsp+7F0h+FileSizeHigh]
0x180021448  shr     r9, 20h; dwMaximumSizeHigh
0x18002144c  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], r12; lpName
0x180021451  mov     [rsp+7F0h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180021455  xor     edx, edx; lpFileMappingAttributes
0x180021457  lea     r8d, [rdx+2]; flProtect
0x18002145b  mov     rcx, rbx; hFile
0x18002145e  call    cs:__imp_CreateFileMappingW
0x180021464  mov     r15, rax
0x180021467  mov     [rbp+6F0h+hObject], rax
0x18002146b  mov     [rbp+6F0h+var_740], rax
0x18002146f  test    rax, rax
0x180021472  jnz     short loc_180021482
0x180021474  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180021479  mov     rcx, r12
0x18002147c  mov     r12, [rbp+6F0h+Size]
0x180021480  jmp     short loc_1800214E9
0x180021482  mov     r12, qword ptr [rsp+7F0h+FileSizeHigh]
0x180021487  mov     [rbp+6F0h+Size], r12
0x18002148b  mov     eax, 4
0x180021490  mov     [rbp+6F0h+var_730], eax
0x180021493  mov     [rbp+6F0h+var_738], 0
0x18002149b  mov     qword ptr [rsp+7F0h+dwFlagsAndAttributes], 0; lpBaseAddress
0x1800214a4  mov     qword ptr [rsp+7F0h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x1800214a9  xor     r9d, r9d; dwFileOffsetLow
0x1800214ac  xor     r8d, r8d; dwFileOffsetHigh
0x1800214af  mov     edx, eax; dwDesiredAccess
0x1800214b1  mov     rcx, r15; hFileMappingObject
0x1800214b4  call    cs:__imp_MapViewOfFileEx
0x1800214ba  mov     r13, rax
0x1800214bd  mov     [rbp+6F0h+var_750], rax
0x1800214c1  test    rax, rax
0x1800214c4  jnz     short loc_1800214F5
0x1800214c6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800214cb  mov     [rsp+7F0h+var_798], eax
0x1800214cf  mov     rcx, r15; hObject
0x1800214d2  call    cs:__imp_CloseHandle
0x1800214d8  xor     r15d, r15d
0x1800214db  mov     [rbp+6F0h+hObject], r15
0x1800214df  mov     [rbp+6F0h+var_740], r15
0x1800214e3  xor     ecx, ecx
0x1800214e5  mov     eax, [rsp+7F0h+var_798]
0x1800214e9  test    eax, eax
0x1800214eb  jns     short loc_1800214F8
0x1800214ed  xor     r12d, r12d
0x1800214f0  jmp     loc_1800217C2
0x1800214f5  mov     rcx, rax
0x1800214f8  cmp     r12, 100000h
0x1800214ff  ja      short loc_1800214ED
0x180021501  mov     [rsp+7F0h+var_79C], 0
0x180021509  mov     r10, [rsp+7F0h+var_788]
0x18002150e  cmp     r12d, 4
0x180021512  jnb     short loc_18002151E
0x180021514  mov     [rsp+7F0h+var_7A0], 1
0x180021519  jmp     loc_1800216C3
0x18002151e  mov     al, [r10+68h]
0x180021522  mov     [rsp+7F0h+var_7A0], al
0x180021526  test    al, al
0x180021528  jnz     loc_1800216BF
0x18002152e  lea     eax, [r12-4]
0x180021533  mov     [rsp+7F0h+var_798], eax
0x180021537  cmp     [r10+88h], eax
0x18002153e  jnb     loc_180021625
0x180021544  mov     rcx, [r10+80h]; Block
0x18002154b  call    free
0x180021550  mov     rcx, [rsp+7F0h+var_788]
0x180021555  mov     qword ptr [rcx+80h], 0
0x180021560  mov     dword ptr [rcx+88h], 0
0x18002156a  mov     ecx, r12d; Size
0x18002156d  call    _o_malloc_0
0x180021572  mov     r10, [rsp+7F0h+var_788]
0x180021577  mov     [r10+80h], rax
0x18002157e  test    rax, rax
0x180021581  jnz     loc_18002161A
0x180021587  xor     r12d, r12d
0x18002158a  test    r13, r13
0x18002158d  jz      short loc_1800215A4
0x18002158f  mov     rcx, r13; lpBaseAddress
0x180021592  call    cs:__imp_UnmapViewOfFile
0x180021598  test    eax, eax
0x18002159a  jnz     short loc_1800215A4
0x18002159c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800215a1  mov     r12d, eax
0x1800215a4  test    r15, r15
0x1800215a7  jz      short loc_1800215C1
0x1800215a9  mov     rcx, r15; hObject
0x1800215ac  call    cs:__imp_CloseHandle
0x1800215b2  test    eax, eax
0x1800215b4  jnz     short loc_1800215C1
0x1800215b6  test    r12d, r12d
0x1800215b9  js      short loc_1800215C1
0x1800215bb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800215c0  nop
0x1800215c1  xor     r12d, r12d
0x1800215c4  test    rbx, rbx
0x1800215c7  jz      short loc_1800215D2
0x1800215c9  mov     rcx, rbx; hObject
0x1800215cc  call    cs:__imp_CloseHandle
0x1800215d2  mov     rbx, [rsp+7F0h+var_780]
0x1800215d7  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x1800215db  mov     rcx, rbx; hFindFile
0x1800215de  call    cs:__imp_FindNextFileW
0x1800215e4  test    eax, eax
0x1800215e6  jnz     loc_180021342
0x1800215ec  mov     rcx, rbx; hFindFile
0x1800215ef  call    cs:__imp_FindClose
0x1800215f5  xor     eax, eax
0x1800215f7  mov     rcx, [rbp+6F0h+var_50]
0x1800215fe  xor     rcx, rsp; StackCookie
0x180021601  call    __security_check_cookie
0x180021606  add     rsp, 7B8h
0x18002160d  pop     r15
0x18002160f  pop     r14
0x180021611  pop     r13
0x180021613  pop     r12
0x180021615  pop     rdi
0x180021616  pop     rsi
0x180021617  pop     rbx
0x180021618  pop     rbp
0x180021619  retn
0x18002161a  mov     [r10+88h], r12d
0x180021621  mov     eax, [rsp+7F0h+var_798]
0x180021625  mov     rcx, [r10+80h]
0x18002162c  cmp     qword ptr [r10+58h], 0
0x180021631  jz      short loc_18002168A
0x180021633  lea     r9, [rcx+4]
0x180021637  mov     ecx, 102h
0x18002163c  mov     rdx, [r10+70h]
0x180021640  mov     [rsp+7F0h+var_7B8], rdx
0x180021645  lea     rdx, [rsp+7F0h+var_79C]
0x18002164a  mov     [rsp+7F0h+hTemplateFile], rdx
0x18002164f  mov     [rsp+7F0h+dwFlagsAndAttributes], 1000h
0x180021657  mov     [rsp+7F0h+dwCreationDisposition], eax
0x18002165b  mov     r8d, r12d
0x18002165e  mov     rdx, r13
0x180021661  mov     rax, [r10+58h]
0x180021665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002166a  mov     r10, [rsp+7F0h+var_788]
0x18002166f  mov     rcx, [r10+80h]
0x180021676  test    eax, eax
0x180021678  jnz     short loc_18002168A
0x18002167a  mov     eax, [rsp+7F0h+var_798]
0x18002167e  cmp     [rsp+7F0h+var_79C], eax
0x180021682  ja      short loc_18002168A
0x180021684  mov     al, [rsp+7F0h+var_7A0]
0x180021688  jmp     short loc_180021690
0x18002168a  mov     al, 1
0x18002168c  mov     [rsp+7F0h+var_7A0], al
0x180021690  add     [rsp+7F0h+var_79C], 4
0x180021695  mov     [rcx], r12d
0x180021698  test    al, al
0x18002169a  jnz     short loc_1800216C3
0x18002169c  mov     r12d, [rsp+7F0h+var_79C]
0x1800216a1  mov     rcx, [r10+80h]
0x1800216a8  mov     qword ptr [rsp+7F0h+FileSizeHigh], rcx
0x1800216ad  mov     [rsp+7F0h+var_778], rcx
0x1800216b2  mov     [rbp+6F0h+var_76C], esi
0x1800216b5  mov     ecx, 38h ; '8'
0x1800216ba  mov     eax, r12d
0x1800216bd  jmp     short loc_1800216DB
0x1800216bf  mov     [rsp+7F0h+var_7A0], al
0x1800216c3  mov     rax, r13
0x1800216c6  mov     qword ptr [rsp+7F0h+FileSizeHigh], rax
0x1800216cb  mov     [rsp+7F0h+var_778], rax
0x1800216d0  mov     [rbp+6F0h+var_76C], edi
0x1800216d3  mov     ecx, 28h ; '('
0x1800216d8  mov     eax, r12d
0x1800216db  mov     [rbp+6F0h+var_770], r12d
0x1800216df  add     rax, 30h ; '0'
0x1800216e3  cmp     rax, 0FFB8h
0x1800216e9  ja      loc_180021587
0x1800216ef  lea     r15, [r10+rcx]
0x1800216f3  lea     r8, [rsp+7F0h+var_778]
0x1800216f8  lea     rdx, [rbp+6F0h+var_728]
  ... truncated ...
```
