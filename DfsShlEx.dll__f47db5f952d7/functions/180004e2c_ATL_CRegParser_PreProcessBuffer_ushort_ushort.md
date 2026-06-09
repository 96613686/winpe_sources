# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180004e2c`
- end: `0x1800050e4`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `696`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800053f8`

## callees

- `0x180003890`
- `0x180004328`
- `0x180004e2c`
- `0x1800068ac`
- `0x18000a9d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180004f6d`
- `msvcrt!wcsncpy_s` at `0x180004f6d`
- `KERNEL32!lstrcmpiW` at `0x180004fb7`
- `KERNEL32!lstrcmpiW` at `0x180004fb7`
- `USER32!CharNextW` at `0x180004f02`
- `USER32!CharNextW` at `0x180004f33`
- `USER32!CharNextW` at `0x180005020`
- `USER32!CharNextW` at `0x180005049`
- `USER32!CharNextW` at `0x180004f02`
- `USER32!CharNextW` at `0x180004f33`
- `USER32!CharNextW` at `0x180005020`
- `USER32!CharNextW` at `0x180005049`
- `ole32!CoTaskMemAlloc` at `0x180004eb8`
- `ole32!CoTaskMemAlloc` at `0x180004eb8`
- `ole32!CoTaskMemFree` at `0x180004ed6`
- `ole32!CoTaskMemFree` at `0x180005073`
- `ole32!CoTaskMemFree` at `0x180004ed6`
- `ole32!CoTaskMemFree` at `0x180005073`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
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
  const WCHAR *v16; // rsi
  __int64 v17; // rax
  errno_t v18; // eax
  const wchar_t *v19; // rdi
  int v20; // ebx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  const unsigned __int16 *v23; // rdx
  __int64 v24; // r8
  const WCHAR *i; // rax
  _DWORD v26[2]; // [rsp+20h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-31h]
  __int64 v28; // [rsp+30h] [rbp-29h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-19h] BYREF

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
LABEL_50:
    v22 = 0;
    pv = 0;
    *a3 = v10;
    goto LABEL_51;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_47:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v15, 1) )
        break;
      goto LABEL_48;
    }
    v13 = CharNextW(v4);
    *this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_47;
    }
    if ( !v13 )
      goto LABEL_34;
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
    {
LABEL_34:
      v22 = -2147352567;
      goto LABEL_51;
    }
    v17 = v16 - *this;
    if ( v17 > 31 )
    {
      v22 = -2147467259;
      goto LABEL_51;
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
    v20 = 0;
    if ( *((int *)v19 + 6) <= 0 )
      goto LABEL_34;
    while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
    {
      if ( ++v20 >= *((_DWORD *)v19 + 6) )
        goto LABEL_34;
    }
    if ( v20 == -1 )
      goto LABEL_34;
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C, v21);
      __debugbreak();
    }
    v23 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
    if ( !v23 )
      goto LABEL_34;
    v28 = 0;
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v26, v23, v24) )
      break;
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
LABEL_48:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v10 = (unsigned __int16 *)pv;
      goto LABEL_50;
    }
  }
  v22 = -2147024882;
LABEL_51:
  CoTaskMemFree(pv);
  return v22;
}

```

## disassembly

