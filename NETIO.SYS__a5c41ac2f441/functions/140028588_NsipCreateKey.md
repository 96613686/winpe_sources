# NsipCreateKey

- ea: `0x140028588`
- end: `0x140028622`
- name: `NsipCreateKey`
- size: `154`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *, void *, ACCESS_MASK DesiredAccess)`
- caller_count: `2`
- callee_count: `0`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140027ef4`
- `0x14005fc08`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140028609`
- `ntoskrnl!ZwCreateKey` at `0x140028609`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400285be`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400285be`

## pseudocode

```c
NTSTATUS __fastcall NsipCreateKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3, void *a4, ACCESS_MASK DesiredAccess)
{
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-1h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a3);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 1728;
  ObjectAttributes.SecurityDescriptor = a4;
  ObjectAttributes.SecurityQualityOfService = 0;
  return ZwCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x140028588  push    rbp
0x14002858a  push    rbx
0x14002858b  push    rsi
0x14002858c  push    rdi
0x14002858d  lea     rbp, [rsp-37h]
0x140028592  sub     rsp, 88h
0x140028599  xorps   xmm0, xmm0
0x14002859c  mov     rbx, rdx
0x14002859f  mov     rsi, rcx
0x1400285a2  xor     eax, eax
0x1400285a4  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400285a8  mov     rdx, r8; SourceString
0x1400285ab  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1400285af  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1400285b3  mov     rdi, r9
0x1400285b6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400285ba  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400285be  call    cs:__imp_RtlInitUnicodeString
0x1400285c5  nop     dword ptr [rax+rax+00h]
0x1400285ca  mov     edx, [rbp+4Fh+DesiredAccess]; DesiredAccess
0x1400285cd  lea     rax, [rbp+4Fh+DestinationString]
0x1400285d1  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400285d5  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400285d9  xor     eax, eax
0x1400285db  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400285e2  mov     [rsp+0A0h+Disposition], rax; Disposition
0x1400285e7  xor     r9d, r9d; TitleIndex
0x1400285ea  mov     [rsp+0A0h+CreateOptions], eax; CreateOptions
0x1400285ee  mov     rcx, rsi; KeyHandle
0x1400285f1  mov     [rsp+0A0h+Class], rax; Class
0x1400285f6  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x1400285fa  mov     [rbp+4Fh+ObjectAttributes.Attributes], 6C0h
0x140028601  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], rdi
0x140028605  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x140028609  call    cs:__imp_ZwCreateKey
0x140028610  nop     dword ptr [rax+rax+00h]
0x140028615  add     rsp, 88h
0x14002861c  pop     rdi
0x14002861d  pop     rsi
0x14002861e  pop     rbx
0x14002861f  pop     rbp
0x140028620  retn
```
