# AiRegCreateKey

- ea: `0x140003134`
- end: `0x14000318f`
- name: `AiRegCreateKey`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140026944`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14000317d`
- `ntoskrnl!ZwCreateKey` at `0x14000317d`

## pseudocode

```c
NTSTATUS __fastcall AiRegCreateKey(void *a1, struct _UNICODE_STRING *a2, __int64 a3, void **a4)
{
  struct _OBJECT_ATTRIBUTES v5; // [rsp+40h] [rbp-38h] BYREF

  v5.RootDirectory = a1;
  v5.ObjectName = a2;
  *(_QWORD *)&v5.Length = 48;
  *(_QWORD *)&v5.Attributes = 576;
  *(_OWORD *)&v5.SecurityDescriptor = 0;
  return ZwCreateKey(a4, 0xF003Fu, &v5, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x140003134  mov     r11, rsp
0x140003137  sub     rsp, 78h
0x14000313b  xor     r8d, r8d
0x14000313e  mov     [r11-30h], rcx
0x140003142  mov     [r11-48h], r8
0x140003146  mov     rax, r9
0x140003149  mov     [r11-50h], r8d
0x14000314d  xorps   xmm0, xmm0
0x140003150  mov     [r11-28h], rdx
0x140003154  xor     r9d, r9d; TitleIndex
0x140003157  mov     [r11-58h], r8
0x14000315b  mov     edx, 0F003Fh; DesiredAccess
0x140003160  mov     qword ptr [r11-38h], 30h ; '0'
0x140003168  lea     r8, [r11-38h]; ObjectAttributes
0x14000316c  mov     qword ptr [r11-20h], 240h
0x140003174  mov     rcx, rax; KeyHandle
0x140003177  movdqu  [rsp+78h+var_18], xmm0
0x14000317d  call    cs:__imp_ZwCreateKey
0x140003184  nop     dword ptr [rax+rax+00h]
0x140003189  add     rsp, 78h
0x14000318d  retn
```
