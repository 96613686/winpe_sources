# UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt(int)

- ea: `0x180012104`
- end: `0x1800122e6`
- name: `?RemoveAt@?$ArrayList@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@UnBCL@@UEAAXH@Z`
- size: `482`
- prototype: `int __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x1800120f0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180005ef8`
- `0x18000eae0`
- `0x1800107cc`
- `0x180012104`
- `0x180036010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180012216`
- `msvcrt!memmove_s` at `0x180012216`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180012188`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1800121b4`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x180012188`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z` at `0x1800121b4`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180012280`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x180012280`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180012263`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180012263`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800121bd`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800121bd`

## string_xrefs

- `0x180012276`: `index out of range to ArrayList#RemoveAt`
- `0x180012294`: `void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)`

## pseudocode

```c
int __fastcall UnBCL::ArrayList<UnBCL::SmartPtr<UnBCL::String>>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rbx
  int (__fastcall ***v4)(_QWORD); // rcx
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  _QWORD *v11; // rdi
  unsigned __int64 v12; // rbp
  __int64 v13; // rsi
  int result; // eax
  unsigned __int64 v15; // rbp
  UnBCL::ArgumentOutOfRangeException *v16; // rax
  UnBCL::Exception *v17; // rbx
  _BYTE v18[40]; // [rsp+20h] [rbp-28h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+60h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v20; // [rsp+68h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v16 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v17 = v16;
    v20 = v16;
    if ( v16 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v16, L"index out of range to ArrayList#RemoveAt");
      *(_QWORD *)v17 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v17 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v17,
                         "void __cdecl UnBCL::ArrayList<class UnBCL::SmartPtr<class UnBCL::String> >::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112) )
  {
    pExceptionObject = (UnBCL::Exception *)v18;
    v5 = *(_QWORD **)(a1 - 96);
    if ( v2 >= v5[1] )
      ATL::AtlThrowImpl(-2147024809);
    v6 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v18, 16 * v2 + *v5);
    if ( !(unsigned int)UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(v6) )
    {
      v7 = *(_QWORD **)(a1 - 96);
      if ( v2 >= v7[1] )
        ATL::AtlThrowImpl(-2147024809);
      v8 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v18, 16 * v2 + *v7);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v8);
    }
  }
  v9 = v2;
  v10 = v2 + 1;
  if ( v10 < v9 )
    goto LABEL_18;
  if ( !v10 )
    goto LABEL_18;
  v11 = *(_QWORD **)(a1 - 96);
  v12 = v11[1];
  if ( v10 > v12 )
    goto LABEL_18;
  v13 = 16 * v9;
  result = ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(
             v13 + *v11,
             1u);
  v15 = v12 - v10;
  if ( !v15 )
    goto LABEL_17;
  result = memmove_s((void *const)(v13 + *v11), 16 * v15, (const void *const)(*v11 + 16 * v10), 16 * v15);
  switch ( result )
  {
    case 0:
      goto LABEL_17;
    case 12:
      ATL::AtlThrowImpl(-2147024882);
    case 22:
    case 34:
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( result != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_17:
  --v11[1];
  return result;
}

```

## disassembly

