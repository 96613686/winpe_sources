# BdeCfgpGetLogVolumeProps

- ea: `0x180006cbc`
- end: `0x180006eb1`
- name: `BdeCfgpGetLogVolumeProps`
- size: `501`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800067f0`
- `0x180006eb8`

## callees

- `0x180006cbc`
- `0x180007470`
- `0x18001358e`
- `0x1800135c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006db2`
- `KERNEL32!GetLastError` at `0x180006db2`
- `KERNEL32!CreateFileW` at `0x180006da3`
- `KERNEL32!CreateFileW` at `0x180006da3`
- `KERNEL32!DeviceIoControl` at `0x180006dff`
- `KERNEL32!DeviceIoControl` at `0x180006e45`
- `KERNEL32!DeviceIoControl` at `0x180006dff`
- `KERNEL32!DeviceIoControl` at `0x180006e45`
- `KERNEL32!CloseHandle` at `0x180006e5f`
- `KERNEL32!CloseHandle` at `0x180006e5f`

## pseudocode

```c
__int64 __fastcall BdeCfgpGetLogVolumeProps(unsigned __int16 *a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned __int16 *v5; // rcx
  __int64 v6; // rdx
  _WORD *v7; // r8
  _WORD *v8; // rcx
  unsigned int v9; // ebx
  HANDLE FileW; // rsi
  signed int LastError; // eax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-E8h] BYREF
  _BYTE OutBuffer[24]; // [rsp+50h] [rbp-D8h] BYREF
  int v15; // [rsp+68h] [rbp-C0h]
  _DWORD v16[8]; // [rsp+E0h] [rbp-48h] BYREF

  BytesReturned[0] = 0;
  memset(v16, 0, sizeof(v16));
  memset_0(OutBuffer, 0, 0x90u);
  if ( !a1 || !a2 )
    return 2147500035LL;
  v4 = 2147483646;
  v5 = a1;
  v6 = 260;
  v7 = (_WORD *)a2;
  do
  {
    if ( !v4 )
      break;
    if ( !*v5 )
      break;
    *v7++ = *v5++;
    --v4;
    --v6;
  }
  while ( v6 );
  v8 = v7 - 1;
  v9 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
    v8 = v7;
  *v8 = 0;
  if ( !v6 )
  {
    *(_WORD *)a2 = 0;
    v9 = 0;
  }
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( DeviceIoControl(FileW, 0x70048u, 0, 0, OutBuffer, 0x90u, BytesReturned, 0) )
      *(_DWORD *)(a2 + 528) = v15;
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v16, 0x20u, BytesReturned, 0) )
      *(_DWORD *)(a2 + 524) = v16[2];
    CloseHandle(FileW);
    if ( (unsigned int)BdeCfgGetVolumeDriveLetter(a1, (unsigned __int16 *)(a2 + 520)) )
      *(_WORD *)(a2 + 520) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180006cbc  mov     r11, rsp
