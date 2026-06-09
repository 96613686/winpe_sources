# SiTranslateSymbolicLink

- ea: `0x1801d2fa4`
- end: `0x1801d3168`
- name: `SiTranslateSymbolicLink`
- size: `452`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801ca3d0`
- `0x1801d25c8`
- `0x1801d40b4`

## callees

- `0x1801d2fa4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1801d305b`
- `ntdll!RtlFreeHeap` at `0x1801d3144`
- `ntdll!RtlFreeHeap` at `0x1801d305b`
- `ntdll!RtlFreeHeap` at `0x1801d3144`
- `ntdll!RtlAllocateHeap` at `0x1801d307d`
- `ntdll!RtlAllocateHeap` at `0x1801d307d`
- `ntdll!RtlInitUnicodeString` at `0x1801d2feb`
- `ntdll!RtlInitUnicodeString` at `0x1801d3033`
- `ntdll!RtlInitUnicodeString` at `0x1801d2feb`
- `ntdll!RtlInitUnicodeString` at `0x1801d3033`
- `ntdll!NtClose` at `0x1801d30af`
- `ntdll!NtClose` at `0x1801d3121`
- `ntdll!NtClose` at `0x1801d30af`
- `ntdll!NtClose` at `0x1801d3121`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1801d301f`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1801d3100`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1801d301f`
- `ntdll!NtOpenSymbolicLinkObject` at `0x1801d3100`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1801d309c`
- `ntdll!NtQuerySymbolicLinkObject` at `0x1801d309c`

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
0x1801d2fa4  mov     [rsp-18h+arg_0], rbx
0x1801d2fa9  mov     [rsp-18h+arg_8], rsi
0x1801d2fae  push    rbp
0x1801d2faf  push    rdi
0x1801d2fb0  push    r14
0x1801d2fb2  mov     rbp, rsp
0x1801d2fb5  sub     rsp, 70h
0x1801d2fb9  xorps   xmm0, xmm0
0x1801d2fbc  xor     r14d, r14d
0x1801d2fbf  mov     rsi, rdx
0x1801d2fc2  mov     qword ptr [rbp+LinkTarget.Length], r14
0x1801d2fc6  mov     rdx, rcx; SourceString
0x1801d2fc9  mov     [rbp+DataWritten], r14d
0x1801d2fcd  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1801d2fd1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1801d2fd5  mov     [rbp+SymbolicLinkHandle], r14
0x1801d2fd9  xor     eax, eax
0x1801d2fdb  mov     [rbp+LinkTarget.Buffer], r14
0x1801d2fdf  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1801d2fe3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1801d2fe7  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1801d2feb  call    cs:__imp_RtlInitUnicodeString
0x1801d2ff1  lea     rax, [rbp+DestinationString]
0x1801d2ff5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1801d2ffc  xorps   xmm0, xmm0
0x1801d2fff  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1801d3003  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1801d3007  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1801d300b  lea     edx, [r14+1]; DesiredAccess
0x1801d300f  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1801d3016  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x1801d301a  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1801d301f  call    cs:__imp_NtOpenSymbolicLinkObject
0x1801d3025  test    eax, eax
0x1801d3027  js      loc_1801D314C
0x1801d302d  xor     edx, edx; SourceString
0x1801d302f  lea     rcx, [rbp+LinkTarget]; DestinationString
0x1801d3033  call    cs:__imp_RtlInitUnicodeString
0x1801d3039  mov     edi, r14d
0x1801d303c  mov     [rbp+DataWritten], r14d
0x1801d3040  jmp     short loc_1801D3090
0x1801d3042  cmp     [rbp+LinkTarget.Buffer], r14
0x1801d3046  jz      short loc_1801D3061
0x1801d3048  mov     rcx, gs:60h
0x1801d3051  xor     edx, edx; Flags
0x1801d3053  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1801d3057  mov     rcx, [rcx+30h]; HeapHandle
0x1801d305b  call    cs:__imp_RtlFreeHeap
0x1801d3061  mov     eax, [rbp+DataWritten]
0x1801d3064  xor     edx, edx; Flags
0x1801d3066  mov     [rbp+LinkTarget.MaximumLength], ax
0x1801d306a  mov     rcx, gs:60h
0x1801d3073  lea     edi, [rax+2]
0x1801d3076  mov     r8d, edi; Size
0x1801d3079  mov     rcx, [rcx+30h]; HeapHandle
0x1801d307d  call    cs:__imp_RtlAllocateHeap
0x1801d3083  mov     [rbp+LinkTarget.Buffer], rax
0x1801d3087  test    rax, rax
0x1801d308a  jz      loc_1801D3161
0x1801d3090  mov     rcx, [rbp+SymbolicLinkHandle]; SymLinkObjHandle
0x1801d3094  lea     r8, [rbp+DataWritten]; DataWritten
0x1801d3098  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1801d309c  call    cs:__imp_NtQuerySymbolicLinkObject
0x1801d30a2  mov     ebx, eax
0x1801d30a4  cmp     eax, 0C0000023h
0x1801d30a9  jz      short loc_1801D3042
0x1801d30ab  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1801d30af  call    cs:__imp_NtClose
0x1801d30b5  mov     [rbp+SymbolicLinkHandle], r14
0x1801d30b9  test    ebx, ebx
0x1801d30bb  js      short loc_1801D312B
0x1801d30bd  movzx   edx, [rbp+LinkTarget.Length]
0x1801d30c1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1801d30c5  mov     rax, [rbp+LinkTarget.Buffer]
0x1801d30c9  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x1801d30cd  shr     rdx, 1
0x1801d30d0  xorps   xmm0, xmm0
0x1801d30d3  mov     [rax+rdx*2], r14w
0x1801d30d8  lea     rax, [rbp+LinkTarget]
0x1801d30dc  mov     edx, 1; DesiredAccess
0x1801d30e1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1801d30e5  mov     [rbp+LinkTarget.MaximumLength], di
0x1801d30e9  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1801d30f0  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x1801d30f4  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1801d30fb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1801d3100  call    cs:__imp_NtOpenSymbolicLinkObject
0x1801d3106  test    eax, eax
0x1801d3108  jns     short loc_1801D3090
0x1801d310a  mov     rax, [rbp+LinkTarget.Buffer]
0x1801d310e  mov     ebx, r14d
0x1801d3111  mov     [rsi], rax
0x1801d3114  mov     [rbp+LinkTarget.Buffer], r14
0x1801d3118  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x1801d311c  test    rcx, rcx
0x1801d311f  jz      short loc_1801D312B
0x1801d3121  call    cs:__imp_NtClose
0x1801d3127  mov     [rbp+SymbolicLinkHandle], r14
0x1801d312b  cmp     [rbp+LinkTarget.Buffer], r14
0x1801d312f  jz      short loc_1801D314A
0x1801d3131  mov     rcx, gs:60h
0x1801d313a  xor     edx, edx; Flags
0x1801d313c  mov     r8, [rbp+LinkTarget.Buffer]; P
0x1801d3140  mov     rcx, [rcx+30h]; HeapHandle
0x1801d3144  call    cs:__imp_RtlFreeHeap
0x1801d314a  mov     eax, ebx
0x1801d314c  lea     r11, [rsp+70h+var_s0]
0x1801d3151  mov     rbx, [r11+20h]
0x1801d3155  mov     rsi, [r11+28h]
0x1801d3159  mov     rsp, r11
0x1801d315c  pop     r14
0x1801d315e  pop     rdi
0x1801d315f  pop     rbp
0x1801d3160  retn
0x1801d3161  mov     ebx, 0C000009Ah
0x1801d3166  jmp     short loc_1801D3118
```
