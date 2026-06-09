# ATL::CRegistryVirtualMachine::GetStringAtLoc(ATL::RGSStrings *,ulong,ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>> &,wchar_t * *)

- ea: `0x18000fa28`
- end: `0x18000fc62`
- name: `?GetStringAtLoc@CRegistryVirtualMachine@ATL@@QEAAJPEAURGSStrings@2@KAEAV?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@2@PEAPEA_W@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, LPWSTR *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000cfb4`
- `0x18000ddf8`
- `0x180012b04`

## callees

- `0x1800026f0`
- `0x18000b410`
- `0x18000bf58`
- `0x18000cf28`
- `0x18000fa28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000faa4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000faa4`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000fb29`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000fb29`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000facc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fbf0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000facc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fbf0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb73`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000fb73`

## pseudocode

```c
__int64 __fastcall ATL::CRegistryVirtualMachine::GetStringAtLoc(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        LPWSTR *a5)
{
  WCHAR *v8; // rax
  LPWSTR v9; // rbx
  WCHAR i; // ax
  WCHAR v11; // ax
  WCHAR *v12; // rdi
  __int64 v13; // rax
  int v14; // eax
  int v15; // edi
  unsigned int v16; // edx
  _WORD *v17; // rdi
  int v18; // ebp
  __int64 v19; // [rsp+20h] [rbp-88h]
  WCHAR String2[32]; // [rsp+30h] [rbp-78h] BYREF

  v19 = -2;
  if ( !a5 )
    return 2147942487LL;
  v8 = *(WCHAR **)(a2 + 16LL * a3);
  *a5 = v8;
  if ( !v8 )
    return 1;
  if ( *(_BYTE *)(a2 + 16LL * a3 + 8) )
  {
    if ( *(_QWORD *)a4 )
    {
      free(*(void **)a4);
      *(_QWORD *)a4 = 0;
    }
    *(_QWORD *)(a4 + 8) = 0;
    v9 = *a5;
    *a5 = 0;
    for ( i = *v9; i; i = *v9 )
    {
      if ( i != 37 || (v9 = CharNextW(v9), v11 = *v9, *v9 == 37) )
      {
        ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(a4, v9);
      }
      else
      {
        if ( !v11 )
          return 2147500037LL;
        v12 = v9;
        while ( v11 != 37 )
        {
          v11 = *++v12;
          if ( !*v12 )
            return 2147500037LL;
        }
        if ( !v12 )
          return 2147500037LL;
        v13 = v12 - v9;
        if ( (int)v13 > 31 )
          return 2147500037LL;
        v14 = _o_wcsncpy_s(String2, 32, v9, (int)v13, v19);
        if ( v14 )
        {
          if ( v14 == 12 )
            ATL::AtlThrowImpl(-2147024882);
          if ( v14 == 22 || v14 == 34 )
            ATL::AtlThrowImpl(-2147024809);
          if ( v14 != 80 )
            ATL::AtlThrowImpl(-2147467259);
        }
        v9 = v12;
        v15 = 0;
        if ( *(int *)(a1 + 24) <= 0 )
          return 2147500037LL;
        while ( lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)(a1 + 8) + 8LL * v15), String2) )
        {
          if ( ++v15 >= *(_DWORD *)(a1 + 24) )
            return 2147500037LL;
        }
        if ( v15 == -1 )
          return 2147500037LL;
        if ( v15 < 0 || v15 >= *(_DWORD *)(a1 + 24) )
        {
          ATL::_AtlRaiseException(0xC000008C, v16);
          __debugbreak();
        }
        _mm_lfence();
        v17 = *(_WORD **)(*(_QWORD *)(a1 + 16) + 8LL * v15);
        if ( !v17 )
          return 2147500037LL;
        v18 = 0;
        if ( *v17 )
        {
          do
            ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(a4, &v17[v18++]);
          while ( v17[v18] );
        }
      }
      v9 = CharNextW(v9);
    }
    ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(a4, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18000fa28  mov     rax, rsp
0x18000fa2b  push    rbp
0x18000fa2c  push    rsi
0x18000fa2d  push    rdi
0x18000fa2e  push    r14
0x18000fa30  push    r15
0x18000fa32  sub     rsp, 80h
0x18000fa39  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x18000fa42  mov     [rax+10h], rbx
0x18000fa46  mov     rax, cs:__security_cookie
0x18000fa4d  xor     rax, rsp
0x18000fa50  mov     [rsp+0A8h+var_38], rax
0x18000fa55  mov     rsi, r9
0x18000fa58  mov     r14, rcx
0x18000fa5b  mov     rdi, [rsp+0A8h+arg_20]
0x18000fa63  xor     r15d, r15d
0x18000fa66  test    rdi, rdi
0x18000fa69  jnz     short loc_18000FA75
0x18000fa6b  mov     eax, 80070057h
0x18000fa70  jmp     loc_18000FC12
0x18000fa75  mov     ecx, r8d
0x18000fa78  add     rcx, rcx
0x18000fa7b  mov     rax, [rdx+rcx*8]
0x18000fa7f  mov     [rdi], rax
0x18000fa82  test    rax, rax
0x18000fa85  jnz     short loc_18000FA91
0x18000fa87  mov     eax, 1
0x18000fa8c  jmp     loc_18000FC12
0x18000fa91  cmp     [rdx+rcx*8+8], r15b
0x18000fa96  jz      loc_18000FC10
0x18000fa9c  mov     rcx, [r9]; Block
0x18000fa9f  test    rcx, rcx
0x18000faa2  jz      short loc_18000FAAD
0x18000faa4  call    cs:__imp_free
0x18000faaa  mov     [rsi], r15
0x18000faad  mov     [rsi+8], r15
0x18000fab1  mov     rbx, [rdi]
0x18000fab4  mov     [rdi], r15
0x18000fab7  movzx   eax, word ptr [rbx]
0x18000faba  jmp     loc_18000FBFC
0x18000fabf  cmp     ax, 25h ; '%'
0x18000fac3  jnz     loc_18000FBE2
0x18000fac9  mov     rcx, rbx; lpsz
0x18000facc  call    cs:__imp_CharNextW
0x18000fad2  mov     rbx, rax
0x18000fad5  movzx   eax, word ptr [rax]
0x18000fad8  cmp     ax, 25h ; '%'
0x18000fadc  jz      loc_18000FBE2
0x18000fae2  test    ax, ax
0x18000fae5  jz      short loc_18000FAFC
0x18000fae7  mov     rdi, rbx
0x18000faea  cmp     ax, 25h ; '%'
0x18000faee  jz      short loc_18000FB06
0x18000faf0  add     rdi, 2
0x18000faf4  movzx   eax, word ptr [rdi]
0x18000faf7  test    ax, ax
0x18000fafa  jnz     short loc_18000FAEA
0x18000fafc  mov     eax, 80004005h
0x18000fb01  jmp     loc_18000FC12
0x18000fb06  test    rdi, rdi
0x18000fb09  jz      short loc_18000FAFC
0x18000fb0b  mov     rax, rdi
0x18000fb0e  sub     rax, rbx
0x18000fb11  sar     rax, 1
0x18000fb14  cmp     eax, 1Fh
0x18000fb17  jg      short loc_18000FAFC
0x18000fb19  movsxd  r9, eax
0x18000fb1c  mov     r8, rbx
0x18000fb1f  mov     edx, 20h ; ' '
0x18000fb24  lea     rcx, [rsp+0A8h+String2]
0x18000fb29  call    cs:__imp__o_wcsncpy_s
0x18000fb2f  test    eax, eax
0x18000fb31  jz      short loc_18000FB57
0x18000fb33  cmp     eax, 0Ch
0x18000fb36  jz      loc_18000FC36
0x18000fb3c  cmp     eax, 16h
0x18000fb3f  jz      loc_18000FC57
0x18000fb45  cmp     eax, 22h ; '"'
0x18000fb48  jz      loc_18000FC57
0x18000fb4e  cmp     eax, 50h ; 'P'
0x18000fb51  jnz     loc_18000FC4C
0x18000fb57  mov     rbx, rdi
0x18000fb5a  mov     edi, r15d
0x18000fb5d  cmp     [r14+18h], r15d
0x18000fb61  jle     short loc_18000FAFC
0x18000fb63  movsxd  rax, edi
0x18000fb66  mov     rcx, [r14+8]
0x18000fb6a  lea     rdx, [rsp+0A8h+String2]; lpString2
0x18000fb6f  mov     rcx, [rcx+rax*8]; lpString1
0x18000fb73  call    cs:__imp_lstrcmpiW
0x18000fb79  test    eax, eax
0x18000fb7b  jz      short loc_18000FB8A
0x18000fb7d  inc     edi
0x18000fb7f  cmp     edi, [r14+18h]
0x18000fb83  jl      short loc_18000FB63
0x18000fb85  jmp     loc_18000FAFC
0x18000fb8a  cmp     edi, 0FFFFFFFFh
0x18000fb8d  jz      loc_18000FAFC
0x18000fb93  test    edi, edi
0x18000fb95  js      loc_18000FC41
0x18000fb9b  cmp     edi, [r14+18h]
0x18000fb9f  jge     loc_18000FC41
0x18000fba5  lfence
0x18000fba8  movsxd  rcx, edi
0x18000fbab  mov     rax, [r14+10h]
0x18000fbaf  mov     rdi, [rax+rcx*8]
0x18000fbb3  test    rdi, rdi
0x18000fbb6  jz      loc_18000FAFC
0x18000fbbc  mov     ebp, r15d
0x18000fbbf  cmp     [rdi], r15w
0x18000fbc3  jz      short loc_18000FBED
0x18000fbc5  movsxd  rax, ebp
0x18000fbc8  lea     rdx, [rdi+rax*2]
0x18000fbcc  mov     rcx, rsi
0x18000fbcf  call    ?Add@?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@ATL@@QEAAHAEB_W@Z; ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(wchar_t const &)
0x18000fbd4  inc     ebp
0x18000fbd6  movsxd  rax, ebp
0x18000fbd9  cmp     [rdi+rax*2], r15w
0x18000fbde  jnz     short loc_18000FBC5
0x18000fbe0  jmp     short loc_18000FBED
0x18000fbe2  mov     rdx, rbx
0x18000fbe5  mov     rcx, rsi
0x18000fbe8  call    ?Add@?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@ATL@@QEAAHAEB_W@Z; ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(wchar_t const &)
0x18000fbed  mov     rcx, rbx; lpsz
0x18000fbf0  call    cs:__imp_CharNextW
0x18000fbf6  mov     rbx, rax
0x18000fbf9  movzx   eax, word ptr [rax]
0x18000fbfc  test    ax, ax
0x18000fbff  jnz     loc_18000FABF
0x18000fc05  mov     rdx, rbx
0x18000fc08  mov     rcx, rsi
0x18000fc0b  call    ?Add@?$CSimpleArray@_WV?$CSimpleArrayEqualHelper@_W@ATL@@@ATL@@QEAAHAEB_W@Z; ATL::CSimpleArray<wchar_t,ATL::CSimpleArrayEqualHelper<wchar_t>>::Add(wchar_t const &)
0x18000fc10  xor     eax, eax
0x18000fc12  mov     rcx, [rsp+0A8h+var_38]
0x18000fc17  xor     rcx, rsp; StackCookie
0x18000fc1a  call    __security_check_cookie
0x18000fc1f  mov     rbx, [rsp+0A8h+arg_8]
0x18000fc27  add     rsp, 80h
0x18000fc2e  pop     r15
0x18000fc30  pop     r14
0x18000fc32  pop     rdi
0x18000fc33  pop     rsi
0x18000fc34  pop     rbp
0x18000fc35  retn
0x18000fc36  mov     ecx, 8007000Eh; int
0x18000fc3b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000fc41  mov     ecx, 0C000008Ch; unsigned int
0x18000fc46  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000fc4b  int     3; Trap to Debugger
0x18000fc4c  mov     ecx, 80004005h; int
0x18000fc51  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000fc57  mov     ecx, 80070057h; int
0x18000fc5c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
