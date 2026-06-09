# _anonymous_namespace_::create_embedding

- ea: `0x1400451c4`
- end: `0x1400452c0`
- name: `_anonymous_namespace_::create_embedding`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400454ac`

## callees

- `0x1400154f0`
- `0x14003a168`
- `0x1400451c4`
- `0x140046540`
- `0x140049804`
- `0x140049a48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140045237`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140045237`

## string_xrefs

- `0x14004527f`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`
- `0x1400452a8`: `onecoreuap\base\appmodel\search\common\imageembedding\aifabric_image_feature_provider.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::create_embedding(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  const char *v7; // [rsp+28h] [rbp-30h]
  __int64 v8; // [rsp+40h] [rbp-18h] BYREF
  __int64 v9; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 != 1 )
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unexpected SemanticVector type.",
        v7);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl'::`2'::impl) )
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\imageembedding\\aifabric_image_feature_provider.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unexpected SemanticVector type.",
        v7);
    v4 = *(unsigned int *)(a2 + 16);
    if ( !*(_QWORD *)(a2 + 24) && *(_DWORD *)(a2 + 16) )
      gsl::details::terminate(0);
    v9 = *(_QWORD *)(a2 + 24);
    v8 = v4;
    embedding::create_blob(a1, &v8);
  }
  else
  {
    v5 = *(_QWORD *)(a2 + 8);
    if ( !v5 && *(_DWORD *)(a2 + 4) )
    {
      _o_terminate();
      __debugbreak();
    }
    v8 = *(unsigned int *)(a2 + 4);
    v9 = v5;
    embedding::create_float(a1, &v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1400451c4  mov     [rsp+arg_0], rbx
0x1400451c9  mov     [rsp+arg_8], rsi
0x1400451ce  push    rdi
0x1400451cf  sub     rsp, 50h
0x1400451d3  mov     rdi, rcx
0x1400451d6  mov     rbx, rdx
0x1400451d9  mov     ecx, [rdx]
0x1400451db  test    ecx, ecx
0x1400451dd  jz      short loc_140045226
0x1400451df  cmp     ecx, 1
0x1400451e2  jnz     loc_140045291
0x1400451e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_49288935@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935> `wil::Feature<__WilFeatureTraits_Feature_49288935>::GetImpl(void)'::`2'::impl
0x1400451ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_49288935@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_49288935>::__private_IsEnabled(void)
0x1400451f4  test    al, al
0x1400451f6  jz      short loc_140045268
0x1400451f8  mov     rcx, [rbx+18h]; this
0x1400451fc  mov     eax, [rbx+10h]
0x1400451ff  test    rcx, rcx
0x140045202  jnz     short loc_14004520D
0x140045204  test    rax, rax
0x140045207  jnz     loc_1400452BA
0x14004520d  mov     [rsp+58h+var_10], rcx
0x140045212  lea     rdx, [rsp+58h+var_18]
0x140045217  mov     rcx, rdi
0x14004521a  mov     [rsp+58h+var_18], rax
0x14004521f  call    ?create_blob@embedding@@SA?AU1@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; embedding::create_blob(gsl::span<gsl::byte const,-1>)
0x140045224  jmp     short loc_140045255
0x140045226  mov     rbx, [rdx+8]
0x14004522a  mov     esi, [rdx+4]
0x14004522d  test    rbx, rbx
0x140045230  jnz     short loc_14004523E
0x140045232  test    rsi, rsi
0x140045235  jz      short loc_14004523E
0x140045237  call    cs:__imp__o_terminate
0x14004523d  int     3; Trap to Debugger
0x14004523e  lea     rdx, [rsp+58h+var_18]
0x140045243  mov     [rsp+58h+var_18], rsi
0x140045248  mov     rcx, rdi
0x14004524b  mov     [rsp+58h+var_10], rbx
0x140045250  call    ?create_float@embedding@@SA?AU1@V?$span@$$CBM$0?0@gsl@@@Z; embedding::create_float(gsl::span<float const,-1>)
0x140045255  mov     rbx, [rsp+58h+arg_0]
0x14004525a  mov     rax, rdi
0x14004525d  mov     rsi, [rsp+58h+arg_8]
0x140045262  add     rsp, 50h
0x140045266  pop     rdi
0x140045267  retn
0x140045268  mov     rcx, [rsp+58h]; this
0x14004526d  lea     rax, aUnexpectedSema; "Unexpected SemanticVector type."
0x140045274  mov     r9d, 8000FFFFh; char *
0x14004527a  mov     qword ptr [rsp+58h+var_38], rax; int
0x14004527f  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\search\\com"...
0x140045286  mov     edx, 29h ; ')'; void *
0x14004528b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x140045291  mov     rcx, [rsp+58h]; this
0x140045296  lea     rax, aUnexpectedSema; "Unexpected SemanticVector type."
0x14004529d  mov     r9d, 8000FFFFh; char *
0x1400452a3  mov     qword ptr [rsp+58h+var_38], rax; int
0x1400452a8  lea     r8, aOnecoreuapBase_30; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400452af  mov     edx, 2Ch ; ','; void *
0x1400452b4  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1400452ba  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
