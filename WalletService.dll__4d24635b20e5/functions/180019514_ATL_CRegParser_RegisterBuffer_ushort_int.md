# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180019514`
- end: `0x180019681`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019688`

## callees

- `0x180018f74`
- `0x1800190d4`
- `0x180019514`
- `0x180019820`
- `0x18001a19c`
- `0x180043090`
- `0x180043150`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800195b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019657`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019657`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
    while ( **this )
    {
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
        Token = -2147352567;
        break;
      }
      if ( a3 )
      {
        v10 = *this;
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *this = v10;
          ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180019514  push    rbx
0x180019516  push    rbp
0x180019517  push    rsi
0x180019518  push    rdi
0x180019519  push    r13
0x18001951b  push    r14
0x18001951d  push    r15
0x18001951f  mov     eax, 2050h
0x180019524  call    _alloca_probe
0x180019529  sub     rsp, rax
0x18001952c  mov     rax, cs:__security_cookie
0x180019533  xor     rax, rsp
0x180019536  mov     [rsp+2088h+var_48], rax
0x18001953e  mov     r15d, r8d
0x180019541  mov     [rsp+2088h+pv], 0
0x18001954a  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18001954f  mov     rdi, rcx
0x180019552  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180019557  mov     ebx, eax
0x180019559  test    eax, eax
0x18001955b  js      loc_18001965F
0x180019561  mov     rbp, [rsp+2088h+pv]
0x180019566  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18001956d  mov     [rdi], rbp
0x180019570  mov     rcx, [rdi]
0x180019573  xor     eax, eax
0x180019575  cmp     ax, [rcx]
0x180019578  jz      loc_180019654
0x18001957e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019583  mov     rcx, rdi; this
0x180019586  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001958b  mov     ebx, eax
0x18001958d  test    eax, eax
0x18001958f  js      loc_180019654
0x180019595  xor     ebx, ebx
0x180019597  cmp     ebx, 0Eh
0x18001959a  jnb     loc_18001964F
0x1800195a0  movsxd  rsi, ebx
0x1800195a3  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800195a8  add     rsi, rsi
0x1800195ab  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800195b0  call    cs:__imp_lstrcmpiW
0x1800195b6  test    eax, eax
0x1800195b8  jz      short loc_1800195BE
0x1800195ba  inc     ebx
0x1800195bc  jmp     short loc_180019597
0x1800195be  mov     rsi, [r13+rsi*8+8]
0x1800195c3  test    rsi, rsi
0x1800195c6  jz      loc_18001964F
0x1800195cc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800195d1  mov     rcx, rdi; this
0x1800195d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800195d9  mov     ebx, eax
0x1800195db  test    eax, eax
0x1800195dd  js      short loc_180019654
0x1800195df  mov     eax, 7Bh ; '{'
0x1800195e4  cmp     ax, [rsp+2088h+String1]
0x1800195e9  jnz     short loc_18001964F
0x1800195eb  mov     [rsp+2088h+var_2068], 0; int
0x1800195f3  mov     r8, rsi; HKEY
0x1800195f6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800195fb  mov     rcx, rdi; this
0x1800195fe  test    r15d, r15d
0x180019601  jz      short loc_180019634
0x180019603  mov     r14, [rdi]
0x180019606  mov     r9d, r15d; int
0x180019609  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001960e  mov     ebx, eax
0x180019610  test    eax, eax
0x180019612  jns     short loc_180019642
0x180019614  xor     r9d, r9d; int
0x180019617  mov     [rdi], r14
0x18001961a  mov     r8, rsi; HKEY
0x18001961d  mov     [rsp+2088h+var_2068], 0; int
0x180019625  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18001962a  mov     rcx, rdi; this
0x18001962d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019632  jmp     short loc_180019654
0x180019634  xor     r9d, r9d; int
0x180019637  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001963c  mov     ebx, eax
0x18001963e  test    eax, eax
0x180019640  js      short loc_180019654
0x180019642  mov     rcx, rdi; this
0x180019645  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18001964a  jmp     loc_180019570
0x18001964f  mov     ebx, 80020009h
0x180019654  mov     rcx, rbp; pv
0x180019657  call    cs:__imp_CoTaskMemFree
0x18001965d  mov     eax, ebx
0x18001965f  mov     rcx, [rsp+2088h+var_48]
0x180019667  xor     rcx, rsp; StackCookie
0x18001966a  call    __security_check_cookie
0x18001966f  add     rsp, 2050h
0x180019676  pop     r15
0x180019678  pop     r14
0x18001967a  pop     r13
0x18001967c  pop     rdi
0x18001967d  pop     rsi
0x18001967e  pop     rbp
0x18001967f  pop     rbx
0x180019680  retn
```
