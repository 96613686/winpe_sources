# WaasMedic::CBinaryHealthPlugin::RunDetection(bool &)

- ea: `0x180042198`
- end: `0x18004249e`
- name: `?RunDetection@CBinaryHealthPlugin@WaasMedic@@AEAAJAEA_N@Z`
- size: `774`
- prototype: `__int64 __fastcall(WaasMedic::CBinaryHealthPlugin *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180040f00`
- `0x1800419d0`

## callees

- `0x1800024a4`
- `0x18000b308`
- `0x180016c9c`
- `0x18002543c`
- `0x180028b78`
- `0x180041970`
- `0x180041bac`
- `0x180042198`
- `0x180042908`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042299`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180042299`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004223c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180042260`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004223c`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180042260`

## string_xrefs

- `0x18004246e`: `onecore\enduser\waasmedic\lib\plugins\binaryhealthplugin.cpp`
- `0x180042421`: `Completed detection, found %d unhealthy binaries.`
- `0x1800422ac`: `CoCreateInstance for aSfpIntegrity failed on RunDetection hr = 0x%08X\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CBinaryHealthPlugin::RunDetection(
        WaasMedic::CBinaryHealthPlugin *this,
        bool *a2,
        __int64 a3,
        unsigned int *a4)
{
  unsigned int v5; // r15d
  bool v6; // r14
  unsigned int *v7; // r9
  int DwordValue; // eax
  unsigned int v9; // edi
  char v10; // r12
  HRESULT v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // esi
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdx
  int v16; // r9d
  unsigned int v17; // r8d
  const char *v18; // r9
  LPVOID v19; // rcx
  __int64 result; // rax
  __int64 v21; // rdi
  __int64 v22; // r13
  int v23; // eax
  int BinaryForCorruption; // eax
  char v25; // al
  LPVOID v26; // rcx
  const char *v27; // [rsp+28h] [rbp-90h]
  unsigned __int16 v28[4]; // [rsp+40h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-70h] BYREF
  __int64 v30; // [rsp+50h] [rbp-68h] BYREF
  _OWORD v31[5]; // [rsp+60h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v34; // [rsp+D0h] [rbp+18h] BYREF
  int v35; // [rsp+D8h] [rbp+20h] BYREF

  v5 = 0;
  LOBYTE(v34) = 0;
  v35 = 0;
  *(_DWORD *)v28 = 0;
  v6 = 0;
  if ( WaasMedic::RegQueryDwordValue(
         (WaasMedic *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_18006C1C0,
         (const unsigned __int16 *)&v35,
         a4) >= 0 )
    v6 = v35 == 1;
  DwordValue = WaasMedic::RegQueryDwordValue((WaasMedic *)0xFFFFFFFF80000002LL, (HKEY)&stru_18006C2D0, v28, v7);
  try
  {
    v9 = DwordValue;
    if ( DwordValue < 0 )
    {
      if ( DwordValue != -2147024894 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1C7,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\binaryhealthplugin.cpp",
          (const char *)(unsigned int)DwordValue,
          (int)"IsServerCoreEdition failed.",
          v27);
        return v9;
      }
    }
    else if ( *(_DWORD *)v28 == 1 )
    {
      v6 = 1;
    }
    v35 = -1;
    RtlGetDeviceFamilyInfoEnum(0, &v35, 0);
    if ( v35 == 16 || (v35 = -1, RtlGetDeviceFamilyInfoEnum(0, &v35, 0), v10 = 0, v35 == 14) )
      v10 = 1;
    ppv = 0;
    v11 = CoCreateInstance(&CLSID_SFPIntegrityCheckAndRepair, 0, 4u, &IID_ISFPIntegrityCheckAndRepair, &ppv);
    v13 = v11;
    if ( v11 >= 0 )
      goto LABEL_20;
    LogLevelW(2u, L"CoCreateInstance for aSfpIntegrity failed on RunDetection hr = 0x%08X\n", (unsigned int)v11);
    v14 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      v15 = *((_QWORD *)v14 + 3);
      if ( (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0 && (v15 & 0x400000000000LL) == v15 )
      {
        v35 = v13;
        *(_QWORD *)v28 = &gc_pszVersionString;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)word_180089D42,
          0,
          v16,
          (__int64)&v30,
          (__int64)v28,
          (__int64)&v35);
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::GetImpl'::`2'::impl,
                            v15) )
    {
      v19 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      }
      result = v13;
    }
    else
    {
LABEL_20:
      v21 = *((_QWORD *)this + 29);
      v22 = *((_QWORD *)this + 30);
      while ( v21 != v22 )
      {
        if ( (!v6 || *(_BYTE *)(v21 + 18)) && (!v10 || *(_BYTE *)(v21 + 19)) )
        {
          BinaryForCorruption = WaasMedic::CBinaryHealthPlugin::QueryBinaryForCorruption(
                                  v12,
                                  *(_QWORD *)v21,
                                  *(_QWORD *)(v21 + 8),
                                  (unsigned int)&ppv,
                                  (__int64)&v34);
          if ( BinaryForCorruption < 0 )
          {
            v13 = BinaryForCorruption;
          }
          else
          {
            if ( (_BYTE)v34 )
            {
              ++v5;
              v25 = 0;
            }
            else
            {
              v25 = 1;
            }
            *(_BYTE *)(v21 + 16) = v25;
          }
          v23 = v13;
        }
        else
        {
          *(_BYTE *)(v21 + 16) = 1;
          v23 = -2147023285;
        }
        *(_DWORD *)(v21 + 20) = v23;
        v31[0] = *(_OWORD *)v21;
        v31[1] = *(_OWORD *)(v21 + 16);
        WaasMedic::CBinaryHealthPlugin::LogBinaryStatus(v12, v31);
        LOBYTE(v34) = 0;
        v21 += 32;
      }
      *a2 = v5 != 0;
      LogLevelW(5u, L"Completed detection, found %d unhealthy binaries.", v5);
      v26 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      }
      result = v13;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x209, v17, v18);
  }
  return result;
}

