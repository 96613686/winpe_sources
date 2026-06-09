# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000917c`
- end: `0x180009306`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000930c`

## callees

- `0x180004180`
- `0x1800089bc`
- `0x180008b6c`
- `0x18000917c`
- `0x1800094ec`
- `0x1800300d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000921a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000921a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092eb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800092eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009201`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180009201`

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
0x18000917c  push    rbx
0x18000917e  push    rbp
0x18000917f  push    rsi
0x180009180  push    rdi
0x180009181  push    r13
0x180009183  push    r14
0x180009185  push    r15
0x180009187  mov     eax, 2050h
0x18000918c  call    _alloca_probe
0x180009191  sub     rsp, rax
0x180009194  mov     rax, cs:__security_cookie
0x18000919b  xor     rax, rsp
0x18000919e  mov     [rsp+2088h+var_48], rax
0x1800091a6  mov     r15d, r8d
0x1800091a9  mov     [rsp+2088h+pv], 0
0x1800091b2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800091b7  mov     rdi, rcx
0x1800091ba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800091bf  mov     ebx, eax
0x1800091c1  test    eax, eax
0x1800091c3  js      short loc_180009222
0x1800091c5  mov     rbp, [rsp+2088h+pv]
0x1800091ca  xor     eax, eax
0x1800091cc  mov     [rdi], rbp
0x1800091cf  cmp     ax, [rbp+0]
0x1800091d3  jz      short loc_180009217
0x1800091d5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800091dc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800091e1  mov     rcx, rdi; this
0x1800091e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091e9  mov     ebx, eax
0x1800091eb  test    eax, eax
0x1800091ed  js      short loc_180009217
0x1800091ef  xor     ebx, ebx
0x1800091f1  movsxd  rsi, ebx
0x1800091f4  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800091f9  add     rsi, rsi
0x1800091fc  mov     rdx, [r13+rsi*8+0]; lpString2
0x180009201  call    cs:__imp_lstrcmpiW
0x180009207  test    eax, eax
0x180009209  jz      short loc_180009244
0x18000920b  inc     ebx
0x18000920d  cmp     ebx, 0Eh
0x180009210  jb      short loc_1800091F1
0x180009212  mov     ebx, 80020009h
0x180009217  mov     rcx, rbp; pv
0x18000921a  call    cs:__imp_CoTaskMemFree
0x180009220  mov     eax, ebx
0x180009222  mov     rcx, [rsp+2088h+var_48]
0x18000922a  xor     rcx, rsp; StackCookie
0x18000922d  call    __security_check_cookie
0x180009232  add     rsp, 2050h
0x180009239  pop     r15
0x18000923b  pop     r14
0x18000923d  pop     r13
0x18000923f  pop     rdi
0x180009240  pop     rsi
0x180009241  pop     rbp
0x180009242  pop     rbx
0x180009243  retn
0x180009244  mov     rsi, [r13+rsi*8+8]
0x180009249  test    rsi, rsi
0x18000924c  jz      short loc_180009212
0x18000924e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009253  mov     rcx, rdi; this
0x180009256  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000925b  mov     ebx, eax
0x18000925d  test    eax, eax
0x18000925f  js      short loc_180009217
0x180009261  mov     eax, 7Bh ; '{'
0x180009266  cmp     ax, [rsp+2088h+String1]
0x18000926b  jnz     short loc_180009212
0x18000926d  mov     [rsp+2088h+var_2068], 0; int
0x180009275  mov     r8, rsi; HKEY
0x180009278  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000927d  mov     rcx, rdi; this
0x180009280  test    r15d, r15d
0x180009283  jz      short loc_1800092B9
0x180009285  mov     r14, [rdi]
0x180009288  mov     r9d, r15d; int
0x18000928b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009290  mov     ebx, eax
0x180009292  test    eax, eax
0x180009294  jns     short loc_1800092CB
0x180009296  xor     r9d, r9d; int
0x180009299  mov     [rdi], r14
0x18000929c  mov     r8, rsi; HKEY
0x18000929f  mov     [rsp+2088h+var_2068], 0; int
0x1800092a7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800092ac  mov     rcx, rdi; this
0x1800092af  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800092b4  jmp     loc_180009217
0x1800092b9  xor     r9d, r9d; int
0x1800092bc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800092c1  mov     ebx, eax
0x1800092c3  test    eax, eax
0x1800092c5  js      loc_180009217
0x1800092cb  mov     r8, [rdi]
0x1800092ce  movzx   edx, word ptr [r8]
0x1800092d2  mov     ecx, edx
0x1800092d4  sub     ecx, 9
0x1800092d7  jz      short loc_1800092E8
0x1800092d9  sub     ecx, 1
0x1800092dc  jz      short loc_1800092E8
0x1800092de  sub     ecx, 3
0x1800092e1  jz      short loc_1800092E8
0x1800092e3  cmp     ecx, 13h
0x1800092e6  jnz     short loc_1800092F6
0x1800092e8  mov     rcx, r8; lpsz
0x1800092eb  call    cs:__imp_CharNextW
0x1800092f1  mov     [rdi], rax
0x1800092f4  jmp     short loc_1800092CB
0x1800092f6  xor     eax, eax
0x1800092f8  cmp     ax, dx
0x1800092fb  jnz     loc_1800091DC
0x180009301  jmp     loc_180009217
```
