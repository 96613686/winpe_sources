# WlanSyncTaskWlanToCDS::PopulateProfileXml(wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile> &,ushort const *,_GUID const &,ushort const * const)

- ea: `0x1800365d8`
- end: `0x1800366d5`
- name: `?PopulateProfileXml@WlanSyncTaskWlanToCDS@@CAXAEAV?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@PEBGAEBU_GUID@@QEBG@Z`
- size: `253`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016ba4`

## callees

- `0x18001c95c`
- `0x18001cf6c`
- `0x18001d100`
- `0x1800291a4`
- `0x18002e2d0`
- `0x18002f1ac`
- `0x18003651c`
- `0x1800365d8`
- `0x180036754`

## string_xrefs

- `0x18003669c`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x1800366c3`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskwlantocds.cpp`
- `0x18003668a`: `ProfileOwnerSecurity: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WlanSyncTaskWlanToCDS::PopulateProfileXml(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  int v10; // r8d
  __int64 v11; // rax
  unsigned int v13; // eax
  int v14; // [rsp+20h] [rbp-78h]
  char *v15; // [rsp+28h] [rbp-70h]
  _BYTE v16[104]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a2 + 2 * v9) );
  if ( !v9 )
  {
    v13 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x185,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)v13,
      v14);
  }
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(v16);
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a2 + 2 * v11) );
  if ( (unsigned __int8)std::_Regex_search2<unsigned short const *,std::allocator<std::sub_match<unsigned short const *>>,unsigned short,std::regex_traits<unsigned short>,unsigned short const *>(
                          a2,
                          (int)a2 + 2 * (int)v11,
                          v10,
                          (unsigned int)v16,
                          16) )
  {
    LODWORD(v15) = WlanSyncTaskWlanToCDS::GetProfileOwnerSecurityWithWlanProfileName(a3, a4);
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskwlantocds.cpp",
      (const char *)0x1771,
      (unsigned int)"ProfileOwnerSecurity: %d",
      v15);
  }
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  std::wstring::_Assign<unsigned short>(a1);
  return std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(v16);
}

```

## disassembly

```asm
0x1800365d8  push    rbx
0x1800365da  push    rbp
0x1800365db  push    rsi
0x1800365dc  push    rdi
0x1800365dd  push    r14
0x1800365df  push    r15
0x1800365e1  sub     rsp, 68h
0x1800365e5  mov     rbp, r9
0x1800365e8  mov     r14, r8
0x1800365eb  mov     rdi, rdx
0x1800365ee  mov     rsi, rcx
0x1800365f1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800365f5  mov     rax, rbx
0x1800365f8  xor     r15d, r15d
0x1800365fb  inc     rax
0x1800365fe  cmp     [rdx+rax*2], r15w
0x180036603  jnz     short loc_1800365FB
0x180036605  test    rax, rax
0x180036608  jz      loc_1800366AE
0x18003660e  lea     rcx, [rsp+98h+var_68]
0x180036613  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180036618  nop
0x180036619  mov     rax, rbx
0x18003661c  inc     rax
0x18003661f  cmp     [rdi+rax*2], r15w
0x180036624  jnz     short loc_18003661C
0x180036626  lea     rdx, [rdi+rax*2]
0x18003662a  mov     [rsp+98h+var_78], 10h
0x180036632  lea     r9, [rsp+98h+var_68]
0x180036637  mov     rcx, rdi
0x18003663a  call    ??$_Regex_search2@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@GV?$regex_traits@G@2@PEBG@std@@YA_NPEBG0PEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@0@AEBV?$basic_regex@GV?$regex_traits@G@std@@@0@W4match_flag_type@regex_constants@0@0@Z; std::_Regex_search2<ushort const *,std::allocator<std::sub_match<ushort const *>>,ushort,std::regex_traits<ushort>,ushort const *>(ushort const *,ushort const *,std::match_results<ushort const *> *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::regex_constants::match_flag_type,ushort const *)
0x18003663f  test    al, al
0x180036641  jnz     short loc_180036673
0x180036643  inc     rbx
0x180036646  cmp     [rdi+rbx*2], r15w
0x18003664b  jnz     short loc_180036643
0x18003664d  mov     r8, rbx
0x180036650  mov     rdx, rdi
0x180036653  mov     rcx, rsi
0x180036656  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003665b  nop
0x18003665c  lea     rcx, [rsp+98h+var_68]
0x180036661  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180036666  add     rsp, 68h
0x18003666a  pop     r15
0x18003666c  pop     r14
0x18003666e  pop     rdi
0x18003666f  pop     rsi
0x180036670  pop     rbp
0x180036671  pop     rbx
0x180036672  retn
0x180036673  mov     rdx, rbp
0x180036676  mov     rcx, r14
0x180036679  call    ?GetProfileOwnerSecurityWithWlanProfileName@WlanSyncTaskWlanToCDS@@CA?AW4ProfileOwnerSecurity@WiFiCloudStore@Internal@Windows@@AEBU_GUID@@QEBG@Z; WlanSyncTaskWlanToCDS::GetProfileOwnerSecurityWithWlanProfileName(_GUID const &,ushort const * const)
0x18003667e  mov     rcx, [rsp+98h]; this
0x180036686  mov     dword ptr [rsp+98h+var_70], eax; char *
0x18003668a  lea     rax, aProfileownerse; "ProfileOwnerSecurity: %d"
0x180036691  mov     qword ptr [rsp+98h+var_78], rax; unsigned int
0x180036696  mov     r9d, 1771h; char *
0x18003669c  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800366a3  mov     edx, 193h; void *
0x1800366a8  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800366ae  mov     ecx, 80070057h
0x1800366b3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800366b8  mov     r9d, eax; char *
0x1800366bb  mov     rcx, [rsp+98h]; this
0x1800366c3  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800366ca  mov     edx, 185h; void *
0x1800366cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
