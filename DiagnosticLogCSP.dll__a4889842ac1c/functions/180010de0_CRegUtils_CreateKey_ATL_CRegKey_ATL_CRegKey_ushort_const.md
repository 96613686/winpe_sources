# CRegUtils::CreateKey(ATL::CRegKey &,ATL::CRegKey &,ushort const *)

- ea: `0x180010de0`
- end: `0x180010e8f`
- name: `?CreateKey@CRegUtils@@SAJAEAVCRegKey@ATL@@0PEBG@Z`
- size: `175`
- prototype: `__int64 __fastcall(HKEY *, HKEY *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000911c`
- `0x18000e158`
- `0x18000e374`
- `0x18000f580`
- `0x180013090`

## callees

- `0x180010de0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e5f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010e49`

## pseudocode

```c
__int64 __fastcall CRegUtils::CreateKey(HKEY *a1, HKEY *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // ebx
  HKEY v5; // rcx
  LSTATUS v6; // edx
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+20h] BYREF

  if ( !a3 )
    return (unsigned int)-2147024809;
  v5 = *a1;
  dwDisposition = 0;
  phkResult = 0;
  v4 = RegCreateKeyExW(v5, a3, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  if ( v4 )
    goto LABEL_8;
  v6 = 0;
  if ( *a2 )
    v6 = RegCloseKey(*a2);
  *a2 = phkResult;
  if ( v6 )
  {
    v4 = v6;
LABEL_8:
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010de0  mov     [rsp+arg_0], rbx
0x180010de5  push    rdi
0x180010de6  sub     rsp, 50h
0x180010dea  mov     rax, r8
0x180010ded  mov     rdi, rdx
0x180010df0  test    r8, r8
0x180010df3  jnz     short loc_180010DFF
0x180010df5  mov     ebx, 80070057h
0x180010dfa  jmp     loc_180010E82
0x180010dff  mov     rcx, [rcx]; hKey
0x180010e02  lea     rdx, [rsp+58h+dwDisposition]
0x180010e07  mov     [rsp+58h+lpdwDisposition], rdx; lpdwDisposition
0x180010e0c  xor     r9d, r9d; lpClass
0x180010e0f  lea     rdx, [rsp+58h+arg_18]
0x180010e14  mov     [rsp+58h+dwDisposition], 0
0x180010e1c  mov     [rsp+58h+phkResult], rdx; phkResult
0x180010e21  xor     r8d, r8d; Reserved
0x180010e24  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010e2d  mov     rdx, rax; lpSubKey
0x180010e30  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x180010e38  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180010e40  mov     [rsp+58h+arg_18], 0
0x180010e49  call    cs:__imp_RegCreateKeyExW
0x180010e4f  mov     ebx, eax
0x180010e51  test    eax, eax
0x180010e53  jnz     short loc_180010E75
0x180010e55  mov     rcx, [rdi]; hKey
0x180010e58  xor     edx, edx
0x180010e5a  test    rcx, rcx
0x180010e5d  jz      short loc_180010E67
0x180010e5f  call    cs:__imp_RegCloseKey
0x180010e65  mov     edx, eax
0x180010e67  mov     rax, [rsp+58h+arg_18]
0x180010e6c  mov     [rdi], rax
0x180010e6f  test    edx, edx
0x180010e71  jz      short loc_180010E82
0x180010e73  mov     ebx, edx
0x180010e75  test    ebx, ebx
0x180010e77  jle     short loc_180010E82
0x180010e79  movzx   ebx, bx
0x180010e7c  or      ebx, 80070000h
0x180010e82  mov     eax, ebx
0x180010e84  mov     rbx, [rsp+58h+arg_0]
0x180010e89  add     rsp, 50h
0x180010e8d  pop     rdi
0x180010e8e  retn
```
