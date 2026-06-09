# Windows::Compat::Inventory::AepicInvCache::Initialize(ushort const *,ulong,ulong)

- ea: `0x180015398`
- end: `0x180015449`
- name: `?Initialize@AepicInvCache@Inventory@Compat@Windows@@QEAAJPEBGKK@Z`
- size: `177`
- prototype: `int(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015cf0`

## callees

- `0x180015398`
- `0x180029000`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015400`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180015400`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800153c0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800153c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800153ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800153ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800153ce`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015441`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180015441`

## string_xrefs

- `0x1800153b6`: `aepic.dll`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::Initialize(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        int a3,
        DWORD a4)
{
  HMODULE Library; // rax
  HMODULE v9; // rsi
  signed int LastError; // eax
  int v11; // ebx
  int v13; // edi

  Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
  v9 = Library;
  if ( Library )
  {
    if ( GetProcAddress(Library, (LPCSTR)0x64) )
    {
      v11 = -2147467259;
      v13 = a3 + 1;
      if ( v13 )
      {
        while ( 1 )
        {
          v11 = InvCacheOpenVerProvider((char *)this + 8, 0, a2, 2);
          if ( v11 >= 0 )
            break;
          if ( !--v13 )
            break;
          Sleep(a4);
        }
      }
    }
    else
    {
      v11 = -2147467262;
    }
    FreeLibrary(v9);
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180015398  push    rbx
0x18001539a  push    rbp
0x18001539b  push    rsi
0x18001539c  push    rdi
0x18001539d  push    r14
0x18001539f  push    r15
0x1800153a1  sub     rsp, 28h
0x1800153a5  mov     edi, r8d
0x1800153a8  mov     r15, rdx
0x1800153ab  mov     rbp, rcx
0x1800153ae  xor     edx, edx; hFile
0x1800153b0  mov     r8d, 800h; dwFlags
0x1800153b6  lea     rcx, aAepicDll_0; "aepic.dll"
0x1800153bd  mov     r14d, r9d
0x1800153c0  call    cs:__imp_LoadLibraryExW
0x1800153c6  mov     rsi, rax
0x1800153c9  test    rax, rax
0x1800153cc  jnz     short loc_1800153E5
0x1800153ce  call    cs:__imp_GetLastError
0x1800153d4  mov     ebx, eax
0x1800153d6  test    eax, eax
0x1800153d8  jle     short loc_180015406
0x1800153da  movzx   ebx, ax
0x1800153dd  or      ebx, 80070000h
0x1800153e3  jmp     short loc_180015406
0x1800153e5  mov     edx, 64h ; 'd'; lpProcName
0x1800153ea  mov     rcx, rsi; hModule
0x1800153ed  call    cs:__imp_GetProcAddress
0x1800153f3  test    rax, rax
0x1800153f6  jnz     short loc_180015415
0x1800153f8  mov     ebx, 80004002h
0x1800153fd  mov     rcx, rsi; hLibModule
0x180015400  call    cs:__imp_FreeLibrary
0x180015406  mov     eax, ebx
0x180015408  add     rsp, 28h
0x18001540c  pop     r15
0x18001540e  pop     r14
0x180015410  pop     rdi
0x180015411  pop     rsi
0x180015412  pop     rbp
0x180015413  pop     rbx
0x180015414  retn
0x180015415  mov     ebx, 80004005h
0x18001541a  add     edi, 1
0x18001541d  jz      short loc_1800153FD
0x18001541f  mov     r9d, 2
0x180015425  lea     rcx, [rbp+8]
0x180015429  mov     r8, r15
0x18001542c  xor     edx, edx
0x18001542e  call    InvCacheOpenVerProvider
0x180015433  mov     ebx, eax
0x180015435  test    eax, eax
0x180015437  jns     short loc_1800153FD
0x180015439  add     edi, 0FFFFFFFFh
0x18001543c  jz      short loc_1800153FD
0x18001543e  mov     ecx, r14d; dwMilliseconds
0x180015441  call    cs:__imp_Sleep
0x180015447  jmp     short loc_18001541F
```
