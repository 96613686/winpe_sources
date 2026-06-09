# F12::CreateOrOpenF12RegRoot(ATL::CRegKey &)

- ea: `0x18002f988`
- end: `0x18002fa6b`
- name: `?CreateOrOpenF12RegRoot@F12@@YAJAEAVCRegKey@ATL@@@Z`
- size: `227`
- prototype: `LSTATUS __fastcall(HKEY *this, struct ATL::CRegKey *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004400`
- `0x180025cac`
- `0x180028a60`
- `0x1800298b4`

## callees

- `0x18002f988`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18002f9cd`
- `ADVAPI32!RegCloseKey` at `0x18002fa47`
- `ADVAPI32!RegCloseKey` at `0x18002f9cd`
- `ADVAPI32!RegCloseKey` at `0x18002fa47`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f9bb`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f9bb`
- `ADVAPI32!RegCreateKeyExW` at `0x18002fa35`
- `ADVAPI32!RegCreateKeyExW` at `0x18002fa35`

## pseudocode

```c
LSTATUS __fastcall F12::CreateOrOpenF12RegRoot(HKEY *this, struct ATL::CRegKey *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF
  HKEY v6; // [rsp+70h] [rbp+18h] BYREF

  phkResult = 0;
  result = RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0x2001Fu, &phkResult);
  if ( result )
    goto LABEL_5;
  if ( *this )
    result = RegCloseKey(*this);
  *this = phkResult;
  if ( result )
  {
LABEL_5:
    LODWORD(phkResult) = 0;
    v6 = 0;
    v4 = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\F12", 0, 0, 0, 0x2001Fu, 0, &v6, (LPDWORD)&phkResult);
    if ( v4 )
    {
      return -2147467259;
    }
    else
    {
      if ( *this )
        v4 = RegCloseKey(*this);
      *this = v6;
      return v4 != 0 ? 0x80004005 : 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002f988  push    rbx
0x18002f98a  sub     rsp, 50h
0x18002f98e  mov     rbx, rcx
0x18002f991  mov     [rsp+58h+arg_8], 0
0x18002f99a  lea     rax, [rsp+58h+arg_8]
0x18002f99f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002f9a6  mov     r9d, 2001Fh; samDesired
0x18002f9ac  mov     [rsp+58h+phkResult], rax; phkResult
0x18002f9b1  xor     r8d, r8d; ulOptions
0x18002f9b4  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x18002f9bb  call    cs:__imp_RegOpenKeyExW
0x18002f9c1  test    eax, eax
0x18002f9c3  jnz     short loc_18002F9E3
0x18002f9c5  mov     rcx, [rbx]; hKey
0x18002f9c8  test    rcx, rcx
0x18002f9cb  jz      short loc_18002F9D3
0x18002f9cd  call    cs:__imp_RegCloseKey
0x18002f9d3  mov     rcx, [rsp+58h+arg_8]
0x18002f9d8  mov     [rbx], rcx
0x18002f9db  test    eax, eax
0x18002f9dd  jz      loc_18002FA65
0x18002f9e3  lea     rax, [rsp+58h+arg_8]
0x18002f9e8  mov     dword ptr [rsp+58h+arg_8], 0
0x18002f9f0  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18002f9f5  lea     rdx, SubKey; "Software\\Microsoft\\F12"
0x18002f9fc  lea     rax, [rsp+58h+arg_10]
0x18002fa01  mov     [rsp+58h+arg_10], 0
0x18002fa0a  mov     [rsp+58h+var_20], rax; phkResult
0x18002fa0f  xor     r9d, r9d; lpClass
0x18002fa12  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002fa1b  xor     r8d, r8d; Reserved
0x18002fa1e  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18002fa26  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002fa2d  mov     dword ptr [rsp+58h+phkResult], 0; dwOptions
0x18002fa35  call    cs:__imp_RegCreateKeyExW
0x18002fa3b  test    eax, eax
0x18002fa3d  jnz     short loc_18002FA60
0x18002fa3f  mov     rcx, [rbx]; hKey
0x18002fa42  test    rcx, rcx
0x18002fa45  jz      short loc_18002FA4D
0x18002fa47  call    cs:__imp_RegCloseKey
0x18002fa4d  mov     rcx, [rsp+58h+arg_10]
0x18002fa52  neg     eax
0x18002fa54  mov     [rbx], rcx
0x18002fa57  sbb     eax, eax
0x18002fa59  and     eax, 80004005h
0x18002fa5e  jmp     short loc_18002FA65
0x18002fa60  mov     eax, 80004005h
0x18002fa65  add     rsp, 50h
0x18002fa69  pop     rbx
0x18002fa6a  retn
```
