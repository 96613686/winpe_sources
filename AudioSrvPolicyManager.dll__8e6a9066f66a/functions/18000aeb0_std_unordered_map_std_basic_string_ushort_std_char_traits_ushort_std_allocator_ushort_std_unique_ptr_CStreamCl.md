# std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<CStreamClassPolicyGains,std::default_delete<CStreamClassPolicyGains>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<CStreamClassPolicyGains,std::default_delete<CStreamClassPolicyGains>>>>>::operator[](std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000aeb0`
- end: `0x18000b19e`
- name: `??A?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b1b0`

## callees

- `0x18000aeb0`
- `0x18000b980`
- `0x18001b910`
- `0x18003a4a0`
- `0x1800411bc`
- `0x180041270`
- `0x180041498`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b015`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b015`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__m128i *__fastcall std::unordered_map<std::wstring,std::unique_ptr<CStreamClassPolicyGains>>::operator[](
        unsigned __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 appended; // rax
  const __m128i *v7; // r8
  __int64 v8; // rdx
  __m128i *v9; // r14
  __m128i *v10; // rdi
  __m128i *v11; // rdi
  const __m128i *v12; // r10
  const __m128i *v13; // r11
  unsigned __int64 v14; // rcx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int16 v18; // cx
  unsigned int v19; // eax
  unsigned __int64 v20; // rax
  __m128i **v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  __m128i *v25; // r8
  unsigned int v29; // eax
  __int64 v30; // rdx
  float v31; // xmm0_4
  __int64 v32; // rcx
  float v33; // xmm1_4
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rbx
  char v37[8]; // [rsp+30h] [rbp-48h] BYREF
  __m128i *v38; // [rsp+38h] [rbp-40h]
  char v39[16]; // [rsp+40h] [rbp-38h] BYREF
  _QWORD *v40; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int64 v41; // [rsp+88h] [rbp+10h]

  v2 = a2;
  v4 = a2[2];
  v5 = a2[3];
  if ( v5 > 7 )
    a2 = (_QWORD *)*a2;
  appended = std::_Fnv1a_append_bytes(a1, (const unsigned __int8 *const)a2, 2 * v4);
  v41 = appended;
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(__m128i **)(v8 + 16 * (appended & *(_QWORD *)(a1 + 48)) + 8);
  v10 = *(__m128i **)(a1 + 8);
  if ( v9 == v10 )
  {
LABEL_28:
    if ( *(_QWORD *)(a1 + 16) == 0x492492492492492LL )
      std::_Xlength_error("unordered_map/set too long");
    v40 = v2;
    std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>(
      v37,
      a1 + 8,
      v7,
      &v40);
    v30 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v30 < 0 )
      v31 = (float)(v30 & 1 | (unsigned int)((unsigned __int64)v30 >> 1))
          + (float)(v30 & 1 | (unsigned int)((unsigned __int64)v30 >> 1));
    else
      v31 = (float)(int)v30;
    v32 = *(_QWORD *)(a1 + 56);
    if ( v32 < 0 )
    {
      v34 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v32 >> 1);
      v33 = (float)(int)v34 + (float)(int)v34;
    }
    else
    {
      v33 = (float)(int)v32;
    }
    if ( (float)(v31 / v33) <= *(float *)a1 )
    {
      v36 = v41;
    }
    else
    {
      v35 = std::_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CStreamClassPolicyGains>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>>,0>>::_Forced_rehash(
        a1,
        v35);
      v36 = v41;
      v10 = *(__m128i **)std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CStreamClassPolicyGains>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>>,0>>::_Find_last<std::wstring>(
                           a1,
                           v39,
                           &v38[1],
                           v41);
    }
    v9 = v38;
    v38 = 0;
    v22 = (__m128i **)v10->m128i_i64[1];
    ++*(_QWORD *)(a1 + 16);
    v9->m128i_i64[0] = (__int64)v10;
    v9->m128i_i64[1] = (__int64)v22;
    *v22 = v9;
    v10->m128i_i64[1] = (__int64)v9;
    v23 = 2 * (v36 & *(_QWORD *)(a1 + 48));
    v24 = *(_QWORD *)(a1 + 24);
    v25 = *(__m128i **)(v24 + 16 * (v36 & *(_QWORD *)(a1 + 48)));
    if ( v25 == *(__m128i **)(a1 + 8) )
    {
      *(_QWORD *)(v24 + 16 * (v36 & *(_QWORD *)(a1 + 48))) = v9;
    }
    else
    {
      if ( v25 == v10 )
      {
        *(_QWORD *)(v24 + 16 * (v36 & *(_QWORD *)(a1 + 48))) = v9;
        goto LABEL_32;
      }
      if ( *(__m128i ***)(v24 + 16 * (v36 & *(_QWORD *)(a1 + 48)) + 8) != v22 )
      {
LABEL_32:
        std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>(v37);
        return v9 + 3;
      }
    }
    *(_QWORD *)(v24 + 8 * v23 + 8) = v9;
    goto LABEL_32;
  }
  v11 = *(__m128i **)(v8 + 16 * (appended & *(_QWORD *)(a1 + 48)));
  while ( 1 )
  {
    v12 = v9 + 1;
    if ( v9[2].m128i_i64[1] > 7uLL )
      v12 = (const __m128i *)v12->m128i_i64[0];
    v13 = v5 <= 7 ? (const __m128i *)v2 : (const __m128i *)*v2;
    if ( v4 == v9[2].m128i_i64[0] )
      break;
LABEL_20:
    if ( v9 == v11 )
    {
      v10 = v9;
      goto LABEL_28;
    }
    v9 = (__m128i *)v9->m128i_i64[1];
  }
  if ( v4 )
  {
    v14 = 0;
    _RDX = v13;
    v7 = v12;
    if ( !Avx2WmemEnabledWeakValue )
      goto LABEL_13;
    while ( 1 )
    {
      v16 = v14 + 16;
      if ( v14 + 16 > v4 )
        break;
      __asm
      {
        vmovdqu ymm1, ymmword ptr [rdx]
        vpcmpeqw ymm1, ymm1, ymmword ptr [r8]
        vpmovmskb ecx, ymm1
      }
      if ( _ECX != -1 )
      {
        _BitScanForward(&v29, ~_ECX);
        LODWORD(v40) = v29;
        __asm { vzeroupper }
        goto LABEL_20;
      }
      v14 = v16;
      _RDX += 2;
      v7 += 2;
      __asm { vzeroupper }
    }
LABEL_13:
    while ( 1 )
    {
      v17 = v14 + 8;
      if ( v14 + 8 > v4 )
        break;
      v18 = _mm_movemask_epi8(_mm_cmpeq_epi16(_mm_loadu_si128(v7), _mm_loadu_si128(_RDX)));
      if ( v18 != 0xFFFF )
      {
        _BitScanForward(&v19, ~v18);
        LODWORD(v40) = v19;
        goto LABEL_20;
      }
      v14 = v17;
      ++_RDX;
      ++v7;
    }
    if ( v14 + 4 > v4 )
      goto LABEL_17;
    if ( _RDX->m128i_i64[0] != v7->m128i_i64[0] )
    {
      _BitScanForward64(&v20, _RDX->m128i_i64[0] ^ v7->m128i_i64[0]);
      LODWORD(v40) = v20;
      goto LABEL_20;
    }
    v14 += 4LL;
LABEL_17:
    while ( v14 < v4 )
    {
      if ( v13->m128i_i16[v14] != v12->m128i_i16[v14] )
        goto LABEL_20;
      ++v14;
    }
  }
  return v9 + 3;
}

