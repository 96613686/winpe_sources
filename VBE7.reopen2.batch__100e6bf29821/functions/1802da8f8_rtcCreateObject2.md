# rtcCreateObject2

- ea: `0x1802da8f8`
- end: `0x1802daf47`
- name: `rtcCreateObject2`
- size: `1615`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800f09f0`
- `0x1800fa390`
- `0x180102944`
- `0x180102a4c`
- `0x18011d6f4`
- `0x1801751d8`
- `0x1802d9e1c`
- `0x1802da814`
- `0x1802da8f8`
- `0x180350ad8`
- `0x180379520`

## import_xrefs

- `MSVCR100!_wcsicmp` at `0x1802da976`
- `MSVCR100!_wcsicmp` at `0x1802dabea`
- `MSVCR100!_wcsicmp` at `0x1802da976`
- `MSVCR100!_wcsicmp` at `0x1802dabea`
- `KERNEL32!GetComputerNameA` at `0x1802dab6c`
- `KERNEL32!GetComputerNameA` at `0x1802dab6c`
- `KERNEL32!MultiByteToWideChar` at `0x1802dab9b`
- `KERNEL32!MultiByteToWideChar` at `0x1802dab9b`
- `ole32!CoCreateInstance` at `0x1802daa26`
- `ole32!CoCreateInstance` at `0x1802daa26`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1802da9d8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1802dac3e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1802da9d8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1802dac3e`

## pseudocode

