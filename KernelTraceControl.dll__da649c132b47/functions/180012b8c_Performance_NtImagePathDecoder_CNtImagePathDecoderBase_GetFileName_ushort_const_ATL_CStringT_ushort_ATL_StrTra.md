# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180012b8c`
- end: `0x180012df3`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `615`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a30c`

## callees

- `0x18000139c`
- `0x180012b8c`
- `0x180012df4`
- `0x1800130a8`
- `0x1800278f6`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180012bd3`
- `msvcrt!wcsncmp` at `0x180012c32`
- `msvcrt!wcsncmp` at `0x180012d25`
- `msvcrt!wcsncmp` at `0x180012bd3`
- `msvcrt!wcsncmp` at `0x180012c32`
- `msvcrt!wcsncmp` at `0x180012d25`
- `msvcrt!wcschr` at `0x180012c50`
- `msvcrt!wcschr` at `0x180012ccc`
- `msvcrt!wcschr` at `0x180012c50`
- `msvcrt!wcschr` at `0x180012ccc`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
        _QWORD *a1,
        __int64 a2,
        __int64 *a3)
{
  _QWORD *v3; // rbx
  const wchar_t *v7; // rcx
  _QWORD *i; // rbx
  _QWORD *v9; // r8
  __int64 v10; // r9
  const wchar_t *v11; // rcx
  _QWORD *v12; // r8
  __int64 v13; // rax
  wchar_t *v15; // rax
  unsigned __int16 *v16; // rdi
  __int64 v17; // rax

  v3 = (_QWORD *)a1[1];
  if ( v3 != (_QWORD *)a1[2] )
  {
    while ( 1 )
    {
      v7 = v3[4] < 8u ? (const wchar_t *)(v3 + 1) : (const wchar_t *)v3[1];
      if ( !wcsncmp(v7, (const wchar_t *)a2, v3[3]) )
        break;
      v3 += 10;
      if ( v3 == (_QWORD *)a1[2] )
        goto LABEL_7;
    }
    if ( v3[9] < 8u )
      v9 = v3 + 6;
    else
      v9 = (_QWORD *)v3[6];
    v10 = a2 + 2LL * v3[3];
    goto LABEL_12;
  }
LABEL_7:
  for ( i = (_QWORD *)a1[5]; i != (_QWORD *)a1[6]; i += 5 )
  {
    if ( i[4] < 8u )
      v11 = (const wchar_t *)(i + 1);
    else
      v11 = (const wchar_t *)i[1];
    if ( !wcsncmp(v11, (const wchar_t *)a2, i[3]) )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(&qword_18002BEF8 + v13) );
      goto LABEL_26;
    }
  }
  if ( !wcschr((const wchar_t *)a2, 0x5Cu) )
  {
    if ( !a1[11] )
      ATL::AtlThrowImpl(-2147418113);
    if ( a1[12] < 8u )
      v12 = a1 + 9;
    else
      v12 = (_QWORD *)a1[9];
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a3,
      L"%ws\\drivers\\%ws",
      v12,
      a2);
    return 1;
  }
  if ( *(_WORD *)a2 != 92
    || *(_WORD *)(a2 + 2) != 59
    || !*(_WORD *)(a2 + 4)
    || *(_WORD *)(a2 + 6) != 58
    || (v15 = wcschr((const wchar_t *)(a2 + 8), 0x5Cu)) == 0 )
  {
    if ( *(_WORD *)a2 && *(_WORD *)(a2 + 2) != 58 )
    {
      if ( !a1[16] )
        ATL::AtlThrowImpl(-2147418113);
      if ( *(_WORD *)a2 != 92 )
      {
        if ( a1[17] < 8u )
          v9 = a1 + 14;
        else
          v9 = (_QWORD *)a1[14];
        v10 = a2;
LABEL_12:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%ws%ws",
          v9,
          v10);
        return 1;
      }
      if ( !wcsncmp(
              (const wchar_t *)a2,
              `Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName'::`35'::wchDevicePrefix,
              8u) )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(&qword_18002BEF8 + v13) );