0x180006cbf  mov     [r11+18h], rbx
0x180006cc3  mov     [r11+20h], rbp
0x180006cc7  push    rsi
0x180006cc8  push    rdi
0x180006cc9  push    r14
0x180006ccb  sub     rsp, 110h
0x180006cd2  mov     rax, cs:__security_cookie
0x180006cd9  xor     rax, rsp
0x180006cdc  mov     [rsp+128h+var_28], rax
0x180006ce4  xorps   xmm0, xmm0
0x180006ce7  mov     rdi, rdx
0x180006cea  mov     rbp, rcx
0x180006ced  xor     r14d, r14d
0x180006cf0  xor     edx, edx; Val
0x180006cf2  mov     [rsp+128h+BytesReturned], r14d
0x180006cf7  lea     rcx, [rsp+128h+OutBuffer]; void *
0x180006cfc  mov     r8d, 90h; Size
0x180006d02  movups  xmmword ptr [r11-48h], xmm0
0x180006d07  movups  xmmword ptr [r11-38h], xmm0
0x180006d0c  call    memset_0
0x180006d11  test    rbp, rbp
0x180006d14  jz      loc_180006E84
0x180006d1a  test    rdi, rdi
0x180006d1d  jz      loc_180006E84
0x180006d23  mov     eax, 7FFFFFFEh
0x180006d28  mov     rcx, rbp
0x180006d2b  mov     edx, 104h
0x180006d30  mov     r8, rdi
0x180006d33  test    rax, rax
0x180006d36  jz      short loc_180006D57
0x180006d38  movzx   r9d, word ptr [rcx]
0x180006d3c  test    r9w, r9w
0x180006d40  jz      short loc_180006D57
0x180006d42  mov     [r8], r9w
0x180006d46  add     rcx, 2
0x180006d4a  add     r8, 2
0x180006d4e  dec     rax
0x180006d51  sub     rdx, 1
0x180006d55  jnz     short loc_180006D33
0x180006d57  mov     rax, rdx
0x180006d5a  lea     rcx, [r8-2]
0x180006d5e  neg     rax
0x180006d61  sbb     ebx, ebx
0x180006d63  not     ebx
0x180006d65  and     ebx, 8007007Ah
0x180006d6b  test    rdx, rdx
0x180006d6e  cmovnz  rcx, r8
0x180006d72  mov     [rcx], r14w
0x180006d76  jnz     short loc_180006D7F
0x180006d78  mov     [rdi], r14w
0x180006d7c  mov     ebx, r14d
0x180006d7f  xor     r9d, r9d; lpSecurityAttributes
0x180006d82  mov     [rsp+128h+hTemplateFile], r14; hTemplateFile
0x180006d87  mov     [rsp+128h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180006d8f  mov     edx, 80000000h; dwDesiredAccess
0x180006d94  mov     rcx, rbp; lpFileName
0x180006d97  mov     [rsp+128h+dwCreationDisposition], 3; dwCreationDisposition
0x180006d9f  lea     r8d, [r9+1]; dwShareMode
0x180006da3  call    cs:__imp_CreateFileW
0x180006da9  mov     rsi, rax
0x180006dac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006db0  jnz     short loc_180006DD0
0x180006db2  call    cs:__imp_GetLastError
0x180006db8  mov     ebx, eax
0x180006dba  test    eax, eax
0x180006dbc  jle     loc_180006E80
0x180006dc2  movzx   ebx, ax
0x180006dc5  or      ebx, 80070000h
0x180006dcb  jmp     loc_180006E80
0x180006dd0  mov     [rsp+128h+lpOverlapped], r14; lpOverlapped
0x180006dd5  lea     rax, [rsp+128h+BytesReturned]
0x180006dda  mov     [rsp+128h+hTemplateFile], rax; lpBytesReturned
0x180006ddf  xor     r9d, r9d; nInBufferSize
0x180006de2  lea     rax, [rsp+128h+OutBuffer]
0x180006de7  mov     [rsp+128h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x180006def  xor     r8d, r8d; lpInBuffer
0x180006df2  mov     qword ptr [rsp+128h+dwCreationDisposition], rax; lpOutBuffer
0x180006df7  mov     edx, 70048h; dwIoControlCode
0x180006dfc  mov     rcx, rsi; hDevice
0x180006dff  call    cs:__imp_DeviceIoControl
0x180006e05  test    eax, eax
0x180006e07  jz      short loc_180006E13
0x180006e09  mov     eax, [rsp+128h+var_C0]
0x180006e0d  mov     [rdi+210h], eax
0x180006e13  mov     [rsp+128h+lpOverlapped], r14; lpOverlapped
0x180006e18  lea     rax, [rsp+128h+BytesReturned]
0x180006e1d  mov     [rsp+128h+hTemplateFile], rax; lpBytesReturned
0x180006e22  xor     r9d, r9d; nInBufferSize
0x180006e25  lea     rax, [rsp+128h+var_48]
0x180006e2d  mov     [rsp+128h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180006e35  xor     r8d, r8d; lpInBuffer
0x180006e38  mov     qword ptr [rsp+128h+dwCreationDisposition], rax; lpOutBuffer
0x180006e3d  mov     edx, 560000h; dwIoControlCode
0x180006e42  mov     rcx, rsi; hDevice
0x180006e45  call    cs:__imp_DeviceIoControl
0x180006e4b  test    eax, eax
0x180006e4d  jz      short loc_180006E5C
0x180006e4f  mov     eax, [rsp+128h+var_40]
0x180006e56  mov     [rdi+20Ch], eax
0x180006e5c  mov     rcx, rsi; hObject
0x180006e5f  call    cs:__imp_CloseHandle
0x180006e65  lea     rdx, [rdi+208h]; unsigned __int16 *
0x180006e6c  mov     rcx, rbp; unsigned __int16 *
0x180006e6f  call    ?BdeCfgGetVolumeDriveLetter@@YAJPEBGPEAG@Z; BdeCfgGetVolumeDriveLetter(ushort const *,ushort *)
0x180006e74  test    eax, eax
0x180006e76  jz      short loc_180006E80
0x180006e78  mov     [rdi+208h], r14w
0x180006e80  mov     eax, ebx
0x180006e82  jmp     short loc_180006E89
0x180006e84  mov     eax, 80004003h
0x180006e89  mov     rcx, [rsp+128h+var_28]
0x180006e91  xor     rcx, rsp; StackCookie
0x180006e94  call    __security_check_cookie
0x180006e99  lea     r11, [rsp+128h+var_18]
0x180006ea1  mov     rbx, [r11+30h]
0x180006ea5  mov     rbp, [r11+38h]
0x180006ea9  mov     rsp, r11
0x180006eac  pop     r14
0x180006eae  pop     rdi
0x180006eaf  pop     rsi
0x180006eb0  retn
```