```c
void *__fastcall rtcCreateObject2(void *a1, const wchar_t *a2, wchar_t *a3)
{
  SCODE v4; // [rsp+30h] [rbp-1B0h]
  unsigned int v5; // [rsp+30h] [rbp-1B0h]
  SCODE v6; // [rsp+30h] [rbp-1B0h]
  struct IUnknown *ppv; // [rsp+38h] [rbp-1A8h] BYREF
  int v8; // [rsp+40h] [rbp-1A0h]
  BOOL v9; // [rsp+44h] [rbp-19Ch]
  DWORD nSize; // [rsp+48h] [rbp-198h] BYREF
  wchar_t *i; // [rsp+50h] [rbp-190h]
  __int64 v12; // [rsp+58h] [rbp-188h] BYREF
  __int64 v13; // [rsp+60h] [rbp-180h] BYREF
  _QWORD v14[3]; // [rsp+68h] [rbp-178h] BYREF
  int v15; // [rsp+80h] [rbp-160h]
  IID rclsid; // [rsp+88h] [rbp-158h] BYREF
  struct tagMULTI_QI v17; // [rsp+A0h] [rbp-140h] BYREF
  GUID *v18; // [rsp+B8h] [rbp-128h]
  __int64 v19; // [rsp+C0h] [rbp-120h]
  int v20; // [rsp+C8h] [rbp-118h]
  GUID *v21; // [rsp+D0h] [rbp-110h]
  __int64 v22; // [rsp+D8h] [rbp-108h]
  int v23; // [rsp+E0h] [rbp-100h]
  GUID *v24; // [rsp+E8h] [rbp-F8h]
  __int64 v25; // [rsp+F0h] [rbp-F0h]
  int v26; // [rsp+F8h] [rbp-E8h]
  CHAR Buffer[16]; // [rsp+100h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+110h] [rbp-D0h] BYREF
  struct _COSERVERINFO v29; // [rsp+118h] [rbp-C8h] BYREF
  struct tagEXCEPINFO v30; // [rsp+140h] [rbp-A0h] BYREF
  struct tagEXCEPINFO v31; // [rsp+180h] [rbp-60h] BYREF

  v8 = 0;
  v15 = 0;
  if ( !a2 || !(unsigned int)BstrLen(a2) )
    EbRaiseExceptionCode(429);
  if ( !a3 || !(unsigned int)BstrLen(a3) )
    goto LABEL_6;
  if ( !dword_180402588 )
  {
    nSize = 16;
    if ( GetComputerNameA(Buffer, &nSize) )
    {
      MultiByteToWideChar(0, 0, Buffer, nSize, &word_180402568, 16);
      dword_180402588 = 1;
    }
  }
  for ( i = a3; *i == 92 && i[1]; ++i )
    ;
  if ( _wcsicmp(&word_180402568, i) )
  {
    if ( !g_pfnCoCreateInstanceEx )
      EbRaiseExceptionCode(429);
    v5 = g_pfnCLSIDFromProgidEx(a2, &rclsid);
    if ( v5 == -2147221005 )
      v5 = -2146827825;
    HresultCheck(v5, 0);
    SetErrorInfo(0, 0);
    v29.dwReserved1 = 0;
    v29.pwszName = a3;
    v29.pAuthInfo = 0;
    v29.dwReserved2 = 0;
    v17.pIID = &IID_IUnknown;
    v17.pItf = 0;
    v17.hr = 0;
    v18 = &IID_IDispatch;
    v19 = 0;
    v20 = 0;
    v21 = &IID_IPersistStreamInit;
    v22 = 0;
    v23 = 0;
    v24 = &IID_IPersistPropertyBag;
    v25 = 0;
    v26 = 0;
    v6 = g_pfnCoCreateInstanceEx(&rclsid, 0, 0x10u, &v29, 4u, &v17);
    if ( v6 >= 0 )
      goto LABEL_45;
    while ( 1 )
    {
      if ( !(unsigned int)GetErrorInfo(&v30) )
      {
        v30.scode = v6;
        v30.wCode = 0;
        EbRaiseException(&v30);
      }
LABEL_45:
      HresultCheck((unsigned int)v6, 0);
      if ( v23 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 64LL))(v22);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v26 >= 0 )
      {
        if ( v23 < 0 )
          v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 32LL))(v25);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      if ( v6 >= 0 )
        break;
      if ( v20 >= 0 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      ((void (__fastcall *)(IUnknown *))v17.pItf->lpVtbl->Release)(v17.pItf);
    }
    if ( v20 >= 0 )
    {
      ((void (__fastcall *)(IUnknown *))v17.pItf->lpVtbl->Release)(v17.pItf);
      LOWORD(v14[0]) = 9;
      v14[1] = v19;
    }
    else
    {
      LOWORD(v14[0]) = 13;
      v14[1] = v17.pItf;
    }
    qmemcpy(a1, v14, 0x18u);
    return a1;
  }
  else
  {
LABEL_6:
    v9 = _wcsicmp(L"vbscript.regexp", a2) == 0;
    v8 |= v9;
    if ( v8 )
      v4 = 0;
    else
      v4 = g_pfnCLSIDFromProgidEx(a2, &rclsid);
    if ( v4 < 0 )
    {
      if ( (int)MapDisplayNameToObject(a2, &ppv) < 0 )
        EbRaiseExceptionCode(429);
    }
    else
    {
      SetErrorInfo(0, 0);
      if ( v8 <= 0 )
      {
        v4 = CoCreateInstance(&rclsid, 0, 0x15u, &IID_IUnknown, (LPVOID *)&ppv);
      }
      else if ( (int)CRegExp::Create(&ppv) < 0 || !ppv )
      {
        v4 = -2147221230;
      }
      if ( v4 >= 0 )
        goto LABEL_19;
      while ( 1 )
      {
        if ( !(unsigned int)GetErrorInfo(&v31) )
        {
          v31.scode = v4;
          v31.wCode = 0;
          EbRaiseException(&v31);
        }
LABEL_19:
        HresultCheck((unsigned int)v4, 0);
        if ( (unsigned int)IsCapabilityEnabled(2) )
          TELMGR::OnComObjectInstantiated(&rclsid);
        if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
               ppv,
               &IID_IPersistStreamInit,
               &v13) < 0 )
        {
          if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
                 ppv,
                 &IID_IPersistPropertyBag,
                 &v12) >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 32LL))(v12);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 64LL))(v13);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
        if ( v4 >= 0 )
          break;
        ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
      }
    }
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))ppv->lpVtbl->QueryInterface)(
           ppv,
           &IID_IDispatch,
           &v28) >= 0 )
    {
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
      LOWORD(v14[0]) = 9;
      v14[1] = v28;
    }
    else
    {
      LOWORD(v14[0]) = 13;
      v14[1] = ppv;
    }
    qmemcpy(a1, v14, 0x18u);
    return a1;
  }
}

```

## disassembly

