# JDictsDictionaryManifest::DecodeChunkDescriptor(__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 const &,_ChunkDescriptorType &)

- ea: `0x1800167a4`
- end: `0x18001696d`
- name: `?DecodeChunkDescriptor@JDictsDictionaryManifest@@AEAAJAEBU__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001@@AEAU_ChunkDescriptorType@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(JDictsDictionaryManifest *this, const struct __MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 *, struct _ChunkDescriptorType *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180016980`

## callees

- `0x18000c6dc`
- `0x18001656c`
- `0x1800167a4`
- `0x180016d68`
- `0x180021816`
- `0x180021850`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001694c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001694c`
- `msvcrt!wcsncpy_s` at `0x180016836`
- `msvcrt!wcsncpy_s` at `0x180016939`
- `msvcrt!wcsncpy_s` at `0x180016836`
- `msvcrt!wcsncpy_s` at `0x180016939`

## string_xrefs

- `0x1800167d9`: `[temp]\`

## pseudocode

```c
__int64 __fastcall JDictsDictionaryManifest::DecodeChunkDescriptor(
        JDictsDictionaryManifest *this,
        const struct __MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 *a2,
        struct _ChunkDescriptorType *a3)
{
  _DWORD *v6; // r12
  _WORD *v7; // rsi
  unsigned __int64 v8; // rbx
  const wchar_t *v10; // r8
  errno_t v11; // eax
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  __int128 *p_Buf2; // rcx
  const wchar_t *v15; // r8
  errno_t v16; // ebx
  __int128 Buf2; // [rsp+28h] [rbp-28h] BYREF
  __int64 v18; // [rsp+38h] [rbp-18h]
  unsigned __int64 v19; // [rsp+40h] [rbp-10h]

