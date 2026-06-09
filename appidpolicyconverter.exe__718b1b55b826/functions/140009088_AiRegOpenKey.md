# AiRegOpenKey

- ea: `0x140009088`
- end: `0x1400090c9`
- name: `AiRegOpenKey`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400090d0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1400090be`
- `ntdll!NtOpenKey` at `0x1400090be`

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
  return NtOpenKey(a4, 0x20006u, &v5);
}

```

## disassembly

```asm
0x140009088  mov     r11, rsp
0x14000908b  sub     rsp, 58h
0x14000908f  mov     [r11-28h], rdx
0x140009093  lea     r8, [r11-38h]; ObjectAttributes
0x140009097  xor     eax, eax
0x140009099  mov     qword ptr [r11-38h], 30h ; '0'
0x1400090a1  xorps   xmm0, xmm0
0x1400090a4  mov     [r11-30h], rax
0x1400090a8  mov     qword ptr [r11-20h], 240h
0x1400090b0  mov     edx, 20006h; DesiredAccess
0x1400090b5  mov     rcx, r9; KeyHandle
0x1400090b8  movdqu  [rsp+58h+var_18], xmm0
0x1400090be  call    cs:__imp_NtOpenKey
0x1400090c4  add     rsp, 58h
0x1400090c8  retn
```
