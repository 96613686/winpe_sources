# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800043e0`
- end: `0x1800046ca`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `746`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180005680`

## callees

- `0x180003e90`
- `0x180003eb0`
- `0x180003ed0`
- `0x180004260`
- `0x1800043e0`
- `0x180007280`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800044f1`
- `KERNEL32!GetLastError` at `0x1800044f1`
- `KERNEL32!OpenSemaphoreW` at `0x1800044e3`
- `KERNEL32!OpenSemaphoreW` at `0x1800045fe`
- `KERNEL32!OpenSemaphoreW` at `0x1800044e3`
- `KERNEL32!OpenSemaphoreW` at `0x1800045fe`
- `KERNEL32!CloseHandle` at `0x180004652`
- `KERNEL32!CloseHandle` at `0x180004661`
- `KERNEL32!CloseHandle` at `0x180004682`
- `KERNEL32!CloseHandle` at `0x180004652`
- `KERNEL32!CloseHandle` at `0x180004661`
- `KERNEL32!CloseHandle` at `0x180004682`

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
  int v26; // r8d
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
  int v42; // r8d
  int v43; // r8d
  const char *v44; // r9
  int v45; // r8d
  const char *v46; // r9
  int v47; // r8d
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v26, (const char *)(unsigned int)ValueFromSemaphore);
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v42, (const char *)(unsigned int)v41);
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
0x1800043e0  mov     [rsp+arg_8], rbx
0x1800043e5  mov     [rsp+arg_18], rbp
0x1800043ea  push    rsi
0x1800043eb  push    rdi
0x1800043ec  push    r15
0x1800043ee  sub     rsp, 250h
0x1800043f5  mov     rax, cs:__security_cookie
0x1800043fc  xor     rax, rsp
0x1800043ff  mov     [rsp+268h+var_28], rax
0x180004407  xor     ebp, ebp
0x180004409  lea     rax, [rsp+268h+Name]
0x18000440e  mov     edi, 104h
0x180004413  mov     [r8], rbp
0x180004416  mov     r9d, edi
0x180004419  lea     rdx, [rsp+268h+Name]
0x18000441e  sub     rcx, rax
0x180004421  mov     r15, r8
0x180004424  lea     rax, [r9+7FFFFEFAh]
0x18000442b  test    rax, rax
0x18000442e  jz      short loc_180004446
0x180004430  movzx   eax, word ptr [rdx+rcx]
0x180004434  test    ax, ax
0x180004437  jz      short loc_180004446
0x180004439  mov     [rdx], ax
0x18000443c  add     rdx, 2
0x180004440  sub     r9, 1
0x180004444  jnz     short loc_180004424
0x180004446  test    r9, r9
0x180004449  lea     rax, [rdx-2]
0x18000444d  mov     rcx, rdi
0x180004450  cmovnz  rax, rdx
0x180004454  mov     [rax], bp
0x180004457  lea     rax, [rsp+268h+Name]
0x18000445c  nop     dword ptr [rax+00h]
0x180004460  cmp     [rax], bp
0x180004463  jz      short loc_18000446F
0x180004465  add     rax, 2
0x180004469  sub     rcx, 1
0x18000446d  jnz     short loc_180004460
0x18000446f  mov     rax, rdi
0x180004472  mov     esi, 7FFFFFFEh
0x180004477  sub     rax, rcx
0x18000447a  test    rcx, rcx
0x18000447d  cmovz   rax, rbp
0x180004481  jz      short loc_1800044CF
0x180004483  mov     rdx, rdi
0x180004486  lea     rcx, [rsp+268h+Name]
0x18000448b  lea     rcx, [rcx+rax*2]
0x18000448f  sub     rdx, rax
0x180004492  jz      short loc_1800044C1
0x180004494  lea     r9, aP0; "_p0"
0x18000449b  mov     eax, esi
0x18000449d  sub     r9, rcx
0x1800044a0  test    rax, rax
0x1800044a3  jz      short loc_1800044C1
0x1800044a5  movzx   r8d, word ptr [rcx+r9]
0x1800044aa  test    r8w, r8w
0x1800044ae  jz      short loc_1800044C1
0x1800044b0  mov     [rcx], r8w
0x1800044b4  dec     rax
0x1800044b7  add     rcx, 2
0x1800044bb  sub     rdx, 1
0x1800044bf  jnz     short loc_1800044A0
0x1800044c1  test    rdx, rdx
0x1800044c4  lea     rax, [rcx-2]
0x1800044c8  cmovnz  rax, rcx
0x1800044cc  mov     [rax], bp
0x1800044cf  lea     r8, [rsp+268h+Name]; lpName
0x1800044d4  mov     [rsp+268h+arg_0], r14
0x1800044dc  xor     edx, edx; bInheritHandle
0x1800044de  mov     ecx, 1F0003h; dwDesiredAccess
0x1800044e3  call    cs:__imp_OpenSemaphoreW
0x1800044e9  mov     rbx, rax
0x1800044ec  test    rax, rax
0x1800044ef  jnz     short loc_180004512
0x1800044f1  call    cs:__imp_GetLastError
0x1800044f7  cmp     eax, 2
0x1800044fa  jz      short loc_180004549
0x1800044fc  mov     rcx, [rsp+268h]; this
0x180004504  mov     edx, 0CDh; void *
0x180004509  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000450e  mov     ebp, eax
0x180004510  jmp     short loc_180004549
0x180004512  lea     rdx, [rsp+268h+var_248]; int *
0x180004517  mov     [rsp+268h+var_248], ebp; int
0x18000451b  mov     rcx, rbx; hHandle
0x18000451e  mov     [rsp+268h+var_244], ebp
0x180004522  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004527  mov     r14d, eax
0x18000452a  test    eax, eax
0x18000452c  jns     short loc_180004584
0x18000452e  lfence
0x180004531  mov     rcx, [rsp+268h]; this
0x180004539  mov     r9d, eax; char *
0x18000453c  mov     edx, 0D3h; void *
0x180004541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004546  mov     ebp, r14d
0x180004549  test    rbx, rbx
0x18000454c  jnz     loc_18000467F
0x180004552  mov     r14, [rsp+268h+arg_0]
0x18000455a  mov     eax, ebp
0x18000455c  mov     rcx, [rsp+268h+var_28]
0x180004564  xor     rcx, rsp; StackCookie
0x180004567  call    __security_check_cookie
0x18000456c  lea     r11, [rsp+268h+var_18]
0x180004574  mov     rbx, [r11+28h]
0x180004578  mov     rbp, [r11+38h]
0x18000457c  mov     rsp, r11
0x18000457f  pop     r15
0x180004581  pop     rdi
0x180004582  pop     rsi
0x180004583  retn
0x180004584  mov     rcx, rdi
0x180004587  lea     rax, [rsp+268h+Name]
0x18000458c  nop     dword ptr [rax+00h]
0x180004590  cmp     [rax], bp
0x180004593  jz      short loc_18000459F
0x180004595  add     rax, 2
0x180004599  sub     rcx, 1
0x18000459d  jnz     short loc_180004590
0x18000459f  mov     rax, rdi
0x1800045a2  sub     rax, rcx
0x1800045a5  test    rcx, rcx
0x1800045a8  cmovz   rax, rbp
0x1800045ac  jz      short loc_1800045F2
0x1800045ae  lea     rdx, [rsp+268h+Name]
0x1800045b3  lea     rdx, [rdx+rax*2]
0x1800045b7  sub     rdi, rax
0x1800045ba  jz      short loc_1800045E4
0x1800045bc  lea     rcx, asc_18000E8A8; "h"
0x1800045c3  sub     rcx, rdx
0x1800045c6  test    rsi, rsi
0x1800045c9  jz      short loc_1800045E4
0x1800045cb  movzx   eax, word ptr [rcx+rdx]
0x1800045cf  test    ax, ax
0x1800045d2  jz      short loc_1800045E4
0x1800045d4  mov     [rdx], ax
0x1800045d7  dec     rsi
0x1800045da  add     rdx, 2
0x1800045de  sub     rdi, 1
0x1800045e2  jnz     short loc_1800045C6
0x1800045e4  test    rdi, rdi
0x1800045e7  lea     rax, [rdx-2]
0x1800045eb  cmovnz  rax, rdx
0x1800045ef  mov     [rax], bp
0x1800045f2  lea     r8, [rsp+268h+Name]; lpName
0x1800045f7  xor     edx, edx; bInheritHandle
0x1800045f9  mov     ecx, 1F0003h; dwDesiredAccess
0x1800045fe  call    cs:__imp_OpenSemaphoreW
0x180004604  mov     rsi, rax
0x180004607  test    rax, rax
0x18000460a  jnz     short loc_180004624
0x18000460c  mov     rcx, [rsp+268h]; this
0x180004614  mov     edx, 0D9h; void *
0x180004619  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000461e  mov     edi, eax
0x180004620  mov     ebp, edi
0x180004622  jmp     short loc_18000467F
0x180004624  lea     rdx, [rsp+268h+var_244]; int *
0x180004629  mov     rcx, rsi; hHandle
0x18000462c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004631  mov     edi, eax
0x180004633  lfence
0x180004636  test    eax, eax
0x180004638  jns     short loc_18000465E
0x18000463a  mov     rcx, [rsp+268h]; this
0x180004642  mov     r9d, eax; char *
0x180004645  mov     edx, 0DBh; void *
0x18000464a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000464f  mov     rcx, rsi; hObject
0x180004652  call    cs:__imp_CloseHandle
0x180004658  test    eax, eax
0x18000465a  jz      short loc_1800046A4
0x18000465c  jmp     short loc_180004620
0x18000465e  mov     rcx, rsi; hObject
0x180004661  call    cs:__imp_CloseHandle
0x180004667  test    eax, eax
0x180004669  jz      short loc_180004691
0x18000466b  movsxd  rcx, [rsp+268h+var_244]
0x180004670  movsxd  rax, [rsp+268h+var_248]
0x180004675  shl     rcx, 1Fh
0x180004679  or      rcx, rax
0x18000467c  mov     [r15], rcx
0x18000467f  mov     rcx, rbx; hObject
0x180004682  call    cs:__imp_CloseHandle
0x180004688  test    eax, eax
0x18000468a  jz      short loc_1800046B7
0x18000468c  jmp     loc_180004552
0x180004691  mov     rcx, [rsp+268h]; this
0x180004699  mov     edx, 9CDh; void *
0x18000469e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800046a4  mov     rcx, [rsp+268h]; this
0x1800046ac  mov     edx, 9CDh; void *
0x1800046b1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800046b7  mov     rcx, [rsp+268h]; this
0x1800046bf  mov     edx, 9CDh; void *
0x1800046c4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
