# HttpRequest::WriteHttpSuccess(ushort)

- ea: `0x180048fe0`
- end: `0x1800491e9`
- name: `?WriteHttpSuccess@HttpRequest@@AEAAXG@Z`
- size: `521`
- prototype: `void __fastcall(HttpRequest *__hidden this, unsigned __int16)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180048138`

## callees

- `0x1800026b0`
- `0x18000d739`
- `0x18002d674`
- `0x180030aac`
- `0x180031798`
- `0x1800348c4`
- `0x180036b80`
- `0x180048fe0`
- `0x180049b40`
- `0x180049d1c`
- `0x18004a1bc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180049135`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180049135`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall HttpRequest::WriteHttpSuccess(HttpRequest *this, unsigned __int16 a2)
{
  HttpRequest *v3; // rbx
  char *v4; // rsi
  __int64 v5; // rdx
  _BOOL8 v6; // rdi
  __int64 v7; // rdi
  int v8; // r15d
  __int128 *v9; // rsi
  _QWORD *v10; // rdi
  ULONGLONG TickCount64; // rax
  ULONGLONG v12; // rdx
  __int64 v13; // r14
  _BYTE v14[16]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v15; // [rsp+50h] [rbp-19h]
  __int128 v16; // [rsp+58h] [rbp-11h] BYREF
  __int128 v17; // [rsp+68h] [rbp-1h]
  __int128 v18; // [rsp+78h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+88h] [rbp+1Fh]

  v3 = this;
  if ( *((_BYTE *)this + 161) )
  {
    v18 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18) = 0;
    v4 = (char *)this + 248;
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v16, L"MS-CV", 5u);
    v5 = *(_QWORD *)(std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
                       v4,
                       v14,
                       &v16)
                   + 16);
    v6 = !*(_BYTE *)(v5 + 25)
      && !(unsigned __int8)std::operator<<unsigned short>((const wchar_t *)&v16, (const wchar_t *)(v5 + 32));
    std::wstring::_Tidy_deallocate((char **)&v16);
    if ( v6 )
    {
      v16 = 0;
      v17 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v16, L"MS-CV", 5u);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
        v4,
        v14,
        &v16);
      v7 = v15;
      if ( *(_BYTE *)(v15 + 25)
        || (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)&v16, (const wchar_t *)(v15 + 32)) )
      {
        std::_Xout_of_range("invalid map<K, T> key");
        JUMPOUT(0x1800491E8LL);
      }
      std::wstring::operator=(&v18, v7 + 64);
      std::wstring::_Tidy_deallocate((char **)&v16);
    }
    v8 = *((_DWORD *)v3 + 60);
    v9 = &v18;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (__int128 *)v18;
    v10 = (_QWORD *)((char *)v3 + 64);
    if ( *((_QWORD *)v3 + 11) > 7u )
      v10 = (_QWORD *)*v10;
    TickCount64 = GetTickCount64();
    v12 = *((_QWORD *)v3 + 29);
    v13 = (TickCount64 - v12) & -(__int64)(v12 < TickCount64);
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(HttpRequest **)v3;
    CacheOrUploadHttpRequest((_DWORD)v3, a2, v12 < TickCount64 ? TickCount64 - v12 : 0, (_DWORD)v9, 0);
    CacheOrUploadHttpRequestSuccess((_DWORD)v3, a2, v13, (_DWORD)v10, (__int64)v9, v8, 0);
    CacheOrUploadOnBoxRequestFailure(0, 0, 0, 0, 0);
    std::wstring::_Tidy_deallocate((char **)&v18);
  }
}

```

## disassembly

