# CProtocolHandlers::GetURLAccessor(CURL &,_AUTH_TYPE,wchar_t const *,wchar_t const *,wchar_t const *,_FILETIME,ulong,ulong,int,wchar_t const *,wchar_t const *,ulong,wchar_t const *,wchar_t const *,ulong,void *,tagBLOB const *,UrlAccessorPointer *,IProtocolHandlerSite *,CTPtrSList<CProtocolHandler> &)

- ea: `0x140043a74`
- end: `0x14004409b`
- name: `?GetURLAccessor@CProtocolHandlers@@QEAAJAEAVCURL@@W4_AUTH_TYPE@@PEB_W22U_FILETIME@@KKH22K22KPEAXPEBUtagBLOB@@PEAVUrlAccessorPointer@@PEAUIProtocolHandlerSite@@AEAV?$CTPtrSList@VCProtocolHandler@@@@@Z`
- size: `1575`
- prototype: `__int64(struct IProtocolHandler3 *, struct CURL *, int, ...)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140040cf4`

## callees

- `0x14000e898`
- `0x14000f2ec`
- `0x1400124cc`
- `0x140015fa4`
- `0x14001ffc0`
- `0x140033530`
- `0x140033c08`
- `0x140042f58`
- `0x14004302c`
- `0x140043a2c`
- `0x140043a74`
- `0x140044344`
- `0x1400445f8`
- `0x1400449d0`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043ab8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140043ab8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140043b1d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140043b1d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140043b09`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140043b09`

## string_xrefs

