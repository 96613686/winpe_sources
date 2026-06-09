# SuResetDrive(_SU_DRIVE_OBJECT *)

- ea: `0x14000f0c4`
- end: `0x14000f402`
- name: `?SuResetDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z`
- size: `830`
- prototype: `__int64 __fastcall(struct _SU_DRIVE_OBJECT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140019804`

## callees

- `0x140001caf`
- `0x140004114`
- `0x1400081d4`
- `0x14000a440`
- `0x14000b828`
- `0x14000b934`
- `0x14000cf3c`
- `0x14000e340`
- `0x14000e3f8`
- `0x14000f0c4`
- `0x14000f450`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000f3cd`
- `KERNEL32!LocalFree` at `0x14000f3cd`
- `KERNEL32!CloseHandle` at `0x14000f3bf`
- `KERNEL32!CloseHandle` at `0x14000f3bf`
- `KERNEL32!SetLastError` at `0x14000f3da`
- `KERNEL32!SetLastError` at `0x14000f3da`
- `KERNEL32!GetLastError` at `0x14000f321`
- `KERNEL32!GetLastError` at `0x14000f321`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f13b`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f32f`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f13b`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f32f`
- `KERNEL32!DeviceIoControl` at `0x14000f1ec`
- `KERNEL32!DeviceIoControl` at `0x14000f2aa`
- `KERNEL32!DeviceIoControl` at `0x14000f1ec`
- `KERNEL32!DeviceIoControl` at `0x14000f2aa`
- `KERNEL32!CreateFileW` at `0x14000f181`
- `KERNEL32!CreateFileW` at `0x14000f181`

## string_xrefs

- `0x14000f196`: `CreateFile`

## pseudocode

```c
__int64 __fastcall SuResetDrive(struct _SU_DRIVE_OBJECT *a1)
{
  const char *v1; // rsi
  HLOCAL v3; // r14
  HANDLE FileW; // r13
  unsigned int IsDrivePooled; // ebx
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  int v8; // r15d
  DWORD LastError; // r12d
  unsigned int Pool; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  int OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+58h] [rbp-A8h] BYREF
  LARGE_INTEGER v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-98h]
  _BYTE v22[40]; // [rsp+70h] [rbp-90h] BYREF
  __int128 InBuffer; // [rsp+98h] [rbp-68h] BYREF
  WCHAR FileName[32]; // [rsp+B0h] [rbp-50h] BYREF

  v1 = 0;
  BytesReturned = 0;
  v15 = 0;
  InBuffer = 0;
  memset_0(FileName, 0, sizeof(FileName));
  hMem = 0;
  memset(v22, 0, sizeof(v22));
  v3 = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  OutBuffer = 0;
  QueryPerformanceCounter(&PerformanceCount);
  StringCchPrintfW(FileName, 0x20u, (size_t *)L"\\\\.\\PhysicalDrive%d", *((unsigned int *)a1 + 28));
  FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    IsDrivePooled = 0;
    v1 = "CreateFile";
