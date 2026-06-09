# AiRegOpenKey

- ea: `0x1400331a0`
- end: `0x1400331e8`
- name: `AiRegOpenKey`
- size: `72`
- prototype: `NTSTATUS __fastcall(void *, struct _UNICODE_STRING *, ACCESS_MASK, void **)`
- caller_count: `11`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140001450`
- `0x140003198`
- `0x140025ba0`
- `0x1400261bc`
- `0x1400266d4`
- `0x140028c6c`
- `0x140028f80`
- `0x1400293ac`
- `0x14002948c`
- `0x1400295e8`
- `0x140038b34`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400331d6`
- `ntoskrnl!ZwOpenKey` at `0x1400331d6`

## pseudocode

```c
NTSTATUS __fastcall AiRegOpenKey(void *a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3, void **a4)
{
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF

  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  return ZwOpenKey(a4, a3, &ObjectAttributes);
}

```

## disassembly

```asm
0x1400331a0  sub     rsp, 58h
0x1400331a4  mov     eax, r8d
0x1400331a7  mov     [rsp+58h+ObjectAttributes.RootDirectory], rcx
0x1400331ac  mov     [rsp+58h+ObjectAttributes.ObjectName], rdx
0x1400331b1  lea     r8, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x1400331b6  xorps   xmm0, xmm0
0x1400331b9  mov     qword ptr [rsp+58h+ObjectAttributes.Length], 30h ; '0'
0x1400331c2  mov     edx, eax; DesiredAccess
0x1400331c4  mov     qword ptr [rsp+58h+ObjectAttributes.Attributes], 240h
0x1400331cd  mov     rcx, r9; KeyHandle
0x1400331d0  movdqu  xmmword ptr [rsp+58h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400331d6  call    cs:__imp_ZwOpenKey
0x1400331dd  nop     dword ptr [rax+rax+00h]
0x1400331e2  add     rsp, 58h
0x1400331e6  retn
```
