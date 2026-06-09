# UnBCL::ArrayList<CFileObject *>::RemoveAt(int)

- ea: `0x18002cd04`
- end: `0x18002ce82`
- name: `?RemoveAt@?$ArrayList@PEAVCFileObject@@@UnBCL@@UEAAXH@Z`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002ccf0`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x18002cd04`
- `0x180053010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002cdcf`
- `msvcrt!memmove_s` at `0x18002cdcf`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002ce15`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002ce15`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002ce32`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002ce32`

## string_xrefs

- `0x18002ce28`: `index out of range to ArrayList#RemoveAt`
- `0x18002ce46`: `void __cdecl UnBCL::ArrayList<class CFileObject *>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<CFileObject *>::RemoveAt(__int64 a1, int a2)
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
                         "void __cdecl UnBCL::ArrayList<class CFileObject *>::RemoveAt(int)");
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
        v8 = (__int64 (__fastcall ***)(_QWORD, __int64))(v7 + *(int *)(*(_QWORD *)v7 + 4LL));
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
0x18002cd04  mov     [rsp+arg_0], rbx
0x18002cd09  mov     [rsp+arg_8], rsi
0x18002cd0e  push    rdi
0x18002cd0f  sub     rsp, 20h
0x18002cd13  movsxd  rdi, edx
0x18002cd16  mov     rbx, rcx
0x18002cd19  test    edx, edx
0x18002cd1b  js      loc_18002CE10
0x18002cd21  mov     rax, [rcx-68h]
0x18002cd25  movsxd  rcx, dword ptr [rax+0Ch]
0x18002cd29  add     rcx, 0FFFFFFFFFFFFFF98h
0x18002cd2d  add     rcx, rbx
0x18002cd30  mov     rax, [rcx]
0x18002cd33  mov     rax, [rax]
0x18002cd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd3b  cmp     edi, eax
0x18002cd3d  jge     loc_18002CE10
0x18002cd43  inc     dword ptr [rbx-58h]
0x18002cd46  mov     rax, [rbx-70h]
0x18002cd4a  lea     rcx, [rbx-70h]
0x18002cd4e  mov     rax, [rax+20h]
0x18002cd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd57  test    eax, eax
0x18002cd59  jz      short loc_18002CD9C
0x18002cd5b  mov     rcx, [rbx-60h]
0x18002cd5f  cmp     rdi, [rcx+8]
0x18002cd63  jnb     loc_18002CE05
0x18002cd69  mov     rax, [rcx]
0x18002cd6c  cmp     qword ptr [rax+rdi*8], 0
0x18002cd71  jz      short loc_18002CD9C
0x18002cd73  lfence
0x18002cd76  mov     rax, [rcx]
0x18002cd79  mov     r8, [rax+rdi*8]
0x18002cd7d  test    r8, r8
0x18002cd80  jz      short loc_18002CD9C
0x18002cd82  mov     rax, [r8]
0x18002cd85  movsxd  rcx, dword ptr [rax+4]
0x18002cd89  add     rcx, r8
0x18002cd8c  mov     rax, [rcx]
0x18002cd8f  mov     edx, 1
0x18002cd94  mov     rax, [rax]
0x18002cd97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd9c  lea     rcx, [rdi+1]
0x18002cda0  cmp     rcx, rdi
0x18002cda3  jb      short loc_18002CE05
0x18002cda5  cmp     rcx, 1
0x18002cda9  jb      short loc_18002CE05
0x18002cdab  mov     rbx, [rbx-60h]
0x18002cdaf  mov     rdx, [rbx+8]
0x18002cdb3  cmp     rcx, rdx
0x18002cdb6  ja      short loc_18002CE05
0x18002cdb8  sub     rdx, rcx
0x18002cdbb  jz      short loc_18002CDF1
0x18002cdbd  mov     rax, [rbx]
0x18002cdc0  shl     rdx, 3; DestinationSize
0x18002cdc4  lea     r8, [rax+rcx*8]; Source
0x18002cdc8  lea     rcx, [rax+rdi*8]; Destination
0x18002cdcc  mov     r9, rdx; SourceSize
0x18002cdcf  call    cs:__imp_memmove_s
0x18002cdd5  test    eax, eax
0x18002cdd7  jz      short loc_18002CDF1
0x18002cdd9  cmp     eax, 0Ch
0x18002cddc  jz      loc_18002CE77
0x18002cde2  cmp     eax, 16h
0x18002cde5  jz      short loc_18002CE05
0x18002cde7  cmp     eax, 22h ; '"'
0x18002cdea  jz      short loc_18002CE05
0x18002cdec  cmp     eax, 50h ; 'P'
0x18002cdef  jnz     short loc_18002CE6C
0x18002cdf1  dec     qword ptr [rbx+8]
0x18002cdf5  mov     rbx, [rsp+28h+arg_0]
0x18002cdfa  mov     rsi, [rsp+28h+arg_8]
0x18002cdff  add     rsp, 20h
0x18002ce03  pop     rdi
0x18002ce04  retn
0x18002ce05  mov     ecx, 80070057h; int
0x18002ce0a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ce10  mov     ecx, 38h ; '8'
0x18002ce15  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002ce1b  mov     rbx, rax
0x18002ce1e  mov     [rsp+28h+arg_18], rax
0x18002ce23  test    rax, rax
0x18002ce26  jz      short loc_18002CE44
0x18002ce28  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18002ce2f  mov     rcx, rax
0x18002ce32  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18002ce38  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18002ce3f  mov     [rbx], rax
0x18002ce42  jmp     short loc_18002CE46
0x18002ce44  xor     ebx, ebx
0x18002ce46  lea     rdx, aVoidCdeclUnbcl_11; "void __cdecl UnBCL::ArrayList<class CFi"...
0x18002ce4d  mov     rcx, rbx
0x18002ce50  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ce55  mov     [rsp+28h+pExceptionObject], rax
0x18002ce5a  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18002ce61  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002ce66  call    _CxxThrowException_0
0x18002ce6c  mov     ecx, 80004005h; int
0x18002ce71  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ce77  mov     ecx, 8007000Eh; int
0x18002ce7c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
