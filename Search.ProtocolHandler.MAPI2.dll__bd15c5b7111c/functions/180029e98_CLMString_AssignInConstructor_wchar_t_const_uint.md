# CLMString::AssignInConstructor(wchar_t const *,uint)

- ea: `0x180029e98`
- end: `0x180029f69`
- name: `?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z`
- size: `209`
- prototype: `__int64 __fastcall(void **this, const wchar_t *, int)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001359c`
- `0x180016044`
- `0x1800179d8`
- `0x180017a1c`
- `0x180017afc`
- `0x180023ba0`
- `0x180025a1c`

## callees

- `0x18000da40`
- `0x180029b08`
- `0x180029b30`
- `0x180029b5c`
- `0x180029e98`
- `0x180029fb4`
- `0x18003a0e4`

## string_xrefs

- `0x180029eb9`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CLMString::AssignInConstructor(void **this, const wchar_t *a2, int a3)
{
  int v3; // ebx
  __int64 v6; // rax
  unsigned int *v7; // rax
  unsigned int *v8; // rax
  _WORD *v9; // rcx
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v13; // [rsp+48h] [rbp+10h] BYREF
  __int64 v14; // [rsp+58h] [rbp+20h] BYREF

  v3 = a3;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v11);
  v13 = a3;
  if ( a3 == -1 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v14 = v6;
    SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(
      &v13,
      &v14);
    v3 = v13;
  }
  if ( *(_DWORD *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                    &v13,
                    &v14) > *((_DWORD *)this + 4) )
  {
    v7 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                           &v13,
                           &v14);
    CLMString::GrowInConstructor((CLMString *)this, *v7);
  }
  v8 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(
                         &v13,
                         &v14);
  memcpy_0(this[1], a2, *v8);
  v9 = this[1];
  *((_DWORD *)this + 5) = v3;
  v9[v3] = 0;
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180029e98  mov     [rsp+arg_0], rbx
0x180029e9d  push    rbp
0x180029e9e  push    rsi
0x180029e9f  push    rdi; int
0x180029ea0  sub     rsp, 20h
0x180029ea4  xor     ebp, ebp
0x180029ea6  mov     ebx, r8d
0x180029ea9  mov     rsi, rdx
0x180029eac  mov     rdi, rcx
0x180029eaf  test    rdx, rdx
0x180029eb2  jnz     short loc_180029ED1
0x180029eb4  mov     rcx, [rsp+38h]; this
0x180029eb9  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180029ec0  mov     r9d, 80070057h; char *
0x180029ec6  mov     edx, 91h; void *
0x180029ecb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029ed1  mov     [rsp+38h+arg_8], ebx
0x180029ed5  cmp     ebx, 0FFFFFFFFh
0x180029ed8  jnz     short loc_180029EFF
0x180029eda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029ede  inc     rax
0x180029ee1  cmp     [rdx+rax*2], bp
0x180029ee5  jnz     short loc_180029EDE
0x180029ee7  lea     rdx, [rsp+38h+arg_18]
0x180029eec  mov     [rsp+38h+arg_18], rax
0x180029ef1  lea     rcx, [rsp+38h+arg_8]
0x180029ef6  call    ??$?4_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEAAAEAV0@AEB_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator=<unsigned __int64>(unsigned __int64 const &)
0x180029efb  mov     ebx, [rsp+38h+arg_8]
0x180029eff  lea     rdx, [rsp+38h+arg_18]
0x180029f04  lea     rcx, [rsp+38h+arg_8]
0x180029f09  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029f0e  mov     ecx, [rax]
0x180029f10  cmp     ecx, [rdi+10h]
0x180029f13  jbe     short loc_180029F2E
0x180029f15  lea     rdx, [rsp+38h+arg_18]
0x180029f1a  lea     rcx, [rsp+38h+arg_8]
0x180029f1f  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180029f24  mov     rcx, rdi; this
0x180029f27  mov     edx, [rax]; unsigned int
0x180029f29  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x180029f2e  lea     rdx, [rsp+38h+arg_18]
0x180029f33  lea     rcx, [rsp+38h+arg_8]
0x180029f38  call    ??$?D_K@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@_K@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator*<unsigned __int64>(unsigned __int64)
0x180029f3d  mov     rcx, [rdi+8]; void *
0x180029f41  mov     rdx, rsi; Src
0x180029f44  mov     r8d, [rax]; Size
0x180029f47  call    memcpy_0
0x180029f4c  mov     rcx, [rdi+8]
0x180029f50  mov     [rdi+14h], ebx
0x180029f53  mov     edx, ebx
0x180029f55  mov     rbx, [rsp+38h+arg_0]
0x180029f5a  mov     [rcx+rdx*2], bp
0x180029f5e  mov     eax, [rdi+14h]
0x180029f61  add     rsp, 20h
0x180029f65  pop     rdi
0x180029f66  pop     rsi
0x180029f67  pop     rbp
0x180029f68  retn
```
