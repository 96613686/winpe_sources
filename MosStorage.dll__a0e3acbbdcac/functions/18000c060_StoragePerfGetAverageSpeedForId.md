# StoragePerfGetAverageSpeedForId

- ea: `0x18000c060`
- end: `0x18000c35d`
- name: `StoragePerfGetAverageSpeedForId`
- size: `765`
- prototype: `__int64 __fastcall(__int64, __int64, long double *, long double *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000c830`

## callees

- `0x180001c80`
- `0x180006100`
- `0x180008690`
- `0x18000c060`
- `0x18000c3dc`
- `0x18000c698`
- `0x18000c708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000c1bd`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000c1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c326`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c326`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c16c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c16c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c1b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000c1b5`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c1aa`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c1aa`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c102`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c102`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c233`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c2a5`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c2fd`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c233`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c2a5`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000c2fd`

## string_xrefs

- `0x18000c295`: `Elapsed time on writes for index %lu is: %lf`
- `0x18000c2ed`: `Elapsed time on reads for index %lu is: %lf`

## pseudocode

```c
__int64 __fastcall StoragePerfGetAverageSpeedForId(__int64 a1, __int64 a2, long double *a3, long double *a4)
{
  int v6; // esi
  __int64 FileW; // rbx
  int Time; // eax
  int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // edi
  signed int LastError; // eax
  int v14; // r8d
  int v15; // ecx
  DWORD TickCount; // eax
  double v17; // xmm6_8
  long double v18; // xmm7_8
  long double v19; // xmm6_8
  unsigned int v20; // esi
  __int64 v22; // [rsp+48h] [rbp-C0h] BYREF
  long double v23; // [rsp+50h] [rbp-B8h] BYREF
  long double v24; // [rsp+58h] [rbp-B0h] BYREF
  long double v25; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+68h] [rbp-A0h]
  __int128 v27; // [rsp+70h] [rbp-98h] BYREF
  __int128 v28; // [rsp+80h] [rbp-88h]
  WCHAR FileName[264]; // [rsp+98h] [rbp-70h] BYREF

  v6 = a2;
  FileW = -1;
  v26 = -1;
  v27 = 0;
  v28 = 0;
  v22 = 0;
  v24 = 0.0;
  v25 = 0.0;
  v23 = 0.0;
  Time = StringCchPrintfW(FileName, 0x104u, L"%s\\MapsPerfTest_%Iu.tmp", a1 + 12, a2);
  if ( Time < 0 )
  {
    v10 = 251;
LABEL_3:
    v11 = ZTraceReportPropagationNoThis(Time, "StoragePerfGetAverageSpeedForId", v10);
LABEL_4:
    v12 = v11;
    goto LABEL_25;
  }
  Time = MosStorageEnsureMapDataDirectoryAndKeepFileHandle((LPCWSTR)(a1 + 12), *(_DWORD *)(a1 + 4) != 0, 0);
  if ( Time < 0 )
  {
    v10 = 254;
    goto LABEL_3;
  }
  Time = StoragePerfGetTime(&v22);
  if ( Time < 0 )
  {
    v10 = 257;
    goto LABEL_3;
  }
  FileW = (__int64)CreateFileW(FileName, 0xC0000000, 0, 0, 2u, 0x24000000u, 0);
  v26 = FileW;
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v14 = 270;
    v15 = LastError;
    goto LABEL_15;
  }
  TickCount = GetTickCount();
  _o_srand(TickCount);
  LOBYTE(v27) = 1;
  *((double *)&v27 + 1) = DOUBLE_2_0;
  LODWORD(v28) = 32;
  *(_QWORD *)((char *)&v28 + 4) = 4;
  Time = StoragePerfTimeElapsed(v22, &v23);
  if ( Time < 0 )
  {
    v10 = 289;
    goto LABEL_3;
  }
  v17 = v23;
  ZTraceHelperNoThis(
    5,
    "StoragePerfGetAverageSpeedForId",
    291,
    "Elapsed time doing setup for index %lu is: %lf",
    v6,
    v23);
  if ( *((double *)&v27 + 1) < v17 )
  {
    v14 = 293;
    v15 = -2147023436;
LABEL_15:
    v11 = ZTraceReportOriginationNoThis(v15, "StoragePerfGetAverageSpeedForId", v14);
    goto LABEL_4;
  }
  Time = StoragePerfGetIoSpeed(StorageWriteFile, FileW, &v27, &v24);
  if ( Time < 0 )
  {
    v10 = 296;
    goto LABEL_3;
  }
  v18 = v24;
  ZTraceHelperNoThis(5, "StoragePerfGetAverageSpeedForId", 298, "Elapsed time on writes for index %lu is: %lf", v6, v24);
  Time = StoragePerfGetIoSpeed(StorageReadFile, FileW, &v27, &v25);
  if ( Time < 0 )
  {
    v10 = 301;
    goto LABEL_3;
  }
  v12 = 0;
  v19 = v25;
  ZTraceHelperNoThis(5, "StoragePerfGetAverageSpeedForId", 303, "Elapsed time on reads for index %lu is: %lf", v6, v25);
  *a4 = v18;
  *a3 = v19;
