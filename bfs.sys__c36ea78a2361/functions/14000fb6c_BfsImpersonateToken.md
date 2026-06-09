# BfsImpersonateToken

- ea: `0x14000fb6c`
- end: `0x14000fdc0`
- name: `BfsImpersonateToken`
- size: `596`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e2a0`

## callees

- `0x140001008`
- `0x14000fb6c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fca6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fca6`
- `ntoskrnl!SeTokenObjectType` at `0x14000fbc2`
- `ntoskrnl!SeTokenObjectType` at `0x14000fc85`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fbf2`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fbf2`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fc6f`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fc6f`
- `ntoskrnl!PsRevertToSelf` at `0x14000fce1`
- `ntoskrnl!PsRevertToSelf` at `0x14000fce1`
- `ntoskrnl!PsImpersonateClient` at `0x14000fd08`
- `ntoskrnl!PsImpersonateClient` at `0x14000fd08`
- `ntoskrnl!ZwClose` at `0x14000fd78`
- `ntoskrnl!ZwClose` at `0x14000fd8d`
- `ntoskrnl!ZwClose` at `0x14000fd78`
- `ntoskrnl!ZwClose` at `0x14000fd8d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fd56`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fd56`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fccd`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fccd`

## pseudocode

```c
__int64 __fastcall BfsImpersonateToken(void *a1, __int64 a2)
{
  NTSTATUS v3; // eax
  int v4; // r8d
  int v5; // r9d
  NTSTATUS v6; // ebx
  int v7; // ecx
  PACCESS_TOKEN v8; // rsi
  int ObjectType; // [rsp+20h] [rbp-79h]
  NTSTATUS v11; // [rsp+40h] [rbp-59h] BYREF
  PVOID Object; // [rsp+48h] [rbp-51h] BYREF
  void *NewTokenHandle; // [rsp+50h] [rbp-49h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-39h] BYREF
  __int64 v16; // [rsp+90h] [rbp-9h] BYREF
  int v17; // [rsp+98h] [rbp-1h]
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+A0h] [rbp+7h] BYREF
  NTSTATUS *v19; // [rsp+C0h] [rbp+27h]
  __int64 v20; // [rsp+C8h] [rbp+2Fh]

  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v16 = 0;
  v17 = 0;
  NewTokenHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Object = 0;
  ExistingTokenHandle = 0;
  v3 = ObOpenObjectByPointer(a1, 0x200u, 0, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &ExistingTokenHandle);
  v6 = v3;
  if ( v3 < 0 )
  {
    v7 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_12;
    v11 = v3;
    goto LABEL_11;
  }
  ObjectAttributes.SecurityQualityOfService = &v16;
  ObjectAttributes.Length = 48;
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
      v8 = PsReferenceImpersonationToken(
             KeGetCurrentThread(),
             (PBOOLEAN)(a2 + 16),
             (PBOOLEAN)(a2 + 17),
             (PSECURITY_IMPERSONATION_LEVEL)(a2 + 20));
      if ( v8 )
        PsRevertToSelf();
      v6 = PsImpersonateClient(KeGetCurrentThread(), Object, 0, 0, SecurityImpersonation);
      if ( v6 >= 0 )
      {
        *(_QWORD *)a2 = Object;
        *(_QWORD *)(a2 + 8) = v8;
        goto LABEL_15;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v11 = v6;
LABEL_11:
    v20 = 4;
    v19 = &v11;
    tlgWriteTransfer_EtwWriteTransfer(v7, (int)&byte_140016D91, v4, v5, ObjectType, &v18);
  }
LABEL_12:
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_15:
  if ( NewTokenHandle )
    ZwClose(NewTokenHandle);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000fb6c  mov     [rsp-8+arg_10], rbx
0x14000fb71  mov     [rsp-8+arg_18], rsi
0x14000fb76  push    rbp
0x14000fb77  push    rdi
0x14000fb78  push    r14
0x14000fb7a  lea     rbp, [rsp-47h]
0x14000fb7f  sub     rsp, 0E0h
0x14000fb86  mov     rax, cs:__security_cookie
0x14000fb8d  xor     rax, rsp
0x14000fb90  mov     [rbp+57h+var_20], rax
0x14000fb94  xor     eax, eax
0x14000fb96  xorps   xmm0, xmm0
0x14000fb99  movups  xmmword ptr [rdx], xmm0
0x14000fb9c  mov     [rdx+10h], rax
0x14000fba0  xor     r14d, r14d
0x14000fba3  mov     [rbp+57h+var_60], rax
0x14000fba7  mov     rdi, rdx
0x14000fbaa  mov     [rbp+57h+var_58], eax
0x14000fbad  mov     esi, 0F01FFh
0x14000fbb2  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000fbb6  mov     [rbp+57h+NewTokenHandle], r14
0x14000fbba  mov     [rsp+0F0h+Handle], rax; Handle
0x14000fbbf  mov     r9d, esi; DesiredAccess
0x14000fbc2  mov     rax, cs:__imp_SeTokenObjectType
0x14000fbc9  xor     r8d, r8d; PassedAccessState
0x14000fbcc  mov     [rsp+0F0h+AccessMode], r14b; AccessMode
0x14000fbd1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000fbd5  mov     [rbp+57h+Object], r14
0x14000fbd9  mov     rdx, [rax]
0x14000fbdc  mov     [rsp+0F0h+ObjectType], rdx; ObjectType
0x14000fbe1  mov     edx, 200h; HandleAttributes
0x14000fbe6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000fbea  mov     [rbp+57h+ExistingTokenHandle], r14
0x14000fbee  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000fbf2  call    cs:__imp_ObOpenObjectByPointer
0x14000fbf9  nop     dword ptr [rax+rax+00h]
0x14000fbfe  mov     ebx, eax
0x14000fc00  test    eax, eax
0x14000fc02  jns     short loc_14000FC1B
0x14000fc04  mov     ecx, cs:dword_140019000
0x14000fc0a  cmp     ecx, 3
0x14000fc0d  jbe     loc_14000FD4D
0x14000fc13  mov     [rbp+57h+var_B0], eax
0x14000fc16  jmp     loc_14000FD28
0x14000fc1b  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000fc1f  lea     rax, [rbp+57h+var_60]
0x14000fc23  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000fc27  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fc2b  lea     rax, [rbp+57h+NewTokenHandle]
0x14000fc2f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000fc36  mov     qword ptr [rsp+0F0h+AccessMode], rax; NewTokenHandle
0x14000fc3b  xor     r9d, r9d; EffectiveOnly
0x14000fc3e  mov     edx, esi; DesiredAccess
0x14000fc40  mov     dword ptr [rsp+0F0h+ObjectType], 2; TokenType
0x14000fc48  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000fc4c  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000fc53  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14000fc57  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x14000fc5b  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000fc62  mov     dword ptr [rbp+57h+var_60+4], 2
0x14000fc69  mov     word ptr [rbp+57h+var_58], 1
0x14000fc6f  call    cs:__imp_ZwDuplicateToken
0x14000fc76  nop     dword ptr [rax+rax+00h]
0x14000fc7b  mov     ebx, eax
0x14000fc7d  test    eax, eax
0x14000fc7f  js      loc_14000FD1A
0x14000fc85  mov     r8, cs:__imp_SeTokenObjectType
0x14000fc8c  lea     rax, [rbp+57h+Object]
0x14000fc90  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fc94  xor     r9d, r9d; AccessMode
0x14000fc97  mov     qword ptr [rsp+0F0h+AccessMode], r14; HandleInformation
0x14000fc9c  mov     edx, esi; DesiredAccess
0x14000fc9e  mov     [rsp+0F0h+ObjectType], rax; Object
0x14000fca3  mov     r8, [r8]; ObjectType
0x14000fca6  call    cs:__imp_ObReferenceObjectByHandle
0x14000fcad  nop     dword ptr [rax+rax+00h]
0x14000fcb2  mov     ebx, eax
0x14000fcb4  test    eax, eax
0x14000fcb6  js      short loc_14000FD1A
0x14000fcb8  mov     rcx, gs:188h; Thread
0x14000fcc1  lea     r9, [rdi+14h]; ImpersonationLevel
0x14000fcc5  lea     r8, [rdi+11h]; EffectiveOnly
0x14000fcc9  lea     rdx, [rdi+10h]; CopyOnOpen
0x14000fccd  call    cs:__imp_PsReferenceImpersonationToken
0x14000fcd4  nop     dword ptr [rax+rax+00h]
0x14000fcd9  mov     rsi, rax
0x14000fcdc  test    rax, rax
0x14000fcdf  jz      short loc_14000FCED
0x14000fce1  call    cs:__imp_PsRevertToSelf
0x14000fce8  nop     dword ptr [rax+rax+00h]
0x14000fced  mov     rcx, gs:188h; Thread
0x14000fcf6  xor     r9d, r9d; EffectiveOnly
0x14000fcf9  mov     rdx, [rbp+57h+Object]; Token
0x14000fcfd  xor     r8d, r8d; CopyOnOpen
0x14000fd00  mov     dword ptr [rsp+0F0h+ObjectType], 2; int
0x14000fd08  call    cs:__imp_PsImpersonateClient
0x14000fd0f  nop     dword ptr [rax+rax+00h]
0x14000fd14  mov     ebx, eax
0x14000fd16  test    eax, eax
0x14000fd18  jns     short loc_14000FD64
0x14000fd1a  mov     eax, cs:dword_140019000
0x14000fd20  cmp     eax, 3
0x14000fd23  jbe     short loc_14000FD4D
0x14000fd25  mov     [rbp+57h+var_B0], ebx
0x14000fd28  lea     rax, [rbp+57h+var_B0]
0x14000fd2c  mov     [rbp+57h+var_28], 4
0x14000fd34  mov     [rbp+57h+var_30], rax
0x14000fd38  lea     rdx, byte_140016D91; int
0x14000fd3f  lea     rax, [rbp+57h+var_50]
0x14000fd43  mov     qword ptr [rsp+0F0h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000fd48  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000fd4d  mov     rcx, [rbp+57h+Object]; Object
0x14000fd51  test    rcx, rcx
0x14000fd54  jz      short loc_14000FD6F
0x14000fd56  call    cs:__imp_ObfDereferenceObject
0x14000fd5d  nop     dword ptr [rax+rax+00h]
0x14000fd62  jmp     short loc_14000FD6F
0x14000fd64  mov     rax, [rbp+57h+Object]
0x14000fd68  mov     [rdi], rax
0x14000fd6b  mov     [rdi+8], rsi
0x14000fd6f  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fd73  test    rcx, rcx
0x14000fd76  jz      short loc_14000FD84
0x14000fd78  call    cs:__imp_ZwClose
0x14000fd7f  nop     dword ptr [rax+rax+00h]
0x14000fd84  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14000fd88  test    rcx, rcx
0x14000fd8b  jz      short loc_14000FD99
0x14000fd8d  call    cs:__imp_ZwClose
0x14000fd94  nop     dword ptr [rax+rax+00h]
0x14000fd99  mov     eax, ebx
0x14000fd9b  mov     rcx, [rbp+57h+var_20]
0x14000fd9f  xor     rcx, rsp; StackCookie
0x14000fda2  call    __security_check_cookie
0x14000fda7  lea     r11, [rsp+0F0h+var_10]
0x14000fdaf  mov     rbx, [r11+30h]
0x14000fdb3  mov     rsi, [r11+38h]
0x14000fdb7  mov     rsp, r11
0x14000fdba  pop     r14
0x14000fdbc  pop     rdi
0x14000fdbd  pop     rbp
0x14000fdbe  retn
```
