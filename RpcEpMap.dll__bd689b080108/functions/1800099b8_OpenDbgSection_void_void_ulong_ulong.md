# OpenDbgSection(void * *,void * *,ulong,ulong *)

- ea: `0x1800099b8`
- end: `0x180009ac5`
- name: `?OpenDbgSection@@YAJPEAPEAX0KPEAK@Z`
- size: `269`
- prototype: `__int64 __fastcall(PHANDLE SectionHandle, void **, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007440`
- `0x180009df8`

## callees

- `0x1800099b8`
- `0x18000a5d8`
- `0x18000a980`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180009a03`
- `ntdll!RtlInitUnicodeString` at `0x180009a03`
- `ntdll!NtOpenSection` at `0x180009a3b`
- `ntdll!NtOpenSection` at `0x180009a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a98`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180009a87`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x180009a87`

## pseudocode

```c
__int64 __fastcall OpenDbgSection(PHANDLE SectionHandle, void **a2, unsigned int a3, unsigned int *a4)
{
  NTSTATUS v6; // eax
  NTSTATUS v7; // ecx
  __int64 result; // rax
  void *v9; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-69h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-59h] BYREF
  WCHAR SourceString[48]; // [rsp+70h] [rbp-29h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  GenerateSectionName(SourceString, (int)a2, a3, a4);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenSection(SectionHandle, 4u, &ObjectAttributes);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v9 = MapViewOfFileEx(*SectionHandle, 4u, 0, 0, 0, 0);
    *a2 = v9;
    if ( v9 )
    {
      return 0;
    }
    else
    {
      CloseHandle(*SectionHandle);
      result = 14;
      *SectionHandle = 0;
    }
  }
  else if ( v6 == -1073741772 )
  {
    return 2;
  }
  else
  {
    result = 14;
    if ( v7 == -1073741790 )
      return 5;
  }
  return result;
}

```

## disassembly

```asm
0x1800099b8  push    rbp
0x1800099ba  push    rbx
0x1800099bb  push    rdi
0x1800099bc  lea     rbp, [rsp-47h]
0x1800099c1  sub     rsp, 0E0h
0x1800099c8  mov     rax, cs:__security_cookie
0x1800099cf  xor     rax, rsp
0x1800099d2  mov     [rbp+57h+var_20], rax
0x1800099d6  xorps   xmm1, xmm1
0x1800099d9  mov     rbx, rcx
0x1800099dc  xorps   xmm0, xmm0
0x1800099df  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1800099e3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800099e7  mov     rdi, rdx
0x1800099ea  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800099ee  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800099f2  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800099f6  call    ?GenerateSectionName@@YAXPEAGHKPEAK@Z; GenerateSectionName(ushort *,int,ulong,ulong *)
0x1800099fb  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800099ff  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180009a03  call    cs:__imp_RtlInitUnicodeString
0x180009a09  lea     rax, [rbp+57h+DestinationString]
0x180009a0d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180009a14  xorps   xmm0, xmm0
0x180009a17  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180009a1b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180009a1f  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180009a27  mov     edx, 4; DesiredAccess
0x180009a2c  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180009a33  mov     rcx, rbx; SectionHandle
0x180009a36  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009a3b  call    cs:__imp_NtOpenSection
0x180009a41  mov     ecx, eax
0x180009a43  test    eax, eax
0x180009a45  jns     short loc_180009A68
0x180009a47  cmp     eax, 0C0000034h
0x180009a4c  jnz     short loc_180009A55
0x180009a4e  mov     eax, 2
0x180009a53  jmp     short loc_180009AAE
0x180009a55  mov     eax, 0Eh
0x180009a5a  cmp     ecx, 0C0000022h
0x180009a60  lea     edx, [rax-9]
0x180009a63  cmovz   eax, edx
0x180009a66  jmp     short loc_180009AAE
0x180009a68  mov     rcx, [rbx]; hFileMappingObject
0x180009a6b  xor     r9d, r9d; dwFileOffsetLow
0x180009a6e  mov     [rsp+0F0h+lpBaseAddress], 0; lpBaseAddress
0x180009a77  xor     r8d, r8d; dwFileOffsetHigh
0x180009a7a  mov     [rsp+0F0h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180009a83  lea     edx, [r9+4]; dwDesiredAccess
0x180009a87  call    cs:__imp_MapViewOfFileEx
0x180009a8d  mov     [rdi], rax
0x180009a90  test    rax, rax
0x180009a93  jnz     short loc_180009AAC
0x180009a95  mov     rcx, [rbx]; hObject
0x180009a98  call    cs:__imp_CloseHandle
0x180009a9e  mov     eax, 0Eh
0x180009aa3  mov     qword ptr [rbx], 0
0x180009aaa  jmp     short loc_180009AAE
0x180009aac  xor     eax, eax
0x180009aae  mov     rcx, [rbp+57h+var_20]
0x180009ab2  xor     rcx, rsp; StackCookie
0x180009ab5  call    __security_check_cookie
0x180009aba  add     rsp, 0E0h
0x180009ac1  pop     rdi
0x180009ac2  pop     rbx
0x180009ac3  pop     rbp
0x180009ac4  retn
```
