# ATL::CRegObject::ResourceUnregisterSz(ushort const *,ushort const *,ushort const *)

- ea: `0x1800061ec`
- end: `0x180006403`
- name: `?ResourceUnregisterSz@CRegObject@ATL@@QEAAJPEBG00@Z`
- size: `535`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, LPCWCH lpWideCharStr, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006b14`

## callees

- `0x1800037f4`
- `0x1800050c0`
- `0x1800061ec`
- `0x180007034`
- `0x18000b640`
- `0x18000b700`

## import_xrefs

- `msvcrt!free` at `0x1800063ad`
- `msvcrt!free` at `0x1800063c4`
- `msvcrt!free` at `0x1800063ad`
- `msvcrt!free` at `0x1800063c4`
- `msvcrt!malloc` at `0x1800062aa`
- `msvcrt!malloc` at `0x180006329`
- `msvcrt!malloc` at `0x1800062aa`
- `msvcrt!malloc` at `0x180006329`
- `KERNEL32!WideCharToMultiByte` at `0x1800062ef`
- `KERNEL32!WideCharToMultiByte` at `0x180006373`
- `KERNEL32!WideCharToMultiByte` at `0x1800062ef`
- `KERNEL32!WideCharToMultiByte` at `0x180006373`

## string_xrefs

- `0x180006367`: `REGISTRY`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegObject::ResourceUnregisterSz(
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
    v18 = ATL::CRegObject::RegisterFromResource(this, a2, v14, v17, 0);
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
0x1800061ec  push    rbp
0x1800061ee  push    rbx
0x1800061ef  push    rsi
0x1800061f0  push    rdi
0x1800061f1  push    r12
0x1800061f3  push    r13
0x1800061f5  push    r14
0x1800061f7  push    r15
0x1800061f9  sub     rsp, 58h
0x1800061fd  lea     rbp, [rsp+40h]
0x180006202  mov     rax, cs:__security_cookie
0x180006209  xor     rax, rbp
0x18000620c  mov     [rbp+50h+var_48], rax
0x180006210  mov     r14, r8
0x180006213  mov     r15, rdx
0x180006216  mov     r12, rcx
0x180006219  xor     r13d, r13d
0x18000621c  mov     ebx, r13d
0x18000621f  mov     qword ptr [rbp+50h+MultiByteStr], rbx
0x180006223  test    r8, r8
0x180006226  jz      loc_1800063D6
0x18000622c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006230  inc     rax
0x180006233  cmp     [r8+rax*2], r13w
0x180006238  jnz     short loc_180006230
0x18000623a  inc     eax
0x18000623c  movsxd  rcx, eax
0x18000623f  lea     rsi, [rcx+rcx]
0x180006243  mov     eax, 80000000h
0x180006248  add     rax, rsi
0x18000624b  mov     ecx, 0FFFFFFFFh
0x180006250  cmp     rax, rcx
0x180006253  ja      loc_1800062FF
0x180006259  movsxd  rdi, esi
0x18000625c  cmp     esi, 400h
0x180006262  jg      short loc_180006296
0x180006264  mov     rcx, rdi; this
0x180006267  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000626c  test    al, al
0x18000626e  jz      short loc_180006296
0x180006270  lea     rax, [rdi+0Fh]
0x180006274  cmp     rax, rdi
0x180006277  ja      short loc_180006283
0x180006279  mov     rax, 0FFFFFFFFFFFFFF0h
0x180006283  and     rax, 0FFFFFFFFFFFFFFF0h
0x180006287  call    _alloca_probe
0x18000628c  sub     rsp, rax
0x18000628f  lea     rdi, [rsp+90h+MultiByteStr]
0x180006294  jmp     short loc_1800062C8
0x180006296  mov     rax, rdi
0x180006299  not     rax
0x18000629c  cmp     rax, 10h
0x1800062a0  jb      loc_1800063F8
0x1800062a6  lea     rcx, [rdi+10h]; Size
0x1800062aa  call    cs:__imp_malloc
0x1800062b0  test    rax, rax
0x1800062b3  jnz     short loc_1800062BA
0x1800062b5  mov     rdi, r13
0x1800062b8  jmp     short loc_1800062C8
0x1800062ba  mov     [rax], r13
0x1800062bd  mov     rbx, rax
0x1800062c0  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x1800062c4  lea     rdi, [rax+10h]
0x1800062c8  test    rdi, rdi
0x1800062cb  jz      short loc_1800062FF
0x1800062cd  mov     [rdi], r13b
0x1800062d0  mov     [rsp+90h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800062d5  mov     [rsp+90h+lpDefaultChar], r13; lpDefaultChar
0x1800062da  mov     [rsp+90h+cbMultiByte], esi; cbMultiByte
0x1800062de  mov     [rsp+90h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800062e3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800062e7  mov     r8, r14; lpWideCharStr
0x1800062ea  xor     edx, edx; dwFlags
0x1800062ec  lea     ecx, [rdx+3]; CodePage
0x1800062ef  call    cs:__imp_WideCharToMultiByte
0x1800062f5  neg     eax
0x1800062f7  sbb     rsi, rsi
0x1800062fa  and     rsi, rdi
0x1800062fd  jmp     short loc_180006302
0x1800062ff  mov     rsi, r13
0x180006302  mov     r14d, 12h
0x180006308  mov     ecx, r14d; this
0x18000630b  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180006310  test    al, al
0x180006312  jz      short loc_180006324
0x180006314  mov     eax, dword ptr [rsp+90h+var_90]
0x180006317  sub     rsp, 20h
0x18000631b  lea     rdi, [rsp+0B0h+lpMultiByteStr]
0x180006320  mov     eax, [rdi]
0x180006322  jmp     short loc_180006347
0x180006324  mov     ecx, 22h ; '"'; Size
0x180006329  call    cs:__imp_malloc
0x18000632f  test    rax, rax
0x180006332  jnz     short loc_180006339
0x180006334  mov     rdi, r13
0x180006337  jmp     short loc_180006347
0x180006339  mov     [rax], rbx
0x18000633c  mov     rbx, rax
0x18000633f  mov     qword ptr [rbp+50h+MultiByteStr], rax
0x180006343  lea     rdi, [rax+10h]
0x180006347  test    rdi, rdi
0x18000634a  jz      short loc_180006383
0x18000634c  mov     [rdi], r13b
0x18000634f  mov     [rsp+0B0h+var_78], r13; lpUsedDefaultChar
0x180006354  mov     [rsp+0B0h+var_80], r13; lpDefaultChar
0x180006359  mov     [rsp+0B0h+var_88], r14d; cbMultiByte
0x18000635e  mov     [rsp+0B0h+var_90], rdi; lpMultiByteStr
0x180006363  or      r9d, 0FFFFFFFFh; cchWideChar
0x180006367  lea     r8, WideCharStr; "REGISTRY"
0x18000636e  xor     edx, edx; dwFlags
0x180006370  lea     ecx, [rdx+3]; CodePage
0x180006373  call    cs:__imp_WideCharToMultiByte
0x180006379  neg     eax
0x18000637b  sbb     r9, r9
0x18000637e  and     r9, rdi
0x180006381  jmp     short loc_180006386
0x180006383  mov     r9, r13; char *
0x180006386  test    rsi, rsi
0x180006389  jz      short loc_1800063BC
0x18000638b  test    r9, r9
0x18000638e  jz      short loc_1800063BC
0x180006390  mov     dword ptr [rsp+0B0h+var_90], r13d; int
0x180006395  mov     r8, rsi; char *
0x180006398  mov     rdx, r15; unsigned __int16 *
0x18000639b  mov     rcx, r12; this
0x18000639e  call    ?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z; ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)
0x1800063a3  mov     edi, eax
0x1800063a5  jmp     short loc_1800063B3
0x1800063a7  mov     rcx, rbx; Block
0x1800063aa  mov     rbx, [rbx]
0x1800063ad  call    cs:__imp_free
0x1800063b3  test    rbx, rbx
0x1800063b6  jnz     short loc_1800063A7
0x1800063b8  mov     eax, edi
0x1800063ba  jmp     short loc_1800063DB
0x1800063bc  jmp     short loc_1800063CA
0x1800063be  mov     rcx, rbx; Block
0x1800063c1  mov     rbx, [rbx]
0x1800063c4  call    cs:__imp_free
0x1800063ca  test    rbx, rbx
0x1800063cd  jnz     short loc_1800063BE
0x1800063cf  mov     eax, 8007000Eh
0x1800063d4  jmp     short loc_1800063DB
0x1800063d6  mov     eax, 80070057h
0x1800063db  mov     rcx, [rbp+50h+var_48]
0x1800063df  xor     rcx, rbp; StackCookie
0x1800063e2  call    __security_check_cookie
0x1800063e7  lea     rsp, [rbp+18h]
0x1800063eb  pop     r15
0x1800063ed  pop     r14
0x1800063ef  pop     r13
0x1800063f1  pop     r12
0x1800063f3  pop     rdi
0x1800063f4  pop     rsi
0x1800063f5  pop     rbx
0x1800063f6  pop     rbp
0x1800063f7  retn
0x1800063f8  mov     ecx, 80070057h; int
0x1800063fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
