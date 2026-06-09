# _AttributesFromSignatureInfo(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e3b70`
- end: `0x1800e3e2a`
- name: `?_AttributesFromSignatureInfo@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `698`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180005890`
- `0x180006938`
- `0x1800295dc`
- `0x1800e3b70`
- `0x1800e4360`
- `0x1800e4548`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e3de9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e3df7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e3de9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e3df7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3cad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3cad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e3d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3d1c`

## string_xrefs

- `0x1800e3c31`: `wintrust.dll`
- `0x1800e3c51`: `_LoadSystemModule failed for wintrust.dll`
- `0x1800e3c69`: `shlwapi.dll`
- `0x1800e3c42`: `_AttributesFromSignatureInfo`
- `0x1800e3c81`: `_LoadSystemModule failed for shlwapi.dll`

## pseudocode

```c
__int64 __fastcall _AttributesFromSignatureInfo(_QWORD **a1, __int64 a2)
{
  unsigned int v4; // ebx
  HMODULE SystemModule; // rax
  HMODULE v6; // rsi
  HMODULE v7; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  int v10; // eax
  FARPROC v11; // rax
  signed int LastError; // eax
  int v13; // eax
  char v14; // al
  _DWORD v16[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+4Ch] [rbp-B4h]
  wchar_t *v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+60h] [rbp-A0h]
  wchar_t *v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  wchar_t *v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+80h] [rbp-80h]
  wchar_t v24[264]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v25[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t v26[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(v16, 0, 0x58u);
  memset_0(v24, 0, 0x208u);
  memset_0(v25, 0, 0x208u);
  memset_0(v26, 0, 0x208u);
  if ( a2 )
  {
    v16[0] = 88;
    v19 = 260;
    v18 = v24;
    v20 = v25;
    v21 = 260;
    v23 = 260;
    v22 = v26;
    SystemModule = _LoadSystemModule(L"wintrust.dll");
    v6 = SystemModule;
    if ( SystemModule )
    {
      ProcAddress = GetProcAddress(SystemModule, "WTGetSignatureInfo");
      if ( ProcAddress )
      {
        v8 = 0;
        v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _DWORD *, _QWORD, _QWORD))ProcAddress)(
                **a1,
                -1,
                4099,
                v16,
                0,
                0);
        v4 = v10;
        if ( v10 < 0 )
        {
          AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1530, "WTGetSignatureInfo failed [%x]", v10);
          goto LABEL_26;
        }
        goto LABEL_17;
      }
    }
    else
    {
      AslLogCallPrintf(2, "_AttributesFromSignatureInfo", 1506, "_LoadSystemModule failed for wintrust.dll");
    }
    v7 = _LoadSystemModule(L"shlwapi.dll");
    v8 = v7;
    if ( !v7 )
    {
      v4 = -2147467259;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1544, "_LoadSystemModule failed for shlwapi.dll");
      goto LABEL_25;
    }
    v11 = GetProcAddress(v7, (LPCSTR)0x22F);
    if ( !v11 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1552, "Failed to get function SHGetSignatureInfo [%x]", v4);
      goto LABEL_24;
    }
    v13 = ((__int64 (__fastcall *)(_QWORD, __int64, _DWORD *))v11)(**a1, 4099, v16);
    v4 = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "_AttributesFromSignatureInfo", 1565, "SHGetSignatureInfo failed [%x]", v13);
      goto LABEL_24;
    }
LABEL_17:
    v14 = v17;
    if ( (v17 & 1) != 0 )
    {
      _SetFileAttributeValue(v24, 0x208u, 19, a2);
      v14 = v17;
    }
    if ( (v14 & 2) != 0 )
    {
      _SetFileAttributeValue(v25, 0x208u, 20, a2);
      v14 = v17;
    }
    if ( (v14 & 4) != 0 )
      _SetFileAttributeValue(v26, 0x208u, 21, a2);
    v4 = 0;
    if ( !v8 )
    {
LABEL_25:
      if ( !v6 )
        return v4;
LABEL_26:
      FreeLibrary(v6);
      return v4;
    }
LABEL_24:
    FreeLibrary(v8);
    goto LABEL_25;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800e3b70  mov     [rsp-8+arg_10], rbx
