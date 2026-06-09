# SiSetDriveMaintenance(_GUID *,uchar,ulong,_SU_DRIVE_OBJECT *)

- ea: `0x14000d70c`
- end: `0x14000d9c3`
- name: `?SiSetDriveMaintenance@@YAHPEAU_GUID@@EKPEAU_SU_DRIVE_OBJECT@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(struct _GUID *, char, int, struct _SU_DRIVE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000ce60`

## callees

- `0x140001caf`
- `0x140004114`
- `0x1400081d4`
- `0x14000d70c`
- `0x14000f6f8`
- `0x14000f818`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000d98e`
- `KERNEL32!CloseHandle` at `0x14000d98e`
- `KERNEL32!SetLastError` at `0x14000d79e`
- `KERNEL32!SetLastError` at `0x14000d99b`
- `KERNEL32!SetLastError` at `0x14000d79e`
- `KERNEL32!SetLastError` at `0x14000d99b`
- `KERNEL32!GetLastError` at `0x14000d8ef`
- `KERNEL32!GetLastError` at `0x14000d8ef`
- `KERNEL32!QueryPerformanceCounter` at `0x14000d789`
- `KERNEL32!QueryPerformanceCounter` at `0x14000d8fd`
- `KERNEL32!QueryPerformanceCounter` at `0x14000d789`
- `KERNEL32!QueryPerformanceCounter` at `0x14000d8fd`
- `KERNEL32!DeviceIoControl` at `0x14000d88c`
- `KERNEL32!DeviceIoControl` at `0x14000d8dc`
- `KERNEL32!DeviceIoControl` at `0x14000d88c`
- `KERNEL32!DeviceIoControl` at `0x14000d8dc`
- `KERNEL32!CreateFileW` at `0x14000d844`
- `KERNEL32!CreateFileW` at `0x14000d844`

## string_xrefs

- `0x14000d855`: `CreateFile`

## pseudocode

```c
__int64 __fastcall SiSetDriveMaintenance(struct _GUID *a1, char a2, int a3, struct _SU_DRIVE_OBJECT *a4)
{
  const char *v5; // rdi
  unsigned int v9; // ebx
  __int64 FileW; // rsi
  int v11; // eax
  struct _GUID v12; // xmm0
  DWORD LastError; // r14d
  int v14; // edx
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v21; // [rsp+64h] [rbp-9Ch] BYREF
  struct _GUID *v22; // [rsp+68h] [rbp-98h]
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER v24; // [rsp+78h] [rbp-88h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  _BYTE InBuffer[40]; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v27[3]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[32]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = 0;
  v22 = a1;
  v21 = 0;
  memset(v27, 0, 44);
  memset_0(FileName, 0, sizeof(FileName));
  memset(InBuffer, 0, sizeof(InBuffer));
  SI_TIMER::SI_TIMER((SI_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)a4 + 28) == -1 )
  {
    SetLastError(0x57u);
    v9 = 0;
    FileW = -1;
    v5 = "SP_DRIVE_INFO.DeviceNumber == ULONG_MAX";
  }
  else
  {
    InBuffer[4] = 1;
    *(_QWORD *)&InBuffer[16] = 8;
    LODWORD(v27[0]) = 44;
    *(_DWORD *)InBuffer = 40;
    BYTE4(v27[0]) = a2;
    *(_QWORD *)&InBuffer[8] = a2 != 0 ? 8 : 0;
    *(GUID *)&InBuffer[24] = PARTITION_SPACES_GUID;
    v11 = a3;
    v12 = *a1;
    if ( a3 == -1 )
      v11 = 300;
    DWORD2(v27[0]) = v11;
    *(struct _GUID *)((char *)v27 + 12) = v12;
    StringCchPrintfW(FileName, 0x20u, L"\\\\.\\PhysicalDrive%d");
    FileW = (__int64)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v9 = 0;
      v5 = "CreateFile";
    }
    else
    {
      BytesReturned = 0;
      v9 = DeviceIoControl((HANDLE)FileW, 0x7C0F4u, InBuffer, 0x28u, 0, 0, &BytesReturned, 0);
      if ( v9 )
      {
        LastError = 0;
        *(_OWORD *)((char *)&v27[1] + 12) = *((_OWORD *)a4 + 6);
        v9 = DeviceIoControl(Spaceport, 0xE7C430u, v27, 0x2Cu, 0, 0, &v21, 0);
        if ( v9 )
          goto LABEL_12;
        v5 = "DeviceIoControl - IOCTL_SPACEPORT_SET_MAINTENANCE_DRIVE";
      }
      else
      {
        v5 = "SiSetDiskAttributes";
      }
    }
  }
  LastError = GetLastError();
