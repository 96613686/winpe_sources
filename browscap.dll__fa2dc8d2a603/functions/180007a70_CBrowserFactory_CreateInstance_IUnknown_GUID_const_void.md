# CBrowserFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007a70`
- end: `0x1800081a7`
- name: `?CreateInstance@CBrowserFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1847`
- prototype: `__int64 __fastcall(CBrowserFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x180002498`
- `0x1800037f4`
- `0x180004820`
- `0x180006680`
- `0x1800074ec`
- `0x1800076e8`
- `0x180007968`
- `0x180007a70`
- `0x180008fa8`
- `0x1800099f8`
- `0x180009ab4`
- `0x180009b10`
- `0x180009c40`
- `0x180009d8c`
- `0x18000b1e8`
- `0x18000b640`
- `0x18000b700`
- `0x18000d010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180007cbc`
- `KERNEL32!WideCharToMultiByte` at `0x180007fa3`
- `KERNEL32!WideCharToMultiByte` at `0x180008029`
- `KERNEL32!WideCharToMultiByte` at `0x180007cbc`
- `KERNEL32!WideCharToMultiByte` at `0x180007fa3`
- `KERNEL32!WideCharToMultiByte` at `0x180008029`
- `ole32!CoGetObjectContext` at `0x180007add`
- `ole32!CoGetObjectContext` at `0x180007add`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b1e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dfd`
- `OLEAUT32!__imp_SysAllocString` at `0x180007b1e`
- `OLEAUT32!__imp_SysAllocString` at `0x180007dfd`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b11`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b53`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b11`
- `OLEAUT32!__imp_SysFreeString` at `0x180007b53`
- `OLEAUT32!__imp_VariantInit` at `0x180007ba7`
- `OLEAUT32!__imp_VariantInit` at `0x180007d90`
- `OLEAUT32!__imp_VariantInit` at `0x180007dbe`
- `OLEAUT32!__imp_VariantInit` at `0x180007dcc`
- `OLEAUT32!__imp_VariantInit` at `0x180007ba7`
- `OLEAUT32!__imp_VariantInit` at `0x180007d90`
- `OLEAUT32!__imp_VariantInit` at `0x180007dbe`
- `OLEAUT32!__imp_VariantInit` at `0x180007dcc`
- `OLEAUT32!__imp_VariantClear` at `0x180007bd6`
- `OLEAUT32!__imp_VariantClear` at `0x180007c00`
- `OLEAUT32!__imp_VariantClear` at `0x180007d59`
- `OLEAUT32!__imp_VariantClear` at `0x180007de7`
- `OLEAUT32!__imp_VariantClear` at `0x180007e52`
- `OLEAUT32!__imp_VariantClear` at `0x180008051`
- `OLEAUT32!__imp_VariantClear` at `0x1800080a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800080b1`
- `OLEAUT32!__imp_VariantClear` at `0x1800080c2`
- `OLEAUT32!__imp_VariantClear` at `0x1800080cd`
- `OLEAUT32!__imp_VariantClear` at `0x180008122`
- `OLEAUT32!__imp_VariantClear` at `0x18000812d`
- `OLEAUT32!__imp_VariantClear` at `0x180007bd6`
- `OLEAUT32!__imp_VariantClear` at `0x180007c00`
- `OLEAUT32!__imp_VariantClear` at `0x180007d59`
- `OLEAUT32!__imp_VariantClear` at `0x180007de7`
- `OLEAUT32!__imp_VariantClear` at `0x180007e52`
- `OLEAUT32!__imp_VariantClear` at `0x180008051`
- `OLEAUT32!__imp_VariantClear` at `0x1800080a6`
- `OLEAUT32!__imp_VariantClear` at `0x1800080b1`
- `OLEAUT32!__imp_VariantClear` at `0x1800080c2`
- `OLEAUT32!__imp_VariantClear` at `0x1800080cd`
- `OLEAUT32!__imp_VariantClear` at `0x180008122`
- `OLEAUT32!__imp_VariantClear` at `0x18000812d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007c39`
- `OLEAUT32!__imp_VariantChangeType` at `0x180007c39`

