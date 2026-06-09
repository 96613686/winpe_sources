# GetDeviceUniqueId(uchar const *,ulong,ulong,uchar *,ulong *)

- ea: `0x18005ff7c`
- end: `0x180060038`
- name: `?GetDeviceUniqueId@@YAJPEBEKKPEAEPEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800603f4`

## callees

- `0x18005ff7c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005ff9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005ff9d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fffe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006001b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005fffe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006001b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ffc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005ffc0`

## string_xrefs

- `0x18005ff96`: `wpcoreutil.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetDeviceUniqueId(
        const unsigned __int8 *a1,
        __int64 a2,
        __int64 a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  HMODULE Library; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v9; // edi

  Library = LoadLibraryExW(L"wpcoreutil.dll", 0, 0x800u);
  v7 = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetDeviceUniqueID")) != 0 )
  {
    v9 = ((__int64 (__fastcall *)(__int64 *, __int64, __int64, unsigned __int8 *, unsigned int *))ProcAddress)(
           qword_1800D0DE0,
           16,
           1,
           a4,
           a5);
    if ( v7 != (HMODULE)-1LL )
      FreeLibrary(v7);
    return v9;
  }
  else
  {
    if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      FreeLibrary(v7);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18005ff7c  mov     [rsp+arg_8], rbx
0x18005ff81  mov     [rsp+arg_0], rcx
0x18005ff86  push    rdi
0x18005ff87  sub     rsp, 30h
0x18005ff8b  mov     rdi, r9
0x18005ff8e  xor     edx, edx; hFile
0x18005ff90  mov     r8d, 800h; dwFlags
0x18005ff96  lea     rcx, LibFileName; "wpcoreutil.dll"
0x18005ff9d  call    cs:__imp_LoadLibraryExW
0x18005ffa4  nop     dword ptr [rax+rax+00h]
0x18005ffa9  mov     rbx, rax
0x18005ffac  mov     [rsp+38h+arg_0], rax
0x18005ffb1  test    rax, rax
0x18005ffb4  jz      short loc_18006000E
0x18005ffb6  lea     rdx, aGetdeviceuniqu; "GetDeviceUniqueID"
0x18005ffbd  mov     rcx, rax; hModule
0x18005ffc0  call    cs:__imp_GetProcAddress
0x18005ffc7  nop     dword ptr [rax+rax+00h]
0x18005ffcc  test    rax, rax
0x18005ffcf  jz      short loc_18006000E
0x18005ffd1  mov     rcx, [rsp+38h+arg_20]
0x18005ffd6  mov     [rsp+38h+var_18], rcx
0x18005ffdb  mov     r9, rdi
0x18005ffde  mov     edx, 10h
0x18005ffe3  lea     r8d, [rdx-0Fh]
0x18005ffe7  lea     rcx, qword_1800D0DE0
0x18005ffee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fff3  mov     edi, eax
0x18005fff5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005fff9  jz      short loc_18006000A
0x18005fffb  mov     rcx, rbx; hLibModule
0x18005fffe  call    cs:__imp_FreeLibrary
0x180060005  nop     dword ptr [rax+rax+00h]
0x18006000a  mov     eax, edi
0x18006000c  jmp     short loc_18006002C
0x18006000e  lea     rax, [rbx-1]
0x180060012  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180060016  ja      short loc_180060027
0x180060018  mov     rcx, rbx; hLibModule
0x18006001b  call    cs:__imp_FreeLibrary
0x180060022  nop     dword ptr [rax+rax+00h]
0x180060027  mov     eax, 80004005h
0x18006002c  mov     rbx, [rsp+38h+arg_8]
0x180060031  add     rsp, 30h
0x180060035  pop     rdi
0x180060036  retn
```
