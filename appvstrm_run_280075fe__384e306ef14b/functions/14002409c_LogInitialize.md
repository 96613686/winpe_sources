# LogInitialize

- ea: `0x14002409c`
- end: `0x1400242d3`
- name: `LogInitialize`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400135b4`

## callees

- `0x140001698`
- `0x140015af0`
- `0x14002409c`
- `0x1400242dc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140024156`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400241a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400241be`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024156`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400241a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400241be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400242be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400242be`
- `ntoskrnl!EtwRegister` at `0x140024117`
- `ntoskrnl!EtwRegister` at `0x140024117`
- `ntoskrnl!ExAllocatePool2` at `0x140024229`
- `ntoskrnl!ExAllocatePool2` at `0x140024229`
- `ntoskrnl!EtwSetInformation` at `0x14002413c`
- `ntoskrnl!EtwSetInformation` at `0x14002413c`
- `ntoskrnl!KeInitializeSpinLock` at `0x140024169`
- `ntoskrnl!KeInitializeSpinLock` at `0x140024169`

## string_xrefs

- `0x140024189`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\Shared\Policy`

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
  xmmword_14001F360 = 0;
  if ( !EtwRegister(&ProviderId, tlgEnableCallback, &dword_14001F338, &RegHandle) )
    EtwSetInformation(RegHandle, EventProviderSetTraits, EventInformation, *(unsigned __int16 *)EventInformation);
  RtlInitUnicodeString(&::DestinationString, L"StrmDrv");
  KeInitializeSpinLock(&SpinLock);
  qword_14001F498 = (__int64)&::P;
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
  dword_14001F3A4 = v3;
  v4 = 0;
  while ( 1 )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 2088, 1735156834);
    v6 = Pool2 == 0 ? 0xC000009A : 0;
    if ( !Pool2 )
      break;
    v7 = (_QWORD *)qword_14001F498;
    if ( *(PVOID **)qword_14001F498 != &::P )
LABEL_19:
      __fastfail(3u);
    *Pool2 = &::P;
    ++v4;
    Pool2[1] = v7;
    *v7 = Pool2;
    qword_14001F498 = (__int64)Pool2;
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
0x14002409c  mov     [rsp+arg_0], rbx
0x1400240a1  mov     [rsp+arg_8], rsi
0x1400240a6  push    rdi
0x1400240a7  sub     rsp, 50h
0x1400240ab  mov     rax, cs:__security_cookie
0x1400240b2  xor     rax, rsp
0x1400240b5  mov     [rsp+58h+var_10], rax
0x1400240ba  lea     r8, AppVClientDbg_Context
0x1400240c1  mov     r9, r8
0x1400240c4  lea     rcx, AppVClientDbg
0x1400240cb  call    McGenEventRegister_EtwRegister
0x1400240d0  cmp     cs:RegHandle, 0
0x1400240d8  mov     rax, cs:EventInformation
0x1400240df  movups  xmm0, xmmword ptr [rax-10h]
0x1400240e3  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1400240e9  jz      short loc_1400240F2
0x1400240eb  mov     ecx, 5
0x1400240f0  int     29h; Win8: RtlFailFast(ecx)
0x1400240f2  xorps   xmm0, xmm0
0x1400240f5  lea     r9, RegHandle; RegHandle
0x1400240fc  lea     r8, dword_14001F338; CallbackContext
0x140024103  lea     rdx, _tlgEnableCallback; EnableCallback
0x14002410a  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x14002410f  movdqu  cs:xmmword_14001F360, xmm0
0x140024117  call    cs:__imp_EtwRegister
0x14002411e  nop     dword ptr [rax+rax+00h]
0x140024123  test    eax, eax
0x140024125  jnz     short loc_140024148
0x140024127  mov     r8, cs:EventInformation; EventInformation
0x14002412e  lea     edx, [rax+2]; InformationClass
0x140024131  mov     rcx, cs:RegHandle; RegHandle
0x140024138  movzx   r9d, word ptr [r8]; InformationLength
0x14002413c  call    cs:__imp_EtwSetInformation
0x140024143  nop     dword ptr [rax+rax+00h]
0x140024148  lea     rdx, aStrmdrv; "StrmDrv"
0x14002414f  lea     rcx, DestinationString; DestinationString
0x140024156  call    cs:__imp_RtlInitUnicodeString
0x14002415d  nop     dword ptr [rax+rax+00h]
0x140024162  lea     rcx, SpinLock; SpinLock
0x140024169  call    cs:__imp_KeInitializeSpinLock
0x140024170  nop     dword ptr [rax+rax+00h]
0x140024175  xorps   xmm0, xmm0
0x140024178  lea     rsi, P
0x14002417f  xorps   xmm1, xmm1
0x140024182  mov     cs:qword_14001F498, rsi
0x140024189  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x140024190  mov     cs:P, rsi
0x140024197  lea     rcx, [rsp+58h+ProviderId]; DestinationString
0x14002419c  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x1400241a1  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm1
0x1400241a6  call    cs:__imp_RtlInitUnicodeString
0x1400241ad  nop     dword ptr [rax+rax+00h]
0x1400241b2  lea     rdx, aDbgfiltermask; "DbgFilterMask"
0x1400241b9  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400241be  call    cs:__imp_RtlInitUnicodeString
0x1400241c5  nop     dword ptr [rax+rax+00h]
0x1400241ca  lea     r9, [rsp+58h+P]
0x1400241cf  mov     [rsp+58h+P], 0
0x1400241d8  lea     rdx, [rsp+58h+DestinationString]
0x1400241dd  lea     rcx, [rsp+58h+ProviderId]
0x1400241e2  call    ReadRegistryValue
0x1400241e7  test    eax, eax
0x1400241e9  js      short loc_14002420E
0x1400241eb  mov     rcx, [rsp+58h+P]; P
0x1400241f0  mov     eax, [rcx+8]
0x1400241f3  mov     ebx, [rax+rcx]
0x1400241f6  test    rcx, rcx
0x1400241f9  jz      short loc_140024211
0x1400241fb  mov     edx, 676C6462h; Tag
0x140024200  call    cs:__imp_ExFreePoolWithTag
0x140024207  nop     dword ptr [rax+rax+00h]
0x14002420c  jmp     short loc_140024211
0x14002420e  or      ebx, 0FFFFFFFFh
0x140024211  mov     cs:dword_14001F3A4, ebx
0x140024217  xor     edi, edi
0x140024219  mov     edx, 828h
0x14002421e  mov     ecx, 40h ; '@'
0x140024223  mov     r8d, 676C6462h
0x140024229  call    cs:__imp_ExAllocatePool2
0x140024230  nop     dword ptr [rax+rax+00h]
0x140024235  mov     rcx, rax
0x140024238  neg     rcx
0x14002423b  sbb     ebx, ebx
0x14002423d  not     ebx
0x14002423f  and     ebx, 0C000009Ah
0x140024245  test    rax, rax
0x140024248  jz      short loc_14002428E
0x14002424a  mov     rcx, cs:qword_14001F498
0x140024251  cmp     [rcx], rsi
0x140024254  jnz     short loc_1400242CC
0x140024256  mov     [rax], rsi
0x140024259  inc     edi
0x14002425b  mov     [rax+8], rcx
0x14002425f  mov     [rcx], rax
0x140024262  mov     cs:qword_14001F498, rax
0x140024269  cmp     edi, 0Ah
0x14002426c  jl      short loc_140024219
0x14002426e  mov     eax, ebx
0x140024270  mov     rcx, [rsp+58h+var_10]
0x140024275  xor     rcx, rsp; StackCookie
0x140024278  call    __security_check_cookie
0x14002427d  mov     rbx, [rsp+58h+arg_0]
0x140024282  mov     rsi, [rsp+58h+arg_8]
0x140024287  add     rsp, 50h
0x14002428b  pop     rdi
0x14002428c  retn
0x14002428e  mov     rcx, cs:P; P
0x140024295  cmp     rcx, rsi
0x140024298  jz      short loc_14002426E
0x14002429a  cmp     [rcx+8], rsi
0x14002429e  jnz     short loc_1400242CC
0x1400242a0  mov     rax, [rcx]
0x1400242a3  cmp     [rax+8], rcx
0x1400242a7  jnz     short loc_1400242CC
0x1400242a9  mov     cs:P, rax
0x1400242b0  mov     [rax+8], rsi
0x1400242b4  test    rcx, rcx
0x1400242b7  jz      short loc_14002428E
0x1400242b9  mov     edx, 676C6462h; Tag
0x1400242be  call    cs:__imp_ExFreePoolWithTag
0x1400242c5  nop     dword ptr [rax+rax+00h]
0x1400242ca  jmp     short loc_14002428E
0x1400242cc  mov     ecx, 3
0x1400242d1  int     29h; Win8: RtlFailFast(ecx)
```
