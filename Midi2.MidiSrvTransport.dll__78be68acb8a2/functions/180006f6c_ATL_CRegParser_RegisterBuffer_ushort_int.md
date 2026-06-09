# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180006f6c`
- end: `0x1800070f6`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800070fc`

## callees

- `0x180002470`
- `0x1800067ac`
- `0x18000695c`
- `0x180006f6c`
- `0x1800072dc`
- `0x180014020`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000700a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000700a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800070db`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800070db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ff1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006ff1`

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
0x180006f6c  push    rbx
0x180006f6e  push    rbp
0x180006f6f  push    rsi
0x180006f70  push    rdi
0x180006f71  push    r13
0x180006f73  push    r14
0x180006f75  push    r15
0x180006f77  mov     eax, 2050h
0x180006f7c  call    _alloca_probe
0x180006f81  sub     rsp, rax
0x180006f84  mov     rax, cs:__security_cookie
0x180006f8b  xor     rax, rsp
0x180006f8e  mov     [rsp+2088h+var_48], rax
0x180006f96  mov     r15d, r8d
0x180006f99  mov     [rsp+2088h+pv], 0
0x180006fa2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180006fa7  mov     rdi, rcx
0x180006faa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180006faf  mov     ebx, eax
0x180006fb1  test    eax, eax
0x180006fb3  js      short loc_180007012
0x180006fb5  mov     rbp, [rsp+2088h+pv]
0x180006fba  xor     eax, eax
0x180006fbc  mov     [rdi], rbp
0x180006fbf  cmp     ax, [rbp+0]
0x180006fc3  jz      short loc_180007007
0x180006fc5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180006fcc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006fd1  mov     rcx, rdi; this
0x180006fd4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006fd9  mov     ebx, eax
0x180006fdb  test    eax, eax
0x180006fdd  js      short loc_180007007
0x180006fdf  xor     ebx, ebx
0x180006fe1  movsxd  rsi, ebx
0x180006fe4  lea     rcx, [rsp+2088h+String1]; lpString1
0x180006fe9  add     rsi, rsi
0x180006fec  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006ff1  call    cs:__imp_lstrcmpiW
0x180006ff7  test    eax, eax
0x180006ff9  jz      short loc_180007034
0x180006ffb  inc     ebx
0x180006ffd  cmp     ebx, 0Eh
0x180007000  jb      short loc_180006FE1
0x180007002  mov     ebx, 80020009h
0x180007007  mov     rcx, rbp; pv
0x18000700a  call    cs:__imp_CoTaskMemFree
0x180007010  mov     eax, ebx
0x180007012  mov     rcx, [rsp+2088h+var_48]
0x18000701a  xor     rcx, rsp; StackCookie
0x18000701d  call    __security_check_cookie
0x180007022  add     rsp, 2050h
0x180007029  pop     r15
0x18000702b  pop     r14
0x18000702d  pop     r13
0x18000702f  pop     rdi
0x180007030  pop     rsi
0x180007031  pop     rbp
0x180007032  pop     rbx
0x180007033  retn
0x180007034  mov     rsi, [r13+rsi*8+8]
0x180007039  test    rsi, rsi
0x18000703c  jz      short loc_180007002
0x18000703e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007043  mov     rcx, rdi; this
0x180007046  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000704b  mov     ebx, eax
0x18000704d  test    eax, eax
0x18000704f  js      short loc_180007007
0x180007051  mov     eax, 7Bh ; '{'
0x180007056  cmp     ax, [rsp+2088h+String1]
0x18000705b  jnz     short loc_180007002
0x18000705d  mov     [rsp+2088h+var_2068], 0; int
0x180007065  mov     r8, rsi; HKEY
0x180007068  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000706d  mov     rcx, rdi; this
0x180007070  test    r15d, r15d
0x180007073  jz      short loc_1800070A9
0x180007075  mov     r14, [rdi]
0x180007078  mov     r9d, r15d; int
0x18000707b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007080  mov     ebx, eax
0x180007082  test    eax, eax
0x180007084  jns     short loc_1800070BB
0x180007086  xor     r9d, r9d; int
0x180007089  mov     [rdi], r14
0x18000708c  mov     r8, rsi; HKEY
0x18000708f  mov     [rsp+2088h+var_2068], 0; int
0x180007097  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000709c  mov     rcx, rdi; this
0x18000709f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800070a4  jmp     loc_180007007
0x1800070a9  xor     r9d, r9d; int
0x1800070ac  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800070b1  mov     ebx, eax
0x1800070b3  test    eax, eax
0x1800070b5  js      loc_180007007
0x1800070bb  mov     r8, [rdi]
0x1800070be  movzx   edx, word ptr [r8]
0x1800070c2  mov     ecx, edx
0x1800070c4  sub     ecx, 9
0x1800070c7  jz      short loc_1800070D8
0x1800070c9  sub     ecx, 1
0x1800070cc  jz      short loc_1800070D8
0x1800070ce  sub     ecx, 3
0x1800070d1  jz      short loc_1800070D8
0x1800070d3  cmp     ecx, 13h
0x1800070d6  jnz     short loc_1800070E6
0x1800070d8  mov     rcx, r8; lpsz
0x1800070db  call    cs:__imp_CharNextW
0x1800070e1  mov     [rdi], rax
0x1800070e4  jmp     short loc_1800070BB
0x1800070e6  xor     eax, eax
0x1800070e8  cmp     ax, dx
0x1800070eb  jnz     loc_180006FCC
0x1800070f1  jmp     loc_180007007
```
