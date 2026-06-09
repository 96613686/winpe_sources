# File::QueryUsn(void *,ushort const *)

- ea: `0x180027728`
- end: `0x1800279c1`
- name: `?QueryUsn@File@@SA_JPEAXPEBG@Z`
- size: `665`
- prototype: `__int64 __fastcall(HANDLE hDevice, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180017d44`
- `0x1800274b0`

## callees

- `0x1800197d4`
- `0x180027728`
- `0x1800279c8`
- `0x1800ff944`
- `0x1800ff9a0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180027839`
- `KERNEL32!DeviceIoControl` at `0x18002794a`
- `KERNEL32!DeviceIoControl` at `0x180027839`
- `KERNEL32!DeviceIoControl` at `0x18002794a`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x18002789e`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x18002789e`
- `KERNEL32!CreateFileW` at `0x1800277a8`
- `KERNEL32!CreateFileW` at `0x1800277a8`
- `KERNEL32!HeapReAlloc` at `0x180027906`
- `KERNEL32!HeapReAlloc` at `0x180027906`
- `KERNEL32!CloseHandle` at `0x1800279a4`
- `KERNEL32!CloseHandle` at `0x1800279a4`
- `KERNEL32!GetProcessHeap` at `0x1800277e4`
- `KERNEL32!GetProcessHeap` at `0x1800278f2`
- `KERNEL32!GetProcessHeap` at `0x180027982`
- `KERNEL32!GetProcessHeap` at `0x1800277e4`
- `KERNEL32!GetProcessHeap` at `0x1800278f2`
- `KERNEL32!GetProcessHeap` at `0x180027982`
- `KERNEL32!HeapAlloc` at `0x1800277f5`
- `KERNEL32!HeapAlloc` at `0x1800277f5`
- `KERNEL32!GetLastError` at `0x180027847`
- `KERNEL32!GetLastError` at `0x1800278a8`
- `KERNEL32!GetLastError` at `0x180027847`
- `KERNEL32!GetLastError` at `0x1800278a8`
- `KERNEL32!HeapFree` at `0x180027990`
- `KERNEL32!HeapFree` at `0x180027990`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall File::QueryUsn(HANDLE hDevice, LPCWSTR lpFileName, unsigned int a3, const char *a4)
{
  HANDLE v4; // r15
  __int64 v5; // rsi
  HANDLE FileW; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // r14
  wil *v12; // rcx
  unsigned int v13; // r8d
  const char *v14; // r9
  DWORD v15; // ebx
  unsigned int v16; // ebx
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  HANDLE v20; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-58h]
  __int64 v23; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-30h]
  __int64 v25; // [rsp+50h] [rbp-28h]
  const std::exception *v26; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD MaximumComponentLength; // [rsp+80h] [rbp+8h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v30; // [rsp+98h] [rbp+20h]

  v25 = -2;
  try
  {
    v4 = hDevice;
    v24 = 0;
    v30 = 0;
    BytesReturned = 0;
    v5 = -1;
    v23 = -1;
    if ( hDevice == (HANDLE)-1LL )
    {
      if ( !lpFileName )
        wil::details::in1diag3::Throw_Win32(retaddr, 0, a3, a4, dwCreationDisposition);
      FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v23,
        FileW);
      v5 = v23;
      v4 = (HANDLE)v23;
      if ( ((v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x950, v7, v8);
    }
    v9 = nOutBufferSize;
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 0xCu, v9);
    v30 = v11;
    if ( !DeviceIoControl(v4, 0x900EBu, 0, 0, v11, nOutBufferSize, &BytesReturned, 0) )
    {
      if ( GetLastError() != 122 )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x95B, v13, v14);
      MaximumComponentLength = 0;
      if ( GetVolumeInformationByHandleW(v4, 0, 0, 0, &MaximumComponentLength, 0, 0, 0) )
      {
        v15 = MaximumComponentLength;
      }
      else
      {
        GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"File::QueryUsn",
          2403,
          (unsigned int)"GetVolumeInformationByHandleW failed [%d]");
        v15 = 260;
        MaximumComponentLength = 260;
      }
      v16 = 2 * v15 + 64;
      LODWORD(nOutBufferSize) = v16;
      v17 = GetProcessHeap();
      v11 = HeapReAlloc(v17, 0xCu, v11, v16);
      v30 = v11;
      if ( !DeviceIoControl(v4, 0x900EBu, 0, 0, v11, nOutBufferSize, &BytesReturned, 0) )
        wil::details::in1diag3::Throw_GetLastError(retaddr, (void *)0x96C, v18, v19);
    }
    v24 = v11[3];
  }
  catch ( const std::exception *v26 )
  {
    wil::ResultFromCaughtException(v12);
    (*(void (__fastcall **)(const std::exception *, _QWORD))(*(_QWORD *)v26 + 8LL))(v26, *(_QWORD *)v26);
    AslLogCallPrintf(1, (unsigned int)"File::QueryUsn", 2421, (unsigned int)"Exception: 0x%08x %s");
    v5 = v23;
    v11 = v30;
  }
  catch ( ... )
  {
    wil::ResultFromCaughtException(v12);
    AslLogCallPrintf(1, (unsigned int)"File::QueryUsn", 2426, (unsigned int)"Exception: [0x%08x]");
    v5 = v23;
    v11 = v30;
  }
  if ( v11 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v11);
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v5);
  return v24;
}

