# RegistryKey::GetDwordValue(ushort const *)

- ea: `0x1800205c0`
- end: `0x180020641`
- name: `?GetDwordValue@RegistryKey@@UEBAKPEBG@Z`
- size: `129`
- prototype: `__int64 __fastcall(RegistryKey *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013294`
- `0x1800205c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020603`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180020603`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetDwordValue(RegistryKey *this, const unsigned __int16 *a2)
{
  HKEY v2; // rcx
  int ValueW; // eax
  bool v4; // sf
  unsigned int v6; // [rsp+50h] [rbp+8h] BYREF
  DWORD v7; // [rsp+60h] [rbp+18h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp+20h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 8);
  if ( !v2 )
    return 0;
  v7 = 4;
  v6 = 0;
  ValueW = RegGetValueW(v2, 0, a2, 0x18u, 0, &v6, &v7);
  if ( ValueW == 2 )
    return 0;
  v4 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = ValueW < 0;
  }
  if ( v4 )
  {
    pExceptionObject = ValueW;
    throw (long *)&pExceptionObject;
  }
  return v6;
}

```

## disassembly

```asm
0x1800205c0  mov     r11, rsp
0x1800205c3  sub     rsp, 48h
0x1800205c7  mov     rcx, [rcx+40h]; hkey
0x1800205cb  test    rcx, rcx
0x1800205ce  jz      short loc_18002063A
0x1800205d0  lea     rax, [r11+18h]
0x1800205d4  mov     [rsp+48h+arg_10], 4
0x1800205dc  mov     [r11-18h], rax
0x1800205e0  mov     r8, rdx; lpValue
0x1800205e3  lea     rax, [r11+8]
0x1800205e7  mov     [rsp+48h+arg_0], 0
0x1800205ef  mov     [r11-20h], rax
0x1800205f3  mov     r9d, 18h; dwFlags
0x1800205f9  xor     edx, edx; lpSubKey
0x1800205fb  mov     qword ptr [r11-28h], 0
0x180020603  call    cs:__imp_RegGetValueW
0x180020609  cmp     eax, 2
0x18002060c  jz      short loc_18002063A
0x18002060e  test    eax, eax
0x180020610  jle     short loc_18002061C
0x180020612  movzx   eax, ax
0x180020615  or      eax, 80070000h
0x18002061a  test    eax, eax
0x18002061c  jns     short loc_180020634
0x18002061e  lea     rdx, _TI1J; pThrowInfo
0x180020625  mov     [rsp+48h+pExceptionObject], eax
0x180020629  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002062e  call    _CxxThrowException_0
0x180020634  mov     eax, [rsp+48h+arg_0]
0x180020638  jmp     short loc_18002063C
0x18002063a  xor     eax, eax
0x18002063c  add     rsp, 48h
0x180020640  retn
```
