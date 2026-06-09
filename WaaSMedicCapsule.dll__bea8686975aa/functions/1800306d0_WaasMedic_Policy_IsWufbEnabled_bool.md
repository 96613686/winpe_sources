# WaasMedic::Policy::IsWufbEnabled(bool &)

- ea: `0x1800306d0`
- end: `0x180030888`
- name: `?IsWufbEnabled@Policy@WaasMedic@@SAJAEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001c638`

## callees

- `0x18002543c`
- `0x1800306d0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003075d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003083e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003075d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003083e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003070d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003070d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030872`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030720`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030768`

## string_xrefs

- `0x180030706`: `UpdatePolicy.dll`
- `0x180030735`: `UpdatePolicy.dll`
- `0x180030753`: `ReadPolicyWithFallback`
- `0x18003077d`: `ReadPolicyWithFallback`
- `0x18003073c`: `LoadLibraryEx for %ws failed with error hr = 0x%08x`
- `0x1800307a5`: `ReadPolicyWithFallback failed with error hr = 0x%08x`
- `0x180030807`: `Device %s configured for WUfB`

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
  if ( !byte_180098DF2 )
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
            byte_180098DF3 = *(_DWORD *)(v13 + 24) == 1;
            v9 = L"is";
            if ( !byte_180098DF3 )
              v9 = L"is not";
            LogLevelW(4u, L"Device %s configured for WUfB", v9);
          }
          byte_180098DF2 = 1;
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
  *a1 = byte_180098DF3;
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
0x1800306d0  mov     [rsp+arg_10], rbx
0x1800306d5  push    rsi
0x1800306d6  push    rdi
0x1800306d7  push    r14
0x1800306d9  sub     rsp, 20h
0x1800306dd  mov     rsi, rcx
0x1800306e0  xor     edi, edi
0x1800306e2  mov     [rsp+38h+arg_0], rdi
0x1800306e7  xor     ebx, ebx
0x1800306e9  mov     [rsp+38h+arg_8], rbx
0x1800306ee  lea     r14d, [rdi+2]
0x1800306f2  cmp     cs:byte_180098DF2, bl
0x1800306f8  jnz     loc_18003081F
0x1800306fe  xor     edx, edx; hFile
0x180030700  mov     r8d, 800h; dwFlags
0x180030706  lea     rcx, aUpdatepolicyDl; "UpdatePolicy.dll"
0x18003070d  call    cs:__imp_LoadLibraryExW
0x180030713  mov     rbx, rax
0x180030716  mov     [rsp+38h+arg_8], rax
0x18003071b  test    rax, rax
0x18003071e  jnz     short loc_180030753
0x180030720  call    cs:__imp_GetLastError
0x180030726  mov     edi, eax
0x180030728  test    eax, eax
0x18003072a  jle     short loc_180030735
0x18003072c  movzx   edi, ax
0x18003072f  or      edi, 80070000h
0x180030735  lea     r8, aUpdatepolicyDl; "UpdatePolicy.dll"
0x18003073c  lea     rdx, aLoadlibraryexF; "LoadLibraryEx for %ws failed with error"...
0x180030743  mov     r9d, edi
0x180030746  mov     ecx, r14d; unsigned __int8
0x180030749  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003074e  jmp     loc_18003081F
0x180030753  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x18003075a  mov     rcx, rax; hModule
0x18003075d  call    cs:__imp_GetProcAddress
0x180030763  test    rax, rax
0x180030766  jnz     short loc_18003078D
0x180030768  call    cs:__imp_GetLastError
0x18003076e  mov     edi, eax
0x180030770  test    eax, eax
0x180030772  jle     short loc_18003077D
0x180030774  movzx   edi, ax
0x180030777  or      edi, 80070000h
0x18003077d  lea     r8, aReadpolicywith; "ReadPolicyWithFallback"
0x180030784  lea     rdx, aGetprocaddress; "GetProcAddress for %hs failed with erro"...
0x18003078b  jmp     short loc_180030743
0x18003078d  lea     rdx, [rsp+38h+arg_0]
0x180030792  mov     ecx, 20h ; ' '
0x180030797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003079c  mov     edi, eax
0x18003079e  test    eax, eax
0x1800307a0  jns     short loc_1800307B6
0x1800307a2  mov     r8d, eax
0x1800307a5  lea     rdx, aReadpolicywith_0; "ReadPolicyWithFallback failed with erro"...
0x1800307ac  mov     ecx, r14d; unsigned __int8
0x1800307af  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800307b4  jmp     short loc_18003081F
0x1800307b6  mov     rax, [rsp+38h+arg_0]
0x1800307bb  cmp     dword ptr [rax+4], 1
0x1800307bf  jnz     short loc_180030818
0x1800307c1  movzx   ecx, word ptr [rax+10h]
0x1800307c5  mov     r8d, 3
0x1800307cb  cmp     cx, r8w
0x1800307cf  jz      short loc_1800307EA
0x1800307d1  mov     edi, 8007025Ch
0x1800307d6  mov     r9d, ecx
0x1800307d9  lea     rdx, aUnexpectedVari; "Unexpected VARIANT data type for WUfB p"...
0x1800307e0  mov     ecx, r14d; unsigned __int8
0x1800307e3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800307e8  jmp     short loc_18003081F
0x1800307ea  cmp     dword ptr [rax+18h], 1
0x1800307ee  setz    cs:byte_180098DF3
0x1800307f5  lea     rcx, aIsNot; "is not"
0x1800307fc  lea     r8, aIs; "is"
0x180030803  cmovnz  r8, rcx
0x180030807  lea     rdx, aDeviceSConfigu; "Device %s configured for WUfB"
0x18003080e  mov     ecx, 4; unsigned __int8
0x180030813  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030818  mov     cs:byte_180098DF2, 1
0x18003081f  mov     al, cs:byte_180098DF3
0x180030825  mov     [rsi], al
0x180030827  test    rbx, rbx
0x18003082a  jz      short loc_18003086A
0x18003082c  cmp     [rsp+38h+arg_0], 0
0x180030832  jz      short loc_18003086A
0x180030834  lea     rdx, aReleaseenterpr; "ReleaseEnterprisePolicyValue"
0x18003083b  mov     rcx, rbx; hModule
0x18003083e  call    cs:__imp_GetProcAddress
0x180030844  test    rax, rax
0x180030847  jz      short loc_18003086A
0x180030849  lea     rcx, [rsp+38h+arg_0]
0x18003084e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030853  test    eax, eax
0x180030855  jns     short loc_18003086A
0x180030857  mov     r8d, eax
0x18003085a  lea     rdx, aReleaseenterpr_0; "ReleaseEnterprisePolicyValue failed wit"...
0x180030861  mov     ecx, r14d; unsigned __int8
0x180030864  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030869  nop
0x18003086a  test    rbx, rbx
0x18003086d  jz      short loc_180030878
0x18003086f  mov     rcx, rbx; hLibModule
0x180030872  call    cs:__imp_FreeLibrary
0x180030878  mov     eax, edi
0x18003087a  mov     rbx, [rsp+38h+arg_10]
0x18003087f  add     rsp, 20h
0x180030883  pop     r14
0x180030885  pop     rdi
0x180030886  pop     rsi
0x180030887  retn
```
