# PushButtonReset::Path::GetFullPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x18004db84`
- end: `0x18004df66`
- name: `?GetFullPath@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `994`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18004d404`
- `0x18004ebec`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x180033b18`
- `0x180037344`
- `0x18004a898`
- `0x18004d6b8`
- `0x18004db84`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004dcfa`
- `KERNEL32!GetLastError` at `0x18004dd41`
- `KERNEL32!GetLastError` at `0x18004dcfa`
- `KERNEL32!GetLastError` at `0x18004dd41`
- `KERNEL32!GetVolumePathNameW` at `0x18004dcf0`
- `KERNEL32!GetVolumePathNameW` at `0x18004dcf0`

## string_xrefs

- `0x18004dc66`: `Failed to get current working directory`
- `0x18004dc81`: `PushButtonReset::Path::GetFullPath`
- `0x18004dd2e`: `PushButtonReset::Path::GetFullPath`
- `0x18004ddd2`: `PushButtonReset::Path::GetFullPath`
- `0x18004deaa`: `PushButtonReset::Path::GetFullPath`
- `0x18004dd13`: `Failed to get mount point for current dir [%s]`
- `0x18004ddb7`: `Failed to combine [%s] onto working volume [%s]`
- `0x18004de8f`: `Failed to combine [%s] onto the working dir [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PushButtonReset::Path::GetFullPath(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rdx
  int *v5; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rbx
  int Current; // ebx
  LPCWSTR v10; // rbx
  signed int LastError; // eax
  signed int v12; // eax
  unsigned int v13; // edi
  int v14; // r12d
  ATL::CStringData *v15; // rcx
  ATL::CStringData *v16; // r14
  int *v17; // r15
  __int64 v18; // rdi
  int v19; // r15d
  LPCWSTR v20; // rbx
  ATL::CStringData *v21; // rcx
  ATL::CStringData *v22; // rdi
  int *v23; // r14
  __int64 v24; // rbx
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpszFileName; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *(int *)(*a1 - 16LL) > 1
    && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a1, 0) == 92
    && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a1, 1) == 92
    || *(int *)(*a1 - 16LL) > 1 && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a1, 1) == 58 )
  {
    v4 = *a1;
    v5 = (int *)(*a2 - 24LL);
    v6 = (_QWORD *)(v4 - 24);
    if ( (int *)(v4 - 24) != v5 )
    {
      if ( v5[4] >= 0 && *v6 == *(_QWORD *)v5 )
      {
        v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6);
        ATL::CStringData::Release((ATL::CStringData *)v5);
        *a2 = v7 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v4, *(unsigned int *)(v4 - 16));
      }
    }
    return 0;
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpszFileName);
    Current = PushButtonReset::Directory::GetCurrent(&lpszFileName);
    if ( Current >= 0 )
    {
      if ( *(int *)(*a1 - 16LL) > 0 && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a1, 0) == 92 )
      {
        memset_0(szVolumePathName, 0, 0x20Au);
        v10 = lpszFileName;
        if ( GetVolumePathNameW(lpszFileName, szVolumePathName, 0x104u) )
        {
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)v27,
            (__int64)szVolumePathName);
          v14 = PushButtonReset::Path::Combine(v27, a1, &v25);
          ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
          if ( v14 >= 0 )
          {
            v16 = (ATL::CStringData *)(v25 - 24);
            v17 = (int *)(*a2 - 24LL);
            if ( (int *)(v25 - 24) != v17 )
            {
              if ( v17[4] >= 0 && *(_QWORD *)v16 == *(_QWORD *)v17 )
              {
                v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25 - 24);
                ATL::CStringData::Release((ATL::CStringData *)v17);
                *a2 = v18 + 24;
              }
              else
              {
                ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v25, *(unsigned int *)(v25 - 16));
              }
            }
            v15 = v16;
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v14,
              "PushButtonReset::Path::GetFullPath",
              "base\\reset\\util\\src\\filesystem.cpp",
              269,
              L"Failed to combine [%s] onto working volume [%s]",
              *a1,
              szVolumePathName);
            v15 = (ATL::CStringData *)(v25 - 24);
          }
          ATL::CStringData::Release(v15);
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
          return (unsigned int)v14;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)LastError,
            "PushButtonReset::Path::GetFullPath",
            "base\\reset\\util\\src\\filesystem.cpp",
            262,
            L"Failed to get mount point for current dir [%s]",
            v10);
          v12 = GetLastError();
          v13 = v12;
          if ( v12 > 0 )
            v13 = (unsigned __int16)v12 | 0x80070000;
          ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
          return v13;
        }
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
        v19 = PushButtonReset::Path::Combine(&lpszFileName, a1, &v25);
        if ( v19 >= 0 )
        {
          v22 = (ATL::CStringData *)(v25 - 24);
          v23 = (int *)(*a2 - 24LL);
          if ( (int *)(v25 - 24) != v23 )
          {
            if ( v23[4] >= 0 && *(_QWORD *)v22 == *(_QWORD *)v23 )
            {
              v24 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25 - 24);
              ATL::CStringData::Release((ATL::CStringData *)v23);
              *a2 = v24 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v25, *(unsigned int *)(v25 - 16));
            }
          }
          ATL::CStringData::Release(v22);
          v21 = (ATL::CStringData *)(lpszFileName - 12);
        }
        else
        {
          v20 = lpszFileName;
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v19,
            "PushButtonReset::Path::GetFullPath",
            "base\\reset\\util\\src\\filesystem.cpp",
            282,
            L"Failed to combine [%s] onto the working dir [%s]",
            *a1,
            lpszFileName);
          ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
          v21 = (ATL::CStringData *)(v20 - 12);
        }
        ATL::CStringData::Release(v21);
        return (unsigned int)v19;
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Current,
        "PushButtonReset::Path::GetFullPath",
        "base\\reset\\util\\src\\filesystem.cpp",
        251,
        L"Failed to get current working directory");
      ATL::CStringData::Release((ATL::CStringData *)(lpszFileName - 12));
      return (unsigned int)Current;
    }
  }
}

```

