# WaasMedic::Policy::IsWUConnected(bool &)

- ea: `0x1800296b4`
- end: `0x180029869`
- name: `?IsWUConnected@Policy@WaasMedic@@SAJAEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18005f348`
- `0x180068100`

## callees

- `0x1800296b4`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029732`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002981d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029732`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002981d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029853`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029853`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800296dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800296dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002973d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002973d`

## string_xrefs

- `0x1800296d5`: `UpdatePolicy.dll`
- `0x180029707`: `UpdatePolicy.dll`
- `0x180029728`: `ReadPolicy`
- `0x180029755`: `ReadPolicy`
- `0x180029813`: `ReleaseUpdatePolicyValue`
- `0x18002970e`: `LoadLibraryEx for %ws failed with error hr = 0x%08x`
- `0x18002978f`: `ReadPolicy failed with error hr = 0x%08x`
- `0x180029839`: `ReleaseUpdatePolicyValue failed with error hr = 0x%08x`
- `0x1800297c7`: `Unexpected VARIANT data type for AllowUpdateService policy value! Expected: %u; Actual: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::Policy::IsWUConnected(bool *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rsi
  signed int LastError; // eax
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  signed int v7; // eax
  bool v8; // di
  int v9; // eax
  const wchar_t *v10; // r8
  FARPROC v11; // rax
  int v12; // eax
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF
  HMODULE v15; // [rsp+48h] [rbp+10h]

  v14 = 0;
  Library = LoadLibraryExW(L"UpdatePolicy.dll", 0, 0x800u);
  v3 = Library;
  v15 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"LoadLibraryEx for %ws failed with error hr = 0x%08x", L"UpdatePolicy.dll", v5);
    *a1 = 1;
    goto LABEL_23;
  }
  ProcAddress = GetProcAddress(Library, "ReadPolicy");
  if ( ProcAddress )
  {
    v9 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(15, &v14);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v8 = 1;
      if ( *(_DWORD *)(v14 + 4) == 1 )
      {
        if ( *(_WORD *)(v14 + 16) != 3 )
        {
          v5 = -2147024292;
          LogLevelW(
            2u,
            L"Unexpected VARIANT data type for AllowUpdateService policy value! Expected: %u; Actual: %u",
            3,
            *(unsigned __int16 *)(v14 + 16));
          goto LABEL_19;
        }
        v8 = *(_DWORD *)(v14 + 24) != 0;
      }
      v10 = L"is not";
      if ( !v8 )
        v10 = L"is";
      LogLevelW(4u, L"Device WU connected status %s blocked by policy.", v10);
      goto LABEL_19;
    }
    LogLevelW(2u, L"ReadPolicy failed with error hr = 0x%08x", (unsigned int)v9);
  }
  else
  {
    v7 = GetLastError();
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    LogLevelW(2u, L"GetProcAddress for %hs failed with error hr = 0x%08x", "ReadPolicy", v5);
  }
  v8 = 1;
LABEL_19:
  *a1 = v8;
  if ( v14 )
  {
    v11 = GetProcAddress(v3, "ReleaseUpdatePolicyValue");
    if ( v11 )
    {
      v12 = ((__int64 (__fastcall *)(__int64 *))v11)(&v14);
      if ( v12 < 0 )
        LogLevelW(2u, L"ReleaseUpdatePolicyValue failed with error hr = 0x%08x", (unsigned int)v12);
    }
  }
LABEL_23:
  if ( v3 )
    FreeLibrary(v3);
  return v5;
}

