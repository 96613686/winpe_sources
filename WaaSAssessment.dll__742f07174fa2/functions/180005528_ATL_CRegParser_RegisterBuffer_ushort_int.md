# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180005528`
- end: `0x1800056b2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800056b8`

## callees

- `0x180004ef0`
- `0x18000509c`
- `0x180005528`
- `0x18000589c`
- `0x180019760`
- `0x180019820`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800055c6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005697`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005697`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800055ad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800055ad`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        while ( lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * v8]) )
        {
          if ( (unsigned int)++v8 >= 0xE )
            goto LABEL_7;
        }
        v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v9 )
          goto LABEL_7;
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
        if ( Token < 0 )
          break;
        if ( String1[0] != 123 )
        {
LABEL_7:
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
        while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
          *this = CharNextW(*this);
      }
      while ( **this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x180005528  push    rbx
0x18000552a  push    rbp
0x18000552b  push    rsi
0x18000552c  push    rdi
0x18000552d  push    r13
0x18000552f  push    r14
0x180005531  push    r15
0x180005533  mov     eax, 2050h
0x180005538  call    _alloca_probe
0x18000553d  sub     rsp, rax
0x180005540  mov     rax, cs:__security_cookie
0x180005547  xor     rax, rsp
0x18000554a  mov     [rsp+2088h+var_48], rax
0x180005552  mov     r15d, r8d
0x180005555  mov     [rsp+2088h+pv], 0
0x18000555e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005563  mov     rdi, rcx
0x180005566  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000556b  mov     ebx, eax
0x18000556d  test    eax, eax
0x18000556f  js      short loc_1800055CE
0x180005571  mov     rbp, [rsp+2088h+pv]
0x180005576  xor     eax, eax
0x180005578  mov     [rdi], rbp
0x18000557b  cmp     ax, [rbp+0]
0x18000557f  jz      short loc_1800055C3
0x180005581  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005588  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000558d  mov     rcx, rdi; this
0x180005590  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005595  mov     ebx, eax
0x180005597  test    eax, eax
0x180005599  js      short loc_1800055C3
0x18000559b  xor     ebx, ebx
0x18000559d  movsxd  rsi, ebx
0x1800055a0  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800055a5  add     rsi, rsi
0x1800055a8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800055ad  call    cs:__imp_lstrcmpiW
0x1800055b3  test    eax, eax
0x1800055b5  jz      short loc_1800055F0
0x1800055b7  inc     ebx
0x1800055b9  cmp     ebx, 0Eh
0x1800055bc  jb      short loc_18000559D
0x1800055be  mov     ebx, 80020009h
0x1800055c3  mov     rcx, rbp; pv
0x1800055c6  call    cs:__imp_CoTaskMemFree
0x1800055cc  mov     eax, ebx
0x1800055ce  mov     rcx, [rsp+2088h+var_48]
0x1800055d6  xor     rcx, rsp; StackCookie
0x1800055d9  call    __security_check_cookie
0x1800055de  add     rsp, 2050h
0x1800055e5  pop     r15
0x1800055e7  pop     r14
0x1800055e9  pop     r13
0x1800055eb  pop     rdi
0x1800055ec  pop     rsi
0x1800055ed  pop     rbp
0x1800055ee  pop     rbx
0x1800055ef  retn
0x1800055f0  mov     rsi, [r13+rsi*8+8]
0x1800055f5  test    rsi, rsi
0x1800055f8  jz      short loc_1800055BE
0x1800055fa  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800055ff  mov     rcx, rdi; this
0x180005602  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005607  mov     ebx, eax
0x180005609  test    eax, eax
0x18000560b  js      short loc_1800055C3
0x18000560d  mov     eax, 7Bh ; '{'
0x180005612  cmp     ax, [rsp+2088h+String1]
0x180005617  jnz     short loc_1800055BE
0x180005619  mov     [rsp+2088h+var_2068], 0; int
0x180005621  mov     r8, rsi; HKEY
0x180005624  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005629  mov     rcx, rdi; this
0x18000562c  test    r15d, r15d
0x18000562f  jz      short loc_180005665
0x180005631  mov     r14, [rdi]
0x180005634  mov     r9d, r15d; int
0x180005637  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000563c  mov     ebx, eax
0x18000563e  test    eax, eax
0x180005640  jns     short loc_180005677
0x180005642  xor     r9d, r9d; int
0x180005645  mov     [rdi], r14
0x180005648  mov     r8, rsi; HKEY
0x18000564b  mov     [rsp+2088h+var_2068], 0; int
0x180005653  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005658  mov     rcx, rdi; this
0x18000565b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005660  jmp     loc_1800055C3
0x180005665  xor     r9d, r9d; int
0x180005668  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000566d  mov     ebx, eax
0x18000566f  test    eax, eax
0x180005671  js      loc_1800055C3
0x180005677  mov     r8, [rdi]
0x18000567a  movzx   edx, word ptr [r8]
0x18000567e  mov     ecx, edx
0x180005680  sub     ecx, 9
0x180005683  jz      short loc_180005694
0x180005685  sub     ecx, 1
0x180005688  jz      short loc_180005694
0x18000568a  sub     ecx, 3
0x18000568d  jz      short loc_180005694
0x18000568f  cmp     ecx, 13h
0x180005692  jnz     short loc_1800056A2
0x180005694  mov     rcx, r8; lpsz
0x180005697  call    cs:__imp_CharNextW
0x18000569d  mov     [rdi], rax
0x1800056a0  jmp     short loc_180005677
0x1800056a2  xor     eax, eax
0x1800056a4  cmp     ax, dx
0x1800056a7  jnz     loc_180005588
0x1800056ad  jmp     loc_1800055C3
```
