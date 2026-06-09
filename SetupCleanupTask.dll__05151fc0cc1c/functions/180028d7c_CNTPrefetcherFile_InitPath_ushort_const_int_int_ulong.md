# CNTPrefetcherFile::InitPath(ushort const *,int,int,ulong)

- ea: `0x180028d7c`
- end: `0x18002913a`
- name: `?InitPath@CNTPrefetcherFile@@QEAAJPEBGHHK@Z`
- size: `958`
- prototype: `__int64 __fastcall(CNTPrefetcherFile *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18002acf8`

## callees

- `0x180022e70`
- `0x180026d68`
- `0x180027008`
- `0x1800285f4`
- `0x1800288c8`
- `0x180028d7c`
- `0x1800293a4`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800290b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002902e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029107`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002902e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029107`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028e59`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028e59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028f82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028f82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800290e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180029070`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800290e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002907e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002907e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800290f4`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028ef5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180028ef5`
- `ntdll!NtQueryInformationFile` at `0x180028e89`
- `ntdll!NtQueryInformationFile` at `0x180029007`
- `ntdll!NtQueryInformationFile` at `0x180028e89`
- `ntdll!NtQueryInformationFile` at `0x180029007`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNTPrefetcherFile::InitPath(CNTPrefetcherFile *this, const unsigned __int16 *a2)
{
  __int64 FileW; // rbx
  struct RETRIEVAL_POINTERS_BUFFER *v4; // rdi
  int VolumeNameForPath; // eax
  signed int v6; // esi
  int v7; // ecx
  NTSTATUS v8; // eax
  struct RETRIEVAL_POINTERS_BUFFER *p_OutBuffer; // r12
  DWORD v10; // r14d
  void *v11; // rcx
  signed int v12; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  void *v15; // rcx
  NTSTATUS v16; // eax
  struct RETRIEVAL_POINTERS_BUFFER *v17; // r12
  __int128 v18; // xmm1
  void *v19; // r14
  HANDLE v20; // rax
  bool v21; // zf
  __int64 v22; // rax
  signed int LastError; // eax
  HANDLE v24; // rax
  signed int v26; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  __int64 InBuffer; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-A0h] BYREF
  __int128 OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h]
  _OWORD FileInformation[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h]
  WCHAR FileName[264]; // [rsp+C0h] [rbp-40h] BYREF

  v29 = 0;
  v35 = 0;
  BytesReturned = 0;
  v30 = 0;
  InBuffer = 0;
  FileW = -1;
  v4 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  IoStatusBlock = 0;
  OutBuffer = 0;
  v33 = 0;
  VolumeNameForPath = CFileUtilsT<CEmptyType>::GetVolumeNameForPath(L"$MFT", FileName);
  v6 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_2;
  VolumeNameForPath = StringCchCatW(FileName, 0x104u, L"$MFT");
  v26 = VolumeNameForPath;
  v6 = VolumeNameForPath;
  if ( VolumeNameForPath < 0 )
    goto LABEL_2;
  FileW = (__int64)CreateFileW(FileName, 0x100080u, 7u, 0, 3u, 0x22200000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    FileW = -1;
    goto LABEL_50;
  }
  v8 = NtQueryInformationFile((HANDLE)FileW, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v8, &v26) )
  {
LABEL_7:
    v6 = v26;
LABEL_8:
    v7 = v6;
    goto LABEL_3;
  }
  InBuffer = 0;
  p_OutBuffer = (struct RETRIEVAL_POINTERS_BUFFER *)&OutBuffer;
  v10 = 32;
  while ( 1 )
  {
    v11 = 0;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      v11 = (void *)FileW;
    if ( DeviceIoControl(v11, 0x90073u, &InBuffer, 8u, p_OutBuffer, v10, &BytesReturned, 0) )
      break;
    v12 = GetLastError();
    v6 = v12;
    if ( v12 == 38 )
      break;
    if ( v12 != 234 && v12 != 122 && v12 != 111 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_50;
      goto LABEL_8;
    }
    if ( v10 )
    {
      if ( (v10 & 0xFFFFFFF) != v10 )
      {
        v6 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        goto LABEL_23;
      }
      v10 *= 16;
    }
    else
    {
      v10 = 0;
    }
    v6 = 0;
LABEL_23:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
    v26 = v6;
    if ( v6 < 0 )
      goto LABEL_8;
    if ( v10 > 0x100000 )
    {
      v6 = 111;
      goto LABEL_50;
    }
    ProcessHeap = GetProcessHeap();
    p_OutBuffer = (struct RETRIEVAL_POINTERS_BUFFER *)HeapAlloc(ProcessHeap, 0, v10);
    if ( v4 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v4);
    }
    if ( !p_OutBuffer )
    {
      v4 = 0;
      v6 = -2147024882;
      goto LABEL_8;
    }
    v4 = p_OutBuffer;
  }
  v15 = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    v15 = (void *)FileW;
  v16 = NtQueryInformationFile(v15, &IoStatusBlock, &v29, 8u, FileInternalInformation);
  if ( !SErrorConverterT<CEmptyType>::C_NtStatus2HR(v16, &v26) )
    goto LABEL_7;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle((HANDLE)FileW);
    FileW = -1;
  }
  VolumeNameForPath = CNTPrefetcherFile::GetSizeInClusters(p_OutBuffer, &v30);
  v6 = VolumeNameForPath;
  if ( VolumeNameForPath >= 0 )
  {
    v17 = v4;
    v4 = 0;
    v18 = v33;
    *((_OWORD *)this + 2) = OutBuffer;
    *((_OWORD *)this + 3) = v18;
    v19 = (void *)*((_QWORD *)this + 3);
    if ( v19 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
    }
    v21 = (v35 & 0x10) == 0;
    v22 = v29;
    *((_QWORD *)this + 3) = v17;
    *((_QWORD *)this + 1) = v22;
    *((_QWORD *)this + 2) = v30;
    *((_DWORD *)this + 1) = 1;
    if ( !v21 )
      *((_DWORD *)this + 1) = 3;
    goto LABEL_50;
  }
