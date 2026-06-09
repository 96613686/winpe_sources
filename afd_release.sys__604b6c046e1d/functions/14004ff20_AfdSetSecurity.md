# AfdSetSecurity

- ea: `0x14004ff20`
- end: `0x14005024b`
- name: `AfdSetSecurity`
- size: `811`
- prototype: `__int64 __fastcall(__int64, DWORD, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x14000fcd0`
- `0x14001e274`
- `0x14001ee68`
- `0x14001eec0`
- `0x14004ff20`
- `0x1400726a0`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005006f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400500b3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140050113`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005006f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400500b3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140050113`
- `ntoskrnl!SeLockSubjectContext` at `0x1400500a7`
- `ntoskrnl!SeLockSubjectContext` at `0x1400500a7`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400500f4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400500f4`
- `ntoskrnl!SeAssignSecurity` at `0x1400500e2`
- `ntoskrnl!SeAssignSecurity` at `0x1400500e2`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140050161`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140050161`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14005013b`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x14005013b`
- `ntoskrnl!SeCreateAccessState` at `0x14005008d`
- `ntoskrnl!SeCreateAccessState` at `0x14005008d`
- `ntoskrnl!SeDeleteAccessState` at `0x140050105`
- `ntoskrnl!SeDeleteAccessState` at `0x140050105`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005022b`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14005022b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050176`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050176`

## pseudocode

```c
__int64 __fastcall AfdSetSecurity(__int64 a1, DWORD a2, void *a3)
{
  int v3; // eax
  __int64 v5; // rcx
  NTSTATUS AccessState; // ebx
  signed __int32 v9; // eax
  void *v10; // r14
  PGENERIC_MAPPING v11; // rax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  void *v14; // rcx
  int v15; // eax
  NTSTATUS v16; // eax
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  void *v18; // [rsp+48h] [rbp-B8h] BYREF
  DWORD SecurityInformation; // [rsp+50h] [rbp-B0h] BYREF
  void *v20; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v21[5]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[224]; // [rsp+100h] [rbp+0h] BYREF

  v3 = *(_DWORD *)(a1 + 8);
  v5 = *(_QWORD *)(a1 + 272);
  SecurityInformation = a2;
  NewDescriptor = 0;
  v18 = 0;
  if ( (v3 & 0x100) != 0 )
  {
    if ( v5 )
      goto LABEL_9;
    return (unsigned int)-1073741436;
  }
  if ( v5 && *(_BYTE *)(v5 + 24) )
  {
    *(_DWORD *)(a1 + 16) = *(_DWORD *)(*(_QWORD *)(a1 + 272) + 72LL);
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0 && (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
      return (unsigned int)-1073741808;
    do
    {
LABEL_9:
      v9 = *(_DWORD *)(a1 + 368);
      if ( v9 > 0 )
        return (unsigned int)-1073741436;
    }
    while ( v9 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 368), v9 - 1, v9) );
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 && *(_BYTE *)(a1 + 2) != 2
      || (*(_DWORD *)(a1 + 8) & 0x100) == 0 && *(_BYTE *)(a1 + 2) != 1 )
    {
      AccessState = -1073741436;
LABEL_34:
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 368));
      return (unsigned int)AccessState;
    }
    if ( !AfdPreventSecurityDescriptorSet(a1) )
    {
      AccessState = -1073741808;
      goto LABEL_34;
    }
    v10 = *(void **)(a1 + 40);
    NewDescriptor = v10;
    if ( v10 )
    {
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      AccessState = SeSetSecurityDescriptorInfo(
                      0,
                      &SecurityInformation,
                      a3,
                      &NewDescriptor,
                      PagedPool,
                      FileObjectGenericMapping);
    }
    else
    {
      memset(v21, 0, sizeof(v21));
      memset(v22, 0, sizeof(v22));
      v11 = IoGetFileObjectGenericMapping();
      AccessState = SeCreateAccessState(v21, v22, 0x10000000, v11);
      if ( AccessState < 0 )
        goto LABEL_33;
      SeLockSubjectContext(&v21[1]);
      GenericMapping = IoGetFileObjectGenericMapping();
      AccessState = SeAssignSecurity(0, a3, &NewDescriptor, 0, &v21[1], GenericMapping, PagedPool);
      SeUnlockSubjectContext(&v21[1]);
      SeDeleteAccessState(v21);
    }
    if ( AccessState < 0 )
      goto LABEL_33;
    AccessState = ObLogSecurityDescriptor(NewDescriptor, &v18, 1);
    ExFreePoolWithTag(NewDescriptor, 0);
    if ( AccessState < 0 )
      goto LABEL_33;
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 || (*(_DWORD *)(a1 + 8) & 0x200) != 0 )
    {
      memset(v21, 0, 0x50u);
      v20 = v18;
      v21[1].ClientToken = &v20;
      v15 = *(_DWORD *)(a1 + 8);
      HIDWORD(v21[0].PrimaryToken) = 65533;
      LODWORD(v21[0].ProcessAuditId) = 24;
      *(_QWORD *)&v21[1].ImpersonationLevel = 8;
      if ( (v15 & 0x100) != 0 )
        v16 = AfdTLIoControl(
                *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(a1 + 24) + 8LL),
                *(_QWORD *)(a1 + 16),
                (__int64)v21,
                a1);
      else
        v16 = AfdTdiTlSyncIoControl(a1, (__int64)v21);
      v14 = v18;
      AccessState = v16;
      goto LABEL_32;
    }
    *(_QWORD *)(a1 + 40) = v18;
    if ( v10 )
    {
      v14 = v10;
LABEL_32:
      ObDereferenceSecurityDescriptor(v14, 1);
    }
LABEL_33:
    AfdReallowSecurityDescriptorSet(a1);
    goto LABEL_34;
  }
  return (unsigned int)-1073741436;
}

```

