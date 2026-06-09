# WaasMedic::CWaasRemediation::LoadPluginLibrary(ushort const *)

- ea: `0x18001558c`
- end: `0x180015754`
- name: `?LoadPluginLibrary@CWaasRemediation@WaasMedic@@QEAAJPEBG@Z`
- size: `456`
- prototype: `__int64 __fastcall(WaasMedic::CWaasRemediation *__hidden this, LPCWSTR lpSrc)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180017a60`
- `0x1800184b0`

## callees

- `0x1800050a0`
- `0x180013998`
- `0x18001558c`
- `0x180028b9c`
- `0x180028bec`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800156c9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800156c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015727`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180015727`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800155cd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800155cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001563b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001563b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800156b9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800156b9`

## string_xrefs

- `0x180015676`: `CreateFile failed wih error: 0x%08x`
- `0x180015708`: `Failed to load plugin library:%s.  hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CWaasRemediation::LoadPluginLibrary(WaasMedic::CWaasRemediation *this, LPCWSTR lpSrc)
{
  char *FileW; // rbx
  DWORD v4; // eax
  signed int LastError; // eax
  signed int IsTrustedLibrary; // edi
  unsigned __int16 *v7; // rdx
  signed int v8; // eax
  WaasMedic *v9; // rcx
  HMODULE LibraryW; // rax
  signed int v11; // eax
  WCHAR Dst[264]; // [rsp+50h] [rbp-228h] BYREF

  FileW = 0;
  v4 = ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u);
  if ( v4 )
  {
    if ( v4 > 0x104 )
    {
      IsTrustedLibrary = -2147024774;
      goto LABEL_24;
    }
    goto LABEL_5;
  }
  LastError = GetLastError();
  IsTrustedLibrary = LastError;
  if ( LastError > 0 )
    IsTrustedLibrary = (unsigned __int16)LastError | 0x80070000;
  if ( IsTrustedLibrary >= 0 )
  {
LABEL_5:
    if ( !*((_QWORD *)this + 8)
      || (IsTrustedLibrary = WaasMedic::CWaasRemediation::FreePluginLibrary(this), IsTrustedLibrary >= 0) )
    {
      FileW = (char *)CreateFileW(Dst, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        IsTrustedLibrary = WaasMedic::IsTrustedLibrary(Dst, v7);
        if ( IsTrustedLibrary >= 0 )
        {
          if ( WaasMedic::IsTestSigningEnabled(v9) )
            LibraryW = LoadLibraryW(Dst);
          else
            LibraryW = LoadLibraryExW(Dst, 0, 0x880u);
          *((_QWORD *)this + 8) = LibraryW;
          if ( LibraryW )
          {
            LogLevelW(5u, L"Library loaded.");
          }
          else
          {
            v11 = GetLastError();
            IsTrustedLibrary = v11;
            if ( v11 > 0 )
              IsTrustedLibrary = (unsigned __int16)v11 | 0x80070000;
            LogLevelW(2u, L"Failed to load plugin library:%s.  hr=0x%08x", Dst, (unsigned int)IsTrustedLibrary);
          }
        }
      }
      else
      {
        v8 = GetLastError();
        IsTrustedLibrary = v8;
        if ( v8 > 0 )
          IsTrustedLibrary = (unsigned __int16)v8 | 0x80070000;
        if ( IsTrustedLibrary >= 0 )
          IsTrustedLibrary = -2147024786;
        LogLevelW(3u, L"CreateFile failed wih error: 0x%08x", (unsigned int)IsTrustedLibrary);
      }
    }
  }
LABEL_24:
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return (unsigned int)IsTrustedLibrary;
}

