# AipkLoadRegCache

- ea: `0x140028c6c`
- end: `0x140028f1f`
- name: `AipkLoadRegCache`
- size: `691`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140028f80`

## callees

- `0x140006a20`
- `0x1400287e0`
- `0x140028c6c`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028ef4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028ef4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140028ca7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140028ca7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028cbc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028cbc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028ee8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028ee8`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140028dd5`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140028ed3`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140028dd5`
- `ntoskrnl!ZwUnloadKeyEx` at `0x140028ed3`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140028d02`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140028d02`
- `ntoskrnl!ZwDeleteFile` at `0x140028d2f`
- `ntoskrnl!ZwDeleteFile` at `0x140028df4`
- `ntoskrnl!ZwDeleteFile` at `0x140028d2f`
- `ntoskrnl!ZwDeleteFile` at `0x140028df4`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028e38`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028e38`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140028e68`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140028e68`
- `ntoskrnl!ZwSetSecurityObject` at `0x140028e86`
- `ntoskrnl!ZwSetSecurityObject` at `0x140028e86`
- `ntoskrnl!ZwQueryKey` at `0x140028d91`
- `ntoskrnl!ZwQueryKey` at `0x140028d91`
- `ntoskrnl!ZwClose` at `0x140028dbc`
- `ntoskrnl!ZwClose` at `0x140028e9d`
- `ntoskrnl!ZwClose` at `0x140028dbc`
- `ntoskrnl!ZwClose` at `0x140028e9d`

## pseudocode

```c
__int64 AipkLoadRegCache()
{
  PACL v0; // r15
  void *v1; // rsi
  int v2; // edi
  NTSTATUS SecurityDescriptor; // ebx
  unsigned int i; // r14d
  NTSTATUS v5; // eax
  void *v6; // rax
  int v7; // eax
  int Parameter; // [rsp+30h] [rbp-39h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-31h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-29h] BYREF
  PACL Dacl; // [rsp+48h] [rbp-21h] BYREF
  __int128 KeyInformation; // [rsp+50h] [rbp-19h] BYREF
  __int128 v14; // [rsp+60h] [rbp-9h]
  __int128 v15; // [rsp+70h] [rbp+7h]

  v0 = 0;
  Parameter = 0;
  Dacl = 0;
  v1 = 0;
  KeyHandle = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&AipAppxRegCache, 0);
  if ( (_BYTE)qword_140019430 )
  {
    v2 = 0;
    SecurityDescriptor = 0;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v2 = 0;
      if ( i >= 2 )
        break;
      SecurityDescriptor = KeExpandKernelStackAndCalloutEx(AipkLoadRegCache_Callout, &Parameter, 0x6000u, 0, 0);
      if ( SecurityDescriptor < 0 )
        goto LABEL_24;
      SecurityDescriptor = Parameter;
      if ( Parameter >= 0 )
      {
        v2 = 1;
        SecurityDescriptor = AiRegOpenKey(0, L"NP", 983103, &KeyHandle);
        if ( SecurityDescriptor < 0 )
          goto LABEL_24;
        ResultLength = 0;
        KeyInformation = 0;
        v14 = 0;
        v15 = 0;
        v5 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
        SecurityDescriptor = 0;
        if ( v5 != -2147483643 )
          SecurityDescriptor = v5;
        if ( SecurityDescriptor < 0 )
          goto LABEL_24;
        if ( DWORD1(v14) < 0x3E8 )
          break;
        ZwClose(KeyHandle);
        KeyHandle = 0;
        SecurityDescriptor = ZwUnloadKeyEx((POBJECT_ATTRIBUTES)&TargetKey, 0);
        if ( SecurityDescriptor < 0 )
          goto LABEL_24;
        v2 = 0;
        SecurityDescriptor = ZwDeleteFile((POBJECT_ATTRIBUTES)&ObjectAttributes);
        if ( SecurityDescriptor < 0 )
          goto LABEL_24;
      }
      else
      {
        if ( i )
        {
          Parameter = 0;
          goto LABEL_24;
        }
        ZwDeleteFile((POBJECT_ATTRIBUTES)&ObjectAttributes);
      }
    }
    v6 = (void *)AiAlloc(40);
    v1 = v6;
    if ( v6 )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(v6, 1u);
      if ( SecurityDescriptor >= 0 )
      {
        v7 = AipkConstructCacheDacl(&Dacl);
        v0 = Dacl;
        SecurityDescriptor = v7;
        if ( v7 >= 0 )
        {
          SecurityDescriptor = RtlSetDaclSecurityDescriptor(v1, 1u, Dacl, 0);
          if ( SecurityDescriptor >= 0 )
            SecurityDescriptor = ZwSetSecurityObject(KeyHandle, 4u, v1);
        }
      }
    }
    else
    {
      SecurityDescriptor = -1073741801;
    }
  }
