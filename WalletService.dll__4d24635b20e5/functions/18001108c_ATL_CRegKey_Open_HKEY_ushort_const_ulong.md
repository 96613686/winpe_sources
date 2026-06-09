# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18001108c`
- end: `0x1800110dd`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f8bc`
- `0x1800102c0`
- `0x180011f20`
- `0x1800124c0`
- `0x180019400`
- `0x180019820`
- `0x18001bc58`
- `0x18001d000`
- `0x1800265ec`
- `0x18002e5b0`
- `0x180034920`
- `0x1800363e0`

## callees

- `0x18000de7c`
- `0x18001108c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800110b7`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x18001108c  push    rbx
0x18001108e  sub     rsp, 40h
0x180011092  mov     rbx, rcx
0x180011095  mov     [rsp+48h+var_18], 0
0x18001109e  mov     rax, r8
0x1800110a1  lea     rcx, [rsp+48h+var_18]
0x1800110a6  mov     r10, rdx
0x1800110a9  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800110ae  mov     rcx, r10; hKey
0x1800110b1  xor     r8d, r8d; ulOptions
0x1800110b4  mov     rdx, rax; lpSubKey
0x1800110b7  call    cs:__imp_RegOpenKeyExW
0x1800110bd  mov     edx, eax
0x1800110bf  test    eax, eax
0x1800110c1  jnz     short loc_1800110D5
0x1800110c3  mov     rcx, rbx; this
0x1800110c6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800110cb  mov     edx, eax
0x1800110cd  mov     rax, [rsp+48h+var_18]
0x1800110d2  mov     [rbx], rax
0x1800110d5  mov     eax, edx
0x1800110d7  add     rsp, 40h
0x1800110db  pop     rbx
0x1800110dc  retn
```
