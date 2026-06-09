# FAX_RemoveMessage

- ea: `0x14001d790`
- end: `0x14001dbae`
- name: `FAX_RemoveMessage`
- size: `1054`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140004f64`
- `0x140006d38`
- `0x14000cc48`
- `0x1400135d0`
- `0x14001d790`
- `0x140023924`
- `0x140047d20`
- `0x1400587f8`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001d8fd`
- `KERNEL32!GetLastError` at `0x14001d96a`
- `KERNEL32!GetLastError` at `0x14001d9ad`
- `KERNEL32!GetLastError` at `0x14001d8fd`
- `KERNEL32!GetLastError` at `0x14001d96a`
- `KERNEL32!GetLastError` at `0x14001d9ad`
- `KERNEL32!FindFirstFileW` at `0x14001d8c2`
- `KERNEL32!FindFirstFileW` at `0x14001d8c2`
- `KERNEL32!FindClose` at `0x14001d942`
- `KERNEL32!FindClose` at `0x14001d942`
- `KERNEL32!LocalFree` at `0x14001dace`
- `KERNEL32!LocalFree` at `0x14001dace`
- `KERNEL32!DeleteFileW` at `0x14001d999`
- `KERNEL32!DeleteFileW` at `0x14001d999`
- `KERNEL32!EnterCriticalSection` at `0x14001db4e`
- `KERNEL32!EnterCriticalSection` at `0x14001db4e`
- `KERNEL32!LeaveCriticalSection` at `0x14001db79`
- `KERNEL32!LeaveCriticalSection` at `0x14001db79`
- `msvcrt!wcsrchr` at `0x14001da42`
- `msvcrt!wcsrchr` at `0x14001da42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FAX_RemoveMessage(__int64 a1, unsigned __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  DWORD v6; // eax
  DWORD v7; // ebx
  HANDLE FirstFileW; // rcx
  unsigned __int64 v9; // rdi
  unsigned __int16 LastError; // ax
  unsigned __int16 v11; // ax
  wchar_t *v12; // rax
  CFaxArchiving *v13; // rcx
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  bool v17; // zf
  HLOCAL v18; // rsi
  unsigned int ArchiveEvent; // eax
  __int64 v20; // rax
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v23 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v21 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 486, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  LODWORD(hMem) = 0;
  result = FaxSvcAccessCheck(0x2000000u, (int *)&hMem, &v21, 1);
  if ( !(_DWORD)result )
  {
    if ( (v21 & 0xE03FF) == 0 )
      return 5;
    v6 = FindArchivedMessageAfterAccessCheck(a3, a2, v21, 0, FileName);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 487, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
      }
    }
    else
    {
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        v9 = 0;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_hS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            488,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError,
            (__int64)FileName);
        }
      }
      else
      {
        v9 = FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
        if ( !FindClose(FirstFileW)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 489, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v11);
        }
      }
      if ( DeleteFileW(FileName) )
      {
        hMem = 0;
        v12 = wcsrchr(FileName, 0x5Cu);
        v14 = v12 + 1;
        if ( !v12 )
          v14 = 0;
        if ( v14 )
        {
          v15 = CFaxArchiving::ExtractComponentsFromArchiveFileName(v13, v14, &v23, &hMem);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                492,
                (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (unsigned int)FileName,
                v15);
            }
          }
          else
          {
            v16 = 32;
            v17 = a3 == 0;
            v18 = hMem;
            if ( !v17 )
              v16 = 64;
            ArchiveEvent = CreateArchiveEvent(v23, v16, 1, hMem);
            if ( ArchiveEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                491,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                ArchiveEvent);
            }
            if ( v18 )
              LocalFree(v18);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 493, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, FileName);
        }
        if ( v9 )
        {
          EnterCriticalSection(&g_CsConfig);
          v20 = *((_QWORD *)g_pFaxConfig + 7);
          if ( v20 != -1 )
            *((_QWORD *)g_pFaxConfig + 7) = v20 - v9;
          LeaveCriticalSection(&g_CsConfig);
        }
        return v7;
      }
      v7 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          490,
          (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
          v7,
          (__int64)FileName);
      }
      if ( v7 == 5 || v7 == 32 )
      {
        v7 = 7008;
      }
      else if ( v7 == 2 )
      {
        return 7009;
      }
    }
    if ( v7 == 8 || v7 == 14 )
      return 7001;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14001d790  mov     [rsp-8+arg_0], rbx
0x14001d795  push    rbp
0x14001d796  push    rsi
0x14001d797  push    rdi
0x14001d798  push    r12
0x14001d79a  push    r13
0x14001d79c  lea     rbp, [rsp-3C0h]
0x14001d7a4  sub     rsp, 4C0h
0x14001d7ab  mov     rax, cs:__security_cookie
0x14001d7b2  xor     rax, rsp
0x14001d7b5  mov     [rbp+3E0h+var_30], rax
0x14001d7bc  mov     esi, r8d
0x14001d7bf  mov     [rsp+4E0h+var_4A0], rdx
0x14001d7c4  mov     rbx, rdx
0x14001d7c7  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x14001d7cc  xor     edx, edx; Val
0x14001d7ce  mov     r8d, 250h; Size
0x14001d7d4  call    memset_0
0x14001d7d9  mov     [rsp+4E0h+var_4B0], 0
0x14001d7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d7e8  lea     r12, WPP_GLOBAL_Control
0x14001d7ef  lea     r13, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d7f6  cmp     rcx, r12
0x14001d7f9  jz      short loc_14001D818
0x14001d7fb  test    byte ptr [rcx+1Ch], 4
0x14001d7ff  jz      short loc_14001D818
0x14001d801  cmp     byte ptr [rcx+19h], 5
0x14001d805  jb      short loc_14001D818
0x14001d807  mov     rcx, [rcx+10h]
0x14001d80b  mov     edx, 1E6h
0x14001d810  mov     r8, r13
0x14001d813  call    WPP_SF_
0x14001d818  mov     r9d, 1; int
0x14001d81e  mov     dword ptr [rsp+4E0h+hMem], 0
0x14001d826  lea     r8, [rsp+4E0h+var_4B0]; unsigned int *
0x14001d82b  mov     ecx, 2000000h; unsigned int
0x14001d830  lea     rdx, [rsp+4E0h+hMem]; int *
0x14001d835  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001d83a  test    eax, eax
0x14001d83c  jnz     loc_14001DB87
0x14001d842  mov     r8d, [rsp+4E0h+var_4B0]
0x14001d847  test    r8d, 0E03FFh
0x14001d84e  jnz     short loc_14001D85A
0x14001d850  mov     eax, 5
0x14001d855  jmp     loc_14001DB87
0x14001d85a  lea     rax, [rbp+3E0h+FileName]
0x14001d861  xor     r9d, r9d
0x14001d864  mov     rdx, rbx
0x14001d867  mov     [rsp+4E0h+var_4C0], rax
0x14001d86c  mov     ecx, esi
0x14001d86e  call    FindArchivedMessageAfterAccessCheck
0x14001d873  mov     ebx, eax
0x14001d875  test    eax, eax
0x14001d877  jz      short loc_14001D8B6
0x14001d879  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d880  cmp     rcx, r12
0x14001d883  jz      loc_14001DA15
0x14001d889  test    byte ptr [rcx+1Ch], 4
0x14001d88d  jz      loc_14001DA15
0x14001d893  cmp     byte ptr [rcx+19h], 2
0x14001d897  jb      loc_14001DA15
0x14001d89d  mov     rcx, [rcx+10h]
0x14001d8a1  mov     edx, 1E7h
0x14001d8a6  mov     r9d, eax
0x14001d8a9  mov     r8, r13
0x14001d8ac  call    WPP_SF_d
0x14001d8b1  jmp     loc_14001DA15
0x14001d8b6  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x14001d8bb  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x14001d8c2  call    cs:__imp_FindFirstFileW
0x14001d8c9  nop     dword ptr [rax+rax+00h]
0x14001d8ce  mov     rcx, rax; hFindFile
0x14001d8d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d8d5  jnz     short loc_14001D933
0x14001d8d7  xor     edi, edi
0x14001d8d9  mov     rax, cs:WPP_GLOBAL_Control
0x14001d8e0  cmp     rax, r12
0x14001d8e3  jz      loc_14001D992
0x14001d8e9  test    byte ptr [rax+1Ch], 4
0x14001d8ed  jz      loc_14001D992
0x14001d8f3  cmp     byte ptr [rax+19h], 2
0x14001d8f7  jb      loc_14001D992
0x14001d8fd  call    cs:__imp_GetLastError
0x14001d904  nop     dword ptr [rax+rax+00h]
0x14001d909  lea     rcx, [rbp+3E0h+FileName]
0x14001d910  mov     edx, 1E8h
0x14001d915  mov     [rsp+4E0h+var_4C0], rcx
0x14001d91a  movzx   r9d, ax
0x14001d91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d925  mov     r8, r13
0x14001d928  mov     rcx, [rcx+10h]
0x14001d92c  call    WPP_SF_hS
0x14001d931  jmp     short loc_14001D992
0x14001d933  mov     edi, [rsp+4E0h+FindFileData.nFileSizeHigh]
0x14001d937  mov     eax, [rsp+4E0h+FindFileData.nFileSizeLow]
0x14001d93b  shl     rdi, 20h
0x14001d93f  or      rdi, rax
0x14001d942  call    cs:__imp_FindClose
0x14001d949  nop     dword ptr [rax+rax+00h]
0x14001d94e  test    eax, eax
0x14001d950  jnz     short loc_14001D992
0x14001d952  mov     rax, cs:WPP_GLOBAL_Control
0x14001d959  cmp     rax, r12
0x14001d95c  jz      short loc_14001D992
0x14001d95e  test    byte ptr [rax+1Ch], 4
0x14001d962  jz      short loc_14001D992
0x14001d964  cmp     byte ptr [rax+19h], 2
0x14001d968  jb      short loc_14001D992
0x14001d96a  call    cs:__imp_GetLastError
0x14001d971  nop     dword ptr [rax+rax+00h]
0x14001d976  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d97d  mov     edx, 1E9h
0x14001d982  movzx   r9d, ax
0x14001d986  mov     r8, r13
0x14001d989  mov     rcx, [rcx+10h]
0x14001d98d  call    WPP_SF_h
0x14001d992  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x14001d999  call    cs:__imp_DeleteFileW
0x14001d9a0  nop     dword ptr [rax+rax+00h]
0x14001d9a5  test    eax, eax
0x14001d9a7  jnz     loc_14001DA2D
0x14001d9ad  call    cs:__imp_GetLastError
0x14001d9b4  nop     dword ptr [rax+rax+00h]
0x14001d9b9  mov     ebx, eax
0x14001d9bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d9c2  cmp     rcx, r12
0x14001d9c5  jz      short loc_14001D9F3
0x14001d9c7  test    byte ptr [rcx+1Ch], 4
0x14001d9cb  jz      short loc_14001D9F3
0x14001d9cd  cmp     byte ptr [rcx+19h], 2
0x14001d9d1  jb      short loc_14001D9F3
0x14001d9d3  mov     rcx, [rcx+10h]
0x14001d9d7  lea     rax, [rbp+3E0h+FileName]
0x14001d9de  mov     edx, 1EAh
0x14001d9e3  mov     [rsp+4E0h+var_4C0], rax
0x14001d9e8  mov     r9d, ebx
0x14001d9eb  mov     r8, r13
0x14001d9ee  call    WPP_SF_DS
0x14001d9f3  cmp     ebx, 5
0x14001d9f6  jz      short loc_14001DA10
0x14001d9f8  mov     edx, 20h ; ' '
0x14001d9fd  cmp     ebx, edx
0x14001d9ff  jz      short loc_14001DA10
0x14001da01  cmp     ebx, 2
0x14001da04  jnz     short loc_14001DA15
0x14001da06  mov     ebx, 1B61h
0x14001da0b  jmp     loc_14001DB85
0x14001da10  mov     ebx, 1B60h
0x14001da15  cmp     ebx, 8
0x14001da18  jz      short loc_14001DA23
0x14001da1a  cmp     ebx, 0Eh
0x14001da1d  jnz     loc_14001DB85
0x14001da23  mov     ebx, 1B59h
0x14001da28  jmp     loc_14001DB85
0x14001da2d  mov     edx, 5Ch ; '\'; Ch
0x14001da32  mov     [rsp+4E0h+hMem], 0
0x14001da3b  lea     rcx, [rbp+3E0h+FileName]; Str
0x14001da42  call    cs:__imp_wcsrchr
0x14001da49  nop     dword ptr [rax+rax+00h]
0x14001da4e  test    rax, rax
0x14001da51  lea     rdx, [rax+2]
0x14001da55  cmovz   rdx, rax; unsigned __int16 *
0x14001da59  test    rdx, rdx
0x14001da5c  jz      loc_14001DB12
0x14001da62  lea     r9, [rsp+4E0h+hMem]; void **
0x14001da67  lea     r8, [rsp+4E0h+var_4A0]; unsigned __int64 *
0x14001da6c  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x14001da71  test    eax, eax
0x14001da73  jnz     short loc_14001DADC
0x14001da75  mov     rcx, [rsp+4E0h+var_4A0]
0x14001da7a  lea     edx, [rax+20h]
0x14001da7d  lea     eax, [rdx+20h]
0x14001da80  test    esi, esi
0x14001da82  mov     rsi, [rsp+4E0h+hMem]
0x14001da87  lea     r8d, [rax-3Fh]
0x14001da8b  cmovnz  edx, eax
0x14001da8e  mov     r9, rsi
0x14001da91  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x14001da96  test    eax, eax
0x14001da98  jz      short loc_14001DAC6
0x14001da9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001daa1  cmp     rcx, r12
0x14001daa4  jz      short loc_14001DAC6
0x14001daa6  test    byte ptr [rcx+1Ch], 4
0x14001daaa  jz      short loc_14001DAC6
0x14001daac  cmp     byte ptr [rcx+19h], 2
0x14001dab0  jb      short loc_14001DAC6
0x14001dab2  mov     rcx, [rcx+10h]
0x14001dab6  mov     edx, 1EBh
0x14001dabb  mov     r9d, eax
0x14001dabe  mov     r8, r13
0x14001dac1  call    WPP_SF_d
0x14001dac6  test    rsi, rsi
0x14001dac9  jz      short loc_14001DB42
0x14001dacb  mov     rcx, rsi; hMem
0x14001dace  call    cs:__imp_LocalFree
0x14001dad5  nop     dword ptr [rax+rax+00h]
0x14001dada  jmp     short loc_14001DB42
0x14001dadc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dae3  cmp     rcx, r12
0x14001dae6  jz      short loc_14001DB42
0x14001dae8  test    byte ptr [rcx+1Ch], 4
0x14001daec  jz      short loc_14001DB42
0x14001daee  cmp     byte ptr [rcx+19h], 2
0x14001daf2  jb      short loc_14001DB42
0x14001daf4  mov     rcx, [rcx+10h]
0x14001daf8  lea     r9, [rbp+3E0h+FileName]
0x14001daff  mov     edx, 1ECh
0x14001db04  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x14001db08  mov     r8, r13
0x14001db0b  call    WPP_SF_Sd
0x14001db10  jmp     short loc_14001DB42
0x14001db12  mov     rcx, cs:WPP_GLOBAL_Control
0x14001db19  cmp     rcx, r12
0x14001db1c  jz      short loc_14001DB42
0x14001db1e  test    byte ptr [rcx+1Ch], 4
0x14001db22  jz      short loc_14001DB42
0x14001db24  cmp     byte ptr [rcx+19h], 2
0x14001db28  jb      short loc_14001DB42
0x14001db2a  mov     rcx, [rcx+10h]
0x14001db2e  lea     r9, [rbp+3E0h+FileName]
0x14001db35  mov     edx, 1EDh
0x14001db3a  mov     r8, r13
0x14001db3d  call    WPP_SF_S
0x14001db42  test    rdi, rdi
0x14001db45  jz      short loc_14001DB85
0x14001db47  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001db4e  call    cs:__imp_EnterCriticalSection
0x14001db55  nop     dword ptr [rax+rax+00h]
0x14001db5a  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14001db61  mov     rax, [rdx+38h]
0x14001db65  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001db69  jz      short loc_14001DB72
0x14001db6b  sub     rax, rdi
0x14001db6e  mov     [rdx+38h], rax
0x14001db72  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001db79  call    cs:__imp_LeaveCriticalSection
0x14001db80  nop     dword ptr [rax+rax+00h]
0x14001db85  mov     eax, ebx
0x14001db87  mov     rcx, [rbp+3E0h+var_30]
0x14001db8e  xor     rcx, rsp; StackCookie
0x14001db91  call    __security_check_cookie
0x14001db96  mov     rbx, [rsp+4E0h+arg_0]
0x14001db9e  add     rsp, 4C0h
0x14001dba5  pop     r13
0x14001dba7  pop     r12
0x14001dba9  pop     rdi
0x14001dbaa  pop     rsi
0x14001dbab  pop     rbp
0x14001dbac  retn
```
