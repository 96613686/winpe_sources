# PTIUtils::ParseStoreIds(web::json::value const &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ProductInstallRequest,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ProductInstallRequest>>> &,bool &)

- ea: `0x180036ec8`
- end: `0x1800374cc`
- name: `?ParseStoreIds@PTIUtils@@YAXAEBVvalue@json@web@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VProductInstallRequest@@@std@@@2@@std@@AEA_N@Z`
- size: `1540`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *, bool *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180032ac0`
- `0x180032cfc`

## callees

- `0x1800026b0`
- `0x180006da0`
- `0x180006e10`
- `0x180006f70`
- `0x180008cc0`
- `0x18000d75c`
- `0x18002d674`
- `0x180030aac`
- `0x180031798`
- `0x180031ac0`
- `0x180032fac`
- `0x1800331dc`
- `0x1800368ac`
- `0x180036ec8`
- `0x180037c44`
- `0x18004f010`

## string_xrefs

- `0x180036f22`: `InstallRequestForOtherUsersOnThisDeviceStillRemain`
- `0x180036f5e`: `InstallRequestForOtherUsersOnThisDeviceStillRemain`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PTIUtils::ParseStoreIds(_QWORD *a1, _QWORD *a2, bool *a3)
{
  int v6; // esi
  web::json::value *v7; // rax
  bool v8; // al
  char v9; // bl
  __int64 result; // rax
  web::json::value *v11; // rax
  const struct web::json::array *v12; // rax
  _QWORD *i; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // r8
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // r8
  web::json::value *v20; // rax
  bool v21; // di
  __int128 *v22; // rdx
  __int128 *v23; // rdx
  __int128 *v24; // rdx
  __int64 *v25; // r14
  __int64 *v26; // rdi
  int v27; // r15d
  __int64 *v28; // r12
  __int64 *v29; // rdi
  _OWORD *v30; // rax
  __int64 *v31; // [rsp+30h] [rbp-D0h] BYREF
  int v32; // [rsp+38h] [rbp-C8h]
  int v33; // [rsp+3Ch] [rbp-C4h]
  __int128 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  _QWORD *v36; // [rsp+58h] [rbp-A8h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int128 v38; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h]
  unsigned __int64 v40; // [rsp+80h] [rbp-80h]
  __int128 v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h]
  unsigned __int64 v43; // [rsp+A0h] [rbp-60h]
  __int128 v44; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h]
  __int64 v46; // [rsp+C0h] [rbp-40h]
  bool v47; // [rsp+C8h] [rbp-38h]
  __int128 v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  __int128 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h]
  __int64 v53; // [rsp+108h] [rbp+8h]
  bool v54; // [rsp+110h] [rbp+10h]
  __int128 v55; // [rsp+120h] [rbp+20h] BYREF
  __int64 v56; // [rsp+130h] [rbp+30h]
  unsigned __int64 v57; // [rsp+138h] [rbp+38h]
  __int128 v58; // [rsp+140h] [rbp+40h] BYREF
  __int64 v59; // [rsp+150h] [rbp+50h]
  __int64 v60; // [rsp+158h] [rbp+58h]
  __int128 v61; // [rsp+160h] [rbp+60h] BYREF
  __int64 v62; // [rsp+170h] [rbp+70h]
  __int64 v63; // [rsp+178h] [rbp+78h]
  __int128 v64; // [rsp+180h] [rbp+80h] BYREF
  __int64 v65; // [rsp+190h] [rbp+90h]
  __int64 v66; // [rsp+198h] [rbp+98h]

  v6 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v55, L"InstallRequestForOtherUsersOnThisDeviceStillRemain", 50);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 8LL))(*a1, &v55) )
  {
    v38 = 0;
    v39 = 0;
    v40 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v38, L"InstallRequestForOtherUsersOnThisDeviceStillRemain", 50);
    v6 = 1;
    v7 = (web::json::value *)web::json::value::at(a1, &v38);
    v8 = web::json::value::as_bool(v7);
  }
  else
  {
    v8 = 0;
  }
  *a3 = v8;
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    std::wstring::_Tidy_deallocate(&v38);
  }
  std::wstring::_Tidy_deallocate(&v55);
  v38 = 0;
  v39 = 0;
  v40 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v38, L"productSkuIds", 13);
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a1 + 8LL))(*a1, &v38);
  result = std::wstring::_Tidy_deallocate(&v38);
  if ( v9 )
  {
    v61 = 0;
    v62 = 0;
    v63 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v61, L"productSkuIds", 13);
    v11 = (web::json::value *)web::json::value::at(a1, &v61);
    v12 = web::json::value::as_array(v11);
    v34 = 0;
    v35 = 0;
    std::vector<web::json::value>::_Construct_n<web::json::value * const &,web::json::value * const &>(
      &v34,
      (__int64)(*((_QWORD *)v12 + 1) - *(_QWORD *)v12) >> 3,
      v12);
    std::wstring::_Tidy_deallocate(&v61);
    for ( i = (_QWORD *)v34; i != *((_QWORD **)&v34 + 1); ++i )
    {
      v64 = 0;
      v65 = 0;
      v66 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v64, L"productSkuId", 12);
      v14 = web::json::value::at(i, &v64);
      v15 = (_QWORD *)web::json::value::as_string(v14);
      v38 = 0;
      v39 = 0;
      v40 = 0;
      v16 = v15[2];
      if ( v15[3] > 7u )
        v15 = (_QWORD *)*v15;
      std::wstring::_Construct<2,unsigned short const *>(&v38, v15, v16);
      std::wstring::_Tidy_deallocate(&v64);
      v58 = 0;
      v59 = 0;
      v60 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v58, L"uniqueId", 8);
      v17 = web::json::value::at(i, &v58);
      v18 = (_QWORD *)web::json::value::as_string(v17);
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v19 = v18[2];
      if ( v18[3] > 7u )
        v18 = (_QWORD *)*v18;
      std::wstring::_Construct<2,unsigned short const *>(&v55, v18, v19);
      std::wstring::_Tidy_deallocate(&v58);
      v44 = 0;
      v45 = 0;
      v46 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v44, L"isInteractive", 13);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*i + 8LL))(*i, &v44) )
      {
        v41 = 0;
        v42 = 0;
        v43 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v41, L"isInteractive", 13);
        v6 |= 2u;
        v20 = (web::json::value *)web::json::value::at(i, &v41);
        v21 = web::json::value::as_bool(v20);
      }
      else
      {
        v21 = 0;
      }
      if ( (v6 & 2) != 0 )
      {
        v6 &= ~2u;
        std::wstring::_Tidy_deallocate(&v41);
      }
      std::wstring::_Tidy_deallocate(&v44);
      v41 = 0;
      v42 = 0;
      v43 = 0;
      v22 = &v38;
      if ( v40 > 7 )
        v22 = (__int128 *)v38;
      std::wstring::_Construct<2,unsigned short const *>(&v41, v22, v39);
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v23 = &v41;
      if ( v43 > 7 )
        v23 = (__int128 *)v41;
      std::wstring::_Construct<2,unsigned short const *>(&v44, v23, v42);
      v47 = v21;
      std::wstring::_Tidy_deallocate(&v41);
      v48 = 0;
      v49 = 0;
      v50 = 0;
      v24 = &v55;
      if ( v57 > 7 )
        v24 = (__int128 *)v55;
      std::wstring::_Construct<2,unsigned short const *>(&v48, v24, v56);
      v51 = v44;
      v52 = v45;
      v53 = v46;
      v45 = 0;
      v46 = 7;
      LOWORD(v44) = 0;
      v54 = v21;
      v25 = (__int64 *)*a2;
      v26 = *(__int64 **)(*a2 + 8LL);
      v27 = 0;
      if ( *((_BYTE *)v26 + 25) )
      {
        v28 = *(__int64 **)(*a2 + 8LL);
      }
      else
      {
        do
        {
          v28 = v26;
          *(_QWORD *)&v58 = v26;
          if ( (unsigned __int8)std::operator<<unsigned short>(v26 + 4, &v48) )
          {
            v27 = 0;
            v26 = (__int64 *)v26[2];
          }
          else
          {
            v27 = 1;
            v25 = v26;
            v26 = (__int64 *)*v26;
          }
        }
        while ( !*((_BYTE *)v26 + 25) );
      }
      if ( *((_BYTE *)v25 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v48, v25 + 4) )
      {
        if ( a2[1] == 0x276276276276276LL )
          std::_Throw_tree_length_error();
        v29 = (__int64 *)*a2;
        v36 = a2;
        v37 = 0;
        v30 = operator new(0x68u);
        v30[2] = v48;
        *((_QWORD *)v30 + 6) = v49;
        *((_QWORD *)v30 + 7) = v50;
        v49 = 0;
        v50 = 7;
        LOWORD(v48) = 0;
        v30[4] = v51;
        *((_QWORD *)v30 + 10) = v52;
        *((_QWORD *)v30 + 11) = v53;
        v52 = 0;
        v53 = 7;
        LOWORD(v51) = 0;
        *((_BYTE *)v30 + 96) = v54;
        *(_QWORD *)v30 = v29;
        *((_QWORD *)v30 + 1) = v29;
        *((_QWORD *)v30 + 2) = v29;
        *((_WORD *)v30 + 12) = 0;
        v37 = 0;
        v31 = v28;
        v32 = v27;
        v33 = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,long>>>::_Insert_node(a2, &v31);
      }
      std::wstring::_Tidy_deallocate(&v51);
      std::wstring::_Tidy_deallocate(&v48);
      std::wstring::_Tidy_deallocate(&v44);
      std::wstring::_Tidy_deallocate(&v55);
      std::wstring::_Tidy_deallocate(&v38);
    }
    return std::vector<web::json::value>::_Tidy(&v34);
  }
  return result;
}

```

