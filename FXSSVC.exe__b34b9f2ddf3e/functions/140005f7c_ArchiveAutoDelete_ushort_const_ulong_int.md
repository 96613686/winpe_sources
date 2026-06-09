# ArchiveAutoDelete(ushort const *,ulong,int)

- ea: `0x140005f7c`
- end: `0x14000648a`
- name: `?ArchiveAutoDelete@@YAHPEBGKH@Z`
- size: `1294`
- prototype: `_BOOL8 __fastcall(WCHAR *, unsigned int, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140006d60`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x140004df0`
- `0x140005f7c`
- `0x140006b0c`
- `0x14000c5ac`
- `0x1400552f0`
- `0x14006e3ec`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006018`
- `KERNEL32!GetLastError` at `0x14000603b`
- `KERNEL32!GetLastError` at `0x1400061be`
- `KERNEL32!GetLastError` at `0x140006340`
- `KERNEL32!GetLastError` at `0x140006431`
- `KERNEL32!GetLastError` at `0x140006018`
- `KERNEL32!GetLastError` at `0x14000603b`
- `KERNEL32!GetLastError` at `0x1400061be`
- `KERNEL32!GetLastError` at `0x140006340`
- `KERNEL32!GetLastError` at `0x140006431`
- `KERNEL32!SetLastError` at `0x1400060bd`
- `KERNEL32!SetLastError` at `0x1400060bd`
- `KERNEL32!FindFirstFileW` at `0x140006009`
- `KERNEL32!FindFirstFileW` at `0x140006009`
- `KERNEL32!FindClose` at `0x14000639a`
- `KERNEL32!FindClose` at `0x14000639a`
- `KERNEL32!LocalFree` at `0x140006324`
- `KERNEL32!LocalFree` at `0x140006324`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400060eb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400060eb`
- `KERNEL32!DeleteFileW` at `0x140006190`
- `KERNEL32!DeleteFileW` at `0x140006190`
- `KERNEL32!FindNextFileW` at `0x140006332`
- `KERNEL32!FindNextFileW` at `0x140006332`
- `KERNEL32!EnterCriticalSection` at `0x1400063e6`
- `KERNEL32!EnterCriticalSection` at `0x1400063e6`
- `KERNEL32!LeaveCriticalSection` at `0x140006402`
- `KERNEL32!LeaveCriticalSection` at `0x140006402`
- `KERNEL32!SetEvent` at `0x14000640f`
- `KERNEL32!SetEvent` at `0x14000640f`
- `msvcrt!wcsrchr` at `0x140006212`
- `msvcrt!wcsrchr` at `0x140006212`

## pseudocode

```c
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
0x140005f7c  mov     [rsp-8+arg_8], rbx
0x140005f81  mov     [rsp-8+arg_10], rsi
0x140005f86  push    rbp
0x140005f87  push    rdi
0x140005f88  push    r12
0x140005f8a  push    r14
0x140005f8c  push    r15
0x140005f8e  lea     rbp, [rsp-5D0h]
0x140005f96  sub     rsp, 6D0h
0x140005f9d  mov     rax, cs:__security_cookie
0x140005fa4  xor     rax, rsp
0x140005fa7  mov     [rbp+5F0h+var_30], rax
0x140005fae  mov     r12d, r8d
0x140005fb1  mov     edi, edx
0x140005fb3  mov     rsi, rcx
0x140005fb6  mov     [rsp+6F0h+var_6A8], rcx
0x140005fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fc2  lea     r15, WPP_GLOBAL_Control
0x140005fc9  cmp     rcx, r15
0x140005fcc  jz      short loc_140005FEF
0x140005fce  test    byte ptr [rcx+1Ch], 4
0x140005fd2  jz      short loc_140005FEF
0x140005fd4  cmp     byte ptr [rcx+19h], 5
0x140005fd8  jb      short loc_140005FEF
0x140005fda  mov     rcx, [rcx+10h]
0x140005fde  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140005fe5  mov     edx, 89h
0x140005fea  call    WPP_SF_
0x140005fef  xor     edx, edx; Val
0x140005ff1  lea     rcx, [rsp+6F0h+FindFileData]; void *
0x140005ff6  mov     r8d, 250h; Size
0x140005ffc  call    memset_0
0x140006001  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x140006006  mov     rcx, rsi; lpFileName
0x140006009  call    cs:__imp_FindFirstFileW
0x14000600f  mov     r14, rax
0x140006012  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140006016  jnz     short loc_140006076
0x140006018  call    cs:__imp_GetLastError
0x14000601e  cmp     eax, 2
0x140006021  jz      short loc_14000606C
0x140006023  mov     rax, cs:WPP_GLOBAL_Control
0x14000602a  cmp     rax, r15
0x14000602d  jz      short loc_140006065
0x14000602f  test    byte ptr [rax+1Ch], 4
0x140006033  jz      short loc_140006065
0x140006035  cmp     byte ptr [rax+19h], 3
0x140006039  jb      short loc_140006065
0x14000603b  call    cs:__imp_GetLastError
0x140006041  mov     rcx, cs:WPP_GLOBAL_Control
0x140006048  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000604f  mov     edx, 8Ah
0x140006054  mov     [rsp+6F0h+var_6D0], rsi
0x140006059  mov     r9d, eax
0x14000605c  mov     rcx, [rcx+10h]
0x140006060  call    WPP_SF_DS
0x140006065  xor     eax, eax
0x140006067  jmp     loc_14000645F
0x14000606c  mov     eax, 1
0x140006071  jmp     loc_14000645F
0x140006076  lea     rdx, [rbp+5F0h+var_240]; unsigned __int16 *
0x14000607d  mov     rcx, rsi; unsigned __int16 *
0x140006080  call    ParentDirectoryFromFileName
0x140006085  mov     ebx, eax
0x140006087  test    eax, eax
0x140006089  jz      short loc_1400060C5
0x14000608b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006092  cmp     rcx, r15
0x140006095  jz      short loc_1400060BB
0x140006097  test    byte ptr [rcx+1Ch], 4
0x14000609b  jz      short loc_1400060BB
0x14000609d  cmp     byte ptr [rcx+19h], 2
0x1400060a1  jb      short loc_1400060BB
0x1400060a3  mov     rcx, [rcx+10h]
0x1400060a7  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400060ae  mov     edx, 8Bh
0x1400060b3  mov     r9d, eax
0x1400060b6  call    WPP_SF_d
0x1400060bb  mov     ecx, ebx; dwErrCode
0x1400060bd  call    cs:__imp_SetLastError
0x1400060c3  jmp     short loc_140006065
0x1400060c5  xor     r15d, r15d
0x1400060c8  lea     rsi, WPP_GLOBAL_Control
0x1400060cf  mov     rax, 0C92A69C000h
0x1400060d9  imul    rdi, rax
0x1400060dd  lea     rcx, [rsp+6F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400060e2  mov     qword ptr [rsp+6F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1400060eb  call    cs:__imp_GetSystemTimeAsFileTime
0x1400060f1  mov     eax, [rsp+6F0h+FindFileData.ftCreationTime.dwLowDateTime]
0x1400060f5  mov     edx, [rsp+6F0h+FindFileData.ftCreationTime.dwHighDateTime]
0x1400060f9  mov     ecx, [rsp+6F0h+SystemTimeAsFileTime.dwHighDateTime]
0x1400060fd  shl     rcx, 20h
0x140006101  shl     rdx, 20h
0x140006105  or      rdx, rax
0x140006108  mov     eax, [rsp+6F0h+SystemTimeAsFileTime.dwLowDateTime]
0x14000610c  or      rcx, rax
0x14000610f  sub     rcx, rdx
0x140006112  cmp     rcx, rdi
0x140006115  jbe     loc_14000632A
0x14000611b  lea     rax, [rsp+6F0h+FindFileData.cFileName]
0x140006120  mov     edx, 104h; unsigned __int64
0x140006125  lea     r9, [rbp+5F0h+var_240]
0x14000612c  mov     [rsp+6F0h+var_6D0], rax
0x140006131  lea     r8, aSS_0; "%s\\%s"
0x140006138  lea     rcx, [rbp+5F0h+FileName]; unsigned __int16 *
0x14000613f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006144  test    eax, eax
0x140006146  jns     short loc_140006189
0x140006148  mov     rcx, cs:WPP_GLOBAL_Control
0x14000614f  cmp     rcx, rsi
0x140006152  jz      loc_14000632A
0x140006158  test    byte ptr [rcx+1Ch], 4
0x14000615c  jz      loc_14000632A
0x140006162  cmp     byte ptr [rcx+19h], 2
0x140006166  jb      loc_14000632A
0x14000616c  mov     rcx, [rcx+10h]
0x140006170  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006177  mov     edx, 8Ch
0x14000617c  mov     r9d, eax
0x14000617f  call    WPP_SF_d
0x140006184  jmp     loc_14000632A
0x140006189  lea     rcx, [rbp+5F0h+FileName]; lpFileName
0x140006190  call    cs:__imp_DeleteFileW
0x140006196  test    eax, eax
0x140006198  jnz     short loc_1400061F0
0x14000619a  mov     rax, cs:WPP_GLOBAL_Control
0x1400061a1  cmp     rax, rsi
0x1400061a4  jz      loc_14000632A
0x1400061aa  test    byte ptr [rax+1Ch], 4
0x1400061ae  jz      loc_14000632A
0x1400061b4  cmp     byte ptr [rax+19h], 2
0x1400061b8  jb      loc_14000632A
0x1400061be  call    cs:__imp_GetLastError
0x1400061c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061cb  lea     r9, [rbp+5F0h+FileName]
0x1400061d2  mov     edx, 8Dh
0x1400061d7  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x1400061db  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400061e2  mov     rcx, [rcx+10h]
0x1400061e6  call    WPP_SF_Sd
0x1400061eb  jmp     loc_14000632A
0x1400061f0  mov     edx, 5Ch ; '\'; Ch
0x1400061f5  mov     [rsp+6F0h+var_6B0], 0
0x1400061fe  lea     rcx, [rbp+5F0h+FileName]; Str
0x140006205  mov     [rsp+6F0h+hMem], 0
0x14000620e  lea     r15d, [rdx-5Bh]
0x140006212  call    cs:__imp_wcsrchr
0x140006218  test    rax, rax
0x14000621b  lea     rbx, [rax+2]
0x14000621f  cmovz   rbx, rax
0x140006223  test    rbx, rbx
0x140006226  jnz     short loc_14000626D
0x140006228  mov     rcx, cs:WPP_GLOBAL_Control
0x14000622f  cmp     rcx, rsi
0x140006232  jz      loc_14000632A
0x140006238  test    byte ptr [rcx+1Ch], 4
0x14000623c  jz      loc_14000632A
0x140006242  cmp     byte ptr [rcx+19h], 2
0x140006246  jb      loc_14000632A
0x14000624c  mov     rcx, [rcx+10h]
0x140006250  lea     r9, [rbp+5F0h+FileName]
0x140006257  mov     edx, 8Eh
0x14000625c  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006263  call    WPP_SF_S
0x140006268  jmp     loc_14000632A
0x14000626d  lea     r9, [rsp+6F0h+hMem]; void **
0x140006272  mov     rdx, rbx; unsigned __int16 *
0x140006275  lea     r8, [rsp+6F0h+var_6B0]; unsigned __int64 *
0x14000627a  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x14000627f  test    eax, eax
0x140006281  jz      short loc_1400062C5
0x140006283  mov     rcx, cs:WPP_GLOBAL_Control
0x14000628a  cmp     rcx, rsi
0x14000628d  jz      loc_14000632A
0x140006293  test    byte ptr [rcx+1Ch], 4
0x140006297  jz      loc_14000632A
0x14000629d  cmp     byte ptr [rcx+19h], 2
0x1400062a1  jb      loc_14000632A
0x1400062a7  mov     rcx, [rcx+10h]
0x1400062ab  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400062b2  mov     edx, 8Fh
0x1400062b7  mov     dword ptr [rsp+6F0h+var_6D0], eax
0x1400062bb  mov     r9, rbx
0x1400062be  call    WPP_SF_Sd
0x1400062c3  jmp     short loc_14000632A
0x1400062c5  mov     rbx, [rsp+6F0h+hMem]
0x1400062ca  mov     eax, r12d
0x1400062cd  mov     rcx, [rsp+6F0h+var_6B0]
0x1400062d2  neg     eax
0x1400062d4  mov     r9, rbx
0x1400062d7  mov     r8d, r15d
0x1400062da  sbb     edx, edx
0x1400062dc  and     edx, 20h
0x1400062df  add     edx, 20h ; ' '
0x1400062e2  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x1400062e7  test    eax, eax
0x1400062e9  jz      short loc_14000631C
0x1400062eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062f2  cmp     rcx, rsi
0x1400062f5  jz      short loc_14000631C
0x1400062f7  test    byte ptr [rcx+1Ch], 4
0x1400062fb  jz      short loc_14000631C
0x1400062fd  cmp     byte ptr [rcx+19h], 2
0x140006301  jb      short loc_14000631C
0x140006303  mov     rcx, [rcx+10h]
0x140006307  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000630e  movzx   r9d, ax
0x140006312  mov     edx, 90h
0x140006317  call    WPP_SF_h
0x14000631c  test    rbx, rbx
0x14000631f  jz      short loc_14000632A
0x140006321  mov     rcx, rbx; hMem
0x140006324  call    cs:__imp_LocalFree
0x14000632a  lea     rdx, [rsp+6F0h+FindFileData]; lpFindFileData
0x14000632f  mov     rcx, r14; hFindFile
0x140006332  call    cs:__imp_FindNextFileW
0x140006338  test    eax, eax
0x14000633a  jnz     loc_1400060DD
0x140006340  call    cs:__imp_GetLastError
0x140006346  mov     rsi, [rsp+6F0h+var_6A8]
0x14000634b  mov     ebx, eax
0x14000634d  cmp     eax, 12h
0x140006350  jz      short loc_140006390
0x140006352  mov     rcx, cs:WPP_GLOBAL_Control
0x140006359  lea     rdi, WPP_GLOBAL_Control
0x140006360  cmp     rcx, rdi
0x140006363  jz      short loc_140006397
0x140006365  test    byte ptr [rcx+1Ch], 4
0x140006369  jz      short loc_140006397
0x14000636b  cmp     byte ptr [rcx+19h], 2
0x14000636f  jb      short loc_140006397
0x140006371  mov     rcx, [rcx+10h]
0x140006375  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000637c  mov     edx, 91h
0x140006381  mov     [rsp+6F0h+var_6D0], rsi
0x140006386  mov     r9d, eax
0x140006389  call    WPP_SF_DS
0x14000638e  jmp     short loc_140006397
0x140006390  lea     rdi, WPP_GLOBAL_Control
0x140006397  mov     rcx, r14; hFindFile
0x14000639a  call    cs:__imp_FindClose
0x1400063a0  test    eax, eax
0x1400063a2  jnz     short loc_1400063D9
0x1400063a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400063ab  cmp     rcx, rdi
0x1400063ae  jz      short loc_1400063D9
0x1400063b0  test    byte ptr [rcx+1Ch], 4
0x1400063b4  jz      short loc_1400063D9
0x1400063b6  cmp     byte ptr [rcx+19h], 2
0x1400063ba  jb      short loc_1400063D9
0x1400063bc  mov     rcx, [rcx+10h]
0x1400063c0  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400063c7  mov     edx, 92h
0x1400063cc  mov     [rsp+6F0h+var_6D0], rsi
0x1400063d1  mov     r9d, ebx
0x1400063d4  call    WPP_SF_DS
0x1400063d9  cmp     r15d, 1
0x1400063dd  jnz     short loc_140006457
0x1400063df  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400063e6  call    cs:__imp_EnterCriticalSection
0x1400063ec  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x1400063f3  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400063fa  mov     qword ptr [rax+38h], 0FFFFFFFFFFFFFFFFh
0x140006402  call    cs:__imp_LeaveCriticalSection
0x140006408  mov     rcx, cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA; hEvent
0x14000640f  call    cs:__imp_SetEvent
0x140006415  test    eax, eax
0x140006417  jnz     short loc_140006457
0x140006419  mov     rax, cs:WPP_GLOBAL_Control
0x140006420  cmp     rax, rdi
0x140006423  jz      short loc_140006457
0x140006425  test    byte ptr [rax+1Ch], 4
0x140006429  jz      short loc_140006457
0x14000642b  cmp     byte ptr [rax+19h], 2
0x14000642f  jb      short loc_140006457
0x140006431  call    cs:__imp_GetLastError
0x140006437  mov     rcx, cs:WPP_GLOBAL_Control
0x14000643e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140006445  mov     edx, 93h
0x14000644a  movzx   r9d, ax
0x14000644e  mov     rcx, [rcx+10h]
0x140006452  call    WPP_SF_h
0x140006457  xor     eax, eax
0x140006459  cmp     ebx, 12h
0x14000645c  setz    al
0x14000645f  mov     rcx, [rbp+5F0h+var_30]
0x140006466  xor     rcx, rsp; StackCookie
0x140006469  call    __security_check_cookie
0x14000646e  lea     r11, [rsp+6F0h+var_20]
0x140006476  mov     rbx, [r11+38h]
0x14000647a  mov     rsi, [r11+40h]
0x14000647e  mov     rsp, r11
0x140006481  pop     r15
0x140006483  pop     r14
0x140006485  pop     r12
0x140006487  pop     rdi
0x140006488  pop     rbp
0x140006489  retn
```
