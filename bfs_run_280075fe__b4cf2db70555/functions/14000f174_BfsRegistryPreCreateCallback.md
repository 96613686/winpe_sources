# BfsRegistryPreCreateCallback

- ea: `0x14000f174`
- end: `0x14000f5c3`
- name: `BfsRegistryPreCreateCallback`
- size: `1103`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400010c0`

## callees

- `0x140001008`
- `0x14000ebf4`
- `0x14000f174`
- `0x140010138`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f2b8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f2b8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f3b1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f3e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f555`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f3b1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f3e3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f555`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f24c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f24c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f28f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f364`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f3ca`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f538`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f28f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f364`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f3ca`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f538`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f1e7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f32b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f349`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f1e7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f32b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f349`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1d1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f1d1`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f57b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f57b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f5a4`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000f5a4`
- `ntoskrnl!ExAllocatePool2` at `0x14000f475`
- `ntoskrnl!ExAllocatePool2` at `0x14000f4d8`
- `ntoskrnl!ExAllocatePool2` at `0x14000f475`
- `ntoskrnl!ExAllocatePool2` at `0x14000f4d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f1fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f234`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f2a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f591`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f1fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f234`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f2a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f591`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f210`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000f210`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f21f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f29b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f370`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f3ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f561`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f5b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f21f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f29b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f370`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f3ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f561`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f5b0`

## string_xrefs

- `0x14000f1a7`: `\Registry\WC\Silo`

## pseudocode

