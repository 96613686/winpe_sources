# PktMonAttachProvider

- ea: `0x140167070`
- end: `0x1401671cf`
- name: `PktMonAttachProvider`
- size: `351`
- prototype: `__int64 __fastcall(HANDLE NmrBindingHandle, PVOID ClientBindingContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14016700c`
- `0x140167070`
- `0x1401678f0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140167184`
- `ntoskrnl!KeWaitForSingleObject` at `0x140167184`
- `ntoskrnl!KeReleaseMutex` at `0x1401671be`
- `ntoskrnl!KeReleaseMutex` at `0x1401671be`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140167105`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140167105`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140167124`
- `ntoskrnl!ExReInitializeRundownProtectionCacheAware` at `0x140167124`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401670bb`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401670bb`
- `NETIO!NmrClientAttachProvider` at `0x14016714e`
- `NETIO!NmrClientAttachProvider` at `0x14016714e`

## pseudocode

```c
__int64 __fastcall PktMonAttachProvider(HANDLE NmrBindingHandle, PVOID ClientBindingContext, __int64 a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  PVOID ProviderBindingContext; // [rsp+58h] [rbp+20h] BYREF

  ProviderBindingContext = 0;
  if ( (unsigned int)Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline()
    && (v6 = *(_QWORD *)(a3 + 32)) != 0
    && *(_WORD *)(v6 + 4) != 1
    || *((_QWORD *)&xmmword_1401A37A0 + 1) )
  {
    v7 = -1073741127;
    goto LABEL_5;
  }
  if ( RunRefCacheAware )
  {
    ExReInitializeRundownProtectionCacheAware(RunRefCacheAware);
  }
  else
  {
    RunRefCacheAware = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x72644D50u);
    if ( !RunRefCacheAware )
    {
      v7 = -1073741801;
      goto LABEL_5;
    }
  }
  v7 = NmrClientAttachProvider(
         NmrBindingHandle,
         ClientBindingContext,
         &PktMonClientDispatch,
         &ProviderBindingContext,
         (const void **)&xmmword_1401A37A0 + 1);
  if ( v7 )
  {
LABEL_5:
    if ( RunRefCacheAware )
    {
      ExFreeCacheAwareRundownProtection(RunRefCacheAware);
      RunRefCacheAware = 0;
    }
    return v7;
  }
  if ( NmrAttachSync )
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
  *(_QWORD *)&xmmword_1401A37A0 = ProviderBindingContext;
  ((void (*)(void))qword_1401A3788)();
  if ( NmrAttachSync )
    KeReleaseMutex(&PktMonCompMutex, 0);
  return v7;
}

```

## disassembly

```asm
0x140167070  mov     [rsp+arg_0], rbx
0x140167075  mov     [rsp+arg_8], rsi
0x14016707a  push    rdi
0x14016707b  sub     rsp, 30h
0x14016707f  mov     rbx, r8
0x140167082  mov     [rsp+38h+ProviderBindingContext], 0
0x14016708b  mov     rdi, rdx
0x14016708e  mov     rsi, rcx
0x140167091  call    Feature_NVBugFixes2507__private_IsEnabledDeviceUsageNoInline
0x140167096  test    eax, eax
0x140167098  jz      short loc_1401670E5
0x14016709a  mov     rax, [rbx+20h]
0x14016709e  test    rax, rax
0x1401670a1  jz      short loc_1401670E5
0x1401670a3  cmp     word ptr [rax+4], 1
0x1401670a8  jz      short loc_1401670E5
0x1401670aa  mov     ebx, 0C00002B9h
0x1401670af  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1401670b6  test    rcx, rcx
0x1401670b9  jz      short loc_1401670D2
0x1401670bb  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401670c2  nop     dword ptr [rax+rax+00h]
0x1401670c7  mov     cs:RunRefCacheAware, 0
0x1401670d2  mov     rsi, [rsp+38h+arg_8]
0x1401670d7  mov     eax, ebx
0x1401670d9  mov     rbx, [rsp+38h+arg_0]
0x1401670de  add     rsp, 30h
0x1401670e2  pop     rdi
0x1401670e3  retn
0x1401670e5  cmp     qword ptr cs:xmmword_1401A37A0+8, 0
0x1401670ed  jnz     short loc_1401670AA
0x1401670ef  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1401670f6  test    rcx, rcx
0x1401670f9  jnz     short loc_140167124
0x1401670fb  mov     edx, 72644D50h; PoolTag
0x140167100  mov     ecx, 200h; PoolType
0x140167105  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14016710c  nop     dword ptr [rax+rax+00h]
0x140167111  mov     cs:RunRefCacheAware, rax
0x140167118  test    rax, rax
0x14016711b  jnz     short loc_140167130
0x14016711d  mov     ebx, 0C0000017h
0x140167122  jmp     short loc_1401670AF
0x140167124  call    cs:__imp_ExReInitializeRundownProtectionCacheAware
0x14016712b  nop     dword ptr [rax+rax+00h]
0x140167130  lea     rax, xmmword_1401A37A0+8
0x140167137  mov     rdx, rdi; ClientBindingContext
0x14016713a  lea     r9, [rsp+38h+ProviderBindingContext]; ProviderBindingContext
0x14016713f  mov     [rsp+38h+ProviderDispatch], rax; ProviderDispatch
0x140167144  lea     r8, PktMonClientDispatch; ClientDispatch
0x14016714b  mov     rcx, rsi; NmrBindingHandle
0x14016714e  call    cs:__imp_NmrClientAttachProvider
0x140167155  nop     dword ptr [rax+rax+00h]
0x14016715a  mov     ebx, eax
0x14016715c  test    eax, eax
0x14016715e  jnz     loc_1401670AF
0x140167164  cmp     cs:NmrAttachSync, al
0x14016716a  jz      short loc_140167190
0x14016716c  xor     r9d, r9d; Alertable
0x14016716f  mov     [rsp+38h+ProviderDispatch], 0; Timeout
0x140167178  xor     r8d, r8d; WaitMode
0x14016717b  lea     rcx, PktMonCompMutex; Object
0x140167182  xor     edx, edx; WaitReason
0x140167184  call    cs:__imp_KeWaitForSingleObject
0x14016718b  nop     dword ptr [rax+rax+00h]
0x140167190  mov     rax, [rsp+38h+ProviderBindingContext]
0x140167195  mov     qword ptr cs:xmmword_1401A37A0, rax
0x14016719c  mov     rax, cs:qword_1401A3788
0x1401671a3  call    _guard_dispatch_icall
0x1401671a8  cmp     cs:NmrAttachSync, 0
0x1401671af  jz      loc_1401670D2
0x1401671b5  xor     edx, edx; Wait
0x1401671b7  lea     rcx, PktMonCompMutex; Mutex
0x1401671be  call    cs:__imp_KeReleaseMutex
0x1401671c5  nop     dword ptr [rax+rax+00h]
0x1401671ca  jmp     loc_1401670D2
```
