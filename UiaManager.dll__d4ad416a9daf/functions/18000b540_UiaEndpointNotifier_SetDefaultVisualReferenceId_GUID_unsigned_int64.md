# UiaEndpointNotifier::SetDefaultVisualReferenceId(_GUID,unsigned __int64)

- ea: `0x18000b540`
- end: `0x18000b8a5`
- name: `?SetDefaultVisualReferenceId@UiaEndpointNotifier@@UEAAJU_GUID@@_K@Z`
- size: `869`
- prototype: `int(UiaEndpointNotifier *__hidden this, struct _GUID *__struct_ptr, unsigned __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800092c0`
- `0x18000b540`
- `0x18001262c`
- `0x1800188ac`
- `0x1800264f8`
- `0x180031540`
- `0x180043a8c`
- `0x180044188`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b83c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b847`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b83c`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b847`
- `msvcp_win!_Mtx_lock` at `0x18000b5a8`
- `msvcp_win!_Mtx_lock` at `0x18000b5a8`
- `msvcp_win!_Mtx_unlock` at `0x18000b667`
- `msvcp_win!_Mtx_unlock` at `0x18000b667`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b855`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b855`

## string_xrefs

- `0x18000b80f`: `onecore\windows\accessibletech\uiamanager\dll\uiaendpointnotifier.cpp`
- `0x18000b826`: `onecore\windows\accessibletech\uiamanager\dll\uiaendpointnotifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall UiaEndpointNotifier::SetDefaultVisualReferenceId(UiaEndpointNotifier *this, __m128i *a2, __int64 a3)
{
  __m128i v5; // xmm6
  unsigned __int64 v6; // rdx
  unsigned int i; // r8d
  _QWORD *v8; // rax
  __int64 v9; // r14
  unsigned __int64 v10; // xmm0_8
  _QWORD *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v15; // rdi
  unsigned int j; // edx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __m128i *v19; // rsi
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  float v22; // xmm0_4
  float v23; // xmm1_4
  __m128i **v24; // rcx
  __int64 v25; // rdi
  _QWORD *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __m128i v29; // [rsp+20h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiaendpointnotifier.cpp",
      (const char *)0x80070057LL,
      v29.m128i_i32[0]);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiaendpointnotifier.cpp",
      (const char *)0x80070057LL,
      v29.m128i_i32[0]);
  v5 = *a2;
  v29 = *a2;
  if ( _Mtx_lock((_Mtx_t)EndpointInProcUtils::s_endpointVisualReferenceIdMap) )
  {
    std::_Throw_Cpp_error(5);
    goto LABEL_48;
  }
  if ( !std::_Mutex_base::_Verify_ownership_levels((std::_Mutex_base *)EndpointInProcUtils::s_endpointVisualReferenceIdMap) )
  {
LABEL_48:
    std::_Throw_Cpp_error(6);
    goto LABEL_49;
  }
  v6 = v29.m128i_u16[2] + v5.m128i_u32[0] + (unsigned __int64)v29.m128i_u16[3];
  for ( i = 0; i < 8; ++i )
    v6 += v29.m128i_u8[i + 8];
  v8 = (_QWORD *)*((_QWORD *)qword_1800C48C8 + 2 * (v6 & qword_1800C48E0) + 1);
  v9 = qword_1800C48B8;
  v10 = _mm_srli_si128(v5, 8).m128i_u64[0];
  if ( v8 == (_QWORD *)qword_1800C48B8 )
  {
LABEL_14:
    v8 = 0;
  }
  else
  {
    v11 = (_QWORD *)*((_QWORD *)qword_1800C48C8 + 2 * (v6 & qword_1800C48E0));
    while ( 1 )
    {
      v12 = v5.m128i_i64[0] - v8[2];
      if ( v5.m128i_i64[0] == v8[2] )
        v12 = v10 - v8[3];
      if ( !v12 )
        break;
      if ( v8 == v11 )
        goto LABEL_14;
      v8 = (_QWORD *)v8[1];
    }
  }
  v13 = qword_1800C48B8;
  if ( v8 )
    v13 = (__int64)v8;
  if ( v13 != qword_1800C48B8 )
  {
    *(_QWORD *)(v13 + 32) = a3;
    goto LABEL_19;
  }
  v15 = v29.m128i_u16[2] + v5.m128i_u32[0] + (unsigned __int64)v29.m128i_u16[3];
  for ( j = 0; j < 8; ++j )
    v15 += v29.m128i_u8[j + 8];
  v17 = (_QWORD *)*((_QWORD *)qword_1800C48C8 + 2 * (qword_1800C48E0 & v15) + 1);
  if ( v17 != (_QWORD *)qword_1800C48B8 )
  {
    while ( 1 )
    {
      v18 = v5.m128i_i64[0] - v17[2];
      if ( v5.m128i_i64[0] == v17[2] )
        v18 = v10 - v17[3];
      if ( !v18 )
        goto LABEL_19;
      if ( v17 == *((_QWORD **)qword_1800C48C8 + 2 * (qword_1800C48E0 & v15)) )
        break;
      v17 = (_QWORD *)v17[1];
    }
    v9 = (__int64)v17;
  }
  if ( qword_1800C48C0 == 0x666666666666666LL )
