# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180005454`
- end: `0x1800055ec`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800055ec`

## callees

- `0x180003984`
- `0x1800047fc`
- `0x1800049b8`
- `0x180005454`
- `0x18000cdb0`
- `0x18000e430`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1800054db`
- `KERNEL32!lstrcmpiW` at `0x1800054db`
- `ole32!CoTaskMemFree` at `0x1800054fb`
- `ole32!CoTaskMemFree` at `0x1800054fb`
- `USER32!CharNextW` at `0x1800055d2`
- `USER32!CharNextW` at `0x1800055d2`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(LPCWSTR *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  unsigned int v8; // esi
  __int64 v9; // rbx
  LPCWSTR *v10; // r14
  HKEY v11; // rsi
  LPCWSTR v12; // r14
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
        v9 = 0;
        v10 = (LPCWSTR *)&`ATL::CRegParser::HKeyFromString'::`2'::map;
        while ( lstrcmpiW(String1, *v10) )
        {
          ++v8;
          ++v9;
          v10 += 2;
          if ( v8 >= 0xE )
            goto LABEL_7;
        }
        v11 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * v9 + 1);
        if ( !v11 )
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
          v12 = *this;
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v11, a3, 0);
          if ( Token < 0 )
          {
            *this = v12;
            ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v11, 0, 0);
            break;
          }
        }
        else
        {
          Token = ATL::CRegParser::RegisterSubkeys((ATL::CRegParser *)this, String1, v11, 0, 0);
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
0x180005454  mov     [rsp+arg_18], rbx
0x180005459  push    rbp
0x18000545a  push    rsi
0x18000545b  push    rdi
0x18000545c  push    r12
0x18000545e  push    r13
0x180005460  push    r14
0x180005462  push    r15
0x180005464  mov     eax, 2050h
0x180005469  call    _alloca_probe
0x18000546e  sub     rsp, rax
0x180005471  mov     rax, cs:__security_cookie
0x180005478  xor     rax, rsp
0x18000547b  mov     [rsp+2088h+var_48], rax
0x180005483  mov     r15d, r8d
0x180005486  xor     r12d, r12d
0x180005489  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000548e  mov     [rsp+2088h+pv], r12
0x180005493  mov     rdi, rcx
0x180005496  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000549b  mov     ebx, eax
0x18000549d  test    eax, eax
0x18000549f  js      short loc_180005503
0x1800054a1  mov     rbp, [rsp+2088h+pv]
0x1800054a6  mov     [rdi], rbp
0x1800054a9  cmp     r12w, [rbp+0]
0x1800054ae  jz      short loc_1800054F8
0x1800054b0  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800054b7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800054bc  mov     rcx, rdi; this
0x1800054bf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800054c4  mov     ebx, eax
0x1800054c6  test    eax, eax
0x1800054c8  js      short loc_1800054F8
0x1800054ca  mov     esi, r12d
0x1800054cd  mov     rbx, r12
0x1800054d0  mov     r14, r13
0x1800054d3  mov     rdx, [r14]; lpString2
0x1800054d6  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800054db  call    cs:__imp_lstrcmpiW
0x1800054e1  test    eax, eax
0x1800054e3  jz      short loc_18000552E
0x1800054e5  inc     esi
0x1800054e7  inc     rbx
0x1800054ea  add     r14, 10h
0x1800054ee  cmp     esi, 0Eh
0x1800054f1  jb      short loc_1800054D3
0x1800054f3  mov     ebx, 80020009h
0x1800054f8  mov     rcx, rbp; pv
0x1800054fb  call    cs:__imp_CoTaskMemFree
0x180005501  mov     eax, ebx
0x180005503  mov     rcx, [rsp+2088h+var_48]
0x18000550b  xor     rcx, rsp; StackCookie
0x18000550e  call    __security_check_cookie
0x180005513  mov     rbx, [rsp+2088h+arg_18]
0x18000551b  add     rsp, 2050h
0x180005522  pop     r15
0x180005524  pop     r14
0x180005526  pop     r13
0x180005528  pop     r12
0x18000552a  pop     rdi
0x18000552b  pop     rsi
0x18000552c  pop     rbp
0x18000552d  retn
0x18000552e  add     rbx, rbx
0x180005531  mov     rsi, [r13+rbx*8+8]
0x180005536  test    rsi, rsi
0x180005539  jz      short loc_1800054F3
0x18000553b  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005540  mov     rcx, rdi; this
0x180005543  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005548  mov     ebx, eax
0x18000554a  test    eax, eax
0x18000554c  js      short loc_1800054F8
0x18000554e  mov     eax, 7Bh ; '{'
0x180005553  cmp     ax, [rsp+2088h+String1]
0x180005558  jnz     short loc_1800054F3
0x18000555a  mov     [rsp+2088h+var_2068], r12d; int
0x18000555f  mov     r8, rsi; HKEY
0x180005562  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005567  mov     rcx, rdi; this
0x18000556a  test    r15d, r15d
0x18000556d  jz      short loc_1800055A0
0x18000556f  mov     r14, [rdi]
0x180005572  mov     r9d, r15d; int
0x180005575  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000557a  mov     ebx, eax
0x18000557c  test    eax, eax
0x18000557e  jns     short loc_1800055B2
0x180005580  xor     r9d, r9d; int
0x180005583  mov     [rdi], r14
0x180005586  mov     r8, rsi; HKEY
0x180005589  mov     [rsp+2088h+var_2068], r12d; int
0x18000558e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005593  mov     rcx, rdi; this
0x180005596  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000559b  jmp     loc_1800054F8
0x1800055a0  xor     r9d, r9d; int
0x1800055a3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800055a8  mov     ebx, eax
0x1800055aa  test    eax, eax
0x1800055ac  js      loc_1800054F8
0x1800055b2  mov     r8, [rdi]
0x1800055b5  movzx   edx, word ptr [r8]
0x1800055b9  mov     ecx, edx
0x1800055bb  sub     ecx, 9
0x1800055be  jz      short loc_1800055CF
0x1800055c0  sub     ecx, 1
0x1800055c3  jz      short loc_1800055CF
0x1800055c5  sub     ecx, 3
0x1800055c8  jz      short loc_1800055CF
0x1800055ca  cmp     ecx, 13h
0x1800055cd  jnz     short loc_1800055DD
0x1800055cf  mov     rcx, r8; lpsz
0x1800055d2  call    cs:__imp_CharNextW
0x1800055d8  mov     [rdi], rax
0x1800055db  jmp     short loc_1800055B2
0x1800055dd  cmp     r12w, dx
0x1800055e1  jz      loc_1800054F8
0x1800055e7  jmp     loc_1800054B7
```
