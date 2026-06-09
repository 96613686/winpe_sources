# BfsApplyPolicyAsUser

- ea: `0x1400052c8`
- end: `0x1400055ab`
- name: `BfsApplyPolicyAsUser`
- size: `739`
- prototype: `__int64 __fastcall(__int64, void *, struct _FLT_FILE_NAME_INFORMATION *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140005768`

## callees

- `0x140001008`
- `0x1400052c8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005416`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005416`
- `ntoskrnl!SeTokenObjectType` at `0x140005319`
- `ntoskrnl!SeTokenObjectType` at `0x1400053f0`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000535b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000535b`
- `ntoskrnl!ZwDuplicateToken` at `0x1400053da`
- `ntoskrnl!ZwDuplicateToken` at `0x1400053da`
- `ntoskrnl!ZwSetInformationToken` at `0x140005457`
- `ntoskrnl!ZwSetInformationToken` at `0x140005457`
- `ntoskrnl!ZwClose` at `0x140005569`
- `ntoskrnl!ZwClose` at `0x14000557e`
- `ntoskrnl!ZwClose` at `0x140005569`
- `ntoskrnl!ZwClose` at `0x14000557e`
- `ntoskrnl!SeExports` at `0x140005428`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054db`
- `ntoskrnl!ObfDereferenceObject` at `0x1400054db`
- `ntoskrnl!ExAllocatePool2` at `0x14000547f`
- `ntoskrnl!ExAllocatePool2` at `0x14000547f`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005537`
- `FLTMGR!FltReferenceFileNameInformation` at `0x140005537`

## pseudocode

