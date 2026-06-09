# CRegistry::Open(HKEY__ *,ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800176a8`
- end: `0x18001772a`
- name: `?Open@CRegistry@@QEAAXPEAUHKEY__@@PEBGKKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `130`
- prototype: `void __fastcall(DWORD *phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD dwOptions)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001241c`
- `0x180015690`
- `0x180031df0`
- `0x1800324dc`

## callees

- `0x1800176a8`
- `0x180017730`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800176e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017716`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180017716`

## pseudocode

```c
void __fastcall CRegistry::Open(DWORD *phkResult, HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, DWORD dwOptions)
{
  LSTATUS Key; // eax

  CRegistry::Close((CRegistry *)phkResult);
  if ( dwOptions == -32 )
  {
    Key = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, (PHKEY)phkResult);
    phkResult[2] = 2;
  }
  else
  {
    Key = RegCreateKeyExW(hKey, lpSubKey, 0, (LPWSTR)&Class, dwOptions, samDesired, 0, (PHKEY)phkResult, phkResult + 2);
  }
  phkResult[10] = Key;
}

```

## disassembly

```asm
0x1800176a8  push    rbx
0x1800176aa  push    rbp
0x1800176ab  push    rsi
0x1800176ac  push    rdi
0x1800176ad  push    r14
0x1800176af  sub     rsp, 50h
0x1800176b3  mov     edi, r9d
0x1800176b6  mov     rsi, r8
0x1800176b9  mov     rbp, rdx
0x1800176bc  mov     rbx, rcx
0x1800176bf  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x1800176c4  mov     eax, [rsp+78h+dwOptions]
0x1800176cb  lea     r14, [rbx+8]
0x1800176cf  xor     r8d, r8d; Reserved
0x1800176d2  mov     rdx, rsi; lpSubKey
0x1800176d5  mov     rcx, rbp; hKey
0x1800176d8  cmp     eax, 0FFFFFFE0h
0x1800176db  jnz     short loc_1800176F4
0x1800176dd  mov     r9d, edi; samDesired
0x1800176e0  mov     [rsp+78h+phkResult], rbx; phkResult
0x1800176e5  call    cs:__imp_RegOpenKeyExW
0x1800176eb  mov     dword ptr [r14], 2
0x1800176f2  jmp     short loc_18001771C
0x1800176f4  mov     [rsp+78h+lpdwDisposition], r14; lpdwDisposition
0x1800176f9  lea     r9, Class; lpClass
0x180017700  mov     [rsp+78h+var_40], rbx; phkResult
0x180017705  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001770e  mov     [rsp+78h+samDesired], edi; samDesired
0x180017712  mov     dword ptr [rsp+78h+phkResult], eax; dwOptions
0x180017716  call    cs:__imp_RegCreateKeyExW
0x18001771c  mov     [rbx+28h], eax
0x18001771f  add     rsp, 50h
0x180017723  pop     r14
0x180017725  pop     rdi
0x180017726  pop     rsi
0x180017727  pop     rbp
0x180017728  pop     rbx
0x180017729  retn
```
