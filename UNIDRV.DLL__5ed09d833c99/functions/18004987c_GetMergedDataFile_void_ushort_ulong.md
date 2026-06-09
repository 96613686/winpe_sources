# GetMergedDataFile(void *,ushort *,ulong)

- ea: `0x18004987c`
- end: `0x1800498c5`
- name: `?GetMergedDataFile@@YAJPEAXPEAGK@Z`
- size: `73`
- prototype: `int __fastcall(void *, BYTE *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180040ef0`

## callees

- `0x18004987c`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x1800498a7`
- `WINSPOOL!GetPrinterDataW` at `0x1800498a7`

## string_xrefs

- `0x180049899`: `V4_Merged_ConfigFile_Name`

## pseudocode

```c
int __fastcall GetMergedDataFile(void *a1, BYTE *a2, int a3)
{
  int result; // eax
  DWORD pcbNeeded; // [rsp+50h] [rbp+18h] BYREF

  pcbNeeded = 0;
  result = GetPrinterDataW(a1, (LPWSTR)L"V4_Merged_ConfigFile_Name", 0, a2, 2 * a3, &pcbNeeded);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004987c  sub     rsp, 38h
0x180049880  lea     eax, [r8+r8]
0x180049884  mov     [rsp+38h+arg_10], 0
0x18004988c  lea     r8, [rsp+38h+arg_10]
0x180049891  mov     r9, rdx; pData
0x180049894  mov     [rsp+38h+pcbNeeded], r8; pcbNeeded
0x180049899  lea     rdx, aV4MergedConfig; "V4_Merged_ConfigFile_Name"
0x1800498a0  xor     r8d, r8d; pType
0x1800498a3  mov     [rsp+38h+nSize], eax; nSize
0x1800498a7  call    cs:__imp_GetPrinterDataW
0x1800498ae  nop     dword ptr [rax+rax+00h]
0x1800498b3  test    eax, eax
0x1800498b5  jle     short loc_1800498BF
0x1800498b7  movzx   eax, ax
0x1800498ba  or      eax, 80070000h
0x1800498bf  add     rsp, 38h
0x1800498c3  retn
```
