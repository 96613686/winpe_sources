# BfsApplyPolicyAsUser

- ea: `0x140005138`
- end: `0x14000541b`
- name: `BfsApplyPolicyAsUser`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400055d8`

## callees

- `0x140001008`
- `0x140005138`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005286`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140005286`
- `ntoskrnl!SeTokenObjectType` at `0x140005189`
- `ntoskrnl!SeTokenObjectType` at `0x140005260`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400051cb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400051cb`
- `ntoskrnl!ZwDuplicateToken` at `0x14000524a`
- `ntoskrnl!ZwDuplicateToken` at `0x14000524a`
- `ntoskrnl!ZwSetInformationToken` at `0x1400052c7`
- `ntoskrnl!ZwSetInformationToken` at `0x1400052c7`
- `ntoskrnl!ZwClose` at `0x1400053d9`
- `ntoskrnl!ZwClose` at `0x1400053ee`
- `ntoskrnl!ZwClose` at `0x1400053d9`
- `ntoskrnl!ZwClose` at `0x1400053ee`
- `ntoskrnl!SeExports` at `0x140005298`
- `ntoskrnl!ObfDereferenceObject` at `0x14000534b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000534b`
- `ntoskrnl!ExAllocatePool2` at `0x1400052ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400052ef`
- `FLTMGR!FltReferenceFileNameInformation` at `0x1400053a7`
- `FLTMGR!FltReferenceFileNameInformation` at `0x1400053a7`

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
0x140005138  push    rbp
0x14000513a  push    rbx
0x14000513b  push    rsi
0x14000513c  push    rdi
0x14000513d  push    r12
0x14000513f  push    r14
0x140005141  push    r15
0x140005143  lea     rbp, [rsp-1Fh]
0x140005148  sub     rsp, 0F0h
0x14000514f  mov     rax, cs:__security_cookie
0x140005156  xor     rax, rsp
0x140005159  mov     [rbp+4Fh+var_40], rax
0x14000515d  mov     rdi, [rbp+4Fh+arg_20]
0x140005161  xor     eax, eax
0x140005163  mov     r10, rdx
0x140005166  mov     [rbp+4Fh+var_80], rax
0x14000516a  xor     r12d, r12d
0x14000516d  mov     [rbp+4Fh+var_78], eax
0x140005170  xorps   xmm1, xmm1
0x140005173  mov     [rsp+120h+NewTokenHandle], r12
0x140005178  lea     rax, [rbp+4Fh+ExistingTokenHandle]
0x14000517c  mov     [rsp+120h+Object], r12
0x140005181  mov     [rsp+120h+Handle], rax; Handle
0x140005186  mov     r14, r9
0x140005189  mov     rax, cs:__imp_SeTokenObjectType
0x140005190  mov     r15, r8
0x140005193  mov     rsi, rcx
0x140005196  mov     [rsp+120h+AccessMode], r12b; AccessMode
0x14000519b  xorps   xmm0, xmm0
0x14000519e  mov     [rbp+4Fh+ExistingTokenHandle], r12
0x1400051a2  mov     r9d, 0F01FFh; DesiredAccess
0x1400051a8  xor     r8d, r8d; PassedAccessState
0x1400051ab  mov     rdx, [rax]
0x1400051ae  mov     rcx, r10; Object
0x1400051b1  mov     [rsp+120h+ObjectType], rdx; ObjectType
0x1400051b6  mov     edx, 200h; HandleAttributes
0x1400051bb  movups  [rbp+4Fh+TokenInformation], xmm0
0x1400051bf  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm1
0x1400051c3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm1
0x1400051c7  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm1
0x1400051cb  call    cs:__imp_ObOpenObjectByPointer
0x1400051d2  nop     dword ptr [rax+rax+00h]
0x1400051d7  mov     ebx, eax
0x1400051d9  test    eax, eax
0x1400051db  jns     short loc_1400051F5
0x1400051dd  mov     ecx, cs:dword_140019000
0x1400051e3  cmp     ecx, 3
0x1400051e6  jbe     loc_14000533D
0x1400051ec  mov     [rsp+120h+var_E0], eax
0x1400051f0  jmp     loc_140005317
0x1400051f5  mov     ecx, 2
0x1400051fa  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140005201  lea     rax, [rbp+4Fh+var_80]
0x140005205  mov     dword ptr [rbp+4Fh+var_80+4], ecx
0x140005208  mov     [rbp+4Fh+ObjectAttributes.SecurityQualityOfService], rax
0x14000520c  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140005210  lea     rax, [rsp+120h+NewTokenHandle]
0x140005215  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r12
0x140005219  mov     qword ptr [rsp+120h+AccessMode], rax; NewTokenHandle
0x14000521e  xor     r9d, r9d; EffectiveOnly
0x140005221  mov     dword ptr [rsp+120h+ObjectType], ecx; TokenType
0x140005225  mov     edx, 0F01FFh; DesiredAccess
0x14000522a  mov     rcx, [rbp+4Fh+ExistingTokenHandle]; ExistingTokenHandle
0x14000522e  mov     [rbp+4Fh+ObjectAttributes.Attributes], 200h
0x140005235  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r12
0x140005239  mov     [rbp+4Fh+ObjectAttributes.SecurityDescriptor], r12
0x14000523d  mov     dword ptr [rbp+4Fh+var_80], 0Ch
0x140005244  mov     word ptr [rbp+4Fh+var_78], 1
0x14000524a  call    cs:__imp_ZwDuplicateToken
0x140005251  nop     dword ptr [rax+rax+00h]
0x140005256  mov     ebx, eax
0x140005258  test    eax, eax
0x14000525a  js      loc_140005308
0x140005260  mov     r8, cs:__imp_SeTokenObjectType
0x140005267  lea     rax, [rsp+120h+Object]
0x14000526c  mov     rcx, [rsp+120h+NewTokenHandle]; Handle
0x140005271  xor     r9d, r9d; AccessMode
0x140005274  mov     qword ptr [rsp+120h+AccessMode], r12; HandleInformation
0x140005279  mov     edx, 0F01FFh; DesiredAccess
0x14000527e  mov     [rsp+120h+ObjectType], rax; int
0x140005283  mov     r8, [r8]; ObjectType
0x140005286  call    cs:__imp_ObReferenceObjectByHandle
0x14000528d  nop     dword ptr [rax+rax+00h]
0x140005292  mov     ebx, eax
0x140005294  test    eax, eax
0x140005296  js      short loc_140005308
0x140005298  mov     rax, cs:__imp_SeExports
0x14000529f  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x1400052a3  mov     r9d, 10h; TokenInformationLength
0x1400052a9  mov     rcx, [rax]
0x1400052ac  lea     edx, [r9+9]; TokenInformationClass
0x1400052b0  mov     rax, [rcx+1E8h]
0x1400052b7  mov     rcx, [rsp+120h+NewTokenHandle]; TokenHandle
0x1400052bc  mov     qword ptr [rbp+4Fh+TokenInformation], rax
0x1400052c0  mov     dword ptr [rbp+4Fh+TokenInformation+8], 60h ; '`'
0x1400052c7  call    cs:__imp_ZwSetInformationToken
0x1400052ce  nop     dword ptr [rax+rax+00h]
0x1400052d3  mov     ebx, eax
0x1400052d5  test    eax, eax
0x1400052d7  js      short loc_140005308
0x1400052d9  mov     rax, [rdi]
0x1400052dc  test    rax, rax
0x1400052df  jnz     short loc_140005359
0x1400052e1  lea     edx, [rax+60h]
0x1400052e4  mov     ecx, 100h
0x1400052e9  mov     r8d, 43736642h
0x1400052ef  call    cs:__imp_ExAllocatePool2
0x1400052f6  nop     dword ptr [rax+rax+00h]
0x1400052fb  mov     [rdi], rax
0x1400052fe  test    rax, rax
0x140005301  jnz     short loc_140005359
0x140005303  mov     ebx, 0C0000017h
0x140005308  mov     eax, cs:dword_140019000
0x14000530e  cmp     eax, 3
0x140005311  jbe     short loc_14000533D
0x140005313  mov     [rsp+120h+var_E0], ebx
0x140005317  lea     rax, [rsp+120h+var_E0]
0x14000531c  mov     [rbp+4Fh+var_48], 4
0x140005324  mov     [rbp+4Fh+var_50], rax
0x140005328  lea     rdx, byte_140016D91; int
0x14000532f  lea     rax, [rbp+4Fh+var_70]
0x140005333  mov     qword ptr [rsp+120h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x140005338  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000533d  mov     rcx, [rsp+120h+Object]; Object
0x140005342  test    rcx, rcx
0x140005345  jz      loc_1400053CF
0x14000534b  call    cs:__imp_ObfDereferenceObject
0x140005352  nop     dword ptr [rax+rax+00h]
0x140005357  jmp     short loc_1400053CF
0x140005359  mov     [rax+8], r12d
0x14000535d  mov     rax, [rsi+10h]
0x140005361  mov     rcx, [rax+18h]
0x140005365  mov     rax, [rcx+8]
0x140005369  mov     rcx, [rdi]
0x14000536c  movups  xmm0, xmmword ptr [rax+20h]
0x140005370  movups  xmmword ptr [rcx+10h], xmm0
0x140005374  movups  xmm1, xmmword ptr [rax+30h]
0x140005378  movups  xmmword ptr [rcx+20h], xmm1
0x14000537c  mov     rax, [rsi+10h]
0x140005380  mov     rcx, [rax+18h]
0x140005384  mov     rax, [rsp+120h+Object]
0x140005389  mov     rdx, [rcx+8]
0x14000538d  mov     [rdx+20h], rax
0x140005391  mov     rax, [rsi+10h]
0x140005395  mov     rcx, [rax+18h]
0x140005399  mov     rax, [rcx+8]
0x14000539d  mov     rcx, r15; FileNameInformation
0x1400053a0  mov     dword ptr [rax+28h], 2
0x1400053a7  call    cs:__imp_FltReferenceFileNameInformation
0x1400053ae  nop     dword ptr [rax+rax+00h]
0x1400053b3  mov     rax, [rdi]
0x1400053b6  mov     [rax+30h], r15
0x1400053ba  lock inc dword ptr [r14+90h]
0x1400053c2  mov     rax, [rdi]
0x1400053c5  mov     [rax+40h], r14
0x1400053c9  mov     rax, [rdi]
0x1400053cc  or      dword ptr [rax], 1
0x1400053cf  mov     rcx, [rsp+120h+NewTokenHandle]; Handle
0x1400053d4  test    rcx, rcx
0x1400053d7  jz      short loc_1400053E5
0x1400053d9  call    cs:__imp_ZwClose
0x1400053e0  nop     dword ptr [rax+rax+00h]
0x1400053e5  mov     rcx, [rbp+4Fh+ExistingTokenHandle]; Handle
0x1400053e9  test    rcx, rcx
0x1400053ec  jz      short loc_1400053FA
0x1400053ee  call    cs:__imp_ZwClose
0x1400053f5  nop     dword ptr [rax+rax+00h]
0x1400053fa  mov     eax, ebx
0x1400053fc  mov     rcx, [rbp+4Fh+var_40]
0x140005400  xor     rcx, rsp; StackCookie
0x140005403  call    __security_check_cookie
0x140005408  add     rsp, 0F0h
0x14000540f  pop     r15
0x140005411  pop     r14
0x140005413  pop     r12
0x140005415  pop     rdi
0x140005416  pop     rsi
0x140005417  pop     rbx
0x140005418  pop     rbp
0x140005419  retn
```
