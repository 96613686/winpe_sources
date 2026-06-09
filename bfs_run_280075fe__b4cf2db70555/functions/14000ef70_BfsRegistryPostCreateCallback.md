# BfsRegistryPostCreateCallback

- ea: `0x14000ef70`
- end: `0x14000f16c`
- name: `BfsRegistryPostCreateCallback`
- size: `508`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400010c0`

## callees

- `0x140001008`
- `0x14000e560`
- `0x14000ef70`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14000efeb`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000efeb`
- `ntoskrnl!CmKeyObjectType` at `0x14000efd4`
- `ntoskrnl!ZwClose` at `0x14000f13a`
- `ntoskrnl!ZwClose` at `0x14000f13a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f0ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f0ab`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f102`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f102`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f125`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f0e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f125`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f03b`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f03b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f0ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f0ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f10e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f10e`

## pseudocode

```c
__int64 __fastcall BfsRegistryPostCreateCallback(__int64 a1, __int64 a2, void *a3)
{
  void *v3; // rdi
  int v4; // ebx
  __int64 v7; // r14
  NTSTATUS v8; // eax
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  void *v12; // rcx
  int ObjectType; // [rsp+20h] [rbp-39h]
  NTSTATUS v15; // [rsp+40h] [rbp-19h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp-11h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+58h] [rbp-1h] BYREF
  NTSTATUS *v19; // [rsp+78h] [rbp+1Fh]
  __int64 v20; // [rsp+80h] [rbp+27h]

  v3 = *(void **)(a2 + 32);
  v4 = 0;
  Handle = 0;
  TokenInformation = 0;
  if ( !v3 )
    return (unsigned int)v4;
  if ( *(_DWORD *)v3 )
  {
    v7 = *(_QWORD *)(a2 + 16);
    v8 = ObOpenObjectByPointer(
           *((PVOID *)v3 + 2),
           0x200u,
           0,
           *((_DWORD *)v3 + 1),
           (POBJECT_TYPE)CmKeyObjectType,
           0,
           &Handle);
    v4 = v8;
    if ( v8 < 0 )
    {
      v11 = dword_140019000;
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v15 = v8;
LABEL_13:
        v20 = 4;
        v19 = &v15;
        tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v9, v10, ObjectType, &v18);
        goto LABEL_14;
      }
      goto LABEL_14;
    }
    if ( *(_DWORD *)v3 == 1 )
    {
      **(_QWORD **)(v7 + 72) = *((_QWORD *)v3 + 2);
LABEL_18:
      v4 = -1073740541;
      *(_DWORD *)(v7 + 60) = *((_DWORD *)v3 + 1);
      *(_QWORD *)a2 = *((_QWORD *)v3 + 2);
      *(_DWORD *)(a2 + 24) = 0;
      goto LABEL_19;
    }
    if ( *(_DWORD *)v3 == 2 )
    {
      v4 = SeQueryInformationToken(a3, TokenAppContainerSid, &TokenInformation);
      if ( v4 < 0
        || (v4 = BfsAdjustRegistryKeySecurity(Handle, *(unsigned __int8 **)TokenInformation, *((_DWORD *)v3 + 2)), v4 < 0) )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v15 = v4;
          goto LABEL_13;
        }
LABEL_14:
        if ( v4 != -1073740541 )
        {
          v12 = (void *)*((_QWORD *)v3 + 2);
          if ( v12 )
            ObfDereferenceObject(v12);
        }
        goto LABEL_19;
      }
      **(_QWORD **)(v7 + 72) = *((_QWORD *)v3 + 2);
      goto LABEL_18;
    }
  }
