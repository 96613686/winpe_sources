# UnBCL::ArrayList<ulong>::RemoveAt(int)

- ea: `0x18002cb94`
- end: `0x18002ccdd`
- name: `?RemoveAt@?$ArrayList@K@UnBCL@@UEAAXH@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002cb80`

## callees

- `0x18000253c`
- `0x180002c8c`
- `0x1800082e4`
- `0x18002cb94`
- `0x180053010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18002cc2a`
- `msvcrt!memmove_s` at `0x18002cc2a`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002cc70`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18002cc70`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002cc8d`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18002cc8d`

## string_xrefs

- `0x18002cc83`: `index out of range to ArrayList#RemoveAt`
- `0x18002cca1`: `void __cdecl UnBCL::ArrayList<unsigned long>::RemoveAt(int)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall UnBCL::ArrayList<unsigned long>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rbx
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  UnBCL::ArgumentOutOfRangeException *v11; // rax
  UnBCL::Exception *v12; // rbx
  UnBCL::Exception *pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  UnBCL::ArgumentOutOfRangeException *v15; // [rsp+48h] [rbp+20h]

  v2 = a2;
  if ( a2 < 0
    || (v4 = (int (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 - 104) + 12LL) - 104LL), a2 >= (**v4)(v4)) )
  {
    v11 = (UnBCL::ArgumentOutOfRangeException *)UnBCL::Object::operator new(0x38u);
    v12 = v11;
    v15 = v11;
    if ( v11 )
    {
      UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(v11, L"index out of range to ArrayList#RemoveAt");
      *(_QWORD *)v12 = &UnBCL::ArgumentOutOfRangeException::`local vftable';
    }
    else
    {
      v12 = 0;
    }
    pExceptionObject = AddStackTraceToException<UnBCL::InvalidOperationException>(
                         v12,
                         "void __cdecl UnBCL::ArrayList<unsigned long>::RemoveAt(int)");
    throw (UnBCL::ArgumentOutOfRangeException **)&pExceptionObject;
  }
  ++*(_DWORD *)(a1 - 88);
  LODWORD(v5) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 112) + 32LL))(a1 - 112);
  v6 = (__int64 *)(a1 - 96);
  if ( (_DWORD)v5 )
  {
    v5 = *v6;
    if ( v2 >= *(_QWORD *)(*v6 + 8) )
      goto LABEL_15;
  }
  v7 = v2 + 1;
  if ( v2 + 1 < v2 )
    goto LABEL_15;
  if ( v2 == -1 )
    goto LABEL_15;
  v8 = (_QWORD *)*v6;
  v9 = v8[1];
  if ( v7 > v9 )
    goto LABEL_15;
  v10 = v9 - v7;
  if ( !v10 )
    goto LABEL_14;
  LODWORD(v5) = memmove_s((void *const)(*v8 + 4 * v2), 4 * v10, (const void *const)(*v8 + 4 * v7), 4 * v10);
  switch ( (_DWORD)v5 )
  {
    case 0:
      goto LABEL_14;
    case 0xC:
      ATL::AtlThrowImpl(-2147024882);
    case 0x16:
    case 0x22:
LABEL_15:
      ATL::AtlThrowImpl(-2147024809);
  }
  if ( (_DWORD)v5 != 80 )
    ATL::AtlThrowImpl(-2147467259);
LABEL_14:
  --v8[1];
  return v5;
}

