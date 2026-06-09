# EURL::RewriteUrlIfExtensionless(_HTTP_FILTER_CONTEXT *,_HTTP_FILTER_PREPROC_HEADERS *,char * *,ulong,int *)

- ea: `0x18000291c`
- end: `0x180002dbc`
- name: `?RewriteUrlIfExtensionless@EURL@@SAKPEAU_HTTP_FILTER_CONTEXT@@PEAU_HTTP_FILTER_PREPROC_HEADERS@@PEAPEADKPEAH@Z`
- size: `1184`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, struct _HTTP_FILTER_PREPROC_HEADERS *, LPCSTR *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001ba0`

## callees

- `0x180001ee8`
- `0x18000291c`
- `0x180003950`
- `0x1800042fc`
- `0x180004302`
- `0x180004320`
- `0x1800043b0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x180002bb6`
- `KERNEL32!lstrlenA` at `0x180002bdf`
- `KERNEL32!lstrlenA` at `0x180002bb6`
- `KERNEL32!lstrlenA` at `0x180002bdf`
- `KERNEL32!SetLastError` at `0x180002d87`
- `KERNEL32!SetLastError` at `0x180002d87`
- `KERNEL32!GetLastError` at `0x1800029aa`
- `KERNEL32!GetLastError` at `0x180002a5e`
- `KERNEL32!GetLastError` at `0x180002af0`
- `KERNEL32!GetLastError` at `0x180002b67`
- `KERNEL32!GetLastError` at `0x1800029aa`
- `KERNEL32!GetLastError` at `0x180002a5e`
- `KERNEL32!GetLastError` at `0x180002af0`
- `KERNEL32!GetLastError` at `0x180002b67`
- `ucrtbase_clr0400!toupper` at `0x180002ab4`
- `ucrtbase_clr0400!toupper` at `0x180002ab4`

## string_xrefs

- `0x180002b4f`: `Lock-Token:`
- `0x180002b9a`: `Lock-Token:`

## pseudocode

```c
__int64 __fastcall EURL::RewriteUrlIfExtensionless(
        struct _HTTP_FILTER_CONTEXT *a1,
        struct _HTTP_FILTER_PREPROC_HEADERS *a2,
        LPCSTR *a3,
        unsigned int a4,
        int *a5)
{
  char *v5; // rbx
  unsigned int v6; // r15d
  __int64 v10; // r12
  int v11; // edi
  BOOL (__stdcall *GetHeader)(struct _HTTP_FILTER_CONTEXT *, LPSTR, LPVOID, LPDWORD); // rax
  __int64 v13; // rax
  BOOL (__stdcall *v14)(struct _HTTP_FILTER_CONTEXT *, LPSTR, LPVOID, LPDWORD); // rax
  __int64 v15; // rax
  BOOL (__stdcall *v16)(struct _HTTP_FILTER_CONTEXT *, LPSTR, LPVOID, LPDWORD); // rax
  __int64 v17; // rax
  BOOL (__stdcall *v18)(struct _HTTP_FILTER_CONTEXT *, LPSTR, LPVOID, LPDWORD); // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rbx
  char *v22; // rax
  const CHAR *v23; // rdi
  LPCSTR v24; // r8
  __int64 v25; // rdx
  int v26; // ecx
  int v27; // ecx
  __int64 v28; // rcx
  CHAR v29; // r12
  DWORD v30; // ecx
  unsigned int v31; // edx
  const CHAR *v32; // rdx
  CHAR *v33; // rbx
  char *v34; // rcx
  char *BufferFromFilterContext; // rax
  char *v36; // r14
  __int64 v37; // rbx
  char *v38; // rax
  char *v39; // rbx
  char *v40; // rsi
  unsigned int v42; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v43; // [rsp+34h] [rbp-CCh]
  size_t Size; // [rsp+38h] [rbp-C8h]
  int *v45; // [rsp+40h] [rbp-C0h]
  char Str2[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = Str2;
  v6 = 0;
  v43 = a4;
  v45 = a5;
  v10 = 0;
  v11 = 1024;
  if ( !a3 || !*a3 )
    goto LABEL_64;
  GetHeader = a2->GetHeader;
  v42 = 1024;
  if ( !((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *, unsigned int *))GetHeader)(
          a1,
          "method",
          Str2,
          &v42) )
  {
    if ( GetLastError() != 122 )
      return 134217730;
    v11 = v42;
    v13 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, v42, 0);
    v5 = (char *)v13;
    if ( !v13 )
      goto LABEL_54;
    if ( !((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, unsigned int *))a2->GetHeader)(
            a1,
            "method",
            v13,
            &v42) )
      return 134217730;
  }
  if ( strcmp_0("GET", v5) && strcmp_0("POST", v5) && strcmp_0("HEAD", v5) )
    return 134217730;
  v14 = a2->GetHeader;
  v42 = v11;
  if ( ((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *, unsigned int *))v14)(
         a1,
         "Translate:",
         v5,
         &v42) )
  {
    goto LABEL_16;
  }
  if ( GetLastError() == 122 )
  {
    v11 = v42;
    v15 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, v42, 0);
    v5 = (char *)v15;
    if ( !v15 )
      goto LABEL_54;
    if ( ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, unsigned int *))a2->GetHeader)(
           a1,
           "Translate:",
           v15,
           &v42) )
    {
LABEL_16:
      if ( v42 && toupper(*v5) == 70 && !v5[1] )
        return 134217730;
    }
  }
  v16 = a2->GetHeader;
  v42 = v11;
  if ( ((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *, unsigned int *))v16)(
         a1,
         "If:",
         v5,
         &v42) )
  {
    return 134217730;
  }
  if ( GetLastError() == 122 )
  {
    v11 = v42;
    v17 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, v42, 0);
    v5 = (char *)v17;
    if ( !v17 )
      goto LABEL_54;
    if ( ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, unsigned int *))a2->GetHeader)(
           a1,
           "If:",
           v17,
           &v42) )
    {
      return 134217730;
    }
  }
  v18 = a2->GetHeader;
  v42 = v11;
  if ( ((unsigned int (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, char *, unsigned int *))v18)(
         a1,
         "Lock-Token:",
         v5,
         &v42) )
  {
    return 134217730;
  }
  if ( GetLastError() == 122 )
  {
    v19 = ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, _QWORD, _QWORD))a1->AllocMem)(a1, v42, 0);
    if ( !v19 )
      goto LABEL_54;
    if ( ((__int64 (__fastcall *)(struct _HTTP_FILTER_CONTEXT *, const char *, __int64, unsigned int *))a2->GetHeader)(
           a1,
           "Lock-Token:",
           v19,
           &v42) )
    {
      return 134217730;
    }
  }
  v20 = lstrlenA(*a3);
  v21 = v20;
  if ( !v20 )
    goto LABEL_64;
  v22 = strchr_0(*a3, 63);
  v23 = v22;
  if ( v22 )
    v6 = lstrlenA(v22);
  v24 = *a3;
  LODWORD(Size) = v21 - v6;
  v25 = (unsigned int)v21 - v6 - 1;
  if ( *v24 == 47 )
    goto LABEL_34;
  v26 = 0;
  if ( !(_DWORD)v21 )
  {
LABEL_64:
    v30 = 87;
    goto LABEL_65;
  }
  while ( v24[v10] != 47 || ++v26 != 3 )
  {
    v10 = (unsigned int)(v10 + 1);
    if ( (unsigned int)v10 >= (unsigned int)v21 )
      goto LABEL_64;
  }