LABEL_19:
  ExFreePoolWithTag(v3, 0);
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000ef70  mov     [rsp-8+arg_0], rbx
0x14000ef75  push    rbp
0x14000ef76  push    rsi
0x14000ef77  push    rdi
0x14000ef78  push    r14
0x14000ef7a  push    r15
0x14000ef7c  lea     rbp, [rsp-37h]
0x14000ef81  sub     rsp, 90h
0x14000ef88  mov     rax, cs:__security_cookie
0x14000ef8f  xor     rax, rsp
0x14000ef92  mov     [rbp+57h+var_28], rax
0x14000ef96  mov     rdi, [rdx+20h]
0x14000ef9a  xor     ebx, ebx
0x14000ef9c  mov     [rbp+57h+var_60], rbx
0x14000efa0  mov     r15, r8
0x14000efa3  mov     [rbp+57h+TokenInformation], rbx
0x14000efa7  mov     rsi, rdx
0x14000efaa  test    rdi, rdi
0x14000efad  jz      loc_14000F146
0x14000efb3  cmp     [rdi], ebx
0x14000efb5  jz      loc_14000F0DE
0x14000efbb  mov     r14, [rdx+10h]
0x14000efbf  lea     rax, [rbp+57h+var_60]
0x14000efc3  mov     r9d, [rdi+4]; DesiredAccess
0x14000efc7  xor     r8d, r8d; PassedAccessState
0x14000efca  mov     [rsp+0B0h+Handle], rax; Handle
0x14000efcf  mov     edx, 200h; HandleAttributes
0x14000efd4  mov     rax, cs:__imp_CmKeyObjectType
0x14000efdb  mov     [rsp+0B0h+AccessMode], bl; AccessMode
0x14000efdf  mov     rcx, [rax]
0x14000efe2  mov     [rsp+0B0h+ObjectType], rcx; int
0x14000efe7  mov     rcx, [rdi+10h]; Object
0x14000efeb  call    cs:__imp_ObOpenObjectByPointer
0x14000eff2  nop     dword ptr [rax+rax+00h]
0x14000eff7  mov     ebx, eax
0x14000eff9  test    eax, eax
0x14000effb  jns     short loc_14000F011
0x14000effd  mov     ecx, cs:dword_140019000
0x14000f003  cmp     ecx, 3
0x14000f006  jbe     loc_14000F09A
0x14000f00c  mov     [rbp+57h+var_70], eax
0x14000f00f  jmp     short loc_14000F075
0x14000f011  mov     eax, [rdi]
0x14000f013  cmp     eax, 1
0x14000f016  jnz     short loc_14000F028
0x14000f018  mov     rcx, [r14+48h]
0x14000f01c  mov     rax, [rdi+10h]
0x14000f020  mov     [rcx], rax
0x14000f023  jmp     loc_14000F0C4
0x14000f028  cmp     eax, 2
0x14000f02b  jnz     loc_14000F0DE
0x14000f031  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000f035  mov     rcx, r15; Token
0x14000f038  lea     edx, [rax+1Dh]; TokenInformationClass
0x14000f03b  call    cs:__imp_SeQueryInformationToken
0x14000f042  nop     dword ptr [rax+rax+00h]
0x14000f047  mov     ebx, eax
0x14000f049  test    eax, eax
0x14000f04b  js      short loc_14000F067
0x14000f04d  mov     rdx, [rbp+57h+TokenInformation]
0x14000f051  mov     r8d, [rdi+8]; AccessMask
0x14000f055  mov     rcx, [rbp+57h+var_60]; Handle
0x14000f059  mov     rdx, [rdx]; PSID
0x14000f05c  call    BfsAdjustRegistryKeySecurity
0x14000f061  mov     ebx, eax
0x14000f063  test    eax, eax
0x14000f065  jns     short loc_14000F0B9
0x14000f067  mov     eax, cs:dword_140019000
0x14000f06d  cmp     eax, 3
0x14000f070  jbe     short loc_14000F09A
0x14000f072  mov     [rbp+57h+var_70], ebx
0x14000f075  lea     rax, [rbp+57h+var_70]
0x14000f079  mov     [rbp+57h+var_30], 4
0x14000f081  mov     [rbp+57h+var_38], rax
0x14000f085  lea     rdx, byte_140016D91; int
0x14000f08c  lea     rax, [rbp+57h+var_58]
0x14000f090  mov     qword ptr [rsp+0B0h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000f095  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f09a  cmp     ebx, 0C0000503h
0x14000f0a0  jz      short loc_14000F0DE
0x14000f0a2  mov     rcx, [rdi+10h]; Object
0x14000f0a6  test    rcx, rcx
0x14000f0a9  jz      short loc_14000F0DE
0x14000f0ab  call    cs:__imp_ObfDereferenceObject
0x14000f0b2  nop     dword ptr [rax+rax+00h]
0x14000f0b7  jmp     short loc_14000F0DE
0x14000f0b9  mov     rdx, [r14+48h]
0x14000f0bd  mov     rax, [rdi+10h]
0x14000f0c1  mov     [rdx], rax
0x14000f0c4  mov     eax, [rdi+4]
0x14000f0c7  mov     ebx, 0C0000503h
0x14000f0cc  mov     [r14+3Ch], eax
0x14000f0d0  mov     rax, [rdi+10h]
0x14000f0d4  mov     [rsi], rax
0x14000f0d7  mov     dword ptr [rsi+18h], 0
0x14000f0de  xor     edx, edx; Tag
0x14000f0e0  mov     rcx, rdi; P
0x14000f0e3  call    cs:__imp_ExFreePoolWithTag
0x14000f0ea  nop     dword ptr [rax+rax+00h]
0x14000f0ef  call    cs:__imp_KeEnterCriticalRegion
0x14000f0f6  nop     dword ptr [rax+rax+00h]
0x14000f0fb  lea     rcx, gBfsRundownProtection; RunRef
0x14000f102  call    cs:__imp_ExReleaseRundownProtection
0x14000f109  nop     dword ptr [rax+rax+00h]
0x14000f10e  call    cs:__imp_KeLeaveCriticalRegion
0x14000f115  nop     dword ptr [rax+rax+00h]
0x14000f11a  mov     rcx, [rbp+57h+TokenInformation]; P
0x14000f11e  test    rcx, rcx
0x14000f121  jz      short loc_14000F131
0x14000f123  xor     edx, edx; Tag
0x14000f125  call    cs:__imp_ExFreePoolWithTag
0x14000f12c  nop     dword ptr [rax+rax+00h]
0x14000f131  mov     rcx, [rbp+57h+var_60]; Handle
0x14000f135  test    rcx, rcx
0x14000f138  jz      short loc_14000F146
0x14000f13a  call    cs:__imp_ZwClose
0x14000f141  nop     dword ptr [rax+rax+00h]
0x14000f146  mov     eax, ebx
0x14000f148  mov     rcx, [rbp+57h+var_28]
0x14000f14c  xor     rcx, rsp; StackCookie
0x14000f14f  call    __security_check_cookie
0x14000f154  mov     rbx, [rsp+0B0h+arg_0]
0x14000f15c  add     rsp, 90h
0x14000f163  pop     r15
0x14000f165  pop     r14
0x14000f167  pop     rdi
0x14000f168  pop     rsi
0x14000f169  pop     rbp
0x14000f16a  retn
```
