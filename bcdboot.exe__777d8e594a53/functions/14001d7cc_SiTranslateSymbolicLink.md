# SiTranslateSymbolicLink

- ea: `0x14001d7cc`
- end: `0x14001d990`
- name: `SiTranslateSymbolicLink`
- size: `452`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, PWSTR *)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140013484`
- `0x14001cc8c`
- `0x1400254d0`

## callees

- `0x14001d7cc`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x14001d847`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14001d928`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14001d847`
- `ntdll!NtOpenSymbolicLinkObject` at `0x14001d928`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14001d8c4`
- `ntdll!NtQuerySymbolicLinkObject` at `0x14001d8c4`
- `ntdll!RtlAllocateHeap` at `0x14001d8a5`
- `ntdll!RtlAllocateHeap` at `0x14001d8a5`
- `ntdll!RtlFreeHeap` at `0x14001d883`
- `ntdll!RtlFreeHeap` at `0x14001d96c`
- `ntdll!RtlFreeHeap` at `0x14001d883`
- `ntdll!RtlFreeHeap` at `0x14001d96c`
- `ntdll!NtClose` at `0x14001d8d7`
- `ntdll!NtClose` at `0x14001d949`
- `ntdll!NtClose` at `0x14001d8d7`
- `ntdll!NtClose` at `0x14001d949`
- `ntdll!RtlInitUnicodeString` at `0x14001d813`
- `ntdll!RtlInitUnicodeString` at `0x14001d85b`
- `ntdll!RtlInitUnicodeString` at `0x14001d813`
- `ntdll!RtlInitUnicodeString` at `0x14001d85b`

## pseudocode

```c
NTSTATUS __fastcall SiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG DataWritten; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  *(_QWORD *)&LinkTarget.Length = 0;
  DataWritten = 0;
  SymbolicLinkHandle = 0;
  LinkTarget.Buffer = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    DataWritten = 0;
    do
    {
      while ( 1 )
      {
        v5 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
        if ( v5 == -1073741789 )
          break;
        NtClose(SymbolicLinkHandle);
        SymbolicLinkHandle = 0;
        if ( v5 < 0 )
          goto LABEL_12;
        LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        LinkTarget.MaximumLength = v4;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
        {
          v5 = 0;
          *a2 = LinkTarget.Buffer;
          LinkTarget.Buffer = 0;
          goto LABEL_10;
        }
      }
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      LinkTarget.MaximumLength = DataWritten;
      v4 = DataWritten + 2;
      LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, DataWritten + 2);
    }
    while ( LinkTarget.Buffer );
    v5 = -1073741670;
LABEL_10:
    if ( SymbolicLinkHandle )
    {
      NtClose(SymbolicLinkHandle);
      SymbolicLinkHandle = 0;
    }
