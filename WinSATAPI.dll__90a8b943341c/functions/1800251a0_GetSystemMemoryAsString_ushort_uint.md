# GetSystemMemoryAsString(ushort *,uint)

- ea: `0x1800251a0`
- end: `0x180025346`
- name: `?GetSystemMemoryAsString@@YAJPEAGI@Z`
- size: `422`
- prototype: `__int64 __fastcall(PWSTR pszBuf, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800108f4`
- `0x18001115c`

## callees

- `0x180010814`
- `0x180013e69`
- `0x1800251a0`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800252f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002530f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800252f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002530f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025225`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025225`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002529f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002529f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025239`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002527f`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18002527f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002520a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002520a`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800252d5`
- `SHLWAPI!StrFormatByteSizeW` at `0x1800252d5`

## string_xrefs

- `0x180025203`: `Shlwapi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSystemMemoryAsString(PWSTR pszBuf)
{
  FARPROC ProcAddress; // rbx
  HMODULE LibraryW; // rax
  DWORDLONG ullTotalPhys; // rcx
  int v5; // ebx
  LONGLONG qdw; // [rsp+38h] [rbp-39h] BYREF
  HMODULE hLibModule[5]; // [rsp+40h] [rbp-31h] BYREF
  unsigned int (__fastcall *v9)(LONGLONG *); // [rsp+68h] [rbp-9h]
  __int64 v10; // [rsp+70h] [rbp-1h]
  struct _MEMORYSTATUSEX Buffer; // [rsp+78h] [rbp+7h] BYREF

  v10 = -2;
  *pszBuf = 0;
  qdw = 0;
  memset(hLibModule, 0, sizeof(hLibModule));
  v9 = 0;
  ProcAddress = 0;
  mlib::KernelAPIs::LoadLibraryW((mlib::KernelAPIs *)hLibModule);
  LibraryW = LoadLibraryW(L"Shlwapi.dll");
  if ( !LibraryW || (ProcAddress = GetProcAddress(LibraryW, "StrFormatByteSizeEx")) == 0 )
    GetLastError();
  if ( v9 && v9(&qdw) )
  {
    ullTotalPhys = qdw << 10;
    goto LABEL_9;
  }
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    ullTotalPhys = Buffer.ullTotalPhys;
LABEL_9:
    qdw = ullTotalPhys;
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(DWORDLONG, __int64, PWSTR))ProcAddress)(ullTotalPhys, 1, pszBuf);
      if ( v5 >= 0 )
      {
LABEL_14:
        if ( hLibModule[0] )
          FreeLibrary(hLibModule[0]);
        return (unsigned int)v5;
      }
    }
    else
    {
      SetLastError(0x32u);
    }
    v5 = -2147467259;
    if ( StrFormatByteSizeW(qdw, pszBuf, 0x10u) )
      v5 = 0;
    goto LABEL_14;
  }
  if ( hLibModule[0] )
    FreeLibrary(hLibModule[0]);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800251a0  mov     rax, rsp
0x1800251a3  push    rbp
0x1800251a4  lea     rbp, [rax-5Fh]
0x1800251a8  sub     rsp, 0C0h
0x1800251af  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800251b7  mov     [rax+10h], rbx
0x1800251bb  mov     [rax+18h], rdi
0x1800251bf  mov     [rax+20h], r14
0x1800251c3  mov     rax, cs:__security_cookie
0x1800251ca  xor     rax, rsp
0x1800251cd  mov     [rbp+57h+var_10], rax
0x1800251d1  mov     rdi, rcx
0x1800251d4  xor     r14d, r14d
0x1800251d7  mov     [rcx], r14w
0x1800251db  mov     [rbp+57h+qdw], r14
0x1800251df  mov     [rbp+57h+hLibModule], r14
0x1800251e3  mov     [rbp+57h+var_80], r14
0x1800251e7  mov     [rbp+57h+var_78], r14
0x1800251eb  mov     [rbp+57h+var_70], r14
0x1800251ef  mov     [rbp+57h+var_68], r14
0x1800251f3  mov     [rbp+57h+var_60], r14
0x1800251f7  mov     ebx, r14d
0x1800251fa  lea     rcx, [rbp+57h+hLibModule]; this
0x1800251fe  call    ?LoadLibraryW@KernelAPIs@mlib@@QEAAKXZ; mlib::KernelAPIs::LoadLibraryW(void)
0x180025203  lea     rcx, aShlwapiDll_0; "Shlwapi.dll"
0x18002520a  call    cs:__imp_LoadLibraryW
0x180025211  nop     dword ptr [rax+rax+00h]
0x180025216  test    rax, rax
0x180025219  jz      short loc_180025239
0x18002521b  lea     rdx, aStrformatbytes; "StrFormatByteSizeEx"
0x180025222  mov     rcx, rax; hModule
0x180025225  call    cs:__imp_GetProcAddress
0x18002522c  nop     dword ptr [rax+rax+00h]
0x180025231  mov     rbx, rax
0x180025234  test    rax, rax
0x180025237  jnz     short loc_180025245
0x180025239  call    cs:__imp_GetLastError
0x180025240  nop     dword ptr [rax+rax+00h]
0x180025245  mov     rax, [rbp+57h+var_60]
0x180025249  test    rax, rax
0x18002524c  jz      short loc_180025265
0x18002524e  lea     rcx, [rbp+57h+qdw]
0x180025252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025257  test    eax, eax
0x180025259  jz      short loc_180025265
0x18002525b  mov     rcx, [rbp+57h+qdw]
0x18002525f  shl     rcx, 0Ah
0x180025263  jmp     short loc_180025293
0x180025265  xor     edx, edx; Val
0x180025267  lea     r8d, [rdx+40h]; Size
0x18002526b  lea     rcx, [rbp+57h+Buffer]; void *
0x18002526f  call    memset_0
0x180025274  mov     [rbp+57h+Buffer.dwLength], 40h ; '@'
0x18002527b  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x18002527f  call    cs:__imp_GlobalMemoryStatusEx
0x180025286  nop     dword ptr [rax+rax+00h]
0x18002528b  test    eax, eax
0x18002528d  jz      short loc_180025306
0x18002528f  mov     rcx, [rbp+57h+Buffer.ullTotalPhys]
0x180025293  mov     [rbp+57h+qdw], rcx
0x180025297  test    rbx, rbx
0x18002529a  jnz     short loc_1800252AD
0x18002529c  lea     ecx, [rbx+32h]; dwErrCode
0x18002529f  call    cs:__imp_SetLastError
0x1800252a6  nop     dword ptr [rax+rax+00h]
0x1800252ab  jmp     short loc_1800252C8
0x1800252ad  mov     r9d, 10h
0x1800252b3  mov     r8, rdi
0x1800252b6  lea     edx, [r9-0Fh]
0x1800252ba  mov     rax, rbx
0x1800252bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252c2  mov     ebx, eax
0x1800252c4  test    eax, eax
0x1800252c6  jns     short loc_1800252ED
0x1800252c8  mov     r8d, 10h; cchBuf
0x1800252ce  mov     rdx, rdi; pszBuf
0x1800252d1  mov     rcx, [rbp+57h+qdw]; qdw
0x1800252d5  call    cs:__imp_StrFormatByteSizeW
0x1800252dc  nop     dword ptr [rax+rax+00h]
0x1800252e1  mov     ebx, 80004005h
0x1800252e6  test    rax, rax
0x1800252e9  cmovnz  ebx, r14d
0x1800252ed  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x1800252f1  test    rcx, rcx
0x1800252f4  jz      short loc_180025302
0x1800252f6  call    cs:__imp_FreeLibrary
0x1800252fd  nop     dword ptr [rax+rax+00h]
0x180025302  mov     eax, ebx
0x180025304  jmp     short loc_180025320
0x180025306  mov     rcx, [rbp+57h+hLibModule]; hLibModule
0x18002530a  test    rcx, rcx
0x18002530d  jz      short loc_18002531B
0x18002530f  call    cs:__imp_FreeLibrary
0x180025316  nop     dword ptr [rax+rax+00h]
0x18002531b  mov     eax, 80004005h
0x180025320  mov     rcx, [rbp+57h+var_10]
0x180025324  xor     rcx, rsp; StackCookie
0x180025327  call    __security_check_cookie
0x18002532c  lea     r11, [rsp+0C0h+var_s0]
0x180025334  mov     rbx, [r11+18h]
0x180025338  mov     rdi, [r11+20h]
0x18002533c  mov     r14, [r11+28h]
0x180025340  mov     rsp, r11
0x180025343  pop     rbp
0x180025344  retn
```
