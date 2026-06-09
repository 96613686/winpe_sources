# TieringPinnedSession::MigratePinnedDatabaseToDscAttribute(void)

- ea: `0x140020390`
- end: `0x140020c65`
- name: `?MigratePinnedDatabaseToDscAttribute@TieringPinnedSession@@QEAAJXZ`
- size: `2261`
- prototype: `__int64 __fastcall(JET_SESID *this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140017120`

## callees

- `0x14000108c`
- `0x140002db0`
- `0x140004ef0`
- `0x140005420`
- `0x140009904`
- `0x140009a04`
- `0x140009c08`
- `0x14000b490`
- `0x14000b7f8`
- `0x14001cd80`
- `0x14001f744`
- `0x140020390`
- `0x140020d74`
- `0x140020f64`
- `0x140021018`
- `0x14003fbb0`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x140020660`
- `ntdll!NtQueryInformationFile` at `0x140020660`
- `ntdll!NtSetInformationFile` at `0x14002070b`
- `ntdll!NtSetInformationFile` at `0x14002070b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400207ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400207ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400206c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400206c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140020a63`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x14002062b`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x14002062b`
- `ESENT!JetMove` at `0x140020436`
- `ESENT!JetMove` at `0x1400208a0`
- `ESENT!JetMove` at `0x140020436`
- `ESENT!JetMove` at `0x1400208a0`

## pseudocode

```c
__int64 __fastcall TieringPinnedSession::MigratePinnedDatabaseToDscAttribute(JET_SESID *this)
{
  PVOID ThreadLocalStoragePointer; // rax
  JET_SESID *v2; // r12
  JET_TABLEID v3; // rdx
  JET_SESID v4; // rcx
  JET_ERR v5; // eax
  JET_ERR v6; // r8d
  int v7; // edi
  int v8; // r13d
  signed int v9; // ebx
  int v10; // eax
  unsigned __int8 v11; // di
  int CurrentPinnedRecord; // eax
  int v13; // r8d
  unsigned __int8 v14; // di
  HANDLE v15; // rax
  unsigned int v16; // r12d
  NTSTATUS v17; // eax
  NTSTATUS v18; // edi
  DWORD v19; // r12d
  __int16 v20; // di
  NTSTATUS v21; // eax
  int v22; // eax
  DWORD LastError; // edx
  int v24; // r8d
  unsigned __int16 v25; // dx
  int v26; // r9d
  int v27; // ecx
  JET_ERR v28; // eax
  int v29; // edi
  int v30; // eax
  int v31; // eax
  __int64 *v32; // rax
  __int64 v33; // rax
  int v34; // ecx
  unsigned __int8 v36[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v37; // [rsp+44h] [rbp-BCh]
  int v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39; // [rsp+4Ch] [rbp-B4h]
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v41; // [rsp+54h] [rbp-ACh] BYREF
  int v42; // [rsp+58h] [rbp-A8h] BYREF
  __int64 FileInformation; // [rsp+60h] [rbp-A0h] BYREF
  TieringPinnedSession *v44; // [rsp+68h] [rbp-98h]
  char v45[8]; // [rsp+70h] [rbp-90h] BYREF
  int v46; // [rsp+78h] [rbp-88h]
  HANDLE hVolumeHint; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  struct FILE_ID_DESCRIPTOR FileId; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 v51; // [rsp+B8h] [rbp-48h] BYREF
  int v52; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v53[2]; // [rsp+CCh] [rbp-34h] BYREF
  int v54; // [rsp+ECh] [rbp-14h]
  char v55[32]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD *v56; // [rsp+110h] [rbp+10h]
  __int64 v57; // [rsp+118h] [rbp+18h]
  __int64 v58; // [rsp+120h] [rbp+20h]
  _DWORD v59[2]; // [rsp+128h] [rbp+28h] BYREF
  int *v60; // [rsp+130h] [rbp+30h]
  __int64 v61; // [rsp+138h] [rbp+38h]
  unsigned __int8 *v62; // [rsp+140h] [rbp+40h]
  __int64 v63; // [rsp+148h] [rbp+48h]
  int *v64; // [rsp+150h] [rbp+50h]
  __int64 v65; // [rsp+158h] [rbp+58h]
  int *v66; // [rsp+160h] [rbp+60h]
  __int64 v67; // [rsp+168h] [rbp+68h]
  unsigned __int16 *v68; // [rsp+170h] [rbp+70h]
  __int64 v69; // [rsp+178h] [rbp+78h]
  int *v70; // [rsp+180h] [rbp+80h]
  __int64 v71; // [rsp+188h] [rbp+88h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v2 = this;
  v44 = (TieringPinnedSession *)this;
  *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL) = "TieringPinnedSession::MigratePinnedDatabaseToDscAttribute";
  CHResultImp::CHResultImp((CHResultImp *)v45);
  v3 = v2[3];
  v4 = v2[1];
  v52 = 0;
  v54 = 0;
  hVolumeHint = 0;
  FileInformation = 0;
  v41 = 5;
  v51 = 0;
  memset(v53, 0, sizeof(v53));
  memset(&FileId, 0, sizeof(FileId));
  IoStatusBlock = 0;
  v5 = JetMove(v4, v3, 0x80000000, 0);
  v6 = v5;
  if ( ((v5 + 1603) & 0xFFFFFFFD) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *(_QWORD *)(v2[5] + 112));
    }
    v46 = 0;
    CHResultImp::~CHResultImp((CHResultImp *)v45);
    return 0;
  }
  v7 = 0;
  v8 = 0;
  v39 = 0;
  v40 = 0;
  if ( v5 )
  {
    if ( v5 == -529 || v5 == -1092 || v5 == -1808 )
    {
      v9 = ATL::AtlHresultFromWin32(0x70u);
    }
    else if ( v5 == -1011 )
    {
      v9 = -2147024882;
    }
    else
    {
      v10 = -v5;
      if ( v10 < 0 )
        LOWORD(v10) = v6;
      v9 = v6 & 0x8E5E0000 | (unsigned __int16)v10 | 0xE5E0000;
    }
    v46 = v9;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *(_QWORD *)(v2[5] + 112),
        v6);
      v8 = 0;
    }
    v11 = 4;
    goto LABEL_111;
  }
  v46 = OpenVolumeHandle(1, (const struct _UNICODE_STRING *)(*(_QWORD *)v2[5] + 672LL), &hVolumeHint, 0x100080u);
  v9 = v46;
  if ( v46 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        *(_DWORD *)v2[5] + 672,
        v46);
      v8 = 0;
    }
    v11 = 5;
    goto LABEL_111;
  }
  v37 = 0;
  v38 = 0;
  v42 = 0;
  v2 = (JET_SESID *)v44;
  while ( 1 )
  {
    v36[0] = 0;
    CurrentPinnedRecord = TieringPinnedSession::GetCurrentPinnedRecord(
                            (TieringPinnedSession *)v2,
                            (struct TE_FILE_ID_128 *)&v51,
                            v36,
                            0);
    v13 = CurrentPinnedRecord;
    if ( CurrentPinnedRecord )
    {
      if ( CurrentPinnedRecord == -529 || CurrentPinnedRecord == -1092 || CurrentPinnedRecord == -1808 )
      {
        v9 = ATL::AtlHresultFromWin32(0x70u);
      }
      else if ( CurrentPinnedRecord == -1011 )
      {
        v9 = -2147024882;
      }
      else
      {
        v31 = -CurrentPinnedRecord;
        if ( v31 < 0 )
          LOWORD(v31) = v13;
        v9 = v13 & 0x8E5E0000 | (unsigned __int16)v31 | 0xE5E0000;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
          v7,
          *(_QWORD *)(v2[5] + 112),
          v13);
      }
      if ( v7 > 0 )
        v9 = 0;
      goto LABEL_88;
    }
    FileId.8 = v51;
    v39 = v7 + 1;
    v14 = v36[0] & 1;
    FileId.dwSize = 24;
    FileId.Type = ExtendedFileIdType;
    v15 = OpenFileById(hVolumeHint, &FileId, 0x180u, 7u, 0, 0x2000000u);
    hObject = v15;
    if ( v15 != (HANDLE)-1LL )
    {
      v16 = v14 + 1;
      v17 = NtQueryInformationFile(v15, &IoStatusBlock, &FileInformation, 8u, FileBothDirectoryInformation|0x40);
      v18 = v17;
      if ( v17 >= 0 )
      {
        if ( (_DWORD)FileInformation != v16
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_DWORD *)v51.ObjectId.Data4,
            v51.FileId.QuadPart,
            *(_QWORD *)(*((_QWORD *)v44 + 5) + 112LL),
            v17);
        }
        goto LABEL_32;
      }
      if ( v17 == -1073740532 )
      {
        FileInformation = v16;
        v21 = NtSetInformationFile(hObject, &IoStatusBlock, &FileInformation, 8u, FileBothDirectoryInformation|0x40);
        v18 = v21;
        if ( v21 >= 0 )
        {
LABEL_32:
          v19 = v37;
LABEL_33:
          CloseHandle(hObject);
          v20 = v38;
          goto LABEL_52;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_DWORD *)v51.ObjectId.Data4,
            v51.FileId.QuadPart,
            *(_QWORD *)(*((_QWORD *)v44 + 5) + 112LL),
            v21);
        }
        v22 = 2;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_iiSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
            *(_DWORD *)v51.ObjectId.Data4,
            v51.FileId.QuadPart,
            *(_QWORD *)(*((_QWORD *)v44 + 5) + 112LL),
            v17);
        }
        v22 = 3;
      }
      v38 = v22;
      v19 = v18;
      v37 = v18;
      goto LABEL_33;
    }
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_iiSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        LastError,
        v24,
        *(_DWORD *)v51.ObjectId.Data4,
        v51.FileId.QuadPart,
        *(_QWORD *)(v2[5] + 112),
        LastError);
    }
    v20 = 1;
    v38 = 1;
    v19 = GetLastError();
    v37 = v19;
