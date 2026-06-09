# PushButtonReset::File::Move(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)

- ea: `0x18004ed94`
- end: `0x18004f176`
- name: `?Move@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0_N@Z`
- size: `994`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180021590`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180011ef4`
- `0x180037344`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x18004d404`
- `0x18004d7a0`
- `0x18004df6c`
- `0x18004ed94`
- `0x18004ffd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f069`
- `KERNEL32!GetLastError` at `0x18004f0b7`
- `KERNEL32!GetLastError` at `0x18004f069`
- `KERNEL32!GetLastError` at `0x18004f0b7`
- `KERNEL32!MoveFileExW` at `0x18004f05f`
- `KERNEL32!MoveFileExW` at `0x18004f05f`

## string_xrefs

- `0x18004ee76`: `Failed to get parent dir for target path [%s]`
- `0x18004eebe`: `Parent directory for target path [%s] does not exist`
- `0x18004ef1b`: `Failed to read short name from [%s]`
- `0x18004edc0`: `Input path [%s] doesn't exist or isn't a file`
- `0x18004eddb`: `PushButtonReset::File::Move`
- `0x18004ee2a`: `PushButtonReset::File::Move`
- `0x18004ee91`: `PushButtonReset::File::Move`
- `0x18004eed9`: `PushButtonReset::File::Move`
- `0x18004ef36`: `PushButtonReset::File::Move`
- `0x18004ef9b`: `PushButtonReset::File::Move`
- `0x18004f00e`: `PushButtonReset::File::Move`
- `0x18004f0a4`: `PushButtonReset::File::Move`
- `0x18004f11e`: `PushButtonReset::File::Move`
- `0x18004ee0f`: `Target path [%s] exists and is a directory`
- `0x18004f089`: `Failed to move file [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PushButtonReset::File::Move(_QWORD *a1, _QWORD *a2)
{
  int Directory; // ebx
  int ShortName; // eax
  signed int Canonical; // esi
  ATL::CStringData *v8; // rcx
  ATL::CStringData *v9; // rcx
  LPCWSTR v10; // rbx
  LPCWSTR v11; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  __int64 v14; // r14
  LPCWSTR lpNewFileName; // [rsp+40h] [rbp-20h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v18; // [rsp+98h] [rbp+38h] BYREF

  if ( !(unsigned __int8)PushButtonReset::File::Exists(a1) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942402LL,
      "PushButtonReset::File::Move",
      "base\\reset\\util\\src\\filesystem.cpp",
      3355,
      L"Input path [%s] doesn't exist or isn't a file",
      *a1);
    return 2147942402LL;
  }
  if ( (unsigned __int8)PushButtonReset::Directory::Exists(a2) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942583LL,
      "PushButtonReset::File::Move",
      "base\\reset\\util\\src\\filesystem.cpp",
      3362,
      L"Target path [%s] exists and is a directory",
      *a2);
    return 2147942583LL;
  }
  PushButtonReset::File::Exists(a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v17);
  Directory = PushButtonReset::Path::GetDirectory(a2, v17);
  if ( Directory >= 0 )
  {
    if ( !(unsigned __int8)PushButtonReset::Directory::Exists(v17) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942403LL,
        "PushButtonReset::File::Move",
        "base\\reset\\util\\src\\filesystem.cpp",
        3381,
        L"Parent directory for target path [%s] does not exist",
        *a2);
      Directory = -2147024893;
      goto LABEL_27;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v18);
    ShortName = PushButtonReset::Path::GetShortName(a1, &v18);
    if ( ShortName < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)ShortName,
        "PushButtonReset::File::Move",
        "base\\reset\\util\\src\\filesystem.cpp",
        3389,
        L"Failed to read short name from [%s]",
        *a1);
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v18, &pszFormat, 0);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpExistingFileName);
    Directory = PushButtonReset::Path::GetCanonical(a1, &lpExistingFileName);
    if ( Directory < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Directory,
        "PushButtonReset::File::Move",
        "base\\reset\\util\\src\\filesystem.cpp",
        3398,
        L"Failed to get canonical form for [%s]",
        *a1);
      ATL::CStringData::Release((ATL::CStringData *)(lpExistingFileName - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
      goto LABEL_27;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpNewFileName);
    Canonical = PushButtonReset::Path::GetCanonical(a2, &lpNewFileName);
    if ( Canonical >= 0 )
    {
      v10 = lpNewFileName;
      v11 = lpExistingFileName;
      if ( MoveFileExW(lpExistingFileName, lpNewFileName, 1u) )
      {
        v14 = v18;
        if ( *(int *)(v18 - 16) > 0 )
        {
          Canonical = PushButtonReset::Path::SetShortName(&lpNewFileName, &v18);
          v10 = lpNewFileName;
          if ( Canonical < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)Canonical,
              "PushButtonReset::File::Move",
              "base\\reset\\util\\src\\filesystem.cpp",
              3421,
              L"Failed to restore short name to [%s]",
              lpNewFileName);
            Canonical = 0;
          }
        }
        ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
        v9 = (ATL::CStringData *)(v14 - 24);
        goto LABEL_26;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PushButtonReset::File::Move",
        "base\\reset\\util\\src\\filesystem.cpp",
        3412,
        L"Failed to move file [%s] -> [%s]",
        v11,
        v10);
      v13 = GetLastError();
      Canonical = v13;
      if ( v13 > 0 )
        Canonical = (unsigned __int16)v13 | 0x80070000;
      ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
      v8 = (ATL::CStringData *)(v11 - 12);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Canonical,
        "PushButtonReset::File::Move",
        "base\\reset\\util\\src\\filesystem.cpp",
        3403,
        L"Failed to get canonical form for [%s]",
        *a2);
      ATL::CStringData::Release((ATL::CStringData *)(lpNewFileName - 12));
      v8 = (ATL::CStringData *)(lpExistingFileName - 12);
    }
    ATL::CStringData::Release(v8);
    v9 = (ATL::CStringData *)(v18 - 24);
