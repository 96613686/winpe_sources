# AslRegistryOpenKey_UStr

- ea: `0x180052174`
- end: `0x1800521b6`
- name: `AslRegistryOpenKey_UStr`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800520f8`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1800521ab`
- `ntdll!ZwOpenKey` at `0x1800521ab`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenKey_UStr(void **a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.ObjectName = a2;
  *(_QWORD *)&v4.Length = 48;
  v4.RootDirectory = 0;
  *a1 = 0;
  *(_QWORD *)&v4.Attributes = 64;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a1, a3, &v4);
}

```

## disassembly

```asm
0x180052174  mov     r11, rsp
0x180052177  sub     rsp, 58h
0x18005217b  mov     eax, r8d
0x18005217e  mov     [r11-28h], rdx
0x180052182  xor     r8d, r8d
0x180052185  mov     qword ptr [r11-38h], 30h ; '0'
0x18005218d  mov     [r11-30h], r8
0x180052191  xorps   xmm0, xmm0
0x180052194  mov     [rcx], r8
0x180052197  mov     edx, eax; DesiredAccess
0x180052199  mov     qword ptr [r11-20h], 40h ; '@'
0x1800521a1  lea     r8, [r11-38h]; ObjectAttributes
0x1800521a5  movdqu  [rsp+58h+var_18], xmm0
0x1800521ab  call    cs:__imp_ZwOpenKey
0x1800521b1  add     rsp, 58h
0x1800521b5  retn
```
