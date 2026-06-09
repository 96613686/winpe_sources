# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180009538`
- end: `0x1800096c2`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800096c8`

## callees

- `0x180008930`
- `0x180008ecc`
- `0x180009538`
- `0x180009884`
- `0x18000c990`
- `0x18000ca20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800095d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800095d6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800096a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800096a7`
- `KERNEL32!lstrcmpiW` at `0x1800095bd`
- `KERNEL32!lstrcmpiW` at `0x1800095bd`

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
0x180009538  push    rbx
0x18000953a  push    rbp
0x18000953b  push    rsi
0x18000953c  push    rdi
0x18000953d  push    r13
0x18000953f  push    r14
0x180009541  push    r15
0x180009543  mov     eax, 2050h
0x180009548  call    _alloca_probe
0x18000954d  sub     rsp, rax
0x180009550  mov     rax, cs:__security_cookie
0x180009557  xor     rax, rsp
0x18000955a  mov     [rsp+2088h+var_48], rax
0x180009562  mov     r15d, r8d
0x180009565  mov     [rsp+2088h+pv], 0
0x18000956e  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180009573  mov     rdi, rcx
0x180009576  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x18000957b  mov     ebx, eax
0x18000957d  test    eax, eax
0x18000957f  js      short loc_1800095DE
0x180009581  mov     rbp, [rsp+2088h+pv]
0x180009586  xor     eax, eax
0x180009588  mov     [rdi], rbp
0x18000958b  cmp     ax, [rbp+0]
0x18000958f  jz      short loc_1800095D3
0x180009591  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180009598  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000959d  mov     rcx, rdi; this
0x1800095a0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800095a5  mov     ebx, eax
0x1800095a7  test    eax, eax
0x1800095a9  js      short loc_1800095D3
0x1800095ab  xor     ebx, ebx
0x1800095ad  movsxd  rsi, ebx
0x1800095b0  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800095b5  add     rsi, rsi
0x1800095b8  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800095bd  call    cs:__imp_lstrcmpiW
0x1800095c3  test    eax, eax
0x1800095c5  jz      short loc_180009600
0x1800095c7  inc     ebx
0x1800095c9  cmp     ebx, 0Eh
0x1800095cc  jb      short loc_1800095AD
0x1800095ce  mov     ebx, 80020009h
0x1800095d3  mov     rcx, rbp; pv
0x1800095d6  call    cs:__imp_CoTaskMemFree
0x1800095dc  mov     eax, ebx
0x1800095de  mov     rcx, [rsp+2088h+var_48]
0x1800095e6  xor     rcx, rsp; StackCookie
0x1800095e9  call    __security_check_cookie
0x1800095ee  add     rsp, 2050h
0x1800095f5  pop     r15
0x1800095f7  pop     r14
0x1800095f9  pop     r13
0x1800095fb  pop     rdi
0x1800095fc  pop     rsi
0x1800095fd  pop     rbp
0x1800095fe  pop     rbx
0x1800095ff  retn
0x180009600  mov     rsi, [r13+rsi*8+8]
0x180009605  test    rsi, rsi
0x180009608  jz      short loc_1800095CE
0x18000960a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18000960f  mov     rcx, rdi; this
0x180009612  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009617  mov     ebx, eax
0x180009619  test    eax, eax
0x18000961b  js      short loc_1800095D3
0x18000961d  mov     eax, 7Bh ; '{'
0x180009622  cmp     ax, [rsp+2088h+String1]
0x180009627  jnz     short loc_1800095CE
0x180009629  mov     [rsp+2088h+var_2068], 0; int
0x180009631  mov     r8, rsi; HKEY
0x180009634  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009639  mov     rcx, rdi; this
0x18000963c  test    r15d, r15d
0x18000963f  jz      short loc_180009675
0x180009641  mov     r14, [rdi]
0x180009644  mov     r9d, r15d; int
0x180009647  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000964c  mov     ebx, eax
0x18000964e  test    eax, eax
0x180009650  jns     short loc_180009687
0x180009652  xor     r9d, r9d; int
0x180009655  mov     [rdi], r14
0x180009658  mov     r8, rsi; HKEY
0x18000965b  mov     [rsp+2088h+var_2068], 0; int
0x180009663  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009668  mov     rcx, rdi; this
0x18000966b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009670  jmp     loc_1800095D3
0x180009675  xor     r9d, r9d; int
0x180009678  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000967d  mov     ebx, eax
0x18000967f  test    eax, eax
0x180009681  js      loc_1800095D3
0x180009687  mov     r8, [rdi]
0x18000968a  movzx   edx, word ptr [r8]
0x18000968e  mov     ecx, edx
0x180009690  sub     ecx, 9
0x180009693  jz      short loc_1800096A4
0x180009695  sub     ecx, 1
0x180009698  jz      short loc_1800096A4
0x18000969a  sub     ecx, 3
0x18000969d  jz      short loc_1800096A4
0x18000969f  cmp     ecx, 13h
0x1800096a2  jnz     short loc_1800096B2
0x1800096a4  mov     rcx, r8; lpsz
0x1800096a7  call    cs:__imp_CharNextW
0x1800096ad  mov     [rdi], rax
0x1800096b0  jmp     short loc_180009687
0x1800096b2  xor     eax, eax
0x1800096b4  cmp     ax, dx
0x1800096b7  jnz     loc_180009598
0x1800096bd  jmp     loc_1800095D3
```
