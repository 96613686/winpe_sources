# Windows::Compat::Inventory::AepicInvCache::Initialize(ushort const *,ulong,ulong)

- ea: `0x18002b264`
- end: `0x18002b316`
- name: `?Initialize@AepicInvCache@Inventory@Compat@Windows@@QEAAJPEBGKK@Z`
- size: `178`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *this, const unsigned __int16 *, int, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002debc`

## callees

- `0x18002b264`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002b28c`
- `KERNEL32!LoadLibraryExW` at `0x18002b28c`
- `KERNEL32!Sleep` at `0x18002b2f7`
- `KERNEL32!Sleep` at `0x18002b2f7`
- `KERNEL32!FreeLibrary` at `0x18002b2b5`
- `KERNEL32!FreeLibrary` at `0x18002b2b5`
- `KERNEL32!GetProcAddress` at `0x18002b2a2`
- `KERNEL32!GetProcAddress` at `0x18002b2a2`
- `KERNEL32!GetLastError` at `0x18002b2ff`
- `KERNEL32!GetLastError` at `0x18002b2ff`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002b2e3`
- `AEPIC!__imp_InvCacheOpenVerProvider` at `0x18002b2e3`

## string_xrefs

- `0x18002b282`: `aepic.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::Initialize(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        int a3,
        DWORD a4)
{
  HMODULE Library; // rax
  HMODULE v9; // rsi
  int v10; // ebx
  int v12; // edi
  signed int LastError; // eax

  Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    if ( GetProcAddress(Library, (LPCSTR)0x64) )
    {
      v10 = -2147467259;
      v12 = a3 + 1;
      if ( v12 )
      {
        while ( 1 )
        {
          v10 = InvCacheOpenVerProvider((char *)this + 8, 0, a2, 2);
          if ( v10 >= 0 )
            break;
          if ( !--v12 )
            break;
          Sleep(a4);
        }
      }
    }
    else
    {
      v10 = -2147467262;
    }
    FreeLibrary(v9);
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b264  push    rbx
0x18002b266  push    rbp
0x18002b267  push    rsi
0x18002b268  push    rdi
0x18002b269  push    r14
0x18002b26b  push    r15
0x18002b26d  sub     rsp, 28h
0x18002b271  mov     edi, r8d
0x18002b274  mov     r15, rdx
0x18002b277  mov     rbp, rcx
0x18002b27a  xor     edx, edx; hFile
0x18002b27c  mov     r8d, 800h; dwFlags
0x18002b282  lea     rcx, aAepicDll_0; "aepic.dll"
0x18002b289  mov     r14d, r9d
0x18002b28c  call    cs:__imp_LoadLibraryExW
0x18002b292  mov     rsi, rax
0x18002b295  test    rax, rax
0x18002b298  jz      short loc_18002B2FF
0x18002b29a  mov     edx, 64h ; 'd'; lpProcName
0x18002b29f  mov     rcx, rax; hModule
0x18002b2a2  call    cs:__imp_GetProcAddress
0x18002b2a8  test    rax, rax
0x18002b2ab  jnz     short loc_18002B2CA
0x18002b2ad  mov     ebx, 80004002h
0x18002b2b2  mov     rcx, rsi; hLibModule
0x18002b2b5  call    cs:__imp_FreeLibrary
0x18002b2bb  mov     eax, ebx
0x18002b2bd  add     rsp, 28h
0x18002b2c1  pop     r15
0x18002b2c3  pop     r14
0x18002b2c5  pop     rdi
0x18002b2c6  pop     rsi
0x18002b2c7  pop     rbp
0x18002b2c8  pop     rbx
0x18002b2c9  retn
0x18002b2ca  mov     ebx, 80004005h
0x18002b2cf  add     edi, 1
0x18002b2d2  jz      short loc_18002B2B2
0x18002b2d4  mov     r9d, 2
0x18002b2da  lea     rcx, [rbp+8]
0x18002b2de  mov     r8, r15
0x18002b2e1  xor     edx, edx
0x18002b2e3  call    cs:__imp_InvCacheOpenVerProvider
0x18002b2e9  mov     ebx, eax
0x18002b2eb  test    eax, eax
0x18002b2ed  jns     short loc_18002B2B2
0x18002b2ef  add     edi, 0FFFFFFFFh
0x18002b2f2  jz      short loc_18002B2B2
0x18002b2f4  mov     ecx, r14d; dwMilliseconds
0x18002b2f7  call    cs:__imp_Sleep
0x18002b2fd  jmp     short loc_18002B2D4
0x18002b2ff  call    cs:__imp_GetLastError
0x18002b305  mov     ebx, eax
0x18002b307  test    eax, eax
0x18002b309  jle     short loc_18002B2BB
0x18002b30b  movzx   ebx, ax
0x18002b30e  or      ebx, 80070000h
0x18002b314  jmp     short loc_18002B2BB
```
