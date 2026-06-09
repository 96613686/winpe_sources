# WaasMedic::CBinaryHealthPlugin::RunRemediation(ushort * * const,ulong &,ulong)

- ea: `0x1800424a4`
- end: `0x1800427d9`
- name: `?RunRemediation@CBinaryHealthPlugin@WaasMedic@@AEAAJQEAPEAGAEAKK@Z`
- size: `821`
- prototype: `__int64 __fastcall(WaasMedic::CBinaryHealthPlugin *__hidden this, unsigned __int16 **const, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800419d0`

## callees

- `0x180002058`
- `0x1800024a4`
- `0x180016c9c`
- `0x18002543c`
- `0x180041970`
- `0x180041d84`
- `0x1800424a4`
- `0x180042908`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800424f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800424f3`

## string_xrefs

- `0x180042506`: `CoCreateInstance for aSfpIntegrity failed on RunRemediation hr = 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CBinaryHealthPlugin::RunRemediation(
        WaasMedic::CBinaryHealthPlugin *this,
        unsigned __int16 **const a2,
        unsigned int *a3,
        unsigned int a4)
{
  HRESULT v6; // eax
  __int64 v7; // rcx
  const struct _tlgProvider_t *v8; // r8
  const char *v9; // r9
  unsigned int v10; // edi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  int v13; // r8d
  int v14; // r9d
  LPVOID v15; // rcx
  __int64 result; // rax
  _QWORD *v17; // rbx
  _QWORD *v18; // r13
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  unsigned int v23; // r14d
  const struct _tlgProvider_t *v24; // rax
  int v25; // r9d
  const struct _tlgProvider_t *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rdx
  LPVOID v29; // rcx
  __int64 v30; // [rsp+40h] [rbp-78h] BYREF
  __int64 v31; // [rsp+48h] [rbp-70h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v33[5]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  LPVOID ppv; // [rsp+D0h] [rbp+18h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp+20h] BYREF

  v37 = a4;
  *a3 = 0;
  ppv = 0;
  v6 = CoCreateInstance(&CLSID_SFPIntegrityCheckAndRepair, 0, 4u, &IID_ISFPIntegrityCheckAndRepair, &ppv);
  try
  {
    v10 = v6;
    if ( v6 >= 0 )
      goto LABEL_11;
    LogLevelW(2u, L"CoCreateInstance for aSfpIntegrity failed on RunRemediation hr = 0x%08X\n", (unsigned int)v6);
    v11 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v11 > 5u )
    {
      v12 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
      {
        v37 = v10;
        v30 = (__int64)&gc_pszVersionString;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v11,
          (unsigned int)&dword_180089C8C,
          v13,
          v14,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v37);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::GetImpl'::`2'::impl,
                            v12) )
    {
      v15 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
      }
      result = v10;
    }
    else
    {
LABEL_11:
      v17 = (_QWORD *)*((_QWORD *)this + 29);
      v18 = (_QWORD *)*((_QWORD *)this + 30);
      while ( v17 != v18 )
      {
        if ( !*((_BYTE *)v17 + 16) )
        {
          if ( v17[1] )
          {
            if ( *((_BYTE *)v17 + 17) )
            {
              v21 = WaasMedic::CBinaryHealthPlugin::RemediateCorruptedBinary(v7, v17, &ppv);
              if ( v21 < 0 )
                v10 = v21;
              v23 = (unsigned int)v21 >> 31;
            }
            else
            {
              LogLevelW(3u, L"Detected an unhealthy binary with no remediation: %ws", *v17);
              LOBYTE(v23) = 1;
              v24 = WaasMedic::TelemetryProvider::Provider();
              v26 = v24;
              v22 = *(unsigned int *)v24;
              if ( (unsigned int)v22 > 5 )
              {
                v27 = *((_QWORD *)v24 + 3);
                v22 = *((_QWORD *)v26 + 2);
                if ( (v22 & 0x400000000000LL) != 0 )
                {
                  v22 = v27 & 0x400000000000LL;
                  if ( (v27 & 0x400000000000LL) == v27 )
                  {
                    v32[0] = *v17;
                    v31 = (__int64)&gc_pszVersionString;
                    v30 = 0x1000000;
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                      (_DWORD)v26,
                      (unsigned int)byte_180089BBB,
                      (_DWORD)v26,
                      v25,
                      (__int64)&v30,
                      (__int64)&v31,
                      (__int64)v32);
                  }
                }
              }
            }
            v33[0] = *(_OWORD *)v17;
            v33[1] = *((_OWORD *)v17 + 1);
            WaasMedic::CBinaryHealthPlugin::LogBinaryStatus(v22, v33);
            if ( (_BYTE)v23 )
            {
              v28 = *a3;
              if ( (unsigned int)v28 < 0x15 )
              {
                LODWORD(v8) = (_DWORD)a2;
                a2[v28] = (unsigned __int16 *)v17[1];
                *a3 = v28 + 1;
              }
            }
          }
          else
          {
            LogLevelW(3u, L"Detected a missing binary. Skipping remediation: %ws", *v17);
            v19 = WaasMedic::TelemetryProvider::Provider();
            v8 = v19;
            v7 = *(unsigned int *)v19;
            if ( (unsigned int)v7 > 5 )
            {
              v20 = *((_QWORD *)v19 + 3);
              v7 = *((_QWORD *)v8 + 2);
              if ( (v7 & 0x400000000000LL) != 0 )
              {
                v7 = v20 & 0x400000000000LL;
                if ( (v20 & 0x400000000000LL) == v20 )
                {
                  v31 = *v17;
                  v30 = (__int64)&gc_pszVersionString;
                  v32[0] = 0x2000000;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                    (_DWORD)v8,
                    (unsigned int)&unk_180089CE8,
                    (_DWORD)v8,
                    (_DWORD)v9,
                    (__int64)v32,
                    (__int64)&v30,
                    (__int64)&v31);
                }
              }
            }
          }
        }
        v17 += 4;
      }
      v29 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v29 + 16LL))(v29);
      }
      result = v10;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x25D, (unsigned int)v8, v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800424a4  mov     rax, rsp
