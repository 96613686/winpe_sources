# SiOpenArcNameObject

- ea: `0x1400258a4`
- end: `0x140025942`
- name: `SiOpenArcNameObject`
- size: `158`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400254d0`

## callees

- `0x1400258a4`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x14002590d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14002590d`
- `ntdll!RtlInitUnicodeString` at `0x1400258d4`
- `ntdll!RtlInitUnicodeString` at `0x1400258d4`

## pseudocode

```c
__int64 __fastcall SiOpenArcNameObject(PCWSTR SourceString, void **a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *SymbolicLinkHandle; // [rsp+80h] [rbp+20h] BYREF

  SymbolicLinkHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 0x20001u, &ObjectAttributes);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *a2 = SymbolicLinkHandle;
  }
  else if ( v3 != -1073741801 && v3 != -1073741670 )
  {
    return (unsigned int)-1073740718;
  }
  return v4;
}

```

## disassembly

```asm
0x1400258a4  mov     [rsp-8+arg_0], rbx
0x1400258a9  push    rbp
0x1400258aa  mov     rbp, rsp
0x1400258ad  sub     rsp, 60h
0x1400258b1  xorps   xmm0, xmm0
0x1400258b4  mov     rbx, rdx
0x1400258b7  mov     rdx, rcx; SourceString
0x1400258ba  xor     eax, eax
0x1400258bc  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400258c0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400258c4  mov     [rbp+SymbolicLinkHandle], rax
0x1400258c8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400258cc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400258d0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400258d4  call    cs:__imp_RtlInitUnicodeString
0x1400258da  lea     rax, [rbp+DestinationString]
0x1400258de  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400258e5  xorps   xmm0, xmm0
0x1400258e8  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400258ec  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400258f0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400258f8  mov     edx, 20001h; DesiredAccess
0x1400258fd  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140025904  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x140025908  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14002590d  call    cs:__imp_NtOpenSymbolicLinkObject
0x140025913  mov     ecx, eax
0x140025915  test    eax, eax
0x140025917  jns     short loc_14002592E
0x140025919  cmp     eax, 0C0000017h
0x14002591e  jz      short loc_140025935
0x140025920  cmp     eax, 0C000009Ah
0x140025925  jz      short loc_140025935
0x140025927  mov     ecx, 0C0000452h
0x14002592c  jmp     short loc_140025935
0x14002592e  mov     rax, [rbp+SymbolicLinkHandle]
0x140025932  mov     [rbx], rax
0x140025935  mov     rbx, [rsp+60h+arg_0]
0x14002593a  mov     eax, ecx
0x14002593c  add     rsp, 60h
0x140025940  pop     rbp
0x140025941  retn
```