LABEL_34:
  v27 = v21 - v6 - 1;
  if ( (unsigned int)v25 > (unsigned int)v10 )
  {
    while ( v24[v27] != 46 )
    {
      if ( --v27 <= (unsigned int)v10 )
        goto LABEL_37;
    }
    return 134217730;
  }
LABEL_37:
  v28 = (unsigned int)EURL::sm_cchEURLAppendage;
  v29 = v24[v25];
  if ( -2 - (int)v21 >= (unsigned int)EURL::sm_cchEURLAppendage )
  {
    v31 = v21 + EURL::sm_cchEURLAppendage + 1;
    if ( v31 < v43 )
    {
      v32 = &v24[v21];
      if ( v23 )
      {
        if ( v32 >= v23 )
        {
          while ( 1 )
          {
            v32[v28] = *v32;
            if ( --v32 < v23 )
              break;
            v28 = (unsigned int)EURL::sm_cchEURLAppendage;
          }
          LODWORD(v28) = EURL::sm_cchEURLAppendage;
        }
        v32 = v23;
        v23 += (unsigned int)v28;
      }
      v33 = (CHAR *)(v32 - 1);
      if ( v29 != 47 )
        v33 = (CHAR *)v32;
      memcpy_0(v33, EURL::sm_pszEURLAppendage, (unsigned int)v28);
      v34 = &v33[(unsigned int)EURL::sm_cchEURLAppendage];
      if ( v29 == 47 )
        *v34++ = 47;
      if ( v23 )
        v34 += v6;
      *v34 = 0;
LABEL_62:
      *v45 = 1;
      return 134217730;
    }
    BufferFromFilterContext = (char *)EURL::GetBufferFromFilterContext((__int64)a1, v31, 0);
    v36 = BufferFromFilterContext;
    if ( BufferFromFilterContext )
    {
      v37 = (unsigned int)Size;
      memcpy_0(BufferFromFilterContext, *a3, (unsigned int)Size);
      v38 = &v36[v37];
      v39 = &v36[v37 - 1];
      if ( v29 != 47 )
        v39 = v38;
      memcpy_0(v39, EURL::sm_pszEURLAppendage, (unsigned int)EURL::sm_cchEURLAppendage);
      v40 = &v39[(unsigned int)EURL::sm_cchEURLAppendage];
      if ( v29 == 47 )
        *v40++ = 47;
      if ( v23 )
      {
        memcpy_0(v40, v23, v6);
        v40 += v6;
      }
      *v40 = 0;
      *a3 = v36;
      goto LABEL_62;
    }
LABEL_54:
    v30 = 14;
    goto LABEL_65;
  }
  v30 = 534;
