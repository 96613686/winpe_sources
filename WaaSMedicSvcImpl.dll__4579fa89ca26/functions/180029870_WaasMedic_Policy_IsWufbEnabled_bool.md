# WaasMedic::Policy::IsWufbEnabled(bool &)

- ea: `0x180029870`
- end: `0x180029a28`
- name: `?IsWufbEnabled@Policy@WaasMedic@@SAJAEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180068100`

## callees

- `0x180029870`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800298fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800299de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800298fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800299de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029a12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029a12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800298ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800298ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029908`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029908`

## string_xrefs

- `0x1800298a6`: `UpdatePolicy.dll`
- `0x1800298d5`: `UpdatePolicy.dll`
- `0x1800298f3`: `ReadPolicyWithFallback`
- `0x18002991d`: `ReadPolicyWithFallback`
- `0x1800298dc`: `LoadLibraryEx for %ws failed with error hr = 0x%08x`
- `0x180029945`: `ReadPolicyWithFallback failed with error hr = 0x%08x`
- `0x1800299a7`: `Device %s configured for WUfB`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::Policy::IsWufbEnabled(bool *a1)
{
  unsigned int v2; // edi
  HMODULE v3; // rbx
  HMODULE Library; // rax
  signed int v5; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v8; // eax
  const wchar_t *v9; // r8
  FARPROC v10; // rax
  int v11; // eax
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF
  HMODULE v14; // [rsp+48h] [rbp+10h]

  v2 = 0;
  v13 = 0;
  v3 = 0;
  v14 = 0;
  if ( !byte_1800A55B6 )
  {
    Library = LoadLibraryExW(L"UpdatePolicy.dll", 0, 0x800u);
    v3 = Library;
    v14 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "ReadPolicyWithFallback");
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(32, &v13);
        v2 = v8;
        if ( v8 >= 0 )
        {
          if ( *(_DWORD *)(v13 + 4) == 1 )
          {
            if ( *(_WORD *)(v13 + 16) != 3 )
            {
              v2 = -2147024292;
              LogLevelW(
                2u,
                L"Unexpected VARIANT data type for WUfB policy value! Expected: %u; Actual: %u",
                3,
                *(unsigned __int16 *)(v13 + 16));
              goto LABEL_20;
            }
            byte_1800A55B7 = *(_DWORD *)(v13 + 24) == 1;
            v9 = L"is";
            if ( !byte_1800A55B7 )
              v9 = L"is not";
            LogLevelW(4u, L"Device %s configured for WUfB", v9);
          }
          byte_1800A55B6 = 1;
          goto LABEL_20;
        }
        LogLevelW(2u, L"ReadPolicyWithFallback failed with error hr = 0x%08x", (unsigned int)v8);
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        LogLevelW(2u, L"GetProcAddress for %hs failed with error hr = 0x%08x", "ReadPolicyWithFallback", v2);
      }
    }
    else
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      LogLevelW(2u, L"LoadLibraryEx for %ws failed with error hr = 0x%08x", L"UpdatePolicy.dll", v2);
    }
  }
LABEL_20:
  *a1 = byte_1800A55B7;
  if ( v3 )
  {
    if ( v13 )
    {
      v10 = GetProcAddress(v3, "ReleaseEnterprisePolicyValue");
      if ( v10 )
      {
        v11 = ((__int64 (__fastcall *)(__int64 *))v10)(&v13);
        if ( v11 < 0 )
          LogLevelW(2u, L"ReleaseEnterprisePolicyValue failed with error hr = 0x%08x", (unsigned int)v11);
      }
    }
  }
  if ( v3 )
    FreeLibrary(v3);
  return v2;
}