LABEL_24:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  AiFree(v0);
  AiFree(v1);
  if ( SecurityDescriptor < 0 )
  {
    if ( v2 )
      ZwUnloadKeyEx((POBJECT_ATTRIBUTES)&TargetKey, 0);
  }
  else
  {
    LOBYTE(qword_140019430) = 1;
  }
  ExReleasePushLockExclusiveEx(&AipAppxRegCache, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140028c6c  push    rbp
0x140028c6e  push    rbx
0x140028c6f  push    rsi
0x140028c70  push    rdi
0x140028c71  push    r14
0x140028c73  push    r15
0x140028c75  lea     rbp, [rsp-2Fh]
0x140028c7a  sub     rsp, 98h
0x140028c81  mov     rax, cs:__security_cookie
0x140028c88  xor     rax, rsp
0x140028c8b  mov     [rbp+57h+var_40], rax
0x140028c8f  xor     r15d, r15d
0x140028c92  mov     [rbp+57h+Parameter], 0
0x140028c99  mov     [rbp+57h+Dacl], r15
0x140028c9d  xor     esi, esi
0x140028c9f  mov     [rbp+57h+KeyHandle], 0
0x140028ca7  call    cs:__imp_KeEnterCriticalRegion
0x140028cae  nop     dword ptr [rax+rax+00h]
0x140028cb3  xor     edx, edx
0x140028cb5  lea     rcx, AipAppxRegCache
0x140028cbc  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140028cc3  nop     dword ptr [rax+rax+00h]
0x140028cc8  cmp     byte ptr cs:qword_140019430, sil
0x140028ccf  jz      short loc_140028CDA
0x140028cd1  xor     edi, edi
0x140028cd3  xor     ebx, ebx
0x140028cd5  jmp     loc_140028E94
0x140028cda  xor     r14d, r14d
0x140028cdd  xor     edi, edi
0x140028cdf  cmp     r14d, 2
0x140028ce3  jnb     loc_140028E17
0x140028ce9  xor     r9d, r9d; Wait
0x140028cec  mov     [rsp+0C0h+Context], rsi; Context
0x140028cf1  mov     r8d, 6000h; Size
0x140028cf7  lea     rdx, [rbp+57h+Parameter]; Parameter
0x140028cfb  lea     rcx, AipkLoadRegCache_Callout; Callout
0x140028d02  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140028d09  nop     dword ptr [rax+rax+00h]
0x140028d0e  mov     ebx, eax
0x140028d10  test    eax, eax
0x140028d12  js      loc_140028E94
0x140028d18  mov     ebx, [rbp+57h+Parameter]
0x140028d1b  test    ebx, ebx
0x140028d1d  jns     short loc_140028D40
0x140028d1f  test    r14d, r14d
0x140028d22  jnz     loc_140028E12
0x140028d28  lea     rcx, ObjectAttributes; ObjectAttributes
0x140028d2f  call    cs:__imp_ZwDeleteFile
0x140028d36  nop     dword ptr [rax+rax+00h]
0x140028d3b  jmp     loc_140028E0A
0x140028d40  lea     r9, [rbp+57h+KeyHandle]
0x140028d44  mov     r8d, 0F003Fh
0x140028d4a  lea     rdx, aNp; "NP"
0x140028d51  xor     ecx, ecx
0x140028d53  mov     edi, 1
0x140028d58  call    AiRegOpenKey
0x140028d5d  mov     ebx, eax
0x140028d5f  test    eax, eax
0x140028d61  js      loc_140028E94
0x140028d67  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140028d6b  lea     rax, [rbp+57h+ResultLength]
0x140028d6f  xorps   xmm0, xmm0
0x140028d72  mov     [rsp+0C0h+Context], rax; ResultLength
0x140028d77  lea     r9d, [rdi+2Fh]; Length
0x140028d7b  mov     [rbp+57h+ResultLength], esi
0x140028d7e  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x140028d82  lea     edx, [rdi+1]; KeyInformationClass
0x140028d85  movups  [rbp+57h+KeyInformation], xmm0
0x140028d89  movups  [rbp+57h+var_60], xmm0
0x140028d8d  movups  [rbp+57h+var_50], xmm0
0x140028d91  call    cs:__imp_ZwQueryKey
0x140028d98  nop     dword ptr [rax+rax+00h]
0x140028d9d  xor     ebx, ebx
0x140028d9f  cmp     eax, 80000005h
0x140028da4  cmovnz  ebx, eax
0x140028da7  test    ebx, ebx
0x140028da9  js      loc_140028E94
0x140028daf  cmp     dword ptr [rbp+57h+var_60+4], 3E8h
0x140028db6  jb      short loc_140028E17
0x140028db8  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140028dbc  call    cs:__imp_ZwClose
0x140028dc3  nop     dword ptr [rax+rax+00h]
0x140028dc8  xor     edx, edx; Event
0x140028dca  mov     [rbp+57h+KeyHandle], rsi
0x140028dce  lea     rcx, TargetKey; TargetKey
0x140028dd5  call    cs:__imp_ZwUnloadKeyEx
0x140028ddc  nop     dword ptr [rax+rax+00h]
0x140028de1  mov     ebx, eax
0x140028de3  test    eax, eax
0x140028de5  js      loc_140028E94
0x140028deb  lea     rcx, ObjectAttributes; ObjectAttributes
0x140028df2  xor     edi, edi
0x140028df4  call    cs:__imp_ZwDeleteFile
0x140028dfb  nop     dword ptr [rax+rax+00h]
0x140028e00  mov     ebx, eax
0x140028e02  test    eax, eax
0x140028e04  js      loc_140028E94
0x140028e0a  inc     r14d
0x140028e0d  jmp     loc_140028CDD
0x140028e12  mov     [rbp+57h+Parameter], esi
0x140028e15  jmp     short loc_140028E94
0x140028e17  mov     ecx, 28h ; '('
0x140028e1c  call    AiAlloc
0x140028e21  mov     rsi, rax
0x140028e24  test    rax, rax
0x140028e27  jnz     short loc_140028E30
0x140028e29  mov     ebx, 0C0000017h
0x140028e2e  jmp     short loc_140028E94
0x140028e30  mov     edx, 1; Revision
0x140028e35  mov     rcx, rsi; SecurityDescriptor
0x140028e38  call    cs:__imp_RtlCreateSecurityDescriptor
0x140028e3f  nop     dword ptr [rax+rax+00h]
0x140028e44  mov     ebx, eax
0x140028e46  test    eax, eax
0x140028e48  js      short loc_140028E94
0x140028e4a  lea     rcx, [rbp+57h+Dacl]
0x140028e4e  call    AipkConstructCacheDacl
0x140028e53  mov     r15, [rbp+57h+Dacl]
0x140028e57  mov     ebx, eax
0x140028e59  test    eax, eax
0x140028e5b  js      short loc_140028E94
0x140028e5d  xor     r9d, r9d; DaclDefaulted
0x140028e60  mov     r8, r15; Dacl
0x140028e63  mov     dl, 1; DaclPresent
0x140028e65  mov     rcx, rsi; SecurityDescriptor
0x140028e68  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140028e6f  nop     dword ptr [rax+rax+00h]
0x140028e74  mov     ebx, eax
0x140028e76  test    eax, eax
0x140028e78  js      short loc_140028E94
0x140028e7a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140028e7e  mov     r8, rsi; SecurityDescriptor
0x140028e81  mov     edx, 4; SecurityInformation
0x140028e86  call    cs:__imp_ZwSetSecurityObject
0x140028e8d  nop     dword ptr [rax+rax+00h]
0x140028e92  mov     ebx, eax
0x140028e94  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140028e98  test    rcx, rcx
0x140028e9b  jz      short loc_140028EA9
0x140028e9d  call    cs:__imp_ZwClose
0x140028ea4  nop     dword ptr [rax+rax+00h]
0x140028ea9  mov     rcx, r15
0x140028eac  call    AiFree
0x140028eb1  mov     rcx, rsi
0x140028eb4  call    AiFree
0x140028eb9  test    ebx, ebx
0x140028ebb  js      short loc_140028EC6
0x140028ebd  mov     byte ptr cs:qword_140019430, 1
0x140028ec4  jmp     short loc_140028EDF
0x140028ec6  test    edi, edi
0x140028ec8  jz      short loc_140028EDF
0x140028eca  xor     edx, edx; Event
0x140028ecc  lea     rcx, TargetKey; TargetKey
0x140028ed3  call    cs:__imp_ZwUnloadKeyEx
0x140028eda  nop     dword ptr [rax+rax+00h]
0x140028edf  xor     edx, edx
0x140028ee1  lea     rcx, AipAppxRegCache
0x140028ee8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140028eef  nop     dword ptr [rax+rax+00h]
0x140028ef4  call    cs:__imp_KeLeaveCriticalRegion
0x140028efb  nop     dword ptr [rax+rax+00h]
0x140028f00  mov     eax, ebx
0x140028f02  mov     rcx, [rbp+57h+var_40]
0x140028f06  xor     rcx, rsp; StackCookie
0x140028f09  call    __security_check_cookie
0x140028f0e  add     rsp, 98h
0x140028f15  pop     r15
0x140028f17  pop     r14
0x140028f19  pop     rdi
0x140028f1a  pop     rsi
0x140028f1b  pop     rbx
0x140028f1c  pop     rbp
0x140028f1d  retn
```
