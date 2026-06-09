# _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)

- ea: `0x18007b090`
- end: `0x18007b299`
- name: `?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `521`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007db28`

## callees

- `0x1800182a0`
- `0x18002da80`
- `0x180040ae0`
- `0x180047660`
- `0x180071dc0`
- `0x18007b090`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b23e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b24f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b267`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b23e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b24f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b267`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x18007b1da`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x18007b1da`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18007b125`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18007b1b9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18007b125`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18007b1b9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007b0dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007b1e3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007b0dc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18007b1e3`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  unsigned __int16 *v2; // rsi
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
  unsigned __int16 v28[264]; // [rsp+40h] [rbp-C0h] BYREF

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
    v6 = _AllocString<CTCoAllocPolicy>(v5, 260, a1, &pszStart);
    v2 = (unsigned __int16 *)pszStart;
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
          if ( lstrlenW(v16) <= 0 || (v7 = _AllocString<CTCoAllocPolicy>(v21, v20, v16, &v12[8 * v17]), v7 < 0) )
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
0x18007b090  mov     [rsp-8+arg_10], rbx
0x18007b095  push    rbp
0x18007b096  push    rsi
0x18007b097  push    rdi
0x18007b098  push    r12
0x18007b09a  push    r13
0x18007b09c  push    r14
0x18007b09e  push    r15
0x18007b0a0  lea     rbp, [rsp-160h]
0x18007b0a8  sub     rsp, 260h
0x18007b0af  mov     rax, cs:__security_cookie
0x18007b0b6  xor     rax, rsp
0x18007b0b9  mov     [rbp+190h+var_40], rax
0x18007b0c0  xorps   xmm0, xmm0
0x18007b0c3  lea     rsi, [rsp+290h+var_250]
0x18007b0c8  xor     eax, eax
0x18007b0ca  mov     [rsp+290h+pszStart], rsi
0x18007b0cf  movups  xmmword ptr [rdx], xmm0
0x18007b0d2  mov     [rdx+10h], rax
0x18007b0d6  mov     r13, rdx
0x18007b0d9  mov     rbx, rcx
0x18007b0dc  call    cs:__imp_lstrlenW
0x18007b0e2  mov     edx, 104h; unsigned __int64
0x18007b0e7  mov     r8, rbx; unsigned __int16 *
0x18007b0ea  cmp     eax, edx
0x18007b0ec  jb      short loc_18007B0FF
0x18007b0ee  lea     r9, [rsp+290h+pszStart]
0x18007b0f3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18007b0f8  mov     rsi, [rsp+290h+pszStart]
0x18007b0fd  jmp     short loc_18007B109
0x18007b0ff  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x18007b104  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007b109  mov     ebx, eax
0x18007b10b  test    eax, eax
0x18007b10d  js      loc_18007B255
0x18007b113  xor     edi, edi
0x18007b115  mov     r8, rsi
0x18007b118  test    rsi, rsi
0x18007b11b  jz      short loc_18007B143
0x18007b11d  mov     edx, 3Bh ; ';'; wMatch
0x18007b122  mov     rcx, r8; pszStart
0x18007b125  call    cs:__imp_StrChrW
0x18007b12b  test    rax, rax
0x18007b12e  lea     ecx, [rdi+1]
0x18007b131  cmovz   ecx, edi
0x18007b134  lea     r8, [rax+2]
0x18007b138  mov     edi, ecx
0x18007b13a  cmovz   r8, rax
0x18007b13e  test    r8, r8
0x18007b141  jnz     short loc_18007B11D
0x18007b143  lea     r9d, [rdi+1]
0x18007b147  mov     dword ptr [rsp+290h+pszStart], r9d
0x18007b14c  test    r9d, r9d
0x18007b14f  jz      loc_18007B255
0x18007b155  xor     r12d, r12d
0x18007b158  mov     ecx, r9d; unsigned __int64
0x18007b15b  lea     r8, [rsp+290h+var_268]; unsigned __int64 *
0x18007b160  mov     [rsp+290h+var_260], r12
0x18007b165  mov     [rsp+290h+var_268], r12
0x18007b16a  lea     edx, [r12+8]; unsigned __int64
0x18007b16f  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18007b174  mov     ebx, eax
0x18007b176  test    eax, eax
0x18007b178  js      short loc_18007B19A
0x18007b17a  mov     r8, [rsp+290h+var_268]; unsigned __int64
0x18007b17f  lea     r9, [rsp+290h+var_260]; void **
0x18007b184  lea     edx, [r12+1]; unsigned int
0x18007b189  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18007b18e  mov     r9d, dword ptr [rsp+290h+pszStart]
0x18007b193  mov     ebx, eax
0x18007b195  mov     r12, [rsp+290h+var_260]
0x18007b19a  test    ebx, ebx
0x18007b19c  js      loc_18007B255
0x18007b1a2  mov     r14, rsi
0x18007b1a5  xor     edi, edi
0x18007b1a7  test    r14, r14
0x18007b1aa  jz      short loc_18007B21B
0x18007b1ac  cmp     edi, r9d
0x18007b1af  jnb     short loc_18007B217
0x18007b1b1  mov     edx, 3Bh ; ';'; wMatch
0x18007b1b6  mov     rcx, r14; pszStart
0x18007b1b9  call    cs:__imp_StrChrW
0x18007b1bf  mov     r15, rax
0x18007b1c2  test    rax, rax
0x18007b1c5  jz      short loc_18007B1D0
0x18007b1c7  xor     ecx, ecx
0x18007b1c9  mov     [rax], cx
0x18007b1cc  add     r15, 2
0x18007b1d0  lea     rdx, pszTrimChars; " "
0x18007b1d7  mov     rcx, r14; psz
0x18007b1da  call    cs:__imp_StrTrimW
0x18007b1e0  mov     rcx, r14; lpString
0x18007b1e3  call    cs:__imp_lstrlenW
0x18007b1e9  test    eax, eax
0x18007b1eb  jle     short loc_18007B20B
0x18007b1ed  lea     r9, [r12+rdi*8]
0x18007b1f1  mov     r8, r14
0x18007b1f4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18007b1f9  mov     ebx, eax
0x18007b1fb  test    eax, eax
0x18007b1fd  js      short loc_18007B20B
0x18007b1ff  mov     r9d, dword ptr [rsp+290h+pszStart]
0x18007b204  inc     edi
0x18007b206  mov     r14, r15
0x18007b209  jmp     short loc_18007B1A7
0x18007b20b  mov     r9d, dword ptr [rsp+290h+pszStart]
0x18007b210  mov     r14, r15
0x18007b213  test    ebx, ebx
0x18007b215  jns     short loc_18007B1A7
0x18007b217  test    ebx, ebx
0x18007b219  js      short loc_18007B230
0x18007b21b  test    edi, edi
0x18007b21d  jz      short loc_18007B230
0x18007b21f  mov     word ptr [r13+0], 101Fh
0x18007b226  mov     [r13+8], edi
0x18007b22a  mov     [r13+10h], r12
0x18007b22e  jmp     short loc_18007B255
0x18007b230  mov     r14d, edi
0x18007b233  xor     edi, edi
0x18007b235  test    r14, r14
0x18007b238  jz      short loc_18007B24C
0x18007b23a  mov     rcx, [r12+rdi*8]; pv
0x18007b23e  call    cs:__imp_CoTaskMemFree
0x18007b244  inc     rdi
0x18007b247  cmp     rdi, r14
0x18007b24a  jb      short loc_18007B23A
0x18007b24c  mov     rcx, r12; pv
0x18007b24f  call    cs:__imp_CoTaskMemFree
0x18007b255  test    rsi, rsi
0x18007b258  jz      short loc_18007B26D
0x18007b25a  lea     rax, [rsp+290h+var_250]
0x18007b25f  cmp     rsi, rax
0x18007b262  jz      short loc_18007B26D
0x18007b264  mov     rcx, rsi; pv
0x18007b267  call    cs:__imp_CoTaskMemFree
0x18007b26d  mov     eax, ebx
0x18007b26f  mov     rcx, [rbp+190h+var_40]
0x18007b276  xor     rcx, rsp; StackCookie
0x18007b279  call    __security_check_cookie
0x18007b27e  mov     rbx, [rsp+290h+arg_10]
0x18007b286  add     rsp, 260h
0x18007b28d  pop     r15
0x18007b28f  pop     r14
0x18007b291  pop     r13
0x18007b293  pop     r12
0x18007b295  pop     rdi
0x18007b296  pop     rsi
0x18007b297  pop     rbp
0x18007b298  retn
```
