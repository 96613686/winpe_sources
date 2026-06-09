# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18001bc08`
- end: `0x18001be55`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `589`
- prototype: `__int64 __fastcall(__int64, const void *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a5c8`

## callees

- `0x1800185f8`
- `0x18001bc08`
- `0x180026e30`
- `0x180027910`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x18001bcde`
- `KERNEL32!GetTempFileNameW` at `0x18001bcfe`
- `KERNEL32!GetTempFileNameW` at `0x18001bcde`
- `KERNEL32!GetTempFileNameW` at `0x18001bcfe`
- `KERNEL32!GetTempPathW` at `0x18001bc5a`
- `KERNEL32!GetTempPathW` at `0x18001bc5a`
- `KERNEL32!GetLastError` at `0x18001bd08`
- `KERNEL32!GetLastError` at `0x18001bd55`
- `KERNEL32!GetLastError` at `0x18001bd96`
- `KERNEL32!GetLastError` at `0x18001bd08`
- `KERNEL32!GetLastError` at `0x18001bd55`
- `KERNEL32!GetLastError` at `0x18001bd96`
- `KERNEL32!CloseHandle` at `0x18001bda9`
- `KERNEL32!CloseHandle` at `0x18001bda9`
- `KERNEL32!CreateFileW` at `0x18001bd47`
- `KERNEL32!CreateFileW` at `0x18001bd47`
- `KERNEL32!DeleteFileW` at `0x18001be22`
- `KERNEL32!DeleteFileW` at `0x18001be22`
- `KERNEL32!WriteFile` at `0x18001bd87`
- `KERNEL32!WriteFile` at `0x18001bd87`

## string_xrefs

- `0x18001bdc2`: `TdhLoadManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const void *a2,
        DWORD a3,
        __int64 a4)
{
  __int64 v7; // rbx
  DWORD TempPathW; // eax
  WCHAR *v9; // rcx
  int v10; // edx
  WCHAR v11; // ax
  __int64 result; // rax
  signed int v13; // ecx
  HANDLE FileW; // rax
  void *v15; // rsi
  signed int v16; // eax
  signed int v17; // ebx
  signed int LastError; // eax
  int v19; // eax
  __int64 (__fastcall *v20)(WCHAR *); // rax
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 (__fastcall *v23)(WCHAR *); // [rsp+60h] [rbp-A8h]
  __int64 v24; // [rsp+68h] [rbp-A0h]
  __int64 v25; // [rsp+70h] [rbp-98h]
  WCHAR TempFileName[264]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+288h] [rbp+180h] BYREF

  v25 = -2;
  v7 = 260;
  TempPathW = GetTempPathW(0x104u, Buffer);
  if ( !TempPathW || TempPathW + 1 > 0x104 )
  {
    v9 = Buffer;
    v10 = 0;
    do
    {
      if ( v7 == -2147483386 )
        break;
      v11 = *(WCHAR *)((char *)v9 + (char *)L"." - (char *)Buffer);
      if ( !v11 )
        break;
      *v9++ = v11;
      --v7;
    }
    while ( v7 );
    if ( !v7 )
    {
      --v9;
      v10 = -2147024774;
    }
    *v9 = 0;
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
  {
    FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v15 = FileW;
    if ( FileW )
    {
      v17 = 0;
      NumberOfBytesWritten[0] = 0;
      if ( !WriteFile(FileW, a2, a3, NumberOfBytesWritten, 0) )
      {
        LastError = GetLastError();
        v17 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v17 = LastError;
      }
      CloseHandle(v15);
    }
    else
    {
      v16 = GetLastError();
      v17 = (unsigned __int16)v16 | 0x80070000;
      if ( v16 <= 0 )
        v17 = v16;
    }
    if ( v17 >= 0 )
    {
      *(_QWORD *)NumberOfBytesWritten = TempFileName;
      v22[0] = a4;
      v22[1] = "TdhLoadManifest";
      v23 = 0;
      LOBYTE(v24) = 0;
      if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22)
        && (!(_BYTE)v24
          ? (v20 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v22),
             v19 = v20(TempFileName))
          : (v19 = v23(TempFileName)),
            v19) )
      {
        v17 = (unsigned __int16)v19 | 0x80070000;
        if ( v19 <= 0 )
          v17 = v19;
      }
      else
      {
        v17 = 0;
      }
      DeleteFileW(TempFileName);
    }
    return (unsigned int)v17;
  }
  else
  {
    v13 = GetLastError();
    result = (unsigned __int16)v13 | 0x80070000;
    if ( v13 <= 0 )
      return (unsigned int)v13;
  }
  return result;
}

