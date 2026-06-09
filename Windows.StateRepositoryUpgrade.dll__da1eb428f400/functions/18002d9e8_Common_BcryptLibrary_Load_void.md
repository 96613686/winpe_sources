# Common::BcryptLibrary::Load(void)

- ea: `0x18002d9e8`
- end: `0x18002dadb`
- name: `?Load@BcryptLibrary@Common@@SAJXZ`
- size: `243`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ca8c`

## callees

- `0x1800043a8`
- `0x1800043b4`
- `0x18002d9e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002da0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002da0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dac4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dac4`

## string_xrefs

- `0x18002da05`: `Bcrypt.dll`

## pseudocode

```c
signed int Common::BcryptLibrary::Load(void)
{
  HMODULE Library; // rdi
  signed int result; // eax
  __int64 v2; // rbx
  FARPROC ProcAddress_0; // rax
  signed int LastError_0; // ebx
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
      ProcAddress_0 = GetProcAddress_0(Library, (LPCSTR)(&Common::BcryptLibrary::functionNames)[v2]);
      *((_QWORD *)&v5 + v2) = ProcAddress_0;
      if ( !ProcAddress_0 )
        break;
      if ( (unsigned __int64)++v2 >= 7 )
      {
        *(_OWORD *)&Common::BcryptLibrary::functions = v5;
        xmmword_18004C128 = v6;
        xmmword_18004C138 = v7;
        qword_18004C148 = v8;
        Common::BcryptLibrary::bcryptModule = Library;
        return 0;
      }
    }
    LastError_0 = GetLastError_0();
    FreeLibrary(Library);
    if ( LastError_0 > 0 )
      return (unsigned __int16)LastError_0 | 0x80070000;
    return LastError_0;
  }
  else
  {
    result = GetLastError_0();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002d9e8  mov     [rsp+arg_0], rbx
0x18002d9ed  push    rdi
0x18002d9ee  sub     rsp, 60h
0x18002d9f2  mov     rax, cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA; void * Common::BcryptLibrary::bcryptModule
0x18002d9f9  test    rax, rax
0x18002d9fc  jnz     loc_18002DAAD
0x18002da02  xor     r8d, r8d; dwFlags
0x18002da05  lea     rcx, aBcryptDll; "Bcrypt.dll"
0x18002da0c  xor     edx, edx; hFile
0x18002da0e  call    cs:__imp_LoadLibraryExW
0x18002da14  mov     rdi, rax
0x18002da17  test    rax, rax
0x18002da1a  jnz     short loc_18002DA33
0x18002da1c  call    GetLastError_0
0x18002da21  test    eax, eax
0x18002da23  jle     loc_18002DAAF
0x18002da29  movzx   eax, ax
0x18002da2c  or      eax, 80070000h
0x18002da31  jmp     short loc_18002DAAF
0x18002da33  xorps   xmm0, xmm0
0x18002da36  xor     eax, eax
0x18002da38  movups  [rsp+68h+var_48], xmm0
0x18002da3d  mov     [rsp+68h+var_18], rax
0x18002da42  xor     ebx, ebx
0x18002da44  movups  [rsp+68h+var_38], xmm0
0x18002da49  movups  [rsp+68h+var_28], xmm0
0x18002da4e  lea     rdx, ?functionNames@BcryptLibrary@Common@@0PAPEBDA; char const * near * Common::BcryptLibrary::functionNames
0x18002da55  mov     rcx, rdi; hModule
0x18002da58  mov     rdx, [rdx+rbx*8]; lpProcName
0x18002da5c  call    GetProcAddress_0
0x18002da61  mov     qword ptr [rsp+rbx*8+68h+var_48], rax
0x18002da66  test    rax, rax
0x18002da69  jz      short loc_18002DABA
0x18002da6b  inc     rbx
0x18002da6e  cmp     rbx, 7
0x18002da72  jb      short loc_18002DA4E
0x18002da74  movups  xmm0, [rsp+68h+var_48]
0x18002da79  movups  xmm1, [rsp+68h+var_38]
0x18002da7e  movups  cs:?functions@BcryptLibrary@Common@@0PAP6A_JXZA, xmm0; __int64 (*near * Common::BcryptLibrary::functions)(void)
0x18002da85  movups  xmm0, [rsp+68h+var_28]
0x18002da8a  movups  cs:xmmword_18004C128, xmm1
0x18002da91  movsd   xmm1, [rsp+68h+var_18]
0x18002da97  movups  cs:xmmword_18004C138, xmm0
0x18002da9e  movsd   cs:qword_18004C148, xmm1
0x18002daa6  mov     cs:?bcryptModule@BcryptLibrary@Common@@0REAXEA, rdi; void * Common::BcryptLibrary::bcryptModule
0x18002daad  xor     eax, eax
0x18002daaf  mov     rbx, [rsp+68h+arg_0]
0x18002dab4  add     rsp, 60h
0x18002dab8  pop     rdi
0x18002dab9  retn
0x18002daba  call    GetLastError_0
0x18002dabf  mov     rcx, rdi; hLibModule
0x18002dac2  mov     ebx, eax
0x18002dac4  call    cs:__imp_FreeLibrary
0x18002daca  test    ebx, ebx
0x18002dacc  jle     short loc_18002DAD7
0x18002dace  movzx   ebx, bx
0x18002dad1  or      ebx, 80070000h
0x18002dad7  mov     eax, ebx
0x18002dad9  jmp     short loc_18002DAAF
```
