# winreConvertDirNameToOffset

- ea: `0x180010010`
- end: `0x1800103ed`
- name: `winreConvertDirNameToOffset`
- size: `989`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszFileName@<rcx>, __int64)`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x180012f58`
- `0x1800174a0`
- `0x180017960`
- `0x18001f5b4`
- `0x180024a10`
- `0x180025560`
- `0x180025a60`
- `0x18003af14`
- `0x18003bfbc`

## callees

- `0x180002786`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000edec`
- `0x18000ee80`
- `0x18000ffcc`
- `0x180010010`
- `0x180011264`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001032c`
- `msvcrt!_wcsicmp` at `0x18001032c`
- `KERNEL32!GetLastError` at `0x1800100dd`
- `KERNEL32!GetLastError` at `0x18001017d`
- `KERNEL32!GetLastError` at `0x1800101ae`
- `KERNEL32!GetLastError` at `0x1800100dd`
- `KERNEL32!GetLastError` at `0x18001017d`
- `KERNEL32!GetLastError` at `0x1800101ae`
- `KERNEL32!GetFileAttributesW` at `0x1800100d2`
- `KERNEL32!GetFileAttributesW` at `0x18001011c`
- `KERNEL32!GetFileAttributesW` at `0x1800100d2`
- `KERNEL32!GetFileAttributesW` at `0x18001011c`
- `KERNEL32!GetFullPathNameW` at `0x180010158`
- `KERNEL32!GetFullPathNameW` at `0x180010158`
- `KERNEL32!GetVolumePathNameW` at `0x180010173`
- `KERNEL32!GetVolumePathNameW` at `0x180010173`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800101a4`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800101a4`
- `ole32!CoTaskMemFree` at `0x1800102b3`
- `ole32!CoTaskMemFree` at `0x1800102c2`
- `ole32!CoTaskMemFree` at `0x1800102d1`
- `ole32!CoTaskMemFree` at `0x1800102b3`
- `ole32!CoTaskMemFree` at `0x1800102c2`
- `ole32!CoTaskMemFree` at `0x1800102d1`

## string_xrefs

- `0x180010075`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x1800101e0`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010272`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010385`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18001006e`: `failed to allocate path`
- `0x18001018b`: `failed to get volume path name`
- `0x18001037e`: `failed to get volume path length`
- `0x1800103da`: `failed to copy relative path`

## pseudocode

