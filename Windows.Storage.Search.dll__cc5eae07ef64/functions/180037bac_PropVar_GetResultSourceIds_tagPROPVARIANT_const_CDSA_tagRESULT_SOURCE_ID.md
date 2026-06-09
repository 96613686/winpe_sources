# PropVar_GetResultSourceIds(tagPROPVARIANT const &,CDSA<tagRESULT_SOURCE_ID> *)

- ea: `0x180037bac`
- end: `0x180037f07`
- name: `?PropVar_GetResultSourceIds@@YAJAEBUtagPROPVARIANT@@PEAV?$CDSA@UtagRESULT_SOURCE_ID@@@@@Z`
- size: `859`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037a28`
- `0x180037b24`

## callees

- `0x180037bac`
- `0x180042a50`
- `0x180044ae0`
- `0x1800490d0`
- `0x180063a68`
- `0x180071dc0`
- `0x18007a4e0`

## import_xrefs

- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180037d0c`
- `Windows.Storage!__imp_SHCLSIDFromString` at `0x180037d0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037e52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180037ce2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180037ce2`
- `PROPSYS!PropVariantGetElementCount` at `0x180037be2`
- `PROPSYS!PropVariantGetElementCount` at `0x180037be2`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180037cc3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180037cc3`

## pseudocode

```c
__int64 __fastcall PropVar_GetResultSourceIds(const PROPVARIANT *a1, struct _DSA **a2)
{
  const PROPVARIANT *v2; // rsi
  ULONG v3; // r14d
  struct _DSA *v4; // rbx
  HRESULT Element; // edi
  unsigned int v6; // r13d
  __int16 v7; // ax
  const WCHAR *v8; // rsi
  PWSTR v10; // rax
  PWSTR v11; // r12
  const WCHAR *v12; // r15
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rsi
  _WORD *v15; // rax
  _WORD *v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // r10
  _WORD *v19; // rcx
  __int64 v20; // r9
  void *v21; // rcx
  __int64 v22; // rsi
  bool v23; // cf
  const WCHAR *pv; // [rsp+20h] [rbp-50h] BYREF
  ULONG ElementCount; // [rsp+28h] [rbp-48h]
  LONG rgIndices[2]; // [rsp+30h] [rbp-40h] BYREF
  const PROPVARIANT *v27; // [rsp+38h] [rbp-38h]
  struct _DSA **v28; // [rsp+40h] [rbp-30h]
  CLSID pclsid; // [rsp+48h] [rbp-28h] BYREF
  _WORD *v30; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v28 = a2;
  *a2 = 0;
  v2 = a1;
  v27 = a1;
  ElementCount = PropVariantGetElementCount(a1);
  v3 = ElementCount;
  v4 = g_pfn_DSA_Create(24, ElementCount);
  if ( v4 )
  {
    Element = 0;
    v6 = 0;
    while ( 1 )
    {
      if ( v6 >= v3 )
      {
        *v28 = v4;
        return (unsigned int)Element;
      }
      v7 = *(_WORD *)v2 & 0xFFF;
      rgIndices[0] = v6;
      pv = 0;
      Element = -2147024809;
      if ( v7 != 31 && v7 != 8 )
        goto LABEL_44;
      if ( (*(_WORD *)v2 & 0x1000) != 0 )
        break;
      if ( (*(_WORD *)v2 & 0x2000) != 0 )
      {
        Element = SafeArrayGetElement(*((SAFEARRAY **)v2 + 1), rgIndices, &pv);
        if ( Element >= 0 )
        {
          v8 = pv;
LABEL_16:
          Element = -2147467259;
          v10 = StrChrW(v8, 0x2Eu);
          v11 = v10;
          if ( !v10 )
            goto LABEL_39;
          *v10 = 0;
          v30 = 0;
          pclsid = 0;
          Element = SHCLSIDFromString(v8, &pclsid);
          if ( Element < 0 )
            goto LABEL_42;
          v12 = v11 + 1;
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          v14 = v13 + 1;
          v30 = 0;
          if ( v13 + 1 >= v13 && (*(_QWORD *)rgIndices = 0, is_mul_ok(v14, 2u)) )
          {
            v15 = CoTaskMemAlloc(2 * v14);
            v30 = v15;
            v16 = v15;
            Element = v15 == 0 ? 0x8007000E : 0;
            if ( v15 )
            {
              if ( v14 <= 0x7FFFFFFF )
              {
                if ( v13 < 0x7FFFFFFF )
                {
                  if ( v11 == (PWSTR)-2LL )
                  {
                    v12 = &pszFormat;
                    v13 = 0;
                  }
                  if ( v14 )
                  {
                    v17 = v14;
                    v18 = 0;
                    do
                    {
                      if ( !v13 )
                        break;
                      if ( !*v12 )
                        break;
                      *v15++ = *v12++;
                      --v13;
                      ++v18;
                      --v17;
                    }
                    while ( v17 );
                    v19 = v15 - 1;
                    v20 = v18 - 1;
                    if ( v17 )
                    {
                      v19 = v15;
                      v20 = v18;
                    }
                    *v19 = 0;
                    if ( v17 )
                    {
                      v23 = v14 == v20;
                      v22 = v14 - v20;
                      if ( !v23 && v22 != 1 )
                        StringExHandleFillBehindNullW(&v16[v20], 2 * v22, 0x300u);
                    }
                  }
LABEL_35:
                  if ( DSA_InsertItem(v4, 0x7FFFFFFF, &pclsid) == -1 )
                  {
                    v21 = v30;
                    Element = -2147024882;
                  }
                  else
                  {
                    v21 = 0;
                    Element = 0;
                    v30 = 0;
                  }
                  CoTaskMemFree(v21);
LABEL_42:
                  *v11 = 46;
                  if ( Element >= 0 )
                  {
LABEL_43:
                    v2 = v27;
                    v3 = ElementCount;
                    goto LABEL_44;
                  }
LABEL_39:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xC1,
                    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
                    (const char *)(unsigned int)Element,
                    (int)pv);
                  goto LABEL_43;
                }
                if ( v13 == -1 )
                  goto LABEL_35;
              }
              *v15 = 0;
              goto LABEL_35;
            }
          }
          else
          {
            Element = -2147024362;
          }
          *v11 = 46;
          goto LABEL_39;
        }
      }
      else if ( (*(_WORD *)v2 & 0xF000) == 0 )
      {
        v8 = (const WCHAR *)*((_QWORD *)v2 + 1);
LABEL_9:
        pv = v8;
        goto LABEL_16;
      }
LABEL_44:
      ++v6;
      if ( Element < 0 )
      {
        g_pfn_DSA_DestroyCallback(v4, DSA_ClearResultSourceId, 0);
        goto LABEL_11;
      }
    }
    v8 = *(const WCHAR **)(*((_QWORD *)v2 + 2) + 8LL * v6);
    goto LABEL_9;
  }
  Element = -2147024882;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDB,
    (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
    (const char *)(unsigned int)Element,
    (int)pv);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x180037bac  mov     [rsp-38h+arg_10], rbx
