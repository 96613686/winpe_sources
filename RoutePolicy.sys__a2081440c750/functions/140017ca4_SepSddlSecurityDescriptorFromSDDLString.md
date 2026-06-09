# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x140017ca4`
- end: `0x140017e42`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400174bc`

## callees

- `0x14000a6c0`
- `0x14000aa80`
- `0x140017674`
- `0x140017ca4`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140017d52`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140017d52`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017da4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017da4`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017d8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017e19`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017d8c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140017e19`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140017d6b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140017d6b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017ce0`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140017ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017de0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017e31`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017de0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017e31`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017cd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140017cd0`

## string_xrefs

- `0x140017cbb`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x140017ca4  mov     [rsp-18h+arg_0], rbx
0x140017ca9  mov     [rsp-18h+BufferLength], edx
0x140017cad  push    rbp
0x140017cae  push    rdi
0x140017caf  push    r14
0x140017cb1  mov     rbp, rsp
0x140017cb4  sub     rsp, 70h
0x140017cb8  mov     rbx, rcx
0x140017cbb  lea     rdx, aSeconvertstrin_0; "SeConvertStringSecurityDescriptorToSecu"...
0x140017cc2  xorps   xmm0, xmm0
0x140017cc5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140017cc9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140017ccd  mov     r14, r8
0x140017cd0  call    cs:__imp_RtlInitUnicodeString
0x140017cd7  nop     dword ptr [rax+rax+00h]
0x140017cdc  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140017ce0  call    cs:__imp_MmGetSystemRoutineAddress
0x140017ce7  nop     dword ptr [rax+rax+00h]
0x140017cec  mov     rcx, rbx
0x140017cef  test    rax, rax
0x140017cf2  jz      short loc_140017D18
0x140017cf4  xor     r9d, r9d
0x140017cf7  mov     r8, r14
0x140017cfa  lea     edx, [r9+1]
0x140017cfe  call    _guard_dispatch_icall
0x140017d03  test    eax, eax
0x140017d05  js      loc_140017DEE
0x140017d0b  mov     rcx, [r14]
0x140017d0e  or      word ptr [rcx+2], 8
0x140017d13  jmp     loc_140017DEE
0x140017d18  xor     eax, eax
0x140017d1a  lea     r9, [rbp+Dacl]
0x140017d1e  xorps   xmm0, xmm0
0x140017d21  mov     [rbp+var_8], rax
0x140017d25  lea     r8, [rbp+arg_18]
0x140017d29  mov     [rbp+arg_18], eax
0x140017d2c  movups  [rbp+SecurityDescriptor], xmm0
0x140017d30  mov     [rbp+BufferLength], eax
0x140017d33  xor     edi, edi
0x140017d35  movups  [rbp+var_18], xmm0
0x140017d39  mov     [rbp+Dacl], rax
0x140017d3d  mov     [r14], rax
0x140017d40  call    SepSddlDaclFromSDDLString
0x140017d45  mov     ebx, eax
0x140017d47  test    eax, eax
0x140017d49  js      short loc_140017DBD
0x140017d4b  lea     edx, [rdi+1]; Revision
0x140017d4e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140017d52  call    cs:__imp_RtlCreateSecurityDescriptor
0x140017d59  nop     dword ptr [rax+rax+00h]
0x140017d5e  mov     r8, [rbp+Dacl]; Dacl
0x140017d62  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140017d66  xor     r9d, r9d; DaclDefaulted
0x140017d69  mov     dl, 1; DaclPresent
0x140017d6b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140017d72  nop     dword ptr [rax+rax+00h]
0x140017d77  movzx   eax, word ptr [rbp+arg_18]
0x140017d7b  lea     r8, [rbp+BufferLength]; BufferLength
0x140017d7f  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140017d83  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140017d87  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140017d89  mov     [rbp+BufferLength], edi
0x140017d8c  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140017d93  nop     dword ptr [rax+rax+00h]
0x140017d98  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140017d9b  lea     ecx, [rdi+1]; PoolType
0x140017d9e  mov     r8d, 64536553h; Tag
0x140017da4  call    cs:__imp_ExAllocatePoolWithTag
0x140017dab  nop     dword ptr [rax+rax+00h]
0x140017db0  mov     rdi, rax
0x140017db3  test    rax, rax
0x140017db6  jnz     short loc_140017E00
0x140017db8  mov     ebx, 0C000009Ah
0x140017dbd  cmp     [rbp+Dacl], 0
0x140017dc2  jz      short loc_140017DD6
0x140017dc4  mov     rcx, [rbp+Dacl]; P
0x140017dc8  xor     edx, edx; Tag
0x140017dca  call    cs:__imp_ExFreePoolWithTag
0x140017dd1  nop     dword ptr [rax+rax+00h]
0x140017dd6  test    rdi, rdi
0x140017dd9  jz      short loc_140017DEC
0x140017ddb  xor     edx, edx; Tag
0x140017ddd  mov     rcx, rdi; P
0x140017de0  call    cs:__imp_ExFreePoolWithTag
0x140017de7  nop     dword ptr [rax+rax+00h]
0x140017dec  mov     eax, ebx
0x140017dee  mov     rbx, [rsp+70h+arg_0]
0x140017df6  add     rsp, 70h
0x140017dfa  pop     r14
0x140017dfc  pop     rdi
0x140017dfd  pop     rbp
0x140017dfe  retn
0x140017e00  mov     r8d, [rbp+BufferLength]; Size
0x140017e04  xor     edx, edx; Val
0x140017e06  mov     rcx, rdi; void *
0x140017e09  call    memset
0x140017e0e  lea     r8, [rbp+BufferLength]; BufferLength
0x140017e12  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140017e15  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140017e19  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140017e20  nop     dword ptr [rax+rax+00h]
0x140017e25  mov     ebx, eax
0x140017e27  test    eax, eax
0x140017e29  js      short loc_140017DBD
0x140017e2b  mov     rcx, [rbp+Dacl]; P
0x140017e2f  xor     edx, edx; Tag
0x140017e31  call    cs:__imp_ExFreePoolWithTag
0x140017e38  nop     dword ptr [rax+rax+00h]
0x140017e3d  mov     [r14], rdi
0x140017e40  jmp     short loc_140017DEC
```
