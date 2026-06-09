# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18002c358`
- end: `0x18002c67f`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `807`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002c8bc`

## callees

- `0x180003400`
- `0x1800109e8`
- `0x180028c50`
- `0x18002c358`
- `0x18002e3e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002c4bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002c4bc`
- `KERNEL32!LeaveCriticalSection` at `0x18002c53a`
- `KERNEL32!LeaveCriticalSection` at `0x18002c53a`
- `KERNEL32!EnterCriticalSection` at `0x18002c4f8`
- `KERNEL32!EnterCriticalSection` at `0x18002c4f8`
- `KERNEL32!lstrcmpiW` at `0x18002c51c`
- `KERNEL32!lstrcmpiW` at `0x18002c51c`
- `USER32!CharNextW` at `0x18002c441`
- `USER32!CharNextW` at `0x18002c478`
- `USER32!CharNextW` at `0x18002c5a1`
- `USER32!CharNextW` at `0x18002c5d0`
- `USER32!CharNextW` at `0x18002c441`
- `USER32!CharNextW` at `0x18002c478`
- `USER32!CharNextW` at `0x18002c5a1`
- `USER32!CharNextW` at `0x18002c5d0`
- `ole32!CoTaskMemAlloc` at `0x18002c3eb`
- `ole32!CoTaskMemAlloc` at `0x18002c3eb`
- `ole32!CoTaskMemFree` at `0x18002c40f`
- `ole32!CoTaskMemFree` at `0x18002c601`
- `ole32!CoTaskMemFree` at `0x18002c40f`
- `ole32!CoTaskMemFree` at `0x18002c601`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  const WCHAR *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdx
  WCHAR v12; // ax
  const WCHAR *v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rdi
  __int64 v17; // rax
  int v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  _DWORD v25[2]; // [rsp+28h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-41h]
  __int64 v27; // [rsp+38h] [rbp-39h]
  __int64 v28; // [rsp+40h] [rbp-31h]
  WCHAR String2[32]; // [rsp+48h] [rbp-29h] BYREF

  v27 = -2;
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
  v25[0] = 0;
  v25[1] = v7;
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
    v24 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v15, 1) )
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
    v24 = -2147467259;
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
    v21 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL);
      __debugbreak();
    }
    v21 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v21 )
  {
LABEL_54:
    v24 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( (unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v21, v22) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v24 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v24;
}

```

## disassembly

