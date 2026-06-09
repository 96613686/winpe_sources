# _InitPropVariantFromParsedString(wchar_t const *,tagPROPVARIANT *)

- ea: `0x180067008`
- end: `0x180067211`
- name: `?_InitPropVariantFromParsedString@@YAJPEB_WPEAUtagPROPVARIANT@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(const wchar_t *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180067b28`

## callees

- `0x180015a40`
- `0x180020250`
- `0x18003bed0`
- `0x18003e5d0`
- `0x18005daf0`
- `0x180067008`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180067054`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006715b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180067054`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006715b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180067152`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x180067152`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18006709d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180067131`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18006709d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180067131`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800671df`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const wchar_t *a1, struct tagPROPVARIANT *a2)
{
  wchar_t *v2; // rsi
  __int64 v5; // rcx
  int v6; // eax
  int v7; // ebx
  int v8; // edi
  const WCHAR *v9; // r8
  PWSTR v10; // rax
  int v11; // ecx
  BYTE *v12; // r12
  void *v13; // rcx
  unsigned int v14; // r9d
  int v15; // eax
  WCHAR *v16; // r14
  __int64 v17; // rdi
  PWSTR v18; // rax
  WCHAR *v19; // r15
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // r14
  unsigned __int64 i; // rdi
  PCWSTR pszStart; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  void *v27; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v28[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = v28;
  pszStart = v28;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  if ( (unsigned int)lstrlenW(a1) < 0x104 )
  {
    v6 = StringCchCopyW(v28, 0x104u, a1);
  }
  else
  {
    v6 = _AllocString<CTCoAllocPolicy>(v5, 260, (const size_t *)a1, &pszStart);
    v2 = (wchar_t *)pszStart;
  }
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    v9 = v2;
    while ( v9 )
    {
      v10 = StrChrW(v9, 0x3Bu);
      v11 = v8 + 1;
      if ( !v10 )
        v11 = v8;
      v9 = v10 + 1;
      v8 = v11;
      if ( !v10 )
        v9 = 0;
    }
    LODWORD(pszStart) = v8 + 1;
    if ( v8 != -1 )
    {
      v12 = 0;
      v27 = 0;
      v26 = 0;
      v7 = ULongLongMult((unsigned int)(v8 + 1), 8u, &v26);
      if ( v7 >= 0 )
      {
        v15 = CTCoAllocPolicy::Alloc(v13, 1u, v26, &v27);
        v14 = (unsigned int)pszStart;
        v7 = v15;
        v12 = (BYTE *)v27;
      }
      if ( v7 >= 0 )
      {
        v16 = v2;
        v17 = 0;
        while ( v16 )
        {
          if ( (unsigned int)v17 >= v14 )
            goto LABEL_24;
          v18 = StrChrW(v16, 0x3Bu);
          v19 = v18;
          if ( v18 )
          {
            *v18 = 0;
            v19 = v18 + 1;
          }
          StrTrimW(v16, L" ");
          if ( lstrlenW(v16) <= 0
            || (v7 = _AllocString<CTCoAllocPolicy>(v21, v20, (const size_t *)v16, &v12[8 * v17]), v7 < 0) )
          {
            v14 = (unsigned int)pszStart;
            v16 = v19;
            if ( v7 < 0 )
            {
LABEL_24:
              if ( v7 < 0 )
                goto LABEL_27;
              break;
            }
          }
          else
          {
            v14 = (unsigned int)pszStart;
            v17 = (unsigned int)(v17 + 1);
            v16 = v19;
          }
        }
        if ( (_DWORD)v17 )
        {
          a2->vt = 4127;
          a2->lVal = v17;
          a2->bstrblobVal.pData = v12;
          goto LABEL_30;
        }
LABEL_27:
        v22 = (unsigned int)v17;
        for ( i = 0; i < v22; ++i )
          CoTaskMemFree(*(LPVOID *)&v12[8 * i]);
        CoTaskMemFree(v12);
      }
    }
  }
LABEL_30:
  if ( v2 && v2 != v28 )
    CoTaskMemFree(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180067008  mov     [rsp-8+arg_10], rbx
0x18006700d  push    rbp
0x18006700e  push    rsi
0x18006700f  push    rdi
0x180067010  push    r12
0x180067012  push    r13
0x180067014  push    r14
0x180067016  push    r15
0x180067018  lea     rbp, [rsp-160h]
0x180067020  sub     rsp, 260h
0x180067027  mov     rax, cs:__security_cookie
0x18006702e  xor     rax, rsp
0x180067031  mov     [rbp+190h+var_40], rax
0x180067038  xorps   xmm0, xmm0
0x18006703b  lea     rsi, [rsp+290h+var_250]
0x180067040  xor     eax, eax
0x180067042  mov     [rsp+290h+pszStart], rsi
0x180067047  movups  xmmword ptr [rdx], xmm0
0x18006704a  mov     [rdx+10h], rax
0x18006704e  mov     r13, rdx
0x180067051  mov     rbx, rcx
0x180067054  call    cs:__imp_lstrlenW
0x18006705a  mov     edx, 104h; unsigned __int64
0x18006705f  mov     r8, rbx; wchar_t *
0x180067062  cmp     eax, edx
0x180067064  jb      short loc_180067077
0x180067066  lea     r9, [rsp+290h+pszStart]
0x18006706b  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180067070  mov     rsi, [rsp+290h+pszStart]
0x180067075  jmp     short loc_180067081
0x180067077  lea     rcx, [rsp+290h+var_250]; wchar_t *
0x18006707c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180067081  mov     ebx, eax
0x180067083  test    eax, eax
0x180067085  js      loc_1800671CD
0x18006708b  xor     edi, edi
0x18006708d  mov     r8, rsi
0x180067090  test    rsi, rsi
0x180067093  jz      short loc_1800670BB
0x180067095  mov     edx, 3Bh ; ';'; wMatch
0x18006709a  mov     rcx, r8; pszStart
0x18006709d  call    cs:__imp_StrChrW
0x1800670a3  test    rax, rax
0x1800670a6  lea     ecx, [rdi+1]
0x1800670a9  cmovz   ecx, edi
0x1800670ac  lea     r8, [rax+2]
0x1800670b0  mov     edi, ecx
0x1800670b2  cmovz   r8, rax
0x1800670b6  test    r8, r8
0x1800670b9  jnz     short loc_180067095
0x1800670bb  lea     r9d, [rdi+1]
0x1800670bf  mov     dword ptr [rsp+290h+pszStart], r9d
0x1800670c4  test    r9d, r9d
0x1800670c7  jz      loc_1800671CD
0x1800670cd  xor     r12d, r12d
0x1800670d0  mov     ecx, r9d; unsigned __int64
0x1800670d3  lea     r8, [rsp+290h+var_268]; unsigned __int64 *
0x1800670d8  mov     [rsp+290h+var_260], r12
0x1800670dd  mov     [rsp+290h+var_268], r12
0x1800670e2  lea     edx, [r12+8]; unsigned __int64
0x1800670e7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800670ec  mov     ebx, eax
0x1800670ee  test    eax, eax
0x1800670f0  js      short loc_180067112
0x1800670f2  mov     r8, [rsp+290h+var_268]; unsigned __int64
0x1800670f7  lea     r9, [rsp+290h+var_260]; void **
0x1800670fc  lea     edx, [r12+1]; unsigned int
0x180067101  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180067106  mov     r9d, dword ptr [rsp+290h+pszStart]
0x18006710b  mov     ebx, eax
0x18006710d  mov     r12, [rsp+290h+var_260]
0x180067112  test    ebx, ebx
0x180067114  js      loc_1800671CD
0x18006711a  mov     r14, rsi
0x18006711d  xor     edi, edi
0x18006711f  test    r14, r14
0x180067122  jz      short loc_180067193
0x180067124  cmp     edi, r9d
0x180067127  jnb     short loc_18006718F
0x180067129  mov     edx, 3Bh ; ';'; wMatch
0x18006712e  mov     rcx, r14; pszStart
0x180067131  call    cs:__imp_StrChrW
0x180067137  mov     r15, rax
0x18006713a  test    rax, rax
0x18006713d  jz      short loc_180067148
0x18006713f  xor     ecx, ecx
0x180067141  mov     [rax], cx
0x180067144  add     r15, 2
0x180067148  lea     rdx, pszTrimChars; " "
0x18006714f  mov     rcx, r14; psz
0x180067152  call    cs:__imp_StrTrimW
0x180067158  mov     rcx, r14; lpString
0x18006715b  call    cs:__imp_lstrlenW
0x180067161  test    eax, eax
0x180067163  jle     short loc_180067183
0x180067165  lea     r9, [r12+rdi*8]
0x180067169  mov     r8, r14
0x18006716c  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x180067171  mov     ebx, eax
0x180067173  test    eax, eax
0x180067175  js      short loc_180067183
0x180067177  mov     r9d, dword ptr [rsp+290h+pszStart]
0x18006717c  inc     edi
0x18006717e  mov     r14, r15
0x180067181  jmp     short loc_18006711F
0x180067183  mov     r9d, dword ptr [rsp+290h+pszStart]
0x180067188  mov     r14, r15
0x18006718b  test    ebx, ebx
0x18006718d  jns     short loc_18006711F
0x18006718f  test    ebx, ebx
0x180067191  js      short loc_1800671A8
0x180067193  test    edi, edi
0x180067195  jz      short loc_1800671A8
0x180067197  mov     word ptr [r13+0], 101Fh
0x18006719e  mov     [r13+8], edi
0x1800671a2  mov     [r13+10h], r12
0x1800671a6  jmp     short loc_1800671CD
0x1800671a8  mov     r14d, edi
0x1800671ab  xor     edi, edi
0x1800671ad  test    r14, r14
0x1800671b0  jz      short loc_1800671C4
0x1800671b2  mov     rcx, [r12+rdi*8]; pv
0x1800671b6  call    cs:__imp_CoTaskMemFree
0x1800671bc  inc     rdi
0x1800671bf  cmp     rdi, r14
0x1800671c2  jb      short loc_1800671B2
0x1800671c4  mov     rcx, r12; pv
0x1800671c7  call    cs:__imp_CoTaskMemFree
0x1800671cd  test    rsi, rsi
0x1800671d0  jz      short loc_1800671E5
0x1800671d2  lea     rax, [rsp+290h+var_250]
0x1800671d7  cmp     rsi, rax
0x1800671da  jz      short loc_1800671E5
0x1800671dc  mov     rcx, rsi; pv
0x1800671df  call    cs:__imp_CoTaskMemFree
0x1800671e5  mov     eax, ebx
0x1800671e7  mov     rcx, [rbp+190h+var_40]
0x1800671ee  xor     rcx, rsp; StackCookie
0x1800671f1  call    __security_check_cookie
0x1800671f6  mov     rbx, [rsp+290h+arg_10]
0x1800671fe  add     rsp, 260h
0x180067205  pop     r15
0x180067207  pop     r14
0x180067209  pop     r13
0x18006720b  pop     r12
0x18006720d  pop     rdi
0x18006720e  pop     rsi
0x18006720f  pop     rbp
0x180067210  retn
```