## disassembly

```asm
0x18004db84  mov     [rsp-8+arg_10], rbx
0x18004db89  mov     [rsp-8+arg_18], rsi
0x18004db8e  push    rbp
0x18004db8f  push    rdi
0x18004db90  push    r12
0x18004db92  push    r14
0x18004db94  push    r15
0x18004db96  lea     rbp, [rsp-180h]
0x18004db9e  sub     rsp, 280h
0x18004dba5  mov     rax, cs:__security_cookie
0x18004dbac  xor     rax, rsp
0x18004dbaf  mov     [rbp+1A0h+var_30], rax
0x18004dbb6  mov     rsi, rdx
0x18004dbb9  mov     rdi, rcx
0x18004dbbc  mov     rax, [rcx]
0x18004dbbf  mov     ebx, 1
0x18004dbc4  cmp     [rax-10h], ebx
0x18004dbc7  jle     short loc_18004DBE6
0x18004dbc9  xor     edx, edx
0x18004dbcb  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004dbd0  cmp     ax, 5Ch ; '\'
0x18004dbd4  jnz     short loc_18004DBE6
0x18004dbd6  mov     edx, ebx
0x18004dbd8  mov     rcx, rdi
0x18004dbdb  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004dbe0  cmp     ax, 5Ch ; '\'
0x18004dbe4  jz      short loc_18004DBFE
0x18004dbe6  mov     rax, [rdi]
0x18004dbe9  cmp     [rax-10h], ebx
0x18004dbec  jle     short loc_18004DC4B
0x18004dbee  mov     edx, ebx
0x18004dbf0  mov     rcx, rdi
0x18004dbf3  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004dbf8  cmp     ax, 3Ah ; ':'
0x18004dbfc  jnz     short loc_18004DC4B
0x18004dbfe  mov     rdx, [rdi]
0x18004dc01  mov     rdi, [rsi]
0x18004dc04  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18004dc08  lea     rcx, [rdx-18h]
0x18004dc0c  cmp     rcx, rdi
0x18004dc0f  jz      short loc_18004DC44
0x18004dc11  cmp     dword ptr [rdi+10h], 0
0x18004dc15  jl      short loc_18004DC38
0x18004dc17  mov     rax, [rdi]
0x18004dc1a  cmp     [rcx], rax
0x18004dc1d  jnz     short loc_18004DC38
0x18004dc1f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004dc24  mov     rbx, rax
0x18004dc27  mov     rcx, rdi; this
0x18004dc2a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004dc2f  lea     rax, [rbx+18h]
0x18004dc33  mov     [rsi], rax
0x18004dc36  jmp     short loc_18004DC44
0x18004dc38  mov     r8d, [rdx-10h]
0x18004dc3c  mov     rcx, rsi
0x18004dc3f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004dc44  xor     eax, eax
0x18004dc46  jmp     loc_18004DF3B
0x18004dc4b  lea     rcx, [rsp+2A0h+lpszFileName]
0x18004dc50  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004dc55  nop
0x18004dc56  lea     rcx, [rsp+2A0h+lpszFileName]
0x18004dc5b  call    ?GetCurrent@Directory@PushButtonReset@@SAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::GetCurrent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004dc60  mov     ebx, eax
0x18004dc62  test    eax, eax
0x18004dc64  jns     short loc_18004DCAA
0x18004dc66  lea     rax, aFailedToGetCur; "Failed to get current working directory"
0x18004dc6d  mov     [rsp+2A0h+var_278], rax
0x18004dc72  mov     [rsp+2A0h+var_280], 0FBh
0x18004dc7a  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004dc81  lea     r8, aPushbuttonrese_38; "PushButtonReset::Path::GetFullPath"
0x18004dc88  mov     edx, ebx
0x18004dc8a  mov     ecx, 2
0x18004dc8f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004dc94  nop
0x18004dc95  mov     rcx, [rsp+2A0h+lpszFileName]
0x18004dc9a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004dc9e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004dca3  mov     eax, ebx
0x18004dca5  jmp     loc_18004DF3B
0x18004dcaa  mov     rax, [rdi]
0x18004dcad  cmp     dword ptr [rax-10h], 0
0x18004dcb1  jle     loc_18004DE59
0x18004dcb7  xor     edx, edx
0x18004dcb9  mov     rcx, rdi
0x18004dcbc  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004dcc1  cmp     ax, 5Ch ; '\'
0x18004dcc5  jnz     loc_18004DE59
0x18004dccb  xor     edx, edx; Val
0x18004dccd  mov     r8d, 20Ah; Size
0x18004dcd3  lea     rcx, [rsp+2A0h+szVolumePathName]; void *
0x18004dcd8  call    memset_0
0x18004dcdd  mov     r8d, 104h; cchBufferLength
0x18004dce3  lea     rdx, [rsp+2A0h+szVolumePathName]; lpszVolumePathName
0x18004dce8  mov     rbx, [rsp+2A0h+lpszFileName]
0x18004dced  mov     rcx, rbx; lpszFileName
0x18004dcf0  call    cs:__imp_GetVolumePathNameW
0x18004dcf6  test    eax, eax
0x18004dcf8  jnz     short loc_18004DD62
0x18004dcfa  call    cs:__imp_GetLastError
0x18004dd00  mov     esi, 80070000h
0x18004dd05  test    eax, eax
0x18004dd07  jle     short loc_18004DD0E
0x18004dd09  movzx   eax, ax
0x18004dd0c  or      eax, esi
0x18004dd0e  mov     [rsp+2A0h+var_270], rbx
0x18004dd13  lea     rcx, aFailedToGetMou_0; "Failed to get mount point for current d"...
0x18004dd1a  mov     [rsp+2A0h+var_278], rcx
0x18004dd1f  mov     [rsp+2A0h+var_280], 106h
0x18004dd27  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004dd2e  lea     r8, aPushbuttonrese_38; "PushButtonReset::Path::GetFullPath"
0x18004dd35  mov     edx, eax
0x18004dd37  mov     ecx, 2
0x18004dd3c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004dd41  call    cs:__imp_GetLastError
0x18004dd47  mov     edi, eax
0x18004dd49  test    eax, eax
0x18004dd4b  jle     short loc_18004DD52
0x18004dd4d  movzx   edi, ax
0x18004dd50  or      edi, esi
0x18004dd52  lea     rcx, [rbx-18h]; this
0x18004dd56  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004dd5b  mov     eax, edi
0x18004dd5d  jmp     loc_18004DF3B
0x18004dd62  lea     rcx, [rsp+2A0h+var_260]
0x18004dd67  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004dd6c  nop
0x18004dd6d  lea     rdx, [rsp+2A0h+szVolumePathName]
0x18004dd72  lea     rcx, [rsp+2A0h+var_250]
0x18004dd77  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004dd7c  nop
0x18004dd7d  lea     r8, [rsp+2A0h+var_260]
0x18004dd82  mov     rdx, rdi
0x18004dd85  lea     rcx, [rsp+2A0h+var_250]
0x18004dd8a  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004dd8f  mov     r12d, eax
0x18004dd92  mov     rcx, [rsp+2A0h+var_250]
0x18004dd97  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004dd9b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004dda0  test    r12d, r12d
0x18004dda3  jns     short loc_18004DE07
0x18004dda5  lea     rax, [rsp+2A0h+szVolumePathName]
0x18004ddaa  mov     [rsp+2A0h+var_268], rax
0x18004ddaf  mov     rcx, [rdi]
0x18004ddb2  mov     [rsp+2A0h+var_270], rcx
0x18004ddb7  lea     rax, aFailedToCombin_0; "Failed to combine [%s] onto working vol"...
0x18004ddbe  mov     [rsp+2A0h+var_278], rax
0x18004ddc3  mov     [rsp+2A0h+var_280], 10Dh
0x18004ddcb  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ddd2  lea     r8, aPushbuttonrese_38; "PushButtonReset::Path::GetFullPath"
0x18004ddd9  mov     edx, r12d
0x18004dddc  mov     ecx, 2
0x18004dde1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004dde6  nop
0x18004dde7  mov     rcx, [rsp+2A0h+var_260]
0x18004ddec  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004ddf0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ddf5  nop
0x18004ddf6  lea     rcx, [rbx-18h]; this
0x18004ddfa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ddff  mov     eax, r12d
0x18004de02  jmp     loc_18004DF3B
0x18004de07  mov     rdx, [rsp+2A0h+var_260]
0x18004de0c  lea     r14, [rdx-18h]
0x18004de10  mov     r15, [rsi]
0x18004de13  add     r15, 0FFFFFFFFFFFFFFE8h
0x18004de17  cmp     r14, r15
0x18004de1a  jz      short loc_18004DE54
0x18004de1c  cmp     dword ptr [r15+10h], 0
0x18004de21  jl      short loc_18004DE47
0x18004de23  mov     rax, [r15]
0x18004de26  cmp     [r14], rax
0x18004de29  jnz     short loc_18004DE47
0x18004de2b  mov     rcx, r14
0x18004de2e  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004de33  mov     rdi, rax
0x18004de36  mov     rcx, r15; this
0x18004de39  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004de3e  lea     rax, [rdi+18h]
0x18004de42  mov     [rsi], rax
0x18004de45  jmp     short loc_18004DE54
0x18004de47  mov     r8d, [rdx-10h]
0x18004de4b  mov     rcx, rsi
0x18004de4e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004de53  nop
0x18004de54  mov     rcx, r14
0x18004de57  jmp     short loc_18004DDF0
0x18004de59  lea     rcx, [rsp+2A0h+var_260]
0x18004de5e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004de63  nop
0x18004de64  lea     r8, [rsp+2A0h+var_260]
0x18004de69  mov     rdx, rdi
0x18004de6c  lea     rcx, [rsp+2A0h+lpszFileName]
0x18004de71  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004de76  mov     r15d, eax
0x18004de79  test    eax, eax
0x18004de7b  jns     short loc_18004DED4
0x18004de7d  mov     rbx, [rsp+2A0h+lpszFileName]
0x18004de82  mov     [rsp+2A0h+var_268], rbx
0x18004de87  mov     rcx, [rdi]
0x18004de8a  mov     [rsp+2A0h+var_270], rcx
0x18004de8f  lea     rax, aFailedToCombin_4; "Failed to combine [%s] onto the working"...
0x18004de96  mov     [rsp+2A0h+var_278], rax
0x18004de9b  mov     [rsp+2A0h+var_280], 11Ah
0x18004dea3  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004deaa  lea     r8, aPushbuttonrese_38; "PushButtonReset::Path::GetFullPath"
0x18004deb1  mov     edx, r15d
0x18004deb4  mov     ecx, 2
0x18004deb9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004debe  nop
0x18004debf  mov     rcx, [rsp+2A0h+var_260]
0x18004dec4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004dec8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004decd  nop
0x18004dece  lea     rcx, [rbx-18h]
0x18004ded2  jmp     short loc_18004DF33
0x18004ded4  mov     rdx, [rsp+2A0h+var_260]
0x18004ded9  lea     rdi, [rdx-18h]
0x18004dedd  mov     r14, [rsi]
0x18004dee0  add     r14, 0FFFFFFFFFFFFFFE8h
0x18004dee4  cmp     rdi, r14
0x18004dee7  jz      short loc_18004DF21
0x18004dee9  cmp     dword ptr [r14+10h], 0
0x18004deee  jl      short loc_18004DF14
0x18004def0  mov     rax, [r14]
0x18004def3  cmp     [rdi], rax
0x18004def6  jnz     short loc_18004DF14
0x18004def8  mov     rcx, rdi
0x18004defb  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004df00  mov     rbx, rax
0x18004df03  mov     rcx, r14; this
0x18004df06  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004df0b  lea     rax, [rbx+18h]
0x18004df0f  mov     [rsi], rax
0x18004df12  jmp     short loc_18004DF21
0x18004df14  mov     r8d, [rdx-10h]
0x18004df18  mov     rcx, rsi
0x18004df1b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004df20  nop
0x18004df21  mov     rcx, rdi; this
0x18004df24  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004df29  nop
0x18004df2a  mov     rcx, [rsp+2A0h+lpszFileName]
0x18004df2f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004df33  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004df38  mov     eax, r15d
0x18004df3b  mov     rcx, [rbp+1A0h+var_30]
0x18004df42  xor     rcx, rsp; StackCookie
0x18004df45  call    __security_check_cookie
0x18004df4a  lea     r11, [rsp+2A0h+var_20]
0x18004df52  mov     rbx, [r11+40h]
0x18004df56  mov     rsi, [r11+48h]
0x18004df5a  mov     rsp, r11
0x18004df5d  pop     r15
0x18004df5f  pop     r14
0x18004df61  pop     r12
0x18004df63  pop     rdi
0x18004df64  pop     rbp
0x18004df65  retn
```
