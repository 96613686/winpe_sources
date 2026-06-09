# AfdCreateSecurityDescriptor

- ea: `0x140049cc4`
- end: `0x140049f3a`
- name: `AfdCreateSecurityDescriptor`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004abb4`

## callees

- `0x140049b34`
- `0x140049cc4`
- `0x1400726a0`
- `0x140072800`
- `0x1400931d0`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049e53`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049e53`
- `ntoskrnl!ObGetObjectSecurity` at `0x140049d0e`
- `ntoskrnl!ObGetObjectSecurity` at `0x140049d0e`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140049dd7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140049dd7`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140049de7`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140049de7`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140049e7d`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140049e7d`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140049ef6`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140049ef6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140049dbe`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140049dbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049eba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049eba`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049ee1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f12`
- `ntoskrnl!ExAllocatePool2` at `0x140049e03`
- `ntoskrnl!ExAllocatePool2` at `0x140049e03`

## pseudocode

```c
__int64 AfdCreateSecurityDescriptor()
{
  NTSTATUS ObjectSecurity; // eax
  unsigned int v1; // ebx
  int v3; // eax
  size_t v4; // r14
  void *Pool2; // rax
  PSECURITY_DESCRIPTOR v6; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS v8; // eax
  unsigned __int8 MemoryAllocated[8]; // [rsp+30h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+40h] [rbp-9h] BYREF
  DWORD SecurityInformation; // [rsp+48h] [rbp-1h] BYREF
  _BYTE ModificationDescriptor[40]; // [rsp+50h] [rbp+7h] BYREF

  Dacl = 0;
  MemoryAllocated[0] = 0;
  SecurityDescriptor = 0;
  SecurityInformation = 4;
  ObjectSecurity = ObGetObjectSecurity(AfdDeviceObject, &SecurityDescriptor, MemoryAllocated);
  v1 = ObjectSecurity;
  if ( ObjectSecurity < 0 )
  {
    if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
      WPP_SF_d(532, 21, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids, (unsigned int)ObjectSecurity);
    return v1;
  }
  if ( SecurityDescriptor )
  {
    v3 = AfdBuildDeviceAcl(&Dacl);
    v1 = v3;
    if ( v3 >= 0 )
    {
      RtlCreateSecurityDescriptor(ModificationDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(ModificationDescriptor, 1u, Dacl, 0);
      v4 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      Pool2 = (void *)ExAllocatePool2(256, v4, 1399088705);
      v6 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, SecurityDescriptor, v4);
        AfdAdminSecurityDescriptor = v6;
        GenericMapping = IoGetFileObjectGenericMapping();
        v8 = SeSetSecurityDescriptorInfo(
               0,
               &SecurityInformation,
               ModificationDescriptor,
               &AfdAdminSecurityDescriptor,
               PagedPool,
               GenericMapping);
        v1 = v8;
        if ( v8 >= 0 )
        {
          if ( AfdAdminSecurityDescriptor != v6 )
            ExFreePoolWithTag(v6, 0);
          v1 = 0;
        }
        else
        {
          if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
            WPP_SF_d(532, 25, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids, (unsigned int)v8);
          ExFreePoolWithTag(AfdAdminSecurityDescriptor, 0);
          AfdAdminSecurityDescriptor = 0;
        }
      }
      else if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
      {
        WPP_SF_(532, 24, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
      }
    }
    else if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
    {
      WPP_SF_d(532, 23, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids, (unsigned int)v3);
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0x53646641u);
    return v1;
  }
  if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
    WPP_SF_(532, 22, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
  return 3221225687LL;
}

```

## disassembly

