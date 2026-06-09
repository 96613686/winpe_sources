# PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)

- ea: `0x18008f890`
- end: `0x18008fcad`
- name: `?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z`
- size: `1053`
- prototype: `__int64 __fastcall(PrintConfig::CConfigFilePreproc *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004aebc`
- `0x18004b448`
- `0x18008f890`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x1800183a0`
- `0x1800183f8`
- `0x18008f890`
- `0x1801495bc`
- `0x180149ae8`
- `0x1801adb10`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008f919`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18008f919`
- `KERNEL32!CreateFileMappingW` at `0x18008f9d8`
- `KERNEL32!CreateFileMappingW` at `0x18008f9d8`
- `KERNEL32!MapViewOfFile` at `0x18008f9fc`
- `KERNEL32!MapViewOfFile` at `0x18008f9fc`
- `KERNEL32!GetFileSize` at `0x18008f9af`
- `KERNEL32!GetFileSize` at `0x18008f9af`
- `KERNEL32!CreateFileW` at `0x18008f992`
- `KERNEL32!CreateFileW` at `0x18008f992`
- `KERNEL32!CloseHandle` at `0x18008fa0d`
- `KERNEL32!CloseHandle` at `0x18008fa24`
- `KERNEL32!CloseHandle` at `0x18008fa0d`
- `KERNEL32!CloseHandle` at `0x18008fa24`
- `KERNEL32!MultiByteToWideChar` at `0x18008fb96`
- `KERNEL32!MultiByteToWideChar` at `0x18008fb96`

## string_xrefs

- `0x18008f8e2`: `PrintConfig::CConfigFilePreproc::PreProcessFile`
- `0x18008f8fb`: `PrintConfig::CConfigFilePreproc::PreProcessFile`

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
  char *v17; // r12
  char *v18; // rcx
  char *v19; // r15
  char *v20; // rdi
  char *v21; // rax
  unsigned int v22; // edi
  int v23; // r14d
  __int64 v24; // rcx
  char *v25; // r12
  int v26; // ebp
  __int64 v27; // rcx
  unsigned int v28; // ebp
  char *v29; // r13
  unsigned int v30; // ebp
  const CHAR *v31; // r8
  unsigned int v32; // ebp
  _BYTE *i; // rax
  int v34; // r13d
  const unsigned __int8 *v35; // rdi
  unsigned int v36; // r8d
  int v38; // [rsp+44h] [rbp-284h] BYREF
  __int64 v39; // [rsp+48h] [rbp-280h]
  char *v40; // [rsp+50h] [rbp-278h]
  char *v41; // [rsp+58h] [rbp-270h]
  __int64 v42; // [rsp+60h] [rbp-268h]
  wchar_t Str[264]; // [rsp+70h] [rbp-258h] BYREF

  v42 = -2;
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
    v40 = 0;
    v19 = 0;
    v12 = -1;
  }
  else
  {
    if ( v9 )
      v4 = (const wchar_t *)v8;
    FileW = CreateFileW(v4, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v12 = (__int64)FileW;
    v39 = (__int64)FileW;
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
          v17 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          v40 = v17;
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
    v40 = 0;
  }
  v39 = v12;
  v18 = 0;
  v10 = -2147467259;
LABEL_18:
  v41 = v18;
  v38 = 0;
  if ( v10 < 0 )
    goto LABEL_62;
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
          goto LABEL_52;
        break;
      }
    }
    v25 = &v19[(unsigned int)v24];
    if ( !v25 )
      goto LABEL_52;
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
LABEL_42:
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
            }
          }
        }
      }
      goto LABEL_52;
    }
LABEL_41:
    if ( (_DWORD)v27 != v28 )
      goto LABEL_42;
LABEL_52:
    if ( v10 >= 0 && !v23 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, int *))(**(_QWORD **)this + 32LL))(
              *(_QWORD *)this,
              v19,
              v22,
              &v38);
      if ( v10 >= 0 )
        *((_DWORD *)this + 4) = ComputeCrc32Checksum(v19, v22, *((unsigned int *)this + 4));
    }
    v19 += v22;
    v18 = v41;
  }
  while ( v10 >= 0 );
  v12 = v39;
  if ( v10 >= 0 )
  {
    v34 = 2;
    v35 = "\r\n";
    v10 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int8 *, __int64, int *))(**(_QWORD **)this + 32LL))(
            *(_QWORD *)this,
            "\r\n",
            2,
            &v38);
    if ( v10 >= 0 )
    {
      v36 = *((_DWORD *)this + 4);
      do
      {
        v36 = *((_DWORD *)qword_18020C030 + (unsigned __int8)(v36 ^ *v35++)) ^ (v36 >> 8);
        --v34;
      }
      while ( v34 );
      *((_DWORD *)this + 4) = v36;
    }
  }
LABEL_62:
  if ( v40 )
    UnmapFileFromMemory(v40, v12);
  --*((_DWORD *)this + 5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008f890  mov     rax, rsp
0x18008f893  push    rbp
0x18008f894  push    rsi
0x18008f895  push    rdi
0x18008f896  push    r12
0x18008f898  push    r13
0x18008f89a  push    r14
0x18008f89c  push    r15
0x18008f89e  sub     rsp, 290h
0x18008f8a5  mov     [rsp+2C8h+var_268], 0FFFFFFFFFFFFFFFEh
0x18008f8ae  mov     [rax+20h], rbx
0x18008f8b2  mov     rax, cs:__security_cookie
0x18008f8b9  xor     rax, rsp
0x18008f8bc  mov     [rsp+2C8h+var_48], rax
0x18008f8c4  mov     bl, r8b
0x18008f8c7  mov     [rsp+2C8h+var_288], bl
0x18008f8cb  mov     rdi, rdx
0x18008f8ce  mov     rsi, rcx
0x18008f8d1  inc     dword ptr [rcx+14h]
0x18008f8d4  mov     r9d, [rcx+14h]
0x18008f8d8  mov     r8, rdx
0x18008f8db  lea     rdx, aFilenameWsNest; "fileName=%ws, nestLevel=%d"
0x18008f8e2  lea     rcx, aPrintconfigCco_16; "PrintConfig::CConfigFilePreproc::PrePro"...
0x18008f8e9  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008f8ee  cmp     dword ptr [rsi+14h], 10h
0x18008f8f2  jbe     short loc_18008F911
0x18008f8f4  lea     rdx, aPreprocessfile; "PreProcessFile MAX_NESTED_INCLUDE_DEPTH"...
0x18008f8fb  lea     rcx, aPrintconfigCco_16; "PrintConfig::CConfigFilePreproc::PrePro"...
0x18008f902  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18008f907  mov     eax, 80004005h
0x18008f90c  jmp     loc_18008FC82
0x18008f911  mov     edx, 5Ch ; '\'; Ch
0x18008f916  mov     rcx, rdi; Str
0x18008f919  call    cs:__imp_wcsrchr
0x18008f91f  test    rax, rax
0x18008f922  jnz     short loc_18008F950
0x18008f924  mov     rcx, [rsi+8]
0x18008f928  mov     rax, [rcx]
0x18008f92b  mov     r8b, bl
0x18008f92e  mov     rdx, rdi
0x18008f931  mov     rax, [rax]
0x18008f934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f939  mov     edx, 1
0x18008f93e  mov     rcx, rax
0x18008f941  neg     rcx
0x18008f944  sbb     ebx, ebx
0x18008f946  not     ebx
0x18008f948  and     ebx, 80070002h
0x18008f94e  jmp     short loc_18008F956
0x18008f950  xor     ebx, ebx
0x18008f952  xor     edx, edx
0x18008f954  xor     eax, eax
0x18008f956  mov     r13d, 2
0x18008f95c  test    ebx, ebx
0x18008f95e  js      loc_18008FA38
0x18008f964  test    edx, edx
0x18008f966  cmovnz  rdi, rax
0x18008f96a  mov     [rsp+2C8h+hTemplateFile], 0; hTemplateFile
0x18008f973  mov     [rsp+2C8h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18008f97b  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x18008f983  xor     r9d, r9d; lpSecurityAttributes
0x18008f986  mov     edx, 80000000h; dwDesiredAccess
0x18008f98b  lea     r8d, [r13-1]; dwShareMode
0x18008f98f  mov     rcx, rdi; lpFileName
0x18008f992  call    cs:__imp_CreateFileW
0x18008f998  mov     r14, rax
0x18008f99b  mov     [rsp+2C8h+var_280], rax
0x18008f9a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008f9a4  jz      loc_18008FA2E
0x18008f9aa  xor     edx, edx; lpFileSizeHigh
0x18008f9ac  mov     rcx, rax; hFile
0x18008f9af  call    cs:__imp_GetFileSize
0x18008f9b5  mov     ebp, eax
0x18008f9b7  cmp     eax, 0FFFFFFFFh
0x18008f9ba  jz      short loc_18008FA21
0x18008f9bc  mov     qword ptr [rsp+2C8h+dwFlagsAndAttributes], 0; lpName
0x18008f9c5  mov     [rsp+2C8h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18008f9cd  xor     r9d, r9d; dwMaximumSizeHigh
0x18008f9d0  mov     r8d, r13d; flProtect
0x18008f9d3  xor     edx, edx; lpFileMappingAttributes
0x18008f9d5  mov     rcx, r14; hFile
0x18008f9d8  call    cs:__imp_CreateFileMappingW
0x18008f9de  mov     rdi, rax
0x18008f9e1  test    rax, rax
0x18008f9e4  jz      short loc_18008FA21
0x18008f9e6  mov     qword ptr [rsp+2C8h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18008f9ef  xor     r9d, r9d; dwFileOffsetLow
0x18008f9f2  xor     r8d, r8d; dwFileOffsetHigh
0x18008f9f5  lea     edx, [r13+2]; dwDesiredAccess
0x18008f9f9  mov     rcx, rax; hFileMappingObject
0x18008f9fc  call    cs:__imp_MapViewOfFile
0x18008fa02  mov     r12, rax
0x18008fa05  mov     [rsp+2C8h+var_278], rax
0x18008fa0a  mov     rcx, rdi; hObject
0x18008fa0d  call    cs:__imp_CloseHandle
0x18008fa13  test    r12, r12
0x18008fa16  jz      short loc_18008FA21
0x18008fa18  lea     rcx, [r12+rbp]
0x18008fa1c  mov     r15, r12
0x18008fa1f  jmp     short loc_18008FA54
0x18008fa21  mov     rcx, r14; hObject
0x18008fa24  call    cs:__imp_CloseHandle
0x18008fa2a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008fa2e  xor     r15d, r15d
0x18008fa31  mov     [rsp+2C8h+var_278], r15
0x18008fa36  jmp     short loc_18008FA48
0x18008fa38  mov     [rsp+2C8h+var_278], 0
0x18008fa41  xor     r15d, r15d
0x18008fa44  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008fa48  mov     [rsp+2C8h+var_280], r14
0x18008fa4d  xor     ecx, ecx
0x18008fa4f  mov     ebx, 80004005h
0x18008fa54  mov     [rsp+2C8h+var_270], rcx
0x18008fa59  mov     [rsp+2C8h+var_284], 0
0x18008fa61  test    ebx, ebx
0x18008fa63  js      loc_18008FC68
0x18008fa69  mov     rdi, r15
0x18008fa6c  cmp     r15, rcx
0x18008fa6f  jnb     short loc_18008FA9F
0x18008fa71  cmp     byte ptr [rdi], 0Ah
0x18008fa74  jz      short loc_18008FA85
0x18008fa76  cmp     byte ptr [rdi], 0Dh
0x18008fa79  jz      short loc_18008FA85
0x18008fa7b  inc     rdi
0x18008fa7e  cmp     rdi, rcx
0x18008fa81  jb      short loc_18008FA71
0x18008fa83  jmp     short loc_18008FA9F
0x18008fa85  lea     rax, [rdi+1]
0x18008fa89  mov     rdi, rax
0x18008fa8c  cmp     rax, rcx
0x18008fa8f  jnb     short loc_18008FA9F
0x18008fa91  cmp     byte ptr [rax], 0Ah
0x18008fa94  jz      short loc_18008FA9B
0x18008fa96  cmp     byte ptr [rax], 0Dh
0x18008fa99  jnz     short loc_18008FA9F
0x18008fa9b  lea     rdi, [rax+1]
0x18008fa9f  sub     edi, r15d
0x18008faa2  jz      loc_18008FC06
0x18008faa8  xor     r14d, r14d
0x18008faab  xor     ecx, ecx
0x18008faad  test    edi, edi
0x18008faaf  jz      short loc_18008FACB
0x18008fab1  cmp     byte ptr [rcx+r15], 20h ; ' '
0x18008fab6  jz      short loc_18008FABF
0x18008fab8  cmp     byte ptr [rcx+r15], 9
0x18008fabd  jnz     short loc_18008FACB
0x18008fabf  inc     ecx
0x18008fac1  cmp     ecx, edi
0x18008fac3  jb      short loc_18008FAB1
0x18008fac5  jz      loc_18008FBBA
0x18008facb  mov     r12d, ecx
0x18008face  add     r12, r15
0x18008fad1  jz      loc_18008FBBA
0x18008fad7  mov     ebp, edi
0x18008fad9  sub     ebp, ecx
0x18008fadb  cmp     ebp, 9
0x18008fade  jbe     loc_18008FBBA
0x18008fae4  mov     r8d, 9; MaxCount
0x18008faea  lea     rdx, Str2; "*Include:"
0x18008faf1  mov     rcx, r12; Str1
0x18008faf4  call    strncmp_0
0x18008faf9  test    eax, eax
0x18008fafb  jnz     loc_18008FBBA
0x18008fb01  xor     ecx, ecx
0x18008fb03  add     ebp, 0FFFFFFF7h
0x18008fb06  jz      short loc_18008FB1E
0x18008fb08  cmp     byte ptr [rcx+r12+9], 20h ; ' '
0x18008fb0e  jz      short loc_18008FB18
0x18008fb10  cmp     byte ptr [rcx+r12+9], 9
0x18008fb16  jnz     short loc_18008FB26
0x18008fb18  inc     ecx
0x18008fb1a  cmp     ecx, ebp
0x18008fb1c  jb      short loc_18008FB08
0x18008fb1e  cmp     ecx, ebp
0x18008fb20  jz      loc_18008FBBA
0x18008fb26  mov     r13d, ecx
0x18008fb29  add     r13, 9
0x18008fb2d  add     r13, r12
0x18008fb30  jz      loc_18008FBBA
0x18008fb36  cmp     byte ptr [r13+0], 22h ; '"'
0x18008fb3b  jnz     short loc_18008FBBA
0x18008fb3d  sub     ebp, ecx
0x18008fb3f  cmp     ebp, 2
0x18008fb42  jbe     short loc_18008FBBA
0x18008fb44  xor     edx, edx; Val
0x18008fb46  mov     r8d, 208h; Size
0x18008fb4c  lea     rcx, [rsp+2C8h+Str]; void *
0x18008fb51  call    memset_0
0x18008fb56  lea     r8, [r13+1]; lpMultiByteStr
0x18008fb5a  sub     ebp, 1
0x18008fb5d  mov     rax, r8
0x18008fb60  jz      short loc_18008FB6F
0x18008fb62  cmp     byte ptr [rax], 22h ; '"'
0x18008fb65  jz      short loc_18008FB6F
0x18008fb67  inc     rax
0x18008fb6a  add     ebp, 0FFFFFFFFh
0x18008fb6d  jnz     short loc_18008FB62
0x18008fb6f  test    ebp, ebp
0x18008fb71  jz      short loc_18008FBBA
0x18008fb73  sub     eax, r8d
0x18008fb76  mov     r9d, eax; cbMultiByte
0x18008fb79  cmp     eax, 104h
0x18008fb7e  jnb     short loc_18008FBBA
0x18008fb80  mov     [rsp+2C8h+dwFlagsAndAttributes], 104h; cchWideChar
0x18008fb88  lea     rax, [rsp+2C8h+Str]
0x18008fb8d  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rax; lpWideCharStr
0x18008fb92  xor     edx, edx; dwFlags
0x18008fb94  xor     ecx, ecx; CodePage
0x18008fb96  call    cs:__imp_MultiByteToWideChar
0x18008fb9c  test    eax, eax
0x18008fb9e  jz      short loc_18008FBBA
0x18008fba0  mov     r14d, 1
0x18008fba6  mov     r8b, [rsp+2C8h+var_288]; bool
0x18008fbab  lea     rdx, [rsp+2C8h+Str]; unsigned __int16 *
0x18008fbb0  mov     rcx, rsi; this
0x18008fbb3  call    ?PreProcessFile@CConfigFilePreproc@PrintConfig@@QEAAJPEBG_N@Z; PrintConfig::CConfigFilePreproc::PreProcessFile(ushort const *,bool)
0x18008fbb8  mov     ebx, eax
0x18008fbba  test    ebx, ebx
0x18008fbbc  js      short loc_18008FBF4
0x18008fbbe  test    r14d, r14d
0x18008fbc1  jnz     short loc_18008FBF4
0x18008fbc3  mov     rcx, [rsi]
0x18008fbc6  mov     rax, [rcx]
0x18008fbc9  lea     r9, [rsp+2C8h+var_284]
0x18008fbce  mov     r8d, edi
0x18008fbd1  mov     rdx, r15
0x18008fbd4  mov     rax, [rax+20h]
0x18008fbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fbdd  mov     ebx, eax
0x18008fbdf  test    eax, eax
0x18008fbe1  js      short loc_18008FBF4
0x18008fbe3  mov     r8d, [rsi+10h]
0x18008fbe7  mov     edx, edi
0x18008fbe9  mov     rcx, r15
0x18008fbec  call    ComputeCrc32Checksum
0x18008fbf1  mov     [rsi+10h], eax
0x18008fbf4  mov     eax, edi
0x18008fbf6  add     r15, rax
0x18008fbf9  test    ebx, ebx
0x18008fbfb  mov     rcx, [rsp+2C8h+var_270]
0x18008fc00  jns     loc_18008FA69
0x18008fc06  test    ebx, ebx
0x18008fc08  mov     r14, [rsp+2C8h+var_280]
0x18008fc0d  js      short loc_18008FC68
0x18008fc0f  mov     rcx, [rsi]
0x18008fc12  mov     rax, [rcx]
0x18008fc15  lea     r9, [rsp+2C8h+var_284]
0x18008fc1a  mov     r13d, 2
0x18008fc20  mov     r8d, r13d
0x18008fc23  lea     rdi, asc_1801F1CA4; "\r\n"
0x18008fc2a  mov     rdx, rdi
0x18008fc2d  mov     rax, [rax+20h]
0x18008fc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fc36  mov     ebx, eax
0x18008fc38  test    eax, eax
0x18008fc3a  js      short loc_18008FC68
0x18008fc3c  mov     r8d, [rsi+10h]
0x18008fc40  movzx   ecx, byte ptr [rdi]
0x18008fc43  mov     eax, r8d
0x18008fc46  xor     rcx, rax
0x18008fc49  movzx   eax, cl
0x18008fc4c  lea     rcx, qword_18020C030
0x18008fc53  shr     r8d, 8
0x18008fc57  xor     r8d, [rcx+rax*4]
0x18008fc5b  inc     rdi
0x18008fc5e  add     r13d, 0FFFFFFFFh
0x18008fc62  jnz     short loc_18008FC40
0x18008fc64  mov     [rsi+10h], r8d
0x18008fc68  mov     rax, [rsp+2C8h+var_278]
0x18008fc6d  test    rax, rax
0x18008fc70  jz      short loc_18008FC7D
0x18008fc72  mov     rdx, r14
0x18008fc75  mov     rcx, rax
0x18008fc78  call    UnmapFileFromMemory
0x18008fc7d  dec     dword ptr [rsi+14h]
0x18008fc80  mov     eax, ebx
0x18008fc82  mov     rcx, [rsp+2C8h+var_48]
0x18008fc8a  xor     rcx, rsp; StackCookie
0x18008fc8d  call    __security_check_cookie
0x18008fc92  mov     rbx, [rsp+2C8h+arg_18]
0x18008fc9a  add     rsp, 290h
0x18008fca1  pop     r15
0x18008fca3  pop     r14
0x18008fca5  pop     r13
0x18008fca7  pop     r12
0x18008fca9  pop     rdi
0x18008fcaa  pop     rsi
0x18008fcab  pop     rbp
0x18008fcac  retn
```