LABEL_26:
    ATL::CStringData::Release(v9);
    Directory = Canonical;
    goto LABEL_27;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Directory,
    "PushButtonReset::File::Move",
    "base\\reset\\util\\src\\filesystem.cpp",
    3375,
    L"Failed to get parent dir for target path [%s]",
    *a2);
LABEL_27:
  ATL::CStringData::Release((ATL::CStringData *)(v17[0] - 24LL));
  return (unsigned int)Directory;
}

```

## disassembly

```asm
0x18004ed94  mov     [rsp-18h+arg_0], rbx
0x18004ed99  mov     [rsp-18h+arg_8], rsi
0x18004ed9e  push    rbp
0x18004ed9f  push    rdi
0x18004eda0  push    r14
0x18004eda2  mov     rbp, rsp
0x18004eda5  sub     rsp, 60h
0x18004eda9  mov     rdi, rdx
0x18004edac  mov     rsi, rcx
0x18004edaf  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004edb4  test    al, al
0x18004edb6  jnz     short loc_18004EDFB
0x18004edb8  mov     rax, [rsi]
0x18004edbb  mov     [rsp+60h+var_30], rax
0x18004edc0  lea     rax, aInputPathSDoes; "Input path [%s] doesn't exist or isn't "...
0x18004edc7  mov     [rsp+60h+var_38], rax
0x18004edcc  mov     [rsp+60h+var_40], 0D1Bh
0x18004edd4  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004eddb  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004ede2  mov     edx, 80070002h
0x18004ede7  mov     ecx, 2
0x18004edec  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004edf1  mov     eax, 80070002h
0x18004edf6  jmp     loc_18004F161
0x18004edfb  mov     rcx, rdi
0x18004edfe  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004ee03  test    al, al
0x18004ee05  jz      short loc_18004EE4A
0x18004ee07  mov     rax, [rdi]
0x18004ee0a  mov     [rsp+60h+var_30], rax
0x18004ee0f  lea     rax, aTargetPathSExi; "Target path [%s] exists and is a direct"...
0x18004ee16  mov     [rsp+60h+var_38], rax
0x18004ee1b  mov     [rsp+60h+var_40], 0D22h
0x18004ee23  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ee2a  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004ee31  mov     edx, 800700B7h
0x18004ee36  mov     ecx, 2
0x18004ee3b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ee40  mov     eax, 800700B7h
0x18004ee45  jmp     loc_18004F161
0x18004ee4a  mov     rcx, rdi
0x18004ee4d  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004ee52  lea     rcx, [rbp+var_10]
0x18004ee56  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004ee5b  nop
0x18004ee5c  lea     rdx, [rbp+var_10]
0x18004ee60  mov     rcx, rdi
0x18004ee63  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004ee68  mov     ebx, eax
0x18004ee6a  test    eax, eax
0x18004ee6c  jns     short loc_18004EEA9
0x18004ee6e  mov     rcx, [rdi]
0x18004ee71  mov     [rsp+60h+var_30], rcx
0x18004ee76  lea     rax, aFailedToGetPar_1; "Failed to get parent dir for target pat"...
0x18004ee7d  mov     [rsp+60h+var_38], rax
0x18004ee82  mov     [rsp+60h+var_40], 0D2Fh
0x18004ee8a  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ee91  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004ee98  mov     edx, ebx
0x18004ee9a  mov     ecx, 2
0x18004ee9f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004eea4  jmp     loc_18004F152
0x18004eea9  lea     rcx, [rbp+var_10]
0x18004eead  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004eeb2  test    al, al
0x18004eeb4  jnz     short loc_18004EEF9
0x18004eeb6  mov     rax, [rdi]
0x18004eeb9  mov     [rsp+60h+var_30], rax
0x18004eebe  lea     rax, aParentDirector; "Parent directory for target path [%s] d"...
0x18004eec5  mov     [rsp+60h+var_38], rax
0x18004eeca  mov     [rsp+60h+var_40], 0D35h
0x18004eed2  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004eed9  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004eee0  mov     edx, 80070003h
0x18004eee5  mov     ecx, 2
0x18004eeea  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004eeef  mov     ebx, 80070003h
0x18004eef4  jmp     loc_18004F152
0x18004eef9  lea     rcx, [rbp+arg_18]
0x18004eefd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004ef02  nop
0x18004ef03  lea     rdx, [rbp+arg_18]
0x18004ef07  mov     rcx, rsi
0x18004ef0a  call    ?GetShortName@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetShortName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004ef0f  test    eax, eax
0x18004ef11  jns     short loc_18004EF5C
0x18004ef13  mov     rcx, [rsi]
0x18004ef16  mov     [rsp+60h+var_30], rcx
0x18004ef1b  lea     rcx, aFailedToReadSh; "Failed to read short name from [%s]"
0x18004ef22  mov     [rsp+60h+var_38], rcx
0x18004ef27  mov     [rsp+60h+var_40], 0D3Dh
0x18004ef2f  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ef36  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004ef3d  mov     edx, eax
0x18004ef3f  mov     ecx, 1
0x18004ef44  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ef49  xor     r8d, r8d
0x18004ef4c  lea     rdx, pszFormat
0x18004ef53  lea     rcx, [rbp+arg_18]
0x18004ef57  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004ef5c  lea     rcx, [rbp+lpExistingFileName]
0x18004ef60  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004ef65  nop
0x18004ef66  lea     rdx, [rbp+lpExistingFileName]
0x18004ef6a  mov     rcx, rsi
0x18004ef6d  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004ef72  mov     ebx, eax
0x18004ef74  test    eax, eax
0x18004ef76  jns     short loc_18004EFCF
0x18004ef78  mov     rcx, [rsi]
0x18004ef7b  mov     [rsp+60h+var_30], rcx
0x18004ef80  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004ef87  mov     [rsp+60h+var_38], rax
0x18004ef8c  mov     [rsp+60h+var_40], 0D46h
0x18004ef94  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ef9b  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004efa2  mov     edx, ebx
0x18004efa4  mov     ecx, 2
0x18004efa9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004efae  nop
0x18004efaf  mov     rcx, [rbp+lpExistingFileName]
0x18004efb3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004efb7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004efbc  nop
0x18004efbd  mov     rcx, [rbp+arg_18]
0x18004efc1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004efc5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004efca  jmp     loc_18004F152
0x18004efcf  lea     rcx, [rbp+lpNewFileName]
0x18004efd3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004efd8  nop
0x18004efd9  lea     rdx, [rbp+lpNewFileName]
0x18004efdd  mov     rcx, rdi
0x18004efe0  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004efe5  mov     esi, eax
0x18004efe7  test    eax, eax
0x18004efe9  jns     short loc_18004F04B
0x18004efeb  mov     rcx, [rdi]
0x18004efee  mov     [rsp+60h+var_30], rcx
0x18004eff3  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004effa  mov     [rsp+60h+var_38], rax
0x18004efff  mov     [rsp+60h+var_40], 0D4Bh
0x18004f007  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f00e  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004f015  mov     edx, esi
0x18004f017  mov     ecx, 2
0x18004f01c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f021  nop
0x18004f022  mov     rcx, [rbp+lpNewFileName]
0x18004f026  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004f02a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f02f  nop
0x18004f030  mov     rcx, [rbp+lpExistingFileName]
0x18004f034  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004f038  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f03d  nop
0x18004f03e  mov     rcx, [rbp+arg_18]
0x18004f042  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18004f046  jmp     loc_18004F14B
0x18004f04b  mov     r8d, 1; dwFlags
0x18004f051  mov     rbx, [rbp+lpNewFileName]
0x18004f055  mov     rdx, rbx; lpNewFileName
0x18004f058  mov     rdi, [rbp+lpExistingFileName]
0x18004f05c  mov     rcx, rdi; lpExistingFileName
0x18004f05f  call    cs:__imp_MoveFileExW
0x18004f065  test    eax, eax
0x18004f067  jnz     short loc_18004F0DC
0x18004f069  call    cs:__imp_GetLastError
0x18004f06f  mov     r14d, 80070000h
0x18004f075  test    eax, eax
0x18004f077  jle     short loc_18004F07F
0x18004f079  movzx   eax, ax
0x18004f07c  or      eax, r14d
0x18004f07f  mov     [rsp+60h+var_28], rbx
0x18004f084  mov     [rsp+60h+var_30], rdi
0x18004f089  lea     rcx, aFailedToMoveFi; "Failed to move file [%s] -> [%s]"
0x18004f090  mov     [rsp+60h+var_38], rcx
0x18004f095  mov     [rsp+60h+var_40], 0D54h
0x18004f09d  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f0a4  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004f0ab  mov     edx, eax
0x18004f0ad  mov     ecx, 2
0x18004f0b2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f0b7  call    cs:__imp_GetLastError
0x18004f0bd  mov     esi, eax
0x18004f0bf  test    eax, eax
0x18004f0c1  jle     short loc_18004F0C9
0x18004f0c3  movzx   esi, ax
0x18004f0c6  or      esi, r14d
0x18004f0c9  lea     rcx, [rbx-18h]; this
0x18004f0cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f0d2  nop
0x18004f0d3  lea     rcx, [rdi-18h]
0x18004f0d7  jmp     loc_18004F038
0x18004f0dc  mov     r14, [rbp+arg_18]
0x18004f0e0  cmp     dword ptr [r14-10h], 0
0x18004f0e5  jle     short loc_18004F133
0x18004f0e7  lea     rdx, [rbp+arg_18]
0x18004f0eb  lea     rcx, [rbp+lpNewFileName]
0x18004f0ef  call    ?SetShortName@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::Path::SetShortName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004f0f4  mov     esi, eax
0x18004f0f6  mov     rbx, [rbp+lpNewFileName]
0x18004f0fa  test    eax, eax
0x18004f0fc  jns     short loc_18004F133
0x18004f0fe  mov     [rsp+60h+var_30], rbx
0x18004f103  lea     rax, aFailedToRestor_0; "Failed to restore short name to [%s]"
0x18004f10a  mov     [rsp+60h+var_38], rax
0x18004f10f  mov     [rsp+60h+var_40], 0D5Dh
0x18004f117  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f11e  lea     r8, aPushbuttonrese_78; "PushButtonReset::File::Move"
0x18004f125  mov     edx, esi
0x18004f127  mov     ecx, 1
0x18004f12c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f131  xor     esi, esi
0x18004f133  lea     rcx, [rbx-18h]; this
0x18004f137  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f13c  nop
0x18004f13d  lea     rcx, [rdi-18h]; this
0x18004f141  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f146  nop
0x18004f147  lea     rcx, [r14-18h]; this
0x18004f14b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f150  mov     ebx, esi
0x18004f152  mov     rcx, [rbp+var_10]
0x18004f156  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004f15a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f15f  mov     eax, ebx
0x18004f161  lea     r11, [rsp+60h+var_s0]
0x18004f166  mov     rbx, [r11+20h]
0x18004f16a  mov     rsi, [r11+28h]
0x18004f16e  mov     rsp, r11
0x18004f171  pop     r14
0x18004f173  pop     rdi
0x18004f174  pop     rbp
0x18004f175  retn
```
