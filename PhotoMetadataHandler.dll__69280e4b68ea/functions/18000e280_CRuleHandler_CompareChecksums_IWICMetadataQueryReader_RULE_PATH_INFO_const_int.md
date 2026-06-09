# CRuleHandler::CompareChecksums(IWICMetadataQueryReader *,RULE_PATH_INFO const *,int *)

- ea: `0x18000e280`
- end: `0x18000e392`
- name: `?CompareChecksums@CRuleHandler@@KAJPEAUIWICMetadataQueryReader@@PEBURULE_PATH_INFO@@PEAH@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, const struct RULE_PATH_INFO *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x18000e280`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e2cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e305`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e2cd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000e305`
- `PROPSYS!PropVariantCompareEx` at `0x18000e373`
- `PROPSYS!PropVariantCompareEx` at `0x18000e373`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRuleHandler::CompareChecksums(
        struct IWICMetadataQueryReader *a1,
        const struct RULE_PATH_INFO *a2,
        int *a3)
{
  int v6; // ebx
  int v8; // eax
  int v9; // eax
  PROPVARIANT propvar2; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-40h] BYREF

  *a3 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v6 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, _QWORD, PROPVARIANT *))a1->lpVtbl->GetMetadataByName)(
         a1,
         *((_QWORD *)a2 + 6),
         &pvar);
  if ( v6 == -2003292352 )
  {
    v6 = 0;
  }
  else
  {
    memset(&propvar2, 0, sizeof(propvar2));
    if ( v6 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, _QWORD, PROPVARIANT *))a1->lpVtbl->GetMetadataByName)(
             a1,
             *((_QWORD *)a2 + 7),
             &propvar2);
      v6 = v8;
      if ( v8 == -2003292352 )
      {
        v6 = 0;
      }
      else if ( v8 >= 0 )
      {
        if ( pvar.vt != propvar2.vt || (v9 = PropVariantCompareEx(&pvar, &propvar2, PVCU_DEFAULT, 0)) != 0 )
          v9 = 1;
        *a3 = v9;
      }
      else if ( g_doStackCaptures )
      {
        DoStackCapture(v8);
      }
    }
    else if ( g_doStackCaptures )
    {
      DoStackCapture(v6);
    }
    PropVariantClear(&propvar2);
  }
  PropVariantClear(&pvar);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e280  push    rbx
0x18000e282  push    rbp
0x18000e283  push    rsi
0x18000e284  push    rdi
0x18000e285  sub     rsp, 58h
0x18000e289  mov     rsi, r8
0x18000e28c  mov     rbp, rdx
0x18000e28f  mov     rdi, rcx
0x18000e292  mov     dword ptr [r8], 0
0x18000e299  xorps   xmm0, xmm0
0x18000e29c  xor     eax, eax
0x18000e29e  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x18000e2a3  mov     qword ptr [rsp+78h+pvar+10h], rax
0x18000e2a8  mov     rax, [rcx]
0x18000e2ab  lea     r8, [rsp+78h+pvar]
0x18000e2b0  mov     rdx, [rdx+30h]
0x18000e2b4  mov     rax, [rax+28h]
0x18000e2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2bd  mov     ebx, eax
0x18000e2bf  cmp     eax, 88982F40h
0x18000e2c4  jnz     short loc_18000E2E5
0x18000e2c6  xor     ebx, ebx
0x18000e2c8  lea     rcx, [rsp+78h+pvar]; pvar
0x18000e2cd  call    cs:__imp_PropVariantClear
0x18000e2d4  nop     dword ptr [rax+rax+00h]
0x18000e2d9  mov     eax, ebx
0x18000e2db  add     rsp, 58h
0x18000e2df  pop     rdi
0x18000e2e0  pop     rsi
0x18000e2e1  pop     rbp
0x18000e2e2  pop     rbx
0x18000e2e3  retn
0x18000e2e5  xorps   xmm0, xmm0
0x18000e2e8  xor     eax, eax
0x18000e2ea  movups  xmmword ptr [rsp+78h+propvar2], xmm0
0x18000e2ef  mov     qword ptr [rsp+78h+propvar2+10h], rax
0x18000e2f4  test    ebx, ebx
0x18000e2f6  jns     short loc_18000E31C
0x18000e2f8  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18000e2fe  jnz     short loc_18000E313
0x18000e300  lea     rcx, [rsp+78h+propvar2]; pvar
0x18000e305  call    cs:__imp_PropVariantClear
0x18000e30c  nop     dword ptr [rax+rax+00h]
0x18000e311  jmp     short loc_18000E2C8
0x18000e313  mov     ecx, ebx; int
0x18000e315  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000e31a  jmp     short loc_18000E300
0x18000e31c  mov     rax, [rdi]
0x18000e31f  lea     r8, [rsp+78h+propvar2]
0x18000e324  mov     rdx, [rbp+38h]
0x18000e328  mov     rcx, rdi
0x18000e32b  mov     rax, [rax+28h]
0x18000e32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e334  mov     ebx, eax
0x18000e336  cmp     eax, 88982F40h
0x18000e33b  jz      short loc_18000E353
0x18000e33d  test    eax, eax
0x18000e33f  jns     short loc_18000E357
0x18000e341  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000e348  jz      short loc_18000E300
0x18000e34a  mov     ecx, eax; int
0x18000e34c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000e351  jmp     short loc_18000E300
0x18000e353  xor     ebx, ebx
0x18000e355  jmp     short loc_18000E300
0x18000e357  movzx   eax, word ptr [rsp+78h+propvar2]
0x18000e35c  cmp     word ptr [rsp+78h+pvar], ax
0x18000e361  jnz     short loc_18000E38A
0x18000e363  xor     r9d, r9d; flags
0x18000e366  xor     r8d, r8d; unit
0x18000e369  lea     rdx, [rsp+78h+propvar2]; propvar2
0x18000e36e  lea     rcx, [rsp+78h+pvar]; propvar1
0x18000e373  call    cs:__imp_PropVariantCompareEx
0x18000e37a  nop     dword ptr [rax+rax+00h]
0x18000e37f  test    eax, eax
0x18000e381  jnz     short loc_18000E38A
0x18000e383  mov     [rsi], eax
0x18000e385  jmp     loc_18000E300
0x18000e38a  mov     eax, 1
0x18000e38f  jmp     short loc_18000E383
```
