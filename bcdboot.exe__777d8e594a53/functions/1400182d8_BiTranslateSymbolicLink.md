# BiTranslateSymbolicLink

- ea: `0x1400182d8`
- end: `0x140018490`
- name: `BiTranslateSymbolicLink`
- size: `440`
- prototype: `NTSTATUS __fastcall(PCWSTR SourceString, PWSTR *)`
- caller_count: `4`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400171b4`
- `0x140017830`
- `0x140020e68`
- `0x140021298`

## callees

- `0x1400182d8`

## import_xrefs

- `ntdll!ZwQuerySymbolicLinkObject` at `0x1400183ca`
- `ntdll!ZwQuerySymbolicLinkObject` at `0x1400183ca`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x14001834e`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x140018431`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x14001834e`
- `ntdll!ZwOpenSymbolicLinkObject` at `0x140018431`
- `ntdll!ZwClose` at `0x1400183dd`
- `ntdll!ZwClose` at `0x14001844d`
- `ntdll!ZwClose` at `0x1400183dd`
- `ntdll!ZwClose` at `0x14001844d`
- `ntdll!RtlAllocateHeap` at `0x1400183ab`
- `ntdll!RtlAllocateHeap` at `0x1400183ab`
- `ntdll!RtlFreeHeap` at `0x140018389`
- `ntdll!RtlFreeHeap` at `0x140018471`
- `ntdll!RtlFreeHeap` at `0x140018389`
- `ntdll!RtlFreeHeap` at `0x140018471`
- `ntdll!RtlInitUnicodeString` at `0x140018315`
- `ntdll!RtlInitUnicodeString` at `0x140018362`
- `ntdll!RtlInitUnicodeString` at `0x140018315`
- `ntdll!RtlInitUnicodeString` at `0x140018362`

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
0x1400182d8  mov     [rsp-18h+arg_0], rbx
0x1400182dd  push    rbp
0x1400182de  push    rsi
0x1400182df  push    rdi
0x1400182e0  mov     rbp, rsp
0x1400182e3  sub     rsp, 70h
0x1400182e7  xorps   xmm0, xmm0
0x1400182ea  xor     eax, eax
0x1400182ec  mov     rsi, rdx
0x1400182ef  mov     [rbp+ReturnedLength], eax
0x1400182f2  mov     rdx, rcx; SourceString
0x1400182f5  mov     qword ptr [rbp+LinkTarget.Length], rax
0x1400182f9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400182fd  lea     rcx, [rbp+DestinationString]; DestinationString
0x140018301  mov     [rbp+SymbolicLinkHandle], rax
0x140018305  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140018309  mov     [rbp+LinkTarget.Buffer], rax
0x14001830d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140018311  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140018315  call    cs:__imp_RtlInitUnicodeString
0x14001831b  lea     rax, [rbp+DestinationString]
0x14001831f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140018326  xorps   xmm0, xmm0
0x140018329  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001832d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140018331  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140018339  mov     edx, 1; DesiredAccess
0x14001833e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140018345  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x140018349  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001834e  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140018354  test    eax, eax
0x140018356  js      loc_140018479
0x14001835c  xor     edx, edx; SourceString
0x14001835e  lea     rcx, [rbp+LinkTarget]; DestinationString
0x140018362  call    cs:__imp_RtlInitUnicodeString
0x140018368  xor     edi, edi
0x14001836a  mov     [rbp+ReturnedLength], edi
0x14001836d  jmp     short loc_1400183BE
0x14001836f  cmp     [rbp+LinkTarget.Buffer], 0
0x140018374  jz      short loc_14001838F
0x140018376  mov     rcx, gs:60h
0x14001837f  xor     edx, edx; Flags
0x140018381  mov     r8, [rbp+LinkTarget.Buffer]; P
0x140018385  mov     rcx, [rcx+30h]; HeapHandle
0x140018389  call    cs:__imp_RtlFreeHeap
0x14001838f  mov     eax, [rbp+ReturnedLength]
0x140018392  xor     edx, edx; Flags
0x140018394  mov     [rbp+LinkTarget.MaximumLength], ax
0x140018398  mov     rcx, gs:60h
0x1400183a1  lea     edi, [rax+2]
0x1400183a4  mov     r8d, edi; Size
0x1400183a7  mov     rcx, [rcx+30h]; HeapHandle
0x1400183ab  call    cs:__imp_RtlAllocateHeap
0x1400183b1  mov     [rbp+LinkTarget.Buffer], rax
0x1400183b5  test    rax, rax
0x1400183b8  jz      loc_140018489
0x1400183be  mov     rcx, [rbp+SymbolicLinkHandle]; LinkHandle
0x1400183c2  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x1400183c6  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1400183ca  call    cs:__imp_ZwQuerySymbolicLinkObject
0x1400183d0  mov     ebx, eax
0x1400183d2  cmp     eax, 0C0000023h
0x1400183d7  jz      short loc_14001836F
0x1400183d9  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1400183dd  call    cs:__imp_ZwClose
0x1400183e3  mov     [rbp+SymbolicLinkHandle], 0
0x1400183eb  test    ebx, ebx
0x1400183ed  js      short loc_140018457
0x1400183ef  movzx   edx, [rbp+LinkTarget.Length]
0x1400183f3  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400183f7  mov     rax, [rbp+LinkTarget.Buffer]
0x1400183fb  xor     ecx, ecx
0x1400183fd  shr     rdx, 1
0x140018400  xorps   xmm0, xmm0
0x140018403  mov     [rax+rdx*2], cx
0x140018407  lea     rax, [rbp+LinkTarget]
0x14001840b  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x14001840f  lea     edx, [rcx+1]; DesiredAccess
0x140018412  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x140018416  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001841a  mov     [rbp+LinkTarget.MaximumLength], di
0x14001841e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140018425  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14001842c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140018431  call    cs:__imp_ZwOpenSymbolicLinkObject
0x140018437  test    eax, eax
0x140018439  jns     short loc_1400183BE
0x14001843b  mov     rax, [rbp+LinkTarget.Buffer]
0x14001843f  xor     ebx, ebx
0x140018441  mov     [rsi], rax
0x140018444  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x140018448  test    rcx, rcx
0x14001844b  jz      short loc_140018453
0x14001844d  call    cs:__imp_ZwClose
0x140018453  test    ebx, ebx
0x140018455  jns     short loc_140018477
0x140018457  cmp     [rbp+LinkTarget.Buffer], 0
0x14001845c  jz      short loc_140018477
0x14001845e  mov     rcx, gs:60h
0x140018467  xor     edx, edx; Flags
0x140018469  mov     r8, [rbp+LinkTarget.Buffer]; P
0x14001846d  mov     rcx, [rcx+30h]; HeapHandle
0x140018471  call    cs:__imp_RtlFreeHeap
0x140018477  mov     eax, ebx
0x140018479  mov     rbx, [rsp+70h+arg_0]
0x140018481  add     rsp, 70h
0x140018485  pop     rdi
0x140018486  pop     rsi
0x140018487  pop     rbp
0x140018488  retn
0x140018489  mov     ebx, 0C000009Ah
0x14001848e  jmp     short loc_140018444
```
