# NsiSetObjectSecurity

- ea: `0x14005f520`
- end: `0x14005f7e1`
- name: `NsiSetObjectSecurity`
- size: `705`
- prototype: `__int64 __fastcall(__int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004ffec`

## callees

- `0x140027ef4`
- `0x14002d280`
- `0x1400468f4`
- `0x140050ea4`
- `0x14005f520`
- `0x1400605c8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005f720`
- `ntoskrnl!ObfDereferenceObject` at `0x14005f720`
- `ntoskrnl!ZwClose` at `0x14005f7c0`
- `ntoskrnl!ZwClose` at `0x14005f7c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7ab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005f7ab`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f6e9`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005f6e9`
- `ntoskrnl!ObGetObjectSecurity` at `0x14005f70f`
- `ntoskrnl!ObGetObjectSecurity` at `0x14005f70f`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f767`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f78a`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f767`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14005f78a`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14005f564`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14005f564`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f79f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005f79f`
- `ntoskrnl!ZwSetSecurityObject` at `0x14005f668`
- `ntoskrnl!ZwSetSecurityObject` at `0x14005f668`

## pseudocode

```c
__int64 __fastcall NsiSetObjectSecurity(__int128 *a1)
{
  __int128 v1; // xmm0
  void *v3; // rcx
  unsigned int *v4; // rsi
  __int64 result; // rax
  __int64 v6; // r9
  SECURITY_INFORMATION v7; // r14d
  NTSTATUS v8; // ebx
  void *v9; // r8
  PVOID v10; // rdi
  NTSTATUS ObjectSecurity; // ebx
  _BYTE v12[24]; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp+40h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+48h] BYREF

  v1 = *a1;
  v3 = (void *)*((_QWORD *)a1 + 4);
  Handle = 0;
  memset(v12, 0, 22);
  if ( !v3 || !RtlValidSecurityDescriptor(v3) )
    return 3221225485LL;
  v4 = (unsigned int *)*((_QWORD *)&v1 + 1);
  if ( !*((_QWORD *)&v1 + 1) )
  {
    if ( (_DWORD)v1 )
    {
      result = NsipFindModuleGuidByModuleId((unsigned int)v1, v12);
      if ( (int)result < 0 )
        return result;
      v4 = (unsigned int *)v12;
      goto LABEL_7;
    }
    return 3221225485LL;
  }