```asm
0x1802da8f8  mov     [rsp-8+arg_10], r8
0x1802da8fd  mov     [rsp-8+String2], rdx
0x1802da902  mov     [rsp-8+arg_0], rcx
0x1802da907  push    rbp
0x1802da908  mov     rbp, rsp
0x1802da90b  push    rsi
0x1802da90c  push    rdi
0x1802da90d  sub     rsp, 1D0h
0x1802da914  mov     rax, cs:__security_cookie
0x1802da91b  xor     rax, rsp
0x1802da91e  mov     [rbp+var_20], rax
0x1802da922  mov     [rsp+1E0h+var_1A0], 0
0x1802da92a  mov     [rsp+1E0h+var_160], 0
0x1802da935  cmp     [rbp+String2], 0
0x1802da93a  jz      short loc_1802DA949
0x1802da93c  mov     rcx, [rbp+String2]
0x1802da940  call    BstrLen
0x1802da945  test    eax, eax
0x1802da947  jnz     short loc_1802DA953
0x1802da949  mov     ecx, 1ADh
0x1802da94e  call    EbRaiseExceptionCode
0x1802da953  cmp     [rbp+arg_10], 0
0x1802da958  jz      short loc_1802DA96B
0x1802da95a  mov     rcx, [rbp+arg_10]
0x1802da95e  call    BstrLen
0x1802da963  test    eax, eax
0x1802da965  jnz     loc_1802DAB4E
0x1802da96b  mov     rdx, [rbp+String2]; String2
0x1802da96f  lea     rcx, aVbscriptRegexp; "vbscript.regexp"
0x1802da976  call    cs:__imp__wcsicmp
0x1802da97c  test    eax, eax
0x1802da97e  jnz     short loc_1802DA98A
0x1802da980  mov     [rsp+1E0h+var_19C], 1
0x1802da988  jmp     short loc_1802DA992
0x1802da98a  mov     [rsp+1E0h+var_19C], 0
0x1802da992  mov     eax, [rsp+1E0h+var_19C]
0x1802da996  mov     ecx, [rsp+1E0h+var_1A0]
0x1802da99a  or      ecx, eax
0x1802da99c  mov     eax, ecx
0x1802da99e  mov     [rsp+1E0h+var_1A0], eax
0x1802da9a2  cmp     [rsp+1E0h+var_1A0], 0
0x1802da9a7  jnz     short loc_1802DA9C1
0x1802da9a9  lea     rdx, [rsp+1E0h+rclsid]
0x1802da9b1  mov     rcx, [rbp+String2]
0x1802da9b5  call    cs:?g_pfnCLSIDFromProgidEx@@3P6AJPEB_WPEAU_GUID@@@ZEA; long (*g_pfnCLSIDFromProgidEx)(wchar_t const *,_GUID *)
0x1802da9bb  mov     [rsp+1E0h+var_1B0], eax
0x1802da9bf  jmp     short loc_1802DA9C9
0x1802da9c1  mov     [rsp+1E0h+var_1B0], 0
0x1802da9c9  cmp     [rsp+1E0h+var_1B0], 0
0x1802da9ce  jl      loc_1802DAB26
0x1802da9d4  xor     edx, edx; perrinfo
0x1802da9d6  xor     ecx, ecx; dwReserved
0x1802da9d8  call    cs:__imp_SetErrorInfo
0x1802da9de  cmp     [rsp+1E0h+var_1A0], 0
0x1802da9e3  jle     short loc_1802DAA05
0x1802da9e5  lea     rcx, [rsp+1E0h+var_1A8]; struct IUnknown **
0x1802da9ea  call    ?Create@CRegExp@@SAJPEAPEAUIUnknown@@@Z; CRegExp::Create(IUnknown * *)
0x1802da9ef  test    eax, eax
0x1802da9f1  jl      short loc_1802DA9FB
0x1802da9f3  cmp     [rsp+1E0h+var_1A8], 0
0x1802da9f9  jnz     short loc_1802DAA03
0x1802da9fb  mov     [rsp+1E0h+var_1B0], 80040112h
0x1802daa03  jmp     short loc_1802DAA30
0x1802daa05  lea     rax, [rsp+1E0h+var_1A8]
0x1802daa0a  mov     [rsp+1E0h+ppv], rax; ppv
0x1802daa0f  lea     r9, IID_IUnknown; riid
0x1802daa16  mov     r8d, 15h; dwClsContext
0x1802daa1c  xor     edx, edx; pUnkOuter
0x1802daa1e  lea     rcx, [rsp+1E0h+rclsid]; rclsid
0x1802daa26  call    cs:__imp_CoCreateInstance
0x1802daa2c  mov     [rsp+1E0h+var_1B0], eax
0x1802daa30  cmp     [rsp+1E0h+var_1B0], 0
0x1802daa35  jge     short loc_1802DAA5A
0x1802daa37  lea     rcx, [rbp+var_60]; struct tagEXCEPINFO *
0x1802daa3b  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x1802daa40  test    eax, eax
0x1802daa42  jnz     short loc_1802DAA5A
0x1802daa44  mov     eax, [rsp+1E0h+var_1B0]
0x1802daa48  mov     [rbp+var_60.scode], eax
0x1802daa4b  xor     eax, eax
0x1802daa4d  mov     [rbp+var_60.wCode], ax
0x1802daa51  lea     rcx, [rbp+var_60]
0x1802daa55  call    EbRaiseException
0x1802daa5a  xor     edx, edx
0x1802daa5c  mov     ecx, [rsp+1E0h+var_1B0]
0x1802daa60  call    HresultCheck
0x1802daa65  mov     ecx, 2
0x1802daa6a  call    ?IsCapabilityEnabled@@YAHW4_VBACAPABILITYTYPE@@@Z; IsCapabilityEnabled(_VBACAPABILITYTYPE)
0x1802daa6f  test    eax, eax
0x1802daa71  jz      short loc_1802DAA80
0x1802daa73  lea     rcx, [rsp+1E0h+rclsid]; struct _GUID *
0x1802daa7b  call    ?OnComObjectInstantiated@TELMGR@@SAXAEBU_GUID@@@Z; TELMGR::OnComObjectInstantiated(_GUID const &)
0x1802daa80  mov     rax, [rsp+1E0h+var_1A8]
0x1802daa85  mov     rax, [rax]
0x1802daa88  lea     r8, [rsp+1E0h+var_180]
0x1802daa8d  lea     rdx, IID_IPersistStreamInit
0x1802daa94  mov     rcx, [rsp+1E0h+var_1A8]
0x1802daa99  call    qword ptr [rax]
0x1802daa9b  test    eax, eax
0x1802daa9d  jl      short loc_1802DAAC5
0x1802daa9f  mov     rax, [rsp+1E0h+var_180]
0x1802daaa4  mov     rax, [rax]
0x1802daaa7  mov     rcx, [rsp+1E0h+var_180]
0x1802daaac  call    qword ptr [rax+40h]
0x1802daaaf  mov     [rsp+1E0h+var_1B0], eax
0x1802daab3  mov     rax, [rsp+1E0h+var_180]
0x1802daab8  mov     rax, [rax]
0x1802daabb  mov     rcx, [rsp+1E0h+var_180]
0x1802daac0  call    qword ptr [rax+10h]
0x1802daac3  jmp     short loc_1802DAB08
0x1802daac5  mov     rax, [rsp+1E0h+var_1A8]
0x1802daaca  mov     rax, [rax]
0x1802daacd  lea     r8, [rsp+1E0h+var_188]
0x1802daad2  lea     rdx, IID_IPersistPropertyBag
0x1802daad9  mov     rcx, [rsp+1E0h+var_1A8]
0x1802daade  call    qword ptr [rax]
0x1802daae0  test    eax, eax
0x1802daae2  jl      short loc_1802DAB08
0x1802daae4  mov     rax, [rsp+1E0h+var_188]
0x1802daae9  mov     rax, [rax]
0x1802daaec  mov     rcx, [rsp+1E0h+var_188]
0x1802daaf1  call    qword ptr [rax+20h]
0x1802daaf4  mov     [rsp+1E0h+var_1B0], eax
0x1802daaf8  mov     rax, [rsp+1E0h+var_188]
0x1802daafd  mov     rax, [rax]
0x1802dab00  mov     rcx, [rsp+1E0h+var_188]
0x1802dab05  call    qword ptr [rax+10h]
0x1802dab08  cmp     [rsp+1E0h+var_1B0], 0
0x1802dab0d  jge     short loc_1802DAB24
0x1802dab0f  mov     rax, [rsp+1E0h+var_1A8]
0x1802dab14  mov     rax, [rax]
0x1802dab17  mov     rcx, [rsp+1E0h+var_1A8]
0x1802dab1c  call    qword ptr [rax+10h]
0x1802dab1f  jmp     loc_1802DAA37
0x1802dab24  jmp     short loc_1802DAB49
0x1802dab26  lea     rdx, [rsp+1E0h+var_1A8]
0x1802dab2b  mov     rcx, [rbp+String2]
0x1802dab2f  call    MapDisplayNameToObject
0x1802dab34  mov     [rsp+1E0h+var_1B0], eax
0x1802dab38  cmp     [rsp+1E0h+var_1B0], 0
0x1802dab3d  jge     short loc_1802DAB49
0x1802dab3f  mov     ecx, 1ADh
0x1802dab44  call    EbRaiseExceptionCode
0x1802dab49  jmp     loc_1802DAEBA
0x1802dab4e  cmp     cs:dword_180402588, 0
0x1802dab55  jnz     short loc_1802DABAB
0x1802dab57  mov     [rsp+1E0h+nSize], 10h
0x1802dab5f  lea     rdx, [rsp+1E0h+nSize]; nSize
0x1802dab64  lea     rcx, [rsp+1E0h+Buffer]; lpBuffer
0x1802dab6c  call    cs:__imp_GetComputerNameA
0x1802dab72  test    eax, eax
0x1802dab74  jz      short loc_1802DABAB
0x1802dab76  mov     [rsp+1E0h+cchWideChar], 10h; cchWideChar
0x1802dab7e  lea     rax, word_180402568
0x1802dab85  mov     [rsp+1E0h+ppv], rax; lpWideCharStr
0x1802dab8a  mov     r9d, [rsp+1E0h+nSize]; cbMultiByte
0x1802dab8f  lea     r8, [rsp+1E0h+Buffer]; lpMultiByteStr
0x1802dab97  xor     edx, edx; dwFlags
0x1802dab99  xor     ecx, ecx; CodePage
0x1802dab9b  call    cs:__imp_MultiByteToWideChar
0x1802daba1  mov     cs:dword_180402588, 1
0x1802dabab  mov     rax, [rbp+arg_10]
0x1802dabaf  mov     [rsp+1E0h+var_190], rax
0x1802dabb4  mov     rax, [rsp+1E0h+var_190]
0x1802dabb9  movzx   eax, word ptr [rax]
0x1802dabbc  cmp     eax, 5Ch ; '\'
0x1802dabbf  jnz     short loc_1802DABDE
0x1802dabc1  mov     rax, [rsp+1E0h+var_190]
0x1802dabc6  movzx   eax, word ptr [rax+2]
0x1802dabca  test    eax, eax
0x1802dabcc  jz      short loc_1802DABDE
0x1802dabce  mov     rax, [rsp+1E0h+var_190]
0x1802dabd3  add     rax, 2
0x1802dabd7  mov     [rsp+1E0h+var_190], rax
0x1802dabdc  jmp     short loc_1802DABB4
0x1802dabde  mov     rdx, [rsp+1E0h+var_190]; String2
0x1802dabe3  lea     rcx, word_180402568; String1
0x1802dabea  call    cs:__imp__wcsicmp
0x1802dabf0  test    eax, eax
0x1802dabf2  jnz     short loc_1802DABF9
0x1802dabf4  jmp     loc_1802DA96B
0x1802dabf9  cmp     cs:?g_pfnCoCreateInstanceEx@@3P6AJAEBU_GUID@@PEAUIUnknown@@KPEAU_COSERVERINFO@@KQEAUtagMULTI_QI@@@ZEA, 0; long (*g_pfnCoCreateInstanceEx)(_GUID const &,IUnknown *,ulong,_COSERVERINFO *,ulong,tagMULTI_QI * const)
0x1802dac01  jz      loc_1802DAEB0
0x1802dac07  lea     rdx, [rsp+1E0h+rclsid]
0x1802dac0f  mov     rcx, [rbp+String2]
0x1802dac13  call    cs:?g_pfnCLSIDFromProgidEx@@3P6AJPEB_WPEAU_GUID@@@ZEA; long (*g_pfnCLSIDFromProgidEx)(wchar_t const *,_GUID *)
0x1802dac19  mov     [rsp+1E0h+var_1B0], eax
0x1802dac1d  cmp     [rsp+1E0h+var_1B0], 800401F3h
0x1802dac25  jnz     short loc_1802DAC2F
0x1802dac27  mov     [rsp+1E0h+var_1B0], 800A01CFh
0x1802dac2f  xor     edx, edx
0x1802dac31  mov     ecx, [rsp+1E0h+var_1B0]
0x1802dac35  call    HresultCheck
0x1802dac3a  xor     edx, edx; perrinfo
0x1802dac3c  xor     ecx, ecx; dwReserved
0x1802dac3e  call    cs:__imp_SetErrorInfo
0x1802dac44  mov     [rsp+1E0h+var_C8], 0
0x1802dac4f  mov     rax, [rbp+arg_10]
0x1802dac53  mov     [rsp+1E0h+var_C0], rax
0x1802dac5b  mov     [rsp+1E0h+var_B8], 0
0x1802dac67  mov     [rsp+1E0h+var_B0], 0
0x1802dac72  lea     rax, IID_IUnknown
0x1802dac79  mov     [rsp+1E0h+var_140], rax
0x1802dac81  mov     [rsp+1E0h+var_138], 0
0x1802dac8d  mov     [rsp+1E0h+var_130], 0
0x1802dac98  lea     rax, IID_IDispatch
0x1802dac9f  mov     [rsp+1E0h+var_128], rax
0x1802daca7  mov     [rsp+1E0h+var_120], 0
0x1802dacb3  mov     [rsp+1E0h+var_118], 0
0x1802dacbe  lea     rax, IID_IPersistStreamInit
0x1802dacc5  mov     [rsp+1E0h+var_110], rax
0x1802daccd  mov     [rsp+1E0h+var_108], 0
0x1802dacd9  mov     [rsp+1E0h+var_100], 0
0x1802dace4  lea     rax, IID_IPersistPropertyBag
0x1802daceb  mov     [rsp+1E0h+var_F8], rax
0x1802dacf3  mov     [rsp+1E0h+var_F0], 0
0x1802dacff  mov     [rsp+1E0h+var_E8], 0
0x1802dad0a  lea     rax, [rsp+1E0h+var_140]
0x1802dad12  mov     qword ptr [rsp+1E0h+cchWideChar], rax
0x1802dad17  mov     dword ptr [rsp+1E0h+ppv], 4
0x1802dad1f  lea     r9, [rsp+1E0h+var_C8]
0x1802dad27  mov     r8d, 10h
0x1802dad2d  xor     edx, edx
0x1802dad2f  lea     rcx, [rsp+1E0h+rclsid]
0x1802dad37  call    cs:?g_pfnCoCreateInstanceEx@@3P6AJAEBU_GUID@@PEAUIUnknown@@KPEAU_COSERVERINFO@@KQEAUtagMULTI_QI@@@ZEA; long (*g_pfnCoCreateInstanceEx)(_GUID const &,IUnknown *,ulong,_COSERVERINFO *,ulong,tagMULTI_QI * const)
0x1802dad3d  mov     [rsp+1E0h+var_1B0], eax
0x1802dad41  cmp     [rsp+1E0h+var_1B0], 0
0x1802dad46  jge     short loc_1802DAD77
0x1802dad48  lea     rcx, [rsp+1E0h+var_A0]; struct tagEXCEPINFO *
0x1802dad50  call    ?GetErrorInfo@@YAJPEAUtagEXCEPINFO@@@Z; GetErrorInfo(tagEXCEPINFO *)
0x1802dad55  test    eax, eax
0x1802dad57  jnz     short loc_1802DAD77
0x1802dad59  mov     eax, [rsp+1E0h+var_1B0]
0x1802dad5d  mov     [rbp+var_A0.scode], eax
0x1802dad60  xor     eax, eax
0x1802dad62  mov     [rsp+1E0h+var_A0.wCode], ax
0x1802dad6a  lea     rcx, [rsp+1E0h+var_A0]
0x1802dad72  call    EbRaiseException
0x1802dad77  xor     edx, edx
0x1802dad79  mov     ecx, [rsp+1E0h+var_1B0]
0x1802dad7d  call    HresultCheck
0x1802dad82  cmp     [rsp+1E0h+var_100], 0
0x1802dad8a  jl      short loc_1802DADBC
0x1802dad8c  mov     rax, [rsp+1E0h+var_108]
0x1802dad94  mov     rax, [rax]
0x1802dad97  mov     rcx, [rsp+1E0h+var_108]
0x1802dad9f  call    qword ptr [rax+40h]
0x1802dada2  mov     [rsp+1E0h+var_1B0], eax
0x1802dada6  mov     rax, [rsp+1E0h+var_108]
0x1802dadae  mov     rax, [rax]
0x1802dadb1  mov     rcx, [rsp+1E0h+var_108]
0x1802dadb9  call    qword ptr [rax+10h]
0x1802dadbc  cmp     [rsp+1E0h+var_E8], 0
0x1802dadc4  jl      short loc_1802DAE00
0x1802dadc6  cmp     [rsp+1E0h+var_100], 0
0x1802dadce  jge     short loc_1802DADEA
0x1802dadd0  mov     rax, [rsp+1E0h+var_F0]
0x1802dadd8  mov     rax, [rax]
0x1802daddb  mov     rcx, [rsp+1E0h+var_F0]
0x1802dade3  call    qword ptr [rax+20h]
0x1802dade6  mov     [rsp+1E0h+var_1B0], eax
0x1802dadea  mov     rax, [rsp+1E0h+var_F0]
0x1802dadf2  mov     rax, [rax]
0x1802dadf5  mov     rcx, [rsp+1E0h+var_F0]
0x1802dadfd  call    qword ptr [rax+10h]
0x1802dae00  cmp     [rsp+1E0h+var_1B0], 0
0x1802dae05  jge     short loc_1802DAE42
0x1802dae07  cmp     [rsp+1E0h+var_118], 0
0x1802dae0f  jl      short loc_1802DAE27
0x1802dae11  mov     rax, [rsp+1E0h+var_120]
0x1802dae19  mov     rax, [rax]
0x1802dae1c  mov     rcx, [rsp+1E0h+var_120]
0x1802dae24  call    qword ptr [rax+10h]
0x1802dae27  mov     rax, [rsp+1E0h+var_138]
0x1802dae2f  mov     rax, [rax]
0x1802dae32  mov     rcx, [rsp+1E0h+var_138]
0x1802dae3a  call    qword ptr [rax+10h]
0x1802dae3d  jmp     loc_1802DAD48
0x1802dae42  cmp     [rsp+1E0h+var_118], 0
0x1802dae4a  jge     short loc_1802DAE65
0x1802dae4c  mov     eax, 0Dh
0x1802dae51  mov     [rsp+1E0h+var_178], ax
0x1802dae56  mov     rax, [rsp+1E0h+var_138]
0x1802dae5e  mov     [rsp+1E0h+var_170], rax
0x1802dae63  jmp     short loc_1802DAE92
0x1802dae65  mov     rax, [rsp+1E0h+var_138]
0x1802dae6d  mov     rax, [rax]
0x1802dae70  mov     rcx, [rsp+1E0h+var_138]
0x1802dae78  call    qword ptr [rax+10h]
0x1802dae7b  mov     eax, 9
0x1802dae80  mov     [rsp+1E0h+var_178], ax
0x1802dae85  mov     rax, [rsp+1E0h+var_120]
0x1802dae8d  mov     [rsp+1E0h+var_170], rax
0x1802dae92  lea     rax, [rsp+1E0h+var_178]
0x1802dae97  mov     rdi, [rbp+arg_0]
0x1802dae9b  mov     rsi, rax
0x1802dae9e  mov     ecx, 18h
0x1802daea3  rep movsb
0x1802daea5  mov     rax, [rbp+arg_0]
0x1802daea9  jmp     loc_1802DAF30
  ... truncated ...
```