LABEL_12:
  QueryPerformanceCounter(&v24);
  if ( v9 )
  {
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
      McTemplateK0zsjtqjx_EventWriteTransfer(
        (_DWORD)a4 + 56,
        1000000 * (v24.QuadPart - PerformanceCount.QuadPart) % v25,
        v16,
        v17,
        dwCreationDisposition,
        (__int64)v22,
        a2,
        a3,
        (__int64)a4 + 56,
        1000000 * (v24.QuadPart - PerformanceCount.QuadPart) / v25);
  }
  else if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    McTemplateK0zsjtqjsq_EventWriteTransfer(
      v15,
      v14,
      v16,
      v17,
      dwCreationDisposition,
      (__int64)v22,
      a2,
      a3,
      (__int64)a4 + 56,
      (__int64)v5,
      LastError);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( !v9 )
    SetLastError(LastError);
  return v9;
}

```

## disassembly

```asm
0x14000d70c  push    rbp
0x14000d70e  push    rbx
0x14000d70f  push    rsi
0x14000d710  push    rdi
0x14000d711  push    r12
0x14000d713  push    r13
0x14000d715  push    r14
0x14000d717  push    r15
0x14000d719  lea     rbp, [rsp-38h]
0x14000d71e  sub     rsp, 138h
0x14000d725  mov     rax, cs:__security_cookie
0x14000d72c  xor     rax, rsp
0x14000d72f  mov     [rbp+70h+var_50], rax
0x14000d733  xorps   xmm0, xmm0
0x14000d736  movzx   r12d, dl
0x14000d73a  xor     edi, edi
0x14000d73c  mov     [rsp+170h+var_108], rcx
0x14000d741  mov     r13d, r8d
0x14000d744  mov     [rsp+170h+var_10C], edi
0x14000d748  mov     rbx, rcx
0x14000d74b  xor     edx, edx; Val
0x14000d74d  movups  [rbp+70h+var_B0], xmm0
0x14000d751  lea     r8d, [rdi+40h]; Size
0x14000d755  mov     r15, r9
0x14000d758  lea     rcx, [rbp+70h+FileName]; void *
0x14000d75c  movups  [rbp+70h+var_C0], xmm0
0x14000d760  movups  [rbp+70h+var_B0+0Ch], xmm0
0x14000d764  call    memset_0
0x14000d769  xorps   xmm0, xmm0
0x14000d76c  lea     rcx, [rsp+170h+PerformanceCount]; this
0x14000d771  xor     eax, eax
0x14000d773  movups  [rbp+70h+InBuffer], xmm0
0x14000d777  mov     [rbp+70h+var_C8], rax
0x14000d77b  movups  [rbp+70h+var_D8], xmm0
0x14000d77f  call    ??0SI_TIMER@@QEAA@XZ; SI_TIMER::SI_TIMER(void)
0x14000d784  lea     rcx, [rsp+170h+PerformanceCount]; lpPerformanceCount
0x14000d789  call    cs:__imp_QueryPerformanceCounter
0x14000d78f  mov     r9d, [r15+70h]
0x14000d793  or      edx, 0FFFFFFFFh
0x14000d796  cmp     r9d, edx
0x14000d799  jnz     short loc_14000D7B6
0x14000d79b  lea     ecx, [rdi+57h]; dwErrCode
0x14000d79e  call    cs:__imp_SetLastError
0x14000d7a4  mov     ebx, edi
0x14000d7a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d7aa  lea     rdi, aSpDriveInfoDev; "SP_DRIVE_INFO.DeviceNumber == ULONG_MAX"
0x14000d7b1  jmp     loc_14000D8EF
0x14000d7b6  movups  xmm0, xmmword ptr cs:PARTITION_SPACES_GUID.Data1
0x14000d7bd  mov     al, r12b
0x14000d7c0  mov     byte ptr [rbp+70h+InBuffer+4], 1
0x14000d7c4  neg     al
0x14000d7c6  mov     qword ptr [rbp+70h+var_D8], 8
0x14000d7ce  mov     r14d, 28h ; '('
0x14000d7d4  mov     dword ptr [rbp+70h+var_C0], 2Ch ; ','
0x14000d7db  sbb     rcx, rcx
0x14000d7de  mov     dword ptr [rbp+70h+InBuffer], r14d
0x14000d7e2  and     ecx, 8
0x14000d7e5  mov     byte ptr [rbp+70h+var_C0+4], r12b
0x14000d7e9  mov     qword ptr [rbp+70h+InBuffer+8], rcx
0x14000d7ed  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000d7f4  cmp     r13d, edx
0x14000d7f7  mov     ecx, 12Ch
0x14000d7fc  movdqu  [rbp+70h+var_D8+8], xmm0
0x14000d801  mov     eax, r13d
0x14000d804  lea     edx, [r14-8]; unsigned __int64
0x14000d808  movups  xmm0, xmmword ptr [rbx]
0x14000d80b  cmovz   eax, ecx
0x14000d80e  lea     rcx, [rbp+70h+FileName]; unsigned __int16 *
0x14000d812  mov     dword ptr [rbp+70h+var_C0+8], eax
0x14000d815  movdqu  [rbp+70h+var_C0+0Ch], xmm0
0x14000d81a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000d81f  mov     [rsp+170h+hTemplateFile], rdi; hTemplateFile
0x14000d824  lea     r8d, [r14-21h]; dwShareMode
0x14000d828  mov     [rsp+170h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000d830  lea     rcx, [rbp+70h+FileName]; lpFileName
0x14000d834  xor     r9d, r9d; lpSecurityAttributes
0x14000d837  mov     [rsp+170h+dwCreationDisposition], 3; dwCreationDisposition
0x14000d83f  mov     edx, 0C0000000h; dwDesiredAccess
0x14000d844  call    cs:__imp_CreateFileW
0x14000d84a  mov     rsi, rax
0x14000d84d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000d851  jnz     short loc_14000D861
0x14000d853  mov     ebx, edi
0x14000d855  lea     rdi, aCreatefile; "CreateFile"
0x14000d85c  jmp     loc_14000D8EF
0x14000d861  mov     [rsp+170h+lpOverlapped], rdi; lpOverlapped
0x14000d866  lea     rax, [rsp+170h+BytesReturned]
0x14000d86b  mov     [rsp+170h+hTemplateFile], rax; lpBytesReturned
0x14000d870  lea     r8, [rbp+70h+InBuffer]; lpInBuffer
0x14000d874  mov     [rsp+170h+dwFlagsAndAttributes], edi; nOutBufferSize
0x14000d878  mov     r9d, r14d; nInBufferSize
0x14000d87b  mov     edx, 7C0F4h; dwIoControlCode
0x14000d880  mov     qword ptr [rsp+170h+dwCreationDisposition], rdi; lpOutBuffer
0x14000d885  mov     rcx, rsi; hDevice
0x14000d888  mov     [rsp+170h+BytesReturned], edi
0x14000d88c  call    cs:__imp_DeviceIoControl
0x14000d892  mov     ebx, eax
0x14000d894  test    eax, eax
0x14000d896  jnz     short loc_14000D8A1
0x14000d898  lea     rdi, aSisetdiskattri; "SiSetDiskAttributes"
0x14000d89f  jmp     short loc_14000D8EF
0x14000d8a1  movups  xmm0, xmmword ptr [r15+60h]
0x14000d8a6  xor     ecx, ecx
0x14000d8a8  lea     rax, [rsp+170h+var_10C]
0x14000d8ad  mov     [rsp+170h+lpOverlapped], rcx; lpOverlapped
0x14000d8b2  lea     r8, [rbp+70h+var_C0]; lpInBuffer
0x14000d8b6  mov     [rsp+170h+hTemplateFile], rax; lpBytesReturned
0x14000d8bb  mov     edx, 0E7C430h; dwIoControlCode
0x14000d8c0  mov     [rsp+170h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x14000d8c4  mov     r14d, edi
0x14000d8c7  mov     qword ptr [rsp+170h+dwCreationDisposition], rcx; lpOutBuffer
0x14000d8cc  lea     r9d, [rcx+2Ch]; nInBufferSize
0x14000d8d0  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000d8d7  movdqu  [rbp+70h+var_B0+0Ch], xmm0
0x14000d8dc  call    cs:__imp_DeviceIoControl
0x14000d8e2  mov     ebx, eax
0x14000d8e4  test    eax, eax
0x14000d8e6  jnz     short loc_14000D8F8
0x14000d8e8  lea     rdi, aDeviceiocontro_5; "DeviceIoControl - IOCTL_SPACEPORT_SET_M"...
0x14000d8ef  call    cs:__imp_GetLastError
0x14000d8f5  mov     r14d, eax
0x14000d8f8  lea     rcx, [rsp+170h+var_F8]; lpPerformanceCount
0x14000d8fd  call    cs:__imp_QueryPerformanceCounter
0x14000d903  test    ebx, ebx
0x14000d905  jz      short loc_14000D950
0x14000d907  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000d90e  jz      short loc_14000D985
0x14000d910  mov     rcx, qword ptr [rsp+170h+var_F8]
0x14000d915  sub     rcx, qword ptr [rsp+170h+PerformanceCount]
0x14000d91a  imul    rax, rcx, 0F4240h
0x14000d921  lea     rcx, [r15+38h]
0x14000d925  cqo
0x14000d927  idiv    [rbp+70h+var_F0]
0x14000d92b  mov     [rsp+170h+var_128], rax
0x14000d930  mov     rax, [rsp+170h+var_108]
0x14000d935  mov     [rsp+170h+var_130], rcx
0x14000d93a  mov     dword ptr [rsp+170h+lpOverlapped], r13d
0x14000d93f  mov     dword ptr [rsp+170h+hTemplateFile], r12d
0x14000d944  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], rax
0x14000d949  call    McTemplateK0zsjtqjx_EventWriteTransfer
0x14000d94e  jmp     short loc_14000D985
0x14000d950  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x14000d957  jz      short loc_14000D985
0x14000d959  mov     [rsp+170h+var_120], r14d
0x14000d95e  lea     rax, [r15+38h]
0x14000d962  mov     [rsp+170h+var_128], rdi
0x14000d967  mov     [rsp+170h+var_130], rax
0x14000d96c  mov     rax, [rsp+170h+var_108]
0x14000d971  mov     dword ptr [rsp+170h+lpOverlapped], r13d
0x14000d976  mov     dword ptr [rsp+170h+hTemplateFile], r12d
0x14000d97b  mov     qword ptr [rsp+170h+dwFlagsAndAttributes], rax
0x14000d980  call    McTemplateK0zsjtqjsq_EventWriteTransfer
0x14000d985  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000d989  jz      short loc_14000D994
0x14000d98b  mov     rcx, rsi; hObject
0x14000d98e  call    cs:__imp_CloseHandle
0x14000d994  test    ebx, ebx
0x14000d996  jnz     short loc_14000D9A1
0x14000d998  mov     ecx, r14d; dwErrCode
0x14000d99b  call    cs:__imp_SetLastError
0x14000d9a1  mov     eax, ebx
0x14000d9a3  mov     rcx, [rbp+70h+var_50]
0x14000d9a7  xor     rcx, rsp; StackCookie
0x14000d9aa  call    __security_check_cookie
0x14000d9af  add     rsp, 138h
0x14000d9b6  pop     r15
0x14000d9b8  pop     r14
0x14000d9ba  pop     r13
0x14000d9bc  pop     r12
0x14000d9be  pop     rdi
0x14000d9bf  pop     rsi
0x14000d9c0  pop     rbx
0x14000d9c1  pop     rbp
0x14000d9c2  retn
```
