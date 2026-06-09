# CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)

- ea: `0x180011930`
- end: `0x1800119c2`
- name: `?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct ATL::CRegKey *)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800094c8`
- `0x180009ca0`
- `0x18000e278`
- `0x18000e558`
- `0x18000e744`
- `0x18000e858`
- `0x18000f228`
- `0x18000f8cc`
- `0x18000f9fc`
- `0x18000fc24`
- `0x18000fd38`
- `0x180010118`
- `0x180012404`
- `0x180012e00`
- `0x180012fe0`
- `0x180013570`
- `0x180013ab4`

## callees

- `0x180011930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001198b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001198b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001196f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001196f`

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
0x180011930  mov     [rsp+arg_8], rbx
0x180011935  push    rdi
0x180011936  sub     rsp, 30h
0x18001193a  mov     rdi, rdx
0x18001193d  test    rcx, rcx
0x180011940  jnz     short loc_180011949
0x180011942  mov     ebx, 80070057h
0x180011947  jmp     short loc_1800119B4
0x180011949  lea     rax, [rsp+38h+arg_0]
0x18001194e  mov     [rsp+38h+arg_0], 0
0x180011957  mov     rdx, rcx; lpSubKey
0x18001195a  mov     [rsp+38h+phkResult], rax; phkResult
0x18001195f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011966  mov     r9d, 2001Fh; samDesired
0x18001196c  xor     r8d, r8d; ulOptions
0x18001196f  call    cs:__imp_RegOpenKeyExW
0x180011976  nop     dword ptr [rax+rax+00h]
0x18001197b  mov     ebx, eax
0x18001197d  test    eax, eax
0x18001197f  jnz     short loc_1800119A7
0x180011981  mov     rcx, [rdi]; hKey
0x180011984  xor     edx, edx
0x180011986  test    rcx, rcx
0x180011989  jz      short loc_180011999
0x18001198b  call    cs:__imp_RegCloseKey
0x180011992  nop     dword ptr [rax+rax+00h]
0x180011997  mov     edx, eax
0x180011999  mov     rax, [rsp+38h+arg_0]
0x18001199e  mov     [rdi], rax
0x1800119a1  test    edx, edx
0x1800119a3  jz      short loc_1800119B4
0x1800119a5  mov     ebx, edx
0x1800119a7  test    ebx, ebx
0x1800119a9  jle     short loc_1800119B4
0x1800119ab  movzx   ebx, bx
0x1800119ae  or      ebx, 80070000h
0x1800119b4  mov     eax, ebx
0x1800119b6  mov     rbx, [rsp+38h+arg_8]
0x1800119bb  add     rsp, 30h
0x1800119bf  pop     rdi
0x1800119c0  retn
```