## disassembly

```asm
0x14004ff20  mov     [rsp-8+arg_18], rbx
0x14004ff25  push    rbp
0x14004ff26  push    rdi
0x14004ff27  push    r12
0x14004ff29  push    r14
0x14004ff2b  push    r15
0x14004ff2d  lea     rbp, [rsp-0F0h]
0x14004ff35  sub     rsp, 1F0h
0x14004ff3c  mov     rax, cs:__security_cookie
0x14004ff43  xor     rax, rsp
0x14004ff46  mov     [rbp+110h+var_30], rax
0x14004ff4d  mov     eax, [rcx+8]
0x14004ff50  mov     rdi, rcx
0x14004ff53  bt      eax, 8
0x14004ff57  mov     rcx, [rcx+110h]
0x14004ff5e  mov     r15, r8
0x14004ff61  mov     [rsp+210h+SecurityInformation], edx
0x14004ff65  mov     [rsp+210h+NewDescriptor], 0
0x14004ff6e  mov     [rsp+210h+var_1C8], 0
0x14004ff77  jnb     short loc_14004FFAD
0x14004ff79  test    rcx, rcx
0x14004ff7c  jnz     short loc_14004FFE5
0x14004ff7e  mov     ebx, 0C0000184h
0x14004ff83  mov     eax, ebx
0x14004ff85  mov     rcx, [rbp+110h+var_30]
0x14004ff8c  xor     rcx, rsp; StackCookie
0x14004ff8f  call    __security_check_cookie
0x14004ff94  mov     rbx, [rsp+210h+arg_18]
0x14004ff9c  add     rsp, 1F0h
0x14004ffa3  pop     r15
0x14004ffa5  pop     r14
0x14004ffa7  pop     r12
0x14004ffa9  pop     rdi
0x14004ffaa  pop     rbp
0x14004ffab  retn
0x14004ffad  test    rcx, rcx
0x14004ffb0  jz      short loc_14004FF7E
0x14004ffb2  mov     al, [rcx+18h]
0x14004ffb5  test    al, al
0x14004ffb7  jz      short loc_14004FF7E
0x14004ffb9  mov     rax, [rdi+110h]
0x14004ffc0  mov     ecx, [rax+48h]
0x14004ffc3  mov     [rdi+10h], ecx
0x14004ffc6  mov     eax, [rdi+8]
0x14004ffc9  test    dword ptr [rdi+10h], 100000h
0x14004ffd0  setz    cl
0x14004ffd3  bt      eax, 8
0x14004ffd7  setnb   al
0x14004ffda  test    al, cl
0x14004ffdc  jz      short loc_14004FFE5
0x14004ffde  mov     ebx, 0C0000010h
0x14004ffe3  jmp     short loc_14004FF83
0x14004ffe5  mov     eax, [rdi+170h]
0x14004ffeb  test    eax, eax
0x14004ffed  jg      short loc_14004FF7E
0x14004ffef  lea     ecx, [rax-1]
0x14004fff2  lock cmpxchg [rdi+170h], ecx
0x14004fffa  jnz     short loc_14004FFE5
0x14004fffc  mov     eax, [rdi+8]
0x14004ffff  bt      eax, 8
0x140050003  jnb     short loc_14005000B
0x140050005  cmp     byte ptr [rdi+2], 2
0x140050009  jnz     short loc_14005001A
0x14005000b  mov     eax, [rdi+8]
0x14005000e  bt      eax, 8
0x140050012  jb      short loc_140050024
0x140050014  cmp     byte ptr [rdi+2], 1
0x140050018  jz      short loc_140050024
0x14005001a  mov     ebx, 0C0000184h
0x14005001f  jmp     loc_14005023F
0x140050024  mov     rcx, rdi
0x140050027  call    AfdPreventSecurityDescriptorSet
0x14005002c  test    al, al
0x14005002e  jnz     short loc_14005003A
0x140050030  mov     ebx, 0C0000010h
0x140050035  jmp     loc_14005023F
0x14005003a  mov     r14, [rdi+28h]
0x14005003e  mov     [rsp+210h+NewDescriptor], r14
0x140050043  test    r14, r14
0x140050046  jnz     loc_140050113
0x14005004c  xor     edx, edx; Val
0x14005004e  lea     rcx, [rsp+210h+var_1B0]; void *
0x140050053  mov     r8d, 0A0h; Size
0x140050059  call    memset
0x14005005e  xor     edx, edx; Val
0x140050060  lea     rcx, [rbp+110h+var_110]; void *
0x140050064  mov     r8d, 0E0h; Size
0x14005006a  call    memset
0x14005006f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140050076  nop     dword ptr [rax+rax+00h]
0x14005007b  mov     r8d, 10000000h
0x140050081  lea     rdx, [rbp+110h+var_110]
0x140050085  mov     r9, rax
0x140050088  lea     rcx, [rsp+210h+var_1B0]
0x14005008d  call    cs:__imp_SeCreateAccessState
0x140050094  nop     dword ptr [rax+rax+00h]
0x140050099  mov     ebx, eax
0x14005009b  test    eax, eax
0x14005009d  js      loc_140050237
0x1400500a3  lea     rcx, [rbp+110h+SubjectContext]; SubjectContext
0x1400500a7  call    cs:__imp_SeLockSubjectContext
0x1400500ae  nop     dword ptr [rax+rax+00h]
0x1400500b3  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400500ba  nop     dword ptr [rax+rax+00h]
0x1400500bf  mov     [rsp+210h+PoolType], 1; PoolType
0x1400500c7  lea     r8, [rsp+210h+NewDescriptor]; NewDescriptor
0x1400500cc  mov     [rsp+210h+GenericMapping], rax; GenericMapping
0x1400500d1  xor     r9d, r9d; IsDirectoryObject
0x1400500d4  lea     rax, [rbp+110h+SubjectContext]
0x1400500d8  mov     rdx, r15; ExplicitDescriptor
0x1400500db  xor     ecx, ecx; ParentDescriptor
0x1400500dd  mov     [rsp+210h+var_1F0], rax; SubjectContext
0x1400500e2  call    cs:__imp_SeAssignSecurity
0x1400500e9  nop     dword ptr [rax+rax+00h]
0x1400500ee  lea     rcx, [rbp+110h+SubjectContext]; SubjectContext
0x1400500f2  mov     ebx, eax
0x1400500f4  call    cs:__imp_SeUnlockSubjectContext
0x1400500fb  nop     dword ptr [rax+rax+00h]
0x140050100  lea     rcx, [rsp+210h+var_1B0]
0x140050105  call    cs:__imp_SeDeleteAccessState
0x14005010c  nop     dword ptr [rax+rax+00h]
0x140050111  jmp     short loc_140050149
0x140050113  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005011a  nop     dword ptr [rax+rax+00h]
0x14005011f  mov     [rsp+210h+GenericMapping], rax; GenericMapping
0x140050124  lea     r9, [rsp+210h+NewDescriptor]; ObjectsSecurityDescriptor
0x140050129  mov     r8, r15; ModificationDescriptor
0x14005012c  mov     dword ptr [rsp+210h+var_1F0], 1; PoolType
0x140050134  lea     rdx, [rsp+210h+SecurityInformation]; SecurityInformation
0x140050139  xor     ecx, ecx; Object
0x14005013b  call    cs:__imp_SeSetSecurityDescriptorInfo
0x140050142  nop     dword ptr [rax+rax+00h]
0x140050147  mov     ebx, eax
0x140050149  test    ebx, ebx
0x14005014b  js      loc_140050237
0x140050151  mov     rcx, [rsp+210h+NewDescriptor]
0x140050156  lea     rdx, [rsp+210h+var_1C8]
0x14005015b  mov     r8d, 1
0x140050161  call    cs:__imp_ObLogSecurityDescriptor
0x140050168  nop     dword ptr [rax+rax+00h]
0x14005016d  mov     rcx, [rsp+210h+NewDescriptor]; P
0x140050172  xor     edx, edx; Tag
0x140050174  mov     ebx, eax
0x140050176  call    cs:__imp_ExFreePoolWithTag
0x14005017d  nop     dword ptr [rax+rax+00h]
0x140050182  test    ebx, ebx
0x140050184  js      loc_140050237
0x14005018a  mov     eax, [rdi+8]
0x14005018d  bt      eax, 8
0x140050191  jb      short loc_1400501B3
0x140050193  mov     eax, [rdi+8]
0x140050196  bt      eax, 9
0x14005019a  jb      short loc_1400501B3
0x14005019c  mov     rax, [rsp+210h+var_1C8]
0x1400501a1  mov     [rdi+28h], rax
0x1400501a5  test    r14, r14
0x1400501a8  jz      loc_140050237
0x1400501ae  mov     rcx, r14
0x1400501b1  jmp     short loc_140050226
0x1400501b3  xor     edx, edx; Val
0x1400501b5  lea     rcx, [rsp+210h+var_1B0]; void *
0x1400501ba  lea     r8d, [rdx+50h]; Size
0x1400501be  call    memset
0x1400501c3  mov     rax, [rsp+210h+var_1C8]
0x1400501c8  mov     [rsp+210h+var_1B8], rax
0x1400501cd  lea     rax, [rsp+210h+var_1B8]
0x1400501d2  mov     [rbp+110h+SubjectContext.ClientToken], rax
0x1400501d6  mov     eax, [rdi+8]
0x1400501d9  bt      eax, 8
0x1400501dd  mov     [rsp+210h+var_19C], 0FFFDh
0x1400501e5  mov     [rsp+210h+var_198], 18h
0x1400501ed  mov     qword ptr [rbp+110h+SubjectContext.ImpersonationLevel], 8
0x1400501f5  jnb     short loc_140050212
0x1400501f7  mov     rcx, [rdi+18h]
0x1400501fb  lea     r8, [rsp+210h+var_1B0]
0x140050200  mov     rdx, [rdi+10h]
0x140050204  mov     r9, rdi
0x140050207  mov     rcx, [rcx+8]
0x14005020b  call    AfdTLIoControl
0x140050210  jmp     short loc_14005021F
0x140050212  lea     rdx, [rsp+210h+var_1B0]
0x140050217  mov     rcx, rdi
0x14005021a  call    AfdTdiTlSyncIoControl
0x14005021f  mov     rcx, [rsp+210h+var_1C8]
0x140050224  mov     ebx, eax
0x140050226  mov     edx, 1
0x14005022b  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140050232  nop     dword ptr [rax+rax+00h]
0x140050237  mov     rcx, rdi
0x14005023a  call    AfdReallowSecurityDescriptorSet
0x14005023f  lock inc dword ptr [rdi+170h]
0x140050246  jmp     loc_14004FF83
```
