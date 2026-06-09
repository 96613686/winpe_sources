# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180018b90`
- end: `0x180018d15`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `389`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018d1c`

## callees

- `0x180018170`
- `0x180018330`
- `0x180018b90`
- `0x180018fb0`
- `0x180019b10`
- `0x18002fb50`
- `0x18002fc10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cdb`
- `KERNEL32!lstrcmpiW` at `0x180018c2e`
- `KERNEL32!lstrcmpiW` at `0x180018c2e`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rbx
  LPCWSTR *i; // r14
  HKEY v11; // rsi
  __int64 v12; // r14
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
      v8 = 0;
      v9 = 0;
      for ( i = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map; ; i += 2 )
      {
        if ( v8 >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, *i) )
          break;
        ++v8;
        ++v9;
      }
      v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v9 + 1);
      if ( !v11 )
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
        v12 = *(_QWORD *)this;
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, a3, 0);
        if ( Token < 0 )
        {
          *(_QWORD *)this = v12;
          ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
          break;
        }
      }
      else
      {
        Token = ATL::CRegParser::RegisterSubkeys(this, String1, v11, 0, 0);
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
0x180018b90  mov     [rsp+arg_18], rbx
0x180018b95  push    rbp
0x180018b96  push    rsi
0x180018b97  push    rdi
0x180018b98  push    r12
0x180018b9a  push    r13
0x180018b9c  push    r14
0x180018b9e  push    r15
0x180018ba0  mov     eax, 2050h
0x180018ba5  call    _alloca_probe
0x180018baa  sub     rsp, rax
0x180018bad  mov     rax, cs:__security_cookie
0x180018bb4  xor     rax, rsp
0x180018bb7  mov     [rsp+2088h+var_48], rax
0x180018bbf  mov     r15d, r8d
0x180018bc2  xor     r12d, r12d
0x180018bc5  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180018bca  mov     [rsp+2088h+pv], r12
0x180018bcf  mov     rdi, rcx
0x180018bd2  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180018bd7  mov     ebx, eax
0x180018bd9  test    eax, eax
0x180018bdb  js      loc_180018CE9
0x180018be1  mov     rbp, [rsp+2088h+pv]
0x180018be6  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180018bed  mov     [rdi], rbp
0x180018bf0  mov     rax, [rdi]
0x180018bf3  cmp     r12w, [rax]
0x180018bf7  jz      loc_180018CD8
0x180018bfd  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180018c02  mov     rcx, rdi; this
0x180018c05  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018c0a  mov     ebx, eax
0x180018c0c  test    eax, eax
0x180018c0e  js      loc_180018CD8
0x180018c14  mov     esi, r12d
0x180018c17  mov     rbx, r12
0x180018c1a  mov     r14, r13
0x180018c1d  cmp     esi, 0Eh
0x180018c20  jnb     loc_180018CD3
0x180018c26  mov     rdx, [r14]; lpString2
0x180018c29  lea     rcx, [rsp+2088h+String1]; lpString1
0x180018c2e  call    cs:__imp_lstrcmpiW
0x180018c35  nop     dword ptr [rax+rax+00h]
0x180018c3a  test    eax, eax
0x180018c3c  jz      short loc_180018C49
0x180018c3e  inc     esi
0x180018c40  inc     rbx
0x180018c43  add     r14, 10h
0x180018c47  jmp     short loc_180018C1D
0x180018c49  add     rbx, rbx
0x180018c4c  mov     rsi, [r13+rbx*8+8]
0x180018c51  test    rsi, rsi
0x180018c54  jz      short loc_180018CD3
0x180018c56  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180018c5b  mov     rcx, rdi; this
0x180018c5e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180018c63  mov     ebx, eax
0x180018c65  test    eax, eax
0x180018c67  js      short loc_180018CD8
0x180018c69  mov     eax, 7Bh ; '{'
0x180018c6e  cmp     ax, [rsp+2088h+String1]
0x180018c73  jnz     short loc_180018CD3
0x180018c75  mov     [rsp+2088h+var_2068], r12d; int
0x180018c7a  mov     r8, rsi; HKEY
0x180018c7d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180018c82  mov     rcx, rdi; this
0x180018c85  test    r15d, r15d
0x180018c88  jz      short loc_180018CB8
0x180018c8a  mov     r14, [rdi]
0x180018c8d  mov     r9d, r15d; int
0x180018c90  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180018c95  mov     ebx, eax
0x180018c97  test    eax, eax
0x180018c99  jns     short loc_180018CC6
0x180018c9b  xor     r9d, r9d; int
0x180018c9e  mov     [rdi], r14
0x180018ca1  mov     r8, rsi; HKEY
0x180018ca4  mov     [rsp+2088h+var_2068], r12d; int
0x180018ca9  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180018cae  mov     rcx, rdi; this
0x180018cb1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180018cb6  jmp     short loc_180018CD8
0x180018cb8  xor     r9d, r9d; int
0x180018cbb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180018cc0  mov     ebx, eax
0x180018cc2  test    eax, eax
0x180018cc4  js      short loc_180018CD8
0x180018cc6  mov     rcx, rdi; this
0x180018cc9  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180018cce  jmp     loc_180018BF0
0x180018cd3  mov     ebx, 80020009h
0x180018cd8  mov     rcx, rbp; pv
0x180018cdb  call    cs:__imp_CoTaskMemFree
0x180018ce2  nop     dword ptr [rax+rax+00h]
0x180018ce7  mov     eax, ebx
0x180018ce9  mov     rcx, [rsp+2088h+var_48]
0x180018cf1  xor     rcx, rsp; StackCookie
0x180018cf4  call    __security_check_cookie
0x180018cf9  mov     rbx, [rsp+2088h+arg_18]
0x180018d01  add     rsp, 2050h
0x180018d08  pop     r15
0x180018d0a  pop     r14
0x180018d0c  pop     r13
0x180018d0e  pop     r12
0x180018d10  pop     rdi
0x180018d11  pop     rsi
0x180018d12  pop     rbp
0x180018d13  retn
```
