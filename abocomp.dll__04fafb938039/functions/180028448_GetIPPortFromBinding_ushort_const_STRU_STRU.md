# GetIPPortFromBinding(ushort const *,STRU *,STRU *)

- ea: `0x180028448`
- end: `0x18002864c`
- name: `?GetIPPortFromBinding@@YAJPEBGPEAVSTRU@@1@Z`
- size: `516`
- prototype: `__int64 __fastcall(wchar_t *Str, struct STRU *, struct STRU *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000b178`
- `0x18000ef4c`
- `0x180028c64`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180028448`

## import_xrefs

- `msvcrt!wcschr` at `0x180028518`
- `msvcrt!wcschr` at `0x18002857c`
- `msvcrt!wcschr` at `0x180028518`
- `msvcrt!wcschr` at `0x18002857c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002855e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285c1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285de`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285fb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002855e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285c1`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285de`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800285fb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800284a3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800284c9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800284a3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800284c9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002860f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002861a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002860f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002861a`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800284f0`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800284f9`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800284f0`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800284f9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800285d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800285ef`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800285d2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800285ef`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002854a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800285ad`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002854a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800285ad`

## pseudocode

```c
__int64 __fastcall GetIPPortFromBinding(wchar_t *Str, struct STRU *a2, struct STRU *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  int v10; // eax
  int v11; // ebx
  wchar_t *v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // rax
  _BYTE v17[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v18[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v19[128]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v20[128]; // [rsp+190h] [rbp+90h] BYREF

  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v18, v19, 0x80u);
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v17, v20, 0x80u);
  if ( Str && a2 && a3 )
  {
    STRU::Reset(a2);
    STRU::Reset(a3);
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( Str[v7] );
    v8 = wcschr(Str, 0x3Au);
    v9 = v8;
    if ( v8 )
      v7 = v8 - Str;
    if ( !(_DWORD)v7 || (_DWORD)v7 == 1 && *Str == 42 )
      v10 = STRU::Copy((STRU *)v18, L"0.0.0.0");
    else
      v10 = STRU::Copy((STRU *)v18, Str, v7);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( !v9 )
        goto LABEL_21;
      v12 = wcschr(v9 + 1, 0x3Au);
      if ( v12 )
      {
        LODWORD(v6) = v12 - v9 - 1;
      }
      else
      {
        do
          ++v6;
        while ( v9[v6 + 1] );
      }
      if ( (_DWORD)v6 )
        v13 = STRU::Copy((STRU *)v17, v9 + 1, v6);
      else
LABEL_21:
        v13 = STRU::Copy((STRU *)v17, L"0");
      v11 = v13;
      if ( v13 >= 0 )
      {
        v14 = STRU::QueryStr((STRU *)v18);
        v11 = STRU::Copy(a2, v14);
        if ( v11 >= 0 )
        {
          v15 = STRU::QueryStr((STRU *)v17);
          v11 = STRU::Copy(a3, v15);
        }
      }
    }
  }
  else
  {
    v11 = -2147024809;
  }
  STRU::~STRU((STRU *)v17);
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180028448  mov     [rsp-8+arg_18], rbx
0x18002844d  push    rbp
0x18002844e  push    rsi
0x18002844f  push    rdi
0x180028450  push    r12
0x180028452  push    r13
0x180028454  push    r14
0x180028456  push    r15
0x180028458  lea     rbp, [rsp-1A0h]
0x180028460  sub     rsp, 2A0h
0x180028467  mov     rax, cs:__security_cookie
0x18002846e  xor     rax, rsp
0x180028471  mov     [rbp+1D0h+var_40], rax
0x180028478  mov     r15, r8
0x18002847b  mov     r12, rdx
0x18002847e  mov     r14, rcx
0x180028481  mov     edi, 100h
0x180028486  mov     r8d, edi; Size
0x180028489  lea     rcx, [rbp+1D0h+var_240]; void *
0x18002848d  xor     edx, edx; Val
0x18002848f  call    memset_0
0x180028494  lea     ebx, [rdi-80h]
0x180028497  mov     r8d, ebx
0x18002849a  lea     rdx, [rbp+1D0h+var_240]
0x18002849e  lea     rcx, [rsp+2D0h+var_278]
0x1800284a3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800284a9  mov     r8d, edi; Size
0x1800284ac  lea     rcx, [rbp+1D0h+var_140]; void *
0x1800284b3  xor     edx, edx; Val
0x1800284b5  call    memset_0
0x1800284ba  mov     r8d, ebx
0x1800284bd  lea     rdx, [rbp+1D0h+var_140]
0x1800284c4  lea     rcx, [rsp+2D0h+var_2B0]
0x1800284c9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800284cf  xor     r13d, r13d
0x1800284d2  test    r14, r14
0x1800284d5  jz      loc_180028605
0x1800284db  test    r12, r12
0x1800284de  jz      loc_180028605
0x1800284e4  test    r15, r15
0x1800284e7  jz      loc_180028605
0x1800284ed  mov     rcx, r12
0x1800284f0  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800284f6  mov     rcx, r15
0x1800284f9  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800284ff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028503  mov     rbx, rdi
0x180028506  inc     rbx
0x180028509  cmp     [r14+rbx*2], r13w
0x18002850e  jnz     short loc_180028506
0x180028510  mov     edx, 3Ah ; ':'; Ch
0x180028515  mov     rcx, r14; Str
0x180028518  call    cs:__imp_wcschr
0x18002851e  mov     rsi, rax
0x180028521  test    rax, rax
0x180028524  jz      short loc_18002852F
0x180028526  mov     rbx, rax
0x180028529  sub     rbx, r14
0x18002852c  sar     rbx, 1
0x18002852f  test    ebx, ebx
0x180028531  jz      short loc_180028552
0x180028533  cmp     ebx, 1
0x180028536  jnz     short loc_18002853F
0x180028538  cmp     word ptr [r14], 2Ah ; '*'
0x18002853d  jz      short loc_180028552
0x18002853f  mov     r8d, ebx
0x180028542  lea     rcx, [rsp+2D0h+var_278]
0x180028547  mov     rdx, r14
0x18002854a  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180028550  jmp     short loc_180028564
0x180028552  lea     rdx, a0000; "0.0.0.0"
0x180028559  lea     rcx, [rsp+2D0h+var_278]
0x18002855e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180028564  mov     ebx, eax
0x180028566  test    eax, eax
0x180028568  js      loc_18002860A
0x18002856e  test    rsi, rsi
0x180028571  jz      short loc_1800285B5
0x180028573  mov     edx, 3Ah ; ':'; Ch
0x180028578  lea     rcx, [rsi+2]; Str
0x18002857c  call    cs:__imp_wcschr
0x180028582  test    rax, rax
0x180028585  jnz     short loc_180028594
0x180028587  inc     rdi
0x18002858a  cmp     [rsi+rdi*2+2], r13w
0x180028590  jnz     short loc_180028587
0x180028592  jmp     short loc_18002859D
0x180028594  sub     rax, rsi
0x180028597  sar     rax, 1
0x18002859a  lea     edi, [rax-1]
0x18002859d  lea     rcx, [rsp+2D0h+var_2B0]
0x1800285a2  test    edi, edi
0x1800285a4  jz      short loc_1800285BA
0x1800285a6  mov     r8d, edi
0x1800285a9  lea     rdx, [rsi+2]
0x1800285ad  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800285b3  jmp     short loc_1800285C7
0x1800285b5  lea     rcx, [rsp+2D0h+var_2B0]
0x1800285ba  lea     rdx, a0; "0"
0x1800285c1  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800285c7  mov     ebx, eax
0x1800285c9  test    eax, eax
0x1800285cb  js      short loc_18002860A
0x1800285cd  lea     rcx, [rsp+2D0h+var_278]
0x1800285d2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800285d8  mov     rdx, rax
0x1800285db  mov     rcx, r12
0x1800285de  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800285e4  mov     ebx, eax
0x1800285e6  test    eax, eax
0x1800285e8  js      short loc_18002860A
0x1800285ea  lea     rcx, [rsp+2D0h+var_2B0]
0x1800285ef  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800285f5  mov     rdx, rax
0x1800285f8  mov     rcx, r15
0x1800285fb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180028601  mov     ebx, eax
0x180028603  jmp     short loc_18002860A
0x180028605  mov     ebx, 80070057h
0x18002860a  lea     rcx, [rsp+2D0h+var_2B0]
0x18002860f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180028615  lea     rcx, [rsp+2D0h+var_278]
0x18002861a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180028620  mov     eax, ebx
0x180028622  mov     rcx, [rbp+1D0h+var_40]
0x180028629  xor     rcx, rsp; StackCookie
0x18002862c  call    __security_check_cookie
0x180028631  mov     rbx, [rsp+2D0h+arg_18]
0x180028639  add     rsp, 2A0h
0x180028640  pop     r15
0x180028642  pop     r14
0x180028644  pop     r13
0x180028646  pop     r12
0x180028648  pop     rdi
0x180028649  pop     rsi
0x18002864a  pop     rbp
0x18002864b  retn
```
