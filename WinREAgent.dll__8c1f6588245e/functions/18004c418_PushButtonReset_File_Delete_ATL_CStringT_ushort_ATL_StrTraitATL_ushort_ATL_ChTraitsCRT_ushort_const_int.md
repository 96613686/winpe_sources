# PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)

- ea: `0x18004c418`
- end: `0x18004c60b`
- name: `?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180006de8`
- `0x180018820`
- `0x18001b268`
- `0x18001fa60`
- `0x1800227f0`
- `0x180023ea0`
- `0x1800240fc`
- `0x180024890`
- `0x18002bb80`
- `0x18002bff0`
- `0x18002fef4`
- `0x1800308cc`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180037344`
- `0x18004c418`
- `0x18004d404`
- `0x18004f39c`
- `0x180066484`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004c4a9`
- `KERNEL32!GetLastError` at `0x18004c4f0`
- `KERNEL32!GetLastError` at `0x18004c521`
- `KERNEL32!GetLastError` at `0x18004c5c1`
- `KERNEL32!GetLastError` at `0x18004c4a9`
- `KERNEL32!GetLastError` at `0x18004c4f0`
- `KERNEL32!GetLastError` at `0x18004c521`
- `KERNEL32!GetLastError` at `0x18004c5c1`
- `KERNEL32!GetFileAttributesW` at `0x18004c49c`
- `KERNEL32!GetFileAttributesW` at `0x18004c49c`
- `KERNEL32!SetFileAttributesW` at `0x18004c512`
- `KERNEL32!SetFileAttributesW` at `0x18004c512`

## string_xrefs

- `0x18004c5d5`: `Failed to delete [%s]`
- `0x18004c535`: `Failed to remove read-only/archive bits from [%s]`
- `0x18004c46b`: `PushButtonReset::File::Delete`
- `0x18004c4dd`: `PushButtonReset::File::Delete`
- `0x18004c550`: `PushButtonReset::File::Delete`
- `0x18004c59e`: `PushButtonReset::File::Delete`
- `0x18004c583`: `Failed to delete reparse point [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushButtonReset::File::Delete(_QWORD *a1)
{
  int Canonical; // ebx
  const WCHAR *v4; // rbx
  DWORD FileAttributesW; // edi
  signed int LastError; // eax
  signed int v7; // eax
  unsigned int v8; // edi
  DWORD v9; // edi
  signed int v10; // eax
  signed int v11; // eax
  LPCWSTR lpFileName; // [rsp+60h] [rbp+18h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
  if ( Canonical < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Canonical,
      "PushButtonReset::File::Delete",
      "base\\reset\\util\\src\\filesystem.cpp",
      3438,
      L"Failed to get canonical form for [%s]",
      *a1);
    ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
    return (unsigned int)Canonical;
  }
  v4 = lpFileName;
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::File::Delete",
      "base\\reset\\util\\src\\filesystem.cpp",
      3450,
      L"Failed to get file attributes for [%s]",
      v4);
LABEL_7:
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_21;
  }
  v9 = FileAttributesW & 0xFFFFFFDE;
  if ( !SetFileAttributesW(v4, v9) )
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v10,
      "PushButtonReset::File::Delete",
      "base\\reset\\util\\src\\filesystem.cpp",
      3460,
      L"Failed to remove read-only/archive bits from [%s]",
      v4);
  }
  if ( (v9 & 0x400) != 0 && (v8 = PbrDeleteReparsePoint(&lpFileName), v4 = lpFileName, (v8 & 0x80000000) != 0) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      v8,
      "PushButtonReset::File::Delete",
      "base\\reset\\util\\src\\filesystem.cpp",
      3467,
      L"Failed to delete reparse point [%s]",
      lpFileName);
  }
  else
  {
    if ( !DeleteFileEx2((__int64)v4, 0) )
    {
      v11 = GetLastError();
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "PushButtonReset::File::Delete",
        "base\\reset\\util\\src\\filesystem.cpp",
        3474,
        L"Failed to delete [%s]",
        v4);
      goto LABEL_7;
    }
    v8 = 0;
  }
LABEL_21:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return v8;
}

```

## disassembly

