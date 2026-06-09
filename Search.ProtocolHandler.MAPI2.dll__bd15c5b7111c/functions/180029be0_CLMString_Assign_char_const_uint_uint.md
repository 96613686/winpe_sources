# CLMString::Assign(char const *,uint,uint)

- ea: `0x180029be0`
- end: `0x180029d0f`
- name: `?Assign@CLMString@@UEAAHPEBDII@Z`
- size: `303`
- prototype: `__int64 __fastcall(CLMString *this, const char *, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000da40`
- `0x180029b08`
- `0x180029b5c`
- `0x180029bb0`
- `0x180029be0`
- `0x18002b6f4`
- `0x18003f010`

## string_xrefs

- `0x180029c0a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const char *a2, unsigned int a3, int a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *v10; // rax
  __int64 v11; // rdx
  void (__fastcall *v12)(CLMString *, _QWORD); // rdi
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int *v15; // rax
  int *v16; // rax
  int v17; // r9d
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v21[4]; // [rsp+24h] [rbp-Ch] BYREF
  __int64 v22; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v24; // [rsp+58h] [rbp+28h] BYREF

  v4 = a4;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v20);
  v24 = a3;
  v20 = a4;
  if ( a4 == -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v22 = v8;
    SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(
      &v20,
      &v22);
    v4 = v20;
  }
  v9 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v24, v21, v4);
  v10 = (_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                    v9,
                    &v22);
  v11 = *((unsigned int *)this + 4);
  if ( *v10 <= (unsigned int)v11 )
  {
    if ( a3 )
      goto LABEL_14;
    v13 = *((_QWORD *)this + 1);
    if ( (unsigned __int64)a2 >= v13 && (unsigned __int64)a2 < v13 + 2 * v11 )
      goto LABEL_14;
    v12 = *(void (__fastcall **)(CLMString *, _QWORD))(*(_QWORD *)this + 8LL);
  }
  else
  {
    v12 = **(void (__fastcall ***)(CLMString *, _QWORD))this;
  }
  v14 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(&v24, &v22, v4);
  v15 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                          v14,
                          v21);
  v12(this, *v15);
LABEL_14:
  v16 = (int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                 &v20,
                 &v22);
  v17 = *v16;
  if ( *v16 + v24 > *((_DWORD *)this + 4) )
    return 0;
  v19 = v24;
  *((_DWORD *)this + 5) = v24;
  *((_DWORD *)this + 5) += MultiByteToWideCharSZ(a2, v4, (wchar_t *)(*((_QWORD *)this + 1) + 2 * v19), v17);
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180029be0  mov     [rsp-18h+arg_0], rbx
0x180029be5  mov     [rsp-18h+arg_10], rsi
0x180029bea  push    rbp
0x180029beb  push    rdi
0x180029bec  push    r14
0x180029bee  mov     rbp, rsp
0x180029bf1  sub     rsp, 30h
0x180029bf5  mov     ebx, r9d
0x180029bf8  mov     edi, r8d
0x180029bfb  mov     r14, rdx
0x180029bfe  mov     rsi, rcx
0x180029c01  test    rdx, rdx
0x180029c04  jnz     short loc_180029C21
0x180029c06  mov     rcx, [rbp+18h]; this
0x180029c0a  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180029c11  mov     r9d, 80070057h; char *
0x180029c17  lea     edx, [r14+63h]; void *
0x180029c1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029c21  mov     [rbp+arg_8], edi
0x180029c24  mov     [rbp+var_10], ebx
0x180029c27  cmp     ebx, 0FFFFFFFFh
0x180029c2a  jnz     short loc_180029C4D
0x180029c2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029c30  inc     rax
0x180029c33  cmp     byte ptr [rdx+rax], 0
0x180029c37  jnz     short loc_180029C30
0x180029c39  lea     rdx, [rbp+var_8]
0x180029c3d  mov     [rbp+var_8], rax
0x180029c41  lea     rcx, [rbp+var_10]
0x180029c45  call    ??$?4_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEAAAEAV0@AEB_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(unsigned __int64 const &)
0x180029c4a  mov     ebx, [rbp+var_10]
0x180029c4d  mov     r8d, ebx
0x180029c50  lea     rdx, [rbp+var_C]
0x180029c54  lea     rcx, [rbp+arg_8]
0x180029c58  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180029c5d  lea     rdx, [rbp+var_8]
0x180029c61  mov     rcx, rax
0x180029c64  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029c69  mov     edx, [rsi+10h]
0x180029c6c  cmp     [rax], edx
0x180029c6e  jbe     short loc_180029C78
0x180029c70  mov     rax, [rsi]
0x180029c73  mov     rdi, [rax]
0x180029c76  jmp     short loc_180029C95
0x180029c78  test    edi, edi
0x180029c7a  jnz     short loc_180029CBE
0x180029c7c  mov     rcx, [rsi+8]
0x180029c80  cmp     r14, rcx
0x180029c83  jb      short loc_180029C8E
0x180029c85  lea     rcx, [rcx+rdx*2]
0x180029c89  cmp     r14, rcx
0x180029c8c  jb      short loc_180029CBE
0x180029c8e  mov     rax, [rsi]
0x180029c91  mov     rdi, [rax+8]
0x180029c95  mov     r8d, ebx
0x180029c98  lea     rdx, [rbp+var_8]
0x180029c9c  lea     rcx, [rbp+arg_8]
0x180029ca0  call    ??H?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@V0@@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+(SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>)
0x180029ca5  lea     rdx, [rbp+var_C]
0x180029ca9  mov     rcx, rax
0x180029cac  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029cb1  mov     rcx, rsi
0x180029cb4  mov     edx, [rax]
0x180029cb6  mov     rax, rdi
0x180029cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029cbe  lea     rdx, [rbp+var_8]
0x180029cc2  lea     rcx, [rbp+var_10]
0x180029cc6  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029ccb  mov     r9d, [rax]; int
0x180029cce  mov     eax, [rbp+arg_8]
0x180029cd1  lea     ecx, [r9+rax]
0x180029cd5  cmp     ecx, [rsi+10h]
0x180029cd8  jbe     short loc_180029CDE
0x180029cda  xor     eax, eax
0x180029cdc  jmp     short loc_180029CFC
0x180029cde  mov     rcx, rax
0x180029ce1  mov     [rsi+14h], eax
0x180029ce4  mov     rax, [rsi+8]
0x180029ce8  mov     edx, ebx; cbMultiByte
0x180029cea  lea     r8, [rax+rcx*2]; wchar_t *
0x180029cee  mov     rcx, r14; lpMultiByteStr
0x180029cf1  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x180029cf6  add     [rsi+14h], eax
0x180029cf9  mov     eax, [rsi+14h]
0x180029cfc  mov     rbx, [rsp+30h+arg_0]
0x180029d01  mov     rsi, [rsp+30h+arg_10]
0x180029d06  add     rsp, 30h
0x180029d0a  pop     r14
0x180029d0c  pop     rdi
0x180029d0d  pop     rbp
0x180029d0e  retn
```
