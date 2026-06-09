# FvepIsVolumeEncryptedNoDriverTest

- ea: `0x180051660`
- end: `0x180051864`
- name: `FvepIsVolumeEncryptedNoDriverTest`
- size: `516`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180050500`

## callees

- `0x180050c04`
- `0x180051274`
- `0x18005156c`
- `0x180051660`
- `0x18005186c`
- `0x180051a44`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x180051832`
- `KERNEL32!VirtualFree` at `0x180051832`
- `KERNEL32!VirtualAlloc` at `0x180051792`
- `KERNEL32!VirtualAlloc` at `0x180051792`
- `KERNEL32!GetLastError` at `0x1800516ec`
- `KERNEL32!GetLastError` at `0x180051757`
- `KERNEL32!GetLastError` at `0x1800517c0`
- `KERNEL32!GetLastError` at `0x1800516ec`
- `KERNEL32!GetLastError` at `0x180051757`
- `KERNEL32!GetLastError` at `0x1800517c0`
- `KERNEL32!ReadFile` at `0x1800517b6`
- `KERNEL32!ReadFile` at `0x1800517b6`
- `KERNEL32!CreateFileW` at `0x1800516dd`
- `KERNEL32!CreateFileW` at `0x1800516dd`
- `KERNEL32!CloseHandle` at `0x18005183b`
- `KERNEL32!CloseHandle` at `0x18005183b`
- `KERNEL32!DeviceIoControl` at `0x18005174d`
- `KERNEL32!DeviceIoControl` at `0x18005174d`

## pseudocode