0x180037bb1  push    rbp
0x180037bb2  push    rsi
0x180037bb3  push    rdi
0x180037bb4  push    r12
0x180037bb6  push    r13
0x180037bb8  push    r14
0x180037bba  push    r15
0x180037bbc  mov     rbp, rsp
0x180037bbf  sub     rsp, 70h
0x180037bc3  mov     rax, cs:__security_cookie
0x180037bca  xor     rax, rsp
0x180037bcd  mov     [rbp+var_10], rax
0x180037bd1  xor     r15d, r15d
0x180037bd4  mov     [rbp+var_30], rdx
0x180037bd8  mov     [rdx], r15
0x180037bdb  mov     rsi, rcx
0x180037bde  mov     [rbp+var_38], rcx
0x180037be2  call    cs:__imp_PropVariantGetElementCount
0x180037be8  mov     edx, eax; cItemGrow
0x180037bea  mov     [rbp+var_48], eax
0x180037bed  lea     ecx, [r15+18h]; cbItem
0x180037bf1  mov     r14d, eax
0x180037bf4  call    cs:g_pfn_DSA_Create
0x180037bfa  mov     rbx, rax
0x180037bfd  test    rax, rax
0x180037c00  jz      short loc_180037C67
0x180037c02  mov     edi, r15d
0x180037c05  lea     r12d, [r15+2Eh]
0x180037c09  mov     r13d, r15d
0x180037c0c  cmp     r13d, r14d
0x180037c0f  jnb     short loc_180037C86
0x180037c11  movzx   eax, word ptr [rsi]
0x180037c14  mov     ecx, 0FFFh
0x180037c19  and     ax, cx
0x180037c1c  mov     [rbp+rgIndices], r13d
0x180037c20  mov     ecx, 1Fh
0x180037c25  mov     [rbp+pv], r15
0x180037c29  mov     edi, 80070057h
0x180037c2e  cmp     cx, ax
0x180037c31  jnz     loc_180037ECC
0x180037c37  mov     eax, 1000h
0x180037c3c  test    [rsi], ax
0x180037c3f  jnz     loc_180037EBC
0x180037c45  mov     eax, 2000h
0x180037c4a  test    [rsi], ax
0x180037c4d  jnz     short loc_180037CB7
0x180037c4f  movzx   eax, word ptr [rsi]
0x180037c52  test    eax, 0FFFFF000h
0x180037c57  jnz     loc_180037E74
0x180037c5d  mov     rsi, [rsi+8]
0x180037c61  mov     [rbp+pv], rsi
0x180037c65  jmp     short loc_180037CD7
0x180037c67  mov     edi, 8007000Eh
0x180037c6c  mov     rcx, [rbp+38h]; this
0x180037c70  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180037c77  mov     r9d, edi; char *
0x180037c7a  mov     edx, 0DBh; void *
0x180037c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037c84  jmp     short loc_180037C91
0x180037c86  mov     rax, [rbp+var_30]
0x180037c8a  mov     [rax], rbx
0x180037c8d  test    edi, edi
0x180037c8f  js      short loc_180037C6C
0x180037c91  mov     eax, edi
0x180037c93  mov     rcx, [rbp+var_10]
0x180037c97  xor     rcx, rsp; StackCookie
0x180037c9a  call    __security_check_cookie
0x180037c9f  mov     rbx, [rsp+70h+arg_10]
0x180037ca7  add     rsp, 70h
0x180037cab  pop     r15
0x180037cad  pop     r14
0x180037caf  pop     r13
0x180037cb1  pop     r12
0x180037cb3  pop     rdi
0x180037cb4  pop     rsi
0x180037cb5  pop     rbp
0x180037cb6  retn
0x180037cb7  mov     rcx, [rsi+8]; psa
0x180037cbb  lea     r8, [rbp+pv]; pv
0x180037cbf  lea     rdx, [rbp+rgIndices]; rgIndices
0x180037cc3  call    cs:__imp_SafeArrayGetElement
0x180037cc9  mov     edi, eax
0x180037ccb  test    eax, eax
0x180037ccd  js      loc_180037E74
0x180037cd3  mov     rsi, [rbp+pv]
0x180037cd7  mov     edx, r12d; wMatch
0x180037cda  mov     rcx, rsi; pszStart
0x180037cdd  mov     edi, 80004005h
0x180037ce2  call    cs:__imp_StrChrW
0x180037ce8  mov     r12, rax
0x180037ceb  test    rax, rax
0x180037cee  jz      loc_180037E2B
0x180037cf4  mov     [rax], r15w
0x180037cf8  lea     rdx, [rbp+pclsid]; pclsid
0x180037cfc  xor     eax, eax
0x180037cfe  xorps   xmm0, xmm0
0x180037d01  mov     rcx, rsi; psz
0x180037d04  mov     [rbp+var_18], rax
0x180037d08  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180037d0c  call    cs:__imp_SHCLSIDFromString
0x180037d12  xor     r11d, r11d
0x180037d15  mov     edi, eax
0x180037d17  test    eax, eax
0x180037d19  js      loc_180037E58
0x180037d1f  lea     r15, [r12+2]
0x180037d24  or      r14, 0FFFFFFFFFFFFFFFFh
0x180037d28  inc     r14
0x180037d2b  cmp     [r15+r14*2], r11w
0x180037d30  jnz     short loc_180037D28
0x180037d32  lea     rsi, [r14+1]
0x180037d36  mov     [rbp+var_18], r11
0x180037d3a  cmp     rsi, r14
0x180037d3d  jb      loc_180037E1C
0x180037d43  mov     eax, 2
0x180037d48  mov     qword ptr [rbp+rgIndices], r11
0x180037d4c  mul     rsi
0x180037d4f  test    rdx, rdx
0x180037d52  jnz     loc_180037E1C
0x180037d58  mov     rcx, rax; cb
0x180037d5b  call    cs:__imp_CoTaskMemAlloc
0x180037d61  mov     rcx, rax
0x180037d64  mov     [rbp+var_18], rax
0x180037d68  neg     rcx
0x180037d6b  mov     r8, rax
0x180037d6e  sbb     edi, edi
0x180037d70  xor     r11d, r11d
0x180037d73  not     edi
0x180037d75  and     edi, 8007000Eh
0x180037d7b  test    rax, rax
0x180037d7e  jz      loc_180037E21
0x180037d84  test    rax, rax
0x180037d87  jz      loc_180037EDC
0x180037d8d  mov     ecx, 7FFFFFFFh
0x180037d92  cmp     rsi, rcx
0x180037d95  ja      loc_180037EEF
0x180037d9b  cmp     r14, rcx
0x180037d9e  jnb     loc_180037EE6
0x180037da4  test    r15, r15
0x180037da7  jz      loc_180037EF8
0x180037dad  test    rsi, rsi
0x180037db0  jz      short loc_180037DFA
0x180037db2  mov     rdx, rsi
0x180037db5  mov     r10, r11
0x180037db8  test    r14, r14
0x180037dbb  jz      short loc_180037DDD
0x180037dbd  movzx   ecx, word ptr [r15]
0x180037dc1  test    cx, cx
0x180037dc4  jz      short loc_180037DDD
0x180037dc6  mov     [rax], cx
0x180037dc9  add     r15, 2
0x180037dcd  add     rax, 2
0x180037dd1  dec     r14
0x180037dd4  inc     r10
0x180037dd7  sub     rdx, 1
0x180037ddb  jnz     short loc_180037DB8
0x180037ddd  test    rdx, rdx
0x180037de0  lea     rcx, [rax-2]
0x180037de4  lea     r9, [r10-1]
0x180037de8  cmovnz  rcx, rax
0x180037dec  cmovnz  r9, r10
0x180037df0  mov     [rcx], r11w
0x180037df4  jnz     loc_180037E97
0x180037dfa  lea     r8, [rbp+pclsid]; pitem
0x180037dfe  mov     edx, 7FFFFFFFh; i
0x180037e03  mov     rcx, rbx; hdsa
0x180037e06  call    cs:__imp_DSA_InsertItem
0x180037e0c  cmp     eax, 0FFFFFFFFh
0x180037e0f  jnz     short loc_180037E45
0x180037e11  mov     rcx, [rbp+var_18]
0x180037e15  mov     edi, 8007000Eh
0x180037e1a  jmp     short loc_180037E52
0x180037e1c  mov     edi, 80070216h
0x180037e21  mov     word ptr [r12], 2Eh ; '.'
0x180037e28  xor     r15d, r15d
0x180037e2b  mov     rcx, [rbp+38h]; this
0x180037e2f  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180037e36  mov     r9d, edi; char *
0x180037e39  mov     edx, 0C1h; void *
0x180037e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037e43  jmp     short loc_180037E66
0x180037e45  xor     r15d, r15d
0x180037e48  mov     ecx, r15d; pv
0x180037e4b  mov     edi, r15d
0x180037e4e  mov     [rbp+var_18], rcx
0x180037e52  call    cs:__imp_CoTaskMemFree
0x180037e58  mov     word ptr [r12], 2Eh ; '.'
0x180037e5f  test    edi, edi
0x180037e61  js      short loc_180037E28
0x180037e63  xor     r15d, r15d
0x180037e66  mov     rsi, [rbp+var_38]
0x180037e6a  mov     r12d, 2Eh ; '.'
0x180037e70  mov     r14d, [rbp+var_48]
0x180037e74  inc     r13d
0x180037e77  test    edi, edi
0x180037e79  jns     loc_180037C0C
0x180037e7f  xor     r8d, r8d; pData
0x180037e82  lea     rdx, ?DSA_ClearResultSourceId@@YAHPEAUtagRESULT_SOURCE_ID@@PEAX@Z; pfnCB
0x180037e89  mov     rcx, rbx; hdsa
0x180037e8c  call    cs:g_pfn_DSA_DestroyCallback
0x180037e92  jmp     loc_180037C6C
0x180037e97  sub     rsi, r9
0x180037e9a  cmp     rsi, 1
0x180037e9e  jbe     loc_180037DFA
0x180037ea4  lea     rcx, [r8+r9*2]; pszDestEnd
0x180037ea8  mov     r8d, 300h; dwFlags
0x180037eae  lea     rdx, [rsi+rsi]; cbRemaining
0x180037eb2  call    StringExHandleFillBehindNullW
0x180037eb7  jmp     loc_180037DFA
0x180037ebc  mov     rax, [rsi+10h]
0x180037ec0  mov     ecx, r13d
0x180037ec3  mov     rsi, [rax+rcx*8]
0x180037ec7  jmp     loc_180037C61
0x180037ecc  mov     ecx, 8
0x180037ed1  cmp     cx, ax
0x180037ed4  jz      loc_180037C37
0x180037eda  jmp     short loc_180037E74
0x180037edc  test    rsi, rsi
0x180037edf  jnz     short loc_180037EEF
0x180037ee1  jmp     loc_180037D8D
0x180037ee6  test    rsi, rsi
0x180037ee9  jz      loc_180037DFA
0x180037eef  mov     [rax], r11w
0x180037ef3  jmp     loc_180037DFA
0x180037ef8  lea     r15, pszFormat
0x180037eff  mov     r14, r11
0x180037f02  jmp     loc_180037DAD
```
