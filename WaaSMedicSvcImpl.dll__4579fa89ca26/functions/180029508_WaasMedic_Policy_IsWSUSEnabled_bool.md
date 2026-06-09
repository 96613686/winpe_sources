# WaasMedic::Policy::IsWSUSEnabled(bool &)

- ea: `0x180029508`
- end: `0x1800296ae`
- name: `?IsWSUSEnabled@Policy@WaasMedic@@SAJAEA_N@Z`
- size: `422`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180068100`

## callees

- `0x180029508`
- `0x18002e81c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029594`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029594`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029660`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029696`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180029696`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029542`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002959f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002959f`

## string_xrefs

- `0x18002953b`: `UpdatePolicy.dll`
- `0x18002956a`: `UpdatePolicy.dll`
- `0x18002958a`: `ReadPolicy`
- `0x1800295b4`: `ReadPolicy`
- `0x180029656`: `ReleaseUpdatePolicyValue`
- `0x180029571`: `LoadLibraryEx for %ws failed with error hr = 0x%08x`
- `0x1800295dc`: `ReadPolicy failed with error hr = 0x%08x`
- `0x18002962e`: `Device does not have a configured managed update service.`
- `0x180029620`: `Device has a configured managed update service URL as %S`
- `0x18002967c`: `ReleaseUpdatePolicyValue failed with error hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::Policy::IsWSUSEnabled(bool *a1)
{
  unsigned int v2; // edi
  HMODULE v3; // rbx
  HMODULE Library; // rax
  signed int v5; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v8; // eax
  char v9; // al
  FARPROC v10; // rax
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF
  HMODULE v14; // [rsp+38h] [rbp+10h]

  v2 = 0;
  v13 = 0;
  v3 = 0;
  v14 = 0;
  if ( !byte_1800A55B9 )
  {
    Library = LoadLibraryExW(L"UpdatePolicy.dll", 0, 0x800u);
    v3 = Library;
    v14 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "ReadPolicy");
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(__int64, __int64 *))ProcAddress)(12, &v13);
        v2 = v8;
        if ( v8 >= 0 )
        {
          if ( *(_DWORD *)(v13 + 4) == 1 && *(_WORD *)(v13 + 16) == 8 )
          {
            v9 = 1;
            byte_1800A55B8 = 1;
          }
          else
          {
            v9 = byte_1800A55B8;
          }
          if ( v9 )
            LogLevelW(4u, L"Device has a configured managed update service URL as %S", *(_QWORD *)(v13 + 24));
          else
            LogLevelW(4u, L"Device does not have a configured managed update service.");
          byte_1800A55B9 = 1;
        }
        else
        {
          LogLevelW(2u, L"ReadPolicy failed with error hr = 0x%08x", (unsigned int)v8);
        }
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        LogLevelW(2u, L"GetProcAddress for %hs failed with error hr = 0x%08x", "ReadPolicy", v2);
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
  *a1 = byte_1800A55B8;
  if ( v3 )
  {
    if ( v13 )
    {
      v10 = GetProcAddress(v3, "ReleaseUpdatePolicyValue");
      if ( v10 )
      {
        v11 = ((__int64 (__fastcall *)(__int64 *))v10)(&v13);
        if ( v11 < 0 )
          LogLevelW(2u, L"ReleaseUpdatePolicyValue failed with error hr = 0x%08x", (unsigned int)v11);
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
0x180029508  mov     rax, rsp
0x18002950b  mov     [rax+18h], rbx
0x18002950f  mov     [rax+20h], rsi
0x180029513  push    rdi
0x180029514  sub     rsp, 20h
0x180029518  mov     rsi, rcx
0x18002951b  xor     edi, edi
0x18002951d  mov     [rax+8], rdi
0x180029521  xor     ebx, ebx
0x180029523  mov     [rax+10h], rbx
0x180029527  cmp     cs:byte_1800A55B9, bl
0x18002952d  jnz     loc_180029641
0x180029533  xor     edx, edx; hFile
0x180029535  mov     r8d, 800h; dwFlags
0x18002953b  lea     rcx, LibFileName; "UpdatePolicy.dll"
0x180029542  call    cs:__imp_LoadLibraryExW
0x180029548  mov     rbx, rax
0x18002954b  mov     [rsp+28h+arg_8], rax
0x180029550  test    rax, rax
0x180029553  jnz     short loc_18002958A
0x180029555  call    cs:__imp_GetLastError
0x18002955b  mov     edi, eax
0x18002955d  test    eax, eax
0x18002955f  jle     short loc_18002956A
0x180029561  movzx   edi, ax
0x180029564  or      edi, 80070000h
0x18002956a  lea     r8, LibFileName; "UpdatePolicy.dll"
0x180029571  lea     rdx, aLoadlibraryexF; "LoadLibraryEx for %ws failed with error"...
0x180029578  mov     r9d, edi
0x18002957b  mov     ecx, 2; unsigned __int8
0x180029580  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180029585  jmp     loc_180029641
0x18002958a  lea     rdx, aReadpolicy; "ReadPolicy"
0x180029591  mov     rcx, rax; hModule
0x180029594  call    cs:__imp_GetProcAddress
0x18002959a  test    rax, rax
0x18002959d  jnz     short loc_1800295C4
0x18002959f  call    cs:__imp_GetLastError
0x1800295a5  mov     edi, eax
0x1800295a7  test    eax, eax
0x1800295a9  jle     short loc_1800295B4
0x1800295ab  movzx   edi, ax
0x1800295ae  or      edi, 80070000h
0x1800295b4  lea     r8, aReadpolicy; "ReadPolicy"
0x1800295bb  lea     rdx, aGetprocaddress; "GetProcAddress for %hs failed with erro"...
0x1800295c2  jmp     short loc_180029578
0x1800295c4  lea     rdx, [rsp+28h+arg_0]
0x1800295c9  mov     ecx, 0Ch
0x1800295ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295d3  mov     edi, eax
0x1800295d5  test    eax, eax
0x1800295d7  jns     short loc_1800295EF
0x1800295d9  mov     r8d, eax
0x1800295dc  lea     rdx, aReadpolicyFail; "ReadPolicy failed with error hr = 0x%08"...
0x1800295e3  mov     ecx, 2; unsigned __int8
0x1800295e8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800295ed  jmp     short loc_180029641
0x1800295ef  mov     r8, [rsp+28h+arg_0]
0x1800295f4  cmp     dword ptr [r8+4], 1
0x1800295f9  jnz     short loc_18002960D
0x1800295fb  cmp     word ptr [r8+10h], 8
0x180029601  jnz     short loc_18002960D
0x180029603  mov     al, 1
0x180029605  mov     cs:byte_1800A55B8, al
0x18002960b  jmp     short loc_180029613
0x18002960d  mov     al, cs:byte_1800A55B8
0x180029613  mov     ecx, 4; unsigned __int8
0x180029618  test    al, al
0x18002961a  jz      short loc_18002962E
0x18002961c  mov     r8, [r8+18h]
0x180029620  lea     rdx, aDeviceHasAConf; "Device has a configured managed update "...
0x180029627  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002962c  jmp     short loc_18002963A
0x18002962e  lea     rdx, aDeviceDoesNotH; "Device does not have a configured manag"...
0x180029635  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002963a  mov     cs:byte_1800A55B9, 1
0x180029641  mov     al, cs:byte_1800A55B8
0x180029647  mov     [rsi], al
0x180029649  test    rbx, rbx
0x18002964c  jz      short loc_18002968E
0x18002964e  cmp     [rsp+28h+arg_0], 0
0x180029654  jz      short loc_18002968E
0x180029656  lea     rdx, aReleaseupdatep_0; "ReleaseUpdatePolicyValue"
0x18002965d  mov     rcx, rbx; hModule
0x180029660  call    cs:__imp_GetProcAddress
0x180029666  test    rax, rax
0x180029669  jz      short loc_18002968E
0x18002966b  lea     rcx, [rsp+28h+arg_0]
0x180029670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029675  test    eax, eax
0x180029677  jns     short loc_18002968E
0x180029679  mov     r8d, eax
0x18002967c  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue failed with er"...
0x180029683  mov     ecx, 2; unsigned __int8
0x180029688  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002968d  nop
0x18002968e  test    rbx, rbx
0x180029691  jz      short loc_18002969C
0x180029693  mov     rcx, rbx; hLibModule
0x180029696  call    cs:__imp_FreeLibrary
0x18002969c  mov     eax, edi
0x18002969e  mov     rbx, [rsp+28h+arg_10]
0x1800296a3  mov     rsi, [rsp+28h+arg_18]
0x1800296a8  add     rsp, 20h
0x1800296ac  pop     rdi
0x1800296ad  retn
```
