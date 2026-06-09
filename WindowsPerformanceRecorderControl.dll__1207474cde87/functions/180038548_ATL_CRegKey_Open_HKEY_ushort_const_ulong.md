# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180038548`
- end: `0x180038599`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d5c0`
- `0x18005cacc`
- `0x180060c20`
- `0x180060d14`
- `0x1800766b0`
- `0x18007f57c`

## callees

- `0x180008270`
- `0x180038548`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038573`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038573`

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
0x180038548  push    rbx
0x18003854a  sub     rsp, 40h
0x18003854e  mov     rbx, rcx
0x180038551  mov     [rsp+48h+var_18], 0
0x18003855a  mov     rax, r8
0x18003855d  lea     rcx, [rsp+48h+var_18]
0x180038562  mov     r10, rdx
0x180038565  mov     [rsp+48h+phkResult], rcx; phkResult
0x18003856a  mov     rcx, r10; hKey
0x18003856d  xor     r8d, r8d; ulOptions
0x180038570  mov     rdx, rax; lpSubKey
0x180038573  call    cs:__imp_RegOpenKeyExW
0x180038579  mov     edx, eax
0x18003857b  test    eax, eax
0x18003857d  jnz     short loc_180038591
0x18003857f  mov     rcx, rbx; this
0x180038582  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180038587  mov     edx, eax
0x180038589  mov     rax, [rsp+48h+var_18]
0x18003858e  mov     [rbx], rax
0x180038591  mov     eax, edx
0x180038593  add     rsp, 40h
0x180038597  pop     rbx
0x180038598  retn
```
