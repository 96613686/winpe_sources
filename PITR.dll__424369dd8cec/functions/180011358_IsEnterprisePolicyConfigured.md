# IsEnterprisePolicyConfigured

- ea: `0x180011358`
- end: `0x180011440`
- name: `IsEnterprisePolicyConfigured`
- size: `232`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf00`

## callees

- `0x180011358`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800113c4`
- `OLEAUT32!__imp_VariantInit` at `0x1800113c4`
- `OLEAUT32!__imp_VariantClear` at `0x180011404`
- `OLEAUT32!__imp_VariantClear` at `0x180011404`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001139f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001139f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 IsEnterprisePolicyConfigured()
{
  unsigned int v0; // ebx
  LPVOID ppv; // [rsp+40h] [rbp-40h] BYREF
  __int128 v3; // [rsp+48h] [rbp-38h] BYREF
  _BYTE pvarg[32]; // [rsp+58h] [rbp-28h] BYREF

  ppv = 0;
  v0 = 1;
  CoCreateInstance(&GUID_07369a67_07a6_4608_abea_379491cb7c46, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &ppv);
  if ( !ppv )
    return 0;
  v3 = 0;
  memset(pvarg, 0, sizeof(pvarg));
  VariantInit((VARIANTARG *)pvarg);
  if ( (*(int (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)ppv + 32LL))(ppv, 63, &v3) < 0
    || DWORD1(v3) != 1
    || *(_WORD *)pvarg != 3 )
  {
    v0 = 0;
  }
  VariantClear((VARIANTARG *)pvarg);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v0;
}

```

## disassembly

```asm
0x180011358  mov     [rsp-8+arg_0], rbx
0x18001135d  push    rbp
0x18001135e  mov     rbp, rsp
0x180011361  sub     rsp, 80h
0x180011368  mov     rax, cs:__security_cookie
0x18001136f  xor     rax, rsp
0x180011372  mov     [rbp+var_8], rax
0x180011376  mov     [rbp+var_40], 0
0x18001137e  lea     rax, [rbp+var_40]
0x180011382  mov     [rsp+80h+ppv], rax; ppv
0x180011387  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18001138e  mov     ebx, 1
0x180011393  mov     r8d, ebx; dwClsContext
0x180011396  xor     edx, edx; pUnkOuter
0x180011398  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18001139f  call    cs:__imp_CoCreateInstance
0x1800113a5  nop
0x1800113a6  cmp     [rbp+var_40], 0
0x1800113ab  jnz     short loc_1800113B1
0x1800113ad  xor     eax, eax
0x1800113af  jmp     short loc_180011423
0x1800113b1  xorps   xmm0, xmm0
0x1800113b4  movups  [rbp+var_38], xmm0
0x1800113b8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800113bc  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x1800113c0  lea     rcx, [rbp+pvarg]; pvarg
0x1800113c4  call    cs:__imp_VariantInit
0x1800113ca  lea     rax, [rbp+var_38]
0x1800113ce  mov     [rbp+var_50], rax
0x1800113d2  mov     [rbp+var_48], bl
0x1800113d5  mov     rcx, [rbp+var_40]
0x1800113d9  mov     rax, [rcx]
0x1800113dc  lea     r8, [rbp+var_38]
0x1800113e0  mov     edx, 3Fh ; '?'
0x1800113e5  mov     rax, [rax+20h]
0x1800113e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ee  test    eax, eax
0x1800113f0  js      short loc_1800113FE
0x1800113f2  cmp     dword ptr [rbp+var_38+4], ebx
0x1800113f5  jnz     short loc_1800113FE
0x1800113f7  cmp     word ptr [rbp+pvarg], 3
0x1800113fc  jz      short loc_180011400
0x1800113fe  xor     ebx, ebx
0x180011400  lea     rcx, [rbp+pvarg]; pvarg
0x180011404  call    cs:__imp_VariantClear
0x18001140a  nop
0x18001140b  mov     rcx, [rbp+var_40]
0x18001140f  test    rcx, rcx
0x180011412  jz      short loc_180011421
0x180011414  mov     rdx, [rcx]
0x180011417  mov     rax, [rdx+10h]
0x18001141b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011420  nop
0x180011421  mov     eax, ebx
0x180011423  mov     rcx, [rbp+var_8]
0x180011427  xor     rcx, rsp; StackCookie
0x18001142a  call    __security_check_cookie
0x18001142f  mov     rbx, [rsp+80h+arg_0]
0x180011437  add     rsp, 80h
0x18001143e  pop     rbp
0x18001143f  retn
```
