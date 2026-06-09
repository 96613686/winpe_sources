# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x180008a68`
- end: `0x180008ab9`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004fb8`
- `0x180008d88`

## callees

- `0x180006820`
- `0x180008a68`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180008a93`
- `ADVAPI32!RegOpenKeyExW` at `0x180008a93`

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
0x180008a68  push    rbx
0x180008a6a  sub     rsp, 40h
0x180008a6e  mov     rbx, rcx
0x180008a71  mov     [rsp+48h+var_18], 0
0x180008a7a  mov     rax, r8
0x180008a7d  lea     rcx, [rsp+48h+var_18]
0x180008a82  mov     r10, rdx
0x180008a85  mov     [rsp+48h+phkResult], rcx; phkResult
0x180008a8a  mov     rcx, r10; hKey
0x180008a8d  xor     r8d, r8d; ulOptions
0x180008a90  mov     rdx, rax; lpSubKey
0x180008a93  call    cs:__imp_RegOpenKeyExW
0x180008a99  mov     edx, eax
0x180008a9b  test    eax, eax
0x180008a9d  jnz     short loc_180008AB1
0x180008a9f  mov     rcx, rbx; this
0x180008aa2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008aa7  mov     edx, eax
0x180008aa9  mov     rax, [rsp+48h+var_18]
0x180008aae  mov     [rbx], rax
0x180008ab1  mov     eax, edx
0x180008ab3  add     rsp, 40h
0x180008ab7  pop     rbx
0x180008ab8  retn
```
