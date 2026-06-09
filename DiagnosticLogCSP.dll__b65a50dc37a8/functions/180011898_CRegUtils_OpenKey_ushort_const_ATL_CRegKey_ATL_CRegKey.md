# CRegUtils::OpenKey(ushort const *,ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x180011898`
- end: `0x180011929`
- name: `?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@1@Z`
- size: `145`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct ATL::CRegKey *, struct ATL::CRegKey *)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ddbc`
- `0x18000dec8`
- `0x18000e09c`
- `0x18000e314`
- `0x18000e628`
- `0x18000e6dc`
- `0x18000ebe8`
- `0x18000ed88`

## callees

- `0x180011898`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800118f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800118f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800118d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800118d6`

## pseudocode

```c
__int64 __fastcall CRegUtils::OpenKey(LPCWSTR lpSubKey, HKEY *a2, HKEY *a3)
{
  LSTATUS v4; // ebx
  LSTATUS v5; // edx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  if ( !lpSubKey )
    return (unsigned int)-2147024809;
  phkResult = 0;
  v4 = RegOpenKeyExW(*a2, lpSubKey, 0, 0x2001Fu, &phkResult);
  if ( v4 )
    goto LABEL_8;
  v5 = 0;
  if ( *a3 )
    v5 = RegCloseKey(*a3);
  *a3 = phkResult;
  if ( v5 )
  {
    v4 = v5;
LABEL_8:
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011898  mov     [rsp+arg_8], rbx
0x18001189d  push    rdi
0x18001189e  sub     rsp, 30h
0x1800118a2  mov     rdi, r8
0x1800118a5  mov     rax, rdx
0x1800118a8  test    rcx, rcx
0x1800118ab  jnz     short loc_1800118B4
0x1800118ad  mov     ebx, 80070057h
0x1800118b2  jmp     short loc_18001191B
0x1800118b4  lea     rdx, [rsp+38h+arg_0]
0x1800118b9  mov     [rsp+38h+arg_0], 0
0x1800118c2  mov     [rsp+38h+phkResult], rdx; phkResult
0x1800118c7  mov     r9d, 2001Fh; samDesired
0x1800118cd  mov     rdx, rcx; lpSubKey
0x1800118d0  xor     r8d, r8d; ulOptions
0x1800118d3  mov     rcx, [rax]; hKey
0x1800118d6  call    cs:__imp_RegOpenKeyExW
0x1800118dd  nop     dword ptr [rax+rax+00h]
0x1800118e2  mov     ebx, eax
0x1800118e4  test    eax, eax
0x1800118e6  jnz     short loc_18001190E
0x1800118e8  mov     rcx, [rdi]; hKey
0x1800118eb  xor     edx, edx
0x1800118ed  test    rcx, rcx
0x1800118f0  jz      short loc_180011900
0x1800118f2  call    cs:__imp_RegCloseKey
0x1800118f9  nop     dword ptr [rax+rax+00h]
0x1800118fe  mov     edx, eax
0x180011900  mov     rax, [rsp+38h+arg_0]
0x180011905  mov     [rdi], rax
0x180011908  test    edx, edx
0x18001190a  jz      short loc_18001191B
0x18001190c  mov     ebx, edx
0x18001190e  test    ebx, ebx
0x180011910  jle     short loc_18001191B
0x180011912  movzx   ebx, bx
0x180011915  or      ebx, 80070000h
0x18001191b  mov     eax, ebx
0x18001191d  mov     rbx, [rsp+38h+arg_8]
0x180011922  add     rsp, 30h
0x180011926  pop     rdi
0x180011927  retn
```
