# CRegUtils::OpenKey(ushort const *,ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x180010ff0`
- end: `0x180011074`
- name: `?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@1@Z`
- size: `132`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct ATL::CRegKey *, struct ATL::CRegKey *)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d710`
- `0x18000d818`
- `0x18000d9e0`
- `0x18000dc40`
- `0x18000df44`
- `0x18000dff4`
- `0x18000e4cc`
- `0x18000e664`

## callees

- `0x180010ff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011044`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011044`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001102e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001102e`

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
0x180010ff0  mov     [rsp+arg_8], rbx
0x180010ff5  push    rdi
0x180010ff6  sub     rsp, 30h
0x180010ffa  mov     rdi, r8
0x180010ffd  mov     rax, rdx
0x180011000  test    rcx, rcx
0x180011003  jnz     short loc_18001100C
0x180011005  mov     ebx, 80070057h
0x18001100a  jmp     short loc_180011067
0x18001100c  lea     rdx, [rsp+38h+arg_0]
0x180011011  mov     [rsp+38h+arg_0], 0
0x18001101a  mov     [rsp+38h+phkResult], rdx; phkResult
0x18001101f  mov     r9d, 2001Fh; samDesired
0x180011025  mov     rdx, rcx; lpSubKey
0x180011028  xor     r8d, r8d; ulOptions
0x18001102b  mov     rcx, [rax]; hKey
0x18001102e  call    cs:__imp_RegOpenKeyExW
0x180011034  mov     ebx, eax
0x180011036  test    eax, eax
0x180011038  jnz     short loc_18001105A
0x18001103a  mov     rcx, [rdi]; hKey
0x18001103d  xor     edx, edx
0x18001103f  test    rcx, rcx
0x180011042  jz      short loc_18001104C
0x180011044  call    cs:__imp_RegCloseKey
0x18001104a  mov     edx, eax
0x18001104c  mov     rax, [rsp+38h+arg_0]
0x180011051  mov     [rdi], rax
0x180011054  test    edx, edx
0x180011056  jz      short loc_180011067
0x180011058  mov     ebx, edx
0x18001105a  test    ebx, ebx
0x18001105c  jle     short loc_180011067
0x18001105e  movzx   ebx, bx
0x180011061  or      ebx, 80070000h
0x180011067  mov     eax, ebx
0x180011069  mov     rbx, [rsp+38h+arg_8]
0x18001106e  add     rsp, 30h
0x180011072  pop     rdi
0x180011073  retn
```
