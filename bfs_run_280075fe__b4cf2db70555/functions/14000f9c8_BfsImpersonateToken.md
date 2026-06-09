# BfsImpersonateToken

- ea: `0x14000f9c8`
- end: `0x14000fc1c`
- name: `BfsImpersonateToken`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e110`

## callees

- `0x140001008`
- `0x14000f9c8`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fb02`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000fb02`
- `ntoskrnl!SeTokenObjectType` at `0x14000fa1e`
- `ntoskrnl!SeTokenObjectType` at `0x14000fae1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fa4e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000fa4e`
- `ntoskrnl!ZwDuplicateToken` at `0x14000facb`
- `ntoskrnl!ZwDuplicateToken` at `0x14000facb`
- `ntoskrnl!PsRevertToSelf` at `0x14000fb3d`
- `ntoskrnl!PsRevertToSelf` at `0x14000fb3d`
- `ntoskrnl!PsImpersonateClient` at `0x14000fb64`
- `ntoskrnl!PsImpersonateClient` at `0x14000fb64`
- `ntoskrnl!ZwClose` at `0x14000fbd4`
- `ntoskrnl!ZwClose` at `0x14000fbe9`
- `ntoskrnl!ZwClose` at `0x14000fbd4`
- `ntoskrnl!ZwClose` at `0x14000fbe9`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fbb2`
- `ntoskrnl!ObfDereferenceObject` at `0x14000fbb2`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fb29`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000fb29`

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
0x14000f9c8  mov     [rsp-8+arg_10], rbx
0x14000f9cd  mov     [rsp-8+arg_18], rsi
0x14000f9d2  push    rbp
0x14000f9d3  push    rdi
0x14000f9d4  push    r14
0x14000f9d6  lea     rbp, [rsp-47h]
0x14000f9db  sub     rsp, 0E0h
0x14000f9e2  mov     rax, cs:__security_cookie
0x14000f9e9  xor     rax, rsp
0x14000f9ec  mov     [rbp+57h+var_20], rax
0x14000f9f0  xor     eax, eax
0x14000f9f2  xorps   xmm0, xmm0
0x14000f9f5  movups  xmmword ptr [rdx], xmm0
0x14000f9f8  mov     [rdx+10h], rax
0x14000f9fc  xor     r14d, r14d
0x14000f9ff  mov     [rbp+57h+var_60], rax
0x14000fa03  mov     rdi, rdx
0x14000fa06  mov     [rbp+57h+var_58], eax
0x14000fa09  mov     esi, 0F01FFh
0x14000fa0e  lea     rax, [rbp+57h+ExistingTokenHandle]
0x14000fa12  mov     [rbp+57h+NewTokenHandle], r14
0x14000fa16  mov     [rsp+0F0h+Handle], rax; Handle
0x14000fa1b  mov     r9d, esi; DesiredAccess
0x14000fa1e  mov     rax, cs:__imp_SeTokenObjectType
0x14000fa25  xor     r8d, r8d; PassedAccessState
0x14000fa28  mov     [rsp+0F0h+AccessMode], r14b; AccessMode
0x14000fa2d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000fa31  mov     [rbp+57h+Object], r14
0x14000fa35  mov     rdx, [rax]
0x14000fa38  mov     [rsp+0F0h+ObjectType], rdx; ObjectType
0x14000fa3d  mov     edx, 200h; HandleAttributes
0x14000fa42  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000fa46  mov     [rbp+57h+ExistingTokenHandle], r14
0x14000fa4a  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000fa4e  call    cs:__imp_ObOpenObjectByPointer
0x14000fa55  nop     dword ptr [rax+rax+00h]
0x14000fa5a  mov     ebx, eax
0x14000fa5c  test    eax, eax
0x14000fa5e  jns     short loc_14000FA77
0x14000fa60  mov     ecx, cs:dword_140019000
0x14000fa66  cmp     ecx, 3
0x14000fa69  jbe     loc_14000FBA9
0x14000fa6f  mov     [rbp+57h+var_B0], eax
0x14000fa72  jmp     loc_14000FB84
0x14000fa77  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x14000fa7b  lea     rax, [rbp+57h+var_60]
0x14000fa7f  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x14000fa83  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000fa87  lea     rax, [rbp+57h+NewTokenHandle]
0x14000fa8b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000fa92  mov     qword ptr [rsp+0F0h+AccessMode], rax; NewTokenHandle
0x14000fa97  xor     r9d, r9d; EffectiveOnly
0x14000fa9a  mov     edx, esi; DesiredAccess
0x14000fa9c  mov     dword ptr [rsp+0F0h+ObjectType], 2; TokenType
0x14000faa4  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x14000faa8  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000faaf  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x14000fab3  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x14000fab7  mov     dword ptr [rbp+57h+var_60], 0Ch
0x14000fabe  mov     dword ptr [rbp+57h+var_60+4], 2
0x14000fac5  mov     word ptr [rbp+57h+var_58], 1
0x14000facb  call    cs:__imp_ZwDuplicateToken
0x14000fad2  nop     dword ptr [rax+rax+00h]
0x14000fad7  mov     ebx, eax
0x14000fad9  test    eax, eax
0x14000fadb  js      loc_14000FB76
0x14000fae1  mov     r8, cs:__imp_SeTokenObjectType
0x14000fae8  lea     rax, [rbp+57h+Object]
0x14000faec  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000faf0  xor     r9d, r9d; AccessMode
0x14000faf3  mov     qword ptr [rsp+0F0h+AccessMode], r14; HandleInformation
0x14000faf8  mov     edx, esi; DesiredAccess
0x14000fafa  mov     [rsp+0F0h+ObjectType], rax; Object
0x14000faff  mov     r8, [r8]; ObjectType
0x14000fb02  call    cs:__imp_ObReferenceObjectByHandle
0x14000fb09  nop     dword ptr [rax+rax+00h]
0x14000fb0e  mov     ebx, eax
0x14000fb10  test    eax, eax
0x14000fb12  js      short loc_14000FB76
0x14000fb14  mov     rcx, gs:188h; Thread
0x14000fb1d  lea     r9, [rdi+14h]; ImpersonationLevel
0x14000fb21  lea     r8, [rdi+11h]; EffectiveOnly
0x14000fb25  lea     rdx, [rdi+10h]; CopyOnOpen
0x14000fb29  call    cs:__imp_PsReferenceImpersonationToken
0x14000fb30  nop     dword ptr [rax+rax+00h]
0x14000fb35  mov     rsi, rax
0x14000fb38  test    rax, rax
0x14000fb3b  jz      short loc_14000FB49
0x14000fb3d  call    cs:__imp_PsRevertToSelf
0x14000fb44  nop     dword ptr [rax+rax+00h]
0x14000fb49  mov     rcx, gs:188h; Thread
0x14000fb52  xor     r9d, r9d; EffectiveOnly
0x14000fb55  mov     rdx, [rbp+57h+Object]; Token
0x14000fb59  xor     r8d, r8d; CopyOnOpen
0x14000fb5c  mov     dword ptr [rsp+0F0h+ObjectType], 2; int
0x14000fb64  call    cs:__imp_PsImpersonateClient
0x14000fb6b  nop     dword ptr [rax+rax+00h]
0x14000fb70  mov     ebx, eax
0x14000fb72  test    eax, eax
0x14000fb74  jns     short loc_14000FBC0
0x14000fb76  mov     eax, cs:dword_140019000
0x14000fb7c  cmp     eax, 3
0x14000fb7f  jbe     short loc_14000FBA9
0x14000fb81  mov     [rbp+57h+var_B0], ebx
0x14000fb84  lea     rax, [rbp+57h+var_B0]
0x14000fb88  mov     [rbp+57h+var_28], 4
0x14000fb90  mov     [rbp+57h+var_30], rax
0x14000fb94  lea     rdx, byte_140016D91; int
0x14000fb9b  lea     rax, [rbp+57h+var_50]
0x14000fb9f  mov     qword ptr [rsp+0F0h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000fba4  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000fba9  mov     rcx, [rbp+57h+Object]; Object
0x14000fbad  test    rcx, rcx
0x14000fbb0  jz      short loc_14000FBCB
0x14000fbb2  call    cs:__imp_ObfDereferenceObject
0x14000fbb9  nop     dword ptr [rax+rax+00h]
0x14000fbbe  jmp     short loc_14000FBCB
0x14000fbc0  mov     rax, [rbp+57h+Object]
0x14000fbc4  mov     [rdi], rax
0x14000fbc7  mov     [rdi+8], rsi
0x14000fbcb  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14000fbcf  test    rcx, rcx
0x14000fbd2  jz      short loc_14000FBE0
0x14000fbd4  call    cs:__imp_ZwClose
0x14000fbdb  nop     dword ptr [rax+rax+00h]
0x14000fbe0  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x14000fbe4  test    rcx, rcx
0x14000fbe7  jz      short loc_14000FBF5
0x14000fbe9  call    cs:__imp_ZwClose
0x14000fbf0  nop     dword ptr [rax+rax+00h]
0x14000fbf5  mov     eax, ebx
0x14000fbf7  mov     rcx, [rbp+57h+var_20]
0x14000fbfb  xor     rcx, rsp; StackCookie
0x14000fbfe  call    __security_check_cookie
0x14000fc03  lea     r11, [rsp+0F0h+var_10]
0x14000fc0b  mov     rbx, [r11+30h]
0x14000fc0f  mov     rsi, [r11+38h]
0x14000fc13  mov     rsp, r11
0x14000fc16  pop     r14
0x14000fc18  pop     rdi
0x14000fc19  pop     rbp
0x14000fc1a  retn
```
