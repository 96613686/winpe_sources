# ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000f620`
- end: `0x18000f671`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001b9c`
- `0x18001833c`
- `0x180019058`
- `0x180019528`

## callees

- `0x18000f620`
- `0x18000f678`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f64b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f64b`

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
0x18000f620  push    rbx
0x18000f622  sub     rsp, 40h
0x18000f626  mov     rbx, rcx
0x18000f629  mov     [rsp+48h+var_18], 0
0x18000f632  mov     rax, r8
0x18000f635  lea     rcx, [rsp+48h+var_18]
0x18000f63a  mov     r10, rdx
0x18000f63d  mov     [rsp+48h+phkResult], rcx; phkResult
0x18000f642  mov     rcx, r10; hKey
0x18000f645  xor     r8d, r8d; ulOptions
0x18000f648  mov     rdx, rax; lpSubKey
0x18000f64b  call    cs:__imp_RegOpenKeyExW
0x18000f651  mov     edx, eax
0x18000f653  test    eax, eax
0x18000f655  jnz     short loc_18000F669
0x18000f657  mov     rcx, rbx; this
0x18000f65a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f65f  mov     edx, eax
0x18000f661  mov     rax, [rsp+48h+var_18]
0x18000f666  mov     [rbx], rax
0x18000f669  mov     eax, edx
0x18000f66b  add     rsp, 40h
0x18000f66f  pop     rbx
0x18000f670  retn
```