```asm
0x180048fe0  mov     [rsp-8+arg_10], rbx
0x180048fe5  mov     [rsp-8+arg_18], rsi
0x180048fea  push    rbp
0x180048feb  push    rdi
0x180048fec  push    r12
0x180048fee  push    r14
0x180048ff0  push    r15
0x180048ff2  lea     rbp, [rsp-37h]
0x180048ff7  sub     rsp, 0A0h
0x180048ffe  mov     rax, cs:__security_cookie
0x180049005  xor     rax, rsp
0x180049008  mov     [rbp+57h+var_28], rax
0x18004900c  movzx   r12d, dx
0x180049010  mov     rbx, rcx
0x180049013  cmp     byte ptr [rcx+0A1h], 0
0x18004901a  jz      loc_1800491B4
0x180049020  xorps   xmm0, xmm0
0x180049023  movups  [rbp+57h+var_48], xmm0
0x180049027  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004902f  movdqu  [rbp+57h+var_38], xmm1
0x180049034  xor     eax, eax
0x180049036  mov     word ptr [rbp+57h+var_48], ax
0x18004903a  lea     rsi, [rcx+0F8h]
0x180049041  movups  [rbp+57h+var_68], xmm0
0x180049045  xorps   xmm1, xmm1
0x180049048  movdqu  [rbp+57h+var_58], xmm1
0x18004904d  lea     r14d, [rax+5]
0x180049051  mov     r8d, r14d
0x180049054  lea     rdx, aMsCv; "MS-CV"
0x18004905b  lea     rcx, [rbp+57h+var_68]
0x18004905f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180049064  lea     r8, [rbp+57h+var_68]
0x180049068  lea     rdx, [rbp+57h+var_80]
0x18004906c  mov     rcx, rsi
0x18004906f  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x180049074  mov     rdx, [rax+10h]
0x180049078  cmp     byte ptr [rdx+19h], 0
0x18004907c  jnz     short loc_180049095
0x18004907e  add     rdx, 20h ; ' '
0x180049082  lea     rcx, [rbp+57h+var_68]
0x180049086  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18004908b  test    al, al
0x18004908d  jnz     short loc_180049095
0x18004908f  lea     edi, [r14-4]
0x180049093  jmp     short loc_180049097
0x180049095  xor     edi, edi
0x180049097  lea     rcx, [rbp+57h+var_68]
0x18004909b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800490a0  test    rdi, rdi
0x1800490a3  jz      short loc_180049112
0x1800490a5  xorps   xmm0, xmm0
0x1800490a8  movups  [rbp+57h+var_68], xmm0
0x1800490ac  xorps   xmm1, xmm1
0x1800490af  movdqu  [rbp+57h+var_58], xmm1
0x1800490b4  mov     r8, r14
0x1800490b7  lea     rdx, aMsCv; "MS-CV"
0x1800490be  lea     rcx, [rbp+57h+var_68]
0x1800490c2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800490c7  nop
0x1800490c8  lea     r8, [rbp+57h+var_68]
0x1800490cc  lea     rdx, [rbp+57h+var_80]
0x1800490d0  mov     rcx, rsi
0x1800490d3  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800490d8  mov     rdi, [rbp+57h+var_70]
0x1800490dc  cmp     byte ptr [rdi+19h], 0
0x1800490e0  jnz     loc_1800491DC
0x1800490e6  lea     rdx, [rdi+20h]
0x1800490ea  lea     rcx, [rbp+57h+var_68]
0x1800490ee  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x1800490f3  test    al, al
0x1800490f5  jnz     loc_1800491DC
0x1800490fb  lea     rdx, [rdi+40h]
0x1800490ff  lea     rcx, [rbp+57h+var_48]
0x180049103  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180049108  nop
0x180049109  lea     rcx, [rbp+57h+var_68]
0x18004910d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049112  mov     r15d, [rbx+0F0h]
0x180049119  lea     rsi, [rbp+57h+var_48]
0x18004911d  cmp     qword ptr [rbp+57h+var_38+8], 7
0x180049122  cmova   rsi, qword ptr [rbp+57h+var_48]
0x180049127  lea     rdi, [rbx+40h]
0x18004912b  cmp     qword ptr [rdi+18h], 7
0x180049130  jbe     short loc_180049135
0x180049132  mov     rdi, [rdi]
0x180049135  call    cs:__imp_GetTickCount64
0x18004913b  mov     rdx, [rbx+0E8h]
0x180049142  mov     rcx, rax
0x180049145  sub     rcx, rdx
0x180049148  cmp     rdx, rax
0x18004914b  sbb     r14, r14
0x18004914e  and     r14, rcx
0x180049151  cmp     qword ptr [rbx+18h], 7
0x180049156  jbe     short loc_18004915B
0x180049158  mov     rbx, [rbx]
0x18004915b  mov     dword ptr [rsp+0C0h+var_A0], 0
0x180049163  mov     r9, rsi
0x180049166  mov     r8, r14
0x180049169  movzx   edx, r12w
0x18004916d  mov     rcx, rbx
0x180049170  call    _CacheOrUploadHttpRequest
0x180049175  mov     [rsp+0C0h+var_90], 0
0x18004917a  mov     [rsp+0C0h+var_98], r15d
0x18004917f  mov     [rsp+0C0h+var_A0], rsi
0x180049184  mov     r9, rdi
0x180049187  mov     r8, r14
0x18004918a  movzx   edx, r12w
0x18004918e  mov     rcx, rbx
0x180049191  call    _CacheOrUploadHttpRequestSuccess
0x180049196  mov     byte ptr [rsp+0C0h+var_A0], 0
0x18004919b  xor     r9d, r9d
0x18004919e  xor     r8d, r8d
0x1800491a1  xor     edx, edx
0x1800491a3  xor     ecx, ecx
0x1800491a5  call    _CacheOrUploadOnBoxRequestFailure
0x1800491aa  nop
0x1800491ab  lea     rcx, [rbp+57h+var_48]
0x1800491af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800491b4  mov     rcx, [rbp+57h+var_28]
0x1800491b8  xor     rcx, rsp; StackCookie
0x1800491bb  call    __security_check_cookie
0x1800491c0  lea     r11, [rsp+0C0h+var_20]
0x1800491c8  mov     rbx, [r11+40h]
0x1800491cc  mov     rsi, [r11+48h]
0x1800491d0  mov     rsp, r11
0x1800491d3  pop     r15
0x1800491d5  pop     r14
0x1800491d7  pop     r12
0x1800491d9  pop     rdi
0x1800491da  pop     rbp
0x1800491db  retn
0x1800491dc  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800491e3  call    ?_Xout_of_range@std@@YAXPEBD@Z_0; std::_Xout_of_range(char const *)
```
