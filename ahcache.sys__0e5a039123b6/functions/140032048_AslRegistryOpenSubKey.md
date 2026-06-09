# AslRegistryOpenSubKey

- ea: `0x140032048`
- end: `0x1400320e7`
- name: `AslRegistryOpenSubKey`
- size: `159`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007450`
- `0x140033320`

## callees

- `0x14000447b`
- `0x1400044b1`
- `0x140032048`
- `0x14003e364`

## string_xrefs

- `0x140032084`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x140032095`: `AslRegistryOpenSubKey`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx_0(&DestinationString, a3);
  v6 = inited;
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return ZwOpenKey_0(KeyHandle, 0x20019u, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]", inited);
    return v6;
  }
}

```

## disassembly

```asm
0x140032048  push    rbp
0x14003204a  push    rbx
0x14003204b  push    rsi
0x14003204c  push    rdi
0x14003204d  mov     rbp, rsp
0x140032050  sub     rsp, 78h
0x140032054  xorps   xmm0, xmm0
0x140032057  xor     eax, eax
0x140032059  mov     [rcx], rax
0x14003205c  mov     rsi, rdx
0x14003205f  mov     rdi, rcx
0x140032062  mov     rdx, r8; SourceString
0x140032065  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140032069  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003206d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140032071  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140032075  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140032079  call    RtlInitUnicodeStringEx_0
0x14003207e  mov     ebx, eax
0x140032080  test    eax, eax
0x140032082  jns     short loc_1400320AA
0x140032084  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x14003208b  mov     [rsp+78h+var_58], eax
0x14003208f  mov     r8d, 3BEh
0x140032095  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x14003209c  mov     ecx, 1
0x1400320a1  call    AslLogCallPrintf
0x1400320a6  mov     eax, ebx
0x1400320a8  jmp     short loc_1400320DD
0x1400320aa  lea     rax, [rbp+DestinationString]
0x1400320ae  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400320b5  xorps   xmm0, xmm0
0x1400320b8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400320bc  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400320c0  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1400320c4  mov     edx, 20019h; DesiredAccess
0x1400320c9  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400320d0  mov     rcx, rdi; KeyHandle
0x1400320d3  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400320d8  call    ZwOpenKey_0
0x1400320dd  add     rsp, 78h
0x1400320e1  pop     rdi
0x1400320e2  pop     rsi
0x1400320e3  pop     rbx
0x1400320e4  pop     rbp
0x1400320e5  retn
```
