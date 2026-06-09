# CActiveXInstallBroker::RunSetupCommand(ushort *,HWND__ *,ushort *,ushort *,ushort *,ushort *,ulong,void * *)

- ea: `0x403d84`
- end: `0x403ff7`
- name: `?RunSetupCommand@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@0000KPAPAX@Z`
- size: `627`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, CLock *@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, LPHANDLE lpTargetHandle, unsigned int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x405d60`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x403094`
- `0x403d84`
- `0x40777d`
- `0x408301`
- `0x40838e`
- `0x408480`
- `0x408a2f`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x403fc7`
- `KERNEL32!CloseHandle` at `0x403fd5`
- `KERNEL32!CloseHandle` at `0x403fc7`
- `KERNEL32!CloseHandle` at `0x403fd5`
- `KERNEL32!GetProcAddress` at `0x403edc`
- `KERNEL32!GetProcAddress` at `0x403edc`
- `KERNEL32!LoadLibraryExW` at `0x403eb0`
- `KERNEL32!LoadLibraryExW` at `0x403eb0`
- `KERNEL32!GetCurrentProcess` at `0x403f64`
- `KERNEL32!GetCurrentProcess` at `0x403f64`
- `KERNEL32!OpenProcess` at `0x403f50`
- `KERNEL32!OpenProcess` at `0x403f50`
- `KERNEL32!DuplicateHandle` at `0x403f7c`
- `KERNEL32!DuplicateHandle` at `0x403f7c`
- `KERNEL32!GetLastError` at `0x403ebd`
- `KERNEL32!GetLastError` at `0x403f86`
- `KERNEL32!GetLastError` at `0x403ebd`
- `KERNEL32!GetLastError` at `0x403f86`
- `ole32!CoTaskMemFree` at `0x403fb9`
- `ole32!CoTaskMemFree` at `0x403fb9`
- `ole32!CoImpersonateClient` at `0x403f36`
- `ole32!CoImpersonateClient` at `0x403f36`
- `ole32!CoRevertToSelf` at `0x403fe1`
- `ole32!CoRevertToSelf` at `0x403fe1`

## string_xrefs

- `0x403eab`: `IEAdvpack.Dll`
- `0x403ed6`: `RunSetupCommandW`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::RunSetupCommand@<eax>(
        const unsigned __int16 *a1@<edx>,
        CLock *a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        HWND a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        LPHANDLE lpTargetHandle,
        unsigned int a10,
        void **a11)
{
  unsigned __int16 *v11; // ebx
  CLock *v12; // esi
  int ExecutablePathFromCommandLine; // edi
  int v15; // eax
  int v16; // ecx
  HMODULE Library; // eax
  signed int v18; // eax
  HRESULT (__stdcall *RunSetupCommandW)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, HANDLE *, DWORD, LPVOID); // edi
  HANDLE v20; // esi
  HANDLE CurrentProcess; // eax
  signed int LastError; // eax
  const unsigned __int16 *v24; // [esp+0h] [ebp-20h]
  int v25; // [esp+Ch] [ebp-14h]
  int hTargetProcessHandle; // [esp+14h] [ebp-Ch]
  LPVOID pv; // [esp+18h] [ebp-8h] BYREF
  HANDLE hSourceHandle; // [esp+1Ch] [ebp-4h] BYREF

  v11 = 0;
  hTargetProcessHandle = -1;
  v12 = a2;
  pv = 0;
  hSourceHandle = 0;
  v25 = 0;
  if ( !CLock::Lock(a2) )
  {
    ExecutablePathFromCommandLine = -2147024882;
    goto LABEL_45;
  }
  if ( *((int *)v12 + 7) < 2 )
  {
    ExecutablePathFromCommandLine = -2147019873;
    goto LABEL_45;
  }
  if ( !a1 || !a4 || !a5 || !a6 || !a7 )
  {
LABEL_42:
    ExecutablePathFromCommandLine = -2147024809;
    goto LABEL_43;
  }
  v15 = wcscmp(a1, *((const unsigned __int16 **)v12 + 9));
  if ( v15 )
    v15 = v15 < 0 ? -1 : 1;
  if ( v15 )
  {
    ExecutablePathFromCommandLine = -2147024891;
    goto LABEL_45;
  }
  ExecutablePathFromCommandLine = GetExecutablePathFromCommandLine(a4, &pv);
  v11 = (unsigned __int16 *)pv;
  if ( ExecutablePathFromCommandLine >= 0 )
  {
    AxiAdjustSlashToBackslashW((__int16 *)pv);
    if ( AxiPreScanPathW(v11) >= 0 && VerifyFileHasExtensionW(v24) >= 0 )
    {
      ExecutablePathFromCommandLine = CActiveXInstallBroker::FileIsAuthorized(v12, v11, v16);
      if ( ExecutablePathFromCommandLine < 0 )
        goto LABEL_43;
      if ( !*((_DWORD *)v12 + 21) && !ContainingPathIsTamperProof(v11) )
      {
        ExecutablePathFromCommandLine = -2147024891;
        goto LABEL_43;
      }
      Library = (HMODULE)*((_DWORD *)v12 + 17);
      if ( Library || (Library = LoadLibraryExW(L"IEAdvpack.Dll", 0, 0x800u), (*((_DWORD *)v12 + 17) = Library) != 0) )
      {
        RunSetupCommandW = (HRESULT (__stdcall *)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, HANDLE *, DWORD, LPVOID))GetProcAddress(Library, "RunSetupCommandW");
        if ( RunSetupCommandW )
        {
          ExecutablePathFromCommandLine = ((int (__thiscall *)(HRESULT (__stdcall *)(HWND, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, HANDLE *, DWORD, LPVOID), CActiveXInstallBroker *, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, HANDLE *, unsigned __int16 *, _DWORD))RunSetupCommandW)(
                                            RunSetupCommandW,
                                            this,
                                            a4,
                                            a5,
                                            a6,
                                            a7,
                                            &hSourceHandle,
                                            a8,
                                            0);
          if ( ExecutablePathFromCommandLine < 0 )
            goto LABEL_43;
          if ( !lpTargetHandle )
            goto LABEL_41;
          if ( !hSourceHandle || hSourceHandle == (HANDLE)-1 )
          {
            *lpTargetHandle = (HANDLE)-1;
LABEL_41:
            *((_DWORD *)v12 + 7) = 6;
            goto LABEL_43;
          }
          if ( !g_fRunningAsSystem )
          {
            ExecutablePathFromCommandLine = CoImpersonateClient();
            if ( ExecutablePathFromCommandLine < 0 )
              goto LABEL_43;
            v25 = 1;
          }
          hTargetProcessHandle = (int)OpenProcess(0x40u, 0, *((_DWORD *)v12 + 18));
          if ( hTargetProcessHandle )
          {
            v20 = hSourceHandle;
            CurrentProcess = GetCurrentProcess();
            if ( !DuplicateHandle(CurrentProcess, v20, (HANDLE)hTargetProcessHandle, lpTargetHandle, 0x20000100u, 0, 0) )
            {
              LastError = GetLastError();
              v12 = a2;
              ExecutablePathFromCommandLine = (unsigned __int16)LastError | 0x80070000;
              if ( LastError <= 0 )
                ExecutablePathFromCommandLine = LastError;
              goto LABEL_43;
            }
            v12 = a2;
            goto LABEL_41;
          }
        }
      }
      v18 = GetLastError();
      ExecutablePathFromCommandLine = (unsigned __int16)v18 | 0x80070000;
      if ( v18 <= 0 )
        ExecutablePathFromCommandLine = v18;
      goto LABEL_43;
    }
    goto LABEL_42;
  }
LABEL_43:
  if ( v11 )
    CoTaskMemFree(v11);
LABEL_45:
  if ( hSourceHandle )
    CloseHandle(hSourceHandle);
  if ( hTargetProcessHandle )
    CloseHandle((HANDLE)hTargetProcessHandle);
  if ( v25 )
    CoRevertToSelf();
  CLock::Unlock(v12);
  return ExecutablePathFromCommandLine;
}

```

