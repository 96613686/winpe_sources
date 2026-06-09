# CompatCacheIsSystemFile

- ea: `0x18001af50`
- end: `0x18001b01b`
- name: `CompatCacheIsSystemFile`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c370`

## callees

- `0x18001a7a8`
- `0x18001af50`
- `0x180039a66`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001afd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001afd5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b003`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001b003`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001afed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001afed`

## string_xrefs

- `0x18001afc3`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall CompatCacheIsSystemFile(int *a1, const wchar_t *a2)
{
  __int64 v2; // rbx
  int Flags; // ecx
  int v6; // eax
  HMODULE Library; // rax
  HMODULE v9; // rdi
  __int64 (*ProcAddress)(void); // rax
  int v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = (__int64)String1;
  v11 = 0;
  if ( !String1 )
  {
    v2 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v9 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v2 = ProcAddress();
      FreeLibrary(v9);
    }
    String1 = (wchar_t *)v2;
  }
  if ( wcsnicmp_0(a2, (const wchar_t *)v2, 3u) )
  {
    v6 = 0;
    Flags = 0;
  }
  else
  {
    Flags = CompatCachepGetFlags(&v11, 512, a2);
    if ( Flags < 0 || (v6 = 1, v11 != 1) )
      v6 = 0;
  }
  *a1 = v6;
  return (unsigned int)Flags;
}

```

## disassembly

```asm
0x18001af50  push    rbx
0x18001af52  push    rsi
0x18001af53  push    rdi
0x18001af54  push    r14
0x18001af56  sub     rsp, 28h
0x18001af5a  mov     rbx, cs:String1
0x18001af61  mov     rsi, rdx
0x18001af64  mov     [rsp+48h+arg_0], 0
0x18001af6c  mov     r14, rcx
0x18001af6f  test    rbx, rbx
0x18001af72  jz      short loc_18001AFC1
0x18001af74  mov     r8d, 3; MaxCount
0x18001af7a  mov     rdx, rbx; String2
0x18001af7d  mov     rcx, rsi; String1
0x18001af80  call    _wcsnicmp_0
0x18001af85  test    eax, eax
0x18001af87  jnz     loc_18001B015
0x18001af8d  mov     r8, rsi
0x18001af90  lea     rcx, [rsp+48h+arg_0]
0x18001af95  mov     edx, 200h
0x18001af9a  call    CompatCachepGetFlags
0x18001af9f  mov     ecx, eax
0x18001afa1  test    eax, eax
0x18001afa3  js      short loc_18001AFB0
0x18001afa5  mov     eax, 1
0x18001afaa  cmp     [rsp+48h+arg_0], eax
0x18001afae  jz      short loc_18001AFB2
0x18001afb0  xor     eax, eax
0x18001afb2  mov     [r14], eax
0x18001afb5  mov     eax, ecx
0x18001afb7  add     rsp, 28h
0x18001afbb  pop     r14
0x18001afbd  pop     rdi
0x18001afbe  pop     rsi
0x18001afbf  pop     rbx
0x18001afc0  retn
0x18001afc1  xor     edx, edx; hFile
0x18001afc3  lea     rcx, LibFileName; "ntdll.dll"
0x18001afca  mov     r8d, 800h; dwFlags
0x18001afd0  mov     ebx, 7FFE0030h
0x18001afd5  call    cs:__imp_LoadLibraryExW
0x18001afdb  mov     rdi, rax
0x18001afde  test    rax, rax
0x18001afe1  jz      short loc_18001B009
0x18001afe3  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18001afea  mov     rcx, rax; hModule
0x18001afed  call    cs:__imp_GetProcAddress
0x18001aff3  test    rax, rax
0x18001aff6  jz      short loc_18001B000
0x18001aff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001affd  mov     rbx, rax
0x18001b000  mov     rcx, rdi; hLibModule
0x18001b003  call    cs:__imp_FreeLibrary
0x18001b009  mov     cs:String1, rbx
0x18001b010  jmp     loc_18001AF74
0x18001b015  xor     eax, eax
0x18001b017  xor     ecx, ecx
0x18001b019  jmp     short loc_18001AFB2
```
