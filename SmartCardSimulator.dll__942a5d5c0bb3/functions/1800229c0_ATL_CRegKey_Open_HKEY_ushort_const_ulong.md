# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x1800229c0`
- end: `0x180022a17`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `87`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021b34`

## callees

- `0x1800220d4`
- `0x1800229c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800229f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800229f1`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v4;
}

```

## disassembly

```asm
0x1800229c0  push    rbx
0x1800229c2  sub     rsp, 40h
0x1800229c6  mov     rbx, rcx
0x1800229c9  mov     [rsp+48h+var_18], 0
0x1800229d2  mov     rax, r8
0x1800229d5  lea     rcx, [rsp+48h+var_18]
0x1800229da  mov     r10, rdx
0x1800229dd  mov     [rsp+48h+phkResult], rcx; phkResult
0x1800229e2  mov     rcx, r10; hKey
0x1800229e5  mov     r9d, 20019h; samDesired
0x1800229eb  xor     r8d, r8d; ulOptions
0x1800229ee  mov     rdx, rax; lpSubKey
0x1800229f1  call    cs:__imp_RegOpenKeyExW
0x1800229f7  mov     edx, eax
0x1800229f9  test    eax, eax
0x1800229fb  jnz     short loc_180022A0F
0x1800229fd  mov     rcx, rbx; this
0x180022a00  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022a05  mov     edx, eax
0x180022a07  mov     rax, [rsp+48h+var_18]
0x180022a0c  mov     [rbx], rax
0x180022a0f  mov     eax, edx
0x180022a11  add     rsp, 40h
0x180022a15  pop     rbx
0x180022a16  retn
```
