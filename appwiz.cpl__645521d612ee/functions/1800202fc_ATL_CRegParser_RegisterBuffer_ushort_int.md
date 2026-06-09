# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800202fc`
- end: `0x180020469`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020494`

## callees

- `0x18001fda4`
- `0x18001ff5c`
- `0x1800202fc`
- `0x18002062c`
- `0x180021758`
- `0x1800582e0`
- `0x1800583a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002043f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002043f`
- `KERNEL32!lstrcmpiW` at `0x180020398`
- `KERNEL32!lstrcmpiW` at `0x180020398`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
  HKEY v9; // rsi
  LPCWSTR v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, &pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
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
0x1800202fc  push    rbx
0x1800202fe  push    rbp
0x1800202ff  push    rsi
0x180020300  push    rdi
0x180020301  push    r13
0x180020303  push    r14
0x180020305  push    r15
0x180020307  mov     eax, 2050h
0x18002030c  call    _alloca_probe
0x180020311  sub     rsp, rax
0x180020314  mov     rax, cs:__security_cookie
0x18002031b  xor     rax, rsp
0x18002031e  mov     [rsp+2088h+var_48], rax
0x180020326  mov     r15d, r8d
0x180020329  mov     [rsp+2088h+pv], 0
0x180020332  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180020337  mov     rdi, rcx
0x18002033a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18002033f  mov     ebx, eax
0x180020341  test    eax, eax
0x180020343  js      loc_180020447
0x180020349  mov     rbp, [rsp+2088h+pv]
0x18002034e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180020355  mov     [rdi], rbp
0x180020358  mov     rcx, [rdi]
0x18002035b  xor     eax, eax
0x18002035d  cmp     ax, [rcx]
0x180020360  jz      loc_18002043C
0x180020366  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002036b  mov     rcx, rdi; this
0x18002036e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020373  mov     ebx, eax
0x180020375  test    eax, eax
0x180020377  js      loc_18002043C
0x18002037d  xor     ebx, ebx
0x18002037f  cmp     ebx, 0Eh
0x180020382  jnb     loc_180020437
0x180020388  movsxd  rsi, ebx
0x18002038b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180020390  add     rsi, rsi
0x180020393  mov     rdx, [r13+rsi*8+0]; lpString2
0x180020398  call    cs:__imp_lstrcmpiW
0x18002039e  test    eax, eax
0x1800203a0  jz      short loc_1800203A6
0x1800203a2  inc     ebx
0x1800203a4  jmp     short loc_18002037F
0x1800203a6  mov     rsi, [r13+rsi*8+8]
0x1800203ab  test    rsi, rsi
0x1800203ae  jz      loc_180020437
0x1800203b4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800203b9  mov     rcx, rdi; this
0x1800203bc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800203c1  mov     ebx, eax
0x1800203c3  test    eax, eax
0x1800203c5  js      short loc_18002043C
0x1800203c7  mov     eax, 7Bh ; '{'
0x1800203cc  cmp     ax, [rsp+2088h+String1]
0x1800203d1  jnz     short loc_180020437
0x1800203d3  mov     [rsp+2088h+var_2068], 0; int
0x1800203db  mov     r8, rsi; HKEY
0x1800203de  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800203e3  mov     rcx, rdi; this
0x1800203e6  test    r15d, r15d
0x1800203e9  jz      short loc_18002041C
0x1800203eb  mov     r14, [rdi]
0x1800203ee  mov     r9d, r15d; int
0x1800203f1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800203f6  mov     ebx, eax
0x1800203f8  test    eax, eax
0x1800203fa  jns     short loc_18002042A
0x1800203fc  xor     r9d, r9d; int
0x1800203ff  mov     [rdi], r14
0x180020402  mov     r8, rsi; HKEY
0x180020405  mov     [rsp+2088h+var_2068], 0; int
0x18002040d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180020412  mov     rcx, rdi; this
0x180020415  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002041a  jmp     short loc_18002043C
0x18002041c  xor     r9d, r9d; int
0x18002041f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180020424  mov     ebx, eax
0x180020426  test    eax, eax
0x180020428  js      short loc_18002043C
0x18002042a  mov     rcx, rdi; this
0x18002042d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180020432  jmp     loc_180020358
0x180020437  mov     ebx, 80020009h
0x18002043c  mov     rcx, rbp; pv
0x18002043f  call    cs:__imp_CoTaskMemFree
0x180020445  mov     eax, ebx
0x180020447  mov     rcx, [rsp+2088h+var_48]
0x18002044f  xor     rcx, rsp; StackCookie
0x180020452  call    __security_check_cookie
0x180020457  add     rsp, 2050h
0x18002045e  pop     r15
0x180020460  pop     r14
0x180020462  pop     r13
0x180020464  pop     rdi
0x180020465  pop     rsi
0x180020466  pop     rbp
0x180020467  pop     rbx
0x180020468  retn
```
