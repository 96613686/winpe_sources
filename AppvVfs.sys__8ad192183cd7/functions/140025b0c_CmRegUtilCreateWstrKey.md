# CmRegUtilCreateWstrKey

- ea: `0x140025b0c`
- end: `0x140025bd7`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: `NTSTATUS __fastcall(__int64, const WCHAR *, __int64, ULONG, void *, ULONG *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400253a8`
- `0x140025890`

## callees

- `0x1400138e0`
- `0x140025b0c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140025b98`
- `ntoskrnl!ZwCreateKey` at `0x140025b98`

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
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+7h] BYREF
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
0x140025b0c  mov     [rsp-8+arg_18], r9d
0x140025b11  push    rbp
0x140025b12  lea     rbp, [rsp-3Fh]
0x140025b17  sub     rsp, 90h
0x140025b1e  mov     r10, rcx
0x140025b21  xorps   xmm0, xmm0
0x140025b24  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140025b28  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140025b2c  call    WdmlibRtlInitUnicodeStringEx
0x140025b31  test    eax, eax
0x140025b33  js      loc_140025BCD
0x140025b39  xor     eax, eax
0x140025b3b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x140025b43  mov     [rbp+3Fh+arg_18], eax
0x140025b46  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x140025b4a  mov     [rbp+3Fh+KeyHandle], rax
0x140025b4e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140025b52  lea     rax, [rbp+3Fh+DestinationString]
0x140025b56  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x140025b5e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x140025b62  xor     r9d, r9d; TitleIndex
0x140025b65  mov     rax, [rbp+3Fh+arg_20]
0x140025b69  mov     edx, 0F003Fh; DesiredAccess
0x140025b6e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x140025b72  lea     rax, [rbp+3Fh+arg_18]
0x140025b76  mov     [rsp+90h+Disposition], rax; Disposition
0x140025b7b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x140025b83  mov     [rsp+90h+Class], 0; Class
0x140025b8c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x140025b90  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x140025b98  call    cs:__imp_ZwCreateKey
0x140025b9f  nop     dword ptr [rax+rax+00h]
0x140025ba4  mov     r8d, eax
0x140025ba7  test    eax, eax
0x140025ba9  jns     short loc_140025BB1
0x140025bab  xor     edx, edx
0x140025bad  xor     ecx, ecx
0x140025baf  jmp     short loc_140025BB8
0x140025bb1  mov     ecx, [rbp+3Fh+arg_18]
0x140025bb4  mov     rdx, [rbp+3Fh+KeyHandle]
0x140025bb8  mov     rax, [rbp+3Fh+arg_30]
0x140025bbc  mov     [rax], rdx
0x140025bbf  mov     rax, [rbp+3Fh+arg_28]
0x140025bc3  test    rax, rax
0x140025bc6  jz      short loc_140025BCA
0x140025bc8  mov     [rax], ecx
0x140025bca  mov     eax, r8d
0x140025bcd  add     rsp, 90h
0x140025bd4  pop     rbp
0x140025bd5  retn
```
