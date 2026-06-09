# softricity::shared::toguid(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_GUID &)

- ea: `0x14001da5c`
- end: `0x14001dbdf`
- name: `?toguid@shared@softricity@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU_GUID@@@Z`
- size: `387`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001c6e8`
- `0x140026dd0`

## callees

- `0x140004280`
- `0x140006304`
- `0x1400066a8`
- `0x1400165b4`
- `0x140019cc8`
- `0x140019da0`
- `0x14001a08c`
- `0x14001a100`
- `0x14001d6e4`
- `0x14001da5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001db7d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001db7d`
- `ole32!CLSIDFromString` at `0x14001db8a`
- `ole32!CLSIDFromString` at `0x14001db8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall softricity::shared::toguid(__int64 a1, CLSID *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  char **v5; // rax
  char **v6; // rax
  __int64 v7; // rax
  char **v8; // r8
  LPCOLESTR lpsz[3]; // [rsp+48h] [rbp-31h] BYREF
  char *v11[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v12; // [rsp+70h] [rbp-9h]
  unsigned __int64 v13; // [rsp+78h] [rbp-1h]
  _OWORD v14[2]; // [rsp+80h] [rbp+7h] BYREF
  char *Src[4]; // [rsp+A0h] [rbp+27h] BYREF

  std::wstring::wstring((__int64)v11, a1);
  v4 = v12;
  if ( v12 )
  {
    v5 = v11;
    if ( v13 > 7 )
      v5 = (char **)v11[0];
    if ( *(_WORD *)v5 != 123 )
    {
      if ( v12 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      v6 = v11;
      if ( v13 > 7 )
        v6 = (char **)v11[0];
      std::wstring::wstring(Src, v12, v3, L"{", 1, v6, v12);
      v7 = std::wstring::append(Src, L"}");
      v14[0] = *(_OWORD *)v7;
      v14[1] = *(_OWORD *)(v7 + 16);
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 7;
      *(_WORD *)v7 = 0;
      std::wstring::operator=(v11, (__int64)v14);
      std::wstring::~wstring((char **)v14);
      std::wstring::~wstring(Src);
      v4 = v12;
    }
  }
  std::vector<wchar_t>::vector<wchar_t>(lpsz, v4 + 1);
  v8 = v11;
  if ( v13 > 7 )
    v8 = (char **)v11[0];
  _o_wcscpy_s(lpsz[0], lpsz[1] - lpsz[0], v8);
  if ( CLSIDFromString(lpsz[0], a2) >= 0 )
  {
    std::vector<wchar_t>::~vector<wchar_t>((char **)lpsz);
    std::wstring::~wstring(v11);
    return 1;
  }
  else
  {
    std::vector<wchar_t>::~vector<wchar_t>((char **)lpsz);
    std::wstring::~wstring(v11);
    return 0;
  }
}

```

## disassembly

```asm
0x14001da5c  mov     [rsp-8+arg_10], rbx
0x14001da61  push    rbp
0x14001da62  lea     rbp, [rsp-57h]
0x14001da67  sub     rsp, 0D0h
0x14001da6e  mov     rax, cs:__security_cookie
0x14001da75  xor     rax, rsp
0x14001da78  mov     [rbp+57h+var_10], rax
0x14001da7c  mov     rbx, rdx
0x14001da7f  mov     rdx, rcx
0x14001da82  lea     rcx, [rbp+57h+var_70]
0x14001da86  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001da8b  nop
0x14001da8c  mov     rdx, [rbp+57h+var_60]
0x14001da90  test    rdx, rdx
0x14001da93  jz      loc_14001DB55
0x14001da99  lea     rax, [rbp+57h+var_70]
0x14001da9d  cmp     [rbp+57h+var_58], 7
0x14001daa2  cmova   rax, [rbp+57h+var_70]
0x14001daa7  cmp     word ptr [rax], 7Bh ; '{'
0x14001daab  jz      loc_14001DB55
0x14001dab1  mov     rax, 7FFFFFFFFFFFFFFEh
0x14001dabb  sub     rax, rdx
0x14001dabe  cmp     rax, 1
0x14001dac2  jb      loc_14001DBD9
0x14001dac8  lea     rax, [rbp+57h+var_70]
0x14001dacc  cmp     [rbp+57h+var_58], 7
0x14001dad1  cmova   rax, [rbp+57h+var_70]
0x14001dad6  mov     [rsp+0D0h+var_A0], rdx
0x14001dadb  mov     [rsp+0D0h+var_A8], rax
0x14001dae0  mov     [rsp+0D0h+var_B0], 1
0x14001dae9  lea     r9, asc_1400884E8; "{"
0x14001daf0  lea     rcx, [rbp+57h+Src]
0x14001daf4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14001daf9  nop
0x14001dafa  lea     rdx, asc_1400884E4; "}"
0x14001db01  lea     rcx, [rbp+57h+Src]; Src
0x14001db05  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x14001db0a  mov     rcx, rax
0x14001db0d  movups  xmm0, xmmword ptr [rax]
0x14001db10  movups  [rbp+57h+var_50], xmm0
0x14001db14  movups  xmm1, xmmword ptr [rax+10h]
0x14001db18  movups  [rbp+57h+var_40], xmm1
0x14001db1c  mov     qword ptr [rax+10h], 0
0x14001db24  mov     qword ptr [rax+18h], 7
0x14001db2c  xor     eax, eax
0x14001db2e  mov     [rcx], ax
0x14001db31  lea     rdx, [rbp+57h+var_50]
0x14001db35  lea     rcx, [rbp+57h+var_70]
0x14001db39  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14001db3e  lea     rcx, [rbp+57h+var_50]
0x14001db42  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001db47  nop
0x14001db48  lea     rcx, [rbp+57h+Src]
0x14001db4c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001db51  mov     rdx, [rbp+57h+var_60]
0x14001db55  inc     rdx
0x14001db58  lea     rcx, [rbp+57h+lpsz]
0x14001db5c  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x14001db61  lea     r8, [rbp+57h+var_70]
0x14001db65  cmp     [rbp+57h+var_58], 7
0x14001db6a  cmova   r8, [rbp+57h+var_70]
0x14001db6f  mov     rcx, [rbp+57h+lpsz]
0x14001db73  mov     rdx, [rbp+57h+var_80]
0x14001db77  sub     rdx, rcx
0x14001db7a  sar     rdx, 1
0x14001db7d  call    cs:__imp__o_wcscpy_s
0x14001db83  mov     rdx, rbx; pclsid
0x14001db86  mov     rcx, [rbp+57h+lpsz]; lpsz
0x14001db8a  call    cs:__imp_CLSIDFromString
0x14001db90  lea     rcx, [rbp+57h+lpsz]
0x14001db94  test    eax, eax
0x14001db96  jns     short loc_14001DBAB
0x14001db98  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14001db9d  nop
0x14001db9e  lea     rcx, [rbp+57h+var_70]
0x14001dba2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dba7  xor     al, al
0x14001dba9  jmp     short loc_14001DBBC
0x14001dbab  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14001dbb0  nop
0x14001dbb1  lea     rcx, [rbp+57h+var_70]
0x14001dbb5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001dbba  mov     al, 1
0x14001dbbc  mov     rcx, [rbp+57h+var_10]
0x14001dbc0  xor     rcx, rsp; StackCookie
0x14001dbc3  call    __security_check_cookie
0x14001dbc8  mov     rbx, [rsp+0D0h+arg_10]
0x14001dbd0  add     rsp, 0D0h
0x14001dbd7  pop     rbp
0x14001dbd8  retn
0x14001dbd9  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
