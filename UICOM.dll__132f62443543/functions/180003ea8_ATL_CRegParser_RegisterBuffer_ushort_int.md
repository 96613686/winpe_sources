# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180003ea8`
- end: `0x180004032`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004038`

## callees

- `0x1800038f4`
- `0x180003a94`
- `0x180003ea8`
- `0x1800041fc`
- `0x180005f60`
- `0x180005ff0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180003f2d`
- `KERNEL32!lstrcmpiW` at `0x180003f2d`
- `USER32!CharNextW` at `0x180004017`
- `USER32!CharNextW` at `0x180004017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003f46`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
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
0x180003ea8  push    rbx
0x180003eaa  push    rbp
0x180003eab  push    rsi
0x180003eac  push    rdi
0x180003ead  push    r13
0x180003eaf  push    r14
0x180003eb1  push    r15
0x180003eb3  mov     eax, 2050h
0x180003eb8  call    _alloca_probe
0x180003ebd  sub     rsp, rax
0x180003ec0  mov     rax, cs:__security_cookie
0x180003ec7  xor     rax, rsp
0x180003eca  mov     [rsp+2088h+var_48], rax
0x180003ed2  mov     r15d, r8d
0x180003ed5  mov     [rsp+2088h+pv], 0
0x180003ede  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180003ee3  mov     rdi, rcx
0x180003ee6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180003eeb  mov     ebx, eax
0x180003eed  test    eax, eax
0x180003eef  js      short loc_180003F4E
0x180003ef1  mov     rbp, [rsp+2088h+pv]
0x180003ef6  xor     eax, eax
0x180003ef8  mov     [rdi], rbp
0x180003efb  cmp     ax, [rbp+0]
0x180003eff  jz      short loc_180003F43
0x180003f01  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180003f08  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003f0d  mov     rcx, rdi; this
0x180003f10  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003f15  mov     ebx, eax
0x180003f17  test    eax, eax
0x180003f19  js      short loc_180003F43
0x180003f1b  xor     ebx, ebx
0x180003f1d  movsxd  rsi, ebx
0x180003f20  lea     rcx, [rsp+2088h+String1]; lpString1
0x180003f25  add     rsi, rsi
0x180003f28  mov     rdx, [r13+rsi*8+0]; lpString2
0x180003f2d  call    cs:__imp_lstrcmpiW
0x180003f33  test    eax, eax
0x180003f35  jz      short loc_180003F70
0x180003f37  inc     ebx
0x180003f39  cmp     ebx, 0Eh
0x180003f3c  jb      short loc_180003F1D
0x180003f3e  mov     ebx, 80020009h
0x180003f43  mov     rcx, rbp; pv
0x180003f46  call    cs:__imp_CoTaskMemFree
0x180003f4c  mov     eax, ebx
0x180003f4e  mov     rcx, [rsp+2088h+var_48]
0x180003f56  xor     rcx, rsp; StackCookie
0x180003f59  call    __security_check_cookie
0x180003f5e  add     rsp, 2050h
0x180003f65  pop     r15
0x180003f67  pop     r14
0x180003f69  pop     r13
0x180003f6b  pop     rdi
0x180003f6c  pop     rsi
0x180003f6d  pop     rbp
0x180003f6e  pop     rbx
0x180003f6f  retn
0x180003f70  mov     rsi, [r13+rsi*8+8]
0x180003f75  test    rsi, rsi
0x180003f78  jz      short loc_180003F3E
0x180003f7a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003f7f  mov     rcx, rdi; this
0x180003f82  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003f87  mov     ebx, eax
0x180003f89  test    eax, eax
0x180003f8b  js      short loc_180003F43
0x180003f8d  mov     eax, 7Bh ; '{'
0x180003f92  cmp     ax, [rsp+2088h+String1]
0x180003f97  jnz     short loc_180003F3E
0x180003f99  mov     [rsp+2088h+var_2068], 0; int
0x180003fa1  mov     r8, rsi; HKEY
0x180003fa4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003fa9  mov     rcx, rdi; this
0x180003fac  test    r15d, r15d
0x180003faf  jz      short loc_180003FE5
0x180003fb1  mov     r14, [rdi]
0x180003fb4  mov     r9d, r15d; int
0x180003fb7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003fbc  mov     ebx, eax
0x180003fbe  test    eax, eax
0x180003fc0  jns     short loc_180003FF7
0x180003fc2  xor     r9d, r9d; int
0x180003fc5  mov     [rdi], r14
0x180003fc8  mov     r8, rsi; HKEY
0x180003fcb  mov     [rsp+2088h+var_2068], 0; int
0x180003fd3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180003fd8  mov     rcx, rdi; this
0x180003fdb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003fe0  jmp     loc_180003F43
0x180003fe5  xor     r9d, r9d; int
0x180003fe8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180003fed  mov     ebx, eax
0x180003fef  test    eax, eax
0x180003ff1  js      loc_180003F43
0x180003ff7  mov     r8, [rdi]
0x180003ffa  movzx   edx, word ptr [r8]
0x180003ffe  mov     ecx, edx
0x180004000  sub     ecx, 9
0x180004003  jz      short loc_180004014
0x180004005  sub     ecx, 1
0x180004008  jz      short loc_180004014
0x18000400a  sub     ecx, 3
0x18000400d  jz      short loc_180004014
0x18000400f  cmp     ecx, 13h
0x180004012  jnz     short loc_180004022
0x180004014  mov     rcx, r8; lpsz
0x180004017  call    cs:__imp_CharNextW
0x18000401d  mov     [rdi], rax
0x180004020  jmp     short loc_180003FF7
0x180004022  xor     eax, eax
0x180004024  cmp     ax, dx
0x180004027  jnz     loc_180003F08
0x18000402d  jmp     loc_180003F43
```