LABEL_52:
    if ( v19 )
    {
      v25 = 0;
      if ( v41 )
      {
        v26 = v42;
        do
        {
          if ( v42 == v41 )
            break;
          v27 = *(&v52 + 2 * v25);
          if ( v27 == v19 && *((_WORD *)v53 + 4 * v25) == v20 )
            break;
          if ( !v27 )
          {
            *(&v52 + 2 * v25) = v19;
            v42 = v26 + 1;
            *((_WORD *)v53 + 4 * v25) = v20;
            break;
          }
          ++v25;
        }
        while ( v25 < v41 );
      }
      v37 = 0;
      ++v40;
      v38 = 0;
    }
    v2 = (JET_SESID *)v44;
    do
    {
      v28 = JetMove(v2[1], v2[3], 1, 0);
      v29 = v28;
    }
    while ( v28 == -1017 );
    if ( ((v28 + 1603) & 0xFFFFFFFD) != 0 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
        v39,
        *(_QWORD *)(v2[5] + 112));
    }
    if ( v29 )
    {
      v7 = v39;
      goto LABEL_106;
    }
LABEL_81:
    v7 = v39;
  }
  if ( !v28 )
    goto LABEL_81;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      v39,
      *(_QWORD *)(v2[5] + 112),
      v28);
  }
  if ( v29 == -529 || v29 == -1092 || v29 == -1808 )
  {
    v9 = ATL::AtlHresultFromWin32(0x70u);
  }
  else if ( v29 == -1011 )
  {
    v9 = -2147024882;
  }
  else
  {
    v30 = -v29;
    if ( v29 > 0 )
      LOWORD(v30) = v29;
    v9 = v29 & 0x8E5E0000 | (unsigned __int16)v30 | 0xE5E0000;
  }
  v7 = v39;
  v46 = v9;
  if ( v39 > 0 )
  {
    v9 = 0;
LABEL_88:
    v46 = v9;
  }
