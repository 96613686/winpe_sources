# BfsAccessRegistryKeyAsUserCallback

- ea: `0x14000e110`
- end: `0x14000e559`
- name: `BfsAccessRegistryKeyAsUserCallback`
- size: `1097`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140001008`
- `0x14000e110`
- `0x14000f9c8`
- `0x14000fc24`
- `0x14000fecc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e4ad`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e4ad`
- `ntoskrnl!ZwOpenKey` at `0x14000e206`
- `ntoskrnl!ZwOpenKey` at `0x14000e206`
- `ntoskrnl!CmKeyObjectType` at `0x14000e48a`
- `ntoskrnl!ZwCreateKey` at `0x14000e284`
- `ntoskrnl!ZwCreateKey` at `0x14000e284`
- `ntoskrnl!SeAccessCheck` at `0x14000e390`
- `ntoskrnl!SeAccessCheck` at `0x14000e44c`
- `ntoskrnl!SeAccessCheck` at `0x14000e390`
- `ntoskrnl!SeAccessCheck` at `0x14000e44c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e2ae`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e32a`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e2ae`
- `ntoskrnl!ZwQuerySecurityObject` at `0x14000e32a`
- `ntoskrnl!ZwClose` at `0x14000e520`
- `ntoskrnl!ZwClose` at `0x14000e520`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e3a2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e45e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e3a2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000e45e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e346`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e402`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e346`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14000e402`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e4fb`
- `ntoskrnl!ExAllocatePool2` at `0x14000e2da`
- `ntoskrnl!ExAllocatePool2` at `0x14000e2da`

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
0x14000e110  mov     [rsp-8+arg_8], rbx
0x14000e115  mov     [rsp-8+arg_10], rsi
0x14000e11a  push    rbp
0x14000e11b  push    rdi
0x14000e11c  push    r12
0x14000e11e  push    r14
0x14000e120  push    r15
0x14000e122  lea     rbp, [rsp-10h]
0x14000e127  sub     rsp, 110h
0x14000e12e  mov     rax, cs:__security_cookie
0x14000e135  xor     rax, rsp
0x14000e138  mov     [rbp+30h+var_28], rax
0x14000e13c  xorps   xmm0, xmm0
0x14000e13f  lea     rdx, [rsp+130h+var_C0]
0x14000e144  xor     r12d, r12d
0x14000e147  mov     rdi, rcx
0x14000e14a  mov     rcx, [rcx+8]
0x14000e14e  xor     eax, eax
0x14000e150  movups  xmmword ptr [rbp+30h+ObjectAttributes.ObjectName], xmm0
0x14000e154  mov     [rsp+130h+var_C8], r12d
0x14000e159  movups  xmmword ptr [rbp+30h+ObjectAttributes+1Ch], xmm0
0x14000e15d  mov     [rsp+130h+LengthNeeded], r12d
0x14000e162  movups  [rsp+130h+var_C0], xmm0
0x14000e167  mov     [rbp+30h+var_B0], rax
0x14000e16b  mov     [rsp+130h+KeyHandle], r12
0x14000e170  movups  xmmword ptr [rbp+30h+ObjectAttributes.Length], xmm0
0x14000e174  mov     [rsp+130h+var_DC], r12d
0x14000e179  movups  xmmword ptr [rbp+30h+SubjectContext.ClientToken], xmm0
0x14000e17d  movups  xmmword ptr [rbp+30h+SubjectContext.PrimaryToken], xmm0
0x14000e181  call    BfsImpersonateUser
0x14000e186  mov     [rsp+130h+var_DC], eax
0x14000e18a  test    eax, eax
0x14000e18c  jns     short loc_14000E1CC
0x14000e18e  mov     ecx, cs:dword_140019000; int
0x14000e194  cmp     ecx, 3
0x14000e197  jbe     loc_14000E516
0x14000e19d  mov     [rsp+130h+var_E0], eax
0x14000e1a1  lea     rdx, byte_140016D91; int
0x14000e1a8  lea     rax, [rsp+130h+var_E0]
0x14000e1ad  mov     [rbp+30h+var_30], 4
0x14000e1b5  mov     [rbp+30h+var_38], rax
0x14000e1b9  lea     rax, [rbp+30h+var_58]
0x14000e1bd  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e1c2  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e1c7  jmp     loc_14000E516
0x14000e1cc  mov     rcx, [rdi]
0x14000e1cf  xorps   xmm0, xmm0
0x14000e1d2  mov     [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x14000e1d9  mov     [rbp+30h+ObjectAttributes.RootDirectory], r12
0x14000e1dd  mov     [rbp+30h+ObjectAttributes.Attributes], 600h
0x14000e1e4  mov     rax, [rcx]
0x14000e1e7  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x14000e1eb  mov     eax, [rdi+20h]
0x14000e1ee  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e1f3  cmp     eax, 1Ch
0x14000e1f6  jnz     short loc_14000E258
0x14000e1f8  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000e1fc  mov     edx, 20000h; DesiredAccess
0x14000e201  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000e206  call    cs:__imp_ZwOpenKey
0x14000e20d  nop     dword ptr [rax+rax+00h]
0x14000e212  mov     [rsp+130h+var_DC], eax
0x14000e216  test    eax, eax
0x14000e218  jns     short loc_14000E292
0x14000e21a  mov     ecx, cs:dword_140019000; int
0x14000e220  cmp     ecx, 3
0x14000e223  jbe     loc_14000E50C
0x14000e229  mov     [rsp+130h+var_E0], eax
0x14000e22d  lea     rax, [rsp+130h+var_E0]
0x14000e232  mov     [rbp+30h+var_30], 4
0x14000e23a  mov     [rbp+30h+var_38], rax
0x14000e23e  lea     rdx, byte_140016D91; int
0x14000e245  lea     rax, [rbp+30h+var_58]
0x14000e249  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e24e  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e253  jmp     loc_14000E50C
0x14000e258  cmp     eax, 1Ah
0x14000e25b  jnz     short loc_14000E292
0x14000e25d  lea     rax, [rsp+130h+var_C8]
0x14000e262  xor     r9d, r9d; TitleIndex
0x14000e265  mov     [rsp+130h+Disposition], rax; Disposition
0x14000e26a  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14000e26e  mov     eax, [rcx+18h]
0x14000e271  mov     edx, 20000h; DesiredAccess
0x14000e276  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14000e27a  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14000e27f  mov     [rsp+130h+Class], r12; Class
0x14000e284  call    cs:__imp_ZwCreateKey
0x14000e28b  nop     dword ptr [rax+rax+00h]
0x14000e290  jmp     short loc_14000E212
0x14000e292  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e297  lea     rax, [rsp+130h+LengthNeeded]
0x14000e29c  xor     r9d, r9d; Length
0x14000e29f  mov     [rsp+130h+Class], rax; LengthNeeded
0x14000e2a4  xor     r8d, r8d; SecurityDescriptor
0x14000e2a7  lea     r15d, [r9+0Fh]
0x14000e2ab  mov     edx, r15d; SecurityInformation
0x14000e2ae  call    cs:__imp_ZwQuerySecurityObject
0x14000e2b5  nop     dword ptr [rax+rax+00h]
0x14000e2ba  mov     [rsp+130h+var_DC], eax
0x14000e2be  cmp     eax, 0C0000023h
0x14000e2c3  jnz     loc_14000E50C
0x14000e2c9  mov     ebx, [rsp+130h+LengthNeeded]
0x14000e2cd  mov     ecx, 100h
0x14000e2d2  mov     edx, ebx
0x14000e2d4  mov     r8d, 44736642h
0x14000e2da  call    cs:__imp_ExAllocatePool2
0x14000e2e1  nop     dword ptr [rax+rax+00h]
0x14000e2e6  mov     rsi, rax
0x14000e2e9  test    rax, rax
0x14000e2ec  jnz     short loc_14000E30F
0x14000e2ee  mov     eax, cs:dword_140019000
0x14000e2f4  mov     ecx, 0C0000017h
0x14000e2f9  mov     [rsp+130h+var_DC], ecx
0x14000e2fd  cmp     eax, 3
0x14000e300  jbe     loc_14000E50C
0x14000e306  mov     [rsp+130h+var_E0], ecx
0x14000e30a  jmp     loc_14000E22D
0x14000e30f  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e314  lea     rax, [rsp+130h+LengthNeeded]
0x14000e319  mov     r9d, ebx; Length
0x14000e31c  mov     [rsp+130h+Class], rax; LengthNeeded
0x14000e321  mov     r8, rsi; SecurityDescriptor
0x14000e324  mov     edx, r15d; SecurityInformation
0x14000e327  mov     r14b, 1
0x14000e32a  call    cs:__imp_ZwQuerySecurityObject
0x14000e331  nop     dword ptr [rax+rax+00h]
0x14000e336  mov     [rsp+130h+var_DC], eax
0x14000e33a  test    eax, eax
0x14000e33c  js      loc_14000E4C1
0x14000e342  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e346  call    cs:__imp_SeCaptureSubjectContext
0x14000e34d  nop     dword ptr [rax+rax+00h]
0x14000e352  lea     rax, [rsp+130h+var_DC]
0x14000e357  mov     r9d, 2000000h; DesiredAccess
0x14000e35d  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x14000e362  lea     r15, [rdi+1Ch]
0x14000e366  mov     [rsp+130h+GrantedAccess], r15; GrantedAccess
0x14000e36b  lea     rax, BfsKeyMapping
0x14000e372  mov     [rsp+130h+AccessMode], r14b; AccessMode
0x14000e377  lea     rdx, [rbp+30h+SubjectContext]; SubjectSecurityContext
0x14000e37b  mov     [rsp+130h+Disposition], rax; GenericMapping
0x14000e380  xor     r8d, r8d; SubjectContextLocked
0x14000e383  mov     qword ptr [rsp+130h+CreateOptions], r12; Privileges
0x14000e388  mov     rcx, rsi; SecurityDescriptor
0x14000e38b  mov     dword ptr [rsp+130h+Class], r12d; PreviouslyGrantedAccess
0x14000e390  call    cs:__imp_SeAccessCheck
0x14000e397  nop     dword ptr [rax+rax+00h]
0x14000e39c  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e3a0  mov     bl, al
0x14000e3a2  call    cs:__imp_SeReleaseSubjectContext
0x14000e3a9  nop     dword ptr [rax+rax+00h]
0x14000e3ae  test    bl, bl
0x14000e3b0  jz      loc_14000E4F6
0x14000e3b6  mov     ecx, [rsp+130h+var_DC]
0x14000e3ba  test    ecx, ecx
0x14000e3bc  jns     short loc_14000E3D6
0x14000e3be  mov     eax, cs:dword_140019000
0x14000e3c4  cmp     eax, 3
0x14000e3c7  jbe     loc_14000E4F6
0x14000e3cd  mov     [rsp+130h+var_E0], ecx
0x14000e3d1  jmp     loc_14000E4D0
0x14000e3d6  lea     rcx, [rsp+130h+var_C0]
0x14000e3db  call    BfsRevertTokenImpersonation
0x14000e3e0  mov     rcx, [rdi+8]
0x14000e3e4  lea     rdx, [rsp+130h+var_C0]
0x14000e3e9  call    BfsImpersonateToken
0x14000e3ee  mov     [rsp+130h+var_DC], eax
0x14000e3f2  test    eax, eax
0x14000e3f4  jns     short loc_14000E3FE
0x14000e3f6  mov     r14b, r12b
0x14000e3f9  jmp     loc_14000E4C1
0x14000e3fe  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e402  call    cs:__imp_SeCaptureSubjectContext
0x14000e409  nop     dword ptr [rax+rax+00h]
0x14000e40e  lea     rcx, [rsp+130h+var_DC]
0x14000e413  mov     r9d, 2000000h; DesiredAccess
0x14000e419  mov     [rsp+130h+AccessStatus], rcx; AccessStatus
0x14000e41e  lea     rax, [rdi+18h]
0x14000e422  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x14000e427  lea     rdx, [rbp+30h+SubjectContext]; SubjectSecurityContext
0x14000e42b  mov     [rsp+130h+AccessMode], r14b; AccessMode
0x14000e430  lea     rax, BfsKeyMapping
0x14000e437  mov     [rsp+130h+Disposition], rax; GenericMapping
0x14000e43c  xor     r8d, r8d; SubjectContextLocked
0x14000e43f  mov     qword ptr [rsp+130h+CreateOptions], r12; Privileges
0x14000e444  mov     rcx, rsi; SecurityDescriptor
0x14000e447  mov     dword ptr [rsp+130h+Class], r12d; PreviouslyGrantedAccess
0x14000e44c  call    cs:__imp_SeAccessCheck
0x14000e453  nop     dword ptr [rax+rax+00h]
0x14000e458  lea     rcx, [rbp+30h+SubjectContext]; SubjectContext
0x14000e45c  mov     bl, al
0x14000e45e  call    cs:__imp_SeReleaseSubjectContext
0x14000e465  nop     dword ptr [rax+rax+00h]
0x14000e46a  test    bl, bl
0x14000e46c  jnz     short loc_14000E48A
0x14000e46e  mov     ecx, [rsp+130h+var_DC]
0x14000e472  mov     edx, 80000000h
0x14000e477  lea     eax, [rcx+rdx]
0x14000e47a  test    edx, eax
0x14000e47c  jnz     short loc_14000E48A
0x14000e47e  cmp     ecx, 0C0000022h
0x14000e484  jnz     loc_14000E3BE
0x14000e48a  mov     r8, cs:__imp_CmKeyObjectType
0x14000e491  lea     rax, [rdi+10h]
0x14000e495  mov     edx, [r15]; DesiredAccess
0x14000e498  xor     r9d, r9d; AccessMode
0x14000e49b  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e4a0  mov     qword ptr [rsp+130h+CreateOptions], r12; HandleInformation
0x14000e4a5  mov     r8, [r8]; ObjectType
0x14000e4a8  mov     [rsp+130h+Class], rax; int
0x14000e4ad  call    cs:__imp_ObReferenceObjectByHandle
0x14000e4b4  nop     dword ptr [rax+rax+00h]
0x14000e4b9  mov     [rsp+130h+var_DC], eax
0x14000e4bd  test    eax, eax
0x14000e4bf  jns     short loc_14000E4F6
0x14000e4c1  mov     ecx, cs:dword_140019000; int
0x14000e4c7  cmp     ecx, 3
0x14000e4ca  jbe     short loc_14000E4F6
0x14000e4cc  mov     [rsp+130h+var_E0], eax
0x14000e4d0  lea     rax, [rsp+130h+var_E0]
0x14000e4d5  mov     [rbp+30h+var_30], 4
0x14000e4dd  mov     [rbp+30h+var_38], rax
0x14000e4e1  lea     rdx, byte_140016D91; int
0x14000e4e8  lea     rax, [rbp+30h+var_58]
0x14000e4ec  mov     qword ptr [rsp+130h+CreateOptions], rax; PEVENT_DATA_DESCRIPTOR
0x14000e4f1  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000e4f6  xor     edx, edx; Tag
0x14000e4f8  mov     rcx, rsi; P
0x14000e4fb  call    cs:__imp_ExFreePoolWithTag
0x14000e502  nop     dword ptr [rax+rax+00h]
0x14000e507  test    r14b, r14b
0x14000e50a  jz      short loc_14000E516
0x14000e50c  lea     rcx, [rsp+130h+var_C0]
0x14000e511  call    BfsRevertTokenImpersonation
0x14000e516  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x14000e51b  test    rcx, rcx
0x14000e51e  jz      short loc_14000E52C
0x14000e520  call    cs:__imp_ZwClose
0x14000e527  nop     dword ptr [rax+rax+00h]
0x14000e52c  mov     eax, [rsp+130h+var_DC]
0x14000e530  mov     rcx, [rbp+30h+var_28]
0x14000e534  xor     rcx, rsp; StackCookie
0x14000e537  call    __security_check_cookie
0x14000e53c  lea     r11, [rsp+130h+var_20]
0x14000e544  mov     rbx, [r11+38h]
0x14000e548  mov     rsi, [r11+40h]
0x14000e54c  mov     rsp, r11
0x14000e54f  pop     r15
0x14000e551  pop     r14
0x14000e553  pop     r12
0x14000e555  pop     rdi
0x14000e556  pop     rbp
0x14000e557  retn
```