- `0x140043ae7`: `onecoreuap\base\appmodel\search\searchprotocolhost\prothndlr.cxx`
- `0x140044063`: `onecoreuap\base\appmodel\search\searchprotocolhost\prothndlr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 CProtocolHandlers::GetURLAccessor(struct IProtocolHandler3 *a1, struct CURL *a2, int a3, ...)
{
  CProtocolHandlers *v4; // rbx
  CLMString **v5; // rax
  CLMString *v6; // r15
  struct ISearchProtocol2 *v7; // rdi
  int v8; // esi
  int Error; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int16 v13; // r13
  __int64 v14; // rcx
  int v15; // eax
  wil::details::in1diag3 *v16; // rcx
  __int64 v17; // rdx
  struct IProtocolHandler *v18; // rbx
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  struct ISearchProtocol *v23; // rbx
  __int64 v24; // rcx
  enum _AUTH_TYPE v25; // r8d
  const wchar_t *v26; // r9
  int AccessorHelper; // eax
  char v28; // cl
  struct _FILETIME v29; // rdi
  __int64 v30; // rcx
  struct IProtocolHandler *v31; // rbx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  const wchar_t *v36; // [rsp+28h] [rbp-A1h]
  int v37; // [rsp+28h] [rbp-A1h]
  unsigned int v38; // [rsp+40h] [rbp-89h]
  unsigned int v39; // [rsp+48h] [rbp-81h]
  int v40; // [rsp+50h] [rbp-79h]
  unsigned int v41; // [rsp+68h] [rbp-61h]
  const wchar_t *v42; // [rsp+78h] [rbp-51h]
  _QWORD v43[2]; // [rsp+A8h] [rbp-21h] BYREF
  _BYTE v44[80]; // [rsp+B8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+47h]
  struct IProtocolHandler3 *v46; // [rsp+118h] [rbp+4Fh] BYREF
  struct CURL *v47; // [rsp+120h] [rbp+57h]
  int v48; // [rsp+128h] [rbp+5Fh]
  struct IUrlAccessor *v49; // [rsp+130h] [rbp+67h] BYREF
  va_list va; // [rsp+130h] [rbp+67h]
  struct ISearchProtocol2 *v51; // [rsp+138h] [rbp+6Fh] BYREF
  va_list va1; // [rsp+138h] [rbp+6Fh]
  wchar_t *v53; // [rsp+140h] [rbp+77h]
  struct _FILETIME v54; // [rsp+148h] [rbp+7Fh]
  __int64 v55; // [rsp+150h] [rbp+87h]
  __int64 v56; // [rsp+158h] [rbp+8Fh]
  __int64 v57; // [rsp+160h] [rbp+97h]
  wchar_t *v58; // [rsp+168h] [rbp+9Fh]
  wchar_t *v59; // [rsp+170h] [rbp+A7h]
  __int64 v60; // [rsp+178h] [rbp+AFh]
  wchar_t *v61; // [rsp+180h] [rbp+B7h]
  __int64 v62; // [rsp+188h] [rbp+BFh] BYREF
  va_list va2; // [rsp+188h] [rbp+BFh]
  __int64 v64; // [rsp+190h] [rbp+C7h]
  __int64 v65; // [rsp+198h] [rbp+CFh] BYREF
  va_list va3; // [rsp+198h] [rbp+CFh]
  struct tagBLOB *v67; // [rsp+1A0h] [rbp+D7h]
  UrlAccessorPointer *v68; // [rsp+1A8h] [rbp+DFh]
  __int64 v69; // [rsp+1B0h] [rbp+E7h] BYREF
  va_list va4; // [rsp+1B0h] [rbp+E7h]
  __int64 v71; // [rsp+1B8h] [rbp+EFh]
  va_list va5; // [rsp+1C0h] [rbp+F7h] BYREF

  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v49 = va_arg(va1, struct IUrlAccessor *);
  va_copy(va2, va1);
  v51 = va_arg(va2, struct ISearchProtocol2 *);
  v53 = va_arg(va2, wchar_t *);
  v54 = va_arg(va2, struct _FILETIME);
  v55 = va_arg(va2, _QWORD);
  v56 = va_arg(va2, _QWORD);
  v57 = va_arg(va2, _QWORD);
  v58 = va_arg(va2, wchar_t *);
  v59 = va_arg(va2, wchar_t *);
  v60 = va_arg(va2, _QWORD);
  v61 = va_arg(va2, wchar_t *);
  va_copy(va3, va2);
  v62 = va_arg(va3, _QWORD);
  v64 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v65 = va_arg(va4, _QWORD);
  v67 = va_arg(va4, struct tagBLOB *);
  v68 = va_arg(va4, UrlAccessorPointer *);
  va_copy(va5, va4);
  v69 = va_arg(va5, _QWORD);
  v71 = va_arg(va5, _QWORD);
  v48 = a3;
  v47 = a2;
  v46 = a1;
  v43[1] = -2;
  v4 = Block;
  v43[0] = (char *)Block + 56;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)Block + 56));
  CURL::GetAccessTypeName(a2, v44);
  v5 = (CLMString **)CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>::Lookup(v4, v44);
  v6 = *v5;
  v7 = 0;
  if ( !*v5 )
  {
    v8 = -2147218150;
    v12 = 732;
    goto LABEL_60;
  }
  v8 = 0;
  if ( *((_DWORD *)v6 + 40) )
  {
LABEL_14:
    v69 = 0;
    v65 = 0;
    v46 = 0;
    v49 = 0;
    v62 = 0;
    v13 = v60;
    if ( (v60 & 0x40) != 0 )
    {
      if ( (int)CProtocolHandler::GetProtocolHandler3(v6, &v46) >= 0 )
      {
        v15 = CProtocolHandlers::CheckThreadInit(v14, v71, v6);
        v8 = v15;
        v16 = retaddr;
        if ( v15 < 0 )
        {
          v17 = 578;
LABEL_35:
          wil::details::in1diag3::_Log_Hr(
            v16,
            (void *)v17,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
            (const char *)(unsigned int)v15,
            (int)v36);
LABEL_58:
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>((__int64 *)va2);
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>((struct IUrlAccessor **)va);
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v46);
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>((__int64 *)va3);
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>((__int64 *)va4);
          goto LABEL_61;
        }
        v18 = v46;
        v19 = (*(__int64 (__fastcall **)(struct IProtocolHandler3 *, struct CURL *, struct _FILETIME, struct IUrlAccessor **))(*(_QWORD *)v46 + 56LL))(
                v46,
                a2,
                v54,
                (struct IUrlAccessor **)va);
        v8 = v19;
        v20 = retaddr;
        if ( v19 < 0 )
        {
          v21 = 583;
LABEL_54:
          wil::details::in1diag3::_Log_Hr(
            v20,
            (void *)v21,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
            (const char *)(unsigned int)v19,
            (int)v36);
          goto LABEL_55;
        }
        goto LABEL_55;
      }
      v22 = 591;
      goto LABEL_57;
    }
    if ( *((int *)v6 + 41) >= 0 )
    {
      v23 = (struct ISearchProtocol *)*((_QWORD *)v6 + 17);
      if ( v23 )
      {
        v62 = *((_QWORD *)v6 + 17);
        ((void (__fastcall *)(struct ISearchProtocol *))v23->lpVtbl->AddRef)(v23);
        v15 = CProtocolHandlers::CheckThreadInit(v24, v71, v6);
        v8 = v15;
        v16 = retaddr;
        if ( v15 >= 0 )
        {
          v51 = 0;
          if ( *((int *)v6 + 41) >= 0 )
          {
            v16 = (wil::details::in1diag3 *)*((_QWORD *)v6 + 18);
            if ( v16 )
            {
              v7 = (struct ISearchProtocol2 *)*((_QWORD *)v6 + 18);
              v51 = v7;
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v16 + 8LL))(v16);
            }
          }
          AccessorHelper = CProtocolHandlers::CreateAccessorHelper(
                             v16,
                             a2,
                             v25,
                             v26,
                             v36,
                             v53,
                             v54,
                             v38,
                             v39,
                             v40,
                             v58,
                             v59,
                             v41,
                             v61,
                             v42,
                             v67,
                             v68,
                             v23,
                             v7,
                             (struct IUrlAccessor **)va);
          v8 = AccessorHelper;
          if ( AccessorHelper < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x272,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
              (const char *)(unsigned int)AccessorHelper,
              v37);
          TComPointer<IBindCtx>::~TComPointer<IBindCtx>((struct ISearchProtocol2 **)va1);
          goto LABEL_58;
        }
        v17 = 599;
        goto LABEL_35;
      }
    }
    v28 = 0;
    LOBYTE(v48) = 0;
    v29 = v54;
    if ( (v60 & 0x30000) == 0x30000 )
    {
      if ( (int)CProtocolHandler::GetProtocolHandler3(v6, &v46) < 0 )
      {
        v28 = v48;
      }
      else
      {
        v15 = CProtocolHandlers::CheckThreadInit(v30, v71, v6);
        v8 = v15;
        v16 = retaddr;
        if ( v15 < 0 )
        {
          v17 = 643;
          goto LABEL_35;
        }
        v31 = v46;
        v48 = v13 & 0x400;
        LODWORD(v36) = v48 != 0;
        v32 = (*(__int64 (__fastcall **)(struct IProtocolHandler3 *, struct CURL *, struct _FILETIME, bool))(*(_QWORD *)v46 + 64LL))(
                v46,
                v47,
                v29,
                (v13 & 0x10) != 0);
        v8 = v32;
        if ( v32 == -2147467263 )
          goto LABEL_43;
        if ( v32 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x295,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
            (const char *)(unsigned int)v32,
            (int)v36);
        UrlAccessorPointer::Init(v68, v49, v31);
        v28 = 1;
      }
    }
    if ( v8 < 0 || v28 )
      goto LABEL_58;
LABEL_43:
    if ( *((int *)v6 + 41) >= 0 )
    {
      v18 = (struct IProtocolHandler *)*((_QWORD *)v6 + 15);
      if ( v18 )
      {
        v65 = *((_QWORD *)v6 + 15);
        (*(void (__fastcall **)(struct IProtocolHandler *))(*(_QWORD *)v18 + 8LL))(v18);
        v15 = CProtocolHandlers::CheckThreadInit(v33, v71, v6);
        v8 = v15;
        v16 = retaddr;
        if ( v15 < 0 )
        {
          v17 = 673;
          goto LABEL_35;
        }
        v36 = &dword_14007696C;
        v19 = (*(__int64 (__fastcall **)(struct IProtocolHandler *, struct CURL *, _QWORD))(*(_QWORD *)v18 + 48LL))(
                v18,
                v47,
                0);
        v8 = v19;
        v20 = retaddr;
        if ( v19 < 0 )
        {
          v21 = 693;
          goto LABEL_54;
        }
LABEL_55:
        UrlAccessorPointer::Init(v68, v49, v18);
        goto LABEL_58;
      }
      v18 = (struct IProtocolHandler *)*((_QWORD *)v6 + 14);
      if ( v18 )
      {
        v69 = *((_QWORD *)v6 + 14);
        (*(void (__fastcall **)(struct IProtocolHandler *))(*(_QWORD *)v18 + 8LL))(v18);
        v15 = CProtocolHandlers::CheckThreadInit(v34, v71, v6);
        v8 = v15;
        v16 = retaddr;
        if ( v15 < 0 )
        {
          v17 = 701;
          goto LABEL_35;
        }
        v36 = &dword_14007696C;
        v19 = (*(__int64 (__fastcall **)(struct IProtocolHandler *, struct CURL *, _QWORD))(*(_QWORD *)v18 + 32LL))(
                v18,
                v47,
                0);
        v8 = v19;
        v20 = retaddr;
        if ( v19 < 0 )
        {
          v21 = 714;
          goto LABEL_54;
        }
        goto LABEL_55;
      }
    }
    v22 = 722;
LABEL_57:
    v8 = -2147218121;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
      (const char *)0x80040D37LL,
      (int)v36);
    goto LABEL_58;
  }
  g_pProtocolHandlerToCreate = *v5;
  if ( SetEvent(g_hNeedToCreatePH) )
  {
    if ( WaitForSingleObject(g_hPHCreated, 0xFFFFFFFF) )
    {
      Error = ResultFromKnownLastError();
      v8 = Error;
      v10 = retaddr;
      if ( Error < 0 )
      {
        v11 = 539;
LABEL_9:
        wil::details::in1diag3::_Log_Hr(
          v10,
          (void *)v11,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
          (const char *)(unsigned int)Error,
          (int)v36);
      }
    }
  }
  else
  {
    Error = ResultFromLastError();
    v8 = Error;
    v10 = retaddr;
    if ( Error < 0 )
    {
      v11 = 545;
      goto LABEL_9;
    }
  }
  g_pProtocolHandlerToCreate = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_53452569>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_53452569>::GetImpl'::`2'::impl)
    && !*((_DWORD *)v6 + 40) )
  {
    v8 = -2147418113;
    v12 = 556;
LABEL_60:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx",
      (const char *)(unsigned int)v8,
      (int)v36);
    goto LABEL_61;
  }
  if ( v8 >= 0 )
    goto LABEL_14;
