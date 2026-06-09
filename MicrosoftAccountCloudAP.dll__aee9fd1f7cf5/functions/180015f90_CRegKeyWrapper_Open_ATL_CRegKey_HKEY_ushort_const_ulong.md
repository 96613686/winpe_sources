# CRegKeyWrapper::Open(ATL::CRegKey *,HKEY__ *,ushort const *,ulong)

- ea: `0x180015f90`
- end: `0x180015fe6`
- name: `?Open@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEAUHKEY__@@PEBGK@Z`
- size: `86`
- prototype: `int(CRegKeyWrapper *__hidden this, struct ATL::CRegKey *, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000e0c4`
- `0x180015f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015fc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015fc0`

## pseudocode

```c
__int64 __fastcall CRegKeyWrapper::Open(
        CRegKeyWrapper *this,
        struct ATL::CRegKey *a2,
        HKEY a3,
        const unsigned __int16 *a4,
        REGSAM samDesired)
{
  unsigned int v6; // ecx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v6 = RegOpenKeyExW(a3, a4, 0, samDesired, &phkResult);
  if ( !v6 )
  {
    v6 = ATL::CRegKey::Close(a2);
    *(_QWORD *)a2 = phkResult;
  }
  return v6;
}

```

## disassembly

```asm
0x180015f90  push    rbx
0x180015f92  sub     rsp, 40h
0x180015f96  mov     rax, r9
0x180015f99  mov     [rsp+48h+var_18], 0
0x180015fa2  mov     r9d, [rsp+48h+samDesired]; samDesired
0x180015fa7  lea     rcx, [rsp+48h+var_18]
0x180015fac  mov     r10, r8
0x180015faf  mov     [rsp+48h+phkResult], rcx; phkResult
0x180015fb4  mov     rbx, rdx
0x180015fb7  mov     rcx, r10; hKey
0x180015fba  xor     r8d, r8d; ulOptions
0x180015fbd  mov     rdx, rax; lpSubKey
0x180015fc0  call    cs:__imp_RegOpenKeyExW
0x180015fc6  mov     ecx, eax
0x180015fc8  test    eax, eax
0x180015fca  jnz     short loc_180015FDE
0x180015fcc  mov     rcx, rbx; this
0x180015fcf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015fd4  mov     ecx, eax
0x180015fd6  mov     rax, [rsp+48h+var_18]
0x180015fdb  mov     [rbx], rax
0x180015fde  mov     eax, ecx
0x180015fe0  add     rsp, 40h
0x180015fe4  pop     rbx
0x180015fe5  retn
```
