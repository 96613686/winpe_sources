# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800078f8`
- end: `0x180007a82`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007a88`

## callees

- `0x1800070f0`
- `0x18000729c`
- `0x1800078f8`
- `0x180007c4c`
- `0x180012e00`
- `0x180012e90`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000797d`
- `KERNEL32!lstrcmpiW` at `0x18000797d`
- `ole32!CoTaskMemFree` at `0x180007996`
- `ole32!CoTaskMemFree` at `0x180007996`
- `USER32!CharNextW` at `0x180007a67`
- `USER32!CharNextW` at `0x180007a67`

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
        Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
0x1800078f8  push    rbx
0x1800078fa  push    rbp
0x1800078fb  push    rsi
0x1800078fc  push    rdi
0x1800078fd  push    r13
0x1800078ff  push    r14
0x180007901  push    r15
0x180007903  mov     eax, 2050h
0x180007908  call    _alloca_probe
0x18000790d  sub     rsp, rax
0x180007910  mov     rax, cs:__security_cookie
0x180007917  xor     rax, rsp
0x18000791a  mov     [rsp+2088h+var_48], rax
0x180007922  mov     r15d, r8d
0x180007925  mov     [rsp+2088h+pv], 0
0x18000792e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180007933  mov     rdi, rcx
0x180007936  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000793b  mov     ebx, eax
0x18000793d  test    eax, eax
0x18000793f  js      short loc_18000799E
0x180007941  mov     rbp, [rsp+2088h+pv]
0x180007946  xor     eax, eax
0x180007948  mov     [rdi], rbp
0x18000794b  cmp     ax, [rbp+0]
0x18000794f  jz      short loc_180007993
0x180007951  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180007958  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000795d  mov     rcx, rdi; this
0x180007960  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007965  mov     ebx, eax
0x180007967  test    eax, eax
0x180007969  js      short loc_180007993
0x18000796b  xor     ebx, ebx
0x18000796d  movsxd  rsi, ebx
0x180007970  lea     rcx, [rsp+2088h+String1]; lpString1
0x180007975  add     rsi, rsi
0x180007978  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000797d  call    cs:__imp_lstrcmpiW
0x180007983  test    eax, eax
0x180007985  jz      short loc_1800079C0
0x180007987  inc     ebx
0x180007989  cmp     ebx, 0Eh
0x18000798c  jb      short loc_18000796D
0x18000798e  mov     ebx, 80020009h
0x180007993  mov     rcx, rbp; pv
0x180007996  call    cs:__imp_CoTaskMemFree
0x18000799c  mov     eax, ebx
0x18000799e  mov     rcx, [rsp+2088h+var_48]
0x1800079a6  xor     rcx, rsp; StackCookie
0x1800079a9  call    __security_check_cookie
0x1800079ae  add     rsp, 2050h
0x1800079b5  pop     r15
0x1800079b7  pop     r14
0x1800079b9  pop     r13
0x1800079bb  pop     rdi
0x1800079bc  pop     rsi
0x1800079bd  pop     rbp
0x1800079be  pop     rbx
0x1800079bf  retn
0x1800079c0  mov     rsi, [r13+rsi*8+8]
0x1800079c5  test    rsi, rsi
0x1800079c8  jz      short loc_18000798E
0x1800079ca  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800079cf  mov     rcx, rdi; this
0x1800079d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800079d7  mov     ebx, eax
0x1800079d9  test    eax, eax
0x1800079db  js      short loc_180007993
0x1800079dd  mov     eax, 7Bh ; '{'
0x1800079e2  cmp     ax, [rsp+2088h+String1]
0x1800079e7  jnz     short loc_18000798E
0x1800079e9  mov     [rsp+2088h+var_2068], 0; int
0x1800079f1  mov     r8, rsi; HKEY
0x1800079f4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800079f9  mov     rcx, rdi; this
0x1800079fc  test    r15d, r15d
0x1800079ff  jz      short loc_180007A35
0x180007a01  mov     r14, [rdi]
0x180007a04  mov     r9d, r15d; int
0x180007a07  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007a0c  mov     ebx, eax
0x180007a0e  test    eax, eax
0x180007a10  jns     short loc_180007A47
0x180007a12  xor     r9d, r9d; int
0x180007a15  mov     [rdi], r14
0x180007a18  mov     r8, rsi; HKEY
0x180007a1b  mov     [rsp+2088h+var_2068], 0; int
0x180007a23  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007a28  mov     rcx, rdi; this
0x180007a2b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007a30  jmp     loc_180007993
0x180007a35  xor     r9d, r9d; int
0x180007a38  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007a3d  mov     ebx, eax
0x180007a3f  test    eax, eax
0x180007a41  js      loc_180007993
0x180007a47  mov     r8, [rdi]
0x180007a4a  movzx   edx, word ptr [r8]
0x180007a4e  mov     ecx, edx
0x180007a50  sub     ecx, 9
0x180007a53  jz      short loc_180007A64
0x180007a55  sub     ecx, 1
0x180007a58  jz      short loc_180007A64
0x180007a5a  sub     ecx, 3
0x180007a5d  jz      short loc_180007A64
0x180007a5f  cmp     ecx, 13h
0x180007a62  jnz     short loc_180007A72
0x180007a64  mov     rcx, r8; lpsz
0x180007a67  call    cs:__imp_CharNextW
0x180007a6d  mov     [rdi], rax
0x180007a70  jmp     short loc_180007A47
0x180007a72  xor     eax, eax
0x180007a74  cmp     ax, dx
0x180007a77  jnz     loc_180007958
0x180007a7d  jmp     loc_180007993
```
