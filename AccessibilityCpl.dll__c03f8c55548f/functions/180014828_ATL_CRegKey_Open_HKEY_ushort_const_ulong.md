# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180014828`
- end: `0x180014879`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `31`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000829c`
- `0x180015dd0`
- `0x180016800`
- `0x180016d70`
- `0x180016ee4`
- `0x1800178c0`
- `0x180018a28`
- `0x18001a340`
- `0x18001d62c`
- `0x18001ddcc`
- `0x18001de80`
- `0x18001df2c`
- `0x180020edc`
- `0x180021750`
- `0x1800223d4`
- `0x1800224c8`
- `0x1800225c4`
- `0x180022724`
- `0x1800228b8`
- `0x1800229ec`
- `0x180023090`
- `0x180023bc0`
- `0x18002486c`
- `0x1800250c8`
- `0x1800251dc`
- `0x180025344`
- `0x1800256a0`
- `0x180026810`
- `0x180027808`
- `0x180029268`
- `0x1800293c4`

## callees

- `0x1800055c0`
- `0x180014828`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014853`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014853`

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
0x180014828  push    rbx
0x18001482a  sub     rsp, 40h
0x18001482e  mov     rbx, rcx
0x180014831  mov     [rsp+48h+var_18], 0
0x18001483a  mov     rax, r8
0x18001483d  lea     rcx, [rsp+48h+var_18]
0x180014842  mov     r10, rdx
0x180014845  mov     [rsp+48h+phkResult], rcx; phkResult
0x18001484a  mov     rcx, r10; hKey
0x18001484d  xor     r8d, r8d; ulOptions
0x180014850  mov     rdx, rax; lpSubKey
0x180014853  call    cs:__imp_RegOpenKeyExW
0x180014859  mov     edx, eax
0x18001485b  test    eax, eax
0x18001485d  jnz     short loc_180014871
0x18001485f  mov     rcx, rbx; this
0x180014862  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014867  mov     edx, eax
0x180014869  mov     rax, [rsp+48h+var_18]
0x18001486e  mov     [rbx], rax
0x180014871  mov     eax, edx
0x180014873  add     rsp, 40h
0x180014877  pop     rbx
0x180014878  retn
```
