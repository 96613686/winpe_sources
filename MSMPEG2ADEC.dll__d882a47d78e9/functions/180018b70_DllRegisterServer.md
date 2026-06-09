# DllRegisterServer

- ea: `0x180018b70`
- end: `0x180018dc0`
- name: `DllRegisterServer`
- size: `592`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800013a0`
- `0x1800013ac`
- `0x180010c10`
- `0x180010cf0`
- `0x180017ba0`
- `0x180018b70`
- `0x180025658`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018bfa`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018bfa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018d47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018d47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018d5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018c90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018cf5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018c90`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018cf5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018c41`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018c41`

## string_xrefs

- `0x180018d25`: `PreferredMPEG2AudioDecoderCLSID`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  unsigned __int16 *v1; // rsi
  OLECHAR *v2; // rax
  BYTE *v3; // rdi
  HRESULT v4; // ebx
  LSTATUS v5; // ebx
  LSTATUS v6; // ebx
  LSTATUS v7; // ebx
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  HKEY v9; // [rsp+78h] [rbp+10h] BYREF

  if ( !(unsigned int)IsLicensedComponentDOLBY_Internal() && !(unsigned int)IsLicensedComponentAAC_Internal() )
    return -2147467259;
  AMovieDllRegisterServer2(1);
  v1 = (unsigned __int16 *)operator new[](0x208u);
  v2 = (OLECHAR *)operator new[](0x4Eu);
  v3 = (BYTE *)v2;
  hKey = 0;
  v9 = 0;
  if ( v1 && v2 )
  {
    v4 = StringFromGUID2(&CLSID_CMPEG2AudDecoderDS, v2, 39);
    if ( v4 >= 0 )
    {
      StringCchPrintfW(v1, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion");
      v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 4u, &hKey);
      if ( v5 )
      {
        v4 = v5 | 0x80070000;
      }
      else
      {
        v6 = RegCreateKeyExW(hKey, L"Media Center", 0, 0, 0, 2u, 0, &v9, 0);
        RegCloseKey(hKey);
        if ( v6 )
        {
          v4 = v6 | 0x80070000;
        }
        else
        {
          hKey = v9;
          v7 = RegCreateKeyExW(v9, L"Decoder", 0, 0, 0, 2u, 0, &v9, 0);
          RegCloseKey(hKey);
          if ( v7 )
          {
            v4 = v7 | 0x80070000;
          }
          else
          {
            hKey = v9;
            v4 = RegSetValueExW(v9, L"PreferredMPEG2AudioDecoderCLSID", 0, 1u, v3, 0x4Eu);
            RegCloseKey(hKey);
            if ( v4 )
              v4 |= 0x80070000;
          }
        }
      }
    }
    goto LABEL_16;
  }
  v4 = -2147024882;
  if ( v1 )
LABEL_16:
    operator delete(v1);
  if ( v3 )
    operator delete(v3);
  return v4;
}

```

## disassembly

