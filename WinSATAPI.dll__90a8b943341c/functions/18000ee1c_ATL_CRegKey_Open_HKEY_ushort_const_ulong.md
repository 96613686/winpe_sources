# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000ee1c`
- end: `0x18000ee71`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `85`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015a44`
- `0x180018a88`
- `0x180018fb0`
- `0x180021cc0`
- `0x180021d84`
- `0x18002d430`
- `0x18002d4dc`
- `0x18002d59c`
- `0x18002d650`
- `0x18002d76c`
- `0x18002d7ec`
- `0x18002e4c0`

## callees

- `0x18000ee1c`
- `0x1800161e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ee44`

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
0x18000ee1c  push    rbx
0x18000ee1e  sub     rsp, 40h
0x18000ee22  and     [rsp+48h+var_18], 0
0x18000ee28  mov     rbx, rcx
0x18000ee2b  mov     rax, r8
0x18000ee2e  lea     rcx, [rsp+48h+var_18]
0x18000ee33  mov     r10, rdx
0x18000ee36  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000ee3b  mov     rcx, r10; hKey
0x18000ee3e  xor     r8d, r8d; ulOptions
0x18000ee41  mov     rdx, rax; lpSubKey
0x18000ee44  call    cs:__imp_RegOpenKeyExW
0x18000ee4b  nop     dword ptr [rax+rax+00h]
0x18000ee50  mov     edx, eax
0x18000ee52  test    eax, eax
0x18000ee54  jnz     short loc_18000EE68
0x18000ee56  mov     rcx, rbx; this
0x18000ee59  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ee5e  mov     edx, eax
0x18000ee60  mov     rax, [rsp+48h+var_18]
0x18000ee65  mov     [rbx], rax
0x18000ee68  mov     eax, edx
0x18000ee6a  add     rsp, 40h
0x18000ee6e  pop     rbx
0x18000ee6f  retn
```
