# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x18000878c`
- end: `0x180008916`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000891c`

## callees

- `0x1800038f0`
- `0x180007f8c`
- `0x18000813c`
- `0x18000878c`
- `0x180008afc`
- `0x18001f830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000882a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000882a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800088fb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800088fb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008811`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008811`

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
0x18000878c  push    rbx
0x18000878e  push    rbp
0x18000878f  push    rsi
0x180008790  push    rdi
0x180008791  push    r13
0x180008793  push    r14
0x180008795  push    r15
0x180008797  mov     eax, 2050h
0x18000879c  call    _alloca_probe
0x1800087a1  sub     rsp, rax
0x1800087a4  mov     rax, cs:__security_cookie
0x1800087ab  xor     rax, rsp
0x1800087ae  mov     [rsp+2088h+var_48], rax
0x1800087b6  mov     r15d, r8d
0x1800087b9  mov     [rsp+2088h+pv], 0
0x1800087c2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800087c7  mov     rdi, rcx
0x1800087ca  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800087cf  mov     ebx, eax
0x1800087d1  test    eax, eax
0x1800087d3  js      short loc_180008832
0x1800087d5  mov     rbp, [rsp+2088h+pv]
0x1800087da  xor     eax, eax
0x1800087dc  mov     [rdi], rbp
0x1800087df  cmp     ax, [rbp+0]
0x1800087e3  jz      short loc_180008827
0x1800087e5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800087ec  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800087f1  mov     rcx, rdi; this
0x1800087f4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800087f9  mov     ebx, eax
0x1800087fb  test    eax, eax
0x1800087fd  js      short loc_180008827
0x1800087ff  xor     ebx, ebx
0x180008801  movsxd  rsi, ebx
0x180008804  lea     rcx, [rsp+2088h+String1]; lpString1
0x180008809  add     rsi, rsi
0x18000880c  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008811  call    cs:__imp_lstrcmpiW
0x180008817  test    eax, eax
0x180008819  jz      short loc_180008854
0x18000881b  inc     ebx
0x18000881d  cmp     ebx, 0Eh
0x180008820  jb      short loc_180008801
0x180008822  mov     ebx, 80020009h
0x180008827  mov     rcx, rbp; pv
0x18000882a  call    cs:__imp_CoTaskMemFree
0x180008830  mov     eax, ebx
0x180008832  mov     rcx, [rsp+2088h+var_48]
0x18000883a  xor     rcx, rsp; StackCookie
0x18000883d  call    __security_check_cookie
0x180008842  add     rsp, 2050h
0x180008849  pop     r15
0x18000884b  pop     r14
0x18000884d  pop     r13
0x18000884f  pop     rdi
0x180008850  pop     rsi
0x180008851  pop     rbp
0x180008852  pop     rbx
0x180008853  retn
0x180008854  mov     rsi, [r13+rsi*8+8]
0x180008859  test    rsi, rsi
0x18000885c  jz      short loc_180008822
0x18000885e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180008863  mov     rcx, rdi; this
0x180008866  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000886b  mov     ebx, eax
0x18000886d  test    eax, eax
0x18000886f  js      short loc_180008827
0x180008871  mov     eax, 7Bh ; '{'
0x180008876  cmp     ax, [rsp+2088h+String1]
0x18000887b  jnz     short loc_180008822
0x18000887d  mov     [rsp+2088h+var_2068], 0; int
0x180008885  mov     r8, rsi; HKEY
0x180008888  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000888d  mov     rcx, rdi; this
0x180008890  test    r15d, r15d
0x180008893  jz      short loc_1800088C9
0x180008895  mov     r14, [rdi]
0x180008898  mov     r9d, r15d; int
0x18000889b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800088a0  mov     ebx, eax
0x1800088a2  test    eax, eax
0x1800088a4  jns     short loc_1800088DB
0x1800088a6  xor     r9d, r9d; int
0x1800088a9  mov     [rdi], r14
0x1800088ac  mov     r8, rsi; HKEY
0x1800088af  mov     [rsp+2088h+var_2068], 0; int
0x1800088b7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800088bc  mov     rcx, rdi; this
0x1800088bf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800088c4  jmp     loc_180008827
0x1800088c9  xor     r9d, r9d; int
0x1800088cc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800088d1  mov     ebx, eax
0x1800088d3  test    eax, eax
0x1800088d5  js      loc_180008827
0x1800088db  mov     r8, [rdi]
0x1800088de  movzx   edx, word ptr [r8]
0x1800088e2  mov     ecx, edx
0x1800088e4  sub     ecx, 9
0x1800088e7  jz      short loc_1800088F8
0x1800088e9  sub     ecx, 1
0x1800088ec  jz      short loc_1800088F8
0x1800088ee  sub     ecx, 3
0x1800088f1  jz      short loc_1800088F8
0x1800088f3  cmp     ecx, 13h
0x1800088f6  jnz     short loc_180008906
0x1800088f8  mov     rcx, r8; lpsz
0x1800088fb  call    cs:__imp_CharNextW
0x180008901  mov     [rdi], rax
0x180008904  jmp     short loc_1800088DB
0x180008906  xor     eax, eax
0x180008908  cmp     ax, dx
0x18000890b  jnz     loc_1800087EC
0x180008911  jmp     loc_180008827
```
