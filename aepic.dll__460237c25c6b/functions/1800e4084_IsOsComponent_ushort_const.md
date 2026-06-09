# _IsOsComponent(ushort const *)

- ea: `0x1800e4084`
- end: `0x1800e4359`
- name: `?_IsOsComponent@@YAHPEBG@Z`
- size: `725`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800e2b80`
- `0x1800e37c0`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x1800072f3`
- `0x1800e2034`
- `0x1800e24a4`
- `0x1800e4084`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e422f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4296`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e422f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4296`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e4148`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e42d6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e4148`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e42d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4255`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e42fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4170`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e4255`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e42fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e42a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e42a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e41cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e41cb`

## string_xrefs

- `0x1800e413b`: `ntdll.dll`
- `0x1800e42c9`: `sfc.dll`

## pseudocode

```c
__int64 __fastcall _IsOsComponent(LPCWSTR lpFileName)
{
  __int64 v2; // rbx
  unsigned int v3; // ebx
  HMODULE Library; // rax
  unsigned __int8 (*ProcAddress)(void); // rax
  HANDLE FileW; // rdi
  FARPROC v7; // rax
  FARPROC v8; // rax
  HMODULE v9; // rax
  DWORD FileSystemFlags; // [rsp+40h] [rbp-258h] BYREF
  DWORD MaximumComponentLength[3]; // [rsp+44h] [rbp-254h] BYREF
  WCHAR VolumeNameBuffer[264]; // [rsp+50h] [rbp-248h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180122F30 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180122F30);
    if ( dword_180122F30 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__SfcModule__);
      Init_thread_footer(&dword_180122F30);
    }
  }
  if ( dword_180122F34 > *(_DWORD *)(v2 + 4) )
  {
    Init_thread_header(&dword_180122F34);
    if ( dword_180122F34 == -1 )
    {
      atexit(_IsOsComponent_::_2_::_dynamic_atexit_destructor_for__NtdllModule__);
      Init_thread_footer(&dword_180122F34);
    }
  }
  v3 = 0;
  if ( hModule
    || (Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u),
        Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Attach(&off_180120780, Library),
        !hModule) )
  {
    ProcAddress = (unsigned __int8 (*)(void))qword_180122BC8;
  }
  else
  {
    ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(hModule, "RtlIsStateSeparationEnabled");
    qword_180122BC8 = (__int64)ProcAddress;
  }
  if ( !ProcAddress )
    goto LABEL_26;
  if ( !ProcAddress() )
    goto LABEL_26;
  MaximumComponentLength[0] = 0;
  FileSystemFlags = 0;
  FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_26;
  if ( GetVolumeInformationByHandleW_0(
         FileW,
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
      if ( !qword_180122BB0 )
      {
        v7 = GetProcAddress(hModule, "RtlGetDeviceFamilyInfoEnum");
        qword_180122BB0 = (__int64)v7;
        if ( v7 )
          ((void (__fastcall *)(_QWORD, int *, _QWORD))v7)(0, &dword_180122BAC, 0);
        else
          qword_180122BB0 = 1;
      }
      if ( dword_180122BAC == 5 && !(unsigned int)_o__wcsicmp(VolumeNameBuffer, L"System Boot") )
        v3 = 1;
    }
    else
    {
      v3 = 1;
    }
  }
  CloseHandle(FileW);
  if ( !v3 )
  {
LABEL_26:
    v8 = (FARPROC)qword_180122BC0;
    if ( qword_180122BC0 )
      return ((unsigned int (__fastcall *)(_QWORD, LPCWSTR))v8)(0, lpFileName);
    if ( !byte_180122BB8
      && ((v9 = LoadLibraryExW(L"sfc.dll", 0, 0x800u),
           Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Attach(&off_180120770, v9),
           !qword_180120778)
        ? (v8 = (FARPROC)qword_180122BC0)
        : (FARPROC)(v8 = GetProcAddress(qword_180120778, "SfcIsFileProtected"), qword_180122BC0 = (__int64)v8),
          v8) )
    {
      return ((unsigned int (__fastcall *)(_QWORD, LPCWSTR))v8)(0, lpFileName);
    }
    else
    {
      byte_180122BB8 = 1;
      Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(&off_180120770);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800e4084  push    rbx
0x1800e4086  push    rsi
0x1800e4087  push    rdi
0x1800e4088  push    r14
0x1800e408a  sub     rsp, 278h
0x1800e4091  mov     rax, cs:__security_cookie
0x1800e4098  xor     rax, rsp
0x1800e409b  mov     [rsp+298h+var_38], rax
0x1800e40a3  mov     rax, gs:58h
0x1800e40ac  mov     rsi, rcx
0x1800e40af  mov     ecx, cs:_tls_index
0x1800e40b5  mov     edi, 4
0x1800e40ba  mov     rbx, [rax+rcx*8]
0x1800e40be  mov     eax, [rbx+rdi]
0x1800e40c1  cmp     cs:dword_180122F30, eax
0x1800e40c7  jle     short loc_1800E40F6
0x1800e40c9  lea     rcx, dword_180122F30
0x1800e40d0  call    _Init_thread_header
0x1800e40d5  cmp     cs:dword_180122F30, 0FFFFFFFFh
0x1800e40dc  jnz     short loc_1800E40F6
0x1800e40de  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__SfcModule__; void (__cdecl *)()
0x1800e40e5  call    atexit
0x1800e40ea  lea     rcx, dword_180122F30
0x1800e40f1  call    _Init_thread_footer
0x1800e40f6  mov     eax, [rbx+rdi]
0x1800e40f9  cmp     cs:dword_180122F34, eax
0x1800e40ff  jle     short loc_1800E412E
0x1800e4101  lea     rcx, dword_180122F34
0x1800e4108  call    _Init_thread_header
0x1800e410d  cmp     cs:dword_180122F34, 0FFFFFFFFh
0x1800e4114  jnz     short loc_1800E412E
0x1800e4116  lea     rcx, __IsOsComponent____2____dynamic_atexit_destructor_for__NtdllModule__; void (__cdecl *)()
0x1800e411d  call    atexit
0x1800e4122  lea     rcx, dword_180122F34
0x1800e4129  call    _Init_thread_footer
0x1800e412e  xor     ebx, ebx
0x1800e4130  cmp     cs:hModule, rbx
0x1800e4137  jnz     short loc_1800E417F
0x1800e4139  xor     edx, edx; hFile
0x1800e413b  lea     rcx, LibFileName; "ntdll.dll"
0x1800e4142  mov     r8d, 800h; dwFlags
0x1800e4148  call    cs:__imp_LoadLibraryExW
0x1800e414e  mov     rdx, rax
0x1800e4151  lea     rcx, off_180120780
0x1800e4158  call    ?Attach@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAUHINSTANCE__@@@Z; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Attach(HINSTANCE__ *)
0x1800e415d  mov     rcx, cs:hModule; hModule
0x1800e4164  test    rcx, rcx
0x1800e4167  jz      short loc_1800E417F
0x1800e4169  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800e4170  call    cs:__imp_GetProcAddress
0x1800e4176  mov     cs:qword_180122BC8, rax
0x1800e417d  jmp     short loc_1800E4186
0x1800e417f  mov     rax, cs:qword_180122BC8
0x1800e4186  mov     r14d, 1
0x1800e418c  test    rax, rax
0x1800e418f  jz      loc_1800E42B3
0x1800e4195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e419a  test    al, al
0x1800e419c  jz      loc_1800E42B3
0x1800e41a2  mov     [rsp+298h+hTemplateFile], rbx; hTemplateFile
0x1800e41a7  lea     r8d, [r14+6]; dwShareMode
0x1800e41ab  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e41b3  xor     r9d, r9d; lpSecurityAttributes
0x1800e41b6  xor     edx, edx; dwDesiredAccess
0x1800e41b8  mov     [rsp+298h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e41c0  mov     rcx, rsi; lpFileName
0x1800e41c3  mov     [rsp+298h+MaximumComponentLength], ebx
0x1800e41c7  mov     [rsp+298h+FileSystemFlags], ebx
0x1800e41cb  call    cs:__imp_CreateFileW
0x1800e41d1  mov     rdi, rax
0x1800e41d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e41d8  jz      loc_1800E42B3
0x1800e41de  mov     [rsp+298h+nFileSystemNameSize], ebx; nFileSystemNameSize
0x1800e41e2  lea     rax, [rsp+298h+FileSystemFlags]
0x1800e41e7  mov     [rsp+298h+hTemplateFile], rbx; lpFileSystemNameBuffer
0x1800e41ec  lea     rdx, [rsp+298h+VolumeNameBuffer]; lpVolumeNameBuffer
0x1800e41f1  mov     qword ptr [rsp+298h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x1800e41f6  xor     r9d, r9d; lpVolumeSerialNumber
0x1800e41f9  lea     rax, [rsp+298h+MaximumComponentLength]
0x1800e41fe  mov     r8d, 105h; nVolumeNameSize
0x1800e4204  mov     rcx, rdi; hFile
0x1800e4207  mov     qword ptr [rsp+298h+dwCreationDisposition], rax; lpMaximumComponentLength
0x1800e420c  call    GetVolumeInformationByHandleW_0
0x1800e4211  test    eax, eax
0x1800e4213  jz      loc_1800E42A2
0x1800e4219  test    [rsp+298h+FileSystemFlags], 80000h
0x1800e4221  jz      short loc_1800E423E
0x1800e4223  lea     rdx, aMainos; "MAINOS"
0x1800e422a  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x1800e422f  call    cs:__imp__o__wcsicmp
0x1800e4235  test    eax, eax
0x1800e4237  jnz     short loc_1800E423E
0x1800e4239  mov     ebx, r14d
0x1800e423c  jmp     short loc_1800E42A2
0x1800e423e  cmp     cs:qword_180122BB0, rbx
0x1800e4245  jnz     short loc_1800E4281
0x1800e4247  mov     rcx, cs:hModule; hModule
0x1800e424e  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x1800e4255  call    cs:__imp_GetProcAddress
0x1800e425b  mov     cs:qword_180122BB0, rax
0x1800e4262  test    rax, rax
0x1800e4265  jz      short loc_1800E427A
0x1800e4267  xor     r8d, r8d
0x1800e426a  lea     rdx, dword_180122BAC
0x1800e4271  xor     ecx, ecx
0x1800e4273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4278  jmp     short loc_1800E4281
0x1800e427a  mov     cs:qword_180122BB0, r14
0x1800e4281  cmp     cs:dword_180122BAC, 5
0x1800e4288  jnz     short loc_1800E42A2
0x1800e428a  lea     rdx, aSystemBoot; "System Boot"
0x1800e4291  lea     rcx, [rsp+298h+VolumeNameBuffer]
0x1800e4296  call    cs:__imp__o__wcsicmp
0x1800e429c  test    eax, eax
0x1800e429e  cmovz   ebx, r14d
0x1800e42a2  mov     rcx, rdi; hObject
0x1800e42a5  call    cs:__imp_CloseHandle
0x1800e42ab  test    ebx, ebx
0x1800e42ad  jnz     loc_1800E433A
0x1800e42b3  mov     rax, cs:qword_180122BC0
0x1800e42ba  test    rax, rax
0x1800e42bd  jnz     short loc_1800E432E
0x1800e42bf  cmp     cs:byte_180122BB8, al
0x1800e42c5  jnz     short loc_1800E4319
0x1800e42c7  xor     edx, edx; hFile
0x1800e42c9  lea     rcx, aSfcDll; "sfc.dll"
0x1800e42d0  mov     r8d, 800h; dwFlags
0x1800e42d6  call    cs:__imp_LoadLibraryExW
0x1800e42dc  mov     rdx, rax
0x1800e42df  lea     rcx, off_180120770
0x1800e42e6  call    ?Attach@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAUHINSTANCE__@@@Z; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Attach(HINSTANCE__ *)
0x1800e42eb  mov     rcx, cs:qword_180120778; hModule
0x1800e42f2  test    rcx, rcx
0x1800e42f5  jz      short loc_1800E430D
0x1800e42f7  lea     rdx, aSfcisfileprote; "SfcIsFileProtected"
0x1800e42fe  call    cs:__imp_GetProcAddress
0x1800e4304  mov     cs:qword_180122BC0, rax
0x1800e430b  jmp     short loc_1800E4314
0x1800e430d  mov     rax, cs:qword_180122BC0
0x1800e4314  test    rax, rax
0x1800e4317  jnz     short loc_1800E432E
0x1800e4319  lea     rcx, off_180120770
0x1800e4320  mov     cs:byte_180122BB8, r14b
0x1800e4327  call    ?Close@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(void)
0x1800e432c  jmp     short loc_1800E433A
0x1800e432e  mov     rdx, rsi
0x1800e4331  xor     ecx, ecx
0x1800e4333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4338  mov     ebx, eax
0x1800e433a  mov     eax, ebx
0x1800e433c  mov     rcx, [rsp+298h+var_38]
0x1800e4344  xor     rcx, rsp; StackCookie
0x1800e4347  call    __security_check_cookie
0x1800e434c  add     rsp, 278h
0x1800e4353  pop     r14
0x1800e4355  pop     rdi
0x1800e4356  pop     rsi
0x1800e4357  pop     rbx
0x1800e4358  retn
```