```asm
0x180018b70  sub     rsp, 68h
0x180018b74  call    ?IsLicensedComponentDOLBY_Internal@@YAHXZ; IsLicensedComponentDOLBY_Internal(void)
0x180018b79  test    eax, eax
0x180018b7b  jnz     short loc_180018B91
0x180018b7d  call    ?IsLicensedComponentAAC_Internal@@YAHXZ; IsLicensedComponentAAC_Internal(void)
0x180018b82  test    eax, eax
0x180018b84  jnz     short loc_180018B91
0x180018b86  mov     eax, 80004005h
0x180018b8b  add     rsp, 68h
0x180018b8f  retn
0x180018b91  mov     [rsp+68h+arg_10], rbx
0x180018b99  mov     ecx, 1
0x180018b9e  mov     [rsp+68h+var_8], rbp
0x180018ba3  mov     [rsp+68h+var_10], rsi
0x180018ba8  mov     [rsp+68h+var_18], rdi
0x180018bad  call    AMovieDllRegisterServer2
0x180018bb2  mov     ecx, 208h; unsigned __int64
0x180018bb7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018bbc  mov     ecx, 4Eh ; 'N'; unsigned __int64
0x180018bc1  mov     rsi, rax
0x180018bc4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180018bc9  xor     ebp, ebp
0x180018bcb  mov     rdi, rax
0x180018bce  mov     [rsp+68h+hKey], rbp
0x180018bd3  mov     [rsp+68h+arg_8], rbp
0x180018bd8  test    rsi, rsi
0x180018bdb  jz      loc_180018D72
0x180018be1  test    rax, rax
0x180018be4  jz      loc_180018D72
0x180018bea  mov     r8d, 27h ; '''; cchMax
0x180018bf0  lea     rcx, CLSID_CMPEG2AudDecoderDS; rguid
0x180018bf7  mov     rdx, rax; lpsz
0x180018bfa  call    cs:__imp_StringFromGUID2
0x180018c01  nop     dword ptr [rax+rax+00h]
0x180018c06  mov     ebx, eax
0x180018c08  test    eax, eax
0x180018c0a  js      loc_180018D7C
0x180018c10  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180018c17  mov     edx, 104h; unsigned __int64
0x180018c1c  mov     rcx, rsi; unsigned __int16 *
0x180018c1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018c24  lea     rax, [rsp+68h+hKey]
0x180018c29  mov     r9d, 4; samDesired
0x180018c2f  xor     r8d, r8d; ulOptions
0x180018c32  mov     [rsp+68h+phkResult], rax; phkResult
0x180018c37  mov     rdx, rsi; lpSubKey
0x180018c3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018c41  call    cs:__imp_RegOpenKeyExW
0x180018c48  nop     dword ptr [rax+rax+00h]
0x180018c4d  mov     ebx, eax
0x180018c4f  test    eax, eax
0x180018c51  jz      short loc_180018C5E
0x180018c53  or      ebx, 80070000h
0x180018c59  jmp     loc_180018D7C
0x180018c5e  mov     rcx, [rsp+68h+hKey]; hKey
0x180018c63  lea     rax, [rsp+68h+arg_8]
0x180018c68  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x180018c6d  lea     rdx, aMediaCenter; "Media Center"
0x180018c74  mov     [rsp+68h+var_30], rax; phkResult
0x180018c79  xor     r9d, r9d; lpClass
0x180018c7c  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180018c81  xor     r8d, r8d; Reserved
0x180018c84  mov     [rsp+68h+samDesired], 2; samDesired
0x180018c8c  mov     dword ptr [rsp+68h+phkResult], ebp; dwOptions
0x180018c90  call    cs:__imp_RegCreateKeyExW
0x180018c97  nop     dword ptr [rax+rax+00h]
0x180018c9c  mov     rcx, [rsp+68h+hKey]; hKey
0x180018ca1  mov     ebx, eax
0x180018ca3  call    cs:__imp_RegCloseKey
0x180018caa  nop     dword ptr [rax+rax+00h]
0x180018caf  test    ebx, ebx
0x180018cb1  jz      short loc_180018CBE
0x180018cb3  or      ebx, 80070000h
0x180018cb9  jmp     loc_180018D7C
0x180018cbe  mov     rcx, [rsp+68h+arg_8]; hKey
0x180018cc3  lea     rax, [rsp+68h+arg_8]
0x180018cc8  mov     [rsp+68h+lpdwDisposition], rbp; lpdwDisposition
0x180018ccd  lea     rdx, aDecoder; "Decoder"
0x180018cd4  mov     [rsp+68h+var_30], rax; phkResult
0x180018cd9  xor     r9d, r9d; lpClass
0x180018cdc  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180018ce1  xor     r8d, r8d; Reserved
0x180018ce4  mov     [rsp+68h+samDesired], 2; samDesired
0x180018cec  mov     dword ptr [rsp+68h+phkResult], ebp; dwOptions
0x180018cf0  mov     [rsp+68h+hKey], rcx
0x180018cf5  call    cs:__imp_RegCreateKeyExW
0x180018cfc  nop     dword ptr [rax+rax+00h]
0x180018d01  mov     rcx, [rsp+68h+hKey]; hKey
0x180018d06  mov     ebx, eax
0x180018d08  call    cs:__imp_RegCloseKey
0x180018d0f  nop     dword ptr [rax+rax+00h]
0x180018d14  test    ebx, ebx
0x180018d16  jz      short loc_180018D20
0x180018d18  or      ebx, 80070000h
0x180018d1e  jmp     short loc_180018D7C
0x180018d20  mov     rcx, [rsp+68h+arg_8]; hKey
0x180018d25  lea     rdx, aPreferredmpeg2; "PreferredMPEG2AudioDecoderCLSID"
0x180018d2c  mov     [rsp+68h+samDesired], 4Eh ; 'N'; cbData
0x180018d34  mov     r9d, 1; dwType
0x180018d3a  xor     r8d, r8d; Reserved
0x180018d3d  mov     [rsp+68h+hKey], rcx
0x180018d42  mov     [rsp+68h+phkResult], rdi; lpData
0x180018d47  call    cs:__imp_RegSetValueExW
0x180018d4e  nop     dword ptr [rax+rax+00h]
0x180018d53  mov     rcx, [rsp+68h+hKey]; hKey
0x180018d58  mov     ebx, eax
0x180018d5a  call    cs:__imp_RegCloseKey
0x180018d61  nop     dword ptr [rax+rax+00h]
0x180018d66  test    ebx, ebx
0x180018d68  jz      short loc_180018D7C
0x180018d6a  or      ebx, 80070000h
0x180018d70  jmp     short loc_180018D7C
0x180018d72  mov     ebx, 8007000Eh
0x180018d77  test    rsi, rsi
0x180018d7a  jz      short loc_180018D84
0x180018d7c  mov     rcx, rsi; Block
0x180018d7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018d84  mov     rsi, [rsp+68h+var_10]
0x180018d89  mov     rbp, [rsp+68h+var_8]
0x180018d8e  test    rdi, rdi
0x180018d91  jz      short loc_180018D9B
0x180018d93  mov     rcx, rdi; Block
0x180018d96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018d9b  mov     rdi, [rsp+68h+var_18]
0x180018da0  mov     eax, ebx
0x180018da2  mov     rbx, [rsp+68h+arg_10]
0x180018daa  add     rsp, 68h
0x180018dae  retn
```
