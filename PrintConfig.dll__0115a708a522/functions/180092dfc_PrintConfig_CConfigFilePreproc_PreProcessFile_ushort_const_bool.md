# PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)

- ea: `0x180092dfc`
- end: `0x180093226`
- name: `?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z`
- size: `1066`
- prototype: `__int64 __fastcall(PrintConfig::CConfigFilePreproc *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004ce04`
- `0x18004d3dc`
- `0x180092dfc`

## callees

- `0x180003400`
- `0x180004558`
- `0x180018f00`
- `0x180018f58`
- `0x180092dfc`
- `0x1801502f4`
- `0x180150854`
- `0x1801b5680`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180092e85`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180092e85`
- `KERNEL32!CreateFileMappingW` at `0x180092f4c`
- `KERNEL32!CreateFileMappingW` at `0x180092f4c`
- `KERNEL32!MapViewOfFile` at `0x180092f76`
- `KERNEL32!MapViewOfFile` at `0x180092f76`
- `KERNEL32!GetFileSize` at `0x180092f1c`
- `KERNEL32!GetFileSize` at `0x180092f1c`
- `KERNEL32!CreateFileW` at `0x180092efe`
- `KERNEL32!CreateFileW` at `0x180092efe`
- `KERNEL32!CloseHandle` at `0x180092f8d`
- `KERNEL32!CloseHandle` at `0x180092faa`
- `KERNEL32!CloseHandle` at `0x180092f8d`
- `KERNEL32!CloseHandle` at `0x180092faa`
- `KERNEL32!MultiByteToWideChar` at `0x180093125`
- `KERNEL32!MultiByteToWideChar` at `0x180093125`

## string_xrefs

- `0x180092e4e`: `PrintConfig::CConfigFilePreproc::PreProcessFile`
- `0x180092e67`: `PrintConfig::CConfigFilePreproc::PreProcessFile`

## pseudocode

