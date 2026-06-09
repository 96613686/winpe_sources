# _AttributesFromRunLevelInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1801173a0`
- end: `0x1801175f8`
- name: `?_AttributesFromRunLevelInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(const wchar_t ***, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180019530`
- `0x1800197d4`
- `0x180059920`
- `0x18005ab10`
- `0x1801173a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011744d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18011744d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180117434`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180117434`
- `KERNEL32!CreateActCtxW` at `0x180117483`
- `KERNEL32!CreateActCtxW` at `0x180117483`
- `KERNEL32!QueryActCtxW` at `0x180117520`
- `KERNEL32!QueryActCtxW` at `0x180117520`
- `KERNEL32!ReleaseActCtx` at `0x180117554`
- `KERNEL32!ReleaseActCtx` at `0x1801175cc`
- `KERNEL32!ReleaseActCtx` at `0x180117554`
- `KERNEL32!ReleaseActCtx` at `0x1801175cc`

## string_xrefs

- `0x1801174b0`: `Failed to create activation context [%x]`
- `0x180117572`: `RequireAdministrator`

## pseudocode

```c
__int64 __fastcall _AttributesFromRunLevelInfo(const wchar_t ***a1, __int64 a2)
{
  const wchar_t **v3; // rax
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx
  HANDLE v6; // rdi
  DWORD LastError_0; // eax
  const wchar_t *v8; // rcx
  BOOL v10; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pvBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v13; // [rsp+98h] [rbp-68h]
  wchar_t Ext[264]; // [rsp+A0h] [rbp-60h] BYREF

  pvBuffer = 0;
  v13 = 0;
  Ext[0] = 0;
  v3 = *a1;
  v10 = 0;
  memset(&pActCtx, 0, sizeof(pActCtx));
  v4 = *v3;
  if ( _wsplitpath_s(*v3, 0, 0, 0, 0, 0, 0, Ext, 0x104u) || (unsigned int)_o__wcsicmp(Ext, L".EXE") )
    return 0;
  pActCtx.cbSize = 56;
  v5 = -2147467259;
  pActCtx.dwFlags = 8;
  pActCtx.lpSource = v4;
  pActCtx.lpResourceName = (LPCWSTR)1;
  v6 = CreateActCtxW(&pActCtx);
  if ( v6 != (HANDLE)-1LL )
  {
    if ( !QueryActCtxW(0x80000000, v6, 0, 5u, &pvBuffer, 0xCu, 0) )
    {
      GetLastError_0();
      AslLogCallPrintf(
        1,
        (unsigned int)"_AttributesFromRunLevelInfo",
        2043,
        (unsigned int)"Failed to query activation context [%x]");
      ReleaseActCtx(v6);
      return v5;
    }
    if ( HIDWORD(pvBuffer) )
    {
      switch ( HIDWORD(pvBuffer) )
      {
        case 1:
          v8 = L"AsInvoker";
          goto LABEL_19;
        case 2:
          v8 = L"HighestAvailable";
          goto LABEL_19;
        case 3:
          v8 = L"RequireAdministrator";
LABEL_19:
          _SetFileAttributeValue(v8, 520, 32, a2);
          v10 = v13 != 0;
          _SetFileAttributeValue(&v10, 4, 33, a2);
          ReleaseActCtx(v6);
          return 0;
      }
    }
    v8 = L"Unspecified";
    goto LABEL_19;
  }
  LastError_0 = GetLastError_0();
  if ( LastError_0 - 1812 <= 2 || LastError_0 == 193 || LastError_0 == 14001 )
  {
    _SetFileAttributeValue(L"Unspecified", 520, 32, a2);
    return 0;
  }
  AslLogCallPrintf(
    1,
    (unsigned int)"_AttributesFromRunLevelInfo",
    2029,
    (unsigned int)"Failed to create activation context [%x]");
  return v5;
}

