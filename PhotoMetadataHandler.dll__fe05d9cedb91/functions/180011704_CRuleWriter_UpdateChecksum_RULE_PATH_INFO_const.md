# CRuleWriter::UpdateChecksum(RULE_PATH_INFO const *)

- ea: `0x180011704`
- end: `0x18001179e`
- name: `?UpdateChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f2d0`
- `0x18001cf60`

## callees

- `0x180011704`
- `0x1800129d8`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011786`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011786`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRuleWriter::UpdateChecksum(CRuleWriter *this, const struct RULE_PATH_INFO *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 5) + 40LL))(
         *((_QWORD *)this + 5),
         *((_QWORD *)a2 + 7),
         &pvar);
  v5 = v4;
  if ( v4 == -2003292352 )
  {
    v5 = 0;
  }
  else if ( v4 < 0
         || (v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)this + 5) + 56LL))(
                    *((_QWORD *)this + 5),
                    *((_QWORD *)a2 + 6),
                    &pvar),
             v5 = v4,
             v4 < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v4);
  }
  PropVariantClear(&pvar);
  return v5;
}

```

## disassembly

```asm
0x180011704  mov     r11, rsp
0x180011707  mov     [r11+8], rbx
0x18001170b  mov     [r11+10h], rsi
0x18001170f  push    rdi
0x180011710  sub     rsp, 40h
0x180011714  mov     rdi, rdx
0x180011717  mov     rsi, rcx
0x18001171a  xorps   xmm0, xmm0
0x18001171d  xor     eax, eax
0x18001171f  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180011724  mov     [r11-18h], rax
0x180011728  mov     rcx, [rcx+28h]
0x18001172c  mov     rax, [rcx]
0x18001172f  lea     r8, [r11-28h]
0x180011733  mov     rdx, [rdx+38h]
0x180011737  mov     rax, [rax+28h]
0x18001173b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011740  mov     ebx, eax
0x180011742  cmp     eax, 88982F40h
0x180011747  jnz     short loc_18001174D
0x180011749  xor     ebx, ebx
0x18001174b  jmp     short loc_180011781
0x18001174d  test    eax, eax
0x18001174f  js      short loc_180011770
0x180011751  mov     rcx, [rsi+28h]
0x180011755  mov     rax, [rcx]
0x180011758  lea     r8, [rsp+48h+pvar]
0x18001175d  mov     rdx, [rdi+30h]
0x180011761  mov     rax, [rax+38h]
0x180011765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001176a  mov     ebx, eax
0x18001176c  test    eax, eax
0x18001176e  jns     short loc_180011781
0x180011770  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011777  jz      short loc_180011781
0x180011779  mov     ecx, eax; int
0x18001177b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011780  nop
0x180011781  lea     rcx, [rsp+48h+pvar]; pvar
0x180011786  call    cs:__imp_PropVariantClear
0x18001178c  mov     eax, ebx
0x18001178e  mov     rbx, [rsp+48h+arg_0]
0x180011793  mov     rsi, [rsp+48h+arg_8]
0x180011798  add     rsp, 40h
0x18001179c  pop     rdi
0x18001179d  retn
```
