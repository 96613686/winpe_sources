# Json::OurReader::decodeUnicodeCodePoint(Json::OurReader::Token &,ushort const * &,ushort const *,uint &)

- ea: `0x1800377b0`
- end: `0x180037912`
- name: `?decodeUnicodeCodePoint@OurReader@Json@@AEAA_NAEAVToken@12@AEAPEBGPEBGAEAI@Z`
- size: `354`
- prototype: `bool __fastcall(Json::OurReader *__hidden this, struct Json::OurReader::Token *, const unsigned __int16 **, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800375b0`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c850`
- `0x180036ea0`
- `0x1800377b0`
- `0x180037918`

## string_xrefs

- `0x1800378c1`: `expecting another \u token to begin the second half of a unicode surrogate pair`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Json::OurReader::decodeUnicodeCodePoint(
        Json::OurReader *this,
        struct Json::OurReader::Token *a2,
        const unsigned __int16 **a3,
        char *a4,
        unsigned int *a5)
{
  const unsigned __int16 *v9; // rbx
  char v10; // bl
  unsigned __int16 v12; // ax
  __int16 *v13; // rdi
  __int16 v14; // ax
  unsigned int v15; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v16[32]; // [rsp+38h] [rbp-60h] BYREF

  if ( Json::OurReader::decodeUnicodeEscapeSequence(this, a2, a3, (const unsigned __int16 *)a4, a5) )
  {
    if ( *a5 - 55296 > 0x3FF )
      return 1;
    v9 = *a3;
    if ( (__int64)((a4 - (char *)*a3) & 0xFFFFFFFFFFFFFFFEuLL) < 12 )
    {
      std::wstring::wstring(
        (__int64)v16,
        (__int64)L"additional six characters expected to parse unicode surrogate pair.");
      v10 = Json::OurReader::addError((_DWORD)this, 8, (unsigned int)v16, (_DWORD)a2, (__int64)v9);
LABEL_5:
      std::wstring::_Tidy_deallocate(v16);
      return v10;
    }
    v15 = 0;
    v12 = *v9;
    v13 = (__int16 *)(v9 + 1);
    *a3 = v9 + 1;
    if ( v12 != 92 || (v14 = *v13, v13 = (__int16 *)(v9 + 2), *a3 = v9 + 2, v14 != 117) )
    {
      std::wstring::wstring(
        (__int64)v16,
        (__int64)L"expecting another \\u token to begin the second half of a unicode surrogate pair");
      v10 = Json::OurReader::addError((_DWORD)this, 8, (unsigned int)v16, (_DWORD)a2, (__int64)v13);
      goto LABEL_5;
    }
    if ( Json::OurReader::decodeUnicodeEscapeSequence(this, a2, a3, (const unsigned __int16 *)a4, &v15) )
    {
      *a5 = (v15 & 0x3FF) + (((*a5 & 0x3FF) + 64) << 10);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800377b0  push    rbx
0x1800377b2  push    rbp
0x1800377b3  push    rsi
0x1800377b4  push    rdi
0x1800377b5  push    r12
0x1800377b7  push    r14
0x1800377b9  push    r15
0x1800377bb  sub     rsp, 60h
0x1800377bf  mov     rax, cs:__security_cookie
0x1800377c6  xor     rax, rsp
0x1800377c9  mov     [rsp+98h+var_40], rax
0x1800377ce  mov     r12, r9
0x1800377d1  mov     rsi, r8
0x1800377d4  mov     r15, rdx
0x1800377d7  mov     rbp, rcx
0x1800377da  mov     r14, [rsp+98h+arg_20]
0x1800377e2  mov     [rsp+98h+var_78], r14; unsigned int *
0x1800377e7  call    ?decodeUnicodeEscapeSequence@OurReader@Json@@AEAA_NAEAVToken@12@AEAPEBGPEBGAEAI@Z; Json::OurReader::decodeUnicodeEscapeSequence(Json::OurReader::Token &,ushort const * &,ushort const *,uint &)
0x1800377ec  test    al, al
0x1800377ee  jz      loc_1800378F4
0x1800377f4  mov     eax, [r14]
0x1800377f7  sub     eax, 0D800h
0x1800377fc  cmp     eax, 3FFh
0x180037801  ja      loc_1800378BD
0x180037807  mov     rbx, [rsi]
0x18003780a  mov     rax, r12
0x18003780d  sub     rax, rbx
0x180037810  and     rax, 0FFFFFFFFFFFFFFFEh
0x180037814  cmp     rax, 0Ch
0x180037818  jge     short loc_180037859
0x18003781a  lea     rdx, aAdditionalSixC; "additional six characters expected to p"...
0x180037821  lea     rcx, [rsp+98h+var_60]
0x180037826  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003782b  nop
0x18003782c  mov     [rsp+98h+var_78], rbx
0x180037831  mov     r9, r15
0x180037834  lea     r8, [rsp+98h+var_60]
0x180037839  mov     edx, 8
0x18003783e  mov     rcx, rbp
0x180037841  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x180037846  mov     bl, al
0x180037848  lea     rcx, [rsp+98h+var_60]
0x18003784d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037852  mov     al, bl
0x180037854  jmp     loc_1800378F6
0x180037859  mov     [rsp+98h+var_68], 0
0x180037861  movzx   eax, word ptr [rbx]
0x180037864  lea     rdi, [rbx+2]
0x180037868  mov     [rsi], rdi
0x18003786b  cmp     ax, 5Ch ; '\'
0x18003786f  jnz     short loc_1800378C1
0x180037871  movzx   eax, word ptr [rdi]
0x180037874  lea     rdi, [rbx+4]
0x180037878  mov     [rsi], rdi
0x18003787b  cmp     ax, 75h ; 'u'
0x18003787f  jnz     short loc_1800378C1
0x180037881  lea     rax, [rsp+98h+var_68]
0x180037886  mov     [rsp+98h+var_78], rax; unsigned int *
0x18003788b  mov     r9, r12; unsigned __int16 *
0x18003788e  mov     r8, rsi; unsigned __int16 **
0x180037891  mov     rdx, r15; struct Json::OurReader::Token *
0x180037894  mov     rcx, rbp; this
0x180037897  call    ?decodeUnicodeEscapeSequence@OurReader@Json@@AEAA_NAEAVToken@12@AEAPEBGPEBGAEAI@Z; Json::OurReader::decodeUnicodeEscapeSequence(Json::OurReader::Token &,ushort const * &,ushort const *,uint &)
0x18003789c  test    al, al
0x18003789e  jz      short loc_1800378F4
0x1800378a0  mov     ecx, [r14]
0x1800378a3  and     ecx, 3FFh
0x1800378a9  add     ecx, 40h ; '@'
0x1800378ac  shl     ecx, 0Ah
0x1800378af  mov     eax, [rsp+98h+var_68]
0x1800378b3  and     eax, 3FFh
0x1800378b8  add     ecx, eax
0x1800378ba  mov     [r14], ecx
0x1800378bd  mov     al, 1
0x1800378bf  jmp     short loc_1800378F6
0x1800378c1  lea     rdx, aExpectingAnoth; "expecting another \\u token to begin th"...
0x1800378c8  lea     rcx, [rsp+98h+var_60]
0x1800378cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800378d2  nop
0x1800378d3  mov     [rsp+98h+var_78], rdi
0x1800378d8  mov     r9, r15
0x1800378db  lea     r8, [rsp+98h+var_60]
0x1800378e0  mov     edx, 8
0x1800378e5  mov     rcx, rbp
0x1800378e8  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x1800378ed  mov     bl, al
0x1800378ef  jmp     loc_180037848
0x1800378f4  xor     al, al
0x1800378f6  mov     rcx, [rsp+98h+var_40]
0x1800378fb  xor     rcx, rsp; StackCookie
0x1800378fe  call    __security_check_cookie
0x180037903  add     rsp, 60h
0x180037907  pop     r15
0x180037909  pop     r14
0x18003790b  pop     r12
0x18003790d  pop     rdi
0x18003790e  pop     rsi
0x18003790f  pop     rbp
0x180037910  pop     rbx
0x180037911  retn
```
