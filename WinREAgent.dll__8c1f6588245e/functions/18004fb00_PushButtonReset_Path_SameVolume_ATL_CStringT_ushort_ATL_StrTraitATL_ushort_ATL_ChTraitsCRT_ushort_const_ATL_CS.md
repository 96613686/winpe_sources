# PushButtonReset::Path::SameVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *)

- ea: `0x18004fb00`
- end: `0x18004fe8c`
- name: `?SameVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEA_N@Z`
- size: `908`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800346cc`
- `0x18003f4b8`
- `0x180041cb0`

## callees

- `0x180004af8`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002476c`
- `0x180033b18`
- `0x180037344`
- `0x18004fb00`
- `0x18006c652`
- `0x18006c690`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004fe4b`
- `msvcrt!_wcsicmp` at `0x18004fe4b`
- `KERNEL32!GetLastError` at `0x18004fc51`
- `KERNEL32!GetLastError` at `0x18004fc9a`
- `KERNEL32!GetLastError` at `0x18004fdd9`
- `KERNEL32!GetLastError` at `0x18004fe22`
- `KERNEL32!GetLastError` at `0x18004fc51`
- `KERNEL32!GetLastError` at `0x18004fc9a`
- `KERNEL32!GetLastError` at `0x18004fdd9`
- `KERNEL32!GetLastError` at `0x18004fe22`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004fc47`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004fdcf`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004fc47`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18004fdcf`

## string_xrefs

- `0x18004fc87`: `PushButtonReset::Path::SameVolume`
- `0x18004fe0f`: `PushButtonReset::Path::SameVolume`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PushButtonReset::Path::SameVolume(__int64 *a1, __int64 *a2, bool *a3)
{
  int v6; // edx
  __int64 v7; // rdx
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rdi
  int *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  int *v14; // rbx
  __int64 v15; // rdi
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // ebx
  int v20; // edx
  __int64 v21; // rdx
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rbx
  int *v24; // rsi
  __int64 v25; // rbx
  __int64 v26; // rdx
  _QWORD *v27; // rcx
  int *v28; // rsi
  __int64 v29; // rbx
  signed int LastError; // eax
  signed int v31; // eax
  unsigned int v32; // esi
  LPCWSTR v33; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpszVolumeMountPoint; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String2[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+270h] [rbp+170h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpszVolumeMountPoint);
  v6 = *(_DWORD *)(*a1 - 16);
  if ( v6 > 0 && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a1, (unsigned int)(v6 - 1)) == 92 )
  {
    v7 = *a1;
    v8 = (const WCHAR *)(*a1 - 24);
    v9 = lpszVolumeMountPoint;
    v10 = (int *)(lpszVolumeMountPoint - 12);
    if ( v8 != lpszVolumeMountPoint - 12 )
    {
      if ( v10[4] >= 0 && *(_QWORD *)v8 == *(_QWORD *)v10 )
      {
        v11 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v8);
        ATL::CStringData::Release((ATL::CStringData *)v10);
        v9 = (const WCHAR *)(v11 + 24);
        lpszVolumeMountPoint = v9;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpszVolumeMountPoint, v7, *(unsigned int *)(v7 - 16));
        v9 = lpszVolumeMountPoint;
      }
    }
  }
  else
  {
    v12 = *(_QWORD *)ATL::operator+(&v33, a1, L"\\");
    v13 = (_QWORD *)(v12 - 24);
    v9 = lpszVolumeMountPoint;
    v14 = (int *)(lpszVolumeMountPoint - 12);
    if ( (LPCWSTR)(v12 - 24) != lpszVolumeMountPoint - 12 )
    {
      if ( v14[4] >= 0 && *v13 == *(_QWORD *)v14 )
      {
        v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
        ATL::CStringData::Release((ATL::CStringData *)v14);
        v9 = (const WCHAR *)(v15 + 24);
        lpszVolumeMountPoint = v9;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&lpszVolumeMountPoint, v12, *(unsigned int *)(v12 - 16));
        v9 = lpszVolumeMountPoint;
      }
    }
    ATL::CStringData::Release((ATL::CStringData *)(v33 - 12));
  }
  memset_0(szVolumeName, 0, 0x20Au);
  if ( GetVolumeNameForVolumeMountPointW(v9, szVolumeName, 0x104u) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v33);
    v20 = *(_DWORD *)(*a2 - 16);
    if ( v20 > 0 && (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::GetAt(a2, (unsigned int)(v20 - 1)) == 92 )
    {
      v21 = *a2;
      v22 = (const WCHAR *)(*a2 - 24);
      v23 = v33;
      v24 = (int *)(v33 - 12);
      if ( v22 != v33 - 12 )
      {
        if ( v24[4] >= 0 && *(_QWORD *)v22 == *(_QWORD *)v24 )
        {
          v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v22);
          ATL::CStringData::Release((ATL::CStringData *)v24);
          v23 = (const WCHAR *)(v25 + 24);
          v33 = v23;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v21, *(unsigned int *)(v21 - 16));
          v23 = v33;
        }
      }
    }
    else
    {
      v26 = *(_QWORD *)ATL::operator+(&v35, a2, L"\\");
      v27 = (_QWORD *)(v26 - 24);
      v23 = v33;
      v28 = (int *)(v33 - 12);
      if ( (LPCWSTR)(v26 - 24) != v33 - 12 )
      {
        if ( v28[4] >= 0 && *v27 == *(_QWORD *)v28 )
        {
          v29 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v27);
          ATL::CStringData::Release((ATL::CStringData *)v28);
          v23 = (const WCHAR *)(v29 + 24);
          v33 = v23;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v26, *(unsigned int *)(v26 - 16));
          v23 = v33;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
    }
    memset_0(String2, 0, 0x20Au);
    if ( GetVolumeNameForVolumeMountPointW(v23, String2, 0x104u) )
    {
      *a3 = _wcsicmp(szVolumeName, String2) == 0;
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
      v32 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PushButtonReset::Path::SameVolume",
        "base\\reset\\util\\src\\filesystem.cpp",
        774,
        L"Failed to look up volume GUID for [%s]",
        v23);
      v31 = GetLastError();
      v32 = v31;
      if ( v31 > 0 )
        v32 = (unsigned __int16)v31 | 0x80070000;
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 12));
    }
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
    return v32;
  }
  else
  {
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v16,
      "PushButtonReset::Path::SameVolume",
      "base\\reset\\util\\src\\filesystem.cpp",
      755,
      L"Failed to look up volume GUID for [%s]",
      v9);
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
    return v18;
  }
}

```

