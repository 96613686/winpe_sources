# WaasMedic::Policy::IsWSUSEnabled(bool &)

- ea: `0x180030524`
- end: `0x1800306ca`
- name: `?IsWSUSEnabled@Policy@WaasMedic@@SAJAEA_N@Z`
- size: `422`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c638`

## callees

- `0x18002543c`
- `0x180030524`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800305b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003067c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800305b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003067c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003055e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003055e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800306b2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800306b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030571`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800305bb`

## string_xrefs

- `0x180030557`: `UpdatePolicy.dll`
- `0x180030586`: `UpdatePolicy.dll`
- `0x1800305a6`: `ReadPolicy`
- `0x1800305d0`: `ReadPolicy`
- `0x180030672`: `ReleaseUpdatePolicyValue`
- `0x18003058d`: `LoadLibraryEx for %ws failed with error hr = 0x%08x`
- `0x1800305f8`: `ReadPolicy failed with error hr = 0x%08x`
- `0x18003064a`: `Device does not have a configured managed update service.`
- `0x18003063c`: `Device has a configured managed update service URL as %S`
- `0x180030698`: `ReleaseUpdatePolicyValue failed with error hr = 0x%08x`

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
  if ( !byte_180098DF5 )
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
            byte_180098DF4 = 1;
          }
          else
          {
            v9 = byte_180098DF4;
          }
          if ( v9 )
            LogLevelW(4u, L"Device has a configured managed update service URL as %S", *(_QWORD *)(v13 + 24));
          else
            LogLevelW(4u, L"Device does not have a configured managed update service.");
          byte_180098DF5 = 1;
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
  *a1 = byte_180098DF4;
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
0x180030524  mov     rax, rsp
0x180030527  mov     [rax+18h], rbx
0x18003052b  mov     [rax+20h], rsi
0x18003052f  push    rdi
0x180030530  sub     rsp, 20h
0x180030534  mov     rsi, rcx
0x180030537  xor     edi, edi
0x180030539  mov     [rax+8], rdi
0x18003053d  xor     ebx, ebx
0x18003053f  mov     [rax+10h], rbx
0x180030543  cmp     cs:byte_180098DF5, bl
0x180030549  jnz     loc_18003065D
0x18003054f  xor     edx, edx; hFile
0x180030551  mov     r8d, 800h; dwFlags
0x180030557  lea     rcx, aUpdatepolicyDl; "UpdatePolicy.dll"
0x18003055e  call    cs:__imp_LoadLibraryExW
0x180030564  mov     rbx, rax
0x180030567  mov     [rsp+28h+arg_8], rax
0x18003056c  test    rax, rax
0x18003056f  jnz     short loc_1800305A6
0x180030571  call    cs:__imp_GetLastError
0x180030577  mov     edi, eax
0x180030579  test    eax, eax
0x18003057b  jle     short loc_180030586
0x18003057d  movzx   edi, ax
0x180030580  or      edi, 80070000h
0x180030586  lea     r8, aUpdatepolicyDl; "UpdatePolicy.dll"
0x18003058d  lea     rdx, aLoadlibraryexF; "LoadLibraryEx for %ws failed with error"...
0x180030594  mov     r9d, edi
0x180030597  mov     ecx, 2; unsigned __int8
0x18003059c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800305a1  jmp     loc_18003065D
0x1800305a6  lea     rdx, aReadpolicy; "ReadPolicy"
0x1800305ad  mov     rcx, rax; hModule
0x1800305b0  call    cs:__imp_GetProcAddress
0x1800305b6  test    rax, rax
0x1800305b9  jnz     short loc_1800305E0
0x1800305bb  call    cs:__imp_GetLastError
0x1800305c1  mov     edi, eax
0x1800305c3  test    eax, eax
0x1800305c5  jle     short loc_1800305D0
0x1800305c7  movzx   edi, ax
0x1800305ca  or      edi, 80070000h
0x1800305d0  lea     r8, aReadpolicy; "ReadPolicy"
0x1800305d7  lea     rdx, aGetprocaddress; "GetProcAddress for %hs failed with erro"...
0x1800305de  jmp     short loc_180030594
0x1800305e0  lea     rdx, [rsp+28h+arg_0]
0x1800305e5  mov     ecx, 0Ch
0x1800305ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305ef  mov     edi, eax
0x1800305f1  test    eax, eax
0x1800305f3  jns     short loc_18003060B
0x1800305f5  mov     r8d, eax
0x1800305f8  lea     rdx, aReadpolicyFail; "ReadPolicy failed with error hr = 0x%08"...
0x1800305ff  mov     ecx, 2; unsigned __int8
0x180030604  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030609  jmp     short loc_18003065D
0x18003060b  mov     r8, [rsp+28h+arg_0]
0x180030610  cmp     dword ptr [r8+4], 1
0x180030615  jnz     short loc_180030629
0x180030617  cmp     word ptr [r8+10h], 8
0x18003061d  jnz     short loc_180030629
0x18003061f  mov     al, 1
0x180030621  mov     cs:byte_180098DF4, al
0x180030627  jmp     short loc_18003062F
0x180030629  mov     al, cs:byte_180098DF4
0x18003062f  mov     ecx, 4; unsigned __int8
0x180030634  test    al, al
0x180030636  jz      short loc_18003064A
0x180030638  mov     r8, [r8+18h]
0x18003063c  lea     rdx, aDeviceHasAConf; "Device has a configured managed update "...
0x180030643  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030648  jmp     short loc_180030656
0x18003064a  lea     rdx, aDeviceDoesNotH; "Device does not have a configured manag"...
0x180030651  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030656  mov     cs:byte_180098DF5, 1
0x18003065d  mov     al, cs:byte_180098DF4
0x180030663  mov     [rsi], al
0x180030665  test    rbx, rbx
0x180030668  jz      short loc_1800306AA
0x18003066a  cmp     [rsp+28h+arg_0], 0
0x180030670  jz      short loc_1800306AA
0x180030672  lea     rdx, aReleaseupdatep_0; "ReleaseUpdatePolicyValue"
0x180030679  mov     rcx, rbx; hModule
0x18003067c  call    cs:__imp_GetProcAddress
0x180030682  test    rax, rax
0x180030685  jz      short loc_1800306AA
0x180030687  lea     rcx, [rsp+28h+arg_0]
0x18003068c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030691  test    eax, eax
0x180030693  jns     short loc_1800306AA
0x180030695  mov     r8d, eax
0x180030698  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue failed with er"...
0x18003069f  mov     ecx, 2; unsigned __int8
0x1800306a4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800306a9  nop
0x1800306aa  test    rbx, rbx
0x1800306ad  jz      short loc_1800306B8
0x1800306af  mov     rcx, rbx; hLibModule
0x1800306b2  call    cs:__imp_FreeLibrary
0x1800306b8  mov     eax, edi
0x1800306ba  mov     rbx, [rsp+28h+arg_10]
0x1800306bf  mov     rsi, [rsp+28h+arg_18]
0x1800306c4  add     rsp, 20h
0x1800306c8  pop     rdi
0x1800306c9  retn
```
