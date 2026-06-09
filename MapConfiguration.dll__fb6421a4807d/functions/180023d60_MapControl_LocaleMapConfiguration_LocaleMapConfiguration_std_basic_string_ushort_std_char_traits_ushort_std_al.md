# MapControl::LocaleMapConfiguration::LocaleMapConfiguration(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023d60`
- end: `0x180023f1d`
- name: `??0LocaleMapConfiguration@MapControl@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18001d560`

## callees

- `0x1800094a0`
- `0x18000ba50`
- `0x18000c354`
- `0x18000cab8`
- `0x18000cfcc`
- `0x18000fb84`
- `0x18000fe30`
- `0x18000fe68`
- `0x180011ddc`
- `0x1800153b4`
- `0x18001d5d8`
- `0x18001dcec`
- `0x18001ef80`
- `0x180023af4`
- `0x180023d60`
- `0x180023f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023ef2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MapControl::LocaleMapConfiguration::LocaleMapConfiguration(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v7; // rsi
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _BYTE v14[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v15[32]; // [rsp+58h] [rbp-70h] BYREF

  Pal::CppEvent<>::CppEvent<>();
  Pal::Mutex::Mutex((Pal::Mutex *)(a1 + 296));
  v7 = a1 + 336;
  std::map<enum MapControl::ConfigurationKeys,std::wstring>::map<enum MapControl::ConfigurationKeys,std::wstring>((_QWORD *)(a1 + 336));
  std::wstring::wstring(a1 + 352, a2);
  std::wstring::wstring(a1 + 384, a3);
  std::wstring::wstring(a1 + 416);
  std::wstring::wstring(a1 + 448);
  *(_QWORD *)(a1 + 480) = 0;
  *(_QWORD *)(a1 + 488) = 0;
  std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 496) = 2;
  *(_BYTE *)(a1 + 505) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 296));
  if ( (__int64 *)(a1 + 336) != &MapControl::EndPoints::sDefaultConfigValuesMap )
  {
    v8 = *(_QWORD **)v7;
    std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
      a1 + 336,
      a1 + 336,
      *(__int64 **)(*(_QWORD *)v7 + 8LL));
    v8[1] = v8;
    *v8 = v8;
    v8[2] = v8;
    *(_QWORD *)(a1 + 344) = 0;
    std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::_Copy<0>(
      (_QWORD *)(a1 + 336),
      &MapControl::EndPoints::sDefaultConfigValuesMap);
  }
  v9 = std::operator+<unsigned short>(v14, a1 + 352, a1 + 384);
  std::wstring::operator=(a1 + 448, v9);
  std::wstring::_Tidy_deallocate(v14);
  v10 = std::operator+<unsigned short>(v15, a1 + 384, L";");
  v11 = std::wstring::append(v10, a4);
  std::wstring::wstring(v14, v11);
  std::wstring::operator=(a1 + 416, v14);
  std::wstring::_Tidy_deallocate(v14);
  std::wstring::_Tidy_deallocate(v15);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 296));
  return a1;
}

```

## disassembly