```

## disassembly

```asm
0x180027728  mov     r11, rsp
0x18002772b  push    rsi
0x18002772c  push    r14
0x18002772e  push    r15
0x180027730  sub     rsp, 60h
0x180027734  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18002773c  mov     [r11+10h], rbx
0x180027740  mov     rax, rdx
0x180027743  mov     r15, rcx
0x180027746  mov     [rsp+78h+var_30], 0
0x18002774f  mov     [rsp+78h+arg_18], 0
0x18002775b  mov     dword ptr [r11+18h], 0
0x180027763  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180027767  mov     [rsp+78h+var_38], rsi
0x18002776c  cmp     rcx, rsi
0x18002776f  jnz     short loc_1800277DE
0x180027771  test    rax, rax
0x180027774  jnz     short loc_180027780
0x180027776  mov     rcx, [rsp+78h]; this
0x18002777b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180027780  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180027789  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180027791  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180027799  xor     r9d, r9d; lpSecurityAttributes
0x18002779c  mov     edx, 80000000h; dwDesiredAccess
0x1800277a1  lea     r8d, [r9+7]; dwShareMode
0x1800277a5  mov     rcx, rax; lpFileName
0x1800277a8  call    cs:__imp_CreateFileW
0x1800277ae  mov     rdx, rax
0x1800277b1  lea     rcx, [rsp+78h+var_38]
0x1800277b6  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800277bb  mov     rsi, [rsp+78h+var_38]
0x1800277c0  mov     r15, rsi
0x1800277c3  lea     rax, [rsi+1]
0x1800277c7  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800277cd  jnz     short loc_1800277DE
0x1800277cf  mov     rcx, [rsp+78h]; this
0x1800277d4  mov     edx, 950h; void *
0x1800277d9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800277de  mov     ebx, cs:nOutBufferSize
0x1800277e4  call    cs:__imp_GetProcessHeap
0x1800277ea  mov     r8d, ebx; dwBytes
0x1800277ed  mov     edx, 0Ch; dwFlags
0x1800277f2  mov     rcx, rax; hHeap
0x1800277f5  call    cs:__imp_HeapAlloc
0x1800277fb  mov     r14, rax
0x1800277fe  mov     [rsp+78h+arg_18], rax
0x180027806  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18002780f  lea     rax, [rsp+78h+BytesReturned]
0x180027817  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18002781c  mov     ecx, cs:nOutBufferSize
0x180027822  mov     [rsp+78h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x180027826  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18002782b  xor     r9d, r9d; nInBufferSize
0x18002782e  xor     r8d, r8d; lpInBuffer
0x180027831  mov     edx, 900EBh; dwIoControlCode
0x180027836  mov     rcx, r15; hDevice
0x180027839  call    cs:__imp_DeviceIoControl
0x18002783f  test    eax, eax
0x180027841  jnz     loc_180027963
0x180027847  call    cs:__imp_GetLastError
0x18002784d  cmp     eax, 7Ah ; 'z'
0x180027850  jz      short loc_180027861
0x180027852  mov     rcx, [rsp+78h]; this
0x180027857  mov     edx, 95Bh; void *
0x18002785c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180027861  mov     [rsp+78h+MaximumComponentLength], 0
0x18002786c  mov     dword ptr [rsp+78h+lpOverlapped], 0; nFileSystemNameSize
0x180027874  mov     [rsp+78h+hTemplateFile], 0; lpFileSystemNameBuffer
0x18002787d  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpFileSystemFlags
0x180027886  lea     rax, [rsp+78h+MaximumComponentLength]
0x18002788e  mov     qword ptr [rsp+78h+dwCreationDisposition], rax; lpMaximumComponentLength
0x180027893  xor     r9d, r9d; lpVolumeSerialNumber
0x180027896  xor     r8d, r8d; nVolumeNameSize
0x180027899  xor     edx, edx; lpVolumeNameBuffer
0x18002789b  mov     rcx, r15; hFile
0x18002789e  call    cs:__imp_GetVolumeInformationByHandleW
0x1800278a4  test    eax, eax
0x1800278a6  jnz     short loc_1800278DE
0x1800278a8  call    cs:__imp_GetLastError
0x1800278ae  mov     [rsp+78h+dwCreationDisposition], eax
0x1800278b2  lea     r9, aGetvolumeinfor; "GetVolumeInformationByHandleW failed [%"...
0x1800278b9  mov     r8d, 963h
0x1800278bf  lea     rdx, aFileQueryusn; "File::QueryUsn"
0x1800278c6  mov     ecx, 1
0x1800278cb  call    AslLogCallPrintf
0x1800278d0  mov     ebx, 104h
0x1800278d5  mov     [rsp+78h+MaximumComponentLength], ebx
0x1800278dc  jmp     short loc_1800278E5
0x1800278de  mov     ebx, [rsp+78h+MaximumComponentLength]
0x1800278e5  lea     ebx, ds:40h[rbx*2]
0x1800278ec  mov     cs:nOutBufferSize, ebx
0x1800278f2  call    cs:__imp_GetProcessHeap
0x1800278f8  mov     r9d, ebx; dwBytes
0x1800278fb  mov     r8, r14; lpMem
0x1800278fe  mov     edx, 0Ch; dwFlags
0x180027903  mov     rcx, rax; hHeap
0x180027906  call    cs:__imp_HeapReAlloc
0x18002790c  mov     r14, rax
0x18002790f  mov     [rsp+78h+arg_18], rax
0x180027917  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x180027920  lea     rax, [rsp+78h+BytesReturned]
0x180027928  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18002792d  mov     eax, cs:nOutBufferSize
0x180027933  mov     [rsp+78h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180027937  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18002793c  xor     r9d, r9d; nInBufferSize
0x18002793f  xor     r8d, r8d; lpInBuffer
0x180027942  mov     edx, 900EBh; dwIoControlCode
0x180027947  mov     rcx, r15; hDevice
0x18002794a  call    cs:__imp_DeviceIoControl
0x180027950  test    eax, eax
0x180027952  jnz     short loc_180027963
0x180027954  mov     rcx, [rsp+78h]; this
0x180027959  mov     edx, 96Ch; void *
0x18002795e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180027963  mov     rax, [r14+18h]
0x180027967  mov     [rsp+78h+var_30], rax
0x18002796c  jmp     short loc_18002797D
0x18002796e  jmp     short $+2
0x180027970  mov     rsi, [rsp+78h+var_38]
0x180027975  mov     r14, [rsp+78h+arg_18]
0x18002797d  test    r14, r14
0x180027980  jz      short loc_180027997
0x180027982  call    cs:__imp_GetProcessHeap
0x180027988  mov     rcx, rax; hHeap
0x18002798b  mov     r8, r14; lpMem
0x18002798e  xor     edx, edx; dwFlags
0x180027990  call    cs:__imp_HeapFree
0x180027996  nop
0x180027997  lea     rax, [rsi-1]
0x18002799b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002799f  ja      short loc_1800279AA
0x1800279a1  mov     rcx, rsi; hObject
0x1800279a4  call    cs:__imp_CloseHandle
0x1800279aa  mov     rax, [rsp+78h+var_30]
0x1800279af  mov     rbx, [rsp+78h+arg_8]
0x1800279b7  add     rsp, 60h
0x1800279bb  pop     r15
0x1800279bd  pop     r14
0x1800279bf  pop     rsi
0x1800279c0  retn
```
