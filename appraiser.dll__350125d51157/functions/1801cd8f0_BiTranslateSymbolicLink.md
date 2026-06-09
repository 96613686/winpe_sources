# BiTranslateSymbolicLink

- ea: `0x1801cd8f0`
- end: `0x1801cdaa8`
- name: `BiTranslateSymbolicLink`
- size: `440`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801cc7dc`
- `0x1801cce4c`
- `0x1801ce330`
- `0x1801ce768`

## callees

- `0x1801cd8f0`

## import_xrefs

- `ntdll!ZwClose` at `0x1801cd9f5`
- `ntdll!ZwClose` at `0x1801cda65`
- `ntdll!ZwClose` at `0x1801cd9f5`
- `ntdll!ZwClose` at `0x1801cda65`
- `ntdll!RtlFreeHeap` at `0x1801cd9a1`
- `ntdll!RtlFreeHeap` at `0x1801cda89`
- `ntdll!RtlFreeHeap` at `0x1801cd9a1`
- `ntdll!RtlFreeHeap` at `0x1801cda89`
- `ntdll!RtlAllocateHeap` at `0x1801cd9c3`
- `ntdll!RtlAllocateHeap` at `0x1801cd9c3`
- `ntdll!RtlInitUnicodeString` at `0x1801cd92d`
- `ntdll!RtlInitUnicodeString` at `0x1801cd97a`
- `ntdll!RtlInitUnicodeString` at `0x1801cd92d`
- `ntdll!RtlInitUnicodeString` at `0x1801cd97a`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x1801cd9e2`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x1801cd9e2`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x1801cd966`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x1801cda49`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x1801cd966`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x1801cda49`

## pseudocode

```c
NTSTATUS __fastcall BiTranslateSymbolicLink(PCWSTR SourceString, PWSTR *a2)
{
  NTSTATUS result; // eax
  USHORT v4; // di
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING LinkTarget; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ReturnedLength; // [rsp+A0h] [rbp+30h] BYREF
  void *SymbolicLinkHandle; // [rsp+A8h] [rbp+38h] BYREF

  ReturnedLength = 0;
  *(_QWORD *)&LinkTarget.Length = 0;
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
  result = ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&LinkTarget, 0);
    v4 = 0;
    ReturnedLength = 0;
    do
    {
      while ( 1 )
      {
        v5 = ZwQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &ReturnedLength);
        if ( v5 == -1073741789 )
          break;
        ZwClose(SymbolicLinkHandle);
        SymbolicLinkHandle = 0;
        if ( v5 < 0 )
          goto LABEL_13;
        LinkTarget.Buffer[(unsigned __int64)LinkTarget.Length >> 1] = 0;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        LinkTarget.MaximumLength = v4;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( ZwOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes) < 0 )
        {
          v5 = 0;
          *a2 = LinkTarget.Buffer;
          goto LABEL_10;
        }
      }
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
      LinkTarget.MaximumLength = ReturnedLength;
      v4 = ReturnedLength + 2;
      LinkTarget.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ReturnedLength + 2);
    }
    while ( LinkTarget.Buffer );
    v5 = -1073741670;
