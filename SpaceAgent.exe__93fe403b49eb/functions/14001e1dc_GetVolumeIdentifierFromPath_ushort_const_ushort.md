# GetVolumeIdentifierFromPath(ushort const *,ushort *)

- ea: `0x14001e1dc`
- end: `0x14001e322`
- name: `?GetVolumeIdentifierFromPath@@YAHPEBGPEAG@Z`
- size: `326`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001e464`

## callees

- `0x14001e1dc`
- `0x14001e328`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001e2e7`
- `KERNEL32!CloseHandle` at `0x14001e2e7`
- `KERNEL32!FindVolumeClose` at `0x14001e2ca`
- `KERNEL32!FindVolumeClose` at `0x14001e2ca`
- `KERNEL32!FindFirstVolumeW` at `0x14001e27d`
- `KERNEL32!FindFirstVolumeW` at `0x14001e27d`
- `KERNEL32!SetLastError` at `0x14001e2fd`
- `KERNEL32!SetLastError` at `0x14001e2fd`
- `KERNEL32!GetLastError` at `0x14001e2a8`
- `KERNEL32!GetLastError` at `0x14001e2b0`
- `KERNEL32!GetLastError` at `0x14001e2d6`
- `KERNEL32!GetLastError` at `0x14001e2f3`
- `KERNEL32!GetLastError` at `0x14001e2a8`
- `KERNEL32!GetLastError` at `0x14001e2b0`
- `KERNEL32!GetLastError` at `0x14001e2d6`
- `KERNEL32!GetLastError` at `0x14001e2f3`
- `KERNEL32!DeviceIoControl` at `0x14001e269`
- `KERNEL32!DeviceIoControl` at `0x14001e269`
- `KERNEL32!CreateFileW` at `0x14001e225`
- `KERNEL32!CreateFileW` at `0x14001e225`

## pseudocode

```c
__int64 __fastcall GetVolumeIdentifierFromPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 FirstVolumeW; // rsi
  HANDLE FileW; // rbp
  unsigned int VolumeIdentifierFromPath_LoopUntilMatch; // ebx
  DWORD LastError; // edi
  BOOL VolumeClose; // eax
  BOOL v8; // eax
  __int64 OutBuffer; // [rsp+40h] [rbp-38h] BYREF
  int v11; // [rsp+48h] [rbp-30h]

  *a2 = 0;
  FirstVolumeW = -1;
  OutBuffer = 0;
  v11 = 0;
  FileW = CreateFileW(a1, 0x20000u, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  VolumeIdentifierFromPath_LoopUntilMatch = DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, 0, 0);
  if ( VolumeIdentifierFromPath_LoopUntilMatch )
  {
    FirstVolumeW = (__int64)FindFirstVolumeW(a2, 0x32u);
    if ( FirstVolumeW == -1 )
    {
LABEL_2:
      VolumeIdentifierFromPath_LoopUntilMatch = 0;
      goto LABEL_6;
    }
    a2[48] = 0;
    VolumeIdentifierFromPath_LoopUntilMatch = GetVolumeIdentifierFromPath_LoopUntilMatch((HANDLE)FirstVolumeW);
  }
LABEL_6:
  LastError = GetLastError();
  if ( GetLastError() == 18 )
    LastError = 2;
  if ( FirstVolumeW != -1 )
  {
    VolumeClose = FindVolumeClose((HANDLE)FirstVolumeW);
    if ( VolumeIdentifierFromPath_LoopUntilMatch )
    {
      VolumeIdentifierFromPath_LoopUntilMatch = VolumeClose;
      LastError = GetLastError();
    }
  }
  if ( FileW != (HANDLE)-1LL )
  {
    v8 = CloseHandle(FileW);
    if ( VolumeIdentifierFromPath_LoopUntilMatch )
    {
      VolumeIdentifierFromPath_LoopUntilMatch = v8;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return VolumeIdentifierFromPath_LoopUntilMatch;
}

```

## disassembly

