# MFCopyStreamMetadata

- ea: `0x180049a9c`
- end: `0x180049f66`
- name: `MFCopyStreamMetadata`
- size: `1226`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800494cc`

## callees

- `0x1800035c0`
- `0x180003690`
- `0x180004a40`
- `0x180007000`
- `0x180008050`
- `0x1800085a0`
- `0x180009230`
- `0x18000eec0`
- `0x18000f0a4`
- `0x1800153ac`
- `0x18001a330`
- `0x18001c280`
- `0x180049a9c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049bfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049b2f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180049bfa`

## string_xrefs

- `0x180049af7`: `MFCopyStreamMetadata`

## pseudocode

```c
__int64 __fastcall MFCopyStreamMetadata(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // edi
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  unsigned int ulVal; // r12d
  __int64 p_QuadPart; // r15
  unsigned int v18; // ecx
  _QWORD *pElems; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // ebx
  __int64 v23; // rdi
  int v25; // [rsp+30h] [rbp-D0h]
  LONG lVal; // [rsp+34h] [rbp-CCh]
  int v27; // [rsp+38h] [rbp-C8h]
  int v28; // [rsp+3Ch] [rbp-C4h]
  _QWORD *v29; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  PROPVARIANT v33; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  PROPVARIANT pvar; // [rsp+98h] [rbp-68h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v38[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v39[24]; // [rsp+E0h] [rbp-20h] BYREF
  char v40[840]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v41; // [rsp+460h] [rbp+360h] BYREF
  int v42; // [rsp+468h] [rbp+368h] BYREF

  v41 = a3;
  v5 = 0;
  v42 = 0;
  memset(&v34, 0, sizeof(v34));
  CWMPropTranslator::CWMPropTranslator((CWMPropTranslator *)v39, 0, &v42);
  pv = 0;
  v31 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v41, "MFCopyStreamMetadata", 60);
  v7 = v42;
  if ( v42 < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( v7 < 0 && *((_DWORD *)ThreadRelativeContext + 499) != v7 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "MFCopyStreamMetadata", 60, v7);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_65;
    v11 = 14;
    goto LABEL_13;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)a1 + 40LL))(a1, &v34);
  if ( v7 < 0 )
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v15 + 499) != v7 )
        CallStackContext::TraceFailure(v15, "MFCopyStreamMetadata", 62, v7);
    }
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_65;
    v11 = 15;
LABEL_13:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids, 0, v7);
    goto LABEL_65;
  }
  v27 = 0;
  v28 = 0;
  if ( v34.vt == 4127 )
  {
    ulVal = 1;
    if ( v34.lVal )
      ulVal = v34.ulVal;
    p_QuadPart = (__int64)v34.bstrblobVal.pData & -(__int64)(v34.lVal != 0);
  }
  else if ( v34.vt == 31 )
  {
    ulVal = 1;
    p_QuadPart = (__int64)&v34.hVal.QuadPart;
  }
  else
  {
    ulVal = 0;
    p_QuadPart = 0;
  }
  (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a1 + 32LL))(a1, &pv);
  (*(void (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)a2 + 32LL))(a2, &v31);
  v41 = 0;
  if ( ulVal )
  {
    while ( 1 )
    {
      memset(&v33, 0, sizeof(v33));
      if ( p_QuadPart )
      {
        if ( (*(int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, *(_QWORD *)(p_QuadPart + 8LL * v5)) < 0 )
          goto LABEL_35;
        v27 = 1;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)a1 + 72LL))(a1, &v33);
      if ( v7 < 0 )
      {
LABEL_35:
        v7 = 0;
        goto LABEL_58;
      }
      if ( v33.vt == 4127 )
      {
        v18 = v33.ulVal;
        lVal = v33.lVal;
        if ( v33.lVal )
        {
          pElems = v33.cabstr.pElems;
          goto LABEL_43;
        }
      }
      else if ( v33.vt == 31 )
      {
        v18 = 1;
        pElems = &v33.hVal.QuadPart;
        lVal = 1;
LABEL_43:
        v29 = pElems;
        v20 = 0;
        v42 = 0;
        while ( 1 )
        {
          v25 = v20;
          if ( (unsigned int)v20 >= v18 )
            break;
          v21 = pElems[v20];
          v32 = 0;
          memset(&pvar, 0, sizeof(pvar));
          v35 = v20;
          CMFBaseStringT<unsigned short>::CMFBaseStringT<unsigned short>(v38, v21);
          v37 = 0;
          v22 = CTBucketHash<CMFBaseStringT<unsigned short>,CMFProperty *>::Find(v40, v38, &v32, &v37);
          CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v38);
          if ( v22 && (unsigned int)MFGetAttributeUINT32(v32, MF_MD_TRANSFERRABLE, 0) )
          {
            if ( !v42 && p_QuadPart )
            {
              v5 = v41;
              v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 24LL))(
                     a2,
                     *(_QWORD *)(p_QuadPart + 8LL * v41));
              if ( v7 < 0 )
              {
                CMFPropVariant::Clear(&pvar);
                break;
              }
              v42 = 1;
              v28 = 1;
            }
            v23 = v35;
            if ( (*(int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)a1 + 56LL))(a1, v29[v35], &pvar) >= 0 )
              (*(void (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)a2 + 48LL))(a2, v29[v23], &pvar);
            v7 = 0;
          }
          CMFPropVariant::Clear(&pvar);
          v18 = lVal;
          v20 = (unsigned int)(v25 + 1);
          v5 = v41;
          pElems = v29;
        }
        if ( v7 < 0 )
          v7 = 0;
      }
