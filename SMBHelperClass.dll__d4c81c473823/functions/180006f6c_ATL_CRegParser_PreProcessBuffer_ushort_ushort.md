# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180006f6c`
- end: `0x180007247`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x18000454c`
- `0x180004684`
- `0x180006f6c`
- `0x1800090c4`
- `0x18000fc30`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800070af`
- `msvcrt!wcsncpy_s` at `0x1800070af`
- `KERNEL32!lstrcmpiW` at `0x180007103`
- `KERNEL32!lstrcmpiW` at `0x180007103`
- `KERNEL32!LeaveCriticalSection` at `0x18000711b`
- `KERNEL32!LeaveCriticalSection` at `0x18000711b`
- `KERNEL32!EnterCriticalSection` at `0x1800070e5`
- `KERNEL32!EnterCriticalSection` at `0x1800070e5`
- `USER32!CharNextW` at `0x180007040`
- `USER32!CharNextW` at `0x180007071`
- `USER32!CharNextW` at `0x18000717c`
- `USER32!CharNextW` at `0x1800071a5`
- `USER32!CharNextW` at `0x180007040`
- `USER32!CharNextW` at `0x180007071`
- `USER32!CharNextW` at `0x18000717c`
- `USER32!CharNextW` at `0x1800071a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006ff6`

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
  errno_t v18; // eax
  LPCWSTR v19; // rsi
  int v20; // ebx
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
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
  v26[0] = 0;
  v26[1] = v7;
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
    v25 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_52;
  }
  while ( v12 != 37 )
  {
    v15 = v4;
LABEL_48:
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
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
    v25 = -2147467259;
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
    v22 = 0;
  }
  else
  {
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
  if ( !v22 )
  {
LABEL_54:
    v25 = -2147352567;
    goto LABEL_52;
  }
  v28 = 0;
  v23 = -1;
  do
    ++v23;
  while ( v22[v23] );
  if ( ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v22, v23) )
  {
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
    goto LABEL_49;
  }
LABEL_55:
  v25 = -2147024882;
LABEL_52:
  CoTaskMemFree(pv);
  return v25;
}

