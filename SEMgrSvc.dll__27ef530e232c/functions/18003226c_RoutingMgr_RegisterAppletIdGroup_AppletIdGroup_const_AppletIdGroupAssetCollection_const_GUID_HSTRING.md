# RoutingMgr::RegisterAppletIdGroup(_AppletIdGroup const *,_AppletIdGroupAssetCollection const *,_GUID *,HSTRING__ * *)

- ea: `0x18003226c`
- end: `0x180032795`
- name: `?RegisterAppletIdGroup@RoutingMgr@@QEAAJPEBU_AppletIdGroup@@PEBU_AppletIdGroupAssetCollection@@PEAU_GUID@@PEAPEAUHSTRING__@@@Z`
- size: `1321`
- prototype: `__int64 __fastcall(RoutingMgr *this, const struct _AppletIdGroup *, const struct _AppletIdGroupAssetCollection *, struct _GUID *, HSTRING *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012020`

## callees

- `0x1800034ec`
- `0x1800049a0`
- `0x18000c964`
- `0x18000f740`
- `0x180013274`
- `0x18003159c`
- `0x180031d0c`
- `0x18003226c`
- `0x180034c54`
- `0x18003bc1c`
- `0x18003c484`
- `0x18003c5ac`
- `0x18003c614`
- `0x18003ce74`
- `0x1800407ec`
- `0x18007a1a0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003276a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003276a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032440`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003251f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003251f`

## string_xrefs

- `0x1800322c3`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x18003249b`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x1800325e1`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x18003264a`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180032687`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x1800326dc`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x180032723`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingmgr.cpp`
- `0x1800323c7`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingvalidation.cpp`
- `0x180032480`: `onecoreuap\ds\nfc\product\semanagement\common\routingmgr\src\routingregistrationstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RoutingMgr::RegisterAppletIdGroup(
        RoutingMgr *this,
        const struct _AppletIdGroup *a2,
        const struct _AppletIdGroupAssetCollection *a3,
        struct _GUID *a4,
        HSTRING *a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rsi
  __int64 v15; // r15
  int v16; // eax
  __int64 v17; // rsi
  int v18; // eax
  RoutingMgr *v19; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // eax
  BYTE *v24; // r8
  int v25; // eax
  int v26; // eax
  int SmartcardInterfaceInfoNameForRegistration; // eax
  int v28; // eax
  const WCHAR *v29; // rcx
  HSTRING HSTRING; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+20h] [rbp-E0h]
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+64h] [rbp-9Ch] BYREF
  int v38; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+6Ch] [rbp-94h] BYREF
  _DWORD v40[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v41; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR StringRawBuffer; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID *v43; // [rsp+98h] [rbp-68h] BYREF
  int v44[2]; // [rsp+A0h] [rbp-60h] BYREF
  char *v45; // [rsp+A8h] [rbp-58h]
  char v46; // [rsp+B0h] [rbp-50h]
  RoutingMgr *v47; // [rsp+B8h] [rbp-48h]
  unsigned __int16 *v48; // [rsp+C0h] [rbp-40h]
  struct _GUID *v49; // [rsp+C8h] [rbp-38h]
  char v50; // [rsp+D0h] [rbp-30h]
  struct _GUID v51; // [rsp+E0h] [rbp-20h] BYREF
  PCNZWCH sourceString[2]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h]
  unsigned __int16 v54[72]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *(_QWORD *)&v41.Data1 = a5;
  if ( !*((_BYTE *)this + 177) )
  {
    v9 = -2147019873;
    v10 = 241;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
      (const char *)v9,
      v32);
    return v9;
  }
  if ( !a2 )
  {
    v9 = -2147467261;
    v10 = 242;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = -2147467261;
    v10 = 243;
    goto LABEL_3;
  }
  v11 = *((unsigned int *)a2 + 35);
  if ( !(_DWORD)v11 )
  {
    v12 = 2147942487LL;
    v9 = -2147024809;
    v13 = 116;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingvalidation.cpp",
      (const char *)v12,
      v32);
    v10 = 244;
    goto LABEL_3;
  }
  if ( (unsigned int)v11 > 9 )
  {
    v12 = 2147942487LL;
    v9 = -2147024809;
    v13 = 117;
    goto LABEL_28;
  }
  v14 = *((_QWORD *)a2 + 18);
  v15 = v14 + 20 * v11;
  while ( v14 != v15 )
  {
    v16 = ValidateAppletId(v14);
    v9 = v16;
    if ( v16 < 0 )
    {
      v13 = 121;
      goto LABEL_27;
    }
    if ( *(_DWORD *)v14 )
    {
      if ( *(_DWORD *)a2 != 1
        && *(_DWORD *)v14 == 14
        && *(_QWORD *)(v14 + 4) == 0x5359532E59415032LL
        && *(_DWORD *)(v14 + 12) == 1178879022
        && *(_WORD *)(v14 + 16) == 12592 )
      {
        v9 = -2134834670;
        v13 = 132;
        goto LABEL_17;
      }
    }
    else if ( *(_DWORD *)a2 )
    {
      v9 = -2134834662;
      v13 = 125;
LABEL_17:
      v12 = v9;
      goto LABEL_28;
    }
    v14 += 20;
  }
  v16 = ValidateCustomProperties(*((_DWORD *)a2 + 38), *((const unsigned __int8 **)a2 + 20));
  v9 = v16;
  if ( v16 < 0 )
  {
    v13 = 136;
LABEL_27:
    v12 = (unsigned int)v16;
    goto LABEL_28;
  }
  v9 = ValidateAppletIdGroupAssetCollection(a3);
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 245;
    goto LABEL_3;
  }
  v9 = (*(__int64 (__fastcall **)(RoutingMgr *, unsigned __int16 *))(*(_QWORD *)this + 24LL))(this, v54);
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 248;
    goto LABEL_3;
  }
  v45 = (char *)this + 80;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v46 = 1;
  v51 = GUID_NULL;
  v17 = *((_QWORD *)this + 19);
  v18 = RoutingRegistryHelper::WriteAppletIdGroupRegKeys(v54, a2, a3, &v51);
  v9 = v18;
  if ( v18 >= 0 )
  {
    if ( *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 1) == 1 )
      ++*(_DWORD *)(v17 + 32);
    v47 = this;
    v48 = v54;
    v49 = &v51;
    v50 = 1;
    if ( (unsigned int)dword_18012F048 > 5 )
    {
      v19 = (RoutingMgr *)qword_18012F060;
      if ( (qword_18012F058 & 0x400000000000LL) != 0 && (qword_18012F060 & 0x400000000000LL) == qword_18012F060 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)a2 + 22), 0);
        v36 = *((unsigned __int8 *)a2 + 168);
        v37 = *((unsigned __int8 *)a2 + 8);
        v38 = *((_DWORD *)a2 + 1);
        v39 = *(_DWORD *)a2;
        v40[0] = *((_DWORD *)a2 + 35);
        v43 = &v51;
        *(_QWORD *)v44 = v54;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v20,
          (unsigned int)byte_18011C64D,
          v21,
          v22,
          (__int64)v44,
          (__int64)&v43,
          (__int64)v40,
          (__int64)&v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&v36,
          (__int64)&StringRawBuffer);
      }
    }
    v23 = RoutingMgr::TraceAppletIdRegistrations(v19, *((struct _AppletId **)a2 + 18), *((_DWORD *)a2 + 35), &v51);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
        (const char *)(unsigned int)v23,
        v32);
    if ( NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID != *(_OWORD *)((char *)this + 180)
      || RoutingMgr::IsLegacyUiccSelectionAvailable(this)
      || (*(GUID *)v24 = GUID_NULL, v25 = PaymentSelection::Store(v24), v9 = v25, v25 >= 0) )
    {
      *(_OWORD *)sourceString = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(sourceString[0]) = 0;
      SmartcardInterfaceInfoNameForRegistration = RoutingMgr::GetSmartcardInterfaceInfoNameForRegistration(
                                                    this,
                                                    &v51,
                                                    v54,
                                                    sourceString);
      v9 = SmartcardInterfaceInfoNameForRegistration;
      if ( SmartcardInterfaceInfoNameForRegistration >= 0 )
      {
        v29 = (const WCHAR *)sourceString;
        if ( si128.m128i_i64[1] > 7uLL )
          v29 = sourceString[0];
        HSTRING = MakeHSTRING(v29);
        **(_QWORD **)&v41.Data1 = HSTRING;
        *a4 = v51;
        std::wstring::~wstring(sourceString);
        v9 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
          (const char *)(unsigned int)SmartcardInterfaceInfoNameForRegistration,
          v32);
        std::wstring::~wstring(sourceString);
        v41 = v51;
        v28 = RoutingRegistrationStore::Unregister(*((RoutingRegistrationStore **)this + 19), v54, &v41);
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
            (const char *)(unsigned int)v28,
            v35);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x116,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
        (const char *)(unsigned int)v25,
        v32);
      v41 = v51;
      v26 = RoutingRegistrationStore::Unregister(*((RoutingRegistrationStore **)this + 19), v54, &v41);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
          (const char *)(unsigned int)v26,
          v34);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingregistrationstore.cpp",
      (const char *)(unsigned int)v18,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\routingmgr\\src\\routingmgr.cpp",
      (const char *)v9,
      v33);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  return v9;
}

