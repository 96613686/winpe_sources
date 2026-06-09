# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180005d08`
- end: `0x180005e92`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e98`

## callees

- `0x180001550`
- `0x180005630`
- `0x1800057d0`
- `0x180005d08`
- `0x18000607c`
- `0x180009f10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005da6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005e77`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005e77`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005d8d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005d8d`

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
0x180005d08  push    rbx
0x180005d0a  push    rbp
0x180005d0b  push    rsi
0x180005d0c  push    rdi
0x180005d0d  push    r13
0x180005d0f  push    r14
0x180005d11  push    r15
0x180005d13  mov     eax, 2050h
0x180005d18  call    _alloca_probe
0x180005d1d  sub     rsp, rax
0x180005d20  mov     rax, cs:__security_cookie
0x180005d27  xor     rax, rsp
0x180005d2a  mov     [rsp+2088h+var_48], rax
0x180005d32  mov     r15d, r8d
0x180005d35  mov     [rsp+2088h+pv], 0
0x180005d3e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005d43  mov     rdi, rcx
0x180005d46  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180005d4b  mov     ebx, eax
0x180005d4d  test    eax, eax
0x180005d4f  js      short loc_180005DAE
0x180005d51  mov     rbp, [rsp+2088h+pv]
0x180005d56  xor     eax, eax
0x180005d58  mov     [rdi], rbp
0x180005d5b  cmp     ax, [rbp+0]
0x180005d5f  jz      short loc_180005DA3
0x180005d61  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005d68  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005d6d  mov     rcx, rdi; this
0x180005d70  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005d75  mov     ebx, eax
0x180005d77  test    eax, eax
0x180005d79  js      short loc_180005DA3
0x180005d7b  xor     ebx, ebx
0x180005d7d  movsxd  rsi, ebx
0x180005d80  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005d85  add     rsi, rsi
0x180005d88  mov     rdx, [r13+rsi*8+0]; lpString2
0x180005d8d  call    cs:__imp_lstrcmpiW
0x180005d93  test    eax, eax
0x180005d95  jz      short loc_180005DD0
0x180005d97  inc     ebx
0x180005d99  cmp     ebx, 0Eh
0x180005d9c  jb      short loc_180005D7D
0x180005d9e  mov     ebx, 80020009h
0x180005da3  mov     rcx, rbp; pv
0x180005da6  call    cs:__imp_CoTaskMemFree
0x180005dac  mov     eax, ebx
0x180005dae  mov     rcx, [rsp+2088h+var_48]
0x180005db6  xor     rcx, rsp; StackCookie
0x180005db9  call    __security_check_cookie
0x180005dbe  add     rsp, 2050h
0x180005dc5  pop     r15
0x180005dc7  pop     r14
0x180005dc9  pop     r13
0x180005dcb  pop     rdi
0x180005dcc  pop     rsi
0x180005dcd  pop     rbp
0x180005dce  pop     rbx
0x180005dcf  retn
0x180005dd0  mov     rsi, [r13+rsi*8+8]
0x180005dd5  test    rsi, rsi
0x180005dd8  jz      short loc_180005D9E
0x180005dda  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005ddf  mov     rcx, rdi; this
0x180005de2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005de7  mov     ebx, eax
0x180005de9  test    eax, eax
0x180005deb  js      short loc_180005DA3
0x180005ded  mov     eax, 7Bh ; '{'
0x180005df2  cmp     ax, [rsp+2088h+String1]
0x180005df7  jnz     short loc_180005D9E
0x180005df9  mov     [rsp+2088h+var_2068], 0; int
0x180005e01  mov     r8, rsi; HKEY
0x180005e04  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005e09  mov     rcx, rdi; this
0x180005e0c  test    r15d, r15d
0x180005e0f  jz      short loc_180005E45
0x180005e11  mov     r14, [rdi]
0x180005e14  mov     r9d, r15d; int
0x180005e17  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005e1c  mov     ebx, eax
0x180005e1e  test    eax, eax
0x180005e20  jns     short loc_180005E57
0x180005e22  xor     r9d, r9d; int
0x180005e25  mov     [rdi], r14
0x180005e28  mov     r8, rsi; HKEY
0x180005e2b  mov     [rsp+2088h+var_2068], 0; int
0x180005e33  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005e38  mov     rcx, rdi; this
0x180005e3b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005e40  jmp     loc_180005DA3
0x180005e45  xor     r9d, r9d; int
0x180005e48  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005e4d  mov     ebx, eax
0x180005e4f  test    eax, eax
0x180005e51  js      loc_180005DA3
0x180005e57  mov     r8, [rdi]
0x180005e5a  movzx   edx, word ptr [r8]
0x180005e5e  mov     ecx, edx
0x180005e60  sub     ecx, 9
0x180005e63  jz      short loc_180005E74
0x180005e65  sub     ecx, 1
0x180005e68  jz      short loc_180005E74
0x180005e6a  sub     ecx, 3
0x180005e6d  jz      short loc_180005E74
0x180005e6f  cmp     ecx, 13h
0x180005e72  jnz     short loc_180005E82
0x180005e74  mov     rcx, r8; lpsz
0x180005e77  call    cs:__imp_CharNextW
0x180005e7d  mov     [rdi], rax
0x180005e80  jmp     short loc_180005E57
0x180005e82  xor     eax, eax
0x180005e84  cmp     ax, dx
0x180005e87  jnz     loc_180005D68
0x180005e8d  jmp     loc_180005DA3
```
