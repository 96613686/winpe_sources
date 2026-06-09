# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140016420`
- end: `0x1400165aa`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400165b0`

## callees

- `0x1400042f0`
- `0x140013988`
- `0x14001445c`
- `0x140016420`
- `0x140016794`
- `0x140059180`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001658f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14001658f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400164a5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1400164a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400164be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400164be`

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
0x140016420  push    rbx
0x140016422  push    rbp
0x140016423  push    rsi
0x140016424  push    rdi
0x140016425  push    r13
0x140016427  push    r14
0x140016429  push    r15
0x14001642b  mov     eax, 2050h
0x140016430  call    _alloca_probe
0x140016435  sub     rsp, rax
0x140016438  mov     rax, cs:__security_cookie
0x14001643f  xor     rax, rsp
0x140016442  mov     [rsp+2088h+var_48], rax
0x14001644a  mov     r15d, r8d
0x14001644d  mov     [rsp+2088h+pv], 0
0x140016456  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x14001645b  mov     rdi, rcx
0x14001645e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140016463  mov     ebx, eax
0x140016465  test    eax, eax
0x140016467  js      short loc_1400164C6
0x140016469  mov     rbp, [rsp+2088h+pv]
0x14001646e  xor     eax, eax
0x140016470  mov     [rdi], rbp
0x140016473  cmp     ax, [rbp+0]
0x140016477  jz      short loc_1400164BB
0x140016479  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140016480  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140016485  mov     rcx, rdi; this
0x140016488  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14001648d  mov     ebx, eax
0x14001648f  test    eax, eax
0x140016491  js      short loc_1400164BB
0x140016493  xor     ebx, ebx
0x140016495  movsxd  rsi, ebx
0x140016498  lea     rcx, [rsp+2088h+String1]; lpString1
0x14001649d  add     rsi, rsi
0x1400164a0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1400164a5  call    cs:__imp_lstrcmpiW
0x1400164ab  test    eax, eax
0x1400164ad  jz      short loc_1400164E8
0x1400164af  inc     ebx
0x1400164b1  cmp     ebx, 0Eh
0x1400164b4  jb      short loc_140016495
0x1400164b6  mov     ebx, 80020009h
0x1400164bb  mov     rcx, rbp; pv
0x1400164be  call    cs:__imp_CoTaskMemFree
0x1400164c4  mov     eax, ebx
0x1400164c6  mov     rcx, [rsp+2088h+var_48]
0x1400164ce  xor     rcx, rsp; StackCookie
0x1400164d1  call    __security_check_cookie
0x1400164d6  add     rsp, 2050h
0x1400164dd  pop     r15
0x1400164df  pop     r14
0x1400164e1  pop     r13
0x1400164e3  pop     rdi
0x1400164e4  pop     rsi
0x1400164e5  pop     rbp
0x1400164e6  pop     rbx
0x1400164e7  retn
0x1400164e8  mov     rsi, [r13+rsi*8+8]
0x1400164ed  test    rsi, rsi
0x1400164f0  jz      short loc_1400164B6
0x1400164f2  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400164f7  mov     rcx, rdi; this
0x1400164fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400164ff  mov     ebx, eax
0x140016501  test    eax, eax
0x140016503  js      short loc_1400164BB
0x140016505  mov     eax, 7Bh ; '{'
0x14001650a  cmp     ax, [rsp+2088h+String1]
0x14001650f  jnz     short loc_1400164B6
0x140016511  mov     [rsp+2088h+var_2068], 0; int
0x140016519  mov     r8, rsi; HKEY
0x14001651c  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140016521  mov     rcx, rdi; this
0x140016524  test    r15d, r15d
0x140016527  jz      short loc_14001655D
0x140016529  mov     r14, [rdi]
0x14001652c  mov     r9d, r15d; int
0x14001652f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140016534  mov     ebx, eax
0x140016536  test    eax, eax
0x140016538  jns     short loc_14001656F
0x14001653a  xor     r9d, r9d; int
0x14001653d  mov     [rdi], r14
0x140016540  mov     r8, rsi; HKEY
0x140016543  mov     [rsp+2088h+var_2068], 0; int
0x14001654b  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140016550  mov     rcx, rdi; this
0x140016553  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140016558  jmp     loc_1400164BB
0x14001655d  xor     r9d, r9d; int
0x140016560  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140016565  mov     ebx, eax
0x140016567  test    eax, eax
0x140016569  js      loc_1400164BB
0x14001656f  mov     r8, [rdi]
0x140016572  movzx   edx, word ptr [r8]
0x140016576  mov     ecx, edx
0x140016578  sub     ecx, 9
0x14001657b  jz      short loc_14001658C
0x14001657d  sub     ecx, 1
0x140016580  jz      short loc_14001658C
0x140016582  sub     ecx, 3
0x140016585  jz      short loc_14001658C
0x140016587  cmp     ecx, 13h
0x14001658a  jnz     short loc_14001659A
0x14001658c  mov     rcx, r8; lpsz
0x14001658f  call    cs:__imp_CharNextW
0x140016595  mov     [rdi], rax
0x140016598  jmp     short loc_14001656F
0x14001659a  xor     eax, eax
0x14001659c  cmp     ax, dx
0x14001659f  jnz     loc_140016480
0x1400165a5  jmp     loc_1400164BB
```
