# BfsImpersonateUser

- ea: `0x14000fdc8`
- end: `0x140010067`
- name: `BfsImpersonateUser`
- size: `671`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400069a0`
- `0x14000a530`
- `0x14000a930`
- `0x14000e2a0`

## callees

- `0x140001008`
- `0x14000fdc8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ff09`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ff09`
- `ntoskrnl!SeTokenObjectType` at `0x14000fe1e`
- `ntoskrnl!SeTokenObjectType` at `0x14000fee8`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fe55`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fe55`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fed2`
- `ntoskrnl!ZwDuplicateToken` at `0x14000fed2`
- `ntoskrnl!ZwSetInformationToken` at `0x14000ff82`
- `ntoskrnl!ZwSetInformationToken` at `0x14000ff82`
- `ntoskrnl!PsRevertToSelf` at `0x14000ff48`
- `ntoskrnl!PsRevertToSelf` at `0x14000ff48`
- `ntoskrnl!PsImpersonateClient` at `0x14000ffaf`
- `ntoskrnl!PsImpersonateClient` at `0x14000ffaf`
- `ntoskrnl!ZwClose` at `0x14001001f`
- `ntoskrnl!ZwClose` at `0x140010034`
- `ntoskrnl!ZwClose` at `0x14001001f`
- `ntoskrnl!ZwClose` at `0x140010034`
- `ntoskrnl!SeExports` at `0x14000ff54`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fffd`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fffd`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000ff34`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000ff34`

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
0x14000fdc8  mov     [rsp-8+arg_10], rbx
0x14000fdcd  mov     [rsp-8+arg_18], rsi
0x14000fdd2  push    rbp
0x14000fdd3  push    rdi
0x14000fdd4  push    r14
0x14000fdd6  lea     rbp, [rsp-47h]
0x14000fddb  sub     rsp, 0F0h
0x14000fde2  mov     rax, cs:__security_cookie
0x14000fde9  xor     rax, rsp
0x14000fdec  mov     [rbp+57h+var_20], rax
0x14000fdf0  xor     eax, eax
0x14000fdf2  xor     r14d, r14d
0x14000fdf5  xorps   xmm1, xmm1
0x14000fdf8  mov     [rbp+57h+var_60], rax
0x14000fdfc  xorps   xmm0, xmm0
0x14000fdff  mov     [rbp+57h+var_58], eax
0x14000fe02  movups  xmmword ptr [rdx], xmm0
0x14000fe05  mov     [rdx+10h], rax
0x14000fe09  mov     rdi, rdx
0x14000fe0c  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000fe10  mov     [rbp+57h+NewTokenHandle], r14
0x14000fe14  mov     [rsp+100h+Handle], rax; Handle
0x14000fe19  mov     esi, 0F01FFh
0x14000fe1e  mov     rax, cs:__imp_SeTokenObjectType
0x14000fe25  mov     r9d, esi; DesiredAccess
0x14000fe28  mov     [rsp+100h+AccessMode], r14b; AccessMode
0x14000fe2d  xor     r8d, r8d; PassedAccessState
0x14000fe30  movups  [rbp+57h+TokenInformation], xmm0
0x14000fe34  mov     [rbp+57h+Object], r14
0x14000fe38  mov     rdx, [rax]
0x14000fe3b  mov     [rsp+100h+ObjectType], rdx; ObjectType
0x14000fe40  mov     edx, 200h; HandleAttributes
0x14000fe45  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x14000fe49  mov     [rbp+57h+ExistingTokenHandle], r14
0x14000fe4d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14000fe51  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x14000fe55  call    cs:__imp_ObOpenObjectByPointer
0x14000fe5c  nop     dword ptr [rax+rax+00h]
0x14000fe61  mov     ebx, eax
0x14000fe63  test    eax, eax
0x14000fe65  jns     short loc_14000FE7E
0x14000fe67  mov     ecx, cs:dword_140019000
0x14000fe6d  cmp     ecx, 3
0x14000fe70  jbe     loc_14000FFF4
0x14000fe76  mov     [rbp+57h+var_C0], eax
0x14000fe79  jmp     loc_14000FFCF
0x14000fe7e  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000fe82  lea     rax, [rbp+57h+var_60]
0x14000fe86  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000fe8a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fe8e  lea     rax, [rbp+57h+NewTokenHandle]
0x14000fe92  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000fe99  mov     qword ptr [rsp+100h+AccessMode], rax; NewTokenHandle
0x14000fe9e  xor     r9d, r9d; EffectiveOnly
0x14000fea1  mov     edx, esi; DesiredAccess
0x14000fea3  mov     dword ptr [rsp+100h+ObjectType], 2; TokenType
0x14000feab  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000feaf  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000feb6  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14000feba  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x14000febe  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000fec5  mov     dword ptr [rbp+57h+var_60+4], 2
0x14000fecc  mov     word ptr [rbp+57h+var_58], 1
0x14000fed2  call    cs:__imp_ZwDuplicateToken
0x14000fed9  nop     dword ptr [rax+rax+00h]
0x14000fede  mov     ebx, eax
0x14000fee0  test    eax, eax
0x14000fee2  js      loc_14000FFC1
0x14000fee8  mov     r8, cs:__imp_SeTokenObjectType
0x14000feef  lea     rax, [rbp+57h+Object]
0x14000fef3  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fef7  xor     r9d, r9d; AccessMode
0x14000fefa  mov     qword ptr [rsp+100h+AccessMode], r14; HandleInformation
0x14000feff  mov     edx, esi; DesiredAccess
0x14000ff01  mov     [rsp+100h+ObjectType], rax; Object
0x14000ff06  mov     r8, [r8]; ObjectType
0x14000ff09  call    cs:__imp_ObReferenceObjectByHandle
0x14000ff10  nop     dword ptr [rax+rax+00h]
0x14000ff15  mov     ebx, eax
0x14000ff17  test    eax, eax
0x14000ff19  js      loc_14000FFC1
0x14000ff1f  mov     rcx, gs:188h; Thread
0x14000ff28  lea     r9, [rdi+14h]; ImpersonationLevel
0x14000ff2c  lea     r8, [rdi+11h]; EffectiveOnly
0x14000ff30  lea     rdx, [rdi+10h]; CopyOnOpen
0x14000ff34  call    cs:__imp_PsReferenceImpersonationToken
0x14000ff3b  nop     dword ptr [rax+rax+00h]
0x14000ff40  mov     rsi, rax
0x14000ff43  test    rax, rax
0x14000ff46  jz      short loc_14000FF54
0x14000ff48  call    cs:__imp_PsRevertToSelf
0x14000ff4f  nop     dword ptr [rax+rax+00h]
0x14000ff54  mov     rcx, cs:__imp_SeExports
0x14000ff5b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000ff5f  mov     r9d, 10h; TokenInformationLength
0x14000ff65  mov     rdx, [rcx]
0x14000ff68  mov     rcx, [rdx+1E8h]
0x14000ff6f  lea     edx, [r9+9]; TokenInformationClass
0x14000ff73  mov     qword ptr [rbp+57h+TokenInformation], rcx
0x14000ff77  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x14000ff7b  mov     dword ptr [rbp+57h+TokenInformation+8], 60h ; '`'
0x14000ff82  call    cs:__imp_ZwSetInformationToken
0x14000ff89  nop     dword ptr [rax+rax+00h]
0x14000ff8e  mov     ebx, eax
0x14000ff90  test    eax, eax
0x14000ff92  js      short loc_14000FFC1
0x14000ff94  mov     rcx, gs:188h; Thread
0x14000ff9d  xor     r9d, r9d; EffectiveOnly
0x14000ffa0  mov     rdx, [rbp+57h+Object]; Token
0x14000ffa4  xor     r8d, r8d; CopyOnOpen
0x14000ffa7  mov     dword ptr [rsp+100h+ObjectType], 2; int
0x14000ffaf  call    cs:__imp_PsImpersonateClient
0x14000ffb6  nop     dword ptr [rax+rax+00h]
0x14000ffbb  mov     ebx, eax
0x14000ffbd  test    eax, eax
0x14000ffbf  jns     short loc_14001000B
0x14000ffc1  mov     eax, cs:dword_140019000
0x14000ffc7  cmp     eax, 3
0x14000ffca  jbe     short loc_14000FFF4
0x14000ffcc  mov     [rbp+57h+var_C0], ebx
0x14000ffcf  lea     rax, [rbp+57h+var_C0]
0x14000ffd3  mov     [rbp+57h+var_28], 4
0x14000ffdb  mov     [rbp+57h+var_30], rax
0x14000ffdf  lea     rdx, byte_140016D91; int
0x14000ffe6  lea     rax, [rbp+57h+var_50]
0x14000ffea  mov     qword ptr [rsp+100h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000ffef  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000fff4  mov     rcx, [rbp+57h+Object]; Object
0x14000fff8  test    rcx, rcx
0x14000fffb  jz      short loc_140010016
0x14000fffd  call    cs:__imp_ObfDereferenceObject
0x140010004  nop     dword ptr [rax+rax+00h]
0x140010009  jmp     short loc_140010016
0x14001000b  mov     rax, [rbp+57h+Object]
0x14001000f  mov     [rdi], rax
0x140010012  mov     [rdi+8], rsi
0x140010016  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14001001a  test    rcx, rcx
0x14001001d  jz      short loc_14001002B
0x14001001f  call    cs:__imp_ZwClose
0x140010026  nop     dword ptr [rax+rax+00h]
0x14001002b  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14001002f  test    rcx, rcx
0x140010032  jz      short loc_140010040
0x140010034  call    cs:__imp_ZwClose
0x14001003b  nop     dword ptr [rax+rax+00h]
0x140010040  mov     eax, ebx
0x140010042  mov     rcx, [rbp+57h+var_20]
0x140010046  xor     rcx, rsp; StackCookie
0x140010049  call    __security_check_cookie
0x14001004e  lea     r11, [rsp+100h+var_10]
0x140010056  mov     rbx, [r11+30h]
0x14001005a  mov     rsi, [r11+38h]
0x14001005e  mov     rsp, r11
0x140010061  pop     r14
0x140010063  pop     rdi
0x140010064  pop     rbp
0x140010065  retn
```
