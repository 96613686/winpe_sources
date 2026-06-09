# SiAttemptShrinkDynamic(_SP_DRIVE_INFO *)

- ea: `0x14000c104`
- end: `0x14000c264`
- name: `?SiAttemptShrinkDynamic@@YAHPEAU_SP_DRIVE_INFO@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(struct _SP_DRIVE_INFO *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e3f8`

## callees

- `0x14000c104`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000c234`
- `KERNEL32!CloseHandle` at `0x14000c234`
- `KERNEL32!DeviceIoControl` at `0x14000c1d8`
- `KERNEL32!DeviceIoControl` at `0x14000c229`
- `KERNEL32!DeviceIoControl` at `0x14000c1d8`
- `KERNEL32!DeviceIoControl` at `0x14000c229`
- `KERNEL32!CreateFileW` at `0x14000c187`
- `KERNEL32!CreateFileW` at `0x14000c187`

## pseudocode

```c
__int64 __fastcall SiAttemptShrinkDynamic(struct _SP_DRIVE_INFO *a1)
{
  HANDLE FileW; // rdi
  unsigned int v3; // ebx
  int InBuffer; // [rsp+48h] [rbp+7h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp+Bh] BYREF
  __m256i OutBuffer; // [rsp+50h] [rbp+Fh] BYREF
  __m256i v8; // [rsp+70h] [rbp+2Fh] BYREF

  BytesReturned = 0;
  InBuffer = 0;
  memset(&OutBuffer, 0, sizeof(OutBuffer));
  memset(&v8, 0, sizeof(v8));
  if ( *((_BYTE *)a1 + 2763) )
  {
    FileW = CreateFileW(L"\\\\.\\VolMgrControl", 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      return 0;
    }
    else
    {
      InBuffer = *((_DWORD *)a1 + 10);
      v3 = DeviceIoControl(FileW, 0x76433Cu, &InBuffer, 4u, &OutBuffer, 0x20u, &BytesReturned, 0);
      if ( v3 )
      {
        v8 = OutBuffer;
        v3 = DeviceIoControl(FileW, 0x76C3B0u, &v8, 0x20u, 0, 0, &BytesReturned, 0);
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x14000c104  mov     r11, rsp
0x14000c107  mov     [r11+10h], rbx
0x14000c10b  mov     [r11+18h], rdi
0x14000c10f  push    rbp
0x14000c110  lea     rbp, [r11-5Fh]
0x14000c114  sub     rsp, 90h
0x14000c11b  mov     rax, cs:__security_cookie
0x14000c122  xor     rax, rsp
0x14000c125  mov     [rbp+57h+var_8], rax
0x14000c129  xorps   xmm0, xmm0
0x14000c12c  mov     [rbp+57h+BytesReturned], 0
0x14000c133  xor     eax, eax
0x14000c135  mov     [rbp+57h+InBuffer], 0
0x14000c13c  xorps   xmm1, xmm1
0x14000c13f  mov     rbx, rcx
0x14000c142  movups  [rbp+57h+OutBuffer+4], xmm0
0x14000c146  mov     dword ptr [rbp+57h+OutBuffer], 0
0x14000c14d  movups  [rbp+57h+var_28+4], xmm1
0x14000c151  mov     dword ptr [rbp+57h+var_28], eax
0x14000c154  movups  [rbp+57h+var_38], xmm0
0x14000c158  movups  [rbp+57h+var_18], xmm1
0x14000c15c  cmp     [rcx+0ACBh], al
0x14000c162  jz      loc_14000C23C
0x14000c168  mov     [r11-68h], rax
0x14000c16c  lea     r8d, [rax+3]; dwShareMode
0x14000c170  mov     [rsp+90h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14000c174  lea     rcx, aVolmgrcontrol; "\\\\.\\VolMgrControl"
0x14000c17b  xor     r9d, r9d; lpSecurityAttributes
0x14000c17e  mov     [r11-78h], r8d
0x14000c182  mov     edx, 0C0000000h; dwDesiredAccess
0x14000c187  call    cs:__imp_CreateFileW
0x14000c18d  mov     rdi, rax
0x14000c190  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c194  jnz     short loc_14000C19D
0x14000c196  xor     ebx, ebx
0x14000c198  jmp     loc_14000C241
0x14000c19d  mov     eax, [rbx+28h]
0x14000c1a0  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14000c1a4  mov     [rbp+57h+InBuffer], eax
0x14000c1a7  mov     r9d, 4; nInBufferSize
0x14000c1ad  mov     [rsp+90h+lpOverlapped], 0; lpOverlapped
0x14000c1b6  lea     rax, [rbp+57h+BytesReturned]
0x14000c1ba  mov     [rsp+90h+lpBytesReturned], rax; lpBytesReturned
0x14000c1bf  mov     edx, 76433Ch; dwIoControlCode
0x14000c1c4  lea     rax, [rbp+57h+OutBuffer]
0x14000c1c8  mov     [rsp+90h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x14000c1d0  mov     rcx, rdi; hDevice
0x14000c1d3  mov     [rsp+90h+lpOutBuffer], rax; lpOutBuffer
0x14000c1d8  call    cs:__imp_DeviceIoControl
0x14000c1de  mov     ebx, eax
0x14000c1e0  test    eax, eax
0x14000c1e2  jz      short loc_14000C231
0x14000c1e4  movups  xmm0, [rbp+57h+OutBuffer]
0x14000c1e8  mov     [rsp+90h+lpOverlapped], 0; lpOverlapped
0x14000c1f1  lea     rax, [rbp+57h+BytesReturned]
0x14000c1f5  movups  xmm1, [rbp+57h+var_38]
0x14000c1f9  mov     [rsp+90h+lpBytesReturned], rax; lpBytesReturned
0x14000c1fe  lea     r8, [rbp+57h+var_28]; lpInBuffer
0x14000c202  mov     [rsp+90h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14000c20a  mov     r9d, 20h ; ' '; nInBufferSize
0x14000c210  mov     edx, 76C3B0h; dwIoControlCode
0x14000c215  mov     [rsp+90h+lpOutBuffer], 0; lpOutBuffer
0x14000c21e  mov     rcx, rdi; hDevice
0x14000c221  movups  [rbp+57h+var_28], xmm0
0x14000c225  movups  [rbp+57h+var_18], xmm1
0x14000c229  call    cs:__imp_DeviceIoControl
0x14000c22f  mov     ebx, eax
0x14000c231  mov     rcx, rdi; hObject
0x14000c234  call    cs:__imp_CloseHandle
0x14000c23a  jmp     short loc_14000C241
0x14000c23c  mov     ebx, 1
0x14000c241  mov     eax, ebx
0x14000c243  mov     rcx, [rbp+57h+var_8]
0x14000c247  xor     rcx, rsp; StackCookie
0x14000c24a  call    __security_check_cookie
0x14000c24f  lea     r11, [rsp+90h+var_s0]
0x14000c257  mov     rbx, [r11+18h]
0x14000c25b  mov     rdi, [r11+20h]
0x14000c25f  mov     rsp, r11
0x14000c262  pop     rbp
0x14000c263  retn
```
