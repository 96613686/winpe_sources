# TryTrimVstoManifestPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004c1a4`
- end: `0x18004c479`
- name: `?TryTrimVstoManifestPath@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bf0c`

## callees

- `0x180001cf0`
- `0x1800020a0`
- `0x180002d1c`
- `0x180002d84`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000e504`
- `0x18002649c`
- `0x18004824c`
- `0x180048714`
- `0x18004c1a4`
- `0x1800543c0`

## string_xrefs

- `0x18004c1e9`: `Manifest Path: %ws`
- `0x18004c1f6`: `TryTrimVstoManifestPath`
- `0x18004c2c1`: `TryTrimVstoManifestPath`
- `0x18004c3a4`: `TryTrimVstoManifestPath`
- `0x18004c397`: `Manifest Path: %ws, Result Path: %ws`
- `0x18004c2b4`: `Found unrecognized pattern of the manifest path: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall TryTrimVstoManifestPath(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  int *v5; // rsi
  __int128 *v7; // rax
  char *v8; // r8
  __int128 v9; // xmm0
  __int64 v10; // [rsp+58h] [rbp-59h] BYREF
  char v11; // [rsp+60h] [rbp-51h]
  _OWORD v12[2]; // [rsp+68h] [rbp-49h] BYREF
  __int64 v13; // [rsp+88h] [rbp-29h]
  char v14; // [rsp+90h] [rbp-21h]
  __int128 v15; // [rsp+98h] [rbp-19h]
  char v16; // [rsp+A8h] [rbp-9h]
  _QWORD v17[2]; // [rsp+B0h] [rbp-1h] BYREF
  char v18; // [rsp+C0h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+C8h] [rbp+17h]
  __int128 v20; // [rsp+D0h] [rbp+1Fh] BYREF
  __int128 v21; // [rsp+E0h] [rbp+2Fh]

  v19 = -2;
  v3 = a1;
  if ( a1[3] <= 7u )
    v4 = a1;
  else
    v4 = (_QWORD *)*a1;
  AslLogCallPrintf(3, "TryTrimVstoManifestPath", 61, "Manifest Path: %ws", v4);
  v5 = (int *)&unk_180097D50;
  if ( dword_180097D48 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180097D48);
    if ( dword_180097D48 == -1 )
    {
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097D50,
        L"file:///(.*\\.vsto)\\|vstolocal",
        256);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097D78,
        L"(.*\\.vsto)\\|vstolocal",
        256);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097DA0,
        L"file:///(.*\\.vsto)",
        256);
      std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(
        &unk_180097DC8,
        L"(.*\\.vsto)",
        256);
      atexit(TryTrimVstoManifestPath_::_2_::_dynamic_atexit_destructor_for__patterns__);
      Init_thread_footer(&dword_180097D48);
    }
  }
  while ( 1 )
  {
    v10 = 0;
    v11 = 0;
    memset(v12, 0, sizeof(v12));
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v16 = 0;
    v17[0] = 0;
    v17[1] = 0;
    v18 = 0;
    if ( (unsigned __int8)std::regex_match<std::char_traits<unsigned short>,std::allocator<unsigned short>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>,unsigned short,std::regex_traits<unsigned short>>(
                            v3,
                            &v10,
                            v5) )
      break;
    std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v12);
    v5 += 10;
    if ( v5 == &dword_180097DF0 )
    {
      if ( v3[3] > 7u )
        v3 = (_QWORD *)*v3;
      AslLogCallPrintf(3, "TryTrimVstoManifestPath", 84, "Found unrecognized pattern of the manifest path: %ws", v3);
      return 0;
    }
  }
  if ( (unsigned __int64)((*((_QWORD *)&v12[0] + 1) - *(_QWORD *)&v12[0]) / 24LL) > 1 )
  {
    v7 = (__int128 *)(*(_QWORD *)&v12[0] + 24LL);
    v8 = (char *)(*(_QWORD *)&v12[0] + 40LL);
  }
  else
  {
    v7 = (__int128 *)v17;
    v8 = &v18;
  }
  if ( *v8 )
    v9 = *v7;
  else
    v9 = 0;
  v20 = 0;
  v21 = 0;
  if ( (_QWORD)v9 == *((_QWORD *)&v9 + 1) )
  {
    *((_QWORD *)&v21 + 1) = 7;
    LOWORD(v20) = 0;
  }
  else
  {
    std::wstring::_Construct<1,unsigned short const *>(&v20, v9, (__int64)(*((_QWORD *)&v9 + 1) - v9) >> 1);
  }
  std::wstring::operator=(a2, &v20);
  std::wstring::~wstring(&v20);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  AslLogCallPrintf(3, "TryTrimVstoManifestPath", 79, "Manifest Path: %ws, Result Path: %ws", v3, a2);
  std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v12);
  return 1;
}