```

## disassembly

```asm
0x1800296b4  mov     [rsp+arg_10], rbx
0x1800296b9  push    rsi
0x1800296ba  push    rdi
0x1800296bb  push    r14
0x1800296bd  sub     rsp, 20h
0x1800296c1  mov     r14, rcx
0x1800296c4  mov     [rsp+38h+arg_0], 0
0x1800296cd  xor     edx, edx; hFile
0x1800296cf  mov     r8d, 800h; dwFlags
0x1800296d5  lea     rcx, LibFileName; "UpdatePolicy.dll"
0x1800296dc  call    cs:__imp_LoadLibraryExW
0x1800296e2  mov     rsi, rax
0x1800296e5  mov     [rsp+38h+arg_8], rax
0x1800296ea  test    rax, rax
0x1800296ed  jnz     short loc_180029728
0x1800296ef  call    cs:__imp_GetLastError
0x1800296f5  mov     ebx, eax
0x1800296f7  test    eax, eax
0x1800296f9  jle     short loc_180029704
0x1800296fb  movzx   ebx, ax
0x1800296fe  or      ebx, 80070000h
0x180029704  mov     r9d, ebx
0x180029707  lea     r8, LibFileName; "UpdatePolicy.dll"
0x18002970e  lea     rdx, aLoadlibraryexF; "LoadLibraryEx for %ws failed with error"...
0x180029715  mov     ecx, 2; unsigned __int8
0x18002971a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002971f  mov     byte ptr [r14], 1
0x180029723  jmp     loc_18002984B
0x180029728  lea     rdx, aReadpolicy; "ReadPolicy"
0x18002972f  mov     rcx, rsi; hModule
0x180029732  call    cs:__imp_GetProcAddress
0x180029738  test    rax, rax
0x18002973b  jnz     short loc_180029777
0x18002973d  call    cs:__imp_GetLastError
0x180029743  mov     ebx, eax
0x180029745  test    eax, eax
0x180029747  jle     short loc_180029752
0x180029749  movzx   ebx, ax
0x18002974c  or      ebx, 80070000h
0x180029752  mov     r9d, ebx
0x180029755  lea     r8, aReadpolicy; "ReadPolicy"
0x18002975c  lea     rdx, aGetprocaddress; "GetProcAddress for %hs failed with erro"...
0x180029763  mov     ecx, 2; unsigned __int8
0x180029768  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002976d  mov     edi, 1
0x180029772  jmp     loc_180029808
0x180029777  lea     rdx, [rsp+38h+arg_0]
0x18002977c  mov     ecx, 0Fh
0x180029781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029786  mov     ebx, eax
0x180029788  test    eax, eax
0x18002978a  jns     short loc_1800297A2
0x18002978c  mov     r8d, eax
0x18002978f  lea     rdx, aReadpolicyFail; "ReadPolicy failed with error hr = 0x%08"...
0x180029796  mov     ecx, 2; unsigned __int8
0x18002979b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800297a0  jmp     short loc_18002976D
0x1800297a2  mov     edi, 1
0x1800297a7  mov     rax, [rsp+38h+arg_0]
0x1800297ac  cmp     [rax+4], edi
0x1800297af  jnz     short loc_1800297E2
0x1800297b1  movzx   ecx, word ptr [rax+10h]
0x1800297b5  lea     r8d, [rdi+2]
0x1800297b9  cmp     cx, r8w
0x1800297bd  jz      short loc_1800297D8
0x1800297bf  mov     ebx, 8007025Ch
0x1800297c4  mov     r9d, ecx
0x1800297c7  lea     rdx, aUnexpectedVari_0; "Unexpected VARIANT data type for AllowU"...
0x1800297ce  lea     ecx, [rdi+1]; unsigned __int8
0x1800297d1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800297d6  jmp     short loc_180029808
0x1800297d8  mov     eax, [rax+18h]
0x1800297db  neg     eax
0x1800297dd  sbb     cl, cl
0x1800297df  and     dil, cl
0x1800297e2  lea     rax, aIs; "is"
0x1800297e9  lea     r8, aIsNot; "is not"
0x1800297f0  test    dil, dil
0x1800297f3  cmovz   r8, rax
0x1800297f7  lea     rdx, aDeviceWuConnec; "Device WU connected status %s blocked b"...
0x1800297fe  mov     ecx, 4; unsigned __int8
0x180029803  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180029808  mov     [r14], dil
0x18002980b  cmp     [rsp+38h+arg_0], 0
0x180029811  jz      short loc_18002984B
0x180029813  lea     rdx, aReleaseupdatep_0; "ReleaseUpdatePolicyValue"
0x18002981a  mov     rcx, rsi; hModule
0x18002981d  call    cs:__imp_GetProcAddress
0x180029823  test    rax, rax
0x180029826  jz      short loc_18002984B
0x180029828  lea     rcx, [rsp+38h+arg_0]
0x18002982d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029832  test    eax, eax
0x180029834  jns     short loc_18002984B
0x180029836  mov     r8d, eax
0x180029839  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue failed with er"...
0x180029840  mov     ecx, 2; unsigned __int8
0x180029845  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002984a  nop
0x18002984b  test    rsi, rsi
0x18002984e  jz      short loc_180029859
0x180029850  mov     rcx, rsi; hLibModule
0x180029853  call    cs:__imp_FreeLibrary
0x180029859  mov     eax, ebx
0x18002985b  mov     rbx, [rsp+38h+arg_10]
0x180029860  add     rsp, 20h
0x180029864  pop     r14
0x180029866  pop     rdi
0x180029867  pop     rsi
0x180029868  retn
```
