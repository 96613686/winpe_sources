# CRuleHandler::CompareChecksums(IWICMetadataQueryReader *,RULE_PATH_INFO const *,int *)

- ea: `0x18000dbd0`
- end: `0x18000dccc`
- name: `?CompareChecksums@CRuleHandler@@KAJPEAUIWICMetadataQueryReader@@PEBURULE_PATH_INFO@@PEAH@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct IWICMetadataQueryReader *, const struct RULE_PATH_INFO *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011838`

## callees

- `0x18000dbd0`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dc1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dc4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dc1d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000dc4e`
- `PROPSYS!PropVariantCompareEx` at `0x18000dcb6`
- `PROPSYS!PropVariantCompareEx` at `0x18000dcb6`

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
0x18000dbd0  push    rbx
0x18000dbd2  push    rbp
0x18000dbd3  push    rsi
0x18000dbd4  push    rdi
0x18000dbd5  sub     rsp, 58h
0x18000dbd9  mov     rsi, r8
0x18000dbdc  mov     rbp, rdx
0x18000dbdf  mov     rdi, rcx
0x18000dbe2  mov     dword ptr [r8], 0
0x18000dbe9  xorps   xmm0, xmm0
0x18000dbec  xor     eax, eax
0x18000dbee  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x18000dbf3  mov     qword ptr [rsp+78h+pvar+10h], rax
0x18000dbf8  mov     rax, [rcx]
0x18000dbfb  lea     r8, [rsp+78h+pvar]
0x18000dc00  mov     rdx, [rdx+30h]
0x18000dc04  mov     rax, [rax+28h]
0x18000dc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc0d  mov     ebx, eax
0x18000dc0f  cmp     eax, 88982F40h
0x18000dc14  jnz     short loc_18000DC2E
0x18000dc16  xor     ebx, ebx
0x18000dc18  lea     rcx, [rsp+78h+pvar]; pvar
0x18000dc1d  call    cs:__imp_PropVariantClear
0x18000dc23  mov     eax, ebx
0x18000dc25  add     rsp, 58h
0x18000dc29  pop     rdi
0x18000dc2a  pop     rsi
0x18000dc2b  pop     rbp
0x18000dc2c  pop     rbx
0x18000dc2d  retn
0x18000dc2e  xorps   xmm0, xmm0
0x18000dc31  xor     eax, eax
0x18000dc33  movups  xmmword ptr [rsp+78h+propvar2], xmm0
0x18000dc38  mov     qword ptr [rsp+78h+propvar2+10h], rax
0x18000dc3d  test    ebx, ebx
0x18000dc3f  jns     short loc_18000DC5F
0x18000dc41  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18000dc47  jnz     short loc_18000DC56
0x18000dc49  lea     rcx, [rsp+78h+propvar2]; pvar
0x18000dc4e  call    cs:__imp_PropVariantClear
0x18000dc54  jmp     short loc_18000DC18
0x18000dc56  mov     ecx, ebx; int
0x18000dc58  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000dc5d  jmp     short loc_18000DC49
0x18000dc5f  mov     rax, [rdi]
0x18000dc62  lea     r8, [rsp+78h+propvar2]
0x18000dc67  mov     rdx, [rbp+38h]
0x18000dc6b  mov     rcx, rdi
0x18000dc6e  mov     rax, [rax+28h]
0x18000dc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc77  mov     ebx, eax
0x18000dc79  cmp     eax, 88982F40h
0x18000dc7e  jz      short loc_18000DC96
0x18000dc80  test    eax, eax
0x18000dc82  jns     short loc_18000DC9A
0x18000dc84  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000dc8b  jz      short loc_18000DC49
0x18000dc8d  mov     ecx, eax; int
0x18000dc8f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000dc94  jmp     short loc_18000DC49
0x18000dc96  xor     ebx, ebx
0x18000dc98  jmp     short loc_18000DC49
0x18000dc9a  movzx   eax, word ptr [rsp+78h+propvar2]
0x18000dc9f  cmp     word ptr [rsp+78h+pvar], ax
0x18000dca4  jnz     short loc_18000DCC4
0x18000dca6  xor     r9d, r9d; flags
0x18000dca9  xor     r8d, r8d; unit
0x18000dcac  lea     rdx, [rsp+78h+propvar2]; propvar2
0x18000dcb1  lea     rcx, [rsp+78h+pvar]; propvar1
0x18000dcb6  call    cs:__imp_PropVariantCompareEx
0x18000dcbc  test    eax, eax
0x18000dcbe  jnz     short loc_18000DCC4
0x18000dcc0  mov     [rsi], eax
0x18000dcc2  jmp     short loc_18000DC49
0x18000dcc4  mov     eax, 1
0x18000dcc9  jmp     short loc_18000DCC0
```
