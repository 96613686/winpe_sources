# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x18000c8a0`
- end: `0x18000c8f1`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bb08`
- `0x18000cbe8`
- `0x18000d0b8`
- `0x180023a88`
- `0x180031594`
- `0x180034578`

## callees

- `0x18000bf84`
- `0x18000c8a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c8cb`

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
0x18000c8a0  push    rbx
0x18000c8a2  sub     rsp, 40h
0x18000c8a6  mov     rbx, rcx
0x18000c8a9  mov     [rsp+48h+var_18], 0
0x18000c8b2  mov     rax, r8
0x18000c8b5  lea     rcx, [rsp+48h+var_18]
0x18000c8ba  mov     r10, rdx
0x18000c8bd  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000c8c2  mov     rcx, r10; hKey
0x18000c8c5  xor     r8d, r8d; ulOptions
0x18000c8c8  mov     rdx, rax; lpSubKey
0x18000c8cb  call    cs:__imp_RegOpenKeyExW
0x18000c8d1  mov     edx, eax
0x18000c8d3  test    eax, eax
0x18000c8d5  jnz     short loc_18000C8E9
0x18000c8d7  mov     rcx, rbx; this
0x18000c8da  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000c8df  mov     edx, eax
0x18000c8e1  mov     rax, [rsp+48h+var_18]
0x18000c8e6  mov     [rbx], rax
0x18000c8e9  mov     eax, edx
0x18000c8eb  add     rsp, 40h
0x18000c8ef  pop     rbx
0x18000c8f0  retn
```
