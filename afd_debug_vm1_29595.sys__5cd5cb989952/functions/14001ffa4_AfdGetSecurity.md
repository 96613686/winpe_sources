# AfdGetSecurity

- ea: `0x14001ffa4`
- end: `0x14002030a`
- name: `AfdGetSecurity`
- size: `870`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x14000fcd0`
- `0x14001c708`
- `0x14001e274`
- `0x14001e7e0`
- `0x14001ee68`
- `0x14001eec0`
- `0x14001ffa4`
- `0x140072840`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400201a1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140077a9f`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400201a1`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140077a9f`
- `ntoskrnl!SeLockSubjectContext` at `0x140020195`
- `ntoskrnl!SeLockSubjectContext` at `0x140020195`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400201e1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400201e1`
- `ntoskrnl!SeAssignSecurity` at `0x1400201cf`
- `ntoskrnl!SeAssignSecurity` at `0x1400201cf`
- `ntoskrnl!SeCreateAccessState` at `0x140077abd`
- `ntoskrnl!SeCreateAccessState` at `0x140077abd`
- `ntoskrnl!SeDeleteAccessState` at `0x1400201f2`
- `ntoskrnl!SeDeleteAccessState` at `0x1400201f2`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14002007f`
- `ntoskrnl!SeQuerySecurityDescriptorInfo` at `0x14002007f`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14002016d`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14002016d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020180`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020180`

## pseudocode

```c
__int64 __fastcall AfdGetSecurity(__int64 a1, DWORD a2, ULONG a3, void *a4, _QWORD *a5)
{
  int v5; // eax
  __int64 v7; // rcx
  signed __int32 v9; // eax
  void *v10; // rax
  char v11; // si
  NTSTATUS AccessState; // ebx
  int v14; // eax
  NTSTATUS v15; // eax
  struct _GENERIC_MAPPING *GenericMapping; // rax
  signed __int64 v17; // rax
  bool v18; // cc
  signed __int64 v19; // rax
  __int64 ConnectionReferenceFromEndpoint; // rax
  __int64 v21; // rsi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  ULONG Length; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR ObjectsSecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  DWORD SecurityInformation; // [rsp+50h] [rbp-B0h] BYREF
  void *v26; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT v27[5]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[224]; // [rsp+100h] [rbp+0h] BYREF

  v5 = *(_DWORD *)(a1 + 8);
  v7 = *(_QWORD *)(a1 + 272);
  SecurityInformation = a2;
  Length = a3;
  ObjectsSecurityDescriptor = 0;
  if ( (v5 & 0x100) != 0 )
  {
    if ( v7 )
      goto LABEL_3;
    return (unsigned int)-1073741436;
  }
  if ( !v7 || !*(_BYTE *)(v7 + 24) )
    return (unsigned int)-1073741436;
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(*(_QWORD *)(a1 + 272) + 72LL);
  if ( (*(_DWORD *)(a1 + 16) & 0x100000) != 0 || (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    do
    {
LABEL_3:
      v9 = *(_DWORD *)(a1 + 368);
      if ( v9 > 0 )
        return (unsigned int)-1073741436;
    }
    while ( v9 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 368), v9 - 1, v9) );
    if ( !(unsigned __int8)AfdPreventSecurityDescriptorSet(a1) )
    {
      AccessState = -1073741808;
      goto LABEL_15;
    }
    if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 && (*(_DWORD *)(a1 + 8) & 0x200) == 0 )
    {
      if ( *(_BYTE *)(a1 + 2) == 1 )
      {
        v10 = *(void **)(a1 + 40);
        v11 = 0;
LABEL_10:
        ObjectsSecurityDescriptor = v10;
        if ( v10 )
          goto LABEL_11;
        memset(v27, 0, sizeof(v27));
        memset(v28, 0, sizeof(v28));
        FileObjectGenericMapping = IoGetFileObjectGenericMapping();
        AccessState = SeCreateAccessState(v27, v28, 0x10000000, FileObjectGenericMapping);
        if ( AccessState >= 0 )
        {
          SeLockSubjectContext(&v27[1]);
          GenericMapping = IoGetFileObjectGenericMapping();
          AccessState = SeAssignSecurity(0, 0, &ObjectsSecurityDescriptor, 0, &v27[1], GenericMapping, PagedPool);
          SeUnlockSubjectContext(&v27[1]);
          SeDeleteAccessState(v27);
          v11 = 0;
          if ( AccessState >= 0 )
          {
LABEL_11:
            AccessState = SeQuerySecurityDescriptorInfo(&SecurityInformation, a4, &Length, &ObjectsSecurityDescriptor);
            if ( AccessState == -1073741789 )
            {
              AccessState = -2147483643;
              *a5 = Length;
            }
            if ( ObjectsSecurityDescriptor != *(PSECURITY_DESCRIPTOR *)(a1 + 40) )
            {
              if ( v11 )
                ObDereferenceSecurityDescriptor(ObjectsSecurityDescriptor, 1);
              else
                ExFreePoolWithTag(ObjectsSecurityDescriptor, 0);
            }
          }
        }
        goto LABEL_14;
      }
      AccessState = -1073741808;
      goto LABEL_14;
    }
    v26 = 0;
    memset(v27, 0, 0x50u);
    HIDWORD(v27[0].PrimaryToken) = 65533;
    v27[1].PrimaryToken = &v26;
    v14 = *(_DWORD *)(a1 + 8);
    LODWORD(v27[0].ProcessAuditId) = 32;
    v27[1].ProcessAuditId = (PVOID)8;
    if ( (v14 & 0x100) != 0 )
    {
      if ( (*(_WORD *)a1 & 0xAFD2) == 0xAFD2 && *(_BYTE *)(a1 + 2) == 4 )
      {
        ConnectionReferenceFromEndpoint = AfdGetConnectionReferenceFromEndpoint(a1);
        v21 = ConnectionReferenceFromEndpoint;
        if ( ConnectionReferenceFromEndpoint )
        {
          AccessState = AfdTLIoControl(
                          *(_QWORD *)(*(_QWORD *)(ConnectionReferenceFromEndpoint + 24) + 8LL),
                          *(_QWORD *)(ConnectionReferenceFromEndpoint + 16),
                          v27,
                          0);
          v17 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v21 + 48), 0xFFFFFFFFFFFFFFFFuLL);
          v18 = v17 <= 1;
          v19 = v17 - 1;
          if ( v18 )
          {
            if ( v19 )
              __fastfail(0xEu);
            AfdCloseConnection(v21);
          }
LABEL_21:
          if ( AccessState >= 0 )
          {
            v10 = v26;
            v11 = 1;
            goto LABEL_10;
          }
LABEL_14:
          AfdReallowSecurityDescriptorSet(a1);
LABEL_15:
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 368));
          return (unsigned int)AccessState;
        }
      }
      v15 = AfdTLIoControl(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL), *(_QWORD *)(a1 + 16), v27, a1);
    }
    else
    {
      v15 = AfdTdiTlSyncIoControl(a1, v27);
    }
    AccessState = v15;
    goto LABEL_21;
  }
  return (unsigned int)-1073741808;
}