```asm
0x180023d60  push    rbx
0x180023d62  push    rbp
0x180023d63  push    rsi
0x180023d64  push    rdi
0x180023d65  push    r12
0x180023d67  push    r13
0x180023d69  push    r14
0x180023d6b  push    r15
0x180023d6d  sub     rsp, 88h
0x180023d74  mov     rax, cs:__security_cookie
0x180023d7b  xor     rax, rsp
0x180023d7e  mov     [rsp+0C8h+var_50], rax
0x180023d83  mov     [rsp+0C8h+var_A0], r9
0x180023d88  mov     rdi, r8
0x180023d8b  mov     rbx, rdx
0x180023d8e  mov     rbp, rcx
0x180023d91  mov     [rsp+0C8h+var_98], rcx
0x180023d96  call    ??0?$CppEvent@$$V@Pal@@QEAA@XZ; Pal::CppEvent<>::CppEvent<>(void)
0x180023d9b  nop
0x180023d9c  lea     r14, [rbp+128h]
0x180023da3  mov     rcx, r14; this
0x180023da6  call    ??0Mutex@Pal@@QEAA@XZ; Pal::Mutex::Mutex(void)
0x180023dab  nop
0x180023dac  lea     rsi, [rbp+150h]
0x180023db3  mov     rcx, rsi
0x180023db6  call    ??0?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAA@XZ; std::map<MapControl::ConfigurationKeys,std::wstring>::map<MapControl::ConfigurationKeys,std::wstring>(void)
0x180023dbb  nop
0x180023dbc  lea     r12, [rbp+160h]
0x180023dc3  mov     rdx, rbx
0x180023dc6  mov     rcx, r12
0x180023dc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023dce  nop
0x180023dcf  lea     r15, [rbp+180h]
0x180023dd6  mov     rdx, rdi
0x180023dd9  mov     rcx, r15
0x180023ddc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023de1  nop
0x180023de2  lea     rdi, [rbp+1A0h]
0x180023de9  mov     rcx, rdi
0x180023dec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023df1  nop
0x180023df2  lea     r13, [rbp+1C0h]
0x180023df9  mov     rcx, r13
0x180023dfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180023e01  nop
0x180023e02  lea     rcx, [rbp+1E0h]
0x180023e09  xor     ebx, ebx
0x180023e0b  mov     [rcx], rbx
0x180023e0e  mov     [rcx+8], rbx
0x180023e12  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<int,std::wstring,std::less<int>,std::allocator<std::pair<int const,std::wstring>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180023e17  nop
0x180023e18  mov     qword ptr [rbp+1F0h], 2
0x180023e23  mov     [rbp+1F9h], bl
0x180023e29  mov     [rsp+0C8h+var_A8], r14
0x180023e2e  mov     rcx, r14; lpCriticalSection
0x180023e31  call    cs:__imp_EnterCriticalSection
0x180023e37  nop
0x180023e38  lea     rax, ?sDefaultConfigValuesMap@EndPoints@MapControl@@2V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@B; std::map<MapControl::ConfigurationKeys,std::wstring> const MapControl::EndPoints::sDefaultConfigValuesMap
0x180023e3f  cmp     rsi, rax
0x180023e42  jz      short loc_180023E78
0x180023e44  mov     rbx, [rsi]
0x180023e47  mov     r8, [rbx+8]
0x180023e4b  mov     rdx, rsi
0x180023e4e  mov     rcx, rsi
0x180023e51  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &,std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *> *)
0x180023e56  mov     [rbx+8], rbx
0x180023e5a  mov     [rbx], rbx
0x180023e5d  mov     [rbx+10h], rbx
0x180023e61  mov     qword ptr [rsi+8], 0
0x180023e69  lea     rdx, ?sDefaultConfigValuesMap@EndPoints@MapControl@@2V?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@B; std::map<MapControl::ConfigurationKeys,std::wstring> const MapControl::EndPoints::sDefaultConfigValuesMap
0x180023e70  mov     rcx, rsi
0x180023e73  call    ??$_Copy@$0A@@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@IEAAXAEBV01@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::_Copy<0>(std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>> const &)
0x180023e78  mov     r8, r15
0x180023e7b  mov     rdx, r12
0x180023e7e  lea     rcx, [rsp+0C8h+var_90]
0x180023e83  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180023e88  mov     rdx, rax
0x180023e8b  mov     rcx, r13
0x180023e8e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023e93  lea     rcx, [rsp+0C8h+var_90]
0x180023e98  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023e9d  lea     r8, asc_180048758; ";"
0x180023ea4  mov     rdx, r15
0x180023ea7  lea     rcx, [rsp+0C8h+var_70]
0x180023eac  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180023eb1  nop
0x180023eb2  mov     rdx, [rsp+0C8h+var_A0]
0x180023eb7  mov     rcx, rax
0x180023eba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180023ebf  mov     rdx, rax
0x180023ec2  lea     rcx, [rsp+0C8h+var_90]
0x180023ec7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180023ecc  lea     rdx, [rsp+0C8h+var_90]
0x180023ed1  mov     rcx, rdi
0x180023ed4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023ed9  lea     rcx, [rsp+0C8h+var_90]
0x180023ede  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023ee3  nop
0x180023ee4  lea     rcx, [rsp+0C8h+var_70]
0x180023ee9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023eee  nop
0x180023eef  mov     rcx, r14; lpCriticalSection
0x180023ef2  call    cs:__imp_LeaveCriticalSection
0x180023ef8  nop
0x180023ef9  mov     rax, rbp
0x180023efc  mov     rcx, [rsp+0C8h+var_50]
0x180023f01  xor     rcx, rsp; StackCookie
0x180023f04  call    __security_check_cookie
0x180023f09  add     rsp, 88h
0x180023f10  pop     r15
0x180023f12  pop     r14
0x180023f14  pop     r13
0x180023f16  pop     r12
0x180023f18  pop     rdi
0x180023f19  pop     rsi
0x180023f1a  pop     rbp
0x180023f1b  pop     rbx
0x180023f1c  retn
```
