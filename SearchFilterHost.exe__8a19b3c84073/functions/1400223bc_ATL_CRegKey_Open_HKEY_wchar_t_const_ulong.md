# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x1400223bc`
- end: `0x14002240d`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400229bc`
- `0x140022e00`

## callees

- `0x14001d910`
- `0x1400223bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400223e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400223e7`

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
0x1400223bc  push    rbx
0x1400223be  sub     rsp, 40h
0x1400223c2  mov     rbx, rcx
0x1400223c5  mov     [rsp+48h+var_18], 0
0x1400223ce  mov     rax, r8
0x1400223d1  lea     rcx, [rsp+48h+var_18]
0x1400223d6  mov     r10, rdx
0x1400223d9  mov     [rsp+48h+phkResult], rcx; phkResult
0x1400223de  mov     rcx, r10; hKey
0x1400223e1  xor     r8d, r8d; ulOptions
0x1400223e4  mov     rdx, rax; lpSubKey
0x1400223e7  call    cs:__imp_RegOpenKeyExW
0x1400223ed  mov     edx, eax
0x1400223ef  test    eax, eax
0x1400223f1  jnz     short loc_140022405
0x1400223f3  mov     rcx, rbx; this
0x1400223f6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400223fb  mov     edx, eax
0x1400223fd  mov     rax, [rsp+48h+var_18]
0x140022402  mov     [rbx], rax
0x140022405  mov     eax, edx
0x140022407  add     rsp, 40h
0x14002240b  pop     rbx
0x14002240c  retn
```
