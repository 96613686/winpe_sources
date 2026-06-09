# ArchiveAutoDelete(ushort const *,ulong,int)

- ea: `0x14000610c`
- end: `0x14000667f`
- name: `?ArchiveAutoDelete@@YAHPEBGKH@Z`
- size: `1395`
- prototype: `_BOOL8 __fastcall(WCHAR *, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140006fc0`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140004f64`
- `0x14000610c`
- `0x140006d38`
- `0x14000cc48`
- `0x1400587f8`
- `0x140072758`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400061ae`
- `KERNEL32!GetLastError` at `0x1400061d7`
- `KERNEL32!GetLastError` at `0x140006372`
- `KERNEL32!GetLastError` at `0x14000650c`
- `KERNEL32!GetLastError` at `0x14000661f`
- `KERNEL32!GetLastError` at `0x1400061ae`
- `KERNEL32!GetLastError` at `0x1400061d7`
- `KERNEL32!GetLastError` at `0x140006372`
- `KERNEL32!GetLastError` at `0x14000650c`
- `KERNEL32!GetLastError` at `0x14000661f`
- `KERNEL32!SetLastError` at `0x14000625f`
- `KERNEL32!SetLastError` at `0x14000625f`
- `KERNEL32!FindFirstFileW` at `0x140006199`
- `KERNEL32!FindFirstFileW` at `0x140006199`
- `KERNEL32!FindClose` at `0x14000656c`
- `KERNEL32!FindClose` at `0x14000656c`
- `KERNEL32!LocalFree` at `0x1400064e4`
- `KERNEL32!LocalFree` at `0x1400064e4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006293`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006293`
- `KERNEL32!DeleteFileW` at `0x14000633e`
- `KERNEL32!DeleteFileW` at `0x14000633e`
- `KERNEL32!FindNextFileW` at `0x1400064f8`
- `KERNEL32!FindNextFileW` at `0x1400064f8`
- `KERNEL32!EnterCriticalSection` at `0x1400065c2`
- `KERNEL32!EnterCriticalSection` at `0x1400065c2`
- `KERNEL32!LeaveCriticalSection` at `0x1400065e4`
- `KERNEL32!LeaveCriticalSection` at `0x1400065e4`
- `KERNEL32!SetEvent` at `0x1400065f7`
- `KERNEL32!SetEvent` at `0x1400065f7`
- `msvcrt!wcsrchr` at `0x1400063cc`
- `msvcrt!wcsrchr` at `0x1400063cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall ArchiveAutoDelete(WCHAR *a1, unsigned int a2, int a3)
{
  __int64 v4; // rdi
  HANDLE FirstFileW; // r14
  DWORD LastError; // eax
  DWORD v9; // eax
  DWORD v10; // ebx
  int v11; // r15d
  unsigned __int64 v12; // rdi
  int v13; // eax
  char v14; // al
  wchar_t *v15; // rax
  CFaxArchiving *v16; // rcx
  const unsigned __int16 *v17; // rbx
  unsigned int v18; // eax
  HLOCAL v19; // rbx
  int ArchiveEvent; // eax
  DWORD v21; // eax
  const unsigned __int16 *v22; // rsi
  DWORD v23; // ebx
  unsigned __int16 v24; // ax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v28; // [rsp+48h] [rbp-B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v4 = a2;
  v28 = a1;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(a1, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    if ( GetLastError() != 2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        LastError = GetLastError();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          LastError,
          (__int64)a1);
      }
      return 0;
    }
    return 1;
  }
  else
  {
    v9 = ParentDirectoryFromFileName(a1, v31);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v9);
      }
      SetLastError(v10);
      return 0;
    }
    v11 = 0;
    v12 = 864000000000LL * v4;
    do
    {
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&FindFileData.ftCreationTime > v12 )
      {
        v13 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v31, FindFileData.cFileName);
        if ( v13 >= 0 )
        {
          if ( DeleteFileW(FileName) )
          {
            v27 = 0;
            hMem = 0;
            v11 = 1;
            v15 = wcsrchr(FileName, 0x5Cu);
            v17 = v15 + 1;
            if ( !v15 )
              v17 = 0;
            if ( v17 )
            {
              v18 = CFaxArchiving::ExtractComponentsFromArchiveFileName(v16, v17, &v27, &hMem);
              if ( v18 )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    143,
                    (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
                    (_DWORD)v17,
                    v18);
                }
              }
              else
              {
                v19 = hMem;
                ArchiveEvent = CreateArchiveEvent(v27, a3 != 0 ? 64 : 32, 1, hMem);
                if ( ArchiveEvent
                  && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_h(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    144,
                    &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
                    (unsigned __int16)ArchiveEvent);
                }
                if ( v19 )
                  LocalFree(v19);
              }
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                142,
                &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
                FileName);
            }
          }
          else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = GetLastError();
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              141,
              (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
              (unsigned int)FileName,
              v14);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            140,
            &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
            (unsigned int)v13);
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    v21 = GetLastError();
    v22 = v28;
    v23 = v21;
    if ( v21 != 18
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        145,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        v21,
        (__int64)v28);
    }
    if ( !FindClose(FirstFileW)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        146,
        (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        v23,
        (__int64)v22);
    }
    if ( v11 == 1 )
    {
      EnterCriticalSection(&g_CsConfig);
      *((_QWORD *)g_pFaxConfig + 7) = -1;
      LeaveCriticalSection(&g_CsConfig);
      if ( !SetEvent(g_hArchiveQuotaWarningEvent)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = GetLastError();
        WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v24);
      }
    }
    return v23 == 18;
  }
}

