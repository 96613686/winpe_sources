# WspiapiLoad

- ea: `0x18007ffa0`
- end: `0x180080172`
- name: `WspiapiLoad`
- size: `466`
- prototype: `FARPROC __stdcall(WORD wFunction)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007de30`
- `0x18007f8bc`
- `0x18007f8f4`

## callees

- `0x18007ffa0`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!strcat_s` at `0x18008006c`
- `msvcrt!strcat_s` at `0x1800800c0`
- `msvcrt!strcat_s` at `0x18008006c`
- `msvcrt!strcat_s` at `0x1800800c0`
- `msvcrt!strcpy_s` at `0x180080058`
- `msvcrt!strcpy_s` at `0x1800800ab`
- `msvcrt!strcpy_s` at `0x180080058`
- `msvcrt!strcpy_s` at `0x1800800ab`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180080077`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800800cb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180080077`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800800cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008008b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800800df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800800ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008008b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800800df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800800ff`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080099`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080116`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080099`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180080116`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180080033`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180080033`

## pseudocode

```c
FARPROC __stdcall WspiapiLoad(WORD wFunction)
{
  __int64 v1; // r15
  HMODULE LibraryA; // rax
  HMODULE v3; // rdi
  HMODULE v4; // rax
  int i; // esi
  FARPROC ProcAddress; // rax
  __int64 j; // rdx
  __int64 v8; // rcx
  LPCSTR lpProcName; // [rsp+20h] [rbp-E0h]
  _QWORD v11[5]; // [rsp+28h] [rbp-D8h]
  char Destination[272]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Buffer[272]; // [rsp+160h] [rbp+60h] BYREF

  v11[0] = WspiapiLegacyGetAddrInfo;
  v1 = wFunction;
  v11[1] = "getnameinfo";
  v11[2] = WspiapiLegacyGetNameInfo;
  v11[3] = "freeaddrinfo";
  v11[4] = WspiapiLegacyFreeAddrInfo;
  lpProcName = "getaddrinfo";
  if ( !`WspiapiLoad'::`2'::bInitialized )
  {
    if ( GetSystemDirectoryA(Buffer, 0x104u) )
    {
      strcpy_s(Destination, 0x10Cu, Buffer);
      strcat_s(Destination, 0x10Cu, "\\ws2_32");
      LibraryA = LoadLibraryA(Destination);
      v3 = LibraryA;
      if ( LibraryA )
      {
        if ( GetProcAddress(LibraryA, "getaddrinfo") )
          goto LABEL_8;
        FreeLibrary(v3);
      }
      strcpy_s(Destination, 0x10Cu, Buffer);
      strcat_s(Destination, 0x10Cu, "\\wship6");
      v4 = LoadLibraryA(Destination);
      v3 = v4;
      if ( v4 )
      {
        if ( GetProcAddress(v4, "getaddrinfo") )
        {
LABEL_8:
          for ( i = 0; i < 3; ++i )
          {
            ProcAddress = GetProcAddress(v3, (LPCSTR)v11[2 * i - 1]);
            v11[2 * i] = ProcAddress;
            if ( !ProcAddress )
              goto LABEL_12;
          }
          if ( v3 )
          {
            for ( j = 0; j != 3; ++j )
            {
              v8 = j;
              (&`WspiapiLoad'::`2'::rgtGlobal)[2 * v8 + 1] = (char *)v11[2 * v8];
            }
          }
          goto LABEL_16;
        }
LABEL_12:
        FreeLibrary(v3);
      }
    }
LABEL_16:
    `WspiapiLoad'::`2'::bInitialized = 1;
  }
  return (FARPROC)(&`WspiapiLoad'::`2'::rgtGlobal)[2 * v1 + 1];
}

```

## disassembly

```asm
0x18007ffa0  push    rbp
0x18007ffa2  push    rbx
0x18007ffa3  push    rsi
0x18007ffa4  push    rdi
0x18007ffa5  push    r14
0x18007ffa7  push    r15
0x18007ffa9  lea     rbp, [rsp-188h]
0x18007ffb1  sub     rsp, 288h
0x18007ffb8  mov     rax, cs:__security_cookie
0x18007ffbf  xor     rax, rsp
0x18007ffc2  mov     [rbp+1B0h+var_40], rax
0x18007ffc9  cmp     cs:?bInitialized@?1??WspiapiLoad@@9@4HA, 0; int `WspiapiLoad'::`2'::bInitialized
0x18007ffd0  lea     rax, WspiapiLegacyGetAddrInfo
0x18007ffd7  mov     [rsp+2B0h+var_288], rax
0x18007ffdc  lea     rbx, aGetaddrinfo; "getaddrinfo"
0x18007ffe3  lea     rax, aGetnameinfo; "getnameinfo"
0x18007ffea  movzx   r15d, cx
0x18007ffee  mov     [rsp+2B0h+var_280], rax
0x18007fff3  lea     rax, WspiapiLegacyGetNameInfo
0x18007fffa  mov     [rsp+2B0h+var_278], rax
0x18007ffff  lea     rax, aFreeaddrinfo; "freeaddrinfo"
0x180080006  mov     [rsp+2B0h+var_270], rax
0x18008000b  lea     rax, WspiapiLegacyFreeAddrInfo
0x180080012  mov     [rsp+2B0h+var_268], rax
0x180080017  mov     [rsp+2B0h+lpProcName], rbx
0x18008001c  jz      short loc_18008002A
0x18008001e  lea     r14, ?rgtGlobal@?1??WspiapiLoad@@9@4PAUWSPIAPI_FUNCTION@@A; WSPIAPI_FUNCTION near * `WspiapiLoad'::`2'::rgtGlobal
0x180080025  jmp     loc_180080148
0x18008002a  mov     edx, 104h; uSize
0x18008002f  lea     rcx, [rbp+1B0h+Buffer]; lpBuffer
0x180080033  call    cs:__imp_GetSystemDirectoryA
0x180080039  lea     r14, ?rgtGlobal@?1??WspiapiLoad@@9@4PAUWSPIAPI_FUNCTION@@A; WSPIAPI_FUNCTION near * `WspiapiLoad'::`2'::rgtGlobal
0x180080040  test    eax, eax
0x180080042  jz      loc_18008013E
0x180080048  mov     esi, 10Ch
0x18008004d  lea     r8, [rbp+1B0h+Buffer]; Source
0x180080051  mov     edx, esi; SizeInBytes
0x180080053  lea     rcx, [rsp+2B0h+Destination]; Destination
0x180080058  call    cs:__imp_strcpy_s
0x18008005e  lea     r8, aWs232; "\\ws2_32"
0x180080065  mov     edx, esi; SizeInBytes
0x180080067  lea     rcx, [rsp+2B0h+Destination]; Destination
0x18008006c  call    cs:__imp_strcat_s
0x180080072  lea     rcx, [rsp+2B0h+Destination]; lpLibFileName
0x180080077  call    cs:__imp_LoadLibraryA
0x18008007d  mov     rdi, rax
0x180080080  test    rax, rax
0x180080083  jz      short loc_18008009F
0x180080085  mov     rdx, rbx; lpProcName
0x180080088  mov     rcx, rax; hModule
0x18008008b  call    cs:__imp_GetProcAddress
0x180080091  test    rax, rax
0x180080094  jnz     short loc_1800800EA
0x180080096  mov     rcx, rdi; hLibModule
0x180080099  call    cs:__imp_FreeLibrary
0x18008009f  lea     r8, [rbp+1B0h+Buffer]; Source
0x1800800a3  mov     rdx, rsi; SizeInBytes
0x1800800a6  lea     rcx, [rsp+2B0h+Destination]; Destination
0x1800800ab  call    cs:__imp_strcpy_s
0x1800800b1  lea     r8, aWship6; "\\wship6"
0x1800800b8  mov     rdx, rsi; SizeInBytes
0x1800800bb  lea     rcx, [rsp+2B0h+Destination]; Destination
0x1800800c0  call    cs:__imp_strcat_s
0x1800800c6  lea     rcx, [rsp+2B0h+Destination]; lpLibFileName
0x1800800cb  call    cs:__imp_LoadLibraryA
0x1800800d1  mov     rdi, rax
0x1800800d4  test    rax, rax
0x1800800d7  jz      short loc_18008013E
0x1800800d9  mov     rdx, rbx; lpProcName
0x1800800dc  mov     rcx, rax; hModule
0x1800800df  call    cs:__imp_GetProcAddress
0x1800800e5  test    rax, rax
0x1800800e8  jz      short loc_180080113
0x1800800ea  xor     esi, esi
0x1800800ec  cmp     esi, 3
0x1800800ef  jge     short loc_18008011E
0x1800800f1  movsxd  rbx, esi
0x1800800f4  mov     rcx, rdi; hModule
0x1800800f7  add     rbx, rbx
0x1800800fa  mov     rdx, [rsp+rbx*8+2B0h+lpProcName]; lpProcName
0x1800800ff  call    cs:__imp_GetProcAddress
0x180080105  mov     [rsp+rbx*8+2B0h+var_288], rax
0x18008010a  test    rax, rax
0x18008010d  jz      short loc_180080113
0x18008010f  inc     esi
0x180080111  jmp     short loc_1800800EC
0x180080113  mov     rcx, rdi; hLibModule
0x180080116  call    cs:__imp_FreeLibrary
0x18008011c  jmp     short loc_18008013E
0x18008011e  test    rdi, rdi
0x180080121  jz      short loc_18008013E
0x180080123  xor     edx, edx
0x180080125  mov     rcx, rdx
0x180080128  inc     rdx
0x18008012b  add     rcx, rcx
0x18008012e  mov     rax, [rsp+rcx*8+2B0h+var_288]
0x180080133  mov     [r14+rcx*8+8], rax
0x180080138  cmp     rdx, 3
0x18008013c  jnz     short loc_180080125
0x18008013e  mov     cs:?bInitialized@?1??WspiapiLoad@@9@4HA, 1; int `WspiapiLoad'::`2'::bInitialized
0x180080148  mov     rax, r15
0x18008014b  add     rax, rax
0x18008014e  mov     rax, [r14+rax*8+8]
0x180080153  mov     rcx, [rbp+1B0h+var_40]
0x18008015a  xor     rcx, rsp; StackCookie
0x18008015d  call    __security_check_cookie
0x180080162  add     rsp, 288h
0x180080169  pop     r15
0x18008016b  pop     r14
0x18008016d  pop     rdi
0x18008016e  pop     rsi
0x18008016f  pop     rbx
0x180080170  pop     rbp
0x180080171  retn
```
