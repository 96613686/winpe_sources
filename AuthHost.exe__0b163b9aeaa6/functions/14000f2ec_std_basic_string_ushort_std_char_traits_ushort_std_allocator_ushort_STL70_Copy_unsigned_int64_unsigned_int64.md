# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000f2ec`
- end: `0x14000f458`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f640`

## callees

- `0x1400029d3`
- `0x14000f2ec`
- `0x14000fa04`
- `0x140012d10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f417`
- `msvcrt!memcpy_s` at `0x14000f417`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14000f3a7`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14000f3a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  __int64 v5; // rsi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  void *v12; // r12
  const void **v13; // r14
  const void *v14; // r8
  __int64 v15; // r13
  __int64 result; // rax
  unsigned __int64 v17; // rcx
  __int64 *v18; // rdx
  __int64 v19; // [rsp+0h] [rbp-88h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v21[10]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v23; // [rsp+90h] [rbp+8h]
  char *v24; // [rsp+98h] [rbp+10h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+18h]
  void *Destination; // [rsp+A8h] [rbp+20h] BYREF

  v25 = a3;
  v24 = (char *)a2;
  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v9 < v7 >> 1 && v7 <= 0x7FFFFFFFFFFFFFFELL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v10 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( 0xFFFFFFFFFFFFFFFFuLL / v10 < 2 )
    {
      Destination = 0;
      exception::exception((exception *)pExceptionObject, (const char *const *)&Destination);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    Destination = 0;
    Common::GlobalHeap::Alloc((ReservedForLocalUse *)(2 * v10), &Destination);
    v12 = Destination;
  }
  catch ( ... )
  {
    Destination = v24;
    v17 = (unsigned __int64)(v24 + 1);
    if ( v24 == (char *)-1LL || 0xFFFFFFFFFFFFFFFFuLL / v17 >= 2 )
    {
      Common::GlobalHeap::Alloc((ReservedForLocalUse *)(2 * v17), (void **)&v24);
      v5 = a1;
      v3 = v25;
      v4 = (unsigned __int64)Destination;
      v12 = 0;
      goto LABEL_10;
    }
    try
    {
      exception::exception((exception *)v21, (const char *const *)&v24);
      v21[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)v21;
    }
    catch ( ... )
    {
      v18 = &v19;
      LOBYTE(v18) = 1;
      std::wstring::_Tidy(v23, v18, 0);
      throw;
    }
  }
LABEL_10:
  v13 = (const void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 8u )
      v14 = (const void *)(v5 + 8);
    else
      v14 = *v13;
    v15 = 2 * v3;
    memcpy_s(v12, 2 * v4 + 2, v14, 2 * v3);
  }
  else
  {
    v15 = 0;
  }
  LOBYTE(v11) = 1;
  result = std::wstring::_Tidy(v5, v11, 0);
  *v13 = v12;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 8 )
    v13 = (const void **)v12;
  *(_QWORD *)(v5 + 24) = v3;
  *(_WORD *)((char *)v13 + v15) = 0;
  return result;
}

```

## disassembly

```asm
0x14000f2ec  mov     [rsp+arg_10], r8
0x14000f2f1  mov     [rsp+arg_8], rdx
0x14000f2f6  mov     [rsp+arg_0], rcx
0x14000f2fb  push    rbx
0x14000f2fc  push    rsi
0x14000f2fd  push    rdi
0x14000f2fe  push    r12
0x14000f300  push    r13
0x14000f302  push    r14
0x14000f304  push    r15
0x14000f306  sub     rsp, 50h
0x14000f30a  mov     r15, r8
0x14000f30d  mov     rdi, rdx
0x14000f310  mov     rsi, rcx
0x14000f313  or      rdx, 7
0x14000f317  mov     r9, 7FFFFFFFFFFFFFFEh
0x14000f321  cmp     rdx, r9
0x14000f324  ja      short loc_14000F354
0x14000f326  mov     rdi, rdx
0x14000f329  mov     r8, [rcx+20h]
0x14000f32d  mov     rcx, r8
0x14000f330  shr     rcx, 1
0x14000f333  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000f33d  mul     rdx
0x14000f340  shr     rdx, 1
0x14000f343  cmp     rdx, rcx
0x14000f346  jnb     short loc_14000F354
0x14000f348  sub     r9, rcx
0x14000f34b  cmp     r8, r9
0x14000f34e  ja      short loc_14000F354
0x14000f350  lea     rdi, [rcx+r8]
0x14000f354  lea     rcx, [rdi+1]
0x14000f358  xor     ebx, ebx
0x14000f35a  test    rcx, rcx
0x14000f35d  jnz     short loc_14000F383
0x14000f35f  mov     ecx, ebx
0x14000f361  mov     [rsp+88h+Destination], rbx
0x14000f369  add     rcx, rcx; unsigned __int64
0x14000f36c  lea     rdx, [rsp+88h+Destination]; void **
0x14000f374  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x14000f379  mov     r12, [rsp+88h+Destination]
0x14000f381  jmp     short loc_14000F3ED
0x14000f383  xor     edx, edx
0x14000f385  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000f389  div     rcx
0x14000f38c  cmp     rax, 2
0x14000f390  jnb     short loc_14000F361
0x14000f392  mov     [rsp+88h+Destination], rbx
0x14000f39a  lea     rdx, [rsp+88h+Destination]
0x14000f3a2  lea     rcx, [rsp+88h+pExceptionObject]
0x14000f3a7  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x14000f3ad  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000f3b4  mov     [rsp+88h+pExceptionObject], rax
0x14000f3b9  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000f3c0  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x14000f3c5  call    _CxxThrowException_0
0x14000f3cb  xor     ebx, ebx
0x14000f3cd  mov     rsi, [rsp+88h+arg_0]
0x14000f3d5  mov     r15, [rsp+88h+arg_10]
0x14000f3dd  mov     rdi, [rsp+88h+Destination]
0x14000f3e5  mov     r12, [rsp+88h+arg_8]
0x14000f3ed  lea     r14, [rsi+8]
0x14000f3f1  test    r15, r15
0x14000f3f4  jz      short loc_14000F41F
0x14000f3f6  cmp     qword ptr [rsi+20h], 8
0x14000f3fb  jb      short loc_14000F402
0x14000f3fd  mov     r8, [r14]
0x14000f400  jmp     short loc_14000F405
0x14000f402  mov     r8, r14; Source
0x14000f405  lea     r13, [r15+r15]
0x14000f409  lea     rdx, ds:2[rdi*2]; DestinationSize
0x14000f411  mov     r9, r13; SourceSize
0x14000f414  mov     rcx, r12; Destination
0x14000f417  call    cs:__imp_memcpy_s
0x14000f41d  jmp     short loc_14000F423
0x14000f41f  lea     r13, [r15+r15]
0x14000f423  xor     r8d, r8d
0x14000f426  mov     dl, 1
0x14000f428  mov     rcx, rsi
0x14000f42b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f430  mov     [r14], r12
0x14000f433  mov     [rsi+20h], rdi
0x14000f437  cmp     rdi, 8
0x14000f43b  cmovnb  r14, r12
0x14000f43f  mov     [rsi+18h], r15
0x14000f443  mov     [r14+r13], bx
0x14000f448  add     rsp, 50h
0x14000f44c  pop     r15
0x14000f44e  pop     r14
0x14000f450  pop     r13
0x14000f452  pop     r12
0x14000f454  pop     rdi
0x14000f455  pop     rsi
0x14000f456  pop     rbx
0x14000f457  retn
```
