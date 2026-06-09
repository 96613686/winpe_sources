# SuUnprepareDrive(_SU_DRIVE_OBJECT *)

- ea: `0x14000f450`
- end: `0x14000f6f2`
- name: `?SuUnprepareDrive@@YAHPEAU_SU_DRIVE_OBJECT@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(struct _SU_DRIVE_OBJECT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000da40`
- `0x14000f0c4`

## callees

- `0x140001caf`
- `0x140004114`
- `0x1400081d4`
- `0x14000b828`
- `0x14000b934`
- `0x14000cf3c`
- `0x14000f450`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000f6b5`
- `KERNEL32!CloseHandle` at `0x14000f6b5`
- `KERNEL32!SetLastError` at `0x14000f6c2`
- `KERNEL32!SetLastError` at `0x14000f6c2`
- `KERNEL32!GetLastError` at `0x14000f529`
- `KERNEL32!GetLastError` at `0x14000f57e`
- `KERNEL32!GetLastError` at `0x14000f529`
- `KERNEL32!GetLastError` at `0x14000f57e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f4cd`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f627`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f4cd`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f627`
- `KERNEL32!DeviceIoControl` at `0x14000f56b`
- `KERNEL32!DeviceIoControl` at `0x14000f5df`
- `KERNEL32!DeviceIoControl` at `0x14000f56b`
- `KERNEL32!DeviceIoControl` at `0x14000f5df`
- `KERNEL32!CreateFileW` at `0x14000f51a`
- `KERNEL32!CreateFileW` at `0x14000f51a`

## string_xrefs

- `0x14000f53b`: `CreateFile`
- `0x14000f577`: `DeviceIoControl - IOCTL_DISK_DELETE_SPACES_METADATA`

## pseudocode