LABEL_61:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v43);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140043a74  mov     rax, rsp
0x140043a77  mov     [rax+20h], r9
0x140043a7b  mov     [rax+18h], r8d
0x140043a7f  mov     [rax+10h], rdx
0x140043a83  mov     [rax+8], rcx
0x140043a87  push    rbp
0x140043a88  push    rbx
0x140043a89  push    rsi
0x140043a8a  push    rdi
0x140043a8b  push    r12
0x140043a8d  push    r13
0x140043a8f  push    r14
0x140043a91  push    r15
0x140043a93  lea     rbp, [rax-47h]
0x140043a97  sub     rsp, 0C8h
0x140043a9e  mov     [rbp+3Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x140043aa6  mov     r12, rdx
0x140043aa9  mov     rbx, cs:Block
0x140043ab0  lea     rcx, [rbx+38h]; lpCriticalSection
0x140043ab4  mov     [rbp+3Fh+var_60], rcx
0x140043ab8  call    cs:__imp_EnterCriticalSection
0x140043abe  nop
0x140043abf  lea     rdx, [rbp+3Fh+var_50]
0x140043ac3  mov     rcx, r12
0x140043ac6  call    ?GetAccessTypeName@CURL@@QEAA?AVCLMSubStr@@XZ; CURL::GetAccessTypeName(void)
0x140043acb  lea     rdx, [rbp+3Fh+var_50]
0x140043acf  mov     rcx, rbx
0x140043ad2  call    ?Lookup@?$CTPtrKPtrHashMap@V?$TLMString@$0CA@$0CA@$0EAA@@@VCProtocolHandler@@VCLMSubStr@@@@QEAAAEAPEAVCProtocolHandler@@PEBVCLMSubStr@@@Z; CTPtrKPtrHashMap<TLMString<32,32,1024>,CProtocolHandler,CLMSubStr>::Lookup(CLMSubStr const *)
0x140043ad7  mov     r15, [rax]
0x140043ada  xor     edi, edi
0x140043adc  test    r15, r15
0x140043adf  jz      loc_14004405E
0x140043ae5  mov     esi, edi
0x140043ae7  lea     r14, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140043aee  cmp     [r15+0A0h], edi
0x140043af5  jnz     loc_140043B96
0x140043afb  mov     cs:?g_pProtocolHandlerToCreate@@3PEAVCProtocolHandler@@EA, r15; CProtocolHandler * g_pProtocolHandlerToCreate
0x140043b02  mov     rcx, cs:?g_hNeedToCreatePH@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x140043b09  call    cs:__imp_SetEvent
0x140043b0f  test    eax, eax
0x140043b11  jz      short loc_140043B3D
0x140043b13  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140043b16  mov     rcx, cs:?g_hPHCreated@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hHandle
0x140043b1d  call    cs:__imp_WaitForSingleObject
0x140043b23  test    eax, eax
0x140043b25  jz      short loc_140043B5C
0x140043b27  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140043b2c  mov     esi, eax
0x140043b2e  mov     rcx, [rbp+47h]
0x140043b32  test    eax, eax
0x140043b34  jns     short loc_140043B5C
0x140043b36  mov     edx, 21Bh
0x140043b3b  jmp     short loc_140043B51
0x140043b3d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140043b42  mov     esi, eax
0x140043b44  mov     rcx, [rbp+47h]; this
0x140043b48  test    eax, eax
0x140043b4a  jns     short loc_140043B5C
0x140043b4c  mov     edx, 221h; void *
0x140043b51  mov     r9d, eax; char *
0x140043b54  mov     r8, r14; unsigned int
0x140043b57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140043b5c  mov     cs:?g_pProtocolHandlerToCreate@@3PEAVCProtocolHandler@@EA, rdi; CProtocolHandler * g_pProtocolHandlerToCreate
0x140043b63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_53452569@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_53452569@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53452569> `wil::Feature<__WilFeatureTraits_Feature_53452569>::GetImpl(void)'::`2'::impl
0x140043b6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_53452569@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_53452569>::__private_IsEnabled(void)
0x140043b6f  test    al, al
0x140043b71  jz      short loc_140043B8E
0x140043b73  cmp     [r15+0A0h], edi
0x140043b7a  jnz     short loc_140043B8E
0x140043b7c  mov     esi, 8000FFFFh
0x140043b81  mov     r8, r14
0x140043b84  mov     edx, 22Ch
0x140043b89  jmp     loc_14004406F
0x140043b8e  test    esi, esi
0x140043b90  js      loc_14004407C
0x140043b96  mov     [rbp+3Fh+arg_98], rdi
0x140043b9d  mov     [rbp+3Fh+arg_80], rdi
0x140043ba4  mov     [rbp+3Fh+arg_0], rdi
0x140043ba8  mov     [rbp+3Fh+arg_18], rdi
0x140043bac  mov     [rbp+3Fh+arg_70], rdi
0x140043bb3  mov     r13d, dword ptr [rbp+3Fh+arg_60]
0x140043bba  test    r13b, 40h
0x140043bbe  jz      short loc_140043C33
0x140043bc0  lea     rdx, [rbp+3Fh+arg_0]; struct IProtocolHandler3 **
0x140043bc4  mov     rcx, r15; this
0x140043bc7  call    ?GetProtocolHandler3@CProtocolHandler@@QEAAJPEAPEAUIProtocolHandler3@@@Z; CProtocolHandler::GetProtocolHandler3(IProtocolHandler3 * *)
0x140043bcc  test    eax, eax
0x140043bce  js      short loc_140043C29
0x140043bd0  mov     r8, r15
0x140043bd3  mov     rdx, [rbp+3Fh+arg_A0]
0x140043bda  call    ?CheckThreadInit@CProtocolHandlers@@AEAAJAEAV?$CTPtrSList@VCProtocolHandler@@@@PEAVCProtocolHandler@@@Z; CProtocolHandlers::CheckThreadInit(CTPtrSList<CProtocolHandler> &,CProtocolHandler *)
0x140043bdf  mov     esi, eax
0x140043be1  mov     rcx, [rbp+47h]
0x140043be5  test    eax, eax
0x140043be7  jns     short loc_140043BF3
0x140043be9  mov     edx, 242h
0x140043bee  jmp     loc_140043DA2
0x140043bf3  mov     rbx, [rbp+3Fh+arg_0]
0x140043bf7  mov     rax, [rbx]
0x140043bfa  lea     r9, [rbp+3Fh+arg_18]
0x140043bfe  mov     r8, qword ptr [rbp+3Fh+arg_30.dwLowDateTime]
0x140043c02  mov     rdx, r12
0x140043c05  mov     rcx, rbx
0x140043c08  mov     rax, [rax+38h]
0x140043c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043c11  mov     esi, eax
0x140043c13  mov     rcx, [rbp+47h]
0x140043c17  test    eax, eax
0x140043c19  jns     loc_140043FF2
0x140043c1f  mov     edx, 247h
0x140043c24  jmp     loc_140043FE7
0x140043c29  mov     edx, 24Fh
0x140043c2e  jmp     loc_14004400C
0x140043c33  cmp     [r15+0A4h], edi
0x140043c3a  jl      loc_140043D54
0x140043c40  mov     rbx, [r15+88h]
0x140043c47  test    rbx, rbx
0x140043c4a  jz      loc_140043D54
0x140043c50  mov     [rbp+3Fh+arg_70], rbx
0x140043c57  mov     rax, [rbx]
0x140043c5a  mov     rcx, rbx
0x140043c5d  mov     rax, [rax+8]
0x140043c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043c66  mov     r8, r15
0x140043c69  mov     rdx, [rbp+3Fh+arg_A0]
0x140043c70  call    ?CheckThreadInit@CProtocolHandlers@@AEAAJAEAV?$CTPtrSList@VCProtocolHandler@@@@PEAVCProtocolHandler@@@Z; CProtocolHandlers::CheckThreadInit(CTPtrSList<CProtocolHandler> &,CProtocolHandler *)
0x140043c75  mov     esi, eax
0x140043c77  mov     rcx, [rbp+47h]
0x140043c7b  test    eax, eax
0x140043c7d  jns     short loc_140043C89
0x140043c7f  mov     edx, 257h
0x140043c84  jmp     loc_140043DA2
0x140043c89  mov     [rbp+3Fh+arg_20], rdi
0x140043c8d  cmp     dword ptr [r15+0A4h], 0
0x140043c95  jl      short loc_140043CB6
0x140043c97  mov     rcx, [r15+90h]
0x140043c9e  test    rcx, rcx
0x140043ca1  jz      short loc_140043CB6
0x140043ca3  mov     rdi, rcx
0x140043ca6  mov     [rbp+3Fh+arg_20], rcx
0x140043caa  mov     rax, [rcx]
0x140043cad  mov     rax, [rax+8]
0x140043cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043cb6  lea     rax, [rbp+3Fh+arg_18]
0x140043cba  mov     [rsp+98h], rax; struct IUrlAccessor **
0x140043cc2  mov     [rsp+100h+var_70], rdi; struct ISearchProtocol2 *
0x140043cca  mov     [rsp+100h+var_78], rbx; struct ISearchProtocol *
0x140043cd2  mov     rax, [rbp+3Fh+arg_90]
0x140043cd9  mov     [rsp+100h+var_80], rax; struct UrlAccessorPointer *
0x140043ce1  mov     rax, [rbp+3Fh+arg_88]
0x140043ce8  mov     [rsp+100h+var_88], rax; struct tagBLOB *
0x140043ced  mov     rax, [rbp+3Fh+arg_68]
0x140043cf4  mov     [rsp+100h+var_98], rax; wchar_t *
0x140043cf9  mov     rax, [rbp+3Fh+arg_58]
0x140043d00  mov     [rsp+100h+var_A8], rax; wchar_t *
0x140043d05  mov     rax, [rbp+3Fh+arg_50]
0x140043d0c  mov     [rsp+100h+var_B0], rax; wchar_t *
0x140043d11  mov     rax, qword ptr [rbp+3Fh+arg_30.dwLowDateTime]
0x140043d15  mov     qword ptr [rsp+100h+var_D0.dwLowDateTime], rax; struct _FILETIME
0x140043d1a  mov     rax, [rbp+3Fh+arg_28]
0x140043d1e  mov     [rsp+100h+var_D8], rax; wchar_t *
0x140043d23  mov     rdx, r12; struct CURL *
0x140043d26  call    ?CreateAccessorHelper@CProtocolHandlers@@AEAAJAEAVCURL@@W4_AUTH_TYPE@@PEB_W22U_FILETIME@@KKH22K22PEBUtagBLOB@@PEAVUrlAccessorPointer@@PEAUISearchProtocol@@PEAUISearchProtocol2@@PEAPEAUIUrlAccessor@@@Z; CProtocolHandlers::CreateAccessorHelper(CURL &,_AUTH_TYPE,wchar_t const *,wchar_t const *,wchar_t const *,_FILETIME,ulong,ulong,int,wchar_t const *,wchar_t const *,ulong,wchar_t const *,wchar_t const *,tagBLOB const *,UrlAccessorPointer *,ISearchProtocol *,ISearchProtocol2 *,IUrlAccessor * *)
0x140043d2b  mov     esi, eax
0x140043d2d  mov     rcx, [rbp+47h]; this
0x140043d31  test    eax, eax
0x140043d33  jns     short loc_140043D46
0x140043d35  mov     r9d, eax; char *
0x140043d38  mov     r8, r14; unsigned int
0x140043d3b  mov     edx, 272h; void *
0x140043d40  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140043d45  nop
0x140043d46  lea     rcx, [rbp+3Fh+arg_20]
0x140043d4a  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x140043d4f  jmp     loc_140044022
0x140043d54  mov     cl, dil
0x140043d57  mov     byte ptr [rbp+3Fh+arg_10], cl
0x140043d5a  mov     eax, r13d
0x140043d5d  mov     edx, 30000h
0x140043d62  and     eax, edx
0x140043d64  mov     rdi, qword ptr [rbp+3Fh+arg_30.dwLowDateTime]
0x140043d68  cmp     eax, edx
0x140043d6a  jnz     loc_140043E39
0x140043d70  lea     rdx, [rbp+3Fh+arg_0]; struct IProtocolHandler3 **
0x140043d74  mov     rcx, r15; this
0x140043d77  call    ?GetProtocolHandler3@CProtocolHandler@@QEAAJPEAPEAUIProtocolHandler3@@@Z; CProtocolHandler::GetProtocolHandler3(IProtocolHandler3 * *)
0x140043d7c  test    eax, eax
0x140043d7e  js      loc_140043E36
0x140043d84  mov     r8, r15
0x140043d87  mov     rdx, [rbp+3Fh+arg_A0]
0x140043d8e  call    ?CheckThreadInit@CProtocolHandlers@@AEAAJAEAV?$CTPtrSList@VCProtocolHandler@@@@PEAVCProtocolHandler@@@Z; CProtocolHandlers::CheckThreadInit(CTPtrSList<CProtocolHandler> &,CProtocolHandler *)
0x140043d93  mov     esi, eax
0x140043d95  mov     rcx, [rbp+47h]; this
0x140043d99  test    eax, eax
0x140043d9b  jns     short loc_140043DB2
0x140043d9d  mov     edx, 283h; void *
0x140043da2  mov     r9d, eax; char *
0x140043da5  mov     r8, r14; unsigned int
0x140043da8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140043dad  jmp     loc_140044022
0x140043db2  mov     rbx, [rbp+3Fh+arg_0]
0x140043db6  mov     edx, r13d
0x140043db9  xor     ecx, ecx
0x140043dbb  and     edx, 400h
0x140043dc1  mov     [rbp+3Fh+arg_10], edx
0x140043dc4  mov     r12d, r13d
0x140043dc7  mov     rax, [rbx]
0x140043dca  setnz   cl
0x140043dcd  xor     r9d, r9d
0x140043dd0  and     r12d, 10h
0x140043dd4  setnz   r9b
0x140043dd8  lea     rdx, [rbp+3Fh+arg_18]
0x140043ddc  mov     [rsp+100h+var_D8], rdx
0x140043de1  mov     [rsp+100h+var_E0], ecx; int
0x140043de5  mov     r8, rdi
0x140043de8  mov     rdx, [rbp+3Fh+arg_8]
0x140043dec  mov     rcx, rbx
0x140043def  mov     rax, [rax+40h]
0x140043df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043df8  mov     esi, eax
0x140043dfa  cmp     eax, 80004001h
0x140043dff  jnz     short loc_140043E07
0x140043e01  mov     r13d, [rbp+3Fh+arg_10]
0x140043e05  jmp     short loc_140043E57
0x140043e07  mov     rcx, [rbp+47h]; this
0x140043e0b  test    eax, eax
0x140043e0d  jns     short loc_140043E1F
0x140043e0f  mov     r9d, eax; char *
0x140043e12  mov     r8, r14; unsigned int
0x140043e15  mov     edx, 295h; void *
0x140043e1a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140043e1f  mov     r8, rbx; struct IProtocolHandler *
0x140043e22  mov     rdx, [rbp+3Fh+arg_18]; struct IUrlAccessor *
0x140043e26  mov     rcx, [rbp+3Fh+arg_90]; this
0x140043e2d  call    ?Init@UrlAccessorPointer@@QEAAXPEAUIUrlAccessor@@PEAUIProtocolHandler@@@Z; UrlAccessorPointer::Init(IUrlAccessor *,IProtocolHandler *)
0x140043e32  mov     cl, 1
0x140043e34  jmp     short loc_140043E39
0x140043e36  mov     cl, byte ptr [rbp+3Fh+arg_10]
0x140043e39  test    esi, esi
0x140043e3b  js      loc_140044022
0x140043e41  mov     r12d, r13d
0x140043e44  test    cl, cl
0x140043e46  jnz     loc_140044022
0x140043e4c  and     r13d, 400h
0x140043e53  and     r12d, 10h
0x140043e57  cmp     dword ptr [r15+0A4h], 0
0x140043e5f  jl      loc_140044007
0x140043e65  mov     rbx, [r15+78h]
0x140043e69  test    rbx, rbx
0x140043e6c  jz      loc_140043F59
0x140043e72  mov     [rbp+3Fh+arg_80], rbx
0x140043e79  mov     rax, [rbx]
0x140043e7c  mov     rcx, rbx
0x140043e7f  mov     rax, [rax+8]
0x140043e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043e88  mov     r8, r15
0x140043e8b  mov     rdx, [rbp+3Fh+arg_A0]
0x140043e92  call    ?CheckThreadInit@CProtocolHandlers@@AEAAJAEAV?$CTPtrSList@VCProtocolHandler@@@@PEAVCProtocolHandler@@@Z; CProtocolHandlers::CheckThreadInit(CTPtrSList<CProtocolHandler> &,CProtocolHandler *)
0x140043e97  mov     esi, eax
0x140043e99  mov     rcx, [rbp+47h]
0x140043e9d  test    eax, eax
0x140043e9f  jns     short loc_140043EAB
0x140043ea1  mov     edx, 2A1h
0x140043ea6  jmp     loc_140043DA2
0x140043eab  mov     rax, [rbx]
0x140043eae  xor     edx, edx
0x140043eb0  test    r13d, r13d
0x140043eb3  setnz   dl
0x140043eb6  xor     ecx, ecx
0x140043eb8  test    r12d, r12d
0x140043ebb  setnz   cl
0x140043ebe  mov     r10, [rax+30h]
0x140043ec2  lea     rax, [rbp+3Fh+arg_18]
0x140043ec6  mov     [rsp+100h+var_88], rax
0x140043ecb  mov     rax, [rbp+3Fh+arg_68]
0x140043ed2  mov     [rsp+100h+var_90], rax
0x140043ed7  mov     dword ptr [rsp+100h+var_98], edx
0x140043edb  mov     dword ptr [rsp+100h+var_A0], ecx
0x140043edf  mov     rax, [rbp+3Fh+arg_58]
0x140043ee6  mov     [rsp+100h+var_A8], rax
0x140043eeb  mov     rax, [rbp+3Fh+arg_50]
0x140043ef2  mov     [rsp+100h+var_B0], rax
0x140043ef7  mov     eax, dword ptr [rbp+3Fh+arg_48]
0x140043efd  mov     dword ptr [rsp+100h+var_B8], eax
0x140043f01  mov     ecx, dword ptr [rbp+3Fh+arg_40]
0x140043f07  mov     [rsp+100h+var_C0], ecx
0x140043f0b  mov     ecx, dword ptr [rbp+3Fh+arg_38]
0x140043f11  mov     [rsp+100h+var_C8], ecx
0x140043f15  mov     qword ptr [rsp+100h+var_D0.dwLowDateTime], rdi
0x140043f1a  mov     rcx, [rbp+3Fh+arg_28]
0x140043f1e  mov     [rsp+100h+var_D8], rcx
0x140043f23  lea     r9, dword_14007696C
0x140043f2a  mov     qword ptr [rsp+100h+var_E0], r9
0x140043f2f  xor     r8d, r8d
0x140043f32  mov     rdx, [rbp+3Fh+arg_8]
0x140043f36  mov     rcx, rbx
0x140043f39  mov     rax, r10
0x140043f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043f41  mov     esi, eax
0x140043f43  mov     rcx, [rbp+47h]
  ... truncated ...
```