```c
__int64 __fastcall BfsApplyPolicyAsUser(
        __int64 a1,
        void *a2,
        struct _FLT_FILE_NAME_INFORMATION *a3,
        __int64 a4,
        __int64 *a5)
{
  NTSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
  NTSTATUS v11; // ebx
  int v12; // ecx
  __int64 Pool2; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  int ObjectType; // [rsp+20h] [rbp-B1h]
  NTSTATUS v18; // [rsp+40h] [rbp-91h] BYREF
  void *NewTokenHandle; // [rsp+48h] [rbp-89h] BYREF
  PVOID Object; // [rsp+50h] [rbp-81h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-79h] BYREF
  __int128 TokenInformation; // [rsp+60h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-61h] BYREF
  __int64 v24; // [rsp+A0h] [rbp-31h] BYREF
  int v25; // [rsp+A8h] [rbp-29h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+B0h] [rbp-21h] BYREF
  NTSTATUS *v27; // [rsp+D0h] [rbp-1h]
  __int64 v28; // [rsp+D8h] [rbp+7h]

  v24 = 0;
  v25 = 0;
  NewTokenHandle = 0;
  Object = 0;
  ExistingTokenHandle = 0;
  TokenInformation = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v8 = ObOpenObjectByPointer(a2, 0x200u, 0, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &ExistingTokenHandle);
  v11 = v8;
  if ( v8 < 0 )
  {
    v12 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_13;
    v18 = v8;
    goto LABEL_12;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = &v24;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  ObjectAttributes.SecurityDescriptor = 0;
  v24 = 0x20000000CLL;
  LOWORD(v25) = 1;
  v11 = ZwDuplicateToken(ExistingTokenHandle, 0xF01FFu, &ObjectAttributes, 0, TokenImpersonation, &NewTokenHandle);
  if ( v11 >= 0 )
  {
    v11 = ObReferenceObjectByHandle(NewTokenHandle, 0xF01FFu, (POBJECT_TYPE)SeTokenObjectType, 0, &Object, 0);
    if ( v11 >= 0 )
    {
      *(_QWORD *)&TokenInformation = SeExports->SeMediumMandatorySid;
      DWORD2(TokenInformation) = 96;
      v11 = ZwSetInformationToken(NewTokenHandle, TokenIntegrityLevel, &TokenInformation, 0x10u);
      if ( v11 >= 0 )
      {
        Pool2 = *a5;
        if ( *a5 || (Pool2 = ExAllocatePool2(256, 96, 1131636290), (*a5 = Pool2) != 0) )
        {
          *(_DWORD *)(Pool2 + 8) = 0;
          v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 8LL);
          v15 = *a5;
          *(_OWORD *)(v15 + 16) = *(_OWORD *)(v14 + 32);
          *(_OWORD *)(v15 + 32) = *(_OWORD *)(v14 + 48);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 8LL) + 32LL) = Object;
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 24LL) + 8LL) + 40LL) = 2;
          FltReferenceFileNameInformation(a3);
          *(_QWORD *)(*a5 + 48) = a3;
          _InterlockedIncrement((volatile signed __int32 *)(a4 + 144));
          *(_QWORD *)(*a5 + 64) = a4;
          *(_DWORD *)*a5 |= 1u;
          goto LABEL_16;
        }
        v11 = -1073741801;
      }
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v18 = v11;
LABEL_12:
    v28 = 4;
    v27 = &v18;
    tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v9, v10, ObjectType, &v26);
  }
LABEL_13:
  if ( Object )
    ObfDereferenceObject(Object);
LABEL_16:
  if ( NewTokenHandle )
    ZwClose(NewTokenHandle);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400052c8  push    rbp
0x1400052ca  push    rbx
0x1400052cb  push    rsi
0x1400052cc  push    rdi
0x1400052cd  push    r12
0x1400052cf  push    r14
0x1400052d1  push    r15
0x1400052d3  lea     rbp, [rsp-1Fh]
0x1400052d8  sub     rsp, 0F0h
0x1400052df  mov     rax, cs:__security_cookie
0x1400052e6  xor     rax, rsp
0x1400052e9  mov     [rbp+4Fh+var_40], rax
0x1400052ed  mov     rdi, [rbp+4Fh+arg_20]
0x1400052f1  xor     eax, eax
0x1400052f3  mov     r10, rdx
0x1400052f6  mov     [rbp+4Fh+var_80], rax
0x1400052fa  xor     r12d, r12d
0x1400052fd  mov     [rbp+4Fh+var_78], eax
0x140005300  xorps   xmm1, xmm1
0x140005303  mov     [rsp+120h+NewTokenHandle], r12
0x140005308  lea     rax, [rbp+4Fh+ExistingTokenHandle]
0x14000530c  mov     [rsp+120h+Object], r12
0x140005311  mov     [rsp+120h+Handle], rax; Handle
0x140005316  mov     r14, r9
0x140005319  mov     rax, cs:__imp_SeTokenObjectType
0x140005320  mov     r15, r8
0x140005323  mov     rsi, rcx
0x140005326  mov     [rsp+120h+AccessMode], r12b; AccessMode
0x14000532b  xorps   xmm0, xmm0
0x14000532e  mov     [rbp+4Fh+ExistingTokenHandle], r12
0x140005332  mov     r9d, 0F01FFh; DesiredAccess
0x140005338  xor     r8d, r8d; PassedAccessState
0x14000533b  mov     rdx, [rax]
0x14000533e  mov     rcx, r10; Object
0x140005341  mov     [rsp+120h+ObjectType], rdx; ObjectType
0x140005346  mov     edx, 200h; HandleAttributes
0x14000534b  movups  [rbp+4Fh+TokenInformation], xmm0
0x14000534f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x140005353  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x140005357  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x14000535b  call    cs:__imp_ObOpenObjectByPointer
0x140005362  nop     dword ptr [rax+rax+00h]
0x140005367  mov     ebx, eax
0x140005369  test    eax, eax
0x14000536b  jns     short loc_140005385
0x14000536d  mov     ecx, cs:dword_140019000
0x140005373  cmp     ecx, 3
0x140005376  jbe     loc_1400054CD
0x14000537c  mov     [rsp+120h+var_E0], eax
0x140005380  jmp     loc_1400054A7
0x140005385  mov     ecx, 2
0x14000538a  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140005391  lea     rax, [rbp+4Fh+var_80]
0x140005395  mov     dword ptr [rbp+4Fh+var_80+4], ecx
0x140005398  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x14000539c  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400053a0  lea     rax, [rsp+120h+NewTokenHandle]
0x1400053a5  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x1400053a9  mov     qword ptr [rsp+120h+AccessMode], rax; NewTokenHandle
0x1400053ae  xor     r9d, r9d; EffectiveOnly
0x1400053b1  mov     dword ptr [rsp+120h+ObjectType], ecx; TokenType
0x1400053b5  mov     edx, 0F01FFh; DesiredAccess
0x1400053ba  mov     rcx, [rbp+4Fh+ExistingTokenHandle]; ExistingTokenHandle
0x1400053be  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x1400053c5  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x1400053c9  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], r12
0x1400053cd  mov     dword ptr [rbp+4Fh+var_80], 0Ch
0x1400053d4  mov     word ptr [rbp+4Fh+var_78], 1
0x1400053da  call    cs:__imp_ZwDuplicateToken
0x1400053e1  nop     dword ptr [rax+rax+00h]
0x1400053e6  mov     ebx, eax
0x1400053e8  test    eax, eax
0x1400053ea  js      loc_140005498
0x1400053f0  mov     r8, cs:__imp_SeTokenObjectType
0x1400053f7  lea     rax, [rsp+120h+Object]
0x1400053fc  mov     rcx, [rsp+120h+NewTokenHandle]; Handle
0x140005401  xor     r9d, r9d; AccessMode
0x140005404  mov     qword ptr [rsp+120h+AccessMode], r12; HandleInformation
0x140005409  mov     edx, 0F01FFh; DesiredAccess
0x14000540e  mov     [rsp+120h+ObjectType], rax; int
0x140005413  mov     r8, [r8]; ObjectType
0x140005416  call    cs:__imp_ObReferenceObjectByHandle
0x14000541d  nop     dword ptr [rax+rax+00h]
0x140005422  mov     ebx, eax
0x140005424  test    eax, eax
0x140005426  js      short loc_140005498
0x140005428  mov     rax, cs:__imp_SeExports
0x14000542f  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x140005433  mov     r9d, 10h; TokenInformationLength
0x140005439  mov     rcx, [rax]
0x14000543c  lea     edx, [r9+9]; TokenInformationClass
0x140005440  mov     rax, [rcx+1E8h]
0x140005447  mov     rcx, [rsp+120h+NewTokenHandle]; TokenHandle
0x14000544c  mov     qword ptr [rbp+4Fh+TokenInformation], rax
0x140005450  mov     dword ptr [rbp+4Fh+TokenInformation+8], 60h ; '`'
0x140005457  call    cs:__imp_ZwSetInformationToken
0x14000545e  nop     dword ptr [rax+rax+00h]
0x140005463  mov     ebx, eax
0x140005465  test    eax, eax
0x140005467  js      short loc_140005498
0x140005469  mov     rax, [rdi]
0x14000546c  test    rax, rax
0x14000546f  jnz     short loc_1400054E9
0x140005471  lea     edx, [rax+60h]
0x140005474  mov     ecx, 100h
0x140005479  mov     r8d, 43736642h
0x14000547f  call    cs:__imp_ExAllocatePool2
0x140005486  nop     dword ptr [rax+rax+00h]
0x14000548b  mov     [rdi], rax
0x14000548e  test    rax, rax
0x140005491  jnz     short loc_1400054E9
0x140005493  mov     ebx, 0C0000017h
0x140005498  mov     eax, cs:dword_140019000
0x14000549e  cmp     eax, 3
0x1400054a1  jbe     short loc_1400054CD
0x1400054a3  mov     [rsp+120h+var_E0], ebx
0x1400054a7  lea     rax, [rsp+120h+var_E0]
0x1400054ac  mov     [rbp+4Fh+var_48], 4
0x1400054b4  mov     [rbp+4Fh+var_50], rax
0x1400054b8  lea     rdx, byte_140016D91; int
0x1400054bf  lea     rax, [rbp+4Fh+var_70]
0x1400054c3  mov     qword ptr [rsp+120h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x1400054c8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400054cd  mov     rcx, [rsp+120h+Object]; Object
0x1400054d2  test    rcx, rcx
0x1400054d5  jz      loc_14000555F
0x1400054db  call    cs:__imp_ObfDereferenceObject
0x1400054e2  nop     dword ptr [rax+rax+00h]
0x1400054e7  jmp     short loc_14000555F
0x1400054e9  mov     [rax+8], r12d
0x1400054ed  mov     rax, [rsi+10h]
0x1400054f1  mov     rcx, [rax+18h]
0x1400054f5  mov     rax, [rcx+8]
0x1400054f9  mov     rcx, [rdi]
0x1400054fc  movups  xmm0, xmmword ptr [rax+20h]
0x140005500  movups  xmmword ptr [rcx+10h], xmm0
0x140005504  movups  xmm1, xmmword ptr [rax+30h]
0x140005508  movups  xmmword ptr [rcx+20h], xmm1
0x14000550c  mov     rax, [rsi+10h]
0x140005510  mov     rcx, [rax+18h]
0x140005514  mov     rax, [rsp+120h+Object]
0x140005519  mov     rdx, [rcx+8]
0x14000551d  mov     [rdx+20h], rax
0x140005521  mov     rax, [rsi+10h]
0x140005525  mov     rcx, [rax+18h]
0x140005529  mov     rax, [rcx+8]
0x14000552d  mov     rcx, r15; FileNameInformation
0x140005530  mov     dword ptr [rax+28h], 2
0x140005537  call    cs:__imp_FltReferenceFileNameInformation
0x14000553e  nop     dword ptr [rax+rax+00h]
0x140005543  mov     rax, [rdi]
0x140005546  mov     [rax+30h], r15
0x14000554a  lock inc dword ptr [r14+90h]
0x140005552  mov     rax, [rdi]
0x140005555  mov     [rax+40h], r14
0x140005559  mov     rax, [rdi]
0x14000555c  or      dword ptr [rax], 1
0x14000555f  mov     rcx, [rsp+120h+NewTokenHandle]; Handle
0x140005564  test    rcx, rcx
0x140005567  jz      short loc_140005575
0x140005569  call    cs:__imp_ZwClose
0x140005570  nop     dword ptr [rax+rax+00h]
0x140005575  mov     rcx, [rbp+4Fh+ExistingTokenHandle]; Handle
0x140005579  test    rcx, rcx
0x14000557c  jz      short loc_14000558A
0x14000557e  call    cs:__imp_ZwClose
0x140005585  nop     dword ptr [rax+rax+00h]
0x14000558a  mov     eax, ebx
0x14000558c  mov     rcx, [rbp+4Fh+var_40]
0x140005590  xor     rcx, rsp; StackCookie
0x140005593  call    __security_check_cookie
0x140005598  add     rsp, 0F0h
0x14000559f  pop     r15
0x1400055a1  pop     r14
0x1400055a3  pop     r12
0x1400055a5  pop     rdi
0x1400055a6  pop     rsi
0x1400055a7  pop     rbx
0x1400055a8  pop     rbp
0x1400055a9  retn
```