LABEL_12:
    if ( LinkTarget.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14001d7cc  mov     [rsp-18h+arg_0], rbx
0x14001d7d1  mov     [rsp-18h+arg_8], rsi
0x14001d7d6  push    rbp
0x14001d7d7  push    rdi
0x14001d7d8  push    r14
0x14001d7da  mov     rbp, rsp
0x14001d7dd  sub     rsp, 70h
0x14001d7e1  xorps   xmm0, xmm0
0x14001d7e4  xor     r14d, r14d
0x14001d7e7  mov     rsi, rdx
0x14001d7ea  mov     qword ptr [rbp+LinkTarget.Length], r14
0x14001d7ee  mov     rdx, rcx; SourceString
0x14001d7f1  mov     [rbp+DataWritten], r14d
0x14001d7f5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14001d7f9  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001d7fd  mov     [rbp+SymbolicLinkHandle], r14
0x14001d801  xor     eax, eax
0x14001d803  mov     [rbp+LinkTarget.Buffer], r14
0x14001d807  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001d80b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001d80f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14001d813  call    cs:__imp_RtlInitUnicodeString
0x14001d819  lea     rax, [rbp+DestinationString]
0x14001d81d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001d824  xorps   xmm0, xmm0
0x14001d827  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001d82b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001d82f  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x14001d833  lea     edx, [r14+1]; DesiredAccess
0x14001d837  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001d83e  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x14001d842  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d847  call    cs:__imp_NtOpenSymbolicLinkObject
0x14001d84d  test    eax, eax
0x14001d84f  js      loc_14001D974
0x14001d855  xor     edx, edx; SourceString
0x14001d857  lea     rcx, [rbp+LinkTarget]; DestinationString
0x14001d85b  call    cs:__imp_RtlInitUnicodeString
0x14001d861  mov     edi, r14d
0x14001d864  mov     [rbp+DataWritten], r14d
0x14001d868  jmp     short loc_14001D8B8
0x14001d86a  cmp     [rbp+LinkTarget.Buffer], r14
0x14001d86e  jz      short loc_14001D889
0x14001d870  mov     rcx, gs:60h
0x14001d879  xor     edx, edx; Flags
0x14001d87b  mov     r8, [rbp+LinkTarget.Buffer]; P
0x14001d87f  mov     rcx, [rcx+30h]; HeapHandle
0x14001d883  call    cs:__imp_RtlFreeHeap
0x14001d889  mov     eax, [rbp+DataWritten]
0x14001d88c  xor     edx, edx; Flags
0x14001d88e  mov     [rbp+LinkTarget.MaximumLength], ax
0x14001d892  mov     rcx, gs:60h
0x14001d89b  lea     edi, [rax+2]
0x14001d89e  mov     r8d, edi; Size
0x14001d8a1  mov     rcx, [rcx+30h]; HeapHandle
0x14001d8a5  call    cs:__imp_RtlAllocateHeap
0x14001d8ab  mov     [rbp+LinkTarget.Buffer], rax
0x14001d8af  test    rax, rax
0x14001d8b2  jz      loc_14001D989
0x14001d8b8  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x14001d8bc  lea     r8, [rbp+DataWritten]; DataWritten
0x14001d8c0  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x14001d8c4  call    cs:__imp_NtQuerySymbolicLinkObject
0x14001d8ca  mov     ebx, eax
0x14001d8cc  cmp     eax, 0C0000023h
0x14001d8d1  jz      short loc_14001D86A
0x14001d8d3  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x14001d8d7  call    cs:__imp_NtClose
0x14001d8dd  mov     [rbp+SymbolicLinkHandle], r14
0x14001d8e1  test    ebx, ebx
0x14001d8e3  js      short loc_14001D953
0x14001d8e5  movzx   edx, [rbp+LinkTarget.Length]
0x14001d8e9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14001d8ed  mov     rax, [rbp+LinkTarget.Buffer]
0x14001d8f1  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x14001d8f5  shr     rdx, 1
0x14001d8f8  xorps   xmm0, xmm0
0x14001d8fb  mov     [rax+rdx*2], r14w
0x14001d900  lea     rax, [rbp+LinkTarget]
0x14001d904  mov     edx, 1; DesiredAccess
0x14001d909  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001d90d  mov     [rbp+LinkTarget.MaximumLength], di
0x14001d911  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001d918  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x14001d91c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001d923  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001d928  call    cs:__imp_NtOpenSymbolicLinkObject
0x14001d92e  test    eax, eax
0x14001d930  jns     short loc_14001D8B8
0x14001d932  mov     rax, [rbp+LinkTarget.Buffer]
0x14001d936  mov     ebx, r14d
0x14001d939  mov     [rsi], rax
0x14001d93c  mov     [rbp+LinkTarget.Buffer], r14
0x14001d940  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x14001d944  test    rcx, rcx
0x14001d947  jz      short loc_14001D953
0x14001d949  call    cs:__imp_NtClose
0x14001d94f  mov     [rbp+SymbolicLinkHandle], r14
0x14001d953  cmp     [rbp+LinkTarget.Buffer], r14
0x14001d957  jz      short loc_14001D972
0x14001d959  mov     rcx, gs:60h
0x14001d962  xor     edx, edx; Flags
0x14001d964  mov     r8, [rbp+LinkTarget.Buffer]; P
0x14001d968  mov     rcx, [rcx+30h]; HeapHandle
0x14001d96c  call    cs:__imp_RtlFreeHeap
0x14001d972  mov     eax, ebx
0x14001d974  lea     r11, [rsp+70h+var_s0]
0x14001d979  mov     rbx, [r11+20h]
0x14001d97d  mov     rsi, [r11+28h]
0x14001d981  mov     rsp, r11
0x14001d984  pop     r14
0x14001d986  pop     rdi
0x14001d987  pop     rbp
0x14001d988  retn
0x14001d989  mov     ebx, 0C000009Ah
0x14001d98e  jmp     short loc_14001D940
```
