# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1400083d0`
- end: `0x140008421`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(HKEY *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000931c`
- `0x140009754`
- `0x14000ceb4`

## callees

- `0x140005134`
- `0x1400083d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400083fb`
- `ADVAPI32!RegOpenKeyExW` at `0x1400083fb`

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
0x1400083d0  push    rbx
0x1400083d2  sub     rsp, 40h
0x1400083d6  mov     rbx, rcx
0x1400083d9  mov     [rsp+48h+var_18], 0
0x1400083e2  mov     rax, r8
0x1400083e5  lea     rcx, [rsp+48h+var_18]
0x1400083ea  mov     r10, rdx
0x1400083ed  mov     [rsp+48h+phkResult], rcx; phkResult
0x1400083f2  mov     rcx, r10; hKey
0x1400083f5  xor     r8d, r8d; ulOptions
0x1400083f8  mov     rdx, rax; lpSubKey
0x1400083fb  call    cs:__imp_RegOpenKeyExW
0x140008401  mov     edx, eax
0x140008403  test    eax, eax
0x140008405  jnz     short loc_140008419
0x140008407  mov     rcx, rbx; this
0x14000840a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000840f  mov     edx, eax
0x140008411  mov     rax, [rsp+48h+var_18]
0x140008416  mov     [rbx], rax
0x140008419  mov     eax, edx
0x14000841b  add     rsp, 40h
0x14000841f  pop     rbx
0x140008420  retn
```
