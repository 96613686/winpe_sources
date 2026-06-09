# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(ushort const *,int)

- ea: `0x180013e40`
- end: `0x180013ff8`
- name: `?Parse@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA?AW4REParseError@2@PEBGH@Z`
- size: `440`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000d770`
- `0x1800166b4`

## callees

- `0x180003bb8`
- `0x180011188`
- `0x180013e40`
- `0x180014000`
- `0x180014bfc`
- `0x180015b80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180013eba`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180013eba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013fb5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013e69`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013fb5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013e8b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013e8b`

## string_xrefs

- `0x180013ea0`: `^(((srv)|(cache)|(symsrv\*symsrv\.dll))\*{\c:[^*]*})`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Parse(unsigned int *a1, wchar_t *a2, int a3)
{
  void *v4; // rcx
  ATL::Checked *v5; // rax
  wchar_t *v6; // rdi
  errno_t v7; // eax
  int v8; // eax
  unsigned __int64 v9; // rsi
  wchar_t *v10; // rax
  unsigned __int64 v12; // [rsp+20h] [rbp-18h]
  wchar_t *v13; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+50h] [rbp+18h] BYREF

  v14 = a3;
  v13 = a2;
  v4 = (void *)*((_QWORD *)a1 + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)a1 + 1) = 0;
  }
  *((_QWORD *)a1 + 2) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 5) = 0;
  *a1 = 0;
  a1[12] = 0;
  v5 = (ATL::Checked *)malloc(0x6Au);
  v6 = (wchar_t *)v5;
  if ( !v5 )
    return 1;
  ATL::Checked::memcpy_s(
    v5,
    (void *)0x6A,
    (unsigned __int64)L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})",
    (const void *)0x6A,
    v12);
  v7 = _wcslwr_s(v6, 0x35u);
  if ( v7 )
  {
    if ( v7 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v7 == 22 || v7 == 34 )
      goto LABEL_25;
    if ( v7 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  v13 = v6;
  v8 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 16);
  v9 = v8;
  if ( v8 < 0 )
    return 1;
  if ( *v13 != 94 )
  {
    if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 29) >= 0 )
    {
      v10 = v13;
      goto LABEL_15;
    }
    return 1;
  }
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 28) < 0 )
    return 1;
  v10 = ++v13;
LABEL_15:
  LOBYTE(v14) = 1;
  if ( *v10 && (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(a1, &v13, &v14) >= 0 )
  {
    LOBYTE(v14) = 1;
    ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(a1, &v13, &v14);
  }
  if ( *a1 )
    goto LABEL_21;
  if ( v9 >= *((_QWORD *)a1 + 2) )
LABEL_25:
    ATL::AtlThrowImpl(-2147024809);
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 16 * v9 + 8) = 2;
  if ( (int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction((__int64)a1, 30) < 0 )
    return 1;
LABEL_21:
  if ( v6 != (wchar_t *)L"^(((srv)|(cache)|(symsrv\\*symsrv\\.dll))\\*{\\c:[^*]*})" )
    free(v6);
  return *a1;
}

```

## disassembly