```asm
0x14001e1dc  mov     r11, rsp
0x14001e1df  mov     [r11+18h], rbx
0x14001e1e3  push    rbp
0x14001e1e4  push    rsi
0x14001e1e5  push    rdi
0x14001e1e6  sub     rsp, 60h
0x14001e1ea  mov     rax, cs:__security_cookie
0x14001e1f1  xor     rax, rsp
0x14001e1f4  mov     [rsp+78h+var_28], rax
0x14001e1f9  xor     eax, eax
0x14001e1fb  mov     rdi, rdx
0x14001e1fe  mov     [r11-48h], rax
0x14001e202  xor     r9d, r9d; lpSecurityAttributes
0x14001e205  mov     [rdx], ax
0x14001e208  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001e20c  mov     [r11-38h], rax
0x14001e210  mov     edx, 20000h; dwDesiredAccess
0x14001e215  lea     r8d, [rax+3]; dwShareMode
0x14001e219  mov     [rsp+78h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x14001e21d  mov     [r11-58h], r8d
0x14001e221  mov     [rsp+78h+var_30], eax
0x14001e225  call    cs:__imp_CreateFileW
0x14001e22b  mov     rbp, rax
0x14001e22e  cmp     rax, rsi
0x14001e231  jnz     short loc_14001E237
0x14001e233  xor     ebx, ebx
0x14001e235  jmp     short loc_14001E2A8
0x14001e237  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14001e240  lea     rax, [rsp+78h+OutBuffer]
0x14001e245  mov     [rsp+78h+lpBytesReturned], 0; lpBytesReturned
0x14001e24e  xor     r9d, r9d; nInBufferSize
0x14001e251  mov     [rsp+78h+dwFlagsAndAttributes], 0Ch; nOutBufferSize
0x14001e259  xor     r8d, r8d; lpInBuffer
0x14001e25c  mov     edx, 2D1080h; dwIoControlCode
0x14001e261  mov     [rsp+78h+lpOutBuffer], rax; lpOutBuffer
0x14001e266  mov     rcx, rbp; hDevice
0x14001e269  call    cs:__imp_DeviceIoControl
0x14001e26f  mov     ebx, eax
0x14001e271  test    eax, eax
0x14001e273  jz      short loc_14001E2A8
0x14001e275  mov     edx, 32h ; '2'; cchBufferLength
0x14001e27a  mov     rcx, rdi; lpszVolumeName
0x14001e27d  call    cs:__imp_FindFirstVolumeW
0x14001e283  mov     rsi, rax
0x14001e286  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e28a  jz      short loc_14001E233
0x14001e28c  mov     r8d, [rsp+78h+var_30]
0x14001e291  xor     eax, eax
0x14001e293  mov     edx, [rsp+78h+var_34]
0x14001e297  mov     r9, rdi
0x14001e29a  mov     rcx, rsi; hFindVolume
0x14001e29d  mov     [rdi+60h], ax
0x14001e2a1  call    GetVolumeIdentifierFromPath_LoopUntilMatch
0x14001e2a6  mov     ebx, eax
0x14001e2a8  call    cs:__imp_GetLastError
0x14001e2ae  mov     edi, eax
0x14001e2b0  call    cs:__imp_GetLastError
0x14001e2b6  cmp     eax, 12h
0x14001e2b9  mov     ecx, 2
0x14001e2be  cmovz   edi, ecx
0x14001e2c1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14001e2c5  jz      short loc_14001E2DE
0x14001e2c7  mov     rcx, rsi; hFindVolume
0x14001e2ca  call    cs:__imp_FindVolumeClose
0x14001e2d0  test    ebx, ebx
0x14001e2d2  jz      short loc_14001E2DE
0x14001e2d4  mov     ebx, eax
0x14001e2d6  call    cs:__imp_GetLastError
0x14001e2dc  mov     edi, eax
0x14001e2de  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x14001e2e2  jz      short loc_14001E2FB
0x14001e2e4  mov     rcx, rbp; hObject
0x14001e2e7  call    cs:__imp_CloseHandle
0x14001e2ed  test    ebx, ebx
0x14001e2ef  jz      short loc_14001E2FB
0x14001e2f1  mov     ebx, eax
0x14001e2f3  call    cs:__imp_GetLastError
0x14001e2f9  mov     edi, eax
0x14001e2fb  mov     ecx, edi; dwErrCode
0x14001e2fd  call    cs:__imp_SetLastError
0x14001e303  mov     eax, ebx
0x14001e305  mov     rcx, [rsp+78h+var_28]
0x14001e30a  xor     rcx, rsp; StackCookie
0x14001e30d  call    __security_check_cookie
0x14001e312  mov     rbx, [rsp+78h+arg_10]
0x14001e31a  add     rsp, 60h
0x14001e31e  pop     rdi
0x14001e31f  pop     rsi
0x14001e320  pop     rbp
0x14001e321  retn
```
