# CRuleReader::CheckPathAllowed(RULE_PATH_INFO const *,int *)

- ea: `0x18000a170`
- end: `0x18000a2a7`
- name: `?CheckPathAllowed@CRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAH@Z`
- size: `311`
- prototype: `__int64 __fastcall(CRuleReader *__hidden this, const struct RULE_PATH_INFO *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a170`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a1d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a216`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a1d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a216`
- `PROPSYS!PropVariantCompareEx` at `0x18000a28d`
- `PROPSYS!PropVariantCompareEx` at `0x18000a28d`

## pseudocode

```c
__int64 __fastcall CRuleReader::CheckPathAllowed(CRuleReader *this, const struct RULE_PATH_INFO *a2, int *a3)
{
  __int64 result; // rax
  BOOL v6; // esi
  __int64 v7; // r14
  int v8; // ebp
  int v9; // eax
  PROPVARIANT propvar2; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-40h] BYREF

  result = 0;
  v6 = 1;
  *a3 = 1;
  if ( *((_QWORD *)a2 + 6) )
  {
    v7 = *((_QWORD *)this + 5);
    *a3 = 0;
    memset(&pvar, 0, sizeof(pvar));
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v7 + 40LL))(
           v7,
           *((_QWORD *)a2 + 6),
           &pvar);
    if ( v8 == -2003292352 )
    {
      v8 = 0;
    }
    else
    {
      memset(&propvar2, 0, sizeof(propvar2));
      if ( v8 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)v7 + 40LL))(
               v7,
               *((_QWORD *)a2 + 7),
               &propvar2);
        v8 = v9;
        if ( v9 == -2003292352 )
        {
          v8 = 0;
        }
        else if ( v9 >= 0 )
        {
          if ( pvar.vt == propvar2.vt )
            v6 = PropVariantCompareEx(&pvar, &propvar2, PVCU_DEFAULT, 0) != 0;
          *a3 = v6;
        }
        else if ( g_doStackCaptures )
        {
          DoStackCapture(v9);
        }
      }
      else if ( g_doStackCaptures )
      {
        DoStackCapture(v8);
      }
      PropVariantClear(&propvar2);
    }
    PropVariantClear(&pvar);
    if ( v8 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v8);
    }
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000a170  push    rbx
0x18000a172  push    rbp
0x18000a173  push    rsi
0x18000a174  push    rdi
0x18000a175  push    r14
0x18000a177  sub     rsp, 50h
0x18000a17b  mov     rdi, r8
0x18000a17e  mov     rbx, rdx
0x18000a181  xor     eax, eax
0x18000a183  mov     esi, 1
0x18000a188  mov     [r8], esi
0x18000a18b  cmp     [rdx+30h], rax
0x18000a18f  jnz     short loc_18000A19D
0x18000a191  add     rsp, 50h
0x18000a195  pop     r14
0x18000a197  pop     rdi
0x18000a198  pop     rsi
0x18000a199  pop     rbp
0x18000a19a  pop     rbx
0x18000a19b  retn
0x18000a19d  mov     r14, [rcx+28h]
0x18000a1a1  mov     [r8], eax
0x18000a1a4  xorps   xmm0, xmm0
0x18000a1a7  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x18000a1ac  mov     qword ptr [rsp+78h+pvar+10h], rax
0x18000a1b1  mov     rax, [r14]
0x18000a1b4  lea     r8, [rsp+78h+pvar]
0x18000a1b9  mov     rdx, [rdx+30h]
0x18000a1bd  mov     rcx, r14
0x18000a1c0  mov     rax, [rax+28h]
0x18000a1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1c9  mov     ebp, eax
0x18000a1cb  cmp     eax, 88982F40h
0x18000a1d0  jnz     short loc_18000A1F6
0x18000a1d2  xor     ebp, ebp
0x18000a1d4  lea     rcx, [rsp+78h+pvar]; pvar
0x18000a1d9  call    cs:__imp_PropVariantClear
0x18000a1e0  nop     dword ptr [rax+rax+00h]
0x18000a1e5  test    ebp, ebp
0x18000a1e7  jns     short loc_18000A1F2
0x18000a1e9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a1f0  jnz     short loc_18000A224
0x18000a1f2  mov     eax, ebp
0x18000a1f4  jmp     short loc_18000A191
0x18000a1f6  xorps   xmm0, xmm0
0x18000a1f9  xor     eax, eax
0x18000a1fb  movups  xmmword ptr [rsp+78h+propvar2], xmm0
0x18000a200  mov     qword ptr [rsp+78h+propvar2+10h], rax
0x18000a205  test    ebp, ebp
0x18000a207  jns     short loc_18000A236
0x18000a209  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18000a20f  jnz     short loc_18000A22D
0x18000a211  lea     rcx, [rsp+78h+propvar2]; pvar
0x18000a216  call    cs:__imp_PropVariantClear
0x18000a21d  nop     dword ptr [rax+rax+00h]
0x18000a222  jmp     short loc_18000A1D4
0x18000a224  mov     ecx, ebp; int
0x18000a226  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a22b  jmp     short loc_18000A1F2
0x18000a22d  mov     ecx, ebp; int
0x18000a22f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a234  jmp     short loc_18000A211
0x18000a236  mov     rax, [r14]
0x18000a239  lea     r8, [rsp+78h+propvar2]
0x18000a23e  mov     rdx, [rbx+38h]
0x18000a242  mov     rcx, r14
0x18000a245  mov     rax, [rax+28h]
0x18000a249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24e  mov     ebp, eax
0x18000a250  cmp     eax, 88982F40h
0x18000a255  jz      short loc_18000A26D
0x18000a257  test    eax, eax
0x18000a259  jns     short loc_18000A271
0x18000a25b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a262  jz      short loc_18000A211
0x18000a264  mov     ecx, eax; int
0x18000a266  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a26b  jmp     short loc_18000A211
0x18000a26d  xor     ebp, ebp
0x18000a26f  jmp     short loc_18000A211
0x18000a271  movzx   eax, word ptr [rsp+78h+propvar2]
0x18000a276  cmp     word ptr [rsp+78h+pvar], ax
0x18000a27b  jnz     short loc_18000A29F
0x18000a27d  xor     r9d, r9d; flags
0x18000a280  xor     r8d, r8d; unit
0x18000a283  lea     rdx, [rsp+78h+propvar2]; propvar2
0x18000a288  lea     rcx, [rsp+78h+pvar]; propvar1
0x18000a28d  call    cs:__imp_PropVariantCompareEx
0x18000a294  nop     dword ptr [rax+rax+00h]
0x18000a299  test    eax, eax
0x18000a29b  jnz     short loc_18000A29F
0x18000a29d  xor     esi, esi
0x18000a29f  mov     [rdi], esi
0x18000a2a1  jmp     loc_18000A211
```