```c
__int64 __fastcall winreConvertDirNameToOffset(LPCWSTR lpszFileName, __int64 a2, void *a3, _DWORD *a4, __int64 a5)
{
  const void **v6; // r14
  unsigned int v9; // esi
  DWORD LastError; // ebx
  const wchar_t *v11; // r8
  int v12; // edi
  DWORD FileAttributesW; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  LPWSTR v17; // rax
  int v18; // r8d
  int v19; // ecx
  const wchar_t *i; // rdi
  int v22; // edi
  unsigned __int16 *v23; // r11
  const wchar_t *v24; // r8
  unsigned __int64 v25; // r8
  int v26; // [rsp+28h] [rbp-38h]
  int v27; // [rsp+28h] [rbp-38h]
  LPWSTR lpszVolumePathName; // [rsp+38h] [rbp-28h] BYREF
  LPWSTR lpszVolumeName; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR lpBuffer; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v31; // [rsp+50h] [rbp-10h] BYREF
  const void **v32; // [rsp+58h] [rbp-8h]

  lpBuffer = 0;
  lpszVolumePathName = 0;
  v6 = 0;
  lpszVolumeName = 0;
  v32 = 0;
  v31 = 0;
  v9 = 3;
  LastError = winreAllocPath(&lpszVolumePathName);
  if ( LastError )
  {
    v26 = 2321;
LABEL_3:
    v11 = L"failed to allocate path";
LABEL_4:
    UnattendLogW(
      2,
      L"winreConvertDirNameToOffset %s (0x%x) in file %S line %d",
      v11,
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
      v26);
LABEL_5:
    v12 = 0;
    goto LABEL_38;
  }
  LastError = winreAllocPath(&lpBuffer);
  if ( LastError )
  {
    v26 = 2322;
    goto LABEL_3;
  }
  LastError = winreAllocPath(&lpszVolumeName);
  if ( LastError )
  {
    v26 = 2323;
    goto LABEL_3;
  }
  FileAttributesW = GetFileAttributesW(lpszFileName);
  if ( FileAttributesW == -1 )
  {
LABEL_11:
    LastError = GetLastError();
    if ( LastError - 2 <= 1 && !ReAgentError )
      ReAgentError = 12;
    goto LABEL_5;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    winreStripFilename(lpszFileName, a2, 302);
    v14 = GetFileAttributesW(lpszFileName);
    if ( v14 == -1 )
      goto LABEL_11;
    if ( (v14 & 0x10) == 0 )
    {
      LastError = 267;
      if ( !ReAgentError )
        ReAgentError = 29;
      goto LABEL_5;
    }
  }
  if ( !GetFullPathNameW(lpszFileName, 0x12Eu, lpBuffer, 0) )
  {
    LastError = 3;
    goto LABEL_5;
  }
  if ( !GetVolumePathNameW(lpszFileName, lpszVolumePathName, 0x12Eu) )
  {
    v15 = GetLastError();
    v26 = 2383;
    v11 = L"failed to get volume path name";
    LastError = v15;
    goto LABEL_4;
  }
  if ( !GetVolumeNameForVolumeMountPointW(lpszVolumePathName, lpszVolumeName, 0x12Eu) )
  {
    v16 = GetLastError();
    v26 = 2387;
    v11 = L"failed to get volume name";
    LastError = v16;
    goto LABEL_4;
  }
  LastError = StringCchLengthW(lpszVolumeName, 0x12Eu, &v31);
  if ( (LastError & 0x80000000) != 0 )
  {
    UnattendLogW(
      2,
      L"winreConvertDirNameToOffset %s (0x%x) in file %S line %d",
      L"failed to get volume name length",
      LastError,
      "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
      2391);
    LastError = (unsigned __int16)LastError;
    goto LABEL_5;
  }
  if ( v31 > 1 )
    lpszVolumeName[v31 - 1] = 0;
  if ( a4 )
  {
    v17 = lpBuffer;
    do
    {
      v18 = *(LPWSTR)((char *)v17 + (char *)lpszVolumePathName - (char *)lpBuffer);
      v19 = *v17 - v18;
      if ( v19 )
        break;
      ++v17;
    }
    while ( v18 );
    if ( !v19 )
      *a4 = 1;
  }
  LastError = PrivateGetPartitionList(0);
  if ( !LastError )
  {
    v6 = v32;
    for ( i = (const wchar_t *)*v32; ; i = *(const wchar_t **)i )
    {
      if ( i == (const wchar_t *)v6 )
        goto LABEL_37;
      if ( !_wcsicmp(lpszVolumeName, i + 26) )
        break;
    }
    memcpy_0(a3, i, 0x530u);
    if ( a5 )
    {
      v22 = StringCchLengthW(lpszVolumePathName, 0x12Eu, &v31);
      if ( v22 < 0 )
      {
        v27 = 2435;
        v24 = L"failed to get volume path length";
LABEL_55:
        UnattendLogW(
          2,
          L"winreConvertDirNameToOffset %s (0x%x) in file %S line %d",
          v24,
          (unsigned int)v22,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          v27);
        LastError = (unsigned __int16)v22;
        goto LABEL_37;
      }
      v25 = v31;
      if ( v31 >= 3 )
        v25 = v31 - 1;
      v22 = StringCchCopyW(v23, 0x12Eu, &lpBuffer[v25]);
      if ( v22 < 0 )
      {
        v27 = 2442;
        v24 = L"failed to copy relative path";
        goto LABEL_55;
      }
    }
    v12 = 1;
    goto LABEL_38;
  }
  UnattendLogW(
    2,
    L"winreConvertDirNameToOffset %s (0x%x) in file %S line %d",
    L"failed to get partition list",
    LastError,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
    2409);
  v6 = v32;
LABEL_37:
  v12 = 0;
LABEL_38:
  if ( lpszVolumePathName )
    CoTaskMemFree(lpszVolumePathName);
  if ( lpszVolumeName )
    CoTaskMemFree(lpszVolumeName);
  if ( lpBuffer )
    CoTaskMemFree(lpBuffer);
  PrivateFreePartitionList(v6);
  if ( !v12 || (v9 = LastError) != 0 )
    UnattendLogW(1, L"winreConvertDirNameToOffset failed: 0x%x", v9);
  return v9;
}

```

## disassembly