LABEL_58:
      CMFPropVariant::Clear(&v33);
      v41 = ++v5;
      if ( v5 >= ulVal )
      {
        if ( v27 && pv )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
        if ( v28 && v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
        break;
      }
    }
  }
LABEL_65:
  CoTaskMemFree(pv);
  CoTaskMemFree(v31);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v41);
  CWMPropTranslator::~CWMPropTranslator((CWMPropTranslator *)v39);
  CMFPropVariant::Clear(&v34);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180049a9c  mov     [rsp-8+arg_0], rbx
0x180049aa1  mov     [rsp-8+arg_10], r8d
0x180049aa6  push    rbp
0x180049aa7  push    rsi
0x180049aa8  push    rdi
0x180049aa9  push    r12
0x180049aab  push    r13
0x180049aad  push    r14
0x180049aaf  push    r15
0x180049ab1  lea     rbp, [rsp-310h]
0x180049ab9  sub     rsp, 410h
0x180049ac0  mov     r13, rdx
0x180049ac3  lea     r8, [rbp+340h+arg_18]; int *
0x180049aca  mov     r14, rcx
0x180049acd  xorps   xmm0, xmm0
0x180049ad0  xor     eax, eax
0x180049ad2  lea     rcx, [rbp+340h+var_360]; this
0x180049ad6  xor     ebx, ebx
0x180049ad8  mov     qword ptr [rbp+340h+var_3C8+10h], rax
0x180049adc  xor     edx, edx; struct IPropertyStore *
0x180049ade  mov     [rbp+340h+arg_18], ebx
0x180049ae4  movups  xmmword ptr [rsp+440h+var_3C8], xmm0
0x180049ae9  call    ??0CWMPropTranslator@@QEAA@PEAUIPropertyStore@@PEAJ@Z; CWMPropTranslator::CWMPropTranslator(IPropertyStore *,long *)
0x180049aee  lea     r15d, [rbx+3Ch]
0x180049af2  mov     [rsp+440h+pv], rbx
0x180049af7  lea     rsi, aMfcopystreamme; "MFCopyStreamMetadata"
0x180049afe  mov     [rsp+440h+var_3F0], rbx
0x180049b03  mov     r8d, r15d; int
0x180049b06  lea     rcx, [rbp+340h+arg_10]; this
0x180049b0d  mov     rdx, rsi; char *
0x180049b10  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180049b15  mov     edi, [rbp+340h+arg_18]
0x180049b1b  test    edi, edi
0x180049b1d  jns     loc_180049BD0
0x180049b23  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b2a  test    rcx, rcx
0x180049b2d  jnz     short loc_180049B70
0x180049b2f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049b35  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b3c  mov     rcx, rax
0x180049b3f  test    rax, rax
0x180049b42  jz      short loc_180049B62
0x180049b44  mov     rax, [rax]
0x180049b47  mov     edx, 7F0h
0x180049b4c  mov     rax, [rax+8]
0x180049b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b55  test    eax, eax
0x180049b57  jz      short loc_180049B62
0x180049b59  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b60  jmp     short loc_180049B70
0x180049b62  lea     rcx, qword_180069A90; this
0x180049b69  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049b70  cmp     [rcx+8], bl
0x180049b73  jz      short loc_180049B97
0x180049b75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049b7a  test    edi, edi
0x180049b7c  jns     short loc_180049B97
0x180049b7e  cmp     [rax+7CCh], edi
0x180049b84  jz      short loc_180049B97
0x180049b86  mov     r9d, edi; int
0x180049b89  mov     r8d, r15d; int
0x180049b8c  mov     rdx, rsi; char *
0x180049b8f  mov     rcx, rax; this
0x180049b92  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049b97  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049b9c  mov     esi, 1
0x180049ba1  cmp     al, sil
0x180049ba4  jb      loc_180049F14
0x180049baa  lea     edx, [rsi+0Dh]
0x180049bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bb4  lea     r8, WPP_c37a1a6f6d1f3c53e793f68f27ee7d1b_Traceguids
0x180049bbb  xor     r9d, r9d
0x180049bbe  mov     [rsp+440h+var_420], edi
0x180049bc2  mov     rcx, [rcx+10h]
0x180049bc6  call    WPP_SF_qd
0x180049bcb  jmp     loc_180049F14
0x180049bd0  mov     rax, [r14]
0x180049bd3  lea     rdx, [rsp+440h+var_3C8]
0x180049bd8  mov     rcx, r14
0x180049bdb  mov     rax, [rax+28h]
0x180049bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049be4  mov     edi, eax
0x180049be6  test    eax, eax
0x180049be8  jns     loc_180049C7C
0x180049bee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049bf5  test    rcx, rcx
0x180049bf8  jnz     short loc_180049C3B
0x180049bfa  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180049c00  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180049c07  mov     rcx, rax
0x180049c0a  test    rax, rax
0x180049c0d  jz      short loc_180049C2D
0x180049c0f  mov     rax, [rax]
0x180049c12  mov     edx, 7F0h
0x180049c17  mov     rax, [rax+8]
0x180049c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c20  test    eax, eax
0x180049c22  jz      short loc_180049C2D
0x180049c24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180049c2b  jmp     short loc_180049C3B
0x180049c2d  lea     rcx, qword_180069A90; this
0x180049c34  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180049c3b  cmp     [rcx+8], bl
0x180049c3e  jz      short loc_180049C61
0x180049c40  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180049c45  cmp     [rax+7CCh], edi
0x180049c4b  jz      short loc_180049C61
0x180049c4d  mov     r9d, edi; int
0x180049c50  mov     r8d, 3Eh ; '>'; int
0x180049c56  mov     rdx, rsi; char *
0x180049c59  mov     rcx, rax; this
0x180049c5c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180049c61  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180049c66  mov     esi, 1
0x180049c6b  cmp     al, sil
0x180049c6e  jb      loc_180049F14
0x180049c74  lea     edx, [rsi+0Eh]
0x180049c77  jmp     loc_180049BAD
0x180049c7c  mov     eax, 101Fh
0x180049c81  mov     [rsp+440h+var_408], ebx
0x180049c85  mov     esi, 1
0x180049c8a  mov     [rsp+440h+var_404], ebx
0x180049c8e  cmp     word ptr [rsp+440h+var_3C8], ax
0x180049c93  jnz     short loc_180049CAC
0x180049c95  mov     eax, dword ptr [rbp+340h+var_3C8+8]
0x180049c98  mov     r12d, esi
0x180049c9b  test    eax, eax
0x180049c9d  cmovnz  r12d, eax
0x180049ca1  neg     eax
0x180049ca3  sbb     r15, r15
0x180049ca6  and     r15, qword ptr [rbp+340h+var_3C8+10h]
0x180049caa  jmp     short loc_180049CC3
0x180049cac  cmp     word ptr [rsp+440h+var_3C8], 1Fh
0x180049cb2  jnz     short loc_180049CBD
0x180049cb4  mov     r12d, esi
0x180049cb7  lea     r15, [rbp+340h+var_3C8+8]
0x180049cbb  jmp     short loc_180049CC3
0x180049cbd  mov     r12d, ebx
0x180049cc0  mov     r15, rbx
0x180049cc3  mov     rax, [r14]
0x180049cc6  lea     rdx, [rsp+440h+pv]
0x180049ccb  mov     rcx, r14
0x180049cce  mov     rax, [rax+20h]
0x180049cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cd7  mov     rax, [r13+0]
0x180049cdb  lea     rdx, [rsp+440h+var_3F0]
0x180049ce0  mov     rcx, r13
0x180049ce3  mov     rax, [rax+20h]
0x180049ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cec  mov     [rbp+340h+arg_10], ebx
0x180049cf2  test    r12d, r12d
0x180049cf5  jz      loc_180049F14
0x180049cfb  xor     eax, eax
0x180049cfd  xorps   xmm0, xmm0
0x180049d00  mov     qword ptr [rsp+440h+var_3E0+10h], rax
0x180049d05  movups  xmmword ptr [rsp+440h+var_3E0], xmm0
0x180049d0a  test    r15, r15
0x180049d0d  jz      short loc_180049D33
0x180049d0f  mov     rax, [r14]
0x180049d12  mov     rcx, r14
0x180049d15  mov     edx, ebx
0x180049d17  mov     rax, [rax+18h]
0x180049d1b  mov     rdx, [r15+rdx*8]
0x180049d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d24  test    eax, eax
0x180049d26  jns     short loc_180049D2F
0x180049d28  xor     edi, edi
0x180049d2a  jmp     loc_180049EB8
0x180049d2f  mov     [rsp+440h+var_408], esi
0x180049d33  mov     rax, [r14]
0x180049d36  lea     rdx, [rsp+440h+var_3E0]
0x180049d3b  mov     rcx, r14
0x180049d3e  mov     rax, [rax+48h]
0x180049d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d47  mov     edi, eax
0x180049d49  test    eax, eax
0x180049d4b  js      short loc_180049D28
0x180049d4d  mov     eax, 101Fh
0x180049d52  cmp     word ptr [rsp+440h+var_3E0], ax
0x180049d57  jnz     short loc_180049D70
0x180049d59  mov     ecx, dword ptr [rsp+440h+var_3E0+8]
0x180049d5d  mov     [rsp+440h+var_40C], ecx
0x180049d61  test    ecx, ecx
0x180049d63  jz      loc_180049EB8
0x180049d69  mov     rdx, qword ptr [rsp+440h+var_3E0+10h]
0x180049d6e  jmp     short loc_180049D87
0x180049d70  cmp     word ptr [rsp+440h+var_3E0], 1Fh
0x180049d76  jnz     loc_180049EB8
0x180049d7c  mov     ecx, esi
0x180049d7e  lea     rdx, [rsp+440h+var_3E0+8]
0x180049d83  mov     [rsp+440h+var_40C], ecx
0x180049d87  mov     [rsp+440h+var_400], rdx
0x180049d8c  xor     eax, eax
0x180049d8e  mov     [rbp+340h+arg_18], 0
0x180049d98  mov     [rsp+440h+var_410], eax
0x180049d9c  cmp     eax, ecx
0x180049d9e  jnb     loc_180049EB1
0x180049da4  mov     rdx, [rdx+rax*8]
0x180049da8  xor     ecx, ecx
0x180049daa  mov     qword ptr [rbp+340h+pvar+10h], rcx
0x180049dae  xorps   xmm0, xmm0
0x180049db1  mov     [rsp+440h+var_3E8], rcx
0x180049db6  lea     rcx, [rbp+340h+var_380]
0x180049dba  movups  xmmword ptr [rbp+340h+pvar], xmm0
0x180049dbe  mov     [rbp+340h+var_3B0], rax
0x180049dc2  call    ??0?$CMFBaseStringT@G@@QEAA@PEBGJ@Z; CMFBaseStringT<ushort>::CMFBaseStringT<ushort>(ushort const *,long)
0x180049dc7  xorps   xmm0, xmm0
0x180049dca  lea     r9, [rbp+340h+var_390]
0x180049dce  lea     r8, [rsp+440h+var_3E8]
0x180049dd3  lea     rdx, [rbp+340h+var_380]
0x180049dd7  lea     rcx, [rbp+340h+var_348]
0x180049ddb  movups  [rbp+340h+var_390], xmm0
0x180049ddf  call    ?Find@?$CTBucketHash@V?$CMFBaseStringT@G@@PEAVCMFProperty@@@@QEAAHAEBV?$CMFBaseStringT@G@@AEAPEAVCMFProperty@@AEAU_POSITION@1@@Z; CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::Find(CMFBaseStringT<ushort> const &,CMFProperty * &,CTBucketHash<CMFBaseStringT<ushort>,CMFProperty *>::_POSITION &)
0x180049de4  lea     rcx, [rbp+340h+var_380]
0x180049de8  mov     ebx, eax
0x180049dea  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x180049def  test    ebx, ebx
0x180049df1  jz      loc_180049E85
0x180049df7  mov     rcx, [rsp+440h+var_3E8]
0x180049dfc  lea     rdx, MF_MD_TRANSFERRABLE
0x180049e03  xor     r8d, r8d
0x180049e06  call    MFGetAttributeUINT32
0x180049e0b  test    eax, eax
0x180049e0d  jz      short loc_180049E85
0x180049e0f  cmp     [rbp+340h+arg_18], 0
0x180049e16  jnz     short loc_180049E47
0x180049e18  test    r15, r15
0x180049e1b  jz      short loc_180049E47
0x180049e1d  mov     rax, [r13+0]
0x180049e21  mov     rcx, r13
0x180049e24  mov     ebx, [rbp+340h+arg_10]
0x180049e2a  mov     rax, [rax+18h]
0x180049e2e  mov     rdx, [r15+rbx*8]
0x180049e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e37  mov     edi, eax
0x180049e39  test    eax, eax
0x180049e3b  js      short loc_180049EA8
0x180049e3d  mov     [rbp+340h+arg_18], esi
0x180049e43  mov     [rsp+440h+var_404], esi
0x180049e47  mov     rax, [r14]
0x180049e4a  lea     r8, [rbp+340h+pvar]
0x180049e4e  mov     rbx, [rsp+440h+var_400]
0x180049e53  mov     rcx, r14
0x180049e56  mov     rdi, [rbp+340h+var_3B0]
0x180049e5a  mov     rax, [rax+38h]
0x180049e5e  mov     rdx, [rbx+rdi*8]
0x180049e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e67  test    eax, eax
0x180049e69  js      short loc_180049E83
0x180049e6b  mov     rax, [r13+0]
0x180049e6f  lea     r8, [rbp+340h+pvar]
0x180049e73  mov     rdx, [rbx+rdi*8]
0x180049e77  mov     rcx, r13
0x180049e7a  mov     rax, [rax+30h]
0x180049e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e83  xor     edi, edi
0x180049e85  lea     rcx, [rbp+340h+pvar]; pvar
0x180049e89  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180049e8e  mov     eax, [rsp+440h+var_410]
0x180049e92  mov     ecx, [rsp+440h+var_40C]
0x180049e96  add     eax, esi
0x180049e98  mov     ebx, [rbp+340h+arg_10]
0x180049e9e  mov     rdx, [rsp+440h+var_400]
0x180049ea3  jmp     loc_180049D98
0x180049ea8  lea     rcx, [rbp+340h+pvar]; pvar
0x180049eac  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180049eb1  xor     eax, eax
0x180049eb3  test    edi, edi
0x180049eb5  cmovs   edi, eax
0x180049eb8  lea     rcx, [rsp+440h+var_3E0]; pvar
0x180049ebd  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180049ec2  add     ebx, esi
0x180049ec4  mov     [rbp+340h+arg_10], ebx
0x180049eca  cmp     ebx, r12d
0x180049ecd  jb      loc_180049CFB
0x180049ed3  cmp     [rsp+440h+var_408], 0
0x180049ed8  jz      short loc_180049EF3
0x180049eda  mov     rdx, [rsp+440h+pv]
0x180049edf  test    rdx, rdx
0x180049ee2  jz      short loc_180049EF3
0x180049ee4  mov     rax, [r14]
0x180049ee7  mov     rcx, r14
0x180049eea  mov     rax, [rax+18h]
0x180049eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ef3  cmp     [rsp+440h+var_404], 0
0x180049ef8  jz      short loc_180049F14
0x180049efa  mov     rdx, [rsp+440h+var_3F0]
0x180049eff  test    rdx, rdx
0x180049f02  jz      short loc_180049F14
0x180049f04  mov     rax, [r13+0]
0x180049f08  mov     rcx, r13
0x180049f0b  mov     rax, [rax+18h]
0x180049f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f14  mov     rcx, [rsp+440h+pv]; pv
0x180049f19  call    cs:__imp_CoTaskMemFree
0x180049f1f  mov     rcx, [rsp+440h+var_3F0]; pv
0x180049f24  call    cs:__imp_CoTaskMemFree
0x180049f2a  lea     rcx, [rbp+340h+arg_10]; this
0x180049f31  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180049f36  lea     rcx, [rbp+340h+var_360]; this
  ... truncated ...
```