```

## disassembly

```asm
0x18001558c  mov     [rsp+arg_10], rbx
0x180015591  mov     [rsp+arg_18], rsi
0x180015596  push    rdi
0x180015597  sub     rsp, 270h
0x18001559e  mov     rax, cs:__security_cookie
0x1800155a5  xor     rax, rsp
0x1800155a8  mov     [rsp+278h+var_18], rax
0x1800155b0  mov     rax, rdx
0x1800155b3  mov     rsi, rcx
0x1800155b6  xor     ebx, ebx
0x1800155b8  mov     [rsp+278h+var_238], rbx
0x1800155bd  mov     edi, 104h
0x1800155c2  mov     r8d, edi; nSize
0x1800155c5  lea     rdx, [rsp+278h+Dst]; lpDst
0x1800155ca  mov     rcx, rax; lpSrc
0x1800155cd  call    cs:__imp_ExpandEnvironmentStringsW
0x1800155d3  test    eax, eax
0x1800155d5  jnz     loc_18001568C
0x1800155db  call    cs:__imp_GetLastError
0x1800155e1  mov     edi, eax
0x1800155e3  test    eax, eax
0x1800155e5  jle     short loc_1800155F0
0x1800155e7  movzx   edi, ax
0x1800155ea  or      edi, 80070000h
0x1800155f0  test    edi, edi
0x1800155f2  js      loc_18001571A
0x1800155f8  cmp     qword ptr [rsi+40h], 0
0x1800155fd  jz      short loc_180015611
0x1800155ff  mov     rcx, rsi; this
0x180015602  call    ?FreePluginLibrary@CWaasRemediation@WaasMedic@@QEAAJXZ; WaasMedic::CWaasRemediation::FreePluginLibrary(void)
0x180015607  mov     edi, eax
0x180015609  test    eax, eax
0x18001560b  js      loc_18001571A
0x180015611  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18001561a  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180015622  mov     [rsp+278h+dwCreationDisposition], 3; dwCreationDisposition
0x18001562a  xor     r9d, r9d; lpSecurityAttributes
0x18001562d  mov     edx, 80000000h; dwDesiredAccess
0x180015632  lea     r8d, [r9+1]; dwShareMode
0x180015636  lea     rcx, [rsp+278h+Dst]; lpFileName
0x18001563b  call    cs:__imp_CreateFileW
0x180015641  mov     rbx, rax
0x180015644  mov     [rsp+278h+var_238], rax
0x180015649  inc     rax
0x18001564c  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015652  jnz     short loc_18001569B
0x180015654  call    cs:__imp_GetLastError
0x18001565a  mov     edi, eax
0x18001565c  test    eax, eax
0x18001565e  jle     short loc_180015669
0x180015660  movzx   edi, ax
0x180015663  or      edi, 80070000h
0x180015669  mov     eax, 8007006Eh
0x18001566e  test    edi, edi
0x180015670  cmovns  edi, eax
0x180015673  mov     r8d, edi
0x180015676  lea     rdx, aCreatefileFail; "CreateFile failed wih error: 0x%08x"
0x18001567d  mov     ecx, 3; unsigned __int8
0x180015682  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180015687  jmp     loc_18001571A
0x18001568c  cmp     eax, edi
0x18001568e  jbe     loc_1800155F8
0x180015694  mov     edi, 8007007Ah
0x180015699  jmp     short loc_18001571A
0x18001569b  lea     rcx, [rsp+278h+Dst]; lpwstrFilename
0x1800156a0  call    ?IsTrustedLibrary@WaasMedic@@YAJPEAG@Z; WaasMedic::IsTrustedLibrary(ushort *)
0x1800156a5  mov     edi, eax
0x1800156a7  test    eax, eax
0x1800156a9  js      short loc_18001571A
0x1800156ab  call    ?IsTestSigningEnabled@WaasMedic@@YA_NXZ; WaasMedic::IsTestSigningEnabled(void)
0x1800156b0  lea     rcx, [rsp+278h+Dst]; lpLibFileName
0x1800156b5  test    al, al
0x1800156b7  jz      short loc_1800156C1
0x1800156b9  call    cs:__imp_LoadLibraryW
0x1800156bf  jmp     short loc_1800156CF
0x1800156c1  xor     edx, edx; hFile
0x1800156c3  mov     r8d, 880h; dwFlags
0x1800156c9  call    cs:__imp_LoadLibraryExW
0x1800156cf  mov     [rsi+40h], rax
0x1800156d3  test    rax, rax
0x1800156d6  jz      short loc_1800156EB
0x1800156d8  lea     rdx, aLibraryLoaded; "Library loaded."
0x1800156df  mov     ecx, 5; unsigned __int8
0x1800156e4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800156e9  jmp     short loc_18001571A
0x1800156eb  call    cs:__imp_GetLastError
0x1800156f1  mov     edi, eax
0x1800156f3  test    eax, eax
0x1800156f5  jle     short loc_180015700
0x1800156f7  movzx   edi, ax
0x1800156fa  or      edi, 80070000h
0x180015700  mov     r9d, edi
0x180015703  lea     r8, [rsp+278h+Dst]
0x180015708  lea     rdx, aFailedToLoadPl; "Failed to load plugin library:%s.  hr=0"...
0x18001570f  mov     ecx, 2; unsigned __int8
0x180015714  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180015719  nop
0x18001571a  lea     rax, [rbx-1]
0x18001571e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015722  ja      short loc_18001572D
0x180015724  mov     rcx, rbx; hObject
0x180015727  call    cs:__imp_CloseHandle
0x18001572d  mov     eax, edi
0x18001572f  mov     rcx, [rsp+278h+var_18]
0x180015737  xor     rcx, rsp; StackCookie
0x18001573a  call    __security_check_cookie
0x18001573f  lea     r11, [rsp+278h+var_8]
0x180015747  mov     rbx, [r11+20h]
0x18001574b  mov     rsi, [r11+28h]
0x18001574f  mov     rsp, r11
0x180015752  pop     rdi
0x180015753  retn
```
