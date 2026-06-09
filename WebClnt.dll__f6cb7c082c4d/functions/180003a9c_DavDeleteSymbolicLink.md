# DavDeleteSymbolicLink

- ea: `0x180003a9c`
- end: `0x180003cb4`
- name: `DavDeleteSymbolicLink`
- size: `536`
- prototype: `__int64 __fastcall(__int64 hMem, LPCWSTR lpTargetPath, WCHAR *lpDeviceName, HANDLE Token, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180003cbc`
- `0x180003f8c`
- `0x180006d20`

## callees

- `0x180003a9c`
- `0x18000591c`
- `0x18000656c`
- `0x180006618`
- `0x18000b7dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c36`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180003bdd`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x180003bdd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003b57`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180003b57`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003c2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180003c2c`
- `KERNEL32!LocalFree` at `0x180003c9d`
- `KERNEL32!LocalFree` at `0x180003c9d`

## pseudocode

```c
__int64 __fastcall DavDeleteSymbolicLink(__int64 hMem, LPCWSTR lpTargetPath, WCHAR *lpDeviceName, HANDLE Token, int a5)
{
  unsigned int v5; // ebx
  WCHAR *v7; // rsi
  int v9; // edi
  char v10; // r12
  int v11; // r14d
  DWORD LastError; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  void *v16; // rcx
  __int64 v17; // r8
  DWORD v18; // eax

  v5 = 0;
  v7 = lpDeviceName;
  v9 = lpTargetPath != 0 ? 5 : 0;
  if ( !hMem && !lpDeviceName )
    return v5;
  v10 = 0;
  v11 = 0;
  if ( g_LUIDDeviceMapsEnabled )
  {
    v7 = (WCHAR *)hMem;
    if ( a5 )
      goto LABEL_22;
    if ( Token == (HANDLE)-1LL )
    {
      LastError = DavImpersonateClient(hMem, lpTargetPath, lpDeviceName);
      v5 = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_38;
        v14 = 225;
LABEL_37:
        WPP_SF_d(v13[2], v14, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        goto LABEL_38;
      }
    }
    else if ( !SetThreadToken(0, Token) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_38;
        v14 = 224;
        goto LABEL_37;
      }
    }
    v11 = 1;
    goto LABEL_22;
  }
  if ( !lpDeviceName )
  {
    v7 = (WCHAR *)DavReturnSessionPath(hMem);
    if ( !v7 )
    {
      v5 = 87;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, 87);
      return v5;
    }
    v10 = 1;
  }
LABEL_22:
  if ( !DefineDosDeviceW(v9 + 10, v7, lpTargetPath) )
  {
    v18 = GetLastError();
    v5 = v18;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v18);
  }
  if ( v11 != 1 )
    goto LABEL_38;
  if ( Token == (HANDLE)-1LL )
  {
    LastError = DavRevertToSelf(v16, v15, v17);
    v5 = LastError;
    if ( LastError )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 228;
        goto LABEL_37;
      }
    }
  }
  else if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 227;
        goto LABEL_37;
      }
    }
  }
LABEL_38:
  if ( v7 && v10 )
    LocalFree(v7);
  return v5;
}

```

## disassembly

