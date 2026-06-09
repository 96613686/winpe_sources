# CFvePolicyReader::ResetRootPolicyKeys(void)

- ea: `0x18002f960`
- end: `0x18002fa5a`
- name: `?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ`
- size: `250`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180032300`

## callees

- `0x180023ca0`
- `0x180027ef0`
- `0x18002f960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f9ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fa40`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ResetRootPolicyKeys(CFvePolicyReader *this)
{
  LSTATUS v2; // eax
  signed int v3; // ebx
  LSTATUS v4; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  phkResult = 0;
  CFvePolicyReader::CloseRootPolicyKeys(this);
  CFvePolicyReader::UnloadVolumePolicy(this);
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  if ( v3 < 0 )
    goto LABEL_8;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System", 0, 0x20019u, &phkResult);
  v3 = v4;
  if ( v4 > 0 )
    v3 = (unsigned __int16)v4 | 0x80070000;
  if ( v3 < 0 )
  {
LABEL_8:
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    *((_QWORD *)this + 2) = hKey;
    *((_QWORD *)this + 3) = phkResult;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f960  mov     [rsp+arg_0], rbx
0x18002f965  push    rdi
0x18002f966  sub     rsp, 30h
0x18002f96a  mov     rdi, rcx
0x18002f96d  mov     [rsp+38h+hKey], 0
0x18002f976  mov     [rsp+38h+arg_10], 0
0x18002f97f  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x18002f984  mov     rcx, rdi; this
0x18002f987  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x18002f98c  lea     rax, [rsp+38h+hKey]
0x18002f991  mov     r9d, 20019h; samDesired
0x18002f997  xor     r8d, r8d; ulOptions
0x18002f99a  mov     [rsp+38h+phkResult], rax; phkResult
0x18002f99f  lea     rdx, aSoftware; "Software"
0x18002f9a6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f9ad  call    cs:__imp_RegOpenKeyExW
0x18002f9b4  nop     dword ptr [rax+rax+00h]
0x18002f9b9  mov     ebx, eax
0x18002f9bb  test    eax, eax
0x18002f9bd  jle     short loc_18002F9C8
0x18002f9bf  movzx   ebx, ax
0x18002f9c2  or      ebx, 80070000h
0x18002f9c8  test    ebx, ebx
0x18002f9ca  js      short loc_18002FA20
0x18002f9cc  lea     rax, [rsp+38h+arg_10]
0x18002f9d1  mov     r9d, 20019h; samDesired
0x18002f9d7  xor     r8d, r8d; ulOptions
0x18002f9da  mov     [rsp+38h+phkResult], rax; phkResult
0x18002f9df  lea     rdx, aSystem; "System"
0x18002f9e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f9ed  call    cs:__imp_RegOpenKeyExW
0x18002f9f4  nop     dword ptr [rax+rax+00h]
0x18002f9f9  mov     ebx, eax
0x18002f9fb  test    eax, eax
0x18002f9fd  jle     short loc_18002FA08
0x18002f9ff  movzx   ebx, ax
0x18002fa02  or      ebx, 80070000h
0x18002fa08  test    ebx, ebx
0x18002fa0a  js      short loc_18002FA20
0x18002fa0c  mov     rax, [rsp+38h+hKey]
0x18002fa11  mov     [rdi+10h], rax
0x18002fa15  mov     rax, [rsp+38h+arg_10]
0x18002fa1a  mov     [rdi+18h], rax
0x18002fa1e  jmp     short loc_18002FA4C
0x18002fa20  mov     rcx, [rsp+38h+hKey]; hKey
0x18002fa25  test    rcx, rcx
0x18002fa28  jz      short loc_18002FA36
0x18002fa2a  call    cs:__imp_RegCloseKey
0x18002fa31  nop     dword ptr [rax+rax+00h]
0x18002fa36  mov     rcx, [rsp+38h+arg_10]; hKey
0x18002fa3b  test    rcx, rcx
0x18002fa3e  jz      short loc_18002FA4C
0x18002fa40  call    cs:__imp_RegCloseKey
0x18002fa47  nop     dword ptr [rax+rax+00h]
0x18002fa4c  mov     eax, ebx
0x18002fa4e  mov     rbx, [rsp+38h+arg_0]
0x18002fa53  add     rsp, 30h
0x18002fa57  pop     rdi
0x18002fa58  retn
```
