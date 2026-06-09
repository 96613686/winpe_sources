# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)

- ea: `0x18001e0e4`
- end: `0x18001e7d8`
- name: `?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z`
- size: `1780`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *this, struct IQueryRecentWinSATAssessment *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002, char, OLECHAR *psz, union _LARGE_INTEGER, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e7d8`

## callees

- `0x18000139c`
- `0x1800130a8`
- `0x18001e0e4`
- `0x180026e30`
- `0x180026f6c`
- `0x1800278f0`
- `0x180027910`

## import_xrefs

- `msvcrt!malloc` at `0x18001e51b`
- `msvcrt!malloc` at `0x18001e640`
- `msvcrt!malloc` at `0x18001e51b`
- `msvcrt!malloc` at `0x18001e640`
- `msvcrt!free` at `0x18001e50e`
- `msvcrt!free` at `0x18001e633`
- `msvcrt!free` at `0x18001e50e`
- `msvcrt!free` at `0x18001e633`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e17c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e17c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e3eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e497`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1cb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e3eb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e497`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        struct IQueryRecentWinSATAssessment *a2,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 a3,
        char a4,
        OLECHAR *psz,
        union _LARGE_INTEGER a6,
        unsigned int a7,
        __int16 a8)
{
  char *v12; // rbx
  int v13; // edi
  __int64 v14; // rax
  volatile signed __int32 *v15; // rbx
  unsigned int v16; // r15d
  char v17; // al
  unsigned int v18; // ecx
  void *v19; // rax
  __int64 (__fastcall *v20)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD); // rax
  int v21; // eax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v22; // rax
  unsigned int v23; // r13d
  void *v24; // rax
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *v25; // rcx
  unsigned int v26; // ecx
  unsigned int v27; // r15d
  unsigned int v28; // [rsp+50h] [rbp-138h] BYREF
  enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v29; // [rsp+54h] [rbp-134h]
  __int64 v30; // [rsp+58h] [rbp-130h] BYREF
  __int64 v31; // [rsp+60h] [rbp-128h] BYREF
  char *v32; // [rsp+70h] [rbp-118h]
  unsigned int v33; // [rsp+78h] [rbp-110h]
  BSTR v34; // [rsp+80h] [rbp-108h] BYREF
  unsigned int v35; // [rsp+88h] [rbp-100h]
  int v36; // [rsp+8Ch] [rbp-FCh]
  int v37; // [rsp+90h] [rbp-F8h]
  int v38; // [rsp+94h] [rbp-F4h]
  BSTR bstrString; // [rsp+98h] [rbp-F0h]
  void *Src; // [rsp+A0h] [rbp-E8h] BYREF
  char *v41; // [rsp+A8h] [rbp-E0h]
  char *v42; // [rsp+B0h] [rbp-D8h]
  char *v43; // [rsp+B8h] [rbp-D0h]
  char *v44; // [rsp+C0h] [rbp-C8h]
  __int64 v45; // [rsp+C8h] [rbp-C0h]
  _WORD v46[2]; // [rsp+E0h] [rbp-A8h] BYREF
  char v47; // [rsp+E4h] [rbp-A4h]
  char v48; // [rsp+E5h] [rbp-A3h]
  __int16 v49; // [rsp+E6h] [rbp-A2h]
  union _LARGE_INTEGER v50; // [rsp+F0h] [rbp-98h]
  __int128 v51; // [rsp+F8h] [rbp-90h]
  char *v52; // [rsp+128h] [rbp-60h]
  unsigned int v53; // [rsp+130h] [rbp-58h]
  unsigned int v54; // [rsp+134h] [rbp-54h]

  v45 = -2;
  v29 = a3;
  if ( !a2 )
    return 2147500035LL;
  v12 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  Src = v12;
  v31 = 0;
  v30 = 0;
  if ( psz )
  {
    bstrString = SysAllocString(psz);
    if ( !bstrString )
      ATL::AtlThrowImpl(-2147024882);
  }
  else
  {
    bstrString = 0;
  }
  v13 = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, BSTR, _QWORD, __int64 *))a2->lpVtbl->get_XML)(
          a2,
          bstrString,
          0,
          &v31);
  v35 = v13;
  SysFreeString(bstrString);
  if ( v13 < 0 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v41 = v12 - 24;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 8LL))(*(_QWORD *)v41);
    return v35;
  }
  if ( !v31 )
  {
    v42 = v12 - 24;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v42 + 8LL))(*(_QWORD *)v42);
    return 1;
  }
  v36 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 72LL))(v31, &v30);
  if ( v36 < 0 )
  {
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v43 = v12 - 24;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v43 + 8LL))(*(_QWORD *)v43);
    return (unsigned int)v36;
  }
  if ( !v30 )
  {
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v44 = v12 - 24;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v44 + 8LL))(*(_QWORD *)v44);
    return 1;
  }
  v34 = 0;
  v37 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v30 + 272LL))(v30, &v34);
  if ( v37 < 0 )
  {
    SysFreeString(v34);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v32 = v12 - 24;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v32 + 8LL))(*(_QWORD *)v32);
    return (unsigned int)v37;
  }
  if ( v34 )
  {
    v14 = -1;
    do
      ++v14;
    while ( v34[v14] );
  }
  else
  {
    LODWORD(v14) = 0;
  }
  v38 = v14;
  ATL::CSimpleStringT<unsigned short,0>::SetString(&Src, v34, (unsigned int)v14);
  SysFreeString(v34);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v15 = (volatile signed __int32 *)Src;
  v16 = 2 * *((_DWORD *)Src - 4) + 2;
  v17 = *((_BYTE *)this + 33);
  if ( v16 < 8 )
    v17 = 1;
  v18 = 0;
  v28 = 0;
  if ( v17 )
    goto LABEL_71;
  if ( *((_DWORD *)this + 20) < v16 - 8 )
  {
    free(*((void **)this + 9));
    *((_DWORD *)this + 20) = 0;
    v19 = malloc(v16);
    *((_QWORD *)this + 9) = v19;
    if ( !v19 )
    {
LABEL_52:
      if ( _InterlockedExchangeAdd(v15 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
      return 2147942414LL;
    }
    *((_DWORD *)this + 20) = v16;
    v18 = v28;
  }
  v20 = (__int64 (__fastcall *)(__int64, volatile signed __int32 *, _QWORD, __int64, unsigned int, int, unsigned int *, _QWORD))*((_QWORD *)this + 5);
  if ( v20 )
  {
    v21 = v20(258, v15, v16, *((_QWORD *)this + 9) + 8LL, v16 - 8, 4096, &v28, *((_QWORD *)this + 7));
    v18 = v28;
  }
  else
  {
    v21 = -1073741822;
  }
  if ( v21 || v18 > v16 - 8 )
  {
LABEL_71:
    v23 = v16 + 4;
    if ( *((_DWORD *)this + 24) < v16 + 4 )
    {
      free(*((void **)this + 11));
      *((_DWORD *)this + 24) = 0;
      v24 = malloc(v23);
      *((_QWORD *)this + 11) = v24;
      if ( !v24 )
        goto LABEL_52;
      *((_DWORD *)this + 24) = v23;
    }
    v25 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 11);
    *v25 = v29;
    memcpy_0(v25 + 1, (const void *)v15, v16);
    v26 = *((_DWORD *)this + 24);
    v32 = (char *)*((_QWORD *)this + 11);
    v33 = v26;
    goto LABEL_75;
  }
  v28 = v18 + 8;
  switch ( a4 )
  {
    case ' ':
      a4 = 33;
      goto LABEL_70;
    case '"':
      a4 = 35;
      goto LABEL_70;
    case '$':
      a4 = 37;
LABEL_70:
      v22 = (enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *)*((_QWORD *)this + 9);
      *v22 = v29;
      *((_DWORD *)v22 + 1) = v16;
      v32 = (char *)*((_QWORD *)this + 9);
      v33 = v28;
LABEL_75:
      v27 = v33;
      if ( v33 < 0xFFFF )
      {
        memset_0(v46, 0, 0x58u);
        v46[0] = a8;
        v50 = a6;
        v51 = *(_OWORD *)WinSATAssessmentGuid;
        v47 = a4;
        v49 = 0;
        v48 = 0;
        v52 = v32;
        v53 = v27;
        v54 = a7;
        (*(void (__fastcall **)(_QWORD, _WORD *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
          *((_QWORD *)this + 2),
          v46,
          0,
          0);
        if ( _InterlockedExchangeAdd(v15 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
        return 0;
      }
      else
      {
        if ( _InterlockedExchangeAdd(v15 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
        return 1;
      }
  }
  if ( _InterlockedExchangeAdd(v15 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v15 - 3) + 8LL))(*((_QWORD *)v15 - 3));
  return 2147500033LL;
}

```

