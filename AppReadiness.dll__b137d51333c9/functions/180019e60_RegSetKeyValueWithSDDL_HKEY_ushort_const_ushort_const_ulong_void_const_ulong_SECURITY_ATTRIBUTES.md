# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180019e60`
- end: `0x180019f19`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `185`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061904`

## callees

- `0x180019e60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ebf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019ebf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019ead`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019ead`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019f05`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180019f05`

## pseudocode

```c
LSTATUS __fastcall _RegSetKeyValueWithSDDL(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  HKEY v6; // rdi
  LSTATUS result; // eax
  unsigned int v10; // ebx
  HKEY hKeya; // [rsp+68h] [rbp+10h] BYREF

  v6 = hKey;
  hKeya = 0;
  if ( a2 && *a2 )
  {
    result = RegCreateKeyExW(hKey, a2, 0, 0, 0, 2u, 0, &hKeya, 0);
    if ( result )
      return result;
    hKey = hKeya;
  }
  else
  {
    hKeya = hKey;
  }
  result = RegSetValueExW(hKey, a3, 0, a4, lpData, cbData);
  v10 = result;
  if ( hKeya != v6 )
  {
    RegCloseKey(hKeya);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180019e60  mov     [rsp+arg_0], rbx
0x180019e65  mov     [rsp+arg_10], rsi
0x180019e6a  push    rdi
0x180019e6b  sub     rsp, 50h
0x180019e6f  mov     rdi, rcx
0x180019e72  mov     ebx, r9d
0x180019e75  xor     ecx, ecx
0x180019e77  mov     rsi, r8
0x180019e7a  mov     [rsp+58h+hKey], rcx
0x180019e7f  test    rdx, rdx
0x180019e82  jnz     short loc_180019ED7
0x180019e84  mov     rcx, rdi; hKey
0x180019e87  mov     [rsp+58h+hKey], rcx
0x180019e8c  mov     eax, [rsp+58h+arg_28]
0x180019e93  mov     r9d, ebx; dwType
0x180019e96  mov     [rsp+58h+cbData], eax; cbData
0x180019e9a  xor     r8d, r8d; Reserved
0x180019e9d  mov     rax, [rsp+58h+arg_20]
0x180019ea5  mov     rdx, rsi; lpValueName
0x180019ea8  mov     [rsp+58h+lpData], rax; lpData
0x180019ead  call    cs:__imp_RegSetValueExW
0x180019eb3  mov     rcx, [rsp+58h+hKey]; hKey
0x180019eb8  mov     ebx, eax
0x180019eba  cmp     rcx, rdi
0x180019ebd  jz      short loc_180019EC7
0x180019ebf  call    cs:__imp_RegCloseKey
0x180019ec5  mov     eax, ebx
0x180019ec7  mov     rbx, [rsp+58h+arg_0]
0x180019ecc  mov     rsi, [rsp+58h+arg_10]
0x180019ed1  add     rsp, 50h
0x180019ed5  pop     rdi
0x180019ed6  retn
0x180019ed7  cmp     [rdx], cx
0x180019eda  jz      short loc_180019E84
0x180019edc  mov     [rsp+58h+lpdwDisposition], rcx; lpdwDisposition
0x180019ee1  lea     rax, [rsp+58h+hKey]
0x180019ee6  mov     [rsp+58h+phkResult], rax; phkResult
0x180019eeb  xor     r9d, r9d; lpClass
0x180019eee  mov     [rsp+58h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180019ef3  xor     r8d, r8d; Reserved
0x180019ef6  mov     [rsp+58h+cbData], 2; samDesired
0x180019efe  mov     dword ptr [rsp+58h+lpData], ecx; dwOptions
0x180019f02  mov     rcx, rdi; hKey
0x180019f05  call    cs:__imp_RegCreateKeyExW
0x180019f0b  test    eax, eax
0x180019f0d  jnz     short loc_180019EC7
0x180019f0f  mov     rcx, [rsp+58h+hKey]
0x180019f14  jmp     loc_180019E8C
```
