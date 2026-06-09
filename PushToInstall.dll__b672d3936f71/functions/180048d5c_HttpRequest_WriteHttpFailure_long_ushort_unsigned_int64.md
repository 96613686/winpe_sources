# HttpRequest::WriteHttpFailure(long,ushort,unsigned __int64)

- ea: `0x180048d5c`
- end: `0x180048fd9`
- name: `?WriteHttpFailure@HttpRequest@@AEAAXJG_K@Z`
- size: `637`
- prototype: `void __fastcall(HttpRequest *__hidden this, int, unsigned __int16, unsigned __int64)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180048138`
- `0x18004e5d6`
- `0x18004e611`

## callees

- `0x1800026b0`
- `0x18000d739`
- `0x18002d674`
- `0x180030aac`
- `0x180030b30`
- `0x180031798`
- `0x1800348c4`
- `0x180036b80`
- `0x1800466f8`
- `0x180048d5c`
- `0x18004b464`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180048da0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180048da0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HttpRequest::WriteHttpFailure(HttpRequest *this, int a2, unsigned __int16 a3, unsigned __int64 a4)
{
  ULONGLONG TickCount64; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rdi
  __int128 *v11; // rsi
  const wchar_t *v12; // r14
  _QWORD *v13; // rdi
  __int64 v14; // r15
  _QWORD *v15; // rcx
  _QWORD *v16; // r9
  __int64 v17; // rdx
  unsigned __int64 v18; // r8
  int v19; // ebx
  __int64 v20; // r8
  __int128 *v21; // rcx
  int v22; // [rsp+28h] [rbp-E8h]
  int v23; // [rsp+38h] [rbp-D8h]
  int v24; // [rsp+50h] [rbp-C0h]
  int v25; // [rsp+58h] [rbp-B8h]
  int v26; // [rsp+60h] [rbp-B0h]
  __int64 v27; // [rsp+68h] [rbp-A8h]
  int v28; // [rsp+80h] [rbp-90h]
  unsigned __int64 v30; // [rsp+98h] [rbp-78h]
  _BYTE v31[16]; // [rsp+A0h] [rbp-70h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-60h]
  __int128 v33; // [rsp+B8h] [rbp-58h] BYREF
  __int128 v34; // [rsp+C8h] [rbp-48h]
  __int128 v35; // [rsp+D8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-28h]

  if ( *((_BYTE *)this + 161) )
  {
    TickCount64 = GetTickCount64();
    v30 = (TickCount64 - *((_QWORD *)this + 29)) & -(__int64)(*((_QWORD *)this + 29) < TickCount64);
    v35 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v35) = 0;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v33, L"MS-CV", 5u);
    v8 = *(_QWORD *)(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
                       (char *)this + 248,
                       v31,
                       &v33)
                   + 16);
    if ( *(_BYTE *)(v8 + 25)
      || (v9 = 1, (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)&v33, (const wchar_t *)(v8 + 32))) )
    {
      v9 = 0;
    }
    std::wstring::_Tidy_deallocate((char **)&v33);
    if ( v9 )
    {
      v33 = 0;
      v34 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v33, L"MS-CV", 5u);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        (char *)this + 248,
        v31,
        &v33);
      v10 = v32;
      if ( *(_BYTE *)(v32 + 25)
        || (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)&v33, (const wchar_t *)(v32 + 32)) )
      {
        std::_Xout_of_range("invalid map<K, T> key");
        JUMPOUT(0x180048FD8LL);
      }
      std::wstring::operator=(&v35, v10 + 64);
      std::wstring::_Tidy_deallocate((char **)&v33);
    }
    v11 = &v35;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v35;
    v12 = L"HTTPS";
    if ( !*((_BYTE *)this + 160) )
      v12 = L"HTTP";
    v13 = (_QWORD *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v13 = (_QWORD *)*v13;
    if ( *((_QWORD *)this + 3) <= 7u )
      LODWORD(v14) = (_DWORD)this;
    else
      v14 = *(_QWORD *)this;
    v15 = (_QWORD *)((char *)this + 32);
    v16 = (_QWORD *)((char *)this + 128);
    v17 = *((_QWORD *)this + 18);
    v18 = *((_QWORD *)this + 6);
    if ( 0x7FFFFFFFFFFFFFFELL - v17 < v18 )
      std::_Xlen_string();
    v19 = *((_DWORD *)this + 60);
    if ( v16[3] > 7u )
      v16 = (_QWORD *)*v16;
    if ( v15[3] > 7u )
      v15 = (_QWORD *)*v15;
    v22 = (int)v15;
    std::wstring::wstring(&v33, v17, v18, v16, v17);
    v21 = &v33;
    if ( *((_QWORD *)&v34 + 1) > 7u )
      v21 = (__int128 *)v33;
    EventWriteHttpRequestFailure(
      (__int64)v21,
      v14,
      v20,
      v30,
      a2,
      v22,
      (__int64)v13,
      v23,
      (__int64)v12,
      a3,
      v24,
      v25,
      v26,
      v27,
      a4,
      (__int64)v11,
      v28,
      v19);
    std::wstring::_Tidy_deallocate((char **)&v33);
    std::wstring::_Tidy_deallocate((char **)&v35);
  }
}