```

## disassembly

```asm
0x18002cb94  mov     [rsp+arg_0], rbx
0x18002cb99  mov     [rsp+arg_8], rsi
0x18002cb9e  push    rdi
0x18002cb9f  sub     rsp, 20h
0x18002cba3  movsxd  rdi, edx
0x18002cba6  mov     rbx, rcx
0x18002cba9  test    edx, edx
0x18002cbab  js      loc_18002CC6B
0x18002cbb1  mov     rax, [rcx-68h]
0x18002cbb5  movsxd  rcx, dword ptr [rax+0Ch]
0x18002cbb9  add     rcx, 0FFFFFFFFFFFFFF98h
0x18002cbbd  add     rcx, rbx
0x18002cbc0  mov     rax, [rcx]
0x18002cbc3  mov     rax, [rax]
0x18002cbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbcb  cmp     edi, eax
0x18002cbcd  jge     loc_18002CC6B
0x18002cbd3  inc     dword ptr [rbx-58h]
0x18002cbd6  mov     rax, [rbx-70h]
0x18002cbda  lea     rcx, [rbx-70h]
0x18002cbde  mov     rax, [rax+20h]
0x18002cbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbe7  add     rbx, 0FFFFFFFFFFFFFFA0h
0x18002cbeb  test    eax, eax
0x18002cbed  jz      short loc_18002CBF8
0x18002cbef  mov     rax, [rbx]
0x18002cbf2  cmp     rdi, [rax+8]
0x18002cbf6  jnb     short loc_18002CC60
0x18002cbf8  lea     rcx, [rdi+1]
0x18002cbfc  cmp     rcx, rdi
0x18002cbff  jb      short loc_18002CC60
0x18002cc01  cmp     rcx, 1
0x18002cc05  jb      short loc_18002CC60
0x18002cc07  mov     rbx, [rbx]
0x18002cc0a  mov     rdx, [rbx+8]
0x18002cc0e  cmp     rcx, rdx
0x18002cc11  ja      short loc_18002CC60
0x18002cc13  sub     rdx, rcx
0x18002cc16  jz      short loc_18002CC4C
0x18002cc18  mov     rax, [rbx]
0x18002cc1b  shl     rdx, 2; DestinationSize
0x18002cc1f  lea     r8, [rax+rcx*4]; Source
0x18002cc23  lea     rcx, [rax+rdi*4]; Destination
0x18002cc27  mov     r9, rdx; SourceSize
0x18002cc2a  call    cs:__imp_memmove_s
0x18002cc30  test    eax, eax
0x18002cc32  jz      short loc_18002CC4C
0x18002cc34  cmp     eax, 0Ch
0x18002cc37  jz      loc_18002CCD2
0x18002cc3d  cmp     eax, 16h
0x18002cc40  jz      short loc_18002CC60
0x18002cc42  cmp     eax, 22h ; '"'
0x18002cc45  jz      short loc_18002CC60
0x18002cc47  cmp     eax, 50h ; 'P'
0x18002cc4a  jnz     short loc_18002CCC7
0x18002cc4c  dec     qword ptr [rbx+8]
0x18002cc50  mov     rbx, [rsp+28h+arg_0]
0x18002cc55  mov     rsi, [rsp+28h+arg_8]
0x18002cc5a  add     rsp, 20h
0x18002cc5e  pop     rdi
0x18002cc5f  retn
0x18002cc60  mov     ecx, 80070057h; int
0x18002cc65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002cc6b  mov     ecx, 38h ; '8'
0x18002cc70  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18002cc76  mov     rbx, rax
0x18002cc79  mov     [rsp+28h+arg_18], rax
0x18002cc7e  test    rax, rax
0x18002cc81  jz      short loc_18002CC9F
0x18002cc83  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18002cc8a  mov     rcx, rax
0x18002cc8d  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18002cc93  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18002cc9a  mov     [rbx], rax
0x18002cc9d  jmp     short loc_18002CCA1
0x18002cc9f  xor     ebx, ebx
0x18002cca1  lea     rdx, aVoidCdeclUnbcl_22; "void __cdecl UnBCL::ArrayList<unsigned "...
0x18002cca8  mov     rcx, rbx
0x18002ccab  call    ??$AddStackTraceToException@VInvalidOperationException@UnBCL@@@@YAPEAVInvalidOperationException@UnBCL@@PEAV01@PEBD@Z; AddStackTraceToException<UnBCL::InvalidOperationException>(UnBCL::InvalidOperationException *,char const *)
0x18002ccb0  mov     [rsp+28h+pExceptionObject], rax
0x18002ccb5  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18002ccbc  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002ccc1  call    _CxxThrowException_0
0x18002ccc7  mov     ecx, 80004005h; int
0x18002cccc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002ccd2  mov     ecx, 8007000Eh; int
0x18002ccd7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
