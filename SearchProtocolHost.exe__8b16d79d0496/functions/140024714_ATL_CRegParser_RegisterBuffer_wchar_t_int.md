# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x140024714`
- end: `0x140024881`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140024888`

## callees

- `0x140005240`
- `0x140020960`
- `0x1400217e8`
- `0x140024714`
- `0x140024a44`
- `0x140029044`
- `0x140069b10`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400247b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400247b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140024857`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, wchar_t *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  __int64 v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (wchar_t **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *(_QWORD *)this = pv;
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
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
      Token = ATL::CRegParser::NextToken(this, String1);
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
        v10 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v10;
          ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v9, 0, 0);
        if ( Token < 0 )
          break;
      }
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x140024714  push    rbx
0x140024716  push    rbp
0x140024717  push    rsi
0x140024718  push    rdi
0x140024719  push    r13
0x14002471b  push    r14
0x14002471d  push    r15
0x14002471f  mov     eax, 2050h
0x140024724  call    _alloca_probe
0x140024729  sub     rsp, rax
0x14002472c  mov     rax, cs:__security_cookie
0x140024733  xor     rax, rsp
0x140024736  mov     [rsp+2088h+var_48], rax
0x14002473e  mov     r15d, r8d
0x140024741  mov     [rsp+2088h+pv], 0
0x14002474a  lea     r8, [rsp+2088h+pv]; wchar_t **
0x14002474f  mov     rdi, rcx
0x140024752  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x140024757  mov     ebx, eax
0x140024759  test    eax, eax
0x14002475b  js      loc_14002485F
0x140024761  mov     rbp, [rsp+2088h+pv]
0x140024766  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x14002476d  mov     [rdi], rbp
0x140024770  mov     rcx, [rdi]
0x140024773  xor     eax, eax
0x140024775  cmp     ax, [rcx]
0x140024778  jz      loc_140024854
0x14002477e  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140024783  mov     rcx, rdi; this
0x140024786  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x14002478b  mov     ebx, eax
0x14002478d  test    eax, eax
0x14002478f  js      loc_140024854
0x140024795  xor     ebx, ebx
0x140024797  cmp     ebx, 0Eh
0x14002479a  jnb     loc_14002484F
0x1400247a0  movsxd  rsi, ebx
0x1400247a3  lea     rcx, [rsp+2088h+String1]; lpString1
0x1400247a8  add     rsi, rsi
0x1400247ab  mov     rdx, [r13+rsi*8+0]; lpString2
0x1400247b0  call    cs:__imp_lstrcmpiW
0x1400247b6  test    eax, eax
0x1400247b8  jz      short loc_1400247BE
0x1400247ba  inc     ebx
0x1400247bc  jmp     short loc_140024797
0x1400247be  mov     rsi, [r13+rsi*8+8]
0x1400247c3  test    rsi, rsi
0x1400247c6  jz      loc_14002484F
0x1400247cc  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1400247d1  mov     rcx, rdi; this
0x1400247d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1400247d9  mov     ebx, eax
0x1400247db  test    eax, eax
0x1400247dd  js      short loc_140024854
0x1400247df  mov     eax, 7Bh ; '{'
0x1400247e4  cmp     ax, [rsp+2088h+String1]
0x1400247e9  jnz     short loc_14002484F
0x1400247eb  mov     [rsp+2088h+var_2068], 0; int
0x1400247f3  mov     r8, rsi; HKEY
0x1400247f6  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x1400247fb  mov     rcx, rdi; this
0x1400247fe  test    r15d, r15d
0x140024801  jz      short loc_140024834
0x140024803  mov     r14, [rdi]
0x140024806  mov     r9d, r15d; int
0x140024809  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x14002480e  mov     ebx, eax
0x140024810  test    eax, eax
0x140024812  jns     short loc_140024842
0x140024814  xor     r9d, r9d; int
0x140024817  mov     [rdi], r14
0x14002481a  mov     r8, rsi; HKEY
0x14002481d  mov     [rsp+2088h+var_2068], 0; int
0x140024825  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x14002482a  mov     rcx, rdi; this
0x14002482d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140024832  jmp     short loc_140024854
0x140024834  xor     r9d, r9d; int
0x140024837  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x14002483c  mov     ebx, eax
0x14002483e  test    eax, eax
0x140024840  js      short loc_140024854
0x140024842  mov     rcx, rdi; this
0x140024845  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x14002484a  jmp     loc_140024770
0x14002484f  mov     ebx, 80020009h
0x140024854  mov     rcx, rbp; pv
0x140024857  call    cs:__imp_CoTaskMemFree
0x14002485d  mov     eax, ebx
0x14002485f  mov     rcx, [rsp+2088h+var_48]
0x140024867  xor     rcx, rsp; StackCookie
0x14002486a  call    __security_check_cookie
0x14002486f  add     rsp, 2050h
0x140024876  pop     r15
0x140024878  pop     r14
0x14002487a  pop     r13
0x14002487c  pop     rdi
0x14002487d  pop     rsi
0x14002487e  pop     rbp
0x14002487f  pop     rbx
0x140024880  retn
```