```c
__int64 __fastcall SuUnprepareDrive(struct _SU_DRIVE_OBJECT *a1)
{
  const char *v2; // rsi
  DWORD LastError; // r14d
  __int64 FileW; // rdi
  unsigned int v5; // ebx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  DWORD BytesReturned; // [rsp+40h] [rbp-89h] BYREF
  DWORD v11; // [rsp+44h] [rbp-85h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-81h] BYREF
  LARGE_INTEGER v13; // [rsp+50h] [rbp-79h] BYREF
  __int64 v14; // [rsp+58h] [rbp-71h]
  int v15; // [rsp+60h] [rbp-69h] BYREF
  GUID v16; // [rsp+64h] [rbp-65h]
  __int128 v17; // [rsp+74h] [rbp-55h]
  char v18; // [rsp+84h] [rbp-45h]
  __int16 v19; // [rsp+85h] [rbp-44h]
  char v20; // [rsp+87h] [rbp-42h]
  _BYTE InBuffer[40]; // [rsp+88h] [rbp-41h] BYREF
  WCHAR FileName[32]; // [rsp+B0h] [rbp-19h] BYREF

  BytesReturned = 0;
  v2 = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  LastError = 0;
  memset_0(FileName, 0, sizeof(FileName));
  v19 = 0;
  v20 = 0;
  v17 = 0;
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)a1 + 28) == -1 )
  {
    FileW = -1;
LABEL_10:
    v5 = 1;
    goto LABEL_11;
  }
  StringCchPrintfW(FileName, 0x20u, (size_t *)L"\\\\.\\PhysicalDrive%d");
  FileW = (__int64)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == -1 )
  {
    if ( GetLastError() != 2 )
    {
      v5 = 0;
      v2 = "CreateFile";
LABEL_7:
      LastError = GetLastError();
      goto LABEL_11;
    }
    goto LABEL_10;
  }
  v5 = DeviceIoControl((HANDLE)FileW, 0x70C024u, 0, 0, 0, 0, &BytesReturned, 0);
  if ( !v5 )
  {
    v2 = "DeviceIoControl - IOCTL_DISK_DELETE_SPACES_METADATA";
    goto LABEL_7;
  }
  *(_DWORD *)InBuffer = 40;
  *(GUID *)&InBuffer[24] = PARTITION_SPACES_GUID;
  InBuffer[5] = 1;
  *(_QWORD *)&InBuffer[8] = 0;
  *(_QWORD *)&InBuffer[16] = 12;
  v11 = 0;
  DeviceIoControl((HANDLE)FileW, 0x7C0F4u, InBuffer, 0x28u, 0, 0, &v11, 0);
  v15 = 40;
  v18 = 0;
  v16 = GUID_NULL;
  v17 = *(_OWORD *)((char *)a1 + 56);
  SiRefreshDrive((struct _SP_REFRESH_INFO *)&v15, a1, 1);
LABEL_11:
  QueryPerformanceCounter(&v13);
  if ( v5 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjx_EventWriteTransfer(
        (_DWORD)a1 + 56,
        (unsigned int)UnprepareDriveSucceeded,
        v7,
        v8,
        (__int64)"SuUnprepareDrive",
        (__int64)a1 + 56,
        1000000 * (v13.QuadPart - PerformanceCount.QuadPart) / v14);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjsq_EventWriteTransfer(
      v6,
      (unsigned int)UnprepareDriveFailed,
      v7,
      v8,
      (__int64)"SuUnprepareDrive",
      (__int64)a1 + 56,
      (__int64)v2,
      LastError);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( !v5 )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x14000f450  mov     [rsp-8+arg_8], rbx
0x14000f455  mov     [rsp-8+arg_10], rsi
0x14000f45a  push    rbp
0x14000f45b  push    rdi
0x14000f45c  push    r13
0x14000f45e  push    r14
0x14000f460  push    r15
0x14000f462  lea     rbp, [rsp-37h]
0x14000f467  sub     rsp, 100h
0x14000f46e  mov     rax, cs:__security_cookie
0x14000f475  xor     rax, rsp
0x14000f478  mov     [rbp+57h+var_30], rax
0x14000f47c  xor     eax, eax
0x14000f47e  xorps   xmm0, xmm0
0x14000f481  xor     r13d, r13d
0x14000f484  mov     [rbp+57h+var_78], rax
0x14000f488  mov     r15, rcx
0x14000f48b  mov     [rsp+120h+BytesReturned], r13d
0x14000f490  xor     edx, edx; Val
0x14000f492  lea     rcx, [rbp+57h+FileName]; void *
0x14000f496  lea     r8d, [rax+40h]; Size
0x14000f49a  mov     esi, r13d
0x14000f49d  movups  [rbp+57h+InBuffer], xmm0
0x14000f4a1  mov     r14d, r13d
0x14000f4a4  movups  [rbp+57h+var_88], xmm0
0x14000f4a8  call    memset_0
0x14000f4ad  xorps   xmm0, xmm0
0x14000f4b0  mov     [rbp+57h+var_9B], r13w
0x14000f4b5  lea     rcx, [rsp+120h+PerformanceCount]; this
0x14000f4ba  mov     [rbp+57h+var_99], r13b
0x14000f4be  movdqu  [rbp+57h+var_AC], xmm0
0x14000f4c3  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000f4c8  lea     rcx, [rsp+120h+PerformanceCount]; lpPerformanceCount
0x14000f4cd  call    cs:__imp_QueryPerformanceCounter
0x14000f4d3  mov     r9d, [r15+70h]
0x14000f4d7  cmp     r9d, 0FFFFFFFFh
0x14000f4db  jz      loc_14000F61A
0x14000f4e1  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000f4e8  lea     edx, [r13+20h]; unsigned __int64
0x14000f4ec  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x14000f4f0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000f4f5  mov     [rsp+120h+hTemplateFile], r13; hTemplateFile
0x14000f4fa  lea     r8d, [r13+7]; dwShareMode
0x14000f4fe  mov     [rsp+120h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000f506  lea     rcx, [rbp+57h+FileName]; lpFileName
0x14000f50a  xor     r9d, r9d; lpSecurityAttributes
0x14000f50d  mov     [rsp+120h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f515  mov     edx, 0C0000000h; dwDesiredAccess
0x14000f51a  call    cs:__imp_CreateFileW
0x14000f520  mov     rdi, rax
0x14000f523  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000f527  jnz     short loc_14000F544
0x14000f529  call    cs:__imp_GetLastError
0x14000f52f  cmp     eax, 2
0x14000f532  jz      loc_14000F61E
0x14000f538  mov     ebx, r13d
0x14000f53b  lea     rsi, aCreatefile; "CreateFile"
0x14000f542  jmp     short loc_14000F57E
0x14000f544  mov     [rsp+120h+lpOverlapped], r13; lpOverlapped
0x14000f549  lea     rax, [rsp+120h+BytesReturned]
0x14000f54e  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x14000f553  xor     r9d, r9d; nInBufferSize
0x14000f556  mov     [rsp+120h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x14000f55b  xor     r8d, r8d; lpInBuffer
0x14000f55e  mov     edx, 70C024h; dwIoControlCode
0x14000f563  mov     qword ptr [rsp+120h+dwCreationDisposition], r13; lpOutBuffer
0x14000f568  mov     rcx, rdi; hDevice
0x14000f56b  call    cs:__imp_DeviceIoControl
0x14000f571  mov     ebx, eax
0x14000f573  test    eax, eax
0x14000f575  jnz     short loc_14000F58C
0x14000f577  lea     rsi, aDeviceiocontro; "DeviceIoControl - IOCTL_DISK_DELETE_SPA"...
0x14000f57e  call    cs:__imp_GetLastError
0x14000f584  mov     r14d, eax
0x14000f587  jmp     loc_14000F623
0x14000f58c  movups  xmm0, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000f593  mov     [rsp+120h+lpOverlapped], r13; lpOverlapped
0x14000f598  lea     rax, [rsp+120h+var_DC]
0x14000f59d  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x14000f5a2  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14000f5a6  mov     [rsp+120h+dwFlagsAndAttributes], r13d; nOutBufferSize
0x14000f5ab  mov     r9d, 28h ; '('; nInBufferSize
0x14000f5b1  mov     edx, 7C0F4h; dwIoControlCode
0x14000f5b6  mov     qword ptr [rsp+120h+dwCreationDisposition], r13; lpOutBuffer
0x14000f5bb  mov     rcx, rdi; hDevice
0x14000f5be  mov     dword ptr [rbp+57h+InBuffer], 28h ; '('
0x14000f5c5  movdqu  [rbp+57h+var_88+8], xmm0
0x14000f5ca  mov     byte ptr [rbp+57h+InBuffer+5], 1
0x14000f5ce  mov     qword ptr [rbp+57h+InBuffer+8], r13
0x14000f5d2  mov     qword ptr [rbp+57h+var_88], 0Ch
0x14000f5da  mov     [rsp+120h+var_DC], r13d
0x14000f5df  call    cs:__imp_DeviceIoControl
0x14000f5e5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14000f5ec  mov     r8d, 1; int
0x14000f5f2  mov     [rbp+57h+var_C0], 28h ; '('
0x14000f5f9  mov     rdx, r15; struct _SU_DRIVE_OBJECT *
0x14000f5fc  mov     [rbp+57h+var_9C], r13b
0x14000f600  movdqu  [rbp+57h+var_BC], xmm0
0x14000f605  lea     rcx, [rbp+57h+var_C0]; struct _SP_REFRESH_INFO *
0x14000f609  movups  xmm0, xmmword ptr [r15+38h]
0x14000f60e  movdqu  [rbp+57h+var_AC], xmm0
0x14000f613  call    ?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z; SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)
0x14000f618  jmp     short loc_14000F623
0x14000f61a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000f61e  mov     ebx, 1
0x14000f623  lea     rcx, [rbp+57h+var_D0]; lpPerformanceCount
0x14000f627  call    cs:__imp_QueryPerformanceCounter
0x14000f62d  test    ebx, ebx
0x14000f62f  jz      short loc_14000F678
0x14000f631  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000f638  jz      short loc_14000F6AC
0x14000f63a  mov     rax, qword ptr [rbp+57h+var_D0]
0x14000f63e  lea     rcx, [r15+38h]
0x14000f642  sub     rax, qword ptr [rsp+120h+PerformanceCount]
0x14000f647  imul    rax, 0F4240h
0x14000f64e  cqo
0x14000f650  idiv    [rbp+57h+var_C8]
0x14000f654  lea     rdx, UnprepareDriveSucceeded
0x14000f65b  mov     [rsp+120h+hTemplateFile], rax
0x14000f660  lea     rax, aSuunpreparedri; "SuUnprepareDrive"
0x14000f667  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rcx
0x14000f66c  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x14000f671  call    McTemplateK0zsjx_EventWriteTransfer
0x14000f676  jmp     short loc_14000F6AC
0x14000f678  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000f67f  jz      short loc_14000F6AC
0x14000f681  mov     dword ptr [rsp+120h+lpOverlapped], r14d
0x14000f686  lea     rax, [r15+38h]
0x14000f68a  mov     [rsp+120h+hTemplateFile], rsi
0x14000f68f  lea     rdx, UnprepareDriveFailed
0x14000f696  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rax
0x14000f69b  lea     rax, aSuunpreparedri; "SuUnprepareDrive"
0x14000f6a2  mov     qword ptr [rsp+120h+dwCreationDisposition], rax
0x14000f6a7  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000f6ac  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000f6b0  jz      short loc_14000F6BB
0x14000f6b2  mov     rcx, rdi; hObject
0x14000f6b5  call    cs:__imp_CloseHandle
0x14000f6bb  test    ebx, ebx
0x14000f6bd  jnz     short loc_14000F6C8
0x14000f6bf  mov     ecx, r14d; dwErrCode
0x14000f6c2  call    cs:__imp_SetLastError
0x14000f6c8  mov     eax, ebx
0x14000f6ca  mov     rcx, [rbp+57h+var_30]
0x14000f6ce  xor     rcx, rsp; StackCookie
0x14000f6d1  call    __security_check_cookie
0x14000f6d6  lea     r11, [rsp+120h+var_20]
0x14000f6de  mov     rbx, [r11+38h]
0x14000f6e2  mov     rsi, [r11+40h]
0x14000f6e6  mov     rsp, r11
0x14000f6e9  pop     r15
0x14000f6eb  pop     r14
0x14000f6ed  pop     r13
0x14000f6ef  pop     rdi
0x14000f6f0  pop     rbp
0x14000f6f1  retn
```
