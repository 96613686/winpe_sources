# CBootCfg::OpenStore(ushort const *)

- ea: `0x18005209c`
- end: `0x1800521b7`
- name: `?OpenStore@CBootCfg@@AEAAKPEBG@Z`
- size: `283`
- prototype: `unsigned int __fastcall(CBootCfg *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180051d24`
- `0x180051dc8`
- `0x180051e68`

## callees

- `0x18001efcc`
- `0x18004f8d0`
- `0x18005209c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180052151`
- `ntdll!RtlInitUnicodeString` at `0x180052151`
- `ntdll!RtlNtStatusToDosError` at `0x18005219e`
- `ntdll!RtlNtStatusToDosError` at `0x18005219e`
- `bcd!BcdOpenStore` at `0x1800520e5`
- `bcd!BcdOpenStore` at `0x1800520e5`
- `bcd!BcdOpenSystemStore` at `0x180052120`
- `bcd!BcdOpenSystemStore` at `0x180052120`
- `bcd!BcdOpenStoreFromFile` at `0x18005215f`
- `bcd!BcdOpenStoreFromFile` at `0x18005215f`

## pseudocode

```c
ULONG __fastcall CBootCfg::OpenStore(CBootCfg *this, const unsigned __int16 *a2)
{
  bool v2; // zf
  NTSTATUS v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF

  v2 = *(_QWORD *)this == 0;
  DestinationString = 0;
  if ( !v2 )
    return 0;
  if ( a2 )
  {
    RtlInitUnicodeString(&DestinationString, a2);
    v5 = BcdOpenStoreFromFile(&DestinationString, this);
    if ( v5 >= 0 )
      return RtlNtStatusToDosError(v5);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return RtlNtStatusToDosError(v5);
    v7 = 17;
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl'::`2'::impl) )
  {
    v5 = BcdOpenStore(0, 0, this);
    if ( v5 >= 0 )
      return RtlNtStatusToDosError(v5);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return RtlNtStatusToDosError(v5);
    v7 = 15;
  }
  else
  {
    v5 = BcdOpenSystemStore(this);
    if ( v5 >= 0 )
      return RtlNtStatusToDosError(v5);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return RtlNtStatusToDosError(v5);
    v7 = 16;
  }
  WPP_SF_d(v6[2], v7, WPP_ae5fadc35b653f72a4834fe07b0ad776_Traceguids, (unsigned int)v5);
  return RtlNtStatusToDosError(v5);
}

```

## disassembly

```asm
0x18005209c  push    rbx
0x18005209e  sub     rsp, 40h
0x1800520a2  mov     rax, cs:__security_cookie
0x1800520a9  xor     rax, rsp
0x1800520ac  mov     [rsp+48h+var_18], rax
0x1800520b1  cmp     qword ptr [rcx], 0
0x1800520b5  xorps   xmm0, xmm0
0x1800520b8  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1800520bd  mov     rbx, rcx
0x1800520c0  jz      short loc_1800520C9
0x1800520c2  xor     eax, eax
0x1800520c4  jmp     loc_1800521A4
0x1800520c9  test    rdx, rdx
0x1800520cc  jnz     short loc_18005214C
0x1800520ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl(void)'::`2'::impl
0x1800520d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)
0x1800520da  test    al, al
0x1800520dc  jz      short loc_18005211D
0x1800520de  mov     r8, rbx
0x1800520e1  xor     edx, edx
0x1800520e3  xor     ecx, ecx
0x1800520e5  call    cs:__imp_BcdOpenStore
0x1800520eb  mov     ebx, eax
0x1800520ed  test    eax, eax
0x1800520ef  jns     loc_18005219C
0x1800520f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800520fc  lea     rax, WPP_GLOBAL_Control
0x180052103  cmp     rcx, rax
0x180052106  jz      loc_18005219C
0x18005210c  test    byte ptr [rcx+1Ch], 2
0x180052110  jz      loc_18005219C
0x180052116  mov     edx, 0Fh
0x18005211b  jmp     short loc_180052189
0x18005211d  mov     rcx, rbx
0x180052120  call    cs:__imp_BcdOpenSystemStore
0x180052126  mov     ebx, eax
0x180052128  test    eax, eax
0x18005212a  jns     short loc_18005219C
0x18005212c  mov     rcx, cs:WPP_GLOBAL_Control
0x180052133  lea     rax, WPP_GLOBAL_Control
0x18005213a  cmp     rcx, rax
0x18005213d  jz      short loc_18005219C
0x18005213f  test    byte ptr [rcx+1Ch], 2
0x180052143  jz      short loc_18005219C
0x180052145  mov     edx, 10h; SourceString
0x18005214a  jmp     short loc_180052189
0x18005214c  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x180052151  call    cs:__imp_RtlInitUnicodeString
0x180052157  mov     rdx, rbx
0x18005215a  lea     rcx, [rsp+48h+DestinationString]
0x18005215f  call    cs:__imp_BcdOpenStoreFromFile
0x180052165  mov     ebx, eax
0x180052167  test    eax, eax
0x180052169  jns     short loc_18005219C
0x18005216b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052172  lea     rax, WPP_GLOBAL_Control
0x180052179  cmp     rcx, rax
0x18005217c  jz      short loc_18005219C
0x18005217e  test    byte ptr [rcx+1Ch], 2
0x180052182  jz      short loc_18005219C
0x180052184  mov     edx, 11h
0x180052189  mov     rcx, [rcx+10h]
0x18005218d  lea     r8, WPP_ae5fadc35b653f72a4834fe07b0ad776_Traceguids
0x180052194  mov     r9d, ebx
0x180052197  call    WPP_SF_d
0x18005219c  mov     ecx, ebx; Status
0x18005219e  call    cs:__imp_RtlNtStatusToDosError
0x1800521a4  mov     rcx, [rsp+48h+var_18]
0x1800521a9  xor     rcx, rsp; StackCookie
0x1800521ac  call    __security_check_cookie
0x1800521b1  add     rsp, 40h
0x1800521b5  pop     rbx
0x1800521b6  retn
```