```asm
0x180013e40  mov     rax, rsp
0x180013e43  mov     [rax+8], rbx
0x180013e47  mov     [rax+20h], rbp
0x180013e4b  mov     [rax+18h], r8d
0x180013e4f  mov     [rax+10h], rdx
0x180013e53  push    rsi
0x180013e54  push    rdi
0x180013e55  push    r14; unsigned __int64
0x180013e57  sub     rsp, 20h
0x180013e5b  mov     rbx, rcx
0x180013e5e  mov     rcx, [rcx+8]; Block
0x180013e62  xor     ebp, ebp
0x180013e64  test    rcx, rcx
0x180013e67  jz      short loc_180013E73
0x180013e69  call    cs:__imp_free
0x180013e6f  mov     [rbx+8], rbp
0x180013e73  mov     [rbx+10h], rbp
0x180013e77  mov     [rbx+18h], rbp
0x180013e7b  mov     [rbx+28h], rbp
0x180013e7f  mov     [rbx], ebp
0x180013e81  mov     [rbx+30h], ebp
0x180013e84  mov     esi, 6Ah ; 'j'
0x180013e89  mov     ecx, esi; Size
0x180013e8b  call    cs:__imp_malloc
0x180013e91  mov     rdi, rax
0x180013e94  test    rax, rax
0x180013e97  jz      loc_180013FBF
0x180013e9d  mov     r9d, esi; void *
0x180013ea0  lea     r14, aSrvCacheSymsrv; "^(((srv)|(cache)|(symsrv\\*symsrv\\.dll"...
0x180013ea7  mov     r8, r14; unsigned __int64
0x180013eaa  mov     edx, esi; void *
0x180013eac  mov     rcx, rax; this
0x180013eaf  call    ?memcpy_s@Checked@ATL@@YAXPEAX_KPEBX1@Z; ATL::Checked::memcpy_s(void *,unsigned __int64,void const *,unsigned __int64)
0x180013eb4  lea     edx, [rsi-35h]; SizeInWords
0x180013eb7  mov     rcx, rdi; String
0x180013eba  call    cs:__imp__wcslwr_s
0x180013ec0  test    eax, eax
0x180013ec2  jz      short loc_180013EE8
0x180013ec4  cmp     eax, 0Ch
0x180013ec7  jz      loc_180013FED
0x180013ecd  cmp     eax, 16h
0x180013ed0  jz      loc_180013FD7
0x180013ed6  cmp     eax, 22h ; '"'
0x180013ed9  jz      loc_180013FD7
0x180013edf  cmp     eax, 50h ; 'P'
0x180013ee2  jnz     loc_180013FE2
0x180013ee8  mov     [rsp+38h+arg_8], rdi
0x180013eed  mov     edx, 10h
0x180013ef2  mov     rcx, rbx
0x180013ef5  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180013efa  movsxd  rsi, eax
0x180013efd  test    eax, eax
0x180013eff  js      loc_180013FBF
0x180013f05  mov     rcx, [rsp+38h+arg_8]
0x180013f0a  cmp     word ptr [rcx], 5Eh ; '^'
0x180013f0e  mov     rcx, rbx
0x180013f11  jnz     short loc_180013F35
0x180013f13  mov     edx, 1Ch
0x180013f18  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180013f1d  test    eax, eax
0x180013f1f  js      loc_180013FBF
0x180013f25  mov     rax, [rsp+38h+arg_8]
0x180013f2a  add     rax, 2
0x180013f2e  mov     [rsp+38h+arg_8], rax
0x180013f33  jmp     short loc_180013F48
0x180013f35  mov     edx, 1Dh
0x180013f3a  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180013f3f  test    eax, eax
0x180013f41  js      short loc_180013FBF
0x180013f43  mov     rax, [rsp+38h+arg_8]
0x180013f48  mov     byte ptr [rsp+38h+arg_10], 1
0x180013f4d  cmp     [rax], bp
0x180013f50  jz      short loc_180013F7F
0x180013f52  lea     r8, [rsp+38h+arg_10]
0x180013f57  lea     rdx, [rsp+38h+arg_8]
0x180013f5c  mov     rcx, rbx
0x180013f5f  call    ?ParseAltE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseAltE(ushort const * *,bool &)
0x180013f64  test    eax, eax
0x180013f66  js      short loc_180013F7F
0x180013f68  mov     byte ptr [rsp+38h+arg_10], 1
0x180013f6d  lea     r8, [rsp+38h+arg_10]
0x180013f72  lea     rdx, [rsp+38h+arg_8]
0x180013f77  mov     rcx, rbx
0x180013f7a  call    ?ParseRE@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHPEAPEBGAEA_N@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::ParseRE(ushort const * *,bool &)
0x180013f7f  cmp     [rbx], ebp
0x180013f81  jnz     short loc_180013FAD
0x180013f83  mov     rcx, rsi
0x180013f86  cmp     rsi, [rbx+10h]
0x180013f8a  jnb     short loc_180013FD7
0x180013f8c  add     rcx, rcx
0x180013f8f  mov     rax, [rbx+8]
0x180013f93  mov     qword ptr [rax+rcx*8+8], 2
0x180013f9c  mov     edx, 1Eh
0x180013fa1  mov     rcx, rbx
0x180013fa4  call    ?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)
0x180013fa9  test    eax, eax
0x180013fab  js      short loc_180013FBF
0x180013fad  cmp     rdi, r14
0x180013fb0  jz      short loc_180013FBB
0x180013fb2  mov     rcx, rdi; Block
0x180013fb5  call    cs:__imp_free
0x180013fbb  mov     eax, [rbx]
0x180013fbd  jmp     short loc_180013FC4
0x180013fbf  mov     eax, 1
0x180013fc4  mov     rbx, [rsp+38h+arg_0]
0x180013fc9  mov     rbp, [rsp+38h+arg_18]
0x180013fce  add     rsp, 20h
0x180013fd2  pop     r14
0x180013fd4  pop     rdi
0x180013fd5  pop     rsi
0x180013fd6  retn
0x180013fd7  mov     ecx, 80070057h; int
0x180013fdc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013fe2  mov     ecx, 80004005h; int
0x180013fe7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180013fed  mov     ecx, 8007000Eh; int
0x180013ff2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
