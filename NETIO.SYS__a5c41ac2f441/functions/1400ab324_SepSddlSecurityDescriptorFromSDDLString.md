# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400ab324`
- end: `0x1400ab4c2`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400aab4c`

## callees

- `0x140078080`
- `0x140078400`
- `0x1400aad04`
- `0x1400ab324`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ab3d2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400ab3d2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ab3eb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400ab3eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab44a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab460`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab4b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab44a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab460`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ab4b1`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400ab40c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400ab499`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400ab40c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400ab499`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ab424`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400ab424`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ab360`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400ab360`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ab350`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ab350`

## string_xrefs

- `0x1400ab33b`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400ab324  mov     [rsp-18h+arg_0], rbx
0x1400ab329  mov     [rsp-18h+BufferLength], edx
0x1400ab32d  push    rbp
0x1400ab32e  push    rdi
0x1400ab32f  push    r14
0x1400ab331  mov     rbp, rsp
0x1400ab334  sub     rsp, 70h
0x1400ab338  mov     rbx, rcx
0x1400ab33b  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400ab342  xorps   xmm0, xmm0
0x1400ab345  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400ab349  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400ab34d  mov     r14, r8
0x1400ab350  call    cs:__imp_RtlInitUnicodeString
0x1400ab357  nop     dword ptr [rax+rax+00h]
0x1400ab35c  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x1400ab360  call    cs:__imp_MmGetSystemRoutineAddress
0x1400ab367  nop     dword ptr [rax+rax+00h]
0x1400ab36c  mov     rcx, rbx
0x1400ab36f  test    rax, rax
0x1400ab372  jz      short loc_1400AB398
0x1400ab374  xor     r9d, r9d
0x1400ab377  mov     r8, r14
0x1400ab37a  lea     edx, [r9+1]
0x1400ab37e  call    _guard_dispatch_icall
0x1400ab383  test    eax, eax
0x1400ab385  js      loc_1400AB46E
0x1400ab38b  mov     rcx, [r14]
0x1400ab38e  or      word ptr [rcx+2], 8
0x1400ab393  jmp     loc_1400AB46E
0x1400ab398  xor     eax, eax
0x1400ab39a  lea     r9, [rbp+Dacl]
0x1400ab39e  xorps   xmm0, xmm0
0x1400ab3a1  mov     [rbp+var_8], rax
0x1400ab3a5  lea     r8, [rbp+arg_18]
0x1400ab3a9  mov     [rbp+arg_18], eax
0x1400ab3ac  movups  [rbp+SecurityDescriptor], xmm0
0x1400ab3b0  mov     [rbp+BufferLength], eax
0x1400ab3b3  xor     edi, edi
0x1400ab3b5  movups  [rbp+var_18], xmm0
0x1400ab3b9  mov     [rbp+Dacl], rax
0x1400ab3bd  mov     [r14], rax
0x1400ab3c0  call    SepSddlDaclFromSDDLString
0x1400ab3c5  mov     ebx, eax
0x1400ab3c7  test    eax, eax
0x1400ab3c9  js      short loc_1400AB43D
0x1400ab3cb  lea     edx, [rdi+1]; Revision
0x1400ab3ce  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400ab3d2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400ab3d9  nop     dword ptr [rax+rax+00h]
0x1400ab3de  mov     r8, [rbp+Dacl]; Dacl
0x1400ab3e2  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400ab3e6  xor     r9d, r9d; DaclDefaulted
0x1400ab3e9  mov     dl, 1; DaclPresent
0x1400ab3eb  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400ab3f2  nop     dword ptr [rax+rax+00h]
0x1400ab3f7  movzx   eax, word ptr [rbp+arg_18]
0x1400ab3fb  lea     r8, [rbp+BufferLength]; BufferLength
0x1400ab3ff  or      word ptr [rbp+SecurityDescriptor+2], ax
0x1400ab403  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400ab407  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1400ab409  mov     [rbp+BufferLength], edi
0x1400ab40c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400ab413  nop     dword ptr [rax+rax+00h]
0x1400ab418  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x1400ab41b  lea     ecx, [rdi+1]; PoolType
0x1400ab41e  mov     r8d, 64536553h; Tag
0x1400ab424  call    cs:__imp_ExAllocatePoolWithTag
0x1400ab42b  nop     dword ptr [rax+rax+00h]
0x1400ab430  mov     rdi, rax
0x1400ab433  test    rax, rax
0x1400ab436  jnz     short loc_1400AB480
0x1400ab438  mov     ebx, 0C000009Ah
0x1400ab43d  cmp     [rbp+Dacl], 0
0x1400ab442  jz      short loc_1400AB456
0x1400ab444  mov     rcx, [rbp+Dacl]; P
0x1400ab448  xor     edx, edx; Tag
0x1400ab44a  call    cs:__imp_ExFreePoolWithTag
0x1400ab451  nop     dword ptr [rax+rax+00h]
0x1400ab456  test    rdi, rdi
0x1400ab459  jz      short loc_1400AB46C
0x1400ab45b  xor     edx, edx; Tag
0x1400ab45d  mov     rcx, rdi; P
0x1400ab460  call    cs:__imp_ExFreePoolWithTag
0x1400ab467  nop     dword ptr [rax+rax+00h]
0x1400ab46c  mov     eax, ebx
0x1400ab46e  mov     rbx, [rsp+70h+arg_0]
0x1400ab476  add     rsp, 70h
0x1400ab47a  pop     r14
0x1400ab47c  pop     rdi
0x1400ab47d  pop     rbp
0x1400ab47e  retn
0x1400ab480  mov     r8d, [rbp+BufferLength]; Size
0x1400ab484  xor     edx, edx; Val
0x1400ab486  mov     rcx, rdi; void *
0x1400ab489  call    memset
0x1400ab48e  lea     r8, [rbp+BufferLength]; BufferLength
0x1400ab492  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400ab495  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400ab499  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400ab4a0  nop     dword ptr [rax+rax+00h]
0x1400ab4a5  mov     ebx, eax
0x1400ab4a7  test    eax, eax
0x1400ab4a9  js      short loc_1400AB43D
0x1400ab4ab  mov     rcx, [rbp+Dacl]; P
0x1400ab4af  xor     edx, edx; Tag
0x1400ab4b1  call    cs:__imp_ExFreePoolWithTag
0x1400ab4b8  nop     dword ptr [rax+rax+00h]
0x1400ab4bd  mov     [r14], rdi
0x1400ab4c0  jmp     short loc_1400AB46C
```