```

## disassembly

```asm
0x180042198  mov     rax, rsp
0x18004219b  mov     [rax+10h], rdx
0x18004219f  push    rbx
0x1800421a0  push    rsi
0x1800421a1  push    rdi
0x1800421a2  push    r12
0x1800421a4  push    r13
0x1800421a6  push    r14
0x1800421a8  push    r15
0x1800421aa  sub     rsp, 80h
0x1800421b1  mov     r13, rcx
0x1800421b4  xor     r15d, r15d
0x1800421b7  mov     [rax+18h], r15b
0x1800421bb  mov     [rax+20h], r15d
0x1800421bf  mov     [rax-78h], r15d
0x1800421c3  movzx   r14d, r15b
0x1800421c7  lea     r8, [rax+20h]; unsigned __int16 *
0x1800421cb  lea     rdx, stru_18006C1C0; HKEY
0x1800421d2  mov     rdi, 0FFFFFFFF80000002h
0x1800421d9  mov     rcx, rdi; this
0x1800421dc  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1800421e1  lea     ebx, [r15+1]
0x1800421e5  test    eax, eax
0x1800421e7  js      short loc_1800421F4
0x1800421e9  cmp     [rsp+0B8h+arg_18], ebx
0x1800421f0  cmovz   r14d, ebx
0x1800421f4  lea     r8, [rsp+0B8h+var_78]; unsigned __int16 *
0x1800421f9  lea     rdx, stru_18006C2D0; HKEY
0x180042200  mov     rcx, rdi; this
0x180042203  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x180042208  mov     edi, eax
0x18004220a  test    eax, eax
0x18004220c  js      short loc_180042219
0x18004220e  cmp     dword ptr [rsp+0B8h+var_78], ebx
0x180042212  jnz     short loc_180042225
0x180042214  mov     r14b, bl
0x180042217  jmp     short loc_180042225
0x180042219  cmp     edi, 80070002h
0x18004221f  jnz     loc_180042457
0x180042225  or      edi, 0FFFFFFFFh
0x180042228  mov     [rsp+0B8h+arg_18], edi
0x18004222f  xor     r8d, r8d
0x180042232  lea     rdx, [rsp+0B8h+arg_18]
0x18004223a  xor     ecx, ecx
0x18004223c  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180042242  cmp     [rsp+0B8h+arg_18], 10h
0x18004224a  jz      short loc_180042273
0x18004224c  mov     [rsp+0B8h+arg_18], edi
0x180042253  xor     r8d, r8d
0x180042256  lea     rdx, [rsp+0B8h+arg_18]
0x18004225e  xor     ecx, ecx
0x180042260  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180042266  cmp     [rsp+0B8h+arg_18], 0Eh
0x18004226e  mov     r12b, r15b
0x180042271  jnz     short loc_180042276
0x180042273  mov     r12b, bl
0x180042276  mov     [rsp+0B8h+var_70], r15
0x18004227b  lea     rax, [rsp+0B8h+var_70]
0x180042280  mov     [rsp+0B8h+ppv], rax; ppv
0x180042285  lea     r9, IID_ISFPIntegrityCheckAndRepair; riid
0x18004228c  xor     edx, edx; pUnkOuter
0x18004228e  lea     r8d, [rdx+4]; dwClsContext
0x180042292  lea     rcx, CLSID_SFPIntegrityCheckAndRepair; rclsid
0x180042299  call    cs:__imp_CoCreateInstance
0x18004229f  mov     esi, eax
0x1800422a1  test    eax, eax
0x1800422a3  jns     loc_18004236A
0x1800422a9  mov     r8d, eax
0x1800422ac  lea     rdx, aCocreateinstan_0; "CoCreateInstance for aSfpIntegrity fail"...
0x1800422b3  mov     ecx, 2; unsigned __int8
0x1800422b8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800422bd  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800422c2  mov     ecx, [rax]
0x1800422c4  cmp     ecx, 5
0x1800422c7  jbe     short loc_180042337
0x1800422c9  mov     rdx, [rax+18h]
0x1800422cd  mov     rcx, [rax+10h]
0x1800422d1  mov     r8, 400000000000h
0x1800422db  test    r8, rcx
0x1800422de  jz      short loc_180042337
0x1800422e0  mov     rcx, rdx
0x1800422e3  and     rcx, r8
0x1800422e6  cmp     rcx, rdx
0x1800422e9  jnz     short loc_180042337
0x1800422eb  mov     [rsp+0B8h+arg_18], esi
0x1800422f2  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800422f9  mov     qword ptr [rsp+0B8h+var_78], rcx
0x1800422fe  mov     [rsp+0B8h+var_68], 1000000h
0x180042307  lea     rcx, [rsp+0B8h+arg_18]
0x18004230f  mov     [rsp+0B8h+var_88], rcx
0x180042314  lea     rcx, [rsp+0B8h+var_78]
0x180042319  mov     [rsp+0B8h+var_90], rcx
0x18004231e  lea     rcx, [rsp+0B8h+var_68]
0x180042323  mov     [rsp+0B8h+ppv], rcx
0x180042328  lea     rdx, word_180089D42
0x18004232f  mov     rcx, rax
0x180042332  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180042337  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError> `wil::Feature<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::GetImpl(void)'::`2'::impl
0x18004233e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BinaryHealthPlugin_Handle_CbsBusyError>::__private_IsEnabled(void)
0x180042343  test    al, al
0x180042345  jz      short loc_18004236A
0x180042347  mov     rcx, [rsp+0B8h+var_70]
0x18004234c  test    rcx, rcx
0x18004234f  jz      short loc_180042363
0x180042351  mov     [rsp+0B8h+var_70], r15
0x180042356  mov     rax, [rcx]
0x180042359  mov     rax, [rax+10h]
0x18004235d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042362  nop
0x180042363  mov     eax, esi
0x180042365  jmp     loc_18004248A
0x18004236a  mov     rdi, [r13+0E8h]
0x180042371  mov     r13, [r13+0F0h]
0x180042378  cmp     rdi, r13
0x18004237b  jz      loc_18004240E
0x180042381  test    r14b, r14b
0x180042384  jz      short loc_18004238C
0x180042386  cmp     byte ptr [rdi+12h], 0
0x18004238a  jz      short loc_180042397
0x18004238c  test    r12b, r12b
0x18004238f  jz      short loc_1800423A1
0x180042391  cmp     byte ptr [rdi+13h], 0
0x180042395  jnz     short loc_1800423A1
0x180042397  mov     [rdi+10h], bl
0x18004239a  mov     eax, 8007064Bh
0x18004239f  jmp     short loc_1800423DF
0x1800423a1  lea     rax, [rsp+0B8h+arg_10]
0x1800423a9  mov     [rsp+0B8h+ppv], rax
0x1800423ae  lea     r9, [rsp+0B8h+var_70]
0x1800423b3  mov     r8, [rdi+8]
0x1800423b7  mov     rdx, [rdi]
0x1800423ba  call    ?QueryBinaryForCorruption@CBinaryHealthPlugin@WaasMedic@@QEAAJPEBGPEAGAEAV?$XInterface@UISFPIntegrityCheckAndRepair@@@2@PEA_N@Z; WaasMedic::CBinaryHealthPlugin::QueryBinaryForCorruption(ushort const *,ushort *,WaasMedic::XInterface<ISFPIntegrityCheckAndRepair> &,bool *)
0x1800423bf  test    eax, eax
0x1800423c1  js      short loc_1800423DB
0x1800423c3  cmp     byte ptr [rsp+0B8h+arg_10], 0
0x1800423cb  jz      short loc_1800423D4
0x1800423cd  add     r15d, ebx
0x1800423d0  xor     al, al
0x1800423d2  jmp     short loc_1800423D6
0x1800423d4  mov     al, bl
0x1800423d6  mov     [rdi+10h], al
0x1800423d9  jmp     short loc_1800423DD
0x1800423db  mov     esi, eax
0x1800423dd  mov     eax, esi
0x1800423df  mov     [rdi+14h], eax
0x1800423e2  movups  xmm0, xmmword ptr [rdi]
0x1800423e5  movaps  [rsp+0B8h+var_58], xmm0
0x1800423ea  movups  xmm1, xmmword ptr [rdi+10h]
0x1800423ee  movaps  [rsp+0B8h+var_48], xmm1
0x1800423f3  lea     rdx, [rsp+0B8h+var_58]
0x1800423f8  call    ?LogBinaryStatus@CBinaryHealthPlugin@WaasMedic@@AEAAXUtagBinaryHealthInfo@2@@Z; WaasMedic::CBinaryHealthPlugin::LogBinaryStatus(WaasMedic::tagBinaryHealthInfo)
0x1800423fd  mov     byte ptr [rsp+0B8h+arg_10], 0
0x180042405  add     rdi, 20h ; ' '
0x180042409  jmp     loc_180042378
0x18004240e  test    r15d, r15d
0x180042411  setnz   al
0x180042414  mov     rcx, [rsp+0B8h+arg_8]
0x18004241c  mov     [rcx], al
0x18004241e  mov     r8d, r15d
0x180042421  lea     rdx, aCompletedDetec; "Completed detection, found %d unhealthy"...
0x180042428  mov     ecx, 5; unsigned __int8
0x18004242d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180042432  nop
0x180042433  mov     rcx, [rsp+0B8h+var_70]
0x180042438  test    rcx, rcx
0x18004243b  jz      short loc_180042453
0x18004243d  mov     [rsp+0B8h+var_70], 0
0x180042446  mov     rax, [rcx]
0x180042449  mov     rax, [rax+10h]
0x18004244d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042452  nop
0x180042453  mov     eax, esi
0x180042455  jmp     short loc_18004248A
0x180042457  mov     rcx, [rsp+0B8h]; this
0x18004245f  lea     rax, aIsservercoreed; "IsServerCoreEdition failed."
0x180042466  mov     [rsp+0B8h+ppv], rax; int
0x18004246b  mov     r9d, edi; char *
0x18004246e  lea     r8, aOnecoreEnduser_47; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180042475  mov     edx, 1C7h; void *
0x18004247a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004247f  mov     eax, edi
0x180042481  jmp     short loc_18004248A
0x180042483  mov     eax, [rsp+0B8h+arg_10]
0x18004248a  add     rsp, 80h
0x180042491  pop     r15
0x180042493  pop     r14
0x180042495  pop     r13
0x180042497  pop     r12
0x180042499  pop     rdi
0x18004249a  pop     rsi
0x18004249b  pop     rbx
0x18004249c  retn
```
