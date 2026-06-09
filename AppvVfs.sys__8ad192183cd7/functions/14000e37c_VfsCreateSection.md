# VfsCreateSection

- ea: `0x14000e37c`
- end: `0x14000e431`
- name: `VfsCreateSection`
- size: `181`
- prototype: `NTSTATUS __fastcall(HANDLE FileHandle, char, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000e18c`

## callees

- `0x14000e37c`

## import_xrefs

- `ntoskrnl!ZwCreateSection` at `0x14000e3de`
- `ntoskrnl!ZwCreateSection` at `0x14000e41b`
- `ntoskrnl!ZwCreateSection` at `0x14000e3de`
- `ntoskrnl!ZwCreateSection` at `0x14000e41b`

## pseudocode

```c
NTSTATUS __fastcall VfsCreateSection(HANDLE FileHandle, char a2, void **a3)
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+B8h] [rbp+40h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  MaximumSize.QuadPart = 1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwCreateSection(a3, 5u, &ObjectAttributes, &MaximumSize, 2u, 0x8000000u, FileHandle);
  if ( result == -1073741760 && !a2 )
    return ZwCreateSection(a3, 5u, &ObjectAttributes, &MaximumSize, 4u, 0x8000000u, FileHandle);
  return result;
}

```

## disassembly

```asm
0x14000e37c  push    rbp
0x14000e37e  push    rbx
0x14000e37f  push    rsi
0x14000e380  push    rdi
0x14000e381  mov     rbp, rsp
0x14000e384  sub     rsp, 78h
0x14000e388  xor     eax, eax
0x14000e38a  mov     [rsp+78h+FileHandle], rcx; FileHandle
0x14000e38f  mov     rbx, r8
0x14000e392  mov     [rsp+78h+AllocationAttributes], 8000000h; AllocationAttributes
0x14000e39a  mov     sil, dl
0x14000e39d  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e3a5  mov     rdi, rcx
0x14000e3a8  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000e3b0  xorps   xmm0, xmm0
0x14000e3b3  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000e3b7  lea     edx, [rax+5]; DesiredAccess
0x14000e3ba  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000e3be  lea     r9, [rbp+MaximumSize]; MaximumSize
0x14000e3c2  mov     qword ptr [rbp+MaximumSize], 1
0x14000e3ca  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e3ce  mov     [rsp+78h+SectionPageProtection], 2; SectionPageProtection
0x14000e3d6  mov     rcx, rbx; SectionHandle
0x14000e3d9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e3de  call    cs:__imp_ZwCreateSection
0x14000e3e5  nop     dword ptr [rax+rax+00h]
0x14000e3ea  cmp     eax, 0C0000040h
0x14000e3ef  jnz     short loc_14000E427
0x14000e3f1  test    sil, sil
0x14000e3f4  jnz     short loc_14000E427
0x14000e3f6  mov     [rsp+78h+FileHandle], rdi; FileHandle
0x14000e3fb  lea     r9, [rbp+MaximumSize]; MaximumSize
0x14000e3ff  mov     [rsp+78h+AllocationAttributes], 8000000h; AllocationAttributes
0x14000e407  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e40b  mov     edx, 5; DesiredAccess
0x14000e410  mov     [rsp+78h+SectionPageProtection], 4; SectionPageProtection
0x14000e418  mov     rcx, rbx; SectionHandle
0x14000e41b  call    cs:__imp_ZwCreateSection
0x14000e422  nop     dword ptr [rax+rax+00h]
0x14000e427  add     rsp, 78h
0x14000e42b  pop     rdi
0x14000e42c  pop     rsi
0x14000e42d  pop     rbx
0x14000e42e  pop     rbp
0x14000e42f  retn
```
