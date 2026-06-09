# RegKey::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18000e358`
- end: `0x18000e391`
- name: `?Open@RegKey@@IEAAXPEAUHKEY__@@PEBGK@Z`
- size: `57`
- prototype: `void(RegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e1a8`
- `0x18000e238`

## callees

- `0x18000e358`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000e37a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e37a`

## pseudocode

```c
void __fastcall RegKey::Open(RegKey *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  _QWORD *v4; // rbx

  *((_DWORD *)this + 4) = a4;
  v4 = (_QWORD *)((char *)this + 8);
  if ( RegOpenKeyExW(a2, a3, 0, a4, (PHKEY)this + 1) )
    *v4 = 0;
}

```

## disassembly

```asm
0x18000e358  push    rbx
0x18000e35a  sub     rsp, 30h
0x18000e35e  mov     rax, r8
0x18000e361  mov     [rcx+10h], r9d
0x18000e365  mov     r10, rdx
0x18000e368  lea     rbx, [rcx+8]
0x18000e36c  mov     rdx, rax; lpSubKey
0x18000e36f  mov     [rsp+38h+phkResult], rbx; phkResult
0x18000e374  mov     rcx, r10; hKey
0x18000e377  xor     r8d, r8d; ulOptions
0x18000e37a  call    cs:__imp_RegOpenKeyExW
0x18000e380  test    eax, eax
0x18000e382  jz      short loc_18000E38B
0x18000e384  mov     qword ptr [rbx], 0
0x18000e38b  add     rsp, 30h
0x18000e38f  pop     rbx
0x18000e390  retn
```
