# InvCacheControl

- ea: `0x1800289f0`
- end: `0x180028a94`
- name: `InvCacheControl`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011480`
- `0x1800130a0`

## callees

- `0x1800289f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180028a68`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180028a68`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180028a76`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180028a76`

## pseudocode

```c
LSTATUS __fastcall InvCacheControl(__int64 a1, int a2, DWORD *a3)
{
  __int64 v3; // rcx
  LSTATUS result; // eax

  if ( !a1 )
    return -2147024809;
  if ( *(_DWORD *)a1 != 1 )
    return -2147024809;
  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 )
    return -2147024809;
  if ( a2 )
  {
    if ( a2 == 1 && a3 )
    {
      result = RegQueryInfoKeyW(*(HKEY *)(v3 + 8), 0, 0, 0, a3, 0, 0, 0, 0, 0, 0, 0);
      goto LABEL_9;
    }
    return -2147024809;
  }
  result = RegDeleteTreeW(*(HKEY *)(v3 + 8), 0);
LABEL_9:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800289f0  mov     rax, rsp
0x1800289f3  sub     rsp, 68h
0x1800289f7  test    rcx, rcx
0x1800289fa  jz      loc_180028A8A
0x180028a00  cmp     dword ptr [rcx], 1
0x180028a03  jnz     loc_180028A8A
0x180028a09  mov     rcx, [rcx+8]
0x180028a0d  test    rcx, rcx
0x180028a10  jz      short loc_180028A8A
0x180028a12  test    edx, edx
0x180028a14  jz      short loc_180028A70
0x180028a16  cmp     edx, 1
0x180028a19  jnz     short loc_180028A8A
0x180028a1b  test    r8, r8
0x180028a1e  jz      short loc_180028A8A
0x180028a20  mov     rcx, [rcx+8]; hKey
0x180028a24  xor     r9d, r9d; lpReserved
0x180028a27  mov     qword ptr [rax-10h], 0
0x180028a2f  xor     edx, edx; lpClass
0x180028a31  mov     qword ptr [rax-18h], 0
0x180028a39  mov     qword ptr [rax-20h], 0
0x180028a41  mov     qword ptr [rax-28h], 0
0x180028a49  mov     qword ptr [rax-30h], 0
0x180028a51  mov     qword ptr [rax-38h], 0
0x180028a59  mov     qword ptr [rax-40h], 0
0x180028a61  mov     [rax-48h], r8
0x180028a65  xor     r8d, r8d; lpcchClass
0x180028a68  call    cs:__imp_RegQueryInfoKeyW
0x180028a6e  jmp     short loc_180028A7C
0x180028a70  mov     rcx, [rcx+8]; hKey
0x180028a74  xor     edx, edx; lpSubKey
0x180028a76  call    cs:__imp_RegDeleteTreeW
0x180028a7c  test    eax, eax
0x180028a7e  jle     short loc_180028A8F
0x180028a80  movzx   eax, ax
0x180028a83  or      eax, 80070000h
0x180028a88  jmp     short loc_180028A8F
0x180028a8a  mov     eax, 80070057h
0x180028a8f  add     rsp, 68h
0x180028a93  retn
```
