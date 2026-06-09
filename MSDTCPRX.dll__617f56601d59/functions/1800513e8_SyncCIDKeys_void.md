# SyncCIDKeys(void)

- ea: `0x1800513e8`
- end: `0x18005146f`
- name: `?SyncCIDKeys@@YAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180051df0`

## callees

- `0x1800513e8`
- `0x180051478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005141e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005141e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051459`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051464`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051459`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180051464`
- `ADVAPI32!RegCreateKeyW` at `0x18005143b`
- `ADVAPI32!RegCreateKeyW` at `0x18005143b`

## pseudocode

```c
void SyncCIDKeys(void)
{
  LSTATUS v0; // eax
  HKEY v1; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CID", 0, 0xF003Fu, &hKey) )
  {
    v0 = RegCreateKeyW(HKEY_CLASSES_ROOT, L"Wow6432Node\\CID", &phkResult);
    v1 = hKey;
    if ( !v0 )
    {
      SyncNode(hKey, phkResult);
      RegCloseKey(hKey);
      v1 = phkResult;
    }
    RegCloseKey(v1);
  }
}

```

## disassembly

```asm
0x1800513e8  mov     r11, rsp
0x1800513eb  sub     rsp, 38h
0x1800513ef  lea     rax, [r11+8]
0x1800513f3  mov     qword ptr [r11+8], 0
0x1800513fb  mov     r9d, 0F003Fh; samDesired
0x180051401  mov     [r11-18h], rax
0x180051405  xor     r8d, r8d; ulOptions
0x180051408  mov     qword ptr [r11+10h], 0
0x180051410  lea     rdx, aCid_0; "CID"
0x180051417  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005141e  call    cs:__imp_RegOpenKeyExW
0x180051424  test    eax, eax
0x180051426  jnz     short loc_18005146A
0x180051428  lea     r8, [rsp+38h+phkResult]; phkResult
0x18005142d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180051434  lea     rdx, aWow6432nodeCid; "Wow6432Node\\CID"
0x18005143b  call    cs:__imp_RegCreateKeyW
0x180051441  mov     rcx, [rsp+38h+hKey]; HKEY
0x180051446  test    eax, eax
0x180051448  jnz     short loc_180051464
0x18005144a  mov     rdx, [rsp+38h+phkResult]; HKEY
0x18005144f  call    ?SyncNode@@YAXPEAUHKEY__@@0@Z; SyncNode(HKEY__ *,HKEY__ *)
0x180051454  mov     rcx, [rsp+38h+hKey]; hKey
0x180051459  call    cs:__imp_RegCloseKey
0x18005145f  mov     rcx, [rsp+38h+phkResult]; hKey
0x180051464  call    cs:__imp_RegCloseKey
0x18005146a  add     rsp, 38h
0x18005146e  retn
```
