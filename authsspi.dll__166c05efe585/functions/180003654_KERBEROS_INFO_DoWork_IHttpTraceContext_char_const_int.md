# KERBEROS_INFO::DoWork(IHttpTraceContext *,char const *,int)

- ea: `0x180003654`
- end: `0x180003a01`
- name: `?DoWork@KERBEROS_INFO@@QEAAJPEAVIHttpTraceContext@@PEBDH@Z`
- size: `941`
- prototype: `int(KERBEROS_INFO *__hidden this, struct IHttpTraceContext *, const char *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002084`

## callees

- `0x180003654`
- `0x1800058fc`
- `0x180008b52`
- `0x180008ba0`
- `0x180009010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039d8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800039d8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800036da`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800036da`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000373b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000376d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003851`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000373b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000376d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003851`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003935`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003944`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003935`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003944`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036ab`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036d0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036ab`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800036d0`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003752`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003784`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003752`
- `iisutil!?AppendA@STRU@@QEAAJPEBD@Z` at `0x180003784`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003825`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003838`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003900`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003913`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003825`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003838`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003900`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NPEBG@Z` at `0x180003913`
- `OLEAUT32!__imp_VariantInit` at `0x18000370c`
- `OLEAUT32!__imp_VariantInit` at `0x1800038c7`
- `OLEAUT32!__imp_VariantInit` at `0x18000370c`
- `OLEAUT32!__imp_VariantInit` at `0x1800038c7`
- `OLEAUT32!__imp_VariantClear` at `0x18000394f`
- `OLEAUT32!__imp_VariantClear` at `0x180003970`
- `OLEAUT32!__imp_VariantClear` at `0x1800039ba`
- `OLEAUT32!__imp_VariantClear` at `0x18000394f`
- `OLEAUT32!__imp_VariantClear` at `0x180003970`
- `OLEAUT32!__imp_VariantClear` at `0x1800039ba`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800038a4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800038a4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000388a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000388a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800038e3`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800038e3`

## pseudocode

```c
__int64 __fastcall KERBEROS_INFO::DoWork(KERBEROS_INFO *this, struct IHttpTraceContext *a2, const char *a3)
{
  HRESULT LBound; // ebx
  char v7; // r14
  const struct _GUID *v8; // rdx
  int v9; // r8d
  const unsigned __int16 *v10; // r15
  HRESULT v11; // eax
  SAFEARRAY *parray; // rsi
  int i; // eax
  char v14; // al
  const unsigned __int16 *v16; // [rsp+30h] [rbp-D0h]
  LONG rgIndices; // [rsp+40h] [rbp-C0h] BYREF
  LONG plLbound; // [rsp+44h] [rbp-BCh] BYREF
  LONG plUbound; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pv; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v23[32]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v24; // [rsp+A8h] [rbp-58h]
  _BYTE v25[56]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v26[56]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v27[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v28[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v26, v27, 0x40u);
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v25, v28, 0x40u);
  STRU::STRU((STRU *)v23);
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  if ( *((_DWORD *)this + 1) )
  {
    v7 = 0;
    VariantInit(&pvarg);
    if ( *((_DWORD *)this + 60) )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 28);
      LBound = STRU::Copy((STRU *)v26, L"HTTP/");
      if ( LBound >= 0 )
      {
        LBound = STRU::AppendA((STRU *)v26, a3);
        if ( LBound >= 0 )
        {
          LBound = STRU::Copy((STRU *)v25, L"HOST/");
          if ( LBound >= 0 )
          {
            LBound = STRU::AppendA((STRU *)v25, a3);
            if ( LBound >= 0 )
            {
              (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 24LL))(s_pGlobalInfo);
              LBound = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))this + 72))(
                         *((_QWORD *)this + 51),
                         &IID_IADs,
                         &v20);
              if ( LBound >= 0 )
                LBound = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)v20 + 120LL))(
                           v20,
                           *((_QWORD *)this + 70),
                           &pvarg);
              (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 32LL))(s_pGlobalInfo);
              if ( LBound >= 0 )
              {
                if ( pvarg.vt == 8 )
                {
                  if ( STRU::EqualsNoCase((STRU *)v26, pvarg.bstrVal) || STRU::EqualsNoCase((STRU *)v25, pvarg.bstrVal) )
                    v7 = 1;
                  STRU::Copy((STRU *)v23, pvarg.bstrVal);
                }
                else if ( (pvarg.vt & 0x2000) != 0 )
                {
                  parray = pvarg.parray;
                  plLbound = 0;
                  plUbound = 0;
                  LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
                  if ( LBound >= 0 )
                  {
                    LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
                    if ( LBound >= 0 )
                    {
                      memset(&pv, 0, sizeof(pv));
                      VariantInit(&pv);
                      for ( i = plLbound; ; i = rgIndices + 1 )
                      {
                        rgIndices = i;
                        if ( i > plUbound )
                          break;
                        LBound = SafeArrayGetElement(parray, &rgIndices, &pv);
                        if ( LBound < 0 )
                        {
                          VariantClear(&pv);
                          break;
                        }
                        if ( pv.vt == 8 )
                        {
                          if ( STRU::EqualsNoCase((STRU *)v26, pv.bstrVal)
                            || STRU::EqualsNoCase((STRU *)v25, pv.bstrVal) )
                          {
                            v7 = 1;
                          }
                          if ( rgIndices > plLbound )
                            STRU::Append((STRU *)v23, L"; ");
                          STRU::Append((STRU *)v23, pv.bstrVal);
                        }
                        VariantClear(&pv);
                      }
                    }
                  }
                }
              }
              else
              {
                v11 = 0;
                if ( LBound != -2147463155 )
                  v11 = LBound;
                LBound = v11;
              }
            }
          }
        }
      }
    }
    else
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 5);
      LBound = -2147467259;
    }
    v14 = 0;
    if ( LBound >= 0 )
      v14 = v7;
    IISAuthenticationEvents::AUTH_KERBEROS_FAILED::RaiseEvent(a2, v8, v9, v10, v24, v14, v16);
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v20 = 0;
    }
    VariantClear(&pvarg);
  }
  else
  {
    LBound = 0;
  }
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180003654  push    rbp
0x180003656  push    rbx
0x180003657  push    rsi
0x180003658  push    rdi
0x180003659  push    r12
0x18000365b  push    r14
0x18000365d  push    r15
0x18000365f  lea     rbp, [rsp-140h]
0x180003667  sub     rsp, 240h
0x18000366e  mov     rax, cs:__security_cookie
0x180003675  xor     rax, rsp
0x180003678  mov     [rbp+170h+var_40], rax
0x18000367f  mov     rsi, r8
0x180003682  mov     r12, rdx
0x180003685  mov     rdi, rcx
0x180003688  mov     r14d, 80h
0x18000368e  mov     r8d, r14d; Size
0x180003691  lea     rcx, [rbp+170h+var_140]; void *
0x180003695  xor     edx, edx; Val
0x180003697  call    memset_0
0x18000369c  lea     ebx, [r14-40h]
0x1800036a0  mov     r8d, ebx
0x1800036a3  lea     rdx, [rbp+170h+var_140]
0x1800036a7  lea     rcx, [rbp+170h+var_178]
0x1800036ab  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036b1  mov     r8d, r14d; Size
0x1800036b4  lea     rcx, [rbp+170h+var_C0]; void *
0x1800036bb  xor     edx, edx; Val
0x1800036bd  call    memset_0
0x1800036c2  mov     r8d, ebx
0x1800036c5  lea     rdx, [rbp+170h+var_C0]
0x1800036cc  lea     rcx, [rbp+170h+var_1B0]
0x1800036d0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800036d6  lea     rcx, [rbp+170h+var_1E8]
0x1800036da  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800036e0  xor     eax, eax
0x1800036e2  mov     [rsp+270h+var_220], 0
0x1800036eb  xorps   xmm0, xmm0
0x1800036ee  mov     qword ptr [rsp+270h+pvarg+10h], rax
0x1800036f3  movups  xmmword ptr [rsp+270h+pvarg], xmm0
0x1800036f8  cmp     [rdi+4], eax
0x1800036fb  jnz     short loc_180003704
0x1800036fd  xor     ebx, ebx
0x1800036ff  jmp     loc_1800039C0
0x180003704  lea     rcx, [rsp+270h+pvarg]; pvarg
0x180003709  xor     r14d, r14d
0x18000370c  call    cs:__imp_VariantInit
0x180003712  cmp     [rdi+0F0h], r14d
0x180003719  jnz     short loc_180003729
0x18000371b  mov     r15, [rdi+28h]
0x18000371f  mov     ebx, 80004005h
0x180003724  jmp     loc_180003976
0x180003729  mov     r15, [rdi+0E0h]
0x180003730  lea     rdx, aHttp; "HTTP/"
0x180003737  lea     rcx, [rbp+170h+var_178]
0x18000373b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003741  mov     ebx, eax
0x180003743  test    eax, eax
0x180003745  js      loc_180003976
0x18000374b  mov     rdx, rsi
0x18000374e  lea     rcx, [rbp+170h+var_178]
0x180003752  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x180003758  mov     ebx, eax
0x18000375a  test    eax, eax
0x18000375c  js      loc_180003976
0x180003762  lea     rdx, aHost; "HOST/"
0x180003769  lea     rcx, [rbp+170h+var_1B0]
0x18000376d  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003773  mov     ebx, eax
0x180003775  test    eax, eax
0x180003777  js      loc_180003976
0x18000377d  mov     rdx, rsi
0x180003780  lea     rcx, [rbp+170h+var_1B0]
0x180003784  call    cs:__imp_?AppendA@STRU@@QEAAJPEBD@Z; STRU::AppendA(char const *)
0x18000378a  mov     ebx, eax
0x18000378c  test    eax, eax
0x18000378e  js      loc_180003976
0x180003794  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000379b  mov     rax, [rcx]
0x18000379e  mov     rax, [rax+18h]
0x1800037a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a7  mov     rcx, [rdi+198h]
0x1800037ae  lea     r8, [rsp+270h+var_220]
0x1800037b3  mov     rax, [rdi+240h]
0x1800037ba  lea     rdx, IID_IADs
0x1800037c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c6  mov     ebx, eax
0x1800037c8  test    eax, eax
0x1800037ca  js      short loc_1800037EB
0x1800037cc  mov     rcx, [rsp+270h+var_220]
0x1800037d1  lea     r8, [rsp+270h+pvarg]
0x1800037d6  mov     rdx, [rdi+230h]
0x1800037dd  mov     rax, [rcx]
0x1800037e0  mov     rax, [rax+78h]
0x1800037e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e9  mov     ebx, eax
0x1800037eb  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800037f2  mov     rax, [rcx]
0x1800037f5  mov     rax, [rax+20h]
0x1800037f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fe  test    ebx, ebx
0x180003800  jns     short loc_180003814
0x180003802  xor     eax, eax
0x180003804  cmp     ebx, 8000500Dh
0x18000380a  cmovnz  eax, ebx
0x18000380d  mov     ebx, eax
0x18000380f  jmp     loc_180003976
0x180003814  cmp     word ptr [rsp+270h+pvarg], 8
0x18000381a  jnz     short loc_18000385C
0x18000381c  mov     rdx, qword ptr [rsp+270h+pvarg+8]
0x180003821  lea     rcx, [rbp+170h+var_178]
0x180003825  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x18000382b  test    al, al
0x18000382d  jnz     short loc_180003842
0x18000382f  mov     rdx, qword ptr [rsp+270h+pvarg+8]
0x180003834  lea     rcx, [rbp+170h+var_1B0]
0x180003838  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x18000383e  test    al, al
0x180003840  jz      short loc_180003848
0x180003842  mov     r14d, 1
0x180003848  mov     rdx, qword ptr [rsp+270h+pvarg+8]
0x18000384d  lea     rcx, [rbp+170h+var_1E8]
0x180003851  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003857  jmp     loc_180003976
0x18000385c  mov     eax, 2000h
0x180003861  test    word ptr [rsp+270h+pvarg], ax
0x180003866  jz      loc_180003976
0x18000386c  mov     rsi, qword ptr [rsp+270h+pvarg+8]
0x180003871  lea     r8, [rsp+270h+plLbound]; plLbound
0x180003876  mov     edi, 1
0x18000387b  mov     [rsp+270h+plLbound], r14d
0x180003880  mov     edx, edi; nDim
0x180003882  mov     [rsp+270h+plUbound], r14d
0x180003887  mov     rcx, rsi; psa
0x18000388a  call    cs:__imp_SafeArrayGetLBound
0x180003890  mov     ebx, eax
0x180003892  test    eax, eax
0x180003894  js      loc_180003976
0x18000389a  lea     r8, [rsp+270h+plUbound]; plUbound
0x18000389f  mov     edx, edi; nDim
0x1800038a1  mov     rcx, rsi; psa
0x1800038a4  call    cs:__imp_SafeArrayGetUBound
0x1800038aa  mov     ebx, eax
0x1800038ac  test    eax, eax
0x1800038ae  js      loc_180003976
0x1800038b4  xorps   xmm0, xmm0
0x1800038b7  lea     rcx, [rsp+270h+pv]; pvarg
0x1800038bc  xor     eax, eax
0x1800038be  movups  xmmword ptr [rsp+270h+pv], xmm0
0x1800038c3  mov     qword ptr [rbp+170h+pv+10h], rax
0x1800038c7  call    cs:__imp_VariantInit
0x1800038cd  mov     eax, [rsp+270h+plLbound]
0x1800038d1  jmp     loc_18000395B
0x1800038d6  lea     r8, [rsp+270h+pv]; pv
0x1800038db  mov     rcx, rsi; psa
0x1800038de  lea     rdx, [rsp+270h+rgIndices]; rgIndices
0x1800038e3  call    cs:__imp_SafeArrayGetElement
0x1800038e9  mov     ebx, eax
0x1800038eb  test    eax, eax
0x1800038ed  js      short loc_18000396B
0x1800038ef  cmp     word ptr [rsp+270h+pv], 8
0x1800038f5  jnz     short loc_18000394A
0x1800038f7  mov     rdx, qword ptr [rsp+270h+pv+8]
0x1800038fc  lea     rcx, [rbp+170h+var_178]
0x180003900  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x180003906  test    al, al
0x180003908  jnz     short loc_18000391D
0x18000390a  mov     rdx, qword ptr [rsp+270h+pv+8]
0x18000390f  lea     rcx, [rbp+170h+var_1B0]
0x180003913  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NPEBG@Z; STRU::EqualsNoCase(ushort const *)
0x180003919  test    al, al
0x18000391b  jz      short loc_180003920
0x18000391d  mov     r14d, edi
0x180003920  mov     eax, [rsp+270h+plLbound]
0x180003924  cmp     [rsp+270h+rgIndices], eax
0x180003928  jle     short loc_18000393B
0x18000392a  lea     rdx, asc_18000AF04; "; "
0x180003931  lea     rcx, [rbp+170h+var_1E8]
0x180003935  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000393b  mov     rdx, qword ptr [rsp+270h+pv+8]
0x180003940  lea     rcx, [rbp+170h+var_1E8]
0x180003944  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000394a  lea     rcx, [rsp+270h+pv]; pvarg
0x18000394f  call    cs:__imp_VariantClear
0x180003955  mov     eax, [rsp+270h+rgIndices]
0x180003959  add     eax, edi
0x18000395b  mov     [rsp+270h+rgIndices], eax
0x18000395f  cmp     eax, [rsp+270h+plUbound]
0x180003963  jle     loc_1800038D6
0x180003969  jmp     short loc_180003976
0x18000396b  lea     rcx, [rsp+270h+pv]; pvarg
0x180003970  call    cs:__imp_VariantClear
0x180003976  xor     eax, eax
0x180003978  mov     r9, r15; unsigned __int16 *
0x18000397b  test    ebx, ebx
0x18000397d  mov     rcx, r12; struct IHttpTraceContext *
0x180003980  cmovns  eax, r14d
0x180003984  mov     dword ptr [rsp+270h+var_248], eax; char
0x180003988  mov     rax, [rbp+170h+var_1C8]
0x18000398c  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x180003991  call    ?RaiseEvent@AUTH_KERBEROS_FAILED@IISAuthenticationEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@HPEBG2H2@Z; IISAuthenticationEvents::AUTH_KERBEROS_FAILED::RaiseEvent(IHttpTraceContext *,_GUID const *,int,ushort const *,ushort const *,int,ushort const *)
0x180003996  mov     rcx, [rsp+270h+var_220]
0x18000399b  test    rcx, rcx
0x18000399e  jz      short loc_1800039B5
0x1800039a0  mov     rax, [rcx]
0x1800039a3  mov     rax, [rax+10h]
0x1800039a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ac  mov     [rsp+270h+var_220], 0
0x1800039b5  lea     rcx, [rsp+270h+pvarg]; pvarg
0x1800039ba  call    cs:__imp_VariantClear
0x1800039c0  lea     rcx, [rbp+170h+var_1E8]
0x1800039c4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039ca  lea     rcx, [rbp+170h+var_1B0]
0x1800039ce  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039d4  lea     rcx, [rbp+170h+var_178]
0x1800039d8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800039de  mov     eax, ebx
0x1800039e0  mov     rcx, [rbp+170h+var_40]
0x1800039e7  xor     rcx, rsp; StackCookie
0x1800039ea  call    __security_check_cookie
0x1800039ef  add     rsp, 240h
0x1800039f6  pop     r15
0x1800039f8  pop     r14
0x1800039fa  pop     r12
0x1800039fc  pop     rdi
0x1800039fd  pop     rsi
0x1800039fe  pop     rbx
0x1800039ff  pop     rbp
0x180003a00  retn
```
