# CmRegUtilCreateUcKey

- ea: `0x14000e60c`
- end: `0x14000e6b0`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e6b8`

## callees

- `0x14000e60c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x14000e674`
- `ntoskrnl!ZwCreateKey` at `0x14000e674`

## pseudocode

```c
__int64 __fastcall CmRegUtilCreateUcKey(
        void *a1,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS v7; // r8d
  void *v8; // rdx
  ULONG v9; // ecx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+28h] BYREF

  ObjectAttributes.RootDirectory = a1;
  Disposition = 0;
  KeyHandle = 0;
  ObjectAttributes.SecurityDescriptor = a5;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  v7 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( v7 >= 0 )
  {
    v9 = Disposition;
    v8 = KeyHandle;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  *a7 = v8;
  if ( a6 )
    *a6 = v9;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000e60c  mov     [rsp-8+arg_18], r9d
0x14000e611  push    rbp
0x14000e612  mov     rbp, rsp
0x14000e615  sub     rsp, 70h
0x14000e619  xor     eax, eax
0x14000e61b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14000e61f  mov     [rbp+arg_18], eax
0x14000e622  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000e626  mov     [rbp+KeyHandle], rax
0x14000e62a  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000e62e  mov     rax, [rbp+arg_20]
0x14000e632  xor     r9d, r9d; TitleIndex
0x14000e635  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x14000e639  lea     rax, [rbp+arg_18]
0x14000e63d  mov     [rsp+70h+Disposition], rax; Disposition
0x14000e642  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x14000e646  mov     edx, 0F003Fh; DesiredAccess
0x14000e64b  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14000e653  mov     [rsp+70h+Class], 0; Class
0x14000e65c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e664  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x14000e66c  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x14000e674  call    cs:__imp_ZwCreateKey
0x14000e67b  nop     dword ptr [rax+rax+00h]
0x14000e680  mov     r8d, eax
0x14000e683  test    eax, eax
0x14000e685  jns     short loc_14000E68D
0x14000e687  xor     edx, edx
0x14000e689  xor     ecx, ecx
0x14000e68b  jmp     short loc_14000E694
0x14000e68d  mov     ecx, [rbp+arg_18]
0x14000e690  mov     rdx, [rbp+KeyHandle]
0x14000e694  mov     rax, [rbp+arg_30]
0x14000e698  mov     [rax], rdx
0x14000e69b  mov     rax, [rbp+arg_28]
0x14000e69f  test    rax, rax
0x14000e6a2  jz      short loc_14000E6A6
0x14000e6a4  mov     [rax], ecx
0x14000e6a6  mov     eax, r8d
0x14000e6a9  add     rsp, 70h
0x14000e6ad  pop     rbp
0x14000e6ae  retn
```
