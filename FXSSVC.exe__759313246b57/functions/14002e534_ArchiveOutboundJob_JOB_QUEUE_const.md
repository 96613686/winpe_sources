# ArchiveOutboundJob(_JOB_QUEUE const *)

- ea: `0x14002e534`
- end: `0x14002eb5d`
- name: `?ArchiveOutboundJob@@YAHPEBU_JOB_QUEUE@@@Z`
- size: `1577`
- prototype: `_BOOL8 __fastcall(const struct _JOB_QUEUE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x140032e04`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x1400066e8`
- `0x14000cc48`
- `0x140023924`
- `0x14002e534`
- `0x1400358e0`
- `0x140036d40`
- `0x1400587f8`
- `0x1400699d0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002e766`
- `KERNEL32!GetLastError` at `0x14002e82d`
- `KERNEL32!GetLastError` at `0x14002e8f1`
- `KERNEL32!GetLastError` at `0x14002ea24`
- `KERNEL32!GetLastError` at `0x14002ead2`
- `KERNEL32!GetLastError` at `0x14002e766`
- `KERNEL32!GetLastError` at `0x14002e82d`
- `KERNEL32!GetLastError` at `0x14002e8f1`
- `KERNEL32!GetLastError` at `0x14002ea24`
- `KERNEL32!GetLastError` at `0x14002ead2`
- `KERNEL32!SetLastError` at `0x14002e8c9`
- `KERNEL32!SetLastError` at `0x14002e8c9`
- `KERNEL32!FindFirstFileW` at `0x14002e9eb`
- `KERNEL32!FindFirstFileW` at `0x14002e9eb`
- `KERNEL32!FindClose` at `0x14002eaaa`
- `KERNEL32!FindClose` at `0x14002eaaa`
- `KERNEL32!DeleteFileW` at `0x14002e805`
- `KERNEL32!DeleteFileW` at `0x14002e805`
- `KERNEL32!EnterCriticalSection` at `0x14002e5b6`
- `KERNEL32!EnterCriticalSection` at `0x14002ea68`
- `KERNEL32!EnterCriticalSection` at `0x14002e5b6`
- `KERNEL32!EnterCriticalSection` at `0x14002ea68`
- `KERNEL32!LeaveCriticalSection` at `0x14002e62b`
- `KERNEL32!LeaveCriticalSection` at `0x14002ea9b`
- `KERNEL32!LeaveCriticalSection` at `0x14002e62b`
- `KERNEL32!LeaveCriticalSection` at `0x14002ea9b`
- `KERNEL32!CopyFileW` at `0x14002e752`
- `KERNEL32!CopyFileW` at `0x14002e752`

## pseudocode

```c
_BOOL8 __fastcall ArchiveOutboundJob(const struct _JOB_QUEUE *a1)
{
  unsigned __int16 *v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rbx
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rcx
  unsigned int v7; // edi
  CFaxArchiving *v8; // rcx
  DWORD v9; // ebx
  unsigned int ArchiveFile; // eax
  int v11; // eax
  unsigned __int16 *v12; // rdx
  DWORD LastError; // eax
  int v14; // eax
  unsigned __int16 *v15; // rdx
  char v16; // al
  int v17; // eax
  unsigned __int16 *v18; // r9
  DWORD v19; // eax
  DWORD v20; // edi
  int v21; // eax
  unsigned __int16 *v22; // rdx
  int ArchiveEvent; // eax
  HANDLE FirstFileW; // rdi
  unsigned __int16 v25; // ax
  unsigned __int16 v26; // ax
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  __int64 v29; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v31[14]; // [rsp+44h] [rbp-BCh] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NewFileName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v34[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsConfig);
  v2 = v34;
  v3 = 2147483646;
  v4 = 260;
  v5 = (unsigned __int16 *)*((_QWORD *)g_pFaxConfig + 6);
  do
  {
    if ( !v3 )
      break;
    if ( !*v5 )
      break;
    *v2++ = *v5++;
    --v3;
    --v4;
  }
  while ( v4 );
  v6 = v2 - 1;
  v7 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v6 = v2;
  *v6 = 0;
  LeaveCriticalSection(&g_CsConfig);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v7);
    }
    v9 = (unsigned __int16)v7;
    v34[0] = 0;
    if ( (v7 & 0x1FFF0000) != 0x70000 )
      v9 = v7;
