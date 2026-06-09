# PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>)

- ea: `0x180041024`
- end: `0x1800411f2`
- name: `?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b7f4`
- `0x18003bfd4`
- `0x18003cadc`
- `0x18003cc3c`
- `0x18003e1f8`
- `0x18003e53c`
- `0x18003ed70`
- `0x18003faa4`

## callees

- `0x180002d40`
- `0x18000f8a8`
- `0x18001031c`
- `0x180023a20`
- `0x1800273f0`
- `0x180027440`
- `0x18003470c`
- `0x18003b418`
- `0x18003e614`
- `0x18003ea4c`
- `0x180041024`
- `0x1800421e0`
- `0x1800425d8`

## string_xrefs

- `0x180041098`: `xmlns`
- `0x1800411d7`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rax
  std::_Ref_count_base *v14; // rcx
  int v16; // eax
  _QWORD *v17; // [rsp+30h] [rbp-59h] BYREF
  std::_Ref_count_base *v18; // [rsp+38h] [rbp-51h]
  _QWORD *v19; // [rsp+48h] [rbp-41h]
  __int64 v20; // [rsp+50h] [rbp-39h] BYREF
  std::_Ref_count_base *v21; // [rsp+58h] [rbp-31h]
  _OWORD v22[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v23; // [rsp+90h] [rbp+7h] BYREF
  __m128i si128; // [rsp+A0h] [rbp+17h]

  v17 = a2;
  v19 = a3;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23) = 0;
  v22[0] = 0;
  v22[1] = si128;
  LOWORD(v22[0]) = 0;
  v6 = std::wstring::find(*a3, 58, 0);
  v7 = v6;
  if ( v6 == -1 )
  {
    std::wstring::_Assign<unsigned short>(&v23, L"xmlns");
    std::wstring::operator=(v22, *a3);
  }
  else
  {
    v8 = std::wstring::substr(*a3, &v20, 0, v6);
    std::wstring::operator=(&v23, v8);
    std::wstring::_Tidy_deallocate(&v20);
    v9 = std::wstring::substr(*a3, &v20, v7 + 1, -1);
    std::wstring::operator=(v22, v9);
    std::wstring::_Tidy_deallocate(&v20);
  }
  PrintDeviceCapabilitiesOM::NamespaceVault::GetNamespace(*(_QWORD *)(a1 + 8), &v20, &v23);
  if ( !v20 )
  {
    v16 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(a3, v10, v11, v12);
    LODWORD(v17) = 14;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v17,
      v16,
      (unsigned int)L"Namespace not found in document",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      314);
  }
  v13 = std::make_shared<PrintDeviceCapabilitiesOM::QualifiedName,std::wstring &,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const> &>(
          &v17,
          (__int64)v22,
          (__int64)&v20);
  *a2 = 0;
  a2[1] = 0;
  *a2 = *v13;
  a2[1] = v13[1];
  *v13 = 0;
  v13[1] = 0;
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(&v23);
  v14 = (std::_Ref_count_base *)a3[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return a2;
}