0x1800424a7  mov     [rax+20h], r9d
0x1800424ab  mov     [rax+10h], rdx
0x1800424af  push    rbx
0x1800424b0  push    rsi
0x1800424b1  push    rdi
0x1800424b2  push    r12
0x1800424b4  push    r13
0x1800424b6  push    r14
0x1800424b8  push    r15
0x1800424ba  sub     rsp, 80h
0x1800424c1  mov     r12, r8
0x1800424c4  mov     r14, rcx
0x1800424c7  mov     dword ptr [r8], 0
0x1800424ce  mov     qword ptr [rax+18h], 0
0x1800424d6  lea     rax, [rax+18h]
0x1800424da  mov     [rsp+0B8h+ppv], rax; ppv
0x1800424df  lea     r9, IID_ISFPIntegrityCheckAndRepair; riid
0x1800424e6  xor     edx, edx; pUnkOuter
0x1800424e8  lea     r8d, [rdx+4]; dwClsContext
0x1800424ec  lea     rcx, CLSID_SFPIntegrityCheckAndRepair; rclsid
0x1800424f3  call    cs:__imp_CoCreateInstance
0x1800424f9  mov     edi, eax
0x1800424fb  test    eax, eax
0x1800424fd  jns     loc_1800425D7
0x180042503  mov     r8d, eax
0x180042506  lea     rdx, aCocreateinstan; "CoCreateInstance for aSfpIntegrity fail"...
0x18004250d  mov     ecx, 2; unsigned __int8
0x180042512  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180042517  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004251c  mov     ecx, [rax]
0x18004251e  mov     rsi, 400000000000h
0x180042528  cmp     ecx, 5
0x18004252b  jbe     short loc_180042593
0x18004252d  mov     rdx, [rax+18h]
0x180042531  mov     rcx, [rax+10h]
0x180042535  test    rsi, rcx
0x180042538  jz      short loc_180042593
0x18004253a  mov     rcx, rdx
0x18004253d  and     rcx, rsi
0x180042540  cmp     rcx, rdx
0x180042543  jnz     short loc_180042593
0x180042545  mov     [rsp+0B8h+arg_18], edi
0x18004254c  lea     r15, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180042553  mov     [rsp+0B8h+var_78], r15
0x180042558  mov     [rsp+0B8h+var_70], 1000000h
0x180042561  lea     rcx, [rsp+0B8h+arg_18]
0x180042569  mov     [rsp+0B8h+var_88], rcx
0x18004256e  lea     rcx, [rsp+0B8h+var_78]
0x180042573  mov     [rsp+0B8h+var_90], rcx
0x180042578  lea     rcx, [rsp+0B8h+var_70]
0x18004257d  mov     [rsp+0B8h+ppv], rcx
0x180042582  lea     rdx, dword_180089C8C
0x180042589  mov     rcx, rax
0x18004258c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180042591  jmp     short loc_18004259A
0x180042593  lea     r15, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18004259a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError> `wil::Feature<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::GetImpl(void)'::`2'::impl
0x1800425a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::__private_IsEnabled(void)
0x1800425a6  test    al, al
0x1800425a8  jz      short loc_1800425E8
0x1800425aa  mov     rcx, [rsp+0B8h+arg_10]
0x1800425b2  test    rcx, rcx
0x1800425b5  jz      short loc_1800425D0
0x1800425b7  mov     [rsp+0B8h+arg_10], 0
0x1800425c3  mov     rax, [rcx]
0x1800425c6  mov     rax, [rax+10h]
0x1800425ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800425cf  nop
0x1800425d0  mov     eax, edi
0x1800425d2  jmp     loc_1800427C5
0x1800425d7  mov     rsi, 400000000000h
0x1800425e1  lea     r15, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800425e8  mov     rbx, [r14+0E8h]
0x1800425ef  mov     r13, [r14+0F0h]
0x1800425f6  cmp     rbx, r13
0x1800425f9  jz      loc_180042794
0x1800425ff  cmp     byte ptr [rbx+10h], 0
0x180042603  jnz     loc_18004278B
0x180042609  cmp     qword ptr [rbx+8], 0
0x18004260e  jnz     loc_1800426A3
0x180042614  mov     r8, [rbx]
0x180042617  lea     rdx, aDetectedAMissi; "Detected a missing binary. Skipping rem"...
0x18004261e  mov     ecx, 3; unsigned __int8
0x180042623  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180042628  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004262d  mov     r8, rax
0x180042630  mov     ecx, [rax]
0x180042632  cmp     ecx, 5
0x180042635  jbe     loc_18004278B
0x18004263b  mov     rax, [rax+18h]
0x18004263f  mov     rcx, [r8+10h]
0x180042643  test    rsi, rcx
0x180042646  jz      loc_18004278B
0x18004264c  mov     rcx, rax
0x18004264f  and     rcx, rsi
0x180042652  cmp     rcx, rax
0x180042655  jnz     loc_18004278B
0x18004265b  mov     rax, [rbx]
0x18004265e  mov     [rsp+0B8h+var_70], rax
0x180042663  mov     [rsp+0B8h+var_78], r15
0x180042668  mov     [rsp+0B8h+var_68], 2000000h
0x180042671  lea     rax, [rsp+0B8h+var_70]
0x180042676  mov     [rsp+0B8h+var_88], rax
0x18004267b  lea     rax, [rsp+0B8h+var_78]
0x180042680  mov     [rsp+0B8h+var_90], rax
0x180042685  lea     rax, [rsp+0B8h+var_68]
0x18004268a  mov     [rsp+0B8h+ppv], rax
0x18004268f  lea     rdx, unk_180089CE8
0x180042696  mov     rcx, r8
0x180042699  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18004269e  jmp     loc_18004278B
0x1800426a3  cmp     byte ptr [rbx+11h], 0
0x1800426a7  jz      short loc_1800426CA
0x1800426a9  lea     r8, [rsp+0B8h+arg_10]
0x1800426b1  mov     rdx, rbx
0x1800426b4  call    ?RemediateCorruptedBinary@CBinaryHealthPlugin@WaasMedic@@QEAAJAEAUtagBinaryHealthInfo@2@AEAV?$XInterface@UISFPIntegrityCheckAndRepair@@@2@@Z; WaasMedic::CBinaryHealthPlugin::RemediateCorruptedBinary(WaasMedic::tagBinaryHealthInfo &,WaasMedic::XInterface<ISFPIntegrityCheckAndRepair> &)
0x1800426b9  mov     r14d, eax
0x1800426bc  test    eax, eax
0x1800426be  cmovs   edi, eax
0x1800426c1  shr     r14d, 1Fh
0x1800426c5  jmp     loc_18004274B
0x1800426ca  mov     r8, [rbx]
0x1800426cd  lea     rdx, aDetectedAnUnhe; "Detected an unhealthy binary with no re"...
0x1800426d4  mov     ecx, 3; unsigned __int8
0x1800426d9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800426de  mov     r14b, 1
0x1800426e1  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800426e6  mov     r8, rax
0x1800426e9  mov     ecx, [rax]
0x1800426eb  cmp     ecx, 5
0x1800426ee  jbe     short loc_18004274B
0x1800426f0  mov     rax, [rax+18h]
0x1800426f4  mov     rcx, [r8+10h]
0x1800426f8  test    rsi, rcx
0x1800426fb  jz      short loc_18004274B
0x1800426fd  mov     rcx, rax
0x180042700  and     rcx, rsi
0x180042703  cmp     rcx, rax
0x180042706  jnz     short loc_18004274B
0x180042708  mov     rax, [rbx]
0x18004270b  mov     [rsp+0B8h+var_68], rax
0x180042710  mov     [rsp+0B8h+var_70], r15
0x180042715  mov     [rsp+0B8h+var_78], 1000000h
0x18004271e  lea     rax, [rsp+0B8h+var_68]
0x180042723  mov     [rsp+0B8h+var_88], rax
0x180042728  lea     rax, [rsp+0B8h+var_70]
0x18004272d  mov     [rsp+0B8h+var_90], rax
0x180042732  lea     rax, [rsp+0B8h+var_78]
0x180042737  mov     [rsp+0B8h+ppv], rax
0x18004273c  lea     rdx, byte_180089BBB
0x180042743  mov     rcx, r8
0x180042746  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18004274b  movups  xmm0, xmmword ptr [rbx]
0x18004274e  movaps  [rsp+0B8h+var_58], xmm0
0x180042753  movups  xmm1, xmmword ptr [rbx+10h]
0x180042757  movaps  [rsp+0B8h+var_48], xmm1
0x18004275c  lea     rdx, [rsp+0B8h+var_58]
0x180042761  call    ?LogBinaryStatus@CBinaryHealthPlugin@WaasMedic@@AEAAXUtagBinaryHealthInfo@2@@Z; WaasMedic::CBinaryHealthPlugin::LogBinaryStatus(WaasMedic::tagBinaryHealthInfo)
0x180042766  test    r14b, r14b
0x180042769  jz      short loc_18004278B
0x18004276b  mov     edx, [r12]
0x18004276f  cmp     edx, 15h
0x180042772  jnb     short loc_18004278B
0x180042774  mov     rax, [rbx+8]
0x180042778  mov     r8, [rsp+0B8h+arg_8]
0x180042780  mov     [r8+rdx*8], rax
0x180042784  lea     eax, [rdx+1]
0x180042787  mov     [r12], eax
0x18004278b  add     rbx, 20h ; ' '
0x18004278f  jmp     loc_1800425F6
0x180042794  mov     rcx, [rsp+0B8h+arg_10]
0x18004279c  test    rcx, rcx
0x18004279f  jz      short loc_1800427BA
0x1800427a1  mov     [rsp+0B8h+arg_10], 0
0x1800427ad  mov     rax, [rcx]
0x1800427b0  mov     rax, [rax+10h]
0x1800427b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427b9  nop
0x1800427ba  mov     eax, edi
0x1800427bc  jmp     short loc_1800427C5
0x1800427be  mov     eax, [rsp+0B8h+arg_18]
0x1800427c5  add     rsp, 80h
0x1800427cc  pop     r15
0x1800427ce  pop     r14
0x1800427d0  pop     r13
0x1800427d2  pop     r12
0x1800427d4  pop     rdi
0x1800427d5  pop     rsi
0x1800427d6  pop     rbx
0x1800427d7  retn
```
