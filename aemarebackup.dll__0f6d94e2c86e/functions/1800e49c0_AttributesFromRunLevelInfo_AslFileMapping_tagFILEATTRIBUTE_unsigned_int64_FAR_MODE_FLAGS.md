# _AttributesFromRunLevelInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e49c0`
- end: `0x1800e4cf6`
- name: `?_AttributesFromRunLevelInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(const wchar_t ***, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180004ea0`
- `0x180005b90`
- `0x18004c020`
- `0x1800e49c0`
- `0x1800e5ec0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4a6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e4a6d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800e4a54`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800e4a54`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800e4b3c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800e4b3c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e4b6e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e4cc0`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e4b6e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800e4cc0`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800e4aa3`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800e4aa3`

## string_xrefs

- `0x1800e4ad0`: `Failed to create activation context [%x]`
- `0x1800e4b8f`: `RequireAdministrator`
- `0x1800e4c84`: `_SetFileAttributeValue`
- `0x1800e4c6f`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromRunLevelInfo(const wchar_t ***a1, _DWORD *a2)
{
  __int64 v3; // rsi
  const wchar_t **v4; // rax
  const WCHAR *v5; // r14
  unsigned int v6; // edi
  HANDLE v7; // r14
  DWORD v8; // eax
  DWORD LastError_0; // eax
  const wchar_t *v10; // rcx
  BOOL v11; // edx
  int v12; // r9d
  __int64 v13; // rax
  _WORD *v14; // rcx
  _WORD *v15; // rdx
  _WORD *v16; // rcx
  _DWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  ACTCTXW pActCtx; // [rsp+58h] [rbp-A8h] BYREF
  __int64 pvBuffer; // [rsp+90h] [rbp-70h] BYREF
  int v21; // [rsp+98h] [rbp-68h]
  wchar_t Ext[264]; // [rsp+A0h] [rbp-60h] BYREF

  pvBuffer = 0;
  v21 = 0;
  v3 = 260;
  v4 = *a1;
  v18[0] = 0;
  memset(&pActCtx, 0, sizeof(pActCtx));
  Ext[0] = 0;
  v5 = *v4;
  if ( _wsplitpath_s(*v4, 0, 0, 0, 0, 0, 0, Ext, 0x104u) || (unsigned int)_o__wcsicmp(Ext, L".EXE") )
    return 0;
  pActCtx.cbSize = 56;
  pActCtx.lpResourceName = (LPCWSTR)1;
  v6 = -2147467259;
  pActCtx.dwFlags = 8;
  pActCtx.lpSource = v5;
  v7 = CreateActCtxW(&pActCtx);
  if ( v7 != (HANDLE)-1LL )
  {
    if ( !QueryActCtxW(0x80000000, v7, 0, 5u, &pvBuffer, 0xCu, 0) )
    {
      LastError_0 = GetLastError_0();
      AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2043, "Failed to query activation context [%x]", LastError_0);
      ReleaseActCtx(v7);
      return v6;
    }
    if ( HIDWORD(pvBuffer) )
    {
      switch ( HIDWORD(pvBuffer) )
      {
        case 1:
          v10 = L"AsInvoker";
          goto LABEL_19;
        case 2:
          v10 = L"HighestAvailable";
          goto LABEL_19;
        case 3:
          v10 = L"RequireAdministrator";
          goto LABEL_19;
      }
    }
    v10 = L"Unspecified";
LABEL_19:
    _SetFileAttributeValue(v10, 520, 32, a2);
    v11 = v21 != 0;
    v18[0] = v11;
    if ( !a2 )
      goto LABEL_34;
    v12 = dword_180119ABC;
    if ( (unsigned int)dword_180119ABC > 2 )
    {
      if ( dword_180119ABC != 3 )
      {
        if ( dword_180119ABC == 4 )
        {
          v13 = 2;
          v14 = v18;
          v15 = a2 + 4488;
          do
          {
            if ( !v13 )
              break;
            if ( !*v14 )
              break;
            *v15++ = *v14++;
            --v13;
            --v3;
          }
          while ( v3 );
          v16 = v15 - 1;
          if ( v3 )
            v16 = v15;
          *v16 = 0;
          if ( !v3 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              33,
              -2147024774);
            goto LABEL_34;
          }
LABEL_33:
          a2[4618] = 33;
          a2[4619] = v12;
          a2[4620] = 1;
        }
LABEL_34:
        ReleaseActCtx(v7);
        return 0;
      }
      a2[4489] = v18[1];
    }
    a2[4488] = v11;
    goto LABEL_33;
  }
  v8 = GetLastError_0();
  if ( v8 - 1812 <= 2 || v8 == 14001 || v8 == 193 )
  {
    _SetFileAttributeValue(L"Unspecified", 520, 32, a2);
    return 0;
  }
  AslLogCallPrintf(1, "_AttributesFromRunLevelInfo", 2029, "Failed to create activation context [%x]", v8);
  return v6;
}

```

