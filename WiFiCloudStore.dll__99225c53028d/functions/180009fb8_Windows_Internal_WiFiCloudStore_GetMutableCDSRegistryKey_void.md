# Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(void)

- ea: `0x180009fb8`
- end: `0x18000a182`
- name: `?GetMutableCDSRegistryKey@WiFiCloudStore@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `458`
- prototype: `__int64 *__fastcall(__int64 *Src)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d18`
- `0x18000ba64`
- `0x180015b9c`
- `0x18003c170`

## callees

- `0x180009fb8`
- `0x18000a188`
- `0x18000cc50`
- `0x180025308`
- `0x1800277c0`
- `0x180027e28`
- `0x18002a030`
- `0x18002aad0`
- `0x18002acc4`
- `0x180039548`
- `0x18003caa8`
- `0x18003cc2c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a145`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a145`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18000a125`
- `ext-ms-win-networking-wlanstorage-l1-1-0!GetCustomRegRootPath` at `0x18000a125`

## string_xrefs

- `0x18000a16c`: `onecore\net\wificloudstore\registry\lib\wificdscommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall Windows::Internal::WiFiCloudStore::GetMutableCDSRegistryKey(__int64 *Src)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rbp
  __int64 v4; // rbx
  unsigned __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r14
  __int64 v9; // rbx
  int CustomRegRootPath; // eax
  int v11[132]; // [rsp+20h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  memset_0(v11, 0, 0x208u);
  std::wstring::wstring(Src);
  v2 = Src[2];
  if ( v2 <= 0x104 )
  {
    v3 = Src[3];
    if ( v3 <= 0x103 )
    {
      v4 = 0x7FFFFFFFFFFFFFFELL;
      if ( 0x7FFFFFFFFFFFFFFELL - v2 < 260 - v2 )
        std::_Xlength_error("string too long");
      v5 = v3 >> 1;
      if ( v3 > 0x7FFFFFFFFFFFFFFELL - (v3 >> 1) )
      {
        v6 = 0x7FFFFFFFFFFFFFFFLL;
      }
      else
      {
        v4 = 263;
        if ( v5 + v3 > 0x107 )
          v4 = v5 + v3;
        v6 = v4 + 1;
        if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      v7 = std::_Allocate<16,std::_Default_allocate_traits>(2 * v6);
      Src[2] = 260;
      Src[3] = v4;
      if ( v3 > 7 )
      {
        v9 = *Src;
        _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(v7, *Src, v2);
        std::_Deallocate<16>(v9, 2 * v3 + 2);
      }
      else
      {
        _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(v7, Src, v2);
      }
      *Src = v7;
      Src[2] = v2;
    }
  }
  if ( (unsigned __int8)IsGetCustomRegRootPathPresent() )
  {
    CustomRegRootPath = GetCustomRegRootPath(v11, 260, L"Software\\Microsoft\\Wlansvc");
    if ( CustomRegRootPath >= 0 )
    {
      std::wstring::append(Src, v11);
      goto LABEL_13;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\wificdscommonreg.cpp",
      (const char *)(unsigned int)CustomRegRootPath,
      v11[0]);
  }
  std::wstring::_Append<unsigned short>(Src);
LABEL_13:
  std::wstring::_Append<unsigned short>(Src);
  return Src;
}

