# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180019cec`
- end: `0x180019e66`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `378`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019e6c`

## callees

- `0x180016a40`
- `0x180019700`
- `0x180019890`
- `0x180019cec`
- `0x18001a0d8`
- `0x18001a8a4`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e35`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019d88`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019d88`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
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
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
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
0x180019cec  push    rbx
0x180019cee  push    rbp
0x180019cef  push    rsi
0x180019cf0  push    rdi
0x180019cf1  push    r13
0x180019cf3  push    r14
0x180019cf5  push    r15
0x180019cf7  mov     eax, 2050h
0x180019cfc  call    _alloca_probe
0x180019d01  sub     rsp, rax
0x180019d04  mov     rax, cs:__security_cookie
0x180019d0b  xor     rax, rsp
0x180019d0e  mov     [rsp+2088h+var_48], rax
0x180019d16  mov     r15d, r8d
0x180019d19  mov     [rsp+2088h+pv], 0
0x180019d22  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180019d27  mov     rdi, rcx
0x180019d2a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180019d2f  mov     ebx, eax
0x180019d31  test    eax, eax
0x180019d33  js      loc_180019E43
0x180019d39  mov     rbp, [rsp+2088h+pv]
0x180019d3e  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180019d45  mov     [rdi], rbp
0x180019d48  mov     rcx, [rdi]
0x180019d4b  xor     eax, eax
0x180019d4d  cmp     ax, [rcx]
0x180019d50  jz      loc_180019E32
0x180019d56  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019d5b  mov     rcx, rdi; this
0x180019d5e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019d63  mov     ebx, eax
0x180019d65  test    eax, eax
0x180019d67  js      loc_180019E32
0x180019d6d  xor     ebx, ebx
0x180019d6f  cmp     ebx, 0Eh
0x180019d72  jnb     loc_180019E2D
0x180019d78  movsxd  rsi, ebx
0x180019d7b  lea     rcx, [rsp+2088h+String1]; lpString1
0x180019d80  add     rsi, rsi
0x180019d83  mov     rdx, [r13+rsi*8+0]; lpString2
0x180019d88  call    cs:__imp_lstrcmpiW
0x180019d8f  nop     dword ptr [rax+rax+00h]
0x180019d94  test    eax, eax
0x180019d96  jz      short loc_180019D9C
0x180019d98  inc     ebx
0x180019d9a  jmp     short loc_180019D6F
0x180019d9c  mov     rsi, [r13+rsi*8+8]
0x180019da1  test    rsi, rsi
0x180019da4  jz      loc_180019E2D
0x180019daa  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019daf  mov     rcx, rdi; this
0x180019db2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019db7  mov     ebx, eax
0x180019db9  test    eax, eax
0x180019dbb  js      short loc_180019E32
0x180019dbd  mov     eax, 7Bh ; '{'
0x180019dc2  cmp     ax, [rsp+2088h+String1]
0x180019dc7  jnz     short loc_180019E2D
0x180019dc9  mov     [rsp+2088h+var_2068], 0; int
0x180019dd1  mov     r8, rsi; HKEY
0x180019dd4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019dd9  mov     rcx, rdi; this
0x180019ddc  test    r15d, r15d
0x180019ddf  jz      short loc_180019E12
0x180019de1  mov     r14, [rdi]
0x180019de4  mov     r9d, r15d; int
0x180019de7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019dec  mov     ebx, eax
0x180019dee  test    eax, eax
0x180019df0  jns     short loc_180019E20
0x180019df2  xor     r9d, r9d; int
0x180019df5  mov     [rdi], r14
0x180019df8  mov     r8, rsi; HKEY
0x180019dfb  mov     [rsp+2088h+var_2068], 0; int
0x180019e03  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019e08  mov     rcx, rdi; this
0x180019e0b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019e10  jmp     short loc_180019E32
0x180019e12  xor     r9d, r9d; int
0x180019e15  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019e1a  mov     ebx, eax
0x180019e1c  test    eax, eax
0x180019e1e  js      short loc_180019E32
0x180019e20  mov     rcx, rdi; this
0x180019e23  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180019e28  jmp     loc_180019D48
0x180019e2d  mov     ebx, 80020009h
0x180019e32  mov     rcx, rbp; pv
0x180019e35  call    cs:__imp_CoTaskMemFree
0x180019e3c  nop     dword ptr [rax+rax+00h]
0x180019e41  mov     eax, ebx
0x180019e43  mov     rcx, [rsp+2088h+var_48]
0x180019e4b  xor     rcx, rsp; StackCookie
0x180019e4e  call    __security_check_cookie
0x180019e53  add     rsp, 2050h
0x180019e5a  pop     r15
0x180019e5c  pop     r14
0x180019e5e  pop     r13
0x180019e60  pop     rdi
0x180019e61  pop     rsi
0x180019e62  pop     rbp
0x180019e63  pop     rbx
0x180019e64  retn
```
