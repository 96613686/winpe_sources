# Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(_LARGE_INTEGER,ulong,ulong,ushort const *,ushort const *)

- ea: `0x18007f144`
- end: `0x18007f576`
- name: `?ProcessPerfTrackManifests@CPerfTrackMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KKPEBG1@Z`
- size: `1074`
- prototype: `int __fastcall(Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this, union _LARGE_INTEGER, int, int, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007eb30`

## callees

- `0x18002da28`
- `0x1800351c0`
- `0x180036d38`
- `0x180037634`
- `0x18004b39c`
- `0x18004ece0`
- `0x18004f964`
- `0x1800556d0`
- `0x18007e8cc`
- `0x18007ea5c`
- `0x18007f144`
- `0x18007f758`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007f3d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007f3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007f554`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f46c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007f46c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007f205`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007f205`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007f45b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007f45b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007f40d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007f536`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007f40d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007f536`

## pseudocode

```c
int __fastcall Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender::ProcessPerfTrackManifests(
        Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        int a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6)
{
  const unsigned __int16 *v7; // r14
  int result; // eax
  HANDLE FirstFileW; // r13
  int v10; // ebx
  int v11; // edi
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  LPCVOID v14; // r14
  HANDLE v15; // r15
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r9
  unsigned int v18; // r15d
  LPCVOID v19; // r12
  char v20; // r13
  __int64 v21; // rcx
  __int64 v22; // rax
  _QWORD *v23; // r14
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v24; // r8
  void **v25; // r14
  int Error; // r14d
  int v27; // r12d
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v30; // [rsp+30h] [rbp-D0h]
  void *v31; // [rsp+38h] [rbp-C8h]
  HANDLE v32; // [rsp+50h] [rbp-B0h]
  unsigned int v33; // [rsp+58h] [rbp-A8h] BYREF
  void *v34; // [rsp+60h] [rbp-A0h]
  Microsoft::Windows::Performance::CPerfTrackMetadataEventTraceExtender *v35; // [rsp+68h] [rbp-98h]
  LPCVOID v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  int v39; // [rsp+80h] [rbp-80h]
  int v40; // [rsp+84h] [rbp-7Ch]
  void *v41; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v42; // [rsp+90h] [rbp-70h]
  LPCVOID lpBaseAddress; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v44; // [rsp+A0h] [rbp-60h]
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  _BYTE v47[8]; // [rsp+C8h] [rbp-38h] BYREF
  _WORD v48[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D4h] [rbp-2Ch]
  char v50; // [rsp+D5h] [rbp-2Bh]
  __int16 v51; // [rsp+D6h] [rbp-2Ah]
  union _LARGE_INTEGER v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+E8h] [rbp-18h]
  void *v54; // [rsp+118h] [rbp+18h]
  unsigned int v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+124h] [rbp+24h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v59[264]; // [rsp+590h] [rbp+490h] BYREF

  v46 = -2;
  v39 = a4;
  v40 = a3;
  v35 = this;
  v7 = a5;
  v42 = a5;
  memset_0(FileName, 0, 0x208u);
  result = StringCchCopyW(FileName, 0x104u, a5);
  if ( result < 0 )
    return result;
  result = StringCchCatW(FileName, 0x104u, a6);
  if ( result < 0 )
    return result;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  v32 = FirstFileW;
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  v10 = v38;
  v11 = v38;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(v59, 0, 0x208u);
      if ( (int)StringCchCopyW(v59, 0x104u, v7) >= 0 && StringCchCatW(v59, 0x104u, FindFileData.cFileName) >= 0 )
      {
        v41 = 0;
        v14 = 0;
        lpBaseAddress = 0;
        v15 = 0;
        hObject = 0;
        if ( ATL::CAtlFile::Create((ATL::CAtlFile *)&v41, v59, v12, v13, v28, v29, v30, v31) >= 0 )
        {
          if ( ATL::CAtlFileMappingBase::MapFile((ATL::CAtlFileMappingBase *)&lpBaseAddress, v41, v16, v17, v28, v29) >= 0 )
          {
            v18 = v44;
            if ( v44 <= 0x100000 )
            {
              v19 = lpBaseAddress;
              v33 = 0;
              if ( (unsigned int)v44 >= 4 )
              {
                v24 = v35;
                v20 = *((_BYTE *)v35 + 104);
                if ( !v20 )
                {
                  LODWORD(v34) = v44 - 4;
                  v25 = (void **)((char *)v35 + 128);
                  if ( *((_DWORD *)v35 + 34) < (unsigned int)(v44 - 4) )
                  {
                    free(*v25);
                    *v25 = 0;
                    *((_DWORD *)v35 + 34) = 0;
                    if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                                             v25,
                                             v18) )
                    {
LABEL_20:
                      Error = 0;
                      if ( v19 && !UnmapViewOfFile(v19) )
                        Error = ATL::AtlHresultFromLastError();
                      if ( hObject && !CloseHandle(hObject) && Error >= 0 )
                        ATL::AtlHresultFromLastError();
                      FirstFileW = v32;
LABEL_28:
                      ATL::CHandle::~CHandle((ATL::CHandle *)&v41);
                      v7 = v42;
                      continue;
                    }
                    v24 = v35;
                    *((_DWORD *)v35 + 34) = v18;
                  }
                  if ( (unsigned int)Performance::RtlCompression::CRtlCompressBuffer::operator()(
                                       (int)v24 + 88,
                                       *(_DWORD *)v25 + 4,
                                       (_DWORD)v19,
                                       v18,
                                       (__int64)*v25 + 4,
                                       (_DWORD)v34,
                                       (_DWORD)v30,
                                       (__int64)&v33,
                                       *((_QWORD *)v24 + 14))
                    || v33 > (unsigned int)v34 )
                  {
                    v20 = 1;
                  }
                  v33 += 4;
                  *(_DWORD *)*v25 = v18;
                  if ( !v20 )
                  {
                    v18 = v33;
                    v34 = *v25;
                    v36 = v34;
                    v38 = v11;
                    v21 = 56;
                    v22 = v33;
                    goto LABEL_14;
                  }
                }
              }
              else
              {
                v20 = 1;
              }
              v34 = (void *)v19;
              v36 = v19;
              v38 = v10;
              v21 = 40;
              v22 = v18;
LABEL_14:
              v37 = v18;
              if ( (unsigned __int64)(v22 + 48) <= 0xFFB8 )
              {
                v23 = (_QWORD *)((char *)v35 + v21);
                if ( *(_QWORD *)std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<unsigned char,ATL::CCRTAllocator>>,0>>::find(
                                  (char *)v35 + v21,
                                  v47,
                                  &v36) == *v23 )
                {
                  memset_0(v48, 0, 0x58u);
                  v48[0] = v39;
                  v52 = a2;
                  v53 = *(_OWORD *)PerfTrackMetadataGuid;
                  v49 = 33 - (v20 != 0);
                  v51 = 0;
                  v50 = 0;
                  v54 = v34;
                  v55 = v18;
                  v56 = v40;
                  (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)v35 + 2) + 192LL))(
                    *((_QWORD *)v35 + 2),
                    v48,
                    0,
                    0);
                }
              }
              goto LABEL_20;
            }
          }
          v15 = hObject;
          v14 = lpBaseAddress;
        }
        v27 = 0;
        if ( v14 && !UnmapViewOfFile(v14) )
          v27 = ATL::AtlHresultFromLastError();
        if ( v15 && !CloseHandle(v15) && v27 >= 0 )
          ATL::AtlHresultFromLastError();
        goto LABEL_28;
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
0x18007f144  push    rbp
0x18007f146  push    rbx
0x18007f147  push    rsi
0x18007f148  push    rdi
0x18007f149  push    r12
0x18007f14b  push    r13
0x18007f14d  push    r14
0x18007f14f  push    r15
0x18007f151  lea     rbp, [rsp-6B8h]
0x18007f159  sub     rsp, 7B8h
0x18007f160  mov     [rbp+6F0h+var_730], 0FFFFFFFFFFFFFFFEh
0x18007f168  mov     rax, cs:__security_cookie
0x18007f16f  xor     rax, rsp
0x18007f172  mov     [rbp+6F0h+var_50], rax
0x18007f179  mov     [rbp+6F0h+var_770], r9d
0x18007f17d  mov     [rbp+6F0h+var_76C], r8d
0x18007f181  mov     rsi, rdx
0x18007f184  mov     [rsp+7F0h+var_788], rcx
0x18007f189  mov     r14, [rbp+6F0h+arg_20]
0x18007f190  mov     [rbp+6F0h+var_760], r14
0x18007f194  mov     rbx, [rbp+6F0h+arg_28]
0x18007f19b  xor     edx, edx; Val
0x18007f19d  mov     r8d, 208h; Size
0x18007f1a3  lea     rcx, [rbp+6F0h+FileName]; void *
0x18007f1aa  call    memset_0
0x18007f1af  mov     r8, r14; unsigned __int16 *
0x18007f1b2  mov     r15d, 104h
0x18007f1b8  mov     edx, r15d; unsigned __int64
0x18007f1bb  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18007f1c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007f1c7  test    eax, eax
0x18007f1c9  js      loc_18007F474
0x18007f1cf  mov     r8, rbx; unsigned __int16 *
0x18007f1d2  mov     edx, r15d; unsigned __int64
0x18007f1d5  lea     rcx, [rbp+6F0h+FileName]; unsigned __int16 *
0x18007f1dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007f1e1  test    eax, eax
0x18007f1e3  js      loc_18007F474
0x18007f1e9  xor     edx, edx; Val
0x18007f1eb  mov     r8d, 250h; Size
0x18007f1f1  lea     rcx, [rbp+6F0h+FindFileData]; void *
0x18007f1f5  call    memset_0
0x18007f1fa  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18007f1fe  lea     rcx, [rbp+6F0h+FileName]; lpFileName
0x18007f205  call    cs:__imp_FindFirstFileW
0x18007f20b  mov     r13, rax
0x18007f20e  mov     [rsp+7F0h+var_7A0], rax
0x18007f213  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007f217  jz      loc_18007F472
0x18007f21d  mov     ebx, [rsp+7F0h+var_774]
0x18007f221  mov     edi, [rsp+7F0h+var_774]
0x18007f225  test    byte ptr [rbp+6F0h+FindFileData.dwFileAttributes], 10h
0x18007f229  jnz     loc_18007F454
0x18007f22f  xor     edx, edx; Val
0x18007f231  mov     r8d, 208h; Size
0x18007f237  lea     rcx, [rbp+6F0h+var_260]; void *
0x18007f23e  call    memset_0
0x18007f243  mov     r8, r14; unsigned __int16 *
0x18007f246  mov     rdx, r15; unsigned __int64
0x18007f249  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18007f250  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007f255  test    eax, eax
0x18007f257  js      loc_18007F454
0x18007f25d  lea     r8, [rbp+6F0h+FindFileData.cFileName]; unsigned __int16 *
0x18007f261  mov     rdx, r15; unsigned __int64
0x18007f264  lea     rcx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18007f26b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007f270  test    eax, eax
0x18007f272  js      loc_18007F454
0x18007f278  mov     [rbp+6F0h+var_768], 0
0x18007f280  xor     r14d, r14d
0x18007f283  mov     [rbp+6F0h+lpBaseAddress], r14
0x18007f287  xor     r15d, r15d
0x18007f28a  mov     [rbp+6F0h+hObject], r15
0x18007f28e  lea     rdx, [rbp+6F0h+var_260]; unsigned __int16 *
0x18007f295  lea     rcx, [rbp+6F0h+var_768]; this
0x18007f299  call    ?Create@CAtlFile@ATL@@QEAAJPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; ATL::CAtlFile::Create(ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x18007f29e  test    eax, eax
0x18007f2a0  js      loc_18007F52B
0x18007f2a6  mov     rdx, [rbp+6F0h+var_768]; void *
0x18007f2aa  lea     rcx, [rbp+6F0h+lpBaseAddress]; this
0x18007f2ae  call    ?MapFile@CAtlFileMappingBase@ATL@@QEAAJPEAX_K1KK@Z; ATL::CAtlFileMappingBase::MapFile(void *,unsigned __int64,unsigned __int64,ulong,ulong)
0x18007f2b3  test    eax, eax
0x18007f2b5  js      loc_18007F523
0x18007f2bb  mov     r15, [rbp+6F0h+var_750]
0x18007f2bf  cmp     r15, 100000h
0x18007f2c6  ja      loc_18007F523
0x18007f2cc  mov     r12, [rbp+6F0h+lpBaseAddress]
0x18007f2d0  mov     [rsp+7F0h+var_798], r14d
0x18007f2d5  cmp     r15d, 4
0x18007f2d9  jnb     loc_18007F3A5
0x18007f2df  mov     r13b, 1
0x18007f2e2  mov     rax, r12
0x18007f2e5  mov     [rsp+7F0h+var_790], rax
0x18007f2ea  mov     [rsp+7F0h+var_780], rax
0x18007f2ef  mov     [rsp+7F0h+var_774], ebx
0x18007f2f3  mov     ecx, 28h ; '('
0x18007f2f8  mov     eax, r15d
0x18007f2fb  mov     [rsp+7F0h+var_778], r15d
0x18007f300  add     rax, 30h ; '0'
0x18007f304  cmp     rax, 0FFB8h
0x18007f30a  ja      loc_18007F402
0x18007f310  mov     r14, [rsp+7F0h+var_788]
0x18007f315  add     r14, rcx
0x18007f318  lea     r8, [rsp+7F0h+var_780]
0x18007f31d  lea     rdx, [rbp+6F0h+var_728]
0x18007f321  mov     rcx, r14
0x18007f324  call    ?find@?$_Tree@V?$_Tset_traits@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@U?$less@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@V?$allocator@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@6@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@std@@@std@@@2@AEBU?$CAllocation@EVCCRTAllocator@ATL@@@Performance@Windows@Microsoft@@@Z; std::_Tree<std::_Tset_traits<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>,std::less<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,std::allocator<Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator>>,0>>::find(Microsoft::Windows::Performance::CAllocation<uchar,ATL::CCRTAllocator> const &)
0x18007f329  mov     rcx, [r14]
0x18007f32c  cmp     [rax], rcx
0x18007f32f  jnz     loc_18007F402
0x18007f335  xor     edx, edx; Val
0x18007f337  lea     r8d, [rdx+58h]; Size
0x18007f33b  lea     rcx, [rbp+6F0h+var_720]; void *
0x18007f33f  call    memset_0
0x18007f344  mov     eax, [rbp+6F0h+var_770]
0x18007f347  mov     [rbp+6F0h+var_720], ax
0x18007f34b  mov     [rbp+6F0h+var_710], rsi
0x18007f34f  movups  xmm0, xmmword ptr cs:PerfTrackMetadataGuid
0x18007f356  movdqu  [rbp+6F0h+var_708], xmm0
0x18007f35b  neg     r13b
0x18007f35e  sbb     al, al
0x18007f360  add     al, 21h ; '!'
0x18007f362  mov     [rbp+6F0h+var_71C], al
0x18007f365  xor     eax, eax
0x18007f367  mov     [rbp+6F0h+var_71A], ax
0x18007f36b  mov     [rbp+6F0h+var_71B], al
0x18007f36e  mov     rax, [rsp+7F0h+var_790]
0x18007f373  mov     [rbp+6F0h+var_6D8], rax
0x18007f377  mov     [rbp+6F0h+var_6D0], r15d
0x18007f37b  mov     eax, [rbp+6F0h+var_76C]
0x18007f37e  mov     [rbp+6F0h+var_6CC], eax
0x18007f381  mov     rax, [rsp+7F0h+var_788]
0x18007f386  mov     rcx, [rax+10h]
0x18007f38a  mov     rax, [rcx]
0x18007f38d  xor     r9d, r9d
0x18007f390  xor     r8d, r8d
0x18007f393  lea     rdx, [rbp+6F0h+var_720]
0x18007f397  mov     rax, [rax+0C0h]
0x18007f39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3a3  jmp     short loc_18007F402
0x18007f3a5  mov     r8, [rsp+7F0h+var_788]
0x18007f3aa  mov     r13b, [r8+68h]
0x18007f3ae  test    r13b, r13b
0x18007f3b1  jnz     loc_18007F2E2
0x18007f3b7  lea     eax, [r15-4]
0x18007f3bb  mov     dword ptr [rsp+7F0h+var_790], eax
0x18007f3bf  lea     r14, [r8+80h]
0x18007f3c6  cmp     [r14+8], eax
0x18007f3ca  jnb     loc_18007F4A3
0x18007f3d0  mov     rcx, [r14]; Block
0x18007f3d3  call    cs:__imp_free
0x18007f3d9  mov     qword ptr [r14], 0
0x18007f3e0  mov     rax, [rsp+7F0h+var_788]
0x18007f3e5  mov     dword ptr [rax+88h], 0
0x18007f3ef  mov     edx, r15d
0x18007f3f2  mov     rcx, r14
0x18007f3f5  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x18007f3fa  test    al, al
0x18007f3fc  jnz     loc_18007F497
0x18007f402  xor     r14d, r14d
0x18007f405  test    r12, r12
0x18007f408  jz      short loc_18007F41F
0x18007f40a  mov     rcx, r12; lpBaseAddress
0x18007f40d  call    cs:__imp_UnmapViewOfFile
0x18007f413  test    eax, eax
0x18007f415  jnz     short loc_18007F41F
0x18007f417  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007f41c  mov     r14d, eax
0x18007f41f  mov     rcx, [rbp+6F0h+hObject]; hObject
0x18007f423  test    rcx, rcx
0x18007f426  jz      short loc_18007F43C
0x18007f428  call    cs:__imp_CloseHandle
0x18007f42e  test    eax, eax
0x18007f430  jnz     short loc_18007F43C
0x18007f432  test    r14d, r14d
0x18007f435  js      short loc_18007F43C
0x18007f437  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007f43c  mov     r13, [rsp+7F0h+var_7A0]
0x18007f441  lea     rcx, [rbp+6F0h+var_768]; this
0x18007f445  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x18007f44a  mov     r14, [rbp+6F0h+var_760]
0x18007f44e  mov     r15d, 104h
0x18007f454  lea     rdx, [rbp+6F0h+FindFileData]; lpFindFileData
0x18007f458  mov     rcx, r13; hFindFile
0x18007f45b  call    cs:__imp_FindNextFileW
0x18007f461  test    eax, eax
0x18007f463  jnz     loc_18007F225
0x18007f469  mov     rcx, r13; hFindFile
0x18007f46c  call    cs:__imp_FindClose
0x18007f472  xor     eax, eax
0x18007f474  mov     rcx, [rbp+6F0h+var_50]
0x18007f47b  xor     rcx, rsp; StackCookie
0x18007f47e  call    __security_check_cookie
0x18007f483  add     rsp, 7B8h
0x18007f48a  pop     r15
0x18007f48c  pop     r14
0x18007f48e  pop     r13
0x18007f490  pop     r12
0x18007f492  pop     rdi
0x18007f493  pop     rsi
0x18007f494  pop     rbx
0x18007f495  pop     rbp
0x18007f496  retn
0x18007f497  mov     r8, [rsp+7F0h+var_788]
0x18007f49c  mov     [r8+88h], r15d
0x18007f4a3  mov     rdx, [r14]
0x18007f4a6  add     rdx, 4
0x18007f4aa  lea     rcx, [r8+58h]
0x18007f4ae  mov     rax, [r8+70h]
0x18007f4b2  mov     [rsp+7F0h+var_7B0], rax
0x18007f4b7  lea     rax, [rsp+7F0h+var_798]
0x18007f4bc  mov     [rsp+7F0h+var_7B8], rax
0x18007f4c1  mov     eax, dword ptr [rsp+7F0h+var_790]
0x18007f4c5  mov     [rsp+7F0h+var_7C8], eax
0x18007f4c9  mov     [rsp+7F0h+var_7D0], rdx
0x18007f4ce  mov     r9d, r15d
0x18007f4d1  mov     r8, r12
0x18007f4d4  call    ??RCRtlCompressBuffer@RtlCompression@Performance@@QEBAJGPEBXKPEAXKKPEAK1@Z; Performance::RtlCompression::CRtlCompressBuffer::operator()(ushort,void const *,ulong,void *,ulong,ulong,ulong *,void *)
0x18007f4d9  mov     ecx, [rsp+7F0h+var_798]
0x18007f4dd  test    eax, eax
0x18007f4df  jnz     short loc_18007F4E7
0x18007f4e1  cmp     ecx, dword ptr [rsp+7F0h+var_790]
0x18007f4e5  jbe     short loc_18007F4EA
0x18007f4e7  mov     r13b, 1
0x18007f4ea  add     ecx, 4
0x18007f4ed  mov     [rsp+7F0h+var_798], ecx
0x18007f4f1  mov     rax, [r14]
0x18007f4f4  mov     [rax], r15d
0x18007f4f7  test    r13b, r13b
0x18007f4fa  jnz     loc_18007F2E2
0x18007f500  mov     r15d, [rsp+7F0h+var_798]
0x18007f505  mov     rcx, [r14]
0x18007f508  mov     [rsp+7F0h+var_790], rcx
0x18007f50d  mov     [rsp+7F0h+var_780], rcx
0x18007f512  mov     [rsp+7F0h+var_774], edi
0x18007f516  mov     ecx, 38h ; '8'
0x18007f51b  mov     eax, r15d
0x18007f51e  jmp     loc_18007F2FB
0x18007f523  mov     r15, [rbp+6F0h+hObject]
0x18007f527  mov     r14, [rbp+6F0h+lpBaseAddress]
0x18007f52b  xor     r12d, r12d
0x18007f52e  test    r14, r14
0x18007f531  jz      short loc_18007F548
0x18007f533  mov     rcx, r14; lpBaseAddress
0x18007f536  call    cs:__imp_UnmapViewOfFile
0x18007f53c  test    eax, eax
0x18007f53e  jnz     short loc_18007F548
0x18007f540  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007f545  mov     r12d, eax
0x18007f548  test    r15, r15
0x18007f54b  jz      loc_18007F441
0x18007f551  mov     rcx, r15; hObject
0x18007f554  call    cs:__imp_CloseHandle
0x18007f55a  test    eax, eax
0x18007f55c  jnz     loc_18007F441
0x18007f562  test    r12d, r12d
0x18007f565  js      loc_18007F441
0x18007f56b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007f570  jmp     loc_18007F441
```
