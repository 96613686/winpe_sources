# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x1801eeaf8`
- end: `0x1801eecfc`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1801ed940`

## callees

- `0x180006290`
- `0x1801ee0e0`
- `0x1801ee70c`
- `0x1801eea04`
- `0x1801eeaf8`
- `0x1801eed04`
- `0x1801eef9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eeb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eebef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eec58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eeb84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eebef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801eec58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801eecd3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801eecd3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801eebe5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801eebe5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801eeb75`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801eeb75`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801eec4e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801eec4e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801eec2a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1801eec2a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801eecca`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1801eecca`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(STRSAFE_PCNZWCH pszSrc)
{
  unsigned int IsBandBitLockerManaged; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int v5; // eax
  signed int LastError; // eax
  DWORD v7; // ebx
  void *v8; // rax
  void *v9; // r14
  signed int v10; // eax
  BOOL v11; // edx
  int v12; // eax
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-28h] BYREF
  __int128 OutBuffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]

  v17 = 0;
  OutBuffer = 0;
  BytesReturned = 0;
  NumberOfBytesRead = 0;
  if ( (unsigned int)FvepIsVolumeEncryptedCached(pszSrc) )
    return 1;
  FileW = CreateFileW(pszSrc, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    IsBandBitLockerManaged = FvepIsBandBitLockerManaged(FileW);
    if ( !IsBandBitLockerManaged )
    {
LABEL_25:
      CloseHandle(v4);
      return IsBandBitLockerManaged;
    }
    if ( !DeviceIoControl(v4, 0x70000u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0)
      || (v7 = (HIDWORD(v17) + 511) & 0xFFFFFE00, v8 = VirtualAlloc(0, v7, 0x3000u, 4u), (v9 = v8) == 0) )
    {
      LastError = GetLastError();
      IsBandBitLockerManaged = LastError;
      if ( LastError > 0 )
        IsBandBitLockerManaged = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_25;
    }
    if ( ReadFile(v4, v8, v7, &NumberOfBytesRead, 0) )
    {
      v12 = FveCheckVolumeTypeEx(v9, NumberOfBytesRead, 0);
      if ( (unsigned int)(v12 - 2) <= 1 )
      {
        IsBandBitLockerManaged = 0;
      }
      else if ( v12 == 1 )
      {
        IsBandBitLockerManaged = FvepCheckForVolumeControlFiles(v4);
        if ( (IsBandBitLockerManaged & 0x80000000) != 0 )
        {
LABEL_24:
          VirtualFree(v9, 0, 0x8000u);
          goto LABEL_25;
        }
      }
      else
      {
        IsBandBitLockerManaged = 1;
      }
      v11 = IsBandBitLockerManaged == 0;
    }
    else
    {
      v10 = GetLastError();
      IsBandBitLockerManaged = v10;
      if ( v10 > 0 )
        IsBandBitLockerManaged = (unsigned __int16)v10 | 0x80070000;
      if ( IsBandBitLockerManaged != -2144272384 )
        goto LABEL_24;
      IsBandBitLockerManaged = 0;
      v11 = 1;
    }
    FvepSetVolumeEncryptedCached(pszSrc, v11);
    goto LABEL_24;
  }
  v5 = GetLastError();
  IsBandBitLockerManaged = v5;
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return IsBandBitLockerManaged;
}