## disassembly

```asm
0x403d84  mov     edi, edi
0x403d86  push    ebp
0x403d87  mov     ebp, esp
0x403d89  sub     esp, 14h
0x403d8c  push    ebx
0x403d8d  push    esi; unsigned __int16 **
0x403d8e  xor     ebx, ebx
0x403d90  mov     [ebp+hTargetProcessHandle], 0FFFFFFFFh
0x403d97  mov     esi, ecx
0x403d99  mov     [ebp+pv], ebx
0x403d9c  push    edi; unsigned __int16 *
0x403d9d  mov     edi, edx
0x403d9f  mov     [ebp+var_10], esi
0x403da2  mov     [ebp+hSourceHandle], ebx
0x403da5  mov     [ebp+var_14], ebx
0x403da8  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x403dad  test    eax, eax
0x403daf  jnz     short loc_403DBB
0x403db1  mov     edi, 8007000Eh
0x403db6  jmp     loc_403FBF
0x403dbb  cmp     dword ptr [esi+1Ch], 2
0x403dbf  jge     short loc_403DCB
0x403dc1  mov     edi, 8007139Fh
0x403dc6  jmp     loc_403FBF
0x403dcb  test    edi, edi
0x403dcd  jz      loc_403FAF
0x403dd3  cmp     [ebp+arg_4], ebx
0x403dd6  jz      loc_403FAF
0x403ddc  cmp     [ebp+arg_8], ebx
0x403ddf  jz      loc_403FAF
0x403de5  cmp     [ebp+arg_C], ebx
0x403de8  jz      loc_403FAF
0x403dee  cmp     [ebp+arg_10], ebx
0x403df1  jz      loc_403FAF
0x403df7  mov     eax, [esi+24h]
0x403dfa  mov     cx, [edi]
0x403dfd  cmp     cx, [eax]
0x403e00  jnz     short loc_403E20
0x403e02  test    cx, cx
0x403e05  jz      short loc_403E1C
0x403e07  mov     cx, [edi+2]
0x403e0b  cmp     cx, [eax+2]
0x403e0f  jnz     short loc_403E20
0x403e11  add     edi, 4
0x403e14  add     eax, 4
0x403e17  test    cx, cx
0x403e1a  jnz     short loc_403DFA
0x403e1c  xor     eax, eax
0x403e1e  jmp     short loc_403E25
0x403e20  sbb     eax, eax
0x403e22  or      eax, 1
0x403e25  test    eax, eax
0x403e27  jz      short loc_403E33
0x403e29  mov     edi, 80070005h
0x403e2e  jmp     loc_403FBF
0x403e33  mov     ecx, [ebp+arg_4]
0x403e36  lea     edx, [ebp+pv]
0x403e39  call    ?GetExecutablePathFromCommandLine@@YGJPBGPAPAG@Z; GetExecutablePathFromCommandLine(ushort const *,ushort * *)
0x403e3e  mov     edi, eax
0x403e40  mov     ebx, [ebp+pv]
0x403e43  test    edi, edi
0x403e45  js      loc_403FB4
0x403e4b  mov     ecx, ebx
0x403e4d  call    ?AxiAdjustSlashToBackslashW@@YGXPAG@Z; AxiAdjustSlashToBackslashW(ushort *)
0x403e52  mov     ecx, ebx
0x403e54  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x403e59  test    eax, eax
0x403e5b  js      loc_403FAF
0x403e61  mov     ecx, ebx
0x403e63  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x403e68  test    eax, eax
0x403e6a  js      loc_403FAF
0x403e70  push    ecx; int
0x403e71  push    ebx; unsigned __int16 *
0x403e72  mov     ecx, esi; this
0x403e74  call    ?FileIsAuthorized@CActiveXInstallBroker@@AAEJPBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x403e79  mov     edi, eax
0x403e7b  test    edi, edi
0x403e7d  js      loc_403FB4
0x403e83  cmp     dword ptr [esi+54h], 0
0x403e87  jnz     short loc_403E9E
0x403e89  mov     ecx, ebx
0x403e8b  call    ?ContainingPathIsTamperProof@@YGHPBG@Z; ContainingPathIsTamperProof(ushort const *)
0x403e90  test    eax, eax
0x403e92  jnz     short loc_403E9E
0x403e94  mov     edi, 80070005h
0x403e99  jmp     loc_403FB4
0x403e9e  mov     eax, [esi+44h]
0x403ea1  test    eax, eax
0x403ea3  jnz     short loc_403ED6
0x403ea5  push    800h; dwFlags
0x403eaa  push    eax; hFile
0x403eab  push    offset LibFileName; "IEAdvpack.Dll"
0x403eb0  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x403eb6  mov     [esi+44h], eax
0x403eb9  test    eax, eax
0x403ebb  jnz     short loc_403ED6
0x403ebd  call    ds:__imp__GetLastError@0; GetLastError()
0x403ec3  movzx   edi, ax
0x403ec6  or      edi, 80070000h
0x403ecc  test    eax, eax
0x403ece  cmovle  edi, eax
0x403ed1  jmp     loc_403FB4
0x403ed6  push    offset ProcName; "RunSetupCommandW"
0x403edb  push    eax; hModule
0x403edc  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x403ee2  mov     edi, eax
0x403ee4  test    edi, edi
0x403ee6  jz      short loc_403EBD
0x403ee8  push    0
0x403eea  push    [ebp+arg_14]
0x403eed  lea     eax, [ebp+hSourceHandle]
0x403ef0  mov     ecx, edi
0x403ef2  push    eax
0x403ef3  push    [ebp+arg_10]
0x403ef6  push    [ebp+arg_C]
0x403ef9  push    [ebp+arg_8]
0x403efc  push    [ebp+arg_4]
0x403eff  push    [ebp+this]
0x403f02  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x403f08  call    edi
0x403f0a  mov     edi, eax
0x403f0c  test    edi, edi
0x403f0e  js      loc_403FB4
0x403f14  mov     edx, [ebp+lpTargetHandle]
0x403f17  test    edx, edx
0x403f19  jz      loc_403FA6
0x403f1f  mov     eax, [ebp+hSourceHandle]
0x403f22  or      ecx, 0FFFFFFFFh
0x403f25  test    eax, eax
0x403f27  jz      short loc_403F9F
0x403f29  cmp     eax, ecx
0x403f2b  jz      short loc_403F9F
0x403f2d  cmp     ?g_fRunningAsSystem@@3HA, 0; int g_fRunningAsSystem
0x403f34  jnz     short loc_403F49
0x403f36  call    ds:__imp__CoImpersonateClient@0; CoImpersonateClient()
0x403f3c  mov     edi, eax
0x403f3e  test    edi, edi
0x403f40  js      short loc_403FB4
0x403f42  mov     [ebp+var_14], 1
0x403f49  push    dword ptr [esi+48h]; dwProcessId
0x403f4c  push    0; bInheritHandle
0x403f4e  push    40h ; '@'; dwDesiredAccess
0x403f50  call    ds:__imp__OpenProcess@12; OpenProcess(x,x,x)
0x403f56  mov     [ebp+hTargetProcessHandle], eax
0x403f59  test    eax, eax
0x403f5b  jz      loc_403EBD
0x403f61  mov     esi, [ebp+hSourceHandle]
0x403f64  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x403f6a  mov     ecx, [ebp+hTargetProcessHandle]
0x403f6d  push    0; dwOptions
0x403f6f  push    0; bInheritHandle
0x403f71  push    20000100h; dwDesiredAccess
0x403f76  push    [ebp+lpTargetHandle]; lpTargetHandle
0x403f79  push    ecx; hTargetProcessHandle
0x403f7a  push    esi; hSourceHandle
0x403f7b  push    eax; hSourceProcessHandle
0x403f7c  call    ds:__imp__DuplicateHandle@28; DuplicateHandle(x,x,x,x,x,x,x)
0x403f82  test    eax, eax
0x403f84  jnz     short loc_403FA3
0x403f86  call    ds:__imp__GetLastError@0; GetLastError()
0x403f8c  mov     esi, [ebp+var_10]
0x403f8f  movzx   edi, ax
0x403f92  or      edi, 80070000h
0x403f98  test    eax, eax
0x403f9a  cmovle  edi, eax
0x403f9d  jmp     short loc_403FB4
0x403f9f  mov     [edx], ecx
0x403fa1  jmp     short loc_403FA6
0x403fa3  mov     esi, [ebp+var_10]
0x403fa6  mov     dword ptr [esi+1Ch], 6
0x403fad  jmp     short loc_403FB4
0x403faf  mov     edi, 80070057h
0x403fb4  test    ebx, ebx
0x403fb6  jz      short loc_403FBF
0x403fb8  push    ebx; pv
0x403fb9  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x403fbf  mov     eax, [ebp+hSourceHandle]
0x403fc2  test    eax, eax
0x403fc4  jz      short loc_403FCD
0x403fc6  push    eax; hObject
0x403fc7  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x403fcd  mov     eax, [ebp+hTargetProcessHandle]
0x403fd0  test    eax, eax
0x403fd2  jz      short loc_403FDB
0x403fd4  push    eax; hObject
0x403fd5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x403fdb  cmp     [ebp+var_14], 0
0x403fdf  jz      short loc_403FE7
0x403fe1  call    ds:__imp__CoRevertToSelf@0; CoRevertToSelf()
0x403fe7  mov     ecx, esi; this
0x403fe9  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x403fee  mov     eax, edi
0x403ff0  pop     edi
0x403ff1  pop     esi
0x403ff2  pop     ebx
0x403ff3  leave
0x403ff4  retn    1Ch
```
