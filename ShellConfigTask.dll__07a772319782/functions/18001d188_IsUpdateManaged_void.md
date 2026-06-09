# IsUpdateManaged(void)

- ea: `0x18001d188`
- end: `0x18001d29b`
- name: `?IsUpdateManaged@@YA_NXZ`
- size: `275`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b7fc`

## callees

- `0x18001d188`
- `0x18002062c`
- `0x180020e9c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1c7`
- `OLEAUT32!__imp_VariantInit` at `0x18001d1ea`
- `OLEAUT32!__imp_VariantInit` at `0x18001d1ea`
- `OLEAUT32!__imp_VariantClear` at `0x18001d236`
- `OLEAUT32!__imp_VariantClear` at `0x18001d27a`
- `OLEAUT32!__imp_VariantClear` at `0x18001d236`
- `OLEAUT32!__imp_VariantClear` at `0x18001d27a`

## string_xrefs

- `0x18001d220`: `pcshell\shell\aix\shellconfigtask\lib\..\inc\ShellConfigTaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool IsUpdateManaged(void)
{
  LPVOID v0; // rcx
  int v1; // eax
  bool v3; // bl
  __int128 v4; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pvarg[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  LPVOID ppv; // [rsp+80h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl'::`2'::impl);
  ppv = 0;
  CoCreateInstance(&GUID_07369a67_07a6_4608_abea_379491cb7c46, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &ppv);
  v0 = ppv;
  if ( !ppv )
  {
LABEL_5:
    if ( v0 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v0 + 16LL))(v0);
    return 0;
  }
  v4 = 0;
  memset(pvarg, 0, sizeof(pvarg));
  VariantInit((VARIANTARG *)pvarg);
  v1 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)ppv + 32LL))(ppv, 63, &v4);
  if ( v1 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2E0,
      (int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\..\\inc\\ShellConfigTaskHelpers.h",
      (const char *)(unsigned int)v1);
LABEL_4:
    VariantClear((VARIANTARG *)pvarg);
    v0 = ppv;
    goto LABEL_5;
  }
  if ( DWORD1(v4) != 1 || *(_WORD *)pvarg != 3 )
    goto LABEL_4;
  v3 = *(_DWORD *)&pvarg[8] == 1;
  VariantClear((VARIANTARG *)pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v3;
}

```

## disassembly

```asm
0x18001d188  mov     [rsp-8+arg_8], rbx
0x18001d18d  push    rbp
0x18001d18e  mov     rbp, rsp
0x18001d191  sub     rsp, 70h
0x18001d195  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769107@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107> `wil::Feature<__WilFeatureTraits_Feature_56769107>::GetImpl(void)'::`2'::impl
0x18001d19c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769107@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769107>::__private_IsEnabled(void)
0x18001d1a1  nop
0x18001d1a2  mov     [rbp+arg_0], 0
0x18001d1aa  lea     rax, [rbp+arg_0]
0x18001d1ae  mov     [rsp+70h+ppv], rax; int
0x18001d1b3  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18001d1ba  xor     edx, edx; pUnkOuter
0x18001d1bc  lea     r8d, [rdx+1]; dwClsContext
0x18001d1c0  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18001d1c7  call    cs:__imp_CoCreateInstance
0x18001d1cd  nop
0x18001d1ce  mov     rcx, [rbp+arg_0]
0x18001d1d2  test    rcx, rcx
0x18001d1d5  jz      short loc_18001D240
0x18001d1d7  xorps   xmm0, xmm0
0x18001d1da  movups  [rbp+var_30], xmm0
0x18001d1de  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d1e2  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x18001d1e6  lea     rcx, [rbp+pvarg]; pvarg
0x18001d1ea  call    cs:__imp_VariantInit
0x18001d1f0  lea     rax, [rbp+var_30]
0x18001d1f4  mov     [rbp+var_40], rax
0x18001d1f8  mov     [rbp+var_38], 1
0x18001d1fc  mov     rcx, [rbp+arg_0]
0x18001d200  mov     rax, [rcx]
0x18001d203  lea     r8, [rbp+var_30]
0x18001d207  mov     edx, 3Fh ; '?'
0x18001d20c  mov     rax, [rax+20h]
0x18001d210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d215  mov     rcx, [rbp+8]; this
0x18001d219  test    eax, eax
0x18001d21b  jns     short loc_18001D262
0x18001d21d  mov     r9d, eax; char *
0x18001d220  lea     r8, aPcshellShellAi_0; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x18001d227  mov     edx, 2E0h; void *
0x18001d22c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d231  nop
0x18001d232  lea     rcx, [rbp+pvarg]; pvarg
0x18001d236  call    cs:__imp_VariantClear
0x18001d23c  mov     rcx, [rbp+arg_0]
0x18001d240  test    rcx, rcx
0x18001d243  jz      short loc_18001D252
0x18001d245  mov     rax, [rcx]
0x18001d248  mov     rax, [rax+10h]
0x18001d24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d251  nop
0x18001d252  xor     al, al
0x18001d254  mov     rbx, [rsp+70h+arg_8]
0x18001d25c  add     rsp, 70h
0x18001d260  pop     rbp
0x18001d261  retn
0x18001d262  cmp     dword ptr [rbp+var_30+4], 1
0x18001d266  jnz     short loc_18001D232
0x18001d268  cmp     word ptr [rbp+pvarg], 3
0x18001d26d  jnz     short loc_18001D232
0x18001d26f  cmp     dword ptr [rbp+pvarg+8], 1
0x18001d273  setz    bl
0x18001d276  lea     rcx, [rbp+pvarg]; pvarg
0x18001d27a  call    cs:__imp_VariantClear
0x18001d280  nop
0x18001d281  mov     rcx, [rbp+arg_0]
0x18001d285  test    rcx, rcx
0x18001d288  jz      short loc_18001D297
0x18001d28a  mov     rdx, [rcx]
0x18001d28d  mov     rax, [rdx+10h]
0x18001d291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d296  nop
0x18001d297  mov     al, bl
0x18001d299  jmp     short loc_18001D254
```
