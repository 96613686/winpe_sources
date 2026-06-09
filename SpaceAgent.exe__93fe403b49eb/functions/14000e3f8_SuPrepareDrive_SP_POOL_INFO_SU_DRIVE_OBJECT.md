# SuPrepareDrive(_SP_POOL_INFO *,_SU_DRIVE_OBJECT *)

- ea: `0x14000e3f8`
- end: `0x14000e85a`
- name: `?SuPrepareDrive@@YAHPEAU_SP_POOL_INFO@@PEAU_SU_DRIVE_OBJECT@@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(struct _SP_POOL_INFO *, struct _SU_DRIVE_OBJECT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ce60`
- `0x14000f0c4`

## callees

- `0x140001caf`
- `0x140004114`
- `0x140008190`
- `0x1400081d4`
- `0x14000b828`
- `0x14000b934`
- `0x14000c104`
- `0x14000c6e0`
- `0x14000c7a4`
- `0x14000e3f8`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000e80c`
- `KERNEL32!LocalFree` at `0x14000e80c`
- `KERNEL32!CloseHandle` at `0x14000e81b`
- `KERNEL32!CloseHandle` at `0x14000e81b`
- `KERNEL32!SetLastError` at `0x14000e4a1`
- `KERNEL32!SetLastError` at `0x14000e828`
- `KERNEL32!SetLastError` at `0x14000e4a1`
- `KERNEL32!SetLastError` at `0x14000e828`
- `KERNEL32!GetLastError` at `0x14000e6ba`
- `KERNEL32!GetLastError` at `0x14000e6ba`
- `KERNEL32!QueryPerformanceCounter` at `0x14000e48c`
- `KERNEL32!QueryPerformanceCounter` at `0x14000e735`
- `KERNEL32!QueryPerformanceCounter` at `0x14000e48c`
- `KERNEL32!QueryPerformanceCounter` at `0x14000e735`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000e5be`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000e5be`
- `KERNEL32!DeviceIoControl` at `0x14000e59e`
- `KERNEL32!DeviceIoControl` at `0x14000e6a2`
- `KERNEL32!DeviceIoControl` at `0x14000e721`
- `KERNEL32!DeviceIoControl` at `0x14000e7fe`
- `KERNEL32!DeviceIoControl` at `0x14000e59e`
- `KERNEL32!DeviceIoControl` at `0x14000e6a2`
- `KERNEL32!DeviceIoControl` at `0x14000e721`
- `KERNEL32!DeviceIoControl` at `0x14000e7fe`
- `KERNEL32!CreateFileW` at `0x14000e4eb`
- `KERNEL32!CreateFileW` at `0x14000e4eb`

## string_xrefs

- `0x14000e503`: `CreateFile`
- `0x14000e6b3`: `DeviceIoControl - IOCTL_DISK_CREATE_SPACES_METADATA`

## pseudocode

```c
__int64 __fastcall SuPrepareDrive(struct _SP_POOL_INFO *a1, struct _SU_DRIVE_OBJECT *a2)
{
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // r15
  HANDLE FileW; // rax
  void *v6; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdi
  unsigned int DriveLayout; // eax
  int v10; // ebx
  unsigned int v11; // ecx
  char *v12; // r8
  __int64 v13; // rax
  __int128 v14; // xmm1
  DWORD LastError; // r14d
  char *v16; // r12
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  DWORD BytesReturned[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h]
  DWORD v23; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h]
  _DWORD v28[4]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE InBuffer[40]; // [rsp+80h] [rbp-80h] BYREF
  __int64 OutBuffer; // [rsp+A8h] [rbp-58h] BYREF
  int v31; // [rsp+B0h] [rbp-50h]
  _DWORD v32[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v33[256]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v34; // [rsp+2C8h] [rbp+1C8h]
  __int128 v35; // [rsp+2D8h] [rbp+1D8h]
  __int16 v36; // [rsp+2E8h] [rbp+1E8h]
  GUID v37; // [rsp+2ECh] [rbp+1ECh]
  GUID v38; // [rsp+2FCh] [rbp+1FCh]
  __int64 v39; // [rsp+310h] [rbp+210h]
  struct _FILETIME v40; // [rsp+318h] [rbp+218h]
  WCHAR FileName[32]; // [rsp+320h] [rbp+220h] BYREF

  v23 = 0;
  *(_QWORD *)BytesReturned = 0;
  v4 = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  memset_0(v32, 0, 0x260u);
  memset_0(FileName, 0, sizeof(FileName));
  v22 = 0;
  SystemTimeAsFileTime = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( !(unsigned int)SiAttemptShrinkDynamic((struct _SU_DRIVE_OBJECT *)((char *)a2 + 72)) )
    SetLastError(0);
  StringCchPrintfW(FileName, 0x20u, (size_t *)L"\\\\.\\PhysicalDrive%d", *((unsigned int *)a2 + 28));
  FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v7 = 0;
    v8 = "CreateFile";
LABEL_21:
    LastError = GetLastError();
    goto LABEL_23;
  }
  DriveLayout = SiGetDriveLayoutEx(FileW, (struct _DRIVE_LAYOUT_INFORMATION_EX **)BytesReturned);
  v4 = *(struct _DRIVE_LAYOUT_INFORMATION_EX **)BytesReturned;
  v7 = DriveLayout;
  if ( !DriveLayout )
  {
    v8 = "SiGetDriveLayoutEx";
    goto LABEL_21;
  }
  if ( SiGetNumberOfPartitions(*(struct _DRIVE_LAYOUT_INFORMATION_EX **)BytesReturned) )
  {
    *(_QWORD *)&InBuffer[8] = 0;
    *(_QWORD *)&InBuffer[16] = 6;
  }
  else
  {
    *(_QWORD *)&InBuffer[8] = 4;
    *(_QWORD *)&InBuffer[16] = 7;
  }
  *(_DWORD *)InBuffer = 40;
  BytesReturned[0] = 0;
  *(GUID *)&InBuffer[24] = PARTITION_SPACES_GUID;
  v7 = DeviceIoControl(v6, 0x7C0F4u, InBuffer, 0x28u, 0, 0, BytesReturned, 0);
  if ( !v7 )
  {
    v8 = "SiSetDiskAttributes";
    goto LABEL_21;
  }
  v10 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v11 = 0;
  v12 = (char *)a1 + *((unsigned int *)a1 + 661);
  while ( v11 < *((_DWORD *)a1 + 660) )
  {
    v13 = *(_QWORD *)&v12[16 * v11] - *((_QWORD *)a2 + 7);
    if ( !v13 )
      v13 = *(_QWORD *)&v12[16 * v11 + 8] - *((_QWORD *)a2 + 8);
    if ( !v13 )
    {
      v10 = 1;
      break;
    }
    ++v11;
  }
  v32[1] = *((_DWORD *)a1 + 647);
  v32[0] = 608;
  StringCchCopyW(v33, 0x100u, (size_t *)a1 + 3);
  v14 = *(_OWORD *)((char *)a2 + 56);
  v34 = *(_OWORD *)((char *)a1 + 8);
  v35 = v14;
  v36 = v10 != 0;
  v40 = SystemTimeAsFileTime;
  v39 = 1;
  v37 = GUID_NULL;
  v38 = GUID_NULL;
  v7 = DeviceIoControl(v6, 0x70C020u, v32, 0x260u, 0, 0, &v23, 0);
  if ( !v7 )
  {
    v22 = 1;
    v8 = "DeviceIoControl - IOCTL_DISK_CREATE_SPACES_METADATA";
    goto LABEL_21;
  }
  OutBuffer = 0;
  v31 = 0;
  v22 = 0;
  BytesReturned[0] = 0;
  v28[2] = 257;
  LastError = 0;
  v8 = 0;
  v28[0] = 1;
  v28[1] = 12;
  DeviceIoControl(v6, 0x2D1104u, v28, 0xCu, &OutBuffer, 0xCu, BytesReturned, 0);
