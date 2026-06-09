# RunToCompletionAsyncOperationImpl::CreateProcessAsCurrentUser(void)

- ea: `0x180019ba8`
- end: `0x180019d60`
- name: `?CreateProcessAsCurrentUser@RunToCompletionAsyncOperationImpl@@AEAAJXZ`
- size: `440`
- prototype: `__int64 __fastcall(RunToCompletionAsyncOperationImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019d90`

## callees

- `0x18000399c`
- `0x180003cc4`
- `0x18000831c`
- `0x180019584`
- `0x180019b08`
- `0x180019ba8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019cf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019c82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180019ca9`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180019ceb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180019ceb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019d35`

## pseudocode

```c
__int64 __fastcall RunToCompletionAsyncOperationImpl::CreateProcessAsCurrentUser(
        RunToCompletionAsyncOperationImpl *this)
{
  unsigned __int16 *v2; // rax
  HSTRING v3; // rcx
  unsigned __int16 *v4; // rbx
  PCWSTR v5; // rdi
  PCWSTR v6; // rax
  int v7; // edi
  HSTRING v8; // rcx
  const WCHAR *lpCurrentDirectory; // r14
  WCHAR *v10; // rdi
  const WCHAR *StringRawBuffer; // rax
  signed int LastError; // eax
  HANDLE hProcess; // rbx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-49h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v17; // [rsp+100h] [rbp+67h] BYREF

  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v2 = (unsigned __int16 *)operator new[](0x10000u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = (HSTRING)*((_QWORD *)this + 23);
  v4 = v2;
  v17 = v2;
  if ( !v3
    || (v5 = WindowsGetStringRawBuffer(v3, 0),
        v6 = WindowsGetStringRawBuffer(*((HSTRING *)this + 22), 0),
        v7 = StringCchPrintfW(v4, 0x8000u, L"\"%ls\" %ls", v6, v5),
        v7 >= 0) )
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    v8 = (HSTRING)*((_QWORD *)this + 24);
    StartupInfo.hStdInput = (HANDLE)*((_QWORD *)this + 44);
    StartupInfo.hStdError = (HANDLE)*((_QWORD *)this + 42);
    StartupInfo.hStdOutput = (HANDLE)*((_QWORD *)this + 38);
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 256;
    if ( v8 )
      lpCurrentDirectory = WindowsGetStringRawBuffer(v8, 0);
    else
      lpCurrentDirectory = 0;
    v10 = (WCHAR *)((unsigned __int64)v4 & -(__int64)(*((_QWORD *)this + 23) != 0));
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 22), 0);
    if ( CreateProcessW(StringRawBuffer, v10, 0, 0, 1, 0, 0, lpCurrentDirectory, &StartupInfo, &ProcessInformation) )
    {
      hProcess = ProcessInformation.hProcess;
      if ( ProcessInformation.hProcess != (HANDLE)*((_QWORD *)this + 29) )
      {
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close((char *)this + 224);
        *((_QWORD *)this + 29) = hProcess;
      }
      if ( ProcessInformation.hThread != (HANDLE)-1LL )
        CloseHandle(ProcessInformation.hThread);
      v7 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
    }
  }
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180019ba8  mov     [rsp-8+arg_8], rbx
0x180019bad  mov     [rsp-8+arg_10], rsi
0x180019bb2  push    rbp
0x180019bb3  push    rdi
0x180019bb4  push    r14
0x180019bb6  lea     rbp, [rsp-47h]
0x180019bbb  sub     rsp, 0E0h
0x180019bc2  mov     rsi, rcx
0x180019bc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019bcc  xorps   xmm0, xmm0
0x180019bcf  xor     eax, eax
0x180019bd1  mov     ecx, 10000h; unsigned __int64
0x180019bd6  mov     qword ptr [rbp+57h+ProcessInformation.dwProcessId], rax
0x180019bda  movups  xmmword ptr [rbp+57h+ProcessInformation.hProcess], xmm0
0x180019bde  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019be3  mov     rcx, [rsi+0B8h]; string
0x180019bea  mov     rbx, rax
0x180019bed  mov     [rbp+57h+arg_0], rax
0x180019bf1  test    rcx, rcx
0x180019bf4  jz      short loc_180019C36
0x180019bf6  xor     edx, edx; length
0x180019bf8  call    cs:__imp_WindowsGetStringRawBuffer
0x180019bfe  mov     rcx, [rsi+0B0h]; string
0x180019c05  xor     edx, edx; length
0x180019c07  mov     rdi, rax
0x180019c0a  call    cs:__imp_WindowsGetStringRawBuffer
0x180019c10  lea     r8, aLsLs; "\"%ls\" %ls"
0x180019c17  mov     qword ptr [rsp+0F0h+bInheritHandles], rdi
0x180019c1c  mov     r9, rax
0x180019c1f  mov     edx, 8000h; unsigned __int64
0x180019c24  mov     rcx, rbx; unsigned __int16 *
0x180019c27  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019c2c  mov     edi, eax
0x180019c2e  test    eax, eax
0x180019c30  js      loc_180019D3D
0x180019c36  mov     edi, 68h ; 'h'
0x180019c3b  lea     rcx, [rbp+57h+StartupInfo]; void *
0x180019c3f  mov     r8d, edi; Size
0x180019c42  xor     edx, edx; Val
0x180019c44  call    memset_0
0x180019c49  mov     rax, [rsi+160h]
0x180019c50  mov     rcx, [rsi+0C0h]; string
0x180019c57  mov     [rbp+57h+StartupInfo.hStdInput], rax
0x180019c5b  mov     rax, [rsi+150h]
0x180019c62  mov     [rbp+57h+StartupInfo.hStdError], rax
0x180019c66  mov     rax, [rsi+130h]
0x180019c6d  mov     [rbp+57h+StartupInfo.hStdOutput], rax
0x180019c71  mov     [rbp+57h+StartupInfo.cb], edi
0x180019c74  mov     [rbp+57h+StartupInfo.dwFlags], 100h
0x180019c7b  test    rcx, rcx
0x180019c7e  jz      short loc_180019C8D
0x180019c80  xor     edx, edx; length
0x180019c82  call    cs:__imp_WindowsGetStringRawBuffer
0x180019c88  mov     r14, rax
0x180019c8b  jmp     short loc_180019C90
0x180019c8d  xor     r14d, r14d
0x180019c90  mov     rax, [rsi+0B8h]
0x180019c97  mov     rcx, [rsi+0B0h]; string
0x180019c9e  neg     rax
0x180019ca1  sbb     rdi, rdi
0x180019ca4  xor     edx, edx; length
0x180019ca6  and     rdi, rbx
0x180019ca9  call    cs:__imp_WindowsGetStringRawBuffer
0x180019caf  lea     rcx, [rbp+57h+ProcessInformation]
0x180019cb3  xor     r9d, r9d; lpThreadAttributes
0x180019cb6  mov     [rsp+0F0h+lpProcessInformation], rcx; lpProcessInformation
0x180019cbb  xor     r8d, r8d; lpProcessAttributes
0x180019cbe  lea     rcx, [rbp+57h+StartupInfo]
0x180019cc2  mov     rdx, rdi; lpCommandLine
0x180019cc5  mov     [rsp+0F0h+lpStartupInfo], rcx; lpStartupInfo
0x180019cca  mov     rcx, rax; lpApplicationName
0x180019ccd  mov     [rsp+0F0h+lpCurrentDirectory], r14; lpCurrentDirectory
0x180019cd2  mov     [rsp+0F0h+lpEnvironment], 0; lpEnvironment
0x180019cdb  mov     [rsp+0F0h+dwCreationFlags], 0; dwCreationFlags
0x180019ce3  mov     [rsp+0F0h+bInheritHandles], 1; bInheritHandles
0x180019ceb  call    cs:__imp_CreateProcessW
0x180019cf1  test    eax, eax
0x180019cf3  jnz     short loc_180019D0B
0x180019cf5  call    cs:__imp_GetLastError
0x180019cfb  test    eax, eax
0x180019cfd  jle     short loc_180019D07
0x180019cff  movzx   eax, ax
0x180019d02  or      eax, 80070000h
0x180019d07  mov     edi, eax
0x180019d09  jmp     short loc_180019D3D
0x180019d0b  mov     rbx, [rbp+57h+ProcessInformation.hProcess]
0x180019d0f  cmp     rbx, [rsi+0E8h]
0x180019d16  jz      short loc_180019D2B
0x180019d18  lea     rcx, [rsi+0E0h]
0x180019d1f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180019d24  mov     [rsi+0E8h], rbx
0x180019d2b  mov     rcx, [rbp+57h+ProcessInformation.hThread]; hObject
0x180019d2f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180019d33  jz      short loc_180019D3B
0x180019d35  call    cs:__imp_CloseHandle
0x180019d3b  xor     edi, edi
0x180019d3d  lea     rcx, [rbp+57h+arg_0]
0x180019d41  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180019d46  lea     r11, [rsp+0F0h+var_10]
0x180019d4e  mov     eax, edi
0x180019d50  mov     rbx, [r11+28h]
0x180019d54  mov     rsi, [r11+30h]
0x180019d58  mov     rsp, r11
0x180019d5b  pop     r14
0x180019d5d  pop     rdi
0x180019d5e  pop     rbp
0x180019d5f  retn
```