```

## disassembly

```asm
0x18004c1a4  mov     rax, rsp
0x18004c1a7  push    rbp
0x18004c1a8  push    rsi
0x18004c1a9  push    rdi
0x18004c1aa  lea     rbp, [rax-5Fh]
0x18004c1ae  sub     rsp, 0F0h
0x18004c1b5  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18004c1bd  mov     [rax+18h], rbx
0x18004c1c1  mov     rax, cs:__security_cookie
0x18004c1c8  xor     rax, rsp
0x18004c1cb  mov     [rbp+57h+var_18], rax
0x18004c1cf  mov     rdi, rdx
0x18004c1d2  mov     rbx, rcx
0x18004c1d5  cmp     qword ptr [rcx+18h], 7
0x18004c1da  jbe     short loc_18004C1E1
0x18004c1dc  mov     rax, [rcx]
0x18004c1df  jmp     short loc_18004C1E4
0x18004c1e1  mov     rax, rbx
0x18004c1e4  mov     [rsp+100h+var_E0], rax
0x18004c1e9  lea     r9, aManifestPathWs; "Manifest Path: %ws"
0x18004c1f0  mov     r8d, 3Dh ; '='
0x18004c1f6  lea     rdx, aTrytrimvstoman; "TryTrimVstoManifestPath"
0x18004c1fd  lea     ecx, [r8-3Ah]
0x18004c201  call    AslLogCallPrintf
0x18004c206  mov     ecx, cs:_tls_index
0x18004c20c  mov     rax, gs:58h
0x18004c215  mov     edx, 4
0x18004c21a  mov     rax, [rax+rcx*8]
0x18004c21e  lea     rsi, unk_180097D50
0x18004c225  mov     eax, [rdx+rax]
0x18004c228  cmp     cs:dword_180097D48, eax
0x18004c22e  jg      loc_18004C3DF
0x18004c234  mov     [rbp+57h+var_B0], 0
0x18004c23c  mov     [rbp+57h+var_A8], 0
0x18004c240  xorps   xmm0, xmm0
0x18004c243  movdqa  [rbp+57h+var_A0], xmm0
0x18004c248  xorps   xmm1, xmm1
0x18004c24b  movdqa  [rbp+57h+var_90], xmm1
0x18004c250  mov     [rbp+57h+var_80], 0
0x18004c258  mov     [rbp+57h+var_78], 0
0x18004c25c  movdqa  [rbp+57h+var_70], xmm0
0x18004c261  mov     [rbp+57h+var_60], 0
0x18004c265  mov     [rbp+57h+var_58], 0
0x18004c26d  mov     [rbp+57h+var_50], 0
0x18004c275  mov     [rbp+57h+var_48], 0
0x18004c279  mov     r8, rsi
0x18004c27c  lea     rdx, [rbp+57h+var_B0]
0x18004c280  mov     rcx, rbx
0x18004c283  call    ??$regex_match@U?$char_traits@G@std@@V?$allocator@G@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@GV?$regex_traits@G@2@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<ushort>,std::allocator<ushort>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>,ushort,std::regex_traits<ushort>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> &,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type)
0x18004c288  test    al, al
0x18004c28a  jnz     short loc_18004C2D8
0x18004c28c  lea     rcx, [rbp+57h+var_A0]
0x18004c290  call    ??1?$vector@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18004c295  add     rsi, 28h ; '('
0x18004c299  lea     rax, dword_180097DF0
0x18004c2a0  cmp     rsi, rax
0x18004c2a3  jnz     short loc_18004C234
0x18004c2a5  cmp     qword ptr [rbx+18h], 7
0x18004c2aa  jbe     short loc_18004C2AF
0x18004c2ac  mov     rbx, [rbx]
0x18004c2af  mov     [rsp+100h+var_E0], rbx
0x18004c2b4  lea     r9, aFoundUnrecogni; "Found unrecognized pattern of the manif"...
0x18004c2bb  mov     r8d, 54h ; 'T'
0x18004c2c1  lea     rdx, aTrytrimvstoman; "TryTrimVstoManifestPath"
0x18004c2c8  lea     ecx, [r8-51h]
0x18004c2cc  call    AslLogCallPrintf
0x18004c2d1  xor     al, al
0x18004c2d3  jmp     loc_18004C3C0
0x18004c2d8  mov     r8, qword ptr [rbp+57h+var_A0]
0x18004c2dc  mov     rcx, qword ptr [rbp+57h+var_A0+8]
0x18004c2e0  sub     rcx, r8
0x18004c2e3  mov     rax, 2AAAAAAAAAAAAAABh
0x18004c2ed  imul    rcx
0x18004c2f0  sar     rdx, 2
0x18004c2f4  mov     rax, rdx
0x18004c2f7  shr     rax, 3Fh
0x18004c2fb  add     rdx, rax
0x18004c2fe  cmp     rdx, 1
0x18004c302  ja      short loc_18004C30E
0x18004c304  lea     rax, [rbp+57h+var_58]
0x18004c308  lea     r8, [rbp+57h+var_48]
0x18004c30c  jmp     short loc_18004C316
0x18004c30e  lea     rax, [r8+18h]
0x18004c312  add     r8, 28h ; '('
0x18004c316  cmp     byte ptr [r8], 0
0x18004c31a  jz      short loc_18004C321
0x18004c31c  movups  xmm0, xmmword ptr [rax]
0x18004c31f  jmp     short loc_18004C324
0x18004c321  xorps   xmm0, xmm0
0x18004c324  movdqu  [rbp+57h+var_C8], xmm0
0x18004c329  xorps   xmm0, xmm0
0x18004c32c  movups  [rbp+57h+var_38], xmm0
0x18004c330  xorps   xmm1, xmm1
0x18004c333  movdqu  [rbp+57h+var_28], xmm1
0x18004c338  mov     rdx, qword ptr [rbp+57h+var_C8]
0x18004c33c  mov     r8, qword ptr [rbp+57h+var_C8+8]
0x18004c340  cmp     rdx, r8
0x18004c343  jnz     short loc_18004C355
0x18004c345  mov     qword ptr [rbp+57h+var_28+8], 7
0x18004c34d  xor     eax, eax
0x18004c34f  mov     word ptr [rbp+57h+var_38], ax
0x18004c353  jmp     short loc_18004C364
0x18004c355  sub     r8, rdx
0x18004c358  sar     r8, 1
0x18004c35b  lea     rcx, [rbp+57h+var_38]
0x18004c35f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004c364  lea     rdx, [rbp+57h+var_38]
0x18004c368  mov     rcx, rdi
0x18004c36b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004c370  lea     rcx, [rbp+57h+var_38]; void *
0x18004c374  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c379  cmp     qword ptr [rdi+18h], 7
0x18004c37e  jbe     short loc_18004C383
0x18004c380  mov     rdi, [rdi]
0x18004c383  cmp     qword ptr [rbx+18h], 7
0x18004c388  jbe     short loc_18004C38D
0x18004c38a  mov     rbx, [rbx]
0x18004c38d  mov     [rsp+28h], rdi
0x18004c392  mov     [rsp+100h+var_E0], rbx
0x18004c397  lea     r9, aManifestPathWs_0; "Manifest Path: %ws, Result Path: %ws"
0x18004c39e  mov     r8d, 4Fh ; 'O'
0x18004c3a4  lea     rdx, aTrytrimvstoman; "TryTrimVstoManifestPath"
0x18004c3ab  lea     ecx, [r8-4Ch]
0x18004c3af  call    AslLogCallPrintf
0x18004c3b4  nop
0x18004c3b5  lea     rcx, [rbp+57h+var_A0]
0x18004c3b9  call    ??1?$vector@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x18004c3be  mov     al, 1
0x18004c3c0  mov     rcx, [rbp+57h+var_18]
0x18004c3c4  xor     rcx, rsp; StackCookie
0x18004c3c7  call    __security_check_cookie
0x18004c3cc  mov     rbx, [rsp+100h+arg_10]
0x18004c3d4  add     rsp, 0F0h
0x18004c3db  pop     rdi
0x18004c3dc  pop     rsi
0x18004c3dd  pop     rbp
0x18004c3de  retn
0x18004c3df  lea     rcx, dword_180097D48
0x18004c3e6  call    _Init_thread_header
0x18004c3eb  cmp     cs:dword_180097D48, 0FFFFFFFFh
0x18004c3f2  jnz     loc_18004C234
0x18004c3f8  mov     r8d, 100h
0x18004c3fe  lea     rdx, aFileVstoVstolo; "file:///(.*\\.vsto)\\|vstolocal"
0x18004c405  mov     rcx, rsi
0x18004c408  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004c40d  nop
0x18004c40e  mov     r8d, 100h
0x18004c414  lea     rdx, aVstoVstolocal; "(.*\\.vsto)\\|vstolocal"
0x18004c41b  lea     rcx, unk_180097D78
0x18004c422  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004c427  nop
0x18004c428  mov     r8d, 100h
0x18004c42e  lea     rdx, aFileVsto; "file:///(.*\\.vsto)"
0x18004c435  lea     rcx, unk_180097DA0
0x18004c43c  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004c441  nop
0x18004c442  mov     r8d, 100h
0x18004c448  lea     rdx, aVsto; "(.*\\.vsto)"
0x18004c44f  lea     rcx, unk_180097DC8
0x18004c456  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x18004c45b  nop
0x18004c45c  lea     rcx, _TryTrimVstoManifestPath____2____dynamic_atexit_destructor_for__patterns__; void (__cdecl *)()
0x18004c463  call    atexit
0x18004c468  lea     rcx, dword_180097D48
0x18004c46f  call    _Init_thread_footer
0x18004c474  jmp     loc_18004C234
```
