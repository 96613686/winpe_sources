# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18001916c`
- end: `0x1800192d9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800192e0`

## callees

- `0x180016020`
- `0x180018bfc`
- `0x180018d5c`
- `0x18001916c`
- `0x180019528`
- `0x180019cb8`
- `0x180026420`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800192af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019208`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180019208`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(ATL::CRegParser *this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
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
    while ( **(_WORD **)this )
    {
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      for ( i = 0; ; ++i )
      {
        if ( i >= 0xE )
          goto LABEL_17;
        if ( !lstrcmpiW(String1, (&`ATL::CRegParser::HKeyFromString'::`2'::map)[2 * (int)i]) )
          break;
      }
      v9 = (HKEY)*(&`ATL::CRegParser::HKeyFromString'::`2'::map + 2 * (int)i + 1);
      if ( !v9 )
        goto LABEL_17;
      Token = ATL::CRegParser::NextToken(this, String1);
      if ( Token < 0 )
        break;
      if ( String1[0] != 123 )
      {
LABEL_17:
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
      ATL::CRegParser::SkipWhiteSpace(this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x18001916c  push    rbx
0x18001916e  push    rbp
0x18001916f  push    rsi
0x180019170  push    rdi
0x180019171  push    r13
0x180019173  push    r14
0x180019175  push    r15
0x180019177  mov     eax, 2050h
0x18001917c  call    _alloca_probe
0x180019181  sub     rsp, rax
0x180019184  mov     rax, cs:__security_cookie
0x18001918b  xor     rax, rsp
0x18001918e  mov     [rsp+2088h+var_48], rax
0x180019196  mov     r15d, r8d
0x180019199  mov     [rsp+2088h+pv], 0
0x1800191a2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800191a7  mov     rdi, rcx
0x1800191aa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800191af  mov     ebx, eax
0x1800191b1  test    eax, eax
0x1800191b3  js      loc_1800192B7
0x1800191b9  mov     rbp, [rsp+2088h+pv]
0x1800191be  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800191c5  mov     [rdi], rbp
0x1800191c8  mov     rcx, [rdi]
0x1800191cb  xor     eax, eax
0x1800191cd  cmp     ax, [rcx]
0x1800191d0  jz      loc_1800192AC
0x1800191d6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800191db  mov     rcx, rdi; this
0x1800191de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800191e3  mov     ebx, eax
0x1800191e5  test    eax, eax
0x1800191e7  js      loc_1800192AC
0x1800191ed  xor     ebx, ebx
0x1800191ef  cmp     ebx, 0Eh
0x1800191f2  jnb     loc_1800192A7
0x1800191f8  movsxd  rsi, ebx
0x1800191fb  lea     rcx, [rsp+2088h+String1]; lpString1
0x180019200  add     rsi, rsi
0x180019203  mov     rdx, [r13+rsi*8+0]; lpString2
0x180019208  call    cs:__imp_lstrcmpiW
0x18001920e  test    eax, eax
0x180019210  jz      short loc_180019216
0x180019212  inc     ebx
0x180019214  jmp     short loc_1800191EF
0x180019216  mov     rsi, [r13+rsi*8+8]
0x18001921b  test    rsi, rsi
0x18001921e  jz      loc_1800192A7
0x180019224  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019229  mov     rcx, rdi; this
0x18001922c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019231  mov     ebx, eax
0x180019233  test    eax, eax
0x180019235  js      short loc_1800192AC
0x180019237  mov     eax, 7Bh ; '{'
0x18001923c  cmp     ax, [rsp+2088h+String1]
0x180019241  jnz     short loc_1800192A7
0x180019243  mov     [rsp+2088h+var_2068], 0; int
0x18001924b  mov     r8, rsi; HKEY
0x18001924e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019253  mov     rcx, rdi; this
0x180019256  test    r15d, r15d
0x180019259  jz      short loc_18001928C
0x18001925b  mov     r14, [rdi]
0x18001925e  mov     r9d, r15d; int
0x180019261  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019266  mov     ebx, eax
0x180019268  test    eax, eax
0x18001926a  jns     short loc_18001929A
0x18001926c  xor     r9d, r9d; int
0x18001926f  mov     [rdi], r14
0x180019272  mov     r8, rsi; HKEY
0x180019275  mov     [rsp+2088h+var_2068], 0; int
0x18001927d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180019282  mov     rcx, rdi; this
0x180019285  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001928a  jmp     short loc_1800192AC
0x18001928c  xor     r9d, r9d; int
0x18001928f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019294  mov     ebx, eax
0x180019296  test    eax, eax
0x180019298  js      short loc_1800192AC
0x18001929a  mov     rcx, rdi; this
0x18001929d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800192a2  jmp     loc_1800191C8
0x1800192a7  mov     ebx, 80020009h
0x1800192ac  mov     rcx, rbp; pv
0x1800192af  call    cs:__imp_CoTaskMemFree
0x1800192b5  mov     eax, ebx
0x1800192b7  mov     rcx, [rsp+2088h+var_48]
0x1800192bf  xor     rcx, rsp; StackCookie
0x1800192c2  call    __security_check_cookie
0x1800192c7  add     rsp, 2050h
0x1800192ce  pop     r15
0x1800192d0  pop     r14
0x1800192d2  pop     r13
0x1800192d4  pop     rdi
0x1800192d5  pop     rsi
0x1800192d6  pop     rbp
0x1800192d7  pop     rbx
0x1800192d8  retn
```