```asm
0x180004e2c  mov     [rsp-8+arg_8], rbx
0x180004e31  mov     [rsp-8+arg_18], rsi
0x180004e36  push    rbp
0x180004e37  push    rdi
0x180004e38  push    r12
0x180004e3a  push    r14
0x180004e3c  push    r15
0x180004e3e  lea     rbp, [rsp-37h]
0x180004e43  sub     rsp, 90h
0x180004e4a  mov     rax, cs:__security_cookie
0x180004e51  xor     rax, rsp
0x180004e54  mov     [rbp+57h+var_30], rax
0x180004e58  mov     r15, r8
0x180004e5b  mov     rbx, rdx
0x180004e5e  mov     r14, rcx
0x180004e61  xor     r12d, r12d
0x180004e64  test    rdx, rdx
0x180004e67  jz      loc_18000508B
0x180004e6d  test    r8, r8
0x180004e70  jz      loc_18000508B
0x180004e76  mov     [r8], r12
0x180004e79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004e7d  inc     rax
0x180004e80  cmp     [rdx+rax*2], r12w
0x180004e85  jnz     short loc_180004E7D
0x180004e87  add     eax, eax
0x180004e89  mov     ecx, 3E8h
0x180004e8e  cmp     eax, 64h ; 'd'
0x180004e91  cmovl   eax, ecx
0x180004e94  mov     [rbp+57h+var_90], r12d
0x180004e98  mov     [rbp+57h+var_8C], eax
0x180004e9b  mov     ecx, eax
0x180004e9d  add     rcx, rcx
0x180004ea0  mov     eax, 0FFFFFFFFh
0x180004ea5  cmp     rcx, rax
0x180004ea8  jbe     short loc_180004EB6
0x180004eaa  mov     rax, r12
0x180004ead  mov     rdx, r12
0x180004eb0  mov     [rbp+57h+pv], rdx
0x180004eb4  jmp     short loc_180004ECE
0x180004eb6  mov     ecx, ecx; cb
0x180004eb8  call    cs:__imp_CoTaskMemAlloc
0x180004ebe  mov     rdx, rax
0x180004ec1  mov     [rbp+57h+pv], rax
0x180004ec5  test    rax, rax
0x180004ec8  jz      short loc_180004ECE
0x180004eca  mov     [rax], r12w
0x180004ece  test    rax, rax
0x180004ed1  jnz     short loc_180004EE6
0x180004ed3  mov     rcx, rax; pv
0x180004ed6  call    cs:__imp_CoTaskMemFree
0x180004edc  mov     eax, 8007000Eh
0x180004ee1  jmp     loc_180005090
0x180004ee6  mov     [r14], rbx
0x180004ee9  movzx   eax, word ptr [rbx]
0x180004eec  test    ax, ax
0x180004eef  jz      loc_180005065
0x180004ef5  cmp     ax, 25h ; '%'
0x180004ef9  jnz     loc_180005030
0x180004eff  mov     rcx, rbx; lpsz
0x180004f02  call    cs:__imp_CharNextW
0x180004f08  mov     [r14], rax
0x180004f0b  movzx   ecx, word ptr [rax]
0x180004f0e  cmp     cx, 25h ; '%'
0x180004f12  jnz     short loc_180004F1C
0x180004f14  mov     rdx, rax
0x180004f17  jmp     loc_180005033
0x180004f1c  test    rax, rax
0x180004f1f  jz      loc_180004FC8
0x180004f25  mov     rsi, r12
0x180004f28  jmp     short loc_180004F3C
0x180004f2a  cmp     cx, 25h ; '%'
0x180004f2e  jz      short loc_180004F43
0x180004f30  mov     rcx, rax; lpsz
0x180004f33  call    cs:__imp_CharNextW
0x180004f39  movzx   ecx, word ptr [rax]
0x180004f3c  test    cx, cx
0x180004f3f  jnz     short loc_180004F2A
0x180004f41  jmp     short loc_180004F46
0x180004f43  mov     rsi, rax
0x180004f46  test    rsi, rsi
0x180004f49  jz      short loc_180004FC8
0x180004f4b  mov     rax, rsi
0x180004f4e  sub     rax, [r14]
0x180004f51  sar     rax, 1
0x180004f54  cmp     rax, 1Fh
0x180004f58  jg      loc_18000507D
0x180004f5e  movsxd  r9, eax; MaxCount
0x180004f61  mov     r8, [r14]; Source
0x180004f64  mov     edx, 20h ; ' '; SizeInWords
0x180004f69  lea     rcx, [rbp+57h+Destination]; Destination
0x180004f6d  call    cs:__imp_wcsncpy_s
0x180004f73  test    eax, eax
0x180004f75  jz      short loc_180004F9B
0x180004f77  cmp     eax, 0Ch
0x180004f7a  jz      loc_1800050D9
0x180004f80  cmp     eax, 16h
0x180004f83  jz      loc_1800050CE
0x180004f89  cmp     eax, 22h ; '"'
0x180004f8c  jz      loc_1800050CE
0x180004f92  cmp     eax, 50h ; 'P'
0x180004f95  jnz     loc_1800050C3
0x180004f9b  mov     rdi, [r14+8]
0x180004f9f  mov     ebx, r12d
0x180004fa2  cmp     [rdi+18h], r12d
0x180004fa6  jle     short loc_180004FC8
0x180004fa8  movsxd  rax, ebx
0x180004fab  mov     rcx, [rdi+8]
0x180004faf  lea     rdx, [rbp+57h+Destination]; lpString2
0x180004fb3  mov     rcx, [rcx+rax*8]; lpString1
0x180004fb7  call    cs:__imp_lstrcmpiW
0x180004fbd  test    eax, eax
0x180004fbf  jz      short loc_180004FD2
0x180004fc1  inc     ebx
0x180004fc3  cmp     ebx, [rdi+18h]
0x180004fc6  jl      short loc_180004FA8
0x180004fc8  mov     ebx, 80020009h
0x180004fcd  jmp     loc_18000506F
0x180004fd2  cmp     ebx, 0FFFFFFFFh
0x180004fd5  jz      short loc_180004FC8
0x180004fd7  test    ebx, ebx
0x180004fd9  js      loc_1800050B8
0x180004fdf  cmp     ebx, [rdi+18h]
0x180004fe2  jge     loc_1800050B8
0x180004fe8  movsxd  rcx, ebx
0x180004feb  mov     rax, [rdi+10h]
0x180004fef  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x180004ff3  test    rdx, rdx
0x180004ff6  jz      short loc_180004FC8
0x180004ff8  mov     [rbp+57h+var_80], r12
0x180004ffc  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005000  inc     r8; int
0x180005003  cmp     [rdx+r8*2], r12w
0x180005008  jnz     short loc_180005000
0x18000500a  lea     rcx, [rbp+57h+var_90]; this
0x18000500e  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005013  nop
0x180005014  test    eax, eax
0x180005016  jz      short loc_180005084
0x180005018  mov     rax, [r14]
0x18000501b  jmp     short loc_180005029
0x18000501d  mov     rcx, rax; lpsz
0x180005020  call    cs:__imp_CharNextW
0x180005026  mov     [r14], rax
0x180005029  cmp     rax, rsi
0x18000502c  jnz     short loc_18000501D
0x18000502e  jmp     short loc_180005046
0x180005030  mov     rdx, rbx; unsigned __int16 *
0x180005033  mov     r8d, 1; int
0x180005039  lea     rcx, [rbp+57h+var_90]; this
0x18000503d  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x180005042  test    eax, eax
0x180005044  jz      short loc_180005084
0x180005046  mov     rcx, [r14]; lpsz
0x180005049  call    cs:__imp_CharNextW
0x18000504f  mov     rbx, rax
0x180005052  mov     [r14], rax
0x180005055  movzx   eax, word ptr [rax]
0x180005058  test    ax, ax
0x18000505b  jnz     loc_180004EF5
0x180005061  mov     rdx, [rbp+57h+pv]
0x180005065  mov     ebx, r12d
0x180005068  mov     [rbp+57h+pv], r12
0x18000506c  mov     [r15], rdx
0x18000506f  mov     rcx, [rbp+57h+pv]; pv
0x180005073  call    cs:__imp_CoTaskMemFree
0x180005079  mov     eax, ebx
0x18000507b  jmp     short loc_180005090
0x18000507d  mov     ebx, 80004005h
0x180005082  jmp     short loc_18000506F
0x180005084  mov     ebx, 8007000Eh
0x180005089  jmp     short loc_18000506F
0x18000508b  mov     eax, 80004003h
0x180005090  mov     rcx, [rbp+57h+var_30]
0x180005094  xor     rcx, rsp; StackCookie
0x180005097  call    __security_check_cookie
0x18000509c  lea     r11, [rsp+0B0h+var_20]
0x1800050a4  mov     rbx, [r11+38h]
0x1800050a8  mov     rsi, [r11+48h]
0x1800050ac  mov     rsp, r11
0x1800050af  pop     r15
0x1800050b1  pop     r14
0x1800050b3  pop     r12
0x1800050b5  pop     rdi
0x1800050b6  pop     rbp
0x1800050b7  retn
0x1800050b8  mov     ecx, 0C000008Ch; unsigned int
0x1800050bd  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800050c2  int     3; Trap to Debugger
0x1800050c3  mov     ecx, 80004005h; int
0x1800050c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800050ce  mov     ecx, 80070057h; int
0x1800050d3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800050d9  mov     ecx, 8007000Eh; int
0x1800050de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
