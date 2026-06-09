# RegKey::CreateSubKey(ushort const *,ulong,ushort *,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x18000e2cc`
- end: `0x18000e351`
- name: `?CreateSubKey@RegKey@@QEBA?AV1@PEBGKPEAGKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `133`
- prototype: `struct RegKey __high(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e3f8`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000e323`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e323`

## pseudocode

```c
__int64 __fastcall RegKey::CreateSubKey(__int64 a1, __int64 a2, const WCHAR *a3, DWORD a4)
{
  HKEY v4; // rcx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  __int64 result; // rax
  HKEY v9; // [rsp+60h] [rbp+8h] BYREF
  DWORD v10; // [rsp+78h] [rbp+20h] BYREF

  v10 = a4;
  v4 = *(HKEY *)(a1 + 8);
  v10 = 0;
  v9 = 0;
  v6 = RegCreateKeyExW(v4, a3, 0, 0, 0, 0x20006u, 0, &v9, &v10);
  v7 = 0;
  if ( !v6 )
    v7 = v9;
  *(_QWORD *)(a2 + 8) = v7;
  *(_QWORD *)a2 = &RegKey::`vftable';
  result = a2;
  *(_DWORD *)(a2 + 16) = 131078;
  return result;
}

```

## disassembly

```asm
0x18000e2cc  mov     r11, rsp
0x18000e2cf  mov     [r11+20h], r9d
0x18000e2d3  push    rbx
0x18000e2d4  sub     rsp, 50h
0x18000e2d8  mov     rcx, [rcx+8]; hKey
0x18000e2dc  mov     rbx, rdx
0x18000e2df  lea     rdx, [r11+20h]
0x18000e2e3  mov     [rsp+58h+arg_18], 0
0x18000e2eb  mov     [r11-18h], rdx
0x18000e2ef  mov     rax, r8
0x18000e2f2  lea     rdx, [r11+8]
0x18000e2f6  mov     qword ptr [r11+8], 0
0x18000e2fe  mov     [r11-20h], rdx
0x18000e302  xor     r9d, r9d; lpClass
0x18000e305  mov     qword ptr [r11-28h], 0
0x18000e30d  xor     r8d, r8d; Reserved
0x18000e310  mov     [rsp+58h+samDesired], 20006h; samDesired
0x18000e318  mov     rdx, rax; lpSubKey
0x18000e31b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000e323  call    cs:__imp_RegCreateKeyExW
0x18000e329  xor     ecx, ecx
0x18000e32b  test    eax, eax
0x18000e32d  lea     rax, ??_7RegKey@@6B@; const RegKey::`vftable'
0x18000e334  cmovz   rcx, [rsp+58h+arg_0]
0x18000e33a  mov     [rbx+8], rcx
0x18000e33e  mov     [rbx], rax
0x18000e341  mov     rax, rbx
0x18000e344  mov     dword ptr [rbx+10h], 20006h
0x18000e34b  add     rsp, 50h
0x18000e34f  pop     rbx
0x18000e350  retn
```