```

## disassembly

```asm
0x14001ffa4  push    rbp
0x14001ffa6  push    rbx
0x14001ffa7  push    rsi
0x14001ffa8  push    rdi
0x14001ffa9  push    r14
0x14001ffab  push    r15
0x14001ffad  lea     rbp, [rsp-0F8h]
0x14001ffb5  sub     rsp, 1F8h
0x14001ffbc  mov     rax, cs:__security_cookie
0x14001ffc3  xor     rax, rsp
0x14001ffc6  mov     [rbp+120h+var_40], rax
0x14001ffcd  mov     eax, [rcx+8]
0x14001ffd0  mov     rdi, rcx
0x14001ffd3  bt      eax, 8
0x14001ffd7  mov     r14, [rbp+120h+arg_20]
0x14001ffde  mov     rcx, [rcx+110h]
0x14001ffe5  mov     r15, r9
0x14001ffe8  mov     [rsp+220h+SecurityInformation], edx
0x14001ffec  mov     [rsp+220h+Length], r8d
0x14001fff1  mov     [rsp+220h+ObjectsSecurityDescriptor], 0
0x14001fffa  jnb     loc_140020252
0x140020000  test    rcx, rcx
0x140020003  jz      loc_140020300
0x140020009  mov     eax, [rdi+170h]
0x14002000f  test    eax, eax
0x140020011  jg      loc_140020300
0x140020017  lea     ecx, [rax-1]
0x14002001a  lock cmpxchg [rdi+170h], ecx
0x140020022  jnz     short loc_140020009
0x140020024  mov     rcx, rdi
0x140020027  call    AfdPreventSecurityDescriptorSet
0x14002002c  test    al, al
0x14002002e  jz      loc_140020299
0x140020034  mov     eax, [rdi+8]
0x140020037  bt      eax, 8
0x14002003b  jb      loc_1400200D8
0x140020041  mov     eax, [rdi+8]
0x140020044  bt      eax, 9
0x140020048  jb      loc_1400200D8
0x14002004e  cmp     byte ptr [rdi+2], 1
0x140020052  jnz     loc_1400202A3
0x140020058  mov     rax, [rdi+28h]
0x14002005c  xor     sil, sil
0x14002005f  mov     [rsp+220h+ObjectsSecurityDescriptor], rax
0x140020064  test    rax, rax
0x140020067  jz      loc_140077A7C
0x14002006d  lea     r9, [rsp+220h+ObjectsSecurityDescriptor]; ObjectsSecurityDescriptor
0x140020072  mov     rdx, r15; SecurityDescriptor
0x140020075  lea     r8, [rsp+220h+Length]; Length
0x14002007a  lea     rcx, [rsp+220h+SecurityInformation]; SecurityInformation
0x14002007f  call    cs:__imp_SeQuerySecurityDescriptorInfo
0x140020086  nop     dword ptr [rax+rax+00h]
0x14002008b  mov     ebx, eax
0x14002008d  cmp     eax, 0C0000023h
0x140020092  jz      loc_1400202EF
0x140020098  mov     rcx, [rsp+220h+ObjectsSecurityDescriptor]; P
0x14002009d  cmp     rcx, [rdi+28h]
0x1400200a1  jnz     loc_140020163
0x1400200a7  mov     rcx, rdi
0x1400200aa  call    AfdReallowSecurityDescriptorSet
0x1400200af  lock inc dword ptr [rdi+170h]
0x1400200b6  mov     eax, ebx
0x1400200b8  mov     rcx, [rbp+120h+var_40]
0x1400200bf  xor     rcx, rsp; StackCookie
0x1400200c2  call    __security_check_cookie
0x1400200c7  add     rsp, 1F8h
0x1400200ce  pop     r15
0x1400200d0  pop     r14
0x1400200d2  pop     rdi
0x1400200d3  pop     rsi
0x1400200d4  pop     rbx
0x1400200d5  pop     rbp
0x1400200d6  retn
0x1400200d8  xor     edx, edx; Val
0x1400200da  mov     [rsp+220h+var_1C8], 0
0x1400200e3  lea     rcx, [rsp+220h+var_1C0]; void *
0x1400200e8  lea     r8d, [rdx+50h]; Size
0x1400200ec  call    memset
0x1400200f1  lea     rax, [rsp+220h+var_1C8]
0x1400200f6  mov     [rsp+220h+var_1AC], 0FFFDh
0x1400200fe  mov     [rbp+120h+SubjectContext.PrimaryToken], rax
0x140020102  mov     eax, [rdi+8]
0x140020105  bt      eax, 8
0x140020109  mov     [rsp+220h+var_1A8], 20h ; ' '
0x140020111  mov     [rbp+120h+SubjectContext.ProcessAuditId], 8
0x140020119  jnb     loc_1400202DD
0x14002011f  movzx   eax, word ptr [rdi]
0x140020122  mov     ecx, 0AFD2h
0x140020127  and     ax, cx
0x14002012a  cmp     ax, cx
0x14002012d  jz      loc_1400202AD
0x140020133  mov     rcx, [rdi+18h]
0x140020137  lea     r8, [rsp+220h+var_1C0]
0x14002013c  mov     rdx, [rdi+10h]
0x140020140  mov     r9, rdi
0x140020143  mov     rcx, [rcx+8]
0x140020147  call    AfdTLIoControl
0x14002014c  mov     ebx, eax
0x14002014e  test    ebx, ebx
0x140020150  js      loc_1400200A7
0x140020156  mov     rax, [rsp+220h+var_1C8]
0x14002015b  mov     sil, 1
0x14002015e  jmp     loc_14002005F
0x140020163  test    sil, sil
0x140020166  jz      short loc_14002017E
0x140020168  mov     edx, 1
0x14002016d  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140020174  nop     dword ptr [rax+rax+00h]
0x140020179  jmp     loc_1400200A7
0x14002017e  xor     edx, edx; Tag
0x140020180  call    cs:__imp_ExFreePoolWithTag
0x140020187  nop     dword ptr [rax+rax+00h]
0x14002018c  jmp     loc_1400200A7
0x140020191  lea     rcx, [rbp+120h+SubjectContext]; SubjectContext
0x140020195  call    cs:__imp_SeLockSubjectContext
0x14002019c  nop     dword ptr [rax+rax+00h]
0x1400201a1  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400201a8  nop     dword ptr [rax+rax+00h]
0x1400201ad  mov     [rsp+220h+PoolType], 1; PoolType
0x1400201b5  lea     r8, [rsp+220h+ObjectsSecurityDescriptor]; NewDescriptor
0x1400201ba  mov     [rsp+220h+GenericMapping], rax; GenericMapping
0x1400201bf  xor     r9d, r9d; IsDirectoryObject
0x1400201c2  lea     rax, [rbp+120h+SubjectContext]
0x1400201c6  xor     edx, edx; ExplicitDescriptor
0x1400201c8  xor     ecx, ecx; ParentDescriptor
0x1400201ca  mov     [rsp+220h+var_200], rax; SubjectContext
0x1400201cf  call    cs:__imp_SeAssignSecurity
0x1400201d6  nop     dword ptr [rax+rax+00h]
0x1400201db  lea     rcx, [rbp+120h+SubjectContext]; SubjectContext
0x1400201df  mov     ebx, eax
0x1400201e1  call    cs:__imp_SeUnlockSubjectContext
0x1400201e8  nop     dword ptr [rax+rax+00h]
0x1400201ed  lea     rcx, [rsp+220h+var_1C0]
0x1400201f2  call    cs:__imp_SeDeleteAccessState
0x1400201f9  nop     dword ptr [rax+rax+00h]
0x1400201fe  xor     sil, sil
0x140020201  test    ebx, ebx
0x140020203  jns     loc_14002006D
0x140020209  jmp     loc_1400200A7
0x14002020e  mov     rcx, [rax+18h]
0x140020212  lea     r8, [rsp+220h+var_1C0]
0x140020217  mov     rdx, [rax+10h]
0x14002021b  xor     r9d, r9d
0x14002021e  mov     rcx, [rcx+8]
0x140020222  call    AfdTLIoControl
0x140020227  mov     ebx, eax
0x140020229  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002022d  lock xadd [rsi+30h], rax
0x140020233  sub     rax, 1
0x140020237  jg      loc_14002014E
0x14002023d  test    rax, rax
0x140020240  jz      loc_1400202D0
0x140020246  mov     ecx, 0Eh
0x14002024b  int     29h; Win8: RtlFailFast(ecx)
0x14002024d  jmp     loc_14002014E
0x140020252  test    rcx, rcx
0x140020255  jz      loc_140020300
0x14002025b  mov     al, [rcx+18h]
0x14002025e  test    al, al
0x140020260  jz      loc_140020300
0x140020266  mov     rax, [rdi+110h]
0x14002026d  mov     ecx, [rax+48h]
0x140020270  mov     [rdi+10h], ecx
0x140020273  mov     eax, [rdi+8]
0x140020276  test    dword ptr [rdi+10h], 100000h
0x14002027d  setz    cl
0x140020280  bt      eax, 8
0x140020284  setnb   al
0x140020287  test    al, cl
0x140020289  jz      loc_140020009
0x14002028f  mov     ebx, 0C0000010h
0x140020294  jmp     loc_1400200B6
0x140020299  mov     ebx, 0C0000010h
0x14002029e  jmp     loc_1400200AF
0x1400202a3  mov     ebx, 0C0000010h
0x1400202a8  jmp     loc_1400200A7
0x1400202ad  cmp     byte ptr [rdi+2], 4
0x1400202b1  jnz     loc_140020133
0x1400202b7  mov     rcx, rdi
0x1400202ba  call    AfdGetConnectionReferenceFromEndpoint
0x1400202bf  mov     rsi, rax
0x1400202c2  test    rax, rax
0x1400202c5  jz      loc_140020133
0x1400202cb  jmp     loc_14002020E
0x1400202d0  mov     rcx, rsi
0x1400202d3  call    AfdCloseConnection
0x1400202d8  jmp     loc_14002014E
0x1400202dd  lea     rdx, [rsp+220h+var_1C0]
0x1400202e2  mov     rcx, rdi
0x1400202e5  call    AfdTdiTlSyncIoControl
0x1400202ea  jmp     loc_14002014C
0x1400202ef  mov     eax, [rsp+220h+Length]
0x1400202f3  mov     ebx, 80000005h
0x1400202f8  mov     [r14], rax
0x1400202fb  jmp     loc_140020098
0x140020300  mov     ebx, 0C0000184h
0x140020305  jmp     loc_1400200B6
0x140077a7c  xor     edx, edx; Val
0x140077a7e  lea     rcx, [rsp+220h+var_1C0]; void *
0x140077a83  mov     r8d, 0A0h; Size
0x140077a89  call    memset
0x140077a8e  xor     edx, edx; Val
0x140077a90  lea     rcx, [rbp+120h+var_120]; void *
0x140077a94  mov     r8d, 0E0h; Size
0x140077a9a  call    memset
0x140077a9f  call    cs:__imp_IoGetFileObjectGenericMapping
0x140077aa6  nop     dword ptr [rax+rax+00h]
0x140077aab  mov     r8d, 10000000h
0x140077ab1  lea     rdx, [rbp+120h+var_120]
0x140077ab5  mov     r9, rax
0x140077ab8  lea     rcx, [rsp+220h+var_1C0]
0x140077abd  call    cs:__imp_SeCreateAccessState
0x140077ac4  nop     dword ptr [rax+rax+00h]
0x140077ac9  mov     ebx, eax
0x140077acb  test    eax, eax
0x140077acd  js      loc_1400200A7
0x140077ad3  jmp     loc_140020191
```