LABEL_39:
    v31[0] = 0;
    v17 = StringCchPrintfW(v31, 0xCu, L"0x%08X", v9);
    v18 = v31;
    if ( v17 < 0 )
      v18 = 0;
    FaxLog(2, 1, 3, 3221257492LL, *((_QWORD *)a1 + 9), v34, v18);
    if ( v9 )
      SetLastError(v9);
    return v9 == 0;
  }
  ArchiveFile = CFaxArchiving::CreateArchiveFile(
                  v8,
                  *((_QWORD *)a1 + 2),
                  *(void **)(*((_QWORD *)a1 + 73) + 408LL),
                  1,
                  NewFileName,
                  v28,
                  v34);
  v9 = ArchiveFile;
  if ( ArchiveFile )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, ArchiveFile);
    }
    v31[0] = 0;
    v11 = StringCchPrintfW(v31, 0xCu, L"%ld", v9);
    v12 = v31;
    if ( v11 < 0 )
      v12 = 0;
    FaxLog(2, 1, 1, 3221257519LL, v12, v29, v30);
    goto LABEL_39;
  }
  if ( !CopyFileW(*((LPCWSTR *)a1 + 9), NewFileName, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_SSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        146,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *((_QWORD *)a1 + 9),
        (__int64)NewFileName,
        LastError);
    }
    v31[0] = 0;
    v14 = StringCchPrintfW(v31, 0xCu, L"%ld", v9);
    v15 = v31;
    if ( v14 < 0 )
      v15 = 0;
    FaxLog(2, 1, 1, 3221257519LL, v15, v29, v30);
    if ( !DeleteFileW(NewFileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)NewFileName,
        v16);
    }
    goto LABEL_39;
  }
  if ( !(unsigned int)StoreSentMessageProperties(NewFileName, a1) )
  {
    v19 = GetLastError();
    v20 = v19;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)NewFileName,
        v19);
    }
    v31[0] = 0;
    v21 = StringCchPrintfW(v31, 0xCu, L"0x%08X", v20);
    v22 = v31;
    if ( v21 < 0 )
      v22 = 0;
    FaxLog(2, 1, 2, 3221257546LL, NewFileName, v22, v30);
  }
  ArchiveEvent = CreateArchiveEvent(*((_QWORD *)a1 + 2), 64, 0, *(_QWORD *)(*((_QWORD *)a1 + 73) + 408LL));
  if ( ArchiveEvent
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_h(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      149,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      (unsigned __int16)ArchiveEvent);
  }
  FirstFileW = FindFirstFileW(NewFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v25 = GetLastError();
      WPP_SF_hS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        v25,
        (__int64)NewFileName);
    }
  }
  else
  {
    EnterCriticalSection(&g_CsConfig);
    if ( *((_QWORD *)g_pFaxConfig + 7) != -1 )
      *((_QWORD *)g_pFaxConfig + 7) += FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
    LeaveCriticalSection(&g_CsConfig);
    if ( !FindClose(FirstFileW)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetLastError();
      WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v26);
    }
  }
  FaxLog(2, 3, 2, 1073773843, *((_QWORD *)a1 + 9), NewFileName, v30);
  return v9 == 0;
}