```

## disassembly

```asm
0x18003226c  push    rbp
0x18003226e  push    rbx
0x18003226f  push    rsi
0x180032270  push    rdi
0x180032271  push    r12
0x180032273  push    r13
0x180032275  push    r14
0x180032277  push    r15
0x180032279  lea     rbp, [rsp-0B8h]
0x180032281  sub     rsp, 1B8h
0x180032288  mov     rax, cs:__security_cookie
0x18003228f  xor     rax, rsp
0x180032292  mov     [rbp+0F0h+var_50], rax
0x180032299  mov     r13, r9
0x18003229c  mov     r12, r8
0x18003229f  mov     rdi, rdx
0x1800322a2  mov     r14, rcx
0x1800322a5  mov     rax, [rbp+0F0h+arg_20]
0x1800322ac  mov     qword ptr [rbp+0F0h+var_170.Data1], rax
0x1800322b0  cmp     byte ptr [rcx+0B1h], 0
0x1800322b7  jnz     short loc_1800322DE
0x1800322b9  mov     ebx, 8007139Fh
0x1800322be  mov     edx, 0F1h; void *
0x1800322c3  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800322ca  mov     r9d, ebx; char *
0x1800322cd  mov     rcx, [rbp+0F8h]; this
0x1800322d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800322d9  jmp     loc_180032770
0x1800322de  test    rdi, rdi
0x1800322e1  jnz     short loc_1800322EF
0x1800322e3  mov     ebx, 80004003h
0x1800322e8  mov     edx, 0F2h
0x1800322ed  jmp     short loc_1800322C3
0x1800322ef  test    r13, r13
0x1800322f2  jnz     short loc_180032300
0x1800322f4  mov     ebx, 80004003h
0x1800322f9  mov     edx, 0F3h
0x1800322fe  jmp     short loc_1800322C3
0x180032300  mov     eax, [rdx+8Ch]
0x180032306  test    eax, eax
0x180032308  jnz     short loc_18003231B
0x18003230a  mov     r9d, 80070057h
0x180032310  mov     ebx, r9d
0x180032313  lea     edx, [rax+74h]
0x180032316  jmp     loc_1800323C7
0x18003231b  cmp     eax, 9
0x18003231e  jbe     short loc_180032333
0x180032320  mov     r9d, 80070057h
0x180032326  mov     ebx, r9d
0x180032329  mov     edx, 75h ; 'u'
0x18003232e  jmp     loc_1800323C7
0x180032333  mov     rsi, [rdx+90h]
0x18003233a  lea     rcx, [rax+rax*4]
0x18003233e  lea     r15, [rsi+rcx*4]
0x180032342  jmp     short loc_1800323A2
0x180032344  mov     rcx, rsi
0x180032347  call    ValidateAppletId
0x18003234c  mov     ebx, eax
0x18003234e  test    eax, eax
0x180032350  js      loc_1800323F3
0x180032356  cmp     dword ptr [rsi], 0
0x180032359  jnz     short loc_18003236F
0x18003235b  cmp     dword ptr [rdi], 0
0x18003235e  jz      short loc_18003239E
0x180032360  mov     ebx, 80C1021Ah
0x180032365  mov     edx, 7Dh ; '}'
0x18003236a  mov     r9d, ebx
0x18003236d  jmp     short loc_1800323C7
0x18003236f  cmp     dword ptr [rdi], 1
0x180032372  jz      short loc_18003239E
0x180032374  cmp     dword ptr [rsi], 0Eh
0x180032377  jnz     short loc_18003239E
0x180032379  mov     rax, [rsi+4]
0x18003237d  cmp     rax, cs:qword_1800A94F8
0x180032384  jnz     short loc_18003239E
0x180032386  mov     eax, [rsi+0Ch]
0x180032389  cmp     eax, cs:dword_1800A9500
0x18003238f  jnz     short loc_18003239E
0x180032391  movzx   eax, word ptr [rsi+10h]
0x180032395  cmp     ax, cs:word_1800A9504
0x18003239c  jz      short loc_1800323E4
0x18003239e  add     rsi, 14h
0x1800323a2  cmp     rsi, r15
0x1800323a5  jnz     short loc_180032344
0x1800323a7  mov     rdx, [rdi+0A0h]; unsigned __int8 *
0x1800323ae  mov     ecx, [rdi+98h]; unsigned int
0x1800323b4  call    ?ValidateCustomProperties@@YAJIPEBE@Z; ValidateCustomProperties(uint,uchar const *)
0x1800323b9  mov     ebx, eax
0x1800323bb  test    eax, eax
0x1800323bd  jns     short loc_1800323FA
0x1800323bf  mov     edx, 88h; void *
0x1800323c4  mov     r9d, eax; char *
0x1800323c7  lea     r8, aOnecoreuapDsNf_59; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800323ce  mov     rcx, [rbp+0F8h]; this
0x1800323d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800323da  mov     edx, 0F4h
0x1800323df  jmp     loc_1800322C3
0x1800323e4  mov     ebx, 80C10212h
0x1800323e9  mov     edx, 84h
0x1800323ee  jmp     loc_18003236A
0x1800323f3  mov     edx, 79h ; 'y'
0x1800323f8  jmp     short loc_1800323C4
0x1800323fa  mov     rcx, r12; struct _AppletIdGroupAssetCollection *
0x1800323fd  call    ?ValidateAppletIdGroupAssetCollection@@YAJPEBU_AppletIdGroupAssetCollection@@@Z; ValidateAppletIdGroupAssetCollection(_AppletIdGroupAssetCollection const *)
0x180032402  mov     ebx, eax
0x180032404  test    eax, eax
0x180032406  jns     short loc_180032412
0x180032408  mov     edx, 0F5h
0x18003240d  jmp     loc_1800322C3
0x180032412  mov     rax, [r14]
0x180032415  lea     rdx, [rbp+0F0h+var_E0]
0x180032419  mov     rcx, r14
0x18003241c  mov     rax, [rax+18h]
0x180032420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032425  mov     ebx, eax
0x180032427  test    eax, eax
0x180032429  jns     short loc_180032435
0x18003242b  mov     edx, 0F8h
0x180032430  jmp     loc_1800322C3
0x180032435  lea     r15, [r14+50h]
0x180032439  mov     [rbp+0F0h+var_148], r15
0x18003243d  mov     rcx, r15; lpCriticalSection
0x180032440  call    cs:__imp_EnterCriticalSection
0x180032446  mov     [rbp+0F0h+var_140], 1
0x18003244a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180032451  movdqu  xmmword ptr [rbp+0F0h+var_110.Data1], xmm0
0x180032456  mov     rsi, [r14+98h]
0x18003245d  lea     r9, [rbp+0F0h+var_110]; struct _GUID *
0x180032461  mov     r8, r12; struct _AppletIdGroupAssetCollection *
0x180032464  mov     rdx, rdi; struct _AppletIdGroup *
0x180032467  lea     rcx, [rbp+0F0h+var_E0]; unsigned __int16 *
0x18003246b  call    ?WriteAppletIdGroupRegKeys@RoutingRegistryHelper@@SAJPEBGPEBU_AppletIdGroup@@PEBU_AppletIdGroupAssetCollection@@PEAU_GUID@@@Z; RoutingRegistryHelper::WriteAppletIdGroupRegKeys(ushort const *,_AppletIdGroup const *,_AppletIdGroupAssetCollection const *,_GUID *)
0x180032470  mov     ebx, eax
0x180032472  test    eax, eax
0x180032474  jns     short loc_1800324B1
0x180032476  mov     rcx, [rbp+0F8h]; this
0x18003247d  mov     r9d, eax; char *
0x180032480  lea     r8, aOnecoreuapDsNf_23; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180032487  mov     edx, 70h ; 'p'; void *
0x18003248c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032491  mov     rcx, [rbp+0F8h]; this
0x180032498  mov     r9d, ebx; char *
0x18003249b  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800324a2  mov     edx, 0FDh; void *
0x1800324a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800324ac  jmp     loc_180032767
0x1800324b1  cmp     dword ptr [rdi], 1
0x1800324b4  jnz     short loc_1800324BF
0x1800324b6  cmp     dword ptr [rdi+4], 1
0x1800324ba  jnz     short loc_1800324BF
0x1800324bc  inc     dword ptr [rsi+20h]
0x1800324bf  mov     [rbp+0F0h+var_138], r14
0x1800324c3  lea     rax, [rbp+0F0h+var_E0]
0x1800324c7  mov     [rbp+0F0h+var_130], rax
0x1800324cb  lea     rax, [rbp+0F0h+var_110]
0x1800324cf  mov     [rbp+0F0h+var_128], rax
0x1800324d3  mov     [rbp+0F0h+var_120], 1
0x1800324d7  mov     eax, cs:dword_18012F048
0x1800324dd  cmp     eax, 5
0x1800324e0  jbe     loc_1800325BC
0x1800324e6  mov     rcx, cs:qword_18012F060
0x1800324ed  mov     rax, cs:qword_18012F058
0x1800324f4  mov     rdx, 400000000000h
0x1800324fe  test    rdx, rax
0x180032501  jz      loc_1800325BC
0x180032507  mov     rax, rcx
0x18003250a  and     rax, rdx
0x18003250d  cmp     rax, rcx
0x180032510  jnz     loc_1800325BC
0x180032516  xor     edx, edx; length
0x180032518  mov     rcx, [rdi+0B0h]; string
0x18003251f  call    cs:__imp_WindowsGetStringRawBuffer
0x180032525  mov     [rbp+0F0h+var_160], rax
0x180032529  movzx   eax, byte ptr [rdi+0A8h]
0x180032530  mov     [rsp+1F0h+var_190], eax
0x180032534  movzx   eax, byte ptr [rdi+8]
0x180032538  mov     [rsp+1F0h+var_18C], eax
0x18003253c  mov     eax, [rdi+4]
0x18003253f  mov     [rsp+1F0h+var_188], eax
0x180032543  mov     eax, [rdi]
0x180032545  mov     [rsp+1F0h+var_184], eax
0x180032549  mov     eax, [rdi+8Ch]
0x18003254f  mov     [rsp+1F0h+var_180], eax
0x180032553  lea     rax, [rbp+0F0h+var_110]
0x180032557  mov     [rbp+0F0h+var_158], rax
0x18003255b  lea     rax, [rbp+0F0h+var_E0]
0x18003255f  mov     qword ptr [rbp+0F0h+var_150], rax
0x180032563  lea     rax, [rbp+0F0h+var_160]
0x180032567  mov     [rsp+1F0h+var_198], rax
0x18003256c  lea     rax, [rsp+1F0h+var_190]
0x180032571  mov     [rsp+1F0h+var_1A0], rax
0x180032576  lea     rax, [rsp+1F0h+var_18C]
0x18003257b  mov     [rsp+1F0h+var_1A8], rax
0x180032580  lea     rax, [rsp+1F0h+var_188]
0x180032585  mov     [rsp+1F0h+var_1B0], rax
0x18003258a  lea     rax, [rsp+1F0h+var_184]
0x18003258f  mov     [rsp+1F0h+var_1B8], rax
0x180032594  lea     rax, [rsp+1F0h+var_180]
0x180032599  mov     [rsp+1F0h+var_1C0], rax
0x18003259e  lea     rax, [rbp+0F0h+var_158]
0x1800325a2  mov     [rsp+1F0h+var_1C8], rax
0x1800325a7  lea     rax, [rbp+0F0h+var_150]
0x1800325ab  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x1800325b0  lea     rdx, byte_18011C64D
0x1800325b7  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@55553@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800325bc  lea     r9, [rbp+0F0h+var_110]; struct _GUID *
0x1800325c0  mov     r8d, [rdi+8Ch]; unsigned int
0x1800325c7  mov     rdx, [rdi+90h]; struct _AppletId *
0x1800325ce  call    ?TraceAppletIdRegistrations@RoutingMgr@@AEAAJPEAU_AppletId@@KAEBU_GUID@@@Z; RoutingMgr::TraceAppletIdRegistrations(_AppletId *,ulong,_GUID const &)
0x1800325d3  mov     rcx, [rbp+0F8h]; this
0x1800325da  test    eax, eax
0x1800325dc  jns     short loc_1800325F2
0x1800325de  mov     r9d, eax; char *
0x1800325e1  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800325e8  mov     edx, 110h; void *
0x1800325ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800325f2  lea     r8, [r14+0B4h]
0x1800325f9  mov     rax, qword ptr cs:NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID
0x180032600  cmp     rax, [r8]
0x180032603  jnz     loc_18003269E
0x180032609  mov     rax, qword ptr cs:NFC_PAYMENT_APPLICATION_LEGACY_UICC_GUID+8
0x180032610  cmp     rax, [r8+8]
0x180032614  jnz     loc_18003269E
0x18003261a  mov     rcx, r14; this
0x18003261d  call    ?IsLegacyUiccSelectionAvailable@RoutingMgr@@AEAA_NXZ; RoutingMgr::IsLegacyUiccSelectionAvailable(void)
0x180032622  test    al, al
0x180032624  jnz     short loc_18003269E
0x180032626  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18003262d  movdqu  xmmword ptr [r8], xmm0
0x180032632  mov     rcx, r8; lpData
0x180032635  call    ?Store@PaymentSelection@@SAJAEBU1@@Z; PaymentSelection::Store(PaymentSelection const &)
0x18003263a  mov     ebx, eax
0x18003263c  test    eax, eax
0x18003263e  jns     short loc_18003269E
0x180032640  mov     rcx, [rbp+0F8h]; this
0x180032647  mov     r9d, eax; char *
0x18003264a  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180032651  mov     edx, 116h; void *
0x180032656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003265b  nop
0x18003265c  movaps  xmm0, xmmword ptr [rbp+0F0h+var_110.Data1]
0x180032660  movdqa  xmmword ptr [rbp+0F0h+var_170.Data1], xmm0
0x180032665  lea     r8, [rbp+0F0h+var_170]; struct _GUID
0x180032669  lea     rdx, [rbp+0F0h+var_E0]; unsigned __int16 *
0x18003266d  mov     rcx, [r14+98h]; this
0x180032674  call    ?Unregister@RoutingRegistrationStore@@QEAAJPEBGU_GUID@@@Z; RoutingRegistrationStore::Unregister(ushort const *,_GUID)
0x180032679  mov     rcx, [rbp+0F8h]; this
0x180032680  test    eax, eax
0x180032682  jns     short loc_180032699
0x180032684  mov     r9d, eax; char *
0x180032687  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003268e  mov     edx, 100h; void *
0x180032693  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032698  nop
0x180032699  jmp     loc_180032767
0x18003269e  xorps   xmm0, xmm0
0x1800326a1  movups  xmmword ptr [rbp+0F0h+sourceString], xmm0
0x1800326a5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800326ad  movdqu  [rbp+0F0h+var_F0], xmm1
0x1800326b2  xor     eax, eax
0x1800326b4  mov     word ptr [rbp+0F0h+sourceString], ax
0x1800326b8  lea     r9, [rbp+0F0h+sourceString]
0x1800326bc  lea     r8, [rbp+0F0h+var_E0]
0x1800326c0  lea     rdx, [rbp+0F0h+var_110]
0x1800326c4  mov     rcx, r14
0x1800326c7  call    ?GetSmartcardInterfaceInfoNameForRegistration@RoutingMgr@@AEAAJAEBU_GUID@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RoutingMgr::GetSmartcardInterfaceInfoNameForRegistration(_GUID const &,ushort const *,std::wstring *)
0x1800326cc  mov     ebx, eax
0x1800326ce  test    eax, eax
0x1800326d0  jns     short loc_180032737
0x1800326d2  mov     rcx, [rbp+0F8h]; this
0x1800326d9  mov     r9d, eax; char *
0x1800326dc  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800326e3  mov     edx, 11Bh; void *
0x1800326e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326ed  nop
0x1800326ee  lea     rcx, [rbp+0F0h+sourceString]
0x1800326f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800326f7  nop
0x1800326f8  movaps  xmm0, xmmword ptr [rbp+0F0h+var_110.Data1]
0x1800326fc  movdqa  xmmword ptr [rbp+0F0h+var_170.Data1], xmm0
0x180032701  lea     r8, [rbp+0F0h+var_170]; struct _GUID
0x180032705  lea     rdx, [rbp+0F0h+var_E0]; unsigned __int16 *
0x180032709  mov     rcx, [r14+98h]; this
0x180032710  call    ?Unregister@RoutingRegistrationStore@@QEAAJPEBGU_GUID@@@Z; RoutingRegistrationStore::Unregister(ushort const *,_GUID)
0x180032715  mov     rcx, [rbp+0F8h]; this
0x18003271c  test    eax, eax
0x18003271e  jns     short loc_180032735
0x180032720  mov     r9d, eax; char *
0x180032723  lea     r8, aOnecoreuapDsNf_15; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18003272a  mov     edx, 100h; void *
0x18003272f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180032734  nop
0x180032735  jmp     short loc_180032767
0x180032737  lea     rcx, [rbp+0F0h+sourceString]
0x18003273b  cmp     qword ptr [rbp+0F0h+var_F0+8], 7
0x180032740  cmova   rcx, [rbp+0F0h+sourceString]; sourceString
0x180032745  call    ?MakeHSTRING@@YAPEAUHSTRING__@@PEBG@Z; MakeHSTRING(ushort const *)
0x18003274a  mov     rcx, qword ptr [rbp+0F0h+var_170.Data1]
0x18003274e  mov     [rcx], rax
0x180032751  movaps  xmm0, xmmword ptr [rbp+0F0h+var_110.Data1]
  ... truncated ...
```
