# ExtractFileFromQuorumSignedInfraCABImp(wchar_t const *,char const *,char const *,wchar_t const *,uchar * *,ulong *)

- ea: `0x14002c6e0`
- end: `0x14002cbd0`
- name: `?ExtractFileFromQuorumSignedInfraCABImp@@YAJPEB_WPEBD10PEAPEAEPEAK@Z`
- size: `1264`
- prototype: `__int64 __fastcall(const wchar_t *, const char *, const char *, const wchar_t *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400333b4`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x14000d7b0`
- `0x14000fc20`
- `0x14000fd94`
- `0x14000feec`
- `0x1400122f0`
- `0x1400154b4`
- `0x140017934`
- `0x14002c6e0`
- `0x14002d138`
- `0x14002fed4`
- `0x140045dc0`
- `0x140045de4`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002cb83`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x14002c9bc`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x14002c9bc`

## string_xrefs

- `0x14002c7ed`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14002c7e3`: `SkipQuorumSignatureChecks`
- `0x14002cadb`: `Cab does not contain correct XML CAB file.`
- `0x14002c72c`: `environment.xml`

## pseudocode

```c
__int64 __fastcall ExtractFileFromQuorumSignedInfraCABImp(
        wchar_t *a1,
        const char *a2,
        const char *a3,
        const wchar_t *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  char v7; // r12
  void *v8; // r15
  void *v9; // r14
  __int64 v10; // rcx
  const wchar_t *v11; // rdx
  signed int FileToSafeByteBuffer; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rsi
  const wchar_t *v17; // rax
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  signed __int64 v20; // rdi
  WCHAR v21; // ax
  WCHAR *v22; // rax
  __int64 v23; // rcx
  WCHAR *v24; // rax
  WCHAR *i; // rax
  signed int LastError; // eax
  signed int v27; // ecx
  signed int v28; // eax
  int v29; // r9d
  const wchar_t *v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rax
  __int64 v34; // rsi
  __int64 v35; // rcx
  unsigned int v36; // edi
  __int64 v37; // r12
  __int64 v38; // rcx
  unsigned __int8 *v39; // rax
  int v41; // [rsp+28h] [rbp-E0h]
  int v42; // [rsp+28h] [rbp-E0h]
  int v43; // [rsp+28h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v44; // [rsp+30h] [rbp-D8h]
  __int64 v45; // [rsp+58h] [rbp-B0h] BYREF
  char v46; // [rsp+60h] [rbp-A8h]
  __int16 v47; // [rsp+61h] [rbp-A7h]
  char v48; // [rsp+63h] [rbp-A5h]
  __int64 v49; // [rsp+68h] [rbp-A0h] BYREF
  char v50; // [rsp+70h] [rbp-98h]
  __int16 v51; // [rsp+71h] [rbp-97h]
  char v52; // [rsp+73h] [rbp-95h]
  _QWORD *v53; // [rsp+78h] [rbp-90h] BYREF
  _QWORD *v54; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-80h] BYREF
  unsigned __int8 **v56; // [rsp+90h] [rbp-78h]
  char *v57; // [rsp+98h] [rbp-70h] BYREF
  char *v58; // [rsp+A0h] [rbp-68h] BYREF
  void *lpMem[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-50h]
  WCHAR PathName[264]; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR TempFileName[264]; // [rsp+2D8h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+520h] [rbp+418h]

  v56 = a5;
  v58 = "environment.xml";
  v57 = "environment.cab";
  v7 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  lpMem[0] = &CSafeBuffer<unsigned char>::`vftable';
  lpMem[1] = 0;
  v60 = 0;
  v8 = 0;
  v54 = 0;
  v9 = 0;
  v53 = 0;
  hObject = (HANDLE)-1LL;
  memset(TempFileName, 0, 0x208u);
  memset(PathName, 0, 0x208u);
  *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( (unsigned int)AreTestKeysAllowed()
    && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                       v10,
                       L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                       L"SkipQuorumSignatureChecks",
                       0) )
  {
    v7 = 1;
    WUTrace(0, 0, 32, 4, 0, L"Using test override : %ws");
  }
  FileToSafeByteBuffer = ReadFileToSafeByteBuffer(a1);
  if ( FileToSafeByteBuffer >= 0 )
  {
    FileToSafeByteBuffer = VerifyInfraCAB(a1, v11, (struct DualSubCAIdentity *)&v49);
    if ( FileToSafeByteBuffer >= 0 )
    {
      FileToSafeByteBuffer = DecompressCabFile((__int64)lpMem, &v57, v13, v14, v41, &v54);
      v8 = v54;
      if ( FileToSafeByteBuffer >= 0 )
      {
        v15 = v54[1];
        v54[4] = v15;
        v16 = v15;
        if ( !v15 )
        {
          v17 = L"Cab does not contain correct inner CAB file.";
LABEL_11:
          WUTrace(0, 0, 32, 5, 0, v17);
          FileToSafeByteBuffer = -2145124275;
          goto LABEL_58;
        }
        v18 = 260;
        v19 = PathName;
        v20 = (char *)a1 - (char *)PathName;
        do
        {
          if ( v18 == -2147483386 )
            break;
          v21 = *(WCHAR *)((char *)v19 + v20);
          if ( !v21 )
            break;
          *v19++ = v21;
          --v18;
        }
        while ( v18 );
        v22 = v19 - 1;
        if ( v18 )
          v22 = v19;
        *v22 = 0;
        FileToSafeByteBuffer = v18 == 0 ? 0x8007007A : 0;
        if ( v18 )
        {
          v23 = 260;
          v24 = PathName;
          do
          {
            if ( !*v24 )
              break;
            ++v24;
            --v23;
          }
          while ( v23 );
          if ( !v23 )
          {
            FileToSafeByteBuffer = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5A5,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
              (const char *)0x80070057LL,
              v42);
            goto LABEL_58;
          }
          for ( i = &PathName[(260 - v23) & ((unsigned __int128)-(__int128)(unsigned __int64)v23 >> 64)]; i > PathName; --i )
          {
            if ( *i == 92 )
              goto LABEL_31;
            if ( *i == 47 )
              break;
          }
          if ( i == PathName )
          {
            PathName[0] = 0;
            goto LABEL_32;
          }
LABEL_31:
          i[1] = 0;
LABEL_32:
          if ( GetTempFileNameW(PathName, L"TMP", 0, TempFileName) )
          {
            FileToSafeByteBuffer = SafeCreateFile(&hObject, 0, TempFileName, 0x80000000, 7u, v44, 2u, 0x4000100u);
            if ( FileToSafeByteBuffer >= 0 )
            {
              FileToSafeByteBuffer = WriteBufferToFile(
                                       TempFileName,
                                       *(void **)(*(_QWORD *)(v16 + 16) + 8LL),
                                       *(_DWORD *)(*(_QWORD *)(v16 + 16) + 20LL),
                                       v29);
              if ( FileToSafeByteBuffer >= 0 )
              {
                FileToSafeByteBuffer = VerifyInfraCAB(TempFileName, v30, (struct DualSubCAIdentity *)&v45);
                if ( FileToSafeByteBuffer >= 0 )
                {
                  if ( !v7 && (v50 != v46 || (_DWORD)v49 == (_DWORD)v45 || v50 && HIDWORD(v49) == HIDWORD(v45)) )
                  {
                    FileToSafeByteBuffer = -2145078525;
                    goto LABEL_58;
                  }
                  FileToSafeByteBuffer = DecompressCabFile(*(_QWORD *)(v16 + 16), &v58, v31, v32, v43, &v53);
                  v9 = v53;
                  if ( FileToSafeByteBuffer >= 0 )
                  {
                    v33 = v53[1];
                    v53[4] = v33;
                    v34 = v33;
                    if ( !v33 || (v35 = *(_QWORD *)(v33 + 16), v36 = *(_DWORD *)(v35 + 20), v37 = v36, v36 < 2) )
                    {
                      v17 = L"Cab does not contain correct XML CAB file.";
                      goto LABEL_11;
                    }
                    if ( *(_BYTE *)(v36 - 1 + *(_QWORD *)(v35 + 8)) )
                    {
                      FileToSafeByteBuffer = CSafeBuffer<unsigned char>::resize(v35, ++v36);
                      if ( FileToSafeByteBuffer < 0 )
                        goto LABEL_58;
                      *(_BYTE *)(v37 + *(_QWORD *)(*(_QWORD *)(v34 + 16) + 8LL)) = 0;
                    }
                    v38 = *(_QWORD *)(v34 + 16);
                    v39 = *(unsigned __int8 **)(v38 + 8);
                    *(_QWORD *)(v38 + 8) = 0;
                    *(_QWORD *)(v38 + 16) = 0;
                    *v56 = v39;
                    if ( a6 )
                      *a6 = v36;
                  }
                }
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v27 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v27 = LastError;
            if ( v27 >= 0 )
            {
              FileToSafeByteBuffer = -2147467259;
            }
            else
            {
              v28 = GetLastError();
              FileToSafeByteBuffer = (unsigned __int16)v28 | 0x80070000;
              if ( v28 <= 0 )
                FileToSafeByteBuffer = v28;
            }
          }
        }
      }
    }
  }
LABEL_58:
  if ( v8 )
  {
    CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v8);
    operator delete(v8, (const struct std::nothrow_t *)0x28);
  }
  if ( v9 )
  {
    CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x28);
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  lpMem[0] = &CSafeBuffer<unsigned char>::`vftable';
  SusFree(lpMem[1]);
  return (unsigned int)FileToSafeByteBuffer;
}