## disassembly

```asm
0x18004fb00  push    rbp
0x18004fb02  push    rbx
0x18004fb03  push    rsi
0x18004fb04  push    rdi
0x18004fb05  push    r14
0x18004fb07  lea     rbp, [rsp-390h]
0x18004fb0f  sub     rsp, 490h
0x18004fb16  mov     rax, cs:__security_cookie
0x18004fb1d  xor     rax, rsp
0x18004fb20  mov     [rbp+3B0h+var_30], rax
0x18004fb27  mov     r14, r8
0x18004fb2a  mov     rsi, rdx
0x18004fb2d  mov     rbx, rcx
0x18004fb30  lea     rcx, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fb35  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004fb3a  nop
0x18004fb3b  mov     rax, [rbx]
0x18004fb3e  mov     edx, [rax-10h]
0x18004fb41  test    edx, edx
0x18004fb43  jle     short loc_18004FBAF
0x18004fb45  dec     edx
0x18004fb47  mov     rcx, rbx
0x18004fb4a  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004fb4f  cmp     ax, 5Ch ; '\'
0x18004fb53  jnz     short loc_18004FBAF
0x18004fb55  mov     rdx, [rbx]
0x18004fb58  lea     rcx, [rdx-18h]
0x18004fb5c  mov     rdi, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fb61  lea     rbx, [rdi-18h]
0x18004fb65  cmp     rcx, rbx
0x18004fb68  jz      loc_18004FC23
0x18004fb6e  cmp     dword ptr [rbx+10h], 0
0x18004fb72  jl      short loc_18004FB9A
0x18004fb74  mov     rax, [rbx]
0x18004fb77  cmp     [rcx], rax
0x18004fb7a  jnz     short loc_18004FB9A
0x18004fb7c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004fb81  mov     rdi, rax
0x18004fb84  mov     rcx, rbx; this
0x18004fb87  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fb8c  add     rdi, 18h
0x18004fb90  mov     [rsp+4B0h+lpszVolumeMountPoint], rdi
0x18004fb95  jmp     loc_18004FC23
0x18004fb9a  mov     r8d, [rdx-10h]
0x18004fb9e  lea     rcx, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fba3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004fba8  mov     rdi, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fbad  jmp     short loc_18004FC23
0x18004fbaf  lea     r8, SubBlock; "\\"
0x18004fbb6  mov     rdx, rbx
0x18004fbb9  lea     rcx, [rsp+4B0h+var_470]
0x18004fbbe  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18004fbc3  nop
0x18004fbc4  mov     rdx, [rax]
0x18004fbc7  lea     rcx, [rdx-18h]
0x18004fbcb  mov     rdi, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fbd0  lea     rbx, [rdi-18h]
0x18004fbd4  cmp     rcx, rbx
0x18004fbd7  jz      short loc_18004FC15
0x18004fbd9  cmp     dword ptr [rbx+10h], 0
0x18004fbdd  jl      short loc_18004FC02
0x18004fbdf  mov     rax, [rbx]
0x18004fbe2  cmp     [rcx], rax
0x18004fbe5  jnz     short loc_18004FC02
0x18004fbe7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004fbec  mov     rdi, rax
0x18004fbef  mov     rcx, rbx; this
0x18004fbf2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fbf7  add     rdi, 18h
0x18004fbfb  mov     [rsp+4B0h+lpszVolumeMountPoint], rdi
0x18004fc00  jmp     short loc_18004FC15
0x18004fc02  mov     r8d, [rdx-10h]
0x18004fc06  lea     rcx, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fc0b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004fc10  mov     rdi, [rsp+4B0h+lpszVolumeMountPoint]
0x18004fc15  mov     rcx, [rsp+4B0h+var_470]
0x18004fc1a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004fc1e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fc23  xor     edx, edx; Val
0x18004fc25  mov     r8d, 20Ah; Size
0x18004fc2b  lea     rcx, [rbp+3B0h+szVolumeName]; void *
0x18004fc32  call    memset_0
0x18004fc37  mov     r8d, 104h; cchBufferLength
0x18004fc3d  lea     rdx, [rbp+3B0h+szVolumeName]; lpszVolumeName
0x18004fc44  mov     rcx, rdi; lpszVolumeMountPoint
0x18004fc47  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004fc4d  test    eax, eax
0x18004fc4f  jnz     short loc_18004FCBC
0x18004fc51  call    cs:__imp_GetLastError
0x18004fc57  mov     r14d, 80070000h
0x18004fc5d  test    eax, eax
0x18004fc5f  jle     short loc_18004FC67
0x18004fc61  movzx   eax, ax
0x18004fc64  or      eax, r14d
0x18004fc67  mov     [rsp+4B0h+var_480], rdi
0x18004fc6c  lea     rcx, aFailedToLookUp_6; "Failed to look up volume GUID for [%s]"
0x18004fc73  mov     [rsp+4B0h+var_488], rcx
0x18004fc78  mov     [rsp+4B0h+var_490], 2F3h
0x18004fc80  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004fc87  lea     r8, aPushbuttonrese_54; "PushButtonReset::Path::SameVolume"
0x18004fc8e  mov     edx, eax
0x18004fc90  mov     ecx, 2
0x18004fc95  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004fc9a  call    cs:__imp_GetLastError
0x18004fca0  mov     ebx, eax
0x18004fca2  test    eax, eax
0x18004fca4  jle     short loc_18004FCAC
0x18004fca6  movzx   ebx, ax
0x18004fca9  or      ebx, r14d
0x18004fcac  lea     rcx, [rdi-18h]; this
0x18004fcb0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fcb5  mov     eax, ebx
0x18004fcb7  jmp     loc_18004FE6F
0x18004fcbc  lea     rcx, [rsp+4B0h+var_470]
0x18004fcc1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004fcc6  nop
0x18004fcc7  mov     rax, [rsi]
0x18004fcca  mov     edx, [rax-10h]
0x18004fccd  test    edx, edx
0x18004fccf  jle     short loc_18004FD3B
0x18004fcd1  dec     edx
0x18004fcd3  mov     rcx, rsi
0x18004fcd6  call    ?GetAt@?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::GetAt(int)
0x18004fcdb  cmp     ax, 5Ch ; '\'
0x18004fcdf  jnz     short loc_18004FD3B
0x18004fce1  mov     rdx, [rsi]
0x18004fce4  lea     rcx, [rdx-18h]
0x18004fce8  mov     rbx, [rsp+4B0h+var_470]
0x18004fced  lea     rsi, [rbx-18h]
0x18004fcf1  cmp     rcx, rsi
0x18004fcf4  jz      loc_18004FDAF
0x18004fcfa  cmp     dword ptr [rsi+10h], 0
0x18004fcfe  jl      short loc_18004FD26
0x18004fd00  mov     rax, [rsi]
0x18004fd03  cmp     [rcx], rax
0x18004fd06  jnz     short loc_18004FD26
0x18004fd08  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004fd0d  mov     rbx, rax
0x18004fd10  mov     rcx, rsi; this
0x18004fd13  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fd18  add     rbx, 18h
0x18004fd1c  mov     [rsp+4B0h+var_470], rbx
0x18004fd21  jmp     loc_18004FDAF
0x18004fd26  mov     r8d, [rdx-10h]
0x18004fd2a  lea     rcx, [rsp+4B0h+var_470]
0x18004fd2f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004fd34  mov     rbx, [rsp+4B0h+var_470]
0x18004fd39  jmp     short loc_18004FDAF
0x18004fd3b  lea     r8, SubBlock; "\\"
0x18004fd42  mov     rdx, rsi
0x18004fd45  lea     rcx, [rsp+4B0h+var_460]
0x18004fd4a  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x18004fd4f  nop
0x18004fd50  mov     rdx, [rax]
0x18004fd53  lea     rcx, [rdx-18h]
0x18004fd57  mov     rbx, [rsp+4B0h+var_470]
0x18004fd5c  lea     rsi, [rbx-18h]
0x18004fd60  cmp     rcx, rsi
0x18004fd63  jz      short loc_18004FDA1
0x18004fd65  cmp     dword ptr [rsi+10h], 0
0x18004fd69  jl      short loc_18004FD8E
0x18004fd6b  mov     rax, [rsi]
0x18004fd6e  cmp     [rcx], rax
0x18004fd71  jnz     short loc_18004FD8E
0x18004fd73  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18004fd78  mov     rbx, rax
0x18004fd7b  mov     rcx, rsi; this
0x18004fd7e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fd83  add     rbx, 18h
0x18004fd87  mov     [rsp+4B0h+var_470], rbx
0x18004fd8c  jmp     short loc_18004FDA1
0x18004fd8e  mov     r8d, [rdx-10h]
0x18004fd92  lea     rcx, [rsp+4B0h+var_470]
0x18004fd97  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18004fd9c  mov     rbx, [rsp+4B0h+var_470]
0x18004fda1  mov     rcx, [rsp+4B0h+var_460]
0x18004fda6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18004fdaa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fdaf  xor     edx, edx; Val
0x18004fdb1  mov     r8d, 20Ah; Size
0x18004fdb7  lea     rcx, [rsp+4B0h+String2]; void *
0x18004fdbc  call    memset_0
0x18004fdc1  mov     r8d, 104h; cchBufferLength
0x18004fdc7  lea     rdx, [rsp+4B0h+String2]; lpszVolumeName
0x18004fdcc  mov     rcx, rbx; lpszVolumeMountPoint
0x18004fdcf  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18004fdd5  test    eax, eax
0x18004fdd7  jnz     short loc_18004FE3F
0x18004fdd9  call    cs:__imp_GetLastError
0x18004fddf  mov     r14d, 80070000h
0x18004fde5  test    eax, eax
0x18004fde7  jle     short loc_18004FDEF
0x18004fde9  movzx   eax, ax
0x18004fdec  or      eax, r14d
0x18004fdef  mov     [rsp+4B0h+var_480], rbx
0x18004fdf4  lea     rcx, aFailedToLookUp_6; "Failed to look up volume GUID for [%s]"
0x18004fdfb  mov     [rsp+4B0h+var_488], rcx
0x18004fe00  mov     [rsp+4B0h+var_490], 306h
0x18004fe08  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004fe0f  lea     r8, aPushbuttonrese_54; "PushButtonReset::Path::SameVolume"
0x18004fe16  mov     edx, eax
0x18004fe18  mov     ecx, 2
0x18004fe1d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004fe22  call    cs:__imp_GetLastError
0x18004fe28  mov     esi, eax
0x18004fe2a  test    eax, eax
0x18004fe2c  jle     short loc_18004FE34
0x18004fe2e  movzx   esi, ax
0x18004fe31  or      esi, r14d
0x18004fe34  lea     rcx, [rbx-18h]; this
0x18004fe38  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fe3d  jmp     short loc_18004FE64
0x18004fe3f  lea     rdx, [rsp+4B0h+String2]; String2
0x18004fe44  lea     rcx, [rbp+3B0h+szVolumeName]; String1
0x18004fe4b  call    cs:__imp__wcsicmp
0x18004fe51  test    eax, eax
0x18004fe53  setz    al
0x18004fe56  mov     [r14], al
0x18004fe59  lea     rcx, [rbx-18h]; this
0x18004fe5d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fe62  xor     esi, esi
0x18004fe64  lea     rcx, [rdi-18h]; this
0x18004fe68  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004fe6d  mov     eax, esi
0x18004fe6f  mov     rcx, [rbp+3B0h+var_30]
0x18004fe76  xor     rcx, rsp; StackCookie
0x18004fe79  call    __security_check_cookie
0x18004fe7e  add     rsp, 490h
0x18004fe85  pop     r14
0x18004fe87  pop     rdi
0x18004fe88  pop     rsi
0x18004fe89  pop     rbx
0x18004fe8a  pop     rbp
0x18004fe8b  retn
```
