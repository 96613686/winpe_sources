# SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)

- ea: `0x14002eec8`
- end: `0x14002efdf`
- name: `?SetKeyAndValue@@YAHPEAGPEBG11@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018624`

## callees

- `0x140016c58`
- `0x140018350`
- `0x14002eec8`
- `0x140046430`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002efa6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14002efa6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002ef69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002ef69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002efb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002efb5`

## pseudocode

```c
__int64 __fastcall SetKeyAndValue(unsigned __int16 *a1, const unsigned __int16 *a2, LPCWSTR lpValueName, BYTE *lpData)
{
  __int64 v7; // rcx
  HKEY hKey; // [rsp+50h] [rbp-248h] BYREF
  WCHAR SubKey[256]; // [rsp+60h] [rbp-238h] BYREF

  hKey = 0;
  StringCchCopyW(SubKey, 0x100u, a1);
  if ( a2 )
  {
    StringCchCatW(SubKey, 0x100u, L"\\");
    StringCchCatW(SubKey, 0x100u, a2);
  }
  if ( RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
    return 0;
  if ( lpData )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&lpData[2 * v7] );
    if ( RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, 2 * v7 + 2) )
      return 0;
  }
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x14002eec8  push    rbx
0x14002eeca  push    rbp
0x14002eecb  push    rsi
0x14002eecc  push    rdi
0x14002eecd  push    r14
0x14002eecf  sub     rsp, 270h
0x14002eed6  mov     rax, cs:__security_cookie
0x14002eedd  xor     rax, rsp
0x14002eee0  mov     [rsp+298h+var_38], rax
0x14002eee8  mov     rsi, r8
0x14002eeeb  mov     rdi, rdx
0x14002eeee  mov     r8, rcx; unsigned __int16 *
0x14002eef1  mov     r14d, 100h
0x14002eef7  xor     ebp, ebp
0x14002eef9  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x14002eefe  mov     edx, r14d; unsigned __int64
0x14002ef01  mov     [rsp+298h+hKey], rbp
0x14002ef06  mov     rbx, r9
0x14002ef09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14002ef0e  test    rdi, rdi
0x14002ef11  jz      short loc_14002EF37
0x14002ef13  lea     r8, asc_14004DB1C; "\\"
0x14002ef1a  mov     edx, r14d; unsigned __int64
0x14002ef1d  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x14002ef22  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002ef27  mov     r8, rdi; unsigned __int16 *
0x14002ef2a  lea     rcx, [rsp+298h+SubKey]; unsigned __int16 *
0x14002ef2f  mov     edx, r14d; unsigned __int64
0x14002ef32  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002ef37  mov     [rsp+298h+lpdwDisposition], rbp; lpdwDisposition
0x14002ef3c  lea     rax, [rsp+298h+hKey]
0x14002ef41  mov     [rsp+298h+phkResult], rax; phkResult
0x14002ef46  lea     rdx, [rsp+298h+SubKey]; lpSubKey
0x14002ef4b  mov     [rsp+298h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x14002ef50  xor     r9d, r9d; lpClass
0x14002ef53  mov     [rsp+298h+samDesired], 0F003Fh; samDesired
0x14002ef5b  xor     r8d, r8d; Reserved
0x14002ef5e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14002ef65  mov     [rsp+298h+dwOptions], ebp; dwOptions
0x14002ef69  call    cs:__imp_RegCreateKeyExW
0x14002ef6f  test    eax, eax
0x14002ef71  jnz     short loc_14002EFBF
0x14002ef73  lea     edi, [rax+1]
0x14002ef76  test    rbx, rbx
0x14002ef79  jz      short loc_14002EFB0
0x14002ef7b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002ef7f  inc     rcx
0x14002ef82  cmp     [rbx+rcx*2], bp
0x14002ef86  jnz     short loc_14002EF7F
0x14002ef88  lea     ecx, ds:2[rcx*2]
0x14002ef8f  mov     r9d, edi; dwType
0x14002ef92  mov     [rsp+298h+samDesired], ecx; cbData
0x14002ef96  xor     r8d, r8d; Reserved
0x14002ef99  mov     rcx, [rsp+298h+hKey]; hKey
0x14002ef9e  mov     rdx, rsi; lpValueName
0x14002efa1  mov     qword ptr [rsp+298h+dwOptions], rbx; lpData
0x14002efa6  call    cs:__imp_RegSetValueExW
0x14002efac  test    eax, eax
0x14002efae  jnz     short loc_14002EFBF
0x14002efb0  mov     rcx, [rsp+298h+hKey]; hKey
0x14002efb5  call    cs:__imp_RegCloseKey
0x14002efbb  mov     eax, edi
0x14002efbd  jmp     short loc_14002EFC1
0x14002efbf  xor     eax, eax
0x14002efc1  mov     rcx, [rsp+298h+var_38]
0x14002efc9  xor     rcx, rsp; StackCookie
0x14002efcc  call    __security_check_cookie
0x14002efd1  add     rsp, 270h
0x14002efd8  pop     r14
0x14002efda  pop     rdi
0x14002efdb  pop     rsi
0x14002efdc  pop     rbp
0x14002efdd  pop     rbx
0x14002efde  retn
```