```

## disassembly

```asm
0x180006f6c  mov     [rsp-8+arg_8], rbx
0x180006f71  push    rbp
0x180006f72  push    rsi
0x180006f73  push    rdi
0x180006f74  push    r12
0x180006f76  push    r13
0x180006f78  push    r14
0x180006f7a  push    r15
0x180006f7c  lea     rbp, [rsp-27h]
0x180006f81  sub     rsp, 90h
0x180006f88  mov     rax, cs:__security_cookie
0x180006f8f  xor     rax, rsp
0x180006f92  mov     [rbp+57h+var_40], rax
0x180006f96  mov     r12, r8
0x180006f99  mov     rbx, rdx
0x180006f9c  mov     r14, rcx
0x180006f9f  xor     r13d, r13d
0x180006fa2  test    rdx, rdx
0x180006fa5  jz      loc_1800071EF
0x180006fab  test    r8, r8
0x180006fae  jz      loc_1800071EF
0x180006fb4  mov     [r8], r13
0x180006fb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006fbb  inc     rax
0x180006fbe  cmp     [rdx+rax*2], r13w
0x180006fc3  jnz     short loc_180006FBB
0x180006fc5  add     eax, eax
0x180006fc7  mov     ecx, 3E8h
0x180006fcc  cmp     eax, 64h ; 'd'
0x180006fcf  cmovl   eax, ecx
0x180006fd2  mov     [rbp+57h+var_A0], r13d
0x180006fd6  mov     [rbp+57h+var_9C], eax
0x180006fd9  mov     ecx, eax
0x180006fdb  add     rcx, rcx
0x180006fde  mov     eax, 0FFFFFFFFh
0x180006fe3  cmp     rcx, rax
0x180006fe6  jbe     short loc_180006FF4
0x180006fe8  mov     rax, r13
0x180006feb  mov     rdx, r13
0x180006fee  mov     [rbp+57h+pv], rdx
0x180006ff2  jmp     short loc_18000700C
0x180006ff4  mov     ecx, ecx; cb
0x180006ff6  call    cs:__imp_CoTaskMemAlloc
0x180006ffc  mov     rdx, rax
0x180006fff  mov     [rbp+57h+pv], rax
0x180007003  test    rax, rax
0x180007006  jz      short loc_18000700C
0x180007008  mov     [rax], r13w
0x18000700c  test    rax, rax
0x18000700f  jnz     short loc_180007024
0x180007011  mov     rcx, rax; pv
0x180007014  call    cs:__imp_CoTaskMemFree
0x18000701a  mov     eax, 8007000Eh
0x18000701f  jmp     loc_1800071F4
0x180007024  mov     [r14], rbx
0x180007027  movzx   eax, word ptr [rbx]
0x18000702a  test    ax, ax
0x18000702d  jz      loc_1800071C1
0x180007033  cmp     ax, 25h ; '%'
0x180007037  jnz     loc_18000718C
0x18000703d  mov     rcx, rbx; lpsz
0x180007040  call    cs:__imp_CharNextW
0x180007046  mov     [r14], rax
0x180007049  movzx   ecx, word ptr [rax]
0x18000704c  cmp     cx, 25h ; '%'
0x180007050  jnz     short loc_18000705A
0x180007052  mov     rdx, rax
0x180007055  jmp     loc_18000718F
0x18000705a  test    rax, rax
0x18000705d  jz      loc_1800071E1
0x180007063  mov     rdi, r13
0x180007066  jmp     short loc_18000707A
0x180007068  cmp     cx, 25h ; '%'
0x18000706c  jz      short loc_180007081
0x18000706e  mov     rcx, rax; lpsz
0x180007071  call    cs:__imp_CharNextW
0x180007077  movzx   ecx, word ptr [rax]
0x18000707a  test    cx, cx
0x18000707d  jnz     short loc_180007068
0x18000707f  jmp     short loc_180007084
0x180007081  mov     rdi, rax
0x180007084  test    rdi, rdi
0x180007087  jz      loc_1800071E1
0x18000708d  mov     rax, rdi
0x180007090  sub     rax, [r14]
0x180007093  sar     rax, 1
0x180007096  cmp     rax, 1Fh
0x18000709a  jg      loc_1800071DA
0x1800070a0  movsxd  r9, eax; MaxCount
0x1800070a3  mov     r8, [r14]; Source
0x1800070a6  mov     edx, 20h ; ' '; SizeInWords
0x1800070ab  lea     rcx, [rbp+57h+Destination]; Destination
0x1800070af  call    cs:__imp_wcsncpy_s
0x1800070b5  test    eax, eax
0x1800070b7  jz      short loc_1800070DD
0x1800070b9  cmp     eax, 0Ch
0x1800070bc  jz      loc_18000723C
0x1800070c2  cmp     eax, 16h
0x1800070c5  jz      loc_180007231
0x1800070cb  cmp     eax, 22h ; '"'
0x1800070ce  jz      loc_180007231
0x1800070d4  cmp     eax, 50h ; 'P'
0x1800070d7  jnz     loc_180007226
0x1800070dd  mov     rsi, [r14+8]
0x1800070e1  lea     rcx, [rsi+20h]; lpCriticalSection
0x1800070e5  call    cs:__imp_EnterCriticalSection
0x1800070eb  mov     ebx, r13d
0x1800070ee  cmp     [rsi+18h], r13d
0x1800070f2  jle     short loc_180007114
0x1800070f4  movsxd  rax, ebx
0x1800070f7  mov     rcx, [rsi+8]
0x1800070fb  lea     rdx, [rbp+57h+Destination]; lpString2
0x1800070ff  mov     rcx, [rcx+rax*8]; lpString1
0x180007103  call    cs:__imp_lstrcmpiW
0x180007109  test    eax, eax
0x18000710b  jz      short loc_180007156
0x18000710d  inc     ebx
0x18000710f  cmp     ebx, [rsi+18h]
0x180007112  jl      short loc_1800070F4
0x180007114  mov     rbx, r13
0x180007117  lea     rcx, [rsi+20h]; lpCriticalSection
0x18000711b  call    cs:__imp_LeaveCriticalSection
0x180007121  test    rbx, rbx
0x180007124  jz      loc_1800071E1
0x18000712a  mov     [rbp+57h+var_90], r13
0x18000712e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007132  inc     r8; int
0x180007135  cmp     [rbx+r8*2], r13w
0x18000713a  jnz     short loc_180007132
0x18000713c  mov     rdx, rbx; unsigned __int16 *
0x18000713f  lea     rcx, [rbp+57h+var_A0]; this
0x180007143  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180007148  nop
0x180007149  test    eax, eax
0x18000714b  jz      loc_1800071E8
0x180007151  mov     rax, [r14]
0x180007154  jmp     short loc_180007185
0x180007156  cmp     ebx, 0FFFFFFFFh
0x180007159  jz      short loc_180007114
0x18000715b  test    ebx, ebx
0x18000715d  js      loc_18000721B
0x180007163  cmp     ebx, [rsi+18h]
0x180007166  jge     loc_18000721B
0x18000716c  movsxd  rcx, ebx
0x18000716f  mov     rax, [rsi+10h]
0x180007173  mov     rbx, [rax+rcx*8]
0x180007177  jmp     short loc_180007117
0x180007179  mov     rcx, rax; lpsz
0x18000717c  call    cs:__imp_CharNextW
0x180007182  mov     [r14], rax
0x180007185  cmp     rax, rdi
0x180007188  jnz     short loc_180007179
0x18000718a  jmp     short loc_1800071A2
0x18000718c  mov     rdx, rbx; unsigned __int16 *
0x18000718f  mov     r8d, 1; int
0x180007195  lea     rcx, [rbp+57h+var_A0]; this
0x180007199  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000719e  test    eax, eax
0x1800071a0  jz      short loc_1800071E8
0x1800071a2  mov     rcx, [r14]; lpsz
0x1800071a5  call    cs:__imp_CharNextW
0x1800071ab  mov     rbx, rax
0x1800071ae  mov     [r14], rax
0x1800071b1  movzx   eax, word ptr [rax]
0x1800071b4  test    ax, ax
0x1800071b7  jnz     loc_180007033
0x1800071bd  mov     rdx, [rbp+57h+pv]
0x1800071c1  mov     ebx, r13d
0x1800071c4  mov     [rbp+57h+pv], r13
0x1800071c8  mov     [r12], rdx
0x1800071cc  mov     rcx, [rbp+57h+pv]; pv
0x1800071d0  call    cs:__imp_CoTaskMemFree
0x1800071d6  mov     eax, ebx
0x1800071d8  jmp     short loc_1800071F4
0x1800071da  mov     ebx, 80004005h
0x1800071df  jmp     short loc_1800071CC
0x1800071e1  mov     ebx, 80020009h
0x1800071e6  jmp     short loc_1800071CC
0x1800071e8  mov     ebx, 8007000Eh
0x1800071ed  jmp     short loc_1800071CC
0x1800071ef  mov     eax, 80004003h
0x1800071f4  mov     rcx, [rbp+57h+var_40]
0x1800071f8  xor     rcx, rsp; StackCookie
0x1800071fb  call    __security_check_cookie
0x180007200  mov     rbx, [rsp+0C0h+arg_8]
0x180007208  add     rsp, 90h
0x18000720f  pop     r15
0x180007211  pop     r14
0x180007213  pop     r13
0x180007215  pop     r12
0x180007217  pop     rdi
0x180007218  pop     rsi
0x180007219  pop     rbp
0x18000721a  retn
0x18000721b  mov     ecx, 0C000008Ch; unsigned int
0x180007220  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180007225  int     3; Trap to Debugger
0x180007226  mov     ecx, 80004005h; int
0x18000722b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007231  mov     ecx, 80070057h; int
0x180007236  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000723c  mov     ecx, 8007000Eh; int
0x180007241  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
