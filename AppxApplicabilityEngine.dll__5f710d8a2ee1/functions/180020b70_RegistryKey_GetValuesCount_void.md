# RegistryKey::GetValuesCount(void)

- ea: `0x180020b70`
- end: `0x180020c12`
- name: `?GetValuesCount@RegistryKey@@UEBAKXZ`
- size: `162`
- prototype: `unsigned int __fastcall(RegistryKey *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x180020b70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020bd4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020bd4`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValuesCount(RegistryKey *this)
{
  HKEY v1; // rcx
  int v2; // eax
  bool v3; // sf
  DWORD v5; // [rsp+70h] [rbp+8h] BYREF
  int pExceptionObject; // [rsp+78h] [rbp+10h] BYREF

  v1 = (HKEY)*((_QWORD *)this + 8);
  if ( !v1 )
    return 0;
  v5 = 0;
  v2 = RegQueryInfoKeyW(v1, 0, 0, 0, 0, 0, 0, &v5, 0, 0, 0, 0);
  if ( v2 == 2 )
    return 0;
  v3 = v2 < 0;
  if ( v2 > 0 )
  {
    v2 = (unsigned __int16)v2 | 0x80070000;
    v3 = v2 < 0;
  }
  if ( v3 )
  {
    pExceptionObject = v2;
    throw (long *)&pExceptionObject;
  }
  return v5;
}

```

## disassembly

```asm
0x180020b70  mov     r11, rsp
0x180020b73  sub     rsp, 68h
0x180020b77  mov     rcx, [rcx+40h]; hKey
0x180020b7b  test    rcx, rcx
0x180020b7e  jz      loc_180020C0B
0x180020b84  mov     qword ptr [r11-10h], 0
0x180020b8c  lea     rax, [r11+8]
0x180020b90  mov     qword ptr [r11-18h], 0
0x180020b98  xor     r9d, r9d; lpReserved
0x180020b9b  mov     qword ptr [r11-20h], 0
0x180020ba3  xor     r8d, r8d; lpcchClass
0x180020ba6  mov     qword ptr [r11-28h], 0
0x180020bae  xor     edx, edx; lpClass
0x180020bb0  mov     [r11-30h], rax
0x180020bb4  mov     qword ptr [r11-38h], 0
0x180020bbc  mov     qword ptr [r11-40h], 0
0x180020bc4  mov     qword ptr [r11-48h], 0
0x180020bcc  mov     [rsp+68h+arg_0], 0
0x180020bd4  call    cs:__imp_RegQueryInfoKeyW
0x180020bda  cmp     eax, 2
0x180020bdd  jz      short loc_180020C0B
0x180020bdf  test    eax, eax
0x180020be1  jle     short loc_180020BED
0x180020be3  movzx   eax, ax
0x180020be6  or      eax, 80070000h
0x180020beb  test    eax, eax
0x180020bed  jns     short loc_180020C05
0x180020bef  lea     rdx, _TI1J; pThrowInfo
0x180020bf6  mov     [rsp+68h+pExceptionObject], eax
0x180020bfa  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180020bff  call    _CxxThrowException_0
0x180020c05  mov     eax, [rsp+68h+arg_0]
0x180020c09  jmp     short loc_180020C0D
0x180020c0b  xor     eax, eax
0x180020c0d  add     rsp, 68h
0x180020c11  retn
```
