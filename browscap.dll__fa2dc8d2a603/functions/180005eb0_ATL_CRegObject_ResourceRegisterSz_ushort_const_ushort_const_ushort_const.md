# ATL::CRegObject::ResourceRegisterSz(ushort const *,ushort const *,ushort const *)

- ea: `0x180005eb0`
- end: `0x1800060ca`
- name: `?ResourceRegisterSz@CRegObject@ATL@@QEAAJPEBG00@Z`
- size: `538`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, LPCWCH lpWideCharStr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006b14`

## callees

- `0x1800037f4`
- `0x1800050c0`
- `0x180005eb0`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!free` at `0x180006074`
- `msvcrt!free` at `0x18000608b`
- `msvcrt!free` at `0x180006074`
- `msvcrt!free` at `0x18000608b`
- `msvcrt!malloc` at `0x180005f6e`
- `msvcrt!malloc` at `0x180005fed`
- `msvcrt!malloc` at `0x180005f6e`
- `msvcrt!malloc` at `0x180005fed`
- `KERNEL32!WideCharToMultiByte` at `0x180005fb3`
- `KERNEL32!WideCharToMultiByte` at `0x180006037`
- `KERNEL32!WideCharToMultiByte` at `0x180005fb3`
- `KERNEL32!WideCharToMultiByte` at `0x180006037`

## string_xrefs

