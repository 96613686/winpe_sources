# InternalInternetSyncGetProxyForUrlA(ulong,INTERNET_HANDLE_OBJECT *,CServerInfo *,char const *,char const *,ProxyResolveScheme,ushort,ProxyResolveScheme *,char * *,ushort *,int *)

- ea: `0x1800bf62c`
- end: `0x1800bfb95`
- name: `?InternalInternetSyncGetProxyForUrlA@@YAJKPEAVINTERNET_HANDLE_OBJECT@@PEAVCServerInfo@@PEBD2W4ProxyResolveScheme@@GPEAW43@PEAPEADPEAGPEAH@Z`
- size: `1385`
- prototype: `int __high(unsigned int, struct INTERNET_HANDLE_OBJECT *, struct CServerInfo *, const char *, const char *, enum ProxyResolveScheme, unsigned __int16, enum ProxyResolveScheme *, char **, unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18014416c`
- `0x18017a738`

## callees

- `0x1800701d0`
- `0x1800bf62c`
- `0x1800bfb9c`
- `0x1800c14f4`
- `0x1800da530`
- `0x1800ddce0`
- `0x1800e98c0`
- `0x18014b3b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf6fc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf75e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf7dc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf84a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf6fc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf75e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf7dc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800bf84a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bfa91`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bfa91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf90f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf90f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf930`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf950`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bf963`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf71e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf71e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf803`

## pseudocode