```

## disassembly

```asm
0x180009fb8  push    rbx
0x180009fba  push    rbp
0x180009fbb  push    rsi
0x180009fbc  push    rdi
0x180009fbd  push    r14
0x180009fbf  push    r15
0x180009fc1  sub     rsp, 248h
0x180009fc8  mov     rax, cs:__security_cookie
0x180009fcf  xor     rax, rsp
0x180009fd2  mov     [rsp+278h+var_48], rax
0x180009fda  mov     rdi, rcx
0x180009fdd  xor     edx, edx; Val
0x180009fdf  mov     r8d, 208h; Size
0x180009fe5  lea     rcx, [rsp+278h+var_258]; void *
0x180009fea  call    memset_0
0x180009fef  mov     rcx, rdi
0x180009ff2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180009ff7  mov     rsi, [rdi+10h]
0x180009ffb  mov     r15d, 104h
0x18000a001  cmp     rsi, r15
0x18000a004  ja      loc_18000A0A3
0x18000a00a  mov     rbp, [rdi+18h]
0x18000a00e  cmp     rbp, 103h
0x18000a015  ja      loc_18000A0A3
0x18000a01b  mov     ecx, r15d
0x18000a01e  sub     rcx, rsi
0x18000a021  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18000a02b  mov     rax, rbx
0x18000a02e  sub     rax, rsi
0x18000a031  cmp     rax, rcx
0x18000a034  jb      loc_18000A13E
0x18000a03a  mov     rcx, rbp
0x18000a03d  shr     rcx, 1
0x18000a040  mov     rax, rbx
0x18000a043  sub     rax, rcx
0x18000a046  cmp     rbp, rax
0x18000a049  ja      loc_18000A14C
0x18000a04f  lea     rax, [rcx+rbp]
0x18000a053  lea     ebx, [r15+3]
0x18000a057  cmp     rax, rbx
0x18000a05a  cmova   rbx, rax
0x18000a05e  lea     rcx, [rbx+1]
0x18000a062  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a06c  cmp     rcx, rax
0x18000a06f  ja      loc_18000A15B
0x18000a075  add     rcx, rcx
0x18000a078  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a07d  mov     r14, rax
0x18000a080  mov     [rdi+10h], r15
0x18000a084  mov     [rdi+18h], rbx
0x18000a088  mov     r8, rsi
0x18000a08b  mov     rcx, rax
0x18000a08e  cmp     rbp, 7
0x18000a092  ja      short loc_18000A0F9
0x18000a094  mov     rdx, rdi
0x18000a097  call    ??R_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@SA@QEAGQEBG_K@Z; _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(ushort * const,ushort const * const,unsigned __int64)
0x18000a09c  mov     [rdi], r14
0x18000a09f  mov     [rdi+10h], rsi
0x18000a0a3  call    IsGetCustomRegRootPathPresent
0x18000a0a8  test    al, al
0x18000a0aa  jnz     short loc_18000A116
0x18000a0ac  mov     r8d, 1Ah
0x18000a0b2  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Wlansvc"
0x18000a0b9  mov     rcx, rdi; Src
0x18000a0bc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000a0c1  mov     r8d, 0Ch
0x18000a0c7  lea     rdx, aProfilesync; "\\ProfileSync"
0x18000a0ce  mov     rcx, rdi; Src
0x18000a0d1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000a0d6  mov     rax, rdi
0x18000a0d9  mov     rcx, [rsp+278h+var_48]
0x18000a0e1  xor     rcx, rsp; StackCookie
0x18000a0e4  call    __security_check_cookie
0x18000a0e9  add     rsp, 248h
0x18000a0f0  pop     r15
0x18000a0f2  pop     r14
0x18000a0f4  pop     rdi
0x18000a0f5  pop     rsi
0x18000a0f6  pop     rbp
0x18000a0f7  pop     rbx
0x18000a0f8  retn
0x18000a0f9  mov     rbx, [rdi]
0x18000a0fc  mov     rdx, rbx
0x18000a0ff  call    ??R_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@SA@QEAGQEBG_K@Z; _lambda_7f96eb1dcf99da5daec8c2467d2d5499_::operator()(ushort * const,ushort const * const,unsigned __int64)
0x18000a104  lea     rdx, ds:2[rbp*2]
0x18000a10c  mov     rcx, rbx
0x18000a10f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000a114  jmp     short loc_18000A09C
0x18000a116  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Wlansvc"
0x18000a11d  mov     rdx, r15
0x18000a120  lea     rcx, [rsp+278h+var_258]
0x18000a125  call    cs:__imp_GetCustomRegRootPath
0x18000a12b  test    eax, eax
0x18000a12d  js      short loc_18000A161
0x18000a12f  lea     rdx, [rsp+278h+var_258]
0x18000a134  mov     rcx, rdi
0x18000a137  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000a13c  jmp     short loc_18000A0C1
0x18000a13e  lea     rcx, aStringTooLong; "string too long"
0x18000a145  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a14c  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18000a156  jmp     loc_18000A075
0x18000a15b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000a161  mov     rcx, [rsp+278h]; this
0x18000a169  mov     r9d, eax; char *
0x18000a16c  lea     r8, aOnecoreNetWifi_1; "onecore\\net\\wificloudstore\\registry"...
0x18000a173  mov     edx, 25h ; '%'; void *
0x18000a178  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000a17d  jmp     loc_18000A0AC
```
