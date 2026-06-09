# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180008e9c`
- end: `0x180009009`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180004710`

## callees

- `0x180004fb8`
- `0x180006330`
- `0x180006490`
- `0x180008ad8`
- `0x180008e9c`
- `0x18000b630`
- `0x18000b6f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180008f38`
- `KERNEL32!lstrcmpiW` at `0x180008f38`
- `ole32!CoTaskMemFree` at `0x180008fdf`
- `ole32!CoTaskMemFree` at `0x180008fdf`

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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
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
0x180008e9c  push    rbx
0x180008e9e  push    rbp
0x180008e9f  push    rsi
0x180008ea0  push    rdi
0x180008ea1  push    r13
0x180008ea3  push    r14
0x180008ea5  push    r15
0x180008ea7  mov     eax, 2050h
0x180008eac  call    _alloca_probe
0x180008eb1  sub     rsp, rax
0x180008eb4  mov     rax, cs:__security_cookie
0x180008ebb  xor     rax, rsp
0x180008ebe  mov     [rsp+2088h+var_48], rax
0x180008ec6  mov     r15d, r8d
0x180008ec9  mov     [rsp+2088h+pv], 0
0x180008ed2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180008ed7  mov     rdi, rcx
0x180008eda  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180008edf  mov     ebx, eax
0x180008ee1  test    eax, eax
0x180008ee3  js      loc_180008FE7
0x180008ee9  mov     rbp, [rsp+2088h+pv]
0x180008eee  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180008ef5  mov     [rdi], rbp
0x180008ef8  mov     rcx, [rdi]
0x180008efb  xor     eax, eax
0x180008efd  cmp     ax, [rcx]
0x180008f00  jz      loc_180008FDC
0x180008f06  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008f0b  mov     rcx, rdi; this
0x180008f0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f13  mov     ebx, eax
0x180008f15  test    eax, eax
0x180008f17  js      loc_180008FDC
0x180008f1d  xor     ebx, ebx
0x180008f1f  cmp     ebx, 0Eh
0x180008f22  jnb     loc_180008FD7
0x180008f28  movsxd  rsi, ebx
0x180008f2b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008f30  add     rsi, rsi
0x180008f33  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008f38  call    cs:__imp_lstrcmpiW
0x180008f3e  test    eax, eax
0x180008f40  jz      short loc_180008F46
0x180008f42  inc     ebx
0x180008f44  jmp     short loc_180008F1F
0x180008f46  mov     rsi, [r13+rsi*8+8]
0x180008f4b  test    rsi, rsi
0x180008f4e  jz      loc_180008FD7
0x180008f54  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008f59  mov     rcx, rdi; this
0x180008f5c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f61  mov     ebx, eax
0x180008f63  test    eax, eax
0x180008f65  js      short loc_180008FDC
0x180008f67  mov     eax, 7Bh ; '{'
0x180008f6c  cmp     ax, [rsp+2088h+String1]
0x180008f71  jnz     short loc_180008FD7
0x180008f73  mov     [rsp+2088h+var_2068], 0; int
0x180008f7b  mov     r8, rsi; HKEY
0x180008f7e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008f83  mov     rcx, rdi; this
0x180008f86  test    r15d, r15d
0x180008f89  jz      short loc_180008FBC
0x180008f8b  mov     r14, [rdi]
0x180008f8e  mov     r9d, r15d; int
0x180008f91  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008f96  mov     ebx, eax
0x180008f98  test    eax, eax
0x180008f9a  jns     short loc_180008FCA
0x180008f9c  xor     r9d, r9d; int
0x180008f9f  mov     [rdi], r14
0x180008fa2  mov     r8, rsi; HKEY
0x180008fa5  mov     [rsp+2088h+var_2068], 0; int
0x180008fad  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008fb2  mov     rcx, rdi; this
0x180008fb5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008fba  jmp     short loc_180008FDC
0x180008fbc  xor     r9d, r9d; int
0x180008fbf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008fc4  mov     ebx, eax
0x180008fc6  test    eax, eax
0x180008fc8  js      short loc_180008FDC
0x180008fca  mov     rcx, rdi; this
0x180008fcd  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180008fd2  jmp     loc_180008EF8
0x180008fd7  mov     ebx, 80020009h
0x180008fdc  mov     rcx, rbp; pv
0x180008fdf  call    cs:__imp_CoTaskMemFree
0x180008fe5  mov     eax, ebx
0x180008fe7  mov     rcx, [rsp+2088h+var_48]
0x180008fef  xor     rcx, rsp; StackCookie
0x180008ff2  call    __security_check_cookie
0x180008ff7  add     rsp, 2050h
0x180008ffe  pop     r15
0x180009000  pop     r14
0x180009002  pop     r13
0x180009004  pop     rdi
0x180009005  pop     rsi
0x180009006  pop     rbp
0x180009007  pop     rbx
0x180009008  retn
```
