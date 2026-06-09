# Cn::DllName::TryImport(char const *,void * *)

- ea: `0x1800a2214`
- end: `0x1800a2290`
- name: `?TryImport@DllName@Cn@@QEAA_NPEBDPEAPEAX@Z`
- size: `124`
- prototype: `bool __fastcall(Cn::DllName *__hidden this, const char *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a2128`

## callees

- `0x1800a2214`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2230`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a2230`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2272`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a2272`

## string_xrefs

- `0x1800a226b`: `WaitServiceState`

## pseudocode

```c
bool __fastcall Cn::DllName::TryImport(Cn::DllName *this, const char *a2, void **a3)
{
  HMODULE v3; // rcx
  HMODULE Library; // rax

  v3 = (HMODULE)qword_1801053D0;
  if ( !qword_1801053D0 )
  {
    Library = LoadLibraryExW(Microsoft::CoreUI::Registrar::g_dllServicePrivate, 0, 0);
    v3 = Library;
    if ( !Library )
      return (char)Library;
    qword_1801053D0 = (__int64)Library;
    qword_1801053D8 = (__int64)Cn::DllName::s_pFirst;
    Cn::DllName::s_pFirst = (struct Cn::DllName *)&Microsoft::CoreUI::Registrar::g_dllServicePrivate;
  }
  if ( Microsoft::CoreUI::Registrar::g_pfnWaitServiceState )
  {
    LOBYTE(Library) = 1;
  }
  else
  {
    Microsoft::CoreUI::Registrar::g_pfnWaitServiceState = (unsigned int (*)(struct SC_HANDLE__ *, unsigned int, unsigned int, void *))GetProcAddress(v3, "WaitServiceState");
    LOBYTE(Library) = Microsoft::CoreUI::Registrar::g_pfnWaitServiceState != 0;
  }
  return (char)Library;
}

```

## disassembly

```asm
0x1800a2214  sub     rsp, 28h
0x1800a2218  mov     rcx, cs:qword_1801053D0
0x1800a221f  test    rcx, rcx
0x1800a2222  jnz     short loc_1800A2261
0x1800a2224  mov     rcx, cs:?g_dllServicePrivate@Registrar@CoreUI@Microsoft@@3VDllName@Cn@@A; lpLibFileName
0x1800a222b  xor     r8d, r8d; dwFlags
0x1800a222e  xor     edx, edx; hFile
0x1800a2230  call    cs:__imp_LoadLibraryExW
0x1800a2236  mov     rcx, rax; hModule
0x1800a2239  test    rax, rax
0x1800a223c  jz      short loc_1800A2287
0x1800a223e  mov     cs:qword_1801053D0, rax
0x1800a2245  mov     rax, cs:?s_pFirst@DllName@Cn@@0PEAV12@EA; Cn::DllName * Cn::DllName::s_pFirst
0x1800a224c  mov     cs:qword_1801053D8, rax
0x1800a2253  lea     rax, ?g_dllServicePrivate@Registrar@CoreUI@Microsoft@@3VDllName@Cn@@A; Cn::DllName Microsoft::CoreUI::Registrar::g_dllServicePrivate
0x1800a225a  mov     cs:?s_pFirst@DllName@Cn@@0PEAV12@EA, rax; Cn::DllName * Cn::DllName::s_pFirst
0x1800a2261  cmp     cs:?g_pfnWaitServiceState@Registrar@CoreUI@Microsoft@@3P6AKPEAUSC_HANDLE__@@KKPEAX@ZEA, 0; ulong (*Microsoft::CoreUI::Registrar::g_pfnWaitServiceState)(SC_HANDLE__ *,ulong,ulong,void *)
0x1800a2269  jnz     short loc_1800A2289
0x1800a226b  lea     rdx, aWaitservicesta; "WaitServiceState"
0x1800a2272  call    cs:__imp_GetProcAddress
0x1800a2278  test    rax, rax
0x1800a227b  mov     cs:?g_pfnWaitServiceState@Registrar@CoreUI@Microsoft@@3P6AKPEAUSC_HANDLE__@@KKPEAX@ZEA, rax; ulong (*Microsoft::CoreUI::Registrar::g_pfnWaitServiceState)(SC_HANDLE__ *,ulong,ulong,void *)
0x1800a2282  setnz   al
0x1800a2285  jmp     short loc_1800A228B
0x1800a2287  jmp     short loc_1800A228B
0x1800a2289  mov     al, 1
0x1800a228b  add     rsp, 28h
0x1800a228f  retn
```
