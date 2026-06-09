# wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(Windows::Data::Platform::ItemReference<Windows::Data::Nlm::NlmSignature> const *)

- ea: `0x180005bb0`
- end: `0x180005d58`
- name: `??$validate_cloud_store_data_reference@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AUvalidated_data_reference@01@PEBU?$ItemReference@UNlmSignature@Nlm@Data@Windows@@@Platform@Data@Windows@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, const char *)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180003850`
- `0x18003019c`

## callees

- `0x180005ac0`
- `0x180005bb0`
- `0x180005d60`
- `0x1800062c0`
- `0x180006a44`
- `0x180025308`
- `0x180026bc8`
- `0x18002a030`
- `0x18002c138`

## pseudocode

```c
__int64 __fastcall wil::cloud_store::validate_cloud_store_data_reference<Windows::Data::Nlm::NlmSignature>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        const char *a4)
{
  _QWORD *v4; // rdi
  _WORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 *v10; // rdx
  size_t v11; // r8
  __int128 v13; // [rsp+48h] [rbp-30h] BYREF
  __int128 v14; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = a2;
  if ( a2 )
  {
    if ( a2[3] <= 7u )
      v6 = a2;
    else
      v6 = (_WORD *)*a2;
    if ( !*v6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6E7,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\clouddata.h",
        a4);
    v7 = a2 + 4;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v8 = v7[2];
    if ( v7[3] > 7u )
      v7 = (_QWORD *)*v7;
    std::wstring::_Construct<2,unsigned short const *>(a1, v7, v8);
    *(_OWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 48) = 0;
    *(_QWORD *)(a1 + 56) = 0;
    v9 = v4[2];
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    std::wstring::_Construct<2,unsigned short const *>(a1 + 32, v4, v9);
    v10 = &qword_180052AA0;
    if ( (unsigned __int64)qword_180052AB8 > 0xF )
      v10 = (__int64 *)qword_180052AA0;
    v13 = 0;
    v14 = 0;
    v11 = -1;
    do
      ++v11;
    while ( *((_BYTE *)v10 + v11) );
    std::string::_Construct<1,char const *>(&v13, v10, v11);
    wil::cloud_store::widen_string(a1 + 64, &v13);
    if ( *((_QWORD *)&v14 + 1) > 0xFu )
      std::_Deallocate<16>((void *)v13, *((_QWORD *)&v14 + 1) + 1LL);
  }
  else
  {
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)a1, byte_180043BA0, 0);
    *(_OWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 48) = 0;
    *(_QWORD *)(a1 + 56) = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)(a1 + 32), byte_180043BA0, 0);
    wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>(a1 + 64);
  }
  return a1;
}

```

## disassembly

