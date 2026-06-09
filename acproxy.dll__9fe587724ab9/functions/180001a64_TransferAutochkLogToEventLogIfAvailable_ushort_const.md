# TransferAutochkLogToEventLogIfAvailable(ushort const *)

- ea: `0x180001a64`
- end: `0x180001c1c`
- name: `?TransferAutochkLogToEventLogIfAvailable@@YAHPEBG@Z`
- size: `440`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180001700`

## callees

- `0x180001a64`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001bda`
- `ntdll!RtlFreeHeap` at `0x180001bda`
- `ntdll!RtlAllocateHeap` at `0x180001b2d`
- `ntdll!RtlAllocateHeap` at `0x180001b2d`
- `KERNEL32!ReadFile` at `0x180001b57`
- `KERNEL32!ReadFile` at `0x180001b57`
- `KERNEL32!CreateFileW` at `0x180001b01`
- `KERNEL32!CreateFileW` at `0x180001b01`
- `KERNEL32!Sleep` at `0x180001acf`
- `KERNEL32!Sleep` at `0x180001acf`
- `KERNEL32!GetLastError` at `0x180001ab1`
- `KERNEL32!GetLastError` at `0x180001ab1`
- `KERNEL32!CloseHandle` at `0x180001bf1`
- `KERNEL32!CloseHandle` at `0x180001bf1`
- `ADVAPI32!RegisterEventSourceW` at `0x180001aa3`
- `ADVAPI32!RegisterEventSourceW` at `0x180001aa3`
- `ADVAPI32!DeregisterEventSource` at `0x180001bff`
- `ADVAPI32!DeregisterEventSource` at `0x180001bff`
- `ADVAPI32!ReportEventW` at `0x180001baa`
- `ADVAPI32!ReportEventW` at `0x180001baa`

## pseudocode

```c
__int64 __fastcall TransferAutochkLogToEventLogIfAvailable(LPCWSTR lpFileName)
{
  unsigned int v1; // edi
  HANDLE v3; // rbx
  DWORD LastError; // eax
  __int64 FileW; // rsi
  WCHAR *Heap; // rax
  unsigned int v7; // edi
  DWORD NumberOfBytesRead; // [rsp+78h] [rbp+28h] BYREF
  LPCWSTR Strings; // [rsp+80h] [rbp+30h] BYREF

  v1 = 0;
  NumberOfBytesRead = 0;
  Strings = 0;
  while ( 1 )
  {
    if ( v1 >= 0xA )
    {
      FileW = -1;
      v7 = 0;
      v3 = 0;
      goto LABEL_14;
    }
    v3 = RegisterEventSourceW(0, L"Autochk");
    if ( v3 )
      break;
    LastError = GetLastError();
    if ( LastError == 1722 || LastError == 1717 )
    {
      Sleep(0x3E8u);
      ++v1;
    }
    else
    {
      v1 = 10;
    }
  }
  FileW = (__int64)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == -1
    || (NumberOfBytesRead = 0x8000,
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x8000u),
        (Strings = Heap) == 0)
    || (v7 = ReadFile((HANDLE)FileW, Heap, NumberOfBytesRead - 2, &NumberOfBytesRead, 0), v7 == 1)
    && (*((_BYTE *)Strings + NumberOfBytesRead) = 0,
        *((_BYTE *)Strings + NumberOfBytesRead + 1) = 0,
        !ReportEventW(v3, 4u, 0, 0x472u, 0, 1u, 0, &Strings, 0)) )
  {
    v7 = 0;
  }
LABEL_14:
  if ( Strings )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Strings);
    Strings = 0;
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( v3 )
    DeregisterEventSource(v3);
  return v7;
}

```

## disassembly

