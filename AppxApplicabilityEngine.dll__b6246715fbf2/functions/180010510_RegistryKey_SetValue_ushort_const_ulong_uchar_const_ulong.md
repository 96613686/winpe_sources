# RegistryKey::SetValue(ushort const *,ulong,uchar const *,ulong)

- ea: `0x180010510`
- end: `0x18001057c`
- name: `?SetValue@RegistryKey@@AEAAXPEBGKPEBEK@Z`
- size: `108`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, DWORD, const unsigned __int8 *, DWORD cbData)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800104e0`
- `0x180020e30`

## callees

- `0x180010510`
- `0x1800106a8`
- `0x180013294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010547`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010547`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(
        HKEY *this,
        const unsigned __int16 *a2,
        DWORD a3,
        const unsigned __int8 *a4,
        DWORD cbData)
{
  int v9; // eax
  bool v10; // sf
  int pExceptionObject; // [rsp+60h] [rbp+8h] BYREF

  RegistryKey::EnsureKeyExists((RegistryKey *)this);
  v9 = RegSetValueExW(this[8], a2, 0, a3, a4, cbData);
  v10 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v10 = v9 < 0;
  }
  if ( v10 )
  {
    pExceptionObject = v9;
    throw (long *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180010510  push    rbx
0x180010512  push    rbp
0x180010513  push    rsi
0x180010514  push    rdi
0x180010515  sub     rsp, 38h
0x180010519  mov     rbx, r9
0x18001051c  mov     edi, r8d
0x18001051f  mov     rsi, rdx
0x180010522  mov     rbp, rcx
0x180010525  call    ?EnsureKeyExists@RegistryKey@@AEAAXXZ; RegistryKey::EnsureKeyExists(void)
0x18001052a  mov     eax, [rsp+58h+arg_20]
0x180010531  mov     r9d, edi; dwType
0x180010534  mov     rcx, [rbp+40h]; hKey
0x180010538  xor     r8d, r8d; Reserved
0x18001053b  mov     [rsp+58h+cbData], eax; cbData
0x18001053f  mov     rdx, rsi; lpValueName
0x180010542  mov     [rsp+58h+lpData], rbx; lpData
0x180010547  call    cs:__imp_RegSetValueExW
0x18001054d  test    eax, eax
0x18001054f  jle     short loc_18001055B
0x180010551  movzx   eax, ax
0x180010554  or      eax, 80070000h
0x180010559  test    eax, eax
0x18001055b  jns     short loc_180010573
0x18001055d  lea     rdx, _TI1J; pThrowInfo
0x180010564  mov     [rsp+58h+pExceptionObject], eax
0x180010568  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18001056d  call    _CxxThrowException_0
0x180010573  add     rsp, 38h
0x180010577  pop     rdi
0x180010578  pop     rsi
0x180010579  pop     rbp
0x18001057a  pop     rbx
0x18001057b  retn
```