## string_xrefs

- `0x180007bbc`: `HTTP_USER_AGENT`

## pseudocode

```c
__int64 __fastcall CBrowserFactory::CreateInstance(
        CBrowserFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  void **v4; // r15
  bool v6; // dl
  int ServerObject; // edi
  struct CBrowserCap *v8; // rax
  OLECHAR *v9; // rbx
  int v10; // esi
  LONGLONG v11; // rbx
  __int64 v12; // rax
  int v13; // edx
  const char *v14; // rbx
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  struct CBrowserCap *v20; // rax
  StringBuffer *v21; // rax
  CCapMap *v22; // rbx
  bool v23; // r8
  struct CBrowserCap *v24; // r14
  __int64 v25; // rbx
  int v26; // ebx
  __int64 v27; // rax
  int v28; // edx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  void *v32; // rsp
  void *v33; // rsp
  const char *v34; // rbx
  __int64 v35; // rax
  int v36; // edx
  unsigned __int64 v37; // rax
  __int64 v38; // rcx
  unsigned __int64 v39; // rcx
  void *v40; // rsp
  void *v41; // rsp
  char *v42; // rdx
  unsigned int v44; // ebx
  _BYTE v45[32]; // [rsp+0h] [rbp-40h] BYREF
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  LONGLONG v47; // [rsp+48h] [rbp+8h] BYREF
  struct CBrowserCap *v48; // [rsp+50h] [rbp+10h] BYREF
  LPVOID ppv[2]; // [rsp+58h] [rbp+18h] BYREF
  __int64 *v50; // [rsp+68h] [rbp+28h] BYREF
  VARIANTARG pvarg; // [rsp+70h] [rbp+30h] BYREF
  _QWORD v52[2]; // [rsp+88h] [rbp+48h] BYREF
  VARIANTARG v53; // [rsp+98h] [rbp+58h] BYREF
  VARIANTARG v54; // [rsp+B0h] [rbp+70h] BYREF
  void **v55; // [rsp+C8h] [rbp+88h]
  VARIANTARG v56; // [rsp+D0h] [rbp+90h] BYREF
  VARIANTARG v57; // [rsp+F0h] [rbp+B0h] BYREF
  VARIANTARG v58; // [rsp+110h] [rbp+D0h] BYREF
  void *v59[2]; // [rsp+128h] [rbp+E8h] BYREF
  __int128 v60; // [rsp+138h] [rbp+F8h]
  __int64 v61; // [rsp+148h] [rbp+108h]

  v4 = a4;
  v55 = a4;
  *(_OWORD *)v59 = 0;
  v60 = 0;
  v61 = 0;
  v50 = 0;
  *a4 = 0;
  ppv[0] = 0;
  if ( CoGetObjectContext(&IID_IObjectContext, ppv) )
  {
    ServerObject = -2147164156;
  }
  else
  {
    *(_QWORD *)MultiByteStr = 0;
    ServerObject = (**(__int64 (__fastcall ***)(LPVOID, GUID *, CHAR *))ppv[0])(
                     ppv[0],
                     &IID_IGetContextProperties,
                     MultiByteStr);
    if ( ServerObject >= 0 )
    {
      SysFreeString(0);
      v8 = (struct CBrowserCap *)SysAllocString(L"Request");
      v9 = (OLECHAR *)v8;
      v48 = v8;
      if ( !v8 )
        ATL::AtlThrowImpl(-2147024882);
      ServerObject = CContext::GetServerObject(
                       *(struct IGetContextProperties **)MultiByteStr,
                       (unsigned __int16 *)v8,
                       &IID_IRequest,
                       v59);
      SysFreeString(v9);
    }
    if ( *(_QWORD *)MultiByteStr )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)MultiByteStr + 16LL))(*(_QWORD *)MultiByteStr);
  }
  if ( ppv[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
  if ( ServerObject < 0 )
    goto LABEL_70;
  String::String((String *)v52, v6);
  v47 = 0;
  VariantInit(&pvarg);
  v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, LONGLONG *))(*(_QWORD *)v59[0] + 56LL))(
          v59[0],
          L"HTTP_USER_AGENT",
          &v47);
  if ( v10 < 0 )
  {
    VariantClear(&pvarg);
    if ( v47 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v47 + 16LL))(v47);
LABEL_69:
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v52);
    ServerObject = v10;
LABEL_70:
    CContext::~CContext((CContext *)v59);
    return (unsigned int)ServerObject;
  }
  v11 = v47;
  VariantClear(&pvarg);
  pvarg.vt = 9;
  pvarg.llVal = v11;
  if ( v11 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v11 + 8LL))(v11);
  VariantChangeType(&pvarg, &pvarg, 0, 8u);
  if ( !pvarg.llVal )
    goto LABEL_22;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(pvarg.llVal + 2 * v12) );
  v13 = v12 + 1;
  if ( (int)v12 + 1 <= 0x3FFFFFFF )
  {
    v15 = 2LL * v13;
    v16 = v15 + 15;
    if ( v15 + 15 < v15 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
    v18 = alloca(v17);
    v19 = alloca(v17);
    if ( v45 == (_BYTE *)-64LL )
    {
      v14 = 0;
    }
    else
    {
      MultiByteStr[0] = 0;
      v14 = (const char *)((unsigned __int64)MultiByteStr
                         & -(__int64)(WideCharToMultiByte(3u, 0, pvarg.bstrVal, -1, MultiByteStr, 2 * v13, 0, 0) != 0));
    }
  }
  else
  {
LABEL_22:
    v14 = 0;
  }
  v20 = (struct CBrowserCap *)operator new(0x28u);
  v48 = v20;
  if ( v20 )
    v21 = StringBuffer::StringBuffer(v20, v14);
  else
    v21 = 0;
  TRefPtr<StringBuffer>::Set(v52, v21);
  CBrwCapModule::Lock((CBrwCapModule *)&_Module);
  v22 = qword_180012920;
  String::String((String *)ppv, *(const char **)(v52[0] + 32LL), v23);
  v24 = CCapMap::LookUp(v22, (const struct String *)ppv);
  v48 = v24;
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(ppv);
  CBrwCapModule::Unlock((CBrwCapModule *)&_Module);
  if ( !v24 )
  {
    VariantClear(&pvarg);
    if ( v47 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v47 + 16LL))(v47);
    TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v52);
    ServerObject = -2147467259;
    goto LABEL_70;
  }
  VariantInit(&v56);
  if ( (*(int (__fastcall **)(void *, __int64 **))(*(_QWORD *)v59[0] + 104LL))(v59[0], &v50) >= 0 )
  {
    *(_QWORD *)MultiByteStr = 0;
    VariantInit(&v54);
    VariantInit(&v58);
    ppv[0] = 0;
    v25 = *v50;
    v53.vt = 0;
    VariantClear(&v53);
    v53.vt = 8;
    v53.llVal = (LONGLONG)SysAllocString(L"BROWSCAP");
    if ( !v53.llVal )
    {
      v53.vt = 10;
      v53.lVal = -2147024882;
      ATL::AtlThrowImpl(-2147024882);
    }
    v57 = v53;
    v26 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *))(v25 + 56))(v50, &v57, &v56);
    VariantClear(&v53);
    if ( v26 >= 0 && v56.vt == 9 )
    {
      v10 = CBrowserCap::Clone(v24, &v48);
      if ( v10 < 0
        || ((**(void (__fastcall ***)(LONGLONG, GUID *, CHAR *))v56.llVal)(v56.llVal, &IID_IReadCookie, MultiByteStr),
            v10 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)MultiByteStr + 72LL))(
                    *(_QWORD *)MultiByteStr,
                    ppv),
            v10 < 0) )
      {
        v24 = v48;
      }
      else
      {
        v24 = v48;
        while ( !(*(unsigned int (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)ppv[0] + 24LL))(
                   ppv[0],
                   1,
                   &v54) )
        {
          v57 = v54;
          v10 = (*(__int64 (__fastcall **)(_QWORD, VARIANTARG *, VARIANTARG *))(**(_QWORD **)MultiByteStr + 56LL))(
                  *(_QWORD *)MultiByteStr,
                  &v57,
                  &v58);
          if ( !v58.llVal )
            goto LABEL_51;
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)(v58.llVal + 2 * v27) );
          v28 = v27 + 1;
          if ( (int)v27 + 1 > 0x3FFFFFFF )
            goto LABEL_51;
          v29 = 2LL * (int)v27 + 2;
          v30 = v29 + 15;
          if ( v29 + 15 < v29 )
            v30 = 0xFFFFFFFFFFFFFF0LL;
          v31 = v30 & 0xFFFFFFFFFFFFFFF0uLL;
          v32 = alloca(v31);
          v33 = alloca(v31);
          if ( v45 == (_BYTE *)-64LL )
          {
LABEL_51:
            v34 = 0;
          }
          else
          {
            MultiByteStr[0] = 0;
            v34 = (const char *)((unsigned __int64)MultiByteStr
                               & -(__int64)(WideCharToMultiByte(3u, 0, v58.bstrVal, -1, MultiByteStr, 2 * v28, 0, 0) != 0));
          }
          if ( !v54.llVal )
            goto LABEL_60;
          v35 = -1;
          do
            ++v35;
          while ( *(_WORD *)(v54.llVal + 2 * v35) );
          v36 = v35 + 1;
          if ( (int)v35 + 1 > 0x3FFFFFFF )
            goto LABEL_60;
          v37 = 2LL * (int)v35 + 2;
          v38 = v37 + 15;
          if ( v37 + 15 < v37 )
            v38 = 0xFFFFFFFFFFFFFF0LL;
          v39 = v38 & 0xFFFFFFFFFFFFFFF0uLL;
          v40 = alloca(v39);
          v41 = alloca(v39);
          if ( v45 == (_BYTE *)-64LL )
          {
LABEL_60:
            v42 = 0;
          }
          else
          {
            MultiByteStr[0] = 0;
            v42 = (char *)((unsigned __int64)MultiByteStr
                         & -(__int64)(WideCharToMultiByte(3u, 0, v54.bstrVal, -1, MultiByteStr, 2 * v36, 0, 0) != 0));
          }
          CBrowserCap::AddProperty(v24, v42, v34, 1);
          VariantClear(&v54);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
        v4 = v55;
      }
    }
    (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
    if ( *(_QWORD *)MultiByteStr )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)MultiByteStr + 16LL))(*(_QWORD *)MultiByteStr);
    VariantClear(&v58);
    VariantClear(&v54);
    if ( v10 < 0 )
    {
      VariantClear(&v56);
      VariantClear(&pvarg);
      if ( v47 )
        (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v47 + 16LL))(v47);
      goto LABEL_69;
    }
  }
  v44 = (**(__int64 (__fastcall ***)(struct CBrowserCap *, const struct _GUID *, void **))v24)(v24, a3, v4);
  VariantClear(&v56);
  VariantClear(&pvarg);
  if ( v47 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v47 + 16LL))(v47);
  TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(v52);
  CContext::~CContext((CContext *)v59);
  return v44;
}

```

