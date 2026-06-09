# CMyRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180095d34`
- end: `0x180095dd7`
- name: `?Open@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `163`
- prototype: `__int64 __fastcall(CMyRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180068790`
- `0x180097e08`
- `0x1800981ac`
- `0x1800987f4`

## callees

- `0x180007fc0`
- `0x180095d34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095d96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095d96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095dbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095dbf`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180095d6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180095d6f`

## pseudocode

```c
__int64 __fastcall CMyRegKey::Open(CMyRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  HKEY v4; // rbx
  unsigned int v6; // ebx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp+10h] BYREF

  phkResult = 0;
  hKeya = 0;
  v4 = hKey;
  if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x20019u, &hKeya) )
    v4 = hKeya;
  v6 = RegOpenKeyExW(v4, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v6 )
  {
    v6 = CInputDllRegKey::Close(this);
    *((_QWORD *)this + 1) = phkResult;
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v6;
}

```

## disassembly

```asm
0x180095d34  mov     rax, rsp
0x180095d37  mov     [rax+8], rbx
0x180095d3b  mov     [rax+18h], rsi
0x180095d3f  push    rdi
0x180095d40  sub     rsp, 40h
0x180095d44  mov     qword ptr [rax-18h], 0
0x180095d4c  mov     rsi, r8
0x180095d4f  mov     qword ptr [rax+10h], 0
0x180095d57  mov     rbx, rdx
0x180095d5a  mov     rdi, rcx
0x180095d5d  cmp     rdx, 0FFFFFFFF80000001h
0x180095d64  jnz     short loc_180095D7D
0x180095d66  lea     rdx, [rax+10h]; phkResult
0x180095d6a  mov     ecx, 20019h; samDesired
0x180095d6f  call    cs:__imp_RegOpenCurrentUser
0x180095d75  test    eax, eax
0x180095d77  cmovz   rbx, [rsp+48h+hKey]
0x180095d7d  lea     rax, [rsp+48h+var_18]
0x180095d82  mov     r9d, 20019h; samDesired
0x180095d88  xor     r8d, r8d; ulOptions
0x180095d8b  mov     [rsp+48h+phkResult], rax; phkResult
0x180095d90  mov     rdx, rsi; lpSubKey
0x180095d93  mov     rcx, rbx; hKey
0x180095d96  call    cs:__imp_RegOpenKeyExW
0x180095d9c  mov     ebx, eax
0x180095d9e  test    eax, eax
0x180095da0  jnz     short loc_180095DB5
0x180095da2  mov     rcx, rdi; this
0x180095da5  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x180095daa  mov     ebx, eax
0x180095dac  mov     rax, [rsp+48h+var_18]
0x180095db1  mov     [rdi+8], rax
0x180095db5  mov     rcx, [rsp+48h+hKey]; hKey
0x180095dba  test    rcx, rcx
0x180095dbd  jz      short loc_180095DC5
0x180095dbf  call    cs:__imp_RegCloseKey
0x180095dc5  mov     rsi, [rsp+48h+arg_10]
0x180095dca  mov     eax, ebx
0x180095dcc  mov     rbx, [rsp+48h+arg_0]
0x180095dd1  add     rsp, 40h
0x180095dd5  pop     rdi
0x180095dd6  retn
```
