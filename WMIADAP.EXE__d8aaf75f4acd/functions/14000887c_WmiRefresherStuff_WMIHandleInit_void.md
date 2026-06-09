# WmiRefresherStuff::WMIHandleInit(void)

- ea: `0x14000887c`
- end: `0x140008a0f`
- name: `?WMIHandleInit@WmiRefresherStuff@@AEAAJXZ`
- size: `403`
- prototype: `__int64 __fastcall(WmiRefresherStuff *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140006bb4`

## callees

- `0x140001a6f`
- `0x140006284`
- `0x1400075f8`
- `0x14000887c`
- `0x140014ad0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140008958`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400089de`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140008958`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400089de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000898d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400089a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000898d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400089a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400088d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1400088d7`

## string_xrefs

- `0x140008934`: `PSAPI.DLL`
- `0x1400089d1`: `loadperf.dll`

## pseudocode

```c
__int64 __fastcall WmiRefresherStuff::WMIHandleInit(WmiRefresherStuff *this)
{
  int v2; // ebx
  __int64 v3; // r11
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  bool v10; // zf
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+230h] [rbp-228h] BYREF

  v2 = 1;
  if ( !*((_QWORD *)this + 10) )
  {
    memset_0(Buffer, 0, 0x20Au);
    if ( GetSystemDirectoryW(Buffer, 0x105u) < 0x105 )
    {
      v2 = StringCchCopyW(LibFileName, 0x105u, Buffer);
      if ( v2 >= 0 )
      {
        if ( LibFileName[v3] == 92 || (v2 = StringCchCatW(LibFileName, 0x105u, L"\\"), v2 >= 0) )
        {
          v2 = StringCchCatW(LibFileName, 0x105u, L"PSAPI.DLL");
          if ( v2 >= 0 )
          {
            Library = LoadLibraryExW(LibFileName, 0, 0);
            *((_QWORD *)this + 10) = Library;
            if ( Library )
            {
              ProcAddress = GetProcAddress(Library, "EnumProcesses");
              v6 = (HMODULE)*((_QWORD *)this + 10);
              *((_QWORD *)this + 11) = ProcAddress;
              v7 = GetProcAddress(v6, "EnumProcessModules");
              v8 = (HMODULE)*((_QWORD *)this + 10);
              *((_QWORD *)this + 12) = v7;
              v9 = GetProcAddress(v8, "GetModuleBaseNameW");
              v10 = *((_QWORD *)this + 11) == 0;
              *((_QWORD *)this + 13) = v9;
              if ( !v10 && *((_QWORD *)this + 12) && v9 )
                v2 = 0;
              else
                v2 = -2147024769;
            }
            else
            {
              v2 = -2147023739;
            }
          }
        }
      }
    }
    else
    {
      v2 = -2147418113;
    }
  }
  if ( !*((_QWORD *)this + 15) )
    *((_QWORD *)this + 15) = LoadLibraryExW(L"loadperf.dll", 0, 0x800u);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000887c  mov     [rsp+arg_8], rbx
