# PushButtonReset::Path::SetHidden(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool)

- ea: `0x18004fe94`
- end: `0x18004ffca`
- name: `?SetHidden@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z`
- size: `310`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18004c034`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180037344`
- `0x18004d404`
- `0x18004fe94`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004ff12`
- `KERNEL32!GetLastError` at `0x18004ff59`
- `KERNEL32!GetLastError` at `0x18004ff7e`
- `KERNEL32!GetLastError` at `0x18004ff12`
- `KERNEL32!GetLastError` at `0x18004ff59`
- `KERNEL32!GetLastError` at `0x18004ff7e`
- `KERNEL32!GetFileAttributesW` at `0x18004ff07`
- `KERNEL32!GetFileAttributesW` at `0x18004ff07`
- `KERNEL32!SetFileAttributesW` at `0x18004ff74`
- `KERNEL32!SetFileAttributesW` at `0x18004ff74`

## string_xrefs

- `0x18004feec`: `PushButtonReset::Path::SetHidden`
- `0x18004ff46`: `PushButtonReset::Path::SetHidden`
- `0x18004ff97`: `Failed to update attributes for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushButtonReset::Path::SetHidden(_QWORD *a1)
{
  unsigned int Canonical; // edi
  const WCHAR *v3; // rbx
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  signed int v6; // eax
  signed int v7; // eax
  LPCWSTR lpFileName; // [rsp+60h] [rbp+18h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
  v3 = lpFileName;
  if ( (Canonical & 0x80000000) == 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PushButtonReset::Path::SetHidden",
        "base\\reset\\util\\src\\filesystem.cpp",
        1245,
        L"Failed to get file attributes for [%s]",
        v3);
    }
    else
    {
      if ( SetFileAttributesW(v3, FileAttributesW | 2) )
      {
        Canonical = 0;
        goto LABEL_14;
      }
      v7 = GetLastError();
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v7,
        "PushButtonReset::Path::SetHidden",
        "base\\reset\\util\\src\\filesystem.cpp",
        1261,
        L"Failed to update attributes for [%s]",
        v3);
    }
    v6 = GetLastError();
    Canonical = v6;
    if ( v6 > 0 )
      Canonical = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      Canonical,
      "PushButtonReset::Path::SetHidden",
      "base\\reset\\util\\src\\filesystem.cpp",
      1238,
      L"Failed to get canonical form for [%s]",
      *a1);
  }
LABEL_14:
  ATL::CStringData::Release((ATL::CStringData *)(v3 - 12));
  return Canonical;
}

```

## disassembly

```asm
0x18004fe94  mov     [rsp+arg_0], rbx
0x18004fe99  mov     [rsp+arg_8], rsi
0x18004fe9e  push    rdi
0x18004fe9f  sub     rsp, 40h
0x18004fea3  mov     rsi, rcx
0x18004fea6  lea     rcx, [rsp+48h+lpFileName]
0x18004feab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004feb0  nop
0x18004feb1  lea     rdx, [rsp+48h+lpFileName]
0x18004feb6  mov     rcx, rsi
0x18004feb9  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004febe  mov     edi, eax
0x18004fec0  mov     rbx, [rsp+48h+lpFileName]
0x18004fec5  test    eax, eax
0x18004fec7  jns     short loc_18004FF04
0x18004fec9  mov     rcx, [rsi]
0x18004fecc  mov     [rsp+48h+var_18], rcx
0x18004fed1  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004fed8  mov     [rsp+48h+var_20], rax
0x18004fedd  mov     [rsp+48h+var_28], 4D6h
0x18004fee5  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004feec  lea     r8, aPushbuttonrese_23; "PushButtonReset::Path::SetHidden"
0x18004fef3  mov     edx, edi
0x18004fef5  mov     ecx, 2
0x18004fefa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004feff  jmp     loc_18004FFAF
0x18004ff04  mov     rcx, rbx; lpFileName
0x18004ff07  call    cs:__imp_GetFileAttributesW
0x18004ff0d  cmp     eax, 0FFFFFFFFh
0x18004ff10  jnz     short loc_18004FF6C
0x18004ff12  call    cs:__imp_GetLastError
0x18004ff18  mov     esi, 80070000h
0x18004ff1d  test    eax, eax
0x18004ff1f  jle     short loc_18004FF26
0x18004ff21  movzx   eax, ax
0x18004ff24  or      eax, esi
0x18004ff26  mov     [rsp+48h+var_18], rbx
0x18004ff2b  lea     rcx, aFailedToGetFil_0; "Failed to get file attributes for [%s]"
0x18004ff32  mov     [rsp+48h+var_20], rcx
0x18004ff37  mov     [rsp+48h+var_28], 4DDh
0x18004ff3f  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004ff46  lea     r8, aPushbuttonrese_23; "PushButtonReset::Path::SetHidden"
0x18004ff4d  mov     edx, eax
0x18004ff4f  mov     ecx, 2
0x18004ff54  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004ff59  call    cs:__imp_GetLastError
0x18004ff5f  mov     edi, eax
0x18004ff61  test    eax, eax
0x18004ff63  jle     short loc_18004FFAF
0x18004ff65  movzx   edi, ax
0x18004ff68  or      edi, esi
0x18004ff6a  jmp     short loc_18004FFAF
0x18004ff6c  or      eax, 2
0x18004ff6f  mov     edx, eax; dwFileAttributes
0x18004ff71  mov     rcx, rbx; lpFileName
0x18004ff74  call    cs:__imp_SetFileAttributesW
0x18004ff7a  test    eax, eax
0x18004ff7c  jnz     short loc_18004FFAD
0x18004ff7e  call    cs:__imp_GetLastError
0x18004ff84  mov     esi, 80070000h
0x18004ff89  test    eax, eax
0x18004ff8b  jle     short loc_18004FF92
0x18004ff8d  movzx   eax, ax
0x18004ff90  or      eax, esi
0x18004ff92  mov     [rsp+48h+var_18], rbx
0x18004ff97  lea     rcx, aFailedToUpdate; "Failed to update attributes for [%s]"
0x18004ff9e  mov     [rsp+48h+var_20], rcx
0x18004ffa3  mov     [rsp+48h+var_28], 4EDh
0x18004ffab  jmp     short loc_18004FF3F
0x18004ffad  xor     edi, edi
0x18004ffaf  lea     rcx, [rbx-18h]; this
0x18004ffb3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004ffb8  mov     eax, edi
0x18004ffba  mov     rbx, [rsp+48h+arg_0]
0x18004ffbf  mov     rsi, [rsp+48h+arg_8]
0x18004ffc4  add     rsp, 40h
0x18004ffc8  pop     rdi
0x18004ffc9  retn
```
