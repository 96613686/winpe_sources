# Json::OurReader::decodeDouble(Json::OurReader::Token &,Json::Value &)

- ea: `0x18007ea64`
- end: `0x18007ec26`
- name: `?decodeDouble@OurReader@Json@@AEAA_NAEAVToken@12@AEAVValue@2@@Z`
- size: `450`
- prototype: `bool __fastcall(Json::OurReader *__hidden this, struct Json::OurReader::Token *, struct Json::Value *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18007ecf8`

## callees

- `0x18000d090`
- `0x18000daa0`
- `0x18000dc98`
- `0x180011d90`
- `0x1800126c4`
- `0x180012720`
- `0x18001420c`
- `0x180021fb8`
- `0x18003d2cc`
- `0x18007c300`
- `0x18007e800`
- `0x18007ea64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18007eb18`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18007eb46`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18007eb18`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18007eb46`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007eae4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007eb59`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007eae4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18007eb59`

## string_xrefs

- `0x18007eaa5`: `Unable to parse token length`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Json::OurReader::decodeDouble(
        Json::OurReader *this,
        struct Json::OurReader::Token *a2,
        struct Json::Value *a3)
{
  int v5; // r15d
  __int64 v6; // rsi
  char v7; // bl
  double *v8; // rcx
  const void *v10; // rdx
  size_t v11; // rsi
  double v12; // xmm6_8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  _BYTE v17[32]; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v18[40]; // [rsp+60h] [rbp-61h] BYREF
  double v19; // [rsp+88h] [rbp-39h] BYREF
  int v20; // [rsp+90h] [rbp-31h]
  __int128 v21; // [rsp+98h] [rbp-29h]
  __int64 v22; // [rsp+A8h] [rbp-19h]

  v5 = (int)this;
  v6 = (__int64)(*((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1)) >> 1;
  if ( v6 < 0 )
  {
    std::wstring::wstring(v17, L"Unable to parse token length");
    v7 = Json::OurReader::addError(v5, 9, (unsigned int)v17, (_DWORD)a2, 0);
    v8 = (double *)v17;
LABEL_3:
    std::wstring::_Tidy_deallocate(v8);
    return v7;
  }
  *(_DWORD *)_o__errno() = 0;
  v10 = (const void *)*((_QWORD *)a2 + 1);
  if ( v6 > 32 )
  {
    std::wstring::wstring(v17, v10, *((_QWORD *)a2 + 2));
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    v12 = _o_wcstod(v13, 0);
    std::wstring::_Tidy_deallocate(v17);
  }
  else
  {
    v11 = 2 * v6;
    memcpy_0(&v19, v10, v11);
    if ( v11 >= 0x42 )
      _report_rangecheckfailure();
    *(_WORD *)((char *)&v19 + v11) = 0;
    v12 = _o_wcstod(&v19, 0);
  }
  if ( *(_DWORD *)_o__errno() )
  {
    v14 = std::wstring::wstring(&v19, *((_QWORD *)a2 + 1), *((_QWORD *)a2 + 2));
    v15 = std::operator+<unsigned short>(v18, L"'", v14);
    v16 = std::operator+<unsigned short>(v17, v15, L"' is not a number.");
    v7 = Json::OurReader::addError(v5, 9, v16, (_DWORD)a2, 0);
    std::wstring::_Tidy_deallocate(v17);
    std::wstring::_Tidy_deallocate(v18);
    v8 = &v19;
    goto LABEL_3;
  }
  LOBYTE(v20) = 3;
  v20 &= ~0x100u;
  v21 = 0;
  v22 = 0;
  v19 = v12;
  Json::Value::operator=(a3, &v19);
  return 1;
}

```

## disassembly

