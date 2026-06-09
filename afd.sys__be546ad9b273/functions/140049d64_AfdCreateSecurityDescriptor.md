# AfdCreateSecurityDescriptor

- ea: `0x140049d64`
- end: `0x140049fda`
- name: `AfdCreateSecurityDescriptor`
- size: `630`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004ac54`

## callees

- `0x140049bd4`
- `0x140049d64`
- `0x140072840`
- `0x140072980`
- `0x1400931d0`
- `0x1400932cc`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049ef3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140049ef3`
- `ntoskrnl!ObGetObjectSecurity` at `0x140049dae`
- `ntoskrnl!ObGetObjectSecurity` at `0x140049dae`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140049e77`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140049e77`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140049e87`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140049e87`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140049f1d`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x140049f1d`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140049f96`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140049f96`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140049e5e`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140049e5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049fb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049f81`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049fb2`
- `ntoskrnl!ExAllocatePool2` at `0x140049ea3`
- `ntoskrnl!ExAllocatePool2` at `0x140049ea3`

## pseudocode

```c
__int64 AfdCreateSecurityDescriptor()
{
  NTSTATUS ObjectSecurity; // ebx
  size_t v2; // r14
  void *Pool2; // rax
  PSECURITY_DESCRIPTOR v4; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
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
  if ( ObjectSecurity < 0 )
  {
    if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
      WPP_SF_d(532, 21, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
    return (unsigned int)ObjectSecurity;
  }
  if ( SecurityDescriptor )
  {
    ObjectSecurity = AfdBuildDeviceAcl(&Dacl);
    if ( ObjectSecurity >= 0 )
    {
      RtlCreateSecurityDescriptor(ModificationDescriptor, 1u);
      RtlSetDaclSecurityDescriptor(ModificationDescriptor, 1u, Dacl, 0);
      v2 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      Pool2 = (void *)ExAllocatePool2(256, v2, 1399088705);
      v4 = Pool2;
      if ( Pool2 )
      {
        memmove(Pool2, SecurityDescriptor, v2);
        AfdAdminSecurityDescriptor = v4;
        GenericMapping = IoGetFileObjectGenericMapping();
        ObjectSecurity = SeSetSecurityDescriptorInfo(
                           0,
                           &SecurityInformation,
                           ModificationDescriptor,
                           &AfdAdminSecurityDescriptor,
                           PagedPool,
                           GenericMapping);
        if ( ObjectSecurity >= 0 )
        {
          if ( AfdAdminSecurityDescriptor != v4 )
            ExFreePoolWithTag(v4, 0);
          ObjectSecurity = 0;
        }
        else
        {
          if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
            WPP_SF_d(532, 25, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
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
      WPP_SF_d(532, 23, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
    }
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
    if ( Dacl )
      ExFreePoolWithTag(Dacl, 0x53646641u);
    return (unsigned int)ObjectSecurity;
  }
  if ( (BYTE2(xmmword_1400875D0) & 0x10) != 0 )
    WPP_SF_(532, 22, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids);
  return 3221225687LL;
}

```

## disassembly

```asm
0x140049d64  push    rbp
0x140049d66  push    rbx
0x140049d67  push    rdi
0x140049d68  push    r14
0x140049d6a  lea     rbp, [rsp-3Fh]
0x140049d6f  sub     rsp, 88h
0x140049d76  mov     rax, cs:__security_cookie
0x140049d7d  xor     rax, rsp
0x140049d80  mov     [rbp+57h+var_28], rax
0x140049d84  mov     rcx, cs:AfdDeviceObject; Object
0x140049d8b  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140049d8f  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049d93  mov     [rbp+57h+Dacl], 0
0x140049d9b  mov     [rbp+57h+MemoryAllocated], 0
0x140049d9f  mov     [rbp+57h+SecurityDescriptor], 0
0x140049da7  mov     [rbp+57h+SecurityInformation], 4
0x140049dae  call    cs:__imp_ObGetObjectSecurity
0x140049db5  nop     dword ptr [rax+rax+00h]
0x140049dba  mov     ebx, eax
0x140049dbc  test    eax, eax
0x140049dbe  jns     short loc_140049DEB
0x140049dc0  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049dc7  jz      loc_140049FBE
0x140049dcd  mov     edx, 15h
0x140049dd2  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049dd9  mov     ecx, 214h
0x140049dde  mov     r9d, eax
0x140049de1  call    WPP_SF_d
0x140049de6  jmp     loc_140049FBE
0x140049deb  cmp     [rbp+57h+SecurityDescriptor], 0
0x140049df0  jnz     short loc_140049E1B
0x140049df2  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049df9  jz      short loc_140049E11
0x140049dfb  mov     edx, 16h
0x140049e00  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049e07  mov     ecx, 214h
0x140049e0c  call    WPP_SF_
0x140049e11  mov     eax, 0C00000D7h
0x140049e16  jmp     loc_140049FC0
0x140049e1b  lea     rcx, [rbp+57h+Dacl]
0x140049e1f  call    AfdBuildDeviceAcl
0x140049e24  mov     ebx, eax
0x140049e26  test    eax, eax
0x140049e28  jns     short loc_140049E55
0x140049e2a  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049e31  jz      loc_140049F8F
0x140049e37  mov     edx, 17h
0x140049e3c  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049e43  mov     ecx, 214h
0x140049e48  mov     r9d, eax
0x140049e4b  call    WPP_SF_d
0x140049e50  jmp     loc_140049F8F
0x140049e55  mov     edx, 1; Revision
0x140049e5a  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x140049e5e  call    cs:__imp_RtlCreateSecurityDescriptor
0x140049e65  nop     dword ptr [rax+rax+00h]
0x140049e6a  mov     r8, [rbp+57h+Dacl]; Dacl
0x140049e6e  lea     rcx, [rbp+57h+ModificationDescriptor]; SecurityDescriptor
0x140049e72  xor     r9d, r9d; DaclDefaulted
0x140049e75  mov     dl, 1; DaclPresent
0x140049e77  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140049e7e  nop     dword ptr [rax+rax+00h]
0x140049e83  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049e87  call    cs:__imp_RtlLengthSecurityDescriptor
0x140049e8e  nop     dword ptr [rax+rax+00h]
0x140049e93  mov     edx, eax
0x140049e95  mov     r8d, 53646641h
0x140049e9b  mov     ecx, 100h
0x140049ea0  mov     r14d, eax
0x140049ea3  call    cs:__imp_ExAllocatePool2
0x140049eaa  nop     dword ptr [rax+rax+00h]
0x140049eaf  mov     rdi, rax
0x140049eb2  test    rax, rax
0x140049eb5  jnz     short loc_140049EDD
0x140049eb7  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049ebe  jz      loc_140049F8F
0x140049ec4  lea     edx, [rax+18h]
0x140049ec7  mov     ecx, 214h
0x140049ecc  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049ed3  call    WPP_SF_
0x140049ed8  jmp     loc_140049F8F
0x140049edd  mov     rdx, [rbp+57h+SecurityDescriptor]; Src
0x140049ee1  mov     r8, r14; Size
0x140049ee4  mov     rcx, rdi; void *
0x140049ee7  call    memmove
0x140049eec  mov     cs:AfdAdminSecurityDescriptor, rdi
0x140049ef3  call    cs:__imp_IoGetFileObjectGenericMapping
0x140049efa  nop     dword ptr [rax+rax+00h]
0x140049eff  mov     [rsp+0A0h+GenericMapping], rax; GenericMapping
0x140049f04  lea     r9, AfdAdminSecurityDescriptor; ObjectsSecurityDescriptor
0x140049f0b  xor     ecx, ecx; Object
0x140049f0d  mov     [rsp+0A0h+PoolType], 1; PoolType
0x140049f15  lea     r8, [rbp+57h+ModificationDescriptor]; ModificationDescriptor
0x140049f19  lea     rdx, [rbp+57h+SecurityInformation]; SecurityInformation
0x140049f1d  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140049f24  nop     dword ptr [rax+rax+00h]
0x140049f29  mov     ebx, eax
0x140049f2b  test    eax, eax
0x140049f2d  jns     short loc_140049F73
0x140049f2f  test    byte ptr cs:xmmword_1400875D0+2, 10h
0x140049f36  jz      short loc_140049F51
0x140049f38  mov     edx, 19h
0x140049f3d  lea     r8, WPP_560c70b1ab923e16318c3ee64288f683_Traceguids
0x140049f44  mov     ecx, 214h
0x140049f49  mov     r9d, eax
0x140049f4c  call    WPP_SF_d
0x140049f51  mov     rcx, cs:AfdAdminSecurityDescriptor; P
0x140049f58  xor     edx, edx; Tag
0x140049f5a  call    cs:__imp_ExFreePoolWithTag
0x140049f61  nop     dword ptr [rax+rax+00h]
0x140049f66  mov     cs:AfdAdminSecurityDescriptor, 0
0x140049f71  jmp     short loc_140049F8F
0x140049f73  cmp     cs:AfdAdminSecurityDescriptor, rdi
0x140049f7a  jz      short loc_140049F8D
0x140049f7c  xor     edx, edx; Tag
0x140049f7e  mov     rcx, rdi; P
0x140049f81  call    cs:__imp_ExFreePoolWithTag
0x140049f88  nop     dword ptr [rax+rax+00h]
0x140049f8d  xor     ebx, ebx
0x140049f8f  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140049f92  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140049f96  call    cs:__imp_ObReleaseObjectSecurity
0x140049f9d  nop     dword ptr [rax+rax+00h]
0x140049fa2  cmp     [rbp+57h+Dacl], 0
0x140049fa7  jz      short loc_140049FBE
0x140049fa9  mov     rcx, [rbp+57h+Dacl]; P
0x140049fad  mov     edx, 53646641h; Tag
0x140049fb2  call    cs:__imp_ExFreePoolWithTag
0x140049fb9  nop     dword ptr [rax+rax+00h]
0x140049fbe  mov     eax, ebx
0x140049fc0  mov     rcx, [rbp+57h+var_28]
0x140049fc4  xor     rcx, rsp; StackCookie
0x140049fc7  call    __security_check_cookie
0x140049fcc  add     rsp, 88h
0x140049fd3  pop     r14
0x140049fd5  pop     rdi
0x140049fd6  pop     rbx
0x140049fd7  pop     rbp
0x140049fd8  retn
```
