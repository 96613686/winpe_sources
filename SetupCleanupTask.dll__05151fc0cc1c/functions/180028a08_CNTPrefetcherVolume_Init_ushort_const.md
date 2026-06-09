# CNTPrefetcherVolume::Init(ushort const *)

- ea: `0x180028a08`
- end: `0x180028d76`
- name: `?Init@CNTPrefetcherVolume@@QEAAJPEBG@Z`
- size: `878`
- prototype: `__int64 __fastcall(CNTPrefetcherVolume *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18002acf8`

## callees

- `0x180002b38`
- `0x180025124`
- `0x180026d68`
- `0x180027008`
- `0x1800275b8`
- `0x1800288c8`
- `0x180028a08`
- `0x1800293a4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028abe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028abe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d1d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028aa8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028ce6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028d28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028cf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028d37`
- `ntdll!NtQueryVolumeInformationFile` at `0x180028b03`
- `ntdll!NtQueryVolumeInformationFile` at `0x180028b56`
- `ntdll!NtQueryVolumeInformationFile` at `0x180028b03`
- `ntdll!NtQueryVolumeInformationFile` at `0x180028b56`

## pseudocode

```c
__int64 __fastcall CNTPrefetcherVolume::Init(CNTPrefetcherVolume *this, const unsigned __int16 *a2)
{
  __int64 v3; // r15
  int VolumeNameForPath; // eax
  signed int v5; // edi
  __int64 v6; // rbx
  HANDLE FileW; // rax
  void *v8; // rsi
  signed int LastError; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  BOOL v12; // eax
  BOOL v13; // r14d
  __int64 v14; // rbx
  unsigned int v15; // r12d
  int StringCch; // eax
  int v17; // eax
  int v18; // ebx
  __int64 v19; // r14
  __int64 v20; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+68h] [rbp-98h] BYREF
  __int128 FsInformation; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF

  v30 = 0;
  v3 = 0;
  v26 = 0;
  FsInformation = 0;
  IoStatusBlock = 0;
  VolumeNameForPath = CFileUtilsT<CEmptyType>::GetVolumeNameForPath(a2, FileName);
  v24 = VolumeNameForPath;
  v5 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
  {
    v6 = -1;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(VolumeNameForPath);
    goto LABEL_46;
  }
  FileW = CreateFileW(FileName, 0x100080u, 7u, 0, 3u, 0x22200000u, 0);
  v8 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v10 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
    if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v10, &v24) )
    {
      v5 = v24;
      goto LABEL_11;
    }
    v25 = 0;
    v24 = 0;
    v28 = 0;
    v11 = NtQueryVolumeInformationFile(v8, &v28, &v25, 8u, FileFsDeviceInformation);
    v12 = SErrorConverterT<CEmptyType>::C_NtStatus2HR(v11, &v24);
    v5 = v24;
    if ( v12 )
    {
      v13 = (unsigned int)(v25 - 7) <= 1
         && (v25 & 0x1000000000LL) == 0
         && (v25 & 0x100000000LL) == 0
         && (v25 & 0x2000000000LL) != 0;
    }
    else
    {
      v13 = 0;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v24);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
    if ( v5 < 0 )
      goto LABEL_11;
    v14 = -1;
    FileName[1] = 63;
    do
      ++v14;
    while ( FileName[v14] );
    v15 = v14;
    if ( v14 == (unsigned int)v14 )
    {
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v5 = 0;
    }
    else
    {
      v15 = 0;
      v5 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
    if ( v5 < 0 )
      goto LABEL_11;
    if ( v15 <= 1 )
    {
      v5 = -2147418113;
      goto LABEL_11;
    }
    if ( 2 * (unsigned __int64)(v15 - 1) >= 0x208 )
      _report_rangecheckfailure();
    FileName[v15 - 1] = 0;
    v24 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(FileName, &v24);
    v5 = StringCch;
    if ( StringCch >= 0 )
    {
      v17 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(FileName, v24, &v26);
      v5 = v17;
      if ( v17 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v17);
      v3 = v26;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
    if ( v5 < 0 )
      goto LABEL_11;
    if ( HIDWORD(v30) && (_DWORD)v30 )
    {
      v18 = v30 * HIDWORD(v30);
      if ( (int)v30 * HIDWORD(v30) / (unsigned int)v30 != HIDWORD(v30) )
      {
        v18 = 0;
        v5 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        goto LABEL_41;
      }
    }
    else
    {
      v18 = 0;
    }
    v5 = 0;
LABEL_41:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
    if ( v5 >= 0 )
    {
      *((_DWORD *)this + 4) = v13;
      v19 = v3;
      *((_DWORD *)this + 1) = v18;
      v3 = 0;
      v20 = *((_QWORD *)this + 1);
      if ( v20 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v20 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      *((_QWORD *)this + 1) = v19;
      goto LABEL_45;
    }
LABEL_11:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_45:
    v6 = (__int64)v8;
    goto LABEL_46;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = -2147467259;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  v6 = -1;
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v3 )
  {
    v22 = GetProcessHeap();
    HeapFree(v22, 0, (LPVOID)(v3 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028a08  mov     [rsp-8+arg_10], rbx
0x180028a0d  push    rbp
0x180028a0e  push    rsi
0x180028a0f  push    rdi
0x180028a10  push    r12
0x180028a12  push    r13
0x180028a14  push    r14
0x180028a16  push    r15
0x180028a18  lea     rbp, [rsp-1B0h]
0x180028a20  sub     rsp, 2B0h
0x180028a27  mov     rax, cs:__security_cookie
0x180028a2e  xor     rax, rsp
0x180028a31  mov     [rbp+1E0h+var_40], rax
0x180028a38  mov     r13, rcx
0x180028a3b  mov     rax, rdx
0x180028a3e  xor     ecx, ecx
0x180028a40  lea     rdx, [rbp+1E0h+FileName]
0x180028a44  xorps   xmm0, xmm0
0x180028a47  mov     [rbp+1E0h+var_258], rcx
0x180028a4b  xor     r12d, r12d
0x180028a4e  mov     rcx, rax
0x180028a51  mov     r15d, r12d
0x180028a54  mov     [rsp+2E0h+var_290], r12
0x180028a59  movups  [rsp+2E0h+FsInformation], xmm0
0x180028a5e  movups  xmmword ptr [rsp+2E0h+IoStatusBlock], xmm0
0x180028a63  call    ?GetVolumeNameForPath@?$CFileUtilsT@VCEmptyType@@@@SAJPEBGPEAGK@Z; CFileUtilsT<CEmptyType>::GetVolumeNameForPath(ushort const *,ushort *,ulong)
0x180028a68  mov     [rsp+2E0h+var_2A0], eax
0x180028a6c  mov     edi, eax
0x180028a6e  test    eax, eax
0x180028a70  jns     short loc_180028A82
0x180028a72  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028a76  mov     ecx, eax
0x180028a78  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028a7d  jmp     loc_180028D09
0x180028a82  mov     ebx, 3
0x180028a87  mov     [rsp+2E0h+hTemplateFile], r12; hTemplateFile
0x180028a8c  mov     [rsp+2E0h+dwFlagsAndAttributes], 22200000h; dwFlagsAndAttributes
0x180028a94  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x180028a98  xor     r9d, r9d; lpSecurityAttributes
0x180028a9b  mov     [rsp+2E0h+dwCreationDisposition], ebx; dwCreationDisposition
0x180028a9f  mov     edx, 100080h; dwDesiredAccess
0x180028aa4  lea     r8d, [rbx+4]; dwShareMode
0x180028aa8  call    cs:__imp_CreateFileW
0x180028aae  mov     rsi, rax
0x180028ab1  lea     rcx, [rax+1]
0x180028ab5  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180028abc  jnz     short loc_180028AEC
0x180028abe  call    cs:__imp_GetLastError
0x180028ac4  mov     edi, eax
0x180028ac6  test    eax, eax
0x180028ac8  jnz     short loc_180028AD1
0x180028aca  mov     edi, 80004005h
0x180028acf  jmp     short loc_180028ADC
0x180028ad1  jle     short loc_180028ADC
0x180028ad3  movzx   edi, ax
0x180028ad6  or      edi, 80070000h
0x180028adc  mov     ecx, edi
0x180028ade  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028ae3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028ae7  jmp     loc_180028D09
0x180028aec  mov     rcx, rsi; FileHandle
0x180028aef  mov     [rsp+2E0h+dwCreationDisposition], ebx; FsInformationClass
0x180028af3  mov     r9d, 18h; Length
0x180028af9  lea     r8, [rsp+2E0h+FsInformation]; FsInformation
0x180028afe  lea     rdx, [rsp+2E0h+IoStatusBlock]; IoStatusBlock
0x180028b03  call    cs:__imp_NtQueryVolumeInformationFile
0x180028b09  mov     ecx, eax
0x180028b0b  lea     rdx, [rsp+2E0h+var_2A0]
0x180028b10  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180028b15  test    eax, eax
0x180028b17  jnz     short loc_180028B29
0x180028b19  mov     edi, [rsp+2E0h+var_2A0]
0x180028b1d  mov     ecx, edi
0x180028b1f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028b24  jmp     loc_180028D06
0x180028b29  xorps   xmm0, xmm0
0x180028b2c  mov     [rsp+2E0h+var_298], r12
0x180028b31  mov     rcx, rsi; FileHandle
0x180028b34  mov     [rsp+2E0h+var_2A0], r12d
0x180028b39  mov     r9d, 8; Length
0x180028b3f  mov     [rsp+2E0h+dwCreationDisposition], 4; FsInformationClass
0x180028b47  lea     r8, [rsp+2E0h+var_298]; FsInformation
0x180028b4c  lea     rdx, [rsp+2E0h+var_278]; IoStatusBlock
0x180028b51  movups  xmmword ptr [rsp+2E0h+var_278], xmm0
0x180028b56  call    cs:__imp_NtQueryVolumeInformationFile
0x180028b5c  mov     ecx, eax
0x180028b5e  lea     rdx, [rsp+2E0h+var_2A0]
0x180028b63  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180028b68  mov     edi, [rsp+2E0h+var_2A0]
0x180028b6c  test    eax, eax
0x180028b6e  jnz     short loc_180028B7C
0x180028b70  mov     ecx, edi
0x180028b72  mov     r14d, r12d
0x180028b75  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028b7a  jmp     short loc_180028BA4
0x180028b7c  mov     eax, dword ptr [rsp+2E0h+var_298]
0x180028b80  add     eax, 0FFFFFFF9h
0x180028b83  cmp     eax, 1
0x180028b86  ja      short loc_180028B94
0x180028b88  mov     eax, dword ptr [rsp+2E0h+var_298+4]
0x180028b8c  test    al, 10h
0x180028b8e  jnz     short loc_180028B94
0x180028b90  test    al, 1
0x180028b92  jz      short loc_180028B99
0x180028b94  mov     r14d, r12d
0x180028b97  jmp     short loc_180028BA4
0x180028b99  and     al, 20h
0x180028b9b  neg     al
0x180028b9d  sbb     r14d, r14d
0x180028ba0  and     r14d, 1
0x180028ba4  mov     ecx, edi
0x180028ba6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028bab  test    edi, edi
0x180028bad  js      loc_180028B1D
0x180028bb3  mov     eax, 3Fh ; '?'
0x180028bb8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028bbc  mov     [rbp+1E0h+var_24E], ax
0x180028bc0  lea     rax, [rbp+1E0h+FileName]
0x180028bc4  inc     rbx
0x180028bc7  cmp     [rax+rbx*2], r12w
0x180028bcc  jnz     short loc_180028BC4
0x180028bce  mov     r12d, ebx
0x180028bd1  mov     eax, 80070216h
0x180028bd6  cmp     rbx, r12
0x180028bd9  jz      short loc_180028BE9
0x180028bdb  xor     r12d, r12d
0x180028bde  mov     ecx, eax
0x180028be0  mov     edi, eax
0x180028be2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028be7  jmp     short loc_180028BF2
0x180028be9  xor     ecx, ecx
0x180028beb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028bf0  xor     edi, edi
0x180028bf2  mov     ecx, edi
0x180028bf4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028bf9  test    edi, edi
0x180028bfb  js      loc_180028B1D
0x180028c01  cmp     r12d, 1
0x180028c05  ja      short loc_180028C11
0x180028c07  mov     edi, 8000FFFFh
0x180028c0c  jmp     loc_180028B1D
0x180028c11  lea     ecx, [r12-1]
0x180028c16  add     rcx, rcx
0x180028c19  cmp     rcx, 208h
0x180028c20  jnb     loc_180028D70
0x180028c26  xor     r12d, r12d
0x180028c29  lea     rdx, [rsp+2E0h+var_2A0]
0x180028c2e  mov     [rbp+rcx+1E0h+FileName], r12w
0x180028c34  lea     rcx, [rbp+1E0h+FileName]
0x180028c38  mov     [rsp+2E0h+var_2A0], r12d
0x180028c3d  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180028c42  mov     edi, eax
0x180028c44  test    eax, eax
0x180028c46  jns     short loc_180028C51
0x180028c48  mov     ecx, eax
0x180028c4a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028c4f  jmp     short loc_180028C75
0x180028c51  mov     edx, [rsp+2E0h+var_2A0]
0x180028c55  lea     r8, [rsp+2E0h+var_290]
0x180028c5a  lea     rcx, [rbp+1E0h+FileName]; Src
0x180028c5e  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180028c63  mov     edi, eax
0x180028c65  test    eax, eax
0x180028c67  jns     short loc_180028C70
0x180028c69  mov     ecx, eax
0x180028c6b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028c70  mov     r15, [rsp+2E0h+var_290]
0x180028c75  mov     ecx, edi
0x180028c77  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028c7c  test    edi, edi
0x180028c7e  js      loc_180028B1D
0x180028c84  mov     r8d, dword ptr [rbp+1E0h+var_258+4]
0x180028c88  test    r8d, r8d
0x180028c8b  jz      short loc_180028CBA
0x180028c8d  mov     r9d, dword ptr [rbp+1E0h+var_258]
0x180028c91  test    r9d, r9d
0x180028c94  jz      short loc_180028CBA
0x180028c96  xor     edx, edx
0x180028c98  mov     ebx, r8d
0x180028c9b  imul    ebx, r9d
0x180028c9f  mov     eax, ebx
0x180028ca1  div     r9d
0x180028ca4  cmp     eax, r8d
0x180028ca7  jz      short loc_180028CBD
0x180028ca9  mov     ecx, 80070216h
0x180028cae  mov     ebx, r12d
0x180028cb1  mov     edi, ecx
0x180028cb3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028cb8  jmp     short loc_180028CC0
0x180028cba  mov     ebx, r12d
0x180028cbd  mov     edi, r12d
0x180028cc0  mov     ecx, edi
0x180028cc2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028cc7  test    edi, edi
0x180028cc9  js      loc_180028B1D
0x180028ccf  mov     [r13+10h], r14d
0x180028cd3  mov     r14, r15
0x180028cd6  mov     [r13+4], ebx
0x180028cda  mov     r15, r12
0x180028cdd  mov     rbx, [r13+8]
0x180028ce1  test    rbx, rbx
0x180028ce4  jz      short loc_180028D02
0x180028ce6  call    cs:__imp_GetProcessHeap
0x180028cec  lea     r8, [rbx-4]; lpMem
0x180028cf0  xor     edx, edx; dwFlags
0x180028cf2  mov     rcx, rax; hHeap
0x180028cf5  call    cs:__imp_HeapFree
0x180028cfb  xor     ecx, ecx
0x180028cfd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028d02  mov     [r13+8], r14
0x180028d06  mov     rbx, rsi
0x180028d09  mov     ecx, edi
0x180028d0b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028d10  lea     rax, [rbx-1]
0x180028d14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028d18  ja      short loc_180028D23
0x180028d1a  mov     rcx, rbx; hObject
0x180028d1d  call    cs:__imp_CloseHandle
0x180028d23  test    r15, r15
0x180028d26  jz      short loc_180028D44
0x180028d28  call    cs:__imp_GetProcessHeap
0x180028d2e  lea     r8, [r15-4]; lpMem
0x180028d32  xor     edx, edx; dwFlags
0x180028d34  mov     rcx, rax; hHeap
0x180028d37  call    cs:__imp_HeapFree
0x180028d3d  xor     ecx, ecx
0x180028d3f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028d44  mov     eax, edi
0x180028d46  mov     rcx, [rbp+1E0h+var_40]
0x180028d4d  xor     rcx, rsp; StackCookie
0x180028d50  call    __security_check_cookie
0x180028d55  mov     rbx, [rsp+2E0h+arg_10]
0x180028d5d  add     rsp, 2B0h
0x180028d64  pop     r15
0x180028d66  pop     r14
0x180028d68  pop     r13
0x180028d6a  pop     r12
0x180028d6c  pop     rdi
0x180028d6d  pop     rsi
0x180028d6e  pop     rbp
0x180028d6f  retn
0x180028d70  call    __report_rangecheckfailure
```