```asm
0x18002c358  mov     rax, rsp
0x18002c35b  push    rbp
0x18002c35c  push    rsi
0x18002c35d  push    rdi
0x18002c35e  push    r12
0x18002c360  push    r13
0x18002c362  push    r14
0x18002c364  push    r15
0x18002c366  lea     rbp, [rax-5Fh]
0x18002c36a  sub     rsp, 90h
0x18002c371  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x18002c379  mov     [rax+10h], rbx
0x18002c37d  mov     rax, cs:__security_cookie
0x18002c384  xor     rax, rsp
0x18002c387  mov     [rbp+57h+var_40], rax
0x18002c38b  mov     r12, r8
0x18002c38e  mov     rbx, rdx
0x18002c391  mov     r14, rcx
0x18002c394  xor     r13d, r13d
0x18002c397  test    rdx, rdx
0x18002c39a  jz      loc_18002C626
0x18002c3a0  test    r8, r8
0x18002c3a3  jz      loc_18002C626
0x18002c3a9  mov     [r8], r13
0x18002c3ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c3b0  inc     rax
0x18002c3b3  cmp     [rdx+rax*2], r13w
0x18002c3b8  jnz     short loc_18002C3B0
0x18002c3ba  add     eax, eax
0x18002c3bc  mov     ecx, 3E8h
0x18002c3c1  cmp     eax, 64h ; 'd'
0x18002c3c4  cmovl   eax, ecx
0x18002c3c7  mov     [rbp+57h+var_A0], r13d
0x18002c3cb  mov     [rbp+57h+var_9C], eax
0x18002c3ce  mov     ecx, eax
0x18002c3d0  add     rcx, rcx
0x18002c3d3  mov     eax, 0FFFFFFFFh
0x18002c3d8  cmp     rcx, rax
0x18002c3db  jbe     short loc_18002C3E9
0x18002c3dd  mov     rax, r13
0x18002c3e0  mov     rdx, r13
0x18002c3e3  mov     [rbp+57h+pv], rdx
0x18002c3e7  jmp     short loc_18002C407
0x18002c3e9  mov     ecx, ecx; cb
0x18002c3eb  call    cs:__imp_CoTaskMemAlloc
0x18002c3f2  nop     dword ptr [rax+rax+00h]
0x18002c3f7  mov     rdx, rax
0x18002c3fa  mov     [rbp+57h+pv], rax
0x18002c3fe  test    rax, rax
0x18002c401  jz      short loc_18002C407
0x18002c403  mov     [rax], r13w
0x18002c407  test    rax, rax
0x18002c40a  jnz     short loc_18002C425
0x18002c40c  mov     rcx, rax; pv
0x18002c40f  call    cs:__imp_CoTaskMemFree
0x18002c416  nop     dword ptr [rax+rax+00h]
0x18002c41b  mov     eax, 8007000Eh
0x18002c420  jmp     loc_18002C62B
0x18002c425  mov     [r14], rbx
0x18002c428  movzx   eax, word ptr [rbx]
0x18002c42b  test    ax, ax
0x18002c42e  jz      loc_18002C5F2
0x18002c434  cmp     ax, 25h ; '%'
0x18002c438  jnz     loc_18002C5B7
0x18002c43e  mov     rcx, rbx; lpsz
0x18002c441  call    cs:__imp_CharNextW
0x18002c448  nop     dword ptr [rax+rax+00h]
0x18002c44d  mov     [r14], rax
0x18002c450  movzx   ecx, word ptr [rax]
0x18002c453  cmp     cx, 25h ; '%'
0x18002c457  jnz     short loc_18002C461
0x18002c459  mov     rdx, rax
0x18002c45c  jmp     loc_18002C5BA
0x18002c461  test    rax, rax
0x18002c464  jz      loc_18002C618
0x18002c46a  mov     rdi, r13
0x18002c46d  jmp     short loc_18002C487
0x18002c46f  cmp     cx, 25h ; '%'
0x18002c473  jz      short loc_18002C48E
0x18002c475  mov     rcx, rax; lpsz
0x18002c478  call    cs:__imp_CharNextW
0x18002c47f  nop     dword ptr [rax+rax+00h]
0x18002c484  movzx   ecx, word ptr [rax]
0x18002c487  test    cx, cx
0x18002c48a  jnz     short loc_18002C46F
0x18002c48c  jmp     short loc_18002C491
0x18002c48e  mov     rdi, rax
0x18002c491  test    rdi, rdi
0x18002c494  jz      loc_18002C618
0x18002c49a  mov     rax, rdi
0x18002c49d  sub     rax, [r14]
0x18002c4a0  sar     rax, 1
0x18002c4a3  cmp     rax, 1Fh
0x18002c4a7  jg      loc_18002C611
0x18002c4ad  movsxd  r9, eax
0x18002c4b0  mov     r8, [r14]
0x18002c4b3  mov     edx, 20h ; ' '
0x18002c4b8  lea     rcx, [rbp+57h+String2]
0x18002c4bc  call    cs:__imp__o_wcsncpy_s
0x18002c4c3  nop     dword ptr [rax+rax+00h]
0x18002c4c8  test    eax, eax
0x18002c4ca  jz      short loc_18002C4F0
0x18002c4cc  cmp     eax, 0Ch
0x18002c4cf  jz      loc_18002C674
0x18002c4d5  cmp     eax, 16h
0x18002c4d8  jz      loc_18002C669
0x18002c4de  cmp     eax, 22h ; '"'
0x18002c4e1  jz      loc_18002C669
0x18002c4e7  cmp     eax, 50h ; 'P'
0x18002c4ea  jnz     loc_18002C65E
0x18002c4f0  mov     rsi, [r14+8]
0x18002c4f4  lea     rcx, [rsi+20h]; lpCriticalSection
0x18002c4f8  call    cs:__imp_EnterCriticalSection
0x18002c4ff  nop     dword ptr [rax+rax+00h]
0x18002c504  mov     ebx, r13d
0x18002c507  cmp     [rsi+18h], r13d
0x18002c50b  jle     short loc_18002C533
0x18002c50d  movsxd  rax, ebx
0x18002c510  mov     rcx, [rsi+8]
0x18002c514  lea     rdx, [rbp+57h+String2]; lpString2
0x18002c518  mov     rcx, [rcx+rax*8]; lpString1
0x18002c51c  call    cs:__imp_lstrcmpiW
0x18002c523  nop     dword ptr [rax+rax+00h]
0x18002c528  test    eax, eax
0x18002c52a  jz      short loc_18002C57B
0x18002c52c  inc     ebx
0x18002c52e  cmp     ebx, [rsi+18h]
0x18002c531  jl      short loc_18002C50D
0x18002c533  mov     rbx, r13
0x18002c536  lea     rcx, [rsi+20h]; lpCriticalSection
0x18002c53a  call    cs:__imp_LeaveCriticalSection
0x18002c541  nop     dword ptr [rax+rax+00h]
0x18002c546  test    rbx, rbx
0x18002c549  jz      loc_18002C618
0x18002c54f  mov     [rbp+57h+var_88], r13
0x18002c553  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c557  inc     r8; int
0x18002c55a  cmp     [rbx+r8*2], r13w
0x18002c55f  jnz     short loc_18002C557
0x18002c561  mov     rdx, rbx; unsigned __int16 *
0x18002c564  lea     rcx, [rbp+57h+var_A0]; this
0x18002c568  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002c56d  nop
0x18002c56e  test    eax, eax
0x18002c570  jz      loc_18002C61F
0x18002c576  mov     rax, [r14]
0x18002c579  jmp     short loc_18002C5B0
0x18002c57b  cmp     ebx, 0FFFFFFFFh
0x18002c57e  jz      short loc_18002C533
0x18002c580  test    ebx, ebx
0x18002c582  js      loc_18002C653
0x18002c588  cmp     ebx, [rsi+18h]
0x18002c58b  jge     loc_18002C653
0x18002c591  movsxd  rcx, ebx
0x18002c594  mov     rax, [rsi+10h]
0x18002c598  mov     rbx, [rax+rcx*8]
0x18002c59c  jmp     short loc_18002C536
0x18002c59e  mov     rcx, rax; lpsz
0x18002c5a1  call    cs:__imp_CharNextW
0x18002c5a8  nop     dword ptr [rax+rax+00h]
0x18002c5ad  mov     [r14], rax
0x18002c5b0  cmp     rax, rdi
0x18002c5b3  jnz     short loc_18002C59E
0x18002c5b5  jmp     short loc_18002C5CD
0x18002c5b7  mov     rdx, rbx; unsigned __int16 *
0x18002c5ba  mov     r8d, 1; int
0x18002c5c0  lea     rcx, [rbp+57h+var_A0]; this
0x18002c5c4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18002c5c9  test    eax, eax
0x18002c5cb  jz      short loc_18002C61F
0x18002c5cd  mov     rcx, [r14]; lpsz
0x18002c5d0  call    cs:__imp_CharNextW
0x18002c5d7  nop     dword ptr [rax+rax+00h]
0x18002c5dc  mov     rbx, rax
0x18002c5df  mov     [r14], rax
0x18002c5e2  movzx   eax, word ptr [rax]
0x18002c5e5  test    ax, ax
0x18002c5e8  jnz     loc_18002C434
0x18002c5ee  mov     rdx, [rbp+57h+pv]
0x18002c5f2  mov     ebx, r13d
0x18002c5f5  mov     [rbp+57h+pv], r13
0x18002c5f9  mov     [r12], rdx
0x18002c5fd  mov     rcx, [rbp+57h+pv]; pv
0x18002c601  call    cs:__imp_CoTaskMemFree
0x18002c608  nop     dword ptr [rax+rax+00h]
0x18002c60d  mov     eax, ebx
0x18002c60f  jmp     short loc_18002C62B
0x18002c611  mov     ebx, 80004005h
0x18002c616  jmp     short loc_18002C5FD
0x18002c618  mov     ebx, 80020009h
0x18002c61d  jmp     short loc_18002C5FD
0x18002c61f  mov     ebx, 8007000Eh
0x18002c624  jmp     short loc_18002C5FD
0x18002c626  mov     eax, 80004003h
0x18002c62b  mov     rcx, [rbp+57h+var_40]
0x18002c62f  xor     rcx, rsp; StackCookie
0x18002c632  call    __security_check_cookie
0x18002c637  mov     rbx, [rsp+0C0h+arg_8]
0x18002c63f  add     rsp, 90h
0x18002c646  pop     r15
0x18002c648  pop     r14
0x18002c64a  pop     r13
0x18002c64c  pop     r12
0x18002c64e  pop     rdi
0x18002c64f  pop     rsi
0x18002c650  pop     rbp
0x18002c651  retn
0x18002c653  mov     ecx, 0C000008Ch; this
0x18002c658  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002c65d  int     3; Trap to Debugger
0x18002c65e  mov     ecx, 80004005h; int
0x18002c663  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c669  mov     ecx, 80070057h; int
0x18002c66e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c674  mov     ecx, 8007000Eh; int
0x18002c679  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
