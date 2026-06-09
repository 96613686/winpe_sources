# PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x18004e5a4`
- end: `0x18004e7ef`
- name: `?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `587`
- prototype: ``
- caller_count: `13`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x18001e51c`
- `0x180024a40`
- `0x180025180`
- `0x180026320`
- `0x180028220`
- `0x1800346cc`
- `0x18003ba10`
- `0x18003bbf4`
- `0x180047d1c`
- `0x18004d8d0`
- `0x18004ebec`
- `0x18004f17c`
- `0x180054ff8`

## callees

- `0x1800049a4`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x180033b18`
- `0x180033be0`
- `0x180037344`
- `0x18004e5a4`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004e601`
- `KERNEL32!GetLastError` at `0x18004e648`
- `KERNEL32!GetLastError` at `0x18004e68d`
- `KERNEL32!GetLastError` at `0x18004e601`
- `KERNEL32!GetLastError` at `0x18004e648`
- `KERNEL32!GetLastError` at `0x18004e68d`
- `KERNEL32!GetVolumePathNameW` at `0x18004e5f4`
- `KERNEL32!GetVolumePathNameW` at `0x18004e5f4`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004e683`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004e683`

## string_xrefs

- `0x18004e61a`: `Failed to get mount point for [%s]`
- `0x18004e635`: `PushButtonReset::Path::GetVolume`
- `0x18004e6ab`: `Failed to get volume name for mount point [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall PushButtonReset::Path::GetVolume(LPCWSTR *a1, _QWORD *a2)
{
  LPCWSTR v4; // rdi
  signed int LastError; // eax
  signed int result; // eax
  signed int v7; // eax
  __int64 v8; // rcx
  int v9; // edx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  int *v12; // rdi
  __int64 v13; // rbx
  int *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(szVolumePathName, 0, 0x20Au);
  if ( !GetVolumePathNameW(*a1, szVolumePathName, 0x104u) )
  {
    v4 = *a1;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::Path::GetVolume",
      "base\\reset\\util\\src\\filesystem.cpp",
      1288,
      L"Failed to get mount point for [%s]",
      v4);
LABEL_5:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  memset_0(szVolumeName, 0, 0x20Au);
  if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "PushButtonReset::Path::GetVolume",
      "base\\reset\\util\\src\\filesystem.cpp",
      1298,
      L"Failed to get volume name for mount point [%s]",
      szVolumePathName);
    goto LABEL_5;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)szVolumeName);
  v8 = v16;
  v9 = *(_DWORD *)(v16 - 16);
  if ( v9 > 0 )
  {
    if ( (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(&v16, (unsigned int)(v9 - 1)) == 92 )
    {
      v10 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                         &v16,
                         &v17,
                         (unsigned int)(*(_DWORD *)(v16 - 16) - 1));
      v11 = (_QWORD *)(v10 - 24);
      v12 = (int *)(v16 - 24);
      if ( v10 - 24 != v16 - 24 )
      {
        if ( v12[4] >= 0 && *v11 == *(_QWORD *)v12 )
        {
          v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v11);
          ATL::CStringData::Release((ATL::CStringData *)v12);
          v16 = v13 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v16, v10, *(unsigned int *)(v10 - 16));
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    }
    v8 = v16;
  }
  v14 = (int *)(*a2 - 24LL);
  if ( (int *)(v8 - 24) != v14 )
  {
    if ( v14[4] >= 0 && *(_QWORD *)(v8 - 24) == *(_QWORD *)v14 )
    {
      v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v8 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v14);
      *a2 = v15 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v8, *(unsigned int *)(v8 - 16));
    }
    v8 = v16;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
  return 0;
}

```

## disassembly