```

## disassembly

```asm
0x1801eeaf8  mov     [rsp-18h+arg_8], rbx
0x1801eeafd  mov     [rsp-18h+arg_10], rsi
0x1801eeb02  push    rbp
0x1801eeb03  push    rdi
0x1801eeb04  push    r14
0x1801eeb06  mov     rbp, rsp
0x1801eeb09  sub     rsp, 70h
0x1801eeb0d  mov     rax, cs:__security_cookie
0x1801eeb14  xor     rax, rsp
0x1801eeb17  mov     [rbp+var_8], rax
0x1801eeb1b  xor     eax, eax
0x1801eeb1d  lea     rdx, [rbp+var_30]
0x1801eeb21  xorps   xmm0, xmm0
0x1801eeb24  mov     [rbp+var_10], rax
0x1801eeb28  movups  [rbp+OutBuffer], xmm0
0x1801eeb2c  mov     [rbp+BytesReturned], eax
0x1801eeb2f  mov     rsi, rcx
0x1801eeb32  mov     [rbp+NumberOfBytesRead], eax
0x1801eeb35  mov     [rbp+var_30], eax
0x1801eeb38  call    FvepIsVolumeEncryptedCached
0x1801eeb3d  test    eax, eax
0x1801eeb3f  jz      short loc_1801EEB4E
0x1801eeb41  xor     ebx, ebx
0x1801eeb43  cmp     [rbp+var_30], ebx
0x1801eeb46  setz    bl
0x1801eeb49  jmp     loc_1801EECD9
0x1801eeb4e  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1801eeb57  mov     r8d, 3; dwShareMode
0x1801eeb5d  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1801eeb65  xor     r9d, r9d; lpSecurityAttributes
0x1801eeb68  mov     edx, 80000000h; dwDesiredAccess
0x1801eeb6d  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801eeb72  mov     rcx, rsi; lpFileName
0x1801eeb75  call    cs:__imp_CreateFileW
0x1801eeb7b  mov     rdi, rax
0x1801eeb7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801eeb82  jnz     short loc_1801EEBA2
0x1801eeb84  call    cs:__imp_GetLastError
0x1801eeb8a  mov     ebx, eax
0x1801eeb8c  test    eax, eax
0x1801eeb8e  jle     loc_1801EECD9
0x1801eeb94  movzx   ebx, ax
0x1801eeb97  or      ebx, 80070000h
0x1801eeb9d  jmp     loc_1801EECD9
0x1801eeba2  mov     rcx, rdi; hDevice
0x1801eeba5  call    FvepIsBandBitLockerManaged
0x1801eebaa  mov     ebx, eax
0x1801eebac  test    eax, eax
0x1801eebae  jz      loc_1801EECD0
0x1801eebb4  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1801eebbd  lea     rax, [rbp+BytesReturned]
0x1801eebc1  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x1801eebc6  xor     r9d, r9d; nInBufferSize
0x1801eebc9  lea     rax, [rbp+OutBuffer]
0x1801eebcd  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1801eebd5  xor     r8d, r8d; lpInBuffer
0x1801eebd8  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x1801eebdd  mov     edx, 70000h; dwIoControlCode
0x1801eebe2  mov     rcx, rdi; hDevice
0x1801eebe5  call    cs:__imp_DeviceIoControl
0x1801eebeb  test    eax, eax
0x1801eebed  jnz     short loc_1801EEC0D
0x1801eebef  call    cs:__imp_GetLastError
0x1801eebf5  mov     ebx, eax
0x1801eebf7  test    eax, eax
0x1801eebf9  jle     loc_1801EECD0
0x1801eebff  movzx   ebx, ax
0x1801eec02  or      ebx, 80070000h
0x1801eec08  jmp     loc_1801EECD0
0x1801eec0d  mov     eax, dword ptr [rbp+var_10+4]
0x1801eec10  xor     ecx, ecx; lpAddress
0x1801eec12  add     eax, 1FFh
0x1801eec17  mov     r8d, 3000h; flAllocationType
0x1801eec1d  and     eax, 0FFFFFE00h
0x1801eec22  mov     edx, eax; dwSize
0x1801eec24  lea     r9d, [rcx+4]; flProtect
0x1801eec28  mov     ebx, eax
0x1801eec2a  call    cs:__imp_VirtualAlloc
0x1801eec30  mov     r14, rax
0x1801eec33  test    rax, rax
0x1801eec36  jz      short loc_1801EEBEF
0x1801eec38  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801eec3c  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1801eec45  mov     r8d, ebx; nNumberOfBytesToRead
0x1801eec48  mov     rdx, rax; lpBuffer
0x1801eec4b  mov     rcx, rdi; hFile
0x1801eec4e  call    cs:__imp_ReadFile
0x1801eec54  test    eax, eax
0x1801eec56  jnz     short loc_1801EEC7C
0x1801eec58  call    cs:__imp_GetLastError
0x1801eec5e  mov     ebx, eax
0x1801eec60  test    eax, eax
0x1801eec62  jle     short loc_1801EEC6D
0x1801eec64  movzx   ebx, ax
0x1801eec67  or      ebx, 80070000h
0x1801eec6d  cmp     ebx, 80310000h
0x1801eec73  jnz     short loc_1801EECBF
0x1801eec75  xor     ebx, ebx
0x1801eec77  lea     edx, [rbx+1]
0x1801eec7a  jmp     short loc_1801EECB7
0x1801eec7c  mov     edx, [rbp+NumberOfBytesRead]
0x1801eec7f  xor     r8d, r8d
0x1801eec82  mov     rcx, r14
0x1801eec85  call    FveCheckVolumeTypeEx
0x1801eec8a  lea     ecx, [rax-2]
0x1801eec8d  cmp     ecx, 1
0x1801eec90  jbe     short loc_1801EECAE
0x1801eec92  cmp     eax, 1
0x1801eec95  jnz     short loc_1801EECA7
0x1801eec97  mov     rcx, rdi; hDevice
0x1801eec9a  call    FvepCheckForVolumeControlFiles
0x1801eec9f  mov     ebx, eax
0x1801eeca1  test    eax, eax
0x1801eeca3  js      short loc_1801EECBF
0x1801eeca5  jmp     short loc_1801EECB0
0x1801eeca7  mov     ebx, 1
0x1801eecac  jmp     short loc_1801EECB0
0x1801eecae  xor     ebx, ebx
0x1801eecb0  xor     edx, edx
0x1801eecb2  test    ebx, ebx
0x1801eecb4  setz    dl
0x1801eecb7  mov     rcx, rsi; pszSrc
0x1801eecba  call    FvepSetVolumeEncryptedCached
0x1801eecbf  xor     edx, edx; dwSize
0x1801eecc1  mov     r8d, 8000h; dwFreeType
0x1801eecc7  mov     rcx, r14; lpAddress
0x1801eecca  call    cs:__imp_VirtualFree
0x1801eecd0  mov     rcx, rdi; hObject
0x1801eecd3  call    cs:__imp_CloseHandle
0x1801eecd9  mov     eax, ebx
0x1801eecdb  mov     rcx, [rbp+var_8]
0x1801eecdf  xor     rcx, rsp; StackCookie
0x1801eece2  call    __security_check_cookie
0x1801eece7  lea     r11, [rsp+70h+var_s0]
0x1801eecec  mov     rbx, [r11+28h]
0x1801eecf0  mov     rsi, [r11+30h]
0x1801eecf4  mov     rsp, r11
0x1801eecf7  pop     r14
0x1801eecf9  pop     rdi
0x1801eecfa  pop     rbp
0x1801eecfb  retn
```
