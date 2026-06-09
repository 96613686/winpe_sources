# CmRegUtilCreateUcKey

- ea: `0x140038294`
- end: `0x140038338`
- name: `CmRegUtilCreateUcKey`
- size: `164`
- prototype: `__int64 __fastcall(void *, struct _UNICODE_STRING *, __int64, __int64, void *, ULONG *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140038340`

## callees

- `0x140038294`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1400382fc`
- `ntoskrnl!ZwCreateKey` at `0x1400382fc`

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
0x140038294  mov     [rsp-8+arg_18], r9d
0x140038299  push    rbp
0x14003829a  mov     rbp, rsp
0x14003829d  sub     rsp, 70h
0x1400382a1  xor     eax, eax
0x1400382a3  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1400382a7  mov     [rbp+arg_18], eax
0x1400382aa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400382ae  mov     [rbp+KeyHandle], rax
0x1400382b2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400382b6  mov     rax, [rbp+arg_20]
0x1400382ba  xor     r9d, r9d; TitleIndex
0x1400382bd  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x1400382c1  lea     rax, [rbp+arg_18]
0x1400382c5  mov     [rsp+70h+Disposition], rax; Disposition
0x1400382ca  mov     [rbp+ObjectAttributes.ObjectName], rdx
0x1400382ce  mov     edx, 0F003Fh; DesiredAccess
0x1400382d3  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x1400382db  mov     [rsp+70h+Class], 0; Class
0x1400382e4  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400382ec  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1400382f4  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x1400382fc  call    cs:__imp_ZwCreateKey
0x140038303  nop     dword ptr [rax+rax+00h]
0x140038308  mov     r8d, eax
0x14003830b  test    eax, eax
0x14003830d  jns     short loc_140038315
0x14003830f  xor     edx, edx
0x140038311  xor     ecx, ecx
0x140038313  jmp     short loc_14003831C
0x140038315  mov     ecx, [rbp+arg_18]
0x140038318  mov     rdx, [rbp+KeyHandle]
0x14003831c  mov     rax, [rbp+arg_30]
0x140038320  mov     [rax], rdx
0x140038323  mov     rax, [rbp+arg_28]
0x140038327  test    rax, rax
0x14003832a  jz      short loc_14003832E
0x14003832c  mov     [rax], ecx
0x14003832e  mov     eax, r8d
0x140038331  add     rsp, 70h
0x140038335  pop     rbp
0x140038336  retn
```
