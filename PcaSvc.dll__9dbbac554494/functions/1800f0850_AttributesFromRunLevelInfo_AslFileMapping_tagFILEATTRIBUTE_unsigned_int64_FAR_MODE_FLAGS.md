# _AttributesFromRunLevelInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800f0850`
- end: `0x1800f0aa8`
- name: `?_AttributesFromRunLevelInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `600`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180012920`
- `0x180027b74`
- `0x180056904`
- `0x1800f0850`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800f08fd`
- `msvcrt!_wcsicmp` at `0x1800f08fd`
- `msvcrt!_wsplitpath_s` at `0x1800f08e4`
- `msvcrt!_wsplitpath_s` at `0x1800f08e4`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800f0a04`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800f0a7c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800f0a04`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800f0a7c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800f09d0`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800f09d0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800f0933`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800f0933`

## string_xrefs

- `0x1800f0960`: `Failed to create activation context [%x]`
- `0x1800f0a22`: `RequireAdministrator`

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
  size_t DirCount; // [rsp+20h] [rbp-E0h]
  size_t DirCounta; // [rsp+20h] [rbp-E0h]
  BOOL v12; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pvBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v15; // [rsp+98h] [rbp-68h]
  wchar_t String1[264]; // [rsp+A0h] [rbp-60h] BYREF

  pvBuffer = 0;
  v15 = 0;
  String1[0] = 0;
  v3 = *a1;
  v12 = 0;
  memset(&pActCtx, 0, sizeof(pActCtx));
  v4 = *v3;
  if ( _wsplitpath_s(*v3, 0, 0, 0, 0, 0, 0, String1, 0x104u) || _wcsicmp(String1, L".EXE") )
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
      LODWORD(DirCounta) = GetLastError_0();
      AslLogCallPrintf(
        1,
        (unsigned int)"_AttributesFromRunLevelInfo",
        2043,
        (unsigned int)"Failed to query activation context [%x]",
        DirCounta);
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
          v12 = v15 != 0;
          _SetFileAttributeValue(&v12, 4, 33, a2);
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
  LODWORD(DirCount) = LastError_0;
  AslLogCallPrintf(
    1,
    (unsigned int)"_AttributesFromRunLevelInfo",
    2029,
    (unsigned int)"Failed to create activation context [%x]",
    DirCount);
  return v5;
}

