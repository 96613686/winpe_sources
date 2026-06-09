# SiRefreshDrive(_SP_REFRESH_INFO *,_SU_DRIVE_OBJECT *,int)

- ea: `0x14000cf3c`
- end: `0x14000d155`
- name: `?SiRefreshDrive@@YAHPEAU_SP_REFRESH_INFO@@PEAU_SU_DRIVE_OBJECT@@H@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct _SP_REFRESH_INFO *, struct _SU_DRIVE_OBJECT *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140004d10`
- `0x14000d15c`
- `0x14000f0c4`
- `0x14000f450`

## callees

- `0x140001caf`
- `0x1400081d4`
- `0x14000b828`
- `0x14000cf3c`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000d11d`
- `KERNEL32!CloseHandle` at `0x14000d11d`
- `KERNEL32!SetLastError` at `0x14000d0c4`
- `KERNEL32!SetLastError` at `0x14000d12a`
- `KERNEL32!SetLastError` at `0x14000d0c4`
- `KERNEL32!SetLastError` at `0x14000d12a`
- `KERNEL32!GetLastError` at `0x14000d09f`
- `KERNEL32!GetLastError` at `0x14000d0ac`
- `KERNEL32!GetLastError` at `0x14000d0b7`
- `KERNEL32!GetLastError` at `0x14000d0d8`
- `KERNEL32!GetLastError` at `0x14000d09f`
- `KERNEL32!GetLastError` at `0x14000d0ac`
- `KERNEL32!GetLastError` at `0x14000d0b7`
- `KERNEL32!GetLastError` at `0x14000d0d8`
- `KERNEL32!DeviceIoControl` at `0x14000d047`
- `KERNEL32!DeviceIoControl` at `0x14000d08f`
- `KERNEL32!DeviceIoControl` at `0x14000d047`
- `KERNEL32!DeviceIoControl` at `0x14000d08f`
- `KERNEL32!CreateFileW` at `0x14000cff2`
- `KERNEL32!CreateFileW` at `0x14000cff2`

## string_xrefs

- `0x14000d003`: `CreateFile`
- `0x14000d053`: `SiUpdateProperties`

## pseudocode

```c
__int64 __fastcall SiRefreshDrive(struct _SP_REFRESH_INFO *a1, struct _SU_DRIVE_OBJECT *a2, int a3)
{
  __int64 FileW; // rsi
  __int128 v7; // xmm1
  unsigned int v8; // ebx
  const char *v9; // rdi
  DWORD v10; // r14d
  DWORD LastError; // eax
  int v12; // r8d
  int v13; // r9d
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  DWORD v16; // [rsp+44h] [rbp-45h] BYREF
  _OWORD InBuffer[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v18; // [rsp+68h] [rbp-21h]
  WCHAR FileName[32]; // [rsp+70h] [rbp-19h] BYREF

  v16 = 0;
  FileW = -1;
  memset_0(FileName, 0, sizeof(FileName));
  v7 = *((_OWORD *)a1 + 1);
  InBuffer[0] = *(_OWORD *)a1;
  v18 = *((_QWORD *)a1 + 4);
  InBuffer[1] = v7;
  if ( BYTE4(v18) && *((_DWORD *)a2 + 28) != -1 )
  {
    StringCchPrintfW(FileName, 0x20u, L"\\\\.\\PhysicalDrive%d");
    FileW = (__int64)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v8 = 0;
      v9 = "CreateFile";
      goto LABEL_15;
    }
    BytesReturned = 0;
    v8 = DeviceIoControl((HANDLE)FileW, 0x70140u, 0, 0, 0, 0, &BytesReturned, 0);
    if ( !v8 )
    {
      v9 = "SiUpdateProperties";
      goto LABEL_15;
    }
    BYTE4(v18) = 0;
  }
  v10 = 0;
  v8 = DeviceIoControl(Spaceport, 0xE7041Cu, InBuffer, InBuffer[0], 0, 0, &v16, 0);
  if ( v8 )
    goto LABEL_17;
  if ( !a3 && (GetLastError() == 1167 || GetLastError() == 55 || GetLastError() == 2) )
  {
    SetLastError(0);
    v8 = 1;
    goto LABEL_17;
  }
  v9 = "DeviceIoControl - IOCTL_SPACEPORT_REFRESH_DRIVE";
LABEL_15:
  LastError = GetLastError();
  v10 = LastError;
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 2) != 0 )
    McTemplateK0zsjsq_EventWriteTransfer(
      (_DWORD)a2 + 56,
      (unsigned int)RefreshDriveFailed,
      v12,
      v13,
      (__int64)"SiRefreshDrive",
      (__int64)a2 + 56,
      (__int64)v9,
      LastError);
