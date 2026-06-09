# OpenRegistryKey

- ea: `0x18000d2c4`
- end: `0x18000d30f`
- name: `OpenRegistryKey`
- size: `75`
- prototype: `NTSTATUS __fastcall(__int64, struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d074`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18000d2fd`
- `ntdll!ZwOpenKey` at `0x18000d2fd`

## pseudocode

```c
NTSTATUS __fastcall OpenRegistryKey(__int64 a1, struct _UNICODE_STRING *a2, void **a3)
{
  struct _OBJECT_ATTRIBUTES v4; // [rsp+20h] [rbp-38h] BYREF

  v4.ObjectName = a2;
  v4.RootDirectory = 0;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 576;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  return ZwOpenKey(a3, 0x2000000u, &v4);
}

```

## disassembly

```asm
0x18000d2c4  mov     r11, rsp
0x18000d2c7  sub     rsp, 58h
0x18000d2cb  xor     ecx, ecx
0x18000d2cd  mov     [r11-28h], rdx
0x18000d2d1  mov     rax, r8
0x18000d2d4  mov     [r11-30h], rcx
0x18000d2d8  xorps   xmm0, xmm0
0x18000d2db  mov     qword ptr [r11-38h], 30h ; '0'
0x18000d2e3  mov     qword ptr [r11-20h], 240h
0x18000d2eb  lea     r8, [r11-38h]; ObjectAttributes
0x18000d2ef  mov     rcx, rax; KeyHandle
0x18000d2f2  mov     edx, 2000000h; DesiredAccess
0x18000d2f7  movdqu  [rsp+58h+var_18], xmm0
0x18000d2fd  call    cs:__imp_ZwOpenKey
0x18000d304  nop     dword ptr [rax+rax+00h]
0x18000d309  add     rsp, 58h
0x18000d30d  retn
```
