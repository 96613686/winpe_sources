# Pal::NetworkResponse::NetworkResponse(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<std::vector<uchar,std::allocator<uchar>> const> const &,std::unique_ptr<Pal::NetworkResponseHeaders,std::default_delete<Pal::NetworkResponseHeaders>>,Pal::NetworkException const *,bool,bool)

- ea: `0x18002dd88`
- end: `0x18002dfa2`
- name: `??0NetworkResponse@Pal@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@3@V?$unique_ptr@VNetworkResponseHeaders@Pal@@U?$default_delete@VNetworkResponseHeaders@Pal@@@std@@@3@PEBVNetworkException@1@_N4@Z`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, _QWORD *, __int64, char)`
- caller_count: `4`
- callee_count: `14`
- tags: ``

## callers

- `0x180031294`
- `0x180031444`
- `0x180031ce0`
- `0x1800327a0`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c850`
- `0x18000cb24`
- `0x18000fe68`
- `0x18001154c`
- `0x180011ddc`
- `0x18002dd88`
- `0x18002e02c`
- `0x18002e0f4`
- `0x18002e1fc`
- `0x180043010`

## string_xrefs

- `0x18002de35`: `Cache-Control`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pal::NetworkResponse::NetworkResponse(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        __int64 a5,
        char a6)
{
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _BYTE *, _BYTE *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _BYTE *, _BYTE *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _BYTE *, _BYTE *); // rbx
  __int64 CharacterSetFromContentTypeHttpHeader; // rax
  _BYTE v19[16]; // [rsp+20h] [rbp-61h] BYREF
  __int64 v20; // [rsp+30h] [rbp-51h]
  _QWORD *v21; // [rsp+40h] [rbp-41h]
  _BYTE v22[16]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v23; // [rsp+58h] [rbp-29h]
  _BYTE v24[32]; // [rsp+68h] [rbp-19h] BYREF

  v20 = a1;
  v21 = a4;
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>((_QWORD *)a1, a3);
  std::wstring::wstring(v8 + 16);
  std::wstring::wstring(a1 + 48, v9);
  std::wstring::wstring(a1 + 80);
  v10 = *a4;
  *a4 = 0;
  *(_QWORD *)(a1 + 112) = v10;
  *(_QWORD *)(a1 + 120) = a5;
  *(_BYTE *)(a1 + 128) = a6;
  *(_BYTE *)(a1 + 129) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  if ( v10 )
  {
    std::wstring::wstring((__int64)v22);
    v11 = *(_QWORD *)(a1 + 112);
    v12 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v11 + 8LL);
    std::wstring::wstring((__int64)v24, (__int64)L"Cache-Control");
    LOBYTE(v12) = v12(v11, v24, v22);
    std::wstring::_Tidy_deallocate(v24);
    if ( (_BYTE)v12 )
      *(_QWORD *)(a1 + 136) = *(_QWORD *)Pal::NetworkResponse::getDateFromCacheControlHttpHeader(v19, v22);
    if ( !*(_QWORD *)(a1 + 136) )
    {
      v23 = 0;
      *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22) = 0;
      v13 = *(_QWORD *)(a1 + 112);
      v14 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v13 + 8LL);
      std::wstring::wstring((__int64)v24, (__int64)L"Expires");
      LOBYTE(v14) = v14(v13, v24, v22);
      std::wstring::_Tidy_deallocate(v24);
      if ( (_BYTE)v14 )
        *(_QWORD *)(a1 + 136) = *(_QWORD *)Pal::NetworkResponse::getDateFromExpiresHttpHeader(v19, v22);
    }
    v23 = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22) = 0;
    v15 = *(_QWORD *)(a1 + 112);
    v16 = *(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v15 + 8LL);
    std::wstring::wstring((__int64)v24, (__int64)L"Content-Type");
    LOBYTE(v16) = v16(v15, v24, v22);
    std::wstring::_Tidy_deallocate(v24);
    if ( (_BYTE)v16 )
    {
      CharacterSetFromContentTypeHttpHeader = Pal::NetworkResponse::getCharacterSetFromContentTypeHttpHeader(v24, v22);
      std::wstring::operator=(a1 + 16, CharacterSetFromContentTypeHttpHeader);
      std::wstring::_Tidy_deallocate(v24);
    }
    std::wstring::_Tidy_deallocate(v22);
  }
  std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(a4);
  return a1;
}