LABEL_106:
  CloseHandle(hVolumeHint);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids,
      v7 - v40,
      v7,
      *(_QWORD *)(v2[5] + 112),
      v9);
  }
  v8 = v40;
  v11 = v38;
  if ( v40 > 0 )
  {
LABEL_112:
    if ( (unsigned int)dword_14004C098 > 5
      && (qword_14004C0A8 & 0x200000000000LL) != 0
      && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
    {
      v70 = &v52;
      v40 = v39;
      v32 = (__int64 *)v2[5];
      v68 = &v41;
      v64 = &v40;
      v66 = &v42;
      v62 = v36;
      v42 = v8;
      v36[0] = v11;
      v38 = v9;
      v33 = *v32;
      v56 = v59;
      v60 = &v38;
      v71 = 40;
      v69 = 2;
      v67 = 4;
      v65 = 4;
      v63 = 1;
      v61 = 4;
      v57 = 2;
      v34 = *(unsigned __int16 *)(v33 + 696);
      v58 = *(_QWORD *)(v33 + 704);
      v59[0] = v34;
      v59[1] = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, &unk_140046030, 0, 0, 10, v55);
    }
  }
  else
  {
LABEL_111:
    if ( v9 < 0 )
      goto LABEL_112;
  }
  CHResultImp::~CHResultImp((CHResultImp *)v45);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140020390  push    rbp