```

## disassembly

```asm
0x180041024  push    rbp
0x180041026  push    rbx
0x180041027  push    rsi
0x180041028  push    rdi
0x180041029  push    r14
0x18004102b  lea     rbp, [rsp-37h]
0x180041030  sub     rsp, 0C0h
0x180041037  mov     rax, cs:__security_cookie
0x18004103e  xor     rax, rsp
0x180041041  mov     [rbp+57h+var_30], rax
0x180041045  mov     rdi, r8
0x180041048  mov     rbx, rdx
0x18004104b  mov     rsi, rcx
0x18004104e  mov     [rbp+57h+var_B0], rdx
0x180041052  mov     [rbp+57h+var_98], r8
0x180041056  xorps   xmm0, xmm0
0x180041059  movups  [rbp+57h+var_50], xmm0
0x18004105d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180041065  movdqu  [rbp+57h+var_40], xmm1
0x18004106a  xor     eax, eax
0x18004106c  mov     word ptr [rbp+57h+var_50], ax
0x180041070  movups  [rbp+57h+var_70], xmm0
0x180041074  movdqu  [rbp+57h+var_60], xmm1
0x180041079  mov     word ptr [rbp+57h+var_70], ax
0x18004107d  lea     edx, [rax+3Ah]
0x180041080  xor     r8d, r8d
0x180041083  mov     rcx, [rdi]
0x180041086  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18004108b  mov     r14, rax
0x18004108e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041092  jnz     short loc_1800410B6
0x180041094  lea     r8d, [rax+6]
0x180041098  lea     rdx, aXmlns; "xmlns"
0x18004109f  lea     rcx, [rbp+57h+var_50]
0x1800410a3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800410a8  mov     rdx, [rdi]
0x1800410ab  lea     rcx, [rbp+57h+var_70]
0x1800410af  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800410b4  jmp     short loc_180041106
0x1800410b6  mov     r9, r14
0x1800410b9  xor     r8d, r8d
0x1800410bc  lea     rdx, [rbp+57h+var_90]
0x1800410c0  mov     rcx, [rdi]
0x1800410c3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800410c8  mov     rdx, rax
0x1800410cb  lea     rcx, [rbp+57h+var_50]
0x1800410cf  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800410d4  lea     rcx, [rbp+57h+var_90]
0x1800410d8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800410dd  lea     r8, [r14+1]
0x1800410e1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800410e5  lea     rdx, [rbp+57h+var_90]
0x1800410e9  mov     rcx, [rdi]
0x1800410ec  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800410f1  mov     rdx, rax
0x1800410f4  lea     rcx, [rbp+57h+var_70]
0x1800410f8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800410fd  lea     rcx, [rbp+57h+var_90]
0x180041101  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041106  lea     r8, [rbp+57h+var_50]
0x18004110a  lea     rdx, [rbp+57h+var_90]
0x18004110e  mov     rcx, [rsi+8]
0x180041112  call    ?GetNamespace@NamespaceVault@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::GetNamespace(std::wstring const &)
0x180041117  nop
0x180041118  cmp     [rbp+57h+var_90], 0
0x18004111d  jz      loc_1800411C0
0x180041123  lea     r8, [rbp+57h+var_90]
0x180041127  lea     rdx, [rbp+57h+var_70]
0x18004112b  lea     rcx, [rbp+57h+var_B0]
0x18004112f  call    ??$make_shared@VQualifiedName@PrintDeviceCapabilitiesOM@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@4@@std@@YA?AV?$shared_ptr@VQualifiedName@PrintDeviceCapabilitiesOM@@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEAV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@0@@Z; std::make_shared<PrintDeviceCapabilitiesOM::QualifiedName,std::wstring &,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const> &>(std::wstring &,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const> &)
0x180041134  mov     rcx, rax
0x180041137  mov     qword ptr [rbx], 0
0x18004113e  mov     qword ptr [rbx+8], 0
0x180041146  mov     rax, [rax]
0x180041149  mov     [rbx], rax
0x18004114c  mov     rax, [rcx+8]
0x180041150  mov     [rbx+8], rax
0x180041154  mov     qword ptr [rcx], 0
0x18004115b  mov     qword ptr [rcx+8], 0
0x180041163  mov     rcx, [rbp+57h+var_A8]; this
0x180041167  test    rcx, rcx
0x18004116a  jz      short loc_180041172
0x18004116c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041171  nop
0x180041172  mov     rcx, [rbp+57h+var_88]; this
0x180041176  test    rcx, rcx
0x180041179  jz      short loc_180041181
0x18004117b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041180  nop
0x180041181  lea     rcx, [rbp+57h+var_70]
0x180041185  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004118a  nop
0x18004118b  lea     rcx, [rbp+57h+var_50]
0x18004118f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041194  nop
0x180041195  mov     rcx, [rdi+8]; this
0x180041199  test    rcx, rcx
0x18004119c  jz      short loc_1800411A3
0x18004119e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800411a3  mov     rax, rbx
0x1800411a6  mov     rcx, [rbp+57h+var_30]
0x1800411aa  xor     rcx, rsp; StackCookie
0x1800411ad  call    __security_check_cookie
0x1800411b2  add     rsp, 0C0h
0x1800411b9  pop     r14
0x1800411bb  pop     rdi
0x1800411bc  pop     rsi
0x1800411bd  pop     rbx
0x1800411be  pop     rbp
0x1800411bf  retn
0x1800411c0  mov     rcx, rdi
0x1800411c3  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x1800411c8  mov     dword ptr [rbp+57h+var_B0], 0Eh
0x1800411cf  mov     [rsp+0E0h+var_C0], 13Ah
0x1800411d7  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x1800411de  lea     r8, aNamespaceNotFo; "Namespace not found in document"
0x1800411e5  mov     rdx, rax
0x1800411e8  lea     rcx, [rbp+57h+var_B0]
0x1800411ec  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