```asm
0x180010010  mov     [rsp-28h+arg_0], rbx
0x180010015  mov     [rsp-28h+arg_8], rsi
0x18001001a  mov     [rsp-28h+arg_10], r8
0x18001001f  push    rbp
0x180010020  push    rdi
0x180010021  push    r12
0x180010023  push    r14
0x180010025  push    r15
0x180010027  mov     rbp, rsp
0x18001002a  sub     rsp, 60h
0x18001002e  xor     eax, eax
0x180010030  mov     rdi, rcx
0x180010033  lea     rcx, [rbp+lpszVolumePathName]
0x180010037  mov     [rbp+lpBuffer], rax
0x18001003b  mov     [rbp+lpszVolumePathName], rax
0x18001003f  mov     r14d, eax
0x180010042  mov     [rbp+lpszVolumeName], rax
0x180010046  mov     r15, r9
0x180010049  mov     [rbp+var_8], rax
0x18001004d  mov     r12, rdx
0x180010050  mov     [rbp+var_10], rax
0x180010054  mov     [rbp+var_30], eax
0x180010057  call    winreAllocPath
0x18001005c  lea     esi, [r14+3]
0x180010060  mov     ebx, eax
0x180010062  test    eax, eax
0x180010064  jz      short loc_18001009D
0x180010066  mov     [rsp+60h+var_38], 911h
0x18001006e  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x180010075  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001007c  mov     r9d, ebx
0x18001007f  lea     rdx, aWinreconvertdi; "winreConvertDirNameToOffset %s (0x%x) i"...
0x180010086  mov     [rsp+60h+var_40], rax
0x18001008b  mov     ecx, 2
0x180010090  call    UnattendLogW
0x180010095  mov     edi, r14d
0x180010098  jmp     loc_1800102A8
0x18001009d  lea     rcx, [rbp+lpBuffer]
0x1800100a1  call    winreAllocPath
0x1800100a6  mov     ebx, eax
0x1800100a8  test    eax, eax
0x1800100aa  jz      short loc_1800100B6
0x1800100ac  mov     [rsp+60h+var_38], 912h
0x1800100b4  jmp     short loc_18001006E
0x1800100b6  lea     rcx, [rbp+lpszVolumeName]
0x1800100ba  call    winreAllocPath
0x1800100bf  mov     ebx, eax
0x1800100c1  test    eax, eax
0x1800100c3  jz      short loc_1800100CF
0x1800100c5  mov     [rsp+60h+var_38], 913h
0x1800100cd  jmp     short loc_18001006E
0x1800100cf  mov     rcx, rdi; lpFileName
0x1800100d2  call    cs:__imp_GetFileAttributesW
0x1800100d8  cmp     eax, 0FFFFFFFFh
0x1800100db  jnz     short loc_180010102
0x1800100dd  call    cs:__imp_GetLastError
0x1800100e3  mov     ebx, eax
0x1800100e5  add     eax, 0FFFFFFFEh
0x1800100e8  cmp     eax, 1
0x1800100eb  ja      short loc_180010095
0x1800100ed  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r14d; _ReAgentErrorCodes ReAgentError
0x1800100f4  jnz     short loc_180010095
0x1800100f6  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0Ch; _ReAgentErrorCodes ReAgentError
0x180010100  jmp     short loc_180010095
0x180010102  mov     ebx, 12Eh
0x180010107  test    al, 10h
0x180010109  jnz     short loc_18001014C
0x18001010b  mov     r8d, ebx
0x18001010e  mov     rdx, r12
0x180010111  mov     rcx, rdi
0x180010114  call    winreStripFilename
0x180010119  mov     rcx, rdi; lpFileName
0x18001011c  call    cs:__imp_GetFileAttributesW
0x180010122  cmp     eax, 0FFFFFFFFh
0x180010125  jz      short loc_1800100DD
0x180010127  test    al, 10h
0x180010129  jnz     short loc_18001014C
0x18001012b  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r14d; _ReAgentErrorCodes ReAgentError
0x180010132  mov     ebx, 10Bh
0x180010137  jnz     loc_180010095
0x18001013d  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Dh; _ReAgentErrorCodes ReAgentError
0x180010147  jmp     loc_180010095
0x18001014c  mov     r8, [rbp+lpBuffer]; lpBuffer
0x180010150  xor     r9d, r9d; lpFilePart
0x180010153  mov     edx, ebx; nBufferLength
0x180010155  mov     rcx, rdi; lpFileName
0x180010158  call    cs:__imp_GetFullPathNameW
0x18001015e  test    eax, eax
0x180010160  jnz     short loc_180010169
0x180010162  mov     ebx, esi
0x180010164  jmp     loc_180010095
0x180010169  mov     rdx, [rbp+lpszVolumePathName]; lpszVolumePathName
0x18001016d  mov     r8d, ebx; cchBufferLength
0x180010170  mov     rcx, rdi; lpszFileName
0x180010173  call    cs:__imp_GetVolumePathNameW
0x180010179  test    eax, eax
0x18001017b  jnz     short loc_180010199
0x18001017d  call    cs:__imp_GetLastError
0x180010183  mov     [rsp+60h+var_38], 94Fh
0x18001018b  lea     r8, aFailedToGetVol; "failed to get volume path name"
0x180010192  mov     ebx, eax
0x180010194  jmp     loc_180010075
0x180010199  mov     rdx, [rbp+lpszVolumeName]; lpszVolumeName
0x18001019d  mov     r8d, ebx; cchBufferLength
0x1800101a0  mov     rcx, [rbp+lpszVolumePathName]; lpszVolumeMountPoint
0x1800101a4  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800101aa  test    eax, eax
0x1800101ac  jnz     short loc_1800101CA
0x1800101ae  call    cs:__imp_GetLastError
0x1800101b4  mov     [rsp+60h+var_38], 953h
0x1800101bc  lea     r8, aFailedToGetVol_3; "failed to get volume name"
0x1800101c3  mov     ebx, eax
0x1800101c5  jmp     loc_180010075
0x1800101ca  mov     rcx, [rbp+lpszVolumeName]; unsigned __int16 *
0x1800101ce  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800101d2  mov     rdx, rbx; unsigned __int64
0x1800101d5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800101da  mov     ebx, eax
0x1800101dc  test    eax, eax
0x1800101de  jns     short loc_180010217
0x1800101e0  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800101e7  mov     [rsp+60h+var_38], 957h
0x1800101ef  mov     r9d, ebx
0x1800101f2  mov     [rsp+60h+var_40], rax
0x1800101f7  lea     r8, aFailedToGetVol_0; "failed to get volume name length"
0x1800101fe  mov     ecx, 2
0x180010203  lea     rdx, aWinreconvertdi; "winreConvertDirNameToOffset %s (0x%x) i"...
0x18001020a  call    UnattendLogW
0x18001020f  movzx   ebx, bx
0x180010212  jmp     loc_180010095
0x180010217  mov     rdx, [rbp+var_10]
0x18001021b  cmp     rdx, 1
0x18001021f  jbe     short loc_18001022C
0x180010221  mov     rax, [rbp+lpszVolumeName]
0x180010225  xor     ecx, ecx
0x180010227  mov     [rax+rdx*2-2], cx
0x18001022c  test    r15, r15
0x18001022f  jz      short loc_18001025D
0x180010231  mov     rax, [rbp+lpBuffer]
0x180010235  mov     rdx, [rbp+lpszVolumePathName]
0x180010239  sub     rdx, rax
0x18001023c  movzx   ecx, word ptr [rax]
0x18001023f  movzx   r8d, word ptr [rax+rdx]
0x180010244  sub     ecx, r8d
0x180010247  jnz     short loc_180010252
0x180010249  add     rax, 2
0x18001024d  test    r8d, r8d
0x180010250  jnz     short loc_18001023C
0x180010252  test    ecx, ecx
0x180010254  jnz     short loc_18001025D
0x180010256  mov     dword ptr [r15], 1
0x18001025d  lea     rdx, [rbp+var_8]
0x180010261  xor     ecx, ecx; struct _GUID *
0x180010263  call    PrivateGetPartitionList
0x180010268  mov     ebx, eax
0x18001026a  test    eax, eax
0x18001026c  jz      loc_180010318
0x180010272  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010279  mov     [rsp+60h+var_38], 969h
0x180010281  mov     r9d, ebx
0x180010284  mov     [rsp+60h+var_40], rax
0x180010289  lea     r8, aFailedToGetPar; "failed to get partition list"
0x180010290  mov     ecx, 2
0x180010295  lea     rdx, aWinreconvertdi; "winreConvertDirNameToOffset %s (0x%x) i"...
0x18001029c  call    UnattendLogW
0x1800102a1  mov     r14, [rbp+var_8]
0x1800102a5  mov     edi, [rbp+var_30]
0x1800102a8  cmp     [rbp+lpszVolumePathName], 0
0x1800102ad  jz      short loc_1800102B9
0x1800102af  mov     rcx, [rbp+lpszVolumePathName]; pv
0x1800102b3  call    cs:__imp_CoTaskMemFree
0x1800102b9  mov     rcx, [rbp+lpszVolumeName]; pv
0x1800102bd  test    rcx, rcx
0x1800102c0  jz      short loc_1800102C8
0x1800102c2  call    cs:__imp_CoTaskMemFree
0x1800102c8  mov     rcx, [rbp+lpBuffer]; pv
0x1800102cc  test    rcx, rcx
0x1800102cf  jz      short loc_1800102D7
0x1800102d1  call    cs:__imp_CoTaskMemFree
0x1800102d7  mov     rcx, r14; pv
0x1800102da  call    PrivateFreePartitionList
0x1800102df  test    edi, edi
0x1800102e1  jz      short loc_1800102E9
0x1800102e3  mov     esi, ebx
0x1800102e5  test    ebx, ebx
0x1800102e7  jz      short loc_1800102FD
0x1800102e9  mov     r8d, esi
0x1800102ec  lea     rdx, aWinreconvertdi_0; "winreConvertDirNameToOffset failed: 0x%"...
0x1800102f3  mov     ecx, 1
0x1800102f8  call    UnattendLogW
0x1800102fd  lea     r11, [rsp+60h+var_s0]
0x180010302  mov     eax, esi
0x180010304  mov     rbx, [r11+30h]
0x180010308  mov     rsi, [r11+38h]
0x18001030c  mov     rsp, r11
0x18001030f  pop     r15
0x180010311  pop     r14
0x180010313  pop     r12
0x180010315  pop     rdi
0x180010316  pop     rbp
0x180010317  retn
0x180010318  mov     r14, [rbp+var_8]
0x18001031c  mov     rdi, [r14]
0x18001031f  cmp     rdi, r14
0x180010322  jz      short loc_1800102A5
0x180010324  mov     rcx, [rbp+lpszVolumeName]; String1
0x180010328  lea     rdx, [rdi+34h]; String2
0x18001032c  call    cs:__imp__wcsicmp
0x180010332  test    eax, eax
0x180010334  jz      short loc_18001033B
0x180010336  mov     rdi, [rdi]
0x180010339  jmp     short loc_18001031F
0x18001033b  mov     rcx, [rbp+arg_10]; void *
0x18001033f  mov     rdx, rdi; Src
0x180010342  mov     r8d, 530h; Size
0x180010348  call    memcpy_0
0x18001034d  mov     r11, [rbp+arg_20]
0x180010351  test    r11, r11
0x180010354  jz      loc_1800103E3
0x18001035a  mov     rcx, [rbp+lpszVolumePathName]; unsigned __int16 *
0x18001035e  lea     r8, [rbp+var_10]; unsigned __int64 *
0x180010362  mov     r15d, 12Eh
0x180010368  mov     edx, r15d; unsigned __int64
0x18001036b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010370  mov     edi, eax
0x180010372  test    eax, eax
0x180010374  jns     short loc_1800103AD
0x180010376  mov     [rsp+60h+var_38], 983h
0x18001037e  lea     r8, aFailedToGetVol_1; "failed to get volume path length"
0x180010385  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x18001038c  mov     r9d, edi
0x18001038f  lea     rdx, aWinreconvertdi; "winreConvertDirNameToOffset %s (0x%x) i"...
0x180010396  mov     [rsp+60h+var_40], rax
0x18001039b  mov     ecx, 2
0x1800103a0  call    UnattendLogW
0x1800103a5  movzx   ebx, di
0x1800103a8  jmp     loc_1800102A5
0x1800103ad  mov     r8, [rbp+var_10]
0x1800103b1  cmp     r8, rsi
0x1800103b4  jb      short loc_1800103B9
0x1800103b6  dec     r8
0x1800103b9  mov     rax, [rbp+lpBuffer]
0x1800103bd  mov     rdx, r15; unsigned __int64
0x1800103c0  mov     rcx, r11; unsigned __int16 *
0x1800103c3  lea     r8, [rax+r8*2]; unsigned __int16 *
0x1800103c7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800103cc  mov     edi, eax
0x1800103ce  test    eax, eax
0x1800103d0  jns     short loc_1800103E3
0x1800103d2  mov     [rsp+60h+var_38], 98Ah
0x1800103da  lea     r8, aFailedToCopyRe; "failed to copy relative path"
0x1800103e1  jmp     short loc_180010385
0x1800103e3  mov     edi, 1
0x1800103e8  jmp     loc_1800102A8
```