LABEL_23:
    LastError = GetLastError();
    goto LABEL_24;
  }
  if ( *((_DWORD *)a1 + 677) == 4 )
  {
    *(_QWORD *)&InBuffer = 0x1000000010LL;
    *((_QWORD *)&InBuffer + 1) = 0x100000002LL;
    IsDrivePooled = DeviceIoControl(FileW, 0x2DDC9Cu, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0);
    if ( !IsDrivePooled )
    {
      v1 = "DeviceIoControl - IOCTL_STORAGE_ATTRIBUTE_MANAGEMENT";
      goto LABEL_23;
    }
    v6 = *(_OWORD *)((char *)a1 + 40);
    v7 = *(_OWORD *)((char *)a1 + 56);
    *(_DWORD *)v22 = 40;
    *(_OWORD *)&v22[4] = v6;
    v22[36] = 0;
    *(_OWORD *)&v22[20] = v7;
    SiRefreshDrive((struct _SP_REFRESH_INFO *)v22, a1, 1);
  }
  v8 = 0;
  if ( *((_DWORD *)a1 + 715) != 3 && !*((_BYTE *)a1 + 2837) && *((_DWORD *)a1 + 710) == 2 )
  {
    IsDrivePooled = SuIsDrivePooled(FileW, &v15);
    if ( !IsDrivePooled )
    {
      v1 = "SuIsDrivePooled";
      goto LABEL_23;
    }
    LOBYTE(v8) = v15 == 0;
  }
  IsDrivePooled = DeviceIoControl(Spaceport, 0xE7C418u, (char *)a1 + 40, 0x20u, &OutBuffer, 4u, &BytesReturned, 0);
  if ( !IsDrivePooled )
  {
    v1 = "DeviceIoControl - IOCTL_SPACEPORT_RESET_DRIVE";
    goto LABEL_23;
  }
  LastError = 0;
  if ( v8 )
  {
    Pool = SiGetPool((struct _GUID *)((char *)a1 + 40), 0, (struct _SU_POOL_OBJECT **)&hMem);
    v3 = hMem;
    IsDrivePooled = Pool;
    if ( Pool )
    {
      IsDrivePooled = SuPrepareDrive((struct _SP_POOL_INFO *)((char *)hMem + 56), a1);
      if ( IsDrivePooled )
        goto LABEL_24;
      v1 = "SuPrepareDrive";
    }
    else
    {
      v1 = "SuGetPool";
    }
    goto LABEL_23;
  }
  if ( OutBuffer )
  {
    IsDrivePooled = SuUnprepareDrive(a1);
    if ( !IsDrivePooled )
    {
      v1 = "SuUnprepareDrive";
      goto LABEL_23;
    }
  }
LABEL_24:
  QueryPerformanceCounter(&v20);
  if ( IsDrivePooled )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjx_EventWriteTransfer(
        (_DWORD)a1 + 56,
        (unsigned int)ResetDriveSucceeded,
        v12,
        v13,
        (__int64)"SuResetDrive",
        (__int64)a1 + 56,
        1000000 * (v20.QuadPart - PerformanceCount.QuadPart) / v21);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjsq_EventWriteTransfer(
      v11,
      (unsigned int)ResetDriveFailed,
      v12,
      v13,
      (__int64)"SuResetDrive",
      (__int64)a1 + 56,
      (__int64)v1,
      LastError);
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( v3 )
    LocalFree(v3);
  if ( !IsDrivePooled )
    SetLastError(LastError);
  return IsDrivePooled;
}

