# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000680c`
- end: `0x180006996`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000699c`

## callees

- `0x180001e60`
- `0x18000604c`
- `0x1800061fc`
- `0x18000680c`
- `0x180006b7c`
- `0x18000b390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800068aa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000697b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000697b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006891`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006891`

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
0x18000680c  push    rbx
0x18000680e  push    rbp
0x18000680f  push    rsi
0x180006810  push    rdi
0x180006811  push    r13
0x180006813  push    r14
0x180006815  push    r15
0x180006817  mov     eax, 2050h
0x18000681c  call    _alloca_probe
0x180006821  sub     rsp, rax
0x180006824  mov     rax, cs:__security_cookie
0x18000682b  xor     rax, rsp
0x18000682e  mov     [rsp+2088h+var_48], rax
0x180006836  mov     r15d, r8d
0x180006839  mov     [rsp+2088h+pv], 0
0x180006842  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180006847  mov     rdi, rcx
0x18000684a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000684f  mov     ebx, eax
0x180006851  test    eax, eax
0x180006853  js      short loc_1800068B2
0x180006855  mov     rbp, [rsp+2088h+pv]
0x18000685a  xor     eax, eax
0x18000685c  mov     [rdi], rbp
0x18000685f  cmp     ax, [rbp+0]
0x180006863  jz      short loc_1800068A7
0x180006865  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000686c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006871  mov     rcx, rdi; this
0x180006874  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006879  mov     ebx, eax
0x18000687b  test    eax, eax
0x18000687d  js      short loc_1800068A7
0x18000687f  xor     ebx, ebx
0x180006881  movsxd  rsi, ebx
0x180006884  lea     rcx, [rsp+2088h+String1]; lpString1
0x180006889  add     rsi, rsi
0x18000688c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006891  call    cs:__imp_lstrcmpiW
0x180006897  test    eax, eax
0x180006899  jz      short loc_1800068D4
0x18000689b  inc     ebx
0x18000689d  cmp     ebx, 0Eh
0x1800068a0  jb      short loc_180006881
0x1800068a2  mov     ebx, 80020009h
0x1800068a7  mov     rcx, rbp; pv
0x1800068aa  call    cs:__imp_CoTaskMemFree
0x1800068b0  mov     eax, ebx
0x1800068b2  mov     rcx, [rsp+2088h+var_48]
0x1800068ba  xor     rcx, rsp; StackCookie
0x1800068bd  call    __security_check_cookie
0x1800068c2  add     rsp, 2050h
0x1800068c9  pop     r15
0x1800068cb  pop     r14
0x1800068cd  pop     r13
0x1800068cf  pop     rdi
0x1800068d0  pop     rsi
0x1800068d1  pop     rbp
0x1800068d2  pop     rbx
0x1800068d3  retn
0x1800068d4  mov     rsi, [r13+rsi*8+8]
0x1800068d9  test    rsi, rsi
0x1800068dc  jz      short loc_1800068A2
0x1800068de  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800068e3  mov     rcx, rdi; this
0x1800068e6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800068eb  mov     ebx, eax
0x1800068ed  test    eax, eax
0x1800068ef  js      short loc_1800068A7
0x1800068f1  mov     eax, 7Bh ; '{'
0x1800068f6  cmp     ax, [rsp+2088h+String1]
0x1800068fb  jnz     short loc_1800068A2
0x1800068fd  mov     [rsp+2088h+var_2068], 0; int
0x180006905  mov     r8, rsi; HKEY
0x180006908  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000690d  mov     rcx, rdi; this
0x180006910  test    r15d, r15d
0x180006913  jz      short loc_180006949
0x180006915  mov     r14, [rdi]
0x180006918  mov     r9d, r15d; int
0x18000691b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006920  mov     ebx, eax
0x180006922  test    eax, eax
0x180006924  jns     short loc_18000695B
0x180006926  xor     r9d, r9d; int
0x180006929  mov     [rdi], r14
0x18000692c  mov     r8, rsi; HKEY
0x18000692f  mov     [rsp+2088h+var_2068], 0; int
0x180006937  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000693c  mov     rcx, rdi; this
0x18000693f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006944  jmp     loc_1800068A7
0x180006949  xor     r9d, r9d; int
0x18000694c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006951  mov     ebx, eax
0x180006953  test    eax, eax
0x180006955  js      loc_1800068A7
0x18000695b  mov     r8, [rdi]
0x18000695e  movzx   edx, word ptr [r8]
0x180006962  mov     ecx, edx
0x180006964  sub     ecx, 9
0x180006967  jz      short loc_180006978
0x180006969  sub     ecx, 1
0x18000696c  jz      short loc_180006978
0x18000696e  sub     ecx, 3
0x180006971  jz      short loc_180006978
0x180006973  cmp     ecx, 13h
0x180006976  jnz     short loc_180006986
0x180006978  mov     rcx, r8; lpsz
0x18000697b  call    cs:__imp_CharNextW
0x180006981  mov     [rdi], rax
0x180006984  jmp     short loc_18000695B
0x180006986  xor     eax, eax
0x180006988  cmp     ax, dx
0x18000698b  jnz     loc_18000686C
0x180006991  jmp     loc_1800068A7
```
