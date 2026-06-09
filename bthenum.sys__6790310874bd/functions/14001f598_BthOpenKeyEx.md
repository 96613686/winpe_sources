# BthOpenKeyEx

- ea: `0x14001f598`
- end: `0x14001f5e3`
- name: `BthOpenKeyEx`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400072a8`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14001f5d1`
- `ntoskrnl!ZwOpenKey` at `0x14001f5d1`

## pseudocode

```c
NTSTATUS __fastcall BthOpenKeyEx(__int64 a1, struct _UNICODE_STRING *a2, void **a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.ObjectName = a2;
  v4.RootDirectory = 0;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 576;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0xF003Fu, &v4);
}

```

## disassembly

```asm
0x14001f598  mov     r11, rsp
0x14001f59b  sub     rsp, 58h
0x14001f59f  xor     ecx, ecx
0x14001f5a1  mov     [r11-28h], rdx
0x14001f5a5  mov     rax, r8
0x14001f5a8  mov     [r11-30h], rcx
0x14001f5ac  xorps   xmm0, xmm0
0x14001f5af  mov     qword ptr [r11-38h], 30h ; '0'
0x14001f5b7  mov     qword ptr [r11-20h], 240h
0x14001f5bf  lea     r8, [r11-38h]; ObjectAttributes
0x14001f5c3  mov     rcx, rax; KeyHandle
0x14001f5c6  mov     edx, 0F003Fh; DesiredAccess
0x14001f5cb  movdqu  [rsp+58h+var_18], xmm0
0x14001f5d1  call    cs:__imp_ZwOpenKey
0x14001f5d8  nop     dword ptr [rax+rax+00h]
0x14001f5dd  add     rsp, 58h
0x14001f5e1  retn
```
