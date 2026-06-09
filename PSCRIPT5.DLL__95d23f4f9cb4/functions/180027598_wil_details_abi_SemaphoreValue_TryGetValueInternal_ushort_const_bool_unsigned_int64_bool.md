# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027598`
- end: `0x180027830`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800238d4`
- `0x180023ca4`

## callees

- `0x180001ee0`
- `0x18001fe90`
- `0x180025234`
- `0x180026e60`
- `0x180026e80`
- `0x180027598`
- `0x180027dbc`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18002762f`
- `KERNEL32!OpenSemaphoreW` at `0x1800276b1`
- `KERNEL32!OpenSemaphoreW` at `0x18002762f`
- `KERNEL32!OpenSemaphoreW` at `0x1800276b1`
- `KERNEL32!CloseHandle` at `0x18002767c`
- `KERNEL32!CloseHandle` at `0x1800276f4`
- `KERNEL32!CloseHandle` at `0x180027705`
- `KERNEL32!CloseHandle` at `0x18002771d`
- `KERNEL32!CloseHandle` at `0x180027742`
- `KERNEL32!CloseHandle` at `0x18002776f`
- `KERNEL32!CloseHandle` at `0x18002767c`
- `KERNEL32!CloseHandle` at `0x1800276f4`
- `KERNEL32!CloseHandle` at `0x180027705`
- `KERNEL32!CloseHandle` at `0x18002771d`
- `KERNEL32!CloseHandle` at `0x180027742`
- `KERNEL32!CloseHandle` at `0x18002776f`
- `KERNEL32!GetLastError` at `0x18002777e`
- `KERNEL32!GetLastError` at `0x18002777e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wchar_t *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  wchar_t *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t pszDest[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = pszDest;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(pszDest, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x180027598  push    rbp
0x18002759a  push    rbx
0x18002759b  push    rsi
0x18002759c  push    rdi
0x18002759d  push    r14
0x18002759f  push    r15
0x1800275a1  lea     rbp, [rsp-158h]
0x1800275a9  sub     rsp, 258h
0x1800275b0  mov     rax, cs:__security_cookie
0x1800275b7  xor     rax, rsp
0x1800275ba  mov     [rbp+180h+var_40], rax
0x1800275c1  xor     r15d, r15d
0x1800275c4  lea     rax, [rsp+280h+pszDest]
0x1800275c9  mov     esi, 104h
0x1800275ce  mov     [r8], r15
0x1800275d1  mov     edx, esi
0x1800275d3  mov     r14, r8
0x1800275d6  mov     r9d, 7FFFFFFEh
0x1800275dc  test    r9, r9
0x1800275df  jz      short loc_180027600
0x1800275e1  movzx   r8d, word ptr [rcx]
0x1800275e5  test    r8w, r8w
0x1800275e9  jz      short loc_180027600
0x1800275eb  mov     [rax], r8w
0x1800275ef  add     rcx, 2
0x1800275f3  add     rax, 2
0x1800275f7  dec     r9
0x1800275fa  sub     rdx, 1
0x1800275fe  jnz     short loc_1800275DC
0x180027600  test    rdx, rdx
0x180027603  lea     rcx, [rax-2]
0x180027607  lea     r8, aP0; "_p0"
0x18002760e  mov     rdx, rsi; cchDest
0x180027611  cmovnz  rcx, rax
0x180027615  mov     [rcx], r15w
0x180027619  lea     rcx, [rsp+280h+pszDest]; pszDest
0x18002761e  call    StringCchCatW
0x180027623  lea     r8, [rsp+280h+pszDest]; lpName
0x180027628  xor     edx, edx; bInheritHandle
0x18002762a  mov     ecx, 1F0003h; dwDesiredAccess
0x18002762f  call    cs:__imp_OpenSemaphoreW
0x180027635  mov     rbx, rax
0x180027638  test    rax, rax
0x18002763b  jz      loc_18002777E
0x180027641  lea     rdx, [rsp+280h+var_25C]; int *
0x180027646  mov     [rsp+280h+var_25C], r15d
0x18002764b  mov     rcx, rax; hHandle
0x18002764e  mov     [rsp+280h+var_260], r15d; int
0x180027653  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027658  mov     edi, eax
0x18002765a  test    eax, eax
0x18002765c  jns     short loc_180027691
0x18002765e  mov     rcx, [rbp+188h]; this
0x180027665  lea     r8, aWil; "wil"
0x18002766c  mov     r9d, eax; char *
0x18002766f  mov     edx, 0D6h; void *
0x180027674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027679  mov     rcx, rbx; hObject
0x18002767c  call    cs:__imp_CloseHandle
0x180027682  test    eax, eax
0x180027684  jz      loc_1800277FA
0x18002768a  mov     eax, edi
0x18002768c  jmp     loc_1800277A5
0x180027691  lea     r8, asc_180064E00; "h"
0x180027698  mov     rdx, rsi; cchDest
0x18002769b  lea     rcx, [rsp+280h+pszDest]; pszDest
0x1800276a0  call    StringCchCatW
0x1800276a5  lea     r8, [rsp+280h+pszDest]; lpName
0x1800276aa  xor     edx, edx; bInheritHandle
0x1800276ac  mov     ecx, 1F0003h; dwDesiredAccess
0x1800276b1  call    cs:__imp_OpenSemaphoreW
0x1800276b7  mov     rdi, rax
0x1800276ba  test    rax, rax
0x1800276bd  jz      loc_180027752
0x1800276c3  lea     rdx, [rsp+280h+var_260]; int *
0x1800276c8  mov     rcx, rax; hHandle
0x1800276cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800276d0  mov     esi, eax
0x1800276d2  test    eax, eax
0x1800276d4  jns     short loc_18002771A
0x1800276d6  mov     rcx, [rbp+188h]; this
0x1800276dd  lea     r8, aWil; "wil"
0x1800276e4  mov     r9d, eax; char *
0x1800276e7  mov     edx, 0DEh; void *
0x1800276ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276f1  mov     rcx, rdi; hObject
0x1800276f4  call    cs:__imp_CloseHandle
0x1800276fa  test    eax, eax
0x1800276fc  jz      loc_18002780C
0x180027702  mov     rcx, rbx; hObject
0x180027705  call    cs:__imp_CloseHandle
0x18002770b  test    eax, eax
0x18002770d  jz      loc_18002781E
0x180027713  mov     eax, esi
0x180027715  jmp     loc_1800277A5
0x18002771a  mov     rcx, rdi; hObject
0x18002771d  call    cs:__imp_CloseHandle
0x180027723  test    eax, eax
0x180027725  jz      loc_1800277C4
0x18002772b  movsxd  rax, [rsp+280h+var_25C]
0x180027730  movsxd  rcx, [rsp+280h+var_260]
0x180027735  shl     rcx, 1Fh
0x180027739  or      rcx, rax
0x18002773c  mov     [r14], rcx
0x18002773f  mov     rcx, rbx; hObject
0x180027742  call    cs:__imp_CloseHandle
0x180027748  test    eax, eax
0x18002774a  jz      loc_1800277D6
0x180027750  jmp     short loc_180027789
0x180027752  mov     rcx, [rbp+188h]; this
0x180027759  lea     r8, aWil; "wil"
0x180027760  mov     edx, 0DCh; void *
0x180027765  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002776a  mov     rcx, rbx; hObject
0x18002776d  mov     edi, eax
0x18002776f  call    cs:__imp_CloseHandle
0x180027775  test    eax, eax
0x180027777  jz      short loc_1800277E8
0x180027779  jmp     loc_18002768A
0x18002777e  call    cs:__imp_GetLastError
0x180027784  cmp     eax, 2
0x180027787  jnz     short loc_18002778D
0x180027789  xor     eax, eax
0x18002778b  jmp     short loc_1800277A5
0x18002778d  mov     rcx, [rbp+188h]; this
0x180027794  lea     r8, aWil; "wil"
0x18002779b  mov     edx, 0D0h; void *
0x1800277a0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800277a5  mov     rcx, [rbp+180h+var_40]
0x1800277ac  xor     rcx, rsp; StackCookie
0x1800277af  call    __security_check_cookie
0x1800277b4  add     rsp, 258h
0x1800277bb  pop     r15
0x1800277bd  pop     r14
0x1800277bf  pop     rdi
0x1800277c0  pop     rsi
0x1800277c1  pop     rbx
0x1800277c2  pop     rbp
0x1800277c3  retn
0x1800277c4  mov     rcx, [rbp+188h]; this
0x1800277cb  mov     edx, 0A0Bh; void *
0x1800277d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800277d6  mov     rcx, [rbp+188h]; this
0x1800277dd  mov     edx, 0A0Bh; void *
0x1800277e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800277e8  mov     rcx, [rbp+188h]; this
0x1800277ef  mov     edx, 0A0Bh; void *
0x1800277f4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800277fa  mov     rcx, [rbp+188h]; this
0x180027801  mov     edx, 0A0Bh; void *
0x180027806  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002780c  mov     rcx, [rbp+188h]; this
0x180027813  mov     edx, 0A0Bh; void *
0x180027818  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18002781e  mov     rcx, [rbp+188h]; this
0x180027825  mov     edx, 0A0Bh; void *
0x18002782a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
