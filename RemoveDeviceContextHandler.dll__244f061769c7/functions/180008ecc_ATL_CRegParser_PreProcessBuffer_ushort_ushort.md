# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x180008ecc`
- end: `0x18000916a`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `670`
- prototype: `__int64 __fastcall(const wchar_t **this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009538`

## callees

- `0x180006cbc`
- `0x180006df4`
- `0x180008ecc`
- `0x18000b5c4`
- `0x18000c990`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008ff6`
- `msvcrt!wcsncpy_s` at `0x180008ff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008f45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800090fd`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fbb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800090a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800090d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008f8a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180008fbb`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800090a6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800090d0`
- `KERNEL32!lstrcmpiW` at `0x180009041`
- `KERNEL32!lstrcmpiW` at `0x180009041`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(const wchar_t **this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  void *v9; // rcx
  _WORD *v11; // rax
  WCHAR v12; // ax
  LPWSTR v13; // rax
  WCHAR v14; // cx
  const unsigned __int16 *v15; // rdx
  const WCHAR *v16; // rbp
  __int64 v17; // rax
  errno_t v18; // eax
  const wchar_t *v19; // rdi
  int v20; // ebx
  unsigned int v21; // ebx
  const unsigned __int16 *v22; // rdx
  __int64 v23; // r8
  const WCHAR *i; // rax
  _DWORD v25[2]; // [rsp+20h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-80h]
  wchar_t Destination[32]; // [rsp+30h] [rbp-78h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  v25[0] = 0;
  if ( v7 < 100 )
    v7 = 1000;
  v25[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 > 0xFFFFFFFF )
  {
    v9 = 0;
LABEL_9:
    CoTaskMemFree(v9);
    return 2147942414LL;
  }
  v11 = CoTaskMemAlloc((unsigned int)v8);
  pv = v11;
  v9 = v11;
  if ( !v11 )
    goto LABEL_9;
  *v11 = 0;
  *this = v4;
  v12 = *v4;
  if ( !*v4 )
  {
LABEL_48:
    v21 = 0;
    pv = 0;
    *a3 = (unsigned __int16 *)v9;
    goto LABEL_49;
  }
  while ( 1 )
  {
    if ( v12 != 37 )
    {
      v15 = v4;
LABEL_45:
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v15, 1) )
        break;
      goto LABEL_46;
    }
    v13 = CharNextW(v4);
    *this = v13;
    v14 = *v13;
    if ( *v13 == 37 )
    {
      v15 = v13;
      goto LABEL_45;
    }
    if ( !v13 )
      goto LABEL_32;
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
LABEL_32:
      v21 = -2147352567;
      goto LABEL_49;
    }
    v17 = v16 - *this;
    if ( v17 > 31 )
    {
      v21 = -2147467259;
      goto LABEL_49;
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
      goto LABEL_32;
    while ( lstrcmpiW(*(LPCWSTR *)(*((_QWORD *)v19 + 1) + 8LL * v20), Destination) )
    {
      if ( ++v20 >= *((_DWORD *)v19 + 6) )
        goto LABEL_32;
    }
    if ( v20 == -1 )
      goto LABEL_32;
    if ( v20 < 0 || v20 >= *((_DWORD *)v19 + 6) )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    v22 = *(const unsigned __int16 **)(*((_QWORD *)v19 + 2) + 8LL * v20);
    if ( !v22 )
      goto LABEL_32;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v25, v22, v23) )
      break;
    for ( i = *this; i != v16; *this = i )
      i = CharNextW(i);
LABEL_46:
    v4 = CharNextW(*this);
    *this = v4;
    v12 = *v4;
    if ( !*v4 )
    {
      v9 = pv;
      goto LABEL_48;
    }
  }
  v21 = -2147024882;
LABEL_49:
  CoTaskMemFree(pv);
  return v21;
}

```

## disassembly

