# AiRegOpenKey

- ea: `0x180008bcc`
- end: `0x180008c0d`
- name: `AiRegOpenKey`
- size: `65`
- prototype: `NTSTATUS __fastcall(__int64, struct _UNICODE_STRING *, ACCESS_MASK, void **)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002994`
- `0x180005154`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180008c02`
- `ntdll!NtOpenKey` at `0x180008c02`

## pseudocode

```c
NTSTATUS __fastcall AiRegOpenKey(__int64 a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3, void **a4)
{
  struct _OBJECT_ATTRIBUTES v5; // [rsp+20h] [rbp-38h] BYREF

  v5.ObjectName = a2;
  v5.RootDirectory = 0;
  *(_QWORD *)&v5.Length = 48;
  *(_QWORD *)&v5.Attributes = 576;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  return NtOpenKey(a4, a3, &v5);
}

```

## disassembly

```asm
0x180008bcc  mov     r11, rsp
0x180008bcf  sub     rsp, 58h
0x180008bd3  xor     ecx, ecx
0x180008bd5  mov     [r11-28h], rdx
0x180008bd9  mov     eax, r8d
0x180008bdc  mov     [r11-30h], rcx
0x180008be0  xorps   xmm0, xmm0
0x180008be3  mov     qword ptr [r11-38h], 30h ; '0'
0x180008beb  mov     qword ptr [r11-20h], 240h
0x180008bf3  lea     r8, [r11-38h]; ObjectAttributes
0x180008bf7  mov     rcx, r9; KeyHandle
0x180008bfa  mov     edx, eax; DesiredAccess
0x180008bfc  movdqu  [rsp+58h+var_18], xmm0
0x180008c02  call    cs:__imp_NtOpenKey
0x180008c08  add     rsp, 58h
0x180008c0c  retn
```
