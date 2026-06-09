# UnBCL::ArrayList<CPITRSnapshot *>::RemoveAt(int)

- ea: `0x180015344`
- end: `0x1800154bc`
- name: `?RemoveAt@?$ArrayList@PEAVCPITRSnapshot@@@UnBCL@@UEAAXH@Z`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015330`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x180015344`
- `0x180053010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180015409`
- `msvcrt!memmove_s` at `0x180015409`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001544f`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18001544f`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18001546c`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18001546c`

## string_xrefs

- `0x180015480`: `void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::RemoveAt(int)`
- `0x180015462`: `index out of range to ArrayList#RemoveAt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<CPITRSnapshot *>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rcx
  unsigned __int64 v8; // rcx
  _QWORD *v9; // rbx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  UnBCL::ArgumentOutOfRangeException *v12; // rax
  UnBCL::Exception *v13; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v16; // [rsp+48h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v12 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v13 = v12;
    v16 = v12;
    if ( v12 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v12, L"index out of range to ArrayList#RemoveAt");
      *(_QWORD *)v13 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v13 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v13,
                         "void __cdecl UnBCL::ArrayList<class CPITRSnapshot *>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  LODWORD(v5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112);
  if ( (_DWORD)v5 )
  {
    v6 = *(__int64 **)(a1 - 96);
    if ( v2 >= v6[1] )
      goto LABEL_18;
    v5 = *v6;
    if ( *(_QWORD *)(*v6 + 8 * v2) )
    {
      _mm_lfence();
      v5 = *v6;
      v7 = *(_QWORD *)(*v6 + 8 * v2);
      if ( v7 )
        LODWORD(v5) = (**(__int64 (__fastcall ***)(__int64, __int64))(v7 + 8))(v7 + 8, 1);
    }
  }
  v8 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_18;
  if ( v2 == -1 )
    goto LABEL_18;
  v9 = *(_QWORD **)(a1 - 96);
  v10 = v9[1];
  if ( v8 > v10 )
    goto LABEL_18;
  v11 = v10 - v8;
  if ( !v11 )
    goto LABEL_17;
  LODWORD(v5) = memmove_s((void *const)(*v9 + 8 * v2), 8 * v11, (const void *const)(*v9 + 8 * v8), 8 * v11);
  switch ( (_DWORD)v5 )
  {
    case 0:
      goto LABEL_17;
    case 0xC:
      ATL::AtlThrowImpl(-2147024882);
    case 0x16:
    case 0x22:
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( (_DWORD)v5 != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_17:
  --v9[1];
  return v5;
}

```

## disassembly

```asm
0x180015344  mov     [rsp+arg_0], rbx
0x180015349  mov     [rsp+arg_8], rsi
0x18001534e  push    rdi
0x18001534f  sub     rsp, 20h
0x180015353  movsxd  rdi, edx
0x180015356  mov     rbx, rcx
0x180015359  test    edx, edx
0x18001535b  js      loc_18001544A
0x180015361  mov     rax, [rcx-68h]
0x180015365  movsxd  rcx, dword ptr [rax+0Ch]
0x180015369  add     rcx, 0FFFFFFFFFFFFFF98h
0x18001536d  add     rcx, rbx
0x180015370  mov     rax, [rcx]
0x180015373  mov     rax, [rax]
0x180015376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001537b  cmp     edi, eax
0x18001537d  jge     loc_18001544A
0x180015383  inc     dword ptr [rbx-58h]
0x180015386  mov     rax, [rbx-70h]
0x18001538a  lea     rcx, [rbx-70h]
0x18001538e  mov     rax, [rax+20h]
0x180015392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015397  test    eax, eax
0x180015399  jz      short loc_1800153D6
0x18001539b  mov     rcx, [rbx-60h]
0x18001539f  cmp     rdi, [rcx+8]
0x1800153a3  jnb     loc_18001543F
0x1800153a9  mov     rax, [rcx]
0x1800153ac  cmp     qword ptr [rax+rdi*8], 0
0x1800153b1  jz      short loc_1800153D6
0x1800153b3  lfence
0x1800153b6  mov     rax, [rcx]
0x1800153b9  mov     rcx, [rax+rdi*8]
0x1800153bd  test    rcx, rcx
0x1800153c0  jz      short loc_1800153D6
0x1800153c2  add     rcx, 8
0x1800153c6  mov     rax, [rcx]
0x1800153c9  mov     edx, 1
0x1800153ce  mov     rax, [rax]
0x1800153d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d6  lea     rcx, [rdi+1]
0x1800153da  cmp     rcx, rdi
0x1800153dd  jb      short loc_18001543F
0x1800153df  cmp     rcx, 1
0x1800153e3  jb      short loc_18001543F
0x1800153e5  mov     rbx, [rbx-60h]
0x1800153e9  mov     rdx, [rbx+8]
0x1800153ed  cmp     rcx, rdx
0x1800153f0  ja      short loc_18001543F
0x1800153f2  sub     rdx, rcx
0x1800153f5  jz      short loc_18001542B
0x1800153f7  mov     rax, [rbx]
0x1800153fa  shl     rdx, 3; DestinationSize
0x1800153fe  lea     r8, [rax+rcx*8]; Source
0x180015402  lea     rcx, [rax+rdi*8]; Destination
0x180015406  mov     r9, rdx; SourceSize
0x180015409  call    cs:__imp_memmove_s
0x18001540f  test    eax, eax
0x180015411  jz      short loc_18001542B
0x180015413  cmp     eax, 0Ch
0x180015416  jz      loc_1800154B1
0x18001541c  cmp     eax, 16h
0x18001541f  jz      short loc_18001543F
0x180015421  cmp     eax, 22h ; '"'
0x180015424  jz      short loc_18001543F
0x180015426  cmp     eax, 50h ; 'P'
0x180015429  jnz     short loc_1800154A6
0x18001542b  dec     qword ptr [rbx+8]
0x18001542f  mov     rbx, [rsp+28h+arg_0]
0x180015434  mov     rsi, [rsp+28h+arg_8]
0x180015439  add     rsp, 20h
0x18001543d  pop     rdi
0x18001543e  retn
0x18001543f  mov     ecx, 80070057h; int
0x180015444  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001544a  mov     ecx, 38h ; '8'
0x18001544f  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180015455  mov     rbx, rax
0x180015458  mov     [rsp+28h+arg_18], rax
0x18001545d  test    rax, rax
0x180015460  jz      short loc_18001547E
0x180015462  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x180015469  mov     rcx, rax
0x18001546c  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180015472  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x180015479  mov     [rbx], rax
0x18001547c  jmp     short loc_180015480
0x18001547e  xor     ebx, ebx
0x180015480  lea     rdx, aVoidCdeclUnbcl_5; "void __cdecl UnBCL::ArrayList<class CPI"...
0x180015487  mov     rcx, rbx
0x18001548a  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18001548f  mov     [rsp+28h+pExceptionObject], rax
0x180015494  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18001549b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800154a0  call    _CxxThrowException_0
0x1800154a6  mov     ecx, 80004005h; int
0x1800154ab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800154b1  mov     ecx, 8007000Eh; int
0x1800154b6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
