# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800069ac`
- end: `0x180006b36`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b3c`

## callees

- `0x180002000`
- `0x1800061ec`
- `0x18000639c`
- `0x1800069ac`
- `0x180006d1c`
- `0x18000cc00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a4a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b1b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006b1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006a31`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006a31`

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
0x1800069ac  push    rbx
0x1800069ae  push    rbp
0x1800069af  push    rsi
0x1800069b0  push    rdi
0x1800069b1  push    r13
0x1800069b3  push    r14
0x1800069b5  push    r15
0x1800069b7  mov     eax, 2050h
0x1800069bc  call    _alloca_probe
0x1800069c1  sub     rsp, rax
0x1800069c4  mov     rax, cs:__security_cookie
0x1800069cb  xor     rax, rsp
0x1800069ce  mov     [rsp+2088h+var_48], rax
0x1800069d6  mov     r15d, r8d
0x1800069d9  mov     [rsp+2088h+pv], 0
0x1800069e2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800069e7  mov     rdi, rcx
0x1800069ea  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800069ef  mov     ebx, eax
0x1800069f1  test    eax, eax
0x1800069f3  js      short loc_180006A52
0x1800069f5  mov     rbp, [rsp+2088h+pv]
0x1800069fa  xor     eax, eax
0x1800069fc  mov     [rdi], rbp
0x1800069ff  cmp     ax, [rbp+0]
0x180006a03  jz      short loc_180006A47
0x180006a05  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180006a0c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006a11  mov     rcx, rdi; this
0x180006a14  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006a19  mov     ebx, eax
0x180006a1b  test    eax, eax
0x180006a1d  js      short loc_180006A47
0x180006a1f  xor     ebx, ebx
0x180006a21  movsxd  rsi, ebx
0x180006a24  lea     rcx, [rsp+2088h+String1]; lpString1
0x180006a29  add     rsi, rsi
0x180006a2c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006a31  call    cs:__imp_lstrcmpiW
0x180006a37  test    eax, eax
0x180006a39  jz      short loc_180006A74
0x180006a3b  inc     ebx
0x180006a3d  cmp     ebx, 0Eh
0x180006a40  jb      short loc_180006A21
0x180006a42  mov     ebx, 80020009h
0x180006a47  mov     rcx, rbp; pv
0x180006a4a  call    cs:__imp_CoTaskMemFree
0x180006a50  mov     eax, ebx
0x180006a52  mov     rcx, [rsp+2088h+var_48]
0x180006a5a  xor     rcx, rsp; StackCookie
0x180006a5d  call    __security_check_cookie
0x180006a62  add     rsp, 2050h
0x180006a69  pop     r15
0x180006a6b  pop     r14
0x180006a6d  pop     r13
0x180006a6f  pop     rdi
0x180006a70  pop     rsi
0x180006a71  pop     rbp
0x180006a72  pop     rbx
0x180006a73  retn
0x180006a74  mov     rsi, [r13+rsi*8+8]
0x180006a79  test    rsi, rsi
0x180006a7c  jz      short loc_180006A42
0x180006a7e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006a83  mov     rcx, rdi; this
0x180006a86  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006a8b  mov     ebx, eax
0x180006a8d  test    eax, eax
0x180006a8f  js      short loc_180006A47
0x180006a91  mov     eax, 7Bh ; '{'
0x180006a96  cmp     ax, [rsp+2088h+String1]
0x180006a9b  jnz     short loc_180006A42
0x180006a9d  mov     [rsp+2088h+var_2068], 0; int
0x180006aa5  mov     r8, rsi; HKEY
0x180006aa8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006aad  mov     rcx, rdi; this
0x180006ab0  test    r15d, r15d
0x180006ab3  jz      short loc_180006AE9
0x180006ab5  mov     r14, [rdi]
0x180006ab8  mov     r9d, r15d; int
0x180006abb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006ac0  mov     ebx, eax
0x180006ac2  test    eax, eax
0x180006ac4  jns     short loc_180006AFB
0x180006ac6  xor     r9d, r9d; int
0x180006ac9  mov     [rdi], r14
0x180006acc  mov     r8, rsi; HKEY
0x180006acf  mov     [rsp+2088h+var_2068], 0; int
0x180006ad7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180006adc  mov     rcx, rdi; this
0x180006adf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006ae4  jmp     loc_180006A47
0x180006ae9  xor     r9d, r9d; int
0x180006aec  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180006af1  mov     ebx, eax
0x180006af3  test    eax, eax
0x180006af5  js      loc_180006A47
0x180006afb  mov     r8, [rdi]
0x180006afe  movzx   edx, word ptr [r8]
0x180006b02  mov     ecx, edx
0x180006b04  sub     ecx, 9
0x180006b07  jz      short loc_180006B18
0x180006b09  sub     ecx, 1
0x180006b0c  jz      short loc_180006B18
0x180006b0e  sub     ecx, 3
0x180006b11  jz      short loc_180006B18
0x180006b13  cmp     ecx, 13h
0x180006b16  jnz     short loc_180006B26
0x180006b18  mov     rcx, r8; lpsz
0x180006b1b  call    cs:__imp_CharNextW
0x180006b21  mov     [rdi], rax
0x180006b24  jmp     short loc_180006AFB
0x180006b26  xor     eax, eax
0x180006b28  cmp     ax, dx
0x180006b2b  jnz     loc_180006A0C
0x180006b31  jmp     loc_180006A47
```