```

## disassembly

```asm
0x18001bc08  mov     rax, rsp
0x18001bc0b  push    rbp
0x18001bc0c  push    rdi
0x18001bc0d  push    r12
0x18001bc0f  push    r14
0x18001bc11  push    r15
0x18001bc13  lea     rbp, [rax-3C8h]
0x18001bc1a  sub     rsp, 4A0h
0x18001bc21  mov     [rsp+4C0h+var_458], 0FFFFFFFFFFFFFFFEh
0x18001bc2a  mov     [rax+8], rbx
0x18001bc2e  mov     [rax+20h], rsi
0x18001bc32  mov     rax, cs:__security_cookie
0x18001bc39  xor     rax, rsp
0x18001bc3c  mov     [rbp+3C0h+var_30], rax
0x18001bc43  mov     r15, r9
0x18001bc46  mov     r14d, r8d
0x18001bc49  mov     rdi, rdx
0x18001bc4c  lea     rdx, [rbp+3C0h+Buffer]; lpBuffer
0x18001bc53  mov     ebx, 104h
0x18001bc58  mov     ecx, ebx; nBufferLength
0x18001bc5a  call    cs:__imp_GetTempPathW
0x18001bc60  xor     r12d, r12d
0x18001bc63  test    eax, eax
0x18001bc65  jz      short loc_18001BC6D
0x18001bc67  inc     eax
0x18001bc69  cmp     eax, ebx
0x18001bc6b  jbe     short loc_18001BCC8
0x18001bc6d  lea     rcx, [rbp+3C0h+Buffer]
0x18001bc74  mov     edx, r12d
0x18001bc77  lea     r8, PathName; "."
0x18001bc7e  lea     rax, [rbp+3C0h+Buffer]
0x18001bc85  sub     r8, rax
0x18001bc88  lea     rax, [rbx+7FFFFEFAh]
0x18001bc8f  test    rax, rax
0x18001bc92  jz      short loc_18001BCAB
0x18001bc94  movzx   eax, word ptr [r8+rcx]
0x18001bc99  test    ax, ax
0x18001bc9c  jz      short loc_18001BCAB
0x18001bc9e  mov     [rcx], ax
0x18001bca1  add     rcx, 2
0x18001bca5  sub     rbx, 1
0x18001bca9  jnz     short loc_18001BC88
0x18001bcab  test    rbx, rbx
0x18001bcae  jnz     short loc_18001BCB9
0x18001bcb0  sub     rcx, 2
0x18001bcb4  mov     edx, 8007007Ah
0x18001bcb9  mov     [rcx], r12w
0x18001bcbd  test    edx, edx
0x18001bcbf  jns     short loc_18001BCC8
0x18001bcc1  mov     eax, edx
0x18001bcc3  jmp     loc_18001BE2A
0x18001bcc8  lea     r9, [rsp+4C0h+TempFileName]; lpTempFileName
0x18001bccd  xor     r8d, r8d; uUnique
0x18001bcd0  lea     rdx, PrefixString; "xpf"
0x18001bcd7  lea     rcx, [rbp+3C0h+Buffer]; lpPathName
0x18001bcde  call    cs:__imp_GetTempFileNameW
0x18001bce4  test    eax, eax
0x18001bce6  jnz     short loc_18001BD22
0x18001bce8  lea     r9, [rsp+4C0h+TempFileName]; lpTempFileName
0x18001bced  xor     r8d, r8d; uUnique
0x18001bcf0  lea     rdx, PrefixString; "xpf"
0x18001bcf7  lea     rcx, PathName; "."
0x18001bcfe  call    cs:__imp_GetTempFileNameW
0x18001bd04  test    eax, eax
0x18001bd06  jnz     short loc_18001BD22
0x18001bd08  call    cs:__imp_GetLastError
0x18001bd0e  mov     ecx, eax
0x18001bd10  movzx   eax, ax
0x18001bd13  or      eax, 80070000h
0x18001bd18  test    ecx, ecx
0x18001bd1a  cmovle  eax, ecx
0x18001bd1d  jmp     loc_18001BE2A
0x18001bd22  mov     [rsp+4C0h+hTemplateFile], r12; hTemplateFile
0x18001bd27  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001bd2f  mov     [rsp+4C0h+dwCreationDisposition], 2; dwCreationDisposition
0x18001bd37  xor     r9d, r9d; lpSecurityAttributes
0x18001bd3a  xor     r8d, r8d; dwShareMode
0x18001bd3d  mov     edx, 40000000h; dwDesiredAccess
0x18001bd42  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x18001bd47  call    cs:__imp_CreateFileW
0x18001bd4d  mov     rsi, rax
0x18001bd50  test    rax, rax
0x18001bd53  jnz     short loc_18001BD6C
0x18001bd55  call    cs:__imp_GetLastError
0x18001bd5b  movzx   ebx, ax
0x18001bd5e  mov     edi, 80070000h
0x18001bd63  or      ebx, edi
0x18001bd65  test    eax, eax
0x18001bd67  cmovle  ebx, eax
0x18001bd6a  jmp     short loc_18001BDAF
0x18001bd6c  mov     ebx, r12d
0x18001bd6f  mov     [rsp+4C0h+NumberOfBytesWritten], r12d
0x18001bd74  mov     qword ptr [rsp+4C0h+dwCreationDisposition], r12; lpOverlapped
0x18001bd79  lea     r9, [rsp+4C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001bd7e  mov     r8d, r14d; nNumberOfBytesToWrite
0x18001bd81  mov     rdx, rdi; lpBuffer
0x18001bd84  mov     rcx, rsi; hFile
0x18001bd87  call    cs:__imp_WriteFile
0x18001bd8d  mov     edi, 80070000h
0x18001bd92  test    eax, eax
0x18001bd94  jnz     short loc_18001BDA6
0x18001bd96  call    cs:__imp_GetLastError
0x18001bd9c  movzx   ebx, ax
0x18001bd9f  or      ebx, edi
0x18001bda1  test    eax, eax
0x18001bda3  cmovle  ebx, eax
0x18001bda6  mov     rcx, rsi; hObject
0x18001bda9  call    cs:__imp_CloseHandle
0x18001bdaf  test    ebx, ebx
0x18001bdb1  js      short loc_18001BE28
0x18001bdb3  lea     rax, [rsp+4C0h+TempFileName]
0x18001bdb8  mov     qword ptr [rsp+4C0h+NumberOfBytesWritten], rax
0x18001bdbd  mov     [rsp+4C0h+var_478], r15
0x18001bdc2  lea     rax, aTdhloadmanifes_0; "TdhLoadManifest"
0x18001bdc9  mov     [rsp+4C0h+var_470], rax
0x18001bdce  mov     [rsp+4C0h+var_468], r12
0x18001bdd3  mov     byte ptr [rsp+4C0h+var_460], r12b
0x18001bdd8  lea     rcx, [rsp+4C0h+var_478]
0x18001bddd  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001bde2  test    rax, rax
0x18001bde5  jz      short loc_18001BE1A
0x18001bde7  cmp     byte ptr [rsp+4C0h+var_460], r12b
0x18001bdec  jz      short loc_18001BDF5
0x18001bdee  mov     rax, [rsp+4C0h+var_468]
0x18001bdf3  jmp     short loc_18001BDFF
0x18001bdf5  lea     rcx, [rsp+4C0h+var_478]
0x18001bdfa  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001bdff  lea     rcx, [rsp+4C0h+TempFileName]
0x18001be04  call    cs:__guard_dispatch_icall_fptr
0x18001be0a  test    eax, eax
0x18001be0c  jz      short loc_18001BE1A
0x18001be0e  movzx   ebx, ax
0x18001be11  or      ebx, edi
0x18001be13  test    eax, eax
0x18001be15  cmovle  ebx, eax
0x18001be18  jmp     short loc_18001BE1D
0x18001be1a  mov     ebx, r12d
0x18001be1d  lea     rcx, [rsp+4C0h+TempFileName]; lpFileName
0x18001be22  call    cs:__imp_DeleteFileW
0x18001be28  mov     eax, ebx
0x18001be2a  mov     rcx, [rbp+3C0h+var_30]
0x18001be31  xor     rcx, rsp; StackCookie
0x18001be34  call    __security_check_cookie
0x18001be39  lea     r11, [rsp+4C0h+var_20]
0x18001be41  mov     rbx, [r11+30h]
0x18001be45  mov     rsi, [r11+48h]
0x18001be49  mov     rsp, r11
0x18001be4c  pop     r15
0x18001be4e  pop     r14
0x18001be50  pop     r12
0x18001be52  pop     rdi
0x18001be53  pop     rbp
0x18001be54  retn
```