LABEL_26:
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &qword_18002BEF8, v13);
        return 0;
      }
      if ( wcscmp_0((const wchar_t *)a2, L"\\FI_UNKNOWN") )
      {
        if ( a1[17] < 8u )
          v16 = (unsigned __int16 *)(a1 + 14);
        else
          v16 = (unsigned __int16 *)a1[14];
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%wc:%ws",
          *v16,
          a2);
        return 1;
      }
    }
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(a2 + 2 * v17) );
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, (const void *)a2, v17);
    return 1;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    a3,
    L"\\%ws",
    v15);
  return 1;
}

```

## disassembly

```asm
0x180012b8c  mov     rax, rsp
0x180012b8f  mov     [rax+8], rbx
0x180012b93  mov     [rax+10h], rbp
0x180012b97  mov     [rax+18h], rsi
0x180012b9b  mov     [rax+20h], rdi
0x180012b9f  push    r14
0x180012ba1  sub     rsp, 20h
0x180012ba5  mov     rbx, [rcx+8]
0x180012ba9  xor     r14d, r14d
0x180012bac  mov     rbp, r8
0x180012baf  mov     rsi, rdx
0x180012bb2  mov     rdi, rcx
0x180012bb5  cmp     rbx, [rcx+10h]
0x180012bb9  jz      short loc_180012BE7
0x180012bbb  cmp     qword ptr [rbx+20h], 8
0x180012bc0  jb      short loc_180012BC8
0x180012bc2  mov     rcx, [rbx+8]
0x180012bc6  jmp     short loc_180012BCC
0x180012bc8  lea     rcx, [rbx+8]; String1
0x180012bcc  mov     r8, [rbx+18h]; MaxCount
0x180012bd0  mov     rdx, rsi; String2
0x180012bd3  call    cs:__imp_wcsncmp
0x180012bd9  test    eax, eax
0x180012bdb  jz      short loc_180012BED
0x180012bdd  add     rbx, 50h ; 'P'
0x180012be1  cmp     rbx, [rdi+10h]
0x180012be5  jnz     short loc_180012BBB
0x180012be7  mov     rbx, [rdi+28h]
0x180012beb  jmp     short loc_180012C40
0x180012bed  cmp     qword ptr [rbx+48h], 8
0x180012bf2  mov     rax, [rbx+18h]
0x180012bf6  jb      short loc_180012BFE
0x180012bf8  mov     r8, [rbx+30h]
0x180012bfc  jmp     short loc_180012C02
0x180012bfe  lea     r8, [rbx+30h]
0x180012c02  lea     r9, [rsi+rax*2]
0x180012c06  lea     rdx, aWsWs; "%ws%ws"
0x180012c0d  mov     rcx, rbp
0x180012c10  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012c15  jmp     loc_180012DC0
0x180012c1a  cmp     qword ptr [rbx+20h], 8
0x180012c1f  jb      short loc_180012C27
0x180012c21  mov     rcx, [rbx+8]
0x180012c25  jmp     short loc_180012C2B
0x180012c27  lea     rcx, [rbx+8]; String1
0x180012c2b  mov     r8, [rbx+18h]; MaxCount
0x180012c2f  mov     rdx, rsi; String2
0x180012c32  call    cs:__imp_wcsncmp
0x180012c38  test    eax, eax
0x180012c3a  jz      short loc_180012C72
0x180012c3c  add     rbx, 28h ; '('
0x180012c40  cmp     rbx, [rdi+30h]
0x180012c44  jnz     short loc_180012C1A
0x180012c46  mov     ebx, 5Ch ; '\'
0x180012c4b  mov     rcx, rsi; Str
0x180012c4e  mov     edx, ebx; Ch
0x180012c50  call    cs:__imp_wcschr
0x180012c56  test    rax, rax
0x180012c59  jnz     short loc_180012CAC
0x180012c5b  cmp     [rdi+58h], r14
0x180012c5f  jz      loc_180012DDD
0x180012c65  cmp     qword ptr [rdi+60h], 8
0x180012c6a  jb      short loc_180012C99
0x180012c6c  mov     r8, [rdi+48h]
0x180012c70  jmp     short loc_180012C9D
0x180012c72  lea     rdx, qword_18002BEF8
0x180012c79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012c7d  inc     rax
0x180012c80  cmp     [rdx+rax*2], r14w
0x180012c85  jnz     short loc_180012C7D
0x180012c87  mov     r8d, eax
0x180012c8a  mov     rcx, rbp
0x180012c8d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180012c92  xor     al, al
0x180012c94  jmp     loc_180012DC2
0x180012c99  lea     r8, [rdi+48h]
0x180012c9d  mov     r9, rsi
0x180012ca0  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x180012ca7  jmp     loc_180012C0D
0x180012cac  cmp     [rsi], bx
0x180012caf  jnz     short loc_180012CEE
0x180012cb1  cmp     word ptr [rsi+2], 3Bh ; ';'
0x180012cb6  jnz     short loc_180012CEE
0x180012cb8  cmp     [rsi+4], r14w
0x180012cbd  jz      short loc_180012CEE
0x180012cbf  cmp     word ptr [rsi+6], 3Ah ; ':'
0x180012cc4  jnz     short loc_180012CEE
0x180012cc6  mov     edx, ebx; Ch
0x180012cc8  lea     rcx, [rsi+8]; Str
0x180012ccc  call    cs:__imp_wcschr
0x180012cd2  test    rax, rax
0x180012cd5  jz      short loc_180012CEE
0x180012cd7  mov     r8, rax
0x180012cda  lea     rdx, aWs_0; "\\%ws"
0x180012ce1  mov     rcx, rbp
0x180012ce4  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012ce9  jmp     loc_180012DC0
0x180012cee  cmp     [rsi], r14w
0x180012cf2  jz      loc_180012DA4
0x180012cf8  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180012cfd  jz      loc_180012DA4
0x180012d03  cmp     [rdi+80h], r14
0x180012d0a  jz      loc_180012DE8
0x180012d10  cmp     [rsi], bx
0x180012d13  jnz     short loc_180012D88
0x180012d15  mov     r8d, 8; MaxCount
0x180012d1b  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x180012d22  mov     rcx, rsi; String1
0x180012d25  call    cs:__imp_wcsncmp
0x180012d2b  test    eax, eax
0x180012d2d  jnz     short loc_180012D49
0x180012d2f  lea     rdx, qword_18002BEF8
0x180012d36  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d3a  inc     rax
0x180012d3d  cmp     [rdx+rax*2], r14w
0x180012d42  jnz     short loc_180012D3A
0x180012d44  jmp     loc_180012C87
0x180012d49  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x180012d50  mov     rcx, rsi; String1
0x180012d53  call    wcscmp_0
0x180012d58  test    eax, eax
0x180012d5a  jz      short loc_180012DA4
0x180012d5c  cmp     qword ptr [rdi+88h], 8
0x180012d64  jb      short loc_180012D6C
0x180012d66  mov     rdi, [rdi+70h]
0x180012d6a  jmp     short loc_180012D70
0x180012d6c  add     rdi, 70h ; 'p'
0x180012d70  movzx   r8d, word ptr [rdi]
0x180012d74  lea     rdx, aWcWs; "%wc:%ws"
0x180012d7b  mov     r9, rsi
0x180012d7e  mov     rcx, rbp
0x180012d81  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180012d86  jmp     short loc_180012DC0
0x180012d88  cmp     qword ptr [rdi+88h], 8
0x180012d90  jb      short loc_180012D98
0x180012d92  mov     r8, [rdi+70h]
0x180012d96  jmp     short loc_180012D9C
0x180012d98  lea     r8, [rdi+70h]
0x180012d9c  mov     r9, rsi
0x180012d9f  jmp     loc_180012C06
0x180012da4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012da8  inc     rax
0x180012dab  cmp     [rsi+rax*2], r14w
0x180012db0  jnz     short loc_180012DA8
0x180012db2  mov     r8d, eax
0x180012db5  mov     rdx, rsi
0x180012db8  mov     rcx, rbp
0x180012dbb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180012dc0  mov     al, 1
0x180012dc2  mov     rbx, [rsp+28h+arg_0]
0x180012dc7  mov     rbp, [rsp+28h+arg_8]
0x180012dcc  mov     rsi, [rsp+28h+arg_10]
0x180012dd1  mov     rdi, [rsp+28h+arg_18]
0x180012dd6  add     rsp, 20h
0x180012dda  pop     r14
0x180012ddc  retn
0x180012ddd  mov     ecx, 8000FFFFh; int
0x180012de2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012de8  mov     ecx, 8000FFFFh; int
0x180012ded  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
