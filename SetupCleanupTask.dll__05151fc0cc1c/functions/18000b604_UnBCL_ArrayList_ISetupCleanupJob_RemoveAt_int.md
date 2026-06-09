# UnBCL::ArrayList<ISetupCleanupJob *>::RemoveAt(int)

- ea: `0x18000b604`
- end: `0x18000b778`
- name: `?RemoveAt@?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@UEAAXH@Z`
- size: `372`
- prototype: `int __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000b5f0`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x180005ef8`
- `0x18000b604`
- `0x180036010`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000b6c5`
- `msvcrt!memmove_s` at `0x18000b6c5`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000b728`
- `unbcl!??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z` at `0x18000b728`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b70b`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000b70b`

## string_xrefs

- `0x18000b73c`: `void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::RemoveAt(int)`
- `0x18000b71e`: `index out of range to ArrayList#RemoveAt`

## pseudocode

```c
int __fastcall UnBCL::ArrayList<ISetupCleanupJob *>::RemoveAt(__int64 a1, int a2)
{
  unsigned __int64 v2; // rdi
  int (__fastcall ***v4)(_QWORD); // rcx
  __int64 v5; // rax
  __int64 *v6; // rcx
  __int64 (__fastcall ***v7)(_QWORD, __int64); // rcx
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
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v13,
                         "void __cdecl UnBCL::ArrayList<class ISetupCleanupJob *>::RemoveAt(int)");
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
      v7 = *(__int64 (__fastcall ****)(_QWORD, __int64))(*v6 + 8 * v2);
      if ( v7 )
        LODWORD(v5) = (**v7)(v7, 1);
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
0x18000b604  mov     [rsp+arg_0], rbx
0x18000b609  mov     [rsp+arg_8], rsi
0x18000b60e  push    rdi
0x18000b60f  sub     rsp, 20h
0x18000b613  movsxd  rdi, edx
0x18000b616  mov     rbx, rcx
0x18000b619  test    edx, edx
0x18000b61b  js      loc_18000B706
0x18000b621  mov     rax, [rcx-68h]
0x18000b625  movsxd  rcx, dword ptr [rax+0Ch]
0x18000b629  add     rcx, 0FFFFFFFFFFFFFF98h
0x18000b62d  add     rcx, rbx
0x18000b630  mov     rax, [rcx]
0x18000b633  mov     rax, [rax]
0x18000b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63b  cmp     edi, eax
0x18000b63d  jge     loc_18000B706
0x18000b643  inc     dword ptr [rbx-58h]
0x18000b646  mov     rax, [rbx-70h]
0x18000b64a  lea     rcx, [rbx-70h]
0x18000b64e  mov     rax, [rax+20h]
0x18000b652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b657  test    eax, eax
0x18000b659  jz      short loc_18000B692
0x18000b65b  mov     rcx, [rbx-60h]
0x18000b65f  cmp     rdi, [rcx+8]
0x18000b663  jnb     loc_18000B6FB
0x18000b669  mov     rax, [rcx]
0x18000b66c  cmp     qword ptr [rax+rdi*8], 0
0x18000b671  jz      short loc_18000B692
0x18000b673  lfence
0x18000b676  mov     rax, [rcx]
0x18000b679  mov     rcx, [rax+rdi*8]
0x18000b67d  test    rcx, rcx
0x18000b680  jz      short loc_18000B692
0x18000b682  mov     rax, [rcx]
0x18000b685  mov     edx, 1
0x18000b68a  mov     rax, [rax]
0x18000b68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b692  lea     rcx, [rdi+1]
0x18000b696  cmp     rcx, rdi
0x18000b699  jb      short loc_18000B6FB
0x18000b69b  cmp     rcx, 1
0x18000b69f  jb      short loc_18000B6FB
0x18000b6a1  mov     rbx, [rbx-60h]
0x18000b6a5  mov     rdx, [rbx+8]
0x18000b6a9  cmp     rcx, rdx
0x18000b6ac  ja      short loc_18000B6FB
0x18000b6ae  sub     rdx, rcx
0x18000b6b1  jz      short loc_18000B6E7
0x18000b6b3  mov     rax, [rbx]
0x18000b6b6  shl     rdx, 3; DestinationSize
0x18000b6ba  lea     r8, [rax+rcx*8]; Source
0x18000b6be  lea     rcx, [rax+rdi*8]; Destination
0x18000b6c2  mov     r9, rdx; SourceSize
0x18000b6c5  call    cs:__imp_memmove_s
0x18000b6cb  test    eax, eax
0x18000b6cd  jz      short loc_18000B6E7
0x18000b6cf  cmp     eax, 0Ch
0x18000b6d2  jz      loc_18000B76D
0x18000b6d8  cmp     eax, 16h
0x18000b6db  jz      short loc_18000B6FB
0x18000b6dd  cmp     eax, 22h ; '"'
0x18000b6e0  jz      short loc_18000B6FB
0x18000b6e2  cmp     eax, 50h ; 'P'
0x18000b6e5  jnz     short loc_18000B762
0x18000b6e7  dec     qword ptr [rbx+8]
0x18000b6eb  mov     rbx, [rsp+28h+arg_0]
0x18000b6f0  mov     rsi, [rsp+28h+arg_8]
0x18000b6f5  add     rsp, 20h
0x18000b6f9  pop     rdi
0x18000b6fa  retn
0x18000b6fb  mov     ecx, 80070057h; int
0x18000b700  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b706  mov     ecx, 38h ; '8'
0x18000b70b  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000b711  mov     rbx, rax
0x18000b714  mov     [rsp+28h+arg_18], rax
0x18000b719  test    rax, rax
0x18000b71c  jz      short loc_18000B73A
0x18000b71e  lea     rdx, aIndexOutOfRang_0; "index out of range to ArrayList#RemoveA"...
0x18000b725  mov     rcx, rax
0x18000b728  call    cs:__imp_??0ArgumentOutOfRangeException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentOutOfRangeException::ArgumentOutOfRangeException(ushort const *)
0x18000b72e  lea     rax, ??_SArgumentOutOfRangeException@UnBCL@@6B@; const UnBCL::ArgumentOutOfRangeException::`local vftable'
0x18000b735  mov     [rbx], rax
0x18000b738  jmp     short loc_18000B73C
0x18000b73a  xor     ebx, ebx
0x18000b73c  lea     rdx, aVoidCdeclUnbcl_6; "void __cdecl UnBCL::ArrayList<class ISe"...
0x18000b743  mov     rcx, rbx
0x18000b746  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x18000b74b  mov     [rsp+28h+pExceptionObject], rax
0x18000b750  lea     rdx, _TI6PEAVArgumentOutOfRangeException@UnBCL@@; pThrowInfo
0x18000b757  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000b75c  call    _CxxThrowException_0
0x18000b762  mov     ecx, 80004005h; int
0x18000b767  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b76d  mov     ecx, 8007000Eh; int
0x18000b772  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