```asm
0x18007ea64  mov     rax, rsp
0x18007ea67  mov     [rax+20h], rbx
0x18007ea6b  push    rbp
0x18007ea6c  push    rsi
0x18007ea6d  push    rdi
0x18007ea6e  push    r14
0x18007ea70  push    r15
0x18007ea72  lea     rbp, [rax-5Fh]
0x18007ea76  sub     rsp, 0F0h
0x18007ea7d  movaps  xmmword ptr [rax-38h], xmm6
0x18007ea81  mov     rax, cs:__security_cookie
0x18007ea88  xor     rax, rsp
0x18007ea8b  mov     [rbp+57h+var_40], rax
0x18007ea8f  mov     r14, r8
0x18007ea92  mov     rdi, rdx
0x18007ea95  mov     r15, rcx
0x18007ea98  mov     rsi, [rdx+10h]
0x18007ea9c  sub     rsi, [rdx+8]
0x18007eaa0  sar     rsi, 1
0x18007eaa3  jns     short loc_18007EAE4
0x18007eaa5  lea     rdx, aUnableToParseT; "Unable to parse token length"
0x18007eaac  lea     rcx, [rsp+110h+var_D8]
0x18007eab1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007eab6  nop
0x18007eab7  xor     ebx, ebx
0x18007eab9  mov     [rsp+110h+var_F0], rbx
0x18007eabe  mov     r9, rdi
0x18007eac1  lea     r8, [rsp+110h+var_D8]
0x18007eac6  lea     edx, [rbx+9]
0x18007eac9  mov     rcx, r15
0x18007eacc  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x18007ead1  mov     bl, al
0x18007ead3  lea     rcx, [rsp+110h+var_D8]
0x18007ead8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007eadd  mov     al, bl
0x18007eadf  jmp     loc_18007EBFE
0x18007eae4  call    cs:__imp__o__errno
0x18007eaea  xor     ebx, ebx
0x18007eaec  mov     [rax], ebx
0x18007eaee  mov     rdx, [rdi+8]; Src
0x18007eaf2  cmp     rsi, 20h ; ' '
0x18007eaf6  jg      short loc_18007EB29
0x18007eaf8  add     rsi, rsi
0x18007eafb  mov     r8, rsi; Size
0x18007eafe  lea     rcx, [rbp+57h+var_90]; void *
0x18007eb02  call    memcpy_0
0x18007eb07  cmp     rsi, 42h ; 'B'
0x18007eb0b  jnb     short loc_18007EB23
0x18007eb0d  mov     word ptr [rbp+rsi+57h+var_90], bx
0x18007eb12  xor     edx, edx
0x18007eb14  lea     rcx, [rbp+57h+var_90]
0x18007eb18  call    cs:__imp__o_wcstod
0x18007eb1e  movaps  xmm6, xmm0
0x18007eb21  jmp     short loc_18007EB59
0x18007eb23  call    __report_rangecheckfailure
0x18007eb29  mov     r8, [rdi+10h]
0x18007eb2d  lea     rcx, [rsp+110h+var_D8]
0x18007eb32  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18007eb37  lea     rcx, [rsp+110h+var_D8]
0x18007eb3c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007eb41  mov     rcx, rax
0x18007eb44  xor     edx, edx
0x18007eb46  call    cs:__imp__o_wcstod
0x18007eb4c  movaps  xmm6, xmm0
0x18007eb4f  lea     rcx, [rsp+110h+var_D8]
0x18007eb54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007eb59  call    cs:__imp__o__errno
0x18007eb5f  cmp     [rax], ebx
0x18007eb61  jz      short loc_18007EBD6
0x18007eb63  mov     r8, [rdi+10h]
0x18007eb67  mov     rdx, [rdi+8]
0x18007eb6b  lea     rcx, [rbp+57h+var_90]
0x18007eb6f  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18007eb74  nop
0x18007eb75  mov     r8, rax
0x18007eb78  lea     rdx, asc_1800C5F58; "'"
0x18007eb7f  lea     rcx, [rbp+57h+var_B8]
0x18007eb83  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBG$$QEAV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring &&)
0x18007eb88  nop
0x18007eb89  lea     r8, aIsNotANumber; "' is not a number."
0x18007eb90  mov     rdx, rax
0x18007eb93  lea     rcx, [rsp+110h+var_D8]
0x18007eb98  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18007eb9d  nop
0x18007eb9e  mov     [rsp+110h+var_F0], rbx
0x18007eba3  mov     r9, rdi
0x18007eba6  mov     r8, rax
0x18007eba9  mov     edx, 9
0x18007ebae  mov     rcx, r15
0x18007ebb1  call    ?addError@OurReader@Json@@AEAA_NW4JsonErrorType@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVToken@12@PEBG@Z; Json::OurReader::addError(Json::JsonErrorType,std::wstring const &,Json::OurReader::Token &,ushort const *)
0x18007ebb6  mov     bl, al
0x18007ebb8  lea     rcx, [rsp+110h+var_D8]
0x18007ebbd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ebc2  nop
0x18007ebc3  lea     rcx, [rbp+57h+var_B8]
0x18007ebc7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ebcc  nop
0x18007ebcd  lea     rcx, [rbp+57h+var_90]
0x18007ebd1  jmp     loc_18007EAD8
0x18007ebd6  mov     byte ptr [rbp+57h+var_88], 3
0x18007ebda  btr     [rbp+57h+var_88], 8
0x18007ebdf  xorps   xmm0, xmm0
0x18007ebe2  movdqu  [rbp+57h+var_80], xmm0
0x18007ebe7  mov     [rbp+57h+var_70], rbx
0x18007ebeb  movsd   [rbp+57h+var_90], xmm6
0x18007ebf0  lea     rdx, [rbp+57h+var_90]
0x18007ebf4  mov     rcx, r14
0x18007ebf7  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x18007ebfc  mov     al, 1
0x18007ebfe  mov     rcx, [rbp+57h+var_40]
0x18007ec02  xor     rcx, rsp; StackCookie
0x18007ec05  call    __security_check_cookie
0x18007ec0a  lea     r11, [rsp+110h+var_20]
0x18007ec12  mov     rbx, [r11+48h]
0x18007ec16  movaps  xmm6, xmmword ptr [r11-10h]
0x18007ec1b  mov     rsp, r11
0x18007ec1e  pop     r15
0x18007ec20  pop     r14
0x18007ec22  pop     rdi
0x18007ec23  pop     rsi
0x18007ec24  pop     rbp
0x18007ec25  retn
```