LABEL_23:
  v16 = (char *)a2 + 56;
  QueryPerformanceCounter(&v26);
  if ( v7 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjx_EventWriteTransfer(
        v17,
        (unsigned int)PrepareDriveSucceeded,
        v18,
        v19,
        (__int64)"SuPrepareDrive",
        (__int64)v16,
        1000000 * (v26.QuadPart - PerformanceCount.QuadPart) / v27);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjsq_EventWriteTransfer(
      v17,
      (unsigned int)PrepareDriveFailed,
      v18,
      v19,
      (__int64)"SuPrepareDrive",
      (__int64)v16,
      (__int64)v8,
      LastError);
  }
  if ( v22 )
  {
    InBuffer[5] = 1;
    *(_QWORD *)&InBuffer[8] = 0;
    *(_QWORD *)&InBuffer[16] = 4;
    BytesReturned[0] = 0;
    DeviceIoControl(v6, 0x7C0F4u, InBuffer, 0x28u, 0, 0, BytesReturned, 0);
  }
  if ( v4 )
    LocalFree(v4);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  if ( !v7 )
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x14000e3f8  mov     [rsp-8+arg_10], rbx
0x14000e3fd  push    rbp
0x14000e3fe  push    rsi
0x14000e3ff  push    rdi
0x14000e400  push    r12
0x14000e402  push    r13
0x14000e404  push    r14
0x14000e406  push    r15
0x14000e408  lea     rbp, [rsp-270h]
0x14000e410  sub     rsp, 370h
0x14000e417  mov     rax, cs:__security_cookie
0x14000e41e  xor     rax, rsp
0x14000e421  mov     [rbp+2A0h+var_40], rax
0x14000e428  xorps   xmm0, xmm0
0x14000e42b  xor     r12d, r12d
0x14000e42e  mov     r13, rdx
0x14000e431  mov     [rsp+3A0h+var_354], r12d
0x14000e436  mov     rdi, rcx
0x14000e439  mov     qword ptr [rsp+3A0h+BytesReturned], r12
0x14000e43e  xor     eax, eax
0x14000e440  lea     rcx, [rbp+2A0h+var_2E0]; void *
0x14000e444  xor     edx, edx; Val
0x14000e446  mov     [rbp+2A0h+var_300], rax
0x14000e44a  mov     r8d, 260h; Size
0x14000e450  mov     r15d, r12d
0x14000e453  movups  [rbp+2A0h+InBuffer], xmm0
0x14000e457  movups  [rbp+2A0h+var_310], xmm0
0x14000e45b  call    memset_0
0x14000e460  xor     edx, edx; Val
0x14000e462  lea     r8d, [r12+40h]; Size
0x14000e467  lea     rcx, [rbp+2A0h+FileName]; void *
0x14000e46e  call    memset_0
0x14000e473  lea     rcx, [rsp+3A0h+PerformanceCount]; this
0x14000e478  mov     [rsp+3A0h+var_358], r12d
0x14000e47d  mov     qword ptr [rsp+3A0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x14000e482  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000e487  lea     rcx, [rsp+3A0h+PerformanceCount]; lpPerformanceCount
0x14000e48c  call    cs:__imp_QueryPerformanceCounter
0x14000e492  lea     rcx, [r13+48h]; struct _SP_DRIVE_INFO *
0x14000e496  call    ?SiAttemptShrinkDynamic@@YAHPEAU_SP_DRIVE_INFO@@@Z; SiAttemptShrinkDynamic(_SP_DRIVE_INFO *)
0x14000e49b  test    eax, eax
0x14000e49d  jnz     short loc_14000E4A7
0x14000e49f  xor     ecx, ecx; dwErrCode
0x14000e4a1  call    cs:__imp_SetLastError
0x14000e4a7  mov     r9d, [r13+70h]
0x14000e4ab  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000e4b2  mov     edx, 20h ; ' '; unsigned __int64
0x14000e4b7  lea     rcx, [rbp+2A0h+FileName]; unsigned __int16 *
0x14000e4be  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e4c3  xor     r9d, r9d; lpSecurityAttributes
0x14000e4c6  mov     [rsp+3A0h+hTemplateFile], r12; hTemplateFile
0x14000e4cb  mov     [rsp+3A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000e4d3  lea     rcx, [rbp+2A0h+FileName]; lpFileName
0x14000e4da  mov     edx, 0C0000000h; dwDesiredAccess
0x14000e4df  mov     [rsp+3A0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000e4e7  lea     r8d, [r9+7]; dwShareMode
0x14000e4eb  call    cs:__imp_CreateFileW
0x14000e4f1  mov     rsi, rax
0x14000e4f4  mov     r14d, 1
0x14000e4fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e4fe  jnz     short loc_14000E50F
0x14000e500  mov     ebx, r12d
0x14000e503  lea     rdi, aCreatefile; "CreateFile"
0x14000e50a  jmp     loc_14000E6BA
0x14000e50f  lea     rdx, [rsp+3A0h+BytesReturned]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14000e514  mov     rcx, rsi; hDevice
0x14000e517  call    ?SiGetDriveLayoutEx@@YAHPEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; SiGetDriveLayoutEx(void *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14000e51c  mov     r15, qword ptr [rsp+3A0h+BytesReturned]
0x14000e521  mov     ebx, eax
0x14000e523  test    eax, eax
0x14000e525  jnz     short loc_14000E533
0x14000e527  lea     rdi, aSigetdrivelayo; "SiGetDriveLayoutEx"
0x14000e52e  jmp     loc_14000E6BA
0x14000e533  mov     rcx, r15; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x14000e536  call    ?SiGetNumberOfPartitions@@YAKPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; SiGetNumberOfPartitions(_DRIVE_LAYOUT_INFORMATION_EX *)
0x14000e53b  test    eax, eax
0x14000e53d  jnz     short loc_14000E551
0x14000e53f  mov     qword ptr [rbp+2A0h+InBuffer+8], 4
0x14000e547  mov     qword ptr [rbp+2A0h+var_310], 7
0x14000e54f  jmp     short loc_14000E55D
0x14000e551  mov     qword ptr [rbp+2A0h+InBuffer+8], r12
0x14000e555  mov     qword ptr [rbp+2A0h+var_310], 6
0x14000e55d  movups  xmm0, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000e564  mov     ecx, 28h ; '('
0x14000e569  mov     [rsp+3A0h+lpOverlapped], r12; lpOverlapped
0x14000e56e  lea     rax, [rsp+3A0h+BytesReturned]
0x14000e573  mov     dword ptr [rbp+2A0h+InBuffer], ecx
0x14000e576  mov     [rsp+3A0h+hTemplateFile], rax; lpBytesReturned
0x14000e57b  lea     r8, [rbp+2A0h+InBuffer]; lpInBuffer
0x14000e57f  mov     r9d, ecx; nInBufferSize
0x14000e582  mov     [rsp+3A0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x14000e587  mov     rcx, rsi; hDevice
0x14000e58a  mov     qword ptr [rsp+3A0h+dwCreationDisposition], r12; lpOutBuffer
0x14000e58f  mov     edx, 7C0F4h; dwIoControlCode
0x14000e594  mov     [rsp+3A0h+BytesReturned], r12d
0x14000e599  movdqu  [rbp+2A0h+var_310+8], xmm0
0x14000e59e  call    cs:__imp_DeviceIoControl
0x14000e5a4  mov     ebx, eax
0x14000e5a6  test    eax, eax
0x14000e5a8  jnz     short loc_14000E5B6
0x14000e5aa  lea     rdi, aSisetdiskattri; "SiSetDiskAttributes"
0x14000e5b1  jmp     loc_14000E6BA
0x14000e5b6  lea     rcx, [rsp+3A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000e5bb  mov     ebx, r12d
0x14000e5be  call    cs:__imp_GetSystemTimeAsFileTime
0x14000e5c4  mov     r8d, [rdi+0A54h]
0x14000e5cb  mov     ecx, r12d
0x14000e5ce  add     r8, rdi
0x14000e5d1  cmp     ecx, [rdi+0A50h]
0x14000e5d7  jnb     short loc_14000E5FE
0x14000e5d9  mov     edx, ecx
0x14000e5db  add     rdx, rdx
0x14000e5de  mov     rax, [r8+rdx*8]
0x14000e5e2  sub     rax, [r13+38h]
0x14000e5e6  jnz     short loc_14000E5F1
0x14000e5e8  mov     rax, [r8+rdx*8+8]
0x14000e5ed  sub     rax, [r13+40h]
0x14000e5f1  test    rax, rax
0x14000e5f4  jz      short loc_14000E5FB
0x14000e5f6  add     ecx, r14d
0x14000e5f9  jmp     short loc_14000E5D1
0x14000e5fb  mov     ebx, r14d
0x14000e5fe  mov     eax, [rdi+0A1Ch]
0x14000e604  lea     r8, [rdi+18h]; unsigned __int16 *
0x14000e608  mov     edx, 100h; unsigned __int64
0x14000e60d  mov     [rbp+2A0h+var_2DC], eax
0x14000e610  lea     rcx, [rbp+2A0h+var_2D8]; unsigned __int16 *
0x14000e614  mov     [rbp+2A0h+var_2E0], 260h
0x14000e61b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000e620  mov     [rbp+2A0h+var_B8], r14w
0x14000e628  movups  xmm0, xmmword ptr [rdi+8]
0x14000e62c  movups  xmm1, xmmword ptr [r13+38h]
0x14000e631  movdqu  [rbp+2A0h+var_D8], xmm0
0x14000e639  movdqu  [rbp+2A0h+var_C8], xmm1
0x14000e641  test    ebx, ebx
0x14000e643  jnz     short loc_14000E64D
0x14000e645  mov     [rbp+2A0h+var_B8], r12w
0x14000e64d  mov     rax, qword ptr [rsp+3A0h+SystemTimeAsFileTime.dwLowDateTime]
0x14000e652  lea     r8, [rbp+2A0h+var_2E0]; lpInBuffer
0x14000e656  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000e65d  mov     [rsp+3A0h+lpOverlapped], r12; lpOverlapped
0x14000e662  mov     r9d, 260h; nInBufferSize
0x14000e668  mov     [rbp+2A0h+var_88], rax
0x14000e66f  mov     edx, 70C020h; dwIoControlCode
0x14000e674  lea     rax, [rsp+3A0h+var_354]
0x14000e679  mov     [rbp+2A0h+var_90], r14
0x14000e680  mov     [rsp+3A0h+hTemplateFile], rax; lpBytesReturned
0x14000e685  mov     rcx, rsi; hDevice
0x14000e688  mov     [rsp+3A0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x14000e68d  mov     qword ptr [rsp+3A0h+dwCreationDisposition], r12; lpOutBuffer
0x14000e692  movdqu  [rbp+2A0h+var_B4], xmm0
0x14000e69a  movdqu  [rbp+2A0h+var_A4], xmm0
0x14000e6a2  call    cs:__imp_DeviceIoControl
0x14000e6a8  mov     ebx, eax
0x14000e6aa  test    eax, eax
0x14000e6ac  jnz     short loc_14000E6C5
0x14000e6ae  mov     [rsp+3A0h+var_358], r14d
0x14000e6b3  lea     rdi, aDeviceiocontro_1; "DeviceIoControl - IOCTL_DISK_CREATE_SPA"...
0x14000e6ba  call    cs:__imp_GetLastError
0x14000e6c0  mov     r14d, eax
0x14000e6c3  jmp     short loc_14000E727
0x14000e6c5  xor     eax, eax
0x14000e6c7  mov     [rsp+3A0h+lpOverlapped], r12; lpOverlapped
0x14000e6cc  mov     [rbp+2A0h+OutBuffer], rax
0x14000e6d0  lea     r8, [rsp+3A0h+var_330]; lpInBuffer
0x14000e6d5  mov     [rbp+2A0h+var_2F0], eax
0x14000e6d8  mov     edx, 2D1104h; dwIoControlCode
0x14000e6dd  mov     rcx, rsi; hDevice
0x14000e6e0  mov     [rsp+3A0h+var_358], r12d
0x14000e6e5  lea     r9d, [rax+0Ch]; nInBufferSize
0x14000e6e9  mov     [rsp+3A0h+BytesReturned], r12d
0x14000e6ee  lea     rax, [rsp+3A0h+BytesReturned]
0x14000e6f3  mov     [rsp+3A0h+var_328], 101h
0x14000e6fb  mov     [rsp+3A0h+hTemplateFile], rax; lpBytesReturned
0x14000e700  mov     r14d, r12d
0x14000e703  lea     rax, [rbp+2A0h+OutBuffer]
0x14000e707  mov     [rsp+3A0h+dwFlagsAndAttributes], r9d; nOutBufferSize
0x14000e70c  mov     qword ptr [rsp+3A0h+dwCreationDisposition], rax; lpOutBuffer
0x14000e711  mov     rdi, r12
0x14000e714  mov     [rsp+3A0h+var_330], 1
0x14000e71c  mov     [rsp+3A0h+var_32C], r9d
0x14000e721  call    cs:__imp_DeviceIoControl
0x14000e727  mov     eax, 38h ; '8'
0x14000e72c  lea     rcx, [rsp+3A0h+var_340]; lpPerformanceCount
0x14000e731  lea     r12, [rax+r13]
0x14000e735  call    cs:__imp_QueryPerformanceCounter
0x14000e73b  xor     r13d, r13d
0x14000e73e  test    ebx, ebx
0x14000e740  jz      short loc_14000E787
0x14000e742  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000e749  jz      short loc_14000E7B7
0x14000e74b  mov     rax, qword ptr [rsp+3A0h+var_340]
0x14000e750  sub     rax, qword ptr [rsp+3A0h+PerformanceCount]
0x14000e755  imul    rax, 0F4240h
0x14000e75c  cqo
0x14000e75e  idiv    [rsp+3A0h+var_338]
0x14000e763  lea     rdx, PrepareDriveSucceeded
0x14000e76a  mov     [rsp+3A0h+hTemplateFile], rax
0x14000e76f  lea     rax, aSupreparedrive; "SuPrepareDrive"
0x14000e776  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], r12
0x14000e77b  mov     qword ptr [rsp+3A0h+dwCreationDisposition], rax
0x14000e780  call    McTemplateK0zsjx_EventWriteTransfer
0x14000e785  jmp     short loc_14000E7B7
0x14000e787  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000e78e  jz      short loc_14000E7B7
0x14000e790  mov     dword ptr [rsp+3A0h+lpOverlapped], r14d
0x14000e795  lea     rax, aSupreparedrive; "SuPrepareDrive"
0x14000e79c  mov     [rsp+3A0h+hTemplateFile], rdi
0x14000e7a1  lea     rdx, PrepareDriveFailed
0x14000e7a8  mov     qword ptr [rsp+3A0h+dwFlagsAndAttributes], r12
0x14000e7ad  mov     qword ptr [rsp+3A0h+dwCreationDisposition], rax
0x14000e7b2  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000e7b7  cmp     [rsp+3A0h+var_358], r13d
0x14000e7bc  jz      short loc_14000E804
0x14000e7be  mov     [rsp+3A0h+lpOverlapped], r13; lpOverlapped
0x14000e7c3  lea     rax, [rsp+3A0h+BytesReturned]
0x14000e7c8  mov     [rsp+3A0h+hTemplateFile], rax; lpBytesReturned
0x14000e7cd  lea     r8, [rbp+2A0h+InBuffer]; lpInBuffer
0x14000e7d1  mov     [rsp+3A0h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x14000e7d6  mov     r9d, 28h ; '('; nInBufferSize
0x14000e7dc  mov     edx, 7C0F4h; dwIoControlCode
0x14000e7e1  mov     qword ptr [rsp+3A0h+dwCreationDisposition], r13; lpOutBuffer
0x14000e7e6  mov     rcx, rsi; hDevice
0x14000e7e9  mov     byte ptr [rbp+2A0h+InBuffer+5], 1
0x14000e7ed  mov     qword ptr [rbp+2A0h+InBuffer+8], r13
0x14000e7f1  mov     qword ptr [rbp+2A0h+var_310], 4
0x14000e7f9  mov     [rsp+3A0h+BytesReturned], r13d
0x14000e7fe  call    cs:__imp_DeviceIoControl
0x14000e804  test    r15, r15
0x14000e807  jz      short loc_14000E812
0x14000e809  mov     rcx, r15; hMem
0x14000e80c  call    cs:__imp_LocalFree
0x14000e812  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000e816  jz      short loc_14000E821
0x14000e818  mov     rcx, rsi; hObject
0x14000e81b  call    cs:__imp_CloseHandle
0x14000e821  test    ebx, ebx
0x14000e823  jnz     short loc_14000E82E
0x14000e825  mov     ecx, r14d; dwErrCode
0x14000e828  call    cs:__imp_SetLastError
0x14000e82e  mov     eax, ebx
0x14000e830  mov     rcx, [rbp+2A0h+var_40]
0x14000e837  xor     rcx, rsp; StackCookie
0x14000e83a  call    __security_check_cookie
0x14000e83f  mov     rbx, [rsp+3A0h+arg_10]
0x14000e847  add     rsp, 370h
0x14000e84e  pop     r15
0x14000e850  pop     r14
0x14000e852  pop     r13
0x14000e854  pop     r12
0x14000e856  pop     rdi
0x14000e857  pop     rsi
0x14000e858  pop     rbp
0x14000e859  retn
```