```asm
0x180008ecc  mov     [rsp+arg_8], rbx
0x180008ed1  push    rbp
0x180008ed2  push    rsi
0x180008ed3  push    rdi
0x180008ed4  push    r14
0x180008ed6  push    r15
0x180008ed8  sub     rsp, 80h
0x180008edf  mov     rax, cs:__security_cookie
0x180008ee6  xor     rax, rsp
0x180008ee9  mov     [rsp+0A8h+var_38], rax
0x180008eee  xor     r15d, r15d
0x180008ef1  mov     r14, r8
0x180008ef4  mov     rbx, rdx
0x180008ef7  mov     rsi, rcx
0x180008efa  test    rdx, rdx
0x180008efd  jz      loc_180009115
0x180008f03  test    r8, r8
0x180008f06  jz      loc_180009115
0x180008f0c  mov     [r8], r15
0x180008f0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f13  inc     rax
0x180008f16  cmp     [rdx+rax*2], r15w
0x180008f1b  jnz     short loc_180008F13
0x180008f1d  add     eax, eax
0x180008f1f  mov     [rsp+0A8h+var_88], r15d
0x180008f24  cmp     eax, 64h ; 'd'
0x180008f27  mov     ecx, 3E8h
0x180008f2c  cmovl   eax, ecx
0x180008f2f  mov     ecx, eax
0x180008f31  mov     [rsp+0A8h+var_84], eax
0x180008f35  add     rcx, rcx
0x180008f38  mov     eax, 0FFFFFFFFh
0x180008f3d  cmp     rcx, rax
0x180008f40  jbe     short loc_180008F55
0x180008f42  mov     rcx, r15; pv
0x180008f45  call    cs:__imp_CoTaskMemFree
0x180008f4b  mov     eax, 8007000Eh
0x180008f50  jmp     loc_18000911A
0x180008f55  mov     ecx, ecx; cb
0x180008f57  call    cs:__imp_CoTaskMemAlloc
0x180008f5d  mov     [rsp+0A8h+pv], rax
0x180008f62  mov     rcx, rax
0x180008f65  test    rax, rax
0x180008f68  jz      short loc_180008F45
0x180008f6a  mov     [rax], r15w
0x180008f6e  mov     [rsi], rbx
0x180008f71  movzx   eax, word ptr [rbx]
0x180008f74  test    ax, ax
0x180008f77  jz      loc_1800090ED
0x180008f7d  cmp     ax, 25h ; '%'
0x180008f81  jnz     loc_1800090B6
0x180008f87  mov     rcx, rbx; lpsz
0x180008f8a  call    cs:__imp_CharNextW
0x180008f90  mov     [rsi], rax
0x180008f93  movzx   ecx, word ptr [rax]
0x180008f96  cmp     cx, 25h ; '%'
0x180008f9a  jnz     short loc_180008FA4
0x180008f9c  mov     rdx, rax
0x180008f9f  jmp     loc_1800090B9
0x180008fa4  test    rax, rax
0x180008fa7  jz      loc_180009052
0x180008fad  mov     rbp, r15
0x180008fb0  jmp     short loc_180008FC4
0x180008fb2  cmp     cx, 25h ; '%'
0x180008fb6  jz      short loc_180008FCB
0x180008fb8  mov     rcx, rax; lpsz
0x180008fbb  call    cs:__imp_CharNextW
0x180008fc1  movzx   ecx, word ptr [rax]
0x180008fc4  test    cx, cx
0x180008fc7  jnz     short loc_180008FB2
0x180008fc9  jmp     short loc_180008FCE
0x180008fcb  mov     rbp, rax
0x180008fce  test    rbp, rbp
0x180008fd1  jz      short loc_180009052
0x180008fd3  mov     rax, rbp
0x180008fd6  sub     rax, [rsi]
0x180008fd9  sar     rax, 1
0x180008fdc  cmp     rax, 1Fh
0x180008fe0  jg      loc_180009107
0x180008fe6  mov     r8, [rsi]; Source
0x180008fe9  lea     rcx, [rsp+0A8h+Destination]; Destination
0x180008fee  movsxd  r9, eax; MaxCount
0x180008ff1  mov     edx, 20h ; ' '; SizeInWords
0x180008ff6  call    cs:__imp_wcsncpy_s
0x180008ffc  test    eax, eax
0x180008ffe  jz      short loc_180009024
0x180009000  cmp     eax, 0Ch
0x180009003  jz      loc_18000915F
0x180009009  cmp     eax, 16h
0x18000900c  jz      loc_180009154
0x180009012  cmp     eax, 22h ; '"'
0x180009015  jz      loc_180009154
0x18000901b  cmp     eax, 50h ; 'P'
0x18000901e  jnz     loc_180009149
0x180009024  mov     rdi, [rsi+8]
0x180009028  mov     ebx, r15d
0x18000902b  cmp     [rdi+18h], r15d
0x18000902f  jle     short loc_180009052
0x180009031  mov     rcx, [rdi+8]
0x180009035  lea     rdx, [rsp+0A8h+Destination]; lpString2
0x18000903a  movsxd  rax, ebx
0x18000903d  mov     rcx, [rcx+rax*8]; lpString1
0x180009041  call    cs:__imp_lstrcmpiW
0x180009047  test    eax, eax
0x180009049  jz      short loc_18000905C
0x18000904b  inc     ebx
0x18000904d  cmp     ebx, [rdi+18h]
0x180009050  jl      short loc_180009031
0x180009052  mov     ebx, 80020009h
0x180009057  jmp     loc_1800090F8
0x18000905c  cmp     ebx, 0FFFFFFFFh
0x18000905f  jz      short loc_180009052
0x180009061  test    ebx, ebx
0x180009063  js      loc_18000913E
0x180009069  cmp     ebx, [rdi+18h]
0x18000906c  jge     loc_18000913E
0x180009072  mov     rax, [rdi+10h]
0x180009076  movsxd  rcx, ebx
0x180009079  mov     rdx, [rax+rcx*8]; unsigned __int16 *
0x18000907d  test    rdx, rdx
0x180009080  jz      short loc_180009052
0x180009082  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009086  inc     r8; int
0x180009089  cmp     [rdx+r8*2], r15w
0x18000908e  jnz     short loc_180009086
0x180009090  lea     rcx, [rsp+0A8h+var_88]; this
0x180009095  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000909a  test    eax, eax
0x18000909c  jz      short loc_18000910E
0x18000909e  mov     rax, [rsi]
0x1800090a1  jmp     short loc_1800090AF
0x1800090a3  mov     rcx, rax; lpsz
0x1800090a6  call    cs:__imp_CharNextW
0x1800090ac  mov     [rsi], rax
0x1800090af  cmp     rax, rbp
0x1800090b2  jnz     short loc_1800090A3
0x1800090b4  jmp     short loc_1800090CD
0x1800090b6  mov     rdx, rbx; unsigned __int16 *
0x1800090b9  mov     r8d, 1; int
0x1800090bf  lea     rcx, [rsp+0A8h+var_88]; this
0x1800090c4  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x1800090c9  test    eax, eax
0x1800090cb  jz      short loc_18000910E
0x1800090cd  mov     rcx, [rsi]; lpsz
0x1800090d0  call    cs:__imp_CharNextW
0x1800090d6  mov     rbx, rax
0x1800090d9  mov     [rsi], rax
0x1800090dc  movzx   eax, word ptr [rax]
0x1800090df  test    ax, ax
0x1800090e2  jnz     loc_180008F7D
0x1800090e8  mov     rcx, [rsp+0A8h+pv]
0x1800090ed  mov     ebx, r15d
0x1800090f0  mov     [rsp+0A8h+pv], r15
0x1800090f5  mov     [r14], rcx
0x1800090f8  mov     rcx, [rsp+0A8h+pv]; pv
0x1800090fd  call    cs:__imp_CoTaskMemFree
0x180009103  mov     eax, ebx
0x180009105  jmp     short loc_18000911A
0x180009107  mov     ebx, 80004005h
0x18000910c  jmp     short loc_1800090F8
0x18000910e  mov     ebx, 8007000Eh
0x180009113  jmp     short loc_1800090F8
0x180009115  mov     eax, 80004003h
0x18000911a  mov     rcx, [rsp+0A8h+var_38]
0x18000911f  xor     rcx, rsp; StackCookie
0x180009122  call    __security_check_cookie
0x180009127  mov     rbx, [rsp+0A8h+arg_8]
0x18000912f  add     rsp, 80h
0x180009136  pop     r15
0x180009138  pop     r14
0x18000913a  pop     rdi
0x18000913b  pop     rsi
0x18000913c  pop     rbp
0x18000913d  retn
0x18000913e  mov     ecx, 0C000008Ch; unsigned int
0x180009143  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180009148  int     3; Trap to Debugger
0x180009149  mov     ecx, 80004005h; int
0x18000914e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009154  mov     ecx, 80070057h; int
0x180009159  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000915f  mov     ecx, 8007000Eh; int
0x180009164  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