LABEL_25:
  v20 = 0;
  if ( v12 != -2147023436 )
    v20 = v12;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return v20;
}

```

## disassembly

```asm
0x18000c060  mov     rax, rsp
0x18000c063  push    rbp
0x18000c064  push    rbx
0x18000c065  push    rsi
0x18000c066  push    rdi
0x18000c067  push    r12
0x18000c069  push    r14
0x18000c06b  push    r15
0x18000c06d  lea     rbp, [rax-208h]
0x18000c074  sub     rsp, 2D0h
0x18000c07b  movaps  xmmword ptr [rax-48h], xmm6
0x18000c07f  movaps  xmmword ptr [rax-58h], xmm7
0x18000c083  mov     rax, cs:__security_cookie
0x18000c08a  xor     rax, rsp
0x18000c08d  mov     [rbp+200h+var_60], rax
0x18000c094  mov     r12, r9
0x18000c097  mov     r15, r8
0x18000c09a  mov     rsi, rdx
0x18000c09d  mov     rdi, rcx
0x18000c0a0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c0a4  mov     qword ptr [rsp+300h+var_2A0], rbx
0x18000c0a9  xorps   xmm0, xmm0
0x18000c0ac  movups  [rsp+300h+var_2A0+8], xmm0
0x18000c0b1  movups  xmmword ptr [rsp+300h+var_290+8], xmm0
0x18000c0b6  mov     [rsp+300h+var_2C0], 0
0x18000c0bf  movsd   [rsp+300h+var_2B0], xmm0
0x18000c0c5  movsd   [rsp+300h+var_2A8], xmm0
0x18000c0cb  movsd   [rsp+300h+var_2B8], xmm0
0x18000c0d1  mov     qword ptr [rsp+300h+dwCreationDisposition], rdx
0x18000c0d6  lea     r9, [rcx+0Ch]
0x18000c0da  lea     r8, aSMapsperftestI; "%s\\MapsPerfTest_%Iu.tmp"
0x18000c0e1  mov     edx, 104h; unsigned __int64
0x18000c0e6  lea     rcx, [rbp+200h+FileName]; unsigned __int16 *
0x18000c0ea  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c0ef  test    eax, eax
0x18000c0f1  jns     short loc_18000C10F
0x18000c0f3  mov     r8d, 0FBh
0x18000c0f9  lea     rdx, aStorageperfget; "StoragePerfGetAverageSpeedForId"
0x18000c100  mov     ecx, eax
0x18000c102  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c108  mov     edi, eax
0x18000c10a  jmp     loc_18000C30E
0x18000c10f  cmp     dword ptr [rdi+4], 0
0x18000c113  setnz   dl; bool
0x18000c116  xor     r8d, r8d; void **
0x18000c119  lea     rcx, [rdi+0Ch]; lpFileName
0x18000c11d  call    ?MosStorageEnsureMapDataDirectoryAndKeepFileHandle@@YAJPEBG_NPEAPEAX@Z; MosStorageEnsureMapDataDirectoryAndKeepFileHandle(ushort const *,bool,void * *)
0x18000c122  test    eax, eax
0x18000c124  jns     short loc_18000C12E
0x18000c126  mov     r8d, 0FEh
0x18000c12c  jmp     short loc_18000C0F9
0x18000c12e  lea     rcx, [rsp+300h+var_2C0]
0x18000c133  call    StoragePerfGetTime
0x18000c138  test    eax, eax
0x18000c13a  jns     short loc_18000C144
0x18000c13c  mov     r8d, 101h
0x18000c142  jmp     short loc_18000C0F9
0x18000c144  mov     [rsp+300h+hTemplateFile], 0; hTemplateFile
0x18000c14d  mov     [rsp+300h+dwFlagsAndAttributes], 24000000h; dwFlagsAndAttributes
0x18000c155  mov     [rsp+300h+dwCreationDisposition], 2; dwCreationDisposition
0x18000c15d  xor     r9d, r9d; lpSecurityAttributes
0x18000c160  xor     r8d, r8d; dwShareMode
0x18000c163  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c168  lea     rcx, [rbp+200h+FileName]; lpFileName
0x18000c16c  call    cs:__imp_CreateFileW
0x18000c172  mov     rbx, rax
0x18000c175  mov     qword ptr [rsp+300h+var_2A0], rax
0x18000c17a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c17e  jnz     short loc_18000C1B5
0x18000c180  call    cs:__imp_GetLastError
0x18000c186  test    eax, eax
0x18000c188  jz      short loc_18000C196
0x18000c18a  jle     short loc_18000C19B
0x18000c18c  movzx   eax, ax
0x18000c18f  or      eax, 80070000h
0x18000c194  jmp     short loc_18000C19B
0x18000c196  mov     eax, 80390004h
0x18000c19b  mov     r8d, 10Eh
0x18000c1a1  mov     ecx, eax
0x18000c1a3  lea     rdx, aStorageperfget; "StoragePerfGetAverageSpeedForId"
0x18000c1aa  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c1b0  jmp     loc_18000C108
0x18000c1b5  call    cs:__imp_GetTickCount
0x18000c1bb  mov     ecx, eax
0x18000c1bd  call    cs:__imp__o_srand
0x18000c1c3  mov     byte ptr [rsp+300h+var_2A0+8], 1
0x18000c1c8  movsd   xmm0, cs:__real@4000000000000000
0x18000c1d0  movsd   qword ptr [rsp+300h+var_290], xmm0
0x18000c1d6  mov     dword ptr [rsp+300h+var_290+8], 20h ; ' '
0x18000c1de  mov     qword ptr [rsp+300h+var_290+0Ch], 4
0x18000c1e7  lea     rdx, [rsp+300h+var_2B8]
0x18000c1ec  mov     rcx, [rsp+300h+var_2C0]
0x18000c1f1  call    StoragePerfTimeElapsed
0x18000c1f6  lea     rdx, aStorageperfget; "StoragePerfGetAverageSpeedForId"
0x18000c1fd  test    eax, eax
0x18000c1ff  jns     short loc_18000C20C
0x18000c201  mov     r8d, 121h
0x18000c207  jmp     loc_18000C100
0x18000c20c  movsd   xmm6, [rsp+300h+var_2B8]
0x18000c212  movsd   qword ptr [rsp+300h+dwFlagsAndAttributes], xmm6
0x18000c218  mov     qword ptr [rsp+300h+dwCreationDisposition], rsi
0x18000c21d  lea     r9, aElapsedTimeDoi; "Elapsed time doing setup for index %lu "...
0x18000c224  mov     r8d, 123h
0x18000c22a  mov     r14d, 5
0x18000c230  mov     ecx, r14d
0x18000c233  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000c239  movsd   xmm0, qword ptr [rsp+300h+var_290]
0x18000c23f  comisd  xmm0, xmm6
0x18000c243  jnb     short loc_18000C255
0x18000c245  mov     r8d, 125h
0x18000c24b  mov     ecx, 800705B4h
0x18000c250  jmp     loc_18000C1A3
0x18000c255  lea     r9, [rsp+300h+var_2B0]
0x18000c25a  lea     r8, [rsp+300h+var_2A0+8]
0x18000c25f  mov     rdx, rbx
0x18000c262  lea     rcx, StorageWriteFile
0x18000c269  call    StoragePerfGetIoSpeed
0x18000c26e  lea     rdx, aStorageperfget; "StoragePerfGetAverageSpeedForId"
0x18000c275  test    eax, eax
0x18000c277  jns     short loc_18000C284
0x18000c279  mov     r8d, 128h
0x18000c27f  jmp     loc_18000C100
0x18000c284  movsd   xmm7, [rsp+300h+var_2B0]
0x18000c28a  movsd   qword ptr [rsp+300h+dwFlagsAndAttributes], xmm7
0x18000c290  mov     qword ptr [rsp+300h+dwCreationDisposition], rsi
0x18000c295  lea     r9, aElapsedTimeOnW; "Elapsed time on writes for index %lu is"...
0x18000c29c  mov     r8d, 12Ah
0x18000c2a2  mov     ecx, r14d
0x18000c2a5  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000c2ab  lea     r9, [rsp+300h+var_2A8]
0x18000c2b0  lea     r8, [rsp+300h+var_2A0+8]
0x18000c2b5  mov     rdx, rbx
0x18000c2b8  lea     rcx, StorageReadFile
0x18000c2bf  call    StoragePerfGetIoSpeed
0x18000c2c4  lea     rdx, aStorageperfget; "StoragePerfGetAverageSpeedForId"
0x18000c2cb  test    eax, eax
0x18000c2cd  jns     short loc_18000C2DA
0x18000c2cf  mov     r8d, 12Dh
0x18000c2d5  jmp     loc_18000C100
0x18000c2da  xor     edi, edi
0x18000c2dc  movsd   xmm6, [rsp+300h+var_2A8]
0x18000c2e2  movsd   qword ptr [rsp+300h+dwFlagsAndAttributes], xmm6
0x18000c2e8  mov     qword ptr [rsp+300h+dwCreationDisposition], rsi
0x18000c2ed  lea     r9, aElapsedTimeOnR; "Elapsed time on reads for index %lu is:"...
0x18000c2f4  mov     r8d, 12Fh
0x18000c2fa  mov     ecx, r14d
0x18000c2fd  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x18000c303  movsd   qword ptr [r12], xmm7
0x18000c309  movsd   qword ptr [r15], xmm6
0x18000c30e  xor     esi, esi
0x18000c310  cmp     edi, 800705B4h
0x18000c316  cmovnz  esi, edi
0x18000c319  lea     rcx, [rbx-1]
0x18000c31d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c321  ja      short loc_18000C32C
0x18000c323  mov     rcx, rbx; hObject
0x18000c326  call    cs:__imp_CloseHandle
0x18000c32c  mov     eax, esi
0x18000c32e  mov     rcx, [rbp+200h+var_60]
0x18000c335  xor     rcx, rsp; StackCookie
0x18000c338  call    __security_check_cookie
0x18000c33d  lea     r11, [rsp+300h+var_30]
0x18000c345  movaps  xmm6, xmmword ptr [r11-10h]
0x18000c34a  movaps  xmm7, xmmword ptr [r11-20h]
0x18000c34f  mov     rsp, r11
0x18000c352  pop     r15
0x18000c354  pop     r14
0x18000c356  pop     r12
0x18000c358  pop     rdi
0x18000c359  pop     rsi
0x18000c35a  pop     rbx
0x18000c35b  pop     rbp
0x18000c35c  retn
```
