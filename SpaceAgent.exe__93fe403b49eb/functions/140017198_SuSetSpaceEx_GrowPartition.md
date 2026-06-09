# SuSetSpaceEx_GrowPartition

- ea: `0x140017198`
- end: `0x140017377`
- name: `SuSetSpaceEx_GrowPartition`
- size: `479`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140017044`

## callees

- `0x1400164c4`
- `0x140017198`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140017319`
- `KERNEL32!CloseHandle` at `0x140017336`
- `KERNEL32!CloseHandle` at `0x140017319`
- `KERNEL32!CloseHandle` at `0x140017336`
- `KERNEL32!SetLastError` at `0x140017308`
- `KERNEL32!SetLastError` at `0x14001734c`
- `KERNEL32!SetLastError` at `0x140017308`
- `KERNEL32!SetLastError` at `0x14001734c`
- `KERNEL32!GetLastError` at `0x1400172f6`
- `KERNEL32!GetLastError` at `0x14001730e`
- `KERNEL32!GetLastError` at `0x140017325`
- `KERNEL32!GetLastError` at `0x140017342`
- `KERNEL32!GetLastError` at `0x1400172f6`
- `KERNEL32!GetLastError` at `0x14001730e`
- `KERNEL32!GetLastError` at `0x140017325`
- `KERNEL32!GetLastError` at `0x140017342`
- `KERNEL32!DeviceIoControl` at `0x14001727b`
- `KERNEL32!DeviceIoControl` at `0x1400172ea`
- `KERNEL32!DeviceIoControl` at `0x14001727b`
- `KERNEL32!DeviceIoControl` at `0x1400172ea`
- `KERNEL32!CreateFileW` at `0x1400171fe`
- `KERNEL32!CreateFileW` at `0x1400172ac`
- `KERNEL32!CreateFileW` at `0x1400171fe`
- `KERNEL32!CreateFileW` at `0x1400172ac`

## pseudocode