LABEL_49:
    std::_Xlength_error("unordered_map/set too long");
  v29.m128i_i64[0] = (__int64)&qword_1800C48B8;
  v29.m128i_i64[1] = 0;
  v19 = (__m128i *)operator new(0x28u);
  v29.m128i_i64[1] = (__int64)v19;
  v19[1] = v5;
  v19[2].m128i_i64[0] = a3;
  v20 = qword_1800C48C0;
  v21 = qword_1800C48C0 + 1;
  if ( qword_1800C48C0 + 1 < 0 )
    v22 = (float)(int)(v21 & 1 | (v21 >> 1)) + (float)(int)(v21 & 1 | (v21 >> 1));
  else
    v22 = (float)(int)v21;
  if ( qword_1800C48E8 < 0 )
    v23 = (float)(qword_1800C48E8 & 1 | (unsigned int)((unsigned __int64)qword_1800C48E8 >> 1))
        + (float)(qword_1800C48E8 & 1 | (unsigned int)((unsigned __int64)qword_1800C48E8 >> 1));
  else
    v23 = (float)(int)qword_1800C48E8;
  if ( (float)(v22 / v23) > *(float *)&dword_1800C48B0 )
  {
    v28 = std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::_Desired_grow_bucket_count(&dword_1800C48B0);
    std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>>>,0>>::_Forced_rehash(
      &dword_1800C48B0,
      v28);
    v9 = *(_QWORD *)std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(
                      &dword_1800C48B0,
                      &v29,
                      &v19[1],
                      v15);
    v20 = qword_1800C48C0;
  }
  v24 = *(__m128i ***)(v9 + 8);
  qword_1800C48C0 = v20 + 1;
  v19->m128i_i64[0] = v9;
  v19->m128i_i64[1] = (__int64)v24;
  *v24 = v19;
  *(_QWORD *)(v9 + 8) = v19;
  v25 = 2 * (qword_1800C48E0 & v15);
  v26 = qword_1800C48C8;
  v27 = *((_QWORD *)qword_1800C48C8 + v25);
  if ( v27 == qword_1800C48B8 )
  {
    *((_QWORD *)qword_1800C48C8 + v25) = v19;
LABEL_40:
    v26[v25 + 1] = v19;
    goto LABEL_19;
  }
  if ( v27 == v9 )
  {
    *((_QWORD *)qword_1800C48C8 + v25) = v19;
    goto LABEL_19;
  }
  if ( *((__m128i ***)qword_1800C48C8 + v25 + 1) == v24 )
    goto LABEL_40;
LABEL_19:
  _Mtx_unlock((_Mtx_t)EndpointInProcUtils::s_endpointVisualReferenceIdMap);
  return 0;
}

