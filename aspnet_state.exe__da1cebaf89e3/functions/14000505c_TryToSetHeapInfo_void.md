# TryToSetHeapInfo(void)

- ea: `0x14000505c`
- end: `0x1400051a9`
- name: `?TryToSetHeapInfo@@YAXXZ`
- size: `333`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140002a78`

## callees

- `0x140004c14`
- `0x14000505c`
- `0x140005b20`
- `0x1400064a0`
- `0x140006590`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x1400050a1`
- `KERNEL32!GetVersionExW` at `0x1400050a1`
- `KERNEL32!GetSystemDirectoryW` at `0x1400050df`
- `KERNEL32!GetSystemDirectoryW` at `0x1400050df`
- `KERNEL32!lstrlenW` at `0x1400050f1`
- `KERNEL32!lstrlenW` at `0x140005104`
- `KERNEL32!lstrlenW` at `0x1400050f1`
- `KERNEL32!lstrlenW` at `0x140005104`
- `KERNEL32!LoadLibraryW` at `0x14000514b`
- `KERNEL32!LoadLibraryW` at `0x14000514b`
- `KERNEL32!FreeLibrary` at `0x140005183`
- `KERNEL32!FreeLibrary` at `0x140005183`
- `KERNEL32!GetProcAddress` at `0x140005163`
- `KERNEL32!GetProcAddress` at `0x140005163`

## string_xrefs

- `0x140005130`: `kernel32.dll`

## pseudocode

```c
void TryToSetHeapInfo(void)
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rbx
  FARPROC ProcAddress; // rax
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+150h] [rbp+50h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( VersionInformation.dwPlatformId == 2 && VersionInformation.dwMajorVersion >= 6 )
    {
      memset_0(Buffer, 0, 0x20Au);
      if ( GetSystemDirectoryW(Buffer, 0x104u) )
      {
        if ( lstrlenW(Buffer) >= 1
          && (Buffer[lstrlenW(Buffer) - 1] == 92 || !(unsigned int)StringCchCatW(Buffer, 0x105u, L"\\"))
          && !(unsigned int)StringCchCatW(Buffer, 0x105u, L"kernel32.dll") )
        {
          LibraryW = LoadLibraryW(Buffer);
          v1 = LibraryW;
          if ( LibraryW )
          {
            ProcAddress = GetProcAddress(LibraryW, "HeapSetInformation");
            if ( ProcAddress )
              ((void (__fastcall *)(_QWORD, __int64, _QWORD))ProcAddress)(0, 1, 0);
            FreeLibrary(v1);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000505c  mov     [rsp-8+arg_0], rbx
0x140005061  push    rbp
0x140005062  lea     rbp, [rsp-270h]
0x14000506a  sub     rsp, 370h
0x140005071  mov     rax, cs:__security_cookie
0x140005078  xor     rax, rsp
0x14000507b  mov     [rbp+270h+var_10], rax
0x140005082  xor     edx, edx; Val
0x140005084  lea     rcx, [rsp+370h+VersionInformation.dwMajorVersion]; void *
0x140005089  mov     r8d, 110h; Size
0x14000508f  call    memset_0
0x140005094  lea     rcx, [rsp+370h+VersionInformation]; lpVersionInformation
0x140005099  mov     [rsp+370h+VersionInformation.dwOSVersionInfoSize], 114h
0x1400050a1  call    cs:__imp_GetVersionExW
0x1400050a7  test    eax, eax
0x1400050a9  jz      loc_140005189
0x1400050af  cmp     [rsp+370h+VersionInformation.dwPlatformId], 2
0x1400050b4  jnz     loc_140005189
0x1400050ba  cmp     [rsp+370h+VersionInformation.dwMajorVersion], 6
0x1400050bf  jb      loc_140005189
0x1400050c5  xor     edx, edx; Val
0x1400050c7  lea     rcx, [rbp+270h+Buffer]; void *
0x1400050cb  mov     r8d, 20Ah; Size
0x1400050d1  call    memset_0
0x1400050d6  mov     edx, 104h; uSize
0x1400050db  lea     rcx, [rbp+270h+Buffer]; lpBuffer
0x1400050df  call    cs:__imp_GetSystemDirectoryW
0x1400050e5  test    eax, eax
0x1400050e7  jz      loc_140005189
0x1400050ed  lea     rcx, [rbp+270h+Buffer]; lpString
0x1400050f1  call    cs:__imp_lstrlenW
0x1400050f7  cmp     eax, 1
0x1400050fa  jl      loc_140005189
0x140005100  lea     rcx, [rbp+270h+Buffer]; lpString
0x140005104  call    cs:__imp_lstrlenW
0x14000510a  movsxd  rcx, eax
0x14000510d  mov     ebx, 105h
0x140005112  cmp     [rbp+rcx*2+270h+var_222], 5Ch ; '\'
0x140005118  jz      short loc_140005130
0x14000511a  lea     r8, asc_140007B90; "\\"
0x140005121  mov     edx, ebx; unsigned __int64
0x140005123  lea     rcx, [rbp+270h+Buffer]; unsigned __int16 *
0x140005127  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000512c  test    eax, eax
0x14000512e  jnz     short loc_140005189
0x140005130  lea     r8, aKernel32Dll_0; "kernel32.dll"
0x140005137  mov     rdx, rbx; unsigned __int64
0x14000513a  lea     rcx, [rbp+270h+Buffer]; unsigned __int16 *
0x14000513e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005143  test    eax, eax
0x140005145  jnz     short loc_140005189
0x140005147  lea     rcx, [rbp+270h+Buffer]; lpLibFileName
0x14000514b  call    cs:__imp_LoadLibraryW
0x140005151  mov     rbx, rax
0x140005154  test    rax, rax
0x140005157  jz      short loc_140005189
0x140005159  lea     rdx, ProcName; "HeapSetInformation"
0x140005160  mov     rcx, rax; hModule
0x140005163  call    cs:__imp_GetProcAddress
0x140005169  test    rax, rax
0x14000516c  jz      short loc_140005180
0x14000516e  xor     r9d, r9d
0x140005171  xor     r8d, r8d
0x140005174  xor     ecx, ecx
0x140005176  lea     edx, [r9+1]
0x14000517a  call    cs:__guard_dispatch_icall_fptr
0x140005180  mov     rcx, rbx; hLibModule
0x140005183  call    cs:__imp_FreeLibrary
0x140005189  mov     rcx, [rbp+270h+var_10]
0x140005190  xor     rcx, rsp; StackCookie
0x140005193  call    __security_check_cookie
0x140005198  mov     rbx, [rsp+370h+arg_0]
0x1400051a0  add     rsp, 370h
0x1400051a7  pop     rbp
0x1400051a8  retn
```
