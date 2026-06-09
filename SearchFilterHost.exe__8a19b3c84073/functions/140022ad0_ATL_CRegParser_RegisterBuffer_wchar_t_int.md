# ATL::CRegParser::RegisterBuffer(wchar_t *,int)

- ea: `0x140022ad0`
- end: `0x140022c3d`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022c44`

## callees

- `0x1400030a0`
- `0x140021cc4`
- `0x140022414`
- `0x140022ad0`
- `0x140022e00`
- `0x140024064`
- `0x140049bf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140022c13`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022b6c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022b6c`

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
0x140022ad0  push    rbx
0x140022ad2  push    rbp
0x140022ad3  push    rsi
0x140022ad4  push    rdi
0x140022ad5  push    r13
0x140022ad7  push    r14
0x140022ad9  push    r15
0x140022adb  mov     eax, 2050h
0x140022ae0  call    _alloca_probe
0x140022ae5  sub     rsp, rax
0x140022ae8  mov     rax, cs:__security_cookie
0x140022aef  xor     rax, rsp
0x140022af2  mov     [rsp+2088h+var_48], rax
0x140022afa  mov     r15d, r8d
0x140022afd  mov     [rsp+2088h+pv], 0
0x140022b06  lea     r8, [rsp+2088h+pv]; wchar_t **
0x140022b0b  mov     rdi, rcx
0x140022b0e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z; ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)
0x140022b13  mov     ebx, eax
0x140022b15  test    eax, eax
0x140022b17  js      loc_140022C1B
0x140022b1d  mov     rbp, [rsp+2088h+pv]
0x140022b22  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEA_W@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(wchar_t *)'::`2'::map
0x140022b29  mov     [rdi], rbp
0x140022b2c  mov     rcx, [rdi]
0x140022b2f  xor     eax, eax
0x140022b31  cmp     ax, [rcx]
0x140022b34  jz      loc_140022C10
0x140022b3a  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140022b3f  mov     rcx, rdi; this
0x140022b42  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022b47  mov     ebx, eax
0x140022b49  test    eax, eax
0x140022b4b  js      loc_140022C10
0x140022b51  xor     ebx, ebx
0x140022b53  cmp     ebx, 0Eh
0x140022b56  jnb     loc_140022C0B
0x140022b5c  movsxd  rsi, ebx
0x140022b5f  lea     rcx, [rsp+2088h+String1]; lpString1
0x140022b64  add     rsi, rsi
0x140022b67  mov     rdx, [r13+rsi*8+0]; lpString2
0x140022b6c  call    cs:__imp_lstrcmpiW
0x140022b72  test    eax, eax
0x140022b74  jz      short loc_140022B7A
0x140022b76  inc     ebx
0x140022b78  jmp     short loc_140022B53
0x140022b7a  mov     rsi, [r13+rsi*8+8]
0x140022b7f  test    rsi, rsi
0x140022b82  jz      loc_140022C0B
0x140022b88  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140022b8d  mov     rcx, rdi; this
0x140022b90  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140022b95  mov     ebx, eax
0x140022b97  test    eax, eax
0x140022b99  js      short loc_140022C10
0x140022b9b  mov     eax, 7Bh ; '{'
0x140022ba0  cmp     ax, [rsp+2088h+String1]
0x140022ba5  jnz     short loc_140022C0B
0x140022ba7  mov     [rsp+2088h+var_2068], 0; int
0x140022baf  mov     r8, rsi; HKEY
0x140022bb2  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140022bb7  mov     rcx, rdi; this
0x140022bba  test    r15d, r15d
0x140022bbd  jz      short loc_140022BF0
0x140022bbf  mov     r14, [rdi]
0x140022bc2  mov     r9d, r15d; int
0x140022bc5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140022bca  mov     ebx, eax
0x140022bcc  test    eax, eax
0x140022bce  jns     short loc_140022BFE
0x140022bd0  xor     r9d, r9d; int
0x140022bd3  mov     [rdi], r14
0x140022bd6  mov     r8, rsi; HKEY
0x140022bd9  mov     [rsp+2088h+var_2068], 0; int
0x140022be1  lea     rdx, [rsp+2088h+String1]; wchar_t *
0x140022be6  mov     rcx, rdi; this
0x140022be9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140022bee  jmp     short loc_140022C10
0x140022bf0  xor     r9d, r9d; int
0x140022bf3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140022bf8  mov     ebx, eax
0x140022bfa  test    eax, eax
0x140022bfc  js      short loc_140022C10
0x140022bfe  mov     rcx, rdi; this
0x140022c01  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140022c06  jmp     loc_140022B2C
0x140022c0b  mov     ebx, 80020009h
0x140022c10  mov     rcx, rbp; pv
0x140022c13  call    cs:__imp_CoTaskMemFree
0x140022c19  mov     eax, ebx
0x140022c1b  mov     rcx, [rsp+2088h+var_48]
0x140022c23  xor     rcx, rsp; StackCookie
0x140022c26  call    __security_check_cookie
0x140022c2b  add     rsp, 2050h
0x140022c32  pop     r15
0x140022c34  pop     r14
0x140022c36  pop     r13
0x140022c38  pop     rdi
0x140022c39  pop     rsi
0x140022c3a  pop     rbp
0x140022c3b  pop     rbx
0x140022c3c  retn
```
