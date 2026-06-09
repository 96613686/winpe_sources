# MapControl::ConfigurationManager::getLanguageFromMapping(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Json::Value const &)

- ea: `0x1800210ac`
- end: `0x1800211aa`
- name: `?getLanguageFromMapping@ConfigurationManager@MapControl@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVValue@Json@@@Z`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002149c`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000ba50`
- `0x18000c354`
- `0x180011ddc`
- `0x18001d6e4`
- `0x1800210ac`
- `0x1800348d8`
- `0x180035110`
- `0x180035934`
- `0x18003b4a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800211a3`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1800211a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MapControl::ConfigurationManager::getLanguageFromMapping(__int64 a1, __int64 a2, __int64 a3)
{
  _BYTE *v6; // r8
  __int64 v7; // r8
  __int64 v8; // r9
  char *i; // rdi
  _QWORD *v10; // rax
  __int64 v11; // rax
  char *v13; // [rsp+28h] [rbp-60h] BYREF
  char *v14; // [rsp+30h] [rbp-58h]
  __int64 v15; // [rsp+38h] [rbp-50h]
  __int64 v16; // [rsp+40h] [rbp-48h]
  _BYTE v17[32]; // [rsp+48h] [rbp-40h] BYREF

  v16 = a1;
  if ( *(_BYTE *)(a3 + 8) != 7 )
  {
    _o_terminate(a1, a2);
    JUMPOUT(0x1800211A9LL);
  }
  std::wstring::wstring(a1);
  Json::Value::getMemberNames(v6, &v13);
  for ( i = v13; i != v14; i += 32 )
  {
    if ( (unsigned __int8)Utility::StringUtils::equalCaseInsensitive<unsigned short>(i, a2) )
    {
      v10 = (_QWORD *)Json::Value::operator[](a3, i);
      v11 = Json::Value::asString(v10, (__int64)v17);
      std::wstring::operator=(a1, v11);
      std::wstring::_Tidy_deallocate(v17);
      break;
    }
  }
  if ( v13 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v13, v14, v7, v8);
    std::_Deallocate<16>(v13, (v15 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return a1;
}

```

## disassembly

```asm
0x1800210ac  mov     [rsp+arg_18], rbp
0x1800210b1  push    rsi
0x1800210b2  push    rdi
0x1800210b3  push    r14
0x1800210b5  sub     rsp, 70h
0x1800210b9  mov     rax, cs:__security_cookie
0x1800210c0  xor     rax, rsp
0x1800210c3  mov     [rsp+88h+var_20], rax
0x1800210c8  mov     rbp, r8
0x1800210cb  mov     r14, rdx
0x1800210ce  mov     rsi, rcx
0x1800210d1  mov     [rsp+88h+var_48], rcx
0x1800210d6  mov     [rsp+88h+var_68], 0
0x1800210de  cmp     byte ptr [r8+8], 7
0x1800210e3  jnz     loc_1800211A3
0x1800210e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800210ee  mov     [rsp+88h+var_68], 1
0x1800210f6  lea     rdx, [rsp+88h+var_60]
0x1800210fb  mov     rcx, r8
0x1800210fe  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x180021103  nop
0x180021104  mov     rdi, [rsp+88h+var_60]
0x180021109  cmp     rdi, [rsp+88h+var_58]
0x18002110e  jz      short loc_180021153
0x180021110  mov     rdx, r14
0x180021113  mov     rcx, rdi
0x180021116  call    ??$equalCaseInsensitive@G@StringUtils@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::StringUtils::equalCaseInsensitive<ushort>(std::wstring const &,std::wstring const &)
0x18002111b  test    al, al
0x18002111d  jnz     short loc_180021125
0x18002111f  add     rdi, 20h ; ' '
0x180021123  jmp     short loc_180021109
0x180021125  mov     rdx, rdi
0x180021128  mov     rcx, rbp
0x18002112b  call    ??AValue@Json@@QEBAAEBV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x180021130  lea     rdx, [rsp+88h+var_40]
0x180021135  mov     rcx, rax
0x180021138  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x18002113d  mov     rdx, rax
0x180021140  mov     rcx, rsi
0x180021143  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180021148  lea     rcx, [rsp+88h+var_40]
0x18002114d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021152  nop
0x180021153  cmp     [rsp+88h+var_60], 0
0x180021159  jz      short loc_180021182
0x18002115b  mov     rdx, [rsp+88h+var_58]
0x180021160  mov     rcx, [rsp+88h+var_60]
0x180021165  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002116a  mov     rdx, [rsp+88h+var_50]
0x18002116f  sub     rdx, [rsp+88h+var_60]
0x180021174  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180021178  mov     rcx, [rsp+88h+var_60]
0x18002117d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021182  mov     rax, rsi
0x180021185  mov     rcx, [rsp+88h+var_20]
0x18002118a  xor     rcx, rsp; StackCookie
0x18002118d  call    __security_check_cookie
0x180021192  mov     rbp, [rsp+88h+arg_18]
0x18002119a  add     rsp, 70h
0x18002119e  pop     r14
0x1800211a0  pop     rdi
0x1800211a1  pop     rsi
0x1800211a2  retn
0x1800211a3  call    cs:__imp__o_terminate
```
