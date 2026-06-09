# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180009954`
- end: `0x180009ade`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009ae4`

## callees

- `0x180004410`
- `0x180008f08`
- `0x1800090a8`
- `0x180009954`
- `0x180009cc4`
- `0x18003e3f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099f2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009ac3`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180009ac3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800099d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800099d9`

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
0x180009954  push    rbx
0x180009956  push    rbp
0x180009957  push    rsi
0x180009958  push    rdi
0x180009959  push    r13
0x18000995b  push    r14
0x18000995d  push    r15
0x18000995f  mov     eax, 2050h
0x180009964  call    _alloca_probe
0x180009969  sub     rsp, rax
0x18000996c  mov     rax, cs:__security_cookie
0x180009973  xor     rax, rsp
0x180009976  mov     [rsp+2088h+var_48], rax
0x18000997e  mov     r15d, r8d
0x180009981  mov     [rsp+2088h+pv], 0
0x18000998a  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x18000998f  mov     rdi, rcx
0x180009992  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180009997  mov     ebx, eax
0x180009999  test    eax, eax
0x18000999b  js      short loc_1800099FA
0x18000999d  mov     rbp, [rsp+2088h+pv]
0x1800099a2  xor     eax, eax
0x1800099a4  mov     [rdi], rbp
0x1800099a7  cmp     ax, [rbp+0]
0x1800099ab  jz      short loc_1800099EF
0x1800099ad  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x1800099b4  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x1800099b9  mov     rcx, rdi; this
0x1800099bc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800099c1  mov     ebx, eax
0x1800099c3  test    eax, eax
0x1800099c5  js      short loc_1800099EF
0x1800099c7  xor     ebx, ebx
0x1800099c9  movsxd  rsi, ebx
0x1800099cc  lea     rcx, [rsp+2088h+String1]; lpString1
0x1800099d1  add     rsi, rsi
0x1800099d4  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800099d9  call    cs:__imp_lstrcmpiW
0x1800099df  test    eax, eax
0x1800099e1  jz      short loc_180009A1C
0x1800099e3  inc     ebx
0x1800099e5  cmp     ebx, 0Eh
0x1800099e8  jb      short loc_1800099C9
0x1800099ea  mov     ebx, 80020009h
0x1800099ef  mov     rcx, rbp; pv
0x1800099f2  call    cs:__imp_CoTaskMemFree
0x1800099f8  mov     eax, ebx
0x1800099fa  mov     rcx, [rsp+2088h+var_48]
0x180009a02  xor     rcx, rsp; StackCookie
0x180009a05  call    __security_check_cookie
0x180009a0a  add     rsp, 2050h
0x180009a11  pop     r15
0x180009a13  pop     r14
0x180009a15  pop     r13
0x180009a17  pop     rdi
0x180009a18  pop     rsi
0x180009a19  pop     rbp
0x180009a1a  pop     rbx
0x180009a1b  retn
0x180009a1c  mov     rsi, [r13+rsi*8+8]
0x180009a21  test    rsi, rsi
0x180009a24  jz      short loc_1800099EA
0x180009a26  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009a2b  mov     rcx, rdi; this
0x180009a2e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009a33  mov     ebx, eax
0x180009a35  test    eax, eax
0x180009a37  js      short loc_1800099EF
0x180009a39  mov     eax, 7Bh ; '{'
0x180009a3e  cmp     ax, [rsp+2088h+String1]
0x180009a43  jnz     short loc_1800099EA
0x180009a45  mov     [rsp+2088h+var_2068], 0; int
0x180009a4d  mov     r8, rsi; HKEY
0x180009a50  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009a55  mov     rcx, rdi; this
0x180009a58  test    r15d, r15d
0x180009a5b  jz      short loc_180009A91
0x180009a5d  mov     r14, [rdi]
0x180009a60  mov     r9d, r15d; int
0x180009a63  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009a68  mov     ebx, eax
0x180009a6a  test    eax, eax
0x180009a6c  jns     short loc_180009AA3
0x180009a6e  xor     r9d, r9d; int
0x180009a71  mov     [rdi], r14
0x180009a74  mov     r8, rsi; HKEY
0x180009a77  mov     [rsp+2088h+var_2068], 0; int
0x180009a7f  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180009a84  mov     rcx, rdi; this
0x180009a87  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009a8c  jmp     loc_1800099EF
0x180009a91  xor     r9d, r9d; int
0x180009a94  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180009a99  mov     ebx, eax
0x180009a9b  test    eax, eax
0x180009a9d  js      loc_1800099EF
0x180009aa3  mov     r8, [rdi]
0x180009aa6  movzx   edx, word ptr [r8]
0x180009aaa  mov     ecx, edx
0x180009aac  sub     ecx, 9
0x180009aaf  jz      short loc_180009AC0
0x180009ab1  sub     ecx, 1
0x180009ab4  jz      short loc_180009AC0
0x180009ab6  sub     ecx, 3
0x180009ab9  jz      short loc_180009AC0
0x180009abb  cmp     ecx, 13h
0x180009abe  jnz     short loc_180009ACE
0x180009ac0  mov     rcx, r8; lpsz
0x180009ac3  call    cs:__imp_CharNextW
0x180009ac9  mov     [rdi], rax
0x180009acc  jmp     short loc_180009AA3
0x180009ace  xor     eax, eax
0x180009ad0  cmp     ax, dx
0x180009ad3  jnz     loc_1800099B4
0x180009ad9  jmp     loc_1800099EF
```