```asm
0x180012104  mov     [rsp+arg_0], rbx
0x180012109  mov     [rsp+arg_8], rbp
0x18001210e  push    rsi
0x18001210f  push    rdi
0x180012110  push    r14
0x180012112  sub     rsp, 30h
0x180012116  movsxd  rbx, edx
0x180012119  mov     rdi, rcx
0x18001211c  test    edx, edx
0x18001211e  js      loc_18001225E
0x180012124  mov     rax, [rcx-68h]
0x180012128  movsxd  rcx, dword ptr [rax+0Ch]
0x18001212c  add     rcx, 0FFFFFFFFFFFFFF98h
0x180012130  add     rcx, rdi
0x180012133  mov     rax, [rcx]
0x180012136  mov     rax, [rax]
0x180012139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001213e  cmp     ebx, eax
0x180012140  jge     loc_18001225E
0x180012146  inc     dword ptr [rdi-58h]
0x180012149  mov     rax, [rdi-70h]
0x18001214d  lea     rcx, [rdi-70h]
0x180012151  mov     rax, [rax+20h]
0x180012155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215a  test    eax, eax
0x18001215c  jz      short loc_1800121C3
0x18001215e  lea     rax, [rsp+48h+var_28]
0x180012163  mov     [rsp+48h+pExceptionObject], rax
0x180012168  mov     rax, [rdi-60h]
0x18001216c  cmp     rbx, [rax+8]
0x180012170  jnb     loc_1800122BA
0x180012176  mov     r14, rbx
0x180012179  shl     r14, 4
0x18001217d  mov     rdx, [rax]
0x180012180  add     rdx, r14
0x180012183  lea     rcx, [rsp+48h+var_28]
0x180012188  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x18001218e  nop
0x18001218f  mov     rcx, rax
0x180012192  call    ?IsNull@?$SmartPtrNull@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@MP@UnBCL@@SAHV?$SmartPtr@VString@UnBCL@@@3@@Z; UnBCL::MP::SmartPtrNull<UnBCL::SmartPtr<UnBCL::String>>::IsNull(UnBCL::SmartPtr<UnBCL::String>)
0x180012197  test    eax, eax
0x180012199  jnz     short loc_1800121C3
0x18001219b  mov     rax, [rdi-60h]
0x18001219f  cmp     rbx, [rax+8]
0x1800121a3  jnb     loc_1800122C5
0x1800121a9  mov     rdx, [rax]
0x1800121ac  add     rdx, r14
0x1800121af  lea     rcx, [rsp+48h+var_28]
0x1800121b4  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::SmartPtr<UnBCL::String> const &)
0x1800121ba  mov     rcx, rax
0x1800121bd  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800121c3  mov     rsi, rbx
0x1800121c6  inc     rbx
0x1800121c9  cmp     rbx, rsi
0x1800121cc  jb      loc_180012253
0x1800121d2  cmp     rbx, 1
0x1800121d6  jb      short loc_180012253
0x1800121d8  mov     rdi, [rdi-60h]
0x1800121dc  mov     rbp, [rdi+8]
0x1800121e0  cmp     rbx, rbp
0x1800121e3  ja      short loc_180012253
0x1800121e5  shl     rsi, 4
0x1800121e9  mov     rcx, [rdi]
0x1800121ec  add     rcx, rsi
0x1800121ef  mov     edx, 1
0x1800121f4  call    ?CallDestructors@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@CAXPEAV?$SmartPtr@VString@UnBCL@@@UnBCL@@_K@Z; ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::CallDestructors(UnBCL::SmartPtr<UnBCL::String> *,unsigned __int64)
0x1800121f9  sub     rbp, rbx
0x1800121fc  jz      short loc_18001223C
0x1800121fe  mov     rax, [rdi]
0x180012201  shl     rbp, 4
0x180012205  add     rbx, rbx
0x180012208  lea     r8, [rax+rbx*8]; Source
0x18001220c  lea     rcx, [rsi+rax]; Destination
0x180012210  mov     r9, rbp; SourceSize
0x180012213  mov     rdx, rbp; DestinationSize
0x180012216  call    cs:__imp_memmove_s
0x18001221c  test    eax, eax
0x18001221e  jz      short loc_18001223C
0x180012220  cmp     eax, 0Ch
0x180012223  jz      loc_1800122DB
0x180012229  cmp     eax, 16h
0x18001222c  jz      short loc_180012253
0x18001222e  cmp     eax, 22h ; '"'
0x180012231  jz      short loc_180012253
0x180012233  cmp     eax, 50h ; 'P'
0x180012236  jnz     loc_1800122D0
0x18001223c  dec     qword ptr [rdi+8]
0x180012240  mov     rbx, [rsp+48h+arg_0]
0x180012245  mov     rbp, [rsp+48h+arg_8]
0x18001224a  add     rsp, 30h
0x18001224e  pop     r14
0x180012250  pop     rdi
0x180012251  pop     rsi
0x180012252  retn
0x180012253  mov     ecx, 80070057h; int
0x180012258  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001225e  mov     ecx, 38h ; '8'
0x180012263  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180012269  mov     rbx, rax
0x18001226c  mov     [rsp+48h+arg_18], rax
0x180012271  test    rax, rax
0x180012274  jz      short loc_180012292
0x180012276  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18001227d  mov     rcx, rax
0x180012280  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x180012286  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18001228d  mov     [rbx], rax
0x180012290  jmp     short loc_180012294
0x180012292  xor     ebx, ebx
0x180012294  lea     rdx, aVoidCdeclUnbcl_1; "void __cdecl UnBCL::ArrayList<class UnB"...
0x18001229b  mov     rcx, rbx
0x18001229e  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x1800122a3  mov     [rsp+48h+pExceptionObject], rax
0x1800122a8  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x1800122af  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800122b4  call    _CxxThrowException_0
0x1800122ba  mov     ecx, 80070057h; int
0x1800122bf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800122c5  mov     ecx, 80070057h; int
0x1800122ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800122d0  mov     ecx, 80004005h; int
0x1800122d5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800122db  mov     ecx, 8007000Eh; int
0x1800122e0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
