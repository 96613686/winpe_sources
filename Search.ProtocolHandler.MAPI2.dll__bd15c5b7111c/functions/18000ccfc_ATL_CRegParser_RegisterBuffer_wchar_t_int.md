# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x18000ccfc`
- end: `0x18000ce69`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ce70`

## callees

- `0x180002300`
- `0x18000c740`
- `0x18000c8f8`
- `0x18000ccfc`
- `0x18000d0b8`
- `0x18000d8f4`
- `0x18003a060`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cd98`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cd98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ce3f`

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
0x18000ccfc  push    rbx
0x18000ccfe  push    rbp
0x18000ccff  push    rsi
0x18000cd00  push    rdi
0x18000cd01  push    r13
0x18000cd03  push    r14
0x18000cd05  push    r15
0x18000cd07  mov     eax, 2050h
0x18000cd0c  call    _alloca_probe
0x18000cd11  sub     rsp, rax
0x18000cd14  mov     rax, cs:__security_cookie
0x18000cd1b  xor     rax, rsp
0x18000cd1e  mov     [rsp+2088h+var_48], rax
0x18000cd26  mov     r15d, r8d
0x18000cd29  mov     [rsp+2088h+pv], 0
0x18000cd32  lea     r8, [rsp+2088h+pv]; wchar_t **
0x18000cd37  mov     rdi, rcx
0x18000cd3a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x18000cd3f  mov     ebx, eax
0x18000cd41  test    eax, eax
0x18000cd43  js      loc_18000CE47
0x18000cd49  mov     rbp, [rsp+2088h+pv]
0x18000cd4e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x18000cd55  mov     [rdi], rbp
0x18000cd58  mov     rcx, [rdi]
0x18000cd5b  xor     eax, eax
0x18000cd5d  cmp     ax, [rcx]
0x18000cd60  jz      loc_18000CE3C
0x18000cd66  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000cd6b  mov     rcx, rdi; this
0x18000cd6e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000cd73  mov     ebx, eax
0x18000cd75  test    eax, eax
0x18000cd77  js      loc_18000CE3C
0x18000cd7d  xor     ebx, ebx
0x18000cd7f  cmp     ebx, 0Eh
0x18000cd82  jnb     loc_18000CE37
0x18000cd88  movsxd  rsi, ebx
0x18000cd8b  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000cd90  add     rsi, rsi
0x18000cd93  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000cd98  call    cs:__imp_lstrcmpiW
0x18000cd9e  test    eax, eax
0x18000cda0  jz      short loc_18000CDA6
0x18000cda2  inc     ebx
0x18000cda4  jmp     short loc_18000CD7F
0x18000cda6  mov     rsi, [r13+rsi*8+8]
0x18000cdab  test    rsi, rsi
0x18000cdae  jz      loc_18000CE37
0x18000cdb4  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000cdb9  mov     rcx, rdi; this
0x18000cdbc  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000cdc1  mov     ebx, eax
0x18000cdc3  test    eax, eax
0x18000cdc5  js      short loc_18000CE3C
0x18000cdc7  mov     eax, 7Bh ; '{'
0x18000cdcc  cmp     ax, [rsp+2088h+String1]
0x18000cdd1  jnz     short loc_18000CE37
0x18000cdd3  mov     [rsp+2088h+var_2068], 0; int
0x18000cddb  mov     r8, rsi; HKEY
0x18000cdde  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000cde3  mov     rcx, rdi; this
0x18000cde6  test    r15d, r15d
0x18000cde9  jz      short loc_18000CE1C
0x18000cdeb  mov     r14, [rdi]
0x18000cdee  mov     r9d, r15d; int
0x18000cdf1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000cdf6  mov     ebx, eax
0x18000cdf8  test    eax, eax
0x18000cdfa  jns     short loc_18000CE2A
0x18000cdfc  xor     r9d, r9d; int
0x18000cdff  mov     [rdi], r14
0x18000ce02  mov     r8, rsi; HKEY
0x18000ce05  mov     [rsp+2088h+var_2068], 0; int
0x18000ce0d  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x18000ce12  mov     rcx, rdi; this
0x18000ce15  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000ce1a  jmp     short loc_18000CE3C
0x18000ce1c  xor     r9d, r9d; int
0x18000ce1f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18000ce24  mov     ebx, eax
0x18000ce26  test    eax, eax
0x18000ce28  js      short loc_18000CE3C
0x18000ce2a  mov     rcx, rdi; this
0x18000ce2d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000ce32  jmp     loc_18000CD58
0x18000ce37  mov     ebx, 80020009h
0x18000ce3c  mov     rcx, rbp; pv
0x18000ce3f  call    cs:__imp_CoTaskMemFree
0x18000ce45  mov     eax, ebx
0x18000ce47  mov     rcx, [rsp+2088h+var_48]
0x18000ce4f  xor     rcx, rsp; StackCookie
0x18000ce52  call    __security_check_cookie
0x18000ce57  add     rsp, 2050h
0x18000ce5e  pop     r15
0x18000ce60  pop     r14
0x18000ce62  pop     r13
0x18000ce64  pop     rdi
0x18000ce65  pop     rsi
0x18000ce66  pop     rbp
0x18000ce67  pop     rbx
0x18000ce68  retn
```
