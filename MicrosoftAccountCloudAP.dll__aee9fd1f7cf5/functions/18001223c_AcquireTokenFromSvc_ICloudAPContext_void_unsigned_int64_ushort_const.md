# AcquireTokenFromSvc(ICloudAPContext *,void *,unsigned __int64,ushort const *)

- ea: `0x18001223c`
- end: `0x18001249b`
- name: `?AcquireTokenFromSvc@@YAJPEAVICloudAPContext@@PEAX_KPEBG@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180015468`

## callees

- `0x1800010c0`
- `0x1800011fc`
- `0x180003160`
- `0x180008440`
- `0x18000baac`
- `0x180010040`
- `0x180010064`
- `0x18001223c`
- `0x1800267c0`
- `0x180032010`

## string_xrefs

- `0x1800122e6`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800123a0`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800123e8`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x1800122b9`: `AcquireTokenFromSvc`
- `0x180012393`: `WLIDCAcquireTokens failed, hr=0x%x`
- `0x1800123db`: `AcquireTokenFromSvc failed, hrRequestStatus = 0x%x, hrAuthState = 0x%x`

## pseudocode

```c
__int64 __fastcall AcquireTokenFromSvc(struct ICloudAPContext *a1, void *a2, __int64 a3, const unsigned __int16 *a4)
{
  __int64 v7; // rsi
  const unsigned __int16 *v8; // rax
  int v9; // eax
  int v10; // ebx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  unsigned int v14; // ebx
  const unsigned __int16 *v16; // [rsp+20h] [rbp-A9h]
  __int64 v17; // [rsp+20h] [rbp-A9h]
  __int64 v18; // [rsp+28h] [rbp-A1h]
  int v19; // [rsp+40h] [rbp-89h] BYREF
  int v20; // [rsp+44h] [rbp-85h] BYREF
  int v21; // [rsp+48h] [rbp-81h] BYREF
  void *v22; // [rsp+50h] [rbp-79h] BYREF
  __int64 v23; // [rsp+58h] [rbp-71h] BYREF
  _OWORD v24[2]; // [rsp+60h] [rbp-69h] BYREF
  const wchar_t *v25; // [rsp+80h] [rbp-49h] BYREF
  __int128 v26; // [rsp+88h] [rbp-41h]
  __int128 v27; // [rsp+98h] [rbp-31h]
  __int128 v28; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-11h]
  _QWORD v30[4]; // [rsp+C0h] [rbp-9h] BYREF
  int v31[4]; // [rsp+E0h] [rbp+17h] BYREF
  int v32; // [rsp+F0h] [rbp+27h]

  v19 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v22 = 0;
  memset(v24, 0, sizeof(v24));
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v28 = 0;
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(struct ICloudAPContext *))(*(_QWORD *)a1 + 24LL))(a1);
  v30[0] = "AcquireTokenFromSvc";
  v30[1] = &v19;
  v30[2] = 0;
  v30[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "AcquireTokenFromSvc",
    (const char *)0x622,
    0,
    v16);
  HIDWORD(v27) = 1;
  v25 = L"http://Passport.NET/tb";
  *(_QWORD *)&v27 = 0;
  *(_QWORD *)&v24[0] = a3 | 0x20480;
  (*((void (__fastcall **)(__int128 *))g_MSACloudAPPluginLsaFunctions + 12))(&v28);
  if ( (WORD4(v28) & 0x1800) != 0 )
    *(_QWORD *)&v24[0] |= 0x40000000uLL;
  v8 = &qword_18003AB48;
  if ( a4 )
    v8 = a4;
  *((_QWORD *)&v24[0] + 1) = v8;
  v9 = (*(__int64 (__fastcall **)(__int64, void *, _OWORD *, __int64, const wchar_t **, int *, void **))(*(_QWORD *)v7 + 24LL))(
         v7,
         a2,
         v24,
         1,
         &v25,
         v31,
         &v22);
  v10 = v9;
  if ( v9 >= 0
    || (LODWORD(v17) = v9,
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
          0x641u,
          L"WLIDCAcquireTokens failed, hr=0x%x",
          v17),
        v19 = LiveMapHResultToNtStatus(v10),
        v19 >= 0) )
  {
    v10 = v31[2];
    if ( v31[2] < 0 || (v10 = v31[0], v31[0] < 0) )
    {
      LODWORD(v18) = v31[0];
      LODWORD(v17) = v31[2];
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
        0x64Du,
        L"AcquireTokenFromSvc failed, hrRequestStatus = 0x%x, hrAuthState = 0x%x",
        v17,
        v18);
      v19 = LiveMapHResultToNtStatus(v10);
    }
  }
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    v23 = 50331648;
    v20 = v19;
    v21 = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v11,
      (unsigned int)&unk_1800440B0,
      v12,
      v13,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v23);
  }
  v14 = v19;
  CTraceFuncW<long>::~CTraceFuncW<long>(v30);
  if ( v22 )
    LiveFree(v22);
  return v14;
}

