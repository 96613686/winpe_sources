# BfsRegistryPostCreateCallback

- ea: `0x14000f100`
- end: `0x14000f2fc`
- name: `BfsRegistryPostCreateCallback`
- size: `508`
- prototype: `__int64 __fastcall(__int64, __int64, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400010c0`

## callees

- `0x140001008`
- `0x14000e6f0`
- `0x14000f100`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f17b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000f17b`
- `ntoskrnl!CmKeyObjectType` at `0x14000f164`
- `ntoskrnl!ZwClose` at `0x14000f2ca`
- `ntoskrnl!ZwClose` at `0x14000f2ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f23b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f23b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f292`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f292`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f273`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f273`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f2b5`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f1cb`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f1cb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f27f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f27f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f29e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f29e`

## pseudocode

```c
__int64 __fastcall BfsRegistryPostCreateCallback(__int64 a1, __int64 a2, void *a3)
{
  void *v3; // rdi
  NTSTATUS v4; // ebx
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
      if ( v4 < 0 || (v4 = BfsAdjustRegistryKeySecurity(Handle, *(PSID *)TokenInformation, *((_DWORD *)v3 + 2)), v4 < 0) )
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
0x14000f100  mov     [rsp-8+arg_0], rbx
0x14000f105  push    rbp
0x14000f106  push    rsi
0x14000f107  push    rdi
0x14000f108  push    r14
0x14000f10a  push    r15
0x14000f10c  lea     rbp, [rsp-37h]
0x14000f111  sub     rsp, 90h
0x14000f118  mov     rax, cs:__security_cookie
0x14000f11f  xor     rax, rsp
0x14000f122  mov     [rbp+57h+var_28], rax
0x14000f126  mov     rdi, [rdx+20h]
0x14000f12a  xor     ebx, ebx
0x14000f12c  mov     [rbp+57h+var_60], rbx
0x14000f130  mov     r15, r8
0x14000f133  mov     [rbp+57h+TokenInformation], rbx
0x14000f137  mov     rsi, rdx
0x14000f13a  test    rdi, rdi
0x14000f13d  jz      loc_14000F2D6
0x14000f143  cmp     [rdi], ebx
0x14000f145  jz      loc_14000F26E
0x14000f14b  mov     r14, [rdx+10h]
0x14000f14f  lea     rax, [rbp+57h+var_60]
0x14000f153  mov     r9d, [rdi+4]; DesiredAccess
0x14000f157  xor     r8d, r8d; PassedAccessState
0x14000f15a  mov     [rsp+0B0h+Handle], rax; Handle
0x14000f15f  mov     edx, 200h; HandleAttributes
0x14000f164  mov     rax, cs:__imp_CmKeyObjectType
0x14000f16b  mov     [rsp+0B0h+AccessMode], bl; AccessMode
0x14000f16f  mov     rcx, [rax]
0x14000f172  mov     [rsp+0B0h+ObjectType], rcx; int
0x14000f177  mov     rcx, [rdi+10h]; Object
0x14000f17b  call    cs:__imp_ObOpenObjectByPointer
0x14000f182  nop     dword ptr [rax+rax+00h]
0x14000f187  mov     ebx, eax
0x14000f189  test    eax, eax
0x14000f18b  jns     short loc_14000F1A1
0x14000f18d  mov     ecx, cs:dword_140019000
0x14000f193  cmp     ecx, 3
0x14000f196  jbe     loc_14000F22A
0x14000f19c  mov     [rbp+57h+var_70], eax
0x14000f19f  jmp     short loc_14000F205
0x14000f1a1  mov     eax, [rdi]
0x14000f1a3  cmp     eax, 1
0x14000f1a6  jnz     short loc_14000F1B8
0x14000f1a8  mov     rcx, [r14+48h]
0x14000f1ac  mov     rax, [rdi+10h]
0x14000f1b0  mov     [rcx], rax
0x14000f1b3  jmp     loc_14000F254
0x14000f1b8  cmp     eax, 2
0x14000f1bb  jnz     loc_14000F26E
0x14000f1c1  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14000f1c5  mov     rcx, r15; Token
0x14000f1c8  lea     edx, [rax+1Dh]; TokenInformationClass
0x14000f1cb  call    cs:__imp_SeQueryInformationToken
0x14000f1d2  nop     dword ptr [rax+rax+00h]
0x14000f1d7  mov     ebx, eax
0x14000f1d9  test    eax, eax
0x14000f1db  js      short loc_14000F1F7
0x14000f1dd  mov     rdx, [rbp+57h+TokenInformation]
0x14000f1e1  mov     r8d, [rdi+8]; AccessMask
0x14000f1e5  mov     rcx, [rbp+57h+var_60]; Handle
0x14000f1e9  mov     rdx, [rdx]; PSID
0x14000f1ec  call    BfsAdjustRegistryKeySecurity
0x14000f1f1  mov     ebx, eax
0x14000f1f3  test    eax, eax
0x14000f1f5  jns     short loc_14000F249
0x14000f1f7  mov     eax, cs:dword_140019000
0x14000f1fd  cmp     eax, 3
0x14000f200  jbe     short loc_14000F22A
0x14000f202  mov     [rbp+57h+var_70], ebx
0x14000f205  lea     rax, [rbp+57h+var_70]
0x14000f209  mov     [rbp+57h+var_30], 4
0x14000f211  mov     [rbp+57h+var_38], rax
0x14000f215  lea     rdx, byte_140016D91; int
0x14000f21c  lea     rax, [rbp+57h+var_58]
0x14000f220  mov     qword ptr [rsp+0B0h+AccessMode], rax; PEVENT_DATA_DESCRIPTOR
0x14000f225  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f22a  cmp     ebx, 0C0000503h
0x14000f230  jz      short loc_14000F26E
0x14000f232  mov     rcx, [rdi+10h]; Object
0x14000f236  test    rcx, rcx
0x14000f239  jz      short loc_14000F26E
0x14000f23b  call    cs:__imp_ObfDereferenceObject
0x14000f242  nop     dword ptr [rax+rax+00h]
0x14000f247  jmp     short loc_14000F26E
0x14000f249  mov     rdx, [r14+48h]
0x14000f24d  mov     rax, [rdi+10h]
0x14000f251  mov     [rdx], rax
0x14000f254  mov     eax, [rdi+4]
0x14000f257  mov     ebx, 0C0000503h
0x14000f25c  mov     [r14+3Ch], eax
0x14000f260  mov     rax, [rdi+10h]
0x14000f264  mov     [rsi], rax
0x14000f267  mov     dword ptr [rsi+18h], 0
0x14000f26e  xor     edx, edx; Tag
0x14000f270  mov     rcx, rdi; P
0x14000f273  call    cs:__imp_ExFreePoolWithTag
0x14000f27a  nop     dword ptr [rax+rax+00h]
0x14000f27f  call    cs:__imp_KeEnterCriticalRegion
0x14000f286  nop     dword ptr [rax+rax+00h]
0x14000f28b  lea     rcx, gBfsRundownProtection; RunRef
0x14000f292  call    cs:__imp_ExReleaseRundownProtection
0x14000f299  nop     dword ptr [rax+rax+00h]
0x14000f29e  call    cs:__imp_KeLeaveCriticalRegion
0x14000f2a5  nop     dword ptr [rax+rax+00h]
0x14000f2aa  mov     rcx, [rbp+57h+TokenInformation]; P
0x14000f2ae  test    rcx, rcx
0x14000f2b1  jz      short loc_14000F2C1
0x14000f2b3  xor     edx, edx; Tag
0x14000f2b5  call    cs:__imp_ExFreePoolWithTag
0x14000f2bc  nop     dword ptr [rax+rax+00h]
0x14000f2c1  mov     rcx, [rbp+57h+var_60]; Handle
0x14000f2c5  test    rcx, rcx
0x14000f2c8  jz      short loc_14000F2D6
0x14000f2ca  call    cs:__imp_ZwClose
0x14000f2d1  nop     dword ptr [rax+rax+00h]
0x14000f2d6  mov     eax, ebx
0x14000f2d8  mov     rcx, [rbp+57h+var_28]
0x14000f2dc  xor     rcx, rsp; StackCookie
0x14000f2df  call    __security_check_cookie
0x14000f2e4  mov     rbx, [rsp+0B0h+arg_0]
0x14000f2ec  add     rsp, 90h
0x14000f2f3  pop     r15
0x14000f2f5  pop     r14
0x14000f2f7  pop     rdi
0x14000f2f8  pop     rsi
0x14000f2f9  pop     rbp
0x14000f2fa  retn
```
