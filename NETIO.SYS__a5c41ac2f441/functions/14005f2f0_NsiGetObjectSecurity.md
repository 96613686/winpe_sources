# NsiGetObjectSecurity

- ea: `0x14005f2f0`
- end: `0x14005f4c0`
- name: `NsiGetObjectSecurity`
- size: `464`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140023ff4`
- `0x140050ea4`
- `0x14005f2f0`
- `0x1400605c8`
- `0x140078100`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005f4a6`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f4a6`
- `ntoskrnl!ZwClose` at `0x14005f492`
- `ntoskrnl!ZwClose` at `0x14005f492`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f40c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f40c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f447`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f447`
- `ntoskrnl!ObGetObjectSecurity` at `0x14005f431`
- `ntoskrnl!ObGetObjectSecurity` at `0x14005f431`
- `ntoskrnl!IoFileObjectType` at `0x14005f3e6`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f47d`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f47d`

## pseudocode

```c
__int64 __fastcall NsiGetObjectSecurity(unsigned int *a1)
{
  _OWORD *v1; // rdx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // r9
  PVOID v6; // rsi
  ACCESS_MASK v7; // r14d
  NTSTATUS ObjectSecurity; // edi
  NTSTATUS v9; // eax
  ULONG v10; // eax
  ULONG v11; // r14d
  BOOLEAN v12; // dl
  PSECURITY_DESCRIPTOR v13; // rcx
  _OWORD v14[2]; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+80h] [rbp+30h] BYREF
  PVOID Object; // [rsp+88h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+90h] [rbp+40h] BYREF
  HANDLE Handle; // [rsp+98h] [rbp+48h] BYREF

  v1 = (_OWORD *)*((_QWORD *)a1 + 1);
  Handle = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  LODWORD(Object) = 0;
  memset(v14, 0, 22);
  if ( v1 )
  {
LABEL_6:
    v5 = *((unsigned int *)v1 + 1);
    if ( (_DWORD)v5 == 1 )
    {
      v6 = 0;
      v7 = ((a1[6] & 7) != 0 ? 0x20000 : 0) | 0x1000000;
      if ( (a1[6] & 8) == 0 )
        v7 = (a1[6] & 7) != 0 ? 0x20000 : 0;
      ObjectSecurity = NsipOpenInformationObjectKeyOrParent(&Handle, (__int64)&Object);
      if ( ObjectSecurity >= 0 )
      {
        Object = 0;
        v9 = ObReferenceObjectByHandle(Handle, v7, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
        v6 = Object;
        ObjectSecurity = v9;
        if ( v9 >= 0 )
        {
          MemoryAllocated = 0;
          ObjectSecurity = ObGetObjectSecurity(Object, &SecurityDescriptor, &MemoryAllocated);
          if ( ObjectSecurity >= 0 )
          {
            v10 = RtlLengthSecurityDescriptor(SecurityDescriptor);
            v11 = v10;
            if ( v10 <= a1[10] )
              memmove(*((void **)a1 + 4), SecurityDescriptor, v10);
            else
              ObjectSecurity = -1073741789;
            v12 = MemoryAllocated;
            v13 = SecurityDescriptor;
            a1[10] = v11;
            ObReleaseObjectSecurity(v13, v12);
          }
        }
      }
      if ( Handle )
        ZwClose(Handle);
      if ( v6 )
        ObfDereferenceObject(v6);
      return (unsigned int)ObjectSecurity;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v5);
      }
      return 3221225659LL;
    }
  }
  v3 = *a1;
  if ( !(_DWORD)v3 )
    return 3221225485LL;
  result = NsipFindModuleGuidByModuleId(v3, v14);
  if ( (int)result >= 0 )
  {
    v1 = v14;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x14005f2f0  push    rbp
0x14005f2f2  push    rbx
0x14005f2f3  push    rsi
0x14005f2f4  push    rdi
0x14005f2f5  push    r14
0x14005f2f7  mov     rbp, rsp
0x14005f2fa  sub     rsp, 50h
0x14005f2fe  mov     rdx, [rcx+8]
0x14005f302  xor     eax, eax
0x14005f304  mov     edi, [rcx+10h]
0x14005f307  xorps   xmm0, xmm0
0x14005f30a  mov     [rbp+Handle], 0
0x14005f312  mov     rbx, rcx
0x14005f315  mov     [rbp+SecurityDescriptor], 0
0x14005f31d  mov     [rbp+MemoryAllocated], 0
0x14005f321  mov     dword ptr [rbp+arg_8], 0
0x14005f328  movups  [rbp+var_20], xmm0
0x14005f32c  mov     qword ptr [rbp+var_20+0Eh], rax
0x14005f330  test    rdx, rdx
0x14005f333  jnz     short loc_14005F35A
0x14005f335  mov     ecx, [rcx]
0x14005f337  test    ecx, ecx
0x14005f339  jnz     short loc_14005F345
0x14005f33b  mov     eax, 0C000000Dh
0x14005f340  jmp     loc_14005F4B4
0x14005f345  lea     rdx, [rbp+var_20]
0x14005f349  call    NsipFindModuleGuidByModuleId
0x14005f34e  test    eax, eax
0x14005f350  js      loc_14005F4B4
0x14005f356  lea     rdx, [rbp+var_20]
0x14005f35a  mov     r9d, [rdx+4]
0x14005f35e  cmp     r9d, 1
0x14005f362  jz      short loc_14005F3A3
0x14005f364  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f36b  lea     rax, WPP_GLOBAL_Control
0x14005f372  cmp     rcx, rax
0x14005f375  jz      short loc_14005F399
0x14005f377  cmp     byte ptr [rcx+29h], 2
0x14005f37b  jb      short loc_14005F399
0x14005f37d  mov     eax, [rcx+2Ch]
0x14005f380  test    al, 10h
0x14005f382  jz      short loc_14005F399
0x14005f384  mov     rcx, [rcx+18h]
0x14005f388  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x14005f38f  mov     edx, 20h ; ' '
0x14005f394  call    WPP_SF_d
0x14005f399  mov     eax, 0C00000BBh
0x14005f39e  jmp     loc_14005F4B4
0x14005f3a3  mov     eax, [rbx+18h]
0x14005f3a6  xor     esi, esi
0x14005f3a8  and     al, 7
0x14005f3aa  mov     r8d, edi
0x14005f3ad  neg     al
0x14005f3af  lea     rax, [rbp+arg_8]
0x14005f3b3  sbb     ecx, ecx
0x14005f3b5  mov     [rsp+50h+Object], rax; __int64
0x14005f3ba  and     ecx, 20000h
0x14005f3c0  mov     r14d, ecx
0x14005f3c3  bts     r14d, 18h
0x14005f3c8  test    byte ptr [rbx+18h], 8
0x14005f3cc  cmovz   r14d, ecx
0x14005f3d0  lea     rcx, [rbp+Handle]; KeyHandle
0x14005f3d4  mov     r9d, r14d
0x14005f3d7  call    NsipOpenInformationObjectKeyOrParent
0x14005f3dc  mov     edi, eax
0x14005f3de  test    eax, eax
0x14005f3e0  js      loc_14005F489
0x14005f3e6  mov     r8, cs:__imp_IoFileObjectType
0x14005f3ed  lea     rax, [rbp+arg_8]
0x14005f3f1  mov     rcx, [rbp+Handle]; Handle
0x14005f3f5  mov     r9b, 1; AccessMode
0x14005f3f8  mov     [rsp+50h+HandleInformation], rsi; HandleInformation
0x14005f3fd  mov     edx, r14d; DesiredAccess
0x14005f400  mov     [rbp+arg_8], rsi
0x14005f404  mov     r8, [r8]; ObjectType
0x14005f407  mov     [rsp+50h+Object], rax; Object
0x14005f40c  call    cs:__imp_ObReferenceObjectByHandle
0x14005f413  nop     dword ptr [rax+rax+00h]
0x14005f418  mov     rsi, [rbp+arg_8]
0x14005f41c  mov     edi, eax
0x14005f41e  test    eax, eax
0x14005f420  js      short loc_14005F489
0x14005f422  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14005f426  mov     [rbp+MemoryAllocated], 0
0x14005f42a  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14005f42e  mov     rcx, rsi; Object
0x14005f431  call    cs:__imp_ObGetObjectSecurity
0x14005f438  nop     dword ptr [rax+rax+00h]
0x14005f43d  mov     edi, eax
0x14005f43f  test    eax, eax
0x14005f441  js      short loc_14005F489
0x14005f443  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14005f447  call    cs:__imp_RtlLengthSecurityDescriptor
0x14005f44e  nop     dword ptr [rax+rax+00h]
0x14005f453  mov     r14d, eax
0x14005f456  cmp     eax, [rbx+28h]
0x14005f459  jbe     short loc_14005F462
0x14005f45b  mov     edi, 0C0000023h
0x14005f460  jmp     short loc_14005F472
0x14005f462  mov     rdx, [rbp+SecurityDescriptor]; Src
0x14005f466  mov     r8, r14; Size
0x14005f469  mov     rcx, [rbx+20h]; void *
0x14005f46d  call    memmove
0x14005f472  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x14005f475  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14005f479  mov     [rbx+28h], r14d
0x14005f47d  call    cs:__imp_ObReleaseObjectSecurity
0x14005f484  nop     dword ptr [rax+rax+00h]
0x14005f489  mov     rcx, [rbp+Handle]; Handle
0x14005f48d  test    rcx, rcx
0x14005f490  jz      short loc_14005F49E
0x14005f492  call    cs:__imp_ZwClose
0x14005f499  nop     dword ptr [rax+rax+00h]
0x14005f49e  test    rsi, rsi
0x14005f4a1  jz      short loc_14005F4B2
0x14005f4a3  mov     rcx, rsi; Object
0x14005f4a6  call    cs:__imp_ObfDereferenceObject
0x14005f4ad  nop     dword ptr [rax+rax+00h]
0x14005f4b2  mov     eax, edi
0x14005f4b4  add     rsp, 50h
0x14005f4b8  pop     r14
0x14005f4ba  pop     rdi
0x14005f4bb  pop     rsi
0x14005f4bc  pop     rbx
0x14005f4bd  pop     rbp
0x14005f4be  retn
```
