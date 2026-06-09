# AssignAccessLetter_ClearAttributes

- ea: `0x14001d054`
- end: `0x14001d138`
- name: `AssignAccessLetter_ClearAttributes`
- size: `228`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14001cde8`

## callees

- `0x14001d054`
- `0x14001edc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001d101`
- `KERNEL32!CloseHandle` at `0x14001d101`
- `KERNEL32!SetLastError` at `0x14001d111`
- `KERNEL32!SetLastError` at `0x14001d111`
- `KERNEL32!GetLastError` at `0x14001d0ae`
- `KERNEL32!GetLastError` at `0x14001d0f6`
- `KERNEL32!GetLastError` at `0x14001d0ae`
- `KERNEL32!GetLastError` at `0x14001d0f6`
- `KERNEL32!DeviceIoControl` at `0x14001d0ee`
- `KERNEL32!DeviceIoControl` at `0x14001d0ee`
- `KERNEL32!CreateFileW` at `0x14001d09d`
- `KERNEL32!CreateFileW` at `0x14001d09d`

## pseudocode

```c
__int64 __fastcall AssignAccessLetter_ClearAttributes(const WCHAR *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  unsigned int v3; // ebx
  DWORD LastError; // edi
  BOOL v5; // esi
  __int128 InBuffer; // [rsp+40h] [rbp-28h] BYREF

  InBuffer = 0;
  FileW = CreateFileW(a1, 0xC0000000, 3u, 0, 3u, 0, 0);
  v2 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v3 = 0;
  }
  else
  {
    v5 = DeviceIoControl(FileW, 0x560034u, &InBuffer, 0x10u, 0, 0, 0, 0);
    LastError = GetLastError();
    v3 = CloseHandle(v2);
    if ( !v5 )
    {
      v3 = 0;
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
LABEL_6:
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x14001d054  mov     r11, rsp
0x14001d057  mov     [r11+10h], rbx
0x14001d05b  mov     [r11+18h], rsi
0x14001d05f  push    rdi
0x14001d060  sub     rsp, 60h
0x14001d064  mov     rax, cs:__security_cookie
0x14001d06b  xor     rax, rsp
0x14001d06e  mov     [rsp+68h+var_18], rax
0x14001d073  mov     qword ptr [r11-38h], 0
0x14001d07b  xorps   xmm0, xmm0
0x14001d07e  mov     r8d, 3; dwShareMode
0x14001d084  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14001d08c  xor     r9d, r9d; lpSecurityAttributes
0x14001d08f  mov     [r11-48h], r8d
0x14001d093  mov     edx, 0C0000000h; dwDesiredAccess
0x14001d098  movups  [rsp+68h+InBuffer], xmm0
0x14001d09d  call    cs:__imp_CreateFileW
0x14001d0a3  mov     rbx, rax
0x14001d0a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d0aa  jnz     short loc_14001D0B8
0x14001d0ac  xor     ebx, ebx
0x14001d0ae  call    cs:__imp_GetLastError
0x14001d0b4  mov     edi, eax
0x14001d0b6  jmp     short loc_14001D10F
0x14001d0b8  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x14001d0c1  lea     r8, [rsp+68h+InBuffer]; lpInBuffer
0x14001d0c6  mov     [rsp+68h+lpBytesReturned], 0; lpBytesReturned
0x14001d0cf  mov     r9d, 10h; nInBufferSize
0x14001d0d5  mov     [rsp+68h+dwFlagsAndAttributes], 0; nOutBufferSize
0x14001d0dd  mov     edx, 560034h; dwIoControlCode
0x14001d0e2  mov     rcx, rbx; hDevice
0x14001d0e5  mov     [rsp+68h+lpOutBuffer], 0; lpOutBuffer
0x14001d0ee  call    cs:__imp_DeviceIoControl
0x14001d0f4  mov     esi, eax
0x14001d0f6  call    cs:__imp_GetLastError
0x14001d0fc  mov     rcx, rbx; hObject
0x14001d0ff  mov     edi, eax
0x14001d101  call    cs:__imp_CloseHandle
0x14001d107  mov     ebx, eax
0x14001d109  test    esi, esi
0x14001d10b  jnz     short loc_14001D0AE
0x14001d10d  mov     ebx, esi
0x14001d10f  mov     ecx, edi; dwErrCode
0x14001d111  call    cs:__imp_SetLastError
0x14001d117  mov     eax, ebx
0x14001d119  mov     rcx, [rsp+68h+var_18]
0x14001d11e  xor     rcx, rsp; StackCookie
0x14001d121  call    __security_check_cookie
0x14001d126  lea     r11, [rsp+68h+var_8]
0x14001d12b  mov     rbx, [r11+18h]
0x14001d12f  mov     rsi, [r11+20h]
0x14001d133  mov     rsp, r11
0x14001d136  pop     rdi
0x14001d137  retn
```
