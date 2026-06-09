# CDwnBindInfo::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x180666da0`
- end: `0x1806670a1`
- name: `?GetBindString@CDwnBindInfo@@UEAAJKPEAPEAGKPEAK@Z`
- size: `769`
- prototype: `int(CDwnBindInfo *__hidden this, unsigned int, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x18030035c`
- `0x1804e223c`
- `0x1804e23dc`
- `0x180666da0`
- `0x180729168`
- `0x180a2ab98`
- `0x181060d90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180666e56`
- `msvcrt!memcpy_s` at `0x180666ebf`
- `msvcrt!memcpy_s` at `0x180666f29`
- `msvcrt!memcpy_s` at `0x180666fa8`
- `msvcrt!memcpy_s` at `0x180666e56`
- `msvcrt!memcpy_s` at `0x180666ebf`
- `msvcrt!memcpy_s` at `0x180666f29`
- `msvcrt!memcpy_s` at `0x180666fa8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666e3d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666e9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666f10`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666f86`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180667010`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666e3d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666e9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666f10`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180666f86`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180667010`
- `OLEAUT32!__imp_SysFreeString` at `0x180666f40`
- `OLEAUT32!__imp_SysFreeString` at `0x180666f40`
- `OLEAUT32!__imp_SysStringLen` at `0x180666eff`
- `OLEAUT32!__imp_SysStringLen` at `0x180666eff`

## pseudocode

```c
__int64 __fastcall CDwnBindInfo::GetBindString(
        CDwnBindInfo *this,
        int a2,
        unsigned __int16 **a3,
        unsigned int a4,
        OLECHAR *pbstr)
{
  OLECHAR *v5; // r14
  unsigned int AcceptHeadersForCategory; // ebx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rdi
  _WORD *v16; // rdi
  __int64 v17; // rax
  SIZE_T v18; // rsi
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r15
  unsigned __int16 *v22; // rax
  rsize_t v23; // r9
  const wchar_t *v24; // r8
  rsize_t v25; // rdx
  __int64 v26; // rax
  CMarkup *v27; // rcx
  OLECHAR *v28; // rdi
  SIZE_T v29; // rsi
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // r15
  struct IUri *v32; // rdx
  SIZE_T v33; // rdi
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rsi
  __int64 v36; // rdi
  const wchar_t *v37; // rdi
  __int64 v38; // rax
  SIZE_T v39; // rsi
  CDwnPost *v40; // rcx
  _QWORD v41[5]; // [rsp+20h] [rbp-38h] BYREF
  int v42; // [rsp+48h] [rbp-10h]
  int v43; // [rsp+A8h] [rbp+50h] BYREF

  v5 = pbstr;
  AcceptHeadersForCategory = 0;
  v43 = 0;
  *(_DWORD *)pbstr = 0;
  v10 = a2 - 2;
  if ( !v10 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_MIME_USE_BUILTIN_ACCEPT_HEADERS)
      && *(int *)(*((_QWORD *)this + 3) + 196LL) >= 9 )
    {
      AcceptHeadersForCategory = GetAcceptHeadersForCategory(*((unsigned int *)this + 30), a3, a4, v5);
      if ( (AcceptHeadersForCategory & 0x80000000) == 0 )
        return AcceptHeadersForCategory;
    }
    v22 = (unsigned __int16 *)CoTaskMemAlloc(8u);
    *a3 = v22;
    if ( v22 )
    {
      v23 = 8;
      v24 = L"*/*";
      v25 = 8;
LABEL_20:
      memcpy_s(v22, v25, v24, v23);
      goto LABEL_14;
    }
    return (unsigned int)-2147024882;
  }
  v11 = v10 - 10;
  if ( !v11 )
  {
    if ( a4 )
    {
      v40 = (CDwnPost *)*((_QWORD *)this + 4);
      if ( v40 )
      {
        AcceptHeadersForCategory = CDwnPost::GetHashString(v40, a3);
        *(_DWORD *)v5 = AcceptHeadersForCategory == 0;
      }
    }
    return AcceptHeadersForCategory;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    v36 = *((_QWORD *)this + 4);
    if ( !v36 )
      return AcceptHeadersForCategory;
    v37 = *(const wchar_t **)(v36 + 56);
    if ( !v37 )
      return (unsigned int)-2146697198;
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = (unsigned int)(2 * v38 + 2);
    v22 = (unsigned __int16 *)CoTaskMemAlloc(v39);
    *a3 = v22;
    if ( v22 )
    {
      v23 = (unsigned int)v39;
      v24 = v37;
      v25 = (unsigned int)v39;
      goto LABEL_20;
    }
    return (unsigned int)-2147024882;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    v32 = (struct IUri *)*((_QWORD *)this + 5);
    if ( v32 )
    {
      CUString::CUString((CUString *)v41, v32, Uri_PROPERTY_ABSOLUTE_URI, &v43);
      AcceptHeadersForCategory = v43;
      if ( !v43 )
      {
        v33 = (unsigned int)(2 * v42 + 2);
        v34 = (unsigned __int16 *)CoTaskMemAlloc(v33);
        v35 = v34;
        if ( v34 )
        {
          memcpy_s(v34, v33, (const void *const)v41[4], v33);
          *a3 = v35;
          *(_DWORD *)v5 = 1;
        }
        else
        {
          AcceptHeadersForCategory = -2147024882;
        }
      }
      v41[0] = &CUString::`vftable';
      CUString::Set((CUString *)v41, 0, Uri_PROPERTY_RAW_URI);
      return AcceptHeadersForCategory;
    }
    return (unsigned int)-2146697198;
  }
  v14 = v13 - 4;
  if ( v14 )
  {
    if ( v14 == 2 )
    {
      if ( a4 )
      {
        v15 = *((_QWORD *)this + 3);
        AcceptHeadersForCategory = -2146697198;
        if ( v15 )
        {
          v16 = *(_WORD **)(v15 + 680);
          if ( v16 )
          {
            AcceptHeadersForCategory = -2147024882;
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            v18 = (unsigned int)(2 * v17 + 2);
            v19 = (unsigned __int16 *)CoTaskMemAlloc(v18);
            v20 = v19;
            if ( v19 )
            {
              memcpy_s(v19, (unsigned int)v18, v16, (unsigned int)v18);
              *a3 = v20;
              AcceptHeadersForCategory = 0;
LABEL_14:
              *(_DWORD *)v5 = 1;
            }
          }
        }
      }
    }
  }
  else if ( a4 )
  {
    v26 = *((_QWORD *)this + 3);
    AcceptHeadersForCategory = -2146697198;
    pbstr = 0;
    v27 = *(CMarkup **)(v26 + 112);
    if ( v27 )
    {
      if ( CMarkup::GetRefererUrl(v27, &pbstr) >= 0 )
      {
        v28 = pbstr;
        AcceptHeadersForCategory = -2147024882;
        v29 = 2 * SysStringLen(pbstr) + 2;
        v30 = (unsigned __int16 *)CoTaskMemAlloc(v29);
        v31 = v30;
        if ( v30 )
        {
          memcpy_s(v30, (unsigned int)v29, v28, (unsigned int)v29);
          *a3 = v31;
          AcceptHeadersForCategory = 0;
          *(_DWORD *)v5 = 1;
        }
        SysFreeString(v28);
      }
    }
  }
  return AcceptHeadersForCategory;
}

```

## disassembly

```asm
0x180666da0  push    rbp
0x180666da2  push    rbx
0x180666da3  push    rsi
0x180666da4  push    rdi
0x180666da5  push    r12
0x180666da7  push    r13
0x180666da9  push    r14
0x180666dab  push    r15
0x180666dad  mov     rbp, rsp
0x180666db0  sub     rsp, 58h
0x180666db4  mov     r14, [rbp+pbstr]
0x180666db8  xor     r13d, r13d
0x180666dbb  mov     ebx, r13d
0x180666dbe  mov     edi, r9d
0x180666dc1  mov     [rbp+arg_8], ebx
0x180666dc4  mov     r12, r8
0x180666dc7  mov     rsi, rcx
0x180666dca  mov     [r14], r13d
0x180666dcd  sub     edx, 2
0x180666dd0  jz      loc_180666E7D
0x180666dd6  sub     edx, 0Ah
0x180666dd9  jz      loc_180667036
0x180666ddf  sub     edx, 1
0x180666de2  jz      loc_180666FD8
0x180666de8  sub     edx, 1
0x180666deb  jz      loc_180666F4B
0x180666df1  sub     edx, 4
0x180666df4  jz      loc_180666EC7
0x180666dfa  cmp     edx, 2
0x180666dfd  jnz     short loc_180666E6A
0x180666dff  cmp     r9d, 1
0x180666e03  jb      short loc_180666E6A
0x180666e05  mov     rdi, [rcx+18h]
0x180666e09  mov     ebx, 800C0012h
0x180666e0e  test    rdi, rdi
0x180666e11  jz      short loc_180666E6A
0x180666e13  mov     rdi, [rdi+2A8h]
0x180666e1a  test    rdi, rdi
0x180666e1d  jz      short loc_180666E6A
0x180666e1f  mov     ebx, 8007000Eh
0x180666e24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180666e28  inc     rax
0x180666e2b  cmp     [rdi+rax*2], r13w
0x180666e30  jnz     short loc_180666E28
0x180666e32  lea     eax, ds:2[rax*2]
0x180666e39  mov     ecx, eax; cb
0x180666e3b  mov     esi, eax
0x180666e3d  call    cs:__imp_CoTaskMemAlloc
0x180666e43  mov     r15, rax
0x180666e46  test    rax, rax
0x180666e49  jz      short loc_180666E6A
0x180666e4b  mov     r9d, esi; SourceSize
0x180666e4e  mov     r8, rdi; Source
0x180666e51  mov     edx, esi; DestinationSize
0x180666e53  mov     rcx, rax; Destination
0x180666e56  call    cs:__imp_memcpy_s
0x180666e5c  mov     [r12], r15
0x180666e60  mov     ebx, r13d
0x180666e63  mov     dword ptr [r14], 1
0x180666e6a  mov     eax, ebx
0x180666e6c  add     rsp, 58h
0x180666e70  pop     r15
0x180666e72  pop     r14
0x180666e74  pop     r13
0x180666e76  pop     r12
0x180666e78  pop     rdi
0x180666e79  pop     rsi
0x180666e7a  pop     rbx
0x180666e7b  pop     rbp
0x180666e7c  retn
0x180666e7d  cmp     edi, 1
0x180666e80  jb      short loc_180666E6A
0x180666e82  lea     rcx, ?FEATURE_MIME_USE_BUILTIN_ACCEPT_HEADERS@FCK@@3VCFeatureControlKey@@A; this
0x180666e89  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180666e8e  test    eax, eax
0x180666e90  jz      loc_180667066
0x180666e96  mov     edi, 8
0x180666e9b  mov     ecx, edi; cb
0x180666e9d  call    cs:__imp_CoTaskMemAlloc
0x180666ea3  mov     [r12], rax
0x180666ea7  test    rax, rax
0x180666eaa  jz      loc_180667097
0x180666eb0  mov     r9d, edi; SourceSize
0x180666eb3  lea     r8, asc_181443B08; "*/*"
0x180666eba  mov     edx, edi; DestinationSize
0x180666ebc  mov     rcx, rax; Destination
0x180666ebf  call    cs:__imp_memcpy_s
0x180666ec5  jmp     short loc_180666E63
0x180666ec7  cmp     edi, 1
0x180666eca  jb      short loc_180666E6A
0x180666ecc  mov     rax, [rcx+18h]
0x180666ed0  mov     ebx, 800C0012h
0x180666ed5  mov     [rbp+pbstr], r13
0x180666ed9  mov     rcx, [rax+70h]; this
0x180666edd  test    rcx, rcx
0x180666ee0  jz      short loc_180666E6A
0x180666ee2  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x180666ee6  call    ?GetRefererUrl@CMarkup@@QEBAJPEAPEAG@Z; CMarkup::GetRefererUrl(ushort * *)
0x180666eeb  test    eax, eax
0x180666eed  js      loc_180666E6A
0x180666ef3  mov     rdi, [rbp+pbstr]
0x180666ef7  mov     ebx, 8007000Eh
0x180666efc  mov     rcx, rdi; pbstr
0x180666eff  call    cs:__imp_SysStringLen
0x180666f05  lea     eax, ds:2[rax*2]
0x180666f0c  mov     ecx, eax; cb
0x180666f0e  mov     esi, eax
0x180666f10  call    cs:__imp_CoTaskMemAlloc
0x180666f16  mov     r15, rax
0x180666f19  test    rax, rax
0x180666f1c  jz      short loc_180666F3D
0x180666f1e  mov     r9d, esi; SourceSize
0x180666f21  mov     r8, rdi; Source
0x180666f24  mov     edx, esi; DestinationSize
0x180666f26  mov     rcx, rax; Destination
0x180666f29  call    cs:__imp_memcpy_s
0x180666f2f  mov     [r12], r15
0x180666f33  mov     ebx, r13d
0x180666f36  mov     dword ptr [r14], 1
0x180666f3d  mov     rcx, rdi; bstrString
0x180666f40  call    cs:__imp_SysFreeString
0x180666f46  jmp     loc_180666E6A
0x180666f4b  cmp     edi, 1
0x180666f4e  jb      loc_180666E6A
0x180666f54  mov     rdx, [rcx+28h]; struct IUri *
0x180666f58  test    rdx, rdx
0x180666f5b  jz      loc_18066702C
0x180666f61  lea     r9, [rbp+arg_8]; int *
0x180666f65  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180666f68  lea     rcx, [rbp+var_38]; this
0x180666f6c  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180666f71  mov     ebx, [rbp+arg_8]
0x180666f74  test    ebx, ebx
0x180666f76  jnz     short loc_180666FB9
0x180666f78  mov     eax, [rbp+var_10]
0x180666f7b  lea     eax, ds:2[rax*2]
0x180666f82  mov     ecx, eax; cb
0x180666f84  mov     edi, eax
0x180666f86  call    cs:__imp_CoTaskMemAlloc
0x180666f8c  mov     rsi, rax
0x180666f8f  test    rax, rax
0x180666f92  jnz     short loc_180666F9B
0x180666f94  mov     ebx, 8007000Eh
0x180666f99  jmp     short loc_180666FB9
0x180666f9b  mov     r8, [rbp+Source]; Source
0x180666f9f  mov     r9, rdi; SourceSize
0x180666fa2  mov     rdx, rdi; DestinationSize
0x180666fa5  mov     rcx, rsi; Destination
0x180666fa8  call    cs:__imp_memcpy_s
0x180666fae  mov     [r12], rsi
0x180666fb2  mov     dword ptr [r14], 1
0x180666fb9  xor     edx, edx; struct IUri *
0x180666fbb  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180666fc2  lea     rcx, [rbp+var_38]; this
0x180666fc6  mov     [rbp+var_38], rax
0x180666fca  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180666fce  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180666fd3  jmp     loc_180666E6A
0x180666fd8  cmp     edi, 1
0x180666fdb  jb      loc_180666E6A
0x180666fe1  mov     rdi, [rcx+20h]
0x180666fe5  test    rdi, rdi
0x180666fe8  jz      loc_180666E6A
0x180666fee  mov     rdi, [rdi+38h]
0x180666ff2  test    rdi, rdi
0x180666ff5  jz      short loc_18066702C
0x180666ff7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180666ffb  inc     rax
0x180666ffe  cmp     [rdi+rax*2], r13w
0x180667003  jnz     short loc_180666FFB
0x180667005  lea     eax, ds:2[rax*2]
0x18066700c  mov     ecx, eax; cb
0x18066700e  mov     esi, eax
0x180667010  call    cs:__imp_CoTaskMemAlloc
0x180667016  mov     [r12], rax
0x18066701a  test    rax, rax
0x18066701d  jz      short loc_180667097
0x18066701f  mov     r9d, esi
0x180667022  mov     r8, rdi
0x180667025  mov     edx, esi
0x180667027  jmp     loc_180666EBC
0x18066702c  mov     ebx, 800C0012h
0x180667031  jmp     loc_180666E6A
0x180667036  cmp     edi, 1
0x180667039  jb      loc_180666E6A
0x18066703f  mov     rcx, [rcx+20h]; this
0x180667043  test    rcx, rcx
0x180667046  jz      loc_180666E6A
0x18066704c  mov     rdx, r12; unsigned __int16 **
0x18066704f  call    ?GetHashString@CDwnPost@@QEAAJPEAPEAG@Z; CDwnPost::GetHashString(ushort * *)
0x180667054  mov     ebx, eax
0x180667056  mov     eax, r13d
0x180667059  test    ebx, ebx
0x18066705b  setz    al
0x18066705e  mov     [r14], eax
0x180667061  jmp     loc_180666E6A
0x180667066  mov     rax, [rsi+18h]
0x18066706a  cmp     dword ptr [rax+0C4h], 9
0x180667071  jl      loc_180666E96
0x180667077  mov     ecx, [rsi+78h]
0x18066707a  mov     r9, r14
0x18066707d  mov     r8d, edi
0x180667080  mov     rdx, r12
0x180667083  call    ?GetAcceptHeadersForCategory@@YAJW4__MIDL___MIDL_itf_urlmonp_0000_0019_0001@@PEAPEAGKPEAK@Z; GetAcceptHeadersForCategory(__MIDL___MIDL_itf_urlmonp_0000_0019_0001,ushort * *,ulong,ulong *)
0x180667088  mov     ebx, eax
0x18066708a  test    eax, eax
0x18066708c  jns     loc_180666E6A
0x180667092  jmp     loc_180666E96
0x180667097  mov     ebx, 8007000Eh
0x18066709c  jmp     loc_180666E6A
```
