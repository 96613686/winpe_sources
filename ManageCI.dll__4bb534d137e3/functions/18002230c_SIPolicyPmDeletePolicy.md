# SIPolicyPmDeletePolicy

- ea: `0x18002230c`
- end: `0x180022345`
- name: `SIPolicyPmDeletePolicy`
- size: `57`
- prototype: `NTSTATUS __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021a38`
- `0x180021e34`
- `0x180021f5c`

## import_xrefs

- `ntdll!NtDeleteFile` at `0x18002233a`
- `ntdll!NtDeleteFile` at `0x18002233a`

## pseudocode

```c
NTSTATUS __fastcall SIPolicyPmDeletePolicy(__int64 a1, struct _UNICODE_STRING *a2)
{
  struct _OBJECT_ATTRIBUTES v3; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)&v3.Length = 48;
  v3.RootDirectory = 0;
  *(_QWORD *)&v3.Attributes = 64;
  v3.ObjectName = a2;
  *(_OWORD *)&v3.SecurityDescriptor = 0;
  return NtDeleteFile(&v3);
}

```

## disassembly

```asm
0x18002230c  mov     r11, rsp
0x18002230f  sub     rsp, 58h
0x180022313  xor     eax, eax
0x180022315  mov     qword ptr [r11-38h], 30h ; '0'
0x18002231d  xorps   xmm0, xmm0
0x180022320  mov     [r11-30h], rax
0x180022324  mov     qword ptr [r11-20h], 40h ; '@'
0x18002232c  lea     rcx, [r11-38h]; ObjectAttributes
0x180022330  mov     [r11-28h], rdx
0x180022334  movdqu  [rsp+58h+var_18], xmm0
0x18002233a  call    cs:__imp_NtDeleteFile
0x180022340  add     rsp, 58h
0x180022344  retn
```
