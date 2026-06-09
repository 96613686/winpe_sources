# CLMString::Assign(wchar_t const *,uint,uint)

- ea: `0x180029d20`
- end: `0x180029e92`
- name: `?Assign@CLMString@@UEAAHPEB_WII@Z`
- size: `370`
- prototype: `__int64 __fastcall(CLMString *this, const wchar_t *, unsigned int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000da40`
- `0x180021b04`
- `0x180029b08`
- `0x180029b30`
- `0x180029b5c`
- `0x180029bb0`
- `0x180029d20`
- `0x18003a0e4`
- `0x18003f010`

## string_xrefs

- `0x180029d48`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const wchar_t *a2, unsigned int a3, int a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rdx
  void (__fastcall *v12)(CLMString *, _QWORD); // rdi
  __int64 v13; // rax
  _BYTE *v14; // rdx
  int *v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned int *v17; // rax
  size_t v18; // rdi
  unsigned int v19; // ecx
  unsigned __int64 v20; // rax
  _WORD *v21; // rcx
  __int64 result; // rax
  int v23; // ecx
  __int64 v24; // rax
  int v25; // [rsp+20h] [rbp-18h] BYREF
  _BYTE v26[4]; // [rsp+24h] [rbp-14h] BYREF
  _QWORD v27[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  unsigned int v29; // [rsp+78h] [rbp+40h] BYREF

  v4 = a4;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v25);
  v29 = a3;
  v25 = a4;
  if ( a4 == -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v27[0] = v8;
    SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(
      &v25,
      v27);
    v4 = v25;
  }
  v9 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v29, v26, v4);
  v10 = (_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                    v9,
                    v27);
  v11 = *((unsigned int *)this + 4);
  if ( *v10 > (unsigned int)v11 )
  {
    v12 = **(void (__fastcall ***)(CLMString *, _QWORD))this;
    v13 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v29, v27, v4);
    v14 = v26;
    v15 = (int *)v13;
LABEL_13:
    v17 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                            v15,
                            v14);
    v12(this, *v17);
    goto LABEL_14;
  }
  if ( !a3 )
  {
    v16 = *((_QWORD *)this + 1);
    if ( (unsigned __int64)a2 < v16 || (unsigned __int64)a2 >= v16 + 2 * v11 )
    {
      v14 = v27;
      v15 = &v25;
      v12 = *(void (__fastcall **)(CLMString *, _QWORD))(*(_QWORD *)this + 8LL);
      goto LABEL_13;
    }
  }
