# UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::RemoveAt(int)

- ea: `0x1800151a4`
- end: `0x180015327`
- name: `?RemoveAt@?$ArrayList@PEAV?$DictionaryEntry@PEAVString@UnBCL@@_K@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180015190`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x1800151a4`
- `0x180053010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180015274`
- `msvcrt!memmove_s` at `0x180015274`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800152ba`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800152ba`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800152d7`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x1800152d7`

## string_xrefs

- `0x1800152cd`: `index out of range to ArrayList#RemoveAt`
- `0x1800152eb`: `void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int64> *>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<UnBCL::DictionaryEntry<UnBCL::String *,unsigned __int64> *>::RemoveAt(
        __int64 a1,
        int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // r8
  __int64 (__fastcall ***v8)(_QWORD, __int64); // rcx
  unsigned __int64 v9; // rcx
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  UnBCL::ArgumentOutOfRangeException *v13; // rax
  UnBCL::Exception *v14; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v17; // [rsp+48h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v13 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v14 = v13;
    v17 = v13;
    if ( v13 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v13, L"index out of range to ArrayList#RemoveAt");
      *(_QWORD *)v14 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v14 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v14,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::DictionaryEntry<class UnBCL::String *,unsigned __int"
                         "64> *>::RemoveAt(int)");
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
      {
        v8 = (__int64 (__fastcall ***)(_QWORD, __int64))(v7 + 8 + *(int *)(*(_QWORD *)(v7 + 8) + 4LL));
        LODWORD(v5) = (**v8)(v8, 1);
      }
    }
  }
  v9 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_18;
  if ( v2 == -1 )
    goto LABEL_18;
  v10 = *(_QWORD **)(a1 - 96);
  v11 = v10[1];
  if ( v9 > v11 )
    goto LABEL_18;
  v12 = v11 - v9;
  if ( !v12 )
    goto LABEL_17;
  LODWORD(v5) = memmove_s((void *const)(*v10 + 8 * v2), 8 * v12, (const void *const)(*v10 + 8 * v9), 8 * v12);
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
  --v10[1];
  return v5;
}

```

## disassembly

```asm
0x1800151a4  mov     [rsp+arg_0], rbx
0x1800151a9  mov     [rsp+arg_8], rsi
0x1800151ae  push    rdi
0x1800151af  sub     rsp, 20h
0x1800151b3  movsxd  rdi, edx
0x1800151b6  mov     rbx, rcx
0x1800151b9  test    edx, edx
0x1800151bb  js      loc_1800152B5
0x1800151c1  mov     rax, [rcx-68h]
0x1800151c5  movsxd  rcx, dword ptr [rax+0Ch]
0x1800151c9  add     rcx, 0FFFFFFFFFFFFFF98h
0x1800151cd  add     rcx, rbx
0x1800151d0  mov     rax, [rcx]
0x1800151d3  mov     rax, [rax]
0x1800151d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151db  cmp     edi, eax
0x1800151dd  jge     loc_1800152B5
0x1800151e3  inc     dword ptr [rbx-58h]
0x1800151e6  mov     rax, [rbx-70h]
0x1800151ea  lea     rcx, [rbx-70h]
0x1800151ee  mov     rax, [rax+20h]
0x1800151f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151f7  test    eax, eax
0x1800151f9  jz      short loc_180015241
0x1800151fb  mov     rcx, [rbx-60h]
0x1800151ff  cmp     rdi, [rcx+8]
0x180015203  jnb     loc_1800152AA
0x180015209  mov     rax, [rcx]
0x18001520c  cmp     qword ptr [rax+rdi*8], 0
0x180015211  jz      short loc_180015241
0x180015213  lfence
0x180015216  mov     rax, [rcx]
0x180015219  mov     r8, [rax+rdi*8]
0x18001521d  test    r8, r8
0x180015220  jz      short loc_180015241
0x180015222  mov     rax, [r8+8]
0x180015226  movsxd  rcx, dword ptr [rax+4]
0x18001522a  add     r8, 8
0x18001522e  add     rcx, r8
0x180015231  mov     rax, [rcx]
0x180015234  mov     edx, 1
0x180015239  mov     rax, [rax]
0x18001523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015241  lea     rcx, [rdi+1]
0x180015245  cmp     rcx, rdi
0x180015248  jb      short loc_1800152AA
0x18001524a  cmp     rcx, 1
0x18001524e  jb      short loc_1800152AA
0x180015250  mov     rbx, [rbx-60h]
0x180015254  mov     rdx, [rbx+8]
0x180015258  cmp     rcx, rdx
0x18001525b  ja      short loc_1800152AA
0x18001525d  sub     rdx, rcx
0x180015260  jz      short loc_180015296
0x180015262  mov     rax, [rbx]
0x180015265  shl     rdx, 3; DestinationSize
0x180015269  lea     r8, [rax+rcx*8]; Source
0x18001526d  lea     rcx, [rax+rdi*8]; Destination
0x180015271  mov     r9, rdx; SourceSize
0x180015274  call    cs:__imp_memmove_s
0x18001527a  test    eax, eax
0x18001527c  jz      short loc_180015296
0x18001527e  cmp     eax, 0Ch
0x180015281  jz      loc_18001531C
0x180015287  cmp     eax, 16h
0x18001528a  jz      short loc_1800152AA
0x18001528c  cmp     eax, 22h ; '"'
0x18001528f  jz      short loc_1800152AA
0x180015291  cmp     eax, 50h ; 'P'
0x180015294  jnz     short loc_180015311
0x180015296  dec     qword ptr [rbx+8]
0x18001529a  mov     rbx, [rsp+28h+arg_0]
0x18001529f  mov     rsi, [rsp+28h+arg_8]
0x1800152a4  add     rsp, 20h
0x1800152a8  pop     rdi
0x1800152a9  retn
0x1800152aa  mov     ecx, 80070057h; int
0x1800152af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800152b5  mov     ecx, 38h ; '8'
0x1800152ba  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800152c0  mov     rbx, rax
0x1800152c3  mov     [rsp+28h+arg_18], rax
0x1800152c8  test    rax, rax
0x1800152cb  jz      short loc_1800152E9
0x1800152cd  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x1800152d4  mov     rcx, rax
0x1800152d7  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x1800152dd  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x1800152e4  mov     [rbx], rax
0x1800152e7  jmp     short loc_1800152EB
0x1800152e9  xor     ebx, ebx
0x1800152eb  lea     rdx, aVoidCdeclUnbcl_12; "void __cdecl UnBCL::ArrayList<class UnB"...
0x1800152f2  mov     rcx, rbx
0x1800152f5  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x1800152fa  mov     [rsp+28h+pExceptionObject], rax
0x1800152ff  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x180015306  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18001530b  call    _CxxThrowException_0
0x180015311  mov     ecx, 80004005h; int
0x180015316  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001531c  mov     ecx, 8007000Eh; int
0x180015321  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
