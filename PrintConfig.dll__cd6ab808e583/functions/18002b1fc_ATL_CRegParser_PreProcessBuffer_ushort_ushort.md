# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18002b1fc`
- end: `0x18002b4e0`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `740`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b6f8`

## callees

- `0x1800032e0`
- `0x18001047c`
- `0x180027d90`
- `0x18002b1fc`
- `0x18002d04c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002b348`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002b348`
- `KERNEL32!LeaveCriticalSection` at `0x18002b3b4`
- `KERNEL32!LeaveCriticalSection` at `0x18002b3b4`
- `KERNEL32!EnterCriticalSection` at `0x18002b37e`
- `KERNEL32!EnterCriticalSection` at `0x18002b37e`
- `KERNEL32!lstrcmpiW` at `0x18002b39c`
- `KERNEL32!lstrcmpiW` at `0x18002b39c`
- `USER32!CharNextW` at `0x18002b2d9`
- `USER32!CharNextW` at `0x18002b30a`
- `USER32!CharNextW` at `0x18002b415`
- `USER32!CharNextW` at `0x18002b43e`
- `USER32!CharNextW` at `0x18002b2d9`
- `USER32!CharNextW` at `0x18002b30a`
- `USER32!CharNextW` at `0x18002b415`
- `USER32!CharNextW` at `0x18002b43e`
- `ole32!CoTaskMemAlloc` at `0x18002b28f`
- `ole32!CoTaskMemAlloc` at `0x18002b28f`
- `ole32!CoTaskMemFree` at `0x18002b2ad`
- `ole32!CoTaskMemFree` at `0x18002b469`
- `ole32!CoTaskMemFree` at `0x18002b2ad`
- `ole32!CoTaskMemFree` at `0x18002b469`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  int v21; // edx
  unsigned int v22; // r8d
  const unsigned __int16 *v23; // rbx
  __int64 v24; // r8
  const WCHAR *i; // rax
  unsigned int v26; // ebx
  _DWORD v27[2]; // [rsp+28h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-41h]
  __int64 v29; // [rsp+38h] [rbp-39h]
  __int64 v30; // [rsp+40h] [rbp-31h]
  WCHAR String2[32]; // [rsp+48h] [rbp-29h] BYREF

  v29 = -2;
  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v27[0] = 0;
  v27[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v8);
    v10 = v9;
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    v10 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_51:
    v26 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v15, 1) )
      goto LABEL_55;
LABEL_49:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_51;
    }
  }
  v13 = CharNextW(v4);
  *this = v13;
  v14 = *v13;
  if ( *v13 == 37 )
  {
    v15 = v13;
    goto LABEL_48;
  }
  if ( !v13 )
    goto LABEL_54;
  v16 = 0;
  while ( v14 )
  {
    if ( v14 == 37 )
    {
      v16 = v13;
      break;
    }
    v13 = CharNextW(v13);
    v14 = *v13;
  }
  if ( !v16 )
    goto LABEL_54;
  v17 = v16 - *this;
  if ( v17 > 31 )
  {
    v26 = -2147467259;
    goto LABEL_52;
  }
  v18 = _o_wcsncpy_s(String2, 32, *this, (int)v17);
  if ( v18 )
  {
    if ( v18 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v18 == 22 || v18 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v18 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v19 = this[1];
  EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  v20 = 0;
  if ( *((int *)v19 + 6) <= 0 )
    goto LABEL_34;
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), String2) )
  {
    if ( ++v20 >= *((_DWORD *)v19 + 6) )
      goto LABEL_34;
  }
  if ( v20 == -1 )
  {
LABEL_34:
    v23 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v21, v22);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v23 )
  {
LABEL_54:
    v26 = -2147352567;
    goto LABEL_52;
  }
  v30 = 0;
  v24 = -1;
  do
    ++v24;
  while ( v23[v24] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v27, v23, v24) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v26 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v26;
}

