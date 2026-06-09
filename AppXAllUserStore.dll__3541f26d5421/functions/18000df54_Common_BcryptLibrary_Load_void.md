# Common::BcryptLibrary::Load(void)

- ea: `0x18000df54`
- end: `0x18000e04a`
- name: `?Load@BcryptLibrary@Common@@SAJXZ`
- size: `246`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000de90`

## callees

- `0x18000df54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e033`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000e033`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000dfc9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000dfc9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000df7a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18000df7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e028`

## string_xrefs

- `0x18000df71`: `Bcrypt.dll`

## pseudocode

```c
signed int Common::BcryptLibrary::Load(void)
{
  HMODULE Library; // rdi
  signed int result; // eax
  __int64 v2; // rbx
  FARPROC ProcAddress; // rax
  signed int LastError; // ebx
  __int128 v5; // [rsp+20h] [rbp-48h]
  __int128 v6; // [rsp+30h] [rbp-38h]
  __int128 v7; // [rsp+40h] [rbp-28h]
  __int64 v8; // [rsp+50h] [rbp-18h]

  if ( Common::BcryptLibrary::bcryptModule )
    return 0;
  Library = LoadLibraryExW(L"Bcrypt.dll", 0, 0);
  if ( Library )
  {
    v5 = 0;
    v8 = 0;
    v2 = 0;
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      ProcAddress = GetProcAddress(Library, (LPCSTR)(&Common::BcryptLibrary::functionNames)[v2]);
      *((_QWORD *)&v5 + v2) = ProcAddress;
      if ( !ProcAddress )
        break;
      if ( (unsigned __int64)++v2 >= 7 )
      {
        *(_OWORD *)&Common::BcryptLibrary::functions = v5;
        xmmword_180064DF8 = v6;
        xmmword_180064E08 = v7;
        qword_180064E18 = v8;
        Common::BcryptLibrary::bcryptModule = Library;
        return 0;
      }
    }
    LastError = GetLastError();
    FreeLibrary(Library);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000df54  mov     [rsp+arg_0], rbx
0x18000df59  push    rdi
0x18000df5a  sub     rsp, 60h
0x18000df5e  mov     rax, cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA; void * Common::BcryptLibrary::bcryptModule
0x18000df65  test    rax, rax
0x18000df68  jnz     loc_18000E01B
0x18000df6e  xor     r8d, r8d; dwFlags
0x18000df71  lea     rcx, aBcryptDll; "Bcrypt.dll"
0x18000df78  xor     edx, edx; hFile
0x18000df7a  call    cs:__imp_LoadLibraryExW
0x18000df80  mov     rdi, rax
0x18000df83  test    rax, rax
0x18000df86  jnz     short loc_18000DFA0
0x18000df88  call    cs:__imp_GetLastError
0x18000df8e  test    eax, eax
0x18000df90  jle     loc_18000E01D
0x18000df96  movzx   eax, ax
0x18000df99  or      eax, 80070000h
0x18000df9e  jmp     short loc_18000E01D
0x18000dfa0  xorps   xmm0, xmm0
0x18000dfa3  xor     eax, eax
0x18000dfa5  movups  [rsp+68h+var_48], xmm0
0x18000dfaa  mov     [rsp+68h+var_18], rax
0x18000dfaf  xor     ebx, ebx
0x18000dfb1  movups  [rsp+68h+var_38], xmm0
0x18000dfb6  movups  [rsp+68h+var_28], xmm0
0x18000dfbb  lea     rdx, ?functionNames@BcryptLibrary@Common@@0PAPEBDA; char const * near * Common::BcryptLibrary::functionNames
0x18000dfc2  mov     rcx, rdi; hModule
0x18000dfc5  mov     rdx, [rdx+rbx*8]; lpProcName
0x18000dfc9  call    cs:__imp_GetProcAddress
0x18000dfcf  mov     qword ptr [rsp+rbx*8+68h+var_48], rax
0x18000dfd4  test    rax, rax
0x18000dfd7  jz      short loc_18000E028
0x18000dfd9  inc     rbx
0x18000dfdc  cmp     rbx, 7
0x18000dfe0  jb      short loc_18000DFBB
0x18000dfe2  movups  xmm0, [rsp+68h+var_48]
0x18000dfe7  movups  xmm1, [rsp+68h+var_38]
0x18000dfec  movups  cs:?functions@BcryptLibrary@Common@@0PAP6A_JXZA, xmm0; __int64 (*near * Common::BcryptLibrary::functions)(void)
0x18000dff3  movups  xmm0, [rsp+68h+var_28]
0x18000dff8  movups  cs:xmmword_180064DF8, xmm1
0x18000dfff  movsd   xmm1, [rsp+68h+var_18]
0x18000e005  movups  cs:xmmword_180064E08, xmm0
0x18000e00c  movsd   cs:qword_180064E18, xmm1
0x18000e014  mov     cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA, rdi; void * Common::BcryptLibrary::bcryptModule
0x18000e01b  xor     eax, eax
0x18000e01d  mov     rbx, [rsp+68h+arg_0]
0x18000e022  add     rsp, 60h
0x18000e026  pop     rdi
0x18000e027  retn
0x18000e028  call    cs:__imp_GetLastError
0x18000e02e  mov     rcx, rdi; hLibModule
0x18000e031  mov     ebx, eax
0x18000e033  call    cs:__imp_FreeLibrary
0x18000e039  test    ebx, ebx
0x18000e03b  jle     short loc_18000E046
0x18000e03d  movzx   ebx, bx
0x18000e040  or      ebx, 80070000h
0x18000e046  mov     eax, ebx
0x18000e048  jmp     short loc_18000E01D
```