LABEL_2:
  v7 = VolumeNameForPath;
LABEL_3:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_50:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v4 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v4);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180028d7c  mov     [rsp-8+arg_8], rbx
0x180028d81  mov     [rsp-8+arg_10], rsi
0x180028d86  push    rbp
0x180028d87  push    rdi
0x180028d88  push    r12
0x180028d8a  push    r14
0x180028d8c  push    r15
0x180028d8e  lea     rbp, [rsp-1E0h]
0x180028d96  sub     rsp, 2E0h
0x180028d9d  mov     rax, cs:__security_cookie
0x180028da4  xor     rax, rsp
0x180028da7  mov     [rbp+200h+var_30], rax
0x180028dae  xor     eax, eax
0x180028db0  mov     [rsp+300h+var_2B0], 0
0x180028db9  xorps   xmm0, xmm0
0x180028dbc  mov     [rbp+200h+var_250], rax
0x180028dc0  xorps   xmm1, xmm1
0x180028dc3  mov     [rsp+300h+BytesReturned], eax
0x180028dc7  mov     r15, rcx
0x180028dca  mov     [rsp+300h+var_2A8], rax
0x180028dcf  or      r14, 0FFFFFFFFFFFFFFFFh
0x180028dd3  mov     [rsp+300h+InBuffer], rax
0x180028dd8  lea     rcx, aMft; "$MFT"
0x180028ddf  mov     rbx, r14
0x180028de2  lea     rdx, [rbp+200h+FileName]
0x180028de6  xor     edi, edi
0x180028de8  movups  [rbp+200h+FileInformation], xmm0
0x180028dec  movups  [rbp+200h+var_260], xmm0
0x180028df0  movups  xmmword ptr [rsp+300h+IoStatusBlock], xmm0
0x180028df5  movups  [rsp+300h+OutBuffer], xmm1
0x180028dfa  movups  [rbp+200h+var_280], xmm1
0x180028dfe  call    ?GetVolumeNameForPath@?$CFileUtilsT@VCEmptyType@@@@SAJPEBGPEAGK@Z; CFileUtilsT<CEmptyType>::GetVolumeNameForPath(ushort const *,ushort *,ulong)
0x180028e03  mov     esi, eax
0x180028e05  test    eax, eax
0x180028e07  jns     short loc_180028E15
0x180028e09  mov     ecx, eax
0x180028e0b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028e10  jmp     loc_1800290DA
0x180028e15  lea     r8, aMft; "$MFT"
0x180028e1c  mov     edx, 104h; unsigned __int64
0x180028e21  lea     rcx, [rbp+200h+FileName]; unsigned __int16 *
0x180028e25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180028e2a  mov     [rsp+300h+var_2C0], eax
0x180028e2e  mov     esi, eax
0x180028e30  test    eax, eax
0x180028e32  js      short loc_180028E09
0x180028e34  xor     r9d, r9d; lpSecurityAttributes
0x180028e37  mov     [rsp+300h+hTemplateFile], rdi; hTemplateFile
0x180028e3c  mov     [rsp+300h+dwFlagsAndAttributes], 22200000h; dwFlagsAndAttributes
0x180028e44  lea     rcx, [rbp+200h+FileName]; lpFileName
0x180028e48  mov     edx, 100080h; dwDesiredAccess
0x180028e4d  mov     [rsp+300h+dwCreationDisposition], 3; dwCreationDisposition
0x180028e55  lea     r8d, [r9+7]; dwShareMode
0x180028e59  call    cs:__imp_CreateFileW
0x180028e5f  mov     rbx, rax
0x180028e62  dec     rax
0x180028e65  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028e69  ja      loc_1800290B2
0x180028e6f  mov     rcx, rbx; FileHandle
0x180028e72  mov     [rsp+300h+dwCreationDisposition], 4; FileInformationClass
0x180028e7a  mov     r9d, 28h ; '('; Length
0x180028e80  lea     r8, [rbp+200h+FileInformation]; FileInformation
0x180028e84  lea     rdx, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x180028e89  call    cs:__imp_NtQueryInformationFile
0x180028e8f  mov     ecx, eax
0x180028e91  lea     rdx, [rsp+300h+var_2C0]
0x180028e96  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180028e9b  test    eax, eax
0x180028e9d  jnz     short loc_180028EAA
0x180028e9f  mov     esi, [rsp+300h+var_2C0]
0x180028ea3  mov     ecx, esi
0x180028ea5  jmp     loc_180028E0B
0x180028eaa  mov     [rsp+300h+InBuffer], rdi
0x180028eaf  lea     r12, [rsp+300h+OutBuffer]
0x180028eb4  mov     r14d, 20h ; ' '
0x180028eba  xor     ecx, ecx
0x180028ebc  mov     [rsp+300h+lpOverlapped], 0; lpOverlapped
0x180028ec5  lea     rax, [rbx-1]
0x180028ec9  mov     r9d, 8; nInBufferSize
0x180028ecf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028ed3  lea     r8, [rsp+300h+InBuffer]; lpInBuffer
0x180028ed8  lea     rax, [rsp+300h+BytesReturned]
0x180028edd  mov     edx, 90073h; dwIoControlCode
0x180028ee2  mov     [rsp+300h+hTemplateFile], rax; lpBytesReturned
0x180028ee7  cmovbe  rcx, rbx; hDevice
0x180028eeb  mov     [rsp+300h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x180028ef0  mov     qword ptr [rsp+300h+dwCreationDisposition], r12; lpOutBuffer
0x180028ef5  call    cs:__imp_DeviceIoControl
0x180028efb  test    eax, eax
0x180028efd  jnz     loc_180028FE1
0x180028f03  call    cs:__imp_GetLastError
0x180028f09  mov     esi, eax
0x180028f0b  cmp     eax, 26h ; '&'
0x180028f0e  jz      loc_180028FE1
0x180028f14  cmp     eax, 0EAh
0x180028f19  jz      short loc_180028F29
0x180028f1b  cmp     eax, 7Ah ; 'z'
0x180028f1e  jz      short loc_180028F29
0x180028f20  cmp     eax, 6Fh ; 'o'
0x180028f23  jnz     loc_180028FB1
0x180028f29  test    r14d, r14d
0x180028f2c  jz      short loc_180028F53
0x180028f2e  mov     ecx, r14d
0x180028f31  shl     ecx, 4
0x180028f34  mov     eax, ecx
0x180028f36  shr     eax, 4
0x180028f39  cmp     eax, r14d
0x180028f3c  jz      short loc_180028F4E
0x180028f3e  mov     eax, 80070216h
0x180028f43  mov     ecx, eax
0x180028f45  mov     esi, eax
0x180028f47  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180028f4c  jmp     short loc_180028F58
0x180028f4e  mov     r14d, ecx
0x180028f51  jmp     short loc_180028F56
0x180028f53  xor     r14d, r14d
0x180028f56  xor     esi, esi
0x180028f58  mov     ecx, esi
0x180028f5a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028f5f  mov     [rsp+300h+var_2C0], esi
0x180028f63  test    esi, esi
0x180028f65  js      loc_180028EA3
0x180028f6b  cmp     r14d, 100000h
0x180028f72  ja      short loc_180028FD7
0x180028f74  call    cs:__imp_GetProcessHeap
0x180028f7a  mov     r8d, r14d; dwBytes
0x180028f7d  xor     edx, edx; dwFlags
0x180028f7f  mov     rcx, rax; hHeap
0x180028f82  call    cs:__imp_HeapAlloc
0x180028f88  mov     r12, rax
0x180028f8b  test    rdi, rdi
0x180028f8e  jz      short loc_180028FA4
0x180028f90  call    cs:__imp_GetProcessHeap
0x180028f96  mov     r8, rdi; lpMem
0x180028f99  xor     edx, edx; dwFlags
0x180028f9b  mov     rcx, rax; hHeap
0x180028f9e  call    cs:__imp_HeapFree
0x180028fa4  test    r12, r12
0x180028fa7  jz      short loc_180028FCB
0x180028fa9  mov     rdi, r12
0x180028fac  jmp     loc_180028EBA
0x180028fb1  test    eax, eax
0x180028fb3  jle     short loc_180028FBE
0x180028fb5  movzx   esi, ax
0x180028fb8  or      esi, 80070000h
0x180028fbe  test    esi, esi
0x180028fc0  jns     loc_1800290DA
0x180028fc6  jmp     loc_180028EA3
0x180028fcb  xor     edi, edi
0x180028fcd  mov     esi, 8007000Eh
0x180028fd2  jmp     loc_180028EA3
0x180028fd7  mov     esi, 6Fh ; 'o'
0x180028fdc  jmp     loc_1800290DA
0x180028fe1  xor     ecx, ecx
0x180028fe3  mov     [rsp+300h+dwCreationDisposition], 6; FileInformationClass
0x180028feb  lea     rax, [rbx-1]
0x180028fef  mov     r9d, 8; Length
0x180028ff5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180028ff9  lea     r8, [rsp+300h+var_2B0]; FileInformation
0x180028ffe  lea     rdx, [rsp+300h+IoStatusBlock]; IoStatusBlock
0x180029003  cmovbe  rcx, rbx; FileHandle
0x180029007  call    cs:__imp_NtQueryInformationFile
0x18002900d  mov     ecx, eax
0x18002900f  lea     rdx, [rsp+300h+var_2C0]
0x180029014  call    ?C_NtStatus2HR@?$SErrorConverterT@VCEmptyType@@@@SAHJPEAJ@Z; SErrorConverterT<CEmptyType>::C_NtStatus2HR(long,long *)
0x180029019  test    eax, eax
0x18002901b  jz      loc_180028E9F
0x180029021  lea     rax, [rbx-1]
0x180029025  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180029029  ja      short loc_180029038
0x18002902b  mov     rcx, rbx; hObject
0x18002902e  call    cs:__imp_CloseHandle
0x180029034  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029038  lea     rdx, [rsp+300h+var_2A8]; __int64 *
0x18002903d  mov     rcx, r12; struct RETRIEVAL_POINTERS_BUFFER *
0x180029040  call    ?GetSizeInClusters@CNTPrefetcherFile@@CAJPEBURETRIEVAL_POINTERS_BUFFER@@PEA_J@Z; CNTPrefetcherFile::GetSizeInClusters(RETRIEVAL_POINTERS_BUFFER const *,__int64 *)
0x180029045  mov     esi, eax
0x180029047  test    eax, eax
0x180029049  js      loc_180028E09
0x18002904f  movups  xmm0, [rsp+300h+OutBuffer]
0x180029054  mov     r12, rdi
0x180029057  xor     edi, edi
0x180029059  movups  xmm1, [rbp+200h+var_280]
0x18002905d  movups  xmmword ptr [r15+20h], xmm0
0x180029062  movups  xmmword ptr [r15+30h], xmm1
0x180029067  mov     r14, [r15+18h]
0x18002906b  test    r14, r14
0x18002906e  jz      short loc_180029084
0x180029070  call    cs:__imp_GetProcessHeap
0x180029076  mov     r8, r14; lpMem
0x180029079  xor     edx, edx; dwFlags
0x18002907b  mov     rcx, rax; hHeap
0x18002907e  call    cs:__imp_HeapFree
0x180029084  test    byte ptr [rbp+200h+var_250], 10h
0x180029088  mov     rax, [rsp+300h+var_2B0]
0x18002908d  mov     [r15+18h], r12
0x180029091  mov     [r15+8], rax
0x180029095  mov     rax, [rsp+300h+var_2A8]
0x18002909a  mov     [r15+10h], rax
0x18002909e  mov     dword ptr [r15+4], 1
0x1800290a6  jz      short loc_1800290DA
0x1800290a8  mov     dword ptr [r15+4], 3
0x1800290b0  jmp     short loc_1800290DA
0x1800290b2  call    cs:__imp_GetLastError
0x1800290b8  mov     esi, eax
0x1800290ba  test    eax, eax
0x1800290bc  jnz     short loc_1800290C5
0x1800290be  mov     esi, 80004005h
0x1800290c3  jmp     short loc_1800290D0
0x1800290c5  jle     short loc_1800290D0
0x1800290c7  movzx   esi, ax
0x1800290ca  or      esi, 80070000h
0x1800290d0  mov     ecx, esi
0x1800290d2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800290d7  mov     rbx, r14
0x1800290da  mov     ecx, esi
0x1800290dc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800290e1  test    rdi, rdi
0x1800290e4  jz      short loc_1800290FA
0x1800290e6  call    cs:__imp_GetProcessHeap
0x1800290ec  mov     r8, rdi; lpMem
0x1800290ef  xor     edx, edx; dwFlags
0x1800290f1  mov     rcx, rax; hHeap
0x1800290f4  call    cs:__imp_HeapFree
0x1800290fa  lea     rcx, [rbx-1]
0x1800290fe  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180029102  ja      short loc_18002910D
0x180029104  mov     rcx, rbx; hObject
0x180029107  call    cs:__imp_CloseHandle
0x18002910d  mov     eax, esi
0x18002910f  mov     rcx, [rbp+200h+var_30]
0x180029116  xor     rcx, rsp; StackCookie
0x180029119  call    __security_check_cookie
0x18002911e  lea     r11, [rsp+300h+var_20]
0x180029126  mov     rbx, [r11+38h]
0x18002912a  mov     rsi, [r11+40h]
0x18002912e  mov     rsp, r11
0x180029131  pop     r15
0x180029133  pop     r14
0x180029135  pop     r12
0x180029137  pop     rdi
0x180029138  pop     rbp
0x180029139  retn
```
