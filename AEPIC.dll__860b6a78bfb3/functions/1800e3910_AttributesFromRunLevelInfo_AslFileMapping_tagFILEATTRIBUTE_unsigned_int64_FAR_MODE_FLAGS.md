# _AttributesFromRunLevelInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e3910`
- end: `0x1800e3b6a`
- name: `?_AttributesFromRunLevelInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `602`
- prototype: `__int64 __fastcall(const wchar_t ***, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180005890`
- `0x1800295dc`
- `0x1800e3910`
- `0x1800e4548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e39bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e39bd`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800e39a4`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800e39a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3a9b`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800e39f3`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800e39f3`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800e3a91`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800e3a91`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e3ac6`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e3b3e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e3ac6`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e3b3e`

## string_xrefs

- `0x1800e3a21`: `Failed to create activation context [%x]`
- `0x1800e3ae4`: `RequireAdministrator`

## pseudocode

```c
__int64 __fastcall _AttributesFromRunLevelInfo(const wchar_t ***a1, __int64 a2)
{
  const wchar_t **v3; // rax
  const WCHAR *v4; // rdi
  unsigned int v5; // ebx
  HANDLE v6; // rdi
  DWORD v7; // eax
  DWORD LastError; // eax
  const wchar_t *v9; // rcx
  BOOL v11; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pvBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v14; // [rsp+98h] [rbp-68h]
  wchar_t Ext[264]; // [rsp+A0h] [rbp-60h] BYREF

  pvBuffer = 0;
  v14 = 0;
  Ext[0] = 0;
  v3 = *a1;
  v11 = 0;
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
      LastError = GetLastError();
      AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2043, "Failed to query activation context [%x]", LastError);
      ReleaseActCtx(v6);
      return v5;
    }
    if ( HIDWORD(pvBuffer) )
    {
      switch ( HIDWORD(pvBuffer) )
      {
        case 1:
          v9 = L"AsInvoker";
          goto LABEL_19;
        case 2:
          v9 = L"HighestAvailable";
          goto LABEL_19;
        case 3:
          v9 = L"RequireAdministrator";
LABEL_19:
          _SetFileAttributeValue(v9, 0x208u, 32, a2);
          v11 = v14 != 0;
          _SetFileAttributeValue((const wchar_t *)&v11, 4u, 33, a2);
          ReleaseActCtx(v6);
          return 0;
      }
    }
    v9 = L"Unspecified";
    goto LABEL_19;
  }
  v7 = GetLastError();
  if ( v7 - 1812 <= 2 || v7 == 193 || v7 == 14001 )
  {
    _SetFileAttributeValue(L"Unspecified", 0x208u, 32, a2);
    return 0;
  }
  AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2029, "Failed to create activation context [%x]", v7);
  return v5;
}

```

## disassembly

```asm
0x1800e3910  mov     [rsp-8+arg_10], rbx
0x1800e3915  push    rbp
0x1800e3916  push    rsi
0x1800e3917  push    rdi
0x1800e3918  lea     rbp, [rsp-1C0h]
0x1800e3920  sub     rsp, 2C0h
0x1800e3927  mov     rax, cs:__security_cookie
0x1800e392e  xor     rax, rsp
0x1800e3931  mov     [rbp+1D0h+var_20], rax
0x1800e3938  xor     eax, eax
0x1800e393a  mov     [rsp+2D0h+ExtCount], 104h; ExtCount
0x1800e3943  mov     [rbp+1D0h+pActCtx.hModule], rax
0x1800e3947  xorps   xmm0, xmm0
0x1800e394a  mov     [rbp+1D0h+pvBuffer], rax
0x1800e394e  mov     rsi, rdx
0x1800e3951  mov     [rbp+1D0h+var_238], eax
0x1800e3954  xor     r9d, r9d; Dir
0x1800e3957  mov     [rbp+1D0h+var_230], ax
0x1800e395b  xor     r8d, r8d; DriveCount
0x1800e395e  mov     rax, [rcx]
0x1800e3961  xor     edx, edx; Drive
0x1800e3963  mov     [rsp+2D0h+var_280], 0
0x1800e396b  movups  xmmword ptr [rsp+2D0h+pActCtx.cbSize], xmm0
0x1800e3970  movups  xmmword ptr [rsp+2D0h+pActCtx.wProcessorArchitecture], xmm0
0x1800e3975  movups  xmmword ptr [rsp+2D0h+pActCtx.lpResourceName], xmm0
0x1800e397a  mov     rdi, [rax]
0x1800e397d  lea     rax, [rbp+1D0h+var_230]
0x1800e3981  mov     [rsp+2D0h+Ext], rax; Ext
0x1800e3986  mov     rcx, rdi; FullPath
0x1800e3989  mov     [rsp+2D0h+FilenameCount], 0; FilenameCount
0x1800e3992  mov     [rsp+2D0h+Filename], 0; Filename
0x1800e399b  mov     [rsp+2D0h+DirCount], 0; DirCount
0x1800e39a4  call    cs:__imp__wsplitpath_s
0x1800e39aa  test    eax, eax
0x1800e39ac  jnz     loc_1800E3B44
0x1800e39b2  lea     rdx, aExe_0; ".EXE"
0x1800e39b9  lea     rcx, [rbp+1D0h+var_230]
0x1800e39bd  call    cs:__imp__o__wcsicmp
0x1800e39c3  test    eax, eax
0x1800e39c5  jnz     loc_1800E3B44
0x1800e39cb  lea     rcx, [rsp+2D0h+pActCtx]; pActCtx
0x1800e39d0  mov     [rsp+2D0h+pActCtx.cbSize], 38h ; '8'
0x1800e39d8  mov     ebx, 80004005h
0x1800e39dd  mov     [rsp+2D0h+pActCtx.dwFlags], 8
0x1800e39e5  mov     [rsp+2D0h+pActCtx.lpSource], rdi
0x1800e39ea  mov     [rsp+2D0h+pActCtx.lpResourceName], 1
0x1800e39f3  call    cs:__imp_CreateActCtxW
0x1800e39f9  mov     rdi, rax
0x1800e39fc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e3a00  jnz     short loc_1800E3A65
0x1800e3a02  call    cs:__imp_GetLastError
0x1800e3a08  lea     edx, [rax-714h]
0x1800e3a0e  cmp     edx, 2
0x1800e3a11  jbe     short loc_1800E3A46
0x1800e3a13  cmp     eax, 0C1h
0x1800e3a18  jz      short loc_1800E3A46
0x1800e3a1a  cmp     eax, 36B1h
0x1800e3a1f  jz      short loc_1800E3A46
0x1800e3a21  lea     r9, aFailedToCreate_0; "Failed to create activation context [%x"...
0x1800e3a28  mov     dword ptr [rsp+2D0h+DirCount], eax
0x1800e3a2c  mov     r8d, 7EDh
0x1800e3a32  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800e3a39  lea     ecx, [rdi+2]
0x1800e3a3c  call    AslLogCallPrintf
0x1800e3a41  jmp     loc_1800E3B46
0x1800e3a46  mov     r9, rsi
0x1800e3a49  lea     rcx, aUnspecified; "Unspecified"
0x1800e3a50  mov     edx, 208h
0x1800e3a55  mov     r8d, 20h ; ' '
0x1800e3a5b  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3a60  jmp     loc_1800E3B44
0x1800e3a65  mov     [rsp+2D0h+FilenameCount], 0; pcbWrittenOrRequired
0x1800e3a6e  lea     rax, [rbp+1D0h+pvBuffer]
0x1800e3a72  mov     [rsp+2D0h+Filename], 0Ch; cbBuffer
0x1800e3a7b  mov     r9d, 5; ulInfoClass
0x1800e3a81  xor     r8d, r8d; pvSubInstance
0x1800e3a84  mov     [rsp+2D0h+DirCount], rax; pvBuffer
0x1800e3a89  mov     rdx, rdi; hActCtx
0x1800e3a8c  mov     ecx, 80000000h; dwFlags
0x1800e3a91  call    cs:__imp_QueryActCtxW
0x1800e3a97  test    eax, eax
0x1800e3a99  jnz     short loc_1800E3ACE
0x1800e3a9b  call    cs:__imp_GetLastError
0x1800e3aa1  lea     r9, aFailedToQueryA; "Failed to query activation context [%x]"
0x1800e3aa8  mov     r8d, 7FBh
0x1800e3aae  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800e3ab5  mov     dword ptr [rsp+2D0h+DirCount], eax
0x1800e3ab9  mov     ecx, 1
0x1800e3abe  call    AslLogCallPrintf
0x1800e3ac3  mov     rcx, rdi; hActCtx
0x1800e3ac6  call    cs:__imp_ReleaseActCtx
0x1800e3acc  jmp     short loc_1800E3B46
0x1800e3ace  mov     ecx, dword ptr [rbp+1D0h+pvBuffer+4]
0x1800e3ad1  test    ecx, ecx
0x1800e3ad3  jz      short loc_1800E3AFF
0x1800e3ad5  sub     ecx, 1
0x1800e3ad8  jz      short loc_1800E3AF6
0x1800e3ada  sub     ecx, 1
0x1800e3add  jz      short loc_1800E3AED
0x1800e3adf  cmp     ecx, 1
0x1800e3ae2  jnz     short loc_1800E3AFF
0x1800e3ae4  lea     rcx, aRequireadminis; "RequireAdministrator"
0x1800e3aeb  jmp     short loc_1800E3B06
0x1800e3aed  lea     rcx, aHighestavailab; "HighestAvailable"
0x1800e3af4  jmp     short loc_1800E3B06
0x1800e3af6  lea     rcx, aAsinvoker; "AsInvoker"
0x1800e3afd  jmp     short loc_1800E3B06
0x1800e3aff  lea     rcx, aUnspecified; "Unspecified"
0x1800e3b06  mov     r9, rsi
0x1800e3b09  mov     edx, 208h
0x1800e3b0e  mov     r8d, 20h ; ' '
0x1800e3b14  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3b19  xor     eax, eax
0x1800e3b1b  lea     rcx, [rsp+2D0h+var_280]
0x1800e3b20  cmp     [rbp+1D0h+var_238], eax
0x1800e3b23  mov     edx, 4
0x1800e3b28  mov     r9, rsi
0x1800e3b2b  setnz   al
0x1800e3b2e  mov     [rsp+2D0h+var_280], eax
0x1800e3b32  lea     r8d, [rdx+1Dh]
0x1800e3b36  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3b3b  mov     rcx, rdi; hActCtx
0x1800e3b3e  call    cs:__imp_ReleaseActCtx
0x1800e3b44  xor     ebx, ebx
0x1800e3b46  mov     eax, ebx
0x1800e3b48  mov     rcx, [rbp+1D0h+var_20]
0x1800e3b4f  xor     rcx, rsp; StackCookie
0x1800e3b52  call    __security_check_cookie
0x1800e3b57  mov     rbx, [rsp+2D0h+arg_10]
0x1800e3b5f  add     rsp, 2C0h
0x1800e3b66  pop     rdi
0x1800e3b67  pop     rsi
0x1800e3b68  pop     rbp
0x1800e3b69  retn
```