LABEL_10:
    if ( SymbolicLinkHandle )
      ZwClose(SymbolicLinkHandle);
    if ( v5 < 0 )
    {
LABEL_13:
      if ( LinkTarget.Buffer )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, LinkTarget.Buffer);
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1801cd8f0  mov     [rsp-18h+arg_0], rbx
0x1801cd8f5  push    rbp
0x1801cd8f6  push    rsi
0x1801cd8f7  push    rdi
0x1801cd8f8  mov     rbp, rsp
0x1801cd8fb  sub     rsp, 70h
0x1801cd8ff  xorps   xmm0, xmm0
0x1801cd902  xor     eax, eax
0x1801cd904  mov     rsi, rdx
0x1801cd907  mov     [rbp+ReturnedLength], eax
0x1801cd90a  mov     rdx, rcx; SourceString
0x1801cd90d  mov     qword ptr [rbp+LinkTarget.Length], rax
0x1801cd911  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1801cd915  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801cd919  mov     [rbp+SymbolicLinkHandle], rax
0x1801cd91d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1801cd921  mov     [rbp+LinkTarget.Buffer], rax
0x1801cd925  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1801cd929  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1801cd92d  call    cs:__imp_RtlInitUnicodeString
0x1801cd933  lea     rax, [rbp+DestinationString]
0x1801cd937  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1801cd93e  xorps   xmm0, xmm0
0x1801cd941  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1801cd945  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1801cd949  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1801cd951  mov     edx, 1; DesiredAccess
0x1801cd956  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1801cd95d  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x1801cd961  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1801cd966  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1801cd96c  test    eax, eax
0x1801cd96e  js      loc_1801CDA91
0x1801cd974  xor     edx, edx; SourceString
0x1801cd976  lea     rcx, [rbp+LinkTarget]; DestinationString
0x1801cd97a  call    cs:__imp_RtlInitUnicodeString
0x1801cd980  xor     edi, edi
0x1801cd982  mov     [rbp+ReturnedLength], edi
0x1801cd985  jmp     short loc_1801CD9D6
0x1801cd987  cmp     [rbp+LinkTarget.Buffer], 0
0x1801cd98c  jz      short loc_1801CD9A7
0x1801cd98e  mov     rcx, gs:60h
0x1801cd997  xor     edx, edx; Flags
0x1801cd999  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1801cd99d  mov     rcx, [rcx+30h]; HeapHandle
0x1801cd9a1  call    cs:__imp_RtlFreeHeap
0x1801cd9a7  mov     eax, [rbp+ReturnedLength]
0x1801cd9aa  xor     edx, edx; Flags
0x1801cd9ac  mov     [rbp+LinkTarget.MaximumLength], ax
0x1801cd9b0  mov     rcx, gs:60h
0x1801cd9b9  lea     edi, [rax+2]
0x1801cd9bc  mov     r8d, edi; Size
0x1801cd9bf  mov     rcx, [rcx+30h]; HeapHandle
0x1801cd9c3  call    cs:__imp_RtlAllocateHeap
0x1801cd9c9  mov     [rbp+LinkTarget.Buffer], rax
0x1801cd9cd  test    rax, rax
0x1801cd9d0  jz      loc_1801CDAA1
0x1801cd9d6  mov     rcx, [rbp+SymbolicLinkHandle]; LinkHandle
0x1801cd9da  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x1801cd9de  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1801cd9e2  call    cs:__imp_ZwQuerySymbolicLinkObject
0x1801cd9e8  mov     ebx, eax
0x1801cd9ea  cmp     eax, 0C0000023h
0x1801cd9ef  jz      short loc_1801CD987
0x1801cd9f1  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1801cd9f5  call    cs:__imp_ZwClose
0x1801cd9fb  mov     [rbp+SymbolicLinkHandle], 0
0x1801cda03  test    ebx, ebx
0x1801cda05  js      short loc_1801CDA6F
0x1801cda07  movzx   edx, [rbp+LinkTarget.Length]
0x1801cda0b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1801cda0f  mov     rax, [rbp+LinkTarget.Buffer]
0x1801cda13  xor     ecx, ecx
0x1801cda15  shr     rdx, 1
0x1801cda18  xorps   xmm0, xmm0
0x1801cda1b  mov     [rax+rdx*2], cx
0x1801cda1f  lea     rax, [rbp+LinkTarget]
0x1801cda23  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1801cda27  lea     edx, [rcx+1]; DesiredAccess
0x1801cda2a  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x1801cda2e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1801cda32  mov     [rbp+LinkTarget.MaximumLength], di
0x1801cda36  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1801cda3d  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1801cda44  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1801cda49  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1801cda4f  test    eax, eax
0x1801cda51  jns     short loc_1801CD9D6
0x1801cda53  mov     rax, [rbp+LinkTarget.Buffer]
0x1801cda57  xor     ebx, ebx
0x1801cda59  mov     [rsi], rax
0x1801cda5c  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1801cda60  test    rcx, rcx
0x1801cda63  jz      short loc_1801CDA6B
0x1801cda65  call    cs:__imp_ZwClose
0x1801cda6b  test    ebx, ebx
0x1801cda6d  jns     short loc_1801CDA8F
0x1801cda6f  cmp     [rbp+LinkTarget.Buffer], 0
0x1801cda74  jz      short loc_1801CDA8F
0x1801cda76  mov     rcx, gs:60h
0x1801cda7f  xor     edx, edx; Flags
0x1801cda81  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1801cda85  mov     rcx, [rcx+30h]; HeapHandle
0x1801cda89  call    cs:__imp_RtlFreeHeap
0x1801cda8f  mov     eax, ebx
0x1801cda91  mov     rbx, [rsp+70h+arg_0]
0x1801cda99  add     rsp, 70h
0x1801cda9d  pop     rdi
0x1801cda9e  pop     rsi
0x1801cda9f  pop     rbp
0x1801cdaa0  retn
0x1801cdaa1  mov     ebx, 0C000009Ah
0x1801cdaa6  jmp     short loc_1801CDA5C
```
