# appv::shared::kernel::open_process_handle

- ea: `0x18000e534`
- end: `0x18000e582`
- name: `appv::shared::kernel::open_process_handle`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180002cb4`
- `0x1800098d8`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x18000e570`
- `ntoskrnl!ZwOpenProcess` at `0x18000e570`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::open_process_handle(void **a1, void *a2)
{
  struct _CLIENT_ID v3; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v4; // [rsp+30h] [rbp-38h] BYREF

  v3.UniqueProcess = a2;
  v4.RootDirectory = 0;
  v4.ObjectName = 0;
  *(_QWORD *)&v4.Length = 48;
  *(_QWORD *)&v4.Attributes = 512;
  *(_OWORD *)&v4.SecurityDescriptor = 0;
  v3.UniqueThread = 0;
  return ZwOpenProcess(a1, 0, &v4, &v3);
}

```

## disassembly

```asm
0x18000e534  mov     r11, rsp
0x18000e537  sub     rsp, 68h
0x18000e53b  xor     eax, eax
0x18000e53d  mov     [r11-48h], rdx
0x18000e541  xorps   xmm0, xmm0
0x18000e544  mov     [r11-30h], rax
0x18000e548  mov     [r11-28h], rax
0x18000e54c  lea     r9, [r11-48h]; ClientId
0x18000e550  mov     qword ptr [r11-38h], 30h ; '0'
0x18000e558  lea     r8, [r11-38h]; ObjectAttributes
0x18000e55c  mov     qword ptr [r11-20h], 200h
0x18000e564  xor     edx, edx; DesiredAccess
0x18000e566  movdqu  [rsp+68h+var_18], xmm0
0x18000e56c  mov     [r11-40h], rax
0x18000e570  call    cs:__imp_ZwOpenProcess
0x18000e577  nop     dword ptr [rax+rax+00h]
0x18000e57c  add     rsp, 68h
0x18000e580  retn
```
