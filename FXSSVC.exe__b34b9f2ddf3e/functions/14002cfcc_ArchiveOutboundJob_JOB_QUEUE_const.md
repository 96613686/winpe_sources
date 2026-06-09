# ArchiveOutboundJob(_JOB_QUEUE const *)

- ea: `0x14002cfcc`
- end: `0x14002d5a0`
- name: `?ArchiveOutboundJob@@YAHPEBU_JOB_QUEUE@@@Z`
- size: `1492`
- prototype: `_BOOL8 __fastcall(const struct _JOB_QUEUE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x1400314a8`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x1400064f0`
- `0x14000c5ac`
- `0x140022970`
- `0x14002cfcc`
- `0x140033d10`
- `0x140035094`
- `0x1400552f0`
- `0x140065df8`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002d1ec`
- `KERNEL32!GetLastError` at `0x14002d2a7`
- `KERNEL32!GetLastError` at `0x14002d35f`
- `KERNEL32!GetLastError` at `0x14002d486`
- `KERNEL32!GetLastError` at `0x14002d51c`
- `KERNEL32!GetLastError` at `0x14002d1ec`
- `KERNEL32!GetLastError` at `0x14002d2a7`
- `KERNEL32!GetLastError` at `0x14002d35f`
- `KERNEL32!GetLastError` at `0x14002d486`
- `KERNEL32!GetLastError` at `0x14002d51c`
- `KERNEL32!SetLastError` at `0x14002d33d`
- `KERNEL32!SetLastError` at `0x14002d33d`
- `KERNEL32!FindFirstFileW` at `0x14002d453`
- `KERNEL32!FindFirstFileW` at `0x14002d453`
- `KERNEL32!FindClose` at `0x14002d4fa`
- `KERNEL32!FindClose` at `0x14002d4fa`
- `KERNEL32!DeleteFileW` at `0x14002d285`
- `KERNEL32!DeleteFileW` at `0x14002d285`
- `KERNEL32!EnterCriticalSection` at `0x14002d04e`
- `KERNEL32!EnterCriticalSection` at `0x14002d4c4`
- `KERNEL32!EnterCriticalSection` at `0x14002d04e`
- `KERNEL32!EnterCriticalSection` at `0x14002d4c4`
- `KERNEL32!LeaveCriticalSection` at `0x14002d0bd`
- `KERNEL32!LeaveCriticalSection` at `0x14002d4f1`
- `KERNEL32!LeaveCriticalSection` at `0x14002d0bd`
- `KERNEL32!LeaveCriticalSection` at `0x14002d4f1`
- `KERNEL32!CopyFileW` at `0x14002d1de`
- `KERNEL32!CopyFileW` at `0x14002d1de`

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
  DWORD v17; // eax
  DWORD v18; // edi
  bool v19; // sf
  unsigned __int16 *v20; // rdx
  int ArchiveEvent; // eax
  HANDLE FirstFileW; // rdi
  unsigned __int16 v23; // ax
  unsigned __int16 v24; // ax
  unsigned int v26; // [rsp+28h] [rbp-D8h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v28[14]; // [rsp+44h] [rbp-BCh] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR NewFileName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v31[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsConfig);
  v2 = v31;
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
    v31[0] = 0;
    if ( (v7 & 0x1FFF0000) != 0x70000 )
      v9 = v7;
LABEL_39:
    v28[0] = 0;
    StringCchPrintfW(v28, 0xCu, L"0x%08X", v9);
    FaxLog(2, 1, 3, 3221257492LL, *((_QWORD *)a1 + 9), v31);
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
                  v26,
                  v31);
  v9 = ArchiveFile;
  if ( ArchiveFile )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, ArchiveFile);
    }
    v28[0] = 0;
    v11 = StringCchPrintfW(v28, 0xCu, L"%ld", v9);
    v12 = v28;
    if ( v11 < 0 )
      v12 = 0;
    FaxLog(2, 1, 1, 3221257519LL, v12, v27);
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
    v28[0] = 0;
    v14 = StringCchPrintfW(v28, 0xCu, L"%ld", v9);
    v15 = v28;
    if ( v14 < 0 )
      v15 = 0;
    FaxLog(2, 1, 1, 3221257519LL, v15, v27);
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
    v17 = GetLastError();
    v18 = v17;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        148,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)NewFileName,
        v17);
    }
    v28[0] = 0;
    v19 = (int)StringCchPrintfW(v28, 0xCu, L"0x%08X", v18) < 0;
    v20 = v28;
    if ( v19 )
      v20 = 0;
    FaxLog(2, 1, 2, 3221257546LL, NewFileName, v20);
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
      v23 = GetLastError();
      WPP_SF_hS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        150,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        v23,
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
      v24 = GetLastError();
      WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v24);
    }
  }
  FaxLog(2, 3, 2, 1073773843, *((_QWORD *)a1 + 9), NewFileName);
  return v9 == 0;
}