```asm
0x180001a64  mov     [rsp-18h+arg_0], rbx
0x180001a69  mov     [rsp-18h+arg_18], rsi
0x180001a6e  push    rbp
0x180001a6f  push    rdi
0x180001a70  push    r15
0x180001a72  mov     rbp, rsp
0x180001a75  sub     rsp, 50h
0x180001a79  xor     edi, edi
0x180001a7b  mov     [rbp+NumberOfBytesRead], 0
0x180001a82  mov     rsi, rcx
0x180001a85  mov     [rbp+Strings], 0
0x180001a8d  lea     r15d, [rdi+1]
0x180001a91  cmp     edi, 0Ah
0x180001a94  jnb     loc_180001BB8
0x180001a9a  lea     rdx, SourceName; "Autochk"
0x180001aa1  xor     ecx, ecx; lpUNCServerName
0x180001aa3  call    cs:__imp_RegisterEventSourceW
0x180001aa9  mov     rbx, rax
0x180001aac  test    rax, rax
0x180001aaf  jnz     short loc_180001ADA
0x180001ab1  call    cs:__imp_GetLastError
0x180001ab7  cmp     eax, 6BAh
0x180001abc  jz      short loc_180001ACA
0x180001abe  cmp     eax, 6B5h
0x180001ac3  jz      short loc_180001ACA
0x180001ac5  lea     edi, [rbx+0Ah]
0x180001ac8  jmp     short loc_180001A91
0x180001aca  mov     ecx, 3E8h; dwMilliseconds
0x180001acf  call    cs:__imp_Sleep
0x180001ad5  add     edi, r15d
0x180001ad8  jmp     short loc_180001A91
0x180001ada  mov     [rsp+50h+hTemplateFile], 0; hTemplateFile
0x180001ae3  xor     r9d, r9d; lpSecurityAttributes
0x180001ae6  mov     [rsp+50h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180001aee  mov     r8d, r15d; dwShareMode
0x180001af1  mov     edx, 80000000h; dwDesiredAccess
0x180001af6  mov     [rsp+50h+dwCreationDisposition], 3; dwCreationDisposition
0x180001afe  mov     rcx, rsi; lpFileName
0x180001b01  call    cs:__imp_CreateFileW
0x180001b07  mov     rsi, rax
0x180001b0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001b0e  jz      loc_180001BB4
0x180001b14  mov     r8d, 8000h; Size
0x180001b1a  xor     edx, edx; Flags
0x180001b1c  mov     [rbp+NumberOfBytesRead], r8d
0x180001b20  mov     rcx, gs:60h
0x180001b29  mov     rcx, [rcx+30h]; HeapHandle
0x180001b2d  call    cs:__imp_RtlAllocateHeap
0x180001b33  mov     [rbp+Strings], rax
0x180001b37  test    rax, rax
0x180001b3a  jz      short loc_180001BB4
0x180001b3c  mov     r8d, [rbp+NumberOfBytesRead]
0x180001b40  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180001b44  add     r8d, 0FFFFFFFEh; nNumberOfBytesToRead
0x180001b48  mov     qword ptr [rsp+50h+dwCreationDisposition], 0; lpOverlapped
0x180001b51  mov     rdx, rax; lpBuffer
0x180001b54  mov     rcx, rsi; hFile
0x180001b57  call    cs:__imp_ReadFile
0x180001b5d  mov     edi, eax
0x180001b5f  cmp     eax, r15d
0x180001b62  jnz     short loc_180001BC0
0x180001b64  mov     ecx, [rbp+NumberOfBytesRead]
0x180001b67  xor     r8d, r8d; wCategory
0x180001b6a  mov     rax, [rbp+Strings]
0x180001b6e  mov     r9d, 472h; dwEventID
0x180001b74  mov     [rsp+50h+lpRawData], r8; lpRawData
0x180001b79  lea     edx, [r8+4]; wType
0x180001b7d  mov     byte ptr [rcx+rax], 0
0x180001b81  mov     ecx, [rbp+NumberOfBytesRead]
0x180001b84  mov     rax, [rbp+Strings]
0x180001b88  inc     ecx
0x180001b8a  mov     byte ptr [rcx+rax], 0
0x180001b8e  lea     rax, [rbp+Strings]
0x180001b92  mov     [rsp+50h+lpStrings], rax; lpStrings
0x180001b97  mov     rcx, rbx; hEventLog
0x180001b9a  mov     dword ptr [rsp+50h+hTemplateFile], r8d; dwDataSize
0x180001b9f  mov     word ptr [rsp+50h+dwFlagsAndAttributes], r15w; wNumStrings
0x180001ba5  mov     qword ptr [rsp+50h+dwCreationDisposition], r8; lpUserSid
0x180001baa  call    cs:__imp_ReportEventW
0x180001bb0  test    eax, eax
0x180001bb2  jnz     short loc_180001BC0
0x180001bb4  xor     edi, edi
0x180001bb6  jmp     short loc_180001BC0
0x180001bb8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180001bbc  xor     edi, edi
0x180001bbe  xor     ebx, ebx
0x180001bc0  cmp     [rbp+Strings], 0
0x180001bc5  jz      short loc_180001BE8
0x180001bc7  mov     rcx, gs:60h
0x180001bd0  xor     edx, edx; Flags
0x180001bd2  mov     r8, [rbp+Strings]; P
0x180001bd6  mov     rcx, [rcx+30h]; HeapHandle
0x180001bda  call    cs:__imp_RtlFreeHeap
0x180001be0  mov     [rbp+Strings], 0
0x180001be8  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180001bec  jz      short loc_180001BF7
0x180001bee  mov     rcx, rsi; hObject
0x180001bf1  call    cs:__imp_CloseHandle
0x180001bf7  test    rbx, rbx
0x180001bfa  jz      short loc_180001C05
0x180001bfc  mov     rcx, rbx; hEventLog
0x180001bff  call    cs:__imp_DeregisterEventSource
0x180001c05  lea     r11, [rsp+50h+var_s0]
0x180001c0a  mov     eax, edi
0x180001c0c  mov     rbx, [r11+20h]
0x180001c10  mov     rsi, [r11+38h]
0x180001c14  mov     rsp, r11
0x180001c17  pop     r15
0x180001c19  pop     rdi
0x180001c1a  pop     rbp
0x180001c1b  retn
```
