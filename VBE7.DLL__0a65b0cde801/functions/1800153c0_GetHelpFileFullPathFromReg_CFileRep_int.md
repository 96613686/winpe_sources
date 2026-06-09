# GetHelpFileFullPathFromReg(CFileRep *,int)

- ea: `0x1800153c0`
- end: `0x180015548`
- name: `?GetHelpFileFullPathFromReg@@YAJPEAVCFileRep@@H@Z`
- size: `392`
- prototype: `__int64 __fastcall(struct CFileRep *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014590`

## callees

- `0x1800153c0`
- `0x18001ba34`
- `0x18001c154`
- `0x18001c6f0`
- `0x18005a514`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x180015525`
- `MSVCR100!free` at `0x180015533`
- `MSVCR100!free` at `0x180015525`
- `MSVCR100!free` at `0x180015533`
- `MSVCR100!malloc` at `0x1800153df`
- `MSVCR100!malloc` at `0x1800153df`
- `KERNEL32!GetPrivateProfileStringA` at `0x1800154e5`
- `KERNEL32!GetPrivateProfileStringA` at `0x1800154e5`
- `ADVAPI32!RegOpenKeyExA` at `0x180015434`
- `ADVAPI32!RegOpenKeyExA` at `0x18001546a`
- `ADVAPI32!RegOpenKeyExA` at `0x180015434`
- `ADVAPI32!RegOpenKeyExA` at `0x18001546a`
- `ADVAPI32!RegQueryValueExA` at `0x18001549b`
- `ADVAPI32!RegQueryValueExA` at `0x18001549b`
- `ADVAPI32!RegCloseKey` at `0x1800154a8`
- `ADVAPI32!RegCloseKey` at `0x1800154b3`
- `ADVAPI32!RegCloseKey` at `0x1800154a8`
- `ADVAPI32!RegCloseKey` at `0x1800154b3`

## pseudocode

```c
__int64 __fastcall GetHelpFileFullPathFromReg(struct CFileRep *a1, int a2)
{
  BYTE *v4; // rsi
  const char *NonPrintFullPath; // rax
  char *v6; // rax
  CHAR *v7; // rdi
  unsigned int v8; // ebx
  const CHAR *v9; // rdx
  LSTATUS v10; // ebp
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  v4 = (BYTE *)malloc(0x801u);
  NonPrintFullPath = CFileRep::GetNonPrintFullPath(a1);
  v6 = StrHszMakeFromLpszImpl(NonPrintFullPath);
  v7 = v6;
  if ( !v4 )
  {
    v8 = -2147024882;
    goto LABEL_16;
  }
  if ( !v6 )
  {
LABEL_13:
    v8 = -2147024882;
    goto LABEL_15;
  }
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Windows", 0, 0x20019u, &hKey) )
  {
    v9 = "Help";
    if ( a2 )
      v9 = "HTML Help";
    v10 = RegOpenKeyExA(hKey, v9, 0, 0x20019u, &phkResult);
    if ( !v10 )
    {
      cbData = 2048;
      v10 = RegQueryValueExA(phkResult, v7, 0, 0, v4, &cbData);
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    if ( !v10 )
      goto LABEL_21;
  }
  if ( GetPrivateProfileStringA("FILES", v7, Rby_szNull, (LPSTR)v4, 0x800u, "WINHELP.INI") )
  {
LABEL_21:
    if ( (unsigned int)CFileRep::SetDirectory(a1, (const char *)v4) )
    {
      v8 = (unsigned int)CFileRep::AddFileToDir(a1, v7) == 0 ? 0x8007000E : 0;
      goto LABEL_15;
    }
    goto LABEL_13;
  }
  v8 = 1;
LABEL_15:
  free(v4);
LABEL_16:
  if ( v7 )
    free(v7);
  return v8;
}

```

## disassembly

```asm
0x1800153c0  mov     [rsp+arg_0], rbx
0x1800153c5  push    rbp
0x1800153c6  push    rsi
0x1800153c7  push    rdi
0x1800153c8  mov     eax, 40h
0x1800153cd  call    _alloca_probe
0x1800153d2  sub     rsp, rax
0x1800153d5  mov     rbx, rcx
0x1800153d8  mov     ecx, 801h; Size
0x1800153dd  mov     ebp, edx
0x1800153df  call    cs:__imp_malloc
0x1800153e5  mov     rcx, rbx; this
0x1800153e8  mov     rsi, rax
0x1800153eb  call    ?GetNonPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetNonPrintFullPath(void)
0x1800153f0  mov     rcx, rax; char *
0x1800153f3  call    ?StrHszMakeFromLpszImpl@@YAPEADPEBD@Z; StrHszMakeFromLpszImpl(char const *)
0x1800153f8  mov     rdi, rax
0x1800153fb  test    rsi, rsi
0x1800153fe  jnz     short loc_18001540A
0x180015400  mov     ebx, 8007000Eh
0x180015405  jmp     loc_18001552B
0x18001540a  test    rax, rax
0x18001540d  jz      loc_180015503
0x180015413  lea     rax, [rsp+58h+hKey]
0x180015418  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows"
0x18001541f  mov     r9d, 20019h; samDesired
0x180015425  xor     r8d, r8d; ulOptions
0x180015428  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001542f  mov     [rsp+58h+phkResult], rax; phkResult
0x180015434  call    cs:__imp_RegOpenKeyExA
0x18001543a  test    eax, eax
0x18001543c  jnz     short loc_1800154BD
0x18001543e  mov     rcx, [rsp+58h+hKey]; hKey
0x180015443  lea     rax, aHtmlHelp; "HTML Help"
0x18001544a  lea     rdx, aHelp; "Help"
0x180015451  test    ebp, ebp
0x180015453  mov     r9d, 20019h; samDesired
0x180015459  cmovnz  rdx, rax; lpSubKey
0x18001545d  lea     rax, [rsp+58h+arg_18]
0x180015462  xor     r8d, r8d; ulOptions
0x180015465  mov     [rsp+58h+phkResult], rax; phkResult
0x18001546a  call    cs:__imp_RegOpenKeyExA
0x180015470  mov     ebp, eax
0x180015472  test    eax, eax
0x180015474  jnz     short loc_1800154AE
0x180015476  mov     rcx, [rsp+58h+arg_18]; hKey
0x18001547b  lea     rax, [rsp+58h+cbData]
0x180015480  xor     r9d, r9d; lpType
0x180015483  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180015488  xor     r8d, r8d; lpReserved
0x18001548b  mov     rdx, rdi; lpValueName
0x18001548e  mov     [rsp+58h+phkResult], rsi; lpData
0x180015493  mov     [rsp+58h+cbData], 800h
0x18001549b  call    cs:__imp_RegQueryValueExA
0x1800154a1  mov     rcx, [rsp+58h+arg_18]; hKey
0x1800154a6  mov     ebp, eax
0x1800154a8  call    cs:__imp_RegCloseKey
0x1800154ae  mov     rcx, [rsp+58h+hKey]; hKey
0x1800154b3  call    cs:__imp_RegCloseKey
0x1800154b9  test    ebp, ebp
0x1800154bb  jz      short loc_1800154F4
0x1800154bd  lea     rax, FileName; "WINHELP.INI"
0x1800154c4  lea     r8, ?Rby_szNull@@3PADA; lpDefault
0x1800154cb  lea     rcx, AppName; "FILES"
0x1800154d2  mov     [rsp+58h+lpcbData], rax; lpFileName
0x1800154d7  mov     r9, rsi; lpReturnedString
0x1800154da  mov     rdx, rdi; lpKeyName
0x1800154dd  mov     dword ptr [rsp+58h+phkResult], 800h; nSize
0x1800154e5  call    cs:__imp_GetPrivateProfileStringA
0x1800154eb  test    eax, eax
0x1800154ed  jnz     short loc_1800154F4
0x1800154ef  lea     ebx, [rax+1]
0x1800154f2  jmp     short loc_180015522
0x1800154f4  mov     rdx, rsi; char *
0x1800154f7  mov     rcx, rbx; this
0x1800154fa  call    ?SetDirectory@CFileRep@@QEAAHPEBD@Z; CFileRep::SetDirectory(char const *)
0x1800154ff  test    eax, eax
0x180015501  jnz     short loc_18001550A
0x180015503  mov     ebx, 8007000Eh
0x180015508  jmp     short loc_180015522
0x18001550a  mov     rdx, rdi; char *
0x18001550d  mov     rcx, rbx; this
0x180015510  call    ?AddFileToDir@CFileRep@@QEAAHPEBD@Z; CFileRep::AddFileToDir(char const *)
0x180015515  mov     ebx, 8007000Eh
0x18001551a  neg     eax
0x18001551c  sbb     ecx, ecx
0x18001551e  not     ecx
0x180015520  and     ebx, ecx
0x180015522  mov     rcx, rsi; Block
0x180015525  call    cs:__imp_free
0x18001552b  test    rdi, rdi
0x18001552e  jz      short loc_180015539
0x180015530  mov     rcx, rdi; Block
0x180015533  call    cs:__imp_free
0x180015539  mov     eax, ebx
0x18001553b  mov     rbx, [rsp+58h+arg_0]
0x180015540  add     rsp, 40h
0x180015544  pop     rdi
0x180015545  pop     rsi
0x180015546  pop     rbp
0x180015547  retn
```
