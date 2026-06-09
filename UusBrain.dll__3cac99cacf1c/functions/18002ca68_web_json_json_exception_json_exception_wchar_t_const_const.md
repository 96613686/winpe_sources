# web::json::json_exception::json_exception(wchar_t const * const &)

- ea: `0x18002ca68`
- end: `0x18002cad5`
- name: `??0json_exception@json@web@@QEAA@AEBQEB_W@Z`
- size: `109`
- prototype: `__int64 __fastcall(web::json::json_exception *__hidden this, const wchar_t *const *)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800298d4`
- `0x180029984`
- `0x18002c7e0`
- `0x18002c820`
- `0x18002c860`
- `0x18002c8a0`
- `0x18002c970`
- `0x18002c9b0`
- `0x18002c9f0`
- `0x18002ca30`
- `0x18002cbf0`
- `0x18002e0cc`
- `0x180033c14`

## callees

- `0x180029518`
- `0x180029644`
- `0x18002ca68`
- `0x180031f2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
web::json::json_exception *__fastcall web::json::json_exception::json_exception(
        web::json::json_exception *this,
        const wchar_t *const *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  _OWORD v6[2]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)((char *)this + 8) = 0;
  *(_QWORD *)this = &web::json::json_exception::`vftable';
  v3 = (__int64)*a2;
  memset(v6, 0, sizeof(v6));
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  std::wstring::_Construct<1,wchar_t const *>(v6);
  utility::conversions::utf16_to_utf8((char *)this + 24);
  std::wstring::_Tidy_deallocate(v6);
  return this;
}

```

## disassembly

```asm
0x18002ca68  mov     [rsp+arg_0], rcx
0x18002ca6d  push    rbx
0x18002ca6e  sub     rsp, 40h
0x18002ca72  mov     rbx, rcx
0x18002ca75  xor     ecx, ecx
0x18002ca77  xorps   xmm0, xmm0
0x18002ca7a  movups  xmmword ptr [rbx+8], xmm0
0x18002ca7e  lea     rax, ??_7json_exception@json@web@@6B@; const web::json::json_exception::`vftable'
0x18002ca85  mov     [rbx], rax
0x18002ca88  mov     rdx, [rdx]
0x18002ca8b  movups  [rsp+48h+var_28], xmm0
0x18002ca90  xorps   xmm1, xmm1
0x18002ca93  movdqu  [rsp+48h+var_18], xmm1
0x18002ca99  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ca9d  inc     r8
0x18002caa0  cmp     [rdx+r8*2], cx
0x18002caa5  jnz     short loc_18002CA9D
0x18002caa7  lea     rcx, [rsp+48h+var_28]
0x18002caac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18002cab1  nop
0x18002cab2  lea     rcx, [rbx+18h]; Src
0x18002cab6  lea     rdx, [rsp+48h+var_28]
0x18002cabb  call    ?utf16_to_utf8@conversions@utility@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; utility::conversions::utf16_to_utf8(std::wstring const &)
0x18002cac0  nop
0x18002cac1  lea     rcx, [rsp+48h+var_28]
0x18002cac6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002cacb  nop
0x18002cacc  mov     rax, rbx
0x18002cacf  add     rsp, 40h
0x18002cad3  pop     rbx
0x18002cad4  retn
```
