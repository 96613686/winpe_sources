# _IsOsComponent(ushort const *)

- ea: `0x1800e591c`
- end: `0x1800e5cd1`
- name: `?_IsOsComponent@@YAHPEBG@Z`
- size: `949`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800e2500`
- `0x1800e4540`

## callees

- `0x180004ea0`
- `0x18000527c`
- `0x180005b90`
- `0x180005bc0`
- `0x180005be0`
- `0x180006eac`
- `0x180006f14`
- `0x18000723c`
- `0x18003dbf0`
- `0x1800e591c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5a99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5aff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5a99`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e5aff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e598d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e5b46`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e598d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e5b46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e5a35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e5a35`

## string_xrefs

- `0x1800e5986`: `ntdll.dll`
- `0x1800e5b3f`: `sfc.dll`

## pseudocode

```c
__int64 __fastcall _IsOsComponent(LPCWSTR lpFileName)
{
  __int64 FileW; // rdi
  __int64 v3; // rbx
  HMODULE Library; // rbx
  HMODULE v5; // rcx
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  FARPROC RtlGetDeviceFamilyInfoEnum; // rax
  BOOL (__stdcall *SfcIsFileProtected)(HANDLE, LPCWSTR); // rax
  HMODULE v9; // rcx
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int LastError_0; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  DWORD FileSystemFlags; // [rsp+40h] [rbp-258h] BYREF
  DWORD MaximumComponentLength[3]; // [rsp+44h] [rbp-254h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+50h] [rbp-248h] BYREF

  FileW = 4;
  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_18011C1A0 > *(_DWORD *)(v3 + 4) )
    goto LABEL_46;
  while ( 1 )
  {
    if ( dword_18011C1A4 > *(_DWORD *)(v3 + FileW) )
    {
      Init_thread_header(&dword_18011C1A4);
      if ( dword_18011C1A4 == -1 )
      {
        atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__NtdllModule__);
        Init_thread_footer(&dword_18011C1A4);
      }
    }
    if ( hModule )
      goto LABEL_10;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v5 = hModule;
    if ( Library != hModule )
    {
      if ( hModule && !((unsigned __int8 (__fastcall *)(void ***))*off_180119DA0)(&off_180119DA0) )
      {
        LastError_0 = GetLastError_0();
        if ( LastError_0 > 0 )
          LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError_0, v15, v16);
LABEL_53:
        v17 = GetLastError_0();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
        JUMPOUT(0x1800E5CD0LL);
      }
      v5 = Library;
      hModule = Library;
    }
    if ( !v5 )
    {
LABEL_10:
      RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))qword_18011C0D0;
    }
    else
    {
      RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(v5, "RtlIsStateSeparationEnabled");
      qword_18011C0D0 = (__int64)RtlIsStateSeparationEnabled;
    }
    v3 = 0;
    if ( RtlIsStateSeparationEnabled )
    {
      if ( RtlIsStateSeparationEnabled() )
      {
        MaximumComponentLength[0] = 0;
        FileSystemFlags = 0;
        FileW = (__int64)CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x80u, 0);
        if ( FileW != -1 )
        {
          if ( GetVolumeInformationByHandleW_0(
                 (HANDLE)FileW,
                 VolumeNameBuffer,
                 0x105u,
                 0,
                 MaximumComponentLength,
                 &FileSystemFlags,
                 0,
                 0) )
          {
            if ( (FileSystemFlags & 0x80000) == 0 || (unsigned int)_o__wcsicmp(VolumeNameBuffer, L"MAINOS") )
            {
              if ( !qword_18011C0E0 )
              {
                RtlGetDeviceFamilyInfoEnum = GetProcAddress_0(hModule, "RtlGetDeviceFamilyInfoEnum");
                qword_18011C0E0 = (__int64)RtlGetDeviceFamilyInfoEnum;
                if ( RtlGetDeviceFamilyInfoEnum )
                  ((void (__fastcall *)(_QWORD, int *, _QWORD))RtlGetDeviceFamilyInfoEnum)(0, &dword_18011C0E8, 0);
                else
                  qword_18011C0E0 = 1;
              }
              if ( dword_18011C0E8 == 5 && !(unsigned int)_o__wcsicmp(VolumeNameBuffer, L"System Boot") )
                v3 = 1;
            }
            else
            {
              v3 = 1;
            }
          }
          CloseHandle_0((HANDLE)FileW);
          if ( (_DWORD)v3 )
            return (unsigned int)v3;
        }
      }
    }
    SfcIsFileProtected = (BOOL (__stdcall *)(HANDLE, LPCWSTR))qword_18011C0D8;
    if ( qword_18011C0D8 )
      goto LABEL_36;
    if ( byte_18011C0C8 )
    {
      v9 = (HMODULE)qword_180119DB8;
    }
    else
    {
      FileW = (__int64)LoadLibraryExW(L"sfc.dll", 0, 0x800u);
      v9 = (HMODULE)qword_180119DB8;
      if ( FileW != qword_180119DB8 )
      {
        if ( qword_180119DB8 && !((unsigned __int8 (__fastcall *)(void ***))*off_180119DB0)(&off_180119DB0) )
          goto LABEL_53;
        v9 = (HMODULE)FileW;
        qword_180119DB8 = FileW;
      }
      if ( v9 )
      {
        SfcIsFileProtected = (BOOL (__stdcall *)(HANDLE, LPCWSTR))GetProcAddress_0(v9, "SfcIsFileProtected");
        qword_18011C0D8 = (__int64)SfcIsFileProtected;
        v9 = (HMODULE)qword_180119DB8;
      }
      else
      {
        SfcIsFileProtected = (BOOL (__stdcall *)(HANDLE, LPCWSTR))qword_18011C0D8;
      }
      if ( SfcIsFileProtected )
      {
LABEL_36:
        LODWORD(v3) = ((__int64 (__fastcall *)(_QWORD, LPCWSTR))SfcIsFileProtected)(0, lpFileName);
        return (unsigned int)v3;
      }
    }
    byte_18011C0C8 = 1;
    if ( !v9 )
      return (unsigned int)v3;
    if ( ((unsigned __int8 (__fastcall *)(void ***))*off_180119DB0)(&off_180119DB0) )
    {
      qword_180119DB8 = 0;
      return (unsigned int)v3;
    }
    v11 = GetLastError_0();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
