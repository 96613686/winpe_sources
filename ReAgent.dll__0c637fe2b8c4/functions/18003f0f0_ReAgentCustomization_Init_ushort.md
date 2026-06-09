# ReAgentCustomization::Init(ushort *)

- ea: `0x18003f0f0`
- end: `0x18003f2b8`
- name: `?Init@ReAgentCustomization@@QEAAKPEAG@Z`
- size: `456`
- prototype: `__int64 __fastcall(ReAgentCustomization *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x1800224f0`
- `0x180026158`

## callees

- `0x1800059fc`
- `0x18003f0f0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003f188`
- `KERNEL32!GetLastError` at `0x18003f1c9`
- `KERNEL32!GetLastError` at `0x18003f24b`
- `KERNEL32!GetLastError` at `0x18003f188`
- `KERNEL32!GetLastError` at `0x18003f1c9`
- `KERNEL32!GetLastError` at `0x18003f24b`
- `KERNEL32!HeapAlloc` at `0x18003f1ea`
- `KERNEL32!HeapAlloc` at `0x18003f1ea`
- `KERNEL32!GetProcessHeap` at `0x18003f1d6`
- `KERNEL32!GetProcessHeap` at `0x18003f1d6`
- `KERNEL32!ReadFile` at `0x18003f241`
- `KERNEL32!ReadFile` at `0x18003f241`
- `KERNEL32!GetFileSize` at `0x18003f1ba`
- `KERNEL32!GetFileSize` at `0x18003f1ba`
- `KERNEL32!CreateFileW` at `0x18003f143`
- `KERNEL32!CreateFileW` at `0x18003f179`
- `KERNEL32!CreateFileW` at `0x18003f143`
- `KERNEL32!CreateFileW` at `0x18003f179`
- `KERNEL32!CloseHandle` at `0x18003f27b`
- `KERNEL32!CloseHandle` at `0x18003f27b`

## string_xrefs

- `0x18003f259`: `failed to read file`
- `0x18003f208`: `base\diagnosis\srt\reagent2\reagent\parserex.cpp`
- `0x18003f212`: `ReAgentCustomization::Init %s (0x%x) in file %S line %d`
- `0x18003f288`: `ReAgentCustomization::Init failed: 0x%x`

## pseudocode

```c
__int64 __fastcall ReAgentCustomization::Init(ReAgentCustomization *this, unsigned __int16 *a2)
{
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD FileSize; // eax
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v9; // r8
  void *v10; // rax
  const wchar_t *v11; // r8
  DWORD v12; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-30h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL || (FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 2u, 0), FileW != (HANDLE)-1LL) )
  {
    FileSize = GetFileSize(FileW, 0);
    v7 = FileSize;
    *(_DWORD *)this = FileSize;
    if ( FileSize == -1 )
    {
      LastError = GetLastError();
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v9 = v7 + 2;
      LastError = 8;
      v10 = HeapAlloc(ProcessHeap, 8u, v9);
      *((_QWORD *)this + 1) = v10;
      if ( v10 )
      {
        if ( ReadFile(FileW, v10, *(_DWORD *)this, &NumberOfBytesRead, 0) )
        {
          LastError = 0;
          if ( NumberOfBytesRead != *(_DWORD *)this )
            LastError = 13;
          goto LABEL_15;
        }
        v12 = GetLastError();
        LODWORD(dwFlagsAndAttributes) = 354;
        v11 = L"failed to read file";
        LastError = v12;
      }
      else
      {
        LODWORD(dwFlagsAndAttributes) = 351;
        v11 = L"failed to allocate memory";
      }
      UnattendLogW(
        2,
        L"ReAgentCustomization::Init %s (0x%x) in file %S line %d",
        v11,
        LastError,
        "base\\diagnosis\\srt\\reagent2\\reagent\\parserex.cpp",
        dwFlagsAndAttributes);
    }
LABEL_15:
    CloseHandle(FileW);
    goto LABEL_16;
  }
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    if ( !ReAgentError )
      ReAgentError = 24;
    goto LABEL_17;
  }
LABEL_16:
  if ( LastError )
LABEL_17:
    UnattendLogW(1, L"ReAgentCustomization::Init failed: 0x%x", LastError);
  return LastError;
}

```

## disassembly

