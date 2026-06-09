# DllRegisterServer

- ea: `0x18001c4b0`
- end: `0x18001c65a`
- name: `DllRegisterServer`
- size: `426`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000de80`
- `0x180019430`
- `0x18001c4b0`
- `0x18001c71c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c5ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001c5ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c642`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c642`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c55f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001c55f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001c5fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001c62d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001c5fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18001c62d`

## string_xrefs

- `0x18001c5b3`: `Image Path`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rdi
  __int64 v1; // rax
  size_t v2; // rbx
  wchar_t *v3; // rsi
  LSTATUS v4; // ebx
  DWORD dwDisposition; // [rsp+70h] [rbp+8h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  v0 = -1;
  Data = 0;
  dwDisposition = 0;
  hKey = 0;
  v1 = -1;
  do
    ++v1;
  while ( SourceString[v1] );
  v2 = (unsigned int)(2 * v1 + 102);
  v3 = (wchar_t *)MIDL_user_allocate(v2);
  if ( !v3 )
  {
    v4 = 8;
    goto LABEL_6;
  }
  StringCbPrintfW(v3, v2, L"%s%s", L"SOFTWARE\\Microsoft\\Cryptography\\Defaults\\Provider\\", SourceString);
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, (LPWSTR)&Class, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  CspFreeH(v3);
  if ( v4 )
  {
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_12;
  }
  do
    ++v0;
  while ( *(_WORD *)&lpData[2 * v0] );
  v4 = RegSetValueExW(hKey, L"Image Path", 0, 1u, lpData, 2 * v0 + 2);
  if ( !v4 )
  {
    v4 = RegSetValueExA(hKey, "Type", 0, 4u, &::Data, 4u);
    if ( !v4 )
      v4 = RegSetValueExA(hKey, "SigInFile", 0, 4u, (const BYTE *)&Data, 4u);
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18001c4b0  mov     rax, rsp
0x18001c4b3  mov     [rax+20h], rbx
0x18001c4b7  push    rbp
0x18001c4b8  push    rsi
0x18001c4b9  push    rdi
0x18001c4ba  sub     rsp, 50h
0x18001c4be  mov     rcx, cs:SourceString
0x18001c4c5  xor     ebp, ebp
0x18001c4c7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c4cb  mov     [rax+10h], ebp
0x18001c4ce  mov     [rax+8], ebp
0x18001c4d1  mov     [rax+18h], rbp
0x18001c4d5  mov     rax, rdi
0x18001c4d8  inc     rax
0x18001c4db  cmp     [rcx+rax*2], bp
0x18001c4df  jnz     short loc_18001C4D8
0x18001c4e1  lea     eax, ds:66h[rax*2]
0x18001c4e8  mov     ecx, eax; size
0x18001c4ea  mov     ebx, eax
0x18001c4ec  call    MIDL_user_allocate
0x18001c4f1  mov     rsi, rax
0x18001c4f4  test    rax, rax
0x18001c4f7  jnz     short loc_18001C4FE
0x18001c4f9  lea     ebx, [rax+8]
0x18001c4fc  jmp     short loc_18001C573
0x18001c4fe  mov     rax, cs:SourceString
0x18001c505  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Cryptography\\Defa"...
0x18001c50c  lea     r8, aSS_0; "%s%s"
0x18001c513  mov     qword ptr [rsp+68h+dwOptions], rax
0x18001c518  mov     rdx, rbx; cbDest
0x18001c51b  mov     rcx, rsi; pszDest
0x18001c51e  call    StringCbPrintfW
0x18001c523  lea     rax, [rsp+68h+dwDisposition]
0x18001c528  xor     r8d, r8d; Reserved
0x18001c52b  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18001c530  lea     r9, Class; lpClass
0x18001c537  lea     rax, [rsp+68h+hKey]
0x18001c53f  mov     rdx, rsi; lpSubKey
0x18001c542  mov     [rsp+68h+phkResult], rax; phkResult
0x18001c547  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c54e  mov     [rsp+68h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18001c553  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x18001c55b  mov     [rsp+68h+dwOptions], ebp; dwOptions
0x18001c55f  call    cs:__imp_RegCreateKeyExW
0x18001c565  mov     ebx, eax
0x18001c567  mov     rcx, rsi
0x18001c56a  call    CspFreeH
0x18001c56f  test    ebx, ebx
0x18001c571  jz      short loc_18001C592
0x18001c573  mov     rcx, [rsp+68h+hKey]; hKey
0x18001c57b  test    rcx, rcx
0x18001c57e  jz      loc_18001C635
0x18001c584  call    cs:__imp_RegCloseKey
0x18001c58a  test    ebx, ebx
0x18001c58c  jnz     loc_18001C635
0x18001c592  mov     rcx, cs:lpData
0x18001c599  inc     rdi
0x18001c59c  cmp     [rcx+rdi*2], bp
0x18001c5a0  jnz     short loc_18001C599
0x18001c5a2  lea     eax, ds:2[rdi*2]
0x18001c5a9  mov     r9d, 1; dwType
0x18001c5af  mov     [rsp+68h+samDesired], eax; cbData
0x18001c5b3  lea     rdx, ValueName; "Image Path"
0x18001c5ba  mov     qword ptr [rsp+68h+dwOptions], rcx; lpData
0x18001c5bf  xor     r8d, r8d; Reserved
0x18001c5c2  mov     rcx, [rsp+68h+hKey]; hKey
0x18001c5ca  call    cs:__imp_RegSetValueExW
0x18001c5d0  mov     ebx, eax
0x18001c5d2  test    eax, eax
0x18001c5d4  jnz     short loc_18001C635
0x18001c5d6  mov     rcx, [rsp+68h+hKey]; hKey
0x18001c5de  lea     edi, [rax+4]
0x18001c5e1  lea     rax, Data
0x18001c5e8  mov     [rsp+68h+samDesired], edi; cbData
0x18001c5ec  mov     r9d, edi; dwType
0x18001c5ef  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18001c5f4  xor     r8d, r8d; Reserved
0x18001c5f7  lea     rdx, aType; "Type"
0x18001c5fe  call    cs:__imp_RegSetValueExA
0x18001c604  mov     ebx, eax
0x18001c606  test    eax, eax
0x18001c608  jnz     short loc_18001C635
0x18001c60a  mov     rcx, [rsp+68h+hKey]; hKey
0x18001c612  lea     rax, [rsp+68h+Data]
0x18001c617  mov     [rsp+68h+samDesired], edi; cbData
0x18001c61b  lea     rdx, aSiginfile; "SigInFile"
0x18001c622  mov     r9d, edi; dwType
0x18001c625  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18001c62a  xor     r8d, r8d; Reserved
0x18001c62d  call    cs:__imp_RegSetValueExA
0x18001c633  mov     ebx, eax
0x18001c635  mov     rcx, [rsp+68h+hKey]; hKey
0x18001c63d  test    rcx, rcx
0x18001c640  jz      short loc_18001C648
0x18001c642  call    cs:__imp_RegCloseKey
0x18001c648  mov     eax, ebx
0x18001c64a  mov     rbx, [rsp+68h+arg_18]
0x18001c652  add     rsp, 50h
0x18001c656  pop     rdi
0x18001c657  pop     rsi
0x18001c658  pop     rbp
0x18001c659  retn
```
