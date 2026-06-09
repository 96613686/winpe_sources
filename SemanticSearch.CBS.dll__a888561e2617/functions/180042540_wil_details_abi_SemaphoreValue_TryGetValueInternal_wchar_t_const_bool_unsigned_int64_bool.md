# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180042540`
- end: `0x18004282a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `746`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800435d0`

## callees

- `0x18003c9e0`
- `0x180041c60`
- `0x180041c80`
- `0x1800423c0`
- `0x180042540`
- `0x18004c070`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180042651`
- `KERNEL32!GetLastError` at `0x180042651`
- `KERNEL32!CloseHandle` at `0x1800427b2`
- `KERNEL32!CloseHandle` at `0x1800427c1`
- `KERNEL32!CloseHandle` at `0x1800427e2`
- `KERNEL32!CloseHandle` at `0x1800427b2`
- `KERNEL32!CloseHandle` at `0x1800427c1`
- `KERNEL32!CloseHandle` at `0x1800427e2`
- `KERNEL32!OpenSemaphoreW` at `0x180042643`
- `KERNEL32!OpenSemaphoreW` at `0x18004275e`
- `KERNEL32!OpenSemaphoreW` at `0x180042643`
- `KERNEL32!OpenSemaphoreW` at `0x18004275e`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebp
  __int64 v5; // r9
  WCHAR *v6; // rdx
  signed __int64 v7; // rcx
  WCHAR v9; // ax
  WCHAR *v10; // rax
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rax
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  char *v18; // r9
  WCHAR v19; // r8
  WCHAR *v20; // rax
  HANDLE v21; // rax
  void *v22; // rbx
  unsigned int v23; // r8d
  const char *v24; // r9
  int ValueFromSemaphore; // eax
  unsigned int v26; // r8d
  int v27; // r14d
  __int64 v29; // rcx
  WCHAR *v30; // rax
  WCHAR *v31; // rdx
  __int64 v32; // rdi
  char *v33; // rcx
  WCHAR v34; // ax
  WCHAR *v35; // rax
  HANDLE v36; // rax
  unsigned int v37; // r8d
  const char *v38; // r9
  void *v39; // rsi
  int v40; // edi
  int v41; // eax
  unsigned int v42; // r8d
  unsigned int v43; // r8d
  const char *v44; // r9
  unsigned int v45; // r8d
  const char *v46; // r9
  unsigned int v47; // r8d
  const char *v48; // r9
  int v49; // [rsp+20h] [rbp-248h] BYREF
  int v50[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  LastError = 0;
  *a3 = 0;
  v5 = 260;
  v6 = Name;
  v7 = (char *)a1 - (char *)Name;
  do
  {
    if ( v5 == -2147483386 )
      break;
    v9 = *(WCHAR *)((char *)v6 + v7);
    if ( !v9 )
      break;
    *v6++ = v9;
    --v5;
  }
  while ( v5 );
  v10 = v6 - 1;
  v11 = 260;
  if ( v5 )
    v10 = v6;
  *v10 = 0;
  v12 = Name;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = 2147483646;
  v14 = 260 - v11;
  if ( v11 )
  {
    v15 = &Name[v14];
    v16 = 260 - v14;
    if ( v14 != 260 )
    {
      v17 = 2147483646;
      v18 = (char *)((char *)L"_p0" - (char *)v15);
      do
      {
        if ( !v17 )
          break;
        v19 = *(_WORD *)&v18[(_QWORD)v15];
        if ( !v19 )
          break;
        *v15 = v19;
        --v17;
        ++v15;
        --v16;
      }
      while ( v16 );
    }
    v20 = v15 - 1;
    if ( v16 )
      v20 = v15;
    *v20 = 0;
  }
  v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v21;
  if ( !v21 )
  {
    if ( GetLastError() != 2 )
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v23, v24);
LABEL_24:
    if ( !v22 )
      return LastError;
    goto LABEL_45;
  }
  v49 = 0;
  v50[0] = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v49);
  v27 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    _mm_lfence();
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v26, (const char *)(unsigned int)ValueFromSemaphore, v49);
    LastError = v27;
    goto LABEL_24;
  }
  v29 = 260;
  v30 = Name;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  if ( v29 )
  {
    v31 = &Name[260 - v29];
    v32 = v29;
    v33 = (char *)((char *)L"h" - (char *)v31);
    do
    {
      if ( !v13 )
        break;
      v34 = *(WCHAR *)((char *)v31 + (_QWORD)v33);
      if ( !v34 )
        break;
      *v31 = v34;
      --v13;
      ++v31;
      --v32;
    }
    while ( v32 );
    v35 = v31 - 1;
    if ( v32 )
      v35 = v31;
    *v35 = 0;
  }
  v36 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v39 = v36;
  if ( v36 )
  {
    v41 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v36, v50);
    v40 = v41;
    _mm_lfence();
    if ( v41 >= 0 )
    {
      if ( !CloseHandle(v39) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v45, v46);
      *a3 = v49 | (unsigned __int64)((__int64)v50[0] << 31);
      goto LABEL_45;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v42, (const char *)(unsigned int)v41, v49);
    if ( !CloseHandle(v39) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v43, v44);
  }
  else
  {
    v40 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v37, v38);
  }
  LastError = v40;
LABEL_45:
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9CD, v47, v48);
  return LastError;
}

```

