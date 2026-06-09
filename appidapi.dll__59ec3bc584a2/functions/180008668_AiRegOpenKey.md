# AiRegOpenKey

- ea: `0x180008668`
- end: `0x1800086a9`
- name: `AiRegOpenKey`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800086b0`
- `0x18000879c`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000869e`
- `ntdll!NtOpenKey` at `0x18000869e`

## pseudocode

```c
NTSTATUS __fastcall AiRegOpenKey(__int64 a1, struct _UNICODE_STRING *a2, __int64 a3, void **a4)
{
  struct _OBJECT_ATTRIBUTES v5; // [rsp+20h] [rbp-38h] BYREF

  v5.ObjectName = a2;
  *(_QWORD *)&v5.Length = 48;
  v5.RootDirectory = 0;
  *(_QWORD *)&v5.Attributes = 576;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  return NtOpenKey(a4, 0x20019u, &v5);
}

```

## disassembly

```asm
0x180008668  mov     r11, rsp
0x18000866b  sub     rsp, 58h
0x18000866f  mov     [r11-28h], rdx
0x180008673  lea     r8, [r11-38h]; ObjectAttributes
0x180008677  xor     eax, eax
0x180008679  mov     qword ptr [r11-38h], 30h ; '0'
0x180008681  xorps   xmm0, xmm0
0x180008684  mov     [r11-30h], rax
0x180008688  mov     qword ptr [r11-20h], 240h
0x180008690  mov     edx, 20019h; DesiredAccess
0x180008695  mov     rcx, r9; KeyHandle
0x180008698  movdqu  [rsp+58h+var_18], xmm0
0x18000869e  call    cs:__imp_NtOpenKey
0x1800086a4  add     rsp, 58h
0x1800086a8  retn
```