```

## disassembly

```asm
0x14002c6e0  mov     rax, rsp
0x14002c6e3  mov     [rax+10h], rbx
0x14002c6e7  mov     [rax+18h], rsi
0x14002c6eb  mov     [rax+20h], rdi
0x14002c6ef  push    rbp
0x14002c6f0  push    r12
0x14002c6f2  push    r13
0x14002c6f4  push    r14
0x14002c6f6  push    r15
0x14002c6f8  lea     rbp, [rax-418h]
0x14002c6ff  sub     rsp, 4F0h
0x14002c706  mov     rax, cs:__security_cookie
0x14002c70d  xor     rax, rsp
0x14002c710  mov     [rbp+410h+var_30], rax
0x14002c717  mov     rdi, rcx
0x14002c71a  mov     rbx, [rbp+410h+arg_20]
0x14002c721  mov     [rbp+410h+var_488], rbx
0x14002c725  mov     r13, [rbp+410h+arg_28]
0x14002c72c  lea     rax, aEnvironmentXml; "environment.xml"
0x14002c733  mov     [rbp+410h+var_478], rax
0x14002c737  lea     rax, aEnvironmentCab; "environment.cab"
0x14002c73e  mov     [rbp+410h+var_480], rax
0x14002c742  xor     r12d, r12d
0x14002c745  mov     qword ptr [rsp+510h+var_4B0], r12
0x14002c74a  mov     byte ptr [rsp+510h+var_4A8], r12b
0x14002c74f  xor     eax, eax
0x14002c751  mov     word ptr [rsp+510h+var_4A8+1], ax
0x14002c756  mov     byte ptr [rsp+510h+var_4A8+3], al
0x14002c75a  mov     qword ptr [rsp+510h+var_4C0], r12
0x14002c75f  mov     byte ptr [rsp+510h+var_4B8], r12b
0x14002c764  mov     word ptr [rsp+510h+var_4B8+1], ax
0x14002c769  mov     byte ptr [rsp+510h+var_4B8+3], al
0x14002c76d  xorps   xmm0, xmm0
0x14002c770  movups  xmmword ptr [rbp+410h+lpMem], xmm0
0x14002c774  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x14002c77b  mov     [rbp+410h+lpMem], rax
0x14002c77f  mov     [rbp+410h+lpMem+8], r12
0x14002c783  mov     [rbp+410h+var_460], r12
0x14002c787  mov     r15d, r12d
0x14002c78a  mov     [rsp+510h+var_498], r12
0x14002c78f  mov     r14d, r12d
0x14002c792  mov     [rsp+510h+var_4A0], r12
0x14002c797  mov     [rbp+410h+hObject], 0FFFFFFFFFFFFFFFFh
0x14002c79f  mov     esi, 208h
0x14002c7a4  mov     r8d, esi; Size
0x14002c7a7  xor     edx, edx; Val
0x14002c7a9  lea     rcx, [rbp+410h+TempFileName]; void *
0x14002c7b0  call    memset
0x14002c7b5  mov     r8d, esi; Size
0x14002c7b8  xor     edx, edx; Val
0x14002c7ba  lea     rcx, [rbp+410h+PathName]; void *
0x14002c7be  call    memset
0x14002c7c3  mov     [rbx], r12
0x14002c7c6  test    r13, r13
0x14002c7c9  jz      short loc_14002C7CF
0x14002c7cb  mov     [r13+0], r12d
0x14002c7cf  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x14002c7d4  test    eax, eax
0x14002c7d6  jz      short loc_14002C827
0x14002c7d8  mov     dword ptr [rsp+510h+var_4E8], 0FFFFFFFFh
0x14002c7e0  xor     r9d, r9d
0x14002c7e3  lea     rbx, ?c_szRegSkipQuorumSignatureChecks@@3QB_WB; "SkipQuorumSignatureChecks"
0x14002c7ea  mov     r8, rbx
0x14002c7ed  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002c7f4  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x14002c7f9  test    eax, eax
0x14002c7fb  jz      short loc_14002C827
0x14002c7fd  mov     r12b, 1
0x14002c800  mov     qword ptr [rsp+510h+var_4E0], rbx
0x14002c805  lea     rax, aUsingTestOverr; "Using test override : %ws"
0x14002c80c  mov     [rsp+510h+var_4E8], rax
0x14002c811  xor     ecx, ecx
0x14002c813  mov     qword ptr [rsp+510h+var_4F0], rcx; int
0x14002c818  xor     edx, edx
0x14002c81a  lea     r9d, [rcx+4]
0x14002c81e  lea     r8d, [rcx+20h]
0x14002c822  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002c827  lea     rdx, [rbp+410h+lpMem]
0x14002c82b  mov     rcx, rdi
0x14002c82e  call    ?ReadFileToSafeByteBuffer@@YAJPEB_WPEAV?$CSafeBuffer@E@@@Z; ReadFileToSafeByteBuffer(wchar_t const *,CSafeBuffer<uchar> *)
0x14002c833  mov     ebx, eax
0x14002c835  test    eax, eax
0x14002c837  js      loc_14002CB45
0x14002c83d  lea     r8, [rsp+510h+var_4B0]; struct DualSubCAIdentity *
0x14002c842  mov     rcx, rdi; wchar_t *
0x14002c845  call    ?VerifyInfraCAB@@YAJPEB_W0PEAUDualSubCAIdentity@@@Z; VerifyInfraCAB(wchar_t const *,wchar_t const *,DualSubCAIdentity *)
0x14002c84a  mov     ebx, eax
0x14002c84c  test    eax, eax
0x14002c84e  js      loc_14002CB45
0x14002c854  lea     rax, [rsp+510h+var_498]
0x14002c859  mov     [rsp+510h+var_4E8], rax
0x14002c85e  lea     rdx, [rbp+410h+var_480]
0x14002c862  lea     rcx, [rbp+410h+lpMem]
0x14002c866  call    ?DecompressCabFile@@YAJAEAV?$CSafeBuffer@E@@PEAPEBDKHPEAXPEAPEAV?$CSusListIterator@VCOutputMemoryFile@@@@@Z; DecompressCabFile(CSafeBuffer<uchar> &,char const * *,ulong,int,void *,CSusListIterator<COutputMemoryFile> * *)
0x14002c86b  mov     ebx, eax
0x14002c86d  xor     r9d, r9d
0x14002c870  mov     r15, [rsp+510h+var_498]
0x14002c875  test    eax, eax
0x14002c877  js      loc_14002CB45
0x14002c87d  mov     rax, [r15+8]
0x14002c881  mov     [r15+20h], rax
0x14002c885  mov     rsi, rax
0x14002c888  test    rax, rax
0x14002c88b  jnz     short loc_14002C8B9
0x14002c88d  lea     rax, aCabDoesNotCont_0; "Cab does not contain correct inner CAB "...
0x14002c894  mov     [rsp+510h+var_4E8], rax
0x14002c899  mov     qword ptr [rsp+510h+var_4F0], r9
0x14002c89e  xor     edx, edx
0x14002c8a0  xor     ecx, ecx
0x14002c8a2  lea     r9d, [rdx+5]
0x14002c8a6  lea     r8d, [rdx+20h]
0x14002c8aa  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002c8af  mov     ebx, 8024004Dh
0x14002c8b4  jmp     loc_14002CB45
0x14002c8b9  mov     r8d, 104h
0x14002c8bf  mov     edx, r8d
0x14002c8c2  lea     rcx, [rbp+410h+PathName]
0x14002c8c6  lea     rax, [rbp+410h+PathName]
0x14002c8ca  sub     rdi, rax
0x14002c8cd  lea     rax, [rdx+7FFFFEFAh]
0x14002c8d4  test    rax, rax
0x14002c8d7  jz      short loc_14002C8EF
0x14002c8d9  movzx   eax, word ptr [rcx+rdi]
0x14002c8dd  test    ax, ax
0x14002c8e0  jz      short loc_14002C8EF
0x14002c8e2  mov     [rcx], ax
0x14002c8e5  add     rcx, 2
0x14002c8e9  sub     rdx, 1
0x14002c8ed  jnz     short loc_14002C8CD
0x14002c8ef  lea     rax, [rcx-2]
0x14002c8f3  test    rdx, rdx
0x14002c8f6  cmovnz  rax, rcx
0x14002c8fa  mov     [rax], r9w
0x14002c8fe  mov     rax, rdx
0x14002c901  neg     rax
0x14002c904  sbb     ebx, ebx
0x14002c906  not     ebx
0x14002c908  and     ebx, 8007007Ah
0x14002c90e  test    rdx, rdx
0x14002c911  jz      loc_14002CB45
0x14002c917  mov     rcx, r8
0x14002c91a  lea     rax, [rbp+410h+PathName]
0x14002c91e  cmp     [rax], r9w
0x14002c922  jz      short loc_14002C92E
0x14002c924  add     rax, 2
0x14002c928  sub     rcx, 1
0x14002c92c  jnz     short loc_14002C91E
0x14002c92e  mov     rax, rcx
0x14002c931  sub     r8, rcx
0x14002c934  neg     rax
0x14002c937  sbb     rdx, rdx
0x14002c93a  and     rdx, r8
0x14002c93d  test    rcx, rcx
0x14002c940  jnz     short loc_14002C967
0x14002c942  mov     rcx, [rbp+418h]; this
0x14002c949  mov     ebx, 80070057h
0x14002c94e  mov     r9d, ebx; char *
0x14002c951  lea     r8, aCW1SSrcClientL_35; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14002c958  mov     edx, 5A5h; void *
0x14002c95d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002c962  jmp     loc_14002CB45
0x14002c967  lea     rax, [rbp+410h+PathName]
0x14002c96b  lea     rax, [rax+rdx*2]
0x14002c96f  jmp     short loc_14002C989
0x14002c971  mov     ecx, 5Ch ; '\'
0x14002c976  cmp     cx, [rax]
0x14002c979  jz      short loc_14002C9A2
0x14002c97b  mov     ecx, 2Fh ; '/'
0x14002c980  cmp     cx, [rax]
0x14002c983  jz      short loc_14002C992
0x14002c985  sub     rax, 2
0x14002c989  lea     rcx, [rbp+410h+PathName]
0x14002c98d  cmp     rax, rcx
0x14002c990  ja      short loc_14002C971
0x14002c992  lea     rcx, [rbp+410h+PathName]
0x14002c996  cmp     rax, rcx
0x14002c999  jnz     short loc_14002C9A2
0x14002c99b  mov     [rbp+410h+PathName], r9w
0x14002c9a0  jmp     short loc_14002C9A7
0x14002c9a2  mov     [rax+2], r9w
0x14002c9a7  lea     r9, [rbp+410h+TempFileName]; lpTempFileName
0x14002c9ae  xor     r8d, r8d; uUnique
0x14002c9b1  lea     rdx, PrefixString; "TMP"
0x14002c9b8  lea     rcx, [rbp+410h+PathName]; lpPathName
0x14002c9bc  call    cs:__imp_GetTempFileNameW
0x14002c9c2  test    eax, eax
0x14002c9c4  jnz     short loc_14002C9FE
0x14002c9c6  call    cs:__imp_GetLastError
0x14002c9cc  movzx   ecx, ax
0x14002c9cf  mov     edi, 80070000h
0x14002c9d4  or      ecx, edi
0x14002c9d6  test    eax, eax
0x14002c9d8  cmovle  ecx, eax
0x14002c9db  test    ecx, ecx
0x14002c9dd  jns     short loc_14002C9F4
0x14002c9df  call    cs:__imp_GetLastError
0x14002c9e5  movzx   ebx, ax
0x14002c9e8  or      ebx, edi
0x14002c9ea  test    eax, eax
0x14002c9ec  cmovle  ebx, eax
0x14002c9ef  jmp     loc_14002CB45
0x14002c9f4  mov     ebx, 80004005h
0x14002c9f9  jmp     loc_14002CB45
0x14002c9fe  mov     [rsp+510h+var_4D8], 4000100h; unsigned int
0x14002ca06  mov     [rsp+510h+var_4E0], 2; unsigned int
0x14002ca0e  mov     [rsp+510h+var_4F0], 7; unsigned int
0x14002ca16  mov     r9d, 80000000h; unsigned int
0x14002ca1c  lea     r8, [rbp+410h+TempFileName]; wchar_t *
0x14002ca23  xor     edx, edx; unsigned int
0x14002ca25  lea     rcx, [rbp+410h+hObject]; void **
0x14002ca29  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x14002ca2e  mov     ebx, eax
0x14002ca30  test    eax, eax
0x14002ca32  js      loc_14002CB45
0x14002ca38  mov     rdx, [rsi+10h]
0x14002ca3c  mov     r8d, [rdx+14h]; unsigned int
0x14002ca40  mov     rdx, [rdx+8]; void *
0x14002ca44  lea     rcx, [rbp+410h+TempFileName]; wchar_t *
0x14002ca4b  call    ?WriteBufferToFile@@YAJPEB_WPEAXKH@Z; WriteBufferToFile(wchar_t const *,void *,ulong,int)
0x14002ca50  mov     ebx, eax
0x14002ca52  test    eax, eax
0x14002ca54  js      loc_14002CB45
0x14002ca5a  lea     r8, [rsp+510h+var_4C0]; struct DualSubCAIdentity *
0x14002ca5f  lea     rcx, [rbp+410h+TempFileName]; wchar_t *
0x14002ca66  call    ?VerifyInfraCAB@@YAJPEB_W0PEAUDualSubCAIdentity@@@Z; VerifyInfraCAB(wchar_t const *,wchar_t const *,DualSubCAIdentity *)
0x14002ca6b  mov     ebx, eax
0x14002ca6d  test    eax, eax
0x14002ca6f  js      loc_14002CB45
0x14002ca75  test    r12b, r12b
0x14002ca78  jnz     short loc_14002CAA6
0x14002ca7a  mov     cl, byte ptr [rsp+510h+var_4A8]
0x14002ca7e  cmp     cl, byte ptr [rsp+510h+var_4B8]
0x14002ca82  jz      short loc_14002CA8E
0x14002ca84  mov     ebx, 8024B303h
0x14002ca89  jmp     loc_14002CB45
0x14002ca8e  mov     eax, dword ptr [rsp+510h+var_4C0]
0x14002ca92  cmp     dword ptr [rsp+510h+var_4B0], eax
0x14002ca96  jz      short loc_14002CA84
0x14002ca98  test    cl, cl
0x14002ca9a  jz      short loc_14002CAA6
0x14002ca9c  mov     eax, [rsp+510h+var_4BC]
0x14002caa0  cmp     [rsp+510h+var_4AC], eax
0x14002caa4  jz      short loc_14002CA84
0x14002caa6  lea     rax, [rsp+510h+var_4A0]
0x14002caab  mov     [rsp+510h+var_4E8], rax
0x14002cab0  lea     rdx, [rbp+410h+var_478]
0x14002cab4  mov     rcx, [rsi+10h]
0x14002cab8  call    ?DecompressCabFile@@YAJAEAV?$CSafeBuffer@E@@PEAPEBDKHPEAXPEAPEAV?$CSusListIterator@VCOutputMemoryFile@@@@@Z; DecompressCabFile(CSafeBuffer<uchar> &,char const * *,ulong,int,void *,CSusListIterator<COutputMemoryFile> * *)
0x14002cabd  mov     ebx, eax
0x14002cabf  xor     r9d, r9d
0x14002cac2  mov     r14, [rsp+510h+var_4A0]
0x14002cac7  test    eax, eax
0x14002cac9  js      short loc_14002CB45
0x14002cacb  mov     rax, [r14+8]
0x14002cacf  mov     [r14+20h], rax
0x14002cad3  mov     rsi, rax
0x14002cad6  test    rax, rax
0x14002cad9  jnz     short loc_14002CAE7
0x14002cadb  lea     rax, aCabDoesNotCont; "Cab does not contain correct XML CAB fi"...
0x14002cae2  jmp     loc_14002C894
0x14002cae7  mov     rcx, [rax+10h]
0x14002caeb  mov     edi, [rcx+14h]
0x14002caee  mov     r12d, edi
0x14002caf1  cmp     edi, 2
0x14002caf4  jb      short loc_14002CADB
0x14002caf6  lea     edx, [rdi-1]
0x14002caf9  mov     rax, [rcx+8]
0x14002cafd  cmp     [rdx+rax], r9b
0x14002cb01  jz      short loc_14002CB21
0x14002cb03  inc     edi
0x14002cb05  mov     edx, edi
0x14002cb07  call    ?resize@?$CSafeBuffer@E@@QEAAJI@Z; CSafeBuffer<uchar>::resize(uint)
0x14002cb0c  mov     ebx, eax
0x14002cb0e  xor     r9d, r9d
0x14002cb11  test    eax, eax
0x14002cb13  js      short loc_14002CB45
0x14002cb15  mov     rax, [rsi+10h]
0x14002cb19  mov     rax, [rax+8]
0x14002cb1d  mov     [r12+rax], r9b
0x14002cb21  mov     rcx, [rsi+10h]
0x14002cb25  mov     rax, [rcx+8]
0x14002cb29  mov     [rcx+8], r9
0x14002cb2d  mov     qword ptr [rcx+10h], 0
0x14002cb35  mov     rcx, [rbp+410h+var_488]
0x14002cb39  mov     [rcx], rax
0x14002cb3c  test    r13, r13
0x14002cb3f  jz      short loc_14002CB45
0x14002cb41  mov     [r13+0], edi
0x14002cb45  mov     edi, 28h ; '('
0x14002cb4a  test    r15, r15
0x14002cb4d  jz      short loc_14002CB61
0x14002cb4f  mov     rcx, r15
0x14002cb52  call    ??1?$CSusListIterator@VCOutputMemoryFile@@@@QEAA@XZ; CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(void)
0x14002cb57  mov     edx, edi; struct std::nothrow_t *
0x14002cb59  mov     rcx, r15; void *
0x14002cb5c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002cb61  test    r14, r14
0x14002cb64  jz      short loc_14002CB79
0x14002cb66  mov     rcx, r14
0x14002cb69  call    ??1?$CSusListIterator@VCOutputMemoryFile@@@@QEAA@XZ; CSusListIterator<COutputMemoryFile>::~CSusListIterator<COutputMemoryFile>(void)
  ... truncated ...
```
