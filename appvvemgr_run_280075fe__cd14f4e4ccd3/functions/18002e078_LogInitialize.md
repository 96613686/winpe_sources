# LogInitialize

- ea: `0x18002e078`
- end: `0x18002e2af`
- name: `LogInitialize`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015fa4`

## callees

- `0x180016338`
- `0x18001baf0`
- `0x18002e078`
- `0x18002e2b8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18002e205`
- `ntoskrnl!ExAllocatePool2` at `0x18002e205`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e1dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e29a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e1dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002e29a`
- `ntoskrnl!EtwRegister` at `0x18002e0f3`
- `ntoskrnl!EtwRegister` at `0x18002e0f3`
- `ntoskrnl!EtwSetInformation` at `0x18002e118`
- `ntoskrnl!EtwSetInformation` at `0x18002e118`
- `ntoskrnl!KeInitializeSpinLock` at `0x18002e145`
- `ntoskrnl!KeInitializeSpinLock` at `0x18002e145`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e132`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e182`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e19a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e132`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e182`
- `ntoskrnl!RtlInitUnicodeString` at `0x18002e19a`

## string_xrefs

- `0x18002e165`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\Shared\Policy`

## pseudocode

```c
__int64 __fastcall LogInitialize(__int64 a1, __int64 a2)
{
  __int64 v2; // r8
  int v3; // ebx
  int v4; // edi
  _QWORD *Pool2; // rax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  PVOID v9; // rcx
  __int64 v10; // rax
  PVOID P; // [rsp+20h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-20h] BYREF

  McGenEventRegister_EtwRegister(AppVClientDbg, a2, AppVClientDbg_Context, AppVClientDbg_Context);
  ProviderId = (GUID)*((_OWORD *)EventInformation - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_180027110 = 0;
  if ( !EtwRegister(&ProviderId, tlgEnableCallback, &dword_1800270E8, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  RtlInitUnicodeString(&::DestinationString, L"VEMgrDrv");
  KeInitializeSpinLock(&SpinLock);
  qword_180027460 = (__int64)&::P;
  ::P = &::P;
  ProviderId = 0;
  DestinationString = 0;
  RtlInitUnicodeString((PUNICODE_STRING)&ProviderId, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\Shared\\Policy");
  RtlInitUnicodeString(&DestinationString, L"DbgFilterMask");
  P = 0;
  if ( (int)ReadRegistryValue((struct _UNICODE_STRING *)&ProviderId, &DestinationString, v2, &P) < 0 )
  {
    v3 = -1;
  }
  else
  {
    v3 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
    if ( P )
      ExFreePoolWithTag(P, 0x676C6462u);
  }
  dword_180027228 = v3;
  v4 = 0;
  while ( 1 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 2088, 1735156834);
    v6 = Pool2 == 0 ? 0xC000009A : 0;
    if ( !Pool2 )
      break;
    v7 = (_QWORD *)qword_180027460;
    if ( *(PVOID **)qword_180027460 != &::P )
LABEL_19:
      __fastfail(3u);
    *Pool2 = &::P;
    ++v4;
    Pool2[1] = v7;
    *v7 = Pool2;
    qword_180027460 = (__int64)Pool2;
    if ( v4 >= 10 )
      return v6;
  }
  while ( 1 )
  {
    v9 = ::P;
    if ( ::P == &::P )
      return v6;
    if ( *((PVOID **)::P + 1) != &::P )
      goto LABEL_19;
    v10 = *(_QWORD *)::P;
    if ( *(PVOID *)(*(_QWORD *)::P + 8LL) != ::P )
      goto LABEL_19;
    ::P = *(PVOID *)::P;
    *(_QWORD *)(v10 + 8) = &::P;
    if ( v9 )
      ExFreePoolWithTag(v9, 0x676C6462u);
  }
}

```

## disassembly

```asm
0x18002e078  mov     [rsp+arg_0], rbx
0x18002e07d  mov     [rsp+arg_8], rsi
0x18002e082  push    rdi
0x18002e083  sub     rsp, 50h
0x18002e087  mov     rax, cs:__security_cookie
0x18002e08e  xor     rax, rsp
0x18002e091  mov     [rsp+58h+var_10], rax
0x18002e096  lea     r8, AppVClientDbg_Context
0x18002e09d  mov     r9, r8
0x18002e0a0  lea     rcx, AppVClientDbg
0x18002e0a7  call    McGenEventRegister_EtwRegister
0x18002e0ac  cmp     cs:RegHandle, 0
0x18002e0b4  mov     rax, cs:EventInformation
0x18002e0bb  movups  xmm0, xmmword ptr [rax-10h]
0x18002e0bf  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18002e0c5  jz      short loc_18002E0CE
0x18002e0c7  mov     ecx, 5
0x18002e0cc  int     29h; Win8: RtlFailFast(ecx)
0x18002e0ce  xorps   xmm0, xmm0
0x18002e0d1  lea     r9, RegHandle; RegHandle
0x18002e0d8  lea     r8, dword_1800270E8; CallbackContext
0x18002e0df  lea     rdx, _tlgEnableCallback; EnableCallback
0x18002e0e6  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x18002e0eb  movdqu  cs:xmmword_180027110, xmm0
0x18002e0f3  call    cs:__imp_EtwRegister
0x18002e0fa  nop     dword ptr [rax+rax+00h]
0x18002e0ff  test    eax, eax
0x18002e101  jnz     short loc_18002E124
0x18002e103  mov     r8, cs:EventInformation; EventInformation
0x18002e10a  lea     edx, [rax+2]; InformationClass
0x18002e10d  mov     rcx, cs:RegHandle; RegHandle
0x18002e114  movzx   r9d, word ptr [r8]; InformationLength
0x18002e118  call    cs:__imp_EtwSetInformation
0x18002e11f  nop     dword ptr [rax+rax+00h]
0x18002e124  lea     rdx, aVemgrdrv; "VEMgrDrv"
0x18002e12b  lea     rcx, DestinationString; DestinationString
0x18002e132  call    cs:__imp_RtlInitUnicodeString
0x18002e139  nop     dword ptr [rax+rax+00h]
0x18002e13e  lea     rcx, SpinLock; SpinLock
0x18002e145  call    cs:__imp_KeInitializeSpinLock
0x18002e14c  nop     dword ptr [rax+rax+00h]
0x18002e151  xorps   xmm0, xmm0
0x18002e154  lea     rsi, P
0x18002e15b  xorps   xmm1, xmm1
0x18002e15e  mov     cs:qword_180027460, rsi
0x18002e165  lea     rdx, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18002e16c  mov     cs:P, rsi
0x18002e173  lea     rcx, [rsp+58h+ProviderId]; DestinationString
0x18002e178  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18002e17d  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm1
0x18002e182  call    cs:__imp_RtlInitUnicodeString
0x18002e189  nop     dword ptr [rax+rax+00h]
0x18002e18e  lea     rdx, aDbgfiltermask; "DbgFilterMask"
0x18002e195  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002e19a  call    cs:__imp_RtlInitUnicodeString
0x18002e1a1  nop     dword ptr [rax+rax+00h]
0x18002e1a6  lea     r9, [rsp+58h+P]
0x18002e1ab  mov     [rsp+58h+P], 0
0x18002e1b4  lea     rdx, [rsp+58h+DestinationString]
0x18002e1b9  lea     rcx, [rsp+58h+ProviderId]
0x18002e1be  call    ReadRegistryValue
0x18002e1c3  test    eax, eax
0x18002e1c5  js      short loc_18002E1EA
0x18002e1c7  mov     rcx, [rsp+58h+P]; P
0x18002e1cc  mov     eax, [rcx+8]
0x18002e1cf  mov     ebx, [rax+rcx]
0x18002e1d2  test    rcx, rcx
0x18002e1d5  jz      short loc_18002E1ED
0x18002e1d7  mov     edx, 676C6462h; Tag
0x18002e1dc  call    cs:__imp_ExFreePoolWithTag
0x18002e1e3  nop     dword ptr [rax+rax+00h]
0x18002e1e8  jmp     short loc_18002E1ED
0x18002e1ea  or      ebx, 0FFFFFFFFh
0x18002e1ed  mov     cs:dword_180027228, ebx
0x18002e1f3  xor     edi, edi
0x18002e1f5  mov     edx, 828h
0x18002e1fa  mov     ecx, 40h ; '@'
0x18002e1ff  mov     r8d, 676C6462h
0x18002e205  call    cs:__imp_ExAllocatePool2
0x18002e20c  nop     dword ptr [rax+rax+00h]
0x18002e211  mov     rcx, rax
0x18002e214  neg     rcx
0x18002e217  sbb     ebx, ebx
0x18002e219  not     ebx
0x18002e21b  and     ebx, 0C000009Ah
0x18002e221  test    rax, rax
0x18002e224  jz      short loc_18002E26A
0x18002e226  mov     rcx, cs:qword_180027460
0x18002e22d  cmp     [rcx], rsi
0x18002e230  jnz     short loc_18002E2A8
0x18002e232  mov     [rax], rsi
0x18002e235  inc     edi
0x18002e237  mov     [rax+8], rcx
0x18002e23b  mov     [rcx], rax
0x18002e23e  mov     cs:qword_180027460, rax
0x18002e245  cmp     edi, 0Ah
0x18002e248  jl      short loc_18002E1F5
0x18002e24a  mov     eax, ebx
0x18002e24c  mov     rcx, [rsp+58h+var_10]
0x18002e251  xor     rcx, rsp; StackCookie
0x18002e254  call    __security_check_cookie
0x18002e259  mov     rbx, [rsp+58h+arg_0]
0x18002e25e  mov     rsi, [rsp+58h+arg_8]
0x18002e263  add     rsp, 50h
0x18002e267  pop     rdi
0x18002e268  retn
0x18002e26a  mov     rcx, cs:P; P
0x18002e271  cmp     rcx, rsi
0x18002e274  jz      short loc_18002E24A
0x18002e276  cmp     [rcx+8], rsi
0x18002e27a  jnz     short loc_18002E2A8
0x18002e27c  mov     rax, [rcx]
0x18002e27f  cmp     [rax+8], rcx
0x18002e283  jnz     short loc_18002E2A8
0x18002e285  mov     cs:P, rax
0x18002e28c  mov     [rax+8], rsi
0x18002e290  test    rcx, rcx
0x18002e293  jz      short loc_18002E26A
0x18002e295  mov     edx, 676C6462h; Tag
0x18002e29a  call    cs:__imp_ExFreePoolWithTag
0x18002e2a1  nop     dword ptr [rax+rax+00h]
0x18002e2a6  jmp     short loc_18002E26A
0x18002e2a8  mov     ecx, 3
0x18002e2ad  int     29h; Win8: RtlFailFast(ecx)
```
