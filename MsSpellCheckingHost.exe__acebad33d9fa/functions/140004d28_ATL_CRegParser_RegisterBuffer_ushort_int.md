# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140004d28`
- end: `0x140004eb2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004eb8`

## callees

- `0x140004070`
- `0x1400048d0`
- `0x140004d28`
- `0x140005098`
- `0x140011e10`
- `0x140011ed0`

## import_xrefs

- `USER32!CharNextW` at `0x140004e97`
- `USER32!CharNextW` at `0x140004e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004dc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004dc6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004dad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004dad`

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
0x140004d28  push    rbx
0x140004d2a  push    rbp
0x140004d2b  push    rsi
0x140004d2c  push    rdi
0x140004d2d  push    r13
0x140004d2f  push    r14
0x140004d31  push    r15
0x140004d33  mov     eax, 2050h
0x140004d38  call    _alloca_probe
0x140004d3d  sub     rsp, rax
0x140004d40  mov     rax, cs:__security_cookie
0x140004d47  xor     rax, rsp
0x140004d4a  mov     [rsp+2088h+var_48], rax
0x140004d52  mov     r15d, r8d
0x140004d55  mov     [rsp+2088h+pv], 0
0x140004d5e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x140004d63  mov     rdi, rcx
0x140004d66  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140004d6b  mov     ebx, eax
0x140004d6d  test    eax, eax
0x140004d6f  js      short loc_140004DCE
0x140004d71  mov     rbp, [rsp+2088h+pv]
0x140004d76  xor     eax, eax
0x140004d78  mov     [rdi], rbp
0x140004d7b  cmp     ax, [rbp+0]
0x140004d7f  jz      short loc_140004DC3
0x140004d81  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140004d88  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140004d8d  mov     rcx, rdi; this
0x140004d90  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004d95  mov     ebx, eax
0x140004d97  test    eax, eax
0x140004d99  js      short loc_140004DC3
0x140004d9b  xor     ebx, ebx
0x140004d9d  movsxd  rsi, ebx
0x140004da0  lea     rcx, [rsp+2088h+String1]; lpString1
0x140004da5  add     rsi, rsi
0x140004da8  mov     rdx, [r13+rsi*8+0]; lpString2
0x140004dad  call    cs:__imp_lstrcmpiW
0x140004db3  test    eax, eax
0x140004db5  jz      short loc_140004DF0
0x140004db7  inc     ebx
0x140004db9  cmp     ebx, 0Eh
0x140004dbc  jb      short loc_140004D9D
0x140004dbe  mov     ebx, 80020009h
0x140004dc3  mov     rcx, rbp; pv
0x140004dc6  call    cs:__imp_CoTaskMemFree
0x140004dcc  mov     eax, ebx
0x140004dce  mov     rcx, [rsp+2088h+var_48]
0x140004dd6  xor     rcx, rsp; StackCookie
0x140004dd9  call    __security_check_cookie
0x140004dde  add     rsp, 2050h
0x140004de5  pop     r15
0x140004de7  pop     r14
0x140004de9  pop     r13
0x140004deb  pop     rdi
0x140004dec  pop     rsi
0x140004ded  pop     rbp
0x140004dee  pop     rbx
0x140004def  retn
0x140004df0  mov     rsi, [r13+rsi*8+8]
0x140004df5  test    rsi, rsi
0x140004df8  jz      short loc_140004DBE
0x140004dfa  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140004dff  mov     rcx, rdi; this
0x140004e02  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140004e07  mov     ebx, eax
0x140004e09  test    eax, eax
0x140004e0b  js      short loc_140004DC3
0x140004e0d  mov     eax, 7Bh ; '{'
0x140004e12  cmp     ax, [rsp+2088h+String1]
0x140004e17  jnz     short loc_140004DBE
0x140004e19  mov     [rsp+2088h+var_2068], 0; int
0x140004e21  mov     r8, rsi; HKEY
0x140004e24  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140004e29  mov     rcx, rdi; this
0x140004e2c  test    r15d, r15d
0x140004e2f  jz      short loc_140004E65
0x140004e31  mov     r14, [rdi]
0x140004e34  mov     r9d, r15d; int
0x140004e37  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140004e3c  mov     ebx, eax
0x140004e3e  test    eax, eax
0x140004e40  jns     short loc_140004E77
0x140004e42  xor     r9d, r9d; int
0x140004e45  mov     [rdi], r14
0x140004e48  mov     r8, rsi; HKEY
0x140004e4b  mov     [rsp+2088h+var_2068], 0; int
0x140004e53  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140004e58  mov     rcx, rdi; this
0x140004e5b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140004e60  jmp     loc_140004DC3
0x140004e65  xor     r9d, r9d; int
0x140004e68  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140004e6d  mov     ebx, eax
0x140004e6f  test    eax, eax
0x140004e71  js      loc_140004DC3
0x140004e77  mov     r8, [rdi]
0x140004e7a  movzx   edx, word ptr [r8]
0x140004e7e  mov     ecx, edx
0x140004e80  sub     ecx, 9
0x140004e83  jz      short loc_140004E94
0x140004e85  sub     ecx, 1
0x140004e88  jz      short loc_140004E94
0x140004e8a  sub     ecx, 3
0x140004e8d  jz      short loc_140004E94
0x140004e8f  cmp     ecx, 13h
0x140004e92  jnz     short loc_140004EA2
0x140004e94  mov     rcx, r8; lpsz
0x140004e97  call    cs:__imp_CharNextW
0x140004e9d  mov     [rdi], rax
0x140004ea0  jmp     short loc_140004E77
0x140004ea2  xor     eax, eax
0x140004ea4  cmp     ax, dx
0x140004ea7  jnz     loc_140004D88
0x140004ead  jmp     loc_140004DC3
```