```

## disassembly

```asm
0x18000aeb0  mov     [rsp+arg_10], rbx
0x18000aeb5  mov     [rsp+arg_18], rsi
0x18000aeba  push    rdi
0x18000aebb  push    r12
0x18000aebd  push    r13
0x18000aebf  push    r14
0x18000aec1  push    r15
0x18000aec3  sub     rsp, 50h
0x18000aec7  mov     rsi, rdx
0x18000aeca  mov     r13, rcx
0x18000aecd  mov     rbx, [rdx+10h]
0x18000aed1  mov     r15, [rdx+18h]
0x18000aed5  cmp     r15, 7
0x18000aed9  jbe     short loc_18000AEDE
0x18000aedb  mov     rdx, [rdx]; unsigned __int8 *
0x18000aede  lea     r8, [rbx+rbx]; unsigned __int64
0x18000aee2  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18000aee7  mov     [rsp+78h+arg_8], rax
0x18000aeef  mov     rcx, [r13+30h]
0x18000aef3  and     rcx, rax
0x18000aef6  add     rcx, rcx
0x18000aef9  mov     rdx, [r13+18h]
0x18000aefd  mov     r14, [rdx+rcx*8+8]
0x18000af02  mov     rdi, [r13+8]
0x18000af06  cmp     r14, rdi
0x18000af09  jz      loc_18000AFFA
0x18000af0f  mov     rdi, [rdx+rcx*8]
0x18000af13  mov     r9d, 0FFFFh
0x18000af19  lea     r10, [r14+10h]
0x18000af1d  cmp     qword ptr [r14+28h], 7
0x18000af22  jbe     short loc_18000AF27
0x18000af24  mov     r10, [r10]
0x18000af27  cmp     r15, 7
0x18000af2b  jbe     loc_18000AFBE
0x18000af31  mov     r11, [rsi]
0x18000af34  cmp     rbx, [r14+20h]
0x18000af38  jnz     short loc_18000AFB0
0x18000af3a  test    rbx, rbx
0x18000af3d  jz      loc_18000B02F
0x18000af43  xor     ecx, ecx
0x18000af45  mov     rdx, r11
0x18000af48  mov     r8, r10
0x18000af4b  cmp     cs:_Avx2WmemEnabledWeakValue, ecx
0x18000af51  jz      short loc_18000AF60
0x18000af53  lea     rax, [rcx+10h]
0x18000af57  cmp     rax, rbx
0x18000af5a  jbe     loc_18000B09D
0x18000af60  lea     rax, [rcx+8]
0x18000af64  cmp     rax, rbx
0x18000af67  ja      short loc_18000AF8D
0x18000af69  movdqu  xmm1, xmmword ptr [r8]
0x18000af6e  movdqu  xmm0, xmmword ptr [rdx]
0x18000af72  pcmpeqw xmm1, xmm0
0x18000af76  pmovmskb ecx, xmm1
0x18000af7a  cmp     cx, r9w
0x18000af7e  jnz     short loc_18000AFD6
0x18000af80  mov     rcx, rax
0x18000af83  add     rdx, 10h
0x18000af87  add     r8, 10h
0x18000af8b  jmp     short loc_18000AF60
0x18000af8d  lea     rax, [rcx+4]
0x18000af91  cmp     rax, rbx
0x18000af94  jbe     short loc_18000AFC6
0x18000af96  cmp     rcx, rbx
0x18000af99  jnb     loc_18000B02F
0x18000af9f  movzx   eax, word ptr [r10+rcx*2]
0x18000afa4  cmp     [r11+rcx*2], ax
0x18000afa9  jnz     short loc_18000AFB0
0x18000afab  inc     rcx
0x18000afae  jmp     short loc_18000AF96
0x18000afb0  cmp     r14, rdi
0x18000afb3  jz      short loc_18000AFF7
0x18000afb5  mov     r14, [r14+8]
0x18000afb9  jmp     loc_18000AF13
0x18000afbe  mov     r11, rsi
0x18000afc1  jmp     loc_18000AF34
0x18000afc6  mov     r9, [rdx]
0x18000afc9  mov     rcx, [r8]
0x18000afcc  cmp     r9, rcx
0x18000afcf  jnz     short loc_18000AFE7
0x18000afd1  mov     rcx, rax
0x18000afd4  jmp     short loc_18000AF96
0x18000afd6  movzx   eax, cx
0x18000afd9  not     eax
0x18000afdb  bsf     eax, eax
0x18000afde  mov     dword ptr [rsp+78h+arg_0], eax
0x18000afe5  jmp     short loc_18000AFB0
0x18000afe7  xor     rcx, r9
0x18000afea  bsf     rax, rcx
0x18000afee  mov     dword ptr [rsp+78h+arg_0], eax
0x18000aff5  jmp     short loc_18000AFB0
0x18000aff7  mov     rdi, r14
0x18000affa  mov     rax, 492492492492492h
0x18000b004  cmp     [r13+10h], rax
0x18000b008  jnz     loc_18000B0D6
0x18000b00e  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000b015  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b01c  mov     [rcx+rax*8], r14
0x18000b020  mov     [rcx+rax*8+8], r14
0x18000b025  lea     rcx, [rsp+78h+var_48]
0x18000b02a  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>(void)
0x18000b02f  lea     rax, [r14+30h]
0x18000b033  lea     r11, [rsp+78h+var_28]
0x18000b038  mov     rbx, [r11+40h]
0x18000b03c  mov     rsi, [r11+48h]
0x18000b040  mov     rsp, r11
0x18000b043  pop     r15
0x18000b045  pop     r14
0x18000b047  pop     r13
0x18000b049  pop     r12
0x18000b04b  pop     rdi
0x18000b04c  retn
0x18000b04d  mov     r14, [rsp+78h+var_40]
0x18000b052  mov     [rsp+78h+var_40], 0
0x18000b05b  mov     rdx, [rdi+8]
0x18000b05f  inc     qword ptr [r13+10h]
0x18000b063  mov     [r14], rdi
0x18000b066  mov     [r14+8], rdx
0x18000b06a  mov     [rdx], r14
0x18000b06d  mov     [rdi+8], r14
0x18000b071  mov     rax, [r13+30h]
0x18000b075  and     rax, rbx
0x18000b078  add     rax, rax
0x18000b07b  mov     rcx, [r13+18h]
0x18000b07f  mov     r8, [rcx+rax*8]
0x18000b083  cmp     r8, [r13+8]
0x18000b087  jz      short loc_18000B01C
0x18000b089  cmp     r8, rdi
0x18000b08c  jz      short loc_18000B097
0x18000b08e  cmp     [rcx+rax*8+8], rdx
0x18000b093  jnz     short loc_18000B025
0x18000b095  jmp     short loc_18000B020
0x18000b097  mov     [rcx+rax*8], r14
0x18000b09b  jmp     short loc_18000B025
0x18000b09d  vmovdqu ymm1, ymmword ptr [rdx]
0x18000b0a1  vpcmpeqw ymm1, ymm1, ymmword ptr [r8]
0x18000b0a6  vpmovmskb ecx, ymm1
0x18000b0aa  cmp     ecx, 0FFFFFFFFh
0x18000b0ad  jnz     short loc_18000B0C2
0x18000b0af  mov     rcx, rax
0x18000b0b2  add     rdx, 20h ; ' '
0x18000b0b6  add     r8, 20h ; ' '
0x18000b0ba  vzeroupper
0x18000b0bd  jmp     loc_18000AF53
0x18000b0c2  not     ecx
0x18000b0c4  bsf     eax, ecx
0x18000b0c7  mov     dword ptr [rsp+78h+arg_0], eax
0x18000b0ce  vzeroupper
0x18000b0d1  jmp     loc_18000AFB0
0x18000b0d6  mov     [rsp+78h+arg_0], rsi
0x18000b0de  lea     r9, [rsp+78h+arg_0]
0x18000b0e6  lea     rdx, [r13+8]
0x18000b0ea  lea     rcx, [rsp+78h+var_48]
0x18000b0ef  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$tuple@$$V@1@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@PEAX@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>,void *>> &,std::piecewise_construct_t const &,std::tuple<std::wstring &&> &&,std::tuple<> &&)
0x18000b0f4  nop
0x18000b0f5  mov     rdx, [r13+10h]
0x18000b0f9  add     rdx, 1
0x18000b0fd  xorps   xmm0, xmm0
0x18000b100  js      short loc_18000B109
0x18000b102  cvtsi2ss xmm0, rdx
0x18000b107  jmp     short loc_18000B121
0x18000b109  mov     rcx, rdx
0x18000b10c  shr     rcx, 1
0x18000b10f  mov     rax, rdx
0x18000b112  and     eax, 1
0x18000b115  or      rcx, rax
0x18000b118  cvtsi2ss xmm0, rcx
0x18000b11d  addss   xmm0, xmm0
0x18000b121  mov     rcx, [r13+38h]
0x18000b125  xorps   xmm1, xmm1
0x18000b128  test    rcx, rcx
0x18000b12b  js      short loc_18000B134
0x18000b12d  cvtsi2ss xmm1, rcx
0x18000b132  jmp     short loc_18000B149
0x18000b134  mov     rax, rcx
0x18000b137  shr     rax, 1
0x18000b13a  and     ecx, 1
0x18000b13d  or      rax, rcx
0x18000b140  cvtsi2ss xmm1, rax
0x18000b145  addss   xmm1, xmm1
0x18000b149  divss   xmm0, xmm1
0x18000b14d  comiss  xmm0, dword ptr [r13+0]
0x18000b152  jbe     short loc_18000B190
0x18000b154  mov     rcx, r13
0x18000b157  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCRenderEndpointDuckingManagerContext@@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<std::wstring,CRenderEndpointDuckingManagerContext,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,CRenderEndpointDuckingManagerContext>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000b15c  mov     rdx, rax
0x18000b15f  mov     rcx, r13
0x18000b162  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CStreamClassPolicyGains>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000b167  mov     r8, [rsp+78h+var_40]
0x18000b16c  add     r8, 10h
0x18000b170  mov     rbx, [rsp+78h+arg_8]
0x18000b178  mov     r9, rbx
0x18000b17b  lea     rdx, [rsp+78h+var_38]
0x18000b180  mov     rcx, r13
0x18000b183  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCStreamClassPolicyGains@@U?$default_delete@VCStreamClassPolicyGains@@@std@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CStreamClassPolicyGains>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CStreamClassPolicyGains>>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000b188  mov     rdi, [rax]
0x18000b18b  jmp     loc_18000B04D
0x18000b190  mov     rbx, [rsp+78h+arg_8]
0x18000b198  jmp     loc_18000B04D
```