```asm
0x18004e5a4  mov     [rsp-8+arg_10], rbx
0x18004e5a9  push    rbp
0x18004e5aa  push    rsi
0x18004e5ab  push    rdi
0x18004e5ac  lea     rbp, [rsp-380h]
0x18004e5b4  sub     rsp, 480h
0x18004e5bb  mov     rax, cs:__security_cookie
0x18004e5c2  xor     rax, rsp
0x18004e5c5  mov     [rbp+390h+var_20], rax
0x18004e5cc  mov     rsi, rdx
0x18004e5cf  mov     rbx, rcx
0x18004e5d2  mov     edi, 20Ah
0x18004e5d7  mov     r8d, edi; Size
0x18004e5da  xor     edx, edx; Val
0x18004e5dc  lea     rcx, [rsp+490h+szVolumePathName]; void *
0x18004e5e1  call    memset_0
0x18004e5e6  mov     r8d, 104h; cchBufferLength
0x18004e5ec  lea     rdx, [rsp+490h+szVolumePathName]; lpszVolumePathName
0x18004e5f1  mov     rcx, [rbx]; lpszFileName
0x18004e5f4  call    cs:__imp_GetVolumePathNameW
0x18004e5fa  test    eax, eax
0x18004e5fc  jnz     short loc_18004E660
0x18004e5fe  mov     rdi, [rbx]
0x18004e601  call    cs:__imp_GetLastError
0x18004e607  mov     ebx, 80070000h
0x18004e60c  test    eax, eax
0x18004e60e  jle     short loc_18004E615
0x18004e610  movzx   eax, ax
0x18004e613  or      eax, ebx
0x18004e615  mov     [rsp+490h+var_460], rdi
0x18004e61a  lea     rcx, aFailedToGetMou; "Failed to get mount point for [%s]"
0x18004e621  mov     [rsp+490h+var_468], rcx
0x18004e626  mov     [rsp+490h+var_470], 508h
0x18004e62e  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004e635  lea     r8, aPushbuttonrese_121; "PushButtonReset::Path::GetVolume"
0x18004e63c  mov     edx, eax
0x18004e63e  mov     ecx, 2
0x18004e643  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004e648  call    cs:__imp_GetLastError
0x18004e64e  test    eax, eax
0x18004e650  jle     loc_18004E7CD
0x18004e656  movzx   eax, ax
0x18004e659  or      eax, ebx
0x18004e65b  jmp     loc_18004E7CD
0x18004e660  mov     r8, rdi; Size
0x18004e663  xor     edx, edx; Val
0x18004e665  lea     rcx, [rbp+390h+szVolumeName]; void *
0x18004e66c  call    memset_0
0x18004e671  mov     r8d, 104h; cchBufferLength
0x18004e677  lea     rdx, [rbp+390h+szVolumeName]; lpszVolumeName
0x18004e67e  lea     rcx, [rsp+490h+szVolumePathName]; lpszVolumeMountPoint
0x18004e683  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004e689  test    eax, eax
0x18004e68b  jnz     short loc_18004E6C4
0x18004e68d  call    cs:__imp_GetLastError
0x18004e693  mov     ebx, 80070000h
0x18004e698  test    eax, eax
0x18004e69a  jle     short loc_18004E6A1
0x18004e69c  movzx   eax, ax
0x18004e69f  or      eax, ebx
0x18004e6a1  lea     rcx, [rsp+490h+szVolumePathName]
0x18004e6a6  mov     [rsp+490h+var_460], rcx
0x18004e6ab  lea     rcx, aFailedToGetVol_8; "Failed to get volume name for mount poi"...
0x18004e6b2  mov     [rsp+490h+var_468], rcx
0x18004e6b7  mov     [rsp+490h+var_470], 512h
0x18004e6bf  jmp     loc_18004E62E
0x18004e6c4  lea     rdx, [rbp+390h+szVolumeName]
0x18004e6cb  lea     rcx, [rsp+490h+var_450]
0x18004e6d0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18004e6d5  nop
0x18004e6d6  mov     rcx, [rsp+490h+var_450]
0x18004e6db  mov     edx, [rcx-10h]
0x18004e6de  test    edx, edx
0x18004e6e0  jle     loc_18004E774
0x18004e6e6  dec     edx
0x18004e6e8  lea     rcx, [rsp+490h+var_450]
0x18004e6ed  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004e6f2  cmp     ax, 5Ch ; '\'
0x18004e6f6  jnz     short loc_18004E76F
0x18004e6f8  mov     rax, [rsp+490h+var_450]
0x18004e6fd  mov     r8d, [rax-10h]
0x18004e701  dec     r8d
0x18004e704  lea     rdx, [rsp+490h+var_448]
0x18004e709  lea     rcx, [rsp+490h+var_450]
0x18004e70e  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18004e713  nop
0x18004e714  mov     rdx, [rax]
0x18004e717  lea     rcx, [rdx-18h]
0x18004e71b  mov     rdi, [rsp+490h+var_450]
0x18004e720  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18004e724  cmp     rcx, rdi
0x18004e727  jz      short loc_18004E761
0x18004e729  cmp     dword ptr [rdi+10h], 0
0x18004e72d  jl      short loc_18004E752
0x18004e72f  mov     rax, [rdi]
0x18004e732  cmp     [rcx], rax
0x18004e735  jnz     short loc_18004E752
0x18004e737  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004e73c  mov     rbx, rax
0x18004e73f  mov     rcx, rdi; this
0x18004e742  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e747  lea     rax, [rbx+18h]
0x18004e74b  mov     [rsp+490h+var_450], rax
0x18004e750  jmp     short loc_18004E761
0x18004e752  mov     r8d, [rdx-10h]
0x18004e756  lea     rcx, [rsp+490h+var_450]
0x18004e75b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004e760  nop
0x18004e761  mov     rcx, [rsp+490h+var_448]
0x18004e766  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004e76a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e76f  mov     rcx, [rsp+490h+var_450]
0x18004e774  lea     rdx, [rcx-18h]
0x18004e778  mov     rdi, [rsi]
0x18004e77b  add     rdi, 0FFFFFFFFFFFFFFE8h
0x18004e77f  cmp     rdx, rdi
0x18004e782  jz      short loc_18004E7C2
0x18004e784  cmp     dword ptr [rdi+10h], 0
0x18004e788  jl      short loc_18004E7AE
0x18004e78a  mov     rax, [rdi]
0x18004e78d  cmp     [rdx], rax
0x18004e790  jnz     short loc_18004E7AE
0x18004e792  mov     rcx, rdx
0x18004e795  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004e79a  mov     rbx, rax
0x18004e79d  mov     rcx, rdi; this
0x18004e7a0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e7a5  lea     rax, [rbx+18h]
0x18004e7a9  mov     [rsi], rax
0x18004e7ac  jmp     short loc_18004E7BD
0x18004e7ae  mov     r8d, [rcx-10h]
0x18004e7b2  mov     rdx, rcx
0x18004e7b5  mov     rcx, rsi
0x18004e7b8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004e7bd  mov     rcx, [rsp+490h+var_450]
0x18004e7c2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004e7c6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004e7cb  xor     eax, eax
0x18004e7cd  mov     rcx, [rbp+390h+var_20]
0x18004e7d4  xor     rcx, rsp; StackCookie
0x18004e7d7  call    __security_check_cookie
0x18004e7dc  mov     rbx, [rsp+490h+arg_10]
0x18004e7e4  add     rsp, 480h
0x18004e7eb  pop     rdi
0x18004e7ec  pop     rsi
0x18004e7ed  pop     rbp
0x18004e7ee  retn
```
