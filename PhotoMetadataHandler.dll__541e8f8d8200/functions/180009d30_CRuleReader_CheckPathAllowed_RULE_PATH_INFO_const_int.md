# CRuleReader::CheckPathAllowed(RULE_PATH_INFO const *,int *)

- ea: `0x180009d30`
- end: `0x180009e54`
- name: `?CheckPathAllowed@CRuleReader@@UEAAJPEBURULE_PATH_INFO@@PEAH@Z`
- size: `292`
- prototype: `__int64 __fastcall(CRuleReader *__hidden this, const struct RULE_PATH_INFO *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009d30`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009d98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009dcf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009d98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009dcf`
- `PROPSYS!PropVariantCompareEx` at `0x180009e40`
- `PROPSYS!PropVariantCompareEx` at `0x180009e40`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180009d30  push    rbx
0x180009d32  push    rbp
0x180009d33  push    rsi
0x180009d34  push    rdi
0x180009d35  push    r14
0x180009d37  sub     rsp, 50h
0x180009d3b  mov     rdi, r8
0x180009d3e  mov     rbx, rdx
0x180009d41  xor     eax, eax
0x180009d43  mov     esi, 1
0x180009d48  mov     [r8], esi
0x180009d4b  cmp     [rdx+30h], rax
0x180009d4f  jnz     short loc_180009D5C
0x180009d51  add     rsp, 50h
0x180009d55  pop     r14
0x180009d57  pop     rdi
0x180009d58  pop     rsi
0x180009d59  pop     rbp
0x180009d5a  pop     rbx
0x180009d5b  retn
0x180009d5c  mov     r14, [rcx+28h]
0x180009d60  mov     [r8], eax
0x180009d63  xorps   xmm0, xmm0
0x180009d66  movups  xmmword ptr [rsp+78h+pvar], xmm0
0x180009d6b  mov     qword ptr [rsp+78h+pvar+10h], rax
0x180009d70  mov     rax, [r14]
0x180009d73  lea     r8, [rsp+78h+pvar]
0x180009d78  mov     rdx, [rdx+30h]
0x180009d7c  mov     rcx, r14
0x180009d7f  mov     rax, [rax+28h]
0x180009d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d88  mov     ebp, eax
0x180009d8a  cmp     eax, 88982F40h
0x180009d8f  jnz     short loc_180009DAF
0x180009d91  xor     ebp, ebp
0x180009d93  lea     rcx, [rsp+78h+pvar]; pvar
0x180009d98  call    cs:__imp_PropVariantClear
0x180009d9e  test    ebp, ebp
0x180009da0  jns     short loc_180009DAB
0x180009da2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180009da9  jnz     short loc_180009DD7
0x180009dab  mov     eax, ebp
0x180009dad  jmp     short loc_180009D51
0x180009daf  xorps   xmm0, xmm0
0x180009db2  xor     eax, eax
0x180009db4  movups  xmmword ptr [rsp+78h+propvar2], xmm0
0x180009db9  mov     qword ptr [rsp+78h+propvar2+10h], rax
0x180009dbe  test    ebp, ebp
0x180009dc0  jns     short loc_180009DE9
0x180009dc2  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x180009dc8  jnz     short loc_180009DE0
0x180009dca  lea     rcx, [rsp+78h+propvar2]; pvar
0x180009dcf  call    cs:__imp_PropVariantClear
0x180009dd5  jmp     short loc_180009D93
0x180009dd7  mov     ecx, ebp; int
0x180009dd9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180009dde  jmp     short loc_180009DAB
0x180009de0  mov     ecx, ebp; int
0x180009de2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180009de7  jmp     short loc_180009DCA
0x180009de9  mov     rax, [r14]
0x180009dec  lea     r8, [rsp+78h+propvar2]
0x180009df1  mov     rdx, [rbx+38h]
0x180009df5  mov     rcx, r14
0x180009df8  mov     rax, [rax+28h]
0x180009dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e01  mov     ebp, eax
0x180009e03  cmp     eax, 88982F40h
0x180009e08  jz      short loc_180009E20
0x180009e0a  test    eax, eax
0x180009e0c  jns     short loc_180009E24
0x180009e0e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180009e15  jz      short loc_180009DCA
0x180009e17  mov     ecx, eax; int
0x180009e19  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180009e1e  jmp     short loc_180009DCA
0x180009e20  xor     ebp, ebp
0x180009e22  jmp     short loc_180009DCA
0x180009e24  movzx   eax, word ptr [rsp+78h+propvar2]
0x180009e29  cmp     word ptr [rsp+78h+pvar], ax
0x180009e2e  jnz     short loc_180009E4C
0x180009e30  xor     r9d, r9d; flags
0x180009e33  xor     r8d, r8d; unit
0x180009e36  lea     rdx, [rsp+78h+propvar2]; propvar2
0x180009e3b  lea     rcx, [rsp+78h+pvar]; propvar1
0x180009e40  call    cs:__imp_PropVariantCompareEx
0x180009e46  test    eax, eax
0x180009e48  jnz     short loc_180009E4C
0x180009e4a  xor     esi, esi
0x180009e4c  mov     [rdi], esi
0x180009e4e  jmp     loc_180009DCA
```