LABEL_14:
  v18 = *(unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(
                           &v25,
                           v27);
  v19 = *(_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(
                     &v29,
                     v27);
  v20 = v19 + (unsigned int)v18;
  if ( (unsigned int)v20 < v19 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
  if ( v20 <= 2 * (unsigned __int64)*((unsigned int *)this + 4) )
  {
    v23 = *(_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(
                       &v29,
                       v27,
                       v4);
    v24 = *((_QWORD *)this + 1);
    *((_DWORD *)this + 5) = v23;
    memcpy_0((void *)(v24 + 2LL * v29), a2, v18);
    *(_WORD *)(*((_QWORD *)this + 1) + 2LL * *((unsigned int *)this + 5)) = 0;
    return *((unsigned int *)this + 5);
  }
  else
  {
    v21 = (_WORD *)*((_QWORD *)this + 1);
    result = 0;
    *((_DWORD *)this + 5) = 0;
    *v21 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180029d20  push    rbp
0x180029d22  push    rbx
0x180029d23  push    rsi
0x180029d24  push    rdi
0x180029d25  push    r14
0x180029d27  push    r15
0x180029d29  mov     rbp, rsp
0x180029d2c  sub     rsp, 38h
0x180029d30  xor     r15d, r15d
0x180029d33  mov     ebx, r9d
0x180029d36  mov     edi, r8d
0x180029d39  mov     r14, rdx
0x180029d3c  mov     rsi, rcx
0x180029d3f  test    rdx, rdx
0x180029d42  jnz     short loc_180029D5F
0x180029d44  mov     rcx, [rbp+30h]; this
0x180029d48  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180029d4f  mov     r9d, 80070057h; char *
0x180029d55  lea     edx, [r14+36h]; void *
0x180029d59  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029d5f  mov     [rbp+arg_8], edi
0x180029d62  mov     [rbp+var_18], ebx
0x180029d65  cmp     ebx, 0FFFFFFFFh
0x180029d68  jnz     short loc_180029D8C
0x180029d6a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029d6e  inc     rax
0x180029d71  cmp     [rdx+rax*2], r15w
0x180029d76  jnz     short loc_180029D6E
0x180029d78  lea     rdx, [rbp+var_10]
0x180029d7c  mov     [rbp+var_10], rax
0x180029d80  lea     rcx, [rbp+var_18]
0x180029d84  call    ??$?4_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEAAAEAV0@AEB_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(unsigned __int64 const &)
0x180029d89  mov     ebx, [rbp+var_18]
0x180029d8c  mov     r8d, ebx
0x180029d8f  lea     rdx, [rbp+var_14]
0x180029d93  lea     rcx, [rbp+arg_8]
0x180029d97  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180029d9c  lea     rdx, [rbp+var_10]
0x180029da0  mov     rcx, rax
0x180029da3  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029da8  mov     edx, [rsi+10h]
0x180029dab  cmp     [rax], edx
0x180029dad  jbe     short loc_180029DCE
0x180029daf  mov     rax, [rsi]
0x180029db2  lea     rdx, [rbp+var_10]
0x180029db6  mov     r8d, ebx
0x180029db9  lea     rcx, [rbp+arg_8]
0x180029dbd  mov     rdi, [rax]
0x180029dc0  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180029dc5  lea     rdx, [rbp+var_14]
0x180029dc9  mov     rcx, rax
0x180029dcc  jmp     short loc_180029DF3
0x180029dce  test    edi, edi
0x180029dd0  jnz     short loc_180029E05
0x180029dd2  mov     rcx, [rsi+8]
0x180029dd6  cmp     r14, rcx
0x180029dd9  jb      short loc_180029DE4
0x180029ddb  lea     rcx, [rcx+rdx*2]
0x180029ddf  cmp     r14, rcx
0x180029de2  jb      short loc_180029E05
0x180029de4  mov     rax, [rsi]
0x180029de7  lea     rdx, [rbp+var_10]
0x180029deb  lea     rcx, [rbp+var_18]
0x180029def  mov     rdi, [rax+8]
0x180029df3  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029df8  mov     rcx, rsi
0x180029dfb  mov     edx, [rax]
0x180029dfd  mov     rax, rdi
0x180029e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e05  lea     rdx, [rbp+var_10]
0x180029e09  lea     rcx, [rbp+var_18]
0x180029e0d  call    ??$?D_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(unsigned __int64)
0x180029e12  lea     rdx, [rbp+var_10]
0x180029e16  lea     rcx, [rbp+arg_8]
0x180029e1a  mov     edi, [rax]
0x180029e1c  call    ??$?D_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(unsigned __int64)
0x180029e21  mov     ecx, [rax]
0x180029e23  lea     eax, [rcx+rdi]
0x180029e26  cmp     eax, ecx
0x180029e28  jnb     short loc_180029E30
0x180029e2a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180029e30  mov     ecx, [rsi+10h]
0x180029e33  add     rcx, rcx
0x180029e36  cmp     rax, rcx
0x180029e39  jbe     short loc_180029E4B
0x180029e3b  mov     rcx, [rsi+8]
0x180029e3f  xor     eax, eax
0x180029e41  mov     [rsi+14h], r15d
0x180029e45  mov     [rcx], r15w
0x180029e49  jmp     short loc_180029E85
0x180029e4b  mov     r8d, ebx
0x180029e4e  lea     rdx, [rbp+var_10]
0x180029e52  lea     rcx, [rbp+arg_8]
0x180029e56  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180029e5b  mov     r8, rdi; Size
0x180029e5e  mov     rdx, r14; Src
0x180029e61  mov     ecx, [rax]
0x180029e63  mov     rax, [rsi+8]
0x180029e67  mov     [rsi+14h], ecx
0x180029e6a  mov     ecx, [rbp+arg_8]
0x180029e6d  lea     rcx, [rax+rcx*2]; void *
0x180029e71  call    memcpy_0
0x180029e76  mov     edx, [rsi+14h]
0x180029e79  mov     rcx, [rsi+8]
0x180029e7d  mov     [rcx+rdx*2], r15w
0x180029e82  mov     eax, [rsi+14h]
0x180029e85  add     rsp, 38h
0x180029e89  pop     r15
0x180029e8b  pop     r14
0x180029e8d  pop     rdi
0x180029e8e  pop     rsi
0x180029e8f  pop     rbx
0x180029e90  pop     rbp
0x180029e91  retn
```
