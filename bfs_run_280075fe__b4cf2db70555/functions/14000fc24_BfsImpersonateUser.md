# BfsImpersonateUser

- ea: `0x14000fc24`
- end: `0x14000fec3`
- name: `BfsImpersonateUser`
- size: `671`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140006810`
- `0x14000a3a0`
- `0x14000a7a0`
- `0x14000e110`

## callees

- `0x140001008`
- `0x14000fc24`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fd65`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fd65`
- `ntoskrnl!SeTokenObjectType` at `0x14000fc7a`
- `ntoskrnl!SeTokenObjectType` at `0x14000fd44`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fcb1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fcb1`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fd2e`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fd2e`
- `ntoskrnl!ZwSetInformationToken` at `0x14000fdde`
- `ntoskrnl!ZwSetInformationToken` at `0x14000fdde`
- `ntoskrnl!PsRevertToSelf` at `0x14000fda4`
- `ntoskrnl!PsRevertToSelf` at `0x14000fda4`
- `ntoskrnl!PsImpersonateClient` at `0x14000fe0b`
- `ntoskrnl!PsImpersonateClient` at `0x14000fe0b`
- `ntoskrnl!ZwClose` at `0x14000fe7b`
- `ntoskrnl!ZwClose` at `0x14000fe90`
- `ntoskrnl!ZwClose` at `0x14000fe7b`
- `ntoskrnl!ZwClose` at `0x14000fe90`
- `ntoskrnl!SeExports` at `0x14000fdb0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fe59`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fe59`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fd90`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fd90`

## pseudocode

```c
__int64 __fastcall BfsImpersonateUser(void *a1, __int64 a2)
{
  NTSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  NTSTATUS v6; // ebx
  int v7; // ecx
  PACCESS_TOKEN v8; // rsi
  int ObjectType; // [rsp+20h] [rbp-89h]
  NTSTATUS v11; // [rsp+40h] [rbp-69h] BYREF
  PVOID Object; // [rsp+48h] [rbp-61h] BYREF
  void *NewTokenHandle; // [rsp+50h] [rbp-59h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-51h] BYREF
  __int128 TokenInformation; // [rsp+60h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-9h] BYREF
  int v18; // [rsp+A8h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+B0h] [rbp+7h] BYREF
  NTSTATUS *v20; // [rsp+D0h] [rbp+27h]
  __int64 v21; // [rsp+D8h] [rbp+2Fh]

  v17 = 0;
  v18 = 0;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  NewTokenHandle = 0;
  TokenInformation = 0;
  Object = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  ExistingTokenHandle = 0;
  v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &ExistingTokenHandle);
  v6 = v3;
  if ( v3 < 0 )
  {
    v7 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_13;
    v11 = v3;
    goto LABEL_12;
  }
  ObjectAttributes.SecurityQualityOfService = &v17;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.SecurityDescriptor = 0;
  v17 = 0x20000000CLL;
  LOWORD(v18) = 1;
  v6 = ZwDuplicateToken(ExistingTokenHandle, 0xF01FFu, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle);
  if ( v6 >= 0 )
  {
    v6 = ObReferenceObjectByHandle(NewTokenHandle, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &Object, 0);
    if ( v6 >= 0 )
    {
      v8 = PsReferenceImpersonationToken(
             KeGetCurrentThread(),
             (PBOOLEAN)(a2 + 16),
             (PBOOLEAN)(a2 + 17),
             (PSECURITY_IMPERSONATION_LEVEL)(a2 + 20));
      if ( v8 )
        PsRevertToSelf();
      *(_QWORD *)&TokenInformation = SeExports->SeMediumMandatorySid;
      DWORD2(TokenInformation) = 96;
      v6 = ZwSetInformationToken(NewTokenHandle, TokenIntegrityLevel, &TokenInformation, 0x10u);
      if ( v6 >= 0 )
      {
        v6 = PsImpersonateClient(KeGetCurrentThread(), Object, 0, 0, SecurityImpersonation);
        if ( v6 >= 0 )
        {
          *(_QWORD *)a2 = Object;
          *(_QWORD *)(a2 + 8) = v8;
          goto LABEL_16;
        }
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v11 = v6;
LABEL_12:
    v21 = 4;
    v20 = &v11;
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, ObjectType, &v19);
  }
LABEL_13:
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_16:
  if ( NewTokenHandle )
    ZwClose(NewTokenHandle);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000fc24  mov     [rsp-8+arg_10], rbx
0x14000fc29  mov     [rsp-8+arg_18], rsi
0x14000fc2e  push    rbp
0x14000fc2f  push    rdi
0x14000fc30  push    r14
0x14000fc32  lea     rbp, [rsp-47h]
0x14000fc37  sub     rsp, 0F0h
0x14000fc3e  mov     rax, cs:__security_cookie
0x14000fc45  xor     rax, rsp
0x14000fc48  mov     [rbp+57h+var_20], rax
0x14000fc4c  xor     eax, eax
0x14000fc4e  xor     r14d, r14d
0x14000fc51  xorps   xmm1, xmm1
0x14000fc54  mov     [rbp+57h+var_60], rax
0x14000fc58  xorps   xmm0, xmm0
0x14000fc5b  mov     [rbp+57h+var_58], eax
0x14000fc5e  movups  xmmword ptr [rdx], xmm0
0x14000fc61  mov     [rdx+10h], rax
0x14000fc65  mov     rdi, rdx
0x14000fc68  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000fc6c  mov     [rbp+57h+NewTokenHandle], r14
0x14000fc70  mov     [rsp+100h+Handle], rax; Handle
0x14000fc75  mov     esi, 0F01FFh
0x14000fc7a  mov     rax, cs:__imp_SeTokenObjectType
0x14000fc81  mov     r9d, esi; DesiredAccess
0x14000fc84  mov     [rsp+100h+AccessMode], r14b; AccessMode
0x14000fc89  xor     r8d, r8d; PassedAccessState
0x14000fc8c  movups  [rbp+57h+TokenInformation], xmm0
0x14000fc90  mov     [rbp+57h+Object], r14
0x14000fc94  mov     rdx, [rax]
0x14000fc97  mov     [rsp+100h+ObjectType], rdx; ObjectType
0x14000fc9c  mov     edx, 200h; HandleAttributes
0x14000fca1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14000fca5  mov     [rbp+57h+ExistingTokenHandle], r14
0x14000fca9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14000fcad  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000fcb1  call    cs:__imp_ObOpenObjectByPointer
0x14000fcb8  nop     dword ptr [rax+rax+00h]
0x14000fcbd  mov     ebx, eax
0x14000fcbf  test    eax, eax
0x14000fcc1  jns     short loc_14000FCDA
0x14000fcc3  mov     ecx, cs:dword_140019000
0x14000fcc9  cmp     ecx, 3
0x14000fccc  jbe     loc_14000FE50
0x14000fcd2  mov     [rbp+57h+var_C0], eax
0x14000fcd5  jmp     loc_14000FE2B
0x14000fcda  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000fcde  lea     rax, [rbp+57h+var_60]
0x14000fce2  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000fce6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fcea  lea     rax, [rbp+57h+NewTokenHandle]
0x14000fcee  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000fcf5  mov     qword ptr [rsp+100h+AccessMode], rax; NewTokenHandle
0x14000fcfa  xor     r9d, r9d; EffectiveOnly
0x14000fcfd  mov     edx, esi; DesiredAccess
0x14000fcff  mov     dword ptr [rsp+100h+ObjectType], 2; TokenType
0x14000fd07  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000fd0b  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000fd12  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14000fd16  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x14000fd1a  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000fd21  mov     dword ptr [rbp+57h+var_60+4], 2
0x14000fd28  mov     word ptr [rbp+57h+var_58], 1
0x14000fd2e  call    cs:__imp_ZwDuplicateToken
0x14000fd35  nop     dword ptr [rax+rax+00h]
0x14000fd3a  mov     ebx, eax
0x14000fd3c  test    eax, eax
0x14000fd3e  js      loc_14000FE1D
0x14000fd44  mov     r8, cs:__imp_SeTokenObjectType
0x14000fd4b  lea     rax, [rbp+57h+Object]
0x14000fd4f  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fd53  xor     r9d, r9d; AccessMode
0x14000fd56  mov     qword ptr [rsp+100h+AccessMode], r14; HandleInformation
0x14000fd5b  mov     edx, esi; DesiredAccess
0x14000fd5d  mov     [rsp+100h+ObjectType], rax; Object
0x14000fd62  mov     r8, [r8]; ObjectType
0x14000fd65  call    cs:__imp_ObReferenceObjectByHandle
0x14000fd6c  nop     dword ptr [rax+rax+00h]
0x14000fd71  mov     ebx, eax
0x14000fd73  test    eax, eax
0x14000fd75  js      loc_14000FE1D
0x14000fd7b  mov     rcx, gs:188h; Thread
0x14000fd84  lea     r9, [rdi+14h]; ImpersonationLevel
0x14000fd88  lea     r8, [rdi+11h]; EffectiveOnly
0x14000fd8c  lea     rdx, [rdi+10h]; CopyOnOpen
0x14000fd90  call    cs:__imp_PsReferenceImpersonationToken
0x14000fd97  nop     dword ptr [rax+rax+00h]
0x14000fd9c  mov     rsi, rax
0x14000fd9f  test    rax, rax
0x14000fda2  jz      short loc_14000FDB0
0x14000fda4  call    cs:__imp_PsRevertToSelf
0x14000fdab  nop     dword ptr [rax+rax+00h]
0x14000fdb0  mov     rcx, cs:__imp_SeExports
0x14000fdb7  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000fdbb  mov     r9d, 10h; TokenInformationLength
0x14000fdc1  mov     rdx, [rcx]
0x14000fdc4  mov     rcx, [rdx+1E8h]
0x14000fdcb  lea     edx, [r9+9]; TokenInformationClass
0x14000fdcf  mov     qword ptr [rbp+57h+TokenInformation], rcx
0x14000fdd3  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x14000fdd7  mov     dword ptr [rbp+57h+TokenInformation+8], 60h ; '`'
0x14000fdde  call    cs:__imp_ZwSetInformationToken
0x14000fde5  nop     dword ptr [rax+rax+00h]
0x14000fdea  mov     ebx, eax
0x14000fdec  test    eax, eax
0x14000fdee  js      short loc_14000FE1D
0x14000fdf0  mov     rcx, gs:188h; Thread
0x14000fdf9  xor     r9d, r9d; EffectiveOnly
0x14000fdfc  mov     rdx, [rbp+57h+Object]; Token
0x14000fe00  xor     r8d, r8d; CopyOnOpen
0x14000fe03  mov     dword ptr [rsp+100h+ObjectType], 2; int
0x14000fe0b  call    cs:__imp_PsImpersonateClient
0x14000fe12  nop     dword ptr [rax+rax+00h]
0x14000fe17  mov     ebx, eax
0x14000fe19  test    eax, eax
0x14000fe1b  jns     short loc_14000FE67
0x14000fe1d  mov     eax, cs:dword_140019000
0x14000fe23  cmp     eax, 3
0x14000fe26  jbe     short loc_14000FE50
0x14000fe28  mov     [rbp+57h+var_C0], ebx
0x14000fe2b  lea     rax, [rbp+57h+var_C0]
0x14000fe2f  mov     [rbp+57h+var_28], 4
0x14000fe37  mov     [rbp+57h+var_30], rax
0x14000fe3b  lea     rdx, byte_140016D91; int
0x14000fe42  lea     rax, [rbp+57h+var_50]
0x14000fe46  mov     qword ptr [rsp+100h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000fe4b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000fe50  mov     rcx, [rbp+57h+Object]; Object
0x14000fe54  test    rcx, rcx
0x14000fe57  jz      short loc_14000FE72
0x14000fe59  call    cs:__imp_ObfDereferenceObject
0x14000fe60  nop     dword ptr [rax+rax+00h]
0x14000fe65  jmp     short loc_14000FE72
0x14000fe67  mov     rax, [rbp+57h+Object]
0x14000fe6b  mov     [rdi], rax
0x14000fe6e  mov     [rdi+8], rsi
0x14000fe72  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fe76  test    rcx, rcx
0x14000fe79  jz      short loc_14000FE87
0x14000fe7b  call    cs:__imp_ZwClose
0x14000fe82  nop     dword ptr [rax+rax+00h]
0x14000fe87  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14000fe8b  test    rcx, rcx
0x14000fe8e  jz      short loc_14000FE9C
0x14000fe90  call    cs:__imp_ZwClose
0x14000fe97  nop     dword ptr [rax+rax+00h]
0x14000fe9c  mov     eax, ebx
0x14000fe9e  mov     rcx, [rbp+57h+var_20]
0x14000fea2  xor     rcx, rsp; StackCookie
0x14000fea5  call    __security_check_cookie
0x14000feaa  lea     r11, [rsp+100h+var_10]
0x14000feb2  mov     rbx, [r11+30h]
0x14000feb6  mov     rsi, [r11+38h]
0x14000feba  mov     rsp, r11
0x14000febd  pop     r14
0x14000febf  pop     rdi
0x14000fec0  pop     rbp
0x14000fec1  retn
```
