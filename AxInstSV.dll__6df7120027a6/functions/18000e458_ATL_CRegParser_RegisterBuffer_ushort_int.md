# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000e458`
- end: `0x18000e5c5`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e660`

## callees

- `0x180001720`
- `0x18000d0c0`
- `0x18000d3ac`
- `0x18000e458`
- `0x18000e810`
- `0x18000fcd4`
- `0x1800142b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e59b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e59b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e4f4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e4f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000e458  push    rbx
0x18000e45a  push    rbp
0x18000e45b  push    rsi
0x18000e45c  push    rdi
0x18000e45d  push    r13
0x18000e45f  push    r14
0x18000e461  push    r15
0x18000e463  mov     eax, 2050h
0x18000e468  call    _alloca_probe
0x18000e46d  sub     rsp, rax
0x18000e470  mov     rax, cs:__security_cookie
0x18000e477  xor     rax, rsp
0x18000e47a  mov     [rsp+2088h+var_48], rax
0x18000e482  mov     r15d, r8d
0x18000e485  mov     [rsp+2088h+pv], 0
0x18000e48e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000e493  mov     rdi, rcx
0x18000e496  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000e49b  mov     ebx, eax
0x18000e49d  test    eax, eax
0x18000e49f  js      loc_18000E5A3
0x18000e4a5  mov     rbp, [rsp+2088h+pv]
0x18000e4aa  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000e4b1  mov     [rdi], rbp
0x18000e4b4  mov     rcx, [rdi]
0x18000e4b7  xor     eax, eax
0x18000e4b9  cmp     ax, [rcx]
0x18000e4bc  jz      loc_18000E598
0x18000e4c2  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000e4c7  mov     rcx, rdi; this
0x18000e4ca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e4cf  mov     ebx, eax
0x18000e4d1  test    eax, eax
0x18000e4d3  js      loc_18000E598
0x18000e4d9  xor     ebx, ebx
0x18000e4db  cmp     ebx, 0Eh
0x18000e4de  jnb     loc_18000E593
0x18000e4e4  movsxd  rsi, ebx
0x18000e4e7  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000e4ec  add     rsi, rsi
0x18000e4ef  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000e4f4  call    cs:__imp_lstrcmpiW
0x18000e4fa  test    eax, eax
0x18000e4fc  jz      short loc_18000E502
0x18000e4fe  inc     ebx
0x18000e500  jmp     short loc_18000E4DB
0x18000e502  mov     rsi, [r13+rsi*8+8]
0x18000e507  test    rsi, rsi
0x18000e50a  jz      loc_18000E593
0x18000e510  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000e515  mov     rcx, rdi; this
0x18000e518  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e51d  mov     ebx, eax
0x18000e51f  test    eax, eax
0x18000e521  js      short loc_18000E598
0x18000e523  mov     eax, 7Bh ; '{'
0x18000e528  cmp     ax, [rsp+2088h+String1]
0x18000e52d  jnz     short loc_18000E593
0x18000e52f  mov     [rsp+2088h+var_2068], 0; int
0x18000e537  mov     r8, rsi; HKEY
0x18000e53a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000e53f  mov     rcx, rdi; this
0x18000e542  test    r15d, r15d
0x18000e545  jz      short loc_18000E578
0x18000e547  mov     r14, [rdi]
0x18000e54a  mov     r9d, r15d; int
0x18000e54d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000e552  mov     ebx, eax
0x18000e554  test    eax, eax
0x18000e556  jns     short loc_18000E586
0x18000e558  xor     r9d, r9d; int
0x18000e55b  mov     [rdi], r14
0x18000e55e  mov     r8, rsi; HKEY
0x18000e561  mov     [rsp+2088h+var_2068], 0; int
0x18000e569  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000e56e  mov     rcx, rdi; this
0x18000e571  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000e576  jmp     short loc_18000E598
0x18000e578  xor     r9d, r9d; int
0x18000e57b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000e580  mov     ebx, eax
0x18000e582  test    eax, eax
0x18000e584  js      short loc_18000E598
0x18000e586  mov     rcx, rdi; this
0x18000e589  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000e58e  jmp     loc_18000E4B4
0x18000e593  mov     ebx, 80020009h
0x18000e598  mov     rcx, rbp; pv
0x18000e59b  call    cs:__imp_CoTaskMemFree
0x18000e5a1  mov     eax, ebx
0x18000e5a3  mov     rcx, [rsp+2088h+var_48]
0x18000e5ab  xor     rcx, rsp; StackCookie
0x18000e5ae  call    __security_check_cookie
0x18000e5b3  add     rsp, 2050h
0x18000e5ba  pop     r15
0x18000e5bc  pop     r14
0x18000e5be  pop     r13
0x18000e5c0  pop     rdi
0x18000e5c1  pop     rsi
0x18000e5c2  pop     rbp
0x18000e5c3  pop     rbx
0x18000e5c4  retn
```
