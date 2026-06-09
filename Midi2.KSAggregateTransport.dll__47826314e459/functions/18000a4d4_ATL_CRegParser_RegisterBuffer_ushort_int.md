# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000a4d4`
- end: `0x18000a65e`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a664`

## callees

- `0x180005020`
- `0x180009a88`
- `0x180009c28`
- `0x18000a4d4`
- `0x18000a844`
- `0x1800599b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a572`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a572`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a643`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000a643`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a559`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a559`

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
0x18000a4d4  push    rbx
0x18000a4d6  push    rbp
0x18000a4d7  push    rsi
0x18000a4d8  push    rdi
0x18000a4d9  push    r13
0x18000a4db  push    r14
0x18000a4dd  push    r15
0x18000a4df  mov     eax, 2050h
0x18000a4e4  call    _alloca_probe
0x18000a4e9  sub     rsp, rax
0x18000a4ec  mov     rax, cs:__security_cookie
0x18000a4f3  xor     rax, rsp
0x18000a4f6  mov     [rsp+2088h+var_48], rax
0x18000a4fe  mov     r15d, r8d
0x18000a501  mov     [rsp+2088h+pv], 0
0x18000a50a  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000a50f  mov     rdi, rcx
0x18000a512  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000a517  mov     ebx, eax
0x18000a519  test    eax, eax
0x18000a51b  js      short loc_18000A57A
0x18000a51d  mov     rbp, [rsp+2088h+pv]
0x18000a522  xor     eax, eax
0x18000a524  mov     [rdi], rbp
0x18000a527  cmp     ax, [rbp+0]
0x18000a52b  jz      short loc_18000A56F
0x18000a52d  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x18000a534  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a539  mov     rcx, rdi; this
0x18000a53c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a541  mov     ebx, eax
0x18000a543  test    eax, eax
0x18000a545  js      short loc_18000A56F
0x18000a547  xor     ebx, ebx
0x18000a549  movsxd  rsi, ebx
0x18000a54c  lea     rcx, [rsp+2088h+String1]; lpString1
0x18000a551  add     rsi, rsi
0x18000a554  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000a559  call    cs:__imp_lstrcmpiW
0x18000a55f  test    eax, eax
0x18000a561  jz      short loc_18000A59C
0x18000a563  inc     ebx
0x18000a565  cmp     ebx, 0Eh
0x18000a568  jb      short loc_18000A549
0x18000a56a  mov     ebx, 80020009h
0x18000a56f  mov     rcx, rbp; pv
0x18000a572  call    cs:__imp_CoTaskMemFree
0x18000a578  mov     eax, ebx
0x18000a57a  mov     rcx, [rsp+2088h+var_48]
0x18000a582  xor     rcx, rsp; StackCookie
0x18000a585  call    __security_check_cookie
0x18000a58a  add     rsp, 2050h
0x18000a591  pop     r15
0x18000a593  pop     r14
0x18000a595  pop     r13
0x18000a597  pop     rdi
0x18000a598  pop     rsi
0x18000a599  pop     rbp
0x18000a59a  pop     rbx
0x18000a59b  retn
0x18000a59c  mov     rsi, [r13+rsi*8+8]
0x18000a5a1  test    rsi, rsi
0x18000a5a4  jz      short loc_18000A56A
0x18000a5a6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a5ab  mov     rcx, rdi; this
0x18000a5ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a5b3  mov     ebx, eax
0x18000a5b5  test    eax, eax
0x18000a5b7  js      short loc_18000A56F
0x18000a5b9  mov     eax, 7Bh ; '{'
0x18000a5be  cmp     ax, [rsp+2088h+String1]
0x18000a5c3  jnz     short loc_18000A56A
0x18000a5c5  mov     [rsp+2088h+var_2068], 0; int
0x18000a5cd  mov     r8, rsi; HKEY
0x18000a5d0  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a5d5  mov     rcx, rdi; this
0x18000a5d8  test    r15d, r15d
0x18000a5db  jz      short loc_18000A611
0x18000a5dd  mov     r14, [rdi]
0x18000a5e0  mov     r9d, r15d; int
0x18000a5e3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a5e8  mov     ebx, eax
0x18000a5ea  test    eax, eax
0x18000a5ec  jns     short loc_18000A623
0x18000a5ee  xor     r9d, r9d; int
0x18000a5f1  mov     [rdi], r14
0x18000a5f4  mov     r8, rsi; HKEY
0x18000a5f7  mov     [rsp+2088h+var_2068], 0; int
0x18000a5ff  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000a604  mov     rcx, rdi; this
0x18000a607  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a60c  jmp     loc_18000A56F
0x18000a611  xor     r9d, r9d; int
0x18000a614  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000a619  mov     ebx, eax
0x18000a61b  test    eax, eax
0x18000a61d  js      loc_18000A56F
0x18000a623  mov     r8, [rdi]
0x18000a626  movzx   edx, word ptr [r8]
0x18000a62a  mov     ecx, edx
0x18000a62c  sub     ecx, 9
0x18000a62f  jz      short loc_18000A640
0x18000a631  sub     ecx, 1
0x18000a634  jz      short loc_18000A640
0x18000a636  sub     ecx, 3
0x18000a639  jz      short loc_18000A640
0x18000a63b  cmp     ecx, 13h
0x18000a63e  jnz     short loc_18000A64E
0x18000a640  mov     rcx, r8; lpsz
0x18000a643  call    cs:__imp_CharNextW
0x18000a649  mov     [rdi], rax
0x18000a64c  jmp     short loc_18000A623
0x18000a64e  xor     eax, eax
0x18000a650  cmp     ax, dx
0x18000a653  jnz     loc_18000A534
0x18000a659  jmp     loc_18000A56F
```