LABEL_17:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( !v8 )
    SetLastError(v10);
  return v8;
}

```

## disassembly

```asm
0x14000cf3c  mov     [rsp-8+arg_10], rbx
0x14000cf41  push    rbp
0x14000cf42  push    rsi
0x14000cf43  push    rdi
0x14000cf44  push    r14
0x14000cf46  push    r15
0x14000cf48  lea     rbp, [rsp-37h]
0x14000cf4d  sub     rsp, 0C0h
0x14000cf54  mov     rax, cs:__security_cookie
0x14000cf5b  xor     rax, rsp
0x14000cf5e  mov     [rbp+57h+var_30], rax
0x14000cf62  mov     edi, r8d
0x14000cf65  mov     [rbp+57h+var_9C], 0
0x14000cf6c  mov     r15, rdx
0x14000cf6f  mov     rbx, rcx
0x14000cf72  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000cf76  lea     rcx, [rbp+57h+FileName]; void *
0x14000cf7a  xor     edx, edx; Val
0x14000cf7c  lea     r8d, [rsi+41h]; Size
0x14000cf80  call    memset_0
0x14000cf85  movups  xmm0, xmmword ptr [rbx]
0x14000cf88  movups  xmm1, xmmword ptr [rbx+10h]
0x14000cf8c  movups  [rbp+57h+InBuffer], xmm0
0x14000cf90  movsd   xmm0, qword ptr [rbx+20h]
0x14000cf95  movsd   [rbp+57h+var_78], xmm0
0x14000cf9a  cmp     byte ptr [rbp+57h+var_78+4], 0
0x14000cf9e  movups  [rbp+57h+var_88], xmm1
0x14000cfa2  jz      loc_14000D060
0x14000cfa8  mov     r9d, [r15+70h]
0x14000cfac  cmp     r9d, 0FFFFFFFFh
0x14000cfb0  jz      loc_14000D060
0x14000cfb6  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000cfbd  lea     edx, [rsi+21h]; unsigned __int64
0x14000cfc0  lea     rcx, [rbp+57h+FileName]; unsigned __int16 *
0x14000cfc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000cfc9  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x14000cfd2  lea     r8d, [rsi+8]; dwShareMode
0x14000cfd6  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000cfde  lea     rcx, [rbp+57h+FileName]; lpFileName
0x14000cfe2  xor     r9d, r9d; lpSecurityAttributes
0x14000cfe5  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x14000cfed  mov     edx, 0C0000000h; dwDesiredAccess
0x14000cff2  call    cs:__imp_CreateFileW
0x14000cff8  mov     rsi, rax
0x14000cffb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000cfff  jnz     short loc_14000D00F
0x14000d001  xor     ebx, ebx
0x14000d003  lea     rdi, aCreatefile; "CreateFile"
0x14000d00a  jmp     loc_14000D0D8
0x14000d00f  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x14000d018  lea     rax, [rbp+57h+BytesReturned]
0x14000d01c  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x14000d021  xor     r9d, r9d; nInBufferSize
0x14000d024  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14000d02c  xor     r8d, r8d; lpInBuffer
0x14000d02f  mov     edx, 70140h; dwIoControlCode
0x14000d034  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOutBuffer
0x14000d03d  mov     rcx, rsi; hDevice
0x14000d040  mov     [rbp+57h+BytesReturned], 0
0x14000d047  call    cs:__imp_DeviceIoControl
0x14000d04d  mov     ebx, eax
0x14000d04f  test    eax, eax
0x14000d051  jnz     short loc_14000D05C
0x14000d053  lea     rdi, aSiupdateproper; "SiUpdateProperties"
0x14000d05a  jmp     short loc_14000D0D8
0x14000d05c  mov     byte ptr [rbp+57h+var_78+4], 0
0x14000d060  mov     r9d, dword ptr [rbp+57h+InBuffer]; nInBufferSize
0x14000d064  lea     rax, [rbp+57h+var_9C]
0x14000d068  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x14000d06f  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14000d073  xor     r14d, r14d
0x14000d076  mov     edx, 0E7041Ch; dwIoControlCode
0x14000d07b  mov     [rsp+0E0h+lpOverlapped], r14; lpOverlapped
0x14000d080  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x14000d085  mov     [rsp+0E0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x14000d08a  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r14; lpOutBuffer
0x14000d08f  call    cs:__imp_DeviceIoControl
0x14000d095  mov     ebx, eax
0x14000d097  test    eax, eax
0x14000d099  jnz     short loc_14000D114
0x14000d09b  test    edi, edi
0x14000d09d  jnz     short loc_14000D0D1
0x14000d09f  call    cs:__imp_GetLastError
0x14000d0a5  cmp     eax, 48Fh
0x14000d0aa  jz      short loc_14000D0C2
0x14000d0ac  call    cs:__imp_GetLastError
0x14000d0b2  cmp     eax, 37h ; '7'
0x14000d0b5  jz      short loc_14000D0C2
0x14000d0b7  call    cs:__imp_GetLastError
0x14000d0bd  cmp     eax, 2
0x14000d0c0  jnz     short loc_14000D0D1
0x14000d0c2  xor     ecx, ecx; dwErrCode
0x14000d0c4  call    cs:__imp_SetLastError
0x14000d0ca  mov     ebx, 1
0x14000d0cf  jmp     short loc_14000D114
0x14000d0d1  lea     rdi, aDeviceiocontro_0; "DeviceIoControl - IOCTL_SPACEPORT_REFRE"...
0x14000d0d8  call    cs:__imp_GetLastError
0x14000d0de  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 2
0x14000d0e5  mov     r14d, eax
0x14000d0e8  jz      short loc_14000D114
0x14000d0ea  mov     dword ptr [rsp+0E0h+lpOverlapped], eax
0x14000d0ee  lea     rcx, [r15+38h]
0x14000d0f2  mov     [rsp+0E0h+hTemplateFile], rdi
0x14000d0f7  lea     rax, aSirefreshdrive; "SiRefreshDrive"
0x14000d0fe  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x14000d103  lea     rdx, RefreshDriveFailed
0x14000d10a  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax
0x14000d10f  call    McTemplateK0zsjsq_EventWriteTransfer
0x14000d114  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000d118  jz      short loc_14000D123
0x14000d11a  mov     rcx, rsi; hObject
0x14000d11d  call    cs:__imp_CloseHandle
0x14000d123  test    ebx, ebx
0x14000d125  jnz     short loc_14000D130
0x14000d127  mov     ecx, r14d; dwErrCode
0x14000d12a  call    cs:__imp_SetLastError
0x14000d130  mov     eax, ebx
0x14000d132  mov     rcx, [rbp+57h+var_30]
0x14000d136  xor     rcx, rsp; StackCookie
0x14000d139  call    __security_check_cookie
0x14000d13e  mov     rbx, [rsp+0E0h+arg_10]
0x14000d146  add     rsp, 0C0h
0x14000d14d  pop     r15
0x14000d14f  pop     r14
0x14000d151  pop     rdi
0x14000d152  pop     rsi
0x14000d153  pop     rbp
0x14000d154  retn
```