```asm
0x18003f0f0  mov     [rsp+arg_10], rbx
0x18003f0f5  mov     [rsp+arg_18], rsi
0x18003f0fa  push    rdi
0x18003f0fb  sub     rsp, 50h
0x18003f0ff  mov     rax, cs:__security_cookie
0x18003f106  xor     rax, rsp
0x18003f109  mov     [rsp+58h+var_10], rax
0x18003f10e  mov     rbx, rdx
0x18003f111  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003f11a  mov     rsi, rcx
0x18003f11d  mov     dword ptr [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18003f125  mov     rcx, rbx; lpFileName
0x18003f128  mov     [rsp+58h+NumberOfBytesRead], 0
0x18003f130  xor     r9d, r9d; lpSecurityAttributes
0x18003f133  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f13b  xor     r8d, r8d; dwShareMode
0x18003f13e  mov     edx, 80000000h; dwDesiredAccess
0x18003f143  call    cs:__imp_CreateFileW
0x18003f149  mov     rdi, rax
0x18003f14c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f150  jnz     short loc_18003F1B5
0x18003f152  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18003f15b  xor     r9d, r9d; lpSecurityAttributes
0x18003f15e  mov     dword ptr [rsp+58h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x18003f166  xor     r8d, r8d; dwShareMode
0x18003f169  mov     edx, 80000000h; dwDesiredAccess
0x18003f16e  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18003f176  mov     rcx, rbx; lpFileName
0x18003f179  call    cs:__imp_CreateFileW
0x18003f17f  mov     rdi, rax
0x18003f182  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003f186  jnz     short loc_18003F1B5
0x18003f188  call    cs:__imp_GetLastError
0x18003f18e  mov     ebx, eax
0x18003f190  cmp     eax, 2
0x18003f193  jnz     loc_18003F281
0x18003f199  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x18003f1a0  jnz     loc_18003F285
0x18003f1a6  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 18h; _ReAgentErrorCodes ReAgentError
0x18003f1b0  jmp     loc_18003F285
0x18003f1b5  xor     edx, edx; lpFileSizeHigh
0x18003f1b7  mov     rcx, rdi; hFile
0x18003f1ba  call    cs:__imp_GetFileSize
0x18003f1c0  mov     ebx, eax
0x18003f1c2  mov     [rsi], ebx
0x18003f1c4  cmp     eax, 0FFFFFFFFh
0x18003f1c7  jnz     short loc_18003F1D6
0x18003f1c9  call    cs:__imp_GetLastError
0x18003f1cf  mov     ebx, eax
0x18003f1d1  jmp     loc_18003F272
0x18003f1d6  call    cs:__imp_GetProcessHeap
0x18003f1dc  lea     r8, [rbx+2]; dwBytes
0x18003f1e0  mov     ebx, 8
0x18003f1e5  mov     edx, ebx; dwFlags
0x18003f1e7  mov     rcx, rax; hHeap
0x18003f1ea  call    cs:__imp_HeapAlloc
0x18003f1f0  mov     [rsi+8], rax
0x18003f1f4  test    rax, rax
0x18003f1f7  jnz     short loc_18003F22A
0x18003f1f9  mov     dword ptr [rsp+58h+dwFlagsAndAttributes], 15Fh
0x18003f201  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x18003f208  lea     rax, aBaseDiagnosisS; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003f20f  mov     r9d, ebx
0x18003f212  lea     rdx, aReagentcustomi; "ReAgentCustomization::Init %s (0x%x) in"...
0x18003f219  mov     qword ptr [rsp+58h+dwCreationDisposition], rax
0x18003f21e  mov     ecx, 2
0x18003f223  call    UnattendLogW
0x18003f228  jmp     short loc_18003F272
0x18003f22a  mov     r8d, [rsi]; nNumberOfBytesToRead
0x18003f22d  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003f232  mov     rdx, rax; lpBuffer
0x18003f235  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x18003f23e  mov     rcx, rdi; hFile
0x18003f241  call    cs:__imp_ReadFile
0x18003f247  test    eax, eax
0x18003f249  jnz     short loc_18003F264
0x18003f24b  call    cs:__imp_GetLastError
0x18003f251  mov     dword ptr [rsp+58h+dwFlagsAndAttributes], 162h
0x18003f259  lea     r8, aFailedToReadFi; "failed to read file"
0x18003f260  mov     ebx, eax
0x18003f262  jmp     short loc_18003F208
0x18003f264  mov     eax, [rsi]
0x18003f266  xor     ebx, ebx
0x18003f268  cmp     [rsp+58h+NumberOfBytesRead], eax
0x18003f26c  lea     ecx, [rbx+0Dh]
0x18003f26f  cmovnz  ebx, ecx
0x18003f272  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003f276  jz      short loc_18003F281
0x18003f278  mov     rcx, rdi; hObject
0x18003f27b  call    cs:__imp_CloseHandle
0x18003f281  test    ebx, ebx
0x18003f283  jz      short loc_18003F299
0x18003f285  mov     r8d, ebx
0x18003f288  lea     rdx, aReagentcustomi_0; "ReAgentCustomization::Init failed: 0x%x"
0x18003f28f  mov     ecx, 1
0x18003f294  call    UnattendLogW
0x18003f299  mov     eax, ebx
0x18003f29b  mov     rcx, [rsp+58h+var_10]
0x18003f2a0  xor     rcx, rsp; StackCookie
0x18003f2a3  call    __security_check_cookie
0x18003f2a8  mov     rbx, [rsp+58h+arg_10]
0x18003f2ad  mov     rsi, [rsp+58h+arg_18]
0x18003f2b2  add     rsp, 50h
0x18003f2b6  pop     rdi
0x18003f2b7  retn
```
