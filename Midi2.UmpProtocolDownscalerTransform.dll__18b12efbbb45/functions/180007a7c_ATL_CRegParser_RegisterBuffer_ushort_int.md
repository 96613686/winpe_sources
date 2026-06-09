# ATL::CRegParser::RegisterBuffer(ushort *,int)

- ea: `0x180007a7c`
- end: `0x180007c06`
- name: `?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z`
- size: `394`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007c0c`

## callees

- `0x180002e70`
- `0x1800072bc`
- `0x18000746c`
- `0x180007a7c`
- `0x180007dec`
- `0x180012080`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007b1a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007beb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180007beb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007b01`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180007b01`

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
0x180007a7c  push    rbx
0x180007a7e  push    rbp
0x180007a7f  push    rsi
0x180007a80  push    rdi
0x180007a81  push    r13
0x180007a83  push    r14
0x180007a85  push    r15
0x180007a87  mov     eax, 2050h
0x180007a8c  call    _alloca_probe
0x180007a91  sub     rsp, rax
0x180007a94  mov     rax, cs:__security_cookie
0x180007a9b  xor     rax, rsp
0x180007a9e  mov     [rsp+2088h+var_48], rax
0x180007aa6  mov     r15d, r8d
0x180007aa9  mov     [rsp+2088h+pv], 0
0x180007ab2  lea     r8, [rsp+2088h+pv]; unsigned __int16 **
0x180007ab7  mov     rdi, rcx
0x180007aba  call    ?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z; ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)
0x180007abf  mov     ebx, eax
0x180007ac1  test    eax, eax
0x180007ac3  js      short loc_180007B22
0x180007ac5  mov     rbp, [rsp+2088h+pv]
0x180007aca  xor     eax, eax
0x180007acc  mov     [rdi], rbp
0x180007acf  cmp     ax, [rbp+0]
0x180007ad3  jz      short loc_180007B17
0x180007ad5  lea     r13, ?map@?1??HKeyFromString@CRegParser@ATL@@KAPEAUHKEY__@@PEAG@Z@4QBUkeymap@?1??123@KAPEAU4@0@Z@B; `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::keymap const near * const `ATL::CRegParser::HKeyFromString(ushort *)'::`2'::map
0x180007adc  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007ae1  mov     rcx, rdi; this
0x180007ae4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007ae9  mov     ebx, eax
0x180007aeb  test    eax, eax
0x180007aed  js      short loc_180007B17
0x180007aef  xor     ebx, ebx
0x180007af1  movsxd  rsi, ebx
0x180007af4  lea     rcx, [rsp+2088h+String1]; lpString1
0x180007af9  add     rsi, rsi
0x180007afc  mov     rdx, [r13+rsi*8+0]; lpString2
0x180007b01  call    cs:__imp_lstrcmpiW
0x180007b07  test    eax, eax
0x180007b09  jz      short loc_180007B44
0x180007b0b  inc     ebx
0x180007b0d  cmp     ebx, 0Eh
0x180007b10  jb      short loc_180007AF1
0x180007b12  mov     ebx, 80020009h
0x180007b17  mov     rcx, rbp; pv
0x180007b1a  call    cs:__imp_CoTaskMemFree
0x180007b20  mov     eax, ebx
0x180007b22  mov     rcx, [rsp+2088h+var_48]
0x180007b2a  xor     rcx, rsp; StackCookie
0x180007b2d  call    __security_check_cookie
0x180007b32  add     rsp, 2050h
0x180007b39  pop     r15
0x180007b3b  pop     r14
0x180007b3d  pop     r13
0x180007b3f  pop     rdi
0x180007b40  pop     rsi
0x180007b41  pop     rbp
0x180007b42  pop     rbx
0x180007b43  retn
0x180007b44  mov     rsi, [r13+rsi*8+8]
0x180007b49  test    rsi, rsi
0x180007b4c  jz      short loc_180007B12
0x180007b4e  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007b53  mov     rcx, rdi; this
0x180007b56  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007b5b  mov     ebx, eax
0x180007b5d  test    eax, eax
0x180007b5f  js      short loc_180007B17
0x180007b61  mov     eax, 7Bh ; '{'
0x180007b66  cmp     ax, [rsp+2088h+String1]
0x180007b6b  jnz     short loc_180007B12
0x180007b6d  mov     [rsp+2088h+var_2068], 0; int
0x180007b75  mov     r8, rsi; HKEY
0x180007b78  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007b7d  mov     rcx, rdi; this
0x180007b80  test    r15d, r15d
0x180007b83  jz      short loc_180007BB9
0x180007b85  mov     r14, [rdi]
0x180007b88  mov     r9d, r15d; int
0x180007b8b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007b90  mov     ebx, eax
0x180007b92  test    eax, eax
0x180007b94  jns     short loc_180007BCB
0x180007b96  xor     r9d, r9d; int
0x180007b99  mov     [rdi], r14
0x180007b9c  mov     r8, rsi; HKEY
0x180007b9f  mov     [rsp+2088h+var_2068], 0; int
0x180007ba7  lea     rdx, [rsp+2088h+String1]; unsigned __int16 *
0x180007bac  mov     rcx, rdi; this
0x180007baf  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007bb4  jmp     loc_180007B17
0x180007bb9  xor     r9d, r9d; int
0x180007bbc  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180007bc1  mov     ebx, eax
0x180007bc3  test    eax, eax
0x180007bc5  js      loc_180007B17
0x180007bcb  mov     r8, [rdi]
0x180007bce  movzx   edx, word ptr [r8]
0x180007bd2  mov     ecx, edx
0x180007bd4  sub     ecx, 9
0x180007bd7  jz      short loc_180007BE8
0x180007bd9  sub     ecx, 1
0x180007bdc  jz      short loc_180007BE8
0x180007bde  sub     ecx, 3
0x180007be1  jz      short loc_180007BE8
0x180007be3  cmp     ecx, 13h
0x180007be6  jnz     short loc_180007BF6
0x180007be8  mov     rcx, r8; lpsz
0x180007beb  call    cs:__imp_CharNextW
0x180007bf1  mov     [rdi], rax
0x180007bf4  jmp     short loc_180007BCB
0x180007bf6  xor     eax, eax
0x180007bf8  cmp     ax, dx
0x180007bfb  jnz     loc_180007ADC
0x180007c01  jmp     loc_180007B17
```