```c
__int64 __fastcall InternalInternetSyncGetProxyForUrlA(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        const CHAR *a4,
        __int64 a5,
        int a6,
        __int16 a7,
        _DWORD *a8,
        _QWORD *a9,
        _WORD *a10,
        _DWORD *a11)
{
  void *v11; // rdi
  void *v12; // r12
  HLOCAL v13; // r14
  WCHAR *v14; // r15
  const CHAR *v15; // rbx
  int v16; // eax
  int cchWideChar; // esi
  WCHAR *v18; // rbx
  WCHAR *v19; // rax
  WCHAR *lpWideCharStr; // r13
  signed int ProxyForUrlW; // r13d
  WCHAR *v22; // rcx
  LPWSTR v23; // rbx
  int v24; // eax
  int v25; // r13d
  LPWSTR v26; // rsi
  WCHAR *v27; // rax
  WCHAR *v28; // rcx
  _QWORD *v29; // rsi
  int LastError; // eax
  int v32; // eax
  signed int v33; // eax
  bool v34; // sf
  int v35; // eax
  LPWSTR v36; // [rsp+60h] [rbp-81h] BYREF
  void *v37; // [rsp+68h] [rbp-79h] BYREF
  WCHAR *v38; // [rsp+70h] [rbp-71h]
  LPCCH lpMultiByteStr; // [rsp+78h] [rbp-69h]
  __int64 v40; // [rsp+80h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-59h] BYREF
  unsigned int v42; // [rsp+90h] [rbp-51h]
  HLOCAL hMem; // [rsp+98h] [rbp-49h]
  void *v44; // [rsp+A0h] [rbp-41h] BYREF
  _QWORD *v45; // [rsp+A8h] [rbp-39h]
  _DWORD *v46; // [rsp+B0h] [rbp-31h]
  _WORD *v47; // [rsp+B8h] [rbp-29h]
  _DWORD *v48; // [rsp+C0h] [rbp-21h]
  __int64 v49; // [rsp+C8h] [rbp-19h]
  __int64 v50; // [rsp+D0h] [rbp-11h]

  v11 = 0;
  v12 = 0;
  v49 = a3;
  v13 = 0;
  v50 = a2;
  v14 = 0;
  v15 = a4;
  v42 = a1;
  lpMultiByteStr = a4;
  v48 = a8;
  v45 = a9;
  v47 = a10;
  v46 = a11;
  v44 = 0;
  pv = 0;
  hMem = 0;
  v40 = 0;
  if ( a8 )
    *a8 = -1;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a11 )
    *a11 = 0;
  if ( !a4 )
    goto LABEL_22;
  HIDWORD(v36) = 0;
  v38 = 0;
  if ( GlobalSafeToAssumeUTF8 )
  {
    HIDWORD(v37) = 0;
    v16 = MultiByteToWideChar(0xFDE9u, 0, a4, -1, 0, 0);
    cchWideChar = v16;
    if ( v16 )
    {
      v18 = 0;
      v37 = (void *)(unsigned int)(2 * v16);
      v36 = 0;
      v19 = (WCHAR *)CoTaskMemAlloc((unsigned int)v37);
      lpWideCharStr = v19;
      if ( v19 )
      {
        memset_0(v19, 0, (size_t)v37);
        v18 = lpWideCharStr;
        v36 = lpWideCharStr;
        if ( MultiByteToWideChar(0xFDE9u, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
        {
          v14 = lpWideCharStr;
          v38 = lpWideCharStr;
          v18 = 0;
          v36 = 0;
          ProxyForUrlW = 0;
        }
        else
        {
          LastError = WxGetLastError();
          ProxyForUrlW = LastError;
          if ( LastError > 0 )
            ProxyForUrlW = (unsigned __int16)LastError | 0x80070000;
          HIDWORD(v37) = 209;
          if ( ProxyForUrlW >= 0 )
            ProxyForUrlW = -2147418113;
        }
      }
      else
      {
        ProxyForUrlW = -2147024882;
        HIDWORD(v37) = 197;
      }
      if ( v18 )
        WxCoTaskAllocator::Free((void **)&v36);
      if ( ProxyForUrlW >= 0 )
        goto LABEL_18;
      v15 = lpMultiByteStr;
    }
    else
    {
      v33 = WxGetLastError();
      v34 = v33 < 0;
      if ( v33 > 0 )
      {
        v33 = (unsigned __int16)v33 | 0x80070000;
        v34 = v33 < 0;
      }
      HIDWORD(v37) = 182;
      if ( !v34 )
        v33 = -2147418113;
      LODWORD(v36) = v33;
    }
  }
  ProxyForUrlW = WxNewStringAtoWCchCp<WxCoTaskAllocator>(v15, -1, 0);
  if ( ProxyForUrlW >= 0 )
  {
    v14 = v38;
LABEL_18:
    v22 = 0;
    goto LABEL_19;
  }
  v22 = v38;
  v14 = 0;
  HIDWORD(v36) = 131;
LABEL_19:
  if ( v22 )
    CoTaskMemFree(v22);
  if ( ProxyForUrlW < 0 )
  {
    v23 = 0;
    HIDWORD(v40) = 163;
    goto LABEL_37;
  }
LABEL_22:
  v23 = 0;
  HIDWORD(lpMultiByteStr) = 0;
  v38 = 0;
  if ( GlobalSafeToAssumeUTF8 )
  {
    HIDWORD(v36) = 0;
    v24 = MultiByteToWideChar(0xFDE9u, 0, "/", -1, 0, 0);
    v25 = v24;
    if ( v24 )
    {
      v26 = 0;
      lpMultiByteStr = (LPCCH)(unsigned int)(2 * v24);
      v37 = 0;
      v27 = (WCHAR *)CoTaskMemAlloc((unsigned int)lpMultiByteStr);
      v36 = v27;
      if ( v27 )
      {
        memset_0(v27, 0, (size_t)lpMultiByteStr);
        v26 = v36;
        v37 = v36;
        if ( MultiByteToWideChar(0xFDE9u, 0, "/", -1, v36, v25) )
        {
          v23 = v26;
          v26 = 0;
          v37 = 0;
          ProxyForUrlW = 0;
          v38 = v23;
        }
        else
        {
          v32 = WxGetLastError();
          ProxyForUrlW = v32;
          if ( v32 > 0 )
            ProxyForUrlW = (unsigned __int16)v32 | 0x80070000;
          HIDWORD(v36) = 209;
          if ( ProxyForUrlW >= 0 )
            ProxyForUrlW = -2147418113;
        }
      }
      else
      {
        v36 = (LPWSTR)0xC500000000LL;
        HIDWORD(lpMultiByteStr) = 76;
        ProxyForUrlW = -2147024882;
      }
      if ( v26 )
        WxCoTaskAllocator::Free(&v37);
      if ( ProxyForUrlW >= 0 )
        goto LABEL_30;
    }
    else
    {
      WxGetLastError();
      HIDWORD(v36) = 182;
    }
  }
  ProxyForUrlW = WxNewStringAtoWCchCp<WxCoTaskAllocator>("/", -1, 0);
  if ( ProxyForUrlW >= 0 )
  {
    v23 = v38;
LABEL_30:
    v28 = 0;
    goto LABEL_31;
  }
  v28 = v38;
  v23 = 0;
  HIDWORD(lpMultiByteStr) = 131;
LABEL_31:
  if ( v28 )
    CoTaskMemFree(v28);
  if ( ProxyForUrlW < 0 )
  {
    HIDWORD(v40) = 170;
  }
  else
  {
    v29 = v45;
    ProxyForUrlW = InternalInternetSyncGetProxyForUrlW(
                     v42,
                     v50,
                     v49,
                     v14,
                     v23,
                     a6,
                     a7,
                     v48,
                     (unsigned __int64)&pv & -(__int64)(v45 != 0),
                     v47,
                     v46);
    if ( ProxyForUrlW < 0 )
    {
      HIDWORD(v40) = 192;
      goto LABEL_36;
    }
    if ( !v29 )
    {
LABEL_36:
      v11 = pv;
      goto LABEL_37;
    }
    v11 = pv;
    if ( pv )
    {
      v35 = HostWCharToCharEx((LPCWSTR)pv, -1, (__int64)&v40);
      ProxyForUrlW = v35;
      if ( v35 > 0 )
        ProxyForUrlW = (unsigned __int16)v35 | 0x80070000;
      v13 = hMem;
      if ( ProxyForUrlW >= 0 )
      {
        ProxyForUrlW = WxNewStringA<WxCoTaskAllocator>(hMem, &v44);
        if ( ProxyForUrlW >= 0 )
        {
          *v29 = v44;
        }
        else
        {
          v12 = v44;
          HIDWORD(v40) = 205;
        }
      }
      else
      {
        HIDWORD(v40) = 203;
      }
    }
    if ( v13 )
      LocalFree(v13);
  }
LABEL_37:
  if ( v11 )
    CoTaskMemFree(v11);
  if ( v12 )
    CoTaskMemFree(v12);
  if ( v23 )
    CoTaskMemFree(v23);
  if ( v14 )
    CoTaskMemFree(v14);
  return (unsigned int)ProxyForUrlW;
}

```

