# CAddMdmObj::AddModem(ulong *,unsigned __int64)

- ea: `0x180005a70`
- end: `0x180005bb8`
- name: `?AddModem@CAddMdmObj@@UEAAJPEAK_K@Z`
- size: `328`
- prototype: `__int64 __fastcall(CAddMdmObj *this, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005a70`
- `0x180005f60`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180005af2`
- `msvcrt!wcscat_s` at `0x180005af2`
- `KERNEL32!GetSystemDirectoryW` at `0x180005ab0`
- `KERNEL32!GetSystemDirectoryW` at `0x180005ab0`
- `KERNEL32!GetLastError` at `0x180005aba`
- `KERNEL32!GetLastError` at `0x180005b4d`
- `KERNEL32!GetLastError` at `0x180005b72`
- `KERNEL32!GetLastError` at `0x180005aba`
- `KERNEL32!GetLastError` at `0x180005b4d`
- `KERNEL32!GetLastError` at `0x180005b72`
- `KERNEL32!LoadLibraryW` at `0x180005afd`
- `KERNEL32!LoadLibraryW` at `0x180005afd`
- `KERNEL32!GetProcAddress` at `0x180005b15`
- `KERNEL32!GetProcAddress` at `0x180005b2e`
- `KERNEL32!GetProcAddress` at `0x180005b15`
- `KERNEL32!GetProcAddress` at `0x180005b2e`
- `KERNEL32!FreeLibrary` at `0x180005b65`
- `KERNEL32!FreeLibrary` at `0x180005b65`

## string_xrefs

- `0x180005b0b`: `InstallNewDevice`
- `0x180005b20`: `InstallNewDevice`

## pseudocode

```c
__int64 __fastcall CAddMdmObj::AddModem(CAddMdmObj *this, unsigned int *a2, __int64 a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  HMODULE LibraryW; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebp
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  signed int v12; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  Buffer[0] = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    wcscat_s(Buffer, 0x104u, L"\\hdwwiz.cpl");
    LibraryW = LoadLibraryW(Buffer);
    v8 = LibraryW;
    if ( LibraryW )
    {
      if ( GetProcAddress(LibraryW, "InstallNewDevice") )
      {
        v6 = 0;
        v9 = 0;
        ProcAddress = GetProcAddress(v8, "InstallNewDevice");
        ((void (__fastcall *)(__int64, GUID *, _QWORD))ProcAddress)(a3, &GUID_DEVCLASS_MODEM, 0);
      }
      else
      {
        v9 = 2;
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      FreeLibrary(v8);
    }
    else
    {
      v9 = 1;
      v12 = GetLastError();
      v6 = v12;
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
    }
    if ( a2 )
      *a2 = v9;
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( a2 )
      *a2 = 3;
  }
  return v6;
}

```

## disassembly

```asm
0x180005a70  mov     [rsp+arg_0], rbx
0x180005a75  mov     [rsp+arg_18], rbp
0x180005a7a  push    rsi
0x180005a7b  push    rdi
0x180005a7c  push    r14
0x180005a7e  sub     rsp, 240h
0x180005a85  mov     rax, cs:__security_cookie
0x180005a8c  xor     rax, rsp
0x180005a8f  mov     [rsp+258h+var_28], rax
0x180005a97  mov     rdi, rdx
0x180005a9a  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180005a9f  xor     eax, eax
0x180005aa1  mov     ebx, 104h
0x180005aa6  mov     edx, ebx; uSize
0x180005aa8  mov     [rsp+258h+Buffer], ax
0x180005aad  mov     r14, r8
0x180005ab0  call    cs:__imp_GetSystemDirectoryW
0x180005ab6  test    eax, eax
0x180005ab8  jnz     short loc_180005AE3
0x180005aba  call    cs:__imp_GetLastError
0x180005ac0  mov     ebx, eax
0x180005ac2  test    eax, eax
0x180005ac4  jle     short loc_180005ACF
0x180005ac6  movzx   ebx, ax
0x180005ac9  or      ebx, 80070000h
0x180005acf  test    rdi, rdi
0x180005ad2  jz      loc_180005B8E
0x180005ad8  mov     dword ptr [rdi], 3
0x180005ade  jmp     loc_180005B8E
0x180005ae3  lea     r8, aHdwwizCpl; "\\hdwwiz.cpl"
0x180005aea  mov     rdx, rbx; SizeInWords
0x180005aed  lea     rcx, [rsp+258h+Buffer]; Destination
0x180005af2  call    cs:__imp_wcscat_s
0x180005af8  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180005afd  call    cs:__imp_LoadLibraryW
0x180005b03  mov     rsi, rax
0x180005b06  test    rax, rax
0x180005b09  jz      short loc_180005B6D
0x180005b0b  lea     rdx, aInstallnewdevi; "InstallNewDevice"
0x180005b12  mov     rcx, rax; hModule
0x180005b15  call    cs:__imp_GetProcAddress
0x180005b1b  test    rax, rax
0x180005b1e  jz      short loc_180005B48
0x180005b20  lea     rdx, aInstallnewdevi; "InstallNewDevice"
0x180005b27  mov     rcx, rsi; hModule
0x180005b2a  xor     ebx, ebx
0x180005b2c  xor     ebp, ebp
0x180005b2e  call    cs:__imp_GetProcAddress
0x180005b34  xor     r8d, r8d
0x180005b37  lea     rdx, GUID_DEVCLASS_MODEM
0x180005b3e  mov     rcx, r14
0x180005b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b46  jmp     short loc_180005B62
0x180005b48  mov     ebp, 2
0x180005b4d  call    cs:__imp_GetLastError
0x180005b53  mov     ebx, eax
0x180005b55  test    eax, eax
0x180005b57  jle     short loc_180005B62
0x180005b59  movzx   ebx, ax
0x180005b5c  or      ebx, 80070000h
0x180005b62  mov     rcx, rsi; hLibModule
0x180005b65  call    cs:__imp_FreeLibrary
0x180005b6b  jmp     short loc_180005B87
0x180005b6d  mov     ebp, 1
0x180005b72  call    cs:__imp_GetLastError
0x180005b78  mov     ebx, eax
0x180005b7a  test    eax, eax
0x180005b7c  jle     short loc_180005B87
0x180005b7e  movzx   ebx, ax
0x180005b81  or      ebx, 80070000h
0x180005b87  test    rdi, rdi
0x180005b8a  jz      short loc_180005B8E
0x180005b8c  mov     [rdi], ebp
0x180005b8e  mov     eax, ebx
0x180005b90  mov     rcx, [rsp+258h+var_28]
0x180005b98  xor     rcx, rsp; StackCookie
0x180005b9b  call    __security_check_cookie
0x180005ba0  lea     r11, [rsp+258h+var_18]
0x180005ba8  mov     rbx, [r11+20h]
0x180005bac  mov     rbp, [r11+38h]
0x180005bb0  mov     rsp, r11
0x180005bb3  pop     r14
0x180005bb5  pop     rdi
0x180005bb6  pop     rsi
0x180005bb7  retn
```
