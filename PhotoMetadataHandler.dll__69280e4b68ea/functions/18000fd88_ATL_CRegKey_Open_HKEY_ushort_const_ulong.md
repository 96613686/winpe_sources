# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000fd88`
- end: `0x18000fde0`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `88`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001c2c`
- `0x180018d78`
- `0x180019bcc`
- `0x18001a0d8`

## callees

- `0x18000fd88`
- `0x18000fde8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fdb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fdb3`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x18000fd88  push    rbx
0x18000fd8a  sub     rsp, 40h
0x18000fd8e  mov     rbx, rcx
0x18000fd91  mov     [rsp+48h+var_18], 0
0x18000fd9a  mov     rax, r8
0x18000fd9d  lea     rcx, [rsp+48h+var_18]
0x18000fda2  mov     r10, rdx
0x18000fda5  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000fdaa  mov     rcx, r10; hKey
0x18000fdad  xor     r8d, r8d; ulOptions
0x18000fdb0  mov     rdx, rax; lpSubKey
0x18000fdb3  call    cs:__imp_RegOpenKeyExW
0x18000fdba  nop     dword ptr [rax+rax+00h]
0x18000fdbf  mov     edx, eax
0x18000fdc1  test    eax, eax
0x18000fdc3  jnz     short loc_18000FDD7
0x18000fdc5  mov     rcx, rbx; this
0x18000fdc8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fdcd  mov     edx, eax
0x18000fdcf  mov     rax, [rsp+48h+var_18]
0x18000fdd4  mov     [rbx], rax
0x18000fdd7  mov     eax, edx
0x18000fdd9  add     rsp, 40h
0x18000fddd  pop     rbx
0x18000fdde  retn
```