```asm
0x18004c418  mov     [rsp+arg_0], rbx
0x18004c41d  mov     [rsp+arg_8], rsi
0x18004c422  push    rdi
0x18004c423  sub     rsp, 40h
0x18004c427  mov     rdi, rcx
0x18004c42a  lea     rcx, [rsp+48h+lpFileName]
0x18004c42f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004c434  nop
0x18004c435  lea     rdx, [rsp+48h+lpFileName]
0x18004c43a  mov     rcx, rdi
0x18004c43d  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004c442  mov     ebx, eax
0x18004c444  test    eax, eax
0x18004c446  jns     short loc_18004C494
0x18004c448  mov     rcx, [rdi]
0x18004c44b  mov     [rsp+48h+var_18], rcx
0x18004c450  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004c457  mov     [rsp+48h+var_20], rax
0x18004c45c  mov     [rsp+48h+var_28], 0D6Eh
0x18004c464  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c46b  lea     r8, aPushbuttonrese_51; "PushButtonReset::File::Delete"
0x18004c472  mov     edx, ebx
0x18004c474  mov     ecx, 2
0x18004c479  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c47e  nop
0x18004c47f  mov     rcx, [rsp+48h+lpFileName]
0x18004c484  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004c488  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004c48d  mov     eax, ebx
0x18004c48f  jmp     loc_18004C5FB
0x18004c494  mov     rbx, [rsp+48h+lpFileName]
0x18004c499  mov     rcx, rbx; lpFileName
0x18004c49c  call    cs:__imp_GetFileAttributesW
0x18004c4a2  mov     edi, eax
0x18004c4a4  cmp     eax, 0FFFFFFFFh
0x18004c4a7  jnz     short loc_18004C50A
0x18004c4a9  call    cs:__imp_GetLastError
0x18004c4af  mov     esi, 80070000h
0x18004c4b4  test    eax, eax
0x18004c4b6  jle     short loc_18004C4BD
0x18004c4b8  movzx   eax, ax
0x18004c4bb  or      eax, esi
0x18004c4bd  mov     [rsp+48h+var_18], rbx
0x18004c4c2  lea     rcx, aFailedToGetFil_0; "Failed to get file attributes for [%s]"
0x18004c4c9  mov     [rsp+48h+var_20], rcx
0x18004c4ce  mov     [rsp+48h+var_28], 0D7Ah
0x18004c4d6  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c4dd  lea     r8, aPushbuttonrese_51; "PushButtonReset::File::Delete"
0x18004c4e4  mov     edx, eax
0x18004c4e6  mov     ecx, 2
0x18004c4eb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c4f0  call    cs:__imp_GetLastError
0x18004c4f6  mov     edi, eax
0x18004c4f8  test    eax, eax
0x18004c4fa  jle     loc_18004C5F0
0x18004c500  movzx   edi, ax
0x18004c503  or      edi, esi
0x18004c505  jmp     loc_18004C5F0
0x18004c50a  and     edi, 0FFFFFFDEh
0x18004c50d  mov     edx, edi; dwFileAttributes
0x18004c50f  mov     rcx, rbx; lpFileName
0x18004c512  call    cs:__imp_SetFileAttributesW
0x18004c518  mov     esi, 80070000h
0x18004c51d  test    eax, eax
0x18004c51f  jnz     short loc_18004C563
0x18004c521  call    cs:__imp_GetLastError
0x18004c527  test    eax, eax
0x18004c529  jle     short loc_18004C530
0x18004c52b  movzx   eax, ax
0x18004c52e  or      eax, esi
0x18004c530  mov     [rsp+48h+var_18], rbx
0x18004c535  lea     rcx, aFailedToRemove_0; "Failed to remove read-only/archive bits"...
0x18004c53c  mov     [rsp+48h+var_20], rcx
0x18004c541  mov     [rsp+48h+var_28], 0D84h
0x18004c549  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c550  lea     r8, aPushbuttonrese_51; "PushButtonReset::File::Delete"
0x18004c557  mov     edx, eax
0x18004c559  mov     ecx, 1
0x18004c55e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c563  bt      edi, 0Ah
0x18004c567  jnb     short loc_18004C5B3
0x18004c569  lea     rcx, [rsp+48h+lpFileName]
0x18004c56e  call    PbrDeleteReparsePoint
0x18004c573  mov     edi, eax
0x18004c575  mov     rbx, [rsp+48h+lpFileName]
0x18004c57a  test    eax, eax
0x18004c57c  jns     short loc_18004C5B3
0x18004c57e  mov     [rsp+48h+var_18], rbx
0x18004c583  lea     rax, aFailedToDelete_0; "Failed to delete reparse point [%s]"
0x18004c58a  mov     [rsp+48h+var_20], rax
0x18004c58f  mov     [rsp+48h+var_28], 0D8Bh
0x18004c597  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004c59e  lea     r8, aPushbuttonrese_51; "PushButtonReset::File::Delete"
0x18004c5a5  mov     edx, edi
0x18004c5a7  mov     ecx, 2
0x18004c5ac  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004c5b1  jmp     short loc_18004C5F0
0x18004c5b3  xor     edx, edx
0x18004c5b5  mov     rcx, rbx
0x18004c5b8  call    DeleteFileEx2
0x18004c5bd  test    eax, eax
0x18004c5bf  jnz     short loc_18004C5EE
0x18004c5c1  call    cs:__imp_GetLastError
0x18004c5c7  test    eax, eax
0x18004c5c9  jle     short loc_18004C5D0
0x18004c5cb  movzx   eax, ax
0x18004c5ce  or      eax, esi
0x18004c5d0  mov     [rsp+48h+var_18], rbx
0x18004c5d5  lea     rcx, aFailedToDelete_19; "Failed to delete [%s]"
0x18004c5dc  mov     [rsp+48h+var_20], rcx
0x18004c5e1  mov     [rsp+48h+var_28], 0D92h
0x18004c5e9  jmp     loc_18004C4D6
0x18004c5ee  xor     edi, edi
0x18004c5f0  lea     rcx, [rbx-18h]; this
0x18004c5f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004c5f9  mov     eax, edi
0x18004c5fb  mov     rbx, [rsp+48h+arg_0]
0x18004c600  mov     rsi, [rsp+48h+arg_8]
0x18004c605  add     rsp, 40h
0x18004c609  pop     rdi
0x18004c60a  retn
```
