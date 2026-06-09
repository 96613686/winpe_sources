# BfsGetUserToken

- ea: `0x14000f944`
- end: `0x14000fb63`
- name: `BfsGetUserToken`
- size: `543`
- prototype: `__int64 __fastcall(void *, PVOID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000dc70`

## callees

- `0x140001008`
- `0x14000f944`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fa74`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fa74`
- `ntoskrnl!SeTokenObjectType` at `0x14000f987`
- `ntoskrnl!SeTokenObjectType` at `0x14000fa50`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f9c1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f9c1`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fa3e`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fa3e`
- `ntoskrnl!ZwSetInformationToken` at `0x14000fab4`
- `ntoskrnl!ZwSetInformationToken` at `0x14000fab4`
- `ntoskrnl!ZwClose` at `0x14000fb20`
- `ntoskrnl!ZwClose` at `0x14000fb35`
- `ntoskrnl!ZwClose` at `0x14000fb20`
- `ntoskrnl!ZwClose` at `0x14000fb35`
- `ntoskrnl!SeExports` at `0x14000fa86`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fb02`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fb02`

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
0x14000f944  mov     [rsp-8+arg_10], rbx
0x14000f949  push    rbp
0x14000f94a  push    rsi
0x14000f94b  push    rdi
0x14000f94c  lea     rbp, [rsp-47h]
0x14000f951  sub     rsp, 0F0h
0x14000f958  mov     rax, cs:__security_cookie
0x14000f95f  xor     rax, rsp
0x14000f962  mov     [rbp+57h+var_20], rax
0x14000f966  xor     eax, eax
0x14000f968  xor     esi, esi
0x14000f96a  xorps   xmm1, xmm1
0x14000f96d  mov     [rbp+57h+var_60], rax
0x14000f971  mov     [rbp+57h+var_58], eax
0x14000f974  mov     rdi, rdx
0x14000f977  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000f97b  mov     [rbp+57h+ExistingTokenHandle], rsi
0x14000f97f  mov     [rsp+100h+Handle], rax; Handle
0x14000f984  xorps   xmm0, xmm0
0x14000f987  mov     rax, cs:__imp_SeTokenObjectType
0x14000f98e  mov     r9d, 0F01FFh; DesiredAccess
0x14000f994  mov     [rsp+100h+AccessMode], sil; AccessMode
0x14000f999  xor     r8d, r8d; PassedAccessState
0x14000f99c  mov     [rbp+57h+Object], rsi
0x14000f9a0  movups  [rbp+57h+TokenInformation], xmm0
0x14000f9a4  mov     rdx, [rax]
0x14000f9a7  mov     [rsp+100h+ObjectType], rdx; ObjectType
0x14000f9ac  mov     edx, 200h; HandleAttributes
0x14000f9b1  mov     [rbp+57h+NewTokenHandle], rsi
0x14000f9b5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14000f9b9  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14000f9bd  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000f9c1  call    cs:__imp_ObOpenObjectByPointer
0x14000f9c8  nop     dword ptr [rax+rax+00h]
0x14000f9cd  mov     ebx, eax
0x14000f9cf  test    eax, eax
0x14000f9d1  jns     short loc_14000F9EA
0x14000f9d3  mov     ecx, cs:dword_140019000
0x14000f9d9  cmp     ecx, 3
0x14000f9dc  jbe     loc_14000FAF9
0x14000f9e2  mov     [rbp+57h+var_C0], eax
0x14000f9e5  jmp     loc_14000FAD4
0x14000f9ea  mov     ecx, 2
0x14000f9ef  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f9f6  lea     rax, [rbp+57h+var_60]
0x14000f9fa  mov     dword ptr [rbp+57h+var_60+4], ecx
0x14000f9fd  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000fa01  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fa05  lea     rax, [rbp+57h+NewTokenHandle]
0x14000fa09  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000fa0d  mov     qword ptr [rsp+100h+AccessMode], rax; NewTokenHandle
0x14000fa12  xor     r9d, r9d; EffectiveOnly
0x14000fa15  mov     dword ptr [rsp+100h+ObjectType], ecx; TokenType
0x14000fa19  mov     edx, 0F01FFh; DesiredAccess
0x14000fa1e  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000fa22  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000fa29  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14000fa2d  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rsi
0x14000fa31  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000fa38  mov     word ptr [rbp+57h+var_58], 1
0x14000fa3e  call    cs:__imp_ZwDuplicateToken
0x14000fa45  nop     dword ptr [rax+rax+00h]
0x14000fa4a  mov     ebx, eax
0x14000fa4c  test    eax, eax
0x14000fa4e  js      short loc_14000FAC6
0x14000fa50  mov     r8, cs:__imp_SeTokenObjectType
0x14000fa57  lea     rax, [rbp+57h+Object]
0x14000fa5b  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fa5f  xor     r9d, r9d; AccessMode
0x14000fa62  mov     qword ptr [rsp+100h+AccessMode], rsi; HandleInformation
0x14000fa67  mov     edx, 0F01FFh; DesiredAccess
0x14000fa6c  mov     [rsp+100h+ObjectType], rax; int
0x14000fa71  mov     r8, [r8]; ObjectType
0x14000fa74  call    cs:__imp_ObReferenceObjectByHandle
0x14000fa7b  nop     dword ptr [rax+rax+00h]
0x14000fa80  mov     ebx, eax
0x14000fa82  test    eax, eax
0x14000fa84  js      short loc_14000FAC6
0x14000fa86  mov     rax, cs:__imp_SeExports
0x14000fa8d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000fa91  mov     r9d, 10h; TokenInformationLength
0x14000fa97  mov     rcx, [rax]
0x14000fa9a  lea     edx, [r9+9]; TokenInformationClass
0x14000fa9e  mov     rax, [rcx+1E8h]
0x14000faa5  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x14000faa9  mov     qword ptr [rbp+57h+TokenInformation], rax
0x14000faad  mov     dword ptr [rbp+57h+TokenInformation+8], 60h ; '`'
0x14000fab4  call    cs:__imp_ZwSetInformationToken
0x14000fabb  nop     dword ptr [rax+rax+00h]
0x14000fac0  mov     ebx, eax
0x14000fac2  test    eax, eax
0x14000fac4  jns     short loc_14000FB10
0x14000fac6  mov     eax, cs:dword_140019000
0x14000facc  cmp     eax, 3
0x14000facf  jbe     short loc_14000FAF9
0x14000fad1  mov     [rbp+57h+var_C0], ebx
0x14000fad4  lea     rax, [rbp+57h+var_C0]
0x14000fad8  mov     [rbp+57h+var_28], 4
0x14000fae0  mov     [rbp+57h+var_30], rax
0x14000fae4  lea     rdx, byte_140016D91; int
0x14000faeb  lea     rax, [rbp+57h+var_50]
0x14000faef  mov     qword ptr [rsp+100h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000faf4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000faf9  mov     rcx, [rbp+57h+Object]; Object
0x14000fafd  test    rcx, rcx
0x14000fb00  jz      short loc_14000FB17
0x14000fb02  call    cs:__imp_ObfDereferenceObject
0x14000fb09  nop     dword ptr [rax+rax+00h]
0x14000fb0e  jmp     short loc_14000FB17
0x14000fb10  mov     rax, [rbp+57h+Object]
0x14000fb14  mov     [rdi], rax
0x14000fb17  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fb1b  test    rcx, rcx
0x14000fb1e  jz      short loc_14000FB2C
0x14000fb20  call    cs:__imp_ZwClose
0x14000fb27  nop     dword ptr [rax+rax+00h]
0x14000fb2c  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14000fb30  test    rcx, rcx
0x14000fb33  jz      short loc_14000FB41
0x14000fb35  call    cs:__imp_ZwClose
0x14000fb3c  nop     dword ptr [rax+rax+00h]
0x14000fb41  mov     eax, ebx
0x14000fb43  mov     rcx, [rbp+57h+var_20]
0x14000fb47  xor     rcx, rsp; StackCookie
0x14000fb4a  call    __security_check_cookie
0x14000fb4f  mov     rbx, [rsp+100h+arg_10]
0x14000fb57  add     rsp, 0F0h
0x14000fb5e  pop     rdi
0x14000fb5f  pop     rsi
0x14000fb60  pop     rbp
0x14000fb61  retn
```