```c
__int64 __fastcall SuSetSpaceEx_GrowPartition(const WCHAR *a1, unsigned __int64 a2, const WCHAR *a3)
{
  HANDLE FileW; // rax
  void *v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rsi
  DWORD LastError; // edi
  BOOL v10; // eax
  BOOL v11; // eax
  unsigned int v13; // [rsp+40h] [rbp-40h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-3Ch] BYREF
  unsigned __int64 v15; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v16; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  __int128 InBuffer; // [rsp+60h] [rbp-20h] BYREF

  BytesReturned = 0;
  v13 = 0;
  v15 = 0;
  InBuffer = 0;
  v16 = 0;
  v17 = 0;
  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v7 = 0;
LABEL_15:
    LastError = GetLastError();
    goto LABEL_16;
  }
  v8 = -1;
  if ( !(unsigned int)GetDisk_LastPartitionInfo(FileW, &v13, &v15, &v16) )
    goto LABEL_9;
  LODWORD(InBuffer) = v13;
  *((_QWORD *)&InBuffer + 1) = v15 - v16;
  v17 = v15 / a2;
  v7 = DeviceIoControl(v6, 0x7C0D0u, &InBuffer, 0x10u, 0, 0, &BytesReturned, 0);
  if ( !v7 )
    goto LABEL_10;
  v8 = (__int64)CreateFileW(a3, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( v8 == -1 )
  {
    v7 = 0;
    goto LABEL_10;
  }
  v7 = DeviceIoControl((HANDLE)v8, 0x900F0u, &v17, 8u, 0, 0, &BytesReturned, 0);
  if ( !v7 && GetLastError() == 87 )
  {
LABEL_9:
    v7 = 1;
    SetLastError(0);
  }
LABEL_10:
  LastError = GetLastError();
  v10 = CloseHandle(v6);
  if ( v7 )
  {
    v7 = v10;
    LastError = GetLastError();
  }
  if ( v8 != -1 )
  {
    v11 = CloseHandle((HANDLE)v8);
    if ( v7 )
    {
      v7 = v11;
      goto LABEL_15;
    }
  }
LABEL_16:
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x140017198  mov     [rsp-28h+arg_18], rbx
0x14001719d  push    rbp
0x14001719e  push    rsi
0x14001719f  push    rdi
0x1400171a0  push    r14
0x1400171a2  push    r15
0x1400171a4  mov     rbp, rsp
0x1400171a7  sub     rsp, 80h
0x1400171ae  mov     rax, cs:__security_cookie
0x1400171b5  xor     rax, rsp
0x1400171b8  mov     [rbp+var_10], rax
0x1400171bc  xor     r15d, r15d
0x1400171bf  mov     rdi, r8
0x1400171c2  mov     rbx, rdx
0x1400171c5  mov     [rsp+80h+hTemplateFile], r15; hTemplateFile
0x1400171ca  xorps   xmm0, xmm0
0x1400171cd  mov     [rsp+80h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1400171d2  xor     r9d, r9d; lpSecurityAttributes
0x1400171d5  mov     [rbp+BytesReturned], r15d
0x1400171d9  lea     r8d, [r15+3]; dwShareMode
0x1400171dd  mov     [rbp+var_40], r15d
0x1400171e1  mov     edx, 0C0000000h; dwDesiredAccess
0x1400171e6  mov     [rbp+var_38], r15
0x1400171ea  movups  [rbp+InBuffer], xmm0
0x1400171ee  mov     [rbp+var_30], r15
0x1400171f2  mov     [rbp+var_28], r15
0x1400171f6  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1400171fe  call    cs:__imp_CreateFileW
0x140017204  mov     r14, rax
0x140017207  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001720b  jnz     short loc_140017215
0x14001720d  mov     ebx, r15d
0x140017210  jmp     loc_140017342
0x140017215  lea     r9, [rbp+var_30]; unsigned __int64 *
0x140017219  mov     rcx, r14; hDevice
0x14001721c  lea     r8, [rbp+var_38]; unsigned __int64 *
0x140017220  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140017224  lea     rdx, [rbp+var_40]; unsigned int *
0x140017228  call    ?GetDisk_LastPartitionInfo@@YAHPEAXPEAIPEA_K2@Z; GetDisk_LastPartitionInfo(void *,uint *,unsigned __int64 *,unsigned __int64 *)
0x14001722d  test    eax, eax
0x14001722f  jz      loc_140017301
0x140017235  mov     eax, [rbp+var_40]
0x140017238  lea     r9d, [rsi+11h]; nInBufferSize
0x14001723c  mov     dword ptr [rbp+InBuffer], eax
0x14001723f  lea     r8, [rbp+InBuffer]; lpInBuffer
0x140017243  mov     rax, [rbp+var_38]
0x140017247  xor     edx, edx
0x140017249  mov     rcx, rax
0x14001724c  mov     [rsp+80h+lpOverlapped], r15; lpOverlapped
0x140017251  sub     rcx, [rbp+var_30]
0x140017255  div     rbx
0x140017258  mov     qword ptr [rbp+InBuffer+8], rcx
0x14001725c  mov     edx, 7C0D0h; dwIoControlCode
0x140017261  mov     [rbp+var_28], rax
0x140017265  mov     rcx, r14; hDevice
0x140017268  lea     rax, [rbp+BytesReturned]
0x14001726c  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x140017271  mov     [rsp+80h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x140017276  mov     qword ptr [rsp+80h+dwCreationDisposition], r15; lpOutBuffer
0x14001727b  call    cs:__imp_DeviceIoControl
0x140017281  mov     ebx, eax
0x140017283  test    eax, eax
0x140017285  jz      loc_14001730E
0x14001728b  mov     [rsp+80h+hTemplateFile], r15; hTemplateFile
0x140017290  lea     r8d, [rsi+4]; dwShareMode
0x140017294  mov     [rsp+80h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x140017299  xor     r9d, r9d; lpSecurityAttributes
0x14001729c  mov     edx, 0C0000000h; dwDesiredAccess
0x1400172a1  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1400172a9  mov     rcx, rdi; lpFileName
0x1400172ac  call    cs:__imp_CreateFileW
0x1400172b2  mov     rsi, rax
0x1400172b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400172b9  jnz     short loc_1400172C0
0x1400172bb  mov     ebx, r15d
0x1400172be  jmp     short loc_14001730E
0x1400172c0  mov     [rsp+80h+lpOverlapped], r15; lpOverlapped
0x1400172c5  lea     rax, [rbp+BytesReturned]
0x1400172c9  mov     [rsp+80h+hTemplateFile], rax; lpBytesReturned
0x1400172ce  lea     r8, [rbp+var_28]; lpInBuffer
0x1400172d2  mov     [rsp+80h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x1400172d7  mov     r9d, 8; nInBufferSize
0x1400172dd  mov     edx, 900F0h; dwIoControlCode
0x1400172e2  mov     qword ptr [rsp+80h+dwCreationDisposition], r15; lpOutBuffer
0x1400172e7  mov     rcx, rsi; hDevice
0x1400172ea  call    cs:__imp_DeviceIoControl
0x1400172f0  mov     ebx, eax
0x1400172f2  test    eax, eax
0x1400172f4  jnz     short loc_14001730E
0x1400172f6  call    cs:__imp_GetLastError
0x1400172fc  cmp     eax, 57h ; 'W'
0x1400172ff  jnz     short loc_14001730E
0x140017301  xor     ecx, ecx; dwErrCode
0x140017303  mov     ebx, 1
0x140017308  call    cs:__imp_SetLastError
0x14001730e  call    cs:__imp_GetLastError
0x140017314  mov     rcx, r14; hObject
0x140017317  mov     edi, eax
0x140017319  call    cs:__imp_CloseHandle
0x14001731f  test    ebx, ebx
0x140017321  jz      short loc_14001732D
0x140017323  mov     ebx, eax
0x140017325  call    cs:__imp_GetLastError
0x14001732b  mov     edi, eax
0x14001732d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140017331  jz      short loc_14001734A
0x140017333  mov     rcx, rsi; hObject
0x140017336  call    cs:__imp_CloseHandle
0x14001733c  test    ebx, ebx
0x14001733e  jz      short loc_14001734A
0x140017340  mov     ebx, eax
0x140017342  call    cs:__imp_GetLastError
0x140017348  mov     edi, eax
0x14001734a  mov     ecx, edi; dwErrCode
0x14001734c  call    cs:__imp_SetLastError
0x140017352  mov     eax, ebx
0x140017354  mov     rcx, [rbp+var_10]
0x140017358  xor     rcx, rsp; StackCookie
0x14001735b  call    __security_check_cookie
0x140017360  mov     rbx, [rsp+80h+arg_18]
0x140017368  add     rsp, 80h
0x14001736f  pop     r15
0x140017371  pop     r14
0x140017373  pop     rdi
0x140017374  pop     rsi
0x140017375  pop     rbp
0x140017376  retn
```
