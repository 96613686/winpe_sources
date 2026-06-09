# CCodeDownload::RegisterPEDll(char const *,int)

- ea: `0x1800c4750`
- end: `0x1800c48f5`
- name: `?RegisterPEDll@CCodeDownload@@QEAAJPEBDH@Z`
- size: `421`
- prototype: `__int64 __fastcall(CCodeDownload *__hidden this, const char *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c1868`

## callees

- `0x1800a17a0`
- `0x1800bd648`
- `0x1800c4750`
- `0x1800d0830`
- `0x18010e6d8`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c48e3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c48e3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800c4888`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800c4888`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c48b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c48b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c47d4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c47d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4814`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c48c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c483b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c483b`

## string_xrefs

- `0x1800c48ad`: `DllRegisterServer`
- `0x1800c47c6`: `CLSID\{aaf8c6ce-f972-11d0-97eb-00aa00615333}`

## pseudocode

```c
__int64 __fastcall CCodeDownload::RegisterPEDll(CCodeDownload *this, const char *a2, int a3)
{
  unsigned int v6; // eax
  CDLDebugLog *v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // ecx
  HMODULE Library; // rax
  HMODULE v11; // rdi
  signed int v12; // eax
  __int64 (*ProcAddress)(void); // rax
  signed int LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+20h] BYREF

  ppv = 0;
  v6 = IsRegisterableDLL(a2);
  v7 = (CDLDebugLog *)*((_QWORD *)this + 62);
  v8 = v6;
  if ( v6 )
  {
    CDLDebugLog::DebugOut(v7, 1, 1, 0x2710u, a2);
  }
  else
  {
    CDLDebugLog::DebugOut(v7, 1, 1, 0x272Au, a2);
    hKey = 0;
    if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID\\{aaf8c6ce-f972-11d0-97eb-00aa00615333}", 0, 0x2000000u, &hKey) )
    {
      ppv = 0;
    }
    else
    {
      RegCloseKey(hKey);
      v8 = CoCreateInstance(&CLSID_IActiveXSafetyProvider, 0, 1u, &IID_IActiveXSafetyProvider, &ppv);
      if ( v8 )
        return v8;
      v9 = (unsigned int)ppv;
      if ( ppv )
      {
        v8 = (*(__int64 (__fastcall **)(LPVOID, const char *))(*(_QWORD *)ppv + 72LL))(ppv, a2);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v8;
      }
    }
    if ( (unsigned int)InstallBrokerIsNeeded(v9) )
    {
      return (unsigned int)CCodeDownload::CallRegisterDllFileBroker(this, a2, a3, 0);
    }
    else
    {
      Library = LoadLibraryExA(a2, 0, 8u);
      v11 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, "DllRegisterServer");
        if ( ProcAddress )
        {
          v8 = ProcAddress();
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
        }
        FreeLibrary(v11);
      }
      else
      {
        v12 = GetLastError();
        v8 = v12;
        if ( v12 > 0 )
          return (unsigned __int16)v12 | 0x80070000;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800c4750  mov     rax, rsp
0x1800c4753  push    rbx
0x1800c4754  push    rbp
0x1800c4755  push    rdi
0x1800c4756  push    r14
0x1800c4758  sub     rsp, 48h
0x1800c475c  mov     rbp, rcx
0x1800c475f  mov     qword ptr [rax+20h], 0
0x1800c4767  mov     rcx, rdx; char *
0x1800c476a  mov     r14d, r8d
0x1800c476d  mov     rdi, rdx
0x1800c4770  call    ?IsRegisterableDLL@@YAJPEBD@Z; IsRegisterableDLL(char const *)
0x1800c4775  mov     rcx, [rbp+1F0h]; this
0x1800c477c  mov     edx, 1; int
0x1800c4781  mov     [rsp+68h+phkResult], rdi
0x1800c4786  mov     r8d, edx; int
0x1800c4789  mov     ebx, eax
0x1800c478b  test    eax, eax
0x1800c478d  jz      short loc_1800C479F
0x1800c478f  mov     r9d, 2710h; unsigned int
0x1800c4795  call    ?DebugOut@CDLDebugLog@@QEAAXHHIZZ; CDLDebugLog::DebugOut(int,int,uint,...)
0x1800c479a  jmp     loc_1800C48E9
0x1800c479f  mov     r9d, 272Ah; unsigned int
0x1800c47a5  call    ?DebugOut@CDLDebugLog@@QEAAXHHIZZ; CDLDebugLog::DebugOut(int,int,uint,...)
0x1800c47aa  lea     rax, [rsp+68h+hKey]
0x1800c47af  mov     [rsp+68h+hKey], 0
0x1800c47b8  mov     r9d, 2000000h; samDesired
0x1800c47be  mov     [rsp+68h+phkResult], rax; phkResult
0x1800c47c3  xor     r8d, r8d; ulOptions
0x1800c47c6  lea     rdx, aClsidAaf8c6ceF; "CLSID\\{aaf8c6ce-f972-11d0-97eb-00aa006"...
0x1800c47cd  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800c47d4  call    cs:__imp_RegOpenKeyExA
0x1800c47da  test    eax, eax
0x1800c47dc  jz      short loc_1800C480F
0x1800c47de  mov     [rsp+68h+ppv], 0
0x1800c47ea  call    ?InstallBrokerIsNeeded@@YAHK@Z; InstallBrokerIsNeeded(ulong)
0x1800c47ef  test    eax, eax
0x1800c47f1  jz      loc_1800C487F
0x1800c47f7  xor     r9d, r9d; int
0x1800c47fa  mov     r8d, r14d; int
0x1800c47fd  mov     rdx, rdi; char *
0x1800c4800  mov     rcx, rbp; this
0x1800c4803  call    ?CallRegisterDllFileBroker@CCodeDownload@@QEAAJPEBDHH@Z; CCodeDownload::CallRegisterDllFileBroker(char const *,int,int)
0x1800c4808  mov     ebx, eax
0x1800c480a  jmp     loc_1800C48E9
0x1800c480f  mov     rcx, [rsp+68h+hKey]; hKey
0x1800c4814  call    cs:__imp_RegCloseKey
0x1800c481a  xor     edx, edx; pUnkOuter
0x1800c481c  lea     rax, [rsp+68h+ppv]
0x1800c4824  lea     r9, IID_IActiveXSafetyProvider; riid
0x1800c482b  mov     [rsp+68h+phkResult], rax; ppv
0x1800c4830  lea     rcx, CLSID_IActiveXSafetyProvider; rclsid
0x1800c4837  lea     r8d, [rdx+1]; dwClsContext
0x1800c483b  call    cs:__imp_CoCreateInstance
0x1800c4841  mov     ebx, eax
0x1800c4843  test    eax, eax
0x1800c4845  jnz     loc_1800C48E9
0x1800c484b  mov     rcx, [rsp+68h+ppv]
0x1800c4853  test    rcx, rcx
0x1800c4856  jz      short loc_1800C47EA
0x1800c4858  mov     rax, [rcx]
0x1800c485b  mov     rdx, rdi
0x1800c485e  mov     rax, [rax+48h]
0x1800c4862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4867  mov     rcx, [rsp+68h+ppv]
0x1800c486f  mov     ebx, eax
0x1800c4871  mov     rax, [rcx]
0x1800c4874  mov     rax, [rax+10h]
0x1800c4878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c487d  jmp     short loc_1800C48E9
0x1800c487f  xor     edx, edx; hFile
0x1800c4881  mov     rcx, rdi; lpLibFileName
0x1800c4884  lea     r8d, [rdx+8]; dwFlags
0x1800c4888  call    cs:__imp_LoadLibraryExA
0x1800c488e  mov     rdi, rax
0x1800c4891  test    rax, rax
0x1800c4894  jnz     short loc_1800C48AD
0x1800c4896  call    cs:__imp_GetLastError
0x1800c489c  mov     ebx, eax
0x1800c489e  test    eax, eax
0x1800c48a0  jle     short loc_1800C48E9
0x1800c48a2  movzx   ebx, ax
0x1800c48a5  or      ebx, 80070000h
0x1800c48ab  jmp     short loc_1800C48E9
0x1800c48ad  lea     rdx, aDllregisterser_1; "DllRegisterServer"
0x1800c48b4  mov     rcx, rdi; hModule
0x1800c48b7  call    cs:__imp_GetProcAddress
0x1800c48bd  test    rax, rax
0x1800c48c0  jnz     short loc_1800C48D9
0x1800c48c2  call    cs:__imp_GetLastError
0x1800c48c8  mov     ebx, eax
0x1800c48ca  test    eax, eax
0x1800c48cc  jle     short loc_1800C48E0
0x1800c48ce  movzx   ebx, ax
0x1800c48d1  or      ebx, 80070000h
0x1800c48d7  jmp     short loc_1800C48E0
0x1800c48d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c48de  mov     ebx, eax
0x1800c48e0  mov     rcx, rdi; hLibModule
0x1800c48e3  call    cs:__imp_FreeLibrary
0x1800c48e9  mov     eax, ebx
0x1800c48eb  add     rsp, 48h
0x1800c48ef  pop     r14
0x1800c48f1  pop     rdi
0x1800c48f2  pop     rbp
0x1800c48f3  pop     rbx
0x1800c48f4  retn
```
