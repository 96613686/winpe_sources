# AfdSetSecurity

- ea: `0x14004ffc0`
- end: `0x1400502eb`
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
- `0x14004ffc0`
- `0x140072840`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005010f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140050153`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400501b3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005010f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140050153`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400501b3`
- `ntoskrnl!SeLockSubjectContext` at `0x140050147`
- `ntoskrnl!SeLockSubjectContext` at `0x140050147`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050194`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050194`
- `ntoskrnl!SeAssignSecurity` at `0x140050182`
- `ntoskrnl!SeAssignSecurity` at `0x140050182`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140050201`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x140050201`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1400501db`
- `ntoskrnl!SeSetSecurityDescriptorInfo` at `0x1400501db`
- `ntoskrnl!SeCreateAccessState` at `0x14005012d`
- `ntoskrnl!SeCreateAccessState` at `0x14005012d`
- `ntoskrnl!SeDeleteAccessState` at `0x1400501a5`
- `ntoskrnl!SeDeleteAccessState` at `0x1400501a5`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400502cb`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400502cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050216`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050216`

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
    if ( !(unsigned __int8)AfdPreventSecurityDescriptorSet(a1) )
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
        v16 = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL), *(_QWORD *)(a1 + 16), v21, a1);
      else
        v16 = AfdTdiTlSyncIoControl(a1, v21);
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
0x14004ffc0  mov     [rsp-8+arg_18], rbx
0x14004ffc5  push    rbp
0x14004ffc6  push    rdi
0x14004ffc7  push    r12
0x14004ffc9  push    r14
0x14004ffcb  push    r15
0x14004ffcd  lea     rbp, [rsp-0F0h]
0x14004ffd5  sub     rsp, 1F0h
0x14004ffdc  mov     rax, cs:__security_cookie
0x14004ffe3  xor     rax, rsp
0x14004ffe6  mov     [rbp+110h+var_30], rax
0x14004ffed  mov     eax, [rcx+8]
0x14004fff0  mov     rdi, rcx
0x14004fff3  bt      eax, 8
0x14004fff7  mov     rcx, [rcx+110h]
0x14004fffe  mov     r15, r8
0x140050001  mov     [rsp+210h+SecurityInformation], edx
0x140050005  mov     [rsp+210h+NewDescriptor], 0
0x14005000e  mov     [rsp+210h+var_1C8], 0
0x140050017  jnb     short loc_14005004D
0x140050019  test    rcx, rcx
0x14005001c  jnz     short loc_140050085
0x14005001e  mov     ebx, 0C0000184h
0x140050023  mov     eax, ebx
0x140050025  mov     rcx, [rbp+110h+var_30]
0x14005002c  xor     rcx, rsp; StackCookie
0x14005002f  call    __security_check_cookie
0x140050034  mov     rbx, [rsp+210h+arg_18]
0x14005003c  add     rsp, 1F0h
0x140050043  pop     r15
0x140050045  pop     r14
0x140050047  pop     r12
0x140050049  pop     rdi
0x14005004a  pop     rbp
0x14005004b  retn
0x14005004d  test    rcx, rcx
0x140050050  jz      short loc_14005001E
0x140050052  mov     al, [rcx+18h]
0x140050055  test    al, al
0x140050057  jz      short loc_14005001E
0x140050059  mov     rax, [rdi+110h]
0x140050060  mov     ecx, [rax+48h]
0x140050063  mov     [rdi+10h], ecx
0x140050066  mov     eax, [rdi+8]
0x140050069  test    dword ptr [rdi+10h], 100000h
0x140050070  setz    cl
0x140050073  bt      eax, 8
0x140050077  setnb   al
0x14005007a  test    al, cl
0x14005007c  jz      short loc_140050085
0x14005007e  mov     ebx, 0C0000010h
0x140050083  jmp     short loc_140050023
0x140050085  mov     eax, [rdi+170h]
0x14005008b  test    eax, eax
0x14005008d  jg      short loc_14005001E
0x14005008f  lea     ecx, [rax-1]
0x140050092  lock cmpxchg [rdi+170h], ecx
0x14005009a  jnz     short loc_140050085
0x14005009c  mov     eax, [rdi+8]
0x14005009f  bt      eax, 8
0x1400500a3  jnb     short loc_1400500AB
0x1400500a5  cmp     byte ptr [rdi+2], 2
0x1400500a9  jnz     short loc_1400500BA
0x1400500ab  mov     eax, [rdi+8]
0x1400500ae  bt      eax, 8
0x1400500b2  jb      short loc_1400500C4
0x1400500b4  cmp     byte ptr [rdi+2], 1
0x1400500b8  jz      short loc_1400500C4
0x1400500ba  mov     ebx, 0C0000184h
0x1400500bf  jmp     loc_1400502DF
0x1400500c4  mov     rcx, rdi
0x1400500c7  call    AfdPreventSecurityDescriptorSet
0x1400500cc  test    al, al
0x1400500ce  jnz     short loc_1400500DA
0x1400500d0  mov     ebx, 0C0000010h
0x1400500d5  jmp     loc_1400502DF
0x1400500da  mov     r14, [rdi+28h]
0x1400500de  mov     [rsp+210h+NewDescriptor], r14
0x1400500e3  test    r14, r14
0x1400500e6  jnz     loc_1400501B3
0x1400500ec  xor     edx, edx; Val
0x1400500ee  lea     rcx, [rsp+210h+var_1B0]; void *
0x1400500f3  mov     r8d, 0A0h; Size
0x1400500f9  call    memset
0x1400500fe  xor     edx, edx; Val
0x140050100  lea     rcx, [rbp+110h+var_110]; void *
0x140050104  mov     r8d, 0E0h; Size
0x14005010a  call    memset
0x14005010f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140050116  nop     dword ptr [rax+rax+00h]
0x14005011b  mov     r8d, 10000000h
0x140050121  lea     rdx, [rbp+110h+var_110]
0x140050125  mov     r9, rax
0x140050128  lea     rcx, [rsp+210h+var_1B0]
0x14005012d  call    cs:__imp_SeCreateAccessState
0x140050134  nop     dword ptr [rax+rax+00h]
0x140050139  mov     ebx, eax
0x14005013b  test    eax, eax
0x14005013d  js      loc_1400502D7
0x140050143  lea     rcx, [rbp+110h+SubjectContext]; SubjectContext
0x140050147  call    cs:__imp_SeLockSubjectContext
0x14005014e  nop     dword ptr [rax+rax+00h]
0x140050153  call    cs:__imp_IoGetFileObjectGenericMapping
0x14005015a  nop     dword ptr [rax+rax+00h]
0x14005015f  mov     [rsp+210h+PoolType], 1; PoolType
0x140050167  lea     r8, [rsp+210h+NewDescriptor]; NewDescriptor
0x14005016c  mov     [rsp+210h+GenericMapping], rax; GenericMapping
0x140050171  xor     r9d, r9d; IsDirectoryObject
0x140050174  lea     rax, [rbp+110h+SubjectContext]
0x140050178  mov     rdx, r15; ExplicitDescriptor
0x14005017b  xor     ecx, ecx; ParentDescriptor
0x14005017d  mov     [rsp+210h+var_1F0], rax; SubjectContext
0x140050182  call    cs:__imp_SeAssignSecurity
0x140050189  nop     dword ptr [rax+rax+00h]
0x14005018e  lea     rcx, [rbp+110h+SubjectContext]; SubjectContext
0x140050192  mov     ebx, eax
0x140050194  call    cs:__imp_SeUnlockSubjectContext
0x14005019b  nop     dword ptr [rax+rax+00h]
0x1400501a0  lea     rcx, [rsp+210h+var_1B0]
0x1400501a5  call    cs:__imp_SeDeleteAccessState
0x1400501ac  nop     dword ptr [rax+rax+00h]
0x1400501b1  jmp     short loc_1400501E9
0x1400501b3  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400501ba  nop     dword ptr [rax+rax+00h]
0x1400501bf  mov     [rsp+210h+GenericMapping], rax; GenericMapping
0x1400501c4  lea     r9, [rsp+210h+NewDescriptor]; ObjectsSecurityDescriptor
0x1400501c9  mov     r8, r15; ModificationDescriptor
0x1400501cc  mov     dword ptr [rsp+210h+var_1F0], 1; PoolType
0x1400501d4  lea     rdx, [rsp+210h+SecurityInformation]; SecurityInformation
0x1400501d9  xor     ecx, ecx; Object
0x1400501db  call    cs:__imp_SeSetSecurityDescriptorInfo
0x1400501e2  nop     dword ptr [rax+rax+00h]
0x1400501e7  mov     ebx, eax
0x1400501e9  test    ebx, ebx
0x1400501eb  js      loc_1400502D7
0x1400501f1  mov     rcx, [rsp+210h+NewDescriptor]
0x1400501f6  lea     rdx, [rsp+210h+var_1C8]
0x1400501fb  mov     r8d, 1
0x140050201  call    cs:__imp_ObLogSecurityDescriptor
0x140050208  nop     dword ptr [rax+rax+00h]
0x14005020d  mov     rcx, [rsp+210h+NewDescriptor]; P
0x140050212  xor     edx, edx; Tag
0x140050214  mov     ebx, eax
0x140050216  call    cs:__imp_ExFreePoolWithTag
0x14005021d  nop     dword ptr [rax+rax+00h]
0x140050222  test    ebx, ebx
0x140050224  js      loc_1400502D7
0x14005022a  mov     eax, [rdi+8]
0x14005022d  bt      eax, 8
0x140050231  jb      short loc_140050253
0x140050233  mov     eax, [rdi+8]
0x140050236  bt      eax, 9
0x14005023a  jb      short loc_140050253
0x14005023c  mov     rax, [rsp+210h+var_1C8]
0x140050241  mov     [rdi+28h], rax
0x140050245  test    r14, r14
0x140050248  jz      loc_1400502D7
0x14005024e  mov     rcx, r14
0x140050251  jmp     short loc_1400502C6
0x140050253  xor     edx, edx; Val
0x140050255  lea     rcx, [rsp+210h+var_1B0]; void *
0x14005025a  lea     r8d, [rdx+50h]; Size
0x14005025e  call    memset
0x140050263  mov     rax, [rsp+210h+var_1C8]
0x140050268  mov     [rsp+210h+var_1B8], rax
0x14005026d  lea     rax, [rsp+210h+var_1B8]
0x140050272  mov     [rbp+110h+SubjectContext.ClientToken], rax
0x140050276  mov     eax, [rdi+8]
0x140050279  bt      eax, 8
0x14005027d  mov     [rsp+210h+var_19C], 0FFFDh
0x140050285  mov     [rsp+210h+var_198], 18h
0x14005028d  mov     qword ptr [rbp+110h+SubjectContext.ImpersonationLevel], 8
0x140050295  jnb     short loc_1400502B2
0x140050297  mov     rcx, [rdi+18h]
0x14005029b  lea     r8, [rsp+210h+var_1B0]
0x1400502a0  mov     rdx, [rdi+10h]
0x1400502a4  mov     r9, rdi
0x1400502a7  mov     rcx, [rcx+8]
0x1400502ab  call    AfdTLIoControl
0x1400502b0  jmp     short loc_1400502BF
0x1400502b2  lea     rdx, [rsp+210h+var_1B0]
0x1400502b7  mov     rcx, rdi
0x1400502ba  call    AfdTdiTlSyncIoControl
0x1400502bf  mov     rcx, [rsp+210h+var_1C8]
0x1400502c4  mov     ebx, eax
0x1400502c6  mov     edx, 1
0x1400502cb  call    cs:__imp_ObDereferenceSecurityDescriptor
0x1400502d2  nop     dword ptr [rax+rax+00h]
0x1400502d7  mov     rcx, rdi
0x1400502da  call    AfdReallowSecurityDescriptorSet
0x1400502df  lock inc dword ptr [rdi+170h]
0x1400502e6  jmp     loc_140050023
```