```

## disassembly

```asm
0x18001223c  push    rbp
0x18001223e  push    rbx
0x18001223f  push    rsi
0x180012240  push    rdi
0x180012241  push    r14
0x180012243  lea     rbp, [rsp-37h]
0x180012248  sub     rsp, 100h
0x18001224f  mov     rax, cs:__security_cookie
0x180012256  xor     rax, rsp
0x180012259  mov     [rbp+57h+var_28], rax
0x18001225d  mov     rdi, r9
0x180012260  mov     rbx, r8
0x180012263  mov     r14, rdx
0x180012266  mov     [rsp+120h+var_E0], 0
0x18001226e  mov     [rbp+57h+var_A0], 0
0x180012276  xorps   xmm0, xmm0
0x180012279  movups  [rbp+57h+var_98], xmm0
0x18001227d  movups  [rbp+57h+var_88], xmm0
0x180012281  mov     [rbp+57h+var_D0], 0
0x180012289  movups  [rbp+57h+var_C0], xmm0
0x18001228d  movups  [rbp+57h+var_B0], xmm0
0x180012291  xorps   xmm1, xmm1
0x180012294  movdqu  xmmword ptr [rbp+57h+var_40], xmm1
0x180012299  mov     [rbp+57h+var_30], 0
0x1800122a0  xor     eax, eax
0x1800122a2  movups  [rbp+57h+var_78], xmm0
0x1800122a6  mov     [rbp+57h+var_68], rax
0x1800122aa  mov     rax, [rcx]
0x1800122ad  mov     rax, [rax+18h]
0x1800122b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122b6  mov     rsi, rax
0x1800122b9  lea     rdx, aAcquiretokenfr_0; "AcquireTokenFromSvc"
0x1800122c0  mov     [rbp+57h+var_60], rdx
0x1800122c4  lea     rax, [rsp+120h+var_E0]
0x1800122c9  mov     [rbp+57h+var_58], rax
0x1800122cd  mov     [rbp+57h+var_50], 0
0x1800122d5  mov     [rbp+57h+var_48], 0
0x1800122dd  xor     r9d, r9d; unsigned int
0x1800122e0  mov     r8d, 622h; char *
0x1800122e6  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800122ed  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800122f2  nop
0x1800122f3  mov     dword ptr [rbp+57h+var_88+0Ch], 1
0x1800122fa  lea     rax, aHttpPassportNe; "http://Passport.NET/tb"
0x180012301  mov     [rbp+57h+var_A0], rax
0x180012305  mov     qword ptr [rbp+57h+var_88], 0
0x18001230d  or      rbx, 20480h
0x180012314  mov     qword ptr [rbp+57h+var_C0], rbx
0x180012318  mov     rax, cs:?g_MSACloudAPPluginLsaFunctions@@3PEAU_CLOUDAP_SECPKG_FUNCTION_TABLE@@EA; _CLOUDAP_SECPKG_FUNCTION_TABLE * g_MSACloudAPPluginLsaFunctions
0x18001231f  lea     rcx, [rbp+57h+var_78]
0x180012323  mov     rax, [rax+60h]
0x180012327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001232c  test    dword ptr [rbp+57h+var_78+8], 1800h
0x180012333  jz      short loc_18001233B
0x180012335  bts     qword ptr [rbp+57h+var_C0], 1Eh
0x18001233b  lea     rax, qword_18003AB48
0x180012342  test    rdi, rdi
0x180012345  cmovnz  rax, rdi
0x180012349  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18001234d  mov     rax, [rsi]
0x180012350  lea     rcx, [rbp+57h+var_D0]
0x180012354  mov     [rsp+120h+var_F0], rcx
0x180012359  lea     rcx, [rbp+57h+var_40]
0x18001235d  mov     [rsp+120h+var_F8], rcx
0x180012362  lea     rcx, [rbp+57h+var_A0]
0x180012366  mov     [rsp+120h+var_100], rcx
0x18001236b  mov     r9d, 1
0x180012371  lea     r8, [rbp+57h+var_C0]
0x180012375  mov     rdx, r14
0x180012378  mov     rcx, rsi
0x18001237b  mov     rax, [rax+18h]
0x18001237f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012384  mov     ebx, eax
0x180012386  mov     edi, 2
0x18001238b  test    eax, eax
0x18001238d  jns     short loc_1800123BD
0x18001238f  mov     dword ptr [rsp+120h+var_100], eax
0x180012393  lea     r9, aWlidcacquireto_2; "WLIDCAcquireTokens failed, hr=0x%x"
0x18001239a  mov     r8d, 641h; unsigned int
0x1800123a0  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800123a7  mov     ecx, edi; unsigned __int8
0x1800123a9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800123ae  mov     ecx, ebx; int
0x1800123b0  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800123b5  mov     [rsp+120h+var_E0], eax
0x1800123b9  test    eax, eax
0x1800123bb  js      short loc_180012401
0x1800123bd  mov     r8d, [rbp+57h+var_40+8]
0x1800123c1  mov     ebx, r8d
0x1800123c4  mov     eax, [rbp+57h+var_40]
0x1800123c7  test    r8d, r8d
0x1800123ca  js      short loc_1800123D2
0x1800123cc  mov     ebx, eax
0x1800123ce  test    eax, eax
0x1800123d0  jns     short loc_180012401
0x1800123d2  mov     dword ptr [rsp+120h+var_F8], eax
0x1800123d6  mov     dword ptr [rsp+120h+var_100], r8d
0x1800123db  lea     r9, aAcquiretokenfr; "AcquireTokenFromSvc failed, hrRequestSt"...
0x1800123e2  mov     r8d, 64Dh; unsigned int
0x1800123e8  lea     rdx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x1800123ef  mov     ecx, edi; unsigned __int8
0x1800123f1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800123f6  mov     ecx, ebx; int
0x1800123f8  call    ?LiveMapHResultToNtStatus@@YAJJ@Z; LiveMapHResultToNtStatus(long)
0x1800123fd  mov     [rsp+120h+var_E0], eax
0x180012401  mov     eax, cs:dword_18004D048
0x180012407  cmp     eax, 5
0x18001240a  jbe     short loc_180012463
0x18001240c  mov     rdx, 400000000000h
0x180012416  lea     rcx, dword_18004D048
0x18001241d  call    _tlgKeywordOn
0x180012422  test    al, al
0x180012424  jz      short loc_180012463
0x180012426  mov     [rbp+57h+var_C8], 3000000h
0x18001242e  mov     eax, [rsp+120h+var_E0]
0x180012432  mov     [rsp+120h+var_DC], eax
0x180012436  mov     [rsp+120h+var_D8], ebx
0x18001243a  lea     rax, [rbp+57h+var_C8]
0x18001243e  mov     [rsp+120h+var_F0], rax
0x180012443  lea     rax, [rsp+120h+var_DC]
0x180012448  mov     [rsp+120h+var_F8], rax
0x18001244d  lea     rax, [rsp+120h+var_D8]
0x180012452  mov     [rsp+120h+var_100], rax
0x180012457  lea     rdx, unk_1800440B0
0x18001245e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180012463  mov     ebx, [rsp+120h+var_E0]
0x180012467  lea     rcx, [rbp+57h+var_60]
0x18001246b  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180012470  nop
0x180012471  mov     rcx, [rbp+57h+var_D0]; void *
0x180012475  test    rcx, rcx
0x180012478  jz      short loc_18001247F
0x18001247a  call    ?LiveFree@@YAXPEAX@Z; LiveFree(void *)
0x18001247f  mov     eax, ebx
0x180012481  mov     rcx, [rbp+57h+var_28]
0x180012485  xor     rcx, rsp; StackCookie
0x180012488  call    __security_check_cookie
0x18001248d  add     rsp, 100h
0x180012494  pop     r14
0x180012496  pop     rdi
0x180012497  pop     rsi
0x180012498  pop     rbx
0x180012499  pop     rbp
0x18001249a  retn
```