```asm
0x180005bb0  mov     [rsp+arg_10], rbx
0x180005bb5  mov     [rsp+arg_18], rsi
0x180005bba  push    rdi
0x180005bbb  sub     rsp, 70h
0x180005bbf  mov     rax, cs:__security_cookie
0x180005bc6  xor     rax, rsp
0x180005bc9  mov     [rsp+78h+var_10], rax
0x180005bce  mov     rdi, rdx
0x180005bd1  mov     rbx, rcx
0x180005bd4  mov     [rsp+78h+var_48], rcx
0x180005bd9  xor     esi, esi
0x180005bdb  test    rdx, rdx
0x180005bde  jz      loc_180005CE7
0x180005be4  cmp     qword ptr [rdx+18h], 7
0x180005be9  jbe     loc_180005CDF
0x180005bef  mov     rax, [rdx]
0x180005bf2  mov     rcx, [rsp+78h]; this
0x180005bf7  cmp     [rax], si
0x180005bfa  jz      loc_180005D33
0x180005c00  add     rdx, 20h ; ' '
0x180005c04  xorps   xmm0, xmm0
0x180005c07  movups  xmmword ptr [rbx], xmm0
0x180005c0a  mov     [rbx+10h], rsi
0x180005c0e  mov     [rbx+18h], rsi
0x180005c12  mov     r8, [rdx+10h]
0x180005c16  cmp     qword ptr [rdx+18h], 7
0x180005c1b  jbe     short loc_180005C20
0x180005c1d  mov     rdx, [rdx]
0x180005c20  mov     rcx, rbx
0x180005c23  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180005c28  nop
0x180005c29  lea     rcx, [rbx+20h]
0x180005c2d  xorps   xmm0, xmm0
0x180005c30  movups  xmmword ptr [rcx], xmm0
0x180005c33  mov     [rcx+10h], rsi
0x180005c37  mov     [rcx+18h], rsi
0x180005c3b  mov     r8, [rdi+10h]
0x180005c3f  cmp     qword ptr [rdi+18h], 7
0x180005c44  ja      loc_180005CD7
0x180005c4a  mov     rdx, rdi
0x180005c4d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180005c52  nop
0x180005c53  lea     rdx, qword_180052AA0
0x180005c5a  cmp     cs:qword_180052AB8, 0Fh
0x180005c62  cmova   rdx, cs:qword_180052AA0
0x180005c6a  xorps   xmm0, xmm0
0x180005c6d  movups  [rsp+78h+var_30], xmm0
0x180005c72  xorps   xmm1, xmm1
0x180005c75  movdqu  [rsp+78h+var_20], xmm1
0x180005c7b  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180005c82  inc     r8
0x180005c85  cmp     byte ptr [rdx+r8], 0
0x180005c8a  jnz     short loc_180005C82
0x180005c8c  lea     rcx, [rsp+78h+var_30]
0x180005c91  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180005c96  nop
0x180005c97  lea     rdx, [rsp+78h+var_30]
0x180005c9c  lea     rcx, [rbx+40h]
0x180005ca0  call    ?widen_string@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; wil::cloud_store::widen_string(std::string const &)
0x180005ca5  nop
0x180005ca6  mov     rdx, qword ptr [rsp+78h+var_20+8]
0x180005cab  cmp     rdx, 0Fh
0x180005caf  ja      loc_180005D45
0x180005cb5  mov     rax, rbx
0x180005cb8  mov     rcx, [rsp+78h+var_10]
0x180005cbd  xor     rcx, rsp; StackCookie
0x180005cc0  call    __security_check_cookie
0x180005cc5  lea     r11, [rsp+78h+var_8]
0x180005cca  mov     rbx, [r11+20h]
0x180005cce  mov     rsi, [r11+28h]
0x180005cd2  mov     rsp, r11
0x180005cd5  pop     rdi
0x180005cd6  retn
0x180005cd7  mov     rdi, [rdi]
0x180005cda  jmp     loc_180005C4A
0x180005cdf  mov     rax, rdi
0x180005ce2  jmp     loc_180005BF2
0x180005ce7  xorps   xmm0, xmm0
0x180005cea  movups  xmmword ptr [rcx], xmm0
0x180005ced  mov     [rcx+10h], rsi
0x180005cf1  mov     [rcx+18h], rsi
0x180005cf5  xor     r8d, r8d
0x180005cf8  lea     rdx, byte_180043BA0
0x180005cff  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180005d04  nop
0x180005d05  lea     rcx, [rbx+20h]
0x180005d09  xorps   xmm0, xmm0
0x180005d0c  movups  xmmword ptr [rcx], xmm0
0x180005d0f  mov     [rcx+10h], rsi
0x180005d13  mov     [rcx+18h], rsi
0x180005d17  xor     r8d, r8d
0x180005d1a  lea     rdx, byte_180043BA0
0x180005d21  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180005d26  nop
0x180005d27  lea     rcx, [rbx+40h]
0x180005d2b  call    ??$get_type_name_wide_string@UNlmSignature@Nlm@Data@Windows@@@cloud_store@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::cloud_store::get_type_name_wide_string<Windows::Data::Nlm::NlmSignature>(void)
0x180005d30  nop
0x180005d31  jmp     short loc_180005CB5
0x180005d33  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\wil\\cl"...
0x180005d3a  mov     edx, 6E7h; void *
0x180005d3f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005d45  inc     rdx
0x180005d48  mov     rcx, qword ptr [rsp+78h+var_30]
0x180005d4d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180005d52  jmp     loc_180005CB5
```