## disassembly

```asm
0x1800e49c0  mov     [rsp-8+arg_10], rbx
0x1800e49c5  mov     [rsp-8+arg_18], rsi
0x1800e49ca  push    rbp
0x1800e49cb  push    rdi
0x1800e49cc  push    r12
0x1800e49ce  push    r14
0x1800e49d0  push    r15
0x1800e49d2  lea     rbp, [rsp-1C0h]
0x1800e49da  sub     rsp, 2C0h
0x1800e49e1  mov     rax, cs:__security_cookie
0x1800e49e8  xor     rax, rsp
0x1800e49eb  mov     [rbp+1E0h+var_30], rax
0x1800e49f2  xor     eax, eax
0x1800e49f4  xor     r15d, r15d
0x1800e49f7  mov     [rbp+1E0h+pActCtx.hModule], rax
0x1800e49fb  xorps   xmm0, xmm0
0x1800e49fe  mov     [rbp+1E0h+pvBuffer], rax
0x1800e4a02  mov     rbx, rdx
0x1800e4a05  mov     [rbp+1E0h+var_248], eax
0x1800e4a08  mov     esi, 104h
0x1800e4a0d  mov     rax, [rcx]
0x1800e4a10  xor     r9d, r9d; Dir
0x1800e4a13  mov     [rsp+2E0h+ExtCount], rsi; ExtCount
0x1800e4a18  xor     r8d, r8d; DriveCount
0x1800e4a1b  mov     [rsp+2E0h+var_290], r15d
0x1800e4a20  xor     edx, edx; Drive
0x1800e4a22  movups  xmmword ptr [rsp+2E0h+pActCtx.cbSize], xmm0
0x1800e4a27  mov     [rbp+1E0h+var_240], r15w
0x1800e4a2c  movups  xmmword ptr [rsp+2E0h+pActCtx.wProcessorArchitecture], xmm0
0x1800e4a31  movups  xmmword ptr [rsp+2E0h+pActCtx.lpResourceName], xmm0
0x1800e4a36  mov     r14, [rax]
0x1800e4a39  lea     rax, [rbp+1E0h+var_240]
0x1800e4a3d  mov     [rsp+2E0h+Ext], rax; Ext
0x1800e4a42  mov     rcx, r14; FullPath
0x1800e4a45  mov     [rsp+2E0h+FilenameCount], r15; FilenameCount
0x1800e4a4a  mov     [rsp+2E0h+Filename], r15; Filename
0x1800e4a4f  mov     [rsp+2E0h+DirCount], r15; DirCount
0x1800e4a54  call    cs:__imp__wsplitpath_s
0x1800e4a5a  test    eax, eax
0x1800e4a5c  jnz     loc_1800E4CC6
0x1800e4a62  lea     rdx, aExe_0; ".EXE"
0x1800e4a69  lea     rcx, [rbp+1E0h+var_240]
0x1800e4a6d  call    cs:__imp__o__wcsicmp
0x1800e4a73  test    eax, eax
0x1800e4a75  jnz     loc_1800E4CC6
0x1800e4a7b  lea     r12d, [r15+1]
0x1800e4a7f  mov     [rsp+2E0h+pActCtx.cbSize], 38h ; '8'
0x1800e4a87  lea     rcx, [rsp+2E0h+pActCtx]; pActCtx
0x1800e4a8c  mov     [rsp+2E0h+pActCtx.lpResourceName], r12
0x1800e4a91  mov     edi, 80004005h
0x1800e4a96  mov     [rsp+2E0h+pActCtx.dwFlags], 8
0x1800e4a9e  mov     [rsp+2E0h+pActCtx.lpSource], r14
0x1800e4aa3  call    cs:__imp_CreateActCtxW
0x1800e4aa9  mov     r14, rax
0x1800e4aac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e4ab0  jnz     short loc_1800E4B14
0x1800e4ab2  call    GetLastError_0
0x1800e4ab7  lea     edx, [rax-714h]
0x1800e4abd  cmp     edx, 2
0x1800e4ac0  jbe     short loc_1800E4AF5
0x1800e4ac2  cmp     eax, 36B1h
0x1800e4ac7  jz      short loc_1800E4AF5
0x1800e4ac9  cmp     eax, 0C1h
0x1800e4ace  jz      short loc_1800E4AF5
0x1800e4ad0  lea     r9, aFailedToCreate; "Failed to create activation context [%x"...
0x1800e4ad7  mov     dword ptr [rsp+2E0h+DirCount], eax
0x1800e4adb  mov     r8d, 7EDh
0x1800e4ae1  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800e4ae8  mov     ecx, r12d
0x1800e4aeb  call    AslLogCallPrintf
0x1800e4af0  jmp     loc_1800E4CC9
0x1800e4af5  mov     r9, rbx
0x1800e4af8  lea     rcx, aUnspecified; "Unspecified"
0x1800e4aff  mov     edx, 208h
0x1800e4b04  mov     r8d, 20h ; ' '
0x1800e4b0a  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e4b0f  jmp     loc_1800E4CC6
0x1800e4b14  mov     [rsp+2E0h+FilenameCount], r15; pcbWrittenOrRequired
0x1800e4b19  lea     rax, [rbp+1E0h+pvBuffer]
0x1800e4b1d  mov     [rsp+2E0h+Filename], 0Ch; cbBuffer
0x1800e4b26  mov     r9d, 5; ulInfoClass
0x1800e4b2c  xor     r8d, r8d; pvSubInstance
0x1800e4b2f  mov     [rsp+2E0h+DirCount], rax; pvBuffer
0x1800e4b34  mov     rdx, r14; hActCtx
0x1800e4b37  mov     ecx, 80000000h; dwFlags
0x1800e4b3c  call    cs:__imp_QueryActCtxW
0x1800e4b42  test    eax, eax
0x1800e4b44  jnz     short loc_1800E4B79
0x1800e4b46  call    GetLastError_0
0x1800e4b4b  lea     r9, aFailedToQueryA; "Failed to query activation context [%x]"
0x1800e4b52  mov     dword ptr [rsp+2E0h+DirCount], eax
0x1800e4b56  mov     r8d, 7FBh
0x1800e4b5c  lea     rdx, aAttributesfrom_4; "_AttributesFromRunLevelInfo"
0x1800e4b63  mov     ecx, r12d
0x1800e4b66  call    AslLogCallPrintf
0x1800e4b6b  mov     rcx, r14; hActCtx
0x1800e4b6e  call    cs:__imp_ReleaseActCtx
0x1800e4b74  jmp     loc_1800E4CC9
0x1800e4b79  mov     ecx, dword ptr [rbp+1E0h+pvBuffer+4]
0x1800e4b7c  test    ecx, ecx
0x1800e4b7e  jz      short loc_1800E4BAA
0x1800e4b80  sub     ecx, r12d
0x1800e4b83  jz      short loc_1800E4BA1
0x1800e4b85  sub     ecx, r12d
0x1800e4b88  jz      short loc_1800E4B98
0x1800e4b8a  cmp     ecx, r12d
0x1800e4b8d  jnz     short loc_1800E4BAA
0x1800e4b8f  lea     rcx, aRequireadminis; "RequireAdministrator"
0x1800e4b96  jmp     short loc_1800E4BB1
0x1800e4b98  lea     rcx, aHighestavailab; "HighestAvailable"
0x1800e4b9f  jmp     short loc_1800E4BB1
0x1800e4ba1  lea     rcx, aAsinvoker; "AsInvoker"
0x1800e4ba8  jmp     short loc_1800E4BB1
0x1800e4baa  lea     rcx, aUnspecified; "Unspecified"
0x1800e4bb1  mov     r9, rbx
0x1800e4bb4  mov     edx, 208h
0x1800e4bb9  mov     r8d, 20h ; ' '
0x1800e4bbf  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e4bc4  cmp     [rbp+1E0h+var_248], r15d
0x1800e4bc8  mov     edx, r15d
0x1800e4bcb  setnz   dl
0x1800e4bce  mov     [rsp+2E0h+var_290], edx
0x1800e4bd2  test    rbx, rbx
0x1800e4bd5  jz      loc_1800E4CBD
0x1800e4bdb  mov     r9d, cs:dword_180119ABC
0x1800e4be2  mov     ecx, r9d
0x1800e4be5  test    r9d, r9d
0x1800e4be8  jz      loc_1800E4C9F
0x1800e4bee  sub     ecx, r12d
0x1800e4bf1  jz      loc_1800E4C9F
0x1800e4bf7  sub     ecx, r12d
0x1800e4bfa  jz      loc_1800E4C9F
0x1800e4c00  sub     ecx, r12d
0x1800e4c03  jz      loc_1800E4C95
0x1800e4c09  cmp     ecx, r12d
0x1800e4c0c  jnz     loc_1800E4CBD
0x1800e4c12  mov     eax, 2
0x1800e4c17  lea     rcx, [rsp+2E0h+var_290]
0x1800e4c1c  lea     rdx, [rbx+4620h]
0x1800e4c23  test    rax, rax
0x1800e4c26  jz      short loc_1800E4C46
0x1800e4c28  movzx   r8d, word ptr [rcx]
0x1800e4c2c  test    r8w, r8w
0x1800e4c30  jz      short loc_1800E4C46
0x1800e4c32  mov     [rdx], r8w
0x1800e4c36  add     rcx, 2
0x1800e4c3a  add     rdx, 2
0x1800e4c3e  sub     rax, r12
0x1800e4c41  sub     rsi, r12
0x1800e4c44  jnz     short loc_1800E4C23
0x1800e4c46  mov     rax, rsi
0x1800e4c49  lea     rcx, [rdx-2]
0x1800e4c4d  neg     rax
0x1800e4c50  sbb     r8d, r8d
0x1800e4c53  not     r8d
0x1800e4c56  and     r8d, 8007007Ah
0x1800e4c5d  test    rsi, rsi
0x1800e4c60  cmovnz  rcx, rdx
0x1800e4c64  mov     [rcx], r15w
0x1800e4c68  jnz     short loc_1800E4CA5
0x1800e4c6a  mov     dword ptr [rsp+2E0h+Filename], r8d
0x1800e4c6f  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800e4c76  mov     r8d, 0C6Ah
0x1800e4c7c  mov     dword ptr [rsp+2E0h+DirCount], 21h ; '!'
0x1800e4c84  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800e4c8b  mov     ecx, r12d
0x1800e4c8e  call    AslLogCallPrintf
0x1800e4c93  jmp     short loc_1800E4CBD
0x1800e4c95  mov     eax, [rsp+2E0h+var_28C]
0x1800e4c99  mov     [rbx+4624h], eax
0x1800e4c9f  mov     [rbx+4620h], edx
0x1800e4ca5  mov     dword ptr [rbx+4828h], 21h ; '!'
0x1800e4caf  mov     [rbx+482Ch], r9d
0x1800e4cb6  mov     [rbx+4830h], r12d
0x1800e4cbd  mov     rcx, r14; hActCtx
0x1800e4cc0  call    cs:__imp_ReleaseActCtx
0x1800e4cc6  mov     edi, r15d
0x1800e4cc9  mov     eax, edi
0x1800e4ccb  mov     rcx, [rbp+1E0h+var_30]
0x1800e4cd2  xor     rcx, rsp; StackCookie
0x1800e4cd5  call    __security_check_cookie
0x1800e4cda  lea     r11, [rsp+2E0h+var_20]
0x1800e4ce2  mov     rbx, [r11+40h]
0x1800e4ce6  mov     rsi, [r11+48h]
0x1800e4cea  mov     rsp, r11
0x1800e4ced  pop     r15
0x1800e4cef  pop     r14
0x1800e4cf1  pop     r12
0x1800e4cf3  pop     rdi
0x1800e4cf4  pop     rbp
0x1800e4cf5  retn
```