```asm
0x180003a9c  push    rbx
0x180003a9e  push    rbp
0x180003a9f  push    rsi
0x180003aa0  push    rdi
0x180003aa1  push    r12
0x180003aa3  push    r14
0x180003aa5  push    r15
0x180003aa7  sub     rsp, 20h
0x180003aab  xor     ebx, ebx
0x180003aad  mov     rax, rdx
0x180003ab0  neg     rax
0x180003ab3  mov     rbp, r9
0x180003ab6  mov     rsi, r8
0x180003ab9  mov     r15, rdx
0x180003abc  sbb     edi, edi
0x180003abe  and     edi, 5
0x180003ac1  test    rcx, rcx
0x180003ac4  jnz     short loc_180003ACF
0x180003ac6  test    r8, r8
0x180003ac9  jz      loc_180003CA3
0x180003acf  xor     r12b, r12b
0x180003ad2  xor     r14d, r14d
0x180003ad5  cmp     cs:g_LUIDDeviceMapsEnabled, ebx
0x180003adb  jnz     short loc_180003B3C
0x180003add  test    r8, r8
0x180003ae0  jnz     loc_180003BD4
0x180003ae6  call    DavReturnSessionPath
0x180003aeb  mov     rsi, rax
0x180003aee  test    rax, rax
0x180003af1  jnz     short loc_180003B34
0x180003af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003afa  lea     rdi, WPP_GLOBAL_Control
0x180003b01  lea     ebx, [rax+57h]
0x180003b04  cmp     rcx, rdi
0x180003b07  jz      loc_180003CA3
0x180003b0d  test    byte ptr [rcx+1Ch], 1
0x180003b11  jz      loc_180003CA3
0x180003b17  mov     rcx, [rcx+10h]
0x180003b1b  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003b22  mov     edx, 0DFh
0x180003b27  mov     r9d, ebx
0x180003b2a  call    WPP_SF_d
0x180003b2f  jmp     loc_180003CA3
0x180003b34  mov     r12b, 1
0x180003b37  jmp     loc_180003BD4
0x180003b3c  mov     rsi, rcx
0x180003b3f  cmp     [rsp+58h+arg_20], ebx
0x180003b46  jnz     loc_180003BD4
0x180003b4c  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180003b50  jz      short loc_180003B98
0x180003b52  mov     rdx, rbp; Token
0x180003b55  xor     ecx, ecx; Thread
0x180003b57  call    cs:__imp_SetThreadToken
0x180003b5d  test    eax, eax
0x180003b5f  jnz     short loc_180003BCE
0x180003b61  call    cs:__imp_GetLastError
0x180003b67  mov     ebx, eax
0x180003b69  test    eax, eax
0x180003b6b  jz      short loc_180003BCE
0x180003b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b74  lea     rdi, WPP_GLOBAL_Control
0x180003b7b  cmp     rcx, rdi
0x180003b7e  jz      loc_180003C90
0x180003b84  test    byte ptr [rcx+1Ch], 1
0x180003b88  jz      loc_180003C90
0x180003b8e  mov     edx, 0E0h
0x180003b93  jmp     loc_180003C7D
0x180003b98  call    DavImpersonateClient
0x180003b9d  mov     ebx, eax
0x180003b9f  test    eax, eax
0x180003ba1  jz      short loc_180003BCE
0x180003ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003baa  lea     rdi, WPP_GLOBAL_Control
0x180003bb1  cmp     rcx, rdi
0x180003bb4  jz      loc_180003C90
0x180003bba  test    byte ptr [rcx+1Ch], 1
0x180003bbe  jz      loc_180003C90
0x180003bc4  mov     edx, 0E1h
0x180003bc9  jmp     loc_180003C7D
0x180003bce  mov     r14d, 1
0x180003bd4  mov     r8, r15; lpTargetPath
0x180003bd7  lea     ecx, [rdi+0Ah]; dwFlags
0x180003bda  mov     rdx, rsi; lpDeviceName
0x180003bdd  call    cs:__imp_DefineDosDeviceW
0x180003be3  lea     rdi, WPP_GLOBAL_Control
0x180003bea  test    eax, eax
0x180003bec  jnz     short loc_180003C20
0x180003bee  call    cs:__imp_GetLastError
0x180003bf4  mov     ebx, eax
0x180003bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bfd  cmp     rcx, rdi
0x180003c00  jz      short loc_180003C20
0x180003c02  test    byte ptr [rcx+1Ch], 1
0x180003c06  jz      short loc_180003C20
0x180003c08  mov     rcx, [rcx+10h]
0x180003c0c  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003c13  mov     edx, 0E2h
0x180003c18  mov     r9d, eax
0x180003c1b  call    WPP_SF_d
0x180003c20  cmp     r14d, 1
0x180003c24  jnz     short loc_180003C90
0x180003c26  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180003c2a  jz      short loc_180003C5B
0x180003c2c  call    cs:__imp_RevertToSelf
0x180003c32  test    eax, eax
0x180003c34  jnz     short loc_180003C90
0x180003c36  call    cs:__imp_GetLastError
0x180003c3c  mov     ebx, eax
0x180003c3e  test    eax, eax
0x180003c40  jz      short loc_180003C90
0x180003c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c49  cmp     rcx, rdi
0x180003c4c  jz      short loc_180003C90
0x180003c4e  test    [rcx+1Ch], r14b
0x180003c52  jz      short loc_180003C90
0x180003c54  mov     edx, 0E3h
0x180003c59  jmp     short loc_180003C7D
0x180003c5b  call    DavRevertToSelf
0x180003c60  mov     ebx, eax
0x180003c62  test    eax, eax
0x180003c64  jz      short loc_180003C90
0x180003c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c6d  cmp     rcx, rdi
0x180003c70  jz      short loc_180003C90
0x180003c72  test    byte ptr [rcx+1Ch], 1
0x180003c76  jz      short loc_180003C90
0x180003c78  mov     edx, 0E4h
0x180003c7d  mov     rcx, [rcx+10h]
0x180003c81  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180003c88  mov     r9d, eax
0x180003c8b  call    WPP_SF_d
0x180003c90  test    rsi, rsi
0x180003c93  jz      short loc_180003CA3
0x180003c95  test    r12b, r12b
0x180003c98  jz      short loc_180003CA3
0x180003c9a  mov     rcx, rsi; hMem
0x180003c9d  call    cs:__imp_LocalFree
0x180003ca3  mov     eax, ebx
0x180003ca5  add     rsp, 20h
0x180003ca9  pop     r15
0x180003cab  pop     r14
0x180003cad  pop     r12
0x180003caf  pop     rdi
0x180003cb0  pop     rsi
0x180003cb1  pop     rbp
0x180003cb2  pop     rbx
0x180003cb3  retn
```
