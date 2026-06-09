# _IsOsComponent(ushort const *)

- ea: `0x18011e18c`
- end: `0x18011e549`
- name: `?_IsOsComponent@@YAHPEBG@Z`
- size: `957`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18011ad10`
- `0x18011cd40`

## callees

- `0x180008570`
- `0x1800089fc`
- `0x18000a79c`
- `0x18000a804`
- `0x18008fadc`
- `0x18011e18c`
- `0x18021f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011e30b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011e372`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011e30b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011e372`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x18011e2e7`
- `KERNEL32!GetVolumeInformationByHandleW` at `0x18011e2e7`
- `KERNEL32!CreateFileW` at `0x18011e2a6`
- `KERNEL32!CreateFileW` at `0x18011e2a6`
- `KERNEL32!LoadLibraryExW` at `0x18011e1fd`
- `KERNEL32!LoadLibraryExW` at `0x18011e3ba`
- `KERNEL32!LoadLibraryExW` at `0x18011e1fd`
- `KERNEL32!LoadLibraryExW` at `0x18011e3ba`
- `KERNEL32!GetProcAddress` at `0x18011e24b`
- `KERNEL32!GetProcAddress` at `0x18011e331`
- `KERNEL32!GetProcAddress` at `0x18011e408`
- `KERNEL32!GetProcAddress` at `0x18011e24b`
- `KERNEL32!GetProcAddress` at `0x18011e331`
- `KERNEL32!GetProcAddress` at `0x18011e408`
- `KERNEL32!CloseHandle` at `0x18011e381`
- `KERNEL32!CloseHandle` at `0x18011e381`
- `KERNEL32!GetLastError` at `0x18011e48f`
- `KERNEL32!GetLastError` at `0x18011e515`
- `KERNEL32!GetLastError` at `0x18011e52f`
- `KERNEL32!GetLastError` at `0x18011e48f`
- `KERNEL32!GetLastError` at `0x18011e515`
- `KERNEL32!GetLastError` at `0x18011e52f`

## string_xrefs

- `0x18011e1f0`: `ntdll.dll`
- `0x18011e3ad`: `sfc.dll`

## pseudocode

```c
__int64 __fastcall _IsOsComponent(LPCWSTR lpFileName)
{
  __int64 v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rcx
  HMODULE v5; // rbx
  unsigned __int8 (*ProcAddress)(void); // rax
  unsigned int v7; // ebx
  HANDLE FileW; // rdi
  FARPROC v9; // rax
  FARPROC v10; // rax
  HMODULE v11; // rax
  HMODULE v12; // rcx
  __int64 v13; // rdi
  signed int v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  signed int LastError; // eax
  int v19; // edx
  unsigned int v20; // r8d
  signed int v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  DWORD FileSystemFlags; // [rsp+40h] [rbp-258h] BYREF
  DWORD MaximumComponentLength[3]; // [rsp+44h] [rbp-254h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+50h] [rbp-248h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1802D5AE0 > *(_DWORD *)(v2 + 8) )
  {
    Init_thread_header(&dword_1802D5AE0);
    if ( dword_1802D5AE0 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__SfcModule__);
      Init_thread_footer(&dword_1802D5AE0);
    }
  }
  if ( dword_1802D5AE4 > *(_DWORD *)(v2 + 8) )
  {
    Init_thread_header(&dword_1802D5AE4);
    if ( dword_1802D5AE4 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__NtdllModule__);
      Init_thread_footer(&dword_1802D5AE4);
    }
  }
  if ( hModule )
    goto LABEL_10;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v4 = hModule;
  v5 = Library;
  if ( Library != hModule )
  {
    if ( hModule && !((unsigned __int8 (__fastcall *)(void ***))*off_1802C9790)(&off_1802C9790) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v19, v20);
      __debugbreak();
    }
    v4 = v5;
    hModule = v5;
  }
  if ( !v4 )
  {
LABEL_10:
    ProcAddress = (unsigned __int8 (*)(void))qword_1802D55D0;
  }
  else
  {
    ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(v4, "RtlIsStateSeparationEnabled");
    qword_1802D55D0 = (__int64)ProcAddress;
  }
  v7 = 0;
  if ( !ProcAddress )
    goto LABEL_26;
  if ( !ProcAddress() )
    goto LABEL_26;
  MaximumComponentLength[0] = 0;
  FileSystemFlags = 0;
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_26;
  if ( GetVolumeInformationByHandleW(FileW, VolumeNameBuffer, 0x105u, 0, MaximumComponentLength, &FileSystemFlags, 0, 0) )
  {
    if ( (FileSystemFlags & 0x80000) == 0 || (unsigned int)_o__wcsicmp(VolumeNameBuffer, L"MAINOS") )
    {
      if ( !qword_1802D55D8 )
      {
        v9 = GetProcAddress(hModule, "RtlGetDeviceFamilyInfoEnum");
        qword_1802D55D8 = (__int64)v9;
        if ( v9 )
          ((void (__fastcall *)(_QWORD, int *, _QWORD))v9)(0, &dword_1802D55E0, 0);
        else
          qword_1802D55D8 = 1;
      }
      if ( dword_1802D55E0 == 5 && !(unsigned int)_o__wcsicmp(VolumeNameBuffer, L"System Boot") )
        v7 = 1;
    }
    else
    {
      v7 = 1;
    }
  }
  CloseHandle(FileW);
  if ( !v7 )
  {
LABEL_26:
    v10 = (FARPROC)qword_1802D55C0;
    if ( qword_1802D55C0 )
      return ((unsigned int (__fastcall *)(_QWORD, LPCWSTR))v10)(0, lpFileName);
    if ( byte_1802D55C8 )
    {
      v12 = (HMODULE)qword_1802C9788;
    }
    else
    {
      v11 = LoadLibraryExW(L"sfc.dll", 0, 0x800u);
      v12 = (HMODULE)qword_1802C9788;
      v13 = (__int64)v11;
      if ( v11 != (HMODULE)qword_1802C9788 )
      {
        if ( qword_1802C9788 && !((unsigned __int8 (__fastcall *)(void ***))*off_1802C9780)(&off_1802C9780) )
        {
          v21 = GetLastError();
          if ( v21 > 0 )
            v21 = (unsigned __int16)v21 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
          JUMPOUT(0x18011E548LL);
        }
        v12 = (HMODULE)v13;
        qword_1802C9788 = v13;
      }
      if ( v12 )
      {
        v10 = GetProcAddress(v12, "SfcIsFileProtected");
        v12 = (HMODULE)qword_1802C9788;
        qword_1802D55C0 = (__int64)v10;
      }
      else
      {
        v10 = (FARPROC)qword_1802D55C0;
      }
      if ( v10 )
        return ((unsigned int (__fastcall *)(_QWORD, LPCWSTR))v10)(0, lpFileName);
    }
    byte_1802D55C8 = 1;
    if ( v12 )
    {
      if ( !((unsigned __int8 (__fastcall *)(void ***))*off_1802C9780)(&off_1802C9780) )
      {
        v15 = GetLastError();
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
        __debugbreak();
      }
      qword_1802C9788 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18011e18c  push    rbx
0x18011e18e  push    rsi
0x18011e18f  push    rdi
0x18011e190  push    r14
0x18011e192  sub     rsp, 278h
0x18011e199  mov     rax, cs:__security_cookie
0x18011e1a0  xor     rax, rsp
0x18011e1a3  mov     [rsp+298h+var_38], rax
0x18011e1ab  mov     rax, gs:58h
0x18011e1b4  mov     rsi, rcx
0x18011e1b7  mov     ecx, cs:_tls_index
0x18011e1bd  mov     edi, 8
0x18011e1c2  mov     rbx, [rax+rcx*8]
0x18011e1c6  mov     eax, [rbx+rdi]
0x18011e1c9  cmp     cs:dword_1802D5AE0, eax
0x18011e1cf  jg      loc_18011E4A9
0x18011e1d5  mov     eax, [rbx+rdi]
0x18011e1d8  cmp     cs:dword_1802D5AE4, eax
0x18011e1de  jg      loc_18011E4DF
0x18011e1e4  cmp     cs:hModule, 0
0x18011e1ec  jnz     short loc_18011E25A
0x18011e1ee  xor     edx, edx; hFile
0x18011e1f0  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x18011e1f7  mov     r8d, 800h; dwFlags
0x18011e1fd  call    cs:__imp_LoadLibraryExW
0x18011e203  mov     rcx, cs:hModule
0x18011e20a  mov     rbx, rax
0x18011e20d  cmp     rax, rcx
0x18011e210  jz      short loc_18011E23F
0x18011e212  test    rcx, rcx
0x18011e215  jz      short loc_18011E235
0x18011e217  mov     rcx, cs:off_1802C9790
0x18011e21e  mov     rax, [rcx]
0x18011e221  lea     rcx, off_1802C9790
0x18011e228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e22d  test    al, al
0x18011e22f  jz      loc_18011E515
0x18011e235  mov     rcx, rbx; hModule
0x18011e238  mov     cs:hModule, rbx
0x18011e23f  test    rcx, rcx
0x18011e242  jz      short loc_18011E25A
0x18011e244  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18011e24b  call    cs:__imp_GetProcAddress
0x18011e251  mov     cs:qword_1802D55D0, rax
0x18011e258  jmp     short loc_18011E261
0x18011e25a  mov     rax, cs:qword_1802D55D0
0x18011e261  xor     ebx, ebx
0x18011e263  lea     r14d, [rbx+1]
0x18011e267  test    rax, rax
0x18011e26a  jz      loc_18011E38F
0x18011e270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e275  test    al, al
0x18011e277  jz      loc_18011E38F
0x18011e27d  mov     [rsp+298h+hTemplateFile], rbx; hTemplateFile
0x18011e282  lea     r8d, [rbx+7]; dwShareMode
0x18011e286  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18011e28e  xor     r9d, r9d; lpSecurityAttributes
0x18011e291  xor     edx, edx; dwDesiredAccess
0x18011e293  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x18011e29b  mov     rcx, rsi; lpFileName
0x18011e29e  mov     [rsp+298h+MaximumComponentLength], ebx
0x18011e2a2  mov     [rsp+298h+FileSystemFlags], ebx
0x18011e2a6  call    cs:__imp_CreateFileW
0x18011e2ac  mov     rdi, rax
0x18011e2af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011e2b3  jz      loc_18011E38F
0x18011e2b9  mov     [rsp+298h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x18011e2bd  lea     rax, [rsp+298h+FileSystemFlags]
0x18011e2c2  mov     [rsp+298h+hTemplateFile], rbx; lpFileSystemNameBuffer
0x18011e2c7  lea     rdx, [rsp+298h+VolumeNameBuffer]; lpVolumeNameBuffer
0x18011e2cc  mov     qword ptr [rsp+298h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x18011e2d1  xor     r9d, r9d; lpVolumeSerialNumber
0x18011e2d4  lea     rax, [rsp+298h+MaximumComponentLength]
0x18011e2d9  mov     r8d, 105h; nVolumeNameSize
0x18011e2df  mov     rcx, rdi; hFile
0x18011e2e2  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; lpMaximumComponentLength
0x18011e2e7  call    cs:__imp_GetVolumeInformationByHandleW
0x18011e2ed  test    eax, eax
0x18011e2ef  jz      loc_18011E37E
0x18011e2f5  test    [rsp+298h+FileSystemFlags], 80000h
0x18011e2fd  jz      short loc_18011E31A
0x18011e2ff  lea     rdx, aMainos; "MAINOS"
0x18011e306  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x18011e30b  call    cs:__imp__o__wcsicmp
0x18011e311  test    eax, eax
0x18011e313  jnz     short loc_18011E31A
0x18011e315  mov     ebx, r14d
0x18011e318  jmp     short loc_18011E37E
0x18011e31a  cmp     cs:qword_1802D55D8, rbx
0x18011e321  jnz     short loc_18011E35D
0x18011e323  mov     rcx, cs:hModule; hModule
0x18011e32a  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18011e331  call    cs:__imp_GetProcAddress
0x18011e337  mov     cs:qword_1802D55D8, rax
0x18011e33e  test    rax, rax
0x18011e341  jz      short loc_18011E356
0x18011e343  xor     r8d, r8d
0x18011e346  lea     rdx, dword_1802D55E0
0x18011e34d  xor     ecx, ecx
0x18011e34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e354  jmp     short loc_18011E35D
0x18011e356  mov     cs:qword_1802D55D8, r14
0x18011e35d  cmp     cs:dword_1802D55E0, 5
0x18011e364  jnz     short loc_18011E37E
0x18011e366  lea     rdx, aSystemBoot; "System Boot"
0x18011e36d  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x18011e372  call    cs:__imp__o__wcsicmp
0x18011e378  test    eax, eax
0x18011e37a  cmovz   ebx, r14d
0x18011e37e  mov     rcx, rdi; hObject
0x18011e381  call    cs:__imp_CloseHandle
0x18011e387  test    ebx, ebx
0x18011e389  jnz     loc_18011E436
0x18011e38f  mov     rax, cs:qword_1802D55C0
0x18011e396  test    rax, rax
0x18011e399  jnz     loc_18011E42A
0x18011e39f  cmp     cs:byte_1802D55C8, al
0x18011e3a5  jnz     loc_18011E455
0x18011e3ab  xor     edx, edx; hFile
0x18011e3ad  lea     rcx, aSfcDll; "sfc.dll"
0x18011e3b4  mov     r8d, 800h; dwFlags
0x18011e3ba  call    cs:__imp_LoadLibraryExW
0x18011e3c0  mov     rcx, cs:qword_1802C9788
0x18011e3c7  mov     rdi, rax
0x18011e3ca  cmp     rax, rcx
0x18011e3cd  jz      short loc_18011E3FC
0x18011e3cf  test    rcx, rcx
0x18011e3d2  jz      short loc_18011E3F2
0x18011e3d4  mov     rcx, cs:off_1802C9780
0x18011e3db  mov     rax, [rcx]
0x18011e3de  lea     rcx, off_1802C9780
0x18011e3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e3ea  test    al, al
0x18011e3ec  jz      loc_18011E52F
0x18011e3f2  mov     rcx, rdi; hModule
0x18011e3f5  mov     cs:qword_1802C9788, rcx
0x18011e3fc  test    rcx, rcx
0x18011e3ff  jz      short loc_18011E41E
0x18011e401  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x18011e408  call    cs:__imp_GetProcAddress
0x18011e40e  mov     rcx, cs:qword_1802C9788
0x18011e415  mov     cs:qword_1802D55C0, rax
0x18011e41c  jmp     short loc_18011E425
0x18011e41e  mov     rax, cs:qword_1802D55C0
0x18011e425  test    rax, rax
0x18011e428  jz      short loc_18011E45C
0x18011e42a  mov     rdx, rsi
0x18011e42d  xor     ecx, ecx
0x18011e42f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e434  mov     ebx, eax
0x18011e436  mov     eax, ebx
0x18011e438  mov     rcx, [rsp+298h+var_38]
0x18011e440  xor     rcx, rsp; StackCookie
0x18011e443  call    __security_check_cookie
0x18011e448  add     rsp, 278h
0x18011e44f  pop     r14
0x18011e451  pop     rdi
0x18011e452  pop     rsi
0x18011e453  pop     rbx
0x18011e454  retn
0x18011e455  mov     rcx, cs:qword_1802C9788
0x18011e45c  mov     cs:byte_1802D55C8, r14b
0x18011e463  test    rcx, rcx
0x18011e466  jz      short loc_18011E436
0x18011e468  mov     rax, cs:off_1802C9780
0x18011e46f  lea     rcx, off_1802C9780
0x18011e476  mov     rax, [rax]
0x18011e479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011e47e  test    al, al
0x18011e480  jz      short loc_18011E48F
0x18011e482  mov     cs:qword_1802C9788, 0
0x18011e48d  jmp     short loc_18011E436
0x18011e48f  call    cs:__imp_GetLastError
0x18011e495  test    eax, eax
0x18011e497  jle     short loc_18011E4A1
0x18011e499  movzx   eax, ax
0x18011e49c  or      eax, 80070000h
0x18011e4a1  mov     ecx, eax; this
0x18011e4a3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18011e4a8  int     3; Trap to Debugger
0x18011e4a9  lea     rcx, dword_1802D5AE0
0x18011e4b0  call    _Init_thread_header
0x18011e4b5  cmp     cs:dword_1802D5AE0, 0FFFFFFFFh
0x18011e4bc  jnz     loc_18011E1D5
0x18011e4c2  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__SfcModule__; void (__cdecl *)()
0x18011e4c9  call    atexit
0x18011e4ce  lea     rcx, dword_1802D5AE0
0x18011e4d5  call    _Init_thread_footer
0x18011e4da  jmp     loc_18011E1D5
0x18011e4df  lea     rcx, dword_1802D5AE4
0x18011e4e6  call    _Init_thread_header
0x18011e4eb  cmp     cs:dword_1802D5AE4, 0FFFFFFFFh
0x18011e4f2  jnz     loc_18011E1E4
0x18011e4f8  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__NtdllModule__; void (__cdecl *)()
0x18011e4ff  call    atexit
0x18011e504  lea     rcx, dword_1802D5AE4
0x18011e50b  call    _Init_thread_footer
0x18011e510  jmp     loc_18011E1E4
0x18011e515  call    cs:__imp_GetLastError
0x18011e51b  test    eax, eax
0x18011e51d  jle     short loc_18011E527
0x18011e51f  movzx   eax, ax
0x18011e522  or      eax, 80070000h
0x18011e527  mov     ecx, eax; this
0x18011e529  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18011e52e  int     3; Trap to Debugger
0x18011e52f  call    cs:__imp_GetLastError
0x18011e535  test    eax, eax
0x18011e537  jle     short loc_18011E541
0x18011e539  movzx   eax, ax
0x18011e53c  or      eax, 80070000h
0x18011e541  mov     ecx, eax; this
0x18011e543  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