```

## disassembly

```asm
0x14000f0c4  push    rbp
0x14000f0c6  push    rbx
0x14000f0c7  push    rsi
0x14000f0c8  push    rdi
0x14000f0c9  push    r12
0x14000f0cb  push    r13
0x14000f0cd  push    r14
0x14000f0cf  push    r15
0x14000f0d1  lea     rbp, [rsp-8]
0x14000f0d6  sub     rsp, 108h
0x14000f0dd  mov     rax, cs:__security_cookie
0x14000f0e4  xor     rax, rsp
0x14000f0e7  mov     [rbp+40h+var_50], rax
0x14000f0eb  xor     esi, esi
0x14000f0ed  mov     rdi, rcx
0x14000f0f0  xorps   xmm0, xmm0
0x14000f0f3  mov     [rsp+140h+BytesReturned], esi
0x14000f0f7  xor     edx, edx; Val
0x14000f0f9  mov     [rsp+140h+var_100], esi
0x14000f0fd  lea     rcx, [rbp+40h+FileName]; void *
0x14000f101  lea     r8d, [rsi+40h]; Size
0x14000f105  movups  [rbp+40h+InBuffer], xmm0
0x14000f109  call    memset_0
0x14000f10e  xorps   xmm0, xmm0
0x14000f111  mov     [rsp+140h+hMem], rsi
0x14000f116  xor     eax, eax
0x14000f118  lea     rcx, [rsp+140h+PerformanceCount]; this
0x14000f11d  movups  [rsp+140h+var_D0], xmm0
0x14000f122  mov     [rbp+40h+var_B0], rax
0x14000f126  mov     r14d, esi
0x14000f129  movups  [rbp+40h+var_C0], xmm0
0x14000f12d  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000f132  lea     rcx, [rsp+140h+PerformanceCount]; lpPerformanceCount
0x14000f137  mov     [rsp+140h+OutBuffer], esi
0x14000f13b  call    cs:__imp_QueryPerformanceCounter
0x14000f141  mov     r9d, [rdi+70h]
0x14000f145  lea     r12d, [rsi+20h]
0x14000f149  mov     edx, r12d; unsigned __int64
0x14000f14c  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000f153  lea     rcx, [rbp+40h+FileName]; unsigned __int16 *
0x14000f157  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f15c  mov     [rsp+140h+hTemplateFile], rsi; hTemplateFile
0x14000f161  lea     r8d, [rsi+7]; dwShareMode
0x14000f165  mov     [rsp+140h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000f16d  lea     rcx, [rbp+40h+FileName]; lpFileName
0x14000f171  xor     r9d, r9d; lpSecurityAttributes
0x14000f174  mov     [rsp+140h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f17c  mov     edx, 0C0000000h; dwDesiredAccess
0x14000f181  call    cs:__imp_CreateFileW
0x14000f187  lea     r15d, [rsi+1]
0x14000f18b  mov     r13, rax
0x14000f18e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f192  jnz     short loc_14000F1A2
0x14000f194  mov     ebx, esi
0x14000f196  lea     rsi, aCreatefile; "CreateFile"
0x14000f19d  jmp     loc_14000F321
0x14000f1a2  cmp     dword ptr [rdi+0A94h], 4
0x14000f1a9  jnz     loc_14000F231
0x14000f1af  mov     [rsp+140h+lpOverlapped], rsi; lpOverlapped
0x14000f1b4  lea     rax, [rsp+140h+BytesReturned]
0x14000f1b9  mov     [rsp+140h+hTemplateFile], rax; lpBytesReturned
0x14000f1be  lea     r8, [rbp+40h+InBuffer]; lpInBuffer
0x14000f1c2  mov     r9d, 10h; nInBufferSize
0x14000f1c8  mov     [rsp+140h+dwFlagsAndAttributes], esi; nOutBufferSize
0x14000f1cc  mov     edx, 2DDC9Ch; dwIoControlCode
0x14000f1d1  mov     qword ptr [rsp+140h+dwCreationDisposition], rsi; lpOutBuffer
0x14000f1d6  mov     rcx, r13; hDevice
0x14000f1d9  mov     dword ptr [rbp+40h+InBuffer+4], r9d
0x14000f1dd  mov     dword ptr [rbp+40h+InBuffer], r9d
0x14000f1e1  mov     dword ptr [rbp+40h+InBuffer+8], 2
0x14000f1e8  mov     dword ptr [rbp+40h+InBuffer+0Ch], r15d
0x14000f1ec  call    cs:__imp_DeviceIoControl
0x14000f1f2  mov     ebx, eax
0x14000f1f4  test    eax, eax
0x14000f1f6  jnz     short loc_14000F204
0x14000f1f8  lea     rsi, aDeviceiocontro_8; "DeviceIoControl - IOCTL_STORAGE_ATTRIBU"...
0x14000f1ff  jmp     loc_14000F321
0x14000f204  movups  xmm0, xmmword ptr [rdi+28h]
0x14000f208  mov     r8d, r15d; int
0x14000f20b  mov     rdx, rdi; struct _SU_DRIVE_OBJECT *
0x14000f20e  movups  xmm1, xmmword ptr [rdi+38h]
0x14000f212  lea     rcx, [rsp+140h+var_D0]; struct _SP_REFRESH_INFO *
0x14000f217  mov     dword ptr [rsp+140h+var_D0], 28h ; '('
0x14000f21f  movups  [rsp+140h+var_D0+4], xmm0
0x14000f224  mov     byte ptr [rbp+40h+var_B0+4], sil
0x14000f228  movups  [rbp+40h+var_C0+4], xmm1
0x14000f22c  call    ?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z; SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)
0x14000f231  cmp     dword ptr [rdi+0B2Ch], 3
0x14000f238  mov     r15d, esi
0x14000f23b  jz      short loc_14000F276
0x14000f23d  cmp     [rdi+0B15h], sil
0x14000f244  jnz     short loc_14000F276
0x14000f246  cmp     dword ptr [rdi+0B18h], 2
0x14000f24d  jnz     short loc_14000F276
0x14000f24f  lea     rdx, [rsp+140h+var_100]; int *
0x14000f254  mov     rcx, r13; void *
0x14000f257  call    ?SuIsDrivePooled@@YAHPEAXPEAH@Z; SuIsDrivePooled(void *,int *)
0x14000f25c  mov     ebx, eax
0x14000f25e  test    eax, eax
0x14000f260  jnz     short loc_14000F26E
0x14000f262  lea     rsi, aSuisdrivepoole; "SuIsDrivePooled"
0x14000f269  jmp     loc_14000F321
0x14000f26e  cmp     [rsp+140h+var_100], esi
0x14000f272  setz    r15b
0x14000f276  mov     [rsp+140h+lpOverlapped], rsi; lpOverlapped
0x14000f27b  lea     rcx, [rsp+140h+BytesReturned]
0x14000f280  mov     [rsp+140h+hTemplateFile], rcx; lpBytesReturned
0x14000f285  lea     r8, [rdi+28h]; lpInBuffer
0x14000f289  lea     rcx, [rsp+140h+OutBuffer]
0x14000f28e  mov     [rsp+140h+dwFlagsAndAttributes], 4; nOutBufferSize
0x14000f296  mov     qword ptr [rsp+140h+dwCreationDisposition], rcx; lpOutBuffer
0x14000f29b  mov     r9d, r12d; nInBufferSize
0x14000f29e  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000f2a5  mov     edx, 0E7C418h; dwIoControlCode
0x14000f2aa  call    cs:__imp_DeviceIoControl
0x14000f2b0  mov     ebx, eax
0x14000f2b2  test    eax, eax
0x14000f2b4  jnz     short loc_14000F2BF
0x14000f2b6  lea     rsi, aDeviceiocontro_4; "DeviceIoControl - IOCTL_SPACEPORT_RESET"...
0x14000f2bd  jmp     short loc_14000F321
0x14000f2bf  mov     r12d, esi
0x14000f2c2  test    r15d, r15d
0x14000f2c5  jz      short loc_14000F306
0x14000f2c7  lea     r8, [rsp+140h+hMem]; struct _SU_POOL_OBJECT **
0x14000f2cc  xor     edx, edx; unsigned int
0x14000f2ce  lea     rcx, [rdi+28h]; struct _GUID *
0x14000f2d2  call    ?SiGetPool@@YAHPEAU_GUID@@KPEAPEAU_SU_POOL_OBJECT@@@Z; SiGetPool(_GUID *,ulong,_SU_POOL_OBJECT * *)
0x14000f2d7  mov     r14, [rsp+140h+hMem]
0x14000f2dc  mov     ebx, eax
0x14000f2de  test    eax, eax
0x14000f2e0  jnz     short loc_14000F2EB
0x14000f2e2  lea     rsi, aSugetpool; "SuGetPool"
0x14000f2e9  jmp     short loc_14000F321
0x14000f2eb  lea     rcx, [r14+38h]; struct _SP_POOL_INFO *
0x14000f2ef  mov     rdx, rdi; struct _SU_DRIVE_OBJECT *
0x14000f2f2  call    ?SuPrepareDrive@@YAHPEAU_SP_POOL_INFO@@PEAU_SU_DRIVE_OBJECT@@@Z; SuPrepareDrive(_SP_POOL_INFO *,_SU_DRIVE_OBJECT *)
0x14000f2f7  mov     ebx, eax
0x14000f2f9  test    eax, eax
0x14000f2fb  jnz     short loc_14000F32A
0x14000f2fd  lea     rsi, aSupreparedrive; "SuPrepareDrive"
0x14000f304  jmp     short loc_14000F321
0x14000f306  cmp     [rsp+140h+OutBuffer], esi
0x14000f30a  jz      short loc_14000F32A
0x14000f30c  mov     rcx, rdi; struct _SU_DRIVE_OBJECT *
0x14000f30f  call    ?SuUnprepareDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z; SuUnprepareDrive(_SU_DRIVE_OBJECT *)
0x14000f314  mov     ebx, eax
0x14000f316  test    eax, eax
0x14000f318  jnz     short loc_14000F32A
0x14000f31a  lea     rsi, aSuunpreparedri; "SuUnprepareDrive"
0x14000f321  call    cs:__imp_GetLastError
0x14000f327  mov     r12d, eax
0x14000f32a  lea     rcx, [rsp+140h+var_E0]; lpPerformanceCount
0x14000f32f  call    cs:__imp_QueryPerformanceCounter
0x14000f335  test    ebx, ebx
0x14000f337  jz      short loc_14000F382
0x14000f339  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000f340  jz      short loc_14000F3B6
0x14000f342  mov     rcx, qword ptr [rsp+140h+var_E0]
0x14000f347  sub     rcx, qword ptr [rsp+140h+PerformanceCount]
0x14000f34c  imul    rax, rcx, 0F4240h
0x14000f353  lea     rcx, [rdi+38h]
0x14000f357  cqo
0x14000f359  idiv    [rsp+140h+var_D8]
0x14000f35e  lea     rdx, ResetDriveSucceeded
0x14000f365  mov     [rsp+140h+hTemplateFile], rax
0x14000f36a  lea     rax, aSuresetdrive; "SuResetDrive"
0x14000f371  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rcx
0x14000f376  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x14000f37b  call    McTemplateK0zsjx_EventWriteTransfer
0x14000f380  jmp     short loc_14000F3B6
0x14000f382  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000f389  jz      short loc_14000F3B6
0x14000f38b  mov     dword ptr [rsp+140h+lpOverlapped], r12d
0x14000f390  lea     rax, [rdi+38h]
0x14000f394  mov     [rsp+140h+hTemplateFile], rsi
0x14000f399  lea     rdx, ResetDriveFailed
0x14000f3a0  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x14000f3a5  lea     rax, aSuresetdrive; "SuResetDrive"
0x14000f3ac  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x14000f3b1  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000f3b6  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x14000f3ba  jz      short loc_14000F3C5
0x14000f3bc  mov     rcx, r13; hObject
0x14000f3bf  call    cs:__imp_CloseHandle
0x14000f3c5  test    r14, r14
0x14000f3c8  jz      short loc_14000F3D3
0x14000f3ca  mov     rcx, r14; hMem
0x14000f3cd  call    cs:__imp_LocalFree
0x14000f3d3  test    ebx, ebx
0x14000f3d5  jnz     short loc_14000F3E0
0x14000f3d7  mov     ecx, r12d; dwErrCode
0x14000f3da  call    cs:__imp_SetLastError
0x14000f3e0  mov     eax, ebx
0x14000f3e2  mov     rcx, [rbp+40h+var_50]
0x14000f3e6  xor     rcx, rsp; StackCookie
0x14000f3e9  call    __security_check_cookie
0x14000f3ee  add     rsp, 108h
0x14000f3f5  pop     r15
0x14000f3f7  pop     r14
0x14000f3f9  pop     r13
0x14000f3fb  pop     r12
0x14000f3fd  pop     rdi
0x14000f3fe  pop     rsi
0x14000f3ff  pop     rbx
0x14000f400  pop     rbp
0x14000f401  retn
```
