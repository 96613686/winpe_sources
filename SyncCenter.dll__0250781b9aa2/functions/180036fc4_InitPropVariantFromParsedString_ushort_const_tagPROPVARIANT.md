# _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)

- ea: `0x180036fc4`
- end: `0x180037215`
- name: `?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `593`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800388e0`

## callees

- `0x180005660`
- `0x18001330c`
- `0x1800138cc`
- `0x1800150dc`
- `0x180036fc4`
- `0x180052950`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180037073`
- `SHLWAPI!StrChrW` at `0x180037110`
- `SHLWAPI!StrChrW` at `0x180037073`
- `SHLWAPI!StrChrW` at `0x180037110`
- `SHLWAPI!StrTrimW` at `0x180037132`
- `SHLWAPI!StrTrimW` at `0x180037132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800371e3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180037010`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003713b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180037010`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18003713b`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  unsigned __int16 *v2; // r14
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r9
  int v7; // eax
  int v8; // ebx
  int v9; // edi
  const WCHAR *v10; // r8
  PWSTR v11; // rax
  int v12; // ecx
  BYTE *v13; // r12
  void *v14; // rcx
  unsigned int v15; // r9d
  int v16; // eax
  WCHAR *v17; // rsi
  unsigned int v18; // edi
  PWSTR v19; // r15
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // rsi
  unsigned __int64 i; // rdi
  __int64 v25; // [rsp+20h] [rbp-E0h]
  PCWSTR pszStart; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  void *v28; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v29[264]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = v29;
  pszStart = v29;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  if ( (unsigned int)lstrlenW(a1) < 0x104 )
  {
    v7 = StringCchCopyW(v29, 0x104u, a1);
  }
  else
  {
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    v7 = _AllocStringWorker<CTCoAllocPolicy>(v5, 260, a1, v6, v25, (void **)&pszStart);
    v2 = (unsigned __int16 *)pszStart;
  }
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = 0;
    v10 = v2;
    while ( v10 )
    {
      v11 = StrChrW(v10, 0x3Bu);
      v12 = v9 + 1;
      if ( !v11 )
        v12 = v9;
      v10 = v11 + 1;
      v9 = v12;
      if ( !v11 )
        v10 = 0;
    }
    LODWORD(pszStart) = v9 + 1;
    if ( v9 != -1 )
    {
      v28 = 0;
      v13 = 0;
      v27 = 0;
      v8 = ULongLongMult((unsigned int)(v9 + 1), 8u, &v27);
      if ( v8 >= 0 )
      {
        v16 = CTCoAllocPolicy::Alloc(v14, 1u, v27, &v28);
        v15 = (unsigned int)pszStart;
        v8 = v16;
        v13 = (BYTE *)v28;
      }
      if ( v8 >= 0 )
      {
        v17 = v2;
        v18 = 0;
        while ( v17 )
        {
          if ( v18 >= v15 )
            goto LABEL_28;
          v19 = StrChrW(v17, 0x3Bu);
          if ( v19 )
            *v19++ = 0;
          StrTrimW(v17, L" ");
          if ( lstrlenW(v17) <= 0 )
            goto LABEL_27;
          v21 = -1;
          do
            ++v21;
          while ( v17[v21] );
          v8 = _AllocStringWorker<CTCoAllocPolicy>(
                 (unsigned __int64)&v13[8 * v18],
                 v20,
                 v17,
                 v21,
                 v25,
                 (void **)&v13[8 * v18]);
          if ( v8 < 0 )
          {
LABEL_27:
            v15 = (unsigned int)pszStart;
            v17 = v19;
            if ( v8 < 0 )
            {
LABEL_28:
              if ( v8 < 0 )
                goto LABEL_31;
              break;
            }
          }
          else
          {
            v15 = (unsigned int)pszStart;
            ++v18;
            v17 = v19;
          }
        }
        if ( v18 )
        {
          a2->vt = 4127;
          a2->lVal = v18;
          a2->bstrblobVal.pData = v13;
          goto LABEL_34;
        }
LABEL_31:
        v22 = v18;
        for ( i = 0; i < v22; ++i )
          CoTaskMemFree(*(LPVOID *)&v13[8 * i]);
        CoTaskMemFree(v13);
      }
    }
  }
LABEL_34:
  if ( v2 && v2 != v29 )
    CoTaskMemFree(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180036fc4  mov     [rsp-8+arg_10], rbx
0x180036fc9  push    rbp
0x180036fca  push    rsi
0x180036fcb  push    rdi
0x180036fcc  push    r12
0x180036fce  push    r13
0x180036fd0  push    r14
0x180036fd2  push    r15
0x180036fd4  lea     rbp, [rsp-170h]
0x180036fdc  sub     rsp, 270h
0x180036fe3  mov     rax, cs:__security_cookie
0x180036fea  xor     rax, rsp
0x180036fed  mov     [rbp+1A0h+var_40], rax
0x180036ff4  xorps   xmm0, xmm0
0x180036ff7  lea     r14, [rsp+2A0h+var_250]
0x180036ffc  xor     eax, eax
0x180036ffe  mov     [rsp+2A0h+pszStart], r14
0x180037003  movups  xmmword ptr [rdx], xmm0
0x180037006  mov     [rdx+10h], rax
0x18003700a  mov     r13, rdx
0x18003700d  mov     rbx, rcx
0x180037010  call    cs:__imp_lstrlenW
0x180037016  mov     edx, 104h; unsigned __int64
0x18003701b  xor     r15d, r15d
0x18003701e  cmp     eax, edx
0x180037020  jb      short loc_180037049
0x180037022  or      r9, 0FFFFFFFFFFFFFFFFh
0x180037026  inc     r9
0x180037029  cmp     [rbx+r9*2], r15w
0x18003702e  jnz     short loc_180037026
0x180037030  lea     rax, [rsp+2A0h+pszStart]
0x180037035  mov     r8, rbx
0x180037038  mov     [rsp+2A0h+var_278], rax
0x18003703d  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180037042  mov     r14, [rsp+2A0h+pszStart]
0x180037047  jmp     short loc_180037056
0x180037049  mov     r8, rbx; unsigned __int16 *
0x18003704c  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180037051  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180037056  mov     ebx, eax
0x180037058  test    eax, eax
0x18003705a  js      loc_1800371D1
0x180037060  mov     edi, r15d
0x180037063  mov     r8, r14
0x180037066  test    r14, r14
0x180037069  jz      short loc_180037091
0x18003706b  mov     edx, 3Bh ; ';'; wMatch
0x180037070  mov     rcx, r8; pszStart
0x180037073  call    cs:__imp_StrChrW
0x180037079  test    rax, rax
0x18003707c  lea     ecx, [rdi+1]
0x18003707f  cmovz   ecx, edi
0x180037082  lea     r8, [rax+2]
0x180037086  mov     edi, ecx
0x180037088  cmovz   r8, rax
0x18003708c  test    r8, r8
0x18003708f  jnz     short loc_18003706B
0x180037091  lea     r9d, [rdi+1]
0x180037095  mov     dword ptr [rsp+2A0h+pszStart], r9d
0x18003709a  test    r9d, r9d
0x18003709d  jz      loc_1800371D1
0x1800370a3  mov     ecx, r9d; unsigned __int64
0x1800370a6  lea     r8, [rsp+2A0h+var_268]; unsigned __int64 *
0x1800370ab  mov     edx, 8; unsigned __int64
0x1800370b0  mov     [rsp+2A0h+var_260], r15
0x1800370b5  mov     r12, r15
0x1800370b8  mov     [rsp+2A0h+var_268], r15
0x1800370bd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800370c2  mov     ebx, eax
0x1800370c4  test    eax, eax
0x1800370c6  js      short loc_1800370E8
0x1800370c8  mov     r8, [rsp+2A0h+var_268]; unsigned __int64
0x1800370cd  lea     r9, [rsp+2A0h+var_260]; void **
0x1800370d2  mov     edx, 1; unsigned int
0x1800370d7  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800370dc  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x1800370e1  mov     ebx, eax
0x1800370e3  mov     r12, [rsp+2A0h+var_260]
0x1800370e8  test    ebx, ebx
0x1800370ea  js      loc_1800371D1
0x1800370f0  mov     rsi, r14
0x1800370f3  mov     edi, r15d
0x1800370f6  test    rsi, rsi
0x1800370f9  jz      loc_180037197
0x1800370ff  cmp     edi, r9d
0x180037102  jnb     loc_180037193
0x180037108  mov     edx, 3Bh ; ';'; wMatch
0x18003710d  mov     rcx, rsi; pszStart
0x180037110  call    cs:__imp_StrChrW
0x180037116  mov     r15, rax
0x180037119  xor     eax, eax
0x18003711b  test    r15, r15
0x18003711e  jz      short loc_180037128
0x180037120  mov     [r15], ax
0x180037124  add     r15, 2
0x180037128  lea     rdx, pszTrimChars; " "
0x18003712f  mov     rcx, rsi; psz
0x180037132  call    cs:__imp_StrTrimW
0x180037138  mov     rcx, rsi; lpString
0x18003713b  call    cs:__imp_lstrlenW
0x180037141  xor     ecx, ecx
0x180037143  test    eax, eax
0x180037145  jle     short loc_180037180
0x180037147  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003714b  inc     r9
0x18003714e  cmp     [rsi+r9*2], cx
0x180037153  jnz     short loc_18003714B
0x180037155  mov     eax, edi
0x180037157  mov     r8, rsi
0x18003715a  lea     rcx, [r12+rax*8]
0x18003715e  mov     [rsp+2A0h+var_278], rcx
0x180037163  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180037168  mov     ebx, eax
0x18003716a  test    eax, eax
0x18003716c  js      short loc_180037180
0x18003716e  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x180037173  inc     edi
0x180037175  mov     rsi, r15
0x180037178  xor     r15d, r15d
0x18003717b  jmp     loc_1800370F6
0x180037180  mov     r9d, dword ptr [rsp+2A0h+pszStart]
0x180037185  mov     rsi, r15
0x180037188  xor     r15d, r15d
0x18003718b  test    ebx, ebx
0x18003718d  jns     loc_1800370F6
0x180037193  test    ebx, ebx
0x180037195  js      short loc_1800371AC
0x180037197  test    edi, edi
0x180037199  jz      short loc_1800371AC
0x18003719b  mov     word ptr [r13+0], 101Fh
0x1800371a2  mov     [r13+8], edi
0x1800371a6  mov     [r13+10h], r12
0x1800371aa  jmp     short loc_1800371D1
0x1800371ac  mov     esi, edi
0x1800371ae  mov     rdi, r15
0x1800371b1  test    rsi, rsi
0x1800371b4  jz      short loc_1800371C8
0x1800371b6  mov     rcx, [r12+rdi*8]; pv
0x1800371ba  call    cs:__imp_CoTaskMemFree
0x1800371c0  inc     rdi
0x1800371c3  cmp     rdi, rsi
0x1800371c6  jb      short loc_1800371B6
0x1800371c8  mov     rcx, r12; pv
0x1800371cb  call    cs:__imp_CoTaskMemFree
0x1800371d1  test    r14, r14
0x1800371d4  jz      short loc_1800371E9
0x1800371d6  lea     rax, [rsp+2A0h+var_250]
0x1800371db  cmp     r14, rax
0x1800371de  jz      short loc_1800371E9
0x1800371e0  mov     rcx, r14; pv
0x1800371e3  call    cs:__imp_CoTaskMemFree
0x1800371e9  mov     eax, ebx
0x1800371eb  mov     rcx, [rbp+1A0h+var_40]
0x1800371f2  xor     rcx, rsp; StackCookie
0x1800371f5  call    __security_check_cookie
0x1800371fa  mov     rbx, [rsp+2A0h+arg_10]
0x180037202  add     rsp, 270h
0x180037209  pop     r15
0x18003720b  pop     r14
0x18003720d  pop     r13
0x18003720f  pop     r12
0x180037211  pop     rdi
0x180037212  pop     rsi
0x180037213  pop     rbp
0x180037214  retn
```
