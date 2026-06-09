# LogInitialize

- ea: `0x14002709c`
- end: `0x1400272d3`
- name: `LogInitialize`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008100`

## callees

- `0x140008428`
- `0x140013b00`
- `0x14002709c`
- `0x1400272dc`

## import_xrefs

- `ntoskrnl!EtwSetInformation` at `0x14002713c`
- `ntoskrnl!EtwSetInformation` at `0x14002713c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140027169`
- `ntoskrnl!KeInitializeSpinLock` at `0x140027169`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027156`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400271a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400271be`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027156`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400271a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400271be`
- `ntoskrnl!EtwRegister` at `0x140027117`
- `ntoskrnl!EtwRegister` at `0x140027117`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272be`
- `ntoskrnl!ExAllocatePool2` at `0x140027229`
- `ntoskrnl!ExAllocatePool2` at `0x140027229`

## string_xrefs

- `0x140027189`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\Shared\Policy`

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
  xmmword_14001F108 = 0;
  if ( !EtwRegister(&ProviderId, tlgEnableCallback, &dword_14001F0E0, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  RtlInitUnicodeString(&::DestinationString, L"VfscDrv");
  KeInitializeSpinLock(&SpinLock);
  qword_14001FD08 = (__int64)&::P;
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
  dword_14001F1D0 = v3;
  v4 = 0;
  while ( 1 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 2088, 1735156834);
    v6 = Pool2 == 0 ? 0xC000009A : 0;
    if ( !Pool2 )
      break;
    v7 = (_QWORD *)qword_14001FD08;
    if ( *(PVOID **)qword_14001FD08 != &::P )
LABEL_19:
      __fastfail(3u);
    *Pool2 = &::P;
    ++v4;
    Pool2[1] = v7;
    *v7 = Pool2;
    qword_14001FD08 = (__int64)Pool2;
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
0x14002709c  mov     [rsp+arg_0], rbx
0x1400270a1  mov     [rsp+arg_8], rsi
0x1400270a6  push    rdi
0x1400270a7  sub     rsp, 50h
0x1400270ab  mov     rax, cs:__security_cookie
0x1400270b2  xor     rax, rsp
0x1400270b5  mov     [rsp+58h+var_10], rax
0x1400270ba  lea     r8, AppVClientDbg_Context
0x1400270c1  mov     r9, r8
0x1400270c4  lea     rcx, AppVClientDbg
0x1400270cb  call    McGenEventRegister_EtwRegister
0x1400270d0  cmp     cs:RegHandle, 0
0x1400270d8  mov     rax, cs:EventInformation
0x1400270df  movups  xmm0, xmmword ptr [rax-10h]
0x1400270e3  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1400270e9  jz      short loc_1400270F2
0x1400270eb  mov     ecx, 5
0x1400270f0  int     29h; Win8: RtlFailFast(ecx)
0x1400270f2  xorps   xmm0, xmm0
0x1400270f5  lea     r9, RegHandle; RegHandle
0x1400270fc  lea     r8, dword_14001F0E0; CallbackContext
0x140027103  lea     rdx, _tlgEnableCallback; EnableCallback
0x14002710a  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x14002710f  movdqu  cs:xmmword_14001F108, xmm0
0x140027117  call    cs:__imp_EtwRegister
0x14002711e  nop     dword ptr [rax+rax+00h]
0x140027123  test    eax, eax
0x140027125  jnz     short loc_140027148
0x140027127  mov     r8, cs:EventInformation; EventInformation
0x14002712e  lea     edx, [rax+2]; InformationClass
0x140027131  mov     rcx, cs:RegHandle; RegHandle
0x140027138  movzx   r9d, word ptr [r8]; InformationLength
0x14002713c  call    cs:__imp_EtwSetInformation
0x140027143  nop     dword ptr [rax+rax+00h]
0x140027148  lea     rdx, aVfscdrv; "VfscDrv"
0x14002714f  lea     rcx, DestinationString; DestinationString
0x140027156  call    cs:__imp_RtlInitUnicodeString
0x14002715d  nop     dword ptr [rax+rax+00h]
0x140027162  lea     rcx, SpinLock; SpinLock
0x140027169  call    cs:__imp_KeInitializeSpinLock
0x140027170  nop     dword ptr [rax+rax+00h]
0x140027175  xorps   xmm0, xmm0
0x140027178  lea     rsi, P
0x14002717f  xorps   xmm1, xmm1
0x140027182  mov     cs:qword_14001FD08, rsi
0x140027189  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x140027190  mov     cs:P, rsi
0x140027197  lea     rcx, [rsp+58h+ProviderId]; DestinationString
0x14002719c  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1400271a1  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm1
0x1400271a6  call    cs:__imp_RtlInitUnicodeString
0x1400271ad  nop     dword ptr [rax+rax+00h]
0x1400271b2  lea     rdx, aDbgfiltermask; "DbgFilterMask"
0x1400271b9  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400271be  call    cs:__imp_RtlInitUnicodeString
0x1400271c5  nop     dword ptr [rax+rax+00h]
0x1400271ca  lea     r9, [rsp+58h+P]
0x1400271cf  mov     [rsp+58h+P], 0
0x1400271d8  lea     rdx, [rsp+58h+DestinationString]
0x1400271dd  lea     rcx, [rsp+58h+ProviderId]
0x1400271e2  call    ReadRegistryValue
0x1400271e7  test    eax, eax
0x1400271e9  js      short loc_14002720E
0x1400271eb  mov     rcx, [rsp+58h+P]; P
0x1400271f0  mov     eax, [rcx+8]
0x1400271f3  mov     ebx, [rax+rcx]
0x1400271f6  test    rcx, rcx
0x1400271f9  jz      short loc_140027211
0x1400271fb  mov     edx, 676C6462h; Tag
0x140027200  call    cs:__imp_ExFreePoolWithTag
0x140027207  nop     dword ptr [rax+rax+00h]
0x14002720c  jmp     short loc_140027211
0x14002720e  or      ebx, 0FFFFFFFFh
0x140027211  mov     cs:dword_14001F1D0, ebx
0x140027217  xor     edi, edi
0x140027219  mov     edx, 828h
0x14002721e  mov     ecx, 40h ; '@'
0x140027223  mov     r8d, 676C6462h
0x140027229  call    cs:__imp_ExAllocatePool2
0x140027230  nop     dword ptr [rax+rax+00h]
0x140027235  mov     rcx, rax
0x140027238  neg     rcx
0x14002723b  sbb     ebx, ebx
0x14002723d  not     ebx
0x14002723f  and     ebx, 0C000009Ah
0x140027245  test    rax, rax
0x140027248  jz      short loc_14002728E
0x14002724a  mov     rcx, cs:qword_14001FD08
0x140027251  cmp     [rcx], rsi
0x140027254  jnz     short loc_1400272CC
0x140027256  mov     [rax], rsi
0x140027259  inc     edi
0x14002725b  mov     [rax+8], rcx
0x14002725f  mov     [rcx], rax
0x140027262  mov     cs:qword_14001FD08, rax
0x140027269  cmp     edi, 0Ah
0x14002726c  jl      short loc_140027219
0x14002726e  mov     eax, ebx
0x140027270  mov     rcx, [rsp+58h+var_10]
0x140027275  xor     rcx, rsp; StackCookie
0x140027278  call    __security_check_cookie
0x14002727d  mov     rbx, [rsp+58h+arg_0]
0x140027282  mov     rsi, [rsp+58h+arg_8]
0x140027287  add     rsp, 50h
0x14002728b  pop     rdi
0x14002728c  retn
0x14002728e  mov     rcx, cs:P; P
0x140027295  cmp     rcx, rsi
0x140027298  jz      short loc_14002726E
0x14002729a  cmp     [rcx+8], rsi
0x14002729e  jnz     short loc_1400272CC
0x1400272a0  mov     rax, [rcx]
0x1400272a3  cmp     [rax+8], rcx
0x1400272a7  jnz     short loc_1400272CC
0x1400272a9  mov     cs:P, rax
0x1400272b0  mov     [rax+8], rsi
0x1400272b4  test    rcx, rcx
0x1400272b7  jz      short loc_14002728E
0x1400272b9  mov     edx, 676C6462h; Tag
0x1400272be  call    cs:__imp_ExFreePoolWithTag
0x1400272c5  nop     dword ptr [rax+rax+00h]
0x1400272ca  jmp     short loc_14002728E
0x1400272cc  mov     ecx, 3
0x1400272d1  int     29h; Win8: RtlFailFast(ecx)
```
