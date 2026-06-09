# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x1800053f8`
- end: `0x180005582`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180005588`

## callees

- `0x180004c80`
- `0x180004e2c`
- `0x1800053f8`
- `0x180005764`
- `0x18000a9d0`
- `0x18000aa90`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000547d`
- `KERNEL32!lstrcmpiW` at `0x18000547d`
- `USER32!CharNextW` at `0x180005567`
- `USER32!CharNextW` at `0x180005567`
- `ole32!CoTaskMemFree` at `0x180005496`
- `ole32!CoTaskMemFree` at `0x180005496`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  _WORD *v7; // rbp
  int v8; // ebx
  HKEY v9; // rsi
  const wchar_t *v10; // r14
  LPVOID pv; // [rsp+30h] [rbp-2058h] BYREF
  WCHAR String1[4096]; // [rsp+40h] [rbp-2048h] BYREF

  pv = 0;
  result = ATL::CRegParser::PreProcessBuffer(this, a2, (unsigned __int16 **)&pv);
  Token = result;
  if ( (int)result >= 0 )
  {
    v7 = pv;
    *this = (const wchar_t *)pv;
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
0x1800053f8  push    rbx
0x1800053fa  push    rbp
0x1800053fb  push    rsi
0x1800053fc  push    rdi
0x1800053fd  push    r13
0x1800053ff  push    r14
0x180005401  push    r15
0x180005403  mov     eax, 2050h
0x180005408  call    _alloca_probe
0x18000540d  sub     rsp, rax
0x180005410  mov     rax, cs:__security_cookie
0x180005417  xor     rax, rsp
0x18000541a  mov     [rsp+2088h+var_48], rax
0x180005422  mov     r15d, r8d
0x180005425  mov     [rsp+2088h+pv], 0
0x18000542e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180005433  mov     rdi, rcx
0x180005436  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000543b  mov     ebx, eax
0x18000543d  test    eax, eax
0x18000543f  js      short loc_18000549E
0x180005441  mov     rbp, [rsp+2088h+pv]
0x180005446  xor     eax, eax
0x180005448  mov     [rdi], rbp
0x18000544b  cmp     ax, [rbp+0]
0x18000544f  jz      short loc_180005493
0x180005451  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180005458  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000545d  mov     rcx, rdi; this
0x180005460  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005465  mov     ebx, eax
0x180005467  test    eax, eax
0x180005469  js      short loc_180005493
0x18000546b  xor     ebx, ebx
0x18000546d  movsxd  rsi, ebx
0x180005470  lea     rcx, [rsp+2088h+String1]; lpString1
0x180005475  add     rsi, rsi
0x180005478  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000547d  call    cs:__imp_lstrcmpiW
0x180005483  test    eax, eax
0x180005485  jz      short loc_1800054C0
0x180005487  inc     ebx
0x180005489  cmp     ebx, 0Eh
0x18000548c  jb      short loc_18000546D
0x18000548e  mov     ebx, 80020009h
0x180005493  mov     rcx, rbp; pv
0x180005496  call    cs:__imp_CoTaskMemFree
0x18000549c  mov     eax, ebx
0x18000549e  mov     rcx, [rsp+2088h+var_48]
0x1800054a6  xor     rcx, rsp; StackCookie
0x1800054a9  call    __security_check_cookie
0x1800054ae  add     rsp, 2050h
0x1800054b5  pop     r15
0x1800054b7  pop     r14
0x1800054b9  pop     r13
0x1800054bb  pop     rdi
0x1800054bc  pop     rsi
0x1800054bd  pop     rbp
0x1800054be  pop     rbx
0x1800054bf  retn
0x1800054c0  mov     rsi, [r13+rsi*8+8]
0x1800054c5  test    rsi, rsi
0x1800054c8  jz      short loc_18000548E
0x1800054ca  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800054cf  mov     rcx, rdi; this
0x1800054d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800054d7  mov     ebx, eax
0x1800054d9  test    eax, eax
0x1800054db  js      short loc_180005493
0x1800054dd  mov     eax, 7Bh ; '{'
0x1800054e2  cmp     ax, [rsp+2088h+String1]
0x1800054e7  jnz     short loc_18000548E
0x1800054e9  mov     [rsp+2088h+var_2068], 0; int
0x1800054f1  mov     r8, rsi; HKEY
0x1800054f4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800054f9  mov     rcx, rdi; this
0x1800054fc  test    r15d, r15d
0x1800054ff  jz      short loc_180005535
0x180005501  mov     r14, [rdi]
0x180005504  mov     r9d, r15d; int
0x180005507  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000550c  mov     ebx, eax
0x18000550e  test    eax, eax
0x180005510  jns     short loc_180005547
0x180005512  xor     r9d, r9d; int
0x180005515  mov     [rdi], r14
0x180005518  mov     r8, rsi; HKEY
0x18000551b  mov     [rsp+2088h+var_2068], 0; int
0x180005523  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180005528  mov     rcx, rdi; this
0x18000552b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005530  jmp     loc_180005493
0x180005535  xor     r9d, r9d; int
0x180005538  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000553d  mov     ebx, eax
0x18000553f  test    eax, eax
0x180005541  js      loc_180005493
0x180005547  mov     r8, [rdi]
0x18000554a  movzx   edx, word ptr [r8]
0x18000554e  mov     ecx, edx
0x180005550  sub     ecx, 9
0x180005553  jz      short loc_180005564
0x180005555  sub     ecx, 1
0x180005558  jz      short loc_180005564
0x18000555a  sub     ecx, 3
0x18000555d  jz      short loc_180005564
0x18000555f  cmp     ecx, 13h
0x180005562  jnz     short loc_180005572
0x180005564  mov     rcx, r8; lpsz
0x180005567  call    cs:__imp_CharNextW
0x18000556d  mov     [rdi], rax
0x180005570  jmp     short loc_180005547
0x180005572  xor     eax, eax
0x180005574  cmp     ax, dx
0x180005577  jnz     loc_180005458
0x18000557d  jmp     loc_180005493
```
