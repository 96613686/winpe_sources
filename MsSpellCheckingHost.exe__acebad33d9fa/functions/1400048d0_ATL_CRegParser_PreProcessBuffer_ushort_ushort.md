# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x1400048d0`
- end: `0x140004bab`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `__int64 __fastcall(LPCWSTR *this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004d28`

## callees

- `0x1400031fc`
- `0x140003b88`
- `0x1400048d0`
- `0x1400062fc`
- `0x140011e10`

## import_xrefs

- `USER32!CharNextW` at `0x1400049a4`
- `USER32!CharNextW` at `0x1400049d5`
- `USER32!CharNextW` at `0x140004ae0`
- `USER32!CharNextW` at `0x140004b09`
- `USER32!CharNextW` at `0x1400049a4`
- `USER32!CharNextW` at `0x1400049d5`
- `USER32!CharNextW` at `0x140004ae0`
- `USER32!CharNextW` at `0x140004b09`
- `msvcrt!wcsncpy_s` at `0x140004a13`
- `msvcrt!wcsncpy_s` at `0x140004a13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000495a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000495a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004b34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140004b34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004a49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004a49`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004a67`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140004a67`

## pseudocode

```c
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
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  const unsigned __int16 *v21; // rbx
  __int64 v22; // r8
  const WCHAR *i; // rax
  unsigned int v24; // ebx
  _DWORD v25[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v27; // [rsp+30h] [rbp-39h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

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
  v18 = wcsncpy_s(Destination, 0x20u, *this, (int)v17);
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
  while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
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
      ATL::_AtlRaiseException(0xC000008C);
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
  v27 = 0;
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
0x1400048d0  mov     [rsp-8+arg_8], rbx
0x1400048d5  push    rbp
0x1400048d6  push    rsi
0x1400048d7  push    rdi
0x1400048d8  push    r12
0x1400048da  push    r13
0x1400048dc  push    r14
0x1400048de  push    r15
0x1400048e0  lea     rbp, [rsp-27h]
0x1400048e5  sub     rsp, 90h
0x1400048ec  mov     rax, cs:__security_cookie
0x1400048f3  xor     rax, rsp
0x1400048f6  mov     [rbp+57h+var_40], rax
0x1400048fa  mov     r12, r8
0x1400048fd  mov     rbx, rdx
0x140004900  mov     r14, rcx
0x140004903  xor     r13d, r13d
0x140004906  test    rdx, rdx
0x140004909  jz      loc_140004B53
0x14000490f  test    r8, r8
0x140004912  jz      loc_140004B53
0x140004918  mov     [r8], r13
0x14000491b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000491f  inc     rax
0x140004922  cmp     [rdx+rax*2], r13w
0x140004927  jnz     short loc_14000491F
0x140004929  add     eax, eax
0x14000492b  mov     ecx, 3E8h
0x140004930  cmp     eax, 64h ; 'd'
0x140004933  cmovl   eax, ecx
0x140004936  mov     [rbp+57h+var_A0], r13d
0x14000493a  mov     [rbp+57h+var_9C], eax
0x14000493d  mov     ecx, eax
0x14000493f  add     rcx, rcx
0x140004942  mov     eax, 0FFFFFFFFh
0x140004947  cmp     rcx, rax
0x14000494a  jbe     short loc_140004958
0x14000494c  mov     rax, r13
0x14000494f  mov     rdx, r13
0x140004952  mov     [rbp+57h+pv], rdx
0x140004956  jmp     short loc_140004970
0x140004958  mov     ecx, ecx; cb
0x14000495a  call    cs:__imp_CoTaskMemAlloc
0x140004960  mov     rdx, rax
0x140004963  mov     [rbp+57h+pv], rax
0x140004967  test    rax, rax
0x14000496a  jz      short loc_140004970
0x14000496c  mov     [rax], r13w
0x140004970  test    rax, rax
0x140004973  jnz     short loc_140004988
0x140004975  mov     rcx, rax; pv
0x140004978  call    cs:__imp_CoTaskMemFree
0x14000497e  mov     eax, 8007000Eh
0x140004983  jmp     loc_140004B58
0x140004988  mov     [r14], rbx
0x14000498b  movzx   eax, word ptr [rbx]
0x14000498e  test    ax, ax
0x140004991  jz      loc_140004B25
0x140004997  cmp     ax, 25h ; '%'
0x14000499b  jnz     loc_140004AF0
0x1400049a1  mov     rcx, rbx; lpsz
0x1400049a4  call    cs:__imp_CharNextW
0x1400049aa  mov     [r14], rax
0x1400049ad  movzx   ecx, word ptr [rax]
0x1400049b0  cmp     cx, 25h ; '%'
0x1400049b4  jnz     short loc_1400049BE
0x1400049b6  mov     rdx, rax
0x1400049b9  jmp     loc_140004AF3
0x1400049be  test    rax, rax
0x1400049c1  jz      loc_140004B45
0x1400049c7  mov     rdi, r13
0x1400049ca  jmp     short loc_1400049DE
0x1400049cc  cmp     cx, 25h ; '%'
0x1400049d0  jz      short loc_1400049E5
0x1400049d2  mov     rcx, rax; lpsz
0x1400049d5  call    cs:__imp_CharNextW
0x1400049db  movzx   ecx, word ptr [rax]
0x1400049de  test    cx, cx
0x1400049e1  jnz     short loc_1400049CC
0x1400049e3  jmp     short loc_1400049E8
0x1400049e5  mov     rdi, rax
0x1400049e8  test    rdi, rdi
0x1400049eb  jz      loc_140004B45
0x1400049f1  mov     rax, rdi
0x1400049f4  sub     rax, [r14]
0x1400049f7  sar     rax, 1
0x1400049fa  cmp     rax, 1Fh
0x1400049fe  jg      loc_140004B3E
0x140004a04  movsxd  r9, eax; MaxCount
0x140004a07  mov     r8, [r14]; Source
0x140004a0a  mov     edx, 20h ; ' '; SizeInWords
0x140004a0f  lea     rcx, [rbp+57h+Destination]; Destination
0x140004a13  call    cs:__imp_wcsncpy_s
0x140004a19  test    eax, eax
0x140004a1b  jz      short loc_140004A41
0x140004a1d  cmp     eax, 0Ch
0x140004a20  jz      loc_140004BA0
0x140004a26  cmp     eax, 16h
0x140004a29  jz      loc_140004B95
0x140004a2f  cmp     eax, 22h ; '"'
0x140004a32  jz      loc_140004B95
0x140004a38  cmp     eax, 50h ; 'P'
0x140004a3b  jnz     loc_140004B8A
0x140004a41  mov     rsi, [r14+8]
0x140004a45  lea     rcx, [rsi+20h]; lpCriticalSection
0x140004a49  call    cs:__imp_EnterCriticalSection
0x140004a4f  mov     ebx, r13d
0x140004a52  cmp     [rsi+18h], r13d
0x140004a56  jle     short loc_140004A78
0x140004a58  movsxd  rax, ebx
0x140004a5b  mov     rcx, [rsi+8]
0x140004a5f  lea     rdx, [rbp+57h+Destination]; lpString2
0x140004a63  mov     rcx, [rcx+rax*8]; lpString1
0x140004a67  call    cs:__imp_lstrcmpiW
0x140004a6d  test    eax, eax
0x140004a6f  jz      short loc_140004ABA
0x140004a71  inc     ebx
0x140004a73  cmp     ebx, [rsi+18h]
0x140004a76  jl      short loc_140004A58
0x140004a78  mov     rbx, r13
0x140004a7b  lea     rcx, [rsi+20h]; lpCriticalSection
0x140004a7f  call    cs:__imp_LeaveCriticalSection
0x140004a85  test    rbx, rbx
0x140004a88  jz      loc_140004B45
0x140004a8e  mov     [rbp+57h+var_90], r13
0x140004a92  or      r8, 0FFFFFFFFFFFFFFFFh
0x140004a96  inc     r8; int
0x140004a99  cmp     [rbx+r8*2], r13w
0x140004a9e  jnz     short loc_140004A96
0x140004aa0  mov     rdx, rbx; unsigned __int16 *
0x140004aa3  lea     rcx, [rbp+57h+var_A0]; this
0x140004aa7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140004aac  nop
0x140004aad  test    eax, eax
0x140004aaf  jz      loc_140004B4C
0x140004ab5  mov     rax, [r14]
0x140004ab8  jmp     short loc_140004AE9
0x140004aba  cmp     ebx, 0FFFFFFFFh
0x140004abd  jz      short loc_140004A78
0x140004abf  test    ebx, ebx
0x140004ac1  js      loc_140004B7F
0x140004ac7  cmp     ebx, [rsi+18h]
0x140004aca  jge     loc_140004B7F
0x140004ad0  movsxd  rcx, ebx
0x140004ad3  mov     rax, [rsi+10h]
0x140004ad7  mov     rbx, [rax+rcx*8]
0x140004adb  jmp     short loc_140004A7B
0x140004add  mov     rcx, rax; lpsz
0x140004ae0  call    cs:__imp_CharNextW
0x140004ae6  mov     [r14], rax
0x140004ae9  cmp     rax, rdi
0x140004aec  jnz     short loc_140004ADD
0x140004aee  jmp     short loc_140004B06
0x140004af0  mov     rdx, rbx; unsigned __int16 *
0x140004af3  mov     r8d, 1; int
0x140004af9  lea     rcx, [rbp+57h+var_A0]; this
0x140004afd  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x140004b02  test    eax, eax
0x140004b04  jz      short loc_140004B4C
0x140004b06  mov     rcx, [r14]; lpsz
0x140004b09  call    cs:__imp_CharNextW
0x140004b0f  mov     rbx, rax
0x140004b12  mov     [r14], rax
0x140004b15  movzx   eax, word ptr [rax]
0x140004b18  test    ax, ax
0x140004b1b  jnz     loc_140004997
0x140004b21  mov     rdx, [rbp+57h+pv]
0x140004b25  mov     ebx, r13d
0x140004b28  mov     [rbp+57h+pv], r13
0x140004b2c  mov     [r12], rdx
0x140004b30  mov     rcx, [rbp+57h+pv]; pv
0x140004b34  call    cs:__imp_CoTaskMemFree
0x140004b3a  mov     eax, ebx
0x140004b3c  jmp     short loc_140004B58
0x140004b3e  mov     ebx, 80004005h
0x140004b43  jmp     short loc_140004B30
0x140004b45  mov     ebx, 80020009h
0x140004b4a  jmp     short loc_140004B30
0x140004b4c  mov     ebx, 8007000Eh
0x140004b51  jmp     short loc_140004B30
0x140004b53  mov     eax, 80004003h
0x140004b58  mov     rcx, [rbp+57h+var_40]
0x140004b5c  xor     rcx, rsp; StackCookie
0x140004b5f  call    __security_check_cookie
0x140004b64  mov     rbx, [rsp+0C0h+arg_8]
0x140004b6c  add     rsp, 90h
0x140004b73  pop     r15
0x140004b75  pop     r14
0x140004b77  pop     r13
0x140004b79  pop     r12
0x140004b7b  pop     rdi
0x140004b7c  pop     rsi
0x140004b7d  pop     rbp
0x140004b7e  retn
0x140004b7f  mov     ecx, 0C000008Ch; unsigned int
0x140004b84  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x140004b89  int     3; Trap to Debugger
0x140004b8a  mov     ecx, 80004005h; int
0x140004b8f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140004b95  mov     ecx, 80070057h; int
0x140004b9a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140004ba0  mov     ecx, 8007000Eh; int
0x140004ba5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