  Buf2 = *(_OWORD *)L"[temp]\\";
  v6 = (_DWORD *)*((_QWORD *)a2 + 2);
  v7 = v6 + 1;
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  if ( *((_DWORD *)a2 + 6) != 2 * v8 + 6 )
    return 2147942411LL;
  if ( *v7 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)&Buf2 + v12) );
    if ( v12 > v8 || memcmp_0(v6 + 1, &Buf2, 2 * v12) )
    {
      v19 = 7;
      v18 = 0;
      LOWORD(Buf2) = 0;
      v13 = v8 + *((_QWORD *)this + 10);
      if ( v13 != 7 )
      {
        LOBYTE(v12) = 1;
        if ( (unsigned __int8)std::wstring::_Grow(&Buf2, v13, v12) )
        {
          p_Buf2 = &Buf2;
          if ( v19 >= 8 )
            p_Buf2 = (__int128 *)Buf2;
          v18 = 0;
          *(_WORD *)p_Buf2 = 0;
        }
      }
      std::wstring::append(&Buf2, (char *)this + 64, 0, -1, 1);
      std::wstring::operator+=(&Buf2, v6 + 1);
      v15 = (const wchar_t *)&Buf2;
      if ( v19 >= 8 )
        v15 = (const wchar_t *)Buf2;
      v16 = wcsncpy_s((wchar_t *)a3, 0x104u, v15, 0xFFFFFFFFFFFFFFFFuLL);
      if ( v19 >= 8 )
        operator delete((void *)Buf2);
      if ( !v16 || v16 == 80 )
        goto LABEL_10;
    }
  }
  else
  {
    v10 = (const wchar_t *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) >= 8u )
      v10 = *(const wchar_t **)v10;
    v11 = wcsncpy_s((wchar_t *)a3, 0x104u, v10, 0xFFFFFFFFFFFFFFFFuLL);
    if ( !v11 || v11 == 80 )
    {
LABEL_10:
      *((_DWORD *)a3 + 130) = *v6;
      *(_OWORD *)((char *)a3 + 524) = *(_OWORD *)a2;
      return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800167a4  mov     [rsp-38h+arg_18], rbx
0x1800167a9  push    rbp
0x1800167aa  push    rsi
0x1800167ab  push    rdi
0x1800167ac  push    r12
0x1800167ae  push    r13
0x1800167b0  push    r14
0x1800167b2  push    r15
0x1800167b4  mov     rbp, rsp
0x1800167b7  sub     rsp, 50h
0x1800167bb  mov     rax, cs:__security_cookie
0x1800167c2  xor     rax, rsp
0x1800167c5  mov     [rbp+var_8], rax
0x1800167c9  mov     rdi, r8
0x1800167cc  mov     r15, rdx
0x1800167cf  mov     r14, rcx
0x1800167d2  xor     r13d, r13d
0x1800167d5  mov     [rbp+var_30], r13d
0x1800167d9  movups  xmm0, xmmword ptr cs:aTemp; "[temp]\\"
0x1800167e0  movdqu  [rbp+Buf2], xmm0
0x1800167e5  mov     r12, [rdx+10h]
0x1800167e9  lea     rsi, [r12+4]
0x1800167ee  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800167f2  mov     rbx, rdx
0x1800167f5  inc     rbx
0x1800167f8  cmp     [rsi+rbx*2], r13w
0x1800167fd  jnz     short loc_1800167F5
0x1800167ff  lea     rcx, ds:6[rbx*2]
0x180016807  mov     eax, [r15+18h]
0x18001680b  cmp     rax, rcx
0x18001680e  jz      short loc_180016817
0x180016810  mov     eax, 8007000Bh
0x180016815  jmp     short loc_180016861
0x180016817  cmp     r13w, [rsi]
0x18001681b  jnz     short loc_180016885
0x18001681d  lea     r8, [r14+20h]
0x180016821  cmp     qword ptr [r8+18h], 8
0x180016826  jb      short loc_18001682B
0x180016828  mov     r8, [r8]; Source
0x18001682b  mov     r9, rdx; MaxCount
0x18001682e  mov     edx, 104h; SizeInWords
0x180016833  mov     rcx, rdi; Destination
0x180016836  call    cs:__imp_wcsncpy_s
0x18001683c  test    eax, eax
0x18001683e  jz      short loc_180016849
0x180016840  cmp     eax, 50h ; 'P'
0x180016843  jnz     loc_180016963
0x180016849  mov     eax, [r12]
0x18001684d  mov     [rdi+208h], eax
0x180016853  movups  xmm0, xmmword ptr [r15]
0x180016857  movdqu  xmmword ptr [rdi+20Ch], xmm0
0x18001685f  xor     eax, eax
0x180016861  mov     rcx, [rbp+var_8]
0x180016865  xor     rcx, rsp; StackCookie
0x180016868  call    __security_check_cookie
0x18001686d  mov     rbx, [rsp+50h+arg_18]
0x180016875  add     rsp, 50h
0x180016879  pop     r15
0x18001687b  pop     r14
0x18001687d  pop     r13
0x18001687f  pop     r12
0x180016881  pop     rdi
0x180016882  pop     rsi
0x180016883  pop     rbp
0x180016884  retn
0x180016885  lea     rax, [rbp+Buf2]
0x180016889  mov     r8, rdx
0x18001688c  inc     r8
0x18001688f  cmp     [rax+r8*2], r13w
0x180016894  jnz     short loc_18001688C
0x180016896  cmp     r8, rbx
0x180016899  ja      short loc_1800168B2
0x18001689b  add     r8, r8; Size
0x18001689e  lea     rdx, [rbp+Buf2]; Buf2
0x1800168a2  mov     rcx, rsi; Buf1
0x1800168a5  call    memcmp_0
0x1800168aa  test    eax, eax
0x1800168ac  jz      loc_180016963
0x1800168b2  mov     [rbp+var_10], 7
0x1800168ba  mov     [rbp+var_18], r13
0x1800168be  mov     word ptr [rbp+Buf2], r13w
0x1800168c3  mov     [rbp+var_30], 1
0x1800168ca  mov     rdx, [r14+50h]
0x1800168ce  add     rdx, rbx
0x1800168d1  cmp     rdx, 7
0x1800168d5  jz      short loc_1800168FD
0x1800168d7  mov     r8b, 1
0x1800168da  lea     rcx, [rbp+Buf2]
0x1800168de  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800168e3  test    al, al
0x1800168e5  jz      short loc_1800168FD
0x1800168e7  lea     rcx, [rbp+Buf2]
0x1800168eb  cmp     [rbp+var_10], 8
0x1800168f0  cmovnb  rcx, qword ptr [rbp+Buf2]
0x1800168f5  mov     [rbp+var_18], r13
0x1800168f9  mov     [rcx], r13w
0x1800168fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016901  mov     r9, rbx
0x180016904  xor     r8d, r8d
0x180016907  lea     rdx, [r14+40h]
0x18001690b  lea     rcx, [rbp+Buf2]
0x18001690f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180016914  mov     rdx, rsi; void *
0x180016917  lea     rcx, [rbp+Buf2]; Src
0x18001691b  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180016920  lea     r8, [rbp+Buf2]
0x180016924  cmp     [rbp+var_10], 8
0x180016929  cmovnb  r8, qword ptr [rbp+Buf2]; Source
0x18001692e  mov     r9, rbx; MaxCount
0x180016931  mov     edx, 104h; SizeInWords
0x180016936  mov     rcx, rdi; Destination
0x180016939  call    cs:__imp_wcsncpy_s
0x18001693f  mov     ebx, eax
0x180016941  cmp     [rbp+var_10], 8
0x180016946  jb      short loc_180016952
0x180016948  mov     rcx, qword ptr [rbp+Buf2]
0x18001694c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016952  test    ebx, ebx
0x180016954  jz      loc_180016849
0x18001695a  cmp     ebx, 50h ; 'P'
0x18001695d  jz      loc_180016849
0x180016963  mov     eax, 80004005h
0x180016968  jmp     loc_180016861
```
