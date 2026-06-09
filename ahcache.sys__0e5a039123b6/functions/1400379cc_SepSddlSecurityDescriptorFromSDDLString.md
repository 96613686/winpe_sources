# SepSddlSecurityDescriptorFromSDDLString

- ea: `0x1400379cc`
- end: `0x140037b6a`
- name: `SepSddlSecurityDescriptorFromSDDLString`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400371fc`

## callees

- `0x140007ad0`
- `0x140007e40`
- `0x1400373b4`
- `0x1400379cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140037af2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037b59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037af2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037b08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037b59`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037acc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140037acc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379f8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400379f8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140037a7a`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140037a7a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140037a93`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140037a93`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140037a08`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140037a08`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140037ab4`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140037b41`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140037ab4`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140037b41`

## string_xrefs

- `0x1400379e3`: `SeConvertStringSecurityDescriptorToSecurityDescriptor`

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
0x1400379cc  mov     [rsp-18h+arg_0], rbx
0x1400379d1  mov     [rsp-18h+BufferLength], edx
0x1400379d5  push    rbp
0x1400379d6  push    rdi
0x1400379d7  push    r14
0x1400379d9  mov     rbp, rsp
0x1400379dc  sub     rsp, 70h
0x1400379e0  mov     rbx, rcx
0x1400379e3  lea     rdx, aSeconvertstrin; "SeConvertStringSecurityDescriptorToSecu"...
0x1400379ea  xorps   xmm0, xmm0
0x1400379ed  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400379f1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400379f5  mov     r14, r8
0x1400379f8  call    cs:__imp_RtlInitUnicodeString
0x1400379ff  nop     dword ptr [rax+rax+00h]
0x140037a04  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140037a08  call    cs:__imp_MmGetSystemRoutineAddress
0x140037a0f  nop     dword ptr [rax+rax+00h]
0x140037a14  mov     rcx, rbx
0x140037a17  test    rax, rax
0x140037a1a  jz      short loc_140037A40
0x140037a1c  xor     r9d, r9d
0x140037a1f  mov     r8, r14
0x140037a22  lea     edx, [r9+1]
0x140037a26  call    _guard_dispatch_icall
0x140037a2b  test    eax, eax
0x140037a2d  js      loc_140037B16
0x140037a33  mov     rcx, [r14]
0x140037a36  or      word ptr [rcx+2], 8
0x140037a3b  jmp     loc_140037B16
0x140037a40  xor     eax, eax
0x140037a42  lea     r9, [rbp+Dacl]
0x140037a46  xorps   xmm0, xmm0
0x140037a49  mov     [rbp+var_8], rax
0x140037a4d  lea     r8, [rbp+arg_18]
0x140037a51  mov     [rbp+arg_18], eax
0x140037a54  movups  [rbp+SecurityDescriptor], xmm0
0x140037a58  mov     [rbp+BufferLength], eax
0x140037a5b  xor     edi, edi
0x140037a5d  movups  [rbp+var_18], xmm0
0x140037a61  mov     [rbp+Dacl], rax
0x140037a65  mov     [r14], rax
0x140037a68  call    SepSddlDaclFromSDDLString
0x140037a6d  mov     ebx, eax
0x140037a6f  test    eax, eax
0x140037a71  js      short loc_140037AE5
0x140037a73  lea     edx, [rdi+1]; Revision
0x140037a76  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140037a7a  call    cs:__imp_RtlCreateSecurityDescriptor
0x140037a81  nop     dword ptr [rax+rax+00h]
0x140037a86  mov     r8, [rbp+Dacl]; Dacl
0x140037a8a  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140037a8e  xor     r9d, r9d; DaclDefaulted
0x140037a91  mov     dl, 1; DaclPresent
0x140037a93  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140037a9a  nop     dword ptr [rax+rax+00h]
0x140037a9f  movzx   eax, word ptr [rbp+arg_18]
0x140037aa3  lea     r8, [rbp+BufferLength]; BufferLength
0x140037aa7  or      word ptr [rbp+SecurityDescriptor+2], ax
0x140037aab  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140037aaf  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140037ab1  mov     [rbp+BufferLength], edi
0x140037ab4  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140037abb  nop     dword ptr [rax+rax+00h]
0x140037ac0  mov     edx, [rbp+BufferLength]; NumberOfBytes
0x140037ac3  lea     ecx, [rdi+1]; PoolType
0x140037ac6  mov     r8d, 64536553h; Tag
0x140037acc  call    cs:__imp_ExAllocatePoolWithTag
0x140037ad3  nop     dword ptr [rax+rax+00h]
0x140037ad8  mov     rdi, rax
0x140037adb  test    rax, rax
0x140037ade  jnz     short loc_140037B28
0x140037ae0  mov     ebx, 0C000009Ah
0x140037ae5  cmp     [rbp+Dacl], 0
0x140037aea  jz      short loc_140037AFE
0x140037aec  mov     rcx, [rbp+Dacl]; P
0x140037af0  xor     edx, edx; Tag
0x140037af2  call    cs:__imp_ExFreePoolWithTag
0x140037af9  nop     dword ptr [rax+rax+00h]
0x140037afe  test    rdi, rdi
0x140037b01  jz      short loc_140037B14
0x140037b03  xor     edx, edx; Tag
0x140037b05  mov     rcx, rdi; P
0x140037b08  call    cs:__imp_ExFreePoolWithTag
0x140037b0f  nop     dword ptr [rax+rax+00h]
0x140037b14  mov     eax, ebx
0x140037b16  mov     rbx, [rsp+70h+arg_0]
0x140037b1e  add     rsp, 70h
0x140037b22  pop     r14
0x140037b24  pop     rdi
0x140037b25  pop     rbp
0x140037b26  retn
0x140037b28  mov     r8d, [rbp+BufferLength]; Size
0x140037b2c  xor     edx, edx; Val
0x140037b2e  mov     rcx, rdi; void *
0x140037b31  call    memset
0x140037b36  lea     r8, [rbp+BufferLength]; BufferLength
0x140037b3a  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x140037b3d  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140037b41  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140037b48  nop     dword ptr [rax+rax+00h]
0x140037b4d  mov     ebx, eax
0x140037b4f  test    eax, eax
0x140037b51  js      short loc_140037AE5
0x140037b53  mov     rcx, [rbp+Dacl]; P
0x140037b57  xor     edx, edx; Tag
0x140037b59  call    cs:__imp_ExFreePoolWithTag
0x140037b60  nop     dword ptr [rax+rax+00h]
0x140037b65  mov     [r14], rdi
0x140037b68  jmp     short loc_140037B14
```