```asm
0x140049cc4  push    rbp
0x140049cc6  push    rbx
0x140049cc7  push    rdi
0x140049cc8  push    r14
0x140049cca  lea     rbp, [rsp-3Fh]
0x140049ccf  sub     rsp, 88h
0x140049cd6  mov     rax, cs:__security_cookie
0x140049cdd  xor     rax, rsp
0x140049ce0  mov     [rbp+57h+var_28], rax
0x140049ce4  mov     rcx, cs:AfdDeviceObject; Object
0x140049ceb  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140049cef  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049cf3  mov     [rbp+57h+Dacl], 0
0x140049cfb  mov     [rbp+57h+MemoryAllocated], 0
0x140049cff  mov     [rbp+57h+SecurityDescriptor], 0
0x140049d07  mov     [rbp+57h+SecurityInformation], 4
0x140049d0e  call    cs:__imp_ObGetObjectSecurity
0x140049d15  nop     dword ptr [rax+rax+00h]
0x140049d1a  mov     ebx, eax
0x140049d1c  test    eax, eax
0x140049d1e  jns     short loc_140049D4B
0x140049d20  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049d27  jz      loc_140049F1E
0x140049d2d  mov     edx, 15h
0x140049d32  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049d39  mov     ecx, 214h
0x140049d3e  mov     r9d, eax
0x140049d41  call    WPP_SF_d
0x140049d46  jmp     loc_140049F1E
0x140049d4b  cmp     [rbp+57h+SecurityDescriptor], 0
0x140049d50  jnz     short loc_140049D7B
0x140049d52  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049d59  jz      short loc_140049D71
0x140049d5b  mov     edx, 16h
0x140049d60  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049d67  mov     ecx, 214h
0x140049d6c  call    WPP_SF_
0x140049d71  mov     eax, 0C00000D7h
0x140049d76  jmp     loc_140049F20
0x140049d7b  lea     rcx, [rbp+57h+Dacl]
0x140049d7f  call    AfdBuildDeviceAcl
0x140049d84  mov     ebx, eax
0x140049d86  test    eax, eax
0x140049d88  jns     short loc_140049DB5
0x140049d8a  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049d91  jz      loc_140049EEF
0x140049d97  mov     edx, 17h
0x140049d9c  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049da3  mov     ecx, 214h
0x140049da8  mov     r9d, eax
0x140049dab  call    WPP_SF_d
0x140049db0  jmp     loc_140049EEF
0x140049db5  mov     edx, 1; Revision
0x140049dba  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x140049dbe  call    cs:__imp_RtlCreateSecurityDescriptor
0x140049dc5  nop     dword ptr [rax+rax+00h]
0x140049dca  mov     r8, [rbp+57h+Dacl]; Dacl
0x140049dce  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x140049dd2  xor     r9d, r9d; DaclDefaulted
0x140049dd5  mov     dl, 1; DaclPresent
0x140049dd7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140049dde  nop     dword ptr [rax+rax+00h]
0x140049de3  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049de7  call    cs:__imp_RtlLengthSecurityDescriptor
0x140049dee  nop     dword ptr [rax+rax+00h]
0x140049df3  mov     edx, eax
0x140049df5  mov     r8d, 53646641h
0x140049dfb  mov     ecx, 100h
0x140049e00  mov     r14d, eax
0x140049e03  call    cs:__imp_ExAllocatePool2
0x140049e0a  nop     dword ptr [rax+rax+00h]
0x140049e0f  mov     rdi, rax
0x140049e12  test    rax, rax
0x140049e15  jnz     short loc_140049E3D
0x140049e17  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049e1e  jz      loc_140049EEF
0x140049e24  lea     edx, [rax+18h]
0x140049e27  mov     ecx, 214h
0x140049e2c  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049e33  call    WPP_SF_
0x140049e38  jmp     loc_140049EEF
0x140049e3d  mov     rdx, [rbp+57h+SecurityDescriptor]; Src
0x140049e41  mov     r8, r14; Size
0x140049e44  mov     rcx, rdi; void *
0x140049e47  call    memmove
0x140049e4c  mov     cs:AfdAdminSecurityDescriptor, rdi
0x140049e53  call    cs:__imp_IoGetFileObjectGenericMapping
0x140049e5a  nop     dword ptr [rax+rax+00h]
0x140049e5f  mov     [rsp+0A0h+GenericMapping], rax; GenericMapping
0x140049e64  lea     r9, AfdAdminSecurityDescriptor; ObjectsSecurityDescriptor
0x140049e6b  xor     ecx, ecx; Object
0x140049e6d  mov     [rsp+0A0h+PoolType], 1; PoolType
0x140049e75  lea     r8, [rbp+57h+ModificationDescriptor]; ModificationDescriptor
0x140049e79  lea     rdx, [rbp+57h+SecurityInformation]; SecurityInformation
0x140049e7d  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140049e84  nop     dword ptr [rax+rax+00h]
0x140049e89  mov     ebx, eax
0x140049e8b  test    eax, eax
0x140049e8d  jns     short loc_140049ED3
0x140049e8f  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049e96  jz      short loc_140049EB1
0x140049e98  mov     edx, 19h
0x140049e9d  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049ea4  mov     ecx, 214h
0x140049ea9  mov     r9d, eax
0x140049eac  call    WPP_SF_d
0x140049eb1  mov     rcx, cs:AfdAdminSecurityDescriptor; P
0x140049eb8  xor     edx, edx; Tag
0x140049eba  call    cs:__imp_ExFreePoolWithTag
0x140049ec1  nop     dword ptr [rax+rax+00h]
0x140049ec6  mov     cs:AfdAdminSecurityDescriptor, 0
0x140049ed1  jmp     short loc_140049EEF
0x140049ed3  cmp     cs:AfdAdminSecurityDescriptor, rdi
0x140049eda  jz      short loc_140049EED
0x140049edc  xor     edx, edx; Tag
0x140049ede  mov     rcx, rdi; P
0x140049ee1  call    cs:__imp_ExFreePoolWithTag
0x140049ee8  nop     dword ptr [rax+rax+00h]
0x140049eed  xor     ebx, ebx
0x140049eef  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140049ef2  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049ef6  call    cs:__imp_ObReleaseObjectSecurity
0x140049efd  nop     dword ptr [rax+rax+00h]
0x140049f02  cmp     [rbp+57h+Dacl], 0
0x140049f07  jz      short loc_140049F1E
0x140049f09  mov     rcx, [rbp+57h+Dacl]; P
0x140049f0d  mov     edx, 53646641h; Tag
0x140049f12  call    cs:__imp_ExFreePoolWithTag
0x140049f19  nop     dword ptr [rax+rax+00h]
0x140049f1e  mov     eax, ebx
0x140049f20  mov     rcx, [rbp+57h+var_28]
0x140049f24  xor     rcx, rsp; StackCookie
0x140049f27  call    __security_check_cookie
0x140049f2c  add     rsp, 88h
0x140049f33  pop     r14
0x140049f35  pop     rdi
0x140049f36  pop     rbx
0x140049f37  pop     rbp
0x140049f38  retn
```