## disassembly

```asm
0x180036ec8  mov     [rsp-8+arg_18], rbx
0x180036ecd  push    rbp
0x180036ece  push    rsi
0x180036ecf  push    rdi
0x180036ed0  push    r12
0x180036ed2  push    r13
0x180036ed4  push    r14
0x180036ed6  push    r15
0x180036ed8  lea     rbp, [rsp-0B0h]
0x180036ee0  sub     rsp, 1B0h
0x180036ee7  mov     rax, cs:__security_cookie
0x180036eee  xor     rax, rsp
0x180036ef1  mov     [rbp+0E0h+var_40], rax
0x180036ef8  mov     rbx, r8
0x180036efb  mov     r13, rdx
0x180036efe  mov     rdi, rcx
0x180036f01  xor     r14d, r14d
0x180036f04  mov     esi, r14d
0x180036f07  mov     dword ptr [rsp+1E0h+var_1C0], r14d
0x180036f0c  xorps   xmm0, xmm0
0x180036f0f  movups  [rbp+0E0h+var_C0], xmm0
0x180036f13  mov     [rbp+0E0h+var_B0], r14
0x180036f17  mov     [rbp+0E0h+var_A8], r14
0x180036f1b  lea     r15d, [r14+32h]
0x180036f1f  mov     r8d, r15d
0x180036f22  lea     rdx, aInstallrequest; "InstallRequestForOtherUsersOnThisDevice"...
0x180036f29  lea     rcx, [rbp+0E0h+var_C0]
0x180036f2d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036f32  nop
0x180036f33  mov     rcx, [rdi]
0x180036f36  mov     rax, [rcx]
0x180036f39  lea     rdx, [rbp+0E0h+var_C0]
0x180036f3d  mov     rax, [rax+8]
0x180036f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036f46  test    al, al
0x180036f48  jz      short loc_180036F8F
0x180036f4a  xorps   xmm0, xmm0
0x180036f4d  movups  [rsp+1E0h+var_178], xmm0
0x180036f52  mov     [rsp+1E0h+var_168], r14
0x180036f57  mov     [rbp+0E0h+var_160], r14
0x180036f5b  mov     r8d, r15d
0x180036f5e  lea     rdx, aInstallrequest; "InstallRequestForOtherUsersOnThisDevice"...
0x180036f65  lea     rcx, [rsp+1E0h+var_178]
0x180036f6a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036f6f  nop
0x180036f70  lea     esi, [r14+1]
0x180036f74  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x180036f78  lea     rdx, [rsp+1E0h+var_178]
0x180036f7d  mov     rcx, rdi
0x180036f80  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180036f85  mov     rcx, rax; this
0x180036f88  call    ?as_bool@value@json@web@@QEBA_NXZ; web::json::value::as_bool(void)
0x180036f8d  jmp     short loc_180036F92
0x180036f8f  mov     al, r14b
0x180036f92  mov     [rbx], al
0x180036f94  test    sil, 1
0x180036f98  jz      short loc_180036FA8
0x180036f9a  and     esi, 0FFFFFFFEh
0x180036f9d  lea     rcx, [rsp+1E0h+var_178]
0x180036fa2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036fa7  nop
0x180036fa8  lea     rcx, [rbp+0E0h+var_C0]
0x180036fac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036fb1  xorps   xmm0, xmm0
0x180036fb4  movups  [rsp+1E0h+var_178], xmm0
0x180036fb9  mov     [rsp+1E0h+var_168], r14
0x180036fbe  mov     [rbp+0E0h+var_160], r14
0x180036fc2  mov     r15d, 0Dh
0x180036fc8  mov     r8d, r15d
0x180036fcb  lea     rdx, aProductskuids; "productSkuIds"
0x180036fd2  lea     rcx, [rsp+1E0h+var_178]
0x180036fd7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036fdc  nop
0x180036fdd  mov     rcx, [rdi]
0x180036fe0  mov     rax, [rcx]
0x180036fe3  lea     rdx, [rsp+1E0h+var_178]
0x180036fe8  mov     rax, [rax+8]
0x180036fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ff1  mov     bl, al
0x180036ff3  lea     rcx, [rsp+1E0h+var_178]
0x180036ff8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036ffd  test    bl, bl
0x180036fff  jz      loc_18003749C
0x180037005  xorps   xmm0, xmm0
0x180037008  movups  [rbp+0E0h+var_80], xmm0
0x18003700c  mov     [rbp+0E0h+var_70], r14
0x180037010  mov     [rbp+0E0h+var_68], r14
0x180037014  mov     r8d, r15d
0x180037017  lea     rdx, aProductskuids; "productSkuIds"
0x18003701e  lea     rcx, [rbp+0E0h+var_80]
0x180037022  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037027  nop
0x180037028  lea     rdx, [rbp+0E0h+var_80]
0x18003702c  mov     rcx, rdi
0x18003702f  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180037034  mov     rcx, rax; this
0x180037037  call    ?as_array@value@json@web@@QEBAAEBVarray@23@XZ; web::json::value::as_array(void)
0x18003703c  xorps   xmm0, xmm0
0x18003703f  movdqu  [rsp+1E0h+var_1A0], xmm0
0x180037045  mov     [rsp+1E0h+var_190], r14
0x18003704a  lea     r9, [rax+8]
0x18003704e  mov     rdx, [r9]
0x180037051  sub     rdx, [rax]
0x180037054  sar     rdx, 3
0x180037058  mov     r8, rax
0x18003705b  lea     rcx, [rsp+1E0h+var_1A0]
0x180037060  call    ??$_Construct_n@AEBQEAVvalue@json@web@@AEBQEAV123@@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAX_KAEBQEAVvalue@json@web@@1@Z; std::vector<web::json::value>::_Construct_n<web::json::value * const &,web::json::value * const &>(unsigned __int64,web::json::value * const &,web::json::value * const &)
0x180037065  nop
0x180037066  lea     rcx, [rbp+0E0h+var_80]
0x18003706a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003706f  mov     rbx, qword ptr [rsp+1E0h+var_1A0]
0x180037074  cmp     rbx, qword ptr [rsp+1E0h+var_1A0+8]
0x180037079  jz      loc_180037492
0x18003707f  xorps   xmm0, xmm0
0x180037082  movups  [rbp+0E0h+var_60], xmm0
0x180037089  mov     [rbp+0E0h+var_50], r14
0x180037090  mov     [rbp+0E0h+var_48], r14
0x180037097  mov     r8d, 0Ch
0x18003709d  lea     rdx, aProductskuid; "productSkuId"
0x1800370a4  lea     rcx, [rbp+0E0h+var_60]
0x1800370ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800370b0  nop
0x1800370b1  lea     rdx, [rbp+0E0h+var_60]
0x1800370b8  mov     rcx, rbx
0x1800370bb  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800370c0  mov     rcx, rax
0x1800370c3  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x1800370c8  xorps   xmm0, xmm0
0x1800370cb  movups  [rsp+1E0h+var_178], xmm0
0x1800370d0  mov     [rsp+1E0h+var_168], r14
0x1800370d5  mov     [rbp+0E0h+var_160], r14
0x1800370d9  mov     r8, [rax+10h]
0x1800370dd  cmp     qword ptr [rax+18h], 7
0x1800370e2  jbe     short loc_1800370E7
0x1800370e4  mov     rax, [rax]
0x1800370e7  mov     rdx, rax
0x1800370ea  lea     rcx, [rsp+1E0h+var_178]
0x1800370ef  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800370f4  nop
0x1800370f5  lea     rcx, [rbp+0E0h+var_60]
0x1800370fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037101  xorps   xmm0, xmm0
0x180037104  movups  [rbp+0E0h+var_A0], xmm0
0x180037108  mov     [rbp+0E0h+var_90], r14
0x18003710c  mov     [rbp+0E0h+var_88], r14
0x180037110  mov     r8d, 8
0x180037116  lea     rdx, aUniqueid; "uniqueId"
0x18003711d  lea     rcx, [rbp+0E0h+var_A0]
0x180037121  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037126  nop
0x180037127  lea     rdx, [rbp+0E0h+var_A0]
0x18003712b  mov     rcx, rbx
0x18003712e  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x180037133  mov     rcx, rax
0x180037136  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; web::json::value::as_string(void)
0x18003713b  xorps   xmm0, xmm0
0x18003713e  movups  [rbp+0E0h+var_C0], xmm0
0x180037142  mov     [rbp+0E0h+var_B0], r14
0x180037146  mov     [rbp+0E0h+var_A8], r14
0x18003714a  mov     r8, [rax+10h]
0x18003714e  cmp     qword ptr [rax+18h], 7
0x180037153  jbe     short loc_180037158
0x180037155  mov     rax, [rax]
0x180037158  mov     rdx, rax
0x18003715b  lea     rcx, [rbp+0E0h+var_C0]
0x18003715f  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180037164  nop
0x180037165  lea     rcx, [rbp+0E0h+var_A0]
0x180037169  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003716e  xorps   xmm0, xmm0
0x180037171  movups  [rbp+0E0h+var_138], xmm0
0x180037175  mov     [rbp+0E0h+var_128], r14
0x180037179  mov     [rbp+0E0h+var_120], r14
0x18003717d  mov     r8, r15
0x180037180  lea     rdx, aIsinteractive; "isInteractive"
0x180037187  lea     rcx, [rbp+0E0h+var_138]
0x18003718b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037190  nop
0x180037191  mov     rcx, [rbx]
0x180037194  mov     rax, [rcx]
0x180037197  lea     rdx, [rbp+0E0h+var_138]
0x18003719b  mov     rax, [rax+8]
0x18003719f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371a4  test    al, al
0x1800371a6  jz      short loc_1800371EB
0x1800371a8  xorps   xmm0, xmm0
0x1800371ab  movups  [rbp+0E0h+var_158], xmm0
0x1800371af  mov     [rbp+0E0h+var_148], r14
0x1800371b3  mov     [rbp+0E0h+var_140], r14
0x1800371b7  mov     r8, r15
0x1800371ba  lea     rdx, aIsinteractive; "isInteractive"
0x1800371c1  lea     rcx, [rbp+0E0h+var_158]
0x1800371c5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800371ca  nop
0x1800371cb  or      esi, 2
0x1800371ce  mov     dword ptr [rsp+1E0h+var_1C0], esi
0x1800371d2  lea     rdx, [rbp+0E0h+var_158]
0x1800371d6  mov     rcx, rbx
0x1800371d9  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800371de  mov     rcx, rax; this
0x1800371e1  call    ?as_bool@value@json@web@@QEBA_NXZ; web::json::value::as_bool(void)
0x1800371e6  mov     dil, al
0x1800371e9  jmp     short loc_1800371EE
0x1800371eb  mov     dil, r14b
0x1800371ee  test    sil, 2
0x1800371f2  jz      short loc_180037201
0x1800371f4  and     esi, 0FFFFFFFDh
0x1800371f7  lea     rcx, [rbp+0E0h+var_158]
0x1800371fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037200  nop
0x180037201  lea     rcx, [rbp+0E0h+var_138]
0x180037205  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003720a  xorps   xmm0, xmm0
0x18003720d  movups  [rbp+0E0h+var_158], xmm0
0x180037211  mov     [rbp+0E0h+var_148], r14
0x180037215  mov     [rbp+0E0h+var_140], r14
0x180037219  lea     rdx, [rsp+1E0h+var_178]
0x18003721e  cmp     [rbp+0E0h+var_160], 7
0x180037223  cmova   rdx, qword ptr [rsp+1E0h+var_178]
0x180037229  mov     r8, [rsp+1E0h+var_168]
0x18003722e  lea     rcx, [rbp+0E0h+var_158]
0x180037232  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180037237  lea     rax, [rbp+0E0h+var_158]
0x18003723b  mov     [rsp+1E0h+var_1C0], rax
0x180037240  xorps   xmm0, xmm0
0x180037243  movups  [rbp+0E0h+var_138], xmm0
0x180037247  mov     [rbp+0E0h+var_128], r14
0x18003724b  mov     [rbp+0E0h+var_120], r14
0x18003724f  lea     rdx, [rbp+0E0h+var_158]
0x180037253  cmp     [rbp+0E0h+var_140], 7
0x180037258  cmova   rdx, qword ptr [rbp+0E0h+var_158]
0x18003725d  mov     r8, [rbp+0E0h+var_148]
0x180037261  lea     rcx, [rbp+0E0h+var_138]
0x180037265  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18003726a  mov     [rbp+0E0h+var_118], dil
0x18003726e  lea     rcx, [rbp+0E0h+var_158]
0x180037272  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037277  nop
0x180037278  xorps   xmm0, xmm0
0x18003727b  movups  [rbp+0E0h+var_110], xmm0
0x18003727f  mov     [rbp+0E0h+var_100], r14
0x180037283  mov     [rbp+0E0h+var_F8], r14
0x180037287  lea     rdx, [rbp+0E0h+var_C0]
0x18003728b  cmp     [rbp+0E0h+var_A8], 7
0x180037290  cmova   rdx, qword ptr [rbp+0E0h+var_C0]
0x180037295  mov     r8, [rbp+0E0h+var_B0]
0x180037299  lea     rcx, [rbp+0E0h+var_110]
0x18003729d  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x1800372a2  xorps   xmm0, xmm0
0x1800372a5  movups  [rbp+0E0h+var_F0], xmm0
0x1800372a9  movzx   eax, word ptr [rbp+0E0h+var_138]
0x1800372ad  mov     word ptr [rbp+0E0h+var_F0], ax
0x1800372b1  movsd   xmm0, qword ptr [rbp+0E0h+var_138+2]
0x1800372b6  movsd   qword ptr [rbp+0E0h+var_F0+2], xmm0
0x1800372bb  mov     eax, dword ptr [rbp+0E0h+var_138+0Ah]
0x1800372be  mov     dword ptr [rbp+0E0h+var_F0+0Ah], eax
0x1800372c1  movzx   eax, word ptr [rbp+0E0h+var_138+0Eh]
0x1800372c5  mov     word ptr [rbp+0E0h+var_F0+0Eh], ax
0x1800372c9  mov     rax, [rbp+0E0h+var_128]
0x1800372cd  mov     [rbp+0E0h+var_E0], rax
0x1800372d1  mov     rax, [rbp+0E0h+var_120]
0x1800372d5  mov     [rbp+0E0h+var_D8], rax
0x1800372d9  mov     [rbp+0E0h+var_128], r14
0x1800372dd  mov     [rbp+0E0h+var_120], 7
0x1800372e5  mov     word ptr [rbp+0E0h+var_138], r14w
0x1800372ea  mov     [rbp+0E0h+var_D0], dil
0x1800372ee  mov     r14, [r13+0]
0x1800372f2  mov     rdi, [r14+8]
0x1800372f6  xor     r15d, r15d
0x1800372f9  xor     eax, eax
0x1800372fb  mov     [rsp+1E0h+var_1C0], rax
0x180037300  cmp     [rdi+19h], al
0x180037303  jnz     short loc_18003733A
0x180037305  mov     r12, rdi
0x180037308  mov     qword ptr [rbp+0E0h+var_A0], rdi
0x18003730c  lea     rcx, [rdi+20h]
0x180037310  lea     rdx, [rbp+0E0h+var_110]
0x180037314  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180037319  test    al, al
0x18003731b  jz      short loc_180037326
0x18003731d  xor     r15d, r15d
0x180037320  mov     rdi, [rdi+10h]
0x180037324  jmp     short loc_180037332
0x180037326  mov     r15d, 1
0x18003732c  mov     r14, rdi
0x18003732f  mov     rdi, [rdi]
0x180037332  cmp     byte ptr [rdi+19h], 0
0x180037336  jz      short loc_180037305
0x180037338  jmp     short loc_18003733D
0x18003733a  mov     r12, rdi
0x18003733d  cmp     byte ptr [r14+19h], 0
0x180037342  jnz     short loc_18003735E
0x180037344  lea     rdx, [r14+20h]
0x180037348  lea     rcx, [rbp+0E0h+var_110]
0x18003734c  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180037351  xor     r14d, r14d
0x180037354  test    al, al
0x180037356  jz      loc_180037452
0x18003735c  jmp     short loc_180037361
0x18003735e  xor     r14d, r14d
  ... truncated ...
```
