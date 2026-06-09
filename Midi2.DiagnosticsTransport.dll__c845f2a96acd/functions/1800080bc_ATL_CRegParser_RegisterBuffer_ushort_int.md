# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800080bc`
- end: `0x180008246`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000824c`

## callees

- `0x1800033d0`
- `0x1800078fc`
- `0x180007aac`
- `0x1800080bc`
- `0x18000842c`
- `0x180011f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000815a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000815a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000822b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000822b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008141`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008141`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
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
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
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
        Token = ATL::CRegParser::NextToken(this, String1);
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
        while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
          *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
      }
      while ( **(_WORD **)this );
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x1800080bc  push    rbx
0x1800080be  push    rbp
0x1800080bf  push    rsi
0x1800080c0  push    rdi
0x1800080c1  push    r13
0x1800080c3  push    r14
0x1800080c5  push    r15
0x1800080c7  mov     eax, 2050h
0x1800080cc  call    _alloca_probe
0x1800080d1  sub     rsp, rax
0x1800080d4  mov     rax, cs:__security_cookie
0x1800080db  xor     rax, rsp
0x1800080de  mov     [rsp+2088h+var_48], rax
0x1800080e6  mov     r15d, r8d
0x1800080e9  mov     [rsp+2088h+pv], 0
0x1800080f2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800080f7  mov     rdi, rcx
0x1800080fa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800080ff  mov     ebx, eax
0x180008101  test    eax, eax
0x180008103  js      short loc_180008162
0x180008105  mov     rbp, [rsp+2088h+pv]
0x18000810a  xor     eax, eax
0x18000810c  mov     [rdi], rbp
0x18000810f  cmp     ax, [rbp+0]
0x180008113  jz      short loc_180008157
0x180008115  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000811c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008121  mov     rcx, rdi; this
0x180008124  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008129  mov     ebx, eax
0x18000812b  test    eax, eax
0x18000812d  js      short loc_180008157
0x18000812f  xor     ebx, ebx
0x180008131  movsxd  rsi, ebx
0x180008134  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008139  add     rsi, rsi
0x18000813c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008141  call    cs:__imp_lstrcmpiW
0x180008147  test    eax, eax
0x180008149  jz      short loc_180008184
0x18000814b  inc     ebx
0x18000814d  cmp     ebx, 0Eh
0x180008150  jb      short loc_180008131
0x180008152  mov     ebx, 80020009h
0x180008157  mov     rcx, rbp; pv
0x18000815a  call    cs:__imp_CoTaskMemFree
0x180008160  mov     eax, ebx
0x180008162  mov     rcx, [rsp+2088h+var_48]
0x18000816a  xor     rcx, rsp; StackCookie
0x18000816d  call    __security_check_cookie
0x180008172  add     rsp, 2050h
0x180008179  pop     r15
0x18000817b  pop     r14
0x18000817d  pop     r13
0x18000817f  pop     rdi
0x180008180  pop     rsi
0x180008181  pop     rbp
0x180008182  pop     rbx
0x180008183  retn
0x180008184  mov     rsi, [r13+rsi*8+8]
0x180008189  test    rsi, rsi
0x18000818c  jz      short loc_180008152
0x18000818e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008193  mov     rcx, rdi; this
0x180008196  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000819b  mov     ebx, eax
0x18000819d  test    eax, eax
0x18000819f  js      short loc_180008157
0x1800081a1  mov     eax, 7Bh ; '{'
0x1800081a6  cmp     ax, [rsp+2088h+String1]
0x1800081ab  jnz     short loc_180008152
0x1800081ad  mov     [rsp+2088h+var_2068], 0; int
0x1800081b5  mov     r8, rsi; HKEY
0x1800081b8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800081bd  mov     rcx, rdi; this
0x1800081c0  test    r15d, r15d
0x1800081c3  jz      short loc_1800081F9
0x1800081c5  mov     r14, [rdi]
0x1800081c8  mov     r9d, r15d; int
0x1800081cb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800081d0  mov     ebx, eax
0x1800081d2  test    eax, eax
0x1800081d4  jns     short loc_18000820B
0x1800081d6  xor     r9d, r9d; int
0x1800081d9  mov     [rdi], r14
0x1800081dc  mov     r8, rsi; HKEY
0x1800081df  mov     [rsp+2088h+var_2068], 0; int
0x1800081e7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800081ec  mov     rcx, rdi; this
0x1800081ef  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800081f4  jmp     loc_180008157
0x1800081f9  xor     r9d, r9d; int
0x1800081fc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008201  mov     ebx, eax
0x180008203  test    eax, eax
0x180008205  js      loc_180008157
0x18000820b  mov     r8, [rdi]
0x18000820e  movzx   edx, word ptr [r8]
0x180008212  mov     ecx, edx
0x180008214  sub     ecx, 9
0x180008217  jz      short loc_180008228
0x180008219  sub     ecx, 1
0x18000821c  jz      short loc_180008228
0x18000821e  sub     ecx, 3
0x180008221  jz      short loc_180008228
0x180008223  cmp     ecx, 13h
0x180008226  jnz     short loc_180008236
0x180008228  mov     rcx, r8; lpsz
0x18000822b  call    cs:__imp_CharNextW
0x180008231  mov     [rdi], rax
0x180008234  jmp     short loc_18000820B
0x180008236  xor     eax, eax
0x180008238  cmp     ax, dx
0x18000823b  jnz     loc_18000811C
0x180008241  jmp     loc_180008157
```