```

## disassembly

```asm
0x14002cfcc  mov     [rsp-8+arg_8], rbx
0x14002cfd1  mov     [rsp-8+arg_10], rsi
0x14002cfd6  push    rbp
0x14002cfd7  push    rdi
0x14002cfd8  push    r13
0x14002cfda  push    r14
0x14002cfdc  push    r15
0x14002cfde  lea     rbp, [rsp-5E0h]
0x14002cfe6  sub     rsp, 6E0h
0x14002cfed  mov     rax, cs:__security_cookie
0x14002cff4  xor     rax, rsp
0x14002cff7  mov     [rbp+600h+var_30], rax
0x14002cffe  mov     rsi, rcx
0x14002d001  xor     edx, edx; Val
0x14002d003  lea     rcx, [rsp+700h+FindFileData]; void *
0x14002d008  mov     r8d, 250h; Size
0x14002d00e  call    memset_0
0x14002d013  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d01a  lea     r13, WPP_GLOBAL_Control
0x14002d021  cmp     rcx, r13
0x14002d024  jz      short loc_14002D047
0x14002d026  test    byte ptr [rcx+1Ch], 4
0x14002d02a  jz      short loc_14002D047
0x14002d02c  cmp     byte ptr [rcx+19h], 5
0x14002d030  jb      short loc_14002D047
0x14002d032  mov     rcx, [rcx+10h]
0x14002d036  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d03d  mov     edx, 8Fh
0x14002d042  call    WPP_SF_
0x14002d047  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002d04e  call    cs:__imp_EnterCriticalSection
0x14002d054  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002d05b  lea     rdx, [rbp+600h+var_240]
0x14002d062  xor     r14d, r14d
0x14002d065  mov     ecx, 7FFFFFFEh
0x14002d06a  mov     ebx, 104h
0x14002d06f  mov     r8, [rax+30h]
0x14002d073  lea     r15d, [r14+2]
0x14002d077  test    rcx, rcx
0x14002d07a  jz      short loc_14002D097
0x14002d07c  movzx   eax, word ptr [r8]
0x14002d080  test    ax, ax
0x14002d083  jz      short loc_14002D097
0x14002d085  mov     [rdx], ax
0x14002d088  add     r8, r15
0x14002d08b  add     rdx, r15
0x14002d08e  dec     rcx
0x14002d091  sub     rbx, 1
0x14002d095  jnz     short loc_14002D077
0x14002d097  lea     rcx, [rdx-2]
0x14002d09b  mov     rax, rbx
0x14002d09e  neg     rax
0x14002d0a1  sbb     edi, edi
0x14002d0a3  not     edi
0x14002d0a5  and     edi, 8007007Ah
0x14002d0ab  test    rbx, rbx
0x14002d0ae  cmovnz  rcx, rdx
0x14002d0b2  mov     [rcx], r14w
0x14002d0b6  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002d0bd  call    cs:__imp_LeaveCriticalSection
0x14002d0c3  test    rbx, rbx
0x14002d0c6  jnz     short loc_14002D117
0x14002d0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d0cf  cmp     rcx, r13
0x14002d0d2  jz      short loc_14002D0F8
0x14002d0d4  test    byte ptr [rcx+1Ch], 4
0x14002d0d8  jz      short loc_14002D0F8
0x14002d0da  cmp     [rcx+19h], r15b
0x14002d0de  jb      short loc_14002D0F8
0x14002d0e0  mov     rcx, [rcx+10h]
0x14002d0e4  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d0eb  mov     edx, 90h
0x14002d0f0  mov     r9d, edi
0x14002d0f3  call    WPP_SF_d
0x14002d0f8  mov     eax, edi
0x14002d0fa  movzx   ebx, di
0x14002d0fd  and     eax, 1FFF0000h
0x14002d102  mov     [rbp+600h+var_240], r14w
0x14002d10a  cmp     eax, 70000h
0x14002d10f  cmovnz  ebx, edi
0x14002d112  jmp     loc_14002D2D4
0x14002d117  mov     r8, [rsi+248h]
0x14002d11e  lea     rax, [rbp+600h+var_240]
0x14002d125  mov     rdx, [rsi+10h]; unsigned __int64
0x14002d129  mov     r9d, 1; int
0x14002d12f  mov     [rsp+700h+var_6D0], rax; unsigned __int16 *
0x14002d134  lea     rax, [rbp+600h+NewFileName]
0x14002d13b  mov     [rsp+700h+var_6E0], rax; unsigned __int16 *
0x14002d140  mov     r8, [r8+198h]; void *
0x14002d147  call    ?CreateArchiveFile@CFaxArchiving@@QEAAK_KPEAXHPEAGKPEBG@Z; CFaxArchiving::CreateArchiveFile(unsigned __int64,void *,int,ushort *,ulong,ushort const *)
0x14002d14c  mov     ebx, eax
0x14002d14e  test    eax, eax
0x14002d150  jz      short loc_14002D1D0
0x14002d152  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d159  cmp     rcx, r13
0x14002d15c  jz      short loc_14002D182
0x14002d15e  test    byte ptr [rcx+1Ch], 4
0x14002d162  jz      short loc_14002D182
0x14002d164  cmp     [rcx+19h], r15b
0x14002d168  jb      short loc_14002D182
0x14002d16a  mov     rcx, [rcx+10h]
0x14002d16e  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d175  mov     edx, 91h
0x14002d17a  mov     r9d, eax
0x14002d17d  call    WPP_SF_d
0x14002d182  mov     r9d, ebx
0x14002d185  mov     [rsp+700h+var_6C0], ebx
0x14002d189  lea     r8, aLd; "%ld"
0x14002d190  mov     [rsp+700h+var_6BC], r14w
0x14002d196  mov     edx, 0Ch; unsigned __int64
0x14002d19b  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002d1a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d1a5  test    eax, eax
0x14002d1a7  lea     rdx, [rsp+700h+var_6BC]
0x14002d1ac  mov     r9d, 0C0007D2Fh
0x14002d1b2  mov     ecx, r15d
0x14002d1b5  cmovs   rdx, r14
0x14002d1b9  mov     [rsp+700h+var_6E0], rdx
0x14002d1be  mov     edx, 1
0x14002d1c3  mov     r8d, edx
0x14002d1c6  call    FaxLog
0x14002d1cb  jmp     loc_14002D2D4
0x14002d1d0  mov     rcx, [rsi+48h]; lpExistingFileName
0x14002d1d4  lea     rdx, [rbp+600h+NewFileName]; lpNewFileName
0x14002d1db  xor     r8d, r8d; bFailIfExists
0x14002d1de  call    cs:__imp_CopyFileW
0x14002d1e4  test    eax, eax
0x14002d1e6  jnz     loc_14002D348
0x14002d1ec  call    cs:__imp_GetLastError
0x14002d1f2  mov     ebx, eax
0x14002d1f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d1fb  cmp     rcx, r13
0x14002d1fe  jz      short loc_14002D235
0x14002d200  test    byte ptr [rcx+1Ch], 4
0x14002d204  jz      short loc_14002D235
0x14002d206  cmp     [rcx+19h], r15b
0x14002d20a  jb      short loc_14002D235
0x14002d20c  mov     r9, [rsi+48h]
0x14002d210  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d217  mov     rcx, [rcx+10h]
0x14002d21b  mov     edx, 92h
0x14002d220  mov     dword ptr [rsp+700h+var_6D8], eax
0x14002d224  lea     rax, [rbp+600h+NewFileName]
0x14002d22b  mov     [rsp+700h+var_6E0], rax
0x14002d230  call    WPP_SF_SSl
0x14002d235  mov     r9d, ebx
0x14002d238  mov     [rsp+700h+var_6C0], ebx
0x14002d23c  lea     r8, aLd; "%ld"
0x14002d243  mov     [rsp+700h+var_6BC], r14w
0x14002d249  mov     edx, 0Ch; unsigned __int64
0x14002d24e  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002d253  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d258  test    eax, eax
0x14002d25a  lea     rdx, [rsp+700h+var_6BC]
0x14002d25f  mov     r9d, 0C0007D2Fh
0x14002d265  mov     ecx, r15d
0x14002d268  cmovs   rdx, r14
0x14002d26c  mov     [rsp+700h+var_6E0], rdx
0x14002d271  mov     edx, 1
0x14002d276  mov     r8d, edx
0x14002d279  call    FaxLog
0x14002d27e  lea     rcx, [rbp+600h+NewFileName]; lpFileName
0x14002d285  call    cs:__imp_DeleteFileW
0x14002d28b  test    eax, eax
0x14002d28d  jnz     short loc_14002D2D4
0x14002d28f  mov     rax, cs:WPP_GLOBAL_Control
0x14002d296  cmp     rax, r13
0x14002d299  jz      short loc_14002D2D4
0x14002d29b  test    byte ptr [rax+1Ch], 4
0x14002d29f  jz      short loc_14002D2D4
0x14002d2a1  cmp     [rax+19h], r15b
0x14002d2a5  jb      short loc_14002D2D4
0x14002d2a7  call    cs:__imp_GetLastError
0x14002d2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2b4  lea     r9, [rbp+600h+NewFileName]
0x14002d2bb  mov     edx, 93h
0x14002d2c0  mov     dword ptr [rsp+700h+var_6E0], eax
0x14002d2c4  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d2cb  mov     rcx, [rcx+10h]
0x14002d2cf  call    WPP_SF_Sd
0x14002d2d4  mov     r9d, ebx
0x14002d2d7  mov     [rsp+700h+var_6C0], ebx
0x14002d2db  lea     r8, a0x08x; "0x%08X"
0x14002d2e2  mov     [rsp+700h+var_6BC], r14w
0x14002d2e8  mov     edx, 0Ch; unsigned __int64
0x14002d2ed  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002d2f2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d2f7  test    eax, eax
0x14002d2f9  lea     r9, [rsp+700h+var_6BC]
0x14002d2fe  mov     edx, 1
0x14002d303  lea     rax, [rbp+600h+var_240]
0x14002d30a  cmovs   r9, r14
0x14002d30e  mov     ecx, r15d
0x14002d311  mov     [rsp+700h+var_6D0], r9
0x14002d316  mov     r9d, 0C0007D14h
0x14002d31c  mov     [rsp+700h+var_6D8], rax
0x14002d321  mov     rax, [rsi+48h]
0x14002d325  lea     r8d, [rdx+2]
0x14002d329  mov     [rsp+700h+var_6E0], rax
0x14002d32e  call    FaxLog
0x14002d333  test    ebx, ebx
0x14002d335  jz      loc_14002D56D
0x14002d33b  mov     ecx, ebx; dwErrCode
0x14002d33d  call    cs:__imp_SetLastError
0x14002d343  jmp     loc_14002D56D
0x14002d348  mov     rdx, rsi; struct _JOB_QUEUE *
0x14002d34b  lea     rcx, [rbp+600h+NewFileName]; unsigned __int16 *
0x14002d352  call    ?StoreSentMessageProperties@@YAHPEBGPEBU_JOB_QUEUE@@@Z; StoreSentMessageProperties(ushort const *,_JOB_QUEUE const *)
0x14002d357  test    eax, eax
0x14002d359  jnz     loc_14002D3F4
0x14002d35f  call    cs:__imp_GetLastError
0x14002d365  mov     edi, eax
0x14002d367  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d36e  cmp     rcx, r13
0x14002d371  jz      short loc_14002D39F
0x14002d373  test    byte ptr [rcx+1Ch], 4
0x14002d377  jz      short loc_14002D39F
0x14002d379  cmp     [rcx+19h], r15b
0x14002d37d  jb      short loc_14002D39F
0x14002d37f  mov     rcx, [rcx+10h]
0x14002d383  lea     r9, [rbp+600h+NewFileName]
0x14002d38a  mov     edx, 94h
0x14002d38f  mov     dword ptr [rsp+700h+var_6E0], eax
0x14002d393  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d39a  call    WPP_SF_Sd
0x14002d39f  mov     r9d, edi
0x14002d3a2  mov     [rsp+700h+var_6C0], edi
0x14002d3a6  lea     r8, a0x08x; "0x%08X"
0x14002d3ad  mov     [rsp+700h+var_6BC], r14w
0x14002d3b3  mov     edx, 0Ch; unsigned __int64
0x14002d3b8  lea     rcx, [rsp+700h+var_6BC]; unsigned __int16 *
0x14002d3bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002d3c2  test    eax, eax
0x14002d3c4  lea     rdx, [rsp+700h+var_6BC]
0x14002d3c9  lea     rax, [rbp+600h+NewFileName]
0x14002d3d0  mov     r9d, 0C0007D4Ah
0x14002d3d6  cmovs   rdx, r14
0x14002d3da  mov     r8d, r15d
0x14002d3dd  mov     [rsp+700h+var_6D8], rdx
0x14002d3e2  mov     ecx, r15d
0x14002d3e5  mov     edx, 1
0x14002d3ea  mov     [rsp+700h+var_6E0], rax
0x14002d3ef  call    FaxLog
0x14002d3f4  mov     r9, [rsi+248h]
0x14002d3fb  xor     r8d, r8d
0x14002d3fe  mov     rcx, [rsi+10h]
0x14002d402  mov     r9, [r9+198h]
0x14002d409  lea     edx, [r8+40h]
0x14002d40d  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x14002d412  test    eax, eax
0x14002d414  jz      short loc_14002D447
0x14002d416  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d41d  cmp     rcx, r13
0x14002d420  jz      short loc_14002D447
0x14002d422  test    byte ptr [rcx+1Ch], 4
0x14002d426  jz      short loc_14002D447
0x14002d428  cmp     [rcx+19h], r15b
0x14002d42c  jb      short loc_14002D447
0x14002d42e  mov     rcx, [rcx+10h]
0x14002d432  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d439  movzx   r9d, ax
0x14002d43d  mov     edx, 95h
0x14002d442  call    WPP_SF_h
0x14002d447  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14002d44c  lea     rcx, [rbp+600h+NewFileName]; lpFileName
0x14002d453  call    cs:__imp_FindFirstFileW
0x14002d459  mov     rdi, rax
0x14002d45c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002d460  jnz     short loc_14002D4BD
0x14002d462  mov     rax, cs:WPP_GLOBAL_Control
0x14002d469  cmp     rax, r13
0x14002d46c  jz      loc_14002D542
0x14002d472  test    byte ptr [rax+1Ch], 4
0x14002d476  jz      loc_14002D542
0x14002d47c  cmp     [rax+19h], r15b
0x14002d480  jb      loc_14002D542
0x14002d486  call    cs:__imp_GetLastError
0x14002d48c  lea     rcx, [rbp+600h+NewFileName]
0x14002d493  mov     edx, 96h
0x14002d498  mov     [rsp+700h+var_6E0], rcx
0x14002d49d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002d4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d4ab  movzx   r9d, ax
0x14002d4af  mov     rcx, [rcx+10h]
0x14002d4b3  call    WPP_SF_hS
0x14002d4b8  jmp     loc_14002D542
0x14002d4bd  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002d4c4  call    cs:__imp_EnterCriticalSection
0x14002d4ca  mov     r8, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14002d4d1  cmp     qword ptr [r8+38h], 0FFFFFFFFFFFFFFFFh
0x14002d4d6  jz      short loc_14002D4EA
0x14002d4d8  mov     edx, [rsp+700h+FindFileData.nFileSizeHigh]
0x14002d4dc  mov     eax, [rbp+600h+FindFileData.nFileSizeLow]
0x14002d4df  shl     rdx, 20h
0x14002d4e3  or      rdx, rax
0x14002d4e6  add     [r8+38h], rdx
0x14002d4ea  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14002d4f1  call    cs:__imp_LeaveCriticalSection
0x14002d4f7  mov     rcx, rdi; hFindFile
0x14002d4fa  call    cs:__imp_FindClose
  ... truncated ...
```