```c
__int64 __fastcall FvepIsVolumeEncryptedNoDriverTest(STRSAFE_PCNZWCH psz)
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
  if ( (unsigned int)FvepIsVolumeEncryptedCached(psz) )
    return 1;
  FileW = CreateFileW(psz, 0x80000000, 3u, 0, 3u, 0x20000000u, 0);
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
    FvepSetVolumeEncryptedCached(psz, v11);
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
0x180051660  mov     [rsp-18h+arg_8], rbx
0x180051665  mov     [rsp-18h+arg_10], rsi
0x18005166a  push    rbp
0x18005166b  push    rdi
0x18005166c  push    r14
0x18005166e  mov     rbp, rsp
0x180051671  sub     rsp, 70h
0x180051675  mov     rax, cs:__security_cookie
0x18005167c  xor     rax, rsp
0x18005167f  mov     [rbp+var_8], rax
0x180051683  xor     eax, eax
0x180051685  lea     rdx, [rbp+var_30]
0x180051689  xorps   xmm0, xmm0
0x18005168c  mov     [rbp+var_10], rax
0x180051690  movups  [rbp+OutBuffer], xmm0
0x180051694  mov     [rbp+BytesReturned], eax
0x180051697  mov     rsi, rcx
0x18005169a  mov     [rbp+NumberOfBytesRead], eax
0x18005169d  mov     [rbp+var_30], eax
0x1800516a0  call    FvepIsVolumeEncryptedCached
0x1800516a5  test    eax, eax
0x1800516a7  jz      short loc_1800516B6
0x1800516a9  xor     ebx, ebx
0x1800516ab  cmp     [rbp+var_30], ebx
0x1800516ae  setz    bl
0x1800516b1  jmp     loc_180051841
0x1800516b6  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x1800516bf  mov     r8d, 3; dwShareMode
0x1800516c5  mov     [rsp+70h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1800516cd  xor     r9d, r9d; lpSecurityAttributes
0x1800516d0  mov     edx, 80000000h; dwDesiredAccess
0x1800516d5  mov     [rsp+70h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800516da  mov     rcx, rsi; lpFileName
0x1800516dd  call    cs:__imp_CreateFileW
0x1800516e3  mov     rdi, rax
0x1800516e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800516ea  jnz     short loc_18005170A
0x1800516ec  call    cs:__imp_GetLastError
0x1800516f2  mov     ebx, eax
0x1800516f4  test    eax, eax
0x1800516f6  jle     loc_180051841
0x1800516fc  movzx   ebx, ax
0x1800516ff  or      ebx, 80070000h
0x180051705  jmp     loc_180051841
0x18005170a  mov     rcx, rdi; hDevice
0x18005170d  call    FvepIsBandBitLockerManaged
0x180051712  mov     ebx, eax
0x180051714  test    eax, eax
0x180051716  jz      loc_180051838
0x18005171c  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180051725  lea     rax, [rbp+BytesReturned]
0x180051729  mov     [rsp+70h+hTemplateFile], rax; lpBytesReturned
0x18005172e  xor     r9d, r9d; nInBufferSize
0x180051731  lea     rax, [rbp+OutBuffer]
0x180051735  mov     [rsp+70h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x18005173d  xor     r8d, r8d; lpInBuffer
0x180051740  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; lpOutBuffer
0x180051745  mov     edx, 70000h; dwIoControlCode
0x18005174a  mov     rcx, rdi; hDevice
0x18005174d  call    cs:__imp_DeviceIoControl
0x180051753  test    eax, eax
0x180051755  jnz     short loc_180051775
0x180051757  call    cs:__imp_GetLastError
0x18005175d  mov     ebx, eax
0x18005175f  test    eax, eax
0x180051761  jle     loc_180051838
0x180051767  movzx   ebx, ax
0x18005176a  or      ebx, 80070000h
0x180051770  jmp     loc_180051838
0x180051775  mov     eax, dword ptr [rbp+var_10+4]
0x180051778  xor     ecx, ecx; lpAddress
0x18005177a  add     eax, 1FFh
0x18005177f  mov     r8d, 3000h; flAllocationType
0x180051785  and     eax, 0FFFFFE00h
0x18005178a  mov     edx, eax; dwSize
0x18005178c  lea     r9d, [rcx+4]; flProtect
0x180051790  mov     ebx, eax
0x180051792  call    cs:__imp_VirtualAlloc
0x180051798  mov     r14, rax
0x18005179b  test    rax, rax
0x18005179e  jz      short loc_180051757
0x1800517a0  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800517a4  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x1800517ad  mov     r8d, ebx; nNumberOfBytesToRead
0x1800517b0  mov     rdx, rax; lpBuffer
0x1800517b3  mov     rcx, rdi; hFile
0x1800517b6  call    cs:__imp_ReadFile
0x1800517bc  test    eax, eax
0x1800517be  jnz     short loc_1800517E4
0x1800517c0  call    cs:__imp_GetLastError
0x1800517c6  mov     ebx, eax
0x1800517c8  test    eax, eax
0x1800517ca  jle     short loc_1800517D5
0x1800517cc  movzx   ebx, ax
0x1800517cf  or      ebx, 80070000h
0x1800517d5  cmp     ebx, 80310000h
0x1800517db  jnz     short loc_180051827
0x1800517dd  xor     ebx, ebx
0x1800517df  lea     edx, [rbx+1]
0x1800517e2  jmp     short loc_18005181F
0x1800517e4  mov     edx, [rbp+NumberOfBytesRead]
0x1800517e7  xor     r8d, r8d
0x1800517ea  mov     rcx, r14
0x1800517ed  call    FveCheckVolumeTypeEx
0x1800517f2  lea     ecx, [rax-2]
0x1800517f5  cmp     ecx, 1
0x1800517f8  jbe     short loc_180051816
0x1800517fa  cmp     eax, 1
0x1800517fd  jnz     short loc_18005180F
0x1800517ff  mov     rcx, rdi; hDevice
0x180051802  call    FvepCheckForVolumeControlFiles
0x180051807  mov     ebx, eax
0x180051809  test    eax, eax
0x18005180b  js      short loc_180051827
0x18005180d  jmp     short loc_180051818
0x18005180f  mov     ebx, 1
0x180051814  jmp     short loc_180051818
0x180051816  xor     ebx, ebx
0x180051818  xor     edx, edx
0x18005181a  test    ebx, ebx
0x18005181c  setz    dl
0x18005181f  mov     rcx, rsi; psz
0x180051822  call    FvepSetVolumeEncryptedCached
0x180051827  xor     edx, edx; dwSize
0x180051829  mov     r8d, 8000h; dwFreeType
0x18005182f  mov     rcx, r14; lpAddress
0x180051832  call    cs:__imp_VirtualFree
0x180051838  mov     rcx, rdi; hObject
0x18005183b  call    cs:__imp_CloseHandle
0x180051841  mov     eax, ebx
0x180051843  mov     rcx, [rbp+var_8]
0x180051847  xor     rcx, rsp; StackCookie
0x18005184a  call    __security_check_cookie
0x18005184f  lea     r11, [rsp+70h+var_s0]
0x180051854  mov     rbx, [r11+28h]
0x180051858  mov     rsi, [r11+30h]
0x18005185c  mov     rsp, r11
0x18005185f  pop     r14
0x180051861  pop     rdi
0x180051862  pop     rbp
0x180051863  retn
```
