# BiCreateKey

- ea: `0x14001e730`
- end: `0x14001e97a`
- name: `BiCreateKey`
- size: `586`
- prototype: `__int64 __fastcall(unsigned __int64, const WCHAR *, ACCESS_MASK, unsigned int, void **, bool *)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140014130`
- `0x140018b54`
- `0x14001a964`
- `0x14001af00`

## callees

- `0x14001e730`
- `0x14001e980`

## import_xrefs

- `ntdll!ZwClose` at `0x14001e8bc`
- `ntdll!ZwClose` at `0x14001e901`
- `ntdll!ZwClose` at `0x14001e8bc`
- `ntdll!ZwClose` at `0x14001e901`
- `ntdll!ZwCreateKey` at `0x14001e869`
- `ntdll!ZwCreateKey` at `0x14001e869`
- `ntdll!ZwSetSecurityObject` at `0x14001e88b`
- `ntdll!ZwSetSecurityObject` at `0x14001e88b`
- `ntdll!ZwOpenKey` at `0x14001e8a7`
- `ntdll!ZwOpenKey` at `0x14001e8a7`
- `ntdll!RtlFreeHeap` at `0x14001e91e`
- `ntdll!RtlFreeHeap` at `0x14001e91e`
- `ntdll!RtlInitUnicodeString` at `0x14001e796`
- `ntdll!RtlInitUnicodeString` at `0x14001e796`

## pseudocode