LABEL_7:
  v6 = v4[1];
  if ( (_DWORD)v6 == 1 )
  {
    v7 = *((_DWORD *)a1 + 6);
    if ( !v7 )
      v7 = 4;
    v8 = NsipCreateInformationObjectKey(&Handle);
    if ( v8 >= 0 )
    {
      v9 = (void *)*((_QWORD *)a1 + 4);
      SecurityDescriptor = 0;
      MemoryAllocated = 0;
      v8 = ZwSetSecurityObject(Handle, v7, v9);
      if ( v8 >= 0 )
      {
        Object = 0;
        if ( ObReferenceObjectByHandle(Handle, 0, 0, 0, &Object, 0) < 0
          || (v10 = Object,
              ObjectSecurity = ObGetObjectSecurity(Object, &SecurityDescriptor, &MemoryAllocated),
              ObfDereferenceObject(v10),
              ObjectSecurity < 0) )
        {
          v8 = 0;
        }
        else
        {
          NsipLockCacheListExclusive();
          v8 = NsipLookupCacheList(v4, (__int64)&Object);
          if ( v8 )
          {
            ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
            v8 = 0;
          }
          else
          {
            if ( MEMORY[0x20] )
              ObReleaseObjectSecurity(MEMORY[0x20], MEMORY[0x28]);
            MEMORY[0x20] = SecurityDescriptor;
            MEMORY[0x28] = MemoryAllocated;
          }
          ExReleaseResourceLite(&NsipCachedRegistryKeyListLock);
          KeLeaveCriticalRegion();
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
          (unsigned int)v8);
      }
    }
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v6);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x14005f520  push    rbp
0x14005f522  push    rbx
0x14005f523  push    rsi
0x14005f524  push    rdi
0x14005f525  push    r14
0x14005f527  mov     rbp, rsp
0x14005f52a  sub     rsp, 70h
0x14005f52e  movups  xmm0, xmmword ptr [rcx]
0x14005f531  xor     eax, eax
0x14005f533  mov     rdi, rcx
0x14005f536  movsd   xmm1, qword ptr [rcx+10h]
0x14005f53b  mov     rcx, [rcx+20h]; SecurityDescriptor
0x14005f53f  movsd   [rbp+var_20], xmm1
0x14005f544  mov     [rbp+Handle], 0
0x14005f54c  movups  xmmword ptr [rbp+Buf2], xmm0
0x14005f550  xorps   xmm0, xmm0
0x14005f553  movups  xmmword ptr [rbp+var_18], xmm0
0x14005f557  mov     qword ptr [rbp+var_18+0Eh], rax
0x14005f55b  test    rcx, rcx
0x14005f55e  jz      loc_14005F7D0
0x14005f564  call    cs:__imp_RtlValidSecurityDescriptor
0x14005f56b  nop     dword ptr [rax+rax+00h]
0x14005f570  test    al, al
0x14005f572  jz      loc_14005F7D0
0x14005f578  mov     rsi, [rbp+Buf2+8]
0x14005f57c  test    rsi, rsi
0x14005f57f  jnz     short loc_14005F5A1
0x14005f581  mov     ecx, dword ptr [rbp+Buf2]
0x14005f584  test    ecx, ecx
0x14005f586  jz      loc_14005F7D0
0x14005f58c  lea     rdx, [rbp+var_18]
0x14005f590  call    NsipFindModuleGuidByModuleId
0x14005f595  test    eax, eax
0x14005f597  js      loc_14005F7D5
0x14005f59d  lea     rsi, [rbp+var_18]
0x14005f5a1  mov     r9d, [rsi+4]
0x14005f5a5  cmp     r9d, 1
0x14005f5a9  jz      short loc_14005F5EA
0x14005f5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f5b2  lea     rax, WPP_GLOBAL_Control
0x14005f5b9  cmp     rcx, rax
0x14005f5bc  jz      short loc_14005F5E0
0x14005f5be  cmp     byte ptr [rcx+29h], 2
0x14005f5c2  jb      short loc_14005F5E0
0x14005f5c4  mov     eax, [rcx+2Ch]
0x14005f5c7  test    al, 10h
0x14005f5c9  jz      short loc_14005F5E0
0x14005f5cb  mov     rcx, [rcx+18h]
0x14005f5cf  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x14005f5d6  mov     edx, 21h ; '!'
0x14005f5db  call    WPP_SF_d
0x14005f5e0  mov     eax, 0C00000BBh
0x14005f5e5  jmp     loc_14005F7D5
0x14005f5ea  mov     r14d, [rdi+18h]
0x14005f5ee  mov     edx, 4
0x14005f5f3  test    r14d, r14d
0x14005f5f6  cmovz   r14d, edx
0x14005f5fa  mov     eax, r14d
0x14005f5fd  and     al, 3
0x14005f5ff  neg     al
0x14005f601  sbb     ecx, ecx
0x14005f603  and     ecx, 80000h
0x14005f609  add     ecx, 20000h
0x14005f60f  mov     r9d, ecx
0x14005f612  bts     r9d, 12h
0x14005f617  test    dl, r14b
0x14005f61a  lea     rdx, [rbp+Buf2]
0x14005f61e  cmovz   r9d, ecx
0x14005f622  lea     rcx, [rbp+Handle]; KeyHandle
0x14005f626  mov     r8d, r9d
0x14005f629  bts     r8d, 18h
0x14005f62e  test    r14b, 8
0x14005f632  cmovz   r8d, r9d
0x14005f636  mov     r9, [rdi+20h]
0x14005f63a  call    NsipCreateInformationObjectKey
0x14005f63f  mov     ebx, eax
0x14005f641  test    eax, eax
0x14005f643  js      loc_14005F7B7
0x14005f649  mov     r8, [rdi+20h]; SecurityDescriptor
0x14005f64d  mov     edx, r14d; SecurityInformation
0x14005f650  mov     rcx, [rbp+Handle]; Handle
0x14005f654  mov     [rbp+var_40], 0
0x14005f65c  mov     [rbp+SecurityDescriptor], 0
0x14005f664  mov     [rbp+MemoryAllocated], 0
0x14005f668  call    cs:__imp_ZwSetSecurityObject
0x14005f66f  nop     dword ptr [rax+rax+00h]
0x14005f674  mov     ebx, eax
0x14005f676  test    eax, eax
0x14005f678  jns     short loc_14005F6C3
0x14005f67a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f681  lea     rax, WPP_GLOBAL_Control
0x14005f688  cmp     rcx, rax
0x14005f68b  jz      loc_14005F7B7
0x14005f691  cmp     byte ptr [rcx+29h], 2
0x14005f695  jb      loc_14005F7B7
0x14005f69b  mov     eax, [rcx+2Ch]
0x14005f69e  test    al, 10h
0x14005f6a0  jz      loc_14005F7B7
0x14005f6a6  mov     rcx, [rcx+18h]
0x14005f6aa  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x14005f6b1  mov     edx, 22h ; '"'
0x14005f6b6  mov     r9d, ebx
0x14005f6b9  call    WPP_SF_d
0x14005f6be  jmp     loc_14005F7B7
0x14005f6c3  mov     rcx, [rbp+Handle]; Handle
0x14005f6c7  lea     rax, [rbp+arg_18]
0x14005f6cb  mov     [rsp+70h+HandleInformation], 0; HandleInformation
0x14005f6d4  xor     r9d, r9d; AccessMode
0x14005f6d7  xor     r8d, r8d; ObjectType
0x14005f6da  mov     [rsp+70h+Object], rax; Object
0x14005f6df  xor     edx, edx; DesiredAccess
0x14005f6e1  mov     [rbp+arg_18], 0
0x14005f6e9  call    cs:__imp_ObReferenceObjectByHandle
0x14005f6f0  nop     dword ptr [rax+rax+00h]
0x14005f6f5  test    eax, eax
0x14005f6f7  jns     short loc_14005F700
0x14005f6f9  xor     ebx, ebx
0x14005f6fb  jmp     loc_14005F7B7
0x14005f700  mov     rdi, [rbp+arg_18]
0x14005f704  lea     r8, [rbp+MemoryAllocated]; MemoryAllocated
0x14005f708  mov     rcx, rdi; Object
0x14005f70b  lea     rdx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14005f70f  call    cs:__imp_ObGetObjectSecurity
0x14005f716  nop     dword ptr [rax+rax+00h]
0x14005f71b  mov     rcx, rdi; Object
0x14005f71e  mov     ebx, eax
0x14005f720  call    cs:__imp_ObfDereferenceObject
0x14005f727  nop     dword ptr [rax+rax+00h]
0x14005f72c  test    ebx, ebx
0x14005f72e  js      short loc_14005F6F9
0x14005f730  call    NsipLockCacheListExclusive
0x14005f735  mov     edx, dword ptr [rbp+var_20]
0x14005f738  lea     rax, [rbp+arg_18]
0x14005f73c  lea     r9, [rbp+var_40]
0x14005f740  mov     [rsp+70h+Object], rax; __int64
0x14005f745  lea     r8, [rbp+var_38]
0x14005f749  mov     rcx, rsi; Buf2
0x14005f74c  call    NsipLookupCacheList
0x14005f751  mov     ebx, eax
0x14005f753  test    eax, eax
0x14005f755  jnz     short loc_14005F783
0x14005f757  mov     rdi, [rbp+var_40]
0x14005f75b  mov     rcx, [rdi+20h]; SecurityDescriptor
0x14005f75f  test    rcx, rcx
0x14005f762  jz      short loc_14005F773
0x14005f764  mov     dl, [rdi+28h]; MemoryAllocated
0x14005f767  call    cs:__imp_ObReleaseObjectSecurity
0x14005f76e  nop     dword ptr [rax+rax+00h]
0x14005f773  mov     rax, [rbp+SecurityDescriptor]
0x14005f777  mov     [rdi+20h], rax
0x14005f77b  mov     al, [rbp+MemoryAllocated]
0x14005f77e  mov     [rdi+28h], al
0x14005f781  jmp     short loc_14005F798
0x14005f783  mov     dl, [rbp+MemoryAllocated]; MemoryAllocated
0x14005f786  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14005f78a  call    cs:__imp_ObReleaseObjectSecurity
0x14005f791  nop     dword ptr [rax+rax+00h]
0x14005f796  xor     ebx, ebx
0x14005f798  lea     rcx, NsipCachedRegistryKeyListLock; Resource
0x14005f79f  call    cs:__imp_ExReleaseResourceLite
0x14005f7a6  nop     dword ptr [rax+rax+00h]
0x14005f7ab  call    cs:__imp_KeLeaveCriticalRegion
0x14005f7b2  nop     dword ptr [rax+rax+00h]
0x14005f7b7  mov     rcx, [rbp+Handle]; Handle
0x14005f7bb  test    rcx, rcx
0x14005f7be  jz      short loc_14005F7CC
0x14005f7c0  call    cs:__imp_ZwClose
0x14005f7c7  nop     dword ptr [rax+rax+00h]
0x14005f7cc  mov     eax, ebx
0x14005f7ce  jmp     short loc_14005F7D5
0x14005f7d0  mov     eax, 0C000000Dh
0x14005f7d5  add     rsp, 70h
0x14005f7d9  pop     r14
0x14005f7db  pop     rdi
0x14005f7dc  pop     rsi
0x14005f7dd  pop     rbx
0x14005f7de  pop     rbp
0x14005f7df  retn
```