```c
__int64 __fastcall BfsRegistryPreCreateCallback(int a1, __int64 a2, void *a3)
{
  int v6; // r15d
  PVOID *v7; // rdi
  BOOLEAN v8; // r13
  int RegistryPrefix; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // ebx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // esi
  _DWORD *v19; // rax
  bool v20; // cc
  _DWORD *Pool2; // rax
  int v22; // eax
  int v23; // ecx
  int v24; // [rsp+20h] [rbp-79h]
  int v25; // [rsp+30h] [rbp-69h] BYREF
  int v26; // [rsp+34h] [rbp-65h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-61h] BYREF
  __int128 v28; // [rsp+48h] [rbp-51h] BYREF
  PVOID Object[2]; // [rsp+58h] [rbp-41h]
  __int64 v30; // [rsp+68h] [rbp-31h]
  UNICODE_STRING String1; // [rsp+70h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+80h] [rbp-19h] BYREF
  int *v33; // [rsp+A0h] [rbp+7h]
  __int64 v34; // [rsp+A8h] [rbp+Fh]

  v30 = 0;
  v28 = 0;
  v6 = 0;
  *(_OWORD *)Object = 0;
  DestinationString = 0;
  String1 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\WC\\Silo");
  if ( !RtlPrefixUnicodeString(&DestinationString, *(PCUNICODE_STRING *)a2, 1u) )
    return 0;
  v7 = 0;
  KeEnterCriticalRegion();
  v8 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( !v8 )
    goto LABEL_44;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&gBfsPolicyTable, 0);
  v25 = 1;
  RegistryPrefix = BfsGetRegistryPrefix(a3, &DestinationString, &String1, &v25);
  v13 = RegistryPrefix;
  if ( RegistryPrefix >= 0 )
    goto LABEL_59;
  if ( RegistryPrefix == -1073741267 )
  {
    if ( v25 == 1 )
    {
      ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
      KeLeaveCriticalRegion();
    }
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&gBfsPolicyTable, 0);
    v25 = 2;
    v13 = BfsGetRegistryPrefix(a3, &DestinationString, &String1, &v25);
    if ( v13 >= 0 )
    {
LABEL_59:
      if ( !RtlPrefixUnicodeString(&DestinationString, *(PCUNICODE_STRING *)a2, 1u)
        && !RtlPrefixUnicodeString(&String1, *(PCUNICODE_STRING *)a2, 1u) )
      {
        if ( v25 == 1 )
        {
          ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
        }
        else
        {
          if ( v25 != 2 )
            return 0;
          ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
        }
        KeLeaveCriticalRegion();
        return 0;
      }
      if ( v25 == 1 )
      {
        ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
      }
      else
      {
        if ( v25 != 2 )
        {
LABEL_24:
          LODWORD(v30) = a1;
          v6 = 0;
          *(_QWORD *)&v28 = a2;
          *((_QWORD *)&v28 + 1) = a3;
          v13 = BfsQueueIoWorkItemAndWait(&v28);
          if ( v13 < 0 )
          {
            if ( (unsigned int)dword_140019000 <= 3 )
              goto LABEL_45;
            v26 = v13;
            goto LABEL_27;
          }
          v18 = HIDWORD(Object[1]);
          if ( LODWORD(Object[1]) )
          {
            if ( LODWORD(Object[1]) == HIDWORD(Object[1])
              || (*(_DWORD *)(a2 + 56) & 0x2020006) == 0
              || (HIDWORD(Object[1]) & 0x20006) == 0 )
            {
              goto LABEL_45;
            }
            Pool2 = (_DWORD *)ExAllocatePool2(256, 24, 1330669122);
            v7 = (PVOID *)Pool2;
            if ( !Pool2 )
            {
              v20 = (unsigned int)dword_140019000 <= 3;
              goto LABEL_32;
            }
            *Pool2 = 1;
            v22 = v18;
            v23 = *(_DWORD *)(a2 + 56);
            if ( (v23 & 0x2000000) == 0 )
              v22 = v18 & v23;
            *((_DWORD *)v7 + 1) = v22;
            *((_DWORD *)v7 + 2) = v18;
          }
          else
          {
            if ( !HIDWORD(Object[1]) )
              goto LABEL_45;
            v19 = (_DWORD *)ExAllocatePool2(256, (unsigned int)(LODWORD(Object[1]) + 24), 1330669122);
            v7 = (PVOID *)v19;
            if ( !v19 )
            {
              v15 = (unsigned int)dword_140019000;
              v20 = (unsigned int)dword_140019000 <= 3;
LABEL_32:
              v13 = -1073741801;
              if ( v20 )
                goto LABEL_45;
              v26 = -1073741801;
LABEL_27:
              v34 = 4;
              v33 = &v26;
              tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v16, v17, v24, &v32);
              goto LABEL_45;
            }
            *v19 = 2;
            v19[1] = v18;
            v19[2] = v18;
          }
          *((_DWORD *)v7 + 3) = *(_DWORD *)(a2 + 24);
          v7[2] = Object[0];
          *(_QWORD *)(a2 + 80) = v7;
LABEL_44:
          v13 = 0;
          goto LABEL_45;
        }
        ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
      }
      KeLeaveCriticalRegion();
      goto LABEL_24;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v26 = v13;
    v33 = &v26;
    v34 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (unsigned __int8 *)&byte_140016D91, v11, v12, v24, &v32);
  }
  v6 = v25;
LABEL_45:
  if ( v6 == 1 )
  {
    ExReleasePushLockSharedEx(&gBfsPolicyTable, 0);
  }
  else
  {
    if ( v6 != 2 )
      goto LABEL_50;
    ExReleasePushLockExclusiveEx(&gBfsPolicyTable, 0);
  }
  KeLeaveCriticalRegion();
LABEL_50:
  if ( Object[0] && !v7 )
    ObfDereferenceObject(Object[0]);
  if ( v8 )
  {
    if ( !v7 )
    {
      KeEnterCriticalRegion();
      ExReleaseRundownProtection(&gBfsRundownProtection);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000f174  mov     [rsp-8+arg_18], rbx
0x14000f179  push    rbp
0x14000f17a  push    rsi
0x14000f17b  push    rdi
0x14000f17c  push    r12
0x14000f17e  push    r13
0x14000f180  push    r14
0x14000f182  push    r15
0x14000f184  lea     rbp, [rsp-27h]
0x14000f189  sub     rsp, 0C0h
0x14000f190  mov     rax, cs:__security_cookie
0x14000f197  xor     rax, rsp
0x14000f19a  mov     [rbp+57h+var_40], rax
0x14000f19e  xorps   xmm0, xmm0
0x14000f1a1  mov     r14, rdx
0x14000f1a4  mov     r12d, ecx
0x14000f1a7  lea     rdx, aRegistryWcSilo; "\\Registry\\WC\\Silo"
0x14000f1ae  xor     eax, eax
0x14000f1b0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f1b4  xorps   xmm1, xmm1
0x14000f1b7  mov     [rbp+57h+var_88], rax
0x14000f1bb  movups  [rbp+57h+var_A8], xmm0
0x14000f1bf  mov     rsi, r8
0x14000f1c2  xor     r15d, r15d
0x14000f1c5  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14000f1c9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f1cd  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x14000f1d1  call    cs:__imp_RtlInitUnicodeString
0x14000f1d8  nop     dword ptr [rax+rax+00h]
0x14000f1dd  mov     rdx, [r14]; String2
0x14000f1e0  lea     rcx, [rbp+57h+DestinationString]; String1
0x14000f1e4  mov     r8b, 1; CaseInSensitive
0x14000f1e7  call    cs:__imp_RtlPrefixUnicodeString
0x14000f1ee  nop     dword ptr [rax+rax+00h]
0x14000f1f3  test    al, al
0x14000f1f5  jz      loc_14000F37C
0x14000f1fb  xor     edi, edi
0x14000f1fd  call    cs:__imp_KeEnterCriticalRegion
0x14000f204  nop     dword ptr [rax+rax+00h]
0x14000f209  lea     rcx, gBfsRundownProtection; RunRef
0x14000f210  call    cs:__imp_ExAcquireRundownProtection
0x14000f217  nop     dword ptr [rax+rax+00h]
0x14000f21c  mov     r13b, al
0x14000f21f  call    cs:__imp_KeLeaveCriticalRegion
0x14000f226  nop     dword ptr [rax+rax+00h]
0x14000f22b  test    r13b, r13b
0x14000f22e  jz      loc_14000F527
0x14000f234  call    cs:__imp_KeEnterCriticalRegion
0x14000f23b  nop     dword ptr [rax+rax+00h]
0x14000f240  lea     r15, gBfsPolicyTable
0x14000f247  xor     edx, edx
0x14000f249  mov     rcx, r15
0x14000f24c  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000f253  nop     dword ptr [rax+rax+00h]
0x14000f258  lea     r9, [rbp+57h+var_C0]
0x14000f25c  mov     [rbp+57h+var_C0], 1
0x14000f263  lea     r8, [rbp+57h+String1]
0x14000f267  mov     rcx, rsi; Token
0x14000f26a  lea     rdx, [rbp+57h+DestinationString]
0x14000f26e  call    BfsGetRegistryPrefix
0x14000f273  mov     ebx, eax
0x14000f275  test    eax, eax
0x14000f277  jns     loc_14000F321
0x14000f27d  cmp     eax, 0C000022Dh
0x14000f282  jnz     short loc_14000F2E5
0x14000f284  cmp     [rbp+57h+var_C0], 1
0x14000f288  jnz     short loc_14000F2A7
0x14000f28a  xor     edx, edx
0x14000f28c  mov     rcx, r15
0x14000f28f  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f296  nop     dword ptr [rax+rax+00h]
0x14000f29b  call    cs:__imp_KeLeaveCriticalRegion
0x14000f2a2  nop     dword ptr [rax+rax+00h]
0x14000f2a7  call    cs:__imp_KeEnterCriticalRegion
0x14000f2ae  nop     dword ptr [rax+rax+00h]
0x14000f2b3  xor     edx, edx
0x14000f2b5  mov     rcx, r15
0x14000f2b8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f2bf  nop     dword ptr [rax+rax+00h]
0x14000f2c4  lea     r9, [rbp+57h+var_C0]
0x14000f2c8  mov     [rbp+57h+var_C0], 2
0x14000f2cf  lea     r8, [rbp+57h+String1]
0x14000f2d3  mov     rcx, rsi; Token
0x14000f2d6  lea     rdx, [rbp+57h+DestinationString]
0x14000f2da  call    BfsGetRegistryPrefix
0x14000f2df  mov     ebx, eax
0x14000f2e1  test    eax, eax
0x14000f2e3  jns     short loc_14000F321
0x14000f2e5  mov     eax, cs:dword_140019000
0x14000f2eb  cmp     eax, 3
0x14000f2ee  jbe     short loc_14000F318
0x14000f2f0  lea     rax, [rbp+57h+var_BC]
0x14000f2f4  mov     [rbp+57h+var_BC], ebx
0x14000f2f7  mov     [rbp+57h+var_50], rax
0x14000f2fb  lea     rdx, byte_140016D91; int
0x14000f302  lea     rax, [rbp+57h+var_70]
0x14000f306  mov     [rbp+57h+var_48], 4
0x14000f30e  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000f313  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f318  mov     r15d, [rbp+57h+var_C0]
0x14000f31c  jmp     loc_14000F529
0x14000f321  mov     rdx, [r14]; String2
0x14000f324  lea     rcx, [rbp+57h+DestinationString]; String1
0x14000f328  mov     r8b, 1; CaseInSensitive
0x14000f32b  call    cs:__imp_RtlPrefixUnicodeString
0x14000f332  nop     dword ptr [rax+rax+00h]
0x14000f337  test    al, al
0x14000f339  jnz     loc_14000F3BF
0x14000f33f  mov     rdx, [r14]; String2
0x14000f342  lea     rcx, [rbp+57h+String1]; String1
0x14000f346  mov     r8b, 1; CaseInSensitive
0x14000f349  call    cs:__imp_RtlPrefixUnicodeString
0x14000f350  nop     dword ptr [rax+rax+00h]
0x14000f355  test    al, al
0x14000f357  jnz     short loc_14000F3BF
0x14000f359  cmp     [rbp+57h+var_C0], 1
0x14000f35d  jnz     short loc_14000F3A6
0x14000f35f  xor     edx, edx
0x14000f361  mov     rcx, r15
0x14000f364  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f36b  nop     dword ptr [rax+rax+00h]
0x14000f370  call    cs:__imp_KeLeaveCriticalRegion
0x14000f377  nop     dword ptr [rax+rax+00h]
0x14000f37c  xor     eax, eax
0x14000f37e  mov     rcx, [rbp+57h+var_40]
0x14000f382  xor     rcx, rsp; StackCookie
0x14000f385  call    __security_check_cookie
0x14000f38a  mov     rbx, [rsp+0F0h+arg_18]
0x14000f392  add     rsp, 0C0h
0x14000f399  pop     r15
0x14000f39b  pop     r14
0x14000f39d  pop     r13
0x14000f39f  pop     r12
0x14000f3a1  pop     rdi
0x14000f3a2  pop     rsi
0x14000f3a3  pop     rbp
0x14000f3a4  retn
0x14000f3a6  cmp     [rbp+57h+var_C0], 2
0x14000f3aa  jnz     short loc_14000F37C
0x14000f3ac  xor     edx, edx
0x14000f3ae  mov     rcx, r15
0x14000f3b1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f3b8  nop     dword ptr [rax+rax+00h]
0x14000f3bd  jmp     short loc_14000F370
0x14000f3bf  cmp     [rbp+57h+var_C0], 1
0x14000f3c3  jnz     short loc_14000F3D8
0x14000f3c5  xor     edx, edx
0x14000f3c7  mov     rcx, r15
0x14000f3ca  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f3d1  nop     dword ptr [rax+rax+00h]
0x14000f3d6  jmp     short loc_14000F3EF
0x14000f3d8  cmp     [rbp+57h+var_C0], 2
0x14000f3dc  jnz     short loc_14000F3FB
0x14000f3de  xor     edx, edx
0x14000f3e0  mov     rcx, r15
0x14000f3e3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f3ea  nop     dword ptr [rax+rax+00h]
0x14000f3ef  call    cs:__imp_KeLeaveCriticalRegion
0x14000f3f6  nop     dword ptr [rax+rax+00h]
0x14000f3fb  lea     rcx, [rbp+57h+var_A8]
0x14000f3ff  mov     dword ptr [rbp+57h+var_88], r12d
0x14000f403  xor     r15d, r15d
0x14000f406  mov     qword ptr [rbp+57h+var_A8], r14
0x14000f40a  mov     qword ptr [rbp+57h+var_A8+8], rsi
0x14000f40e  call    BfsQueueIoWorkItemAndWait
0x14000f413  mov     ebx, eax
0x14000f415  test    eax, eax
0x14000f417  jns     short loc_14000F455
0x14000f419  mov     eax, cs:dword_140019000
0x14000f41f  cmp     eax, 3
0x14000f422  jbe     loc_14000F529
0x14000f428  mov     [rbp+57h+var_BC], ebx
0x14000f42b  lea     rax, [rbp+57h+var_BC]
0x14000f42f  mov     [rbp+57h+var_48], 4
0x14000f437  mov     [rbp+57h+var_50], rax
0x14000f43b  lea     rdx, byte_140016D91; int
0x14000f442  lea     rax, [rbp+57h+var_70]
0x14000f446  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000f44b  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000f450  jmp     loc_14000F529
0x14000f455  mov     eax, dword ptr [rbp+57h+Object+8]
0x14000f458  mov     esi, dword ptr [rbp+57h+Object+0Ch]
0x14000f45b  test    eax, eax
0x14000f45d  jnz     short loc_14000F4B2
0x14000f45f  test    esi, esi
0x14000f461  jz      loc_14000F529
0x14000f467  lea     edx, [rax+18h]
0x14000f46a  mov     ecx, 100h
0x14000f46f  mov     r8d, 4F506642h
0x14000f475  call    cs:__imp_ExAllocatePool2
0x14000f47c  nop     dword ptr [rax+rax+00h]
0x14000f481  mov     rdi, rax
0x14000f484  test    rax, rax
0x14000f487  jnz     short loc_14000F4A4
0x14000f489  mov     ecx, cs:dword_140019000
0x14000f48f  cmp     ecx, 3
0x14000f492  mov     edx, 0C0000017h
0x14000f497  mov     ebx, edx
0x14000f499  jbe     loc_14000F529
0x14000f49f  mov     [rbp+57h+var_BC], edx
0x14000f4a2  jmp     short loc_14000F42B
0x14000f4a4  mov     dword ptr [rax], 2
0x14000f4aa  mov     [rax+4], esi
0x14000f4ad  mov     [rax+8], esi
0x14000f4b0  jmp     short loc_14000F514
0x14000f4b2  cmp     eax, esi
0x14000f4b4  jz      short loc_14000F529
0x14000f4b6  test    dword ptr [r14+38h], 2020006h
0x14000f4be  jz      short loc_14000F529
0x14000f4c0  test    esi, 20006h
0x14000f4c6  jz      short loc_14000F529
0x14000f4c8  mov     edx, 18h
0x14000f4cd  mov     ecx, 100h
0x14000f4d2  mov     r8d, 4F506642h
0x14000f4d8  call    cs:__imp_ExAllocatePool2
0x14000f4df  nop     dword ptr [rax+rax+00h]
0x14000f4e4  mov     rdi, rax
0x14000f4e7  test    rax, rax
0x14000f4ea  jnz     short loc_14000F4F7
0x14000f4ec  mov     eax, cs:dword_140019000
0x14000f4f2  cmp     eax, 3
0x14000f4f5  jmp     short loc_14000F492
0x14000f4f7  mov     dword ptr [rax], 1
0x14000f4fd  mov     eax, esi
0x14000f4ff  mov     edx, [r14+38h]
0x14000f503  mov     ecx, edx
0x14000f505  and     edx, esi
0x14000f507  bt      ecx, 19h
0x14000f50b  cmovnb  eax, edx
0x14000f50e  mov     [rdi+4], eax
0x14000f511  mov     [rdi+8], esi
0x14000f514  mov     eax, [r14+18h]
0x14000f518  mov     [rdi+0Ch], eax
0x14000f51b  mov     rax, [rbp+57h+Object]
0x14000f51f  mov     [rdi+10h], rax
0x14000f523  mov     [r14+50h], rdi
0x14000f527  xor     ebx, ebx
0x14000f529  cmp     r15d, 1
0x14000f52d  jnz     short loc_14000F546
0x14000f52f  xor     edx, edx
0x14000f531  lea     rcx, gBfsPolicyTable
0x14000f538  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f53f  nop     dword ptr [rax+rax+00h]
0x14000f544  jmp     short loc_14000F561
0x14000f546  cmp     r15d, 2
0x14000f54a  jnz     short loc_14000F56D
0x14000f54c  xor     edx, edx
0x14000f54e  lea     rcx, gBfsPolicyTable
0x14000f555  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f55c  nop     dword ptr [rax+rax+00h]
0x14000f561  call    cs:__imp_KeLeaveCriticalRegion
0x14000f568  nop     dword ptr [rax+rax+00h]
0x14000f56d  mov     rcx, [rbp+57h+Object]; Object
0x14000f571  test    rcx, rcx
0x14000f574  jz      short loc_14000F587
0x14000f576  test    rdi, rdi
0x14000f579  jnz     short loc_14000F587
0x14000f57b  call    cs:__imp_ObfDereferenceObject
0x14000f582  nop     dword ptr [rax+rax+00h]
0x14000f587  test    r13b, r13b
0x14000f58a  jz      short loc_14000F5BC
0x14000f58c  test    rdi, rdi
0x14000f58f  jnz     short loc_14000F5BC
0x14000f591  call    cs:__imp_KeEnterCriticalRegion
0x14000f598  nop     dword ptr [rax+rax+00h]
0x14000f59d  lea     rcx, gBfsRundownProtection; RunRef
0x14000f5a4  call    cs:__imp_ExReleaseRundownProtection
0x14000f5ab  nop     dword ptr [rax+rax+00h]
0x14000f5b0  call    cs:__imp_KeLeaveCriticalRegion
0x14000f5b7  nop     dword ptr [rax+rax+00h]
0x14000f5bc  mov     eax, ebx
0x14000f5be  jmp     loc_14000F37E
```