## disassembly

```asm
0x180007a70  push    rbp
0x180007a72  push    rbx
0x180007a73  push    rsi
0x180007a74  push    rdi
0x180007a75  push    r12
0x180007a77  push    r13
0x180007a79  push    r14
0x180007a7b  push    r15
0x180007a7d  sub     rsp, 168h
0x180007a84  lea     rbp, [rsp+40h]
0x180007a89  mov     rax, cs:__security_cookie
0x180007a90  xor     rax, rbp
0x180007a93  mov     [rbp+160h+var_50], rax
0x180007a9a  mov     r15, r9
0x180007a9d  mov     [rbp+160h+var_D8], r9
0x180007aa4  mov     r12, r8
0x180007aa7  xorps   xmm0, xmm0
0x180007aaa  movdqu  xmmword ptr [rbp+160h+var_78], xmm0
0x180007ab2  xorps   xmm1, xmm1
0x180007ab5  movdqu  [rbp+160h+var_68], xmm1
0x180007abd  xor     r13d, r13d
0x180007ac0  mov     [rbp+160h+var_58], r13
0x180007ac7  mov     [rbp+160h+var_138], r13
0x180007acb  mov     [r9], r13
0x180007ace  mov     [rbp+160h+ppv], r13
0x180007ad2  lea     rdx, [rbp+160h+ppv]; ppv
0x180007ad6  lea     rcx, IID_IObjectContext; riid
0x180007add  call    cs:__imp_CoGetObjectContext
0x180007ae3  test    eax, eax
0x180007ae5  jnz     loc_180007B72
0x180007aeb  mov     qword ptr [rbp+160h+MultiByteStr], r13
0x180007aef  mov     rcx, [rbp+160h+ppv]
0x180007af3  mov     rax, [rcx]
0x180007af6  lea     r8, [rbp+160h+MultiByteStr]
0x180007afa  lea     rdx, IID_IGetContextProperties
0x180007b01  mov     rax, [rax]
0x180007b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b09  mov     edi, eax
0x180007b0b  test    eax, eax
0x180007b0d  js      short loc_180007B5A
0x180007b0f  xor     ecx, ecx; bstrString
0x180007b11  call    cs:__imp_SysFreeString
0x180007b17  lea     rcx, psz; "Request"
0x180007b1e  call    cs:__imp_SysAllocString
0x180007b24  mov     rbx, rax
0x180007b27  mov     [rbp+160h+var_150], rax
0x180007b2b  test    rax, rax
0x180007b2e  jz      loc_18000819C
0x180007b34  lea     r9, [rbp+160h+var_78]; void **
0x180007b3b  lea     r8, IID_IRequest; struct _GUID *
0x180007b42  mov     rdx, rax; unsigned __int16 *
0x180007b45  mov     rcx, qword ptr [rbp+160h+MultiByteStr]; struct IGetContextProperties *
0x180007b49  call    ?GetServerObject@CContext@@SAJPEAUIGetContextProperties@@PEAGAEBU_GUID@@PEAPEAX@Z; CContext::GetServerObject(IGetContextProperties *,ushort *,_GUID const &,void * *)
0x180007b4e  mov     edi, eax
0x180007b50  mov     rcx, rbx; bstrString
0x180007b53  call    cs:__imp_SysFreeString
0x180007b59  nop
0x180007b5a  mov     rcx, qword ptr [rbp+160h+MultiByteStr]
0x180007b5e  test    rcx, rcx
0x180007b61  jz      short loc_180007B70
0x180007b63  mov     rax, [rcx]
0x180007b66  mov     rax, [rax+10h]
0x180007b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b6f  nop
0x180007b70  jmp     short loc_180007B77
0x180007b72  mov     edi, 8004E004h
0x180007b77  mov     rcx, [rbp+160h+ppv]
0x180007b7b  test    rcx, rcx
0x180007b7e  jz      short loc_180007B8D
0x180007b80  mov     rax, [rcx]
0x180007b83  mov     rax, [rax+10h]
0x180007b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b8c  nop
0x180007b8d  test    edi, edi
0x180007b8f  js      loc_1800080F5
0x180007b95  lea     rcx, [rbp+160h+var_118]; this
0x180007b99  call    ??0String@@QEAA@_N@Z; String::String(bool)
0x180007b9e  nop
0x180007b9f  mov     [rbp+160h+var_158], r13
0x180007ba3  lea     rcx, [rbp+160h+pvarg]; pvarg
0x180007ba7  call    cs:__imp_VariantInit
0x180007bad  nop
0x180007bae  mov     rcx, [rbp+160h+var_78]
0x180007bb5  mov     rax, [rcx]
0x180007bb8  lea     r8, [rbp+160h+var_158]
0x180007bbc  lea     rdx, aHttpUserAgent; "HTTP_USER_AGENT"
0x180007bc3  mov     rax, [rax+38h]
0x180007bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bcc  mov     esi, eax
0x180007bce  test    eax, eax
0x180007bd0  jns     short loc_180007BF8
0x180007bd2  lea     rcx, [rbp+160h+pvarg]; pvarg
0x180007bd6  call    cs:__imp_VariantClear
0x180007bdc  nop
0x180007bdd  mov     rcx, [rbp+160h+var_158]
0x180007be1  test    rcx, rcx
0x180007be4  jz      short loc_180007BF3
0x180007be6  mov     rdx, [rcx]
0x180007be9  mov     rax, [rdx+10h]
0x180007bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf2  nop
0x180007bf3  jmp     loc_1800080EA
0x180007bf8  mov     rbx, [rbp+160h+var_158]
0x180007bfc  lea     rcx, [rbp+160h+pvarg]; pvarg
0x180007c00  call    cs:__imp_VariantClear
0x180007c06  mov     edi, 9
0x180007c0b  mov     word ptr [rbp+160h+pvarg], di
0x180007c0f  mov     qword ptr [rbp+160h+pvarg+8], rbx
0x180007c13  test    rbx, rbx
0x180007c16  jz      short loc_180007C28
0x180007c18  mov     rax, [rbx]
0x180007c1b  mov     rcx, rbx
0x180007c1e  mov     rax, [rax+8]
0x180007c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c27  nop
0x180007c28  mov     r9d, 8; vt
0x180007c2e  xor     r8d, r8d; wFlags
0x180007c31  lea     rdx, [rbp+160h+pvarg]; pvarSrc
0x180007c35  lea     rcx, [rbp+160h+pvarg]; pvargDest
0x180007c39  call    cs:__imp_VariantChangeType
0x180007c3f  mov     r8, qword ptr [rbp+160h+pvarg+8]
0x180007c43  mov     r10, 0FFFFFFFFFFFFFF0h
0x180007c4d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180007c51  test    r8, r8
0x180007c54  jz      short loc_180007C6E
0x180007c56  mov     rax, r9
0x180007c59  inc     rax
0x180007c5c  cmp     [r8+rax*2], r13w
0x180007c61  jnz     short loc_180007C59
0x180007c63  lea     edx, [rax+1]
0x180007c66  cmp     edx, 3FFFFFFFh
0x180007c6c  jle     short loc_180007C73
0x180007c6e  mov     rbx, r13
0x180007c71  jmp     short loc_180007CD4
0x180007c73  movsxd  rax, edx
0x180007c76  add     rax, rax
0x180007c79  lea     rcx, [rax+0Fh]
0x180007c7d  cmp     rcx, rax
0x180007c80  ja      short loc_180007C85
0x180007c82  mov     rcx, r10
0x180007c85  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180007c89  mov     rax, rcx
0x180007c8c  call    _alloca_probe
0x180007c91  sub     rsp, rcx
0x180007c94  lea     rdi, [rsp+1A0h+MultiByteStr]
0x180007c99  test    rdi, rdi
0x180007c9c  jz      short loc_180007CCC
0x180007c9e  mov     [rdi], r13b
0x180007ca1  lea     eax, [rdx+rdx]
0x180007ca4  mov     [rsp+1A0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180007ca9  mov     [rsp+1A0h+lpDefaultChar], r13; lpDefaultChar
0x180007cae  mov     [rsp+1A0h+cbMultiByte], eax; cbMultiByte
0x180007cb2  mov     [rsp+1A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180007cb7  xor     edx, edx; dwFlags
0x180007cb9  lea     ecx, [rdx+3]; CodePage
0x180007cbc  call    cs:__imp_WideCharToMultiByte
0x180007cc2  neg     eax
0x180007cc4  sbb     rbx, rbx
0x180007cc7  and     rbx, rdi
0x180007cca  jmp     short loc_180007CCF
0x180007ccc  mov     rbx, r13
0x180007ccf  mov     edi, 9
0x180007cd4  mov     ecx, 28h ; '('; unsigned __int64
0x180007cd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007cde  mov     [rbp+160h+var_150], rax
0x180007ce2  test    rax, rax
0x180007ce5  jz      short loc_180007CF4
0x180007ce7  mov     rdx, rbx; char *
0x180007cea  mov     rcx, rax; this
0x180007ced  call    ??0StringBuffer@@QEAA@PEBD@Z; StringBuffer::StringBuffer(char const *)
0x180007cf2  jmp     short loc_180007CF7
0x180007cf4  mov     rax, r13
0x180007cf7  mov     rdx, rax
0x180007cfa  lea     rcx, [rbp+160h+var_118]
0x180007cfe  call    ?Set@?$TRefPtr@VStringBuffer@@@@QEAAXPEAVStringBuffer@@@Z; TRefPtr<StringBuffer>::Set(StringBuffer *)
0x180007d03  lea     rcx, ?_Module@@3VCBrwCapModule@@A; this
0x180007d0a  call    ?Lock@CBrwCapModule@@UEAAJXZ; CBrwCapModule::Lock(void)
0x180007d0f  mov     rbx, cs:qword_180012920
0x180007d16  mov     rdx, [rbp+160h+var_118]
0x180007d1a  mov     rdx, [rdx+20h]; char *
0x180007d1e  lea     rcx, [rbp+160h+ppv]; this
0x180007d22  call    ??0String@@QEAA@PEBD_N@Z; String::String(char const *,bool)
0x180007d27  nop
0x180007d28  lea     rdx, [rbp+160h+ppv]; struct String *
0x180007d2c  mov     rcx, rbx; this
0x180007d2f  call    ?LookUp@CCapMap@@QEAAPEAVCBrowserCap@@AEBVString@@@Z; CCapMap::LookUp(String const &)
0x180007d34  mov     r14, rax
0x180007d37  mov     [rbp+160h+var_150], rax
0x180007d3b  lea     rcx, [rbp+160h+ppv]
0x180007d3f  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180007d44  lea     rcx, ?_Module@@3VCBrwCapModule@@A; this
0x180007d4b  call    ?Unlock@CBrwCapModule@@UEAAJXZ; CBrwCapModule::Unlock(void)
0x180007d50  test    r14, r14
0x180007d53  jnz     short loc_180007D89
0x180007d55  lea     rcx, [rbp+160h+pvarg]; pvarg
0x180007d59  call    cs:__imp_VariantClear
0x180007d5f  nop
0x180007d60  mov     rcx, [rbp+160h+var_158]
0x180007d64  test    rcx, rcx
0x180007d67  jz      short loc_180007D76
0x180007d69  mov     rax, [rcx]
0x180007d6c  mov     rax, [rax+10h]
0x180007d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d75  nop
0x180007d76  lea     rcx, [rbp+160h+var_118]
0x180007d7a  call    ??1?$TRefPtr@VCMonitorNotify@@@@QEAA@XZ; TRefPtr<CMonitorNotify>::~TRefPtr<CMonitorNotify>(void)
0x180007d7f  mov     edi, 80004005h
0x180007d84  jmp     loc_1800080F5
0x180007d89  lea     rcx, [rbp+160h+var_D0]; pvarg
0x180007d90  call    cs:__imp_VariantInit
0x180007d96  nop
0x180007d97  mov     rcx, [rbp+160h+var_78]
0x180007d9e  mov     rax, [rcx]
0x180007da1  lea     rdx, [rbp+160h+var_138]
0x180007da5  mov     rax, [rax+68h]
0x180007da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dae  test    eax, eax
0x180007db0  js      loc_180008105
0x180007db6  mov     qword ptr [rbp+160h+MultiByteStr], r13
0x180007dba  lea     rcx, [rbp+160h+var_F0]; pvarg
0x180007dbe  call    cs:__imp_VariantInit
0x180007dc4  nop
0x180007dc5  lea     rcx, [rbp+160h+var_90]; pvarg
0x180007dcc  call    cs:__imp_VariantInit
0x180007dd2  nop
0x180007dd3  mov     [rbp+160h+ppv], r13
0x180007dd7  mov     rax, [rbp+160h+var_138]
0x180007ddb  mov     rbx, [rax]
0x180007dde  mov     word ptr [rbp+160h+var_108], r13w
0x180007de3  lea     rcx, [rbp+160h+var_108]; pvarg
0x180007de7  call    cs:__imp_VariantClear
0x180007ded  mov     eax, 8
0x180007df2  mov     word ptr [rbp+160h+var_108], ax
0x180007df6  lea     rcx, aBrowscap; "BROWSCAP"
0x180007dfd  call    cs:__imp_SysAllocString
0x180007e03  mov     dword ptr [rbp+160h+var_108+8], eax
0x180007e06  mov     rcx, rax
0x180007e09  sar     rcx, 20h
0x180007e0d  mov     dword ptr [rbp+160h+var_108+0Ch], ecx
0x180007e10  test    rax, rax
0x180007e13  jz      loc_180008185
0x180007e19  movups  xmm0, xmmword ptr [rbp+160h+var_108]
0x180007e1d  movaps  [rbp+160h+var_B0], xmm0
0x180007e24  movsd   xmm1, qword ptr [rbp+160h+var_108+10h]
0x180007e29  movsd   [rbp+160h+var_A0], xmm1
0x180007e31  lea     r8, [rbp+160h+var_D0]
0x180007e38  lea     rdx, [rbp+160h+var_B0]
0x180007e3f  mov     rcx, [rbp+160h+var_138]
0x180007e43  mov     rax, [rbx+38h]
0x180007e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4c  mov     ebx, eax
0x180007e4e  lea     rcx, [rbp+160h+var_108]; pvarg
0x180007e52  call    cs:__imp_VariantClear
0x180007e58  shr     ebx, 1Fh
0x180007e5b  test    bl, bl
0x180007e5d  jnz     loc_180008079
0x180007e63  cmp     word ptr [rbp+160h+var_D0], di
0x180007e6a  jnz     loc_180008079
0x180007e70  lea     rdx, [rbp+160h+var_150]; struct CBrowserCap **
0x180007e74  mov     rcx, r14; this
0x180007e77  call    ?Clone@CBrowserCap@@QEAAJPEAPEAV1@@Z; CBrowserCap::Clone(CBrowserCap * *)
0x180007e7c  mov     esi, eax
0x180007e7e  test    eax, eax
0x180007e80  js      loc_180008075
0x180007e86  mov     rcx, qword ptr [rbp+160h+var_D0+8]
0x180007e8d  mov     rax, [rcx]
0x180007e90  lea     r8, [rbp+160h+MultiByteStr]
0x180007e94  lea     rdx, IID_IReadCookie
0x180007e9b  mov     rax, [rax]
0x180007e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea3  mov     rcx, qword ptr [rbp+160h+MultiByteStr]
0x180007ea7  mov     rax, [rcx]
0x180007eaa  lea     rdx, [rbp+160h+ppv]
0x180007eae  mov     rax, [rax+48h]
0x180007eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb7  mov     esi, eax
0x180007eb9  test    eax, eax
0x180007ebb  js      loc_180008075
0x180007ec1  mov     r14, [rbp+160h+var_150]
0x180007ec5  mov     r15, 0FFFFFFFFFFFFFF0h
0x180007ecf  mov     rcx, [rbp+160h+ppv]
0x180007ed3  mov     rax, [rcx]
0x180007ed6  xor     r9d, r9d
0x180007ed9  lea     r8, [rbp+160h+var_F0]
0x180007edd  lea     edx, [r9+1]
0x180007ee1  mov     rax, [rax+18h]
0x180007ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eea  test    eax, eax
0x180007eec  jnz     loc_18000805C
0x180007ef2  movups  xmm0, xmmword ptr [rbp+160h+var_F0]
0x180007ef6  movaps  [rbp+160h+var_B0], xmm0
0x180007efd  movsd   xmm1, qword ptr [rbp+160h+var_F0+10h]
0x180007f05  movsd   [rbp+160h+var_A0], xmm1
0x180007f0d  mov     rcx, qword ptr [rbp+160h+MultiByteStr]
0x180007f11  mov     rax, [rcx]
0x180007f14  lea     r8, [rbp+160h+var_90]
0x180007f1b  lea     rdx, [rbp+160h+var_B0]
0x180007f22  mov     rax, [rax+38h]
0x180007f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2b  mov     esi, eax
  ... truncated ...
```
