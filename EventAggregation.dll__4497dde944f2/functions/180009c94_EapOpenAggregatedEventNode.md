# EapOpenAggregatedEventNode

- ea: `0x180009c94`
- end: `0x180009d2f`
- name: `EapOpenAggregatedEventNode`
- size: `155`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009070`
- `0x180009370`
- `0x180009d38`
- `0x18000a414`

## callees

- `0x180009c94`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180009d1e`
- `ntdll!RtlFreeUnicodeString` at `0x180009d1e`
- `ntdll!RtlInitUnicodeString` at `0x180009cc4`
- `ntdll!RtlInitUnicodeString` at `0x180009cc4`
- `ntdll!RtlStringFromGUID` at `0x180009cd1`
- `ntdll!RtlStringFromGUID` at `0x180009cd1`
- `ntdll!ZwOpenKey` at `0x180009d0b`
- `ntdll!ZwOpenKey` at `0x180009d0b`

## pseudocode

```c
__int64 __fastcall EapOpenAggregatedEventNode(void *a1, const GUID *a2, void **a3)
{
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF

  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v6 = RtlStringFromGUID(a2, &DestinationString);
  if ( v6 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v6 = ZwOpenKey(a3, 0xF003Fu, &ObjectAttributes);
  }
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009c94  push    rbp
0x180009c96  push    rbx
0x180009c97  push    rsi
0x180009c98  push    rdi
0x180009c99  mov     rbp, rsp
0x180009c9c  sub     rsp, 68h
0x180009ca0  xorps   xmm0, xmm0
0x180009ca3  mov     rbx, rdx
0x180009ca6  mov     rsi, rcx
0x180009ca9  xor     eax, eax
0x180009cab  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180009caf  xor     edx, edx; SourceString
0x180009cb1  lea     rcx, [rbp+DestinationString]; DestinationString
0x180009cb5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180009cb9  mov     rdi, r8
0x180009cbc  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180009cc0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180009cc4  call    cs:__imp_RtlInitUnicodeString
0x180009cca  lea     rdx, [rbp+DestinationString]; GuidString
0x180009cce  mov     rcx, rbx; Guid
0x180009cd1  call    cs:__imp_RtlStringFromGUID
0x180009cd7  mov     ebx, eax
0x180009cd9  test    eax, eax
0x180009cdb  js      short loc_180009D13
0x180009cdd  lea     rax, [rbp+DestinationString]
0x180009ce1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180009ce8  xorps   xmm0, xmm0
0x180009ceb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180009cef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180009cf3  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180009cf7  mov     edx, 0F003Fh; DesiredAccess
0x180009cfc  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180009d03  mov     rcx, rdi; KeyHandle
0x180009d06  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180009d0b  call    cs:__imp_ZwOpenKey
0x180009d11  mov     ebx, eax
0x180009d13  cmp     [rbp+DestinationString.Buffer], 0
0x180009d18  jz      short loc_180009D24
0x180009d1a  lea     rcx, [rbp+DestinationString]; UnicodeString
0x180009d1e  call    cs:__imp_RtlFreeUnicodeString
0x180009d24  mov     eax, ebx
0x180009d26  add     rsp, 68h
0x180009d2a  pop     rdi
0x180009d2b  pop     rsi
0x180009d2c  pop     rbx
0x180009d2d  pop     rbp
0x180009d2e  retn
```