```

## disassembly

```asm
0x18000b540  push    rbx
0x18000b542  push    rsi
0x18000b543  push    rdi
0x18000b544  push    r12
0x18000b546  push    r14
0x18000b548  push    r15
0x18000b54a  sub     rsp, 48h
0x18000b54e  movaps  [rsp+78h+var_48], xmm6
0x18000b553  mov     r12, r8
0x18000b556  mov     rbx, rdx
0x18000b559  mov     r8d, 10h; Size
0x18000b55f  lea     rdx, GUID_NULL; Buf2
0x18000b566  mov     rcx, rbx; Buf1
0x18000b569  call    memcmp_0
0x18000b56e  test    eax, eax
0x18000b570  setz    al
0x18000b573  mov     rcx, [rsp+78h]; this
0x18000b578  test    al, al
0x18000b57a  jnz     loc_18000B809
0x18000b580  mov     rcx, [rsp+78h]; this
0x18000b585  test    r12, r12
0x18000b588  jz      loc_18000B820
0x18000b58e  movups  xmm6, xmmword ptr [rbx]
0x18000b591  movaps  [rsp+78h+var_58], xmm6
0x18000b596  lea     rbx, ?s_endpointVisualReferenceIdMap@EndpointInProcUtils@@0V?$ThreadSafeMap@U_GUID@@_K@@A; ThreadSafeMap<_GUID,unsigned __int64> EndpointInProcUtils::s_endpointVisualReferenceIdMap
0x18000b59d  mov     [rsp+78h+arg_18], rbx
0x18000b5a5  mov     rcx, rbx; _Mtx_t
0x18000b5a8  call    cs:__imp__Mtx_lock
0x18000b5ae  test    eax, eax
0x18000b5b0  jnz     loc_18000B837
0x18000b5b6  mov     rcx, rbx; this
0x18000b5b9  call    ?_Verify_ownership_levels@_Mutex_base@std@@IEAA_NXZ; std::_Mutex_base::_Verify_ownership_levels(void)
0x18000b5be  test    al, al
0x18000b5c0  jz      loc_18000B842
0x18000b5c6  movzx   edx, word ptr [rsp+78h+var_58+6]
0x18000b5cb  movq    r10, xmm6
0x18000b5d0  mov     eax, r10d
0x18000b5d3  add     rdx, rax
0x18000b5d6  movzx   eax, word ptr [rsp+78h+var_58+4]
0x18000b5db  add     rdx, rax
0x18000b5de  xor     r8d, r8d
0x18000b5e1  movsxd  rax, r8d
0x18000b5e4  movzx   ecx, byte ptr [rsp+rax+78h+var_58+8]
0x18000b5e9  add     rdx, rcx
0x18000b5ec  inc     r8d
0x18000b5ef  cmp     r8d, 8
0x18000b5f3  jb      short loc_18000B5E1
0x18000b5f5  mov     r11, cs:qword_1800C48E0
0x18000b5fc  mov     rcx, r11
0x18000b5ff  and     rcx, rdx
0x18000b602  add     rcx, rcx
0x18000b605  mov     r8, cs:qword_1800C48C8
0x18000b60c  mov     rax, [r8+rcx*8+8]
0x18000b611  mov     r14, cs:qword_1800C48B8
0x18000b618  movdqa  xmm0, xmm6
0x18000b61c  psrldq  xmm0, 8
0x18000b621  movq    r9, xmm0
0x18000b626  cmp     rax, r14
0x18000b629  jz      short loc_18000B64F
0x18000b62b  mov     rdx, [r8+rcx*8]
0x18000b62f  mov     rcx, r10
0x18000b632  sub     rcx, [rax+10h]
0x18000b636  jnz     short loc_18000B63F
0x18000b638  mov     rcx, r9
0x18000b63b  sub     rcx, [rax+18h]
0x18000b63f  test    rcx, rcx
0x18000b642  jz      short loc_18000B651
0x18000b644  cmp     rax, rdx
0x18000b647  jz      short loc_18000B64F
0x18000b649  mov     rax, [rax+8]
0x18000b64d  jmp     short loc_18000B62F
0x18000b64f  xor     eax, eax
0x18000b651  mov     rcx, r14
0x18000b654  test    rax, rax
0x18000b657  cmovnz  rcx, rax
0x18000b65b  cmp     rcx, r14
0x18000b65e  jz      short loc_18000B682
0x18000b660  mov     [rcx+20h], r12
0x18000b664  mov     rcx, rbx; _Mtx_t
0x18000b667  call    cs:__imp__Mtx_unlock
0x18000b66d  xor     eax, eax
0x18000b66f  movaps  xmm6, [rsp+78h+var_48]
0x18000b674  add     rsp, 48h
0x18000b678  pop     r15
0x18000b67a  pop     r14
0x18000b67c  pop     r12
0x18000b67e  pop     rdi
0x18000b67f  pop     rsi
0x18000b680  pop     rbx
0x18000b681  retn
0x18000b682  movzx   edi, word ptr [rsp+78h+var_58+6]
0x18000b687  mov     eax, r10d
0x18000b68a  add     rdi, rax
0x18000b68d  movzx   eax, word ptr [rsp+78h+var_58+4]
0x18000b692  add     rdi, rax
0x18000b695  xor     edx, edx
0x18000b697  movsxd  rax, edx
0x18000b69a  movzx   ecx, byte ptr [rsp+rax+78h+var_58+8]
0x18000b69f  add     rdi, rcx
0x18000b6a2  inc     edx
0x18000b6a4  cmp     edx, 8
0x18000b6a7  jb      short loc_18000B697
0x18000b6a9  mov     rcx, rdi
0x18000b6ac  and     rcx, r11
0x18000b6af  add     rcx, rcx
0x18000b6b2  mov     rax, [r8+rcx*8+8]
0x18000b6b7  cmp     rax, r14
0x18000b6ba  jz      short loc_18000B6E1
0x18000b6bc  mov     rdx, [r8+rcx*8]
0x18000b6c0  mov     rcx, r10
0x18000b6c3  sub     rcx, [rax+10h]
0x18000b6c7  jnz     short loc_18000B6D0
0x18000b6c9  mov     rcx, r9
0x18000b6cc  sub     rcx, [rax+18h]
0x18000b6d0  test    rcx, rcx
0x18000b6d3  jz      short loc_18000B664
0x18000b6d5  cmp     rax, rdx
0x18000b6d8  jnz     loc_18000B7C0
0x18000b6de  mov     r14, rax
0x18000b6e1  mov     rax, 666666666666666h
0x18000b6eb  cmp     cs:qword_1800C48C0, rax
0x18000b6f2  jz      loc_18000B84E
0x18000b6f8  lea     rax, qword_1800C48B8
0x18000b6ff  mov     qword ptr [rsp+78h+var_58], rax
0x18000b704  mov     qword ptr [rsp+78h+var_58+8], 0
0x18000b70d  mov     ecx, 28h ; '('; Size
0x18000b712  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b717  mov     rsi, rax
0x18000b71a  mov     qword ptr [rsp+78h+var_58+8], rax
0x18000b71f  movdqu  xmmword ptr [rax+10h], xmm6
0x18000b724  mov     [rax+20h], r12
0x18000b728  mov     r8, cs:qword_1800C48C0
0x18000b72f  lea     rdx, [r8+1]
0x18000b733  xorps   xmm0, xmm0
0x18000b736  test    rdx, rdx
0x18000b739  js      loc_18000B7D2
0x18000b73f  cvtsi2ss xmm0, rdx
0x18000b744  mov     rcx, cs:qword_1800C48E8
0x18000b74b  xorps   xmm1, xmm1
0x18000b74e  test    rcx, rcx
0x18000b751  js      loc_18000B7EF
0x18000b757  cvtsi2ss xmm1, rcx
0x18000b75c  divss   xmm0, xmm1
0x18000b760  comiss  xmm0, cs:dword_1800C48B0
0x18000b767  ja      loc_18000B85C
0x18000b76d  mov     rcx, [r14+8]
0x18000b771  inc     r8
0x18000b774  mov     cs:qword_1800C48C0, r8
0x18000b77b  mov     [rsi], r14
0x18000b77e  mov     [rsi+8], rcx
0x18000b782  mov     [rcx], rsi
0x18000b785  mov     [r14+8], rsi
0x18000b789  and     rdi, cs:qword_1800C48E0
0x18000b790  add     rdi, rdi
0x18000b793  mov     rax, cs:qword_1800C48C8
0x18000b79a  mov     rdx, [rax+rdi*8]
0x18000b79e  cmp     rdx, cs:qword_1800C48B8
0x18000b7a5  jz      short loc_18000B7B5
0x18000b7a7  cmp     rdx, r14
0x18000b7aa  jnz     short loc_18000B7C9
0x18000b7ac  mov     [rax+rdi*8], rsi
0x18000b7b0  jmp     loc_18000B664
0x18000b7b5  mov     [rax+rdi*8], rsi
0x18000b7b9  mov     [rax+rdi*8+8], rsi
0x18000b7be  jmp     short loc_18000B7B0
0x18000b7c0  mov     rax, [rax+8]
0x18000b7c4  jmp     loc_18000B6C0
0x18000b7c9  cmp     [rax+rdi*8+8], rcx
0x18000b7ce  jnz     short loc_18000B7B0
0x18000b7d0  jmp     short loc_18000B7B9
0x18000b7d2  mov     rcx, rdx
0x18000b7d5  shr     rcx, 1
0x18000b7d8  mov     rax, rdx
0x18000b7db  and     eax, 1
0x18000b7de  or      rcx, rax
0x18000b7e1  cvtsi2ss xmm0, rcx
0x18000b7e6  addss   xmm0, xmm0
0x18000b7ea  jmp     loc_18000B744
0x18000b7ef  mov     rax, rcx
0x18000b7f2  shr     rax, 1
0x18000b7f5  and     ecx, 1
0x18000b7f8  or      rax, rcx
0x18000b7fb  cvtsi2ss xmm1, rax
0x18000b800  addss   xmm1, xmm1
0x18000b804  jmp     loc_18000B75C
0x18000b809  mov     r9d, 80070057h; char *
0x18000b80f  lea     r8, aOnecoreWindows_8; "onecore\\windows\\accessibletech\\uiama"...
0x18000b816  mov     edx, 89h; void *
0x18000b81b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b820  mov     r9d, 80070057h; char *
0x18000b826  lea     r8, aOnecoreWindows_8; "onecore\\windows\\accessibletech\\uiama"...
0x18000b82d  mov     edx, 8Ah; void *
0x18000b832  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b837  mov     ecx, 5
0x18000b83c  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b842  mov     ecx, 6
0x18000b847  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b84d  nop
0x18000b84e  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18000b855  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b85c  lea     r14, dword_1800C48B0
0x18000b863  mov     rcx, r14
0x18000b866  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Umap_traits@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$optional@VProviderEntrypointId@@@std@@@std@@@3@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Umap_traits<_GUID,std::optional<ProviderEntrypointId>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,std::optional<ProviderEntrypointId>>>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x18000b86b  mov     rdx, rax
0x18000b86e  mov     rcx, r14
0x18000b871  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VUiaManagerCrossMachineStub@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<UiaManagerCrossMachineStub,wil::err_exception_policy>>>,0>>::_Forced_rehash(unsigned __int64)
0x18000b876  mov     r9, rdi
0x18000b879  lea     r8, [rsi+10h]
0x18000b87d  lea     rdx, [rsp+78h+var_58]
0x18000b882  mov     rcx, r14
0x18000b885  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x18000b88a  mov     r14, [rax]
0x18000b88d  mov     r8, cs:qword_1800C48C0
0x18000b894  jmp     loc_18000B76D
0x18000b899  mov     eax, dword ptr [rsp+78h+arg_18]
0x18000b8a0  jmp     loc_18000B66F
```
