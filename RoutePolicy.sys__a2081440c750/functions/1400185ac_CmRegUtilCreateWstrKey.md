# CmRegUtilCreateWstrKey

- ea: `0x1400185ac`
- end: `0x140018677`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140017e48`
- `0x140018330`

## callees

- `0x140008c0c`
- `0x1400185ac`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140018638`
- `ntoskrnl!ZwCreateKey` at `0x140018638`

## pseudocode

```c
NTSTATUS __fastcall CmRegUtilCreateWstrKey(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        ULONG a4,
        void *a5,
        ULONG *a6,
        _QWORD *a7)
{
  NTSTATUS result; // eax
  void *v8; // r10
  NTSTATUS v9; // r8d
  void *v10; // rdx
  ULONG v11; // ecx
  void *KeyHandle; // [rsp+40h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+7h] BYREF
  ULONG Disposition; // [rsp+B8h] [rbp+67h] BYREF

  Disposition = a4;
  DestinationString = 0;
  result = WdmlibRtlInitUnicodeStringEx(&DestinationString, a2);
  if ( result >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    Disposition = 0;
    KeyHandle = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = a5;
    ObjectAttributes.RootDirectory = v8;
    ObjectAttributes.SecurityQualityOfService = 0;
    v9 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v9 >= 0 )
    {
      v11 = Disposition;
      v10 = KeyHandle;
    }
    else
    {
      v10 = 0;
      v11 = 0;
    }
    *a7 = v10;
    if ( a6 )
      *a6 = v11;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1400185ac  mov     [rsp-8+arg_18], r9d
0x1400185b1  push    rbp
0x1400185b2  lea     rbp, [rsp-3Fh]
0x1400185b7  sub     rsp, 90h
0x1400185be  mov     r10, rcx
0x1400185c1  xorps   xmm0, xmm0
0x1400185c4  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1400185c8  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1400185cc  call    WdmlibRtlInitUnicodeStringEx
0x1400185d1  test    eax, eax
0x1400185d3  js      loc_14001866D
0x1400185d9  xor     eax, eax
0x1400185db  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1400185e3  mov     [rbp+3Fh+arg_18], eax
0x1400185e6  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1400185ea  mov     [rbp+3Fh+KeyHandle], rax
0x1400185ee  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x1400185f2  lea     rax, [rbp+3Fh+DestinationString]
0x1400185f6  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1400185fe  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140018602  xor     r9d, r9d; TitleIndex
0x140018605  mov     rax, [rbp+3Fh+arg_20]
0x140018609  mov     edx, 0F003Fh; DesiredAccess
0x14001860e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x140018612  lea     rax, [rbp+3Fh+arg_18]
0x140018616  mov     [rsp+90h+Disposition], rax; Disposition
0x14001861b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x140018623  mov     [rsp+90h+Class], 0; Class
0x14001862c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x140018630  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x140018638  call    cs:__imp_ZwCreateKey
0x14001863f  nop     dword ptr [rax+rax+00h]
0x140018644  mov     r8d, eax
0x140018647  test    eax, eax
0x140018649  jns     short loc_140018651
0x14001864b  xor     edx, edx
0x14001864d  xor     ecx, ecx
0x14001864f  jmp     short loc_140018658
0x140018651  mov     ecx, [rbp+3Fh+arg_18]
0x140018654  mov     rdx, [rbp+3Fh+KeyHandle]
0x140018658  mov     rax, [rbp+3Fh+arg_30]
0x14001865c  mov     [rax], rdx
0x14001865f  mov     rax, [rbp+3Fh+arg_28]
0x140018663  test    rax, rax
0x140018666  jz      short loc_14001866A
0x140018668  mov     [rax], ecx
0x14001866a  mov     eax, r8d
0x14001866d  add     rsp, 90h
0x140018674  pop     rbp
0x140018675  retn
```
