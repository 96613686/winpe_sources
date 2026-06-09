# CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)

- ea: `0x18001107c`
- end: `0x180011101`
- name: `?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct ATL::CRegKey *)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009260`
- `0x180009a10`
- `0x18000dbb0`
- `0x18000de80`
- `0x18000e054`
- `0x18000e158`
- `0x18000eaf8`
- `0x18000f170`
- `0x18000f280`
- `0x18000f47c`
- `0x18000f580`
- `0x18000f924`
- `0x180011a8c`
- `0x180012440`
- `0x180012618`
- `0x180012b8c`
- `0x180013090`

## callees

- `0x18001107c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800110d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110bb`

## pseudocode

```c
__int64 __fastcall CRegUtils::OpenKey(LPCWSTR lpSubKey, HKEY *a2)
{
  LSTATUS v3; // ebx
  LSTATUS v4; // edx
  HKEY phkResult; // [rsp+40h] [rbp+8h] BYREF

  if ( !lpSubKey )
    return (unsigned int)-2147024809;
  phkResult = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &phkResult);
  if ( v3 )
    goto LABEL_8;
  v4 = 0;
  if ( *a2 )
    v4 = RegCloseKey(*a2);
  *a2 = phkResult;
  if ( v4 )
  {
    v3 = v4;
LABEL_8:
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001107c  mov     [rsp+arg_8], rbx
0x180011081  push    rdi
0x180011082  sub     rsp, 30h
0x180011086  mov     rdi, rdx
0x180011089  test    rcx, rcx
0x18001108c  jnz     short loc_180011095
0x18001108e  mov     ebx, 80070057h
0x180011093  jmp     short loc_1800110F4
0x180011095  lea     rax, [rsp+38h+arg_0]
0x18001109a  mov     [rsp+38h+arg_0], 0
0x1800110a3  mov     rdx, rcx; lpSubKey
0x1800110a6  mov     [rsp+38h+phkResult], rax; phkResult
0x1800110ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800110b2  mov     r9d, 2001Fh; samDesired
0x1800110b8  xor     r8d, r8d; ulOptions
0x1800110bb  call    cs:__imp_RegOpenKeyExW
0x1800110c1  mov     ebx, eax
0x1800110c3  test    eax, eax
0x1800110c5  jnz     short loc_1800110E7
0x1800110c7  mov     rcx, [rdi]; hKey
0x1800110ca  xor     edx, edx
0x1800110cc  test    rcx, rcx
0x1800110cf  jz      short loc_1800110D9
0x1800110d1  call    cs:__imp_RegCloseKey
0x1800110d7  mov     edx, eax
0x1800110d9  mov     rax, [rsp+38h+arg_0]
0x1800110de  mov     [rdi], rax
0x1800110e1  test    edx, edx
0x1800110e3  jz      short loc_1800110F4
0x1800110e5  mov     ebx, edx
0x1800110e7  test    ebx, ebx
0x1800110e9  jle     short loc_1800110F4
0x1800110eb  movzx   ebx, bx
0x1800110ee  or      ebx, 80070000h
0x1800110f4  mov     eax, ebx
0x1800110f6  mov     rbx, [rsp+38h+arg_8]
0x1800110fb  add     rsp, 30h
0x1800110ff  pop     rdi
0x180011100  retn
```