```

## disassembly

```asm
0x18002b1fc  mov     rax, rsp
0x18002b1ff  push    rbp
0x18002b200  push    rsi
0x18002b201  push    rdi
0x18002b202  push    r12
0x18002b204  push    r13
0x18002b206  push    r14
0x18002b208  push    r15
0x18002b20a  lea     rbp, [rax-5Fh]
0x18002b20e  sub     rsp, 90h
0x18002b215  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18002b21d  mov     [rax+10h], rbx
0x18002b221  mov     rax, cs:__security_cookie
0x18002b228  xor     rax, rsp
0x18002b22b  mov     [rbp+57h+var_40], rax
0x18002b22f  mov     r12, r8
0x18002b232  mov     rbx, rdx
0x18002b235  mov     r14, rcx
0x18002b238  xor     r13d, r13d
0x18002b23b  test    rdx, rdx
0x18002b23e  jz      loc_18002B488
0x18002b244  test    r8, r8
0x18002b247  jz      loc_18002B488
0x18002b24d  mov     [r8], r13
0x18002b250  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b254  inc     rax
0x18002b257  cmp     [rdx+rax*2], r13w
0x18002b25c  jnz     short loc_18002B254
0x18002b25e  add     eax, eax
0x18002b260  mov     ecx, 3E8h
0x18002b265  cmp     eax, 64h ; 'd'
0x18002b268  cmovl   eax, ecx
0x18002b26b  mov     [rbp+57h+var_A0], r13d
0x18002b26f  mov     [rbp+57h+var_9C], eax
0x18002b272  mov     ecx, eax
0x18002b274  add     rcx, rcx
0x18002b277  mov     eax, 0FFFFFFFFh
0x18002b27c  cmp     rcx, rax
0x18002b27f  jbe     short loc_18002B28D
0x18002b281  mov     rax, r13
0x18002b284  mov     rdx, r13
0x18002b287  mov     [rbp+57h+pv], rdx
0x18002b28b  jmp     short loc_18002B2A5
0x18002b28d  mov     ecx, ecx; cb
0x18002b28f  call    cs:__imp_CoTaskMemAlloc
0x18002b295  mov     rdx, rax
0x18002b298  mov     [rbp+57h+pv], rax
0x18002b29c  test    rax, rax
0x18002b29f  jz      short loc_18002B2A5
0x18002b2a1  mov     [rax], r13w
0x18002b2a5  test    rax, rax
0x18002b2a8  jnz     short loc_18002B2BD
0x18002b2aa  mov     rcx, rax; pv
0x18002b2ad  call    cs:__imp_CoTaskMemFree
0x18002b2b3  mov     eax, 8007000Eh
0x18002b2b8  jmp     loc_18002B48D
0x18002b2bd  mov     [r14], rbx
0x18002b2c0  movzx   eax, word ptr [rbx]
0x18002b2c3  test    ax, ax
0x18002b2c6  jz      loc_18002B45A
0x18002b2cc  cmp     ax, 25h ; '%'
0x18002b2d0  jnz     loc_18002B425
0x18002b2d6  mov     rcx, rbx; lpsz
0x18002b2d9  call    cs:__imp_CharNextW
0x18002b2df  mov     [r14], rax
0x18002b2e2  movzx   ecx, word ptr [rax]
0x18002b2e5  cmp     cx, 25h ; '%'
0x18002b2e9  jnz     short loc_18002B2F3
0x18002b2eb  mov     rdx, rax
0x18002b2ee  jmp     loc_18002B428
0x18002b2f3  test    rax, rax
0x18002b2f6  jz      loc_18002B47A
0x18002b2fc  mov     rdi, r13
0x18002b2ff  jmp     short loc_18002B313
0x18002b301  cmp     cx, 25h ; '%'
0x18002b305  jz      short loc_18002B31A
0x18002b307  mov     rcx, rax; lpsz
0x18002b30a  call    cs:__imp_CharNextW
0x18002b310  movzx   ecx, word ptr [rax]
0x18002b313  test    cx, cx
0x18002b316  jnz     short loc_18002B301
0x18002b318  jmp     short loc_18002B31D
0x18002b31a  mov     rdi, rax
0x18002b31d  test    rdi, rdi
0x18002b320  jz      loc_18002B47A
0x18002b326  mov     rax, rdi
0x18002b329  sub     rax, [r14]
0x18002b32c  sar     rax, 1
0x18002b32f  cmp     rax, 1Fh
0x18002b333  jg      loc_18002B473
0x18002b339  movsxd  r9, eax
0x18002b33c  mov     r8, [r14]
0x18002b33f  mov     edx, 20h ; ' '
0x18002b344  lea     rcx, [rbp+57h+String2]
0x18002b348  call    cs:__imp__o_wcsncpy_s
0x18002b34e  test    eax, eax
0x18002b350  jz      short loc_18002B376
0x18002b352  cmp     eax, 0Ch
0x18002b355  jz      loc_18002B4D5
0x18002b35b  cmp     eax, 16h
0x18002b35e  jz      loc_18002B4CA
0x18002b364  cmp     eax, 22h ; '"'
0x18002b367  jz      loc_18002B4CA
0x18002b36d  cmp     eax, 50h ; 'P'
0x18002b370  jnz     loc_18002B4BF
0x18002b376  mov     rsi, [r14+8]
0x18002b37a  lea     rcx, [rsi+20h]; lpCriticalSection
0x18002b37e  call    cs:__imp_EnterCriticalSection
0x18002b384  mov     ebx, r13d
0x18002b387  cmp     [rsi+18h], r13d
0x18002b38b  jle     short loc_18002B3AD
0x18002b38d  movsxd  rax, ebx
0x18002b390  mov     rcx, [rsi+8]
0x18002b394  lea     rdx, [rbp+57h+String2]; lpString2
0x18002b398  mov     rcx, [rcx+rax*8]; lpString1
0x18002b39c  call    cs:__imp_lstrcmpiW
0x18002b3a2  test    eax, eax
0x18002b3a4  jz      short loc_18002B3EF
0x18002b3a6  inc     ebx
0x18002b3a8  cmp     ebx, [rsi+18h]
0x18002b3ab  jl      short loc_18002B38D
0x18002b3ad  mov     rbx, r13
0x18002b3b0  lea     rcx, [rsi+20h]; lpCriticalSection
0x18002b3b4  call    cs:__imp_LeaveCriticalSection
0x18002b3ba  test    rbx, rbx
0x18002b3bd  jz      loc_18002B47A
0x18002b3c3  mov     [rbp+57h+var_88], r13
0x18002b3c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b3cb  inc     r8; int
0x18002b3ce  cmp     [rbx+r8*2], r13w
0x18002b3d3  jnz     short loc_18002B3CB
0x18002b3d5  mov     rdx, rbx; unsigned __int16 *
0x18002b3d8  lea     rcx, [rbp+57h+var_A0]; this
0x18002b3dc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002b3e1  nop
0x18002b3e2  test    eax, eax
0x18002b3e4  jz      loc_18002B481
0x18002b3ea  mov     rax, [r14]
0x18002b3ed  jmp     short loc_18002B41E
0x18002b3ef  cmp     ebx, 0FFFFFFFFh
0x18002b3f2  jz      short loc_18002B3AD
0x18002b3f4  test    ebx, ebx
0x18002b3f6  js      loc_18002B4B4
0x18002b3fc  cmp     ebx, [rsi+18h]
0x18002b3ff  jge     loc_18002B4B4
0x18002b405  movsxd  rcx, ebx
0x18002b408  mov     rax, [rsi+10h]
0x18002b40c  mov     rbx, [rax+rcx*8]
0x18002b410  jmp     short loc_18002B3B0
0x18002b412  mov     rcx, rax; lpsz
0x18002b415  call    cs:__imp_CharNextW
0x18002b41b  mov     [r14], rax
0x18002b41e  cmp     rax, rdi
0x18002b421  jnz     short loc_18002B412
0x18002b423  jmp     short loc_18002B43B
0x18002b425  mov     rdx, rbx; unsigned __int16 *
0x18002b428  mov     r8d, 1; int
0x18002b42e  lea     rcx, [rbp+57h+var_A0]; this
0x18002b432  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002b437  test    eax, eax
0x18002b439  jz      short loc_18002B481
0x18002b43b  mov     rcx, [r14]; lpsz
0x18002b43e  call    cs:__imp_CharNextW
0x18002b444  mov     rbx, rax
0x18002b447  mov     [r14], rax
0x18002b44a  movzx   eax, word ptr [rax]
0x18002b44d  test    ax, ax
0x18002b450  jnz     loc_18002B2CC
0x18002b456  mov     rdx, [rbp+57h+pv]
0x18002b45a  mov     ebx, r13d
0x18002b45d  mov     [rbp+57h+pv], r13
0x18002b461  mov     [r12], rdx
0x18002b465  mov     rcx, [rbp+57h+pv]; pv
0x18002b469  call    cs:__imp_CoTaskMemFree
0x18002b46f  mov     eax, ebx
0x18002b471  jmp     short loc_18002B48D
0x18002b473  mov     ebx, 80004005h
0x18002b478  jmp     short loc_18002B465
0x18002b47a  mov     ebx, 80020009h
0x18002b47f  jmp     short loc_18002B465
0x18002b481  mov     ebx, 8007000Eh
0x18002b486  jmp     short loc_18002B465
0x18002b488  mov     eax, 80004003h
0x18002b48d  mov     rcx, [rbp+57h+var_40]
0x18002b491  xor     rcx, rsp; StackCookie
0x18002b494  call    __security_check_cookie
0x18002b499  mov     rbx, [rsp+0C0h+arg_8]
0x18002b4a1  add     rsp, 90h
0x18002b4a8  pop     r15
0x18002b4aa  pop     r14
0x18002b4ac  pop     r13
0x18002b4ae  pop     r12
0x18002b4b0  pop     rdi
0x18002b4b1  pop     rsi
0x18002b4b2  pop     rbp
0x18002b4b3  retn
0x18002b4b4  mov     ecx, 0C000008Ch; this
0x18002b4b9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002b4be  int     3; Trap to Debugger
0x18002b4bf  mov     ecx, 80004005h; int
0x18002b4c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002b4ca  mov     ecx, 80070057h; int
0x18002b4cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002b4d5  mov     ecx, 8007000Eh; int
0x18002b4da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
