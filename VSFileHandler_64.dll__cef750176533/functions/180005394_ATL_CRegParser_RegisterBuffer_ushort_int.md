# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180005394`
- end: `0x180005537`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `419`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005538`

## callees

- `0x180003d1c`
- `0x180004a10`
- `0x180004bb4`
- `0x180005394`
- `0x180007700`
- `0x18001aff0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000541b`
- `KERNEL32!lstrcmpiW` at `0x18000541b`
- `USER32!CharNextW` at `0x18000551d`
- `USER32!CharNextW` at `0x18000551d`
- `ole32!CoTaskMemFree` at `0x18000543a`
- `ole32!CoTaskMemFree` at `0x18000543a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  unsigned __int64 v8; // rbx
  LPCWSTR *v9; // rsi
  HKEY v10; // rsi
  LPCWSTR v11; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  _mm_lfence();
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (LPCWSTR)pv;
    if ( *v7 )
    {
      do
      {
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        v8 = 0;
        v9 = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map;
        while ( lstrcmpiW(String1, *v9) )
        {
          ++v8;
          v9 += 2;
          if ( v8 >= 0xE )
            goto LABEL_7;
        }
        v10 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v8 + 1);
        if ( !v10 )
          goto LABEL_7;
        _mm_lfence();
        Token = ATL::CRegParser::NextToken(this, String1);
        if ( Token < 0 )
          break;
        _mm_lfence();
        if ( String1[0] != 123 )
        {
LABEL_7:
          Token = -2147352567;
          break;
        }
        if ( a3 )
        {
          v11 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, a3, 0);
          if ( Token < 0 )
          {
            _mm_lfence();
            *this = v11;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v10, 0, 0);
          if ( Token < 0 )
            break;
        }
        _mm_lfence();
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
0x180005394  mov     [rsp+arg_18], rbx
0x180005399  push    rbp
0x18000539a  push    rsi
0x18000539b  push    rdi
0x18000539c  push    r12
0x18000539e  push    r13
0x1800053a0  push    r14
0x1800053a2  push    r15
0x1800053a4  mov     eax, 2050h
0x1800053a9  call    _alloca_probe
0x1800053ae  sub     rsp, rax
0x1800053b1  mov     rax, cs:__security_cookie
0x1800053b8  xor     rax, rsp
0x1800053bb  mov     [rsp+2088h+var_48], rax
0x1800053c3  mov     r15d, r8d
0x1800053c6  xor     r12d, r12d
0x1800053c9  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800053ce  mov     [rsp+2088h+pv], r12
0x1800053d3  mov     rdi, rcx
0x1800053d6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800053db  mov     ebx, eax
0x1800053dd  lfence
0x1800053e0  test    eax, eax
0x1800053e2  js      short loc_180005442
0x1800053e4  mov     rbp, [rsp+2088h+pv]
0x1800053e9  mov     [rdi], rbp
0x1800053ec  cmp     r12w, [rbp+0]
0x1800053f1  jz      short loc_180005437
0x1800053f3  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800053fa  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800053ff  mov     rcx, rdi; this
0x180005402  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005407  mov     ebx, eax
0x180005409  test    eax, eax
0x18000540b  js      short loc_180005437
0x18000540d  mov     rbx, r12
0x180005410  mov     rsi, r13
0x180005413  mov     rdx, [rsi]; lpString2
0x180005416  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000541b  call    cs:__imp_lstrcmpiW
0x180005421  test    eax, eax
0x180005423  jz      short loc_18000546D
0x180005425  inc     rbx
0x180005428  add     rsi, 10h
0x18000542c  cmp     rbx, 0Eh
0x180005430  jb      short loc_180005413
0x180005432  mov     ebx, 80020009h
0x180005437  mov     rcx, rbp; pv
0x18000543a  call    cs:__imp_CoTaskMemFree
0x180005440  mov     eax, ebx
0x180005442  mov     rcx, [rsp+2088h+var_48]
0x18000544a  xor     rcx, rsp; StackCookie
0x18000544d  call    __security_check_cookie
0x180005452  mov     rbx, [rsp+2088h+arg_18]
0x18000545a  add     rsp, 2050h
0x180005461  pop     r15
0x180005463  pop     r14
0x180005465  pop     r13
0x180005467  pop     r12
0x180005469  pop     rdi
0x18000546a  pop     rsi
0x18000546b  pop     rbp
0x18000546c  retn
0x18000546d  add     rbx, rbx
0x180005470  mov     rsi, [r13+rbx*8+8]
0x180005475  test    rsi, rsi
0x180005478  jz      short loc_180005432
0x18000547a  lfence
0x18000547d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005482  mov     rcx, rdi; this
0x180005485  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000548a  mov     ebx, eax
0x18000548c  test    eax, eax
0x18000548e  js      short loc_180005437
0x180005490  lfence
0x180005493  mov     eax, 7Bh ; '{'
0x180005498  cmp     ax, [rsp+2088h+String1]
0x18000549d  jnz     short loc_180005432
0x18000549f  mov     [rsp+2088h+var_2068], r12d; int
0x1800054a4  mov     r8, rsi; HKEY
0x1800054a7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800054ac  mov     rcx, rdi; this
0x1800054af  test    r15d, r15d
0x1800054b2  jz      short loc_1800054E8
0x1800054b4  mov     r14, [rdi]
0x1800054b7  mov     r9d, r15d; int
0x1800054ba  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800054bf  mov     ebx, eax
0x1800054c1  test    eax, eax
0x1800054c3  jns     short loc_1800054FA
0x1800054c5  lfence
0x1800054c8  xor     r9d, r9d; int
0x1800054cb  mov     [rdi], r14
0x1800054ce  mov     r8, rsi; HKEY
0x1800054d1  mov     [rsp+2088h+var_2068], r12d; int
0x1800054d6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800054db  mov     rcx, rdi; this
0x1800054de  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800054e3  jmp     loc_180005437
0x1800054e8  xor     r9d, r9d; int
0x1800054eb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800054f0  mov     ebx, eax
0x1800054f2  test    eax, eax
0x1800054f4  js      loc_180005437
0x1800054fa  lfence
0x1800054fd  mov     r8, [rdi]
0x180005500  movzx   edx, word ptr [r8]
0x180005504  mov     ecx, edx
0x180005506  sub     ecx, 9
0x180005509  jz      short loc_18000551A
0x18000550b  sub     ecx, 1
0x18000550e  jz      short loc_18000551A
0x180005510  sub     ecx, 3
0x180005513  jz      short loc_18000551A
0x180005515  cmp     ecx, 13h
0x180005518  jnz     short loc_180005528
0x18000551a  mov     rcx, r8; lpsz
0x18000551d  call    cs:__imp_CharNextW
0x180005523  mov     [rdi], rax
0x180005526  jmp     short loc_1800054FD
0x180005528  cmp     r12w, dx
0x18000552c  jnz     loc_1800053FA
0x180005532  jmp     loc_180005437
```
