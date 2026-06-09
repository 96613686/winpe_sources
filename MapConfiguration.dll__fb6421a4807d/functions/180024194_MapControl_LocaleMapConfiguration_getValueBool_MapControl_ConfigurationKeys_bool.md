# MapControl::LocaleMapConfiguration::getValueBool(MapControl::ConfigurationKeys,bool *)

- ea: `0x180024194`
- end: `0x1800242a1`
- name: `?getValueBool@LocaleMapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEA_N@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800232c0`
- `0x180023350`

## callees

- `0x1800094a0`
- `0x18000c354`
- `0x18000c850`
- `0x1800236bc`
- `0x180024194`
- `0x18003b4a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800241cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800241cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024277`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall MapControl::LocaleMapConfiguration::getValueBool(__int64 a1, int a2, _BYTE *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  __int64 v6; // rbx
  char v7; // di
  char v8; // si
  __int64 v9; // r15
  char v10; // bl
  char v11; // bl
  _QWORD v13[2]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+98h] [rbp+10h] BYREF

  v15 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)(a1 + 296);
  v13[1] = a1 + 296;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 296));
  std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::find(
    a1 + 336,
    v13,
    &v15);
  v6 = v13[0];
  if ( v13[0] == *(_QWORD *)(a1 + 336) )
  {
    v7 = 0;
  }
  else
  {
    v8 = 1;
    std::wstring::wstring((__int64)v14, (__int64)L"false");
    v9 = v6 + 40;
    v10 = Utility::StringUtils::equalCaseInsensitive<unsigned short>(v6 + 40, v14);
    std::wstring::_Tidy_deallocate(v14);
    if ( v10 )
    {
      *a3 = 0;
    }
    else
    {
      std::wstring::wstring((__int64)v14, (__int64)L"true");
      v11 = Utility::StringUtils::equalCaseInsensitive<unsigned short>(v9, v14);
      std::wstring::_Tidy_deallocate(v14);
      if ( v11 )
        *a3 = 1;
      else
        v8 = 0;
    }
    v7 = v8;
  }
  LeaveCriticalSection(v5);
  return v7;
}

```

## disassembly

```asm
0x180024194  mov     [rsp+arg_18], rbx
0x180024199  mov     [rsp+arg_8], edx
0x18002419d  push    rbp
0x18002419e  push    rsi
0x18002419f  push    rdi
0x1800241a0  push    r14
0x1800241a2  push    r15
0x1800241a4  sub     rsp, 60h
0x1800241a8  mov     rax, cs:__security_cookie
0x1800241af  xor     rax, rsp
0x1800241b2  mov     [rsp+88h+var_38], rax
0x1800241b7  mov     r14, r8
0x1800241ba  mov     rdi, rcx
0x1800241bd  lea     rbp, [rcx+128h]
0x1800241c4  mov     [rsp+88h+var_60], rbp
0x1800241c9  mov     rcx, rbp; lpCriticalSection
0x1800241cc  call    cs:__imp_EnterCriticalSection
0x1800241d2  nop
0x1800241d3  lea     r8, [rsp+88h+arg_8]
0x1800241db  lea     rdx, [rsp+88h+var_68]
0x1800241e0  lea     rcx, [rdi+150h]
0x1800241e7  call    ?find@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@AEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::find(MapControl::ConfigurationKeys const &)
0x1800241ec  mov     rbx, [rsp+88h+var_68]
0x1800241f1  cmp     rbx, [rdi+150h]
0x1800241f8  jnz     short loc_1800241FE
0x1800241fa  xor     edi, edi
0x1800241fc  jmp     short loc_180024274
0x1800241fe  mov     sil, 1
0x180024201  lea     rdx, aFalse; "false"
0x180024208  lea     rcx, [rsp+88h+var_58]
0x18002420d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180024212  lea     r15, [rbx+28h]
0x180024216  lea     rdx, [rsp+88h+var_58]
0x18002421b  mov     rcx, r15
0x18002421e  call    ??$equalCaseInsensitive@G@StringUtils@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::StringUtils::equalCaseInsensitive<ushort>(std::wstring const &,std::wstring const &)
0x180024223  mov     bl, al
0x180024225  lea     rcx, [rsp+88h+var_58]
0x18002422a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002422f  xor     dil, dil
0x180024232  test    bl, bl
0x180024234  jz      short loc_18002423B
0x180024236  mov     [r14], dil
0x180024239  jmp     short loc_180024271
0x18002423b  lea     rdx, aTrue; "true"
0x180024242  lea     rcx, [rsp+88h+var_58]
0x180024247  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002424c  lea     rdx, [rsp+88h+var_58]
0x180024251  mov     rcx, r15
0x180024254  call    ??$equalCaseInsensitive@G@StringUtils@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::StringUtils::equalCaseInsensitive<ushort>(std::wstring const &,std::wstring const &)
0x180024259  mov     bl, al
0x18002425b  lea     rcx, [rsp+88h+var_58]
0x180024260  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024265  test    bl, bl
0x180024267  jz      short loc_18002426E
0x180024269  mov     [r14], sil
0x18002426c  jmp     short loc_180024271
0x18002426e  mov     sil, dil
0x180024271  mov     dil, sil
0x180024274  mov     rcx, rbp; lpCriticalSection
0x180024277  call    cs:__imp_LeaveCriticalSection
0x18002427d  mov     al, dil
0x180024280  mov     rcx, [rsp+88h+var_38]
0x180024285  xor     rcx, rsp; StackCookie
0x180024288  call    __security_check_cookie
0x18002428d  mov     rbx, [rsp+88h+arg_18]
0x180024295  add     rsp, 60h
0x180024299  pop     r15
0x18002429b  pop     r14
0x18002429d  pop     rdi
0x18002429e  pop     rsi
0x18002429f  pop     rbp
0x1800242a0  retn
```