```

## disassembly

```asm
0x1800f0850  mov     [rsp-8+arg_10], rbx
0x1800f0855  push    rbp
0x1800f0856  push    rsi
0x1800f0857  push    rdi
0x1800f0858  lea     rbp, [rsp-1C0h]
0x1800f0860  sub     rsp, 2C0h
0x1800f0867  mov     rax, cs:__security_cookie
0x1800f086e  xor     rax, rsp
0x1800f0871  mov     [rbp+1D0h+var_20], rax
0x1800f0878  xor     eax, eax
0x1800f087a  mov     [rsp+2D0h+ExtCount], 104h; ExtCount
0x1800f0883  mov     [rbp+1D0h+pActCtx.hModule], rax
0x1800f0887  xorps   xmm0, xmm0
0x1800f088a  mov     [rbp+1D0h+pvBuffer], rax
0x1800f088e  mov     rsi, rdx
0x1800f0891  mov     [rbp+1D0h+var_238], eax
0x1800f0894  xor     r9d, r9d; Dir
0x1800f0897  mov     [rbp+1D0h+String1], ax
0x1800f089b  xor     r8d, r8d; DriveCount
0x1800f089e  mov     rax, [rcx]
0x1800f08a1  xor     edx, edx; Drive
0x1800f08a3  mov     [rsp+2D0h+var_280], 0
0x1800f08ab  movups  xmmword ptr [rsp+2D0h+pActCtx.cbSize], xmm0
0x1800f08b0  movups  xmmword ptr [rsp+2D0h+pActCtx.wProcessorArchitecture], xmm0
0x1800f08b5  movups  xmmword ptr [rsp+2D0h+pActCtx.lpResourceName], xmm0
0x1800f08ba  mov     rdi, [rax]
0x1800f08bd  lea     rax, [rbp+1D0h+String1]
0x1800f08c1  mov     [rsp+2D0h+Ext], rax; Ext
0x1800f08c6  mov     rcx, rdi; FullPath
0x1800f08c9  mov     [rsp+2D0h+FilenameCount], 0; FilenameCount
0x1800f08d2  mov     [rsp+2D0h+Filename], 0; Filename
0x1800f08db  mov     [rsp+2D0h+DirCount], 0; DirCount
0x1800f08e4  call    cs:__imp__wsplitpath_s
0x1800f08ea  test    eax, eax
0x1800f08ec  jnz     loc_1800F0A82
0x1800f08f2  lea     rdx, aExe_0; ".EXE"
0x1800f08f9  lea     rcx, [rbp+1D0h+String1]; String1
0x1800f08fd  call    cs:__imp__wcsicmp
0x1800f0903  test    eax, eax
0x1800f0905  jnz     loc_1800F0A82
0x1800f090b  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x1800f0910  mov     [rsp+2D0h+pActCtx.cbSize], 38h ; '8'
0x1800f0918  mov     ebx, 80004005h
0x1800f091d  mov     [rsp+2D0h+pActCtx.dwFlags], 8
0x1800f0925  mov     [rsp+2D0h+pActCtx.lpSource], rdi
0x1800f092a  mov     [rsp+2D0h+pActCtx.lpResourceName], 1
0x1800f0933  call    cs:__imp_CreateActCtxW
0x1800f0939  mov     rdi, rax
0x1800f093c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f0940  jnz     short loc_1800F09A4
0x1800f0942  call    GetLastError_0
0x1800f0947  lea     edx, [rax-714h]
0x1800f094d  cmp     edx, 2
0x1800f0950  jbe     short loc_1800F0985
0x1800f0952  cmp     eax, 0C1h
0x1800f0957  jz      short loc_1800F0985
0x1800f0959  cmp     eax, 36B1h
0x1800f095e  jz      short loc_1800F0985
0x1800f0960  lea     r9, aFailedToCreate_19; "Failed to create activation context [%x"...
0x1800f0967  mov     dword ptr [rsp+2D0h+DirCount], eax
0x1800f096b  mov     r8d, 7EDh
0x1800f0971  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800f0978  lea     ecx, [rdi+2]
0x1800f097b  call    AslLogCallPrintf
0x1800f0980  jmp     loc_1800F0A84
0x1800f0985  mov     r9, rsi
0x1800f0988  lea     rcx, aUnspecified; "Unspecified"
0x1800f098f  mov     edx, 208h
0x1800f0994  mov     r8d, 20h ; ' '
0x1800f099a  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800f099f  jmp     loc_1800F0A82
0x1800f09a4  mov     [rsp+2D0h+FilenameCount], 0; pcbWrittenOrRequired
0x1800f09ad  lea     rax, [rbp+1D0h+pvBuffer]
0x1800f09b1  mov     [rsp+2D0h+Filename], 0Ch; cbBuffer
0x1800f09ba  mov     r9d, 5; ulInfoClass
0x1800f09c0  xor     r8d, r8d; pvSubInstance
0x1800f09c3  mov     [rsp+2D0h+DirCount], rax; pvBuffer
0x1800f09c8  mov     rdx, rdi; hActCtx
0x1800f09cb  mov     ecx, 80000000h; dwFlags
0x1800f09d0  call    cs:__imp_QueryActCtxW
0x1800f09d6  test    eax, eax
0x1800f09d8  jnz     short loc_1800F0A0C
0x1800f09da  call    GetLastError_0
0x1800f09df  lea     r9, aFailedToQueryA_0; "Failed to query activation context [%x]"
0x1800f09e6  mov     dword ptr [rsp+2D0h+DirCount], eax
0x1800f09ea  mov     r8d, 7FBh
0x1800f09f0  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800f09f7  mov     ecx, 1
0x1800f09fc  call    AslLogCallPrintf
0x1800f0a01  mov     rcx, rdi; hActCtx
0x1800f0a04  call    cs:__imp_ReleaseActCtx
0x1800f0a0a  jmp     short loc_1800F0A84
0x1800f0a0c  mov     ecx, dword ptr [rbp+1D0h+pvBuffer+4]
0x1800f0a0f  test    ecx, ecx
0x1800f0a11  jz      short loc_1800F0A3D
0x1800f0a13  sub     ecx, 1
0x1800f0a16  jz      short loc_1800F0A34
0x1800f0a18  sub     ecx, 1
0x1800f0a1b  jz      short loc_1800F0A2B
0x1800f0a1d  cmp     ecx, 1
0x1800f0a20  jnz     short loc_1800F0A3D
0x1800f0a22  lea     rcx, aRequireadminis; "RequireAdministrator"
0x1800f0a29  jmp     short loc_1800F0A44
0x1800f0a2b  lea     rcx, aHighestavailab; "HighestAvailable"
0x1800f0a32  jmp     short loc_1800F0A44
0x1800f0a34  lea     rcx, aAsinvoker; "AsInvoker"
0x1800f0a3b  jmp     short loc_1800F0A44
0x1800f0a3d  lea     rcx, aUnspecified; "Unspecified"
0x1800f0a44  mov     r9, rsi
0x1800f0a47  mov     edx, 208h
0x1800f0a4c  mov     r8d, 20h ; ' '
0x1800f0a52  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800f0a57  xor     eax, eax
0x1800f0a59  lea     rcx, [rsp+2D0h+var_280]
0x1800f0a5e  cmp     [rbp+1D0h+var_238], eax
0x1800f0a61  mov     edx, 4
0x1800f0a66  mov     r9, rsi
0x1800f0a69  setnz   al
0x1800f0a6c  mov     [rsp+2D0h+var_280], eax
0x1800f0a70  lea     r8d, [rdx+1Dh]
0x1800f0a74  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800f0a79  mov     rcx, rdi; hActCtx
0x1800f0a7c  call    cs:__imp_ReleaseActCtx
0x1800f0a82  xor     ebx, ebx
0x1800f0a84  mov     eax, ebx
0x1800f0a86  mov     rcx, [rbp+1D0h+var_20]
0x1800f0a8d  xor     rcx, rsp; StackCookie
0x1800f0a90  call    __security_check_cookie
0x1800f0a95  mov     rbx, [rsp+2D0h+arg_10]
0x1800f0a9d  add     rsp, 2C0h
0x1800f0aa4  pop     rdi
0x1800f0aa5  pop     rsi
0x1800f0aa6  pop     rbp
0x1800f0aa7  retn
```