```

## disassembly

```asm
0x180029870  mov     [rsp+arg_10], rbx
0x180029875  push    rsi
0x180029876  push    rdi
0x180029877  push    r14
0x180029879  sub     rsp, 20h
0x18002987d  mov     rsi, rcx
0x180029880  xor     edi, edi
0x180029882  mov     [rsp+38h+arg_0], rdi
0x180029887  xor     ebx, ebx
0x180029889  mov     [rsp+38h+arg_8], rbx
0x18002988e  lea     r14d, [rdi+2]
0x180029892  cmp     cs:byte_1800A55B6, bl
0x180029898  jnz     loc_1800299BF
0x18002989e  xor     edx, edx; hFile
0x1800298a0  mov     r8d, 800h; dwFlags
0x1800298a6  lea     rcx, LibFileName; "UpdatePolicy.dll"
0x1800298ad  call    cs:__imp_LoadLibraryExW
0x1800298b3  mov     rbx, rax
0x1800298b6  mov     [rsp+38h+arg_8], rax
0x1800298bb  test    rax, rax
0x1800298be  jnz     short loc_1800298F3
0x1800298c0  call    cs:__imp_GetLastError
0x1800298c6  mov     edi, eax
0x1800298c8  test    eax, eax
0x1800298ca  jle     short loc_1800298D5
0x1800298cc  movzx   edi, ax
0x1800298cf  or      edi, 80070000h
0x1800298d5  lea     r8, LibFileName; "UpdatePolicy.dll"
0x1800298dc  lea     rdx, aLoadlibraryexF; "LoadLibraryEx for %ws failed with error"...
0x1800298e3  mov     r9d, edi
0x1800298e6  mov     ecx, r14d; unsigned __int8
0x1800298e9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800298ee  jmp     loc_1800299BF
0x1800298f3  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x1800298fa  mov     rcx, rax; hModule
0x1800298fd  call    cs:__imp_GetProcAddress
0x180029903  test    rax, rax
0x180029906  jnz     short loc_18002992D
0x180029908  call    cs:__imp_GetLastError
0x18002990e  mov     edi, eax
0x180029910  test    eax, eax
0x180029912  jle     short loc_18002991D
0x180029914  movzx   edi, ax
0x180029917  or      edi, 80070000h
0x18002991d  lea     r8, aReadpolicywith; "ReadPolicyWithFallback"
0x180029924  lea     rdx, aGetprocaddress; "GetProcAddress for %hs failed with erro"...
0x18002992b  jmp     short loc_1800298E3
0x18002992d  lea     rdx, [rsp+38h+arg_0]
0x180029932  mov     ecx, 20h ; ' '
0x180029937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002993c  mov     edi, eax
0x18002993e  test    eax, eax
0x180029940  jns     short loc_180029956
0x180029942  mov     r8d, eax
0x180029945  lea     rdx, aReadpolicywith_0; "ReadPolicyWithFallback failed with erro"...
0x18002994c  mov     ecx, r14d; unsigned __int8
0x18002994f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180029954  jmp     short loc_1800299BF
0x180029956  mov     rax, [rsp+38h+arg_0]
0x18002995b  cmp     dword ptr [rax+4], 1
0x18002995f  jnz     short loc_1800299B8
0x180029961  movzx   ecx, word ptr [rax+10h]
0x180029965  mov     r8d, 3
0x18002996b  cmp     cx, r8w
0x18002996f  jz      short loc_18002998A
0x180029971  mov     edi, 8007025Ch
0x180029976  mov     r9d, ecx
0x180029979  lea     rdx, aUnexpectedVari_2; "Unexpected VARIANT data type for WUfB p"...
0x180029980  mov     ecx, r14d; unsigned __int8
0x180029983  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180029988  jmp     short loc_1800299BF
0x18002998a  cmp     dword ptr [rax+18h], 1
0x18002998e  setz    cs:byte_1800A55B7
0x180029995  lea     rcx, aIsNot; "is not"
0x18002999c  lea     r8, aIs; "is"
0x1800299a3  cmovnz  r8, rcx
0x1800299a7  lea     rdx, aDeviceSConfigu; "Device %s configured for WUfB"
0x1800299ae  mov     ecx, 4; unsigned __int8
0x1800299b3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800299b8  mov     cs:byte_1800A55B6, 1
0x1800299bf  mov     al, cs:byte_1800A55B7
0x1800299c5  mov     [rsi], al
0x1800299c7  test    rbx, rbx
0x1800299ca  jz      short loc_180029A0A
0x1800299cc  cmp     [rsp+38h+arg_0], 0
0x1800299d2  jz      short loc_180029A0A
0x1800299d4  lea     rdx, aReleaseenterpr; "ReleaseEnterprisePolicyValue"
0x1800299db  mov     rcx, rbx; hModule
0x1800299de  call    cs:__imp_GetProcAddress
0x1800299e4  test    rax, rax
0x1800299e7  jz      short loc_180029A0A
0x1800299e9  lea     rcx, [rsp+38h+arg_0]
0x1800299ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299f3  test    eax, eax
0x1800299f5  jns     short loc_180029A0A
0x1800299f7  mov     r8d, eax
0x1800299fa  lea     rdx, aReleaseenterpr_0; "ReleaseEnterprisePolicyValue failed wit"...
0x180029a01  mov     ecx, r14d; unsigned __int8
0x180029a04  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180029a09  nop
0x180029a0a  test    rbx, rbx
0x180029a0d  jz      short loc_180029A18
0x180029a0f  mov     rcx, rbx; hLibModule
0x180029a12  call    cs:__imp_FreeLibrary
0x180029a18  mov     eax, edi
0x180029a1a  mov     rbx, [rsp+38h+arg_10]
0x180029a1f  add     rsp, 20h
0x180029a23  pop     r14
0x180029a25  pop     rdi
0x180029a26  pop     rsi
0x180029a27  retn
```
