# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180092f6c`
- end: `0x1800930d9`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800930e0`

## callees

- `0x180061320`
- `0x180092970`
- `0x180092ae8`
- `0x180092f6c`
- `0x180093290`
- `0x180093b44`
- `0x1800b7bf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800930af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800930af`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180093008`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180093008`

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
0x180092f6c  push    rbx
0x180092f6e  push    rbp
0x180092f6f  push    rsi
0x180092f70  push    rdi
0x180092f71  push    r13
0x180092f73  push    r14
0x180092f75  push    r15
0x180092f77  mov     eax, 2050h
0x180092f7c  call    _alloca_probe
0x180092f81  sub     rsp, rax
0x180092f84  mov     rax, cs:__security_cookie
0x180092f8b  xor     rax, rsp
0x180092f8e  mov     [rsp+2088h+var_48], rax
0x180092f96  mov     r15d, r8d
0x180092f99  mov     [rsp+2088h+pv], 0
0x180092fa2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180092fa7  mov     rdi, rcx
0x180092faa  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180092faf  mov     ebx, eax
0x180092fb1  test    eax, eax
0x180092fb3  js      loc_1800930B7
0x180092fb9  mov     rbp, [rsp+2088h+pv]
0x180092fbe  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180092fc5  mov     [rdi], rbp
0x180092fc8  mov     rcx, [rdi]
0x180092fcb  xor     eax, eax
0x180092fcd  cmp     ax, [rcx]
0x180092fd0  jz      loc_1800930AC
0x180092fd6  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180092fdb  mov     rcx, rdi; this
0x180092fde  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180092fe3  mov     ebx, eax
0x180092fe5  test    eax, eax
0x180092fe7  js      loc_1800930AC
0x180092fed  xor     ebx, ebx
0x180092fef  cmp     ebx, 0Eh
0x180092ff2  jnb     loc_1800930A7
0x180092ff8  movsxd  rsi, ebx
0x180092ffb  lea     rcx, [rsp+2088h+String1]; lpString1
0x180093000  add     rsi, rsi
0x180093003  mov     rdx, [r13+rsi*8+0]; lpString2
0x180093008  call    cs:__imp_lstrcmpiW
0x18009300e  test    eax, eax
0x180093010  jz      short loc_180093016
0x180093012  inc     ebx
0x180093014  jmp     short loc_180092FEF
0x180093016  mov     rsi, [r13+rsi*8+8]
0x18009301b  test    rsi, rsi
0x18009301e  jz      loc_1800930A7
0x180093024  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180093029  mov     rcx, rdi; this
0x18009302c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180093031  mov     ebx, eax
0x180093033  test    eax, eax
0x180093035  js      short loc_1800930AC
0x180093037  mov     eax, 7Bh ; '{'
0x18009303c  cmp     ax, [rsp+2088h+String1]
0x180093041  jnz     short loc_1800930A7
0x180093043  mov     [rsp+2088h+var_2068], 0; int
0x18009304b  mov     r8, rsi; HKEY
0x18009304e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180093053  mov     rcx, rdi; this
0x180093056  test    r15d, r15d
0x180093059  jz      short loc_18009308C
0x18009305b  mov     r14, [rdi]
0x18009305e  mov     r9d, r15d; int
0x180093061  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180093066  mov     ebx, eax
0x180093068  test    eax, eax
0x18009306a  jns     short loc_18009309A
0x18009306c  xor     r9d, r9d; int
0x18009306f  mov     [rdi], r14
0x180093072  mov     r8, rsi; HKEY
0x180093075  mov     [rsp+2088h+var_2068], 0; int
0x18009307d  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180093082  mov     rcx, rdi; this
0x180093085  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18009308a  jmp     short loc_1800930AC
0x18009308c  xor     r9d, r9d; int
0x18009308f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180093094  mov     ebx, eax
0x180093096  test    eax, eax
0x180093098  js      short loc_1800930AC
0x18009309a  mov     rcx, rdi; this
0x18009309d  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800930a2  jmp     loc_180092FC8
0x1800930a7  mov     ebx, 80020009h
0x1800930ac  mov     rcx, rbp; pv
0x1800930af  call    cs:__imp_CoTaskMemFree
0x1800930b5  mov     eax, ebx
0x1800930b7  mov     rcx, [rsp+2088h+var_48]
0x1800930bf  xor     rcx, rsp; StackCookie
0x1800930c2  call    __security_check_cookie
0x1800930c7  add     rsp, 2050h
0x1800930ce  pop     r15
0x1800930d0  pop     r14
0x1800930d2  pop     r13
0x1800930d4  pop     rdi
0x1800930d5  pop     rsi
0x1800930d6  pop     rbp
0x1800930d7  pop     rbx
0x1800930d8  retn
```
