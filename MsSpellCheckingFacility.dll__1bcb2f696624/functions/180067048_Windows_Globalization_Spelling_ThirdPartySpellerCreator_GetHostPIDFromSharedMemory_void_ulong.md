# Windows::Globalization::Spelling::ThirdPartySpellerCreator::GetHostPIDFromSharedMemory(void *,ulong *)

- ea: `0x180067048`
- end: `0x180067150`
- name: `?GetHostPIDFromSharedMemory@ThirdPartySpellerCreator@Spelling@Globalization@Windows@@CAJPEAXPEAK@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800666a4`

## callees

- `0x180061320`
- `0x180066f20`
- `0x180067048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800670d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067107`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067124`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067124`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800670c9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800670c9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800670fd`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800670fd`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180067092`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180067092`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::ThirdPartySpellerCreator::GetHostPIDFromSharedMemory(
        void *a1,
        unsigned int *a2,
        __int64 a3)
{
  HANDLE v4; // rdi
  int FullAppContainerNamedObjectPath; // ebx
  signed int LastError; // eax
  unsigned int *v7; // rsi
  signed int v8; // eax
  signed int v9; // eax
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF

  v4 = 0;
  FullAppContainerNamedObjectPath = ACUtil::GetFullAppContainerNamedObjectPath(
                                      a1,
                                      L"SpellingHostPIDSharedMemory",
                                      a3,
                                      Name);
  if ( FullAppContainerNamedObjectPath < 0 )
    goto LABEL_5;
  v4 = OpenFileMappingW(4u, 0, Name);
  if ( !v4 )
  {
    LastError = GetLastError();
    FullAppContainerNamedObjectPath = LastError;
    if ( LastError > 0 )
      FullAppContainerNamedObjectPath = (unsigned __int16)LastError | 0x80070000;
LABEL_5:
    if ( FullAppContainerNamedObjectPath < 0 )
      return (unsigned int)FullAppContainerNamedObjectPath;
  }
  v7 = (unsigned int *)MapViewOfFile(v4, 4u, 0, 0, 4u);
  if ( v7 )
    goto LABEL_10;
  v8 = GetLastError();
  FullAppContainerNamedObjectPath = v8;
  if ( v8 > 0 )
    FullAppContainerNamedObjectPath = (unsigned __int16)v8 | 0x80070000;
  if ( FullAppContainerNamedObjectPath >= 0 )
  {
LABEL_10:
    *a2 = *v7;
    if ( v7 )
    {
      if ( !UnmapViewOfFile(v7) )
      {
        v9 = GetLastError();
        FullAppContainerNamedObjectPath = v9;
        if ( v9 > 0 )
          FullAppContainerNamedObjectPath = (unsigned __int16)v9 | 0x80070000;
      }
    }
  }
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)FullAppContainerNamedObjectPath;
}

```

## disassembly

```asm
0x180067048  mov     [rsp+arg_10], rbx
0x18006704d  push    rsi
0x18006704e  push    rdi
0x18006704f  push    r14
0x180067051  sub     rsp, 250h
0x180067058  mov     rax, cs:__security_cookie
0x18006705f  xor     rax, rsp
0x180067062  mov     [rsp+268h+var_28], rax
0x18006706a  mov     r14, rdx
0x18006706d  lea     r9, [rsp+268h+Name]; unsigned __int16 *
0x180067072  lea     rdx, aSpellinghostpi; "SpellingHostPIDSharedMemory"
0x180067079  call    ?GetFullAppContainerNamedObjectPath@ACUtil@@SAJPEAXPEBGKPEAG@Z; ACUtil::GetFullAppContainerNamedObjectPath(void *,ushort const *,ulong,ushort *)
0x18006707e  xor     edi, edi
0x180067080  mov     ebx, eax
0x180067082  lea     esi, [rdi+4]
0x180067085  test    eax, eax
0x180067087  js      short loc_1800670B5
0x180067089  lea     r8, [rsp+268h+Name]; lpName
0x18006708e  xor     edx, edx; bInheritHandle
0x180067090  mov     ecx, esi; dwDesiredAccess
0x180067092  call    cs:__imp_OpenFileMappingW
0x180067098  mov     rdi, rax
0x18006709b  test    rax, rax
0x18006709e  jnz     short loc_1800670B9
0x1800670a0  call    cs:__imp_GetLastError
0x1800670a6  mov     ebx, eax
0x1800670a8  test    eax, eax
0x1800670aa  jle     short loc_1800670B5
0x1800670ac  movzx   ebx, ax
0x1800670af  or      ebx, 80070000h
0x1800670b5  test    ebx, ebx
0x1800670b7  js      short loc_18006712A
0x1800670b9  xor     r9d, r9d; dwFileOffsetLow
0x1800670bc  mov     [rsp+268h+dwNumberOfBytesToMap], rsi; dwNumberOfBytesToMap
0x1800670c1  xor     r8d, r8d; dwFileOffsetHigh
0x1800670c4  mov     edx, esi; dwDesiredAccess
0x1800670c6  mov     rcx, rdi; hFileMappingObject
0x1800670c9  call    cs:__imp_MapViewOfFile
0x1800670cf  mov     rsi, rax
0x1800670d2  test    rax, rax
0x1800670d5  jnz     short loc_1800670F0
0x1800670d7  call    cs:__imp_GetLastError
0x1800670dd  mov     ebx, eax
0x1800670df  test    eax, eax
0x1800670e1  jle     short loc_1800670EC
0x1800670e3  movzx   ebx, ax
0x1800670e6  or      ebx, 80070000h
0x1800670ec  test    ebx, ebx
0x1800670ee  js      short loc_18006711C
0x1800670f0  mov     eax, [rsi]
0x1800670f2  mov     [r14], eax
0x1800670f5  test    rsi, rsi
0x1800670f8  jz      short loc_18006711C
0x1800670fa  mov     rcx, rsi; lpBaseAddress
0x1800670fd  call    cs:__imp_UnmapViewOfFile
0x180067103  test    eax, eax
0x180067105  jnz     short loc_18006711C
0x180067107  call    cs:__imp_GetLastError
0x18006710d  mov     ebx, eax
0x18006710f  test    eax, eax
0x180067111  jle     short loc_18006711C
0x180067113  movzx   ebx, ax
0x180067116  or      ebx, 80070000h
0x18006711c  test    rdi, rdi
0x18006711f  jz      short loc_18006712A
0x180067121  mov     rcx, rdi; hObject
0x180067124  call    cs:__imp_CloseHandle
0x18006712a  mov     eax, ebx
0x18006712c  mov     rcx, [rsp+268h+var_28]
0x180067134  xor     rcx, rsp; StackCookie
0x180067137  call    __security_check_cookie
0x18006713c  mov     rbx, [rsp+268h+arg_10]
0x180067144  add     rsp, 250h
0x18006714b  pop     r14
0x18006714d  pop     rdi
0x18006714e  pop     rsi
0x18006714f  retn
```
