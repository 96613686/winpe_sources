# BfsAccessRegistryKeyAsUserCallback

- ea: `0x14000e2a0`
- end: `0x14000e6e9`
- name: `BfsAccessRegistryKeyAsUserCallback`
- size: `1097`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x14000e2a0`
- `0x14000fb6c`
- `0x14000fdc8`
- `0x140010070`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e63d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e63d`
- `ntoskrnl!ZwOpenKey` at `0x14000e396`
- `ntoskrnl!ZwOpenKey` at `0x14000e396`
- `ntoskrnl!CmKeyObjectType` at `0x14000e61a`
- `ntoskrnl!ZwCreateKey` at `0x14000e414`
- `ntoskrnl!ZwCreateKey` at `0x14000e414`
- `ntoskrnl!SeAccessCheck` at `0x14000e520`
- `ntoskrnl!SeAccessCheck` at `0x14000e5dc`
- `ntoskrnl!SeAccessCheck` at `0x14000e520`
- `ntoskrnl!SeAccessCheck` at `0x14000e5dc`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e43e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e4ba`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e43e`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e4ba`
- `ntoskrnl!ZwClose` at `0x14000e6b0`
- `ntoskrnl!ZwClose` at `0x14000e6b0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e532`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e5ee`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e532`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e5ee`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e4d6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e592`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e4d6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e592`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e68b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e68b`
- `ntoskrnl!ExAllocatePool2` at `0x14000e46a`
- `ntoskrnl!ExAllocatePool2` at `0x14000e46a`

## pseudocode

```c
__int64 __fastcall BfsAccessRegistryKeyAsUserCallback(__int64 *a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rcx
  int v7; // eax
  NTSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  ULONG v12; // ebx
  void *Pool2; // rsi
  char v14; // r14
  NTSTATUS v15; // eax
  int v16; // r8d
  int v17; // r9d
  BOOLEAN v18; // bl
  int v19; // ecx
  BOOLEAN v20; // bl
  int Class; // [rsp+20h] [rbp-E0h]
  int Classa; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int AccessStatus; // [rsp+54h] [rbp-ACh] BYREF
  ULONG LengthNeeded; // [rsp+58h] [rbp-A8h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  ULONG Disposition; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+D8h] [rbp-28h] BYREF
  int *v34; // [rsp+F8h] [rbp-8h]
  __int64 v35; // [rsp+100h] [rbp+0h]

  v2 = a1[1];
  Disposition = 0;
  LengthNeeded = 0;
  v29 = 0;
  v30 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v3 = BfsImpersonateUser(v2, &v29);
  AccessStatus = v3;
  if ( v3 >= 0 )
  {
    v6 = *a1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 1536;
    ObjectAttributes.ObjectName = *(PUNICODE_STRING *)v6;
    v7 = *((_DWORD *)a1 + 8);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( v7 == 28 )
    {
      v8 = ZwOpenKey(&KeyHandle, 0x20000u, &ObjectAttributes);
    }
    else
    {
      if ( v7 != 26 )
        goto LABEL_12;
      v8 = ZwCreateKey(&KeyHandle, 0x20000u, &ObjectAttributes, 0, 0, *(_DWORD *)(v6 + 24), &Disposition);
    }
    AccessStatus = v8;
    if ( v8 < 0 )
    {
      v11 = dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
      {
LABEL_31:
        BfsRevertTokenImpersonation(&v29);
        goto LABEL_32;
      }
      v24 = v8;
LABEL_9:
      v35 = 4;
      v34 = &v24;
      tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v9, v10, Class, &v33);
      goto LABEL_31;
    }
LABEL_12:
    AccessStatus = ZwQuerySecurityObject(KeyHandle, 0xFu, 0, 0, &LengthNeeded);
    if ( AccessStatus != -1073741789 )
      goto LABEL_31;
    v12 = LengthNeeded;
    Pool2 = (void *)ExAllocatePool2(256, LengthNeeded, 1148413506);
    if ( !Pool2 )
    {
      v11 = -1073741801;
      AccessStatus = -1073741801;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_31;
      v24 = -1073741801;
      goto LABEL_9;
    }
    v14 = 1;
    v15 = ZwQuerySecurityObject(KeyHandle, 0xFu, Pool2, v12, &LengthNeeded);
    AccessStatus = v15;
    if ( v15 >= 0 )
    {
      SeCaptureSubjectContext(&SubjectContext);
      v18 = SeAccessCheck(
              Pool2,
              &SubjectContext,
              0,
              0x2000000u,
              0,
              0,
              &BfsKeyMapping,
              1,
              (PACCESS_MASK)a1 + 7,
              &AccessStatus);
      SeReleaseSubjectContext(&SubjectContext);
      if ( !v18 )
        goto LABEL_30;
      v19 = AccessStatus;
      if ( AccessStatus < 0 )
        goto LABEL_19;
      BfsRevertTokenImpersonation(&v29);
      v15 = BfsImpersonateToken(a1[1], &v29);
      AccessStatus = v15;
      if ( v15 >= 0 )
      {
        SeCaptureSubjectContext(&SubjectContext);
        v20 = SeAccessCheck(
                Pool2,
                &SubjectContext,
                0,
                0x2000000u,
                0,
                0,
                &BfsKeyMapping,
                1,
                (PACCESS_MASK)a1 + 6,
                &AccessStatus);
        SeReleaseSubjectContext(&SubjectContext);
        if ( !v20 )
        {
          v19 = AccessStatus;
          if ( (int)(AccessStatus + 0x80000000) >= 0 && AccessStatus != -1073741790 )
          {
LABEL_19:
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_30;
            v24 = v19;
            goto LABEL_29;
          }
        }
        v15 = ObReferenceObjectByHandle(
                KeyHandle,
                *((_DWORD *)a1 + 7),
                (POBJECT_TYPE)CmKeyObjectType,
                0,
                (PVOID *)a1 + 2,
                0);
        AccessStatus = v15;
        if ( v15 >= 0 )
          goto LABEL_30;
      }
      else
      {
        v14 = 0;
      }
    }
    v19 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_30;
    v24 = v15;
LABEL_29:
    v35 = 4;
    v34 = &v24;
    tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v16, v17, Classa, &v33);
