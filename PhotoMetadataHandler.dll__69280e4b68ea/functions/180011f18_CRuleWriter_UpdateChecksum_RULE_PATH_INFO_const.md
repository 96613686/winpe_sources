# CRuleWriter::UpdateChecksum(RULE_PATH_INFO const *)

- ea: `0x180011f18`
- end: `0x180011fb9`
- name: `?UpdateChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fa14`
- `0x18001dd00`

## callees

- `0x180011f18`
- `0x1800132dc`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f9a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011f9a`

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
0x180011f18  mov     r11, rsp
0x180011f1b  mov     [r11+8], rbx
0x180011f1f  mov     [r11+10h], rsi
0x180011f23  push    rdi
0x180011f24  sub     rsp, 40h
0x180011f28  mov     rdi, rdx
0x180011f2b  mov     rsi, rcx
0x180011f2e  xorps   xmm0, xmm0
0x180011f31  xor     eax, eax
0x180011f33  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180011f38  mov     [r11-18h], rax
0x180011f3c  mov     rcx, [rcx+28h]
0x180011f40  mov     rax, [rcx]
0x180011f43  lea     r8, [r11-28h]
0x180011f47  mov     rdx, [rdx+38h]
0x180011f4b  mov     rax, [rax+28h]
0x180011f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f54  mov     ebx, eax
0x180011f56  cmp     eax, 88982F40h
0x180011f5b  jnz     short loc_180011F61
0x180011f5d  xor     ebx, ebx
0x180011f5f  jmp     short loc_180011F95
0x180011f61  test    eax, eax
0x180011f63  js      short loc_180011F84
0x180011f65  mov     rcx, [rsi+28h]
0x180011f69  mov     rax, [rcx]
0x180011f6c  lea     r8, [rsp+48h+pvar]
0x180011f71  mov     rdx, [rdi+30h]
0x180011f75  mov     rax, [rax+38h]
0x180011f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f7e  mov     ebx, eax
0x180011f80  test    eax, eax
0x180011f82  jns     short loc_180011F95
0x180011f84  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011f8b  jz      short loc_180011F95
0x180011f8d  mov     ecx, eax; int
0x180011f8f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011f94  nop
0x180011f95  lea     rcx, [rsp+48h+pvar]; pvar
0x180011f9a  call    cs:__imp_PropVariantClear
0x180011fa1  nop     dword ptr [rax+rax+00h]
0x180011fa6  mov     eax, ebx
0x180011fa8  mov     rbx, [rsp+48h+arg_0]
0x180011fad  mov     rsi, [rsp+48h+arg_8]
0x180011fb2  add     rsp, 40h
0x180011fb6  pop     rdi
0x180011fb7  retn
```