```c
__int64 __fastcall PrintConfig::CConfigFilePreproc::PreProcessFile(
        PrintConfig::CConfigFilePreproc *this,
        const unsigned __int16 *a2,
        bool a3)
{
  const wchar_t *v4; // rdi
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // edx
  signed int v10; // ebx
  HANDLE FileW; // rax
  __int64 v12; // r14
  DWORD FileSize; // eax
  __int64 v14; // rbp
  HANDLE FileMappingW; // rax
  void *v16; // rdi
  _BYTE *v17; // r12
  char *v18; // rcx
  char *v19; // r15
  char *v20; // rdi
  char *v21; // rax
  unsigned int v22; // edi
  int v23; // ebp
  __int64 v24; // rcx
  char *v25; // r13
  int v26; // ebp
  __int64 v27; // rcx
  unsigned int v28; // ebp
  char *v29; // r13
  unsigned int v30; // ebp
  const CHAR *v31; // r8
  unsigned int v32; // ebp
  _BYTE *i; // rax
  int v35; // [rsp+48h] [rbp-280h] BYREF
  _BYTE *v36; // [rsp+50h] [rbp-278h]
  char *v37; // [rsp+58h] [rbp-270h]
  __int64 v38; // [rsp+60h] [rbp-268h]
  wchar_t Str[264]; // [rsp+70h] [rbp-258h] BYREF

  v38 = -2;
  v4 = a2;
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "PrintConfig::CConfigFilePreproc::PreProcessFile",
    L"fileName=%ws, nestLevel=%d",
    a2,
    (unsigned int)++*((_DWORD *)this + 5));
  if ( *((_DWORD *)this + 5) > 0x10u )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigFilePreproc::PreProcessFile",
      L"PreProcessFile MAX_NESTED_INCLUDE_DEPTH overflow");
    return 2147500037LL;
  }
  if ( wcsrchr(v4, 0x5Cu) )
  {
    v10 = 0;
    v9 = 0;
    v8 = 0;
  }
  else
  {
    LOBYTE(v7) = a3;
    v8 = (***((__int64 (__fastcall ****)(_QWORD, const wchar_t *, __int64))this + 1))(*((_QWORD *)this + 1), v4, v7);
    v9 = 1;
    v10 = v8 == 0 ? 0x80070002 : 0;
  }
  if ( v10 < 0 )
  {
    v17 = 0;
    v19 = 0;
    v12 = -1;
  }
  else
  {
    if ( v9 )
      v4 = (const wchar_t *)v8;
    FileW = CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v12 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileSize = GetFileSize(FileW, 0);
      v14 = FileSize;
      if ( FileSize != -1 )
      {
        FileMappingW = CreateFileMappingW((HANDLE)v12, 0, 2u, 0, 0, 0);
        v16 = FileMappingW;
        if ( FileMappingW )
        {
          v17 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          v36 = v17;
          CloseHandle(v16);
          if ( v17 )
          {
            v18 = &v17[v14];
            v19 = v17;
            goto LABEL_18;
          }
        }
      }
      CloseHandle((HANDLE)v12);
      v12 = -1;
    }
    v19 = 0;
    v17 = 0;
  }
  v36 = 0;
  v18 = 0;
  v10 = -2147467259;
LABEL_18:
  v37 = v18;
  v35 = 0;
  if ( v10 < 0 )
    goto LABEL_61;
  do
  {
    v20 = v19;
    if ( v19 < v18 )
    {
      while ( *v20 != 10 && *v20 != 13 )
      {
        if ( ++v20 >= v18 )
          goto LABEL_28;
      }
      v21 = v20 + 1;
      LODWORD(v20) = (_DWORD)v20 + 1;
      if ( v21 < v18 && (*v21 == 10 || *v21 == 13) )
        LODWORD(v20) = (_DWORD)v21 + 1;
    }
LABEL_28:
    v22 = (_DWORD)v20 - (_DWORD)v19;
    if ( !v22 )
      break;
    v23 = 0;
    v24 = 0;
    while ( v19[v24] == 32 || v19[v24] == 9 )
    {
      v24 = (unsigned int)(v24 + 1);
      if ( (unsigned int)v24 >= v22 )
      {
        if ( (_DWORD)v24 == v22 )
          goto LABEL_53;
        break;
      }
    }
    v25 = &v19[(unsigned int)v24];
    if ( !v25 )
      goto LABEL_53;
    v26 = v22 - v24;
    if ( v22 - (unsigned int)v24 <= 9 || strncmp_0(&v19[(unsigned int)v24], "*Include:", 9u) )
      goto LABEL_52;
    v27 = 0;
    v28 = v26 - 9;
    if ( v28 )
    {
      while ( v25[v27 + 9] == 32 || v25[v27 + 9] == 9 )
      {
        v27 = (unsigned int)(v27 + 1);
        if ( (unsigned int)v27 >= v28 )
          goto LABEL_41;
      }
    }
    else
    {
LABEL_41:
      if ( (_DWORD)v27 == v28 )
        goto LABEL_52;
    }
    v29 = &v25[(unsigned int)v27 + 9];
    if ( v29 )
    {
      if ( *v29 == 34 )
      {
        v30 = v28 - v27;
        if ( v30 > 2 )
        {
          memset_0(Str, 0, 0x208u);
          v31 = v29 + 1;
          v32 = v30 - 1;
          for ( i = v29 + 1; v32; --v32 )
          {
            if ( *i == 34 )
              break;
            ++i;
          }
          if ( v32
            && (unsigned int)((_DWORD)i - (_DWORD)v31) < 0x104
            && MultiByteToWideChar(0, 0, v31, (_DWORD)i - (_DWORD)v31, Str, 260) )
          {
            v23 = 1;
            v10 = PrintConfig::CConfigFilePreproc::PreProcessFile(this, Str, a3);
            goto LABEL_53;
          }
        }
      }
    }
LABEL_52:
    v23 = 0;
LABEL_53:
    if ( v10 >= 0 && !v23 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, int *))(**(_QWORD **)this + 32LL))(
              *(_QWORD *)this,
              v19,
              v22,
              &v35);
      if ( v10 >= 0 )
        *((_DWORD *)this + 4) = ComputeCrc32Checksum(v19, v22, *((_DWORD *)this + 4));
    }
    v19 += v22;
    v18 = v37;
  }
  while ( v10 >= 0 );
  v17 = v36;
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, __int64, int *))(**(_QWORD **)this + 32LL))(
            *(_QWORD *)this,
            "\r\n",
            2,
            &v35);
    if ( v10 >= 0 )
      *((_DWORD *)this + 4) = ComputeCrc32Checksum("\r\n", 2, *((_DWORD *)this + 4));
  }
LABEL_61:
  if ( v17 )
    UnmapFileFromMemory(v17, (void *)v12);
  --*((_DWORD *)this + 5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180092dfc  mov     rax, rsp
0x180092dff  push    rbp
0x180092e00  push    rsi
0x180092e01  push    rdi
0x180092e02  push    r12
0x180092e04  push    r13
0x180092e06  push    r14
0x180092e08  push    r15
0x180092e0a  sub     rsp, 290h
0x180092e11  mov     [rsp+2C8h+var_268], 0FFFFFFFFFFFFFFFEh
0x180092e1a  mov     [rax+20h], rbx
0x180092e1e  mov     rax, cs:__security_cookie
0x180092e25  xor     rax, rsp
0x180092e28  mov     [rsp+2C8h+var_48], rax
0x180092e30  mov     bl, r8b
0x180092e33  mov     [rsp+2C8h+var_284], bl
0x180092e37  mov     rdi, rdx
0x180092e3a  mov     rsi, rcx
0x180092e3d  inc     dword ptr [rcx+14h]
0x180092e40  mov     r9d, [rcx+14h]
0x180092e44  mov     r8, rdx
0x180092e47  lea     rdx, aFilenameWsNest; "fileName=%ws, nestLevel=%d"
0x180092e4e  lea     rcx, aPrintconfigCco_16; "PrintConfig::CConfigFilePreproc::PrePro"...
0x180092e55  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180092e5a  cmp     dword ptr [rsi+14h], 10h
0x180092e5e  jbe     short loc_180092E7D
0x180092e60  lea     rdx, aPreprocessfile; "PreProcessFile MAX_NESTED_INCLUDE_DEPTH"...
0x180092e67  lea     rcx, aPrintconfigCco_16; "PrintConfig::CConfigFilePreproc::PrePro"...
0x180092e6e  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180092e73  mov     eax, 80004005h
0x180092e78  jmp     loc_1800931FA
0x180092e7d  mov     edx, 5Ch ; '\'; Ch
0x180092e82  mov     rcx, rdi; Str
0x180092e85  call    cs:__imp_wcsrchr
0x180092e8c  nop     dword ptr [rax+rax+00h]
0x180092e91  test    rax, rax
0x180092e94  jnz     short loc_180092EC2
0x180092e96  mov     rcx, [rsi+8]
0x180092e9a  mov     rax, [rcx]
0x180092e9d  mov     r8b, bl
0x180092ea0  mov     rdx, rdi
0x180092ea3  mov     rax, [rax]
0x180092ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092eab  mov     edx, 1
0x180092eb0  mov     rcx, rax
0x180092eb3  neg     rcx
0x180092eb6  sbb     ebx, ebx
0x180092eb8  not     ebx
0x180092eba  and     ebx, 80070002h
0x180092ec0  jmp     short loc_180092EC8
0x180092ec2  xor     ebx, ebx
0x180092ec4  xor     edx, edx
0x180092ec6  xor     eax, eax
0x180092ec8  test    ebx, ebx
0x180092eca  js      loc_180092FC2
0x180092ed0  test    edx, edx
0x180092ed2  cmovnz  rdi, rax
0x180092ed6  mov     [rsp+2C8h+hTemplateFile], 0; hTemplateFile
0x180092edf  mov     [rsp+2C8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180092ee7  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x180092eef  xor     r9d, r9d; lpSecurityAttributes
0x180092ef2  mov     edx, 80000000h; dwDesiredAccess
0x180092ef7  lea     r8d, [r9+1]; dwShareMode
0x180092efb  mov     rcx, rdi; lpFileName
0x180092efe  call    cs:__imp_CreateFileW
0x180092f05  nop     dword ptr [rax+rax+00h]
0x180092f0a  mov     r14, rax
0x180092f0d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180092f11  jz      loc_180092FBA
0x180092f17  xor     edx, edx; lpFileSizeHigh
0x180092f19  mov     rcx, rax; hFile
0x180092f1c  call    cs:__imp_GetFileSize
0x180092f23  nop     dword ptr [rax+rax+00h]
0x180092f28  mov     ebp, eax
0x180092f2a  cmp     eax, 0FFFFFFFFh
0x180092f2d  jz      short loc_180092FA7
0x180092f2f  mov     qword ptr [rsp+2C8h+dwFlagsAndAttributes], 0; lpName
0x180092f38  mov     [rsp+2C8h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180092f40  xor     r9d, r9d; dwMaximumSizeHigh
0x180092f43  xor     edx, edx; lpFileMappingAttributes
0x180092f45  lea     r8d, [r9+2]; flProtect
0x180092f49  mov     rcx, r14; hFile
0x180092f4c  call    cs:__imp_CreateFileMappingW
0x180092f53  nop     dword ptr [rax+rax+00h]
0x180092f58  mov     rdi, rax
0x180092f5b  test    rax, rax
0x180092f5e  jz      short loc_180092FA7
0x180092f60  mov     qword ptr [rsp+2C8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180092f69  xor     r9d, r9d; dwFileOffsetLow
0x180092f6c  xor     r8d, r8d; dwFileOffsetHigh
0x180092f6f  lea     edx, [r9+4]; dwDesiredAccess
0x180092f73  mov     rcx, rax; hFileMappingObject
0x180092f76  call    cs:__imp_MapViewOfFile
0x180092f7d  nop     dword ptr [rax+rax+00h]
0x180092f82  mov     r12, rax
0x180092f85  mov     [rsp+2C8h+var_278], rax
0x180092f8a  mov     rcx, rdi; hObject
0x180092f8d  call    cs:__imp_CloseHandle
0x180092f94  nop     dword ptr [rax+rax+00h]
0x180092f99  test    r12, r12
0x180092f9c  jz      short loc_180092FA7
0x180092f9e  lea     rcx, [r12+rbp]
0x180092fa2  mov     r15, r12
0x180092fa5  jmp     short loc_180092FD8
0x180092fa7  mov     rcx, r14; hObject
0x180092faa  call    cs:__imp_CloseHandle
0x180092fb1  nop     dword ptr [rax+rax+00h]
0x180092fb6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180092fba  xor     r15d, r15d
0x180092fbd  xor     r12d, r12d
0x180092fc0  jmp     short loc_180092FCC
0x180092fc2  xor     r12d, r12d
0x180092fc5  xor     r15d, r15d
0x180092fc8  or      r14, 0FFFFFFFFFFFFFFFFh
0x180092fcc  mov     [rsp+2C8h+var_278], r12
0x180092fd1  xor     ecx, ecx
0x180092fd3  mov     ebx, 80004005h
0x180092fd8  mov     [rsp+2C8h+var_270], rcx
0x180092fdd  mov     [rsp+2C8h+var_280], 0
0x180092fe5  test    ebx, ebx
0x180092fe7  js      loc_1800931E5
0x180092fed  mov     r12b, [rsp+2C8h+var_284]
0x180092ff2  mov     rdi, r15
0x180092ff5  cmp     r15, rcx
0x180092ff8  jnb     short loc_180093028
0x180092ffa  cmp     byte ptr [rdi], 0Ah
0x180092ffd  jz      short loc_18009300E
0x180092fff  cmp     byte ptr [rdi], 0Dh
0x180093002  jz      short loc_18009300E
0x180093004  inc     rdi
0x180093007  cmp     rdi, rcx
0x18009300a  jb      short loc_180092FFA
0x18009300c  jmp     short loc_180093028
0x18009300e  lea     rax, [rdi+1]
0x180093012  mov     rdi, rax
0x180093015  cmp     rax, rcx
0x180093018  jnb     short loc_180093028
0x18009301a  cmp     byte ptr [rax], 0Ah
0x18009301d  jz      short loc_180093024
0x18009301f  cmp     byte ptr [rax], 0Dh
0x180093022  jnz     short loc_180093028
0x180093024  lea     rdi, [rax+1]
0x180093028  sub     edi, r15d
0x18009302b  jz      loc_18009319D
0x180093031  xor     ebp, ebp
0x180093033  mov     [rsp+2C8h+var_288], ebp
0x180093037  xor     ecx, ecx
0x180093039  test    edi, edi
0x18009303b  jz      short loc_180093057
0x18009303d  cmp     byte ptr [rcx+r15], 20h ; ' '
0x180093042  jz      short loc_18009304B
0x180093044  cmp     byte ptr [rcx+r15], 9
0x180093049  jnz     short loc_180093057
0x18009304b  inc     ecx
0x18009304d  cmp     ecx, edi
0x18009304f  jb      short loc_18009303D
0x180093051  jz      loc_180093152
0x180093057  mov     r13d, ecx
0x18009305a  add     r13, r15
0x18009305d  jz      loc_180093152
0x180093063  mov     ebp, edi
0x180093065  sub     ebp, ecx
0x180093067  cmp     ebp, 9
0x18009306a  jbe     loc_18009314E
0x180093070  mov     r8d, 9; MaxCount
0x180093076  lea     rdx, Str2; "*Include:"
0x18009307d  mov     rcx, r13; Str1
0x180093080  call    strncmp_0
0x180093085  test    eax, eax
0x180093087  jnz     loc_18009314E
0x18009308d  xor     ecx, ecx
0x18009308f  add     ebp, 0FFFFFFF7h
0x180093092  jz      short loc_1800930AA
0x180093094  cmp     byte ptr [rcx+r13+9], 20h ; ' '
0x18009309a  jz      short loc_1800930A4
0x18009309c  cmp     byte ptr [rcx+r13+9], 9
0x1800930a2  jnz     short loc_1800930B2
0x1800930a4  inc     ecx
0x1800930a6  cmp     ecx, ebp
0x1800930a8  jb      short loc_180093094
0x1800930aa  cmp     ecx, ebp
0x1800930ac  jz      loc_18009314E
0x1800930b2  mov     eax, ecx
0x1800930b4  add     r13, 9
0x1800930b8  add     r13, rax
0x1800930bb  jz      loc_18009314E
0x1800930c1  cmp     byte ptr [r13+0], 22h ; '"'
0x1800930c6  jnz     loc_18009314E
0x1800930cc  sub     ebp, ecx
0x1800930ce  cmp     ebp, 2
0x1800930d1  jbe     short loc_18009314E
0x1800930d3  xor     edx, edx; Val
0x1800930d5  mov     r8d, 208h; Size
0x1800930db  lea     rcx, [rsp+2C8h+Str]; void *
0x1800930e0  call    memset_0
0x1800930e5  lea     r8, [r13+1]; lpMultiByteStr
0x1800930e9  sub     ebp, 1
0x1800930ec  mov     rax, r8
0x1800930ef  jz      short loc_1800930FE
0x1800930f1  cmp     byte ptr [rax], 22h ; '"'
0x1800930f4  jz      short loc_1800930FE
0x1800930f6  inc     rax
0x1800930f9  add     ebp, 0FFFFFFFFh
0x1800930fc  jnz     short loc_1800930F1
0x1800930fe  test    ebp, ebp
0x180093100  jz      short loc_18009314E
0x180093102  sub     eax, r8d
0x180093105  mov     r9d, eax; cbMultiByte
0x180093108  cmp     eax, 104h
0x18009310d  jnb     short loc_18009314E
0x18009310f  mov     [rsp+2C8h+dwFlagsAndAttributes], 104h; cchWideChar
0x180093117  lea     rax, [rsp+2C8h+Str]
0x18009311c  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; lpWideCharStr
0x180093121  xor     edx, edx; dwFlags
0x180093123  xor     ecx, ecx; CodePage
0x180093125  call    cs:__imp_MultiByteToWideChar
0x18009312c  nop     dword ptr [rax+rax+00h]
0x180093131  test    eax, eax
0x180093133  jz      short loc_18009314E
0x180093135  mov     ebp, 1
0x18009313a  mov     r8b, r12b; bool
0x18009313d  lea     rdx, [rsp+2C8h+Str]; unsigned __int16 *
0x180093142  mov     rcx, rsi; this
0x180093145  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18009314a  mov     ebx, eax
0x18009314c  jmp     short loc_180093152
0x18009314e  mov     ebp, [rsp+2C8h+var_288]
0x180093152  test    ebx, ebx
0x180093154  js      short loc_18009318B
0x180093156  test    ebp, ebp
0x180093158  jnz     short loc_18009318B
0x18009315a  mov     rcx, [rsi]
0x18009315d  mov     rax, [rcx]
0x180093160  lea     r9, [rsp+2C8h+var_280]
0x180093165  mov     r8d, edi
0x180093168  mov     rdx, r15
0x18009316b  mov     rax, [rax+20h]
0x18009316f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093174  mov     ebx, eax
0x180093176  test    eax, eax
0x180093178  js      short loc_18009318B
0x18009317a  mov     r8d, [rsi+10h]
0x18009317e  mov     edx, edi
0x180093180  mov     rcx, r15
0x180093183  call    ComputeCrc32Checksum
0x180093188  mov     [rsi+10h], eax
0x18009318b  mov     eax, edi
0x18009318d  add     r15, rax
0x180093190  test    ebx, ebx
0x180093192  mov     rcx, [rsp+2C8h+var_270]
0x180093197  jns     loc_180092FF2
0x18009319d  test    ebx, ebx
0x18009319f  mov     r12, [rsp+2C8h+var_278]
0x1800931a4  js      short loc_1800931E5
0x1800931a6  mov     rcx, [rsi]
0x1800931a9  mov     rax, [rcx]
0x1800931ac  lea     r9, [rsp+2C8h+var_280]
0x1800931b1  mov     r8d, 2
0x1800931b7  lea     rdx, asc_1801F9AA4; "\r\n"
0x1800931be  mov     rax, [rax+20h]
0x1800931c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800931c7  mov     ebx, eax
0x1800931c9  test    eax, eax
0x1800931cb  js      short loc_1800931E5
0x1800931cd  mov     r8d, [rsi+10h]
0x1800931d1  mov     edx, 2
0x1800931d6  lea     rcx, asc_1801F9AA4; "\r\n"
0x1800931dd  call    ComputeCrc32Checksum
0x1800931e2  mov     [rsi+10h], eax
0x1800931e5  test    r12, r12
0x1800931e8  jz      short loc_1800931F5
0x1800931ea  mov     rdx, r14
0x1800931ed  mov     rcx, r12
0x1800931f0  call    UnmapFileFromMemory
0x1800931f5  dec     dword ptr [rsi+14h]
0x1800931f8  mov     eax, ebx
0x1800931fa  mov     rcx, [rsp+2C8h+var_48]
0x180093202  xor     rcx, rsp; StackCookie
0x180093205  call    __security_check_cookie
0x18009320a  mov     rbx, [rsp+2C8h+arg_18]
0x180093212  add     rsp, 290h
0x180093219  pop     r15
0x18009321b  pop     r14
0x18009321d  pop     r13
0x18009321f  pop     r12
0x180093221  pop     rdi
0x180093222  pop     rsi
0x180093223  pop     rbp
0x180093224  retn
```
