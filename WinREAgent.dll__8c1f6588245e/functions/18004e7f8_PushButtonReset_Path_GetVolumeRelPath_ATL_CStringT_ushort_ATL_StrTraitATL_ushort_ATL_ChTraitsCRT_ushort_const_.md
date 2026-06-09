# PushButtonReset::Path::GetVolumeRelPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x18004e7f8`
- end: `0x18004e99c`
- name: `?GetVolumeRelPath@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `420`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180034480`
- `0x1800345c0`
- `0x1800346cc`
- `0x180052fd0`
- `0x180057ecc`

## callees

- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x1800340cc`
- `0x180037344`
- `0x18004e7f8`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004e84e`
- `KERNEL32!GetLastError` at `0x18004e895`
- `KERNEL32!GetLastError` at `0x18004e84e`
- `KERNEL32!GetLastError` at `0x18004e895`
- `KERNEL32!GetVolumePathNameW` at `0x18004e83f`
- `KERNEL32!GetVolumePathNameW` at `0x18004e83f`

## string_xrefs

- `0x18004e867`: `Failed to get mount point for [%s]`
- `0x18004e882`: `PushButtonReset::Path::GetVolumeRelPath`
- `0x18004e8f2`: `PushButtonReset::Path::GetVolumeRelPath`
- `0x18004e8d7`: `Mount point [%s] exceeds length of [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall PushButtonReset::Path::GetVolumeRelPath(LPCWSTR *a1, _QWORD *a2)
{
  BOOL VolumePathNameW; // eax
  LPCWSTR v5; // rbx
  signed int LastError; // eax
  signed int result; // eax
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // [rsp+40h] [rbp-248h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+50h] [rbp-238h] BYREF

  memset_0(szVolumePathName, 0, 0x20Au);
  VolumePathNameW = GetVolumePathNameW(*a1, szVolumePathName, 0x104u);
  v5 = *a1;
  if ( VolumePathNameW )
  {
    v8 = *((int *)v5 - 4);
    v9 = -1;
    do
      ++v9;
    while ( szVolumePathName[v9] );
    if ( v9 <= v8 )
    {
      v10 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                         a1,
                         &v14,
                         (unsigned int)(v8 - v9 + 1));
      v11 = (_QWORD *)(v10 - 24);
      v12 = (int *)(*a2 - 24LL);
      if ( (int *)(v10 - 24) != v12 )
      {
        if ( v12[4] >= 0 && *v11 == *(_QWORD *)v12 )
        {
          v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v11);
          ATL::CStringData::Release((ATL::CStringData *)v12);
          *a2 = v13 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v10, *(unsigned int *)(v10 - 16));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
      return 0;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147549183LL,
        "PushButtonReset::Path::GetVolumeRelPath",
        "base\\reset\\util\\src\\filesystem.cpp",
        1368,
        L"Mount point [%s] exceeds length of [%s]",
        szVolumePathName,
        *a1);
      return -2147418113;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::Path::GetVolumeRelPath",
      "base\\reset\\util\\src\\filesystem.cpp",
      1361,
      L"Failed to get mount point for [%s]",
      v5);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18004e7f8  mov     [rsp+arg_10], rbx
0x18004e7fd  push    rbp
0x18004e7fe  push    rsi
0x18004e7ff  push    rdi
0x18004e800  sub     rsp, 270h
0x18004e807  mov     rax, cs:__security_cookie
0x18004e80e  xor     rax, rsp
0x18004e811  mov     [rsp+288h+var_28], rax
0x18004e819  mov     rsi, rdx
0x18004e81c  mov     rdi, rcx
0x18004e81f  xor     edx, edx; Val
0x18004e821  mov     r8d, 20Ah; Size
0x18004e827  lea     rcx, [rsp+288h+szVolumePathName]; void *
0x18004e82c  call    memset_0
0x18004e831  mov     r8d, 104h; cchBufferLength
0x18004e837  lea     rdx, [rsp+288h+szVolumePathName]; lpszVolumePathName
0x18004e83c  mov     rcx, [rdi]; lpszFileName
0x18004e83f  call    cs:__imp_GetVolumePathNameW
0x18004e845  mov     rbx, [rdi]
0x18004e848  xor     ebp, ebp
0x18004e84a  test    eax, eax
0x18004e84c  jnz     short loc_18004E8AD
0x18004e84e  call    cs:__imp_GetLastError
0x18004e854  mov     edi, 80070000h
0x18004e859  test    eax, eax
0x18004e85b  jle     short loc_18004E862
0x18004e85d  movzx   eax, ax
0x18004e860  or      eax, edi
0x18004e862  mov     [rsp+288h+var_258], rbx
0x18004e867  lea     rcx, aFailedToGetMou; "Failed to get mount point for [%s]"
0x18004e86e  mov     [rsp+288h+var_260], rcx
0x18004e873  mov     [rsp+288h+var_268], 551h
0x18004e87b  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004e882  lea     r8, aPushbuttonrese_110; "PushButtonReset::Path::GetVolumeRelPath"
0x18004e889  mov     edx, eax
0x18004e88b  mov     ecx, 2
0x18004e890  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004e895  call    cs:__imp_GetLastError
0x18004e89b  test    eax, eax
0x18004e89d  jle     loc_18004E979
0x18004e8a3  movzx   eax, ax
0x18004e8a6  or      eax, edi
0x18004e8a8  jmp     loc_18004E979
0x18004e8ad  movsxd  r8, dword ptr [rbx-10h]
0x18004e8b1  lea     rax, [rsp+288h+szVolumePathName]
0x18004e8b6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004e8ba  inc     rcx
0x18004e8bd  cmp     [rax+rcx*2], bp
0x18004e8c1  jnz     short loc_18004E8BA
0x18004e8c3  cmp     rcx, r8
0x18004e8c6  jbe     short loc_18004E90F
0x18004e8c8  mov     [rsp+288h+var_250], rbx
0x18004e8cd  lea     rax, [rsp+288h+szVolumePathName]
0x18004e8d2  mov     [rsp+288h+var_258], rax
0x18004e8d7  lea     rax, aMountPointSExc; "Mount point [%s] exceeds length of [%s]"
0x18004e8de  mov     [rsp+288h+var_260], rax
0x18004e8e3  mov     [rsp+288h+var_268], 558h
0x18004e8eb  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004e8f2  lea     r8, aPushbuttonrese_110; "PushButtonReset::Path::GetVolumeRelPath"
0x18004e8f9  mov     edx, 8000FFFFh
0x18004e8fe  mov     ecx, 2
0x18004e903  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004e908  mov     eax, 8000FFFFh
0x18004e90d  jmp     short loc_18004E979
0x18004e90f  sub     r8d, ecx
0x18004e912  inc     r8d
0x18004e915  lea     rdx, [rsp+288h+var_248]
0x18004e91a  mov     rcx, rdi
0x18004e91d  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x18004e922  nop
0x18004e923  mov     rdx, [rax]
0x18004e926  lea     rcx, [rdx-18h]
0x18004e92a  mov     rdi, [rsi]
0x18004e92d  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18004e931  cmp     rcx, rdi
0x18004e934  jz      short loc_18004E969
0x18004e936  cmp     [rdi+10h], ebp
0x18004e939  jl      short loc_18004E95C
0x18004e93b  mov     rax, [rdi]
0x18004e93e  cmp     [rcx], rax
0x18004e941  jnz     short loc_18004E95C
0x18004e943  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004e948  mov     rbx, rax
0x18004e94b  mov     rcx, rdi; this
0x18004e94e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e953  lea     rax, [rbx+18h]
0x18004e957  mov     [rsi], rax
0x18004e95a  jmp     short loc_18004E969
0x18004e95c  mov     r8d, [rdx-10h]
0x18004e960  mov     rcx, rsi
0x18004e963  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004e968  nop
0x18004e969  mov     rcx, [rsp+288h+var_248]
0x18004e96e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004e972  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e977  xor     eax, eax
0x18004e979  mov     rcx, [rsp+288h+var_28]
0x18004e981  xor     rcx, rsp; StackCookie
0x18004e984  call    __security_check_cookie
0x18004e989  mov     rbx, [rsp+288h+arg_10]
0x18004e991  add     rsp, 270h
0x18004e998  pop     rdi
0x18004e999  pop     rsi
0x18004e99a  pop     rbp
0x18004e99b  retn
```
