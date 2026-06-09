# LSUtility::BuildTraceState(LSUtility::TraceStateContext const &)

- ea: `0x1800ed3b4`
- end: `0x1800ed5ae`
- name: `?BuildTraceState@LSUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUTraceStateContext@1@@Z`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18011d3c0`

## callees

- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800ec3f0`
- `0x1800ecb30`
- `0x1800ecccc`
- `0x1800ece10`
- `0x1800ed3b4`
- `0x1800f33f0`

## import_xrefs

- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed440`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed458`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed4e8`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed53f`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed440`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed458`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed4e8`
- `msvcp_win!?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z` at `0x1800ed53f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800ed564`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1800ed564`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800ed518`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x1800ed518`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed407`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed417`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed507`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed407`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed417`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x1800ed507`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall LSUtility::BuildTraceState(_OWORD *a1, unsigned int *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  _OWORD *result; // rax
  _OWORD *v11; // rax
  _BYTE *v12; // [rsp+20h] [rbp-138h] BYREF
  _OWORD *v13; // [rsp+28h] [rbp-130h]
  _OWORD v14[2]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v15[8]; // [rsp+50h] [rbp-108h] BYREF
  _BYTE v16[232]; // [rsp+58h] [rbp-100h] BYREF

  v13 = a1;
  memset_0(v15, 0, 0xE8u);
  try
  {
    std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>(v15);
    v4 = std::basic_ostream<unsigned short>::operator<<(v15, std::nouppercase);
    v5 = std::basic_ostream<unsigned short>::operator<<(v4, std::hex);
    *(_WORD *)(*(int *)(*(_QWORD *)v5 + 4LL) + v5 + 88) = 48;
    std::basic_ostream<unsigned short>::write(v15, L"lfsvc=", 6);
    std::basic_ostream<unsigned short>::write(v15, L"v:1", 3);
    v12 = v15;
    v14[0] = *(_OWORD *)&off_180169018;
    LSUtility::BuildTraceState_::_3_::_lambda_1_::operator()(&v12, v14, *a2);
    v14[0] = *(_OWORD *)&off_180168DF0;
    LSUtility::BuildTraceState_::_3_::_lambda_1_::operator()(&v12, v14, a2[1]);
    v14[0] = *(_OWORD *)&off_180168FB8;
    LSUtility::BuildTraceState_::_3_::_lambda_1_::operator()(&v12, v14, a2[2]);
    std::basic_ostream<unsigned short>::operator<<(v15, 59);
    std::basic_ostream<unsigned short>::write(v15, L"auth-usedcachedtoken", 20);
    v6 = std::basic_ostream<unsigned short>::operator<<(v15, 58);
    v7 = std::basic_ostream<unsigned short>::operator<<(v6, std::dec);
    std::basic_ostream<unsigned short>::operator<<(v7, *((_BYTE *)a2 + 12) != 0);
    std::basic_ostream<unsigned short>::operator<<(v15, 59);
    std::basic_ostream<unsigned short>::write(v15, L"auth-cachedtokenagesec", 22);
    v8 = std::basic_ostream<unsigned short>::operator<<(v15, 58);
    if ( *((_BYTE *)a2 + 12) )
      v9 = a2[4];
    else
      v9 = 0;
    std::basic_ostream<unsigned short>::operator<<(v8, v9);
    std::basic_stringbuf<unsigned short>::str(v16, a1);
    std::basic_ostringstream<unsigned short>::`vbase destructor'(v15);
    result = a1;
  }
  catch ( ... )
  {
    v11 = v13;
    *v13 = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 3) = 7;
    *(_WORD *)v11 = 0;
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x1800ed3b4  mov     [rsp+arg_10], rbx
0x1800ed3b9  push    rdi
0x1800ed3ba  sub     rsp, 150h
0x1800ed3c1  mov     rax, cs:__security_cookie
0x1800ed3c8  xor     rax, rsp
0x1800ed3cb  mov     [rsp+158h+var_18], rax
0x1800ed3d3  mov     rbx, rdx
0x1800ed3d6  mov     rdi, rcx
0x1800ed3d9  mov     [rsp+158h+var_130], rcx
0x1800ed3de  xor     edx, edx; Val
0x1800ed3e0  mov     r8d, 0E8h; Size
0x1800ed3e6  lea     rcx, [rsp+158h+var_108]; void *
0x1800ed3eb  call    memset_0
0x1800ed3f0  lea     rcx, [rsp+158h+var_108]
0x1800ed3f5  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800ed3fa  nop
0x1800ed3fb  lea     rdx, ?nouppercase@std@@YAAEAVios_base@1@AEAV21@@Z; std::nouppercase(std::ios_base &)
0x1800ed402  lea     rcx, [rsp+158h+var_108]
0x1800ed407  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800ed40d  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x1800ed414  mov     rcx, rax
0x1800ed417  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800ed41d  mov     rdx, rax
0x1800ed420  mov     rax, [rax]
0x1800ed423  movsxd  rcx, dword ptr [rax+4]
0x1800ed427  mov     word ptr [rcx+rdx+58h], 30h ; '0'
0x1800ed42e  mov     r8d, 6
0x1800ed434  mov     rdx, cs:off_180169038; "lfsvc="
0x1800ed43b  lea     rcx, [rsp+158h+var_108]
0x1800ed440  call    cs:__imp_?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z; std::basic_ostream<ushort>::write(ushort const *,__int64)
0x1800ed446  mov     r8d, 3
0x1800ed44c  mov     rdx, cs:off_180168DE0; "v:1"
0x1800ed453  lea     rcx, [rsp+158h+var_108]
0x1800ed458  call    cs:__imp_?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z; std::basic_ostream<ushort>::write(ushort const *,__int64)
0x1800ed45e  lea     rax, [rsp+158h+var_108]
0x1800ed463  mov     [rsp+158h+var_138], rax
0x1800ed468  movups  xmm0, xmmword ptr cs:off_180169018; "auth-fetchhr"
0x1800ed46f  movdqu  [rsp+158h+var_128], xmm0
0x1800ed475  mov     r8d, [rbx]
0x1800ed478  lea     rdx, [rsp+158h+var_128]
0x1800ed47d  lea     rcx, [rsp+158h+var_138]
0x1800ed482  call    _LSUtility__BuildTraceState____3____lambda_1___operator__
0x1800ed487  movups  xmm0, xmmword ptr cs:off_180168DF0; "auth-acquisitionhr"
0x1800ed48e  movdqu  [rsp+158h+var_128], xmm0
0x1800ed494  mov     r8d, [rbx+4]
0x1800ed498  lea     rdx, [rsp+158h+var_128]
0x1800ed49d  lea     rcx, [rsp+158h+var_138]
0x1800ed4a2  call    _LSUtility__BuildTraceState____3____lambda_1___operator__
0x1800ed4a7  movups  xmm0, xmmword ptr cs:off_180168FB8; "auth-extendedhr"
0x1800ed4ae  movdqu  [rsp+158h+var_128], xmm0
0x1800ed4b4  mov     r8d, [rbx+8]
0x1800ed4b8  lea     rdx, [rsp+158h+var_128]
0x1800ed4bd  lea     rcx, [rsp+158h+var_138]
0x1800ed4c2  call    _LSUtility__BuildTraceState____3____lambda_1___operator__
0x1800ed4c7  mov     edx, 3Bh ; ';'
0x1800ed4cc  lea     rcx, [rsp+158h+var_108]
0x1800ed4d1  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800ed4d6  mov     r8d, 14h
0x1800ed4dc  mov     rdx, cs:off_180168E00; "auth-usedcachedtoken"
0x1800ed4e3  lea     rcx, [rsp+158h+var_108]
0x1800ed4e8  call    cs:__imp_?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z; std::basic_ostream<ushort>::write(ushort const *,__int64)
0x1800ed4ee  mov     edx, 3Ah ; ':'
0x1800ed4f3  lea     rcx, [rsp+158h+var_108]
0x1800ed4f8  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800ed4fd  lea     rdx, ?dec@std@@YAAEAVios_base@1@AEAV21@@Z; std::dec(std::ios_base &)
0x1800ed504  mov     rcx, rax
0x1800ed507  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x1800ed50d  xor     edx, edx
0x1800ed50f  cmp     [rbx+0Ch], dl
0x1800ed512  setnz   dl
0x1800ed515  mov     rcx, rax
0x1800ed518  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x1800ed51e  mov     edx, 3Bh ; ';'
0x1800ed523  lea     rcx, [rsp+158h+var_108]
0x1800ed528  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800ed52d  mov     r8d, 16h
0x1800ed533  mov     rdx, cs:off_180168DC0; "auth-cachedtokenagesec"
0x1800ed53a  lea     rcx, [rsp+158h+var_108]
0x1800ed53f  call    cs:__imp_?write@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEBG_J@Z; std::basic_ostream<ushort>::write(ushort const *,__int64)
0x1800ed545  mov     edx, 3Ah ; ':'
0x1800ed54a  lea     rcx, [rsp+158h+var_108]
0x1800ed54f  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800ed554  cmp     byte ptr [rbx+0Ch], 0
0x1800ed558  jz      short loc_1800ED55F
0x1800ed55a  mov     edx, [rbx+10h]
0x1800ed55d  jmp     short loc_1800ED561
0x1800ed55f  xor     edx, edx
0x1800ed561  mov     rcx, rax
0x1800ed564  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z; std::basic_ostream<ushort>::operator<<(uint)
0x1800ed56a  mov     rdx, rdi
0x1800ed56d  lea     rcx, [rsp+158h+var_100]
0x1800ed572  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x1800ed577  nop
0x1800ed578  lea     rcx, [rsp+158h+var_108]
0x1800ed57d  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x1800ed582  mov     rax, rdi
0x1800ed585  jmp     short loc_1800ED58C
0x1800ed587  mov     rax, [rsp+158h+var_130]
0x1800ed58c  mov     rcx, [rsp+158h+var_18]
0x1800ed594  xor     rcx, rsp; StackCookie
0x1800ed597  call    __security_check_cookie
0x1800ed59c  mov     rbx, [rsp+158h+arg_10]
0x1800ed5a4  add     rsp, 150h
0x1800ed5ab  pop     rdi
0x1800ed5ac  retn
```
