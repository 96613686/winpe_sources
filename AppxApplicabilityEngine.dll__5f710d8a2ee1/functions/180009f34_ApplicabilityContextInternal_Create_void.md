# ApplicabilityContextInternal::Create(void)

- ea: `0x180009f34`
- end: `0x18000a0bb`
- name: `?Create@ApplicabilityContextInternal@@SA?AV?$unique_ptr@VApplicabilityContextInternal@@U?$default_delete@VApplicabilityContextInternal@@@std@@@std@@XZ`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x180009ed0`
- `0x18000e8dc`

## callees

- `0x180003ebc`
- `0x1800040bc`
- `0x180004920`
- `0x180009f34`
- `0x18000a144`
- `0x18000adb0`
- `0x180011a64`
- `0x180016b8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall ApplicabilityContextInternal::Create(__int64 *a1)
{
  char *v2; // rax
  const char *v3; // r9
  __int64 *v4; // rdi
  void *v5; // rsi
  AttributeGrammar *v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rdi
  void *v9; // rsi
  AttributeGrammar *v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rdi
  void *v13; // rsi
  AttributeGrammar *v14; // rax
  __int64 v15; // rsi
  _BYTE v17[128]; // [rsp+30h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = (char *)operator new(0x20u);
  if ( v2 )
  {
    *(_OWORD *)v2 = 0;
    *((_OWORD *)v2 + 1) = 0;
    *(_QWORD *)v2 = &ApplicabilityContextInternal::`vftable';
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 2) = 0;
    *((_QWORD *)v2 + 3) = 0;
  }
  *a1 = (__int64)v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecoreuap\\base\\mrt\\applicability\\src\\applicabilitycontext.cpp",
      v3);
  v4 = (__int64 *)(v2 + 8);
  v5 = operator new(0x88u);
  if ( v5 )
  {
    v6 = AttributeGrammar::AttributeGrammar(
           (AttributeGrammar *)v17,
           (const struct AttributeGrammar *)ApplicabilityContextInternal::serializationGrammar);
    v7 = CStrings::CStrings(v5, v6);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 != *v4 )
  {
    std::unique_ptr<CUints>::_Delete(v4);
    *v4 = v7;
  }
  v8 = *a1;
  v9 = operator new(0x88u);
  if ( v9 )
  {
    v10 = AttributeGrammar::AttributeGrammar((AttributeGrammar *)v17, (const struct AttributeGrammar *)&word_18003A058);
    v11 = CUints::CUints(v9, v10);
  }
  else
  {
    v11 = 0;
  }
  if ( v11 != *(_QWORD *)(v8 + 16) )
  {
    std::unique_ptr<CUints>::_Delete(v8 + 16);
    *(_QWORD *)(v8 + 16) = v11;
  }
  v12 = *a1;
  v13 = operator new(0x88u);
  if ( v13 )
  {
    v14 = AttributeGrammar::AttributeGrammar((AttributeGrammar *)v17, (const struct AttributeGrammar *)&word_18003A0B0);
    v15 = CDxFeatureLevels::CDxFeatureLevels(v13, v14);
  }
  else
  {
    v15 = 0;
  }
  if ( v15 != *(_QWORD *)(v12 + 24) )
  {
    std::unique_ptr<CUints>::_Delete(v12 + 24);
    *(_QWORD *)(v12 + 24) = v15;
  }
  return a1;
}

```

## disassembly

```asm
0x180009f34  mov     [rsp-8+arg_0], rcx
0x180009f39  push    rbp
0x180009f3a  push    rbx
0x180009f3b  push    rsi
0x180009f3c  push    rdi
0x180009f3d  push    r15
0x180009f3f  lea     rbp, [rsp-37h]
0x180009f44  sub     rsp, 90h
0x180009f4b  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x180009f53  mov     rbx, rcx
0x180009f56  mov     [rbp+57h+var_90], 0
0x180009f5d  mov     ecx, 20h ; ' '; Size
0x180009f62  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f67  mov     [rbp+57h+arg_8], rax
0x180009f6b  test    rax, rax
0x180009f6e  jz      short loc_180009F9C
0x180009f70  xorps   xmm0, xmm0
0x180009f73  movups  xmmword ptr [rax], xmm0
0x180009f76  movups  xmmword ptr [rax+10h], xmm0
0x180009f7a  lea     rcx, ??_7ApplicabilityContextInternal@@6B@; const ApplicabilityContextInternal::`vftable'
0x180009f81  mov     [rax], rcx
0x180009f84  mov     qword ptr [rax+8], 0
0x180009f8c  mov     qword ptr [rax+10h], 0
0x180009f94  mov     qword ptr [rax+18h], 0
0x180009f9c  mov     [rbx], rax
0x180009f9f  mov     [rbp+57h+var_90], 1
0x180009fa6  mov     rcx, [rbp+5Fh]; this
0x180009faa  test    rax, rax
0x180009fad  jnz     short loc_180009FC1
0x180009faf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\applicability\\s"...
0x180009fb6  mov     edx, 105h; void *
0x180009fbb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180009fc1  lea     rdi, [rax+8]
0x180009fc5  mov     r15d, 88h
0x180009fcb  mov     ecx, r15d; Size
0x180009fce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009fd3  mov     rsi, rax
0x180009fd6  mov     [rbp+57h+arg_8], rax
0x180009fda  test    rax, rax
0x180009fdd  jz      short loc_180009FFF
0x180009fdf  lea     rdx, ?serializationGrammar@ApplicabilityContextInternal@@0UGrammar@@B; struct AttributeGrammar *
0x180009fe6  lea     rcx, [rbp+57h+var_80]; this
0x180009fea  call    ??0AttributeGrammar@@QEAA@AEBU0@@Z; AttributeGrammar::AttributeGrammar(AttributeGrammar const &)
0x180009fef  mov     rdx, rax
0x180009ff2  mov     rcx, rsi
0x180009ff5  call    ??0CStrings@@QEAA@UAttributeGrammar@@@Z; CStrings::CStrings(AttributeGrammar)
0x180009ffa  mov     rsi, rax
0x180009ffd  jmp     short loc_18000A001
0x180009fff  xor     esi, esi
0x18000a001  cmp     rsi, [rdi]
0x18000a004  jz      short loc_18000A011
0x18000a006  mov     rcx, rdi
0x18000a009  call    ?_Delete@?$unique_ptr@VCUints@@U?$default_delete@VCUints@@@std@@@std@@AEAAXXZ; std::unique_ptr<CUints>::_Delete(void)
0x18000a00e  mov     [rdi], rsi
0x18000a011  mov     rdi, [rbx]
0x18000a014  mov     rcx, r15; Size
0x18000a017  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a01c  mov     rsi, rax
0x18000a01f  mov     [rbp+57h+arg_8], rax
0x18000a023  test    rax, rax
0x18000a026  jz      short loc_18000A048
0x18000a028  lea     rdx, word_18003A058; struct AttributeGrammar *
0x18000a02f  lea     rcx, [rbp+57h+var_80]; this
0x18000a033  call    ??0AttributeGrammar@@QEAA@AEBU0@@Z; AttributeGrammar::AttributeGrammar(AttributeGrammar const &)
0x18000a038  mov     rdx, rax
0x18000a03b  mov     rcx, rsi
0x18000a03e  call    ??0CUints@@QEAA@UAttributeGrammar@@@Z; CUints::CUints(AttributeGrammar)
0x18000a043  mov     rsi, rax
0x18000a046  jmp     short loc_18000A04A
0x18000a048  xor     esi, esi
0x18000a04a  cmp     rsi, [rdi+10h]
0x18000a04e  jz      short loc_18000A05D
0x18000a050  lea     rcx, [rdi+10h]
0x18000a054  call    ?_Delete@?$unique_ptr@VCUints@@U?$default_delete@VCUints@@@std@@@std@@AEAAXXZ; std::unique_ptr<CUints>::_Delete(void)
0x18000a059  mov     [rdi+10h], rsi
0x18000a05d  mov     rdi, [rbx]
0x18000a060  mov     rcx, r15; Size
0x18000a063  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a068  mov     rsi, rax
0x18000a06b  mov     [rbp+57h+arg_8], rax
0x18000a06f  test    rax, rax
0x18000a072  jz      short loc_18000A094
0x18000a074  lea     rdx, word_18003A0B0; struct AttributeGrammar *
0x18000a07b  lea     rcx, [rbp+57h+var_80]; this
0x18000a07f  call    ??0AttributeGrammar@@QEAA@AEBU0@@Z; AttributeGrammar::AttributeGrammar(AttributeGrammar const &)
0x18000a084  mov     rdx, rax
0x18000a087  mov     rcx, rsi
0x18000a08a  call    ??0CDxFeatureLevels@@QEAA@UAttributeGrammar@@@Z; CDxFeatureLevels::CDxFeatureLevels(AttributeGrammar)
0x18000a08f  mov     rsi, rax
0x18000a092  jmp     short loc_18000A096
0x18000a094  xor     esi, esi
0x18000a096  cmp     rsi, [rdi+18h]
0x18000a09a  jz      short loc_18000A0A9
0x18000a09c  lea     rcx, [rdi+18h]
0x18000a0a0  call    ?_Delete@?$unique_ptr@VCUints@@U?$default_delete@VCUints@@@std@@@std@@AEAAXXZ; std::unique_ptr<CUints>::_Delete(void)
0x18000a0a5  mov     [rdi+18h], rsi
0x18000a0a9  mov     rax, rbx
0x18000a0ac  add     rsp, 90h
0x18000a0b3  pop     r15
0x18000a0b5  pop     rdi
0x18000a0b6  pop     rsi
0x18000a0b7  pop     rbx
0x18000a0b8  pop     rbp
0x18000a0b9  retn
```
