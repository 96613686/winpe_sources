# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180015acc`
- end: `0x180015c56`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015c5c`

## callees

- `0x180001800`
- `0x180015400`
- `0x1800155a0`
- `0x180015acc`
- `0x180015e40`
- `0x180032a50`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180015b51`
- `KERNEL32!lstrcmpiW` at `0x180015b51`
- `ole32!CoTaskMemFree` at `0x180015b6a`
- `ole32!CoTaskMemFree` at `0x180015b6a`
- `USER32!CharNextW` at `0x180015c3b`
- `USER32!CharNextW` at `0x180015c3b`

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
0x180015acc  push    rbx
0x180015ace  push    rbp
0x180015acf  push    rsi
0x180015ad0  push    rdi
0x180015ad1  push    r13
0x180015ad3  push    r14
0x180015ad5  push    r15
0x180015ad7  mov     eax, 2050h
0x180015adc  call    _alloca_probe
0x180015ae1  sub     rsp, rax
0x180015ae4  mov     rax, cs:__security_cookie
0x180015aeb  xor     rax, rsp
0x180015aee  mov     [rsp+2088h+var_48], rax
0x180015af6  mov     r15d, r8d
0x180015af9  mov     [rsp+2088h+pv], 0
0x180015b02  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180015b07  mov     rdi, rcx
0x180015b0a  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180015b0f  mov     ebx, eax
0x180015b11  test    eax, eax
0x180015b13  js      short loc_180015B72
0x180015b15  mov     rbp, [rsp+2088h+pv]
0x180015b1a  xor     eax, eax
0x180015b1c  mov     [rdi], rbp
0x180015b1f  cmp     ax, [rbp+0]
0x180015b23  jz      short loc_180015B67
0x180015b25  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180015b2c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180015b31  mov     rcx, rdi; this
0x180015b34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015b39  mov     ebx, eax
0x180015b3b  test    eax, eax
0x180015b3d  js      short loc_180015B67
0x180015b3f  xor     ebx, ebx
0x180015b41  movsxd  rsi, ebx
0x180015b44  lea     rcx, [rsp+2088h+String1]; lpString1
0x180015b49  add     rsi, rsi
0x180015b4c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180015b51  call    cs:__imp_lstrcmpiW
0x180015b57  test    eax, eax
0x180015b59  jz      short loc_180015B94
0x180015b5b  inc     ebx
0x180015b5d  cmp     ebx, 0Eh
0x180015b60  jb      short loc_180015B41
0x180015b62  mov     ebx, 80020009h
0x180015b67  mov     rcx, rbp; pv
0x180015b6a  call    cs:__imp_CoTaskMemFree
0x180015b70  mov     eax, ebx
0x180015b72  mov     rcx, [rsp+2088h+var_48]
0x180015b7a  xor     rcx, rsp; StackCookie
0x180015b7d  call    __security_check_cookie
0x180015b82  add     rsp, 2050h
0x180015b89  pop     r15
0x180015b8b  pop     r14
0x180015b8d  pop     r13
0x180015b8f  pop     rdi
0x180015b90  pop     rsi
0x180015b91  pop     rbp
0x180015b92  pop     rbx
0x180015b93  retn
0x180015b94  mov     rsi, [r13+rsi*8+8]
0x180015b99  test    rsi, rsi
0x180015b9c  jz      short loc_180015B62
0x180015b9e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180015ba3  mov     rcx, rdi; this
0x180015ba6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015bab  mov     ebx, eax
0x180015bad  test    eax, eax
0x180015baf  js      short loc_180015B67
0x180015bb1  mov     eax, 7Bh ; '{'
0x180015bb6  cmp     ax, [rsp+2088h+String1]
0x180015bbb  jnz     short loc_180015B62
0x180015bbd  mov     [rsp+2088h+var_2068], 0; int
0x180015bc5  mov     r8, rsi; HKEY
0x180015bc8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180015bcd  mov     rcx, rdi; this
0x180015bd0  test    r15d, r15d
0x180015bd3  jz      short loc_180015C09
0x180015bd5  mov     r14, [rdi]
0x180015bd8  mov     r9d, r15d; int
0x180015bdb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015be0  mov     ebx, eax
0x180015be2  test    eax, eax
0x180015be4  jns     short loc_180015C1B
0x180015be6  xor     r9d, r9d; int
0x180015be9  mov     [rdi], r14
0x180015bec  mov     r8, rsi; HKEY
0x180015bef  mov     [rsp+2088h+var_2068], 0; int
0x180015bf7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180015bfc  mov     rcx, rdi; this
0x180015bff  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015c04  jmp     loc_180015B67
0x180015c09  xor     r9d, r9d; int
0x180015c0c  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015c11  mov     ebx, eax
0x180015c13  test    eax, eax
0x180015c15  js      loc_180015B67
0x180015c1b  mov     r8, [rdi]
0x180015c1e  movzx   edx, word ptr [r8]
0x180015c22  mov     ecx, edx
0x180015c24  sub     ecx, 9
0x180015c27  jz      short loc_180015C38
0x180015c29  sub     ecx, 1
0x180015c2c  jz      short loc_180015C38
0x180015c2e  sub     ecx, 3
0x180015c31  jz      short loc_180015C38
0x180015c33  cmp     ecx, 13h
0x180015c36  jnz     short loc_180015C46
0x180015c38  mov     rcx, r8; lpsz
0x180015c3b  call    cs:__imp_CharNextW
0x180015c41  mov     [rdi], rax
0x180015c44  jmp     short loc_180015C1B
0x180015c46  xor     eax, eax
0x180015c48  cmp     ax, dx
0x180015c4b  jnz     loc_180015B2C
0x180015c51  jmp     loc_180015B67
```