```

## disassembly

```asm
0x1801173a0  mov     [rsp-8+arg_10], rbx
0x1801173a5  push    rbp
0x1801173a6  push    rsi
0x1801173a7  push    rdi
0x1801173a8  lea     rbp, [rsp-1C0h]
0x1801173b0  sub     rsp, 2C0h
0x1801173b7  mov     rax, cs:__security_cookie
0x1801173be  xor     rax, rsp
0x1801173c1  mov     [rbp+1D0h+var_20], rax
0x1801173c8  xor     eax, eax
0x1801173ca  mov     [rsp+2D0h+ExtCount], 104h; ExtCount
0x1801173d3  mov     [rbp+1D0h+pActCtx.hModule], rax
0x1801173d7  xorps   xmm0, xmm0
0x1801173da  mov     [rbp+1D0h+pvBuffer], rax
0x1801173de  mov     rsi, rdx
0x1801173e1  mov     [rbp+1D0h+var_238], eax
0x1801173e4  xor     r9d, r9d; Dir
0x1801173e7  mov     [rbp+1D0h+var_230], ax
0x1801173eb  xor     r8d, r8d; DriveCount
0x1801173ee  mov     rax, [rcx]
0x1801173f1  xor     edx, edx; Drive
0x1801173f3  mov     [rsp+2D0h+var_280], 0
0x1801173fb  movups  xmmword ptr [rsp+2D0h+pActCtx.cbSize], xmm0
0x180117400  movups  xmmword ptr [rsp+2D0h+pActCtx.wProcessorArchitecture], xmm0
0x180117405  movups  xmmword ptr [rsp+2D0h+pActCtx.lpResourceName], xmm0
0x18011740a  mov     rdi, [rax]
0x18011740d  lea     rax, [rbp+1D0h+var_230]
0x180117411  mov     [rsp+2D0h+Ext], rax; Ext
0x180117416  mov     rcx, rdi; FullPath
0x180117419  mov     [rsp+2D0h+FilenameCount], 0; FilenameCount
0x180117422  mov     [rsp+2D0h+Filename], 0; Filename
0x18011742b  mov     [rsp+2D0h+DirCount], 0; DirCount
0x180117434  call    cs:__imp__wsplitpath_s
0x18011743a  test    eax, eax
0x18011743c  jnz     loc_1801175D2
0x180117442  lea     rdx, aExe_0; ".EXE"
0x180117449  lea     rcx, [rbp+1D0h+var_230]
0x18011744d  call    cs:__imp__o__wcsicmp
0x180117453  test    eax, eax
0x180117455  jnz     loc_1801175D2
0x18011745b  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x180117460  mov     [rsp+2D0h+pActCtx.cbSize], 38h ; '8'
0x180117468  mov     ebx, 80004005h
0x18011746d  mov     [rsp+2D0h+pActCtx.dwFlags], 8
0x180117475  mov     [rsp+2D0h+pActCtx.lpSource], rdi
0x18011747a  mov     [rsp+2D0h+pActCtx.lpResourceName], 1
0x180117483  call    cs:__imp_CreateActCtxW
0x180117489  mov     rdi, rax
0x18011748c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180117490  jnz     short loc_1801174F4
0x180117492  call    GetLastError_0
0x180117497  lea     edx, [rax-714h]
0x18011749d  cmp     edx, 2
0x1801174a0  jbe     short loc_1801174D5
0x1801174a2  cmp     eax, 0C1h
0x1801174a7  jz      short loc_1801174D5
0x1801174a9  cmp     eax, 36B1h
0x1801174ae  jz      short loc_1801174D5
0x1801174b0  lea     r9, aFailedToCreate_0; "Failed to create activation context [%x"...
0x1801174b7  mov     dword ptr [rsp+2D0h+DirCount], eax
0x1801174bb  mov     r8d, 7EDh
0x1801174c1  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1801174c8  lea     ecx, [rdi+2]
0x1801174cb  call    AslLogCallPrintf
0x1801174d0  jmp     loc_1801175D4
0x1801174d5  mov     r9, rsi
0x1801174d8  lea     rcx, aUnspecified; "Unspecified"
0x1801174df  mov     edx, 208h
0x1801174e4  mov     r8d, 20h ; ' '
0x1801174ea  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1801174ef  jmp     loc_1801175D2
0x1801174f4  mov     [rsp+2D0h+FilenameCount], 0; pcbWrittenOrRequired
0x1801174fd  lea     rax, [rbp+1D0h+pvBuffer]
0x180117501  mov     [rsp+2D0h+Filename], 0Ch; cbBuffer
0x18011750a  mov     r9d, 5; ulInfoClass
0x180117510  xor     r8d, r8d; pvSubInstance
0x180117513  mov     [rsp+2D0h+DirCount], rax; pvBuffer
0x180117518  mov     rdx, rdi; hActCtx
0x18011751b  mov     ecx, 80000000h; dwFlags
0x180117520  call    cs:__imp_QueryActCtxW
0x180117526  test    eax, eax
0x180117528  jnz     short loc_18011755C
0x18011752a  call    GetLastError_0
0x18011752f  lea     r9, aFailedToQueryA; "Failed to query activation context [%x]"
0x180117536  mov     dword ptr [rsp+2D0h+DirCount], eax
0x18011753a  mov     r8d, 7FBh
0x180117540  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x180117547  mov     ecx, 1
0x18011754c  call    AslLogCallPrintf
0x180117551  mov     rcx, rdi; hActCtx
0x180117554  call    cs:__imp_ReleaseActCtx
0x18011755a  jmp     short loc_1801175D4
0x18011755c  mov     ecx, dword ptr [rbp+1D0h+pvBuffer+4]
0x18011755f  test    ecx, ecx
0x180117561  jz      short loc_18011758D
0x180117563  sub     ecx, 1
0x180117566  jz      short loc_180117584
0x180117568  sub     ecx, 1
0x18011756b  jz      short loc_18011757B
0x18011756d  cmp     ecx, 1
0x180117570  jnz     short loc_18011758D
0x180117572  lea     rcx, aRequireadminis; "RequireAdministrator"
0x180117579  jmp     short loc_180117594
0x18011757b  lea     rcx, aHighestavailab; "HighestAvailable"
0x180117582  jmp     short loc_180117594
0x180117584  lea     rcx, aAsinvoker; "AsInvoker"
0x18011758b  jmp     short loc_180117594
0x18011758d  lea     rcx, aUnspecified; "Unspecified"
0x180117594  mov     r9, rsi
0x180117597  mov     edx, 208h
0x18011759c  mov     r8d, 20h ; ' '
0x1801175a2  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1801175a7  xor     eax, eax
0x1801175a9  lea     rcx, [rsp+2D0h+var_280]
0x1801175ae  cmp     [rbp+1D0h+var_238], eax
0x1801175b1  mov     edx, 4
0x1801175b6  mov     r9, rsi
0x1801175b9  setnz   al
0x1801175bc  mov     [rsp+2D0h+var_280], eax
0x1801175c0  lea     r8d, [rdx+1Dh]
0x1801175c4  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1801175c9  mov     rcx, rdi; hActCtx
0x1801175cc  call    cs:__imp_ReleaseActCtx
0x1801175d2  xor     ebx, ebx
0x1801175d4  mov     eax, ebx
0x1801175d6  mov     rcx, [rbp+1D0h+var_20]
0x1801175dd  xor     rcx, rsp; StackCookie
0x1801175e0  call    __security_check_cookie
0x1801175e5  mov     rbx, [rsp+2D0h+arg_10]
0x1801175ed  add     rsp, 2C0h
0x1801175f4  pop     rdi
0x1801175f5  pop     rsi
0x1801175f6  pop     rbp
0x1801175f7  retn
```