LABEL_30:
    ExFreePoolWithTag(Pool2, 0);
    if ( !v14 )
      goto LABEL_32;
    goto LABEL_31;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v24 = v3;
    v35 = 4;
    v34 = &v24;
    tlgWriteTransfer_EtwWriteTransfer(dword_140019000, (int)&byte_140016D91, v4, v5, Class, &v33);
  }
LABEL_32:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x14000e2a0  mov     [rsp-8+arg_8], rbx
0x14000e2a5  mov     [rsp-8+arg_10], rsi
0x14000e2aa  push    rbp
0x14000e2ab  push    rdi
0x14000e2ac  push    r12
0x14000e2ae  push    r14
0x14000e2b0  push    r15
0x14000e2b2  lea     rbp, [rsp-10h]
0x14000e2b7  sub     rsp, 110h
0x14000e2be  mov     rax, cs:__security_cookie
0x14000e2c5  xor     rax, rsp
0x14000e2c8  mov     [rbp+30h+var_28], rax
0x14000e2cc  xorps   xmm0, xmm0
0x14000e2cf  lea     rdx, [rsp+130h+var_C0]
0x14000e2d4  xor     r12d, r12d
0x14000e2d7  mov     rdi, rcx
0x14000e2da  mov     rcx, [rcx+8]
0x14000e2de  xor     eax, eax
0x14000e2e0  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14000e2e4  mov     [rsp+130h+var_C8], r12d
0x14000e2e9  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14000e2ed  mov     [rsp+130h+LengthNeeded], r12d
0x14000e2f2  movups  [rsp+130h+var_C0], xmm0
0x14000e2f7  mov     [rbp+30h+var_B0], rax
0x14000e2fb  mov     [rsp+130h+KeyHandle], r12
0x14000e300  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14000e304  mov     [rsp+130h+var_DC], r12d
0x14000e309  movups  xmmword ptr [rbp+30h+SubjectContext.ClientToken], xmm0
0x14000e30d  movups  xmmword ptr [rbp+30h+SubjectContext.PrimaryToken], xmm0
0x14000e311  call    BfsImpersonateUser
0x14000e316  mov     [rsp+130h+var_DC], eax
0x14000e31a  test    eax, eax
0x14000e31c  jns     short loc_14000E35C
0x14000e31e  mov     ecx, cs:dword_140019000; int
0x14000e324  cmp     ecx, 3
0x14000e327  jbe     loc_14000E6A6
0x14000e32d  mov     [rsp+130h+var_E0], eax
0x14000e331  lea     rdx, byte_140016D91; int
0x14000e338  lea     rax, [rsp+130h+var_E0]
0x14000e33d  mov     [rbp+30h+var_30], 4
0x14000e345  mov     [rbp+30h+var_38], rax
0x14000e349  lea     rax, [rbp+30h+var_58]
0x14000e34d  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e352  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e357  jmp     loc_14000E6A6
0x14000e35c  mov     rcx, [rdi]
0x14000e35f  xorps   xmm0, xmm0
0x14000e362  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14000e369  mov     [rbp+30h+ObjectAttributes.RootDirectory], r12
0x14000e36d  mov     [rbp+30h+ObjectAttributes.Attributes], 600h
0x14000e374  mov     rax, [rcx]
0x14000e377  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x14000e37b  mov     eax, [rdi+20h]
0x14000e37e  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e383  cmp     eax, 1Ch
0x14000e386  jnz     short loc_14000E3E8
0x14000e388  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000e38c  mov     edx, 20000h; DesiredAccess
0x14000e391  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000e396  call    cs:__imp_ZwOpenKey
0x14000e39d  nop     dword ptr [rax+rax+00h]
0x14000e3a2  mov     [rsp+130h+var_DC], eax
0x14000e3a6  test    eax, eax
0x14000e3a8  jns     short loc_14000E422
0x14000e3aa  mov     ecx, cs:dword_140019000; int
0x14000e3b0  cmp     ecx, 3
0x14000e3b3  jbe     loc_14000E69C
0x14000e3b9  mov     [rsp+130h+var_E0], eax
0x14000e3bd  lea     rax, [rsp+130h+var_E0]
0x14000e3c2  mov     [rbp+30h+var_30], 4
0x14000e3ca  mov     [rbp+30h+var_38], rax
0x14000e3ce  lea     rdx, byte_140016D91; int
0x14000e3d5  lea     rax, [rbp+30h+var_58]
0x14000e3d9  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e3de  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e3e3  jmp     loc_14000E69C
0x14000e3e8  cmp     eax, 1Ah
0x14000e3eb  jnz     short loc_14000E422
0x14000e3ed  lea     rax, [rsp+130h+var_C8]
0x14000e3f2  xor     r9d, r9d; TitleIndex
0x14000e3f5  mov     [rsp+130h+Disposition], rax; Disposition
0x14000e3fa  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000e3fe  mov     eax, [rcx+18h]
0x14000e401  mov     edx, 20000h; DesiredAccess
0x14000e406  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14000e40a  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000e40f  mov     [rsp+130h+Class], r12; Class
0x14000e414  call    cs:__imp_ZwCreateKey
0x14000e41b  nop     dword ptr [rax+rax+00h]
0x14000e420  jmp     short loc_14000E3A2
0x14000e422  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e427  lea     rax, [rsp+130h+LengthNeeded]
0x14000e42c  xor     r9d, r9d; Length
0x14000e42f  mov     [rsp+130h+Class], rax; LengthNeeded
0x14000e434  xor     r8d, r8d; SecurityDescriptor
0x14000e437  lea     r15d, [r9+0Fh]
0x14000e43b  mov     edx, r15d; SecurityInformation
0x14000e43e  call    cs:__imp_ZwQuerySecurityObject
0x14000e445  nop     dword ptr [rax+rax+00h]
0x14000e44a  mov     [rsp+130h+var_DC], eax
0x14000e44e  cmp     eax, 0C0000023h
0x14000e453  jnz     loc_14000E69C
0x14000e459  mov     ebx, [rsp+130h+LengthNeeded]
0x14000e45d  mov     ecx, 100h
0x14000e462  mov     edx, ebx
0x14000e464  mov     r8d, 44736642h
0x14000e46a  call    cs:__imp_ExAllocatePool2
0x14000e471  nop     dword ptr [rax+rax+00h]
0x14000e476  mov     rsi, rax
0x14000e479  test    rax, rax
0x14000e47c  jnz     short loc_14000E49F
0x14000e47e  mov     eax, cs:dword_140019000
0x14000e484  mov     ecx, 0C0000017h
0x14000e489  mov     [rsp+130h+var_DC], ecx
0x14000e48d  cmp     eax, 3
0x14000e490  jbe     loc_14000E69C
0x14000e496  mov     [rsp+130h+var_E0], ecx
0x14000e49a  jmp     loc_14000E3BD
0x14000e49f  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e4a4  lea     rax, [rsp+130h+LengthNeeded]
0x14000e4a9  mov     r9d, ebx; Length
0x14000e4ac  mov     [rsp+130h+Class], rax; LengthNeeded
0x14000e4b1  mov     r8, rsi; SecurityDescriptor
0x14000e4b4  mov     edx, r15d; SecurityInformation
0x14000e4b7  mov     r14b, 1
0x14000e4ba  call    cs:__imp_ZwQuerySecurityObject
0x14000e4c1  nop     dword ptr [rax+rax+00h]
0x14000e4c6  mov     [rsp+130h+var_DC], eax
0x14000e4ca  test    eax, eax
0x14000e4cc  js      loc_14000E651
0x14000e4d2  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e4d6  call    cs:__imp_SeCaptureSubjectContext
0x14000e4dd  nop     dword ptr [rax+rax+00h]
0x14000e4e2  lea     rax, [rsp+130h+var_DC]
0x14000e4e7  mov     r9d, 2000000h; DesiredAccess
0x14000e4ed  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x14000e4f2  lea     r15, [rdi+1Ch]
0x14000e4f6  mov     [rsp+130h+GrantedAccess], r15; GrantedAccess
0x14000e4fb  lea     rax, BfsKeyMapping
0x14000e502  mov     [rsp+130h+AccessMode], r14b; AccessMode
0x14000e507  lea     rdx, [rbp+30h+SubjectContext]; SubjectSecurityContext
0x14000e50b  mov     [rsp+130h+Disposition], rax; GenericMapping
0x14000e510  xor     r8d, r8d; SubjectContextLocked
0x14000e513  mov     qword ptr [rsp+130h+CreateOptions], r12; Privileges
0x14000e518  mov     rcx, rsi; SecurityDescriptor
0x14000e51b  mov     dword ptr [rsp+130h+Class], r12d; PreviouslyGrantedAccess
0x14000e520  call    cs:__imp_SeAccessCheck
0x14000e527  nop     dword ptr [rax+rax+00h]
0x14000e52c  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e530  mov     bl, al
0x14000e532  call    cs:__imp_SeReleaseSubjectContext
0x14000e539  nop     dword ptr [rax+rax+00h]
0x14000e53e  test    bl, bl
0x14000e540  jz      loc_14000E686
0x14000e546  mov     ecx, [rsp+130h+var_DC]
0x14000e54a  test    ecx, ecx
0x14000e54c  jns     short loc_14000E566
0x14000e54e  mov     eax, cs:dword_140019000
0x14000e554  cmp     eax, 3
0x14000e557  jbe     loc_14000E686
0x14000e55d  mov     [rsp+130h+var_E0], ecx
0x14000e561  jmp     loc_14000E660
0x14000e566  lea     rcx, [rsp+130h+var_C0]
0x14000e56b  call    BfsRevertTokenImpersonation
0x14000e570  mov     rcx, [rdi+8]
0x14000e574  lea     rdx, [rsp+130h+var_C0]
0x14000e579  call    BfsImpersonateToken
0x14000e57e  mov     [rsp+130h+var_DC], eax
0x14000e582  test    eax, eax
0x14000e584  jns     short loc_14000E58E
0x14000e586  mov     r14b, r12b
0x14000e589  jmp     loc_14000E651
0x14000e58e  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e592  call    cs:__imp_SeCaptureSubjectContext
0x14000e599  nop     dword ptr [rax+rax+00h]
0x14000e59e  lea     rcx, [rsp+130h+var_DC]
0x14000e5a3  mov     r9d, 2000000h; DesiredAccess
0x14000e5a9  mov     [rsp+130h+AccessStatus], rcx; AccessStatus
0x14000e5ae  lea     rax, [rdi+18h]
0x14000e5b2  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x14000e5b7  lea     rdx, [rbp+30h+SubjectContext]; SubjectSecurityContext
0x14000e5bb  mov     [rsp+130h+AccessMode], r14b; AccessMode
0x14000e5c0  lea     rax, BfsKeyMapping
0x14000e5c7  mov     [rsp+130h+Disposition], rax; GenericMapping
0x14000e5cc  xor     r8d, r8d; SubjectContextLocked
0x14000e5cf  mov     qword ptr [rsp+130h+CreateOptions], r12; Privileges
0x14000e5d4  mov     rcx, rsi; SecurityDescriptor
0x14000e5d7  mov     dword ptr [rsp+130h+Class], r12d; PreviouslyGrantedAccess
0x14000e5dc  call    cs:__imp_SeAccessCheck
0x14000e5e3  nop     dword ptr [rax+rax+00h]
0x14000e5e8  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e5ec  mov     bl, al
0x14000e5ee  call    cs:__imp_SeReleaseSubjectContext
0x14000e5f5  nop     dword ptr [rax+rax+00h]
0x14000e5fa  test    bl, bl
0x14000e5fc  jnz     short loc_14000E61A
0x14000e5fe  mov     ecx, [rsp+130h+var_DC]
0x14000e602  mov     edx, 80000000h
0x14000e607  lea     eax, [rcx+rdx]
0x14000e60a  test    edx, eax
0x14000e60c  jnz     short loc_14000E61A
0x14000e60e  cmp     ecx, 0C0000022h
0x14000e614  jnz     loc_14000E54E
0x14000e61a  mov     r8, cs:__imp_CmKeyObjectType
0x14000e621  lea     rax, [rdi+10h]
0x14000e625  mov     edx, [r15]; DesiredAccess
0x14000e628  xor     r9d, r9d; AccessMode
0x14000e62b  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e630  mov     qword ptr [rsp+130h+CreateOptions], r12; HandleInformation
0x14000e635  mov     r8, [r8]; ObjectType
0x14000e638  mov     [rsp+130h+Class], rax; int
0x14000e63d  call    cs:__imp_ObReferenceObjectByHandle
0x14000e644  nop     dword ptr [rax+rax+00h]
0x14000e649  mov     [rsp+130h+var_DC], eax
0x14000e64d  test    eax, eax
0x14000e64f  jns     short loc_14000E686
0x14000e651  mov     ecx, cs:dword_140019000; int
0x14000e657  cmp     ecx, 3
0x14000e65a  jbe     short loc_14000E686
0x14000e65c  mov     [rsp+130h+var_E0], eax
0x14000e660  lea     rax, [rsp+130h+var_E0]
0x14000e665  mov     [rbp+30h+var_30], 4
0x14000e66d  mov     [rbp+30h+var_38], rax
0x14000e671  lea     rdx, byte_140016D91; int
0x14000e678  lea     rax, [rbp+30h+var_58]
0x14000e67c  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e681  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e686  xor     edx, edx; Tag
0x14000e688  mov     rcx, rsi; P
0x14000e68b  call    cs:__imp_ExFreePoolWithTag
0x14000e692  nop     dword ptr [rax+rax+00h]
0x14000e697  test    r14b, r14b
0x14000e69a  jz      short loc_14000E6A6
0x14000e69c  lea     rcx, [rsp+130h+var_C0]
0x14000e6a1  call    BfsRevertTokenImpersonation
0x14000e6a6  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e6ab  test    rcx, rcx
0x14000e6ae  jz      short loc_14000E6BC
0x14000e6b0  call    cs:__imp_ZwClose
0x14000e6b7  nop     dword ptr [rax+rax+00h]
0x14000e6bc  mov     eax, [rsp+130h+var_DC]
0x14000e6c0  mov     rcx, [rbp+30h+var_28]
0x14000e6c4  xor     rcx, rsp; StackCookie
0x14000e6c7  call    __security_check_cookie
0x14000e6cc  lea     r11, [rsp+130h+var_20]
0x14000e6d4  mov     rbx, [r11+38h]
0x14000e6d8  mov     rsi, [r11+40h]
0x14000e6dc  mov     rsp, r11
0x14000e6df  pop     r15
0x14000e6e1  pop     r14
0x14000e6e3  pop     r12
0x14000e6e5  pop     rdi
0x14000e6e6  pop     rbp
0x14000e6e7  retn
```