LABEL_65:
  SetLastError(v30);
  return 134217732;
}

```

## disassembly

```asm
0x18000291c  mov     [rsp-8+arg_18], rbx
0x180002921  push    rbp
0x180002922  push    rsi
0x180002923  push    rdi
0x180002924  push    r12
0x180002926  push    r13
0x180002928  push    r14
0x18000292a  push    r15
0x18000292c  lea     rbp, [rsp-360h]
0x180002934  sub     rsp, 460h
0x18000293b  mov     rax, cs:__security_cookie
0x180002942  xor     rax, rsp
0x180002945  mov     [rbp+390h+var_40], rax
0x18000294c  mov     rax, [rbp+390h+arg_20]
0x180002953  lea     rbx, [rsp+490h+Str2]
0x180002958  xor     r15d, r15d
0x18000295b  mov     [rsp+490h+var_45C], r9d
0x180002960  mov     [rsp+490h+var_450], rax
0x180002965  mov     r13, r8
0x180002968  mov     r14, rdx
0x18000296b  mov     rsi, rcx
0x18000296e  mov     r12d, r15d
0x180002971  mov     edi, 400h
0x180002976  test    r8, r8
0x180002979  jz      loc_180002D82
0x18000297f  cmp     [r8], r15
0x180002982  jz      loc_180002D82
0x180002988  mov     rax, [r14]
0x18000298b  lea     r9, [rsp+490h+var_460]
0x180002990  lea     r8, [rsp+490h+Str2]
0x180002995  mov     [rsp+490h+var_460], edi
0x180002999  lea     rdx, aMethod; "method"
0x1800029a0  call    cs:__guard_dispatch_icall_fptr
0x1800029a6  test    eax, eax
0x1800029a8  jnz     short loc_1800029FE
0x1800029aa  call    cs:__imp_GetLastError
0x1800029b0  cmp     eax, 7Ah ; 'z'
0x1800029b3  jnz     loc_180002D7B
0x1800029b9  mov     edi, [rsp+490h+var_460]
0x1800029bd  xor     r8d, r8d
0x1800029c0  mov     rax, [rsi+38h]
0x1800029c4  mov     edx, edi
0x1800029c6  mov     rcx, rsi
0x1800029c9  call    cs:__guard_dispatch_icall_fptr
0x1800029cf  mov     rbx, rax
0x1800029d2  test    rax, rax
0x1800029d5  jz      loc_180002CF8
0x1800029db  mov     r8, rax
0x1800029de  lea     r9, [rsp+490h+var_460]
0x1800029e3  mov     rax, [r14]
0x1800029e6  lea     rdx, aMethod; "method"
0x1800029ed  mov     rcx, rsi
0x1800029f0  call    cs:__guard_dispatch_icall_fptr
0x1800029f6  test    eax, eax
0x1800029f8  jz      loc_180002D7B
0x1800029fe  mov     rdx, rbx; Str2
0x180002a01  lea     rcx, Str1; "GET"
0x180002a08  call    strcmp_0
0x180002a0d  test    eax, eax
0x180002a0f  jz      short loc_180002A3B
0x180002a11  mov     rdx, rbx; Str2
0x180002a14  lea     rcx, aPost; "POST"
0x180002a1b  call    strcmp_0
0x180002a20  test    eax, eax
0x180002a22  jz      short loc_180002A3B
0x180002a24  mov     rdx, rbx; Str2
0x180002a27  lea     rcx, aHead; "HEAD"
0x180002a2e  call    strcmp_0
0x180002a33  test    eax, eax
0x180002a35  jnz     loc_180002D7B
0x180002a3b  mov     rax, [r14]
0x180002a3e  lea     r9, [rsp+490h+var_460]
0x180002a43  mov     r8, rbx
0x180002a46  mov     [rsp+490h+var_460], edi
0x180002a4a  lea     rdx, aTranslate; "Translate:"
0x180002a51  mov     rcx, rsi
0x180002a54  call    cs:__guard_dispatch_icall_fptr
0x180002a5a  test    eax, eax
0x180002a5c  jnz     short loc_180002AAA
0x180002a5e  call    cs:__imp_GetLastError
0x180002a64  cmp     eax, 7Ah ; 'z'
0x180002a67  jnz     short loc_180002AC9
0x180002a69  mov     edi, [rsp+490h+var_460]
0x180002a6d  xor     r8d, r8d
0x180002a70  mov     rax, [rsi+38h]
0x180002a74  mov     edx, edi
0x180002a76  mov     rcx, rsi
0x180002a79  call    cs:__guard_dispatch_icall_fptr
0x180002a7f  mov     rbx, rax
0x180002a82  test    rax, rax
0x180002a85  jz      loc_180002CF8
0x180002a8b  mov     r8, rax
0x180002a8e  lea     r9, [rsp+490h+var_460]
0x180002a93  mov     rax, [r14]
0x180002a96  lea     rdx, aTranslate; "Translate:"
0x180002a9d  mov     rcx, rsi
0x180002aa0  call    cs:__guard_dispatch_icall_fptr
0x180002aa6  test    eax, eax
0x180002aa8  jz      short loc_180002AC9
0x180002aaa  cmp     [rsp+490h+var_460], r15d
0x180002aaf  jbe     short loc_180002AC9
0x180002ab1  movsx   ecx, byte ptr [rbx]; C
0x180002ab4  call    cs:__imp_toupper
0x180002aba  cmp     eax, 46h ; 'F'
0x180002abd  jnz     short loc_180002AC9
0x180002abf  cmp     [rbx+1], r15b
0x180002ac3  jz      loc_180002D7B
0x180002ac9  mov     rax, [r14]
0x180002acc  lea     r9, [rsp+490h+var_460]
0x180002ad1  mov     r8, rbx
0x180002ad4  mov     [rsp+490h+var_460], edi
0x180002ad8  lea     rdx, aIf; "If:"
0x180002adf  mov     rcx, rsi
0x180002ae2  call    cs:__guard_dispatch_icall_fptr
0x180002ae8  test    eax, eax
0x180002aea  jnz     loc_180002D7B
0x180002af0  call    cs:__imp_GetLastError
0x180002af6  cmp     eax, 7Ah ; 'z'
0x180002af9  jnz     short loc_180002B40
0x180002afb  mov     edi, [rsp+490h+var_460]
0x180002aff  xor     r8d, r8d
0x180002b02  mov     rax, [rsi+38h]
0x180002b06  mov     edx, edi
0x180002b08  mov     rcx, rsi
0x180002b0b  call    cs:__guard_dispatch_icall_fptr
0x180002b11  mov     rbx, rax
0x180002b14  test    rax, rax
0x180002b17  jz      loc_180002CF8
0x180002b1d  mov     r8, rax
0x180002b20  lea     r9, [rsp+490h+var_460]
0x180002b25  mov     rax, [r14]
0x180002b28  lea     rdx, aIf; "If:"
0x180002b2f  mov     rcx, rsi
0x180002b32  call    cs:__guard_dispatch_icall_fptr
0x180002b38  test    eax, eax
0x180002b3a  jnz     loc_180002D7B
0x180002b40  mov     rax, [r14]
0x180002b43  lea     r9, [rsp+490h+var_460]
0x180002b48  mov     r8, rbx
0x180002b4b  mov     [rsp+490h+var_460], edi
0x180002b4f  lea     rdx, aLockToken; "Lock-Token:"
0x180002b56  mov     rcx, rsi
0x180002b59  call    cs:__guard_dispatch_icall_fptr
0x180002b5f  test    eax, eax
0x180002b61  jnz     loc_180002D7B
0x180002b67  call    cs:__imp_GetLastError
0x180002b6d  cmp     eax, 7Ah ; 'z'
0x180002b70  jnz     short loc_180002BB2
0x180002b72  mov     edx, [rsp+490h+var_460]
0x180002b76  xor     r8d, r8d
0x180002b79  mov     rax, [rsi+38h]
0x180002b7d  mov     rcx, rsi
0x180002b80  call    cs:__guard_dispatch_icall_fptr
0x180002b86  test    rax, rax
0x180002b89  jz      loc_180002CF8
0x180002b8f  mov     r8, rax
0x180002b92  lea     r9, [rsp+490h+var_460]
0x180002b97  mov     rax, [r14]
0x180002b9a  lea     rdx, aLockToken; "Lock-Token:"
0x180002ba1  mov     rcx, rsi
0x180002ba4  call    cs:__guard_dispatch_icall_fptr
0x180002baa  test    eax, eax
0x180002bac  jnz     loc_180002D7B
0x180002bb2  mov     rcx, [r13+0]; lpString
0x180002bb6  call    cs:__imp_lstrlenA
0x180002bbc  mov     ebx, eax
0x180002bbe  test    eax, eax
0x180002bc0  jz      loc_180002D82
0x180002bc6  mov     rcx, [r13+0]; Str
0x180002bca  mov     edx, 3Fh ; '?'; Val
0x180002bcf  call    strchr_0
0x180002bd4  mov     rdi, rax
0x180002bd7  test    rax, rax
0x180002bda  jz      short loc_180002BE8
0x180002bdc  mov     rcx, rax; lpString
0x180002bdf  call    cs:__imp_lstrlenA
0x180002be5  mov     r15d, eax
0x180002be8  mov     r8, [r13+0]
0x180002bec  mov     eax, ebx
0x180002bee  sub     eax, r15d
0x180002bf1  mov     r14b, 2Fh ; '/'
0x180002bf4  mov     dword ptr [rsp+490h+Size], eax
0x180002bf8  lea     edx, [rax-1]
0x180002bfb  cmp     [r8], r14b
0x180002bfe  jz      short loc_180002C2B
0x180002c00  xor     ecx, ecx
0x180002c02  test    ebx, ebx
0x180002c04  jz      loc_180002D82
0x180002c0a  cmp     [r12+r8], r14b
0x180002c0e  jnz     short loc_180002C17
0x180002c10  inc     ecx
0x180002c12  cmp     ecx, 3
0x180002c15  jz      short loc_180002C2B
0x180002c17  inc     r12d
0x180002c1a  cmp     r12d, ebx
0x180002c1d  jb      short loc_180002C0A
0x180002c1f  xor     r12d, r12d
0x180002c22  cmp     ecx, 3
0x180002c25  jnz     loc_180002D82
0x180002c2b  mov     ecx, edx
0x180002c2d  cmp     edx, r12d
0x180002c30  jbe     short loc_180002C46
0x180002c32  mov     eax, ecx
0x180002c34  cmp     byte ptr [rax+r8], 2Eh ; '.'
0x180002c39  jz      loc_180002D7B
0x180002c3f  dec     ecx
0x180002c41  cmp     ecx, r12d
0x180002c44  ja      short loc_180002C32
0x180002c46  mov     ecx, cs:?sm_cchEURLAppendage@EURL@@0KA; ulong EURL::sm_cchEURLAppendage
0x180002c4c  mov     eax, 0FFFFFFFEh
0x180002c51  mov     r12b, [rdx+r8]
0x180002c55  sub     eax, ebx
0x180002c57  cmp     eax, ecx
0x180002c59  jnb     short loc_180002C65
0x180002c5b  mov     ecx, 216h
0x180002c60  jmp     loc_180002D87
0x180002c65  lea     edx, [rcx+1]
0x180002c68  add     edx, ebx
0x180002c6a  cmp     edx, [rsp+490h+var_45C]
0x180002c6e  jnb     short loc_180002CE5
0x180002c70  lea     rdx, [r8+rbx]
0x180002c74  test    rdi, rdi
0x180002c77  jz      short loc_180002CA1
0x180002c79  cmp     rdx, rdi
0x180002c7c  jb      short loc_180002C99
0x180002c7e  mov     al, [rdx]
0x180002c80  mov     [rcx+rdx], al
0x180002c83  dec     rdx
0x180002c86  cmp     rdx, rdi
0x180002c89  jb      short loc_180002C93
0x180002c8b  mov     ecx, cs:?sm_cchEURLAppendage@EURL@@0KA; ulong EURL::sm_cchEURLAppendage
0x180002c91  jmp     short loc_180002C7E
0x180002c93  mov     ecx, cs:?sm_cchEURLAppendage@EURL@@0KA; ulong EURL::sm_cchEURLAppendage
0x180002c99  mov     eax, ecx
0x180002c9b  mov     rdx, rdi
0x180002c9e  add     rdi, rax
0x180002ca1  lea     rbx, [rdx-1]
0x180002ca5  mov     r8d, ecx; Size
0x180002ca8  cmp     r12b, r14b
0x180002cab  cmovnz  rbx, rdx
0x180002caf  mov     rdx, cs:?sm_pszEURLAppendage@EURL@@0PEADEA; Src
0x180002cb6  mov     rcx, rbx; void *
0x180002cb9  call    memcpy_0
0x180002cbe  mov     ecx, cs:?sm_cchEURLAppendage@EURL@@0KA; ulong EURL::sm_cchEURLAppendage
0x180002cc4  add     rcx, rbx
0x180002cc7  cmp     r12b, r14b
0x180002cca  jnz     short loc_180002CD2
0x180002ccc  mov     [rcx], r14b
0x180002ccf  inc     rcx
0x180002cd2  test    rdi, rdi
0x180002cd5  jz      short loc_180002CDD
0x180002cd7  mov     eax, r15d
0x180002cda  add     rcx, rax
0x180002cdd  mov     byte ptr [rcx], 0
0x180002ce0  jmp     loc_180002D70
0x180002ce5  xor     r8d, r8d
0x180002ce8  mov     rcx, rsi
0x180002ceb  call    ?GetBufferFromFilterContext@EURL@@SAPEADPEAU_HTTP_FILTER_CONTEXT@@KW4EBufferType@@@Z; EURL::GetBufferFromFilterContext(_HTTP_FILTER_CONTEXT *,ulong,EBufferType)
0x180002cf0  mov     r14, rax
0x180002cf3  test    rax, rax
0x180002cf6  jnz     short loc_180002D02
0x180002cf8  mov     ecx, 0Eh
0x180002cfd  jmp     loc_180002D87
0x180002d02  mov     ebx, dword ptr [rsp+490h+Size]
0x180002d06  mov     rcx, r14; void *
0x180002d09  mov     rdx, [r13+0]; Src
0x180002d0d  mov     r8d, ebx; Size
0x180002d10  call    memcpy_0
0x180002d15  mov     r8d, cs:?sm_cchEURLAppendage@EURL@@0KA; Size
0x180002d1c  lea     rax, [rbx+r14]
0x180002d20  mov     rdx, cs:?sm_pszEURLAppendage@EURL@@0PEADEA; Src
0x180002d27  lea     rbx, [rax-1]
0x180002d2b  cmp     r12b, 2Fh ; '/'
0x180002d2f  cmovnz  rbx, rax
0x180002d33  mov     rcx, rbx; void *
0x180002d36  call    memcpy_0
0x180002d3b  mov     esi, cs:?sm_cchEURLAppendage@EURL@@0KA; ulong EURL::sm_cchEURLAppendage
0x180002d41  add     rsi, rbx
0x180002d44  cmp     r12b, 2Fh ; '/'
0x180002d48  jnz     short loc_180002D50
0x180002d4a  mov     [rsi], r12b
0x180002d4d  inc     rsi
0x180002d50  test    rdi, rdi
0x180002d53  jz      short loc_180002D69
0x180002d55  mov     r8d, r15d; Size
0x180002d58  mov     rdx, rdi; Src
0x180002d5b  mov     rcx, rsi; void *
0x180002d5e  mov     ebx, r15d
0x180002d61  call    memcpy_0
0x180002d66  add     rsi, rbx
0x180002d69  mov     byte ptr [rsi], 0
0x180002d6c  mov     [r13+0], r14
0x180002d70  mov     rax, [rsp+490h+var_450]
0x180002d75  mov     dword ptr [rax], 1
0x180002d7b  mov     eax, 8000002h
0x180002d80  jmp     short loc_180002D92
0x180002d82  mov     ecx, 57h ; 'W'; dwErrCode
0x180002d87  call    cs:__imp_SetLastError
0x180002d8d  mov     eax, 8000004h
0x180002d92  mov     rcx, [rbp+390h+var_40]
  ... truncated ...
```
