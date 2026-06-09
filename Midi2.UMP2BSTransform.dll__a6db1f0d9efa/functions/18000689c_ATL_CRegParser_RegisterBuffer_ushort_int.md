# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000689c`
- end: `0x180006a26`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006a2c`

## callees

- `0x180001ef0`
- `0x1800060dc`
- `0x18000628c`
- `0x18000689c`
- `0x180006c0c`
- `0x18000e890`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000693a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000693a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a0b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006a0b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006921`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006921`

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
0x18000689c  push    rbx
0x18000689e  push    rbp
0x18000689f  push    rsi
0x1800068a0  push    rdi
0x1800068a1  push    r13
0x1800068a3  push    r14
0x1800068a5  push    r15
0x1800068a7  mov     eax, 2050h
0x1800068ac  call    _alloca_probe
0x1800068b1  sub     rsp, rax
0x1800068b4  mov     rax, cs:__security_cookie
0x1800068bb  xor     rax, rsp
0x1800068be  mov     [rsp+2088h+var_48], rax
0x1800068c6  mov     r15d, r8d
0x1800068c9  mov     [rsp+2088h+pv], 0
0x1800068d2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800068d7  mov     rdi, rcx
0x1800068da  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800068df  mov     ebx, eax
0x1800068e1  test    eax, eax
0x1800068e3  js      short loc_180006942
0x1800068e5  mov     rbp, [rsp+2088h+pv]
0x1800068ea  xor     eax, eax
0x1800068ec  mov     [rdi], rbp
0x1800068ef  cmp     ax, [rbp+0]
0x1800068f3  jz      short loc_180006937
0x1800068f5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800068fc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006901  mov     rcx, rdi; this
0x180006904  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006909  mov     ebx, eax
0x18000690b  test    eax, eax
0x18000690d  js      short loc_180006937
0x18000690f  xor     ebx, ebx
0x180006911  movsxd  rsi, ebx
0x180006914  lea     rcx, [rsp+2088h+String1]; lpString1
0x180006919  add     rsi, rsi
0x18000691c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006921  call    cs:__imp_lstrcmpiW
0x180006927  test    eax, eax
0x180006929  jz      short loc_180006964
0x18000692b  inc     ebx
0x18000692d  cmp     ebx, 0Eh
0x180006930  jb      short loc_180006911
0x180006932  mov     ebx, 80020009h
0x180006937  mov     rcx, rbp; pv
0x18000693a  call    cs:__imp_CoTaskMemFree
0x180006940  mov     eax, ebx
0x180006942  mov     rcx, [rsp+2088h+var_48]
0x18000694a  xor     rcx, rsp; StackCookie
0x18000694d  call    __security_check_cookie
0x180006952  add     rsp, 2050h
0x180006959  pop     r15
0x18000695b  pop     r14
0x18000695d  pop     r13
0x18000695f  pop     rdi
0x180006960  pop     rsi
0x180006961  pop     rbp
0x180006962  pop     rbx
0x180006963  retn
0x180006964  mov     rsi, [r13+rsi*8+8]
0x180006969  test    rsi, rsi
0x18000696c  jz      short loc_180006932
0x18000696e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006973  mov     rcx, rdi; this
0x180006976  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000697b  mov     ebx, eax
0x18000697d  test    eax, eax
0x18000697f  js      short loc_180006937
0x180006981  mov     eax, 7Bh ; '{'
0x180006986  cmp     ax, [rsp+2088h+String1]
0x18000698b  jnz     short loc_180006932
0x18000698d  mov     [rsp+2088h+var_2068], 0; int
0x180006995  mov     r8, rsi; HKEY
0x180006998  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000699d  mov     rcx, rdi; this
0x1800069a0  test    r15d, r15d
0x1800069a3  jz      short loc_1800069D9
0x1800069a5  mov     r14, [rdi]
0x1800069a8  mov     r9d, r15d; int
0x1800069ab  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800069b0  mov     ebx, eax
0x1800069b2  test    eax, eax
0x1800069b4  jns     short loc_1800069EB
0x1800069b6  xor     r9d, r9d; int
0x1800069b9  mov     [rdi], r14
0x1800069bc  mov     r8, rsi; HKEY
0x1800069bf  mov     [rsp+2088h+var_2068], 0; int
0x1800069c7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800069cc  mov     rcx, rdi; this
0x1800069cf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800069d4  jmp     loc_180006937
0x1800069d9  xor     r9d, r9d; int
0x1800069dc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800069e1  mov     ebx, eax
0x1800069e3  test    eax, eax
0x1800069e5  js      loc_180006937
0x1800069eb  mov     r8, [rdi]
0x1800069ee  movzx   edx, word ptr [r8]
0x1800069f2  mov     ecx, edx
0x1800069f4  sub     ecx, 9
0x1800069f7  jz      short loc_180006A08
0x1800069f9  sub     ecx, 1
0x1800069fc  jz      short loc_180006A08
0x1800069fe  sub     ecx, 3
0x180006a01  jz      short loc_180006A08
0x180006a03  cmp     ecx, 13h
0x180006a06  jnz     short loc_180006A16
0x180006a08  mov     rcx, r8; lpsz
0x180006a0b  call    cs:__imp_CharNextW
0x180006a11  mov     [rdi], rax
0x180006a14  jmp     short loc_1800069EB
0x180006a16  xor     eax, eax
0x180006a18  cmp     ax, dx
0x180006a1b  jnz     loc_1800068FC
0x180006a21  jmp     loc_180006937
```