0x140020392  push    rbx
0x140020393  push    rsi
0x140020394  push    rdi
0x140020395  push    r12
0x140020397  push    r13
0x140020399  push    r14
0x14002039b  push    r15
0x14002039d  lea     rbp, [rsp-0A8h]
0x1400203a5  sub     rsp, 1A8h
0x1400203ac  mov     rax, cs:__security_cookie
0x1400203b3  xor     rax, rsp
0x1400203b6  mov     [rbp+0E0h+var_50], rax
0x1400203bd  mov     rax, gs:58h
0x1400203c6  mov     r12, rcx
0x1400203c9  mov     [rsp+1E0h+var_178], rcx
0x1400203ce  mov     ecx, 8
0x1400203d3  mov     rdx, [rax]
0x1400203d6  lea     rax, aTieringpinneds_3; "TieringPinnedSession::MigratePinnedData"...
0x1400203dd  mov     [rcx+rdx], rax
0x1400203e1  lea     rcx, [rsp+1E0h+var_170]; this
0x1400203e6  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400203eb  mov     rdx, [r12+18h]; tableid
0x1400203f0  xorps   xmm0, xmm0
0x1400203f3  mov     rcx, [r12+8]; sesid
0x1400203f8  xor     ebx, ebx
0x1400203fa  xor     eax, eax
0x1400203fc  mov     [rbp+0E0h+var_118], ebx
0x1400203ff  mov     [rbp+0E0h+var_F4], eax
0x140020402  xor     r9d, r9d; grbit
0x140020405  mov     r8d, 80000000h; cRow
0x14002040b  mov     [rbp+0E0h+hVolumeHint], rbx
0x14002040f  lea     eax, [rbx+5]
0x140020412  mov     [rsp+1E0h+FileInformation], rbx
0x140020417  mov     [rsp+1E0h+var_18C], ax
0x14002041c  xor     eax, eax
0x14002041e  mov     qword ptr [rbp+0E0h+FileId.8+8], rax
0x140020422  movups  [rbp+0E0h+var_128], xmm0
0x140020426  movups  [rbp+0E0h+var_114], xmm0
0x14002042a  movups  [rbp+0E0h+var_104], xmm0
0x14002042e  movups  xmmword ptr [rbp+0E0h+FileId.dwSize], xmm0
0x140020432  movups  xmmword ptr [rbp+0E0h+IoStatusBlock], xmm0
0x140020436  call    cs:__imp_JetMove
0x14002043c  mov     r8d, eax
0x14002043f  lea     ecx, [rax+643h]
0x140020445  test    ecx, 0FFFFFFFDh
0x14002044b  jz      loc_140020BF2
0x140020451  xor     edi, edi
0x140020453  xor     r13d, r13d
0x140020456  mov     [rsp+1E0h+var_194], edi
0x14002045a  mov     [rsp+1E0h+var_190], r13d
0x14002045f  test    eax, eax
0x140020461  jz      loc_14002050B
0x140020467  cmp     eax, 0FFFFFDEFh
0x14002046c  jz      short loc_1400204A5
0x14002046e  cmp     eax, 0FFFFFBBCh
0x140020473  jz      short loc_1400204A5
0x140020475  cmp     eax, 0FFFFF8F0h
0x14002047a  jz      short loc_1400204A5
0x14002047c  cmp     eax, 0FFFFFC0Dh
0x140020481  jnz     short loc_14002048A
0x140020483  mov     ebx, 8007000Eh
0x140020488  jmp     short loc_1400204B1
0x14002048a  neg     eax
0x14002048c  cmovs   eax, r8d
0x140020490  movzx   ebx, ax
0x140020493  mov     eax, r8d
0x140020496  and     eax, 8E5E0000h
0x14002049b  or      ebx, eax
0x14002049d  or      ebx, 0E5E0000h
0x1400204a3  jmp     short loc_1400204B1
0x1400204a5  mov     ecx, 70h ; 'p'; unsigned int
0x1400204aa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1400204af  mov     ebx, eax
0x1400204b1  mov     [rsp+1E0h+var_168], ebx
0x1400204b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400204bc  lea     r14, WPP_GLOBAL_Control
0x1400204c3  mov     esi, 1
0x1400204c8  lea     r15d, [rsi+1]
0x1400204cc  cmp     rcx, r14
0x1400204cf  jz      short loc_140020501
0x1400204d1  test    [rcx+1Ch], sil
0x1400204d5  jz      short loc_140020501
0x1400204d7  cmp     [rcx+19h], r15b
0x1400204db  jb      short loc_140020501
0x1400204dd  mov     r9, [r12+28h]
0x1400204e2  lea     edx, [rsi+10h]
0x1400204e5  mov     rcx, [rcx+10h]
0x1400204e9  mov     dword ptr [rsp+1E0h+lpSecurityAttributes], r8d
0x1400204ee  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x1400204f5  mov     r9, [r9+70h]
0x1400204f9  call    WPP_SF_Sd
0x1400204fe  mov     r13d, edi
0x140020501  mov     edi, 4
0x140020506  jmp     loc_140020ABE
0x14002050b  mov     rax, [r12+28h]
0x140020510  lea     r8, [rbp+0E0h+hVolumeHint]; void **
0x140020514  mov     esi, 1
0x140020519  mov     r9d, 100080h; unsigned int
0x14002051f  mov     cl, sil; bool
0x140020522  mov     rdx, [rax]
0x140020525  add     rdx, 2A0h; struct _UNICODE_STRING *
0x14002052c  call    ?OpenVolumeHandle@@YAJ_NPEBU_UNICODE_STRING@@PEAPEAXK@Z; OpenVolumeHandle(bool,_UNICODE_STRING const *,void * *,ulong)
0x140020531  mov     [rsp+1E0h+var_168], eax
0x140020535  mov     ebx, eax
0x140020537  test    eax, eax
0x140020539  jns     short loc_140020591
0x14002053b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020542  lea     r14, WPP_GLOBAL_Control
0x140020549  lea     r15d, [rsi+1]
0x14002054d  cmp     rcx, r14
0x140020550  jz      short loc_140020587
0x140020552  test    [rcx+1Ch], sil
0x140020556  jz      short loc_140020587
0x140020558  cmp     [rcx+19h], r15b
0x14002055c  jb      short loc_140020587
0x14002055e  mov     rax, [r12+28h]
0x140020563  lea     edx, [rsi+11h]
0x140020566  mov     rcx, [rcx+10h]
0x14002056a  lea     r8, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x140020571  mov     dword ptr [rsp+1E0h+lpSecurityAttributes], ebx
0x140020575  mov     r9, [rax]
0x140020578  add     r9, 2A0h
0x14002057f  call    WPP_SF_Zd
0x140020584  mov     r13d, edi
0x140020587  mov     edi, 5
0x14002058c  jmp     loc_140020ABE
0x140020591  xor     r12d, r12d
0x140020594  lea     r14, WPP_GLOBAL_Control
0x14002059b  xor     eax, eax
0x14002059d  mov     [rsp+1E0h+var_19C], r12d
0x1400205a2  mov     [rsp+1E0h+var_198], eax
0x1400205a6  lea     r13, WPP_e7ee5fd4dd92374815a10654f437e543_Traceguids
0x1400205ad  mov     [rsp+1E0h+var_188], eax
0x1400205b1  lea     r15d, [r12+2]
0x1400205b6  mov     r12, [rsp+1E0h+var_178]
0x1400205bb  xor     r9d, r9d; unsigned __int8 *
0x1400205be  mov     [rsp+1E0h+var_1A0], 0
0x1400205c3  lea     r8, [rsp+1E0h+var_1A0]; unsigned __int8 *
0x1400205c8  mov     rcx, r12; this
0x1400205cb  lea     rdx, [rbp+0E0h+var_128]; struct TE_FILE_ID_128 *
0x1400205cf  call    ?GetCurrentPinnedRecord@TieringPinnedSession@@QEAAJPEAUTE_FILE_ID_128@@PEAE1@Z; TieringPinnedSession::GetCurrentPinnedRecord(TE_FILE_ID_128 *,uchar *,uchar *)
0x1400205d4  mov     r8d, eax
0x1400205d7  test    eax, eax
0x1400205d9  jnz     loc_1400209BE
0x1400205df  mov     rax, qword ptr [rbp+0E0h+var_128]
0x1400205e3  lea     r9d, [r8+7]; dwShareMode
0x1400205e7  mov     rcx, [rbp+0E0h+hVolumeHint]; hVolumeHint
0x1400205eb  lea     rdx, [rbp+0E0h+FileId]; lpFileId
0x1400205ef  add     edi, esi
0x1400205f1  mov     qword ptr [rbp+0E0h+FileId.8], rax
0x1400205f5  mov     rax, qword ptr [rbp+0E0h+var_128+8]
0x1400205f9  mov     r8d, 180h; dwDesiredAccess
0x1400205ff  mov     [rsp+1E0h+var_194], edi
0x140020603  mov     dil, [rsp+1E0h+var_1A0]
0x140020608  mov     [rsp+1E0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x140020610  and     dil, sil
0x140020613  mov     qword ptr [rbp+0E0h+FileId.8+8], rax
0x140020617  mov     [rbp+0E0h+FileId.dwSize], 18h
0x14002061e  mov     [rbp+0E0h+FileId.Type], r15d
0x140020622  mov     [rsp+1E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14002062b  call    cs:__imp_OpenFileById
0x140020631  mov     [rbp+0E0h+hObject], rax
0x140020635  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140020639  jz      loc_1400207CA
0x14002063f  movzx   r12d, dil
0x140020643  lea     r8, [rsp+1E0h+FileInformation]; FileInformation
0x140020648  mov     r9d, 8; Length
0x14002064e  mov     dword ptr [rsp+1E0h+lpSecurityAttributes], 43h ; 'C'; FileInformationClass
0x140020656  lea     rdx, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x14002065a  mov     rcx, rax; FileHandle
0x14002065d  inc     r12d
0x140020660  call    cs:__imp_NtQueryInformationFile
0x140020666  mov     edi, eax
0x140020668  test    eax, eax
0x14002066a  js      short loc_1400206D7
0x14002066c  cmp     dword ptr [rsp+1E0h+FileInformation], r12d
0x140020671  jz      short loc_1400206BF
0x140020673  mov     rcx, cs:WPP_GLOBAL_Control
0x14002067a  cmp     rcx, r14
0x14002067d  jz      short loc_1400206BF
0x14002067f  test    [rcx+1Ch], sil
0x140020683  jz      short loc_1400206BF
0x140020685  cmp     [rcx+19h], r15b
0x140020689  jb      short loc_1400206BF
0x14002068b  mov     rax, [rsp+1E0h+var_178]
0x140020690  mov     edx, 14h
0x140020695  mov     r9, qword ptr [rbp+0E0h+var_128+8]
0x140020699  mov     r8, r13
0x14002069c  mov     rcx, [rcx+10h]
0x1400206a0  mov     [rsp+1E0h+var_1B0], edi
0x1400206a4  mov     rax, [rax+28h]
0x1400206a8  mov     rax, [rax+70h]
0x1400206ac  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rax
0x1400206b1  mov     rax, qword ptr [rbp+0E0h+var_128]
0x1400206b5  mov     [rsp+1E0h+lpSecurityAttributes], rax
0x1400206ba  call    WPP_SF_iiSd
0x1400206bf  mov     r12d, [rsp+1E0h+var_19C]
0x1400206c4  mov     rcx, [rbp+0E0h+hObject]; hObject
0x1400206c8  call    cs:__imp_CloseHandle
0x1400206ce  mov     edi, [rsp+1E0h+var_198]
0x1400206d2  jmp     loc_140020826
0x1400206d7  cmp     edi, 0C000050Ch
0x1400206dd  jnz     loc_140020777
0x1400206e3  mov     rcx, [rbp+0E0h+hObject]; FileHandle
0x1400206e7  lea     r8, [rsp+1E0h+FileInformation]; FileInformation
0x1400206ec  mov     r9d, 8; Length
0x1400206f2  mov     dword ptr [rsp+1E0h+FileInformation+4], 0
0x1400206fa  lea     rdx, [rbp+0E0h+IoStatusBlock]; IoStatusBlock
0x1400206fe  mov     dword ptr [rsp+1E0h+FileInformation], r12d
0x140020703  mov     dword ptr [rsp+1E0h+lpSecurityAttributes], 43h ; 'C'; FileInformationClass
0x14002070b  call    cs:__imp_NtSetInformationFile
0x140020711  mov     edi, eax
0x140020713  test    eax, eax
0x140020715  jns     short loc_1400206BF
0x140020717  mov     rcx, cs:WPP_GLOBAL_Control
0x14002071e  cmp     rcx, r14
0x140020721  jz      short loc_140020763
0x140020723  test    [rcx+1Ch], sil
0x140020727  jz      short loc_140020763
0x140020729  cmp     [rcx+19h], r15b
0x14002072d  jb      short loc_140020763
0x14002072f  mov     rax, [rsp+1E0h+var_178]
0x140020734  mov     edx, 15h
0x140020739  mov     r9, qword ptr [rbp+0E0h+var_128+8]
0x14002073d  mov     r8, r13
0x140020740  mov     rcx, [rcx+10h]
0x140020744  mov     [rsp+1E0h+var_1B0], edi
0x140020748  mov     rax, [rax+28h]
0x14002074c  mov     rax, [rax+70h]
0x140020750  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rax
0x140020755  mov     rax, qword ptr [rbp+0E0h+var_128]
0x140020759  mov     [rsp+1E0h+lpSecurityAttributes], rax
0x14002075e  call    WPP_SF_iiSd
0x140020763  movzx   eax, r15w
0x140020767  mov     [rsp+1E0h+var_198], eax
0x14002076b  mov     r12d, edi
0x14002076e  mov     [rsp+1E0h+var_19C], edi
0x140020772  jmp     loc_1400206C4
0x140020777  mov     rcx, cs:WPP_GLOBAL_Control
0x14002077e  cmp     rcx, r14
0x140020781  jz      short loc_1400207C3
0x140020783  test    [rcx+1Ch], sil
0x140020787  jz      short loc_1400207C3
0x140020789  cmp     [rcx+19h], r15b
0x14002078d  jb      short loc_1400207C3
0x14002078f  mov     rax, [rsp+1E0h+var_178]
0x140020794  mov     edx, 16h
0x140020799  mov     r9, qword ptr [rbp+0E0h+var_128+8]
0x14002079d  mov     r8, r13
0x1400207a0  mov     rcx, [rcx+10h]
0x1400207a4  mov     [rsp+1E0h+var_1B0], edi
0x1400207a8  mov     rax, [rax+28h]
0x1400207ac  mov     rax, [rax+70h]
0x1400207b0  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rax
0x1400207b5  mov     rax, qword ptr [rbp+0E0h+var_128]
0x1400207b9  mov     [rsp+1E0h+lpSecurityAttributes], rax
0x1400207be  call    WPP_SF_iiSd
0x1400207c3  mov     eax, 3
0x1400207c8  jmp     short loc_140020767
0x1400207ca  call    cs:__imp_GetLastError
0x1400207d0  mov     edx, eax
0x1400207d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207d9  cmp     rcx, r14
0x1400207dc  jz      short loc_140020812
0x1400207de  test    [rcx+1Ch], sil
0x1400207e2  jz      short loc_140020812
0x1400207e4  cmp     [rcx+19h], r15b
0x1400207e8  jb      short loc_140020812
0x1400207ea  mov     rax, [r12+28h]
0x1400207ef  mov     r9, qword ptr [rbp+0E0h+var_128+8]
0x1400207f3  mov     rcx, [rcx+10h]
0x1400207f7  mov     [rsp+1E0h+var_1B0], edx
0x1400207fb  mov     rax, [rax+70h]
0x1400207ff  mov     qword ptr [rsp+1E0h+dwFlagsAndAttributes], rax
0x140020804  mov     rax, qword ptr [rbp+0E0h+var_128]
0x140020808  mov     [rsp+1E0h+lpSecurityAttributes], rax
0x14002080d  call    WPP_SF_iiSD
0x140020812  movzx   edi, si
0x140020815  mov     [rsp+1E0h+var_198], edi
0x140020819  call    cs:__imp_GetLastError
0x14002081f  mov     r12d, eax
0x140020822  mov     [rsp+1E0h+var_19C], eax
0x140020826  test    r12d, r12d
0x140020829  jz      short loc_14002088B
0x14002082b  movzx   r8d, [rsp+1E0h+var_18C]
0x140020831  xor     edx, edx
0x140020833  xor     ecx, ecx
0x140020835  cmp     cx, r8w
0x140020839  jnb     short loc_140020879
0x14002083b  mov     r9d, [rsp+1E0h+var_188]
0x140020840  cmp     r9d, r8d
0x140020843  jz      short loc_140020879
0x140020845  movzx   eax, dx
0x140020848  mov     ecx, [rbp+rax*8+0E0h+var_118]
0x14002084c  cmp     ecx, r12d
0x14002084f  jnz     short loc_140020858
0x140020851  cmp     word ptr [rbp+rax*8+0E0h+var_114], di
0x140020856  jz      short loc_140020879
0x140020858  test    ecx, ecx
  ... truncated ...
```
