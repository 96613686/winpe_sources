# IsEnterprisePolicyConfigured

- ea: `0x18000b9a8`
- end: `0x18000ba70`
- name: `IsEnterprisePolicyConfigured`
- size: `200`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f418`

## callees

- `0x18000b9a8`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ba03`
- `OLEAUT32!__imp_VariantInit` at `0x18000ba03`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba43`
- `OLEAUT32!__imp_VariantClear` at `0x18000ba43`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b9de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b9de`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char IsEnterprisePolicyConfigured()
{
  char v0; // bl
  __int128 v2; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pvarg[32]; // [rsp+50h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+88h] [rbp+18h] BYREF

  ppv = 0;
  v0 = 1;
  CoCreateInstance(&GUID_07369a67_07a6_4608_abea_379491cb7c46, 0, 1u, &GUID_152807bd_4d18_46c5_ae31_dd8d597d0559, &ppv);
  if ( !ppv )
    return 0;
  v2 = 0;
  memset(pvarg, 0, sizeof(pvarg));
  VariantInit((VARIANTARG *)pvarg);
  if ( (*(int (__fastcall **)(LPVOID, __int64, __int128 *))(*(_QWORD *)ppv + 32LL))(ppv, 63, &v2) < 0
    || DWORD1(v2) != 1
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
0x18000b9a8  mov     [rsp-8+arg_0], rbx
0x18000b9ad  push    rbp
0x18000b9ae  mov     rbp, rsp
0x18000b9b1  sub     rsp, 70h
0x18000b9b5  mov     [rbp+arg_8], 0
0x18000b9bd  lea     rax, [rbp+arg_8]
0x18000b9c1  mov     [rsp+70h+ppv], rax; ppv
0x18000b9c6  lea     r9, _GUID_152807bd_4d18_46c5_ae31_dd8d597d0559; riid
0x18000b9cd  mov     ebx, 1
0x18000b9d2  mov     r8d, ebx; dwClsContext
0x18000b9d5  xor     edx, edx; pUnkOuter
0x18000b9d7  lea     rcx, _GUID_07369a67_07a6_4608_abea_379491cb7c46; rclsid
0x18000b9de  call    cs:__imp_CoCreateInstance
0x18000b9e4  nop
0x18000b9e5  cmp     [rbp+arg_8], 0
0x18000b9ea  jnz     short loc_18000B9F0
0x18000b9ec  xor     al, al
0x18000b9ee  jmp     short loc_18000BA62
0x18000b9f0  xorps   xmm0, xmm0
0x18000b9f3  movups  [rbp+var_30], xmm0
0x18000b9f7  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b9fb  movups  xmmword ptr [rbp+pvarg+10h], xmm0
0x18000b9ff  lea     rcx, [rbp+pvarg]; pvarg
0x18000ba03  call    cs:__imp_VariantInit
0x18000ba09  lea     rax, [rbp+var_30]
0x18000ba0d  mov     [rbp+var_40], rax
0x18000ba11  mov     [rbp+var_38], bl
0x18000ba14  mov     rcx, [rbp+arg_8]
0x18000ba18  mov     rax, [rcx]
0x18000ba1b  lea     r8, [rbp+var_30]
0x18000ba1f  mov     edx, 3Fh ; '?'
0x18000ba24  mov     rax, [rax+20h]
0x18000ba28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba2d  test    eax, eax
0x18000ba2f  js      short loc_18000BA3D
0x18000ba31  cmp     dword ptr [rbp+var_30+4], ebx
0x18000ba34  jnz     short loc_18000BA3D
0x18000ba36  cmp     word ptr [rbp+pvarg], 3
0x18000ba3b  jz      short loc_18000BA3F
0x18000ba3d  xor     bl, bl
0x18000ba3f  lea     rcx, [rbp+pvarg]; pvarg
0x18000ba43  call    cs:__imp_VariantClear
0x18000ba49  nop
0x18000ba4a  mov     rcx, [rbp+arg_8]
0x18000ba4e  test    rcx, rcx
0x18000ba51  jz      short loc_18000BA60
0x18000ba53  mov     rdx, [rcx]
0x18000ba56  mov     rax, [rdx+10h]
0x18000ba5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5f  nop
0x18000ba60  mov     al, bl
0x18000ba62  mov     rbx, [rsp+70h+arg_0]
0x18000ba6a  add     rsp, 70h
0x18000ba6e  pop     rbp
0x18000ba6f  retn
```
