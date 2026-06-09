# AipRequireElevationPrompt(ulong,ulong *,void *)

- ea: `0x180016fa0`
- end: `0x1800170ff`
- name: `?AipRequireElevationPrompt@@YAJKPEAKPEAX@Z`
- size: `351`
- prototype: `int(unsigned int, unsigned int *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180016da4`

## callees

- `0x180011ff8`
- `0x180016a40`
- `0x180016fa0`
- `0x180022b74`
- `0x180043f6c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001702e`
- `ntdll!NtQueryInformationToken` at `0x18001702e`

## pseudocode

```c
__int64 __fastcall AipRequireElevationPrompt(int a1, unsigned int *a2, void *a3)
{
  NTSTATUS v3; // esi
  int TokenInformation; // [rsp+30h] [rbp-18h] BYREF
  ULONG ReturnLength[5]; // [rsp+34h] [rbp-14h] BYREF
  int v10; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v10 = 0;
  TokenInformation = 0;
  ReturnLength[0] = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl) )
  {
    if ( !a1 )
    {
      *a2 |= 0x10u;
      if ( !(unsigned int)LUAIsShadowAdminEnabled() || (*a2 & 0x40000004) != 4 )
        return (unsigned int)v3;
      *a2 &= ~0x10u;
    }
  }
  else if ( !a1 )
  {
    goto LABEL_17;
  }
  if ( (*a2 & 0x2000000) != 0 )
  {
LABEL_20:
    v3 = AiCheckForAdminUser(a3, (*a2 >> 25) & 1, &v10);
    if ( v3 >= 0 )
    {
      *a2 |= v10 != 0 ? 32 : 64;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl) )
      {
        if ( !a1 && (*a2 & 0x40) != 0 )
          *a2 |= 0x10u;
      }
    }
    return (unsigned int)v3;
  }
  v3 = NtQueryInformationToken(a3, TokenElevationType, &TokenInformation, 4u, ReturnLength);
  if ( v3 < 0 )
    return (unsigned int)v3;
  if ( TokenInformation == 2 )
  {
LABEL_17:
    *a2 |= 0x10u;
    return (unsigned int)v3;
  }
  if ( TokenInformation != 1 )
  {
    if ( a1 == 1 )
      *a2 |= 0x200u;
    goto LABEL_20;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl)
    && !a1 )
  {
    goto LABEL_17;
  }
  if ( a1 == 1 )
    goto LABEL_17;
  v3 = AiCheckForElevatedUser(a3, &v10);
  if ( v3 >= 0 )
  {
    if ( v10 )
      goto LABEL_17;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016fa0  mov     rax, rsp
0x180016fa3  mov     [rax+8], rbx
0x180016fa7  mov     [rax+10h], rbp
0x180016fab  mov     [rax+18h], rsi
0x180016faf  push    rdi
0x180016fb0  sub     rsp, 40h
0x180016fb4  xor     esi, esi
0x180016fb6  mov     rbp, r8
0x180016fb9  and     [rax+20h], esi
0x180016fbc  mov     rbx, rdx
0x180016fbf  and     [rax-18h], esi
0x180016fc2  mov     edi, ecx
0x180016fc4  and     [rax-14h], esi
0x180016fc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2045735225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225> `wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl(void)'::`2'::impl
0x180016fce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(void)
0x180016fd3  test    al, al
0x180016fd5  jz      loc_180017087
0x180016fdb  test    edi, edi
0x180016fdd  jnz     short loc_180017006
0x180016fdf  or      dword ptr [rbx], 10h
0x180016fe2  call    LUAIsShadowAdminEnabled
0x180016fe7  test    eax, eax
0x180016fe9  jz      loc_1800170E7
0x180016fef  mov     ecx, [rbx]
0x180016ff1  mov     eax, ecx
0x180016ff3  and     eax, 40000004h
0x180016ff8  cmp     eax, 4
0x180016ffb  jnz     loc_1800170E7
0x180017001  and     ecx, 0FFFFFFEFh
0x180017004  mov     [rbx], ecx
0x180017006  test    dword ptr [rbx], 2000000h
0x18001700c  jnz     loc_18001709D
0x180017012  mov     r9d, 4; TokenInformationLength
0x180017018  lea     rax, [rsp+48h+var_14]
0x18001701d  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180017022  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180017027  mov     rcx, rbp; TokenHandle
0x18001702a  lea     edx, [r9+0Eh]; TokenInformationClass
0x18001702e  call    cs:__imp_NtQueryInformationToken
0x180017035  nop     dword ptr [rax+rax+00h]
0x18001703a  mov     esi, eax
0x18001703c  test    eax, eax
0x18001703e  js      loc_1800170E7
0x180017044  cmp     [rsp+48h+TokenInformation], 2
0x180017049  jz      short loc_18001708F
0x18001704b  cmp     [rsp+48h+TokenInformation], 1
0x180017050  jnz     short loc_180017094
0x180017052  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2045735225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225> `wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl(void)'::`2'::impl
0x180017059  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(void)
0x18001705e  test    al, al
0x180017060  jz      short loc_180017066
0x180017062  test    edi, edi
0x180017064  jz      short loc_18001708F
0x180017066  cmp     edi, 1
0x180017069  jz      short loc_18001708F
0x18001706b  lea     rdx, [rsp+48h+arg_18]; int *
0x180017070  mov     rcx, rbp; void *
0x180017073  call    ?AiCheckForElevatedUser@@YAJPEAXPEAH@Z; AiCheckForElevatedUser(void *,int *)
0x180017078  mov     esi, eax
0x18001707a  test    eax, eax
0x18001707c  js      short loc_1800170E7
0x18001707e  cmp     [rsp+48h+arg_18], 0
0x180017083  jz      short loc_1800170E7
0x180017085  jmp     short loc_18001708F
0x180017087  test    edi, edi
0x180017089  jnz     loc_180017006
0x18001708f  or      dword ptr [rbx], 10h
0x180017092  jmp     short loc_1800170E7
0x180017094  cmp     edi, 1
0x180017097  jnz     short loc_18001709D
0x180017099  bts     dword ptr [rbx], 9
0x18001709d  mov     edx, [rbx]
0x18001709f  lea     r8, [rsp+48h+arg_18]; int *
0x1800170a4  shr     edx, 19h
0x1800170a7  mov     rcx, rbp; Handle
0x1800170aa  and     edx, 1; int
0x1800170ad  call    ?AiCheckForAdminUser@@YAJPEAXHPEAH@Z; AiCheckForAdminUser(void *,int,int *)
0x1800170b2  mov     esi, eax
0x1800170b4  test    eax, eax
0x1800170b6  js      short loc_1800170E7
0x1800170b8  mov     eax, [rsp+48h+arg_18]
0x1800170bc  neg     eax
0x1800170be  sbb     ecx, ecx
0x1800170c0  and     ecx, 0FFFFFFE0h
0x1800170c3  add     ecx, 40h ; '@'
0x1800170c6  or      [rbx], ecx
0x1800170c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2045735225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225> `wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl(void)'::`2'::impl
0x1800170cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(void)
0x1800170d4  test    al, al
0x1800170d6  jz      short loc_1800170E7
0x1800170d8  test    edi, edi
0x1800170da  jnz     short loc_1800170E7
0x1800170dc  mov     eax, [rbx]
0x1800170de  test    al, 40h
0x1800170e0  jz      short loc_1800170E7
0x1800170e2  or      eax, 10h
0x1800170e5  mov     [rbx], eax
0x1800170e7  mov     rbx, [rsp+48h+arg_0]
0x1800170ec  mov     eax, esi
0x1800170ee  mov     rsi, [rsp+48h+arg_10]
0x1800170f3  mov     rbp, [rsp+48h+arg_8]
0x1800170f8  add     rsp, 40h
0x1800170fc  pop     rdi
0x1800170fd  retn
```
