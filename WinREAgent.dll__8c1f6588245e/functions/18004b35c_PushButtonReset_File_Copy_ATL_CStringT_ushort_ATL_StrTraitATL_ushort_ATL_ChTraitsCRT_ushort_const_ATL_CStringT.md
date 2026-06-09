# PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)

- ea: `0x18004b35c`
- end: `0x18004b66b`
- name: `?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z`
- size: `783`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, void (__fastcall ***)(void *, __int64, __int64))`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800173a0`
- `0x18001b268`
- `0x18001f880`
- `0x180023ea0`
- `0x1800240fc`
- `0x180027c6c`
- `0x18002bb80`
- `0x18002c0c8`
- `0x18004aabc`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180037344`
- `0x18004b35c`
- `0x18004b8bc`
- `0x18004d404`
- `0x18004e47c`
- `0x18004eb3c`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004b56e`
- `KERNEL32!GetLastError` at `0x18004b5ba`
- `KERNEL32!GetLastError` at `0x18004b56e`
- `KERNEL32!GetLastError` at `0x18004b5ba`
- `KERNEL32!GetFileAttributesW` at `0x18004b550`
- `KERNEL32!GetFileAttributesW` at `0x18004b550`
- `KERNEL32!SetFileAttributesW` at `0x18004b560`
- `KERNEL32!SetFileAttributesW` at `0x18004b560`
- `KERNEL32!CopyFile2` at `0x18004b474`
- `KERNEL32!CopyFile2` at `0x18004b474`

## string_xrefs

