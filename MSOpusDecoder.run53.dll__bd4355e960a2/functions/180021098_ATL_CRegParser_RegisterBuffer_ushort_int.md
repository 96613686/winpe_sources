# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180021098`
- end: `0x180021222`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021228`

## callees

- `0x1800018f0`
- `0x18001afd0`
- `0x180020980`
- `0x180020b20`
- `0x180021098`
- `0x18002140c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021136`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180021207`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180021207`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002111d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002111d`

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
0x180021098  push    rbx
0x18002109a  push    rbp
0x18002109b  push    rsi
0x18002109c  push    rdi
0x18002109d  push    r13
0x18002109f  push    r14
0x1800210a1  push    r15
0x1800210a3  mov     eax, 2050h
0x1800210a8  call    _alloca_probe
0x1800210ad  sub     rsp, rax
0x1800210b0  mov     rax, cs:__security_cookie
0x1800210b7  xor     rax, rsp
0x1800210ba  mov     [rsp+2088h+var_48], rax
0x1800210c2  mov     r15d, r8d
0x1800210c5  mov     [rsp+2088h+pv], 0
0x1800210ce  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x1800210d3  mov     rdi, rcx
0x1800210d6  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x1800210db  mov     ebx, eax
0x1800210dd  test    eax, eax
0x1800210df  js      short loc_18002113E
0x1800210e1  mov     rbp, [rsp+2088h+pv]
0x1800210e6  xor     eax, eax
0x1800210e8  mov     [rdi], rbp
0x1800210eb  cmp     ax, [rbp+0]
0x1800210ef  jz      short loc_180021133
0x1800210f1  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800210f8  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800210fd  mov     rcx, rdi; this
0x180021100  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180021105  mov     ebx, eax
0x180021107  test    eax, eax
0x180021109  js      short loc_180021133
0x18002110b  xor     ebx, ebx
0x18002110d  movsxd  rsi, ebx
0x180021110  lea     rcx, [rsp+2088h+String1]; lpString1
0x180021115  add     rsi, rsi
0x180021118  mov     rdx, [r13+rsi*8+0]; lpString2
0x18002111d  call    cs:__imp_lstrcmpiW
0x180021123  test    eax, eax
0x180021125  jz      short loc_180021160
0x180021127  inc     ebx
0x180021129  cmp     ebx, 0Eh
0x18002112c  jb      short loc_18002110D
0x18002112e  mov     ebx, 80020009h
0x180021133  mov     rcx, rbp; pv
0x180021136  call    cs:__imp_CoTaskMemFree
0x18002113c  mov     eax, ebx
0x18002113e  mov     rcx, [rsp+2088h+var_48]
0x180021146  xor     rcx, rsp; StackCookie
0x180021149  call    __security_check_cookie
0x18002114e  add     rsp, 2050h
0x180021155  pop     r15
0x180021157  pop     r14
0x180021159  pop     r13
0x18002115b  pop     rdi
0x18002115c  pop     rsi
0x18002115d  pop     rbp
0x18002115e  pop     rbx
0x18002115f  retn
0x180021160  mov     rsi, [r13+rsi*8+8]
0x180021165  test    rsi, rsi
0x180021168  jz      short loc_18002112E
0x18002116a  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x18002116f  mov     rcx, rdi; this
0x180021172  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180021177  mov     ebx, eax
0x180021179  test    eax, eax
0x18002117b  js      short loc_180021133
0x18002117d  mov     eax, 7Bh ; '{'
0x180021182  cmp     ax, [rsp+2088h+String1]
0x180021187  jnz     short loc_18002112E
0x180021189  mov     [rsp+2088h+var_2068], 0; int
0x180021191  mov     r8, rsi; HKEY
0x180021194  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180021199  mov     rcx, rdi; this
0x18002119c  test    r15d, r15d
0x18002119f  jz      short loc_1800211D5
0x1800211a1  mov     r14, [rdi]
0x1800211a4  mov     r9d, r15d; int
0x1800211a7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800211ac  mov     ebx, eax
0x1800211ae  test    eax, eax
0x1800211b0  jns     short loc_1800211E7
0x1800211b2  xor     r9d, r9d; int
0x1800211b5  mov     [rdi], r14
0x1800211b8  mov     r8, rsi; HKEY
0x1800211bb  mov     [rsp+2088h+var_2068], 0; int
0x1800211c3  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800211c8  mov     rcx, rdi; this
0x1800211cb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800211d0  jmp     loc_180021133
0x1800211d5  xor     r9d, r9d; int
0x1800211d8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800211dd  mov     ebx, eax
0x1800211df  test    eax, eax
0x1800211e1  js      loc_180021133
0x1800211e7  mov     r8, [rdi]
0x1800211ea  movzx   edx, word ptr [r8]
0x1800211ee  mov     ecx, edx
0x1800211f0  sub     ecx, 9
0x1800211f3  jz      short loc_180021204
0x1800211f5  sub     ecx, 1
0x1800211f8  jz      short loc_180021204
0x1800211fa  sub     ecx, 3
0x1800211fd  jz      short loc_180021204
0x1800211ff  cmp     ecx, 13h
0x180021202  jnz     short loc_180021212
0x180021204  mov     rcx, r8; lpsz
0x180021207  call    cs:__imp_CharNextW
0x18002120d  mov     [rdi], rax
0x180021210  jmp     short loc_1800211E7
0x180021212  xor     eax, eax
0x180021214  cmp     ax, dx
0x180021217  jnz     loc_1800210F8
0x18002121d  jmp     loc_180021133
```
