# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000d354`
- end: `0x18000d3a5`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e344`
- `0x18000e810`

## callees

- `0x18000a1a0`
- `0x18000d354`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d37f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d37f`

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
0x18000d354  push    rbx
0x18000d356  sub     rsp, 40h
0x18000d35a  mov     rbx, rcx
0x18000d35d  mov     [rsp+48h+var_18], 0
0x18000d366  mov     rax, r8
0x18000d369  lea     rcx, [rsp+48h+var_18]
0x18000d36e  mov     r10, rdx
0x18000d371  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000d376  mov     rcx, r10; hKey
0x18000d379  xor     r8d, r8d; ulOptions
0x18000d37c  mov     rdx, rax; lpSubKey
0x18000d37f  call    cs:__imp_RegOpenKeyExW
0x18000d385  mov     edx, eax
0x18000d387  test    eax, eax
0x18000d389  jnz     short loc_18000D39D
0x18000d38b  mov     rcx, rbx; this
0x18000d38e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d393  mov     edx, eax
0x18000d395  mov     rax, [rsp+48h+var_18]
0x18000d39a  mov     [rbx], rax
0x18000d39d  mov     eax, edx
0x18000d39f  add     rsp, 40h
0x18000d3a3  pop     rbx
0x18000d3a4  retn
```