## disassembly

```asm
0x180042540  mov     [rsp+arg_8], rbx
0x180042545  mov     [rsp+arg_18], rbp
0x18004254a  push    rsi
0x18004254b  push    rdi
0x18004254c  push    r15
0x18004254e  sub     rsp, 250h
0x180042555  mov     rax, cs:__security_cookie
0x18004255c  xor     rax, rsp
0x18004255f  mov     [rsp+268h+var_28], rax
0x180042567  xor     ebp, ebp
0x180042569  lea     rax, [rsp+268h+Name]
0x18004256e  mov     edi, 104h
0x180042573  mov     [r8], rbp
0x180042576  mov     r9d, edi
0x180042579  lea     rdx, [rsp+268h+Name]
0x18004257e  sub     rcx, rax
0x180042581  mov     r15, r8
0x180042584  lea     rax, [r9+7FFFFEFAh]
0x18004258b  test    rax, rax
0x18004258e  jz      short loc_1800425A6
0x180042590  movzx   eax, word ptr [rdx+rcx]
0x180042594  test    ax, ax
0x180042597  jz      short loc_1800425A6
0x180042599  mov     [rdx], ax
0x18004259c  add     rdx, 2
0x1800425a0  sub     r9, 1
0x1800425a4  jnz     short loc_180042584
0x1800425a6  test    r9, r9
0x1800425a9  lea     rax, [rdx-2]
0x1800425ad  mov     rcx, rdi
0x1800425b0  cmovnz  rax, rdx
0x1800425b4  mov     [rax], bp
0x1800425b7  lea     rax, [rsp+268h+Name]
0x1800425bc  nop     dword ptr [rax+00h]
0x1800425c0  cmp     [rax], bp
0x1800425c3  jz      short loc_1800425CF
0x1800425c5  add     rax, 2
0x1800425c9  sub     rcx, 1
0x1800425cd  jnz     short loc_1800425C0
0x1800425cf  mov     rax, rdi
0x1800425d2  mov     esi, 7FFFFFFEh
0x1800425d7  sub     rax, rcx
0x1800425da  test    rcx, rcx
0x1800425dd  cmovz   rax, rbp
0x1800425e1  jz      short loc_18004262F
0x1800425e3  mov     rdx, rdi
0x1800425e6  lea     rcx, [rsp+268h+Name]
0x1800425eb  lea     rcx, [rcx+rax*2]
0x1800425ef  sub     rdx, rax
0x1800425f2  jz      short loc_180042621
0x1800425f4  lea     r9, aP0; "_p0"
0x1800425fb  mov     eax, esi
0x1800425fd  sub     r9, rcx
0x180042600  test    rax, rax
0x180042603  jz      short loc_180042621
0x180042605  movzx   r8d, word ptr [rcx+r9]
0x18004260a  test    r8w, r8w
0x18004260e  jz      short loc_180042621
0x180042610  mov     [rcx], r8w
0x180042614  dec     rax
0x180042617  add     rcx, 2
0x18004261b  sub     rdx, 1
0x18004261f  jnz     short loc_180042600
0x180042621  test    rdx, rdx
0x180042624  lea     rax, [rcx-2]
0x180042628  cmovnz  rax, rcx
0x18004262c  mov     [rax], bp
0x18004262f  lea     r8, [rsp+268h+Name]; lpName
0x180042634  mov     [rsp+268h+arg_0], r14
0x18004263c  xor     edx, edx; bInheritHandle
0x18004263e  mov     ecx, 1F0003h; dwDesiredAccess
0x180042643  call    cs:__imp_OpenSemaphoreW
0x180042649  mov     rbx, rax
0x18004264c  test    rax, rax
0x18004264f  jnz     short loc_180042672
0x180042651  call    cs:__imp_GetLastError
0x180042657  cmp     eax, 2
0x18004265a  jz      short loc_1800426A9
0x18004265c  mov     rcx, [rsp+268h]; this
0x180042664  mov     edx, 0CDh; void *
0x180042669  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004266e  mov     ebp, eax
0x180042670  jmp     short loc_1800426A9
0x180042672  lea     rdx, [rsp+268h+var_248]; int *
0x180042677  mov     [rsp+268h+var_248], ebp; int
0x18004267b  mov     rcx, rbx; hHandle
0x18004267e  mov     [rsp+268h+var_244], ebp
0x180042682  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180042687  mov     r14d, eax
0x18004268a  test    eax, eax
0x18004268c  jns     short loc_1800426E4
0x18004268e  lfence
0x180042691  mov     rcx, [rsp+268h]; this
0x180042699  mov     r9d, eax; char *
0x18004269c  mov     edx, 0D3h; void *
0x1800426a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800426a6  mov     ebp, r14d
0x1800426a9  test    rbx, rbx
0x1800426ac  jnz     loc_1800427DF
0x1800426b2  mov     r14, [rsp+268h+arg_0]
0x1800426ba  mov     eax, ebp
0x1800426bc  mov     rcx, [rsp+268h+var_28]
0x1800426c4  xor     rcx, rsp; StackCookie
0x1800426c7  call    __security_check_cookie
0x1800426cc  lea     r11, [rsp+268h+var_18]
0x1800426d4  mov     rbx, [r11+28h]
0x1800426d8  mov     rbp, [r11+38h]
0x1800426dc  mov     rsp, r11
0x1800426df  pop     r15
0x1800426e1  pop     rdi
0x1800426e2  pop     rsi
0x1800426e3  retn
0x1800426e4  mov     rcx, rdi
0x1800426e7  lea     rax, [rsp+268h+Name]
0x1800426ec  nop     dword ptr [rax+00h]
0x1800426f0  cmp     [rax], bp
0x1800426f3  jz      short loc_1800426FF
0x1800426f5  add     rax, 2
0x1800426f9  sub     rcx, 1
0x1800426fd  jnz     short loc_1800426F0
0x1800426ff  mov     rax, rdi
0x180042702  sub     rax, rcx
0x180042705  test    rcx, rcx
0x180042708  cmovz   rax, rbp
0x18004270c  jz      short loc_180042752
0x18004270e  lea     rdx, [rsp+268h+Name]
0x180042713  lea     rdx, [rdx+rax*2]
0x180042717  sub     rdi, rax
0x18004271a  jz      short loc_180042744
0x18004271c  lea     rcx, asc_180076850; "h"
0x180042723  sub     rcx, rdx
0x180042726  test    rsi, rsi
0x180042729  jz      short loc_180042744
0x18004272b  movzx   eax, word ptr [rcx+rdx]
0x18004272f  test    ax, ax
0x180042732  jz      short loc_180042744
0x180042734  mov     [rdx], ax
0x180042737  dec     rsi
0x18004273a  add     rdx, 2
0x18004273e  sub     rdi, 1
0x180042742  jnz     short loc_180042726
0x180042744  test    rdi, rdi
0x180042747  lea     rax, [rdx-2]
0x18004274b  cmovnz  rax, rdx
0x18004274f  mov     [rax], bp
0x180042752  lea     r8, [rsp+268h+Name]; lpName
0x180042757  xor     edx, edx; bInheritHandle
0x180042759  mov     ecx, 1F0003h; dwDesiredAccess
0x18004275e  call    cs:__imp_OpenSemaphoreW
0x180042764  mov     rsi, rax
0x180042767  test    rax, rax
0x18004276a  jnz     short loc_180042784
0x18004276c  mov     rcx, [rsp+268h]; this
0x180042774  mov     edx, 0D9h; void *
0x180042779  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004277e  mov     edi, eax
0x180042780  mov     ebp, edi
0x180042782  jmp     short loc_1800427DF
0x180042784  lea     rdx, [rsp+268h+var_244]; int *
0x180042789  mov     rcx, rsi; hHandle
0x18004278c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180042791  mov     edi, eax
0x180042793  lfence
0x180042796  test    eax, eax
0x180042798  jns     short loc_1800427BE
0x18004279a  mov     rcx, [rsp+268h]; this
0x1800427a2  mov     r9d, eax; char *
0x1800427a5  mov     edx, 0DBh; void *
0x1800427aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800427af  mov     rcx, rsi; hObject
0x1800427b2  call    cs:__imp_CloseHandle
0x1800427b8  test    eax, eax
0x1800427ba  jz      short loc_180042804
0x1800427bc  jmp     short loc_180042780
0x1800427be  mov     rcx, rsi; hObject
0x1800427c1  call    cs:__imp_CloseHandle
0x1800427c7  test    eax, eax
0x1800427c9  jz      short loc_1800427F1
0x1800427cb  movsxd  rcx, [rsp+268h+var_244]
0x1800427d0  movsxd  rax, [rsp+268h+var_248]
0x1800427d5  shl     rcx, 1Fh
0x1800427d9  or      rcx, rax
0x1800427dc  mov     [r15], rcx
0x1800427df  mov     rcx, rbx; hObject
0x1800427e2  call    cs:__imp_CloseHandle
0x1800427e8  test    eax, eax
0x1800427ea  jz      short loc_180042817
0x1800427ec  jmp     loc_1800426B2
0x1800427f1  mov     rcx, [rsp+268h]; this
0x1800427f9  mov     edx, 9CDh; void *
0x1800427fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180042804  mov     rcx, [rsp+268h]; this
0x18004280c  mov     edx, 9CDh; void *
0x180042811  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180042817  mov     rcx, [rsp+268h]; this
0x18004281f  mov     edx, 9CDh; void *
0x180042824  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
