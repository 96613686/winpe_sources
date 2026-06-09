# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180020b20`
- end: `0x180020dfb`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `731`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021098`

## callees

- `0x1800018f0`
- `0x18001faac`
- `0x180020178`
- `0x180020b20`
- `0x18002262c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180020c63`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180020c63`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020c99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020ccf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020baa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020d84`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020bf4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020c25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020d30`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020d59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020bf4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020c25`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020d30`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020d59`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020cb7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020cb7`

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
  unsigned int v21; // edx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  const WCHAR *i; // rax
  unsigned int v25; // ebx
  _DWORD v26[2]; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

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
0x180020b20  mov     [rsp-8+arg_8], rbx
0x180020b25  push    rbp
0x180020b26  push    rsi
0x180020b27  push    rdi
0x180020b28  push    r12
0x180020b2a  push    r13
0x180020b2c  push    r14
0x180020b2e  push    r15
0x180020b30  lea     rbp, [rsp-27h]
0x180020b35  sub     rsp, 90h
0x180020b3c  mov     rax, cs:__security_cookie
0x180020b43  xor     rax, rsp
0x180020b46  mov     [rbp+57h+var_40], rax
0x180020b4a  mov     r12, r8
0x180020b4d  mov     rbx, rdx
0x180020b50  mov     r14, rcx
0x180020b53  xor     r13d, r13d
0x180020b56  test    rdx, rdx
0x180020b59  jz      loc_180020DA3
0x180020b5f  test    r8, r8
0x180020b62  jz      loc_180020DA3
0x180020b68  mov     [r8], r13
0x180020b6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020b6f  inc     rax
0x180020b72  cmp     [rdx+rax*2], r13w
0x180020b77  jnz     short loc_180020B6F
0x180020b79  add     eax, eax
0x180020b7b  mov     ecx, 3E8h
0x180020b80  cmp     eax, 64h ; 'd'
0x180020b83  cmovl   eax, ecx
0x180020b86  mov     [rbp+57h+var_A0], r13d
0x180020b8a  mov     [rbp+57h+var_9C], eax
0x180020b8d  mov     ecx, eax
0x180020b8f  add     rcx, rcx
0x180020b92  mov     eax, 0FFFFFFFFh
0x180020b97  cmp     rcx, rax
0x180020b9a  jbe     short loc_180020BA8
0x180020b9c  mov     rax, r13
0x180020b9f  mov     rdx, r13
0x180020ba2  mov     [rbp+57h+pv], rdx
0x180020ba6  jmp     short loc_180020BC0
0x180020ba8  mov     ecx, ecx; cb
0x180020baa  call    cs:__imp_CoTaskMemAlloc
0x180020bb0  mov     rdx, rax
0x180020bb3  mov     [rbp+57h+pv], rax
0x180020bb7  test    rax, rax
0x180020bba  jz      short loc_180020BC0
0x180020bbc  mov     [rax], r13w
0x180020bc0  test    rax, rax
0x180020bc3  jnz     short loc_180020BD8
0x180020bc5  mov     rcx, rax; pv
0x180020bc8  call    cs:__imp_CoTaskMemFree
0x180020bce  mov     eax, 8007000Eh
0x180020bd3  jmp     loc_180020DA8
0x180020bd8  mov     [r14], rbx
0x180020bdb  movzx   eax, word ptr [rbx]
0x180020bde  test    ax, ax
0x180020be1  jz      loc_180020D75
0x180020be7  cmp     ax, 25h ; '%'
0x180020beb  jnz     loc_180020D40
0x180020bf1  mov     rcx, rbx; lpsz
0x180020bf4  call    cs:__imp_CharNextW
0x180020bfa  mov     [r14], rax
0x180020bfd  movzx   ecx, word ptr [rax]
0x180020c00  cmp     cx, 25h ; '%'
0x180020c04  jnz     short loc_180020C0E
0x180020c06  mov     rdx, rax
0x180020c09  jmp     loc_180020D43
0x180020c0e  test    rax, rax
0x180020c11  jz      loc_180020D95
0x180020c17  mov     rdi, r13
0x180020c1a  jmp     short loc_180020C2E
0x180020c1c  cmp     cx, 25h ; '%'
0x180020c20  jz      short loc_180020C35
0x180020c22  mov     rcx, rax; lpsz
0x180020c25  call    cs:__imp_CharNextW
0x180020c2b  movzx   ecx, word ptr [rax]
0x180020c2e  test    cx, cx
0x180020c31  jnz     short loc_180020C1C
0x180020c33  jmp     short loc_180020C38
0x180020c35  mov     rdi, rax
0x180020c38  test    rdi, rdi
0x180020c3b  jz      loc_180020D95
0x180020c41  mov     rax, rdi
0x180020c44  sub     rax, [r14]
0x180020c47  sar     rax, 1
0x180020c4a  cmp     rax, 1Fh
0x180020c4e  jg      loc_180020D8E
0x180020c54  movsxd  r9, eax
0x180020c57  mov     r8, [r14]
0x180020c5a  mov     edx, 20h ; ' '
0x180020c5f  lea     rcx, [rbp+57h+String2]
0x180020c63  call    cs:__imp__o_wcsncpy_s
0x180020c69  test    eax, eax
0x180020c6b  jz      short loc_180020C91
0x180020c6d  cmp     eax, 0Ch
0x180020c70  jz      loc_180020DF0
0x180020c76  cmp     eax, 16h
0x180020c79  jz      loc_180020DE5
0x180020c7f  cmp     eax, 22h ; '"'
0x180020c82  jz      loc_180020DE5
0x180020c88  cmp     eax, 50h ; 'P'
0x180020c8b  jnz     loc_180020DDA
0x180020c91  mov     rsi, [r14+8]
0x180020c95  lea     rcx, [rsi+20h]; lpCriticalSection
0x180020c99  call    cs:__imp_EnterCriticalSection
0x180020c9f  mov     ebx, r13d
0x180020ca2  cmp     [rsi+18h], r13d
0x180020ca6  jle     short loc_180020CC8
0x180020ca8  movsxd  rax, ebx
0x180020cab  mov     rcx, [rsi+8]
0x180020caf  lea     rdx, [rbp+57h+String2]; lpString2
0x180020cb3  mov     rcx, [rcx+rax*8]; lpString1
0x180020cb7  call    cs:__imp_lstrcmpiW
0x180020cbd  test    eax, eax
0x180020cbf  jz      short loc_180020D0A
0x180020cc1  inc     ebx
0x180020cc3  cmp     ebx, [rsi+18h]
0x180020cc6  jl      short loc_180020CA8
0x180020cc8  mov     rbx, r13
0x180020ccb  lea     rcx, [rsi+20h]; lpCriticalSection
0x180020ccf  call    cs:__imp_LeaveCriticalSection
0x180020cd5  test    rbx, rbx
0x180020cd8  jz      loc_180020D95
0x180020cde  mov     [rbp+57h+var_90], r13
0x180020ce2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020ce6  inc     r8; int
0x180020ce9  cmp     [rbx+r8*2], r13w
0x180020cee  jnz     short loc_180020CE6
0x180020cf0  mov     rdx, rbx; unsigned __int16 *
0x180020cf3  lea     rcx, [rbp+57h+var_A0]; this
0x180020cf7  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180020cfc  nop
0x180020cfd  test    eax, eax
0x180020cff  jz      loc_180020D9C
0x180020d05  mov     rax, [r14]
0x180020d08  jmp     short loc_180020D39
0x180020d0a  cmp     ebx, 0FFFFFFFFh
0x180020d0d  jz      short loc_180020CC8
0x180020d0f  test    ebx, ebx
0x180020d11  js      loc_180020DCF
0x180020d17  cmp     ebx, [rsi+18h]
0x180020d1a  jge     loc_180020DCF
0x180020d20  movsxd  rcx, ebx
0x180020d23  mov     rax, [rsi+10h]
0x180020d27  mov     rbx, [rax+rcx*8]
0x180020d2b  jmp     short loc_180020CCB
0x180020d2d  mov     rcx, rax; lpsz
0x180020d30  call    cs:__imp_CharNextW
0x180020d36  mov     [r14], rax
0x180020d39  cmp     rax, rdi
0x180020d3c  jnz     short loc_180020D2D
0x180020d3e  jmp     short loc_180020D56
0x180020d40  mov     rdx, rbx; unsigned __int16 *
0x180020d43  mov     r8d, 1; int
0x180020d49  lea     rcx, [rbp+57h+var_A0]; this
0x180020d4d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180020d52  test    eax, eax
0x180020d54  jz      short loc_180020D9C
0x180020d56  mov     rcx, [r14]; lpsz
0x180020d59  call    cs:__imp_CharNextW
0x180020d5f  mov     rbx, rax
0x180020d62  mov     [r14], rax
0x180020d65  movzx   eax, word ptr [rax]
0x180020d68  test    ax, ax
0x180020d6b  jnz     loc_180020BE7
0x180020d71  mov     rdx, [rbp+57h+pv]
0x180020d75  mov     ebx, r13d
0x180020d78  mov     [rbp+57h+pv], r13
0x180020d7c  mov     [r12], rdx
0x180020d80  mov     rcx, [rbp+57h+pv]; pv
0x180020d84  call    cs:__imp_CoTaskMemFree
0x180020d8a  mov     eax, ebx
0x180020d8c  jmp     short loc_180020DA8
0x180020d8e  mov     ebx, 80004005h
0x180020d93  jmp     short loc_180020D80
0x180020d95  mov     ebx, 80020009h
0x180020d9a  jmp     short loc_180020D80
0x180020d9c  mov     ebx, 8007000Eh
0x180020da1  jmp     short loc_180020D80
0x180020da3  mov     eax, 80004003h
0x180020da8  mov     rcx, [rbp+57h+var_40]
0x180020dac  xor     rcx, rsp; StackCookie
0x180020daf  call    __security_check_cookie
0x180020db4  mov     rbx, [rsp+0C0h+arg_8]
0x180020dbc  add     rsp, 90h
0x180020dc3  pop     r15
0x180020dc5  pop     r14
0x180020dc7  pop     r13
0x180020dc9  pop     r12
0x180020dcb  pop     rdi
0x180020dcc  pop     rsi
0x180020dcd  pop     rbp
0x180020dce  retn
0x180020dcf  mov     ecx, 0C000008Ch; unsigned int
0x180020dd4  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180020dd9  int     3; Trap to Debugger
0x180020dda  mov     ecx, 80004005h; int
0x180020ddf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020de5  mov     ecx, 80070057h; int
0x180020dea  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020df0  mov     ecx, 8007000Eh; int
0x180020df5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