- `0x18004b58a`: `Failed to copy attributes from [%s] to [%s]`
- `0x18004b612`: `Failed to copy security information`
- `0x18004b3b9`: `PushButtonReset::File::Copy`
- `0x18004b425`: `PushButtonReset::File::Copy`
- `0x18004b4b4`: `PushButtonReset::File::Copy`
- `0x18004b51c`: `PushButtonReset::File::Copy`
- `0x18004b5a5`: `PushButtonReset::File::Copy`
- `0x18004b5ec`: `PushButtonReset::File::Copy`
- `0x18004b62d`: `PushButtonReset::File::Copy`
- `0x18004b499`: `Failed to copy [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PushButtonReset::File::Copy(
        _QWORD *a1,
        _QWORD *a2,
        void (__fastcall ***a3)(void *, __int64, __int64))
{
  int Canonical; // ebx
  HRESULT Size; // esi
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rbx
  DWORD FileAttributesW; // eax
  signed int v12; // eax
  signed int LastError; // eax
  PCWSTR pwszExistingFileName; // [rsp+40h] [rbp-40h] BYREF
  PCWSTR pwszNewFileName; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+50h] [rbp-30h] BYREF
  COPYFILE2_EXTENDED_PARAMETERS pExtendedParameters; // [rsp+58h] [rbp-28h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&pwszExistingFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &pwszExistingFileName);
  if ( Canonical < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Canonical,
      "PushButtonReset::File::Copy",
      "base\\reset\\util\\src\\filesystem.cpp",
      3242,
      L"Failed to get canonical form for [%s]",
      *a1);
    ATL::CStringData::Release((ATL::CStringData *)(pwszExistingFileName - 12));
    return (unsigned int)Canonical;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&pwszNewFileName);
  Size = PushButtonReset::Path::GetCanonical(a2, &pwszNewFileName);
  v9 = pwszNewFileName;
  if ( Size >= 0 )
  {
    *(_QWORD *)&pExtendedParameters.dwCopyFlags = 0;
    HIDWORD(pExtendedParameters.pfCancel) = 0;
    pExtendedParameters.dwSize = 32;
    pExtendedParameters.pProgressRoutine = (PCOPYFILE2_PROGRESS_ROUTINE)PbrCopyFile2Progress;
    pExtendedParameters.pvCallbackContext = a3;
    v10 = pwszExistingFileName;
    Size = CopyFile2(pwszExistingFileName, pwszNewFileName, &pExtendedParameters);
    if ( Size == -2147023661 )
    {
      Size = -2147023673;
    }
    else
    {
      if ( Size >= 0 )
      {
        if ( a3 && !(unsigned __int8)PushButtonReset::Path::IsReparsePoint(a1) )
        {
          v16 = 0;
          Size = PushButtonReset::File::GetSize(&pwszExistingFileName, &v16);
          if ( Size < 0 )
          {
            v10 = pwszExistingFileName;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Size,
              "PushButtonReset::File::Copy",
              "base\\reset\\util\\src\\filesystem.cpp",
              3271,
              L"Failed to get size of [%s]",
              pwszExistingFileName);
            goto LABEL_25;
          }
          (**a3)(a3, v16, v16);
          v10 = pwszExistingFileName;
        }
        FileAttributesW = GetFileAttributesW(v10);
        if ( FileAttributesW == -1 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)LastError,
            "PushButtonReset::File::Copy",
            "base\\reset\\util\\src\\filesystem.cpp",
            3292,
            L"Failed to get file attributes for [%s]",
            v10);
        }
        else if ( !SetFileAttributesW(v9, FileAttributesW) )
        {
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v12,
            "PushButtonReset::File::Copy",
            "base\\reset\\util\\src\\filesystem.cpp",
            3285,
            L"Failed to copy attributes from [%s] to [%s]",
            v10,
            v9);
        }
        Size = PushButtonReset::File::CopySecurity(&pwszExistingFileName, &pwszNewFileName);
        if ( Size >= 0 )
          Size = 0;
        else
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Size,
            "PushButtonReset::File::Copy",
            "base\\reset\\util\\src\\filesystem.cpp",
            3299,
            L"Failed to copy security information");
        goto LABEL_25;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "PushButtonReset::File::Copy",
        "base\\reset\\util\\src\\filesystem.cpp",
        3264,
        L"Failed to copy [%s] -> [%s]",
        v10,
        v9);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "PushButtonReset::File::Copy",
      "base\\reset\\util\\src\\filesystem.cpp",
      3247,
      L"Failed to get canonical form for [%s]",
      *a2);
    v10 = pwszExistingFileName;
  }
LABEL_25:
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18004b35c  push    rbp
0x18004b35e  push    rbx
0x18004b35f  push    rsi
0x18004b360  push    rdi
0x18004b361  push    r12
0x18004b363  push    r14
0x18004b365  push    r15
0x18004b367  mov     rbp, rsp
0x18004b36a  sub     rsp, 80h
0x18004b371  mov     r14, r8
0x18004b374  mov     r12, rdx
0x18004b377  mov     r15, rcx
0x18004b37a  lea     rcx, [rbp+pwszExistingFileName]
0x18004b37e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004b383  nop
0x18004b384  lea     rdx, [rbp+pwszExistingFileName]
0x18004b388  mov     rcx, r15
0x18004b38b  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004b390  mov     ebx, eax
0x18004b392  test    eax, eax
0x18004b394  jns     short loc_18004B3E1
0x18004b396  mov     rcx, [r15]
0x18004b399  mov     [rsp+80h+var_50], rcx
0x18004b39e  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004b3a5  mov     [rsp+80h+var_58], rax
0x18004b3aa  mov     [rsp+80h+var_60], 0CAAh
0x18004b3b2  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b3b9  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b3c0  mov     edx, ebx
0x18004b3c2  mov     ecx, 2
0x18004b3c7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b3cc  nop
0x18004b3cd  mov     rcx, [rbp+pwszExistingFileName]
0x18004b3d1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004b3d5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004b3da  mov     eax, ebx
0x18004b3dc  jmp     loc_18004B659
0x18004b3e1  lea     rcx, [rbp+pwszNewFileName]
0x18004b3e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004b3ea  nop
0x18004b3eb  lea     rdx, [rbp+pwszNewFileName]
0x18004b3ef  mov     rcx, r12
0x18004b3f2  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004b3f7  mov     esi, eax
0x18004b3f9  mov     rdi, [rbp+pwszNewFileName]
0x18004b3fd  test    eax, eax
0x18004b3ff  jns     short loc_18004B441
0x18004b401  mov     rcx, [r12]
0x18004b405  mov     [rsp+80h+var_50], rcx
0x18004b40a  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004b411  mov     [rsp+80h+var_58], rax
0x18004b416  mov     [rsp+80h+var_60], 0CAFh
0x18004b41e  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b425  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b42c  mov     edx, esi
0x18004b42e  mov     ecx, 2
0x18004b433  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b438  mov     rbx, [rbp+pwszExistingFileName]
0x18004b43c  jmp     loc_18004B644
0x18004b441  mov     qword ptr [rbp+pExtendedParameters.dwCopyFlags], 0
0x18004b449  mov     dword ptr [rbp+pExtendedParameters.pfCancel+4], 0
0x18004b450  mov     [rbp+pExtendedParameters.dwSize], 20h ; ' '
0x18004b457  lea     rax, PbrCopyFile2Progress
0x18004b45e  mov     [rbp+pExtendedParameters.pProgressRoutine], rax
0x18004b462  mov     [rbp+pExtendedParameters.pvCallbackContext], r14
0x18004b466  lea     r8, [rbp+pExtendedParameters]; pExtendedParameters
0x18004b46a  mov     rdx, rdi; pwszNewFileName
0x18004b46d  mov     rbx, [rbp+pwszExistingFileName]
0x18004b471  mov     rcx, rbx; pwszExistingFileName
0x18004b474  call    cs:__imp_CopyFile2
0x18004b47a  mov     esi, eax
0x18004b47c  cmp     eax, 800704D3h
0x18004b481  jnz     short loc_18004B48B
0x18004b483  lea     esi, [rax-0Ch]
0x18004b486  jmp     loc_18004B644
0x18004b48b  test    esi, esi
0x18004b48d  jns     short loc_18004B4CC
0x18004b48f  mov     [rsp+80h+var_48], rdi
0x18004b494  mov     [rsp+80h+var_50], rbx
0x18004b499  lea     rax, aFailedToCopySS; "Failed to copy [%s] -> [%s]"
0x18004b4a0  mov     [rsp+80h+var_58], rax
0x18004b4a5  mov     [rsp+80h+var_60], 0CC0h
0x18004b4ad  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b4b4  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b4bb  mov     edx, esi
0x18004b4bd  mov     ecx, 2
0x18004b4c2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b4c7  jmp     loc_18004B644
0x18004b4cc  test    r14, r14
0x18004b4cf  jz      short loc_18004B54D
0x18004b4d1  mov     rcx, r15
0x18004b4d4  call    ?IsReparsePoint@Path@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Path::IsReparsePoint(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004b4d9  test    al, al
0x18004b4db  jnz     short loc_18004B54D
0x18004b4dd  mov     [rbp+var_30], 0
0x18004b4e5  lea     rdx, [rbp+var_30]
0x18004b4e9  lea     rcx, [rbp+pwszExistingFileName]
0x18004b4ed  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18004b4f2  mov     esi, eax
0x18004b4f4  test    eax, eax
0x18004b4f6  jns     short loc_18004B534
0x18004b4f8  mov     rbx, [rbp+pwszExistingFileName]
0x18004b4fc  mov     [rsp+80h+var_50], rbx
0x18004b501  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x18004b508  mov     [rsp+80h+var_58], rax
0x18004b50d  mov     [rsp+80h+var_60], 0CC7h
0x18004b515  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b51c  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b523  mov     edx, esi
0x18004b525  mov     ecx, 2
0x18004b52a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b52f  jmp     loc_18004B644
0x18004b534  mov     rax, [r14]
0x18004b537  mov     rdx, [rbp+var_30]
0x18004b53b  mov     r8, rdx
0x18004b53e  mov     rcx, r14
0x18004b541  mov     rax, [rax]
0x18004b544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b549  mov     rbx, [rbp+pwszExistingFileName]
0x18004b54d  mov     rcx, rbx; lpFileName
0x18004b550  call    cs:__imp_GetFileAttributesW
0x18004b556  cmp     eax, 0FFFFFFFFh
0x18004b559  jz      short loc_18004B5BA
0x18004b55b  mov     edx, eax; dwFileAttributes
0x18004b55d  mov     rcx, rdi; lpFileName
0x18004b560  call    cs:__imp_SetFileAttributesW
0x18004b566  test    eax, eax
0x18004b568  jnz     loc_18004B5FF
0x18004b56e  call    cs:__imp_GetLastError
0x18004b574  test    eax, eax
0x18004b576  jle     short loc_18004B580
0x18004b578  movzx   eax, ax
0x18004b57b  or      eax, 80070000h
0x18004b580  mov     [rsp+80h+var_48], rdi
0x18004b585  mov     [rsp+80h+var_50], rbx
0x18004b58a  lea     rcx, aFailedToCopyAt; "Failed to copy attributes from [%s] to "...
0x18004b591  mov     [rsp+80h+var_58], rcx
0x18004b596  mov     [rsp+80h+var_60], 0CD5h
0x18004b59e  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b5a5  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b5ac  mov     edx, eax
0x18004b5ae  mov     ecx, 1
0x18004b5b3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b5b8  jmp     short loc_18004B5FF
0x18004b5ba  call    cs:__imp_GetLastError
0x18004b5c0  test    eax, eax
0x18004b5c2  jle     short loc_18004B5CC
0x18004b5c4  movzx   eax, ax
0x18004b5c7  or      eax, 80070000h
0x18004b5cc  mov     [rsp+80h+var_50], rbx
0x18004b5d1  lea     rcx, aFailedToGetFil_0; "Failed to get file attributes for [%s]"
0x18004b5d8  mov     [rsp+80h+var_58], rcx
0x18004b5dd  mov     [rsp+80h+var_60], 0CDCh
0x18004b5e5  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b5ec  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b5f3  mov     edx, eax
0x18004b5f5  mov     ecx, 1
0x18004b5fa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b5ff  lea     rdx, [rbp+pwszNewFileName]
0x18004b603  lea     rcx, [rbp+pwszExistingFileName]
0x18004b607  call    ?CopySecurity@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::File::CopySecurity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004b60c  mov     esi, eax
0x18004b60e  test    eax, eax
0x18004b610  jns     short loc_18004B642
0x18004b612  lea     rax, aFailedToCopySe; "Failed to copy security information"
0x18004b619  mov     [rsp+80h+var_58], rax
0x18004b61e  mov     [rsp+80h+var_60], 0CE3h
0x18004b626  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004b62d  lea     r8, aPushbuttonrese_136; "PushButtonReset::File::Copy"
0x18004b634  mov     edx, esi
0x18004b636  mov     ecx, 2
0x18004b63b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004b640  jmp     short loc_18004B644
0x18004b642  xor     esi, esi
0x18004b644  lea     rcx, [rdi-18h]; this
0x18004b648  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004b64d  nop
0x18004b64e  lea     rcx, [rbx-18h]; this
0x18004b652  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004b657  mov     eax, esi
0x18004b659  add     rsp, 80h
0x18004b660  pop     r15
0x18004b662  pop     r14
0x18004b664  pop     r12
0x18004b666  pop     rdi
0x18004b667  pop     rsi
0x18004b668  pop     rbx
0x18004b669  pop     rbp
0x18004b66a  retn
```
