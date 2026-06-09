# CmRegUtilOpenExistingUcKey

- ea: `0x1400383a0`
- end: `0x14003840a`
- name: `CmRegUtilOpenExistingUcKey`
- size: `106`
- prototype: `NTSTATUS __fastcall(void *, struct _UNICODE_STRING *, ACCESS_MASK, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140038410`

## callees

- `0x1400383a0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400383e7`
- `ntoskrnl!ZwOpenKey` at `0x1400383e7`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilOpenExistingUcKey(void *a1, struct _UNICODE_STRING *a2, ACCESS_MASK a3, void **a4)
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp+10h] BYREF

  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.ObjectName = a2;
  KeyHandle = 0;
  *a4 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  if ( result >= 0 )
    *a4 = KeyHandle;
  return result;
}

```

## disassembly

```asm
0x1400383a0  mov     [rsp-8+arg_8], rbx
0x1400383a5  push    rbp
0x1400383a6  mov     rbp, rsp
0x1400383a9  sub     rsp, 50h
0x1400383ad  mov     eax, r8d
0x1400383b0  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400383b4  xor     r8d, r8d
0x1400383b7  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1400383bb  mov     [rbp+KeyHandle], r8
0x1400383bf  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400383c3  mov     [r9], r8
0x1400383c6  xorps   xmm0, xmm0
0x1400383c9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400383cd  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400383d5  mov     edx, eax; DesiredAccess
0x1400383d7  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400383df  mov     rbx, r9
0x1400383e2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400383e7  call    cs:__imp_ZwOpenKey
0x1400383ee  nop     dword ptr [rax+rax+00h]
0x1400383f3  test    eax, eax
0x1400383f5  js      short loc_1400383FE
0x1400383f7  mov     rcx, [rbp+KeyHandle]
0x1400383fb  mov     [rbx], rcx
0x1400383fe  mov     rbx, [rsp+50h+arg_8]
0x140038403  add     rsp, 50h
0x140038407  pop     rbp
0x140038408  retn
```