LABEL_46:
    Init_thread_header(&dword_18011C1A0);
    if ( dword_18011C1A0 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__SfcModule__);
      Init_thread_footer(&dword_18011C1A0);
    }
  }
}

```

## disassembly

```asm
0x1800e591c  push    rbx
0x1800e591e  push    rsi
0x1800e591f  push    rdi
0x1800e5920  push    r14
0x1800e5922  sub     rsp, 278h
0x1800e5929  mov     rax, cs:__security_cookie
0x1800e5930  xor     rax, rsp
0x1800e5933  mov     [rsp+298h+var_38], rax
0x1800e593b  mov     rsi, rcx
0x1800e593e  mov     ecx, cs:_tls_index
0x1800e5944  mov     rax, gs:58h
0x1800e594d  mov     edi, 4
0x1800e5952  mov     rbx, [rax+rcx*8]
0x1800e5956  mov     eax, [rbx+rdi]
0x1800e5959  cmp     cs:dword_18011C1A0, eax
0x1800e595f  jg      loc_1800E5C33
0x1800e5965  mov     eax, [rbx+rdi]
0x1800e5968  cmp     cs:dword_18011C1A4, eax
0x1800e596e  jg      loc_1800E5C69
0x1800e5974  cmp     cs:hModule, 0
0x1800e597c  jnz     short loc_1800E59E9
0x1800e597e  xor     edx, edx; hFile
0x1800e5980  mov     r8d, 800h; dwFlags
0x1800e5986  lea     rcx, LibFileName; "ntdll.dll"
0x1800e598d  call    cs:__imp_LoadLibraryExW
0x1800e5993  mov     rbx, rax
0x1800e5996  mov     rcx, cs:hModule
0x1800e599d  cmp     rax, rcx
0x1800e59a0  jz      short loc_1800E59CF
0x1800e59a2  test    rcx, rcx
0x1800e59a5  jz      short loc_1800E59C5
0x1800e59a7  mov     rcx, cs:off_180119DA0
0x1800e59ae  mov     rax, [rcx]
0x1800e59b1  lea     rcx, off_180119DA0
0x1800e59b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e59bd  test    al, al
0x1800e59bf  jz      loc_1800E5C9F
0x1800e59c5  mov     rcx, rbx; hModule
0x1800e59c8  mov     cs:hModule, rbx
0x1800e59cf  test    rcx, rcx
0x1800e59d2  jz      short loc_1800E59E9
0x1800e59d4  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800e59db  call    GetProcAddress_0
0x1800e59e0  mov     cs:qword_18011C0D0, rax
0x1800e59e7  jmp     short loc_1800E59F0
0x1800e59e9  mov     rax, cs:qword_18011C0D0
0x1800e59f0  xor     ebx, ebx
0x1800e59f2  lea     r14d, [rbx+1]
0x1800e59f6  test    rax, rax
0x1800e59f9  jz      loc_1800E5B1B
0x1800e59ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5a04  test    al, al
0x1800e5a06  jz      loc_1800E5B1B
0x1800e5a0c  mov     [rsp+298h+MaximumComponentLength], ebx
0x1800e5a10  mov     [rsp+298h+FileSystemFlags], ebx
0x1800e5a14  mov     [rsp+298h+hTemplateFile], rbx; hTemplateFile
0x1800e5a19  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e5a21  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e5a29  xor     r9d, r9d; lpSecurityAttributes
0x1800e5a2c  xor     edx, edx; dwDesiredAccess
0x1800e5a2e  lea     r8d, [rbx+7]; dwShareMode
0x1800e5a32  mov     rcx, rsi; lpFileName
0x1800e5a35  call    cs:__imp_CreateFileW
0x1800e5a3b  mov     rdi, rax
0x1800e5a3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e5a42  jz      loc_1800E5B1B
0x1800e5a48  mov     [rsp+298h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x1800e5a4c  mov     [rsp+298h+hTemplateFile], rbx; lpFileSystemNameBuffer
0x1800e5a51  lea     rax, [rsp+298h+FileSystemFlags]
0x1800e5a56  mov     qword ptr [rsp+298h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x1800e5a5b  lea     rax, [rsp+298h+MaximumComponentLength]
0x1800e5a60  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; lpMaximumComponentLength
0x1800e5a65  xor     r9d, r9d; lpVolumeSerialNumber
0x1800e5a68  mov     r8d, 105h; nVolumeNameSize
0x1800e5a6e  lea     rdx, [rsp+298h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800e5a73  mov     rcx, rdi; hFile
0x1800e5a76  call    GetVolumeInformationByHandleW_0
0x1800e5a7b  test    eax, eax
0x1800e5a7d  jz      loc_1800E5B0B
0x1800e5a83  test    [rsp+298h+FileSystemFlags], 80000h
0x1800e5a8b  jz      short loc_1800E5AA8
0x1800e5a8d  lea     rdx, aMainos; "MAINOS"
0x1800e5a94  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x1800e5a99  call    cs:__imp__o__wcsicmp
0x1800e5a9f  test    eax, eax
0x1800e5aa1  jnz     short loc_1800E5AA8
0x1800e5aa3  mov     ebx, r14d
0x1800e5aa6  jmp     short loc_1800E5B0B
0x1800e5aa8  cmp     cs:qword_18011C0E0, rbx
0x1800e5aaf  jnz     short loc_1800E5AEA
0x1800e5ab1  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x1800e5ab8  mov     rcx, cs:hModule; hModule
0x1800e5abf  call    GetProcAddress_0
0x1800e5ac4  mov     cs:qword_18011C0E0, rax
0x1800e5acb  test    rax, rax
0x1800e5ace  jz      short loc_1800E5AE3
0x1800e5ad0  xor     r8d, r8d
0x1800e5ad3  lea     rdx, dword_18011C0E8
0x1800e5ada  xor     ecx, ecx
0x1800e5adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5ae1  jmp     short loc_1800E5AEA
0x1800e5ae3  mov     cs:qword_18011C0E0, r14
0x1800e5aea  cmp     cs:dword_18011C0E8, 5
0x1800e5af1  jnz     short loc_1800E5B0B
0x1800e5af3  lea     rdx, aSystemBoot; "System Boot"
0x1800e5afa  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x1800e5aff  call    cs:__imp__o__wcsicmp
0x1800e5b05  test    eax, eax
0x1800e5b07  cmovz   ebx, r14d
0x1800e5b0b  mov     rcx, rdi; hObject
0x1800e5b0e  call    CloseHandle_0
0x1800e5b13  test    ebx, ebx
0x1800e5b15  jnz     loc_1800E5BC1
0x1800e5b1b  mov     rax, cs:qword_18011C0D8
0x1800e5b22  test    rax, rax
0x1800e5b25  jnz     loc_1800E5BB5
0x1800e5b2b  cmp     cs:byte_18011C0C8, al
0x1800e5b31  jnz     loc_1800E5BE0
0x1800e5b37  xor     edx, edx; hFile
0x1800e5b39  mov     r8d, 800h; dwFlags
0x1800e5b3f  lea     rcx, aSfcDll; "sfc.dll"
0x1800e5b46  call    cs:__imp_LoadLibraryExW
0x1800e5b4c  mov     rdi, rax
0x1800e5b4f  mov     rcx, cs:qword_180119DB8
0x1800e5b56  cmp     rax, rcx
0x1800e5b59  jz      short loc_1800E5B88
0x1800e5b5b  test    rcx, rcx
0x1800e5b5e  jz      short loc_1800E5B7E
0x1800e5b60  mov     rcx, cs:off_180119DB0
0x1800e5b67  mov     rax, [rcx]
0x1800e5b6a  lea     rcx, off_180119DB0
0x1800e5b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5b76  test    al, al
0x1800e5b78  jz      loc_1800E5CB8
0x1800e5b7e  mov     rcx, rdi; hModule
0x1800e5b81  mov     cs:qword_180119DB8, rcx
0x1800e5b88  test    rcx, rcx
0x1800e5b8b  jz      short loc_1800E5BA9
0x1800e5b8d  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x1800e5b94  call    GetProcAddress_0
0x1800e5b99  mov     cs:qword_18011C0D8, rax
0x1800e5ba0  mov     rcx, cs:qword_180119DB8
0x1800e5ba7  jmp     short loc_1800E5BB0
0x1800e5ba9  mov     rax, cs:qword_18011C0D8
0x1800e5bb0  test    rax, rax
0x1800e5bb3  jz      short loc_1800E5BE7
0x1800e5bb5  mov     rdx, rsi
0x1800e5bb8  xor     ecx, ecx
0x1800e5bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5bbf  mov     ebx, eax
0x1800e5bc1  mov     eax, ebx
0x1800e5bc3  mov     rcx, [rsp+298h+var_38]
0x1800e5bcb  xor     rcx, rsp; StackCookie
0x1800e5bce  call    __security_check_cookie
0x1800e5bd3  add     rsp, 278h
0x1800e5bda  pop     r14
0x1800e5bdc  pop     rdi
0x1800e5bdd  pop     rsi
0x1800e5bde  pop     rbx
0x1800e5bdf  retn
0x1800e5be0  mov     rcx, cs:qword_180119DB8
0x1800e5be7  mov     cs:byte_18011C0C8, r14b
0x1800e5bee  test    rcx, rcx
0x1800e5bf1  jz      short loc_1800E5C18
0x1800e5bf3  mov     rax, cs:off_180119DB0
0x1800e5bfa  lea     rcx, off_180119DB0
0x1800e5c01  mov     rax, [rax]
0x1800e5c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5c09  test    al, al
0x1800e5c0b  jz      short loc_1800E5C1A
0x1800e5c0d  mov     cs:qword_180119DB8, 0
0x1800e5c18  jmp     short loc_1800E5BC1
0x1800e5c1a  call    GetLastError_0
0x1800e5c1f  test    eax, eax
0x1800e5c21  jle     short loc_1800E5C2B
0x1800e5c23  movzx   eax, ax
0x1800e5c26  or      eax, 80070000h
0x1800e5c2b  mov     ecx, eax; this
0x1800e5c2d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800e5c32  nop
0x1800e5c33  lea     rcx, dword_18011C1A0
0x1800e5c3a  call    _Init_thread_header
0x1800e5c3f  cmp     cs:dword_18011C1A0, 0FFFFFFFFh
0x1800e5c46  jnz     loc_1800E5965
0x1800e5c4c  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__SfcModule__; void (__cdecl *)()
0x1800e5c53  call    atexit
0x1800e5c58  lea     rcx, dword_18011C1A0
0x1800e5c5f  call    _Init_thread_footer
0x1800e5c64  jmp     loc_1800E5965
0x1800e5c69  lea     rcx, dword_18011C1A4
0x1800e5c70  call    _Init_thread_header
0x1800e5c75  cmp     cs:dword_18011C1A4, 0FFFFFFFFh
0x1800e5c7c  jnz     loc_1800E5974
0x1800e5c82  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__NtdllModule__; void (__cdecl *)()
0x1800e5c89  call    atexit
0x1800e5c8e  lea     rcx, dword_18011C1A4
0x1800e5c95  call    _Init_thread_footer
0x1800e5c9a  jmp     loc_1800E5974
0x1800e5c9f  call    GetLastError_0
0x1800e5ca4  test    eax, eax
0x1800e5ca6  jle     short loc_1800E5CB0
0x1800e5ca8  movzx   eax, ax
0x1800e5cab  or      eax, 80070000h
0x1800e5cb0  mov     ecx, eax; this
0x1800e5cb2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800e5cb7  nop
0x1800e5cb8  call    GetLastError_0
0x1800e5cbd  test    eax, eax
0x1800e5cbf  jle     short loc_1800E5CC9
0x1800e5cc1  movzx   eax, ax
0x1800e5cc4  or      eax, 80070000h
0x1800e5cc9  mov     ecx, eax; this
0x1800e5ccb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
