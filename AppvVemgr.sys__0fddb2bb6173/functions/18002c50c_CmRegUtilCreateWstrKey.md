# CmRegUtilCreateWstrKey

- ea: `0x18002c50c`
- end: `0x18002c5d7`
- name: `CmRegUtilCreateWstrKey`
- size: `203`
- prototype: `NTSTATUS __fastcall(__int64, const WCHAR *, __int64, ULONG, void *, ULONG *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002bda8`
- `0x18002c290`

## callees

- `0x18001b8ac`
- `0x18002c50c`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x18002c598`
- `ntoskrnl!ZwCreateKey` at `0x18002c598`

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
0x18002c50c  mov     [rsp-8+arg_18], r9d
0x18002c511  push    rbp
0x18002c512  lea     rbp, [rsp-3Fh]
0x18002c517  sub     rsp, 90h
0x18002c51e  mov     r10, rcx
0x18002c521  xorps   xmm0, xmm0
0x18002c524  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18002c528  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18002c52c  call    WdmlibRtlInitUnicodeStringEx
0x18002c531  test    eax, eax
0x18002c533  js      loc_18002C5CD
0x18002c539  xor     eax, eax
0x18002c53b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18002c543  mov     [rbp+3Fh+arg_18], eax
0x18002c546  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18002c54a  mov     [rbp+3Fh+KeyHandle], rax
0x18002c54e  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x18002c552  lea     rax, [rbp+3Fh+DestinationString]
0x18002c556  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x18002c55e  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x18002c562  xor     r9d, r9d; TitleIndex
0x18002c565  mov     rax, [rbp+3Fh+arg_20]
0x18002c569  mov     edx, 0F003Fh; DesiredAccess
0x18002c56e  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x18002c572  lea     rax, [rbp+3Fh+arg_18]
0x18002c576  mov     [rsp+90h+Disposition], rax; Disposition
0x18002c57b  mov     [rsp+90h+CreateOptions], 0; CreateOptions
0x18002c583  mov     [rsp+90h+Class], 0; Class
0x18002c58c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r10
0x18002c590  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], 0
0x18002c598  call    cs:__imp_ZwCreateKey
0x18002c59f  nop     dword ptr [rax+rax+00h]
0x18002c5a4  mov     r8d, eax
0x18002c5a7  test    eax, eax
0x18002c5a9  jns     short loc_18002C5B1
0x18002c5ab  xor     edx, edx
0x18002c5ad  xor     ecx, ecx
0x18002c5af  jmp     short loc_18002C5B8
0x18002c5b1  mov     ecx, [rbp+3Fh+arg_18]
0x18002c5b4  mov     rdx, [rbp+3Fh+KeyHandle]
0x18002c5b8  mov     rax, [rbp+3Fh+arg_30]
0x18002c5bc  mov     [rax], rdx
0x18002c5bf  mov     rax, [rbp+3Fh+arg_28]
0x18002c5c3  test    rax, rax
0x18002c5c6  jz      short loc_18002C5CA
0x18002c5c8  mov     [rax], ecx
0x18002c5ca  mov     eax, r8d
0x18002c5cd  add     rsp, 90h
0x18002c5d4  pop     rbp
0x18002c5d5  retn
```
