# _ReplaceAppInfoField(_AppInfoData *,ulong,ushort const *,ushort * *)

- ea: `0x18002ca1c`
- end: `0x18002ca71`
- name: `?_ReplaceAppInfoField@@YAXPEAU_AppInfoData@@KPEBGPEAPEAG@Z`
- size: `85`
- prototype: `void(struct _AppInfoData *, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a3e0`
- `0x18002ca78`
- `0x18002cbb4`

## callees

- `0x18002ca1c`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x18002ca43`
- `SHCORE!SHStrDupW` at `0x18002ca43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ca50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ca50`

## pseudocode

```c
void __fastcall _ReplaceAppInfoField(struct _AppInfoData *a1, int a2, const unsigned __int16 *a3, LPVOID *a4)
{
  LPWSTR v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  if ( SHStrDupW(a3, &v7) >= 0 )
  {
    CoTaskMemFree(*a4);
    *a4 = v7;
    a1->dwMask |= a2;
  }
}

```

## disassembly

```asm
0x18002ca1c  mov     rax, rsp
0x18002ca1f  mov     [rax+8], rbx
0x18002ca23  mov     [rax+10h], rsi
0x18002ca27  push    rdi
0x18002ca28  sub     rsp, 30h
0x18002ca2c  mov     esi, edx
0x18002ca2e  mov     qword ptr [rax-18h], 0
0x18002ca36  mov     rdi, rcx
0x18002ca39  lea     rdx, [rax-18h]; ppwsz
0x18002ca3d  mov     rcx, r8; psz
0x18002ca40  mov     rbx, r9
0x18002ca43  call    cs:__imp_SHStrDupW
0x18002ca49  test    eax, eax
0x18002ca4b  js      short loc_18002CA61
0x18002ca4d  mov     rcx, [rbx]; pv
0x18002ca50  call    cs:__imp_CoTaskMemFree
0x18002ca56  mov     rax, [rsp+38h+var_18]
0x18002ca5b  mov     [rbx], rax
0x18002ca5e  or      [rdi+4], esi
0x18002ca61  mov     rbx, [rsp+38h+arg_0]
0x18002ca66  mov     rsi, [rsp+38h+arg_8]
0x18002ca6b  add     rsp, 30h
0x18002ca6f  pop     rdi
0x18002ca70  retn
```