```

## disassembly

```asm
0x18002dd88  push    rbp
0x18002dd8a  push    rbx
0x18002dd8b  push    rsi
0x18002dd8c  push    rdi
0x18002dd8d  push    r14
0x18002dd8f  push    r15
0x18002dd91  lea     rbp, [rsp-17h]
0x18002dd96  sub     rsp, 98h
0x18002dd9d  mov     rax, cs:__security_cookie
0x18002dda4  xor     rax, rsp
0x18002dda7  mov     [rbp+3Fh+var_38], rax
0x18002ddab  mov     r14, r9
0x18002ddae  mov     r9, rdx
0x18002ddb1  mov     rsi, rcx
0x18002ddb4  mov     [rbp+3Fh+var_90], rcx
0x18002ddb8  mov     [rbp+3Fh+var_80], r14
0x18002ddbc  mov     rdx, r8
0x18002ddbf  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18002ddc4  nop
0x18002ddc5  add     rcx, 10h
0x18002ddc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002ddce  nop
0x18002ddcf  lea     rcx, [rsi+30h]
0x18002ddd3  mov     rdx, r9
0x18002ddd6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dddb  nop
0x18002dddc  lea     rcx, [rsi+50h]
0x18002dde0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002dde5  nop
0x18002dde6  mov     rcx, [r14]
0x18002dde9  mov     qword ptr [r14], 0
0x18002ddf0  mov     [rsi+70h], rcx
0x18002ddf4  mov     rax, [rbp+3Fh+arg_20]
0x18002ddf8  mov     [rsi+78h], rax
0x18002ddfc  mov     al, [rbp+3Fh+arg_28]
0x18002ddff  mov     [rsi+80h], al
0x18002de05  mov     byte ptr [rsi+81h], 0
0x18002de0c  mov     qword ptr [rsi+88h], 0
0x18002de17  test    rcx, rcx
0x18002de1a  jz      loc_18002DF7B
0x18002de20  lea     rcx, [rbp+3Fh+var_78]
0x18002de24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002de29  nop
0x18002de2a  mov     rdi, [rsi+70h]
0x18002de2e  mov     rax, [rdi]
0x18002de31  mov     rbx, [rax+8]
0x18002de35  lea     rdx, aCacheControl; "Cache-Control"
0x18002de3c  lea     rcx, [rbp+3Fh+var_58]
0x18002de40  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002de45  nop
0x18002de46  lea     r8, [rbp+3Fh+var_78]
0x18002de4a  lea     rdx, [rbp+3Fh+var_58]
0x18002de4e  mov     rcx, rdi
0x18002de51  mov     rax, rbx
0x18002de54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de59  mov     bl, al
0x18002de5b  lea     rcx, [rbp+3Fh+var_58]
0x18002de5f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002de64  test    bl, bl
0x18002de66  jz      short loc_18002DE7F
0x18002de68  lea     rdx, [rbp+3Fh+var_78]
0x18002de6c  lea     rcx, [rbp+3Fh+var_A0]
0x18002de70  call    ?getDateFromCacheControlHttpHeader@NetworkResponse@Pal@@SA?AVTimeSpanSinceEpoch@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::NetworkResponse::getDateFromCacheControlHttpHeader(std::wstring const &)
0x18002de75  mov     rcx, [rax]
0x18002de78  mov     [rsi+88h], rcx
0x18002de7f  cmp     qword ptr [rsi+88h], 0
0x18002de87  jnz     short loc_18002DEF7
0x18002de89  mov     [rbp+3Fh+var_68], 0
0x18002de91  lea     rcx, [rbp+3Fh+var_78]
0x18002de95  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002de9a  mov     rdx, rax
0x18002de9d  xor     eax, eax
0x18002de9f  mov     [rdx], ax
0x18002dea2  mov     rdi, [rsi+70h]
0x18002dea6  mov     rax, [rdi]
0x18002dea9  mov     rbx, [rax+8]
0x18002dead  lea     rdx, aExpires; "Expires"
0x18002deb4  lea     rcx, [rbp+3Fh+var_58]
0x18002deb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002debd  nop
0x18002debe  lea     r8, [rbp+3Fh+var_78]
0x18002dec2  lea     rdx, [rbp+3Fh+var_58]
0x18002dec6  mov     rcx, rdi
0x18002dec9  mov     rax, rbx
0x18002decc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ded1  mov     bl, al
0x18002ded3  lea     rcx, [rbp+3Fh+var_58]
0x18002ded7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dedc  test    bl, bl
0x18002dede  jz      short loc_18002DEF7
0x18002dee0  lea     rdx, [rbp+3Fh+var_78]
0x18002dee4  lea     rcx, [rbp+3Fh+var_A0]
0x18002dee8  call    ?getDateFromExpiresHttpHeader@NetworkResponse@Pal@@SA?AVTimeSpanSinceEpoch@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::NetworkResponse::getDateFromExpiresHttpHeader(std::wstring const &)
0x18002deed  mov     rcx, [rax]
0x18002def0  mov     [rsi+88h], rcx
0x18002def7  mov     [rbp+3Fh+var_68], 0
0x18002deff  lea     rcx, [rbp+3Fh+var_78]
0x18002df03  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002df08  mov     rdx, rax
0x18002df0b  xor     eax, eax
0x18002df0d  mov     [rdx], ax
0x18002df10  mov     rdi, [rsi+70h]
0x18002df14  mov     rax, [rdi]
0x18002df17  mov     rbx, [rax+8]
0x18002df1b  lea     rdx, aContentType; "Content-Type"
0x18002df22  lea     rcx, [rbp+3Fh+var_58]
0x18002df26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002df2b  nop
0x18002df2c  lea     r8, [rbp+3Fh+var_78]
0x18002df30  lea     rdx, [rbp+3Fh+var_58]
0x18002df34  mov     rcx, rdi
0x18002df37  mov     rax, rbx
0x18002df3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df3f  mov     bl, al
0x18002df41  lea     rcx, [rbp+3Fh+var_58]
0x18002df45  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df4a  test    bl, bl
0x18002df4c  jz      short loc_18002DF71
0x18002df4e  lea     rdx, [rbp+3Fh+var_78]
0x18002df52  lea     rcx, [rbp+3Fh+var_58]
0x18002df56  call    ?getCharacterSetFromContentTypeHttpHeader@NetworkResponse@Pal@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; Pal::NetworkResponse::getCharacterSetFromContentTypeHttpHeader(std::wstring const &)
0x18002df5b  mov     rdx, rax
0x18002df5e  lea     rcx, [rsi+10h]
0x18002df62  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002df67  lea     rcx, [rbp+3Fh+var_58]
0x18002df6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df70  nop
0x18002df71  lea     rcx, [rbp+3Fh+var_78]
0x18002df75  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002df7a  nop
0x18002df7b  mov     rcx, r14
0x18002df7e  call    ??1?$unique_ptr@VNetworkRequestImpl@Pal@@U?$default_delete@VNetworkRequestImpl@Pal@@@std@@@std@@QEAA@XZ; std::unique_ptr<Pal::NetworkRequestImpl>::~unique_ptr<Pal::NetworkRequestImpl>(void)
0x18002df83  mov     rax, rsi
0x18002df86  mov     rcx, [rbp+3Fh+var_38]
0x18002df8a  xor     rcx, rsp; StackCookie
0x18002df8d  call    __security_check_cookie
0x18002df92  add     rsp, 98h
0x18002df99  pop     r15
0x18002df9b  pop     r14
0x18002df9d  pop     rdi
0x18002df9e  pop     rsi
0x18002df9f  pop     rbx
0x18002dfa0  pop     rbp
0x18002dfa1  retn
```
