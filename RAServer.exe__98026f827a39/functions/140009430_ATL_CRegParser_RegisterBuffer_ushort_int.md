# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x140009430`
- end: `0x14000959d`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `365`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400095a4`

## callees

- `0x1400080e8`
- `0x140008428`
- `0x140009430`
- `0x140009754`
- `0x14000a938`
- `0x140015aa0`
- `0x140015b60`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x1400094cc`
- `KERNEL32!lstrcmpiW` at `0x1400094cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009573`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterBuffer(const wchar_t **this, unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  int Token; // ebx
  void *v7; // rbp
  unsigned int i; // ebx
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
    while ( **this )
    {
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
      Token = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
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
      ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)this);
    }
    CoTaskMemFree(v7);
    return (unsigned int)Token;
  }
  return result;
}

```

## disassembly

```asm
0x140009430  push    rbx
0x140009432  push    rbp
0x140009433  push    rsi
0x140009434  push    rdi
0x140009435  push    r13
0x140009437  push    r14
0x140009439  push    r15
0x14000943b  mov     eax, 2050h
0x140009440  call    _alloca_probe
0x140009445  sub     rsp, rax
0x140009448  mov     rax, cs:__security_cookie
0x14000944f  xor     rax, rsp
0x140009452  mov     [rsp+2088h+var_48], rax
0x14000945a  mov     r15d, r8d
0x14000945d  mov     [rsp+2088h+pv], 0
0x140009466  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x14000946b  mov     rdi, rcx
0x14000946e  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x140009473  mov     ebx, eax
0x140009475  test    eax, eax
0x140009477  js      loc_14000957B
0x14000947d  mov     rbp, [rsp+2088h+pv]
0x140009482  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x140009489  mov     [rdi], rbp
0x14000948c  mov     rcx, [rdi]
0x14000948f  xor     eax, eax
0x140009491  cmp     ax, [rcx]
0x140009494  jz      loc_140009570
0x14000949a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x14000949f  mov     rcx, rdi; this
0x1400094a2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400094a7  mov     ebx, eax
0x1400094a9  test    eax, eax
0x1400094ab  js      loc_140009570
0x1400094b1  xor     ebx, ebx
0x1400094b3  cmp     ebx, 0Eh
0x1400094b6  jnb     loc_14000956B
0x1400094bc  movsxd  rsi, ebx
0x1400094bf  lea     rcx, [rsp+2088h+String1]; lpString1
0x1400094c4  add     rsi, rsi
0x1400094c7  mov     rdx, [r13+rsi*8+0]; lpString2
0x1400094cc  call    cs:__imp_lstrcmpiW
0x1400094d2  test    eax, eax
0x1400094d4  jz      short loc_1400094DA
0x1400094d6  inc     ebx
0x1400094d8  jmp     short loc_1400094B3
0x1400094da  mov     rsi, [r13+rsi*8+8]
0x1400094df  test    rsi, rsi
0x1400094e2  jz      loc_14000956B
0x1400094e8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1400094ed  mov     rcx, rdi; this
0x1400094f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400094f5  mov     ebx, eax
0x1400094f7  test    eax, eax
0x1400094f9  js      short loc_140009570
0x1400094fb  mov     eax, 7Bh ; '{'
0x140009500  cmp     ax, [rsp+2088h+String1]
0x140009505  jnz     short loc_14000956B
0x140009507  mov     [rsp+2088h+var_2068], 0; int
0x14000950f  mov     r8, rsi; HKEY
0x140009512  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140009517  mov     rcx, rdi; this
0x14000951a  test    r15d, r15d
0x14000951d  jz      short loc_140009550
0x14000951f  mov     r14, [rdi]
0x140009522  mov     r9d, r15d; int
0x140009525  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000952a  mov     ebx, eax
0x14000952c  test    eax, eax
0x14000952e  jns     short loc_14000955E
0x140009530  xor     r9d, r9d; int
0x140009533  mov     [rdi], r14
0x140009536  mov     r8, rsi; HKEY
0x140009539  mov     [rsp+2088h+var_2068], 0; int
0x140009541  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x140009546  mov     rcx, rdi; this
0x140009549  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000954e  jmp     short loc_140009570
0x140009550  xor     r9d, r9d; int
0x140009553  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x140009558  mov     ebx, eax
0x14000955a  test    eax, eax
0x14000955c  js      short loc_140009570
0x14000955e  mov     rcx, rdi; this
0x140009561  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140009566  jmp     loc_14000948C
0x14000956b  mov     ebx, 80020009h
0x140009570  mov     rcx, rbp; pv
0x140009573  call    cs:__imp_CoTaskMemFree
0x140009579  mov     eax, ebx
0x14000957b  mov     rcx, [rsp+2088h+var_48]
0x140009583  xor     rcx, rsp; StackCookie
0x140009586  call    __security_check_cookie
0x14000958b  add     rsp, 2050h
0x140009592  pop     r15
0x140009594  pop     r14
0x140009596  pop     r13
0x140009598  pop     rdi
0x140009599  pop     rsi
0x14000959a  pop     rbp
0x14000959b  pop     rbx
0x14000959c  retn
```