- `0x18000602b`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::ResourceRegisterSz(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        LPCWCH lpWideCharStr,
        const unsigned __int16 *a4)
{
  _QWORD *v7; // rbx
  __int64 v8; // rax
  __int64 cbMultiByte; // rsi
  unsigned __int64 v10; // rax
  void *v11; // rsp
  CHAR *v12; // rdi
  _QWORD *v13; // rax
  const char *v14; // rsi
  LPSTR *p_lpMultiByteStr; // rdi
  _QWORD *v16; // rax
  const char *v17; // r9
  unsigned int v18; // edi
  void *v19; // rcx
  void *v21; // rcx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-20h] BYREF
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF

  v7 = 0;
  *(_QWORD *)MultiByteStr = 0;
  if ( !lpWideCharStr )
    return 2147942487LL;
  v8 = -1;
  do
    ++v8;
  while ( lpWideCharStr[v8] );
  cbMultiByte = 2LL * ((int)v8 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_16;
  if ( (int)cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte,
         (unsigned __int64)a2) )
  {
    v10 = (int)cbMultiByte + 15LL;
    if ( v10 < (int)cbMultiByte )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    v12 = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
      ATL::AtlThrowImpl(-2147024809);
    v13 = malloc((int)cbMultiByte + 16LL);
    if ( v13 )
    {
      *v13 = 0;
      v7 = v13;
      *(_QWORD *)MultiByteStr = v13;
      v12 = (CHAR *)(v13 + 2);
    }
    else
    {
      v12 = 0;
    }
  }
  if ( v12 )
  {
    *v12 = 0;
    v14 = (const char *)((unsigned __int64)v12
                       & -(__int64)(WideCharToMultiByte(3u, 0, lpWideCharStr, -1, v12, cbMultiByte, 0, 0) != 0));
  }
  else
  {
LABEL_16:
    v14 = 0;
  }
  if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x12, (unsigned __int64)a2) )
  {
    p_lpMultiByteStr = &lpMultiByteStr;
  }
  else
  {
    v16 = malloc(0x22u);
    if ( v16 )
    {
      *v16 = v7;
      v7 = v16;
      *(_QWORD *)MultiByteStr = v16;
      p_lpMultiByteStr = (LPSTR *)(v16 + 2);
    }
    else
    {
      p_lpMultiByteStr = 0;
    }
  }
  if ( p_lpMultiByteStr )
  {
    *(_BYTE *)p_lpMultiByteStr = 0;
    v17 = (const char *)((unsigned __int64)p_lpMultiByteStr
                       & -(__int64)(WideCharToMultiByte(3u, 0, L"REGISTRY", -1, (LPSTR)p_lpMultiByteStr, 18, 0, 0) != 0));
  }
  else
  {
    v17 = 0;
  }
  if ( v14 && v17 )
  {
    v18 = ATL::CRegObject::RegisterFromResource(this, a2, v14, v17, 1);
    while ( v7 )
    {
      v19 = v7;
      v7 = (_QWORD *)*v7;
      free(v19);
    }
    return v18;
  }
  else
  {
    while ( v7 )
    {
      v21 = v7;
      v7 = (_QWORD *)*v7;
      free(v21);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180005eb0  push    rbp
0x180005eb2  push    rbx
0x180005eb3  push    rsi
0x180005eb4  push    rdi
0x180005eb5  push    r12
0x180005eb7  push    r13
0x180005eb9  push    r14
0x180005ebb  push    r15
0x180005ebd  sub     rsp, 58h
0x180005ec1  lea     rbp, [rsp+40h]
0x180005ec6  mov     rax, cs:__security_cookie
0x180005ecd  xor     rax, rbp
0x180005ed0  mov     [rbp+50h+var_48], rax
0x180005ed4  mov     r14, r8
0x180005ed7  mov     r15, rdx
0x180005eda  mov     r12, rcx
0x180005edd  xor     r13d, r13d
0x180005ee0  mov     ebx, r13d
0x180005ee3  mov     qword ptr [rbp+50h+MultiByteStr], rbx
0x180005ee7  test    r8, r8
0x180005eea  jz      loc_18000609D
0x180005ef0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ef4  inc     rax
0x180005ef7  cmp     [r8+rax*2], r13w
0x180005efc  jnz     short loc_180005EF4
0x180005efe  inc     eax
0x180005f00  movsxd  rcx, eax
0x180005f03  lea     rsi, [rcx+rcx]
0x180005f07  mov     eax, 80000000h
0x180005f0c  add     rax, rsi
0x180005f0f  mov     ecx, 0FFFFFFFFh
0x180005f14  cmp     rax, rcx
0x180005f17  ja      loc_180005FC3
0x180005f1d  movsxd  rdi, esi
0x180005f20  cmp     esi, 400h
0x180005f26  jg      short loc_180005F5A
0x180005f28  mov     rcx, rdi; this
0x180005f2b  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180005f30  test    al, al
0x180005f32  jz      short loc_180005F5A
0x180005f34  lea     rax, [rdi+0Fh]
0x180005f38  cmp     rax, rdi
0x180005f3b  ja      short loc_180005F47
0x180005f3d  mov     rax, 0FFFFFFFFFFFFFF0h
0x180005f47  and     rax, 0FFFFFFFFFFFFFFF0h
0x180005f4b  call    _alloca_probe
0x180005f50  sub     rsp, rax
0x180005f53  lea     rdi, [rsp+90h+MultiByteStr]
0x180005f58  jmp     short loc_180005F8C
0x180005f5a  mov     rax, rdi
0x180005f5d  not     rax
0x180005f60  cmp     rax, 10h
0x180005f64  jb      loc_1800060BF
0x180005f6a  lea     rcx, [rdi+10h]; Size
0x180005f6e  call    cs:__imp_malloc
0x180005f74  test    rax, rax
0x180005f77  jnz     short loc_180005F7E
0x180005f79  mov     rdi, r13
0x180005f7c  jmp     short loc_180005F8C
0x180005f7e  mov     [rax], r13
0x180005f81  mov     rbx, rax
0x180005f84  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180005f88  lea     rdi, [rax+10h]
0x180005f8c  test    rdi, rdi
0x180005f8f  jz      short loc_180005FC3
0x180005f91  mov     [rdi], r13b
0x180005f94  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180005f99  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x180005f9e  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x180005fa2  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x180005fa7  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005fab  mov     r8, r14; lpWideCharStr
0x180005fae  xor     edx, edx; dwFlags
0x180005fb0  lea     ecx, [rdx+3]; CodePage
0x180005fb3  call    cs:__imp_WideCharToMultiByte
0x180005fb9  neg     eax
0x180005fbb  sbb     rsi, rsi
0x180005fbe  and     rsi, rdi
0x180005fc1  jmp     short loc_180005FC6
0x180005fc3  mov     rsi, r13
0x180005fc6  mov     r14d, 12h
0x180005fcc  mov     ecx, r14d; this
0x180005fcf  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180005fd4  test    al, al
0x180005fd6  jz      short loc_180005FE8
0x180005fd8  mov     eax, dword ptr [rsp+90h+var_90]
0x180005fdb  sub     rsp, 20h
0x180005fdf  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x180005fe4  mov     eax, [rdi]
0x180005fe6  jmp     short loc_18000600B
0x180005fe8  mov     ecx, 22h ; '"'; Size
0x180005fed  call    cs:__imp_malloc
0x180005ff3  test    rax, rax
0x180005ff6  jnz     short loc_180005FFD
0x180005ff8  mov     rdi, r13
0x180005ffb  jmp     short loc_18000600B
0x180005ffd  mov     [rax], rbx
0x180006000  mov     rbx, rax
0x180006003  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180006007  lea     rdi, [rax+10h]
0x18000600b  test    rdi, rdi
0x18000600e  jz      short loc_180006047
0x180006010  mov     [rdi], r13b
0x180006013  mov     [rsp+0B0h+var_78], r13; lpUsedDefaultChar
0x180006018  mov     [rsp+0B0h+var_80], r13; lpDefaultChar
0x18000601d  mov     [rsp+0B0h+var_88], r14d; cbMultiByte
0x180006022  mov     [rsp+0B0h+var_90], rdi; lpMultiByteStr
0x180006027  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000602b  lea     r8, WideCharStr; "REGISTRY"
0x180006032  xor     edx, edx; dwFlags
0x180006034  lea     ecx, [rdx+3]; CodePage
0x180006037  call    cs:__imp_WideCharToMultiByte
0x18000603d  neg     eax
0x18000603f  sbb     r9, r9
0x180006042  and     r9, rdi
0x180006045  jmp     short loc_18000604A
0x180006047  mov     r9, r13; char *
0x18000604a  test    rsi, rsi
0x18000604d  jz      short loc_180006083
0x18000604f  test    r9, r9
0x180006052  jz      short loc_180006083
0x180006054  mov     dword ptr [rsp+0B0h+var_90], 1; int
0x18000605c  mov     r8, rsi; char *
0x18000605f  mov     rdx, r15; unsigned __int16 *
0x180006062  mov     rcx, r12; this
0x180006065  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x18000606a  mov     edi, eax
0x18000606c  jmp     short loc_18000607A
0x18000606e  mov     rcx, rbx; Block
0x180006071  mov     rbx, [rbx]
0x180006074  call    cs:__imp_free
0x18000607a  test    rbx, rbx
0x18000607d  jnz     short loc_18000606E
0x18000607f  mov     eax, edi
0x180006081  jmp     short loc_1800060A2
0x180006083  jmp     short loc_180006091
0x180006085  mov     rcx, rbx; Block
0x180006088  mov     rbx, [rbx]
0x18000608b  call    cs:__imp_free
0x180006091  test    rbx, rbx
0x180006094  jnz     short loc_180006085
0x180006096  mov     eax, 8007000Eh
0x18000609b  jmp     short loc_1800060A2
0x18000609d  mov     eax, 80070057h
0x1800060a2  mov     rcx, [rbp+50h+var_48]
0x1800060a6  xor     rcx, rbp; StackCookie
0x1800060a9  call    __security_check_cookie
0x1800060ae  lea     rsp, [rbp+18h]
0x1800060b2  pop     r15
0x1800060b4  pop     r14
0x1800060b6  pop     r13
0x1800060b8  pop     r12
0x1800060ba  pop     rdi
0x1800060bb  pop     rsi
0x1800060bc  pop     rbx
0x1800060bd  pop     rbp
0x1800060be  retn
0x1800060bf  mov     ecx, 80070057h; int
0x1800060c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
