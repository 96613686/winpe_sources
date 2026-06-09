# UalOpenSession

- ea: `0x140086ae4`
- end: `0x140086c73`
- name: `UalOpenSession`
- size: `399`
- prototype: `signed int()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400246b0`

## callees

- `0x140002c73`
- `0x140086ae4`
- `0x140086ec0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140086b1c`
- `KERNEL32!LoadLibraryExW` at `0x140086b1c`
- `KERNEL32!FreeLibrary` at `0x140086be5`
- `KERNEL32!FreeLibrary` at `0x140086be5`
- `KERNEL32!GetLastError` at `0x140086b34`
- `KERNEL32!GetLastError` at `0x140086bc3`
- `KERNEL32!GetLastError` at `0x140086b34`
- `KERNEL32!GetLastError` at `0x140086bc3`
- `KERNEL32!GetProcAddress` at `0x140086b5f`
- `KERNEL32!GetProcAddress` at `0x140086b85`
- `KERNEL32!GetProcAddress` at `0x140086bab`
- `KERNEL32!GetProcAddress` at `0x140086b5f`
- `KERNEL32!GetProcAddress` at `0x140086b85`
- `KERNEL32!GetProcAddress` at `0x140086bab`

## string_xrefs

- `0x140086b0f`: `ualapi.dll`

## pseudocode

```c
signed int UalOpenSession()
{
  HMODULE Library; // rax
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // [rsp+20h] [rbp-2C8h] BYREF
  __int128 v5; // [rsp+24h] [rbp-2C4h]
  _BYTE v6[668]; // [rsp+34h] [rbp-2B4h] BYREF

  if ( ualapiModule )
    goto LABEL_11;
  Library = LoadLibraryExW(L"ualapi.dll", 0, 0x800u);
  ualapiModule = Library;
  if ( !Library )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  fnUalInstrument = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(Library, "UalInstrument");
  if ( fnUalInstrument )
  {
    fnUalStart = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStart");
    if ( fnUalStart )
    {
      fnUalStop = (int (*)(struct tagUAL_DATA_BLOB *))GetProcAddress(ualapiModule, "UalStop");
      if ( fnUalStop )
      {
LABEL_11:
        memset_0(v6, 0, sizeof(v6));
        v4 = 688;
        v5 = SumGuid_FAX;
        return ((__int64 (__fastcall *)(int *))fnUalStart)(&v4);
      }
    }
  }
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  FreeLibrary(ualapiModule);
  result = v3;
  ualapiModule = 0;
  fnUalInstrument = 0;
  fnUalStart = 0;
  fnUalStop = 0;
  return result;
}

```

## disassembly

```asm
0x140086ae4  push    rbx
0x140086ae6  sub     rsp, 2E0h
0x140086aed  mov     rax, cs:__security_cookie
0x140086af4  xor     rax, rsp
0x140086af7  mov     [rsp+2E8h+var_18], rax
0x140086aff  cmp     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x140086b07  jnz     loc_140086C21
0x140086b0d  xor     edx, edx; hFile
0x140086b0f  lea     rcx, aUalapiDll; "ualapi.dll"
0x140086b16  mov     r8d, 800h; dwFlags
0x140086b1c  call    cs:__imp_LoadLibraryExW
0x140086b23  nop     dword ptr [rax+rax+00h]
0x140086b28  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * ualapiModule
0x140086b2f  test    rax, rax
0x140086b32  jnz     short loc_140086B55
0x140086b34  call    cs:__imp_GetLastError
0x140086b3b  nop     dword ptr [rax+rax+00h]
0x140086b40  test    eax, eax
0x140086b42  jle     loc_140086C59
0x140086b48  movzx   eax, ax
0x140086b4b  or      eax, 80070000h
0x140086b50  jmp     loc_140086C59
0x140086b55  lea     rdx, aUalinstrument; "UalInstrument"
0x140086b5c  mov     rcx, rax; hModule
0x140086b5f  call    cs:__imp_GetProcAddress
0x140086b66  nop     dword ptr [rax+rax+00h]
0x140086b6b  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x140086b72  test    rax, rax
0x140086b75  jz      short loc_140086BC3
0x140086b77  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x140086b7e  lea     rdx, aUalstart; "UalStart"
0x140086b85  call    cs:__imp_GetProcAddress
0x140086b8c  nop     dword ptr [rax+rax+00h]
0x140086b91  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x140086b98  test    rax, rax
0x140086b9b  jz      short loc_140086BC3
0x140086b9d  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hModule
0x140086ba4  lea     rdx, aUalstop; "UalStop"
0x140086bab  call    cs:__imp_GetProcAddress
0x140086bb2  nop     dword ptr [rax+rax+00h]
0x140086bb7  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, rax; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x140086bbe  test    rax, rax
0x140086bc1  jnz     short loc_140086C21
0x140086bc3  call    cs:__imp_GetLastError
0x140086bca  nop     dword ptr [rax+rax+00h]
0x140086bcf  mov     ebx, eax
0x140086bd1  test    eax, eax
0x140086bd3  jle     short loc_140086BDE
0x140086bd5  movzx   ebx, ax
0x140086bd8  or      ebx, 80070000h
0x140086bde  mov     rcx, cs:?ualapiModule@@3PEAUHINSTANCE__@@EA; hLibModule
0x140086be5  call    cs:__imp_FreeLibrary
0x140086bec  nop     dword ptr [rax+rax+00h]
0x140086bf1  mov     eax, ebx
0x140086bf3  mov     cs:?ualapiModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * ualapiModule
0x140086bfe  mov     cs:?fnUalInstrument@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalInstrument)(tagUAL_DATA_BLOB *)
0x140086c09  mov     cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x140086c14  mov     cs:?fnUalStop@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA, 0; long (*fnUalStop)(tagUAL_DATA_BLOB *)
0x140086c1f  jmp     short loc_140086C59
0x140086c21  xor     edx, edx; Val
0x140086c23  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x140086c28  mov     r8d, 29Ch; Size
0x140086c2e  call    memset_0
0x140086c33  movups  xmm0, cs:SumGuid_FAX
0x140086c3a  mov     rax, cs:?fnUalStart@@3P6AJPEAUtagUAL_DATA_BLOB@@@ZEA; long (*fnUalStart)(tagUAL_DATA_BLOB *)
0x140086c41  lea     rcx, [rsp+2E8h+var_2C8]
0x140086c46  mov     [rsp+2E8h+var_2C8], 2B0h
0x140086c4e  movdqu  [rsp+2E8h+var_2C4], xmm0
0x140086c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140086c59  mov     rcx, [rsp+2E8h+var_18]
0x140086c61  xor     rcx, rsp; StackCookie
0x140086c64  call    __security_check_cookie
0x140086c69  add     rsp, 2E0h
0x140086c70  pop     rbx
0x140086c71  retn
```