```

## disassembly

```asm
0x14000610c  mov     [rsp-8+arg_8], rbx
0x140006111  mov     [rsp-8+arg_10], rsi
0x140006116  push    rbp
0x140006117  push    rdi
0x140006118  push    r12
0x14000611a  push    r14
0x14000611c  push    r15
0x14000611e  lea     rbp, [rsp-5D0h]
0x140006126  sub     rsp, 6D0h
0x14000612d  mov     rax, cs:__security_cookie
0x140006134  xor     rax, rsp
0x140006137  mov     [rbp+5F0h+var_30], rax
0x14000613e  mov     r12d, r8d
0x140006141  mov     edi, edx
0x140006143  mov     rsi, rcx
0x140006146  mov     [rsp+6F0h+var_6A8], rcx
0x14000614b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006152  lea     r15, WPP_GLOBAL_Control
0x140006159  cmp     rcx, r15
0x14000615c  jz      short loc_14000617F
0x14000615e  test    byte ptr [rcx+1Ch], 4
0x140006162  jz      short loc_14000617F
0x140006164  cmp     byte ptr [rcx+19h], 5
0x140006168  jb      short loc_14000617F
0x14000616a  mov     rcx, [rcx+10h]
0x14000616e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006175  mov     edx, 89h
0x14000617a  call    WPP_SF_
0x14000617f  xor     edx, edx; Val
0x140006181  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x140006186  mov     r8d, 250h; Size
0x14000618c  call    memset_0
0x140006191  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x140006196  mov     rcx, rsi; lpFileName
0x140006199  call    cs:__imp_FindFirstFileW
0x1400061a0  nop     dword ptr [rax+rax+00h]
0x1400061a5  mov     r14, rax
0x1400061a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400061ac  jnz     short loc_140006218
0x1400061ae  call    cs:__imp_GetLastError
0x1400061b5  nop     dword ptr [rax+rax+00h]
0x1400061ba  cmp     eax, 2
0x1400061bd  jz      short loc_14000620E
0x1400061bf  mov     rax, cs:WPP_GLOBAL_Control
0x1400061c6  cmp     rax, r15
0x1400061c9  jz      short loc_140006207
0x1400061cb  test    byte ptr [rax+1Ch], 4
0x1400061cf  jz      short loc_140006207
0x1400061d1  cmp     byte ptr [rax+19h], 3
0x1400061d5  jb      short loc_140006207
0x1400061d7  call    cs:__imp_GetLastError
0x1400061de  nop     dword ptr [rax+rax+00h]
0x1400061e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061ea  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400061f1  mov     edx, 8Ah
0x1400061f6  mov     [rsp+6F0h+var_6D0], rsi
0x1400061fb  mov     r9d, eax
0x1400061fe  mov     rcx, [rcx+10h]
0x140006202  call    WPP_SF_DS
0x140006207  xor     eax, eax
0x140006209  jmp     loc_140006653
0x14000620e  mov     eax, 1
0x140006213  jmp     loc_140006653
0x140006218  lea     rdx, [rbp+5F0h+var_240]; unsigned __int16 *
0x14000621f  mov     rcx, rsi; unsigned __int16 *
0x140006222  call    ParentDirectoryFromFileName
0x140006227  mov     ebx, eax
0x140006229  test    eax, eax
0x14000622b  jz      short loc_14000626D
0x14000622d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006234  cmp     rcx, r15
0x140006237  jz      short loc_14000625D
0x140006239  test    byte ptr [rcx+1Ch], 4
0x14000623d  jz      short loc_14000625D
0x14000623f  cmp     byte ptr [rcx+19h], 2
0x140006243  jb      short loc_14000625D
0x140006245  mov     rcx, [rcx+10h]
0x140006249  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006250  mov     edx, 8Bh
0x140006255  mov     r9d, eax
0x140006258  call    WPP_SF_d
0x14000625d  mov     ecx, ebx; dwErrCode
0x14000625f  call    cs:__imp_SetLastError
0x140006266  nop     dword ptr [rax+rax+00h]
0x14000626b  jmp     short loc_140006207
0x14000626d  xor     r15d, r15d
0x140006270  lea     rsi, WPP_GLOBAL_Control
0x140006277  mov     rax, 0C92A69C000h
0x140006281  imul    rdi, rax
0x140006285  lea     rcx, [rsp+6F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000628a  mov     qword ptr [rsp+6F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140006293  call    cs:__imp_GetSystemTimeAsFileTime
0x14000629a  nop     dword ptr [rax+rax+00h]
0x14000629f  mov     eax, [rsp+6F0h+FindFileData.ftCreationTime.dwLowDateTime]
0x1400062a3  mov     edx, [rsp+6F0h+FindFileData.ftCreationTime.dwHighDateTime]
0x1400062a7  mov     ecx, [rsp+6F0h+SystemTimeAsFileTime.dwHighDateTime]
0x1400062ab  shl     rcx, 20h
0x1400062af  shl     rdx, 20h
0x1400062b3  or      rdx, rax
0x1400062b6  mov     eax, [rsp+6F0h+SystemTimeAsFileTime.dwLowDateTime]
0x1400062ba  or      rcx, rax
0x1400062bd  sub     rcx, rdx
0x1400062c0  cmp     rcx, rdi
0x1400062c3  jbe     loc_1400064F0
0x1400062c9  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x1400062ce  mov     edx, 104h; unsigned __int64
0x1400062d3  lea     r9, [rbp+5F0h+var_240]
0x1400062da  mov     [rsp+6F0h+var_6D0], rax
0x1400062df  lea     r8, aSS_0; "%s\\%s"
0x1400062e6  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x1400062ed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400062f2  test    eax, eax
0x1400062f4  jns     short loc_140006337
0x1400062f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062fd  cmp     rcx, rsi
0x140006300  jz      loc_1400064F0
0x140006306  test    byte ptr [rcx+1Ch], 4
0x14000630a  jz      loc_1400064F0
0x140006310  cmp     byte ptr [rcx+19h], 2
0x140006314  jb      loc_1400064F0
0x14000631a  mov     rcx, [rcx+10h]
0x14000631e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006325  mov     edx, 8Ch
0x14000632a  mov     r9d, eax
0x14000632d  call    WPP_SF_d
0x140006332  jmp     loc_1400064F0
0x140006337  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x14000633e  call    cs:__imp_DeleteFileW
0x140006345  nop     dword ptr [rax+rax+00h]
0x14000634a  test    eax, eax
0x14000634c  jnz     short loc_1400063AA
0x14000634e  mov     rax, cs:WPP_GLOBAL_Control
0x140006355  cmp     rax, rsi
0x140006358  jz      loc_1400064F0
0x14000635e  test    byte ptr [rax+1Ch], 4
0x140006362  jz      loc_1400064F0
0x140006368  cmp     byte ptr [rax+19h], 2
0x14000636c  jb      loc_1400064F0
0x140006372  call    cs:__imp_GetLastError
0x140006379  nop     dword ptr [rax+rax+00h]
0x14000637e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006385  lea     r9, [rbp+5F0h+FileName]
0x14000638c  mov     edx, 8Dh
0x140006391  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x140006395  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000639c  mov     rcx, [rcx+10h]
0x1400063a0  call    WPP_SF_Sd
0x1400063a5  jmp     loc_1400064F0
0x1400063aa  mov     edx, 5Ch ; '\'; Ch
0x1400063af  mov     [rsp+6F0h+var_6B0], 0
0x1400063b8  lea     rcx, [rbp+5F0h+FileName]; Str
0x1400063bf  mov     [rsp+6F0h+hMem], 0
0x1400063c8  lea     r15d, [rdx-5Bh]
0x1400063cc  call    cs:__imp_wcsrchr
0x1400063d3  nop     dword ptr [rax+rax+00h]
0x1400063d8  test    rax, rax
0x1400063db  lea     rbx, [rax+2]
0x1400063df  cmovz   rbx, rax
0x1400063e3  test    rbx, rbx
0x1400063e6  jnz     short loc_14000642D
0x1400063e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063ef  cmp     rcx, rsi
0x1400063f2  jz      loc_1400064F0
0x1400063f8  test    byte ptr [rcx+1Ch], 4
0x1400063fc  jz      loc_1400064F0
0x140006402  cmp     byte ptr [rcx+19h], 2
0x140006406  jb      loc_1400064F0
0x14000640c  mov     rcx, [rcx+10h]
0x140006410  lea     r9, [rbp+5F0h+FileName]
0x140006417  mov     edx, 8Eh
0x14000641c  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006423  call    WPP_SF_S
0x140006428  jmp     loc_1400064F0
0x14000642d  lea     r9, [rsp+6F0h+hMem]; void **
0x140006432  mov     rdx, rbx; unsigned __int16 *
0x140006435  lea     r8, [rsp+6F0h+var_6B0]; unsigned __int64 *
0x14000643a  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x14000643f  test    eax, eax
0x140006441  jz      short loc_140006485
0x140006443  mov     rcx, cs:WPP_GLOBAL_Control
0x14000644a  cmp     rcx, rsi
0x14000644d  jz      loc_1400064F0
0x140006453  test    byte ptr [rcx+1Ch], 4
0x140006457  jz      loc_1400064F0
0x14000645d  cmp     byte ptr [rcx+19h], 2
0x140006461  jb      loc_1400064F0
0x140006467  mov     rcx, [rcx+10h]
0x14000646b  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006472  mov     edx, 8Fh
0x140006477  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x14000647b  mov     r9, rbx
0x14000647e  call    WPP_SF_Sd
0x140006483  jmp     short loc_1400064F0
0x140006485  mov     rbx, [rsp+6F0h+hMem]
0x14000648a  mov     eax, r12d
0x14000648d  mov     rcx, [rsp+6F0h+var_6B0]
0x140006492  neg     eax
0x140006494  mov     r9, rbx
0x140006497  mov     r8d, r15d
0x14000649a  sbb     edx, edx
0x14000649c  and     edx, 20h
0x14000649f  add     edx, 20h ; ' '
0x1400064a2  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x1400064a7  test    eax, eax
0x1400064a9  jz      short loc_1400064DC
0x1400064ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064b2  cmp     rcx, rsi
0x1400064b5  jz      short loc_1400064DC
0x1400064b7  test    byte ptr [rcx+1Ch], 4
0x1400064bb  jz      short loc_1400064DC
0x1400064bd  cmp     byte ptr [rcx+19h], 2
0x1400064c1  jb      short loc_1400064DC
0x1400064c3  mov     rcx, [rcx+10h]
0x1400064c7  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400064ce  movzx   r9d, ax
0x1400064d2  mov     edx, 90h
0x1400064d7  call    WPP_SF_h
0x1400064dc  test    rbx, rbx
0x1400064df  jz      short loc_1400064F0
0x1400064e1  mov     rcx, rbx; hMem
0x1400064e4  call    cs:__imp_LocalFree
0x1400064eb  nop     dword ptr [rax+rax+00h]
0x1400064f0  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x1400064f5  mov     rcx, r14; hFindFile
0x1400064f8  call    cs:__imp_FindNextFileW
0x1400064ff  nop     dword ptr [rax+rax+00h]
0x140006504  test    eax, eax
0x140006506  jnz     loc_140006285
0x14000650c  call    cs:__imp_GetLastError
0x140006513  nop     dword ptr [rax+rax+00h]
0x140006518  mov     rsi, [rsp+6F0h+var_6A8]
0x14000651d  mov     ebx, eax
0x14000651f  cmp     eax, 12h
0x140006522  jz      short loc_140006562
0x140006524  mov     rcx, cs:WPP_GLOBAL_Control
0x14000652b  lea     rdi, WPP_GLOBAL_Control
0x140006532  cmp     rcx, rdi
0x140006535  jz      short loc_140006569
0x140006537  test    byte ptr [rcx+1Ch], 4
0x14000653b  jz      short loc_140006569
0x14000653d  cmp     byte ptr [rcx+19h], 2
0x140006541  jb      short loc_140006569
0x140006543  mov     rcx, [rcx+10h]
0x140006547  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000654e  mov     edx, 91h
0x140006553  mov     [rsp+6F0h+var_6D0], rsi
0x140006558  mov     r9d, eax
0x14000655b  call    WPP_SF_DS
0x140006560  jmp     short loc_140006569
0x140006562  lea     rdi, WPP_GLOBAL_Control
0x140006569  mov     rcx, r14; hFindFile
0x14000656c  call    cs:__imp_FindClose
0x140006573  nop     dword ptr [rax+rax+00h]
0x140006578  test    eax, eax
0x14000657a  jnz     short loc_1400065B1
0x14000657c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006583  cmp     rcx, rdi
0x140006586  jz      short loc_1400065B1
0x140006588  test    byte ptr [rcx+1Ch], 4
0x14000658c  jz      short loc_1400065B1
0x14000658e  cmp     byte ptr [rcx+19h], 2
0x140006592  jb      short loc_1400065B1
0x140006594  mov     rcx, [rcx+10h]
0x140006598  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000659f  mov     edx, 92h
0x1400065a4  mov     [rsp+6F0h+var_6D0], rsi
0x1400065a9  mov     r9d, ebx
0x1400065ac  call    WPP_SF_DS
0x1400065b1  cmp     r15d, 1
0x1400065b5  jnz     loc_14000664B
0x1400065bb  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400065c2  call    cs:__imp_EnterCriticalSection
0x1400065c9  nop     dword ptr [rax+rax+00h]
0x1400065ce  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400065d5  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400065dc  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x1400065e4  call    cs:__imp_LeaveCriticalSection
0x1400065eb  nop     dword ptr [rax+rax+00h]
0x1400065f0  mov     rcx, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; hEvent
0x1400065f7  call    cs:__imp_SetEvent
0x1400065fe  nop     dword ptr [rax+rax+00h]
0x140006603  test    eax, eax
0x140006605  jnz     short loc_14000664B
0x140006607  mov     rax, cs:WPP_GLOBAL_Control
0x14000660e  cmp     rax, rdi
0x140006611  jz      short loc_14000664B
0x140006613  test    byte ptr [rax+1Ch], 4
0x140006617  jz      short loc_14000664B
0x140006619  cmp     byte ptr [rax+19h], 2
0x14000661d  jb      short loc_14000664B
0x14000661f  call    cs:__imp_GetLastError
0x140006626  nop     dword ptr [rax+rax+00h]
0x14000662b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006632  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006639  mov     edx, 93h
0x14000663e  movzx   r9d, ax
0x140006642  mov     rcx, [rcx+10h]
0x140006646  call    WPP_SF_h
0x14000664b  xor     eax, eax
0x14000664d  cmp     ebx, 12h
  ... truncated ...
```