0x1800e3b75  mov     [rsp-8+arg_18], rsi
0x1800e3b7a  push    rbp
0x1800e3b7b  push    rdi
0x1800e3b7c  push    r12
0x1800e3b7e  push    r14
0x1800e3b80  push    r15
0x1800e3b82  lea     rbp, [rsp-5E0h]
0x1800e3b8a  sub     rsp, 6E0h
0x1800e3b91  mov     rax, cs:__security_cookie
0x1800e3b98  xor     rax, rsp
0x1800e3b9b  mov     [rbp+600h+var_30], rax
0x1800e3ba2  mov     r14, rdx
0x1800e3ba5  mov     rbx, rcx
0x1800e3ba8  mov     edi, 58h ; 'X'
0x1800e3bad  lea     rcx, [rsp+700h+var_6C0]; void *
0x1800e3bb2  mov     r8d, edi; Size
0x1800e3bb5  xor     edx, edx; Val
0x1800e3bb7  call    memset_0
0x1800e3bbc  mov     r12d, 208h
0x1800e3bc2  lea     rcx, [rbp+600h+var_660]; void *
0x1800e3bc6  mov     r8d, r12d; Size
0x1800e3bc9  xor     edx, edx; Val
0x1800e3bcb  call    memset_0
0x1800e3bd0  mov     r8d, r12d; Size
0x1800e3bd3  lea     rcx, [rbp+600h+var_450]; void *
0x1800e3bda  xor     edx, edx; Val
0x1800e3bdc  call    memset_0
0x1800e3be1  mov     r8d, r12d; Size
0x1800e3be4  lea     rcx, [rbp+600h+var_240]; void *
0x1800e3beb  xor     edx, edx; Val
0x1800e3bed  call    memset_0
0x1800e3bf2  test    r14, r14
0x1800e3bf5  jnz     short loc_1800E3C01
0x1800e3bf7  mov     ebx, 80070057h
0x1800e3bfc  jmp     loc_1800E3DFD
0x1800e3c01  mov     ecx, 104h
0x1800e3c06  mov     [rsp+700h+var_6C0], edi
0x1800e3c0a  lea     rax, [rbp+600h+var_660]
0x1800e3c0e  mov     [rsp+700h+var_6A0], ecx
0x1800e3c12  mov     [rsp+700h+var_6A8], rax
0x1800e3c17  lea     rax, [rbp+600h+var_450]
0x1800e3c1e  mov     [rsp+700h+var_698], rax
0x1800e3c23  lea     rax, [rbp+600h+var_240]
0x1800e3c2a  mov     [rsp+700h+var_690], ecx
0x1800e3c2e  mov     [rbp+600h+var_680], ecx
0x1800e3c31  lea     rcx, aWintrustDll; "wintrust.dll"
0x1800e3c38  mov     [rsp+700h+var_688], rax
0x1800e3c3d  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x1800e3c42  lea     r15, aAttributesfrom_2; "_AttributesFromSignatureInfo"
0x1800e3c49  mov     rsi, rax
0x1800e3c4c  test    rax, rax
0x1800e3c4f  jnz     short loc_1800E3CA3
0x1800e3c51  lea     r9, aLoadsystemmodu_0; "_LoadSystemModule failed for wintrust.d"...
0x1800e3c58  mov     r8d, 5E2h
0x1800e3c5e  mov     rdx, r15
0x1800e3c61  lea     ecx, [rax+2]
0x1800e3c64  call    AslLogCallPrintf
0x1800e3c69  lea     rcx, aShlwapiDll; "shlwapi.dll"
0x1800e3c70  call    ?_LoadSystemModule@@YAPEAUHINSTANCE__@@PEBG@Z; _LoadSystemModule(ushort const *)
0x1800e3c75  mov     rdi, rax
0x1800e3c78  test    rax, rax
0x1800e3c7b  jnz     loc_1800E3D09
0x1800e3c81  lea     r9, aLoadsystemmodu; "_LoadSystemModule failed for shlwapi.dl"...
0x1800e3c88  mov     r8d, 608h
0x1800e3c8e  mov     rdx, r15
0x1800e3c91  lea     ecx, [rax+1]
0x1800e3c94  mov     ebx, 80004005h
0x1800e3c99  call    AslLogCallPrintf
0x1800e3c9e  jmp     loc_1800E3DEF
0x1800e3ca3  lea     rdx, aWtgetsignature_0; "WTGetSignatureInfo"
0x1800e3caa  mov     rcx, rsi; hModule
0x1800e3cad  call    cs:__imp_GetProcAddress
0x1800e3cb3  test    rax, rax
0x1800e3cb6  jz      short loc_1800E3C69
0x1800e3cb8  mov     rcx, [rbx]
0x1800e3cbb  lea     r9, [rsp+700h+var_6C0]
0x1800e3cc0  xor     edi, edi
0x1800e3cc2  mov     r8d, 1003h
0x1800e3cc8  mov     [rsp+700h+var_6D8], rdi
0x1800e3ccd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e3cd1  mov     [rsp+700h+var_6E0], rdi
0x1800e3cd6  mov     rcx, [rcx]
0x1800e3cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3cde  mov     ebx, eax
0x1800e3ce0  test    eax, eax
0x1800e3ce2  jns     loc_1800E3D82
0x1800e3ce8  lea     r9, aWtgetsignature; "WTGetSignatureInfo failed [%x]"
0x1800e3cef  mov     dword ptr [rsp+700h+var_6E0], eax
0x1800e3cf3  mov     r8d, 5FAh
0x1800e3cf9  lea     ecx, [rdi+1]
0x1800e3cfc  mov     rdx, r15
0x1800e3cff  call    AslLogCallPrintf
0x1800e3d04  jmp     loc_1800E3DF4
0x1800e3d09  mov     edx, 22Fh; lpProcName
0x1800e3d0e  mov     rcx, rax; hModule
0x1800e3d11  call    cs:__imp_GetProcAddress
0x1800e3d17  test    rax, rax
0x1800e3d1a  jnz     short loc_1800E3D54
0x1800e3d1c  call    cs:__imp_GetLastError
0x1800e3d22  mov     ebx, eax
0x1800e3d24  test    eax, eax
0x1800e3d26  jle     short loc_1800E3D31
0x1800e3d28  movzx   ebx, ax
0x1800e3d2b  or      ebx, 80070000h
0x1800e3d31  mov     dword ptr [rsp+700h+var_6E0], ebx
0x1800e3d35  lea     r9, aFailedToGetFun; "Failed to get function SHGetSignatureIn"...
0x1800e3d3c  mov     r8d, 610h
0x1800e3d42  mov     rdx, r15
0x1800e3d45  mov     ecx, 1
0x1800e3d4a  call    AslLogCallPrintf
0x1800e3d4f  jmp     loc_1800E3DE6
0x1800e3d54  mov     rcx, [rbx]
0x1800e3d57  lea     r8, [rsp+700h+var_6C0]
0x1800e3d5c  mov     edx, 1003h
0x1800e3d61  mov     rcx, [rcx]
0x1800e3d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3d69  mov     ebx, eax
0x1800e3d6b  test    eax, eax
0x1800e3d6d  jns     short loc_1800E3D82
0x1800e3d6f  mov     dword ptr [rsp+700h+var_6E0], eax
0x1800e3d73  lea     r9, aShgetsignature; "SHGetSignatureInfo failed [%x]"
0x1800e3d7a  mov     r8d, 61Dh
0x1800e3d80  jmp     short loc_1800E3D42
0x1800e3d82  mov     eax, [rsp+700h+var_6B4]
0x1800e3d86  test    al, 1
0x1800e3d88  jz      short loc_1800E3DA3
0x1800e3d8a  mov     r9, r14
0x1800e3d8d  lea     rcx, [rbp+600h+var_660]
0x1800e3d91  mov     r8d, 13h
0x1800e3d97  mov     edx, r12d
0x1800e3d9a  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3d9f  mov     eax, [rsp+700h+var_6B4]
0x1800e3da3  test    al, 2
0x1800e3da5  jz      short loc_1800E3DC3
0x1800e3da7  mov     r9, r14
0x1800e3daa  lea     rcx, [rbp+600h+var_450]
0x1800e3db1  mov     r8d, 14h
0x1800e3db7  mov     edx, r12d
0x1800e3dba  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3dbf  mov     eax, [rsp+700h+var_6B4]
0x1800e3dc3  test    al, 4
0x1800e3dc5  jz      short loc_1800E3DDF
0x1800e3dc7  mov     r9, r14
0x1800e3dca  lea     rcx, [rbp+600h+var_240]
0x1800e3dd1  mov     r8d, 15h
0x1800e3dd7  mov     edx, r12d
0x1800e3dda  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3ddf  xor     ebx, ebx
0x1800e3de1  test    rdi, rdi
0x1800e3de4  jz      short loc_1800E3DEF
0x1800e3de6  mov     rcx, rdi; hLibModule
0x1800e3de9  call    cs:__imp_FreeLibrary
0x1800e3def  test    rsi, rsi
0x1800e3df2  jz      short loc_1800E3DFD
0x1800e3df4  mov     rcx, rsi; hLibModule
0x1800e3df7  call    cs:__imp_FreeLibrary
0x1800e3dfd  mov     eax, ebx
0x1800e3dff  mov     rcx, [rbp+600h+var_30]
0x1800e3e06  xor     rcx, rsp; StackCookie
0x1800e3e09  call    __security_check_cookie
0x1800e3e0e  lea     r11, [rsp+700h+var_20]
0x1800e3e16  mov     rbx, [r11+40h]
0x1800e3e1a  mov     rsi, [r11+48h]
0x1800e3e1e  mov     rsp, r11
0x1800e3e21  pop     r15
0x1800e3e23  pop     r14
0x1800e3e25  pop     r12
0x1800e3e27  pop     rdi
0x1800e3e28  pop     rbp
0x1800e3e29  retn
```
