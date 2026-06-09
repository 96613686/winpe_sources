# GetEnabledKeyRollouts(ulong *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180013ad4`
- end: `0x180013d67`
- name: `?GetEnabledKeyRollouts@@YAXPEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001e5d0`

## callees

- `0x18000bc54`
- `0x180013ad4`
- `0x180023924`
- `0x180023960`
- `0x18002399c`
- `0x1800239d8`
- `0x180023a14`
- `0x180023a8c`
- `0x180023ac8`
- `0x180023b7c`
- `0x180023bb8`
- `0x180023c30`

## string_xrefs

- `0x180013b4a`: `DBUpdateExternalRollout`
- `0x180013b43`: ` | DBUpdateExternalRollout`
- `0x180013b8d`: `KEKUpdateAllowList`
- `0x180013b82`: ` | KEKUpdateAllowList`
- `0x180013bcc`: `DBUpdate3PUEFICARollout`
- `0x180013bc1`: ` | DBUpdate3PUEFICARollout`
- `0x180013c0b`: `DBUpdate3POROMRollout`
- `0x180013c00`: ` | DBUpdate3POROMRollout`
- `0x180013b0a`: `DBUpdateInternalRollout`
- `0x180013b03`: ` | DBUpdateInternalRollout`
- `0x180013cff`: `Feature_SkipCanAttemptUpdateAfter_Wait`
- `0x180013cf8`: ` | Feature_SkipCanAttemptUpdateAfter_Wait`

## pseudocode

```c
__int64 __fastcall GetEnabledKeyRollouts(int *a1, __int64 a2)
{
  __int64 v4; // rdi
  int v5; // esi
  const wchar_t *v6; // rdx
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  __int64 v9; // r8
  const wchar_t *v10; // rdx
  __int64 v11; // r8
  const wchar_t *v12; // rdx
  __int64 v13; // r8
  const wchar_t *v14; // rdx
  __int64 v15; // r8
  const wchar_t *v16; // rdx
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  __int64 v19; // r8
  const wchar_t *v20; // rdx
  __int64 v21; // r8
  const wchar_t *v22; // rdx
  __int64 v23; // r8
  __int64 result; // rax
  const wchar_t *v25; // rdx

  v4 = -1;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_DBUpdateFlighting>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DBUpdateFlighting>::GetImpl'::`2'::impl) )
  {
    v6 = L"DBUpdateInternalRollout";
    v5 = 64;
    if ( *(_QWORD *)(a2 + 16) )
      v6 = L" | DBUpdateInternalRollout";
    v7 = -1;
    do
      ++v7;
    while ( v6[v7] );
    std::wstring::_Append<unsigned short>(a2, v6, v7);
  }
  else
  {
    v5 = 0;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout>::GetImpl'::`2'::impl) )
  {
    v8 = L"DBUpdateExternalRollout";
    v5 = 64;
    if ( *(_QWORD *)(a2 + 16) )
      v8 = L" | DBUpdateExternalRollout";
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    std::wstring::_Append<unsigned short>(a2, v8, v9);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_KEKUpdateAllowList>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_KEKUpdateAllowList>::GetImpl'::`2'::impl) )
  {
    v5 |= 4u;
    v10 = L"KEKUpdateAllowList";
    v11 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v10 = L" | KEKUpdateAllowList";
    do
      ++v11;
    while ( v10[v11] );
    std::wstring::_Append<unsigned short>(a2, v10, v11);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3PUEFICARollout>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Allow3PUEFICARollout>::GetImpl'::`2'::impl) )
  {
    v5 |= 0x1000u;
    v12 = L"DBUpdate3PUEFICARollout";
    v13 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v12 = L" | DBUpdate3PUEFICARollout";
    do
      ++v13;
    while ( v12[v13] );
    std::wstring::_Append<unsigned short>(a2, v12, v13);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3POROMRollout>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Allow3POROMRollout>::GetImpl'::`2'::impl) )
  {
    v5 |= 0x800u;
    v14 = L"DBUpdate3POROMRollout";
    v15 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v14 = L" | DBUpdate3POROMRollout";
    do
      ++v15;
    while ( v14[v15] );
    std::wstring::_Append<unsigned short>(a2, v14, v15);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_PCA2023BootMgrUpdate>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_PCA2023BootMgrUpdate>::GetImpl'::`2'::impl) )
  {
    v5 |= 0x100u;
    v16 = L"PCA2023BootMgrRollout";
    v17 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v16 = L" | PCA2023BootMgrRollout";
    do
      ++v17;
    while ( v16[v17] );
    std::wstring::_Append<unsigned short>(a2, v16, v17);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestKeyRolling>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestKeyRolling>::GetImpl'::`2'::impl) )
  {
    v5 |= 0x2000u;
    v18 = L"TestKeyRolling";
    v19 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v18 = L" | TestKeyRolling";
    do
      ++v19;
    while ( v18[v19] );
    std::wstring::_Append<unsigned short>(a2, v18, v19);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipDeviceCheck>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SkipDeviceCheck>::GetImpl'::`2'::impl) )
  {
    v20 = L"Feature_SkipDeviceCheck";
    v21 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v20 = L" | Feature_SkipDeviceCheck";
    do
      ++v21;
    while ( v20[v21] );
    std::wstring::_Append<unsigned short>(a2, v20, v21);
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait>::GetImpl'::`2'::impl) )
  {
    v22 = L"Feature_SkipCanAttemptUpdateAfter_Wait";
    v23 = -1;
    if ( *(_QWORD *)(a2 + 16) )
      v22 = L" | Feature_SkipCanAttemptUpdateAfter_Wait";
    do
      ++v23;
    while ( v22[v23] );
    std::wstring::_Append<unsigned short>(a2, v22, v23);
  }
  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS>::GetImpl'::`2'::impl);
  if ( (_BYTE)result )
  {
    v25 = L"Feature_AllKeysAndBootMgrByWinCS";
    if ( *(_QWORD *)(a2 + 16) )
      v25 = L" | Feature_AllKeysAndBootMgrByWinCS";
    do
      ++v4;
    while ( v25[v4] );
    result = std::wstring::_Append<unsigned short>(a2, v25, v4);
  }
  *a1 = v5;
  return result;
}