## disassembly

```asm
0x18001e0e4  push    rbx
0x18001e0e6  push    rsi
0x18001e0e7  push    rdi
0x18001e0e8  push    r12
0x18001e0ea  push    r13
0x18001e0ec  push    r14
0x18001e0ee  push    r15
0x18001e0f0  sub     rsp, 150h
0x18001e0f7  mov     [rsp+188h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18001e103  mov     rax, cs:__security_cookie
0x18001e10a  xor     rax, rsp
0x18001e10d  mov     [rsp+188h+var_48], rax
0x18001e115  mov     r12b, r9b
0x18001e118  mov     [rsp+188h+var_134], r8d
0x18001e11d  mov     r15, rdx
0x18001e120  mov     r14, rcx
0x18001e123  mov     rdi, [rsp+188h+psz]
0x18001e12b  xor     esi, esi
0x18001e12d  test    rdx, rdx
0x18001e130  jnz     short loc_18001E13C
0x18001e132  mov     eax, 80004003h
0x18001e137  jmp     loc_18001E7B5
0x18001e13c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e143  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001e14a  mov     rax, [rax+18h]
0x18001e14e  call    cs:__guard_dispatch_icall_fptr
0x18001e154  lea     rbx, [rax+18h]
0x18001e158  mov     [rsp+188h+Src], rbx
0x18001e160  mov     [rsp+188h+var_128], rsi
0x18001e165  mov     [rsp+188h+var_130], rsi
0x18001e16a  test    rdi, rdi
0x18001e16d  jnz     short loc_18001E179
0x18001e16f  mov     [rsp+188h+bstrString], rsi
0x18001e177  jmp     short loc_18001E19A
0x18001e179  mov     rcx, rdi; psz
0x18001e17c  call    cs:__imp_SysAllocString
0x18001e182  mov     [rsp+188h+bstrString], rax
0x18001e18a  test    rax, rax
0x18001e18d  jnz     short loc_18001E19A
0x18001e18f  mov     ecx, 8007000Eh; int
0x18001e194  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001e19a  mov     rax, [r15]
0x18001e19d  lea     r9, [rsp+188h+var_128]
0x18001e1a2  xor     r8d, r8d
0x18001e1a5  mov     rdx, [rsp+188h+bstrString]
0x18001e1ad  mov     rcx, r15
0x18001e1b0  mov     rax, [rax+38h]
0x18001e1b4  call    cs:__guard_dispatch_icall_fptr
0x18001e1ba  mov     edi, eax
0x18001e1bc  mov     [rsp+188h+var_100], eax
0x18001e1c3  mov     rcx, [rsp+188h+bstrString]; bstrString
0x18001e1cb  call    cs:__imp_SysFreeString
0x18001e1d1  test    edi, edi
0x18001e1d3  jns     short loc_18001E242
0x18001e1d5  mov     rcx, [rsp+188h+var_130]
0x18001e1da  test    rcx, rcx
0x18001e1dd  jz      short loc_18001E1ED
0x18001e1df  mov     rax, [rcx]
0x18001e1e2  mov     rax, [rax+10h]
0x18001e1e6  call    cs:__guard_dispatch_icall_fptr
0x18001e1ec  nop
0x18001e1ed  mov     rcx, [rsp+188h+var_128]
0x18001e1f2  test    rcx, rcx
0x18001e1f5  jz      short loc_18001E205
0x18001e1f7  mov     rax, [rcx]
0x18001e1fa  mov     rax, [rax+10h]
0x18001e1fe  call    cs:__guard_dispatch_icall_fptr
0x18001e204  nop
0x18001e205  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001e209  mov     [rsp+188h+var_E0], rbx
0x18001e211  or      eax, 0FFFFFFFFh
0x18001e214  lock xadd [rbx+10h], eax
0x18001e219  sub     eax, 1
0x18001e21c  jg      short loc_18001E236
0x18001e21e  mov     rdx, [rsp+188h+var_E0]
0x18001e226  mov     rcx, [rdx]
0x18001e229  mov     rax, [rcx]
0x18001e22c  mov     rax, [rax+8]
0x18001e230  call    cs:__guard_dispatch_icall_fptr
0x18001e236  mov     eax, [rsp+188h+var_100]
0x18001e23d  jmp     loc_18001E7B5
0x18001e242  mov     rcx, [rsp+188h+var_128]
0x18001e247  test    rcx, rcx
0x18001e24a  jnz     short loc_18001E2B7
0x18001e24c  mov     rcx, [rsp+188h+var_130]
0x18001e251  test    rcx, rcx
0x18001e254  jz      short loc_18001E264
0x18001e256  mov     rax, [rcx]
0x18001e259  mov     rax, [rax+10h]
0x18001e25d  call    cs:__guard_dispatch_icall_fptr
0x18001e263  nop
0x18001e264  mov     rcx, [rsp+188h+var_128]
0x18001e269  test    rcx, rcx
0x18001e26c  jz      short loc_18001E27C
0x18001e26e  mov     rax, [rcx]
0x18001e271  mov     rax, [rax+10h]
0x18001e275  call    cs:__guard_dispatch_icall_fptr
0x18001e27b  nop
0x18001e27c  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001e280  mov     [rsp+188h+var_D8], rbx
0x18001e288  or      eax, 0FFFFFFFFh
0x18001e28b  lock xadd [rbx+10h], eax
0x18001e290  sub     eax, 1
0x18001e293  jg      short loc_18001E2AD
0x18001e295  mov     rdx, [rsp+188h+var_D8]
0x18001e29d  mov     rcx, [rdx]
0x18001e2a0  mov     rax, [rcx]
0x18001e2a3  mov     rax, [rax+8]
0x18001e2a7  call    cs:__guard_dispatch_icall_fptr
0x18001e2ad  mov     eax, 1
0x18001e2b2  jmp     loc_18001E7B5
0x18001e2b7  mov     rax, [rcx]
0x18001e2ba  lea     rdx, [rsp+188h+var_130]
0x18001e2bf  mov     rax, [rax+48h]
0x18001e2c3  call    cs:__guard_dispatch_icall_fptr
0x18001e2c9  mov     [rsp+188h+var_FC], eax
0x18001e2d0  test    eax, eax
0x18001e2d2  jns     short loc_18001E341
0x18001e2d4  mov     rcx, [rsp+188h+var_130]
0x18001e2d9  test    rcx, rcx
0x18001e2dc  jz      short loc_18001E2EC
0x18001e2de  mov     rax, [rcx]
0x18001e2e1  mov     rax, [rax+10h]
0x18001e2e5  call    cs:__guard_dispatch_icall_fptr
0x18001e2eb  nop
0x18001e2ec  mov     rcx, [rsp+188h+var_128]
0x18001e2f1  test    rcx, rcx
0x18001e2f4  jz      short loc_18001E304
0x18001e2f6  mov     rax, [rcx]
0x18001e2f9  mov     rax, [rax+10h]
0x18001e2fd  call    cs:__guard_dispatch_icall_fptr
0x18001e303  nop
0x18001e304  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001e308  mov     [rsp+188h+var_D0], rbx
0x18001e310  or      eax, 0FFFFFFFFh
0x18001e313  lock xadd [rbx+10h], eax
0x18001e318  sub     eax, 1
0x18001e31b  jg      short loc_18001E335
0x18001e31d  mov     rdx, [rsp+188h+var_D0]
0x18001e325  mov     rcx, [rdx]
0x18001e328  mov     rax, [rcx]
0x18001e32b  mov     rax, [rax+8]
0x18001e32f  call    cs:__guard_dispatch_icall_fptr
0x18001e335  mov     eax, [rsp+188h+var_FC]
0x18001e33c  jmp     loc_18001E7B5
0x18001e341  cmp     [rsp+188h+var_130], rsi
0x18001e346  jnz     short loc_18001E3B3
0x18001e348  mov     rcx, [rsp+188h+var_130]
0x18001e34d  test    rcx, rcx
0x18001e350  jz      short loc_18001E360
0x18001e352  mov     rax, [rcx]
0x18001e355  mov     rax, [rax+10h]
0x18001e359  call    cs:__guard_dispatch_icall_fptr
0x18001e35f  nop
0x18001e360  mov     rcx, [rsp+188h+var_128]
0x18001e365  test    rcx, rcx
0x18001e368  jz      short loc_18001E378
0x18001e36a  mov     rax, [rcx]
0x18001e36d  mov     rax, [rax+10h]
0x18001e371  call    cs:__guard_dispatch_icall_fptr
0x18001e377  nop
0x18001e378  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001e37c  mov     [rsp+188h+var_C8], rbx
0x18001e384  or      eax, 0FFFFFFFFh
0x18001e387  lock xadd [rbx+10h], eax
0x18001e38c  sub     eax, 1
0x18001e38f  jg      short loc_18001E3A9
0x18001e391  mov     rdx, [rsp+188h+var_C8]
0x18001e399  mov     rcx, [rdx]
0x18001e39c  mov     rax, [rcx]
0x18001e39f  mov     rax, [rax+8]
0x18001e3a3  call    cs:__guard_dispatch_icall_fptr
0x18001e3a9  mov     eax, 1
0x18001e3ae  jmp     loc_18001E7B5
0x18001e3b3  mov     [rsp+188h+var_108], rsi
0x18001e3bb  mov     rcx, [rsp+188h+var_130]
0x18001e3c0  mov     rax, [rcx]
0x18001e3c3  lea     rdx, [rsp+188h+var_108]
0x18001e3cb  mov     rax, [rax+110h]
0x18001e3d2  call    cs:__guard_dispatch_icall_fptr
0x18001e3d8  mov     [rsp+188h+var_F8], eax
0x18001e3df  test    eax, eax
0x18001e3e1  jns     short loc_18001E459
0x18001e3e3  mov     rcx, [rsp+188h+var_108]; bstrString
0x18001e3eb  call    cs:__imp_SysFreeString
0x18001e3f1  nop
0x18001e3f2  mov     rcx, [rsp+188h+var_130]
0x18001e3f7  test    rcx, rcx
0x18001e3fa  jz      short loc_18001E40A
0x18001e3fc  mov     rax, [rcx]
0x18001e3ff  mov     rax, [rax+10h]
0x18001e403  call    cs:__guard_dispatch_icall_fptr
0x18001e409  nop
0x18001e40a  mov     rcx, [rsp+188h+var_128]
0x18001e40f  test    rcx, rcx
0x18001e412  jz      short loc_18001E422
0x18001e414  mov     rax, [rcx]
0x18001e417  mov     rax, [rax+10h]
0x18001e41b  call    cs:__guard_dispatch_icall_fptr
0x18001e421  nop
0x18001e422  add     rbx, 0FFFFFFFFFFFFFFE8h
0x18001e426  mov     qword ptr [rsp+188h+var_118], rbx
0x18001e42b  or      eax, 0FFFFFFFFh
0x18001e42e  lock xadd [rbx+10h], eax
0x18001e433  sub     eax, 1
0x18001e436  jg      short loc_18001E44D
0x18001e438  mov     rdx, qword ptr [rsp+188h+var_118]
0x18001e43d  mov     rcx, [rdx]
0x18001e440  mov     rax, [rcx]
0x18001e443  mov     rax, [rax+8]
0x18001e447  call    cs:__guard_dispatch_icall_fptr
0x18001e44d  mov     eax, [rsp+188h+var_F8]
0x18001e454  jmp     loc_18001E7B5
0x18001e459  mov     rdx, [rsp+188h+var_108]
0x18001e461  test    rdx, rdx
0x18001e464  jnz     short loc_18001E46A
0x18001e466  mov     eax, esi
0x18001e468  jmp     short loc_18001E477
0x18001e46a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e46e  inc     rax
0x18001e471  cmp     [rdx+rax*2], si
0x18001e475  jnz     short loc_18001E46E
0x18001e477  mov     [rsp+188h+var_F4], eax
0x18001e47e  mov     r8d, eax
0x18001e481  lea     rcx, [rsp+188h+Src]
0x18001e489  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e48e  nop
0x18001e48f  mov     rcx, [rsp+188h+var_108]; bstrString
0x18001e497  call    cs:__imp_SysFreeString
0x18001e49d  nop
0x18001e49e  mov     rcx, [rsp+188h+var_130]
0x18001e4a3  test    rcx, rcx
0x18001e4a6  jz      short loc_18001E4B6
0x18001e4a8  mov     rax, [rcx]
0x18001e4ab  mov     rax, [rax+10h]
0x18001e4af  call    cs:__guard_dispatch_icall_fptr
0x18001e4b5  nop
0x18001e4b6  mov     rcx, [rsp+188h+var_128]
0x18001e4bb  test    rcx, rcx
0x18001e4be  jz      short loc_18001E4CE
0x18001e4c0  mov     rax, [rcx]
0x18001e4c3  mov     rax, [rax+10h]
0x18001e4c7  call    cs:__guard_dispatch_icall_fptr
0x18001e4cd  nop
0x18001e4ce  mov     rbx, [rsp+188h+Src]
0x18001e4d6  mov     eax, [rbx-10h]
0x18001e4d9  lea     r15d, ds:2[rax*2]
0x18001e4e1  movzx   eax, byte ptr [r14+21h]
0x18001e4e6  mov     edi, 1
0x18001e4eb  cmp     r15d, 8
0x18001e4ef  cmovb   eax, edi
0x18001e4f2  mov     ecx, esi
0x18001e4f4  mov     [rsp+188h+var_138], ecx
0x18001e4f8  test    al, al
0x18001e4fa  jnz     loc_18001E625
0x18001e500  lea     r13d, [r15-8]
0x18001e504  cmp     [r14+50h], r13d
0x18001e508  jnb     short loc_18001E55D
0x18001e50a  mov     rcx, [r14+48h]; Block
0x18001e50e  call    cs:__imp_free
0x18001e514  mov     [r14+50h], esi
0x18001e518  mov     ecx, r15d; Size
0x18001e51b  call    cs:__imp_malloc
0x18001e521  mov     [r14+48h], rax
0x18001e525  test    rax, rax
0x18001e528  jnz     short loc_18001E555
0x18001e52a  lea     rdx, [rbx-18h]
0x18001e52e  or      eax, 0FFFFFFFFh
0x18001e531  lock xadd [rdx+10h], eax
0x18001e536  sub     eax, 1
0x18001e539  jg      short loc_18001E54B
0x18001e53b  mov     rcx, [rdx]
0x18001e53e  mov     rax, [rcx]
0x18001e541  mov     rax, [rax+8]
0x18001e545  call    cs:__guard_dispatch_icall_fptr
0x18001e54b  mov     eax, 8007000Eh
0x18001e550  jmp     loc_18001E7B5
0x18001e555  mov     [r14+50h], r15d
0x18001e559  mov     ecx, [rsp+188h+var_138]
0x18001e55d  mov     rdx, [r14+38h]
0x18001e561  mov     r9, [r14+48h]
0x18001e565  mov     rax, [r14+28h]
0x18001e569  test    rax, rax
0x18001e56c  jz      short loc_18001E5A5
0x18001e56e  add     r9, 8
0x18001e572  mov     ecx, 102h
0x18001e577  mov     [rsp+188h+var_150], rdx
0x18001e57c  lea     rdx, [rsp+188h+var_138]
0x18001e581  mov     [rsp+188h+var_158], rdx
0x18001e586  mov     [rsp+188h+var_160], 1000h
0x18001e58e  mov     [rsp+188h+var_168], r13d
0x18001e593  mov     r8d, r15d
0x18001e596  mov     rdx, rbx
0x18001e599  call    cs:__guard_dispatch_icall_fptr
0x18001e59f  mov     ecx, [rsp+188h+var_138]
0x18001e5a3  jmp     short loc_18001E5AA
0x18001e5a5  mov     eax, 0C0000002h
0x18001e5aa  test    eax, eax
0x18001e5ac  jnz     short loc_18001E625
0x18001e5ae  cmp     ecx, r13d
  ... truncated ...
```