## disassembly

```asm
0x1800bf62c  push    rbp
0x1800bf62e  push    rbx
0x1800bf62f  push    rsi
0x1800bf630  push    rdi
0x1800bf631  push    r12
0x1800bf633  push    r13
0x1800bf635  push    r14
0x1800bf637  push    r15
0x1800bf639  lea     rbp, [rsp-7]
0x1800bf63e  sub     rsp, 0E8h
0x1800bf645  mov     rax, [rbp+3Fh+arg_40]
0x1800bf64c  xor     edi, edi
0x1800bf64e  xor     r12d, r12d
0x1800bf651  mov     [rbp+3Fh+var_58], r8
0x1800bf655  mov     r8, [rbp+3Fh+arg_38]
0x1800bf65c  xor     r14d, r14d
0x1800bf65f  mov     [rbp+3Fh+var_50], rdx
0x1800bf663  xor     r15d, r15d
0x1800bf666  mov     rdx, [rbp+3Fh+arg_48]
0x1800bf66d  mov     rbx, r9
0x1800bf670  mov     [rbp+3Fh+var_90], ecx
0x1800bf673  mov     rcx, [rbp+3Fh+arg_50]
0x1800bf67a  mov     [rbp+3Fh+lpMultiByteStr], rbx
0x1800bf67e  mov     [rbp+3Fh+var_60], r8
0x1800bf682  mov     [rbp+3Fh+var_78], rax
0x1800bf686  mov     [rbp+3Fh+var_68], rdx
0x1800bf68a  mov     [rbp+3Fh+var_70], rcx
0x1800bf68e  mov     dword ptr [rbp+3Fh+var_A0+4], 0
0x1800bf695  mov     [rbp+3Fh+var_80], r12
0x1800bf699  mov     [rbp+3Fh+pv], rdi
0x1800bf69d  mov     [rbp+3Fh+hMem], r14
0x1800bf6a1  mov     dword ptr [rbp+3Fh+var_A0], edi
0x1800bf6a4  test    r8, r8
0x1800bf6a7  jnz     loc_1800BFAE2
0x1800bf6ad  test    rax, rax
0x1800bf6b0  jnz     loc_1800BFAEE
0x1800bf6b6  test    rdx, rdx
0x1800bf6b9  jnz     loc_1800BFAF6
0x1800bf6bf  test    rcx, rcx
0x1800bf6c2  jz      short loc_1800BF6C6
0x1800bf6c4  mov     [rcx], edi
0x1800bf6c6  test    rbx, rbx
0x1800bf6c9  jz      loc_1800BF7A9
0x1800bf6cf  cmp     cs:GlobalSafeToAssumeUTF8, edi
0x1800bf6d5  mov     dword ptr [rbp+3Fh+var_C0+4], edi
0x1800bf6d8  mov     [rbp+3Fh+var_B0], r15
0x1800bf6dc  jz      loc_1800BF9FE
0x1800bf6e2  mov     [rsp+120h+cchWideChar], edi; cchWideChar
0x1800bf6e6  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800bf6ea  mov     r8, rbx; lpMultiByteStr
0x1800bf6ed  mov     [rsp+120h+lpWideCharStr], rdi; lpWideCharStr
0x1800bf6f2  xor     edx, edx; dwFlags
0x1800bf6f4  mov     dword ptr [rbp+3Fh+var_B8+4], edi
0x1800bf6f7  mov     ecx, 0FDE9h; CodePage
0x1800bf6fc  call    cs:__imp_MultiByteToWideChar
0x1800bf702  mov     esi, eax
0x1800bf704  test    eax, eax
0x1800bf706  jz      loc_1800BFA5A
0x1800bf70c  add     eax, eax
0x1800bf70e  mov     dword ptr [rbp+3Fh+var_B8+4], edi
0x1800bf711  xor     ebx, ebx
0x1800bf713  mov     [rbp-79h], rax
0x1800bf717  mov     ecx, eax; cb
0x1800bf719  mov     [rsp+60h], rbx
0x1800bf71e  call    cs:__imp_CoTaskMemAlloc
0x1800bf724  mov     r13, rax
0x1800bf727  test    rax, rax
0x1800bf72a  jz      loc_1800BF96E
0x1800bf730  mov     r8, [rbp-79h]; Size
0x1800bf734  xor     edx, edx; Val
0x1800bf736  mov     rcx, rax; void *
0x1800bf739  call    memset_0
0x1800bf73e  mov     rbx, r13
0x1800bf741  mov     [rsp+60h], rbx
0x1800bf746  mov     r8, [rbp+3Fh+lpMultiByteStr]; lpMultiByteStr
0x1800bf74a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800bf74e  mov     [rsp+120h+cchWideChar], esi; cchWideChar
0x1800bf752  xor     edx, edx; dwFlags
0x1800bf754  mov     ecx, 0FDE9h; CodePage
0x1800bf759  mov     [rsp+120h+lpWideCharStr], rbx; lpWideCharStr
0x1800bf75e  call    cs:__imp_MultiByteToWideChar
0x1800bf764  test    eax, eax
0x1800bf766  jz      loc_1800BF9A0
0x1800bf76c  mov     r15, rbx
0x1800bf76f  mov     [rbp+3Fh+var_B0], rbx
0x1800bf773  xor     ebx, ebx
0x1800bf775  mov     [rsp+60h], rbx
0x1800bf77a  xor     r13d, r13d
0x1800bf77d  test    rbx, rbx
0x1800bf780  jz      short loc_1800BF78C
0x1800bf782  lea     rcx, [rsp+120h+var_C0]; void **
0x1800bf787  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800bf78c  test    r13d, r13d
0x1800bf78f  js      loc_1800BFB00
0x1800bf795  xor     ecx, ecx; pv
0x1800bf797  test    rcx, rcx
0x1800bf79a  jnz     loc_1800BF958
0x1800bf7a0  test    r13d, r13d
0x1800bf7a3  js      loc_1800BFB1C
0x1800bf7a9  xor     ebx, ebx
0x1800bf7ab  mov     dword ptr [rbp+3Fh+lpMultiByteStr+4], edi
0x1800bf7ae  cmp     cs:GlobalSafeToAssumeUTF8, ebx
0x1800bf7b4  mov     [rbp+3Fh+var_B0], rbx
0x1800bf7b8  jz      loc_1800BFA30
0x1800bf7be  mov     [rsp+120h+cchWideChar], ebx; cchWideChar
0x1800bf7c2  lea     r8, MultiByteStr; "/"
0x1800bf7c9  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800bf7cd  mov     [rsp+120h+lpWideCharStr], rbx; lpWideCharStr
0x1800bf7d2  xor     edx, edx; dwFlags
0x1800bf7d4  mov     dword ptr [rbp+3Fh+var_C0+4], ebx
0x1800bf7d7  mov     ecx, 0FDE9h; CodePage
0x1800bf7dc  call    cs:__imp_MultiByteToWideChar
0x1800bf7e2  mov     r13d, eax
0x1800bf7e5  test    eax, eax
0x1800bf7e7  jz      loc_1800BFA24
0x1800bf7ed  lea     eax, ds:0[rax*2]
0x1800bf7f4  mov     dword ptr [rbp+3Fh+lpMultiByteStr+4], ebx
0x1800bf7f7  xor     esi, esi
0x1800bf7f9  mov     [rbp+3Fh+lpMultiByteStr], rax
0x1800bf7fd  mov     ecx, eax; cb
0x1800bf7ff  mov     [rbp-79h], rsi
0x1800bf803  call    cs:__imp_CoTaskMemAlloc
0x1800bf809  mov     [rsp+120h+var_C0], rax
0x1800bf80e  test    rax, rax
0x1800bf811  jz      loc_1800BF987
0x1800bf817  mov     r8, [rbp+3Fh+lpMultiByteStr]; Size
0x1800bf81b  xor     edx, edx; Val
0x1800bf81d  mov     rcx, rax; void *
0x1800bf820  call    memset_0
0x1800bf825  mov     rsi, [rsp+120h+var_C0]
0x1800bf82a  mov     [rbp-79h], rsi
0x1800bf82e  mov     [rsp+120h+cchWideChar], r13d; cchWideChar
0x1800bf833  lea     r8, MultiByteStr; "/"
0x1800bf83a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800bf83e  mov     [rsp+120h+lpWideCharStr], rsi; lpWideCharStr
0x1800bf843  xor     edx, edx; dwFlags
0x1800bf845  mov     ecx, 0FDE9h; CodePage
0x1800bf84a  call    cs:__imp_MultiByteToWideChar
0x1800bf850  test    eax, eax
0x1800bf852  jz      loc_1800BF9CF
0x1800bf858  mov     rbx, rsi
0x1800bf85b  xor     esi, esi
0x1800bf85d  mov     [rbp-79h], rsi
0x1800bf861  xor     r13d, r13d
0x1800bf864  mov     [rbp+3Fh+var_B0], rbx
0x1800bf868  test    rsi, rsi
0x1800bf86b  jz      short loc_1800BF876
0x1800bf86d  lea     rcx, [rbp+3Fh+var_B8]; void **
0x1800bf871  call    ?Free@WxCoTaskAllocator@@SAXPEAPEAX@Z; WxCoTaskAllocator::Free(void * *)
0x1800bf876  test    r13d, r13d
0x1800bf879  js      loc_1800BFA30
0x1800bf87f  xor     ecx, ecx; pv
0x1800bf881  test    rcx, rcx
0x1800bf884  jnz     loc_1800BF963
0x1800bf88a  test    r13d, r13d
0x1800bf88d  js      loc_1800BFB3C
0x1800bf893  mov     rsi, [rbp+3Fh+var_78]
0x1800bf897  mov     r8, [rbp+3Fh+var_58]
0x1800bf89b  mov     rax, rsi
0x1800bf89e  mov     rdx, [rbp+3Fh+var_50]
0x1800bf8a2  neg     rax
0x1800bf8a5  mov     ecx, [rbp+3Fh+var_90]
0x1800bf8a8  lea     rax, [rbp+3Fh+pv]
0x1800bf8ac  sbb     r9, r9
0x1800bf8af  and     r9, rax
0x1800bf8b2  mov     rax, [rbp+3Fh+var_70]
0x1800bf8b6  mov     [rsp+120h+var_D0], rax
0x1800bf8bb  mov     rax, [rbp+3Fh+var_68]
0x1800bf8bf  mov     [rsp+120h+var_D8], rax
0x1800bf8c4  mov     rax, [rbp+3Fh+var_60]
0x1800bf8c8  mov     [rsp+120h+var_E0], r9
0x1800bf8cd  mov     r9, r15
0x1800bf8d0  mov     [rsp+120h+var_E8], rax
0x1800bf8d5  movzx   eax, [rbp+3Fh+arg_30]
0x1800bf8d9  mov     [rsp+120h+var_F0], ax
0x1800bf8de  mov     eax, [rbp+3Fh+arg_28]
0x1800bf8e1  mov     [rsp+120h+cchWideChar], eax
0x1800bf8e5  mov     [rsp+120h+lpWideCharStr], rbx
0x1800bf8ea  call    ?InternalInternetSyncGetProxyForUrlW@@YAJKPEAVINTERNET_HANDLE_OBJECT@@PEAVCServerInfo@@PEBG2W4ProxyResolveScheme@@GPEAW43@PEAPEAGPEAGPEAH@Z; InternalInternetSyncGetProxyForUrlW(ulong,INTERNET_HANDLE_OBJECT *,CServerInfo *,ushort const *,ushort const *,ProxyResolveScheme,ushort,ProxyResolveScheme *,ushort * *,ushort *,int *)
0x1800bf8ef  mov     r13d, eax
0x1800bf8f2  test    eax, eax
0x1800bf8f4  js      loc_1800BFB48
0x1800bf8fa  test    rsi, rsi
0x1800bf8fd  jnz     loc_1800BFB54
0x1800bf903  mov     rdi, [rbp+3Fh+pv]
0x1800bf907  test    rdi, rdi
0x1800bf90a  jz      short loc_1800BF915
0x1800bf90c  mov     rcx, rdi; pv
0x1800bf90f  call    cs:__imp_CoTaskMemFree
0x1800bf915  test    r12, r12
0x1800bf918  jnz     short loc_1800BF94D
0x1800bf91a  test    rbx, rbx
0x1800bf91d  jz      short loc_1800BF928
0x1800bf91f  mov     rcx, rbx; pv
0x1800bf922  call    cs:__imp_CoTaskMemFree
0x1800bf928  test    r15, r15
0x1800bf92b  jz      short loc_1800BF936
0x1800bf92d  mov     rcx, r15; pv
0x1800bf930  call    cs:__imp_CoTaskMemFree
0x1800bf936  mov     eax, r13d
0x1800bf939  add     rsp, 0E8h
0x1800bf940  pop     r15
0x1800bf942  pop     r14
0x1800bf944  pop     r13
0x1800bf946  pop     r12
0x1800bf948  pop     rdi
0x1800bf949  pop     rsi
0x1800bf94a  pop     rbx
0x1800bf94b  pop     rbp
0x1800bf94c  retn
0x1800bf94d  mov     rcx, r12; pv
0x1800bf950  call    cs:__imp_CoTaskMemFree
0x1800bf956  jmp     short loc_1800BF91A
0x1800bf958  call    cs:__imp_CoTaskMemFree
0x1800bf95e  jmp     loc_1800BF7A0
0x1800bf963  call    cs:__imp_CoTaskMemFree
0x1800bf969  jmp     loc_1800BF88A
0x1800bf96e  mov     dword ptr [rbp+3Fh+var_B8+4], 4Ch ; 'L'
0x1800bf975  mov     r13d, 8007000Eh
0x1800bf97b  mov     dword ptr [rbp+3Fh+var_B8+4], 0C5h
0x1800bf982  jmp     loc_1800BF77D
0x1800bf987  mov     dword ptr [rbp+3Fh+lpMultiByteStr+4], 4Ch ; 'L'
0x1800bf98e  mov     r13d, 8007000Eh
0x1800bf994  mov     dword ptr [rbp+3Fh+var_C0+4], 0C5h
0x1800bf99b  jmp     loc_1800BF868
0x1800bf9a0  call    WxGetLastError
0x1800bf9a5  mov     r13d, eax
0x1800bf9a8  test    eax, eax
0x1800bf9aa  jle     short loc_1800BF9B7
0x1800bf9ac  movzx   r13d, ax
0x1800bf9b0  or      r13d, 80070000h
0x1800bf9b7  test    r13d, r13d
0x1800bf9ba  mov     dword ptr [rbp+3Fh+var_B8+4], 0D1h
0x1800bf9c1  mov     esi, 8000FFFFh
0x1800bf9c6  cmovns  r13d, esi
0x1800bf9ca  jmp     loc_1800BF77D
0x1800bf9cf  call    WxGetLastError
0x1800bf9d4  mov     r13d, eax
0x1800bf9d7  test    eax, eax
0x1800bf9d9  jle     short loc_1800BF9E6
0x1800bf9db  movzx   r13d, ax
0x1800bf9df  or      r13d, 80070000h
0x1800bf9e6  test    r13d, r13d
0x1800bf9e9  mov     dword ptr [rbp+3Fh+var_C0+4], 0D1h
0x1800bf9f0  mov     eax, 8000FFFFh
0x1800bf9f5  cmovns  r13d, eax
0x1800bf9f9  jmp     loc_1800BF868
0x1800bf9fe  lea     r9, [rbp+3Fh+var_B0]
0x1800bfa02  xor     r8d, r8d; CodePage
0x1800bfa05  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800bfa08  mov     rcx, rbx; lpMultiByteStr
0x1800bfa0b  call    ??$WxNewStringAtoWCchCp@VWxCoTaskAllocator@@@@YAJPEBDKKPEAPEAG@Z; WxNewStringAtoWCchCp<WxCoTaskAllocator>(char const *,ulong,ulong,ushort * *)
0x1800bfa10  mov     r13d, eax
0x1800bfa13  test    eax, eax
0x1800bfa15  js      loc_1800BFB09
0x1800bfa1b  mov     r15, [rbp+3Fh+var_B0]
0x1800bfa1f  jmp     loc_1800BF795
0x1800bfa24  call    WxGetLastError
0x1800bfa29  mov     dword ptr [rbp+3Fh+var_C0+4], 0B6h
0x1800bfa30  lea     r9, [rbp+3Fh+var_B0]
0x1800bfa34  xor     r8d, r8d; CodePage
0x1800bfa37  or      edx, 0FFFFFFFFh; cbMultiByte
0x1800bfa3a  lea     rcx, MultiByteStr; "/"
0x1800bfa41  call    ??$WxNewStringAtoWCchCp@VWxCoTaskAllocator@@@@YAJPEBDKKPEAPEAG@Z; WxNewStringAtoWCchCp<WxCoTaskAllocator>(char const *,ulong,ulong,ushort * *)
0x1800bfa46  mov     r13d, eax
0x1800bfa49  test    eax, eax
0x1800bfa4b  js      loc_1800BFB2A
0x1800bfa51  mov     rbx, [rbp+3Fh+var_B0]
0x1800bfa55  jmp     loc_1800BF87F
0x1800bfa5a  call    WxGetLastError
0x1800bfa5f  test    eax, eax
0x1800bfa61  jle     short loc_1800BFA6D
0x1800bfa63  movzx   eax, ax
0x1800bfa66  or      eax, 80070000h
0x1800bfa6b  test    eax, eax
0x1800bfa6d  mov     esi, 8000FFFFh
0x1800bfa72  mov     dword ptr [rbp+3Fh+var_B8+4], 0B6h
0x1800bfa79  cmovns  eax, esi
0x1800bfa7c  mov     dword ptr [rsp+120h+var_C0], eax
0x1800bfa80  jmp     loc_1800BF9FE
0x1800bfa85  test    r14, r14
0x1800bfa88  jz      loc_1800BF907
0x1800bfa8e  mov     rcx, r14; hMem
0x1800bfa91  call    cs:__imp_LocalFree
0x1800bfa97  jmp     loc_1800BF907
0x1800bfa9c  lea     rax, [rbp+3Fh+var_A0]
0x1800bfaa0  mov     r8d, 1
0x1800bfaa6  lea     r9, [rbp+3Fh+hMem]
0x1800bfaaa  mov     [rsp+120h+lpWideCharStr], rax; __int64
0x1800bfaaf  or      edx, 0FFFFFFFFh; cchUnicodeChar
0x1800bfab2  mov     rcx, rdi; lpUnicodeCharStr
0x1800bfab5  call    HostWCharToCharEx
0x1800bfaba  mov     r13d, eax
0x1800bfabd  test    eax, eax
0x1800bfabf  jle     short loc_1800BFACC
0x1800bfac1  movzx   r13d, ax
0x1800bfac5  or      r13d, 80070000h
0x1800bfacc  mov     r14, [rbp+3Fh+hMem]
0x1800bfad0  test    r13d, r13d
0x1800bfad3  jns     loc_1800BFB66
  ... truncated ...
```