```

## disassembly

```asm
0x180013ad4  push    rbx
0x180013ad6  push    rbp
0x180013ad7  push    rsi
0x180013ad8  push    rdi
0x180013ad9  push    r14
0x180013adb  sub     rsp, 20h
0x180013adf  mov     rbx, rdx
0x180013ae2  mov     r14, rcx
0x180013ae5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DBUpdateFlighting@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DBUpdateFlighting@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DBUpdateFlighting> `wil::Feature<__WilFeatureTraits_Feature_DBUpdateFlighting>::GetImpl(void)'::`2'::impl
0x180013aec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DBUpdateFlighting@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DBUpdateFlighting>::__private_IsEnabled(void)
0x180013af1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013af5  xor     ebp, ebp
0x180013af7  test    al, al
0x180013af9  jnz     short loc_180013AFF
0x180013afb  mov     esi, ebp
0x180013afd  jmp     short loc_180013B2F
0x180013aff  cmp     [rbx+10h], rbp
0x180013b03  lea     rax, aDbupdateintern; " | DBUpdateInternalRollout"
0x180013b0a  lea     rdx, aDbupdateintern_0; "DBUpdateInternalRollout"
0x180013b11  mov     esi, 40h ; '@'
0x180013b16  cmovnz  rdx, rax
0x180013b1a  mov     r8, rdi
0x180013b1d  inc     r8
0x180013b20  cmp     [rdx+r8*2], bp
0x180013b25  jnz     short loc_180013B1D
0x180013b27  mov     rcx, rbx
0x180013b2a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013b2f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout> `wil::Feature<__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout>::GetImpl(void)'::`2'::impl
0x180013b36  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllowDBUpdate2023Rollout>::__private_IsEnabled(void)
0x180013b3b  test    al, al
0x180013b3d  jz      short loc_180013B6F
0x180013b3f  cmp     [rbx+10h], rbp
0x180013b43  lea     rax, aDbupdateextern; " | DBUpdateExternalRollout"
0x180013b4a  lea     rdx, aDbupdateextern_0; "DBUpdateExternalRollout"
0x180013b51  mov     esi, 40h ; '@'
0x180013b56  cmovnz  rdx, rax
0x180013b5a  mov     r8, rdi
0x180013b5d  inc     r8
0x180013b60  cmp     [rdx+r8*2], bp
0x180013b65  jnz     short loc_180013B5D
0x180013b67  mov     rcx, rbx
0x180013b6a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013b6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KEKUpdateAllowList@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KEKUpdateAllowList@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KEKUpdateAllowList> `wil::Feature<__WilFeatureTraits_Feature_KEKUpdateAllowList>::GetImpl(void)'::`2'::impl
0x180013b76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_KEKUpdateAllowList@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KEKUpdateAllowList>::__private_IsEnabled(void)
0x180013b7b  test    al, al
0x180013b7d  jz      short loc_180013BAD
0x180013b7f  or      esi, 4
0x180013b82  lea     rax, aKekupdateallow; " | KEKUpdateAllowList"
0x180013b89  cmp     [rbx+10h], rbp
0x180013b8d  lea     rdx, aKekupdateallow_0; "KEKUpdateAllowList"
0x180013b94  mov     r8, rdi
0x180013b97  cmovnz  rdx, rax
0x180013b9b  inc     r8
0x180013b9e  cmp     [rdx+r8*2], bp
0x180013ba3  jnz     short loc_180013B9B
0x180013ba5  mov     rcx, rbx
0x180013ba8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013bad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Allow3PUEFICARollout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Allow3PUEFICARollout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3PUEFICARollout> `wil::Feature<__WilFeatureTraits_Feature_Allow3PUEFICARollout>::GetImpl(void)'::`2'::impl
0x180013bb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Allow3PUEFICARollout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3PUEFICARollout>::__private_IsEnabled(void)
0x180013bb9  test    al, al
0x180013bbb  jz      short loc_180013BEC
0x180013bbd  bts     esi, 0Ch
0x180013bc1  lea     rax, aDbupdate3puefi_0; " | DBUpdate3PUEFICARollout"
0x180013bc8  cmp     [rbx+10h], rbp
0x180013bcc  lea     rdx, aDbupdate3puefi; "DBUpdate3PUEFICARollout"
0x180013bd3  mov     r8, rdi
0x180013bd6  cmovnz  rdx, rax
0x180013bda  inc     r8
0x180013bdd  cmp     [rdx+r8*2], bp
0x180013be2  jnz     short loc_180013BDA
0x180013be4  mov     rcx, rbx
0x180013be7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013bec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Allow3POROMRollout@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Allow3POROMRollout@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3POROMRollout> `wil::Feature<__WilFeatureTraits_Feature_Allow3POROMRollout>::GetImpl(void)'::`2'::impl
0x180013bf3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Allow3POROMRollout@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Allow3POROMRollout>::__private_IsEnabled(void)
0x180013bf8  test    al, al
0x180013bfa  jz      short loc_180013C2B
0x180013bfc  bts     esi, 0Bh
0x180013c00  lea     rax, aDbupdate3porom; " | DBUpdate3POROMRollout"
0x180013c07  cmp     [rbx+10h], rbp
0x180013c0b  lea     rdx, aDbupdate3porom_0; "DBUpdate3POROMRollout"
0x180013c12  mov     r8, rdi
0x180013c15  cmovnz  rdx, rax
0x180013c19  inc     r8
0x180013c1c  cmp     [rdx+r8*2], bp
0x180013c21  jnz     short loc_180013C19
0x180013c23  mov     rcx, rbx
0x180013c26  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013c2b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PCA2023BootMgrUpdate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PCA2023BootMgrUpdate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PCA2023BootMgrUpdate> `wil::Feature<__WilFeatureTraits_Feature_PCA2023BootMgrUpdate>::GetImpl(void)'::`2'::impl
0x180013c32  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PCA2023BootMgrUpdate@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PCA2023BootMgrUpdate>::__private_IsEnabled(void)
0x180013c37  test    al, al
0x180013c39  jz      short loc_180013C6A
0x180013c3b  bts     esi, 8
0x180013c3f  lea     rax, aPca2023bootmgr; " | PCA2023BootMgrRollout"
0x180013c46  cmp     [rbx+10h], rbp
0x180013c4a  lea     rdx, aPca2023bootmgr_0; "PCA2023BootMgrRollout"
0x180013c51  mov     r8, rdi
0x180013c54  cmovnz  rdx, rax
0x180013c58  inc     r8
0x180013c5b  cmp     [rdx+r8*2], bp
0x180013c60  jnz     short loc_180013C58
0x180013c62  mov     rcx, rbx
0x180013c65  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013c6a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestKeyRolling@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestKeyRolling@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestKeyRolling> `wil::Feature<__WilFeatureTraits_Feature_TestKeyRolling>::GetImpl(void)'::`2'::impl
0x180013c71  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestKeyRolling@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestKeyRolling>::__private_IsEnabled(void)
0x180013c76  test    al, al
0x180013c78  jz      short loc_180013CA9
0x180013c7a  bts     esi, 0Dh
0x180013c7e  lea     rax, aTestkeyrolling_2; " | TestKeyRolling"
0x180013c85  cmp     [rbx+10h], rbp
0x180013c89  lea     rdx, aTestkeyrolling_0; "TestKeyRolling"
0x180013c90  mov     r8, rdi
0x180013c93  cmovnz  rdx, rax
0x180013c97  inc     r8
0x180013c9a  cmp     [rdx+r8*2], bp
0x180013c9f  jnz     short loc_180013C97
0x180013ca1  mov     rcx, rbx
0x180013ca4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013ca9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SkipDeviceCheck@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SkipDeviceCheck@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipDeviceCheck> `wil::Feature<__WilFeatureTraits_Feature_SkipDeviceCheck>::GetImpl(void)'::`2'::impl
0x180013cb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SkipDeviceCheck@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipDeviceCheck>::__private_IsEnabled(void)
0x180013cb5  test    al, al
0x180013cb7  jz      short loc_180013CE4
0x180013cb9  cmp     [rbx+10h], rbp
0x180013cbd  lea     rax, aFeatureSkipdev; " | Feature_SkipDeviceCheck"
0x180013cc4  lea     rdx, aFeatureSkipdev_0; "Feature_SkipDeviceCheck"
0x180013ccb  mov     r8, rdi
0x180013cce  cmovnz  rdx, rax
0x180013cd2  inc     r8
0x180013cd5  cmp     [rdx+r8*2], bp
0x180013cda  jnz     short loc_180013CD2
0x180013cdc  mov     rcx, rbx
0x180013cdf  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013ce4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait> `wil::Feature<__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait>::GetImpl(void)'::`2'::impl
0x180013ceb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SkipCanAttemptUpdateAfter_Wait>::__private_IsEnabled(void)
0x180013cf0  test    al, al
0x180013cf2  jz      short loc_180013D1F
0x180013cf4  cmp     [rbx+10h], rbp
0x180013cf8  lea     rax, aFeatureSkipcan; " | Feature_SkipCanAttemptUpdateAfter_Wa"...
0x180013cff  lea     rdx, aFeatureSkipcan_0; "Feature_SkipCanAttemptUpdateAfter_Wait"
0x180013d06  mov     r8, rdi
0x180013d09  cmovnz  rdx, rax
0x180013d0d  inc     r8
0x180013d10  cmp     [rdx+r8*2], bp
0x180013d15  jnz     short loc_180013D0D
0x180013d17  mov     rcx, rbx
0x180013d1a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013d1f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS> `wil::Feature<__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS>::GetImpl(void)'::`2'::impl
0x180013d26  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AllKeysAndBootMgrByWinCS>::__private_IsEnabled(void)
0x180013d2b  test    al, al
0x180013d2d  jz      short loc_180013D59
0x180013d2f  cmp     [rbx+10h], rbp
0x180013d33  lea     rax, aFeatureAllkeys_1; " | Feature_AllKeysAndBootMgrByWinCS"
0x180013d3a  lea     rdx, aFeatureAllkeys; "Feature_AllKeysAndBootMgrByWinCS"
0x180013d41  cmovnz  rdx, rax
0x180013d45  inc     rdi
0x180013d48  cmp     [rdx+rdi*2], bp
0x180013d4c  jnz     short loc_180013D45
0x180013d4e  mov     r8, rdi
0x180013d51  mov     rcx, rbx
0x180013d54  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180013d59  mov     [r14], esi
0x180013d5c  add     rsp, 20h
0x180013d60  pop     r14
0x180013d62  pop     rdi
0x180013d63  pop     rsi
0x180013d64  pop     rbp
0x180013d65  pop     rbx
0x180013d66  retn
```