```

## disassembly

```asm
0x14002e534  mov     [rsp-8+arg_8], rbx
0x14002e539  mov     [rsp-8+arg_10], rsi
0x14002e53e  push    rbp
0x14002e53f  push    rdi
0x14002e540  push    r13
0x14002e542  push    r14
0x14002e544  push    r15
0x14002e546  lea     rbp, [rsp-5E0h]
0x14002e54e  sub     rsp, 6E0h
0x14002e555  mov     rax, cs:__security_cookie
0x14002e55c  xor     rax, rsp
0x14002e55f  mov     [rbp+600h+var_30], rax
0x14002e566  mov     rsi, rcx
0x14002e569  xor     edx, edx; Val
0x14002e56b  lea     rcx, [rsp+700h+FindFileData]; void *
0x14002e570  mov     r8d, 250h; Size
0x14002e576  call    memset_0
0x14002e57b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e582  lea     r13, WPP_GLOBAL_Control
0x14002e589  cmp     rcx, r13
0x14002e58c  jz      short loc_14002E5AF
0x14002e58e  test    byte ptr [rcx+1Ch], 4
0x14002e592  jz      short loc_14002E5AF
0x14002e594  cmp     byte ptr [rcx+19h], 5
0x14002e598  jb      short loc_14002E5AF
0x14002e59a  mov     rcx, [rcx+10h]
0x14002e59e  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e5a5  mov     edx, 8Fh
0x14002e5aa  call    WPP_SF_
0x14002e5af  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002e5b6  call    cs:__imp_EnterCriticalSection
0x14002e5bd  nop     dword ptr [rax+rax+00h]
0x14002e5c2  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002e5c9  lea     rdx, [rbp+600h+var_240]
0x14002e5d0  xor     r14d, r14d
0x14002e5d3  mov     ecx, 7FFFFFFEh
0x14002e5d8  mov     ebx, 104h
0x14002e5dd  mov     r8, [rax+30h]
0x14002e5e1  lea     r15d, [r14+2]
0x14002e5e5  test    rcx, rcx
0x14002e5e8  jz      short loc_14002E605
0x14002e5ea  movzx   eax, word ptr [r8]
0x14002e5ee  test    ax, ax
0x14002e5f1  jz      short loc_14002E605
0x14002e5f3  mov     [rdx], ax
0x14002e5f6  add     r8, r15
0x14002e5f9  add     rdx, r15
0x14002e5fc  dec     rcx
0x14002e5ff  sub     rbx, 1
0x14002e603  jnz     short loc_14002E5E5
0x14002e605  lea     rcx, [rdx-2]
0x14002e609  mov     rax, rbx
0x14002e60c  neg     rax
0x14002e60f  sbb     edi, edi
0x14002e611  not     edi
0x14002e613  and     edi, 8007007Ah
0x14002e619  test    rbx, rbx
0x14002e61c  cmovnz  rcx, rdx
0x14002e620  mov     [rcx], r14w
0x14002e624  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002e62b  call    cs:__imp_LeaveCriticalSection
0x14002e632  nop     dword ptr [rax+rax+00h]
0x14002e637  test    rbx, rbx
0x14002e63a  jnz     short loc_14002E68B
0x14002e63c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e643  cmp     rcx, r13
0x14002e646  jz      short loc_14002E66C
0x14002e648  test    byte ptr [rcx+1Ch], 4
0x14002e64c  jz      short loc_14002E66C
0x14002e64e  cmp     [rcx+19h], r15b
0x14002e652  jb      short loc_14002E66C
0x14002e654  mov     rcx, [rcx+10h]
0x14002e658  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e65f  mov     edx, 90h
0x14002e664  mov     r9d, edi
0x14002e667  call    WPP_SF_d
0x14002e66c  mov     eax, edi
0x14002e66e  movzx   ebx, di
0x14002e671  and     eax, 1FFF0000h
0x14002e676  mov     [rbp+600h+var_240], r14w
0x14002e67e  cmp     eax, 70000h
0x14002e683  cmovnz  ebx, edi
0x14002e686  jmp     loc_14002E860
0x14002e68b  mov     r8, [rsi+248h]
0x14002e692  lea     rax, [rbp+600h+var_240]
0x14002e699  mov     rdx, [rsi+10h]; unsigned __int64
0x14002e69d  mov     r9d, 1; int
0x14002e6a3  mov     [rsp+700h+var_6D0], rax; unsigned __int16 *
0x14002e6a8  lea     rax, [rbp+600h+NewFileName]
0x14002e6af  mov     [rsp+700h+var_6E0], rax; unsigned __int16 *
0x14002e6b4  mov     r8, [r8+198h]; void *
0x14002e6bb  call    ?CreateArchiveFile@CFaxArchiving@@QEAAK_KPEAXHPEAGKPEBG@Z; CFaxArchiving::CreateArchiveFile(unsigned __int64,void *,int,ushort *,ulong,ushort const *)
0x14002e6c0  mov     ebx, eax
0x14002e6c2  test    eax, eax
0x14002e6c4  jz      short loc_14002E744
0x14002e6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e6cd  cmp     rcx, r13
0x14002e6d0  jz      short loc_14002E6F6
0x14002e6d2  test    byte ptr [rcx+1Ch], 4
0x14002e6d6  jz      short loc_14002E6F6
0x14002e6d8  cmp     [rcx+19h], r15b
0x14002e6dc  jb      short loc_14002E6F6
0x14002e6de  mov     rcx, [rcx+10h]
0x14002e6e2  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e6e9  mov     edx, 91h
0x14002e6ee  mov     r9d, eax
0x14002e6f1  call    WPP_SF_d
0x14002e6f6  mov     r9d, ebx
0x14002e6f9  mov     [rsp+700h+var_6C0], ebx
0x14002e6fd  lea     r8, aLd; "%ld"
0x14002e704  mov     [rsp+700h+var_6BC], r14w
0x14002e70a  mov     edx, 0Ch; unsigned __int64
0x14002e70f  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002e714  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e719  test    eax, eax
0x14002e71b  lea     rdx, [rsp+700h+var_6BC]
0x14002e720  mov     r9d, 0C0007D2Fh
0x14002e726  mov     ecx, r15d
0x14002e729  cmovs   rdx, r14
0x14002e72d  mov     [rsp+700h+var_6E0], rdx
0x14002e732  mov     edx, 1
0x14002e737  mov     r8d, edx
0x14002e73a  call    FaxLog
0x14002e73f  jmp     loc_14002E860
0x14002e744  mov     rcx, [rsi+48h]; lpExistingFileName
0x14002e748  lea     rdx, [rbp+600h+NewFileName]; lpNewFileName
0x14002e74f  xor     r8d, r8d; bFailIfExists
0x14002e752  call    cs:__imp_CopyFileW
0x14002e759  nop     dword ptr [rax+rax+00h]
0x14002e75e  test    eax, eax
0x14002e760  jnz     loc_14002E8DA
0x14002e766  call    cs:__imp_GetLastError
0x14002e76d  nop     dword ptr [rax+rax+00h]
0x14002e772  mov     ebx, eax
0x14002e774  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e77b  cmp     rcx, r13
0x14002e77e  jz      short loc_14002E7B5
0x14002e780  test    byte ptr [rcx+1Ch], 4
0x14002e784  jz      short loc_14002E7B5
0x14002e786  cmp     [rcx+19h], r15b
0x14002e78a  jb      short loc_14002E7B5
0x14002e78c  mov     r9, [rsi+48h]
0x14002e790  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e797  mov     rcx, [rcx+10h]
0x14002e79b  mov     edx, 92h
0x14002e7a0  mov     dword ptr [rsp+700h+var_6D8], eax
0x14002e7a4  lea     rax, [rbp+600h+NewFileName]
0x14002e7ab  mov     [rsp+700h+var_6E0], rax
0x14002e7b0  call    WPP_SF_SSl
0x14002e7b5  mov     r9d, ebx
0x14002e7b8  mov     [rsp+700h+var_6C0], ebx
0x14002e7bc  lea     r8, aLd; "%ld"
0x14002e7c3  mov     [rsp+700h+var_6BC], r14w
0x14002e7c9  mov     edx, 0Ch; unsigned __int64
0x14002e7ce  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002e7d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e7d8  test    eax, eax
0x14002e7da  lea     rdx, [rsp+700h+var_6BC]
0x14002e7df  mov     r9d, 0C0007D2Fh
0x14002e7e5  mov     ecx, r15d
0x14002e7e8  cmovs   rdx, r14
0x14002e7ec  mov     [rsp+700h+var_6E0], rdx
0x14002e7f1  mov     edx, 1
0x14002e7f6  mov     r8d, edx
0x14002e7f9  call    FaxLog
0x14002e7fe  lea     rcx, [rbp+600h+NewFileName]; lpFileName
0x14002e805  call    cs:__imp_DeleteFileW
0x14002e80c  nop     dword ptr [rax+rax+00h]
0x14002e811  test    eax, eax
0x14002e813  jnz     short loc_14002E860
0x14002e815  mov     rax, cs:WPP_GLOBAL_Control
0x14002e81c  cmp     rax, r13
0x14002e81f  jz      short loc_14002E860
0x14002e821  test    byte ptr [rax+1Ch], 4
0x14002e825  jz      short loc_14002E860
0x14002e827  cmp     [rax+19h], r15b
0x14002e82b  jb      short loc_14002E860
0x14002e82d  call    cs:__imp_GetLastError
0x14002e834  nop     dword ptr [rax+rax+00h]
0x14002e839  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e840  lea     r9, [rbp+600h+NewFileName]
0x14002e847  mov     edx, 93h
0x14002e84c  mov     dword ptr [rsp+700h+var_6E0], eax
0x14002e850  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e857  mov     rcx, [rcx+10h]
0x14002e85b  call    WPP_SF_Sd
0x14002e860  mov     r9d, ebx
0x14002e863  mov     [rsp+700h+var_6C0], ebx
0x14002e867  lea     r8, a0x08x; "0x%08X"
0x14002e86e  mov     [rsp+700h+var_6BC], r14w
0x14002e874  mov     edx, 0Ch; unsigned __int64
0x14002e879  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002e87e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e883  test    eax, eax
0x14002e885  lea     r9, [rsp+700h+var_6BC]
0x14002e88a  mov     edx, 1
0x14002e88f  lea     rax, [rbp+600h+var_240]
0x14002e896  cmovs   r9, r14
0x14002e89a  mov     ecx, r15d
0x14002e89d  mov     [rsp+700h+var_6D0], r9
0x14002e8a2  mov     r9d, 0C0007D14h
0x14002e8a8  mov     [rsp+700h+var_6D8], rax
0x14002e8ad  mov     rax, [rsi+48h]
0x14002e8b1  lea     r8d, [rdx+2]
0x14002e8b5  mov     [rsp+700h+var_6E0], rax
0x14002e8ba  call    FaxLog
0x14002e8bf  test    ebx, ebx
0x14002e8c1  jz      loc_14002EB29
0x14002e8c7  mov     ecx, ebx; dwErrCode
0x14002e8c9  call    cs:__imp_SetLastError
0x14002e8d0  nop     dword ptr [rax+rax+00h]
0x14002e8d5  jmp     loc_14002EB29
0x14002e8da  mov     rdx, rsi; struct _JOB_QUEUE *
0x14002e8dd  lea     rcx, [rbp+600h+NewFileName]; unsigned __int16 *
0x14002e8e4  call    ?StoreSentMessageProperties@@YAHPEBGPEBU_JOB_QUEUE@@@Z; StoreSentMessageProperties(ushort const *,_JOB_QUEUE const *)
0x14002e8e9  test    eax, eax
0x14002e8eb  jnz     loc_14002E98C
0x14002e8f1  call    cs:__imp_GetLastError
0x14002e8f8  nop     dword ptr [rax+rax+00h]
0x14002e8fd  mov     edi, eax
0x14002e8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e906  cmp     rcx, r13
0x14002e909  jz      short loc_14002E937
0x14002e90b  test    byte ptr [rcx+1Ch], 4
0x14002e90f  jz      short loc_14002E937
0x14002e911  cmp     [rcx+19h], r15b
0x14002e915  jb      short loc_14002E937
0x14002e917  mov     rcx, [rcx+10h]
0x14002e91b  lea     r9, [rbp+600h+NewFileName]
0x14002e922  mov     edx, 94h
0x14002e927  mov     dword ptr [rsp+700h+var_6E0], eax
0x14002e92b  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e932  call    WPP_SF_Sd
0x14002e937  mov     r9d, edi
0x14002e93a  mov     [rsp+700h+var_6C0], edi
0x14002e93e  lea     r8, a0x08x; "0x%08X"
0x14002e945  mov     [rsp+700h+var_6BC], r14w
0x14002e94b  mov     edx, 0Ch; unsigned __int64
0x14002e950  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002e955  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002e95a  test    eax, eax
0x14002e95c  lea     rdx, [rsp+700h+var_6BC]
0x14002e961  lea     rax, [rbp+600h+NewFileName]
0x14002e968  mov     r9d, 0C0007D4Ah
0x14002e96e  cmovs   rdx, r14
0x14002e972  mov     r8d, r15d
0x14002e975  mov     [rsp+700h+var_6D8], rdx
0x14002e97a  mov     ecx, r15d
0x14002e97d  mov     edx, 1
0x14002e982  mov     [rsp+700h+var_6E0], rax
0x14002e987  call    FaxLog
0x14002e98c  mov     r9, [rsi+248h]
0x14002e993  xor     r8d, r8d
0x14002e996  mov     rcx, [rsi+10h]
0x14002e99a  mov     r9, [r9+198h]
0x14002e9a1  lea     edx, [r8+40h]
0x14002e9a5  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x14002e9aa  test    eax, eax
0x14002e9ac  jz      short loc_14002E9DF
0x14002e9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e9b5  cmp     rcx, r13
0x14002e9b8  jz      short loc_14002E9DF
0x14002e9ba  test    byte ptr [rcx+1Ch], 4
0x14002e9be  jz      short loc_14002E9DF
0x14002e9c0  cmp     [rcx+19h], r15b
0x14002e9c4  jb      short loc_14002E9DF
0x14002e9c6  mov     rcx, [rcx+10h]
0x14002e9ca  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002e9d1  movzx   r9d, ax
0x14002e9d5  mov     edx, 95h
0x14002e9da  call    WPP_SF_h
0x14002e9df  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14002e9e4  lea     rcx, [rbp+600h+NewFileName]; lpFileName
0x14002e9eb  call    cs:__imp_FindFirstFileW
0x14002e9f2  nop     dword ptr [rax+rax+00h]
0x14002e9f7  mov     rdi, rax
0x14002e9fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002e9fe  jnz     short loc_14002EA61
0x14002ea00  mov     rax, cs:WPP_GLOBAL_Control
0x14002ea07  cmp     rax, r13
0x14002ea0a  jz      loc_14002EAFE
0x14002ea10  test    byte ptr [rax+1Ch], 4
0x14002ea14  jz      loc_14002EAFE
0x14002ea1a  cmp     [rax+19h], r15b
0x14002ea1e  jb      loc_14002EAFE
0x14002ea24  call    cs:__imp_GetLastError
0x14002ea2b  nop     dword ptr [rax+rax+00h]
0x14002ea30  lea     rcx, [rbp+600h+NewFileName]
0x14002ea37  mov     edx, 96h
0x14002ea3c  mov     [rsp+700h+var_6E0], rcx
0x14002ea41  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ea48  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ea4f  movzx   r9d, ax
0x14002ea53  mov     rcx, [rcx+10h]
0x14002ea57  call    WPP_SF_hS
0x14002ea5c  jmp     loc_14002EAFE
0x14002ea61  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002ea68  call    cs:__imp_EnterCriticalSection
0x14002ea6f  nop     dword ptr [rax+rax+00h]
0x14002ea74  mov     r8, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
  ... truncated ...
```
