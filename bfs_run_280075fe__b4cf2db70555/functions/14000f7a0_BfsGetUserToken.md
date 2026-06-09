# BfsGetUserToken

- ea: `0x14000f7a0`
- end: `0x14000f9bf`
- name: `BfsGetUserToken`
- size: `543`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000dadc`

## callees

- `0x140001008`
- `0x14000f7a0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f8d0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f8d0`
- `ntoskrnl!SeTokenObjectType` at `0x14000f7e3`
- `ntoskrnl!SeTokenObjectType` at `0x14000f8ac`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f81d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f81d`
- `ntoskrnl!ZwDuplicateToken` at `0x14000f89a`
- `ntoskrnl!ZwDuplicateToken` at `0x14000f89a`
- `ntoskrnl!ZwSetInformationToken` at `0x14000f910`
- `ntoskrnl!ZwSetInformationToken` at `0x14000f910`
- `ntoskrnl!ZwClose` at `0x14000f97c`
- `ntoskrnl!ZwClose` at `0x14000f991`
- `ntoskrnl!ZwClose` at `0x14000f97c`
- `ntoskrnl!ZwClose` at `0x14000f991`
- `ntoskrnl!SeExports` at `0x14000f8e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f95e`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f95e`

## pseudocode

```c
__int64 __fastcall BfsGetUserToken(void *a1, PVOID *a2)
{
  NTSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  NTSTATUS v6; // ebx
  int v7; // ecx
  int ObjectType; // [rsp+20h] [rbp-89h]
  NTSTATUS v10; // [rsp+40h] [rbp-69h] BYREF
  void *NewTokenHandle; // [rsp+48h] [rbp-61h] BYREF
  PVOID Object; // [rsp+50h] [rbp-59h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-51h] BYREF
  __int128 TokenInformation; // [rsp+60h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-9h] BYREF
  int v17; // [rsp+A8h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+B0h] [rbp+7h] BYREF
  NTSTATUS *v19; // [rsp+D0h] [rbp+27h]
  __int64 v20; // [rsp+D8h] [rbp+2Fh]

  v16 = 0;
  v17 = 0;
  ExistingTokenHandle = 0;
  Object = 0;
  TokenInformation = 0;
  NewTokenHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &ExistingTokenHandle);
  v6 = v3;
  if ( v3 < 0 )
  {
    v7 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_10;
    v10 = v3;
    goto LABEL_9;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = &v16;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.SecurityDescriptor = 0;
  v16 = 0x20000000CLL;
  LOWORD(v17) = 1;
  v6 = ZwDuplicateToken(ExistingTokenHandle, 0xF01FFu, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle);
  if ( v6 >= 0 )
  {
    v6 = ObReferenceObjectByHandle(NewTokenHandle, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &Object, 0);
    if ( v6 >= 0 )
    {
      *(_QWORD *)&TokenInformation = SeExports->SeMediumMandatorySid;
      DWORD2(TokenInformation) = 96;
      v6 = ZwSetInformationToken(NewTokenHandle, TokenIntegrityLevel, &TokenInformation, 0x10u);
      if ( v6 >= 0 )
      {
        *a2 = Object;
        goto LABEL_13;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v10 = v6;
LABEL_9:
    v20 = 4;
    v19 = &v10;
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, ObjectType, &v18);
  }
LABEL_10:
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_13:
  if ( NewTokenHandle )
    ZwClose(NewTokenHandle);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000f7a0  mov     [rsp-8+arg_10], rbx
0x14000f7a5  push    rbp
0x14000f7a6  push    rsi
0x14000f7a7  push    rdi
0x14000f7a8  lea     rbp, [rsp-47h]
0x14000f7ad  sub     rsp, 0F0h
0x14000f7b4  mov     rax, cs:__security_cookie
0x14000f7bb  xor     rax, rsp
0x14000f7be  mov     [rbp+57h+var_20], rax
0x14000f7c2  xor     eax, eax
0x14000f7c4  xor     esi, esi
0x14000f7c6  xorps   xmm1, xmm1
0x14000f7c9  mov     [rbp+57h+var_60], rax
0x14000f7cd  mov     [rbp+57h+var_58], eax
0x14000f7d0  mov     rdi, rdx
0x14000f7d3  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000f7d7  mov     [rbp+57h+ExistingTokenHandle], rsi
0x14000f7db  mov     [rsp+100h+Handle], rax; Handle
0x14000f7e0  xorps   xmm0, xmm0
0x14000f7e3  mov     rax, cs:__imp_SeTokenObjectType
0x14000f7ea  mov     r9d, 0F01FFh; DesiredAccess
0x14000f7f0  mov     [rsp+100h+AccessMode], sil; AccessMode
0x14000f7f5  xor     r8d, r8d; PassedAccessState
0x14000f7f8  mov     [rbp+57h+Object], rsi
0x14000f7fc  movups  [rbp+57h+TokenInformation], xmm0
0x14000f800  mov     rdx, [rax]
0x14000f803  mov     [rsp+100h+ObjectType], rdx; ObjectType
0x14000f808  mov     edx, 200h; HandleAttributes
0x14000f80d  mov     [rbp+57h+NewTokenHandle], rsi
0x14000f811  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14000f815  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14000f819  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000f81d  call    cs:__imp_ObOpenObjectByPointer
0x14000f824  nop     dword ptr [rax+rax+00h]
0x14000f829  mov     ebx, eax
0x14000f82b  test    eax, eax
0x14000f82d  jns     short loc_14000F846
0x14000f82f  mov     ecx, cs:dword_140019000
0x14000f835  cmp     ecx, 3
0x14000f838  jbe     loc_14000F955
0x14000f83e  mov     [rbp+57h+var_C0], eax
0x14000f841  jmp     loc_14000F930
0x14000f846  mov     ecx, 2
0x14000f84b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f852  lea     rax, [rbp+57h+var_60]
0x14000f856  mov     dword ptr [rbp+57h+var_60+4], ecx
0x14000f859  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000f85d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f861  lea     rax, [rbp+57h+NewTokenHandle]
0x14000f865  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000f869  mov     qword ptr [rsp+100h+AccessMode], rax; NewTokenHandle
0x14000f86e  xor     r9d, r9d; EffectiveOnly
0x14000f871  mov     dword ptr [rsp+100h+ObjectType], ecx; TokenType
0x14000f875  mov     edx, 0F01FFh; DesiredAccess
0x14000f87a  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000f87e  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000f885  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14000f889  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rsi
0x14000f88d  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000f894  mov     word ptr [rbp+57h+var_58], 1
0x14000f89a  call    cs:__imp_ZwDuplicateToken
0x14000f8a1  nop     dword ptr [rax+rax+00h]
0x14000f8a6  mov     ebx, eax
0x14000f8a8  test    eax, eax
0x14000f8aa  js      short loc_14000F922
0x14000f8ac  mov     r8, cs:__imp_SeTokenObjectType
0x14000f8b3  lea     rax, [rbp+57h+Object]
0x14000f8b7  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000f8bb  xor     r9d, r9d; AccessMode
0x14000f8be  mov     qword ptr [rsp+100h+AccessMode], rsi; HandleInformation
0x14000f8c3  mov     edx, 0F01FFh; DesiredAccess
0x14000f8c8  mov     [rsp+100h+ObjectType], rax; int
0x14000f8cd  mov     r8, [r8]; ObjectType
0x14000f8d0  call    cs:__imp_ObReferenceObjectByHandle
0x14000f8d7  nop     dword ptr [rax+rax+00h]
0x14000f8dc  mov     ebx, eax
0x14000f8de  test    eax, eax
0x14000f8e0  js      short loc_14000F922
0x14000f8e2  mov     rax, cs:__imp_SeExports
0x14000f8e9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000f8ed  mov     r9d, 10h; TokenInformationLength
0x14000f8f3  mov     rcx, [rax]
0x14000f8f6  lea     edx, [r9+9]; TokenInformationClass
0x14000f8fa  mov     rax, [rcx+1E8h]
0x14000f901  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x14000f905  mov     qword ptr [rbp+57h+TokenInformation], rax
0x14000f909  mov     dword ptr [rbp+57h+TokenInformation+8], 60h ; '`'
0x14000f910  call    cs:__imp_ZwSetInformationToken
0x14000f917  nop     dword ptr [rax+rax+00h]
0x14000f91c  mov     ebx, eax
0x14000f91e  test    eax, eax
0x14000f920  jns     short loc_14000F96C
0x14000f922  mov     eax, cs:dword_140019000
0x14000f928  cmp     eax, 3
0x14000f92b  jbe     short loc_14000F955
0x14000f92d  mov     [rbp+57h+var_C0], ebx
0x14000f930  lea     rax, [rbp+57h+var_C0]
0x14000f934  mov     [rbp+57h+var_28], 4
0x14000f93c  mov     [rbp+57h+var_30], rax
0x14000f940  lea     rdx, byte_140016D91; int
0x14000f947  lea     rax, [rbp+57h+var_50]
0x14000f94b  mov     qword ptr [rsp+100h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000f950  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f955  mov     rcx, [rbp+57h+Object]; Object
0x14000f959  test    rcx, rcx
0x14000f95c  jz      short loc_14000F973
0x14000f95e  call    cs:__imp_ObfDereferenceObject
0x14000f965  nop     dword ptr [rax+rax+00h]
0x14000f96a  jmp     short loc_14000F973
0x14000f96c  mov     rax, [rbp+57h+Object]
0x14000f970  mov     [rdi], rax
0x14000f973  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000f977  test    rcx, rcx
0x14000f97a  jz      short loc_14000F988
0x14000f97c  call    cs:__imp_ZwClose
0x14000f983  nop     dword ptr [rax+rax+00h]
0x14000f988  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14000f98c  test    rcx, rcx
0x14000f98f  jz      short loc_14000F99D
0x14000f991  call    cs:__imp_ZwClose
0x14000f998  nop     dword ptr [rax+rax+00h]
0x14000f99d  mov     eax, ebx
0x14000f99f  mov     rcx, [rbp+57h+var_20]
0x14000f9a3  xor     rcx, rsp; StackCookie
0x14000f9a6  call    __security_check_cookie
0x14000f9ab  mov     rbx, [rsp+100h+arg_10]
0x14000f9b3  add     rsp, 0F0h
0x14000f9ba  pop     rdi
0x14000f9bb  pop     rsi
0x14000f9bc  pop     rbp
0x14000f9bd  retn
```