```

## disassembly

```asm
0x180048d5c  push    rbp
0x180048d5e  push    rbx
0x180048d5f  push    rsi
0x180048d60  push    rdi
0x180048d61  push    r12
0x180048d63  push    r13
0x180048d65  push    r14
0x180048d67  push    r15
0x180048d69  lea     rbp, [rsp+8]
0x180048d6e  sub     rsp, 108h
0x180048d75  mov     rax, cs:__security_cookie
0x180048d7c  xor     rax, rsp
0x180048d7f  mov     [rbp+30h+var_48], rax
0x180048d83  mov     r12, r9
0x180048d86  movzx   r13d, r8w
0x180048d8a  mov     [rbp+30h+var_B0], edx
0x180048d8d  mov     rbx, rcx
0x180048d90  xor     r15d, r15d
0x180048d93  cmp     [rcx+0A1h], r15b
0x180048d9a  jz      loc_180048FA6
0x180048da0  call    cs:__imp_GetTickCount64
0x180048da6  mov     rdx, [rbx+0E8h]
0x180048dad  mov     rcx, rax
0x180048db0  sub     rcx, rdx
0x180048db3  cmp     rdx, rax
0x180048db6  sbb     rax, rax
0x180048db9  and     rax, rcx
0x180048dbc  mov     [rbp+30h+var_A8], rax
0x180048dc0  xorps   xmm0, xmm0
0x180048dc3  movups  [rbp+30h+var_68], xmm0
0x180048dc7  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180048dcf  movdqu  [rbp+30h+var_58], xmm1
0x180048dd4  mov     word ptr [rbp+30h+var_68], r15w
0x180048dd9  lea     rsi, [rbx+0F8h]
0x180048de0  movups  [rbp+30h+var_88], xmm0
0x180048de4  xorps   xmm1, xmm1
0x180048de7  movdqu  [rbp+30h+var_78], xmm1
0x180048dec  lea     r14d, [r15+5]
0x180048df0  mov     r8d, r14d
0x180048df3  lea     rdx, aMsCv; "MS-CV"
0x180048dfa  lea     rcx, [rbp+30h+var_88]
0x180048dfe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048e03  lea     r8, [rbp+30h+var_88]
0x180048e07  lea     rdx, [rbp+30h+var_A0]
0x180048e0b  mov     rcx, rsi
0x180048e0e  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180048e13  mov     rdx, [rax+10h]
0x180048e17  cmp     [rdx+19h], r15b
0x180048e1b  jnz     short loc_180048E32
0x180048e1d  add     rdx, 20h ; ' '
0x180048e21  lea     rcx, [rbp+30h+var_88]
0x180048e25  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180048e2a  test    al, al
0x180048e2c  lea     edi, [r15+1]
0x180048e30  jz      short loc_180048E35
0x180048e32  mov     rdi, r15
0x180048e35  lea     rcx, [rbp+30h+var_88]
0x180048e39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048e3e  test    rdi, rdi
0x180048e41  jz      short loc_180048EB0
0x180048e43  xorps   xmm0, xmm0
0x180048e46  movups  [rbp+30h+var_88], xmm0
0x180048e4a  xorps   xmm1, xmm1
0x180048e4d  movdqu  [rbp+30h+var_78], xmm1
0x180048e52  mov     r8, r14
0x180048e55  lea     rdx, aMsCv; "MS-CV"
0x180048e5c  lea     rcx, [rbp+30h+var_88]
0x180048e60  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048e65  nop
0x180048e66  lea     r8, [rbp+30h+var_88]
0x180048e6a  lea     rdx, [rbp+30h+var_A0]
0x180048e6e  mov     rcx, rsi
0x180048e71  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180048e76  mov     rdi, [rbp+30h+var_90]
0x180048e7a  cmp     [rdi+19h], r15b
0x180048e7e  jnz     loc_180048FCC
0x180048e84  lea     rdx, [rdi+20h]
0x180048e88  lea     rcx, [rbp+30h+var_88]
0x180048e8c  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180048e91  test    al, al
0x180048e93  jnz     loc_180048FCC
0x180048e99  lea     rdx, [rdi+40h]
0x180048e9d  lea     rcx, [rbp+30h+var_68]
0x180048ea1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180048ea6  nop
0x180048ea7  lea     rcx, [rbp+30h+var_88]
0x180048eab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048eb0  lea     rsi, [rbp+30h+var_68]
0x180048eb4  cmp     qword ptr [rbp+30h+var_58+8], 7
0x180048eb9  cmova   rsi, qword ptr [rbp+30h+var_68]
0x180048ebe  lea     rax, aHttp; "HTTP"
0x180048ec5  lea     r14, aHttps_0; "HTTPS"
0x180048ecc  cmp     [rbx+0A0h], r15b
0x180048ed3  cmovz   r14, rax
0x180048ed7  lea     rdi, [rbx+40h]
0x180048edb  cmp     qword ptr [rdi+18h], 7
0x180048ee0  jbe     short loc_180048EE5
0x180048ee2  mov     rdi, [rdi]
0x180048ee5  cmp     qword ptr [rbx+18h], 7
0x180048eea  jbe     short loc_180048EF1
0x180048eec  mov     r15, [rbx]
0x180048eef  jmp     short loc_180048EF4
0x180048ef1  mov     r15, rbx
0x180048ef4  lea     rcx, [rbx+20h]
0x180048ef8  lea     r9, [rbx+80h]
0x180048eff  mov     rdx, [r9+10h]
0x180048f03  mov     r8, [rcx+10h]
0x180048f07  mov     rax, 7FFFFFFFFFFFFFFEh
0x180048f11  sub     rax, rdx
0x180048f14  cmp     rax, r8
0x180048f17  jb      loc_180048FC6
0x180048f1d  mov     ebx, [rbx+0F0h]
0x180048f23  cmp     qword ptr [r9+18h], 7
0x180048f28  jbe     short loc_180048F2D
0x180048f2a  mov     r9, [r9]
0x180048f2d  cmp     qword ptr [rcx+18h], 7
0x180048f32  jbe     short loc_180048F37
0x180048f34  mov     rcx, [rcx]
0x180048f37  mov     [rsp+140h+var_110], r8
0x180048f3c  mov     [rsp+140h+var_118], rcx
0x180048f41  mov     [rsp+140h+var_120], rdx
0x180048f46  lea     rcx, [rbp+30h+var_88]
0x180048f4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180048f4f  nop
0x180048f50  lea     rcx, [rbp+30h+var_88]
0x180048f54  cmp     qword ptr [rbp+30h+var_78+8], 7
0x180048f59  cmova   rcx, qword ptr [rbp+30h+var_88]
0x180048f5e  mov     [rsp+140h+var_B8], ebx
0x180048f65  mov     [rsp+140h+var_C8], rsi
0x180048f6a  mov     [rsp+140h+var_D0], r12
0x180048f6f  mov     [rsp+140h+var_F8], r13w
0x180048f75  mov     [rsp+140h+var_100], r14
0x180048f7a  mov     [rsp+140h+var_110], rdi
0x180048f7f  mov     eax, [rbp+30h+var_B0]
0x180048f82  mov     dword ptr [rsp+140h+var_120], eax
0x180048f86  mov     r9, [rbp+30h+var_A8]
0x180048f8a  mov     rdx, r15
0x180048f8d  call    EventWriteHttpRequestFailure
0x180048f92  nop
0x180048f93  lea     rcx, [rbp+30h+var_88]
0x180048f97  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048f9c  nop
0x180048f9d  lea     rcx, [rbp+30h+var_68]
0x180048fa1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180048fa6  mov     rcx, [rbp+30h+var_48]
0x180048faa  xor     rcx, rsp; StackCookie
0x180048fad  call    __security_check_cookie
0x180048fb2  add     rsp, 108h
0x180048fb9  pop     r15
0x180048fbb  pop     r14
0x180048fbd  pop     r13
0x180048fbf  pop     r12
0x180048fc1  pop     rdi
0x180048fc2  pop     rsi
0x180048fc3  pop     rbx
0x180048fc4  pop     rbp
0x180048fc5  retn
0x180048fc6  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180048fcc  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x180048fd3  call    ?_Xout_of_range@std@@YAXPEBD@Z_0; std::_Xout_of_range(char const *)
```