0x140008881  mov     [rsp+arg_10], rbp
0x140008886  push    rdi
0x140008887  sub     rsp, 450h
0x14000888e  mov     rax, cs:__security_cookie
0x140008895  xor     rax, rsp
0x140008898  mov     [rsp+458h+var_18], rax
0x1400088a0  cmp     qword ptr [rcx+50h], 0
0x1400088a5  mov     rdi, rcx
0x1400088a8  mov     ebx, 1
0x1400088ad  jnz     loc_1400089C8
0x1400088b3  xor     edx, edx; Val
0x1400088b5  lea     rcx, [rsp+458h+Buffer]; void *
0x1400088bd  mov     r8d, 20Ah; Size
0x1400088c3  call    memset_0
0x1400088c8  mov     ebp, 105h
0x1400088cd  lea     rcx, [rsp+458h+Buffer]; lpBuffer
0x1400088d5  mov     edx, ebp; uSize
0x1400088d7  call    cs:__imp_GetSystemDirectoryW
0x1400088dd  mov     r11d, eax
0x1400088e0  cmp     eax, ebp
0x1400088e2  jb      short loc_1400088EE
0x1400088e4  mov     ebx, 8000FFFFh
0x1400088e9  jmp     loc_1400089C8
0x1400088ee  lea     r8, [rsp+458h+Buffer]; unsigned __int16 *
0x1400088f6  mov     rdx, rbp; unsigned __int64
0x1400088f9  lea     rcx, [rsp+458h+LibFileName]; unsigned __int16 *
0x1400088fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008903  mov     ebx, eax
0x140008905  test    eax, eax
0x140008907  js      loc_1400089C8
0x14000890d  cmp     [rsp+r11*2+458h+LibFileName], 5Ch ; '\'
0x140008914  jz      short loc_140008934
0x140008916  lea     r8, asc_14001A9B8; "\\"
0x14000891d  mov     rdx, rbp; unsigned __int64
0x140008920  lea     rcx, [rsp+458h+LibFileName]; unsigned __int16 *
0x140008925  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000892a  mov     ebx, eax
0x14000892c  test    eax, eax
0x14000892e  js      loc_1400089C8
0x140008934  lea     r8, aPsapiDll; "PSAPI.DLL"
0x14000893b  mov     rdx, rbp; unsigned __int64
0x14000893e  lea     rcx, [rsp+458h+LibFileName]; unsigned __int16 *
0x140008943  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008948  mov     ebx, eax
0x14000894a  test    eax, eax
0x14000894c  js      short loc_1400089C8
0x14000894e  xor     r8d, r8d; dwFlags
0x140008951  lea     rcx, [rsp+458h+LibFileName]; lpLibFileName
0x140008956  xor     edx, edx; hFile
0x140008958  call    cs:__imp_LoadLibraryExW
0x14000895e  mov     [rdi+50h], rax
0x140008962  test    rax, rax
0x140008965  jnz     short loc_14000896E
0x140008967  mov     ebx, 80070485h
0x14000896c  jmp     short loc_1400089C8
0x14000896e  lea     rdx, aEnumprocesses; "EnumProcesses"
0x140008975  mov     rcx, rax; hModule
0x140008978  call    cs:__imp_GetProcAddress
0x14000897e  mov     rcx, [rdi+50h]; hModule
0x140008982  lea     rdx, aEnumprocessmod; "EnumProcessModules"
0x140008989  mov     [rdi+58h], rax
0x14000898d  call    cs:__imp_GetProcAddress
0x140008993  mov     rcx, [rdi+50h]; hModule
0x140008997  lea     rdx, aGetmodulebasen; "GetModuleBaseNameW"
0x14000899e  mov     [rdi+60h], rax
0x1400089a2  call    cs:__imp_GetProcAddress
0x1400089a8  cmp     qword ptr [rdi+58h], 0
0x1400089ad  mov     [rdi+68h], rax
0x1400089b1  jz      short loc_1400089C3
0x1400089b3  cmp     qword ptr [rdi+60h], 0
0x1400089b8  jz      short loc_1400089C3
0x1400089ba  test    rax, rax
0x1400089bd  jz      short loc_1400089C3
0x1400089bf  xor     ebx, ebx
0x1400089c1  jmp     short loc_1400089C8
0x1400089c3  mov     ebx, 8007007Fh
0x1400089c8  cmp     qword ptr [rdi+78h], 0
0x1400089cd  jnz     short loc_1400089E8
0x1400089cf  xor     edx, edx; hFile
0x1400089d1  lea     rcx, LibFileName; "loadperf.dll"
0x1400089d8  mov     r8d, 800h; dwFlags
0x1400089de  call    cs:__imp_LoadLibraryExW
0x1400089e4  mov     [rdi+78h], rax
0x1400089e8  mov     eax, ebx
0x1400089ea  mov     rcx, [rsp+458h+var_18]
0x1400089f2  xor     rcx, rsp; StackCookie
0x1400089f5  call    __security_check_cookie
0x1400089fa  lea     r11, [rsp+458h+var_8]
0x140008a02  mov     rbx, [r11+18h]
0x140008a06  mov     rbp, [r11+20h]
0x140008a0a  mov     rsp, r11
0x140008a0d  pop     rdi
0x140008a0e  retn
```
