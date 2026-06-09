# ForEachFormerCandidate(IMtfSuggestionInputQuery *,std::function<void (_MTF_FORMER_RESULT const &,IMtfSuggestionListElement *)>)

- ea: `0x18000904c`
- end: `0x180009193`
- name: `?ForEachFormerCandidate@@YAXPEAUIMtfSuggestionInputQuery@@V?$function@$$A6AXAEBU_MTF_FORMER_RESULT@@PEAUIMtfSuggestionListElement@@@Z@std@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000919c`
- `0x180009250`

## callees

- `0x180001fd0`
- `0x18000904c`
- `0x18000ac8c`
- `0x18000c530`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ForEachFormerCandidate(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  unsigned int i; // ebx
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  int v9[2]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v10[3]; // [rsp+28h] [rbp-58h] BYREF
  _QWORD *v11; // [rsp+40h] [rbp-40h]
  __int128 v12; // [rsp+48h] [rbp-38h] BYREF
  __int128 v13; // [rsp+58h] [rbp-28h]
  _QWORD *v14; // [rsp+68h] [rbp-18h]
  __int64 v15; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v15 = a2;
  v9[1] = (int)v10;
  v10[0] = off_18000FCC0;
  v10[1] = a2;
  v11 = v10;
  v14 = v10;
  v9[0] = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 96LL))(a1, v9);
  if ( (int)result < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x65,
      (int)"mincore\\textinput\\dev\\mtf\\datasources\\bingfilterds\\lib\\bingfilterds.cpp",
      (const char *)(unsigned int)result,
      v9[0]);
  for ( i = 0; i < v9[0]; ++i )
  {
    v12 = 0;
    v13 = 0;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)a1 + 104LL))(a1, i, &v12);
    if ( (int)result >= 0 && *((_QWORD *)&v13 + 1) )
    {
      if ( !v11 )
        std::_Xbad_function_call();
      result = (*(__int64 (__fastcall **)(_QWORD *, __int128 *))(*v11 + 16LL))(v11, &v12);
    }
  }
  if ( v11 )
  {
    v7 = v10;
    LOBYTE(v7) = v11 != v10;
    result = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v11 + 32LL))(v11, v7);
  }
  v8 = *(_QWORD *)(a2 + 24);
  if ( v8 )
  {
    LOBYTE(v5) = v8 != a2;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v5);
    *(_QWORD *)(a2 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000904c  mov     [rsp-18h+arg_10], rbx
0x180009051  push    rbp
0x180009052  push    rsi
0x180009053  push    rdi
0x180009054  mov     rbp, rsp
0x180009057  sub     rsp, 80h
0x18000905e  mov     rax, cs:__security_cookie
0x180009065  xor     rax, rsp
0x180009068  mov     [rbp+var_8], rax
0x18000906c  mov     rdi, rdx
0x18000906f  mov     rsi, rcx
0x180009072  mov     [rbp+var_10], rdx
0x180009076  lea     rax, [rbp+var_58]
0x18000907a  mov     [rbp+var_60], rax
0x18000907e  lea     rax, off_18000FCC0
0x180009085  mov     [rbp+var_58], rax
0x180009089  mov     [rbp+var_50], rdx
0x18000908d  lea     rax, [rbp+var_58]
0x180009091  mov     [rbp+var_40], rax
0x180009095  lea     rax, [rbp+var_58]
0x180009099  mov     [rbp+var_18], rax
0x18000909d  mov     dword ptr [rbp+var_60], 0
0x1800090a4  mov     rax, [rcx]
0x1800090a7  lea     rdx, [rbp+var_60]
0x1800090ab  mov     rax, [rax+60h]
0x1800090af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b4  mov     rcx, [rbp+18h]; this
0x1800090b8  test    eax, eax
0x1800090ba  js      loc_180009178
0x1800090c0  xor     ebx, ebx
0x1800090c2  cmp     dword ptr [rbp+var_60], ebx
0x1800090c5  jbe     short loc_180009116
0x1800090c7  xorps   xmm0, xmm0
0x1800090ca  movups  [rbp+var_38], xmm0
0x1800090ce  movups  [rbp+var_28], xmm0
0x1800090d2  mov     rax, [rsi]
0x1800090d5  lea     r8, [rbp+var_38]
0x1800090d9  mov     edx, ebx
0x1800090db  mov     rcx, rsi
0x1800090de  mov     rax, [rax+68h]
0x1800090e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e7  test    eax, eax
0x1800090e9  js      short loc_18000910F
0x1800090eb  cmp     qword ptr [rbp+var_28+8], 0
0x1800090f0  jz      short loc_18000910F
0x1800090f2  mov     rcx, [rbp+var_40]
0x1800090f6  test    rcx, rcx
0x1800090f9  jz      loc_18000918D
0x1800090ff  mov     rax, [rcx]
0x180009102  lea     rdx, [rbp+var_38]
0x180009106  mov     rax, [rax+10h]
0x18000910a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000910f  inc     ebx
0x180009111  cmp     ebx, dword ptr [rbp+var_60]
0x180009114  jb      short loc_1800090C7
0x180009116  mov     rcx, [rbp+var_40]
0x18000911a  test    rcx, rcx
0x18000911d  jz      short loc_180009136
0x18000911f  mov     rax, [rcx]
0x180009122  lea     rdx, [rbp+var_58]
0x180009126  cmp     rcx, rdx
0x180009129  setnz   dl
0x18000912c  mov     rax, [rax+20h]
0x180009130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009135  nop
0x180009136  mov     rcx, [rdi+18h]
0x18000913a  test    rcx, rcx
0x18000913d  jz      short loc_180009159
0x18000913f  mov     rax, [rcx]
0x180009142  cmp     rcx, rdi
0x180009145  setnz   dl
0x180009148  mov     rax, [rax+20h]
0x18000914c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009151  mov     qword ptr [rdi+18h], 0
0x180009159  mov     rcx, [rbp+var_8]
0x18000915d  xor     rcx, rsp; StackCookie
0x180009160  call    __security_check_cookie
0x180009165  mov     rbx, [rsp+80h+arg_10]
0x18000916d  add     rsp, 80h
0x180009174  pop     rdi
0x180009175  pop     rsi
0x180009176  pop     rbp
0x180009177  retn
0x180009178  mov     r9d, eax; char *
0x18000917b  lea     r8, aMincoreTextinp; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180009182  mov     edx, 65h ; 'e'; void *
0x180009187  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000918d  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
