# RegReader::QueryStringValue(ushort *,ushort const *,ulong)

- ea: `0x180016124`
- end: `0x180016195`
- name: `?QueryStringValue@RegReader@@QEAAJPEAGPEBGK@Z`
- size: `113`
- prototype: `__int64 __fastcall(HKEY *this, BYTE *, const unsigned __int16 *, DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001094c`
- `0x180013d40`
- `0x1800140b0`

## callees

- `0x180016124`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016164`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016164`

## pseudocode

```c
__int64 __fastcall RegReader::QueryStringValue(HKEY *this, BYTE *a2, const unsigned __int16 *a3, DWORD a4)
{
  HKEY v4; // rcx
  LSTATUS v6; // edx
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+20h] BYREF

  v9 = a4;
  v8 = 1;
  *(_WORD *)a2 = 0;
  v4 = *this;
  v9 = 520;
  v6 = RegQueryValueExW(v4, a3, 0, &v8, a2, &v9);
  *(_WORD *)&a2[v6 == 0 ? 0x206 : 0] = 0;
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016124  mov     r11, rsp
0x180016127  mov     [r11+20h], r9d
0x18001612b  push    rbx
0x18001612c  sub     rsp, 30h
0x180016130  xor     eax, eax
0x180016132  mov     [rsp+38h+arg_0], 1
0x18001613a  mov     [rdx], ax
0x18001613d  lea     r9, [r11+8]; lpType
0x180016141  mov     rcx, [rcx]; hKey
0x180016144  lea     rax, [r11+20h]
0x180016148  mov     r10, r8
0x18001614b  mov     [r11-10h], rax
0x18001614f  mov     [r11-18h], rdx
0x180016153  mov     rbx, rdx
0x180016156  mov     rdx, r10; lpValueName
0x180016159  mov     [rsp+38h+arg_18], 208h
0x180016161  xor     r8d, r8d; lpReserved
0x180016164  call    cs:__imp_RegQueryValueExW
0x18001616a  mov     edx, eax
0x18001616c  neg     eax
0x18001616e  sbb     rcx, rcx
0x180016171  xor     eax, eax
0x180016173  not     rcx
0x180016176  and     ecx, 206h
0x18001617c  mov     [rcx+rbx], ax
0x180016180  test    edx, edx
0x180016182  jle     short loc_18001618D
0x180016184  movzx   edx, dx
0x180016187  or      edx, 80070000h
0x18001618d  mov     eax, edx
0x18001618f  add     rsp, 30h
0x180016193  pop     rbx
0x180016194  retn
```