```c
__int64 __fastcall BiCreateKey(
        unsigned __int64 a1,
        const WCHAR *a2,
        ACCESS_MASK a3,
        unsigned int a4,
        void **a5,
        bool *a6)
{
  char v6; // r14
  const WCHAR *v8; // rax
  unsigned int i; // r15d
  ACCESS_MASK v11; // edi
  char v12; // r12
  void *KeySecurityDescriptor; // rax
  void *v14; // r14
  NTSTATUS v15; // edi
  ULONG v17; // [rsp+40h] [rbp-98h]
  ULONG Disposition; // [rsp+44h] [rbp-94h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-90h] BYREF
  void *v20; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-70h] BYREF

  v6 = a4;
  v8 = a2;
  Disposition = 0;
  v20 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  for ( i = 0; ; ++i )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, v8);
    a1 &= ~2uLL;
    a3 |= 0x40000u;
    v17 = 64;
    v11 = a3;
    v12 = 0;
    if ( (v6 & 1) != 0 )
    {
      v17 = 192;
      if ( (a3 & 0x60019) != a3 )
      {
        v11 = 0x40000;
        v12 = 1;
      }
    }
    KeySecurityDescriptor = (void *)BiCreateKeySecurityDescriptor(0xF003Fu);
    v14 = KeySecurityDescriptor;
    if ( KeySecurityDescriptor )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = (HANDLE)a1;
      ObjectAttributes.Attributes = v17;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = KeySecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      v15 = ZwCreateKey(&KeyHandle, v11, &ObjectAttributes, 0, 0, (a4 >> 1) & 1, &Disposition);
      if ( v15 < 0 )
        goto LABEL_15;
      if ( v12 )
      {
        v15 = ZwSetSecurityObject(KeyHandle, 4u, v14);
        if ( v15 < 0 )
          goto LABEL_15;
        v15 = ZwOpenKey(&v20, a3, &ObjectAttributes);
        if ( v15 < 0 )
          goto LABEL_15;
        ZwClose(KeyHandle);
        KeyHandle = v20;
      }
      if ( a6 )
        *a6 = Disposition == 1;
      *a5 = KeyHandle;
LABEL_15:
      if ( v15 >= 0 )
        goto LABEL_18;
      goto LABEL_16;
    }
    v15 = -1073741703;
LABEL_16:
    if ( KeyHandle )
      ZwClose(KeyHandle);
LABEL_18:
    if ( v14 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    if ( v15 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
    v6 = a4;
    v8 = a2;
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14001e730  mov     r11, rsp
0x14001e733  mov     [r11+20h], r9d
0x14001e737  mov     [r11+10h], rdx
0x14001e73b  push    rsi
0x14001e73c  push    rdi
0x14001e73d  push    r12
0x14001e73f  push    r13
0x14001e741  push    r14
0x14001e743  push    r15
0x14001e745  sub     rsp, 0A8h
0x14001e74c  mov     r14d, r9d
0x14001e74f  mov     esi, r8d
0x14001e752  mov     rax, rdx
0x14001e755  mov     r13, rcx
0x14001e758  mov     [rsp+0D8h+var_94], 0
0x14001e760  mov     [rsp+0D8h+var_88], 0
0x14001e769  xorps   xmm0, xmm0
0x14001e76c  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x14001e771  xor     ecx, ecx
0x14001e773  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.Length], xmm0
0x14001e778  movups  xmmword ptr [rsp+0D8h+ObjectAttributes.ObjectName], xmm0
0x14001e77d  movups  xmmword ptr [r11-54h], xmm0
0x14001e782  xor     r15d, r15d
0x14001e785  mov     [rsp+0D8h+KeyHandle], 0
0x14001e78e  mov     rdx, rax; SourceString
0x14001e791  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x14001e796  call    cs:__imp_RtlInitUnicodeString
0x14001e79c  and     r13, 0FFFFFFFFFFFFFFFDh
0x14001e7a0  mov     [rsp+0D8h+arg_0], r13
0x14001e7a8  bts     esi, 12h
0x14001e7ac  mov     [rsp+0D8h+arg_10], esi
0x14001e7b3  mov     [rsp+0D8h+var_98], 40h ; '@'
0x14001e7bb  mov     edi, esi
0x14001e7bd  xor     r12b, r12b
0x14001e7c0  test    r14b, 1
0x14001e7c4  jz      short loc_14001E7E1
0x14001e7c6  mov     [rsp+0D8h+var_98], 0C0h
0x14001e7ce  mov     eax, esi
0x14001e7d0  and     eax, 60019h
0x14001e7d5  cmp     eax, esi
0x14001e7d7  jz      short loc_14001E7E1
0x14001e7d9  mov     edi, 40000h
0x14001e7de  mov     r12b, 1
0x14001e7e1  mov     ecx, 0F003Fh; AccessMask
0x14001e7e6  call    BiCreateKeySecurityDescriptor
0x14001e7eb  mov     r14, rax
0x14001e7ee  test    rax, rax
0x14001e7f1  jnz     short loc_14001E801
0x14001e7f3  mov     edi, 0C0000079h
0x14001e7f8  mov     [rsp+0D8h+var_98], edi
0x14001e7fc  jmp     loc_14001E8F7
0x14001e801  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x14001e809  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], r13
0x14001e80e  mov     eax, [rsp+0D8h+var_98]
0x14001e812  mov     [rsp+0D8h+ObjectAttributes.Attributes], eax
0x14001e819  lea     rax, [rsp+0D8h+DestinationString]
0x14001e81e  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x14001e823  mov     [rsp+0D8h+ObjectAttributes.SecurityDescriptor], r14
0x14001e82b  mov     [rsp+0D8h+ObjectAttributes.SecurityQualityOfService], 0
0x14001e837  mov     eax, [rsp+0D8h+arg_18]
0x14001e83e  shr     eax, 1
0x14001e840  and     eax, 1
0x14001e843  lea     rcx, [rsp+0D8h+var_94]
0x14001e848  mov     [rsp+0D8h+Disposition], rcx; Disposition
0x14001e84d  mov     [rsp+0D8h+CreateOptions], eax; CreateOptions
0x14001e851  mov     [rsp+0D8h+Class], 0; Class
0x14001e85a  xor     r9d, r9d; TitleIndex
0x14001e85d  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x14001e862  mov     edx, edi; DesiredAccess
0x14001e864  lea     rcx, [rsp+0D8h+KeyHandle]; KeyHandle
0x14001e869  call    cs:__imp_ZwCreateKey
0x14001e86f  mov     edi, eax
0x14001e871  mov     [rsp+0D8h+var_98], eax
0x14001e875  test    eax, eax
0x14001e877  js      short loc_14001E8F3
0x14001e879  test    r12b, r12b
0x14001e87c  jz      short loc_14001E8CC
0x14001e87e  mov     r8, r14; SecurityDescriptor
0x14001e881  mov     edx, 4; SecurityInformation
0x14001e886  mov     rcx, [rsp+0D8h+KeyHandle]; Handle
0x14001e88b  call    cs:__imp_ZwSetSecurityObject
0x14001e891  mov     edi, eax
0x14001e893  mov     [rsp+0D8h+var_98], eax
0x14001e897  test    eax, eax
0x14001e899  js      short loc_14001E8F3
0x14001e89b  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x14001e8a0  mov     edx, esi; DesiredAccess
0x14001e8a2  lea     rcx, [rsp+0D8h+var_88]; KeyHandle
0x14001e8a7  call    cs:__imp_ZwOpenKey
0x14001e8ad  mov     edi, eax
0x14001e8af  mov     [rsp+0D8h+var_98], eax
0x14001e8b3  test    eax, eax
0x14001e8b5  js      short loc_14001E8F3
0x14001e8b7  mov     rcx, [rsp+0D8h+KeyHandle]; Handle
0x14001e8bc  call    cs:__imp_ZwClose
0x14001e8c2  mov     rax, [rsp+0D8h+var_88]
0x14001e8c7  mov     [rsp+0D8h+KeyHandle], rax
0x14001e8cc  mov     rcx, [rsp+0D8h+arg_28]
0x14001e8d4  test    rcx, rcx
0x14001e8d7  jz      short loc_14001E8E3
0x14001e8d9  cmp     [rsp+0D8h+var_94], 1
0x14001e8de  setz    al
0x14001e8e1  mov     [rcx], al
0x14001e8e3  mov     rcx, [rsp+0D8h+arg_20]
0x14001e8eb  mov     rax, [rsp+0D8h+KeyHandle]
0x14001e8f0  mov     [rcx], rax
0x14001e8f3  test    edi, edi
0x14001e8f5  jns     short loc_14001E907
0x14001e8f7  mov     rcx, [rsp+0D8h+KeyHandle]; Handle
0x14001e8fc  test    rcx, rcx
0x14001e8ff  jz      short loc_14001E907
0x14001e901  call    cs:__imp_ZwClose
0x14001e907  test    r14, r14
0x14001e90a  jz      short loc_14001E924
0x14001e90c  mov     rcx, gs:60h
0x14001e915  mov     r8, r14; P
0x14001e918  xor     edx, edx; Flags
0x14001e91a  mov     rcx, [rcx+30h]; HeapHandle
0x14001e91e  call    cs:__imp_RtlFreeHeap
0x14001e924  cmp     edi, 0C000017Dh
0x14001e92a  jnz     short loc_14001E966
0x14001e92c  int     3; Trap to Debugger
0x14001e92d  jmp     short loc_14001E948
0x14001e92f  mov     r15d, 5
0x14001e935  mov     esi, [rsp+0D8h+arg_10]
0x14001e93c  mov     r13, [rsp+0D8h+arg_0]
0x14001e944  mov     edi, [rsp+0D8h+var_98]
0x14001e948  cmp     r15d, 5
0x14001e94c  jnb     short loc_14001E966
0x14001e94e  inc     r15d
0x14001e951  mov     r14d, [rsp+0D8h+arg_18]
0x14001e959  mov     rax, [rsp+0D8h+arg_8]
0x14001e961  jmp     loc_14001E785
0x14001e966  mov     eax, edi
0x14001e968  add     rsp, 0A8h
0x14001e96f  pop     r15
0x14001e971  pop     r14
0x14001e973  pop     r13
0x14001e975  pop     r12
0x14001e977  pop     rdi
0x14001e978  pop     rsi
0x14001e979  retn
```
