# FindVolume_IsVolumeOnDisk

- ea: `0x14001dd54`
- end: `0x14001ded4`
- name: `FindVolume_IsVolumeOnDisk`
- size: `384`
- prototype: `__int64 __fastcall(int, const WCHAR *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001db30`
- `0x14001dce4`

## callees

- `0x14001dd54`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001de92`
- `KERNEL32!CloseHandle` at `0x14001de92`
- `KERNEL32!SetLastError` at `0x14001deab`
- `KERNEL32!SetLastError` at `0x14001deab`
- `KERNEL32!GetLastError` at `0x14001de77`
- `KERNEL32!GetLastError` at `0x14001de81`
- `KERNEL32!GetLastError` at `0x14001de9e`
- `KERNEL32!GetLastError` at `0x14001de77`
- `KERNEL32!GetLastError` at `0x14001de81`
- `KERNEL32!GetLastError` at `0x14001de9e`
- `KERNEL32!DeviceIoControl` at `0x14001dde6`
- `KERNEL32!DeviceIoControl` at `0x14001de14`
- `KERNEL32!DeviceIoControl` at `0x14001de5f`
- `KERNEL32!DeviceIoControl` at `0x14001dde6`
- `KERNEL32!DeviceIoControl` at `0x14001de14`
- `KERNEL32!DeviceIoControl` at `0x14001de5f`
- `KERNEL32!CreateFileW` at `0x14001ddb2`
- `KERNEL32!CreateFileW` at `0x14001ddb2`

## pseudocode

```c
__int64 __fastcall FindVolume_IsVolumeOnDisk(int a1, const WCHAR *a2, int *a3)
{
  int v3; // ebp
  unsigned int v6; // ebx
  HANDLE FileW; // rax
  void *v8; // rsi
  BOOL v9; // edi
  BOOL v10; // eax
  DWORD LastError; // edi
  BOOL v12; // eax
  _BYTE OutBuffer[8]; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v15[2]; // [rsp+48h] [rbp-50h] BYREF

  OutBuffer[0] = 0;
  v3 = 0;
  v6 = 1;
  memset(v15, 0, sizeof(v15));
  FileW = CreateFileW(a2, 0x20000u, 3u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL
    || ((v9 = DeviceIoControl(FileW, 0x560028u, 0, 0, 0, 0, 0, 0),
         v10 = DeviceIoControl(v8, 0x560048u, 0, 0, OutBuffer, 1u, 0, 0),
         (v6 = v10) != 0)
      ? (LOBYTE(v10) = OutBuffer[0])
      : (OutBuffer[0] = 0, v6 = 1),
        !v9 || v10 || (v6 = DeviceIoControl(v8, 0x560000u, 0, 0, v15, 0x20u, 0, 0)) == 0) )
  {
    LastError = GetLastError();
    if ( v8 == (void *)-1LL )
      goto LABEL_14;
  }
  else
  {
    if ( DWORD2(v15[0]) == a1 )
      v3 = 1;
    LastError = GetLastError();
  }
  v12 = CloseHandle(v8);
  if ( v6 )
  {
    v6 = v12;
    LastError = GetLastError();
  }
LABEL_14:
  *a3 = v3;
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x14001dd54  mov     [rsp+arg_0], rbx
0x14001dd59  push    rbp
0x14001dd5a  push    rsi
0x14001dd5b  push    rdi
0x14001dd5c  push    r14
0x14001dd5e  push    r15
0x14001dd60  sub     rsp, 70h
0x14001dd64  mov     rax, cs:__security_cookie
0x14001dd6b  xor     rax, rsp
0x14001dd6e  mov     [rsp+98h+var_30], rax
0x14001dd73  mov     rax, rdx
0x14001dd76  mov     [rsp+98h+OutBuffer], 0
0x14001dd7b  xorps   xmm0, xmm0
0x14001dd7e  xor     ebp, ebp
0x14001dd80  mov     r15, r8
0x14001dd83  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x14001dd88  mov     r14d, ecx
0x14001dd8b  mov     [rsp+98h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x14001dd8f  mov     ebx, 1
0x14001dd94  xor     r9d, r9d; lpSecurityAttributes
0x14001dd97  mov     edx, 20000h; dwDesiredAccess
0x14001dd9c  mov     rcx, rax; lpFileName
0x14001dd9f  movups  [rsp+98h+var_50], xmm0
0x14001dda4  lea     r8d, [rbx+2]; dwShareMode
0x14001dda8  mov     [rsp+98h+dwCreationDisposition], r8d; dwCreationDisposition
0x14001ddad  movups  [rsp+98h+var_40], xmm0
0x14001ddb2  call    cs:__imp_CreateFileW
0x14001ddb8  mov     rsi, rax
0x14001ddbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ddbf  jz      loc_14001DE81
0x14001ddc5  mov     [rsp+98h+lpOverlapped], rbp; lpOverlapped
0x14001ddca  xor     r9d, r9d; nInBufferSize
0x14001ddcd  mov     [rsp+98h+hTemplateFile], rbp; lpBytesReturned
0x14001ddd2  xor     r8d, r8d; lpInBuffer
0x14001ddd5  mov     [rsp+98h+dwFlagsAndAttributes], ebp; nOutBufferSize
0x14001ddd9  mov     edx, 560028h; dwIoControlCode
0x14001ddde  mov     rcx, rax; hDevice
0x14001dde1  mov     qword ptr [rsp+98h+dwCreationDisposition], rbp; lpOutBuffer
0x14001dde6  call    cs:__imp_DeviceIoControl
0x14001ddec  mov     [rsp+98h+lpOverlapped], rbp; lpOverlapped
0x14001ddf1  xor     r9d, r9d; nInBufferSize
0x14001ddf4  mov     edi, eax
0x14001ddf6  mov     [rsp+98h+hTemplateFile], rbp; lpBytesReturned
0x14001ddfb  lea     rax, [rsp+98h+OutBuffer]
0x14001de00  mov     [rsp+98h+dwFlagsAndAttributes], ebx; nOutBufferSize
0x14001de04  xor     r8d, r8d; lpInBuffer
0x14001de07  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpOutBuffer
0x14001de0c  mov     edx, 560048h; dwIoControlCode
0x14001de11  mov     rcx, rsi; hDevice
0x14001de14  call    cs:__imp_DeviceIoControl
0x14001de1a  mov     ebx, eax
0x14001de1c  test    eax, eax
0x14001de1e  jnz     short loc_14001DE29
0x14001de20  mov     [rsp+98h+OutBuffer], al
0x14001de24  lea     ebx, [rbp+1]
0x14001de27  jmp     short loc_14001DE2D
0x14001de29  mov     al, [rsp+98h+OutBuffer]
0x14001de2d  test    edi, edi
0x14001de2f  jz      short loc_14001DE81
0x14001de31  test    al, al
0x14001de33  jnz     short loc_14001DE81
0x14001de35  mov     [rsp+98h+lpOverlapped], rbp; lpOverlapped
0x14001de3a  lea     rax, [rsp+98h+var_50]
0x14001de3f  mov     [rsp+98h+hTemplateFile], rbp; lpBytesReturned
0x14001de44  xor     r9d, r9d; nInBufferSize
0x14001de47  mov     [rsp+98h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x14001de4f  xor     r8d, r8d; lpInBuffer
0x14001de52  mov     edx, 560000h; dwIoControlCode
0x14001de57  mov     qword ptr [rsp+98h+dwCreationDisposition], rax; lpOutBuffer
0x14001de5c  mov     rcx, rsi; hDevice
0x14001de5f  call    cs:__imp_DeviceIoControl
0x14001de65  mov     ebx, eax
0x14001de67  test    eax, eax
0x14001de69  jz      short loc_14001DE81
0x14001de6b  cmp     dword ptr [rsp+98h+var_50+8], r14d
0x14001de70  jnz     short loc_14001DE77
0x14001de72  mov     ebp, 1
0x14001de77  call    cs:__imp_GetLastError
0x14001de7d  mov     edi, eax
0x14001de7f  jmp     short loc_14001DE8F
0x14001de81  call    cs:__imp_GetLastError
0x14001de87  mov     edi, eax
0x14001de89  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14001de8d  jz      short loc_14001DEA6
0x14001de8f  mov     rcx, rsi; hObject
0x14001de92  call    cs:__imp_CloseHandle
0x14001de98  test    ebx, ebx
0x14001de9a  jz      short loc_14001DEA6
0x14001de9c  mov     ebx, eax
0x14001de9e  call    cs:__imp_GetLastError
0x14001dea4  mov     edi, eax
0x14001dea6  mov     ecx, edi; dwErrCode
0x14001dea8  mov     [r15], ebp
0x14001deab  call    cs:__imp_SetLastError
0x14001deb1  mov     eax, ebx
0x14001deb3  mov     rcx, [rsp+98h+var_30]
0x14001deb8  xor     rcx, rsp; StackCookie
0x14001debb  call    __security_check_cookie
0x14001dec0  mov     rbx, [rsp+98h+arg_0]
0x14001dec8  add     rsp, 70h
0x14001decc  pop     r15
0x14001dece  pop     r14
0x14001ded0  pop     rdi
0x14001ded1  pop     rsi
0x14001ded2  pop     rbp
0x14001ded3  retn
```
