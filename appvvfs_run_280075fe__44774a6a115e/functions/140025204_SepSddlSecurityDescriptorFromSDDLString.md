# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140025204`
- end: `0x1400253a2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140024a1c`

## callees

- `0x140013b40`
- `0x140014000`
- `0x140024bd4`
- `0x140025204`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140025240`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140025240`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400252cb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400252cb`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400252ec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140025379`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400252ec`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140025379`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025304`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025304`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400252b2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400252b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140025230`
- `ntoskrnl!RtlInitUnicodeString` at `0x140025230`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002532a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025340`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025391`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002532a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025340`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025391`

## string_xrefs

- `0x14002521b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall SepSddlSecurityDescriptorFromSDDLString(__int64 a1, ULONG a2, __int64 a3)
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, __int64, __int64); // rax
  __int64 v6; // rdx
  __int64 result; // rax
  void *v8; // rdi
  NTSTATUS v9; // ebx
  PVOID PoolWithTag; // rax
  PACL Dacl; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-38h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-8h]
  ULONG BufferLength; // [rsp+98h] [rbp+28h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF

  BufferLength = a2;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"SeConvertStringSecurityDescriptorToSecurityDescriptor");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, __int64, __int64))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
  {
    v14 = 0;
    v16 = 0;
    memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
    BufferLength = 0;
    v8 = 0;
    Dacl = 0;
    *(_QWORD *)a3 = 0;
    v9 = SepSddlDaclFromSDDLString(a1, v6, &v16, &Dacl);
    if ( v9 >= 0 )
    {
      RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, Dacl, 0);
      WORD1(SecurityDescriptor[0]) |= v16;
      BufferLength = 0;
      RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x64536553u);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, BufferLength);
        v9 = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v8, &BufferLength);
        if ( v9 >= 0 )
        {
          ExFreePoolWithTag(Dacl, 0);
          *(_QWORD *)a3 = v8;
          return (unsigned int)v9;
        }
      }
      else
      {
        v9 = -1073741670;
      }
    }
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0);
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return (unsigned int)v9;
  }
  result = SystemRoutineAddress(a1, 1, a3);
  if ( (int)result >= 0 )
    *(_WORD *)(*(_QWORD *)a3 + 2LL) |= 8u;
  return result;
}

```

## disassembly

```asm
0x140025204  mov     [rsp-18h+arg_0], rbx
0x140025209  mov     [rsp-18h+BufferLength], edx
0x14002520d  push    rbp
0x14002520e  push    rdi
0x14002520f  push    r14
0x140025211  mov     rbp, rsp
0x140025214  sub     rsp, 70h
0x140025218  mov     rbx, rcx
0x14002521b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x140025222  xorps   xmm0, xmm0
0x140025225  lea     rcx, [rbp+DestinationString]; DestinationString
0x140025229  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002522d  mov     r14, r8
0x140025230  call    cs:__imp_RtlInitUnicodeString
0x140025237  nop     dword ptr [rax+rax+00h]
0x14002523c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140025240  call    cs:__imp_MmGetSystemRoutineAddress
0x140025247  nop     dword ptr [rax+rax+00h]
0x14002524c  mov     rcx, rbx
0x14002524f  test    rax, rax
0x140025252  jz      short loc_140025278
0x140025254  xor     r9d, r9d
0x140025257  mov     r8, r14
0x14002525a  lea     edx, [r9+1]
0x14002525e  call    _guard_dispatch_icall
0x140025263  test    eax, eax
0x140025265  js      loc_14002534E
0x14002526b  mov     rcx, [r14]
0x14002526e  or      word ptr [rcx+2], 8
0x140025273  jmp     loc_14002534E
0x140025278  xor     eax, eax
0x14002527a  lea     r9, [rbp+Dacl]
0x14002527e  xorps   xmm0, xmm0
0x140025281  mov     [rbp+var_8], rax
0x140025285  lea     r8, [rbp+arg_18]
0x140025289  mov     [rbp+arg_18], eax
0x14002528c  movups  [rbp+SecurityDescriptor], xmm0
0x140025290  mov     [rbp+BufferLength], eax
0x140025293  xor     edi, edi
0x140025295  movups  [rbp+var_18], xmm0
0x140025299  mov     [rbp+Dacl], rax
0x14002529d  mov     [r14], rax
0x1400252a0  call    SepSddlDaclFromSDDLString
0x1400252a5  mov     ebx, eax
0x1400252a7  test    eax, eax
0x1400252a9  js      short loc_14002531D
0x1400252ab  lea     edx, [rdi+1]; Revision
0x1400252ae  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400252b2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400252b9  nop     dword ptr [rax+rax+00h]
0x1400252be  mov     r8, [rbp+Dacl]; Dacl
0x1400252c2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400252c6  xor     r9d, r9d; DaclDefaulted
0x1400252c9  mov     dl, 1; DaclPresent
0x1400252cb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400252d2  nop     dword ptr [rax+rax+00h]
0x1400252d7  movzx   eax, word ptr [rbp+arg_18]
0x1400252db  lea     r8, [rbp+BufferLength]; BufferLength
0x1400252df  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400252e3  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400252e7  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400252e9  mov     [rbp+BufferLength], edi
0x1400252ec  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400252f3  nop     dword ptr [rax+rax+00h]
0x1400252f8  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x1400252fb  lea     ecx, [rdi+1]; PoolType
0x1400252fe  mov     r8d, 64536553h; Tag
0x140025304  call    cs:__imp_ExAllocatePoolWithTag
0x14002530b  nop     dword ptr [rax+rax+00h]
0x140025310  mov     rdi, rax
0x140025313  test    rax, rax
0x140025316  jnz     short loc_140025360
0x140025318  mov     ebx, 0C000009Ah
0x14002531d  cmp     [rbp+Dacl], 0
0x140025322  jz      short loc_140025336
0x140025324  mov     rcx, [rbp+Dacl]; P
0x140025328  xor     edx, edx; Tag
0x14002532a  call    cs:__imp_ExFreePoolWithTag
0x140025331  nop     dword ptr [rax+rax+00h]
0x140025336  test    rdi, rdi
0x140025339  jz      short loc_14002534C
0x14002533b  xor     edx, edx; Tag
0x14002533d  mov     rcx, rdi; P
0x140025340  call    cs:__imp_ExFreePoolWithTag
0x140025347  nop     dword ptr [rax+rax+00h]
0x14002534c  mov     eax, ebx
0x14002534e  mov     rbx, [rsp+70h+arg_0]
0x140025356  add     rsp, 70h
0x14002535a  pop     r14
0x14002535c  pop     rdi
0x14002535d  pop     rbp
0x14002535e  retn
0x140025360  mov     r8d, [rbp+BufferLength]; Size
0x140025364  xor     edx, edx; Val
0x140025366  mov     rcx, rdi; void *
0x140025369  call    memset
0x14002536e  lea     r8, [rbp+BufferLength]; BufferLength
0x140025372  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140025375  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140025379  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140025380  nop     dword ptr [rax+rax+00h]
0x140025385  mov     ebx, eax
0x140025387  test    eax, eax
0x140025389  js      short loc_14002531D
0x14002538b  mov     rcx, [rbp+Dacl]; P
0x14002538f  xor     edx, edx; Tag
0x140025391  call    cs:__imp_ExFreePoolWithTag
0x140025398  nop     dword ptr [rax+rax+00h]
0x14002539d  mov     [r14], rdi
0x1400253a0  jmp     short loc_14002534C
```
