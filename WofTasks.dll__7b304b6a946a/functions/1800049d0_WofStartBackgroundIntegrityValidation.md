# WofStartBackgroundIntegrityValidation

- ea: `0x1800049d0`
- end: `0x180004aed`
- name: `WofStartBackgroundIntegrityValidation`
- size: `285`
- prototype: `__int64 __fastcall(LPOVERLAPPED lpOverlapped, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003ac0`

## callees

- `0x1800049d0`
- `0x180004ef4`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180004a82`
- `KERNEL32!DeviceIoControl` at `0x180004a82`
- `KERNEL32!GetLastError` at `0x180004a1d`
- `KERNEL32!GetLastError` at `0x180004a90`
- `KERNEL32!GetLastError` at `0x180004a1d`
- `KERNEL32!GetLastError` at `0x180004a90`
- `KERNEL32!CloseHandle` at `0x180004ac9`
- `KERNEL32!CloseHandle` at `0x180004ac9`

## pseudocode

```c
__int64 __fastcall WofStartBackgroundIntegrityValidation(LPOVERLAPPED lpOverlapped, __int64 *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  signed int v7; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-28h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+58h] [rbp-18h]

  BytesReturned = 0;
  InBuffer = 0;
  v12 = 0;
  hDevice = (HANDLE)-1LL;
  if ( (int)WofpOpenSystemVolumeWithFlagsAndAttributes(0x40000000, &hDevice) < 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = (__int64)hDevice;
    goto LABEL_12;
  }
  v6 = (__int64)hDevice;
  InBuffer = 0x100000001LL;
  v12 = 4;
  if ( DeviceIoControl(hDevice, 0x90328u, &InBuffer, 0xCu, 0, 0, &BytesReturned, lpOverlapped) )
  {
    v5 = 0;
LABEL_11:
    *a2 = v6;
    v6 = -1;
    goto LABEL_12;
  }
  v7 = GetLastError();
  v5 = v7;
  if ( v7 > 0 )
    v5 = (unsigned __int16)v7 | 0x80070000;
  if ( (int)(v5 + 0x80000000) < 0 || v5 == -2147023899 )
    goto LABEL_11;
LABEL_12:
  if ( v6 != -1 )
    CloseHandle((HANDLE)v6);
  return v5;
}

```

## disassembly

```asm
0x1800049d0  mov     [rsp-18h+arg_10], rbx
0x1800049d5  push    rbp
0x1800049d6  push    rsi
0x1800049d7  push    rdi
0x1800049d8  mov     rbp, rsp
0x1800049db  sub     rsp, 70h
0x1800049df  mov     rax, cs:__security_cookie
0x1800049e6  xor     rax, rsp
0x1800049e9  mov     [rbp+var_10], rax
0x1800049ed  xor     eax, eax
0x1800049ef  mov     [rbp+BytesReturned], 0
0x1800049f6  mov     rsi, rdx
0x1800049f9  mov     [rbp+InBuffer], rax
0x1800049fd  mov     rbx, rcx
0x180004a00  mov     [rbp+var_18], eax
0x180004a03  lea     rdx, [rbp+hDevice]
0x180004a07  mov     [rbp+hDevice], 0FFFFFFFFFFFFFFFFh
0x180004a0f  mov     ecx, 40000000h
0x180004a14  call    WofpOpenSystemVolumeWithFlagsAndAttributes
0x180004a19  test    eax, eax
0x180004a1b  jns     short loc_180004A3B
0x180004a1d  call    cs:__imp_GetLastError
0x180004a23  mov     ebx, eax
0x180004a25  test    eax, eax
0x180004a27  jle     short loc_180004A32
0x180004a29  movzx   ebx, ax
0x180004a2c  or      ebx, 80070000h
0x180004a32  mov     rdi, [rbp+hDevice]
0x180004a36  jmp     loc_180004AC0
0x180004a3b  mov     rdi, [rbp+hDevice]
0x180004a3f  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180004a43  mov     eax, 1
0x180004a48  mov     [rsp+70h+lpOverlapped], rbx; lpOverlapped
0x180004a4d  mov     dword ptr [rbp+InBuffer], eax
0x180004a50  mov     r9d, 0Ch; nInBufferSize
0x180004a56  mov     dword ptr [rbp+InBuffer+4], eax
0x180004a59  mov     edx, 90328h; dwIoControlCode
0x180004a5e  lea     rax, [rbp+BytesReturned]
0x180004a62  mov     [rbp+var_18], 4
0x180004a69  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180004a6e  mov     rcx, rdi; hDevice
0x180004a71  mov     [rsp+70h+nOutBufferSize], 0; nOutBufferSize
0x180004a79  mov     [rsp+70h+lpOutBuffer], 0; lpOutBuffer
0x180004a82  call    cs:__imp_DeviceIoControl
0x180004a88  test    eax, eax
0x180004a8a  jz      short loc_180004A90
0x180004a8c  xor     ebx, ebx
0x180004a8e  jmp     short loc_180004AB9
0x180004a90  call    cs:__imp_GetLastError
0x180004a96  mov     ebx, eax
0x180004a98  test    eax, eax
0x180004a9a  jle     short loc_180004AA5
0x180004a9c  movzx   ebx, ax
0x180004a9f  or      ebx, 80070000h
0x180004aa5  mov     ecx, 80000000h
0x180004aaa  lea     eax, [rbx+rcx]
0x180004aad  test    ecx, eax
0x180004aaf  jnz     short loc_180004AB9
0x180004ab1  cmp     ebx, 800703E5h
0x180004ab7  jnz     short loc_180004AC0
0x180004ab9  mov     [rsi], rdi
0x180004abc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004ac0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180004ac4  jz      short loc_180004ACF
0x180004ac6  mov     rcx, rdi; hObject
0x180004ac9  call    cs:__imp_CloseHandle
0x180004acf  mov     eax, ebx
0x180004ad1  mov     rcx, [rbp+var_10]
0x180004ad5  xor     rcx, rsp; StackCookie
0x180004ad8  call    __security_check_cookie
0x180004add  mov     rbx, [rsp+70h+arg_10]
0x180004ae5  add     rsp, 70h
0x180004ae9  pop     rdi
0x180004aea  pop     rsi
0x180004aeb  pop     rbp
0x180004aec  retn
```
