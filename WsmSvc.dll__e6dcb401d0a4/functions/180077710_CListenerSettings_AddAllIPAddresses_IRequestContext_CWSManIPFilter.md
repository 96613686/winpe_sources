# CListenerSettings::AddAllIPAddresses(IRequestContext *,CWSManIPFilter *)

- ea: `0x180077710`
- end: `0x180077d26`
- name: `?AddAllIPAddresses@CListenerSettings@@AEAAHPEAVIRequestContext@@PEAVCWSManIPFilter@@@Z`
- size: `1558`
- prototype: `int(CListenerSettings *__hidden this, struct IRequestContext *, struct CWSManIPFilter *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180040a08`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180067bc4`
- `0x180077490`
- `0x180077710`
- `0x180077d2c`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18011d8c0`
- `0x1801ba152`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180077922`
- `msvcrt!_wcsicmp` at `0x180077922`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077b11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077bfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077835`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077b11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180077bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077ba9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180077a93`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180077a93`
- `WS2_32!getnameinfo` at `0x180077a60`
- `WS2_32!getnameinfo` at `0x180077a60`
- `WS2_32!__imp_WSAStartup` at `0x180077a29`
- `WS2_32!__imp_WSAStartup` at `0x180077a29`
- `WS2_32!__imp_WSACleanup` at `0x180077aa1`
- `WS2_32!__imp_WSACleanup` at `0x180077be5`
- `WS2_32!__imp_WSACleanup` at `0x180077c3d`
- `WS2_32!__imp_WSACleanup` at `0x180077aa1`
- `WS2_32!__imp_WSACleanup` at `0x180077be5`
- `WS2_32!__imp_WSACleanup` at `0x180077c3d`

## string_xrefs

- `0x1800777a9`: `onecore\admin\wmi\wmx\config\clistenersettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CListenerSettings::AddAllIPAddresses(
        CListenerSettings *this,
        struct IRequestContext *a2,
        struct CWSManIPFilter *a3)
{
  PVOID v5; // rcx
  const unsigned __int16 *v6; // r8
  __int64 v7; // rdx
  unsigned int v9; // r15d
  DWORD AdapterAddress; // esi
  __int64 v11; // r13
  int v12; // eax
  PVOID *v13; // r10
  unsigned int v14; // r14d
  __int64 i; // rsi
  __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  unsigned __int64 v18; // rdx
  const unsigned __int16 *v19; // r8
  DWORD v20; // eax
  DWORD v21; // ecx
  int v22; // eax
  __int64 v23; // rsi
  const SOCKADDR *v24; // r12
  socklen_t v25; // r13d
  unsigned int v26; // r14d
  const unsigned __int16 *v27; // r8
  __int64 v28; // rdx
  DWORD v29; // edi
  DWORD LastError; // edi
  DWORD v31; // ecx
  int v32; // [rsp+40h] [rbp-C0h]
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  struct CWSManIPFilter *v35; // [rsp+58h] [rbp-A8h]
  struct WSAData WSAData; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t String2; // [rsp+200h] [rbp+100h] BYREF
  __int128 v38; // [rsp+202h] [rbp+102h]
  CHAR v39[30]; // [rsp+212h] [rbp+112h] BYREF
  CHAR pNodeBuffer[80]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR WideCharStr[72]; // [rsp+280h] [rbp+180h] BYREF

  v35 = a3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids,
      *((_QWORD *)this + 3),
      *((_QWORD *)this + 2));
  if ( !a2 )
  {
    v6 = L"283";
    v7 = 283;
LABEL_6:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\clistenersettings.cpp", v7, v6, 0x54Fu, 0);
    return 0;
  }
  v9 = 1;
  if ( ((*((_DWORD *)this + 1) - 1) & 0xFFFFFFFD) != 0 )
  {
    v6 = L"285";
    v7 = 285;
    goto LABEL_6;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\clistenersettings.cpp", 286, L"286", 0x54Fu, a2);
    return 0;
  }
  v33 = 0;
  AdapterAddress = ConfigUtilGetAdapterAddress(v5, 12, &v33);
  if ( AdapterAddress )
  {
    (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
      a2,
      1077134180,
      L"GetAdaptersAddresses",
      AdapterAddress);
    SetLastError(AdapterAddress);
    goto LABEL_14;
  }
  v11 = v33;
  v12 = 0;
  v32 = 0;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  while ( 1 )
  {
    v34 = v11;
    if ( !v11 )
    {
      if ( !v12 && v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x400) != 0 )
        WPP_SF_SS(
          (unsigned int)v13[2],
          21,
          (unsigned int)WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids,
          *((_QWORD *)this + 3),
          *((_QWORD *)this + 2));
LABEL_83:
      AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v33);
      return v9;
    }
    String2 = 0;
    v38 = 0;
    memset(v39, 0, sizeof(v39));
    v14 = *(_DWORD *)(v11 + 88);
    if ( v14 )
      break;
LABEL_27:
    if ( *((_DWORD *)this + 1) != 1 )
    {
      if ( *((_DWORD *)this + 1) != 3
        || (v22 = _wcsicmp(*((const wchar_t **)this + 2), &String2), v13 = (PVOID *)WPP_GLOBAL_Control, v22) )
      {
        v12 = v32;
        goto LABEL_53;
      }
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x400) != 0 )
    {
      WPP_SF_S(v13[2], 22, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids, &String2);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v23 = *(_QWORD *)(v11 + 24);
    if ( v23 )
    {
      while ( 1 )
      {
        memset_0(WideCharStr, 0, 0x82u);
        v24 = *(const SOCKADDR **)(v23 + 16);
        if ( !v24 )
          break;
        v25 = *(_DWORD *)(v23 + 24);
        memset_0(&WSAData, 0, sizeof(WSAData));
        v26 = WSAStartup(0x202u, &WSAData);
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v26);
          goto LABEL_76;
        }
        v26 = getnameinfo(v24, v25, pNodeBuffer, 0x41u, 0, 0, 2);
        if ( v26 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, v26);
          WSACleanup();
LABEL_76:
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v26);
          v31 = v26;
LABEL_68:
          SetLastError(v31);
          goto LABEL_78;
        }
        if ( !MultiByteToWideChar(3u, 0, pNodeBuffer, 65, WideCharStr, 65) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids,
              LastError);
          WSACleanup();
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, LastError);
          v31 = LastError;
          goto LABEL_68;
        }
        WSACleanup();
        if ( !CListenerSettings::AddIPAddress(this, WideCharStr, a2, v35) )
          goto LABEL_78;
        v23 = *(_QWORD *)(v23 + 8);
        if ( !v23 )
        {
          v11 = v34;
          goto LABEL_49;
        }
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 1208, L"1208", 0x54Fu, a2);
LABEL_78:
      v9 = 0;
      goto LABEL_83;
    }
    if ( *((_DWORD *)this + 1) == 1 )
    {
      if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x400) != 0 )
      {
        WPP_SF_(v13[2], 23, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids);
LABEL_49:
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 7) & 0x200) != 0 )
    {
      WPP_SF_S(v13[2], 24, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids, &String2);
      goto LABEL_49;
    }
    v12 = 1;
    v32 = 1;
    if ( *((_DWORD *)this + 1) == 3 )
      goto LABEL_83;
LABEL_53:
    v11 = *(_QWORD *)(v11 + 8);
  }
  if ( v11 == -80 )
  {
    v27 = L"1134";
    v28 = 1134;
    goto LABEL_59;
  }
  if ( v14 > 8 )
  {
    v27 = L"1137";
    v28 = 1137;
LABEL_59:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", v28, v27, 0x54Fu, 0);
    goto LABEL_60;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v14 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_27;
    }
    v16 = (unsigned int)(3 * i);
    v17 = &String2 + v16;
    v18 = (unsigned int)(24 - v16);
    v19 = L"%02x";
    if ( (_DWORD)i != v14 - 1 )
      v19 = L"%02x-";
    v20 = StringCchPrintfW(v17, v18, v19, *(unsigned __int8 *)(i + v11 + 80));
    v21 = v20;
    if ( v20 )
      break;
  }
  if ( (v20 & 0x1FFF0000) == 0x70000 )
    v21 = (unsigned __int16)v20;
  SetLastError(v21);
LABEL_60:
  v29 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids, v29);
  (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
    a2,
    1077134176,
    L"ConvertPhysicalAddressToString",
    v29);
LABEL_14:
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v33);
  return 0;
}

```

## disassembly

```asm
0x180077710  mov     [rsp-8+arg_18], rbx
0x180077715  push    rbp
0x180077716  push    rsi
0x180077717  push    rdi
0x180077718  push    r12
0x18007771a  push    r13
0x18007771c  push    r14
0x18007771e  push    r15
0x180077720  lea     rbp, [rsp-220h]
0x180077728  sub     rsp, 320h
0x18007772f  mov     rax, cs:__security_cookie
0x180077736  xor     rax, rsp
0x180077739  mov     [rbp+250h+var_40], rax
0x180077740  mov     [rsp+350h+var_2F8], r8
0x180077745  mov     rbx, rdx
0x180077748  mov     rdi, rcx
0x18007774b  lea     r12, WPP_GLOBAL_Control
0x180077752  mov     rcx, cs:WPP_GLOBAL_Control
0x180077759  cmp     rcx, r12
0x18007775c  jz      short loc_180077789
0x18007775e  test    dword ptr [rcx+1Ch], 400h
0x180077765  jz      short loc_180077789
0x180077767  mov     edx, 13h
0x18007776c  mov     rax, [rdi+10h]
0x180077770  mov     [rsp+350h+pServiceBuffer], rax
0x180077775  mov     r9, [rdi+18h]
0x180077779  lea     r8, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids
0x180077780  mov     rcx, [rcx+10h]
0x180077784  call    WPP_SF_SS
0x180077789  test    rbx, rbx
0x18007778c  jnz     short loc_1800777BC
0x18007778e  lea     r8, a283; "283"
0x180077795  mov     edx, 11Bh; unsigned int
0x18007779a  mov     [rsp+350h+pServiceBuffer], 0; struct IRequestContext *
0x1800777a3  mov     r9d, 54Fh; unsigned int
0x1800777a9  lea     rcx, aOnecoreAdminWm_168; "onecore\\admin\\wmi\\wmx\\config\\clist"...
0x1800777b0  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800777b5  xor     eax, eax
0x1800777b7  jmp     loc_180077CFC
0x1800777bc  mov     eax, [rdi+4]
0x1800777bf  mov     r15d, 1
0x1800777c5  sub     eax, r15d
0x1800777c8  test    eax, 0FFFFFFFDh
0x1800777cd  jz      short loc_1800777DD
0x1800777cf  lea     r8, a285; "285"
0x1800777d6  mov     edx, 11Dh
0x1800777db  jmp     short loc_18007779A
0x1800777dd  cmp     qword ptr [rdi+10h], 0
0x1800777e2  jnz     short loc_1800777F7
0x1800777e4  mov     [rsp+350h+pServiceBuffer], rbx
0x1800777e9  lea     r8, a286; "286"
0x1800777f0  mov     edx, 11Eh
0x1800777f5  jmp     short loc_1800777A3
0x1800777f7  mov     [rsp+350h+var_308], 0
0x180077800  lea     r8, [rsp+350h+var_308]
0x180077805  mov     edx, 0Ch
0x18007780a  call    ?ConfigUtilGetAdapterAddress@@YAKKKAEAV?$AutoDeleteVector@E@@@Z; ConfigUtilGetAdapterAddress(ulong,ulong,AutoDeleteVector<uchar> &)
0x18007780f  mov     esi, eax
0x180077811  test    eax, eax
0x180077813  jz      short loc_18007784B
0x180077815  mov     rdx, [rbx]
0x180077818  mov     rax, [rdx+58h]
0x18007781c  mov     r9d, esi
0x18007781f  lea     r8, aGetadaptersadd; "GetAdaptersAddresses"
0x180077826  mov     edx, 4033C364h
0x18007782b  mov     rcx, rbx
0x18007782e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077833  mov     ecx, esi; dwErrCode
0x180077835  call    cs:__imp_SetLastError
0x18007783b  nop
0x18007783c  lea     rcx, [rsp+350h+var_308]
0x180077841  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180077846  jmp     loc_1800777B5
0x18007784b  mov     r13, [rsp+350h+var_308]
0x180077850  xor     eax, eax
0x180077852  mov     [rsp+350h+var_310], eax
0x180077856  mov     r10, cs:WPP_GLOBAL_Control
0x18007785d  mov     [rsp+350h+var_300], r13
0x180077862  test    r13, r13
0x180077865  jz      loc_180077CBB
0x18007786b  xor     eax, eax
0x18007786d  mov     [rbp+250h+String2], ax
0x180077874  xorps   xmm0, xmm0
0x180077877  movups  [rbp+250h+var_14E], xmm0
0x18007787e  movups  xmmword ptr [rbp+250h+var_13E], xmm0
0x180077885  movups  xmmword ptr [rbp+250h+var_13E+0Eh], xmm0
0x18007788c  mov     r14d, [r13+58h]
0x180077890  test    r14d, r14d
0x180077893  jz      short loc_180077907
0x180077895  lea     r12, [r13+50h]
0x180077899  test    r12, r12
0x18007789c  jz      loc_180077B27
0x1800778a2  cmp     r14d, 8
0x1800778a6  ja      loc_180077B19
0x1800778ac  xor     esi, esi
0x1800778ae  cmp     esi, r14d
0x1800778b1  jnb     short loc_1800778F9
0x1800778b3  lea     edx, [rsi+rsi*2]
0x1800778b6  lea     rcx, [rbp+250h+String2]
0x1800778bd  lea     rcx, [rcx+rdx*2]; unsigned __int16 *
0x1800778c1  mov     eax, 18h
0x1800778c6  sub     eax, edx
0x1800778c8  mov     edx, eax; unsigned __int64
0x1800778ca  movzx   r9d, byte ptr [rsi+r12]
0x1800778cf  lea     eax, [r14-1]
0x1800778d3  cmp     esi, eax
0x1800778d5  lea     r8, a02x; "%02x"
0x1800778dc  jz      short loc_1800778E5
0x1800778de  lea     r8, a02x_0; "%02x-"
0x1800778e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800778ea  test    eax, eax
0x1800778ec  mov     ecx, eax
0x1800778ee  jnz     loc_180077B02
0x1800778f4  add     esi, r15d
0x1800778f7  jmp     short loc_1800778AE
0x1800778f9  mov     r10, cs:WPP_GLOBAL_Control
0x180077900  lea     r12, WPP_GLOBAL_Control
0x180077907  cmp     [rdi+4], r15d
0x18007790b  jz      short loc_180077937
0x18007790d  cmp     dword ptr [rdi+4], 3
0x180077911  jnz     loc_180077AF5
0x180077917  lea     rdx, [rbp+250h+String2]; String2
0x18007791e  mov     rcx, [rdi+10h]; String1
0x180077922  call    cs:__imp__wcsicmp
0x180077928  mov     r10, cs:WPP_GLOBAL_Control
0x18007792f  test    eax, eax
0x180077931  jnz     loc_180077AF5
0x180077937  cmp     r10, r12
0x18007793a  jz      short loc_180077969
0x18007793c  test    dword ptr [r10+1Ch], 400h
0x180077944  jz      short loc_180077969
0x180077946  mov     edx, 16h
0x18007794b  lea     r9, [rbp+250h+String2]
0x180077952  lea     r8, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids
0x180077959  mov     rcx, [r10+10h]
0x18007795d  call    WPP_SF_S
0x180077962  mov     r10, cs:WPP_GLOBAL_Control
0x180077969  mov     rsi, [r13+18h]
0x18007796d  test    rsi, rsi
0x180077970  jnz     short loc_1800779E8
0x180077972  cmp     [rdi+4], r15d
0x180077976  jnz     short loc_1800779A7
0x180077978  cmp     r10, r12
0x18007797b  jz      loc_180077AE2
0x180077981  test    dword ptr [r10+1Ch], 400h
0x180077989  jz      loc_180077AE2
0x18007798f  lea     edx, [rsi+17h]
0x180077992  lea     r8, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids
0x180077999  mov     rcx, [r10+10h]
0x18007799d  call    WPP_SF_
0x1800779a2  jmp     loc_180077ADB
0x1800779a7  cmp     r10, r12
0x1800779aa  jz      loc_180077AE2
0x1800779b0  test    dword ptr [r10+1Ch], 200h
0x1800779b8  jz      loc_180077AE2
0x1800779be  mov     edx, 18h
0x1800779c3  lea     r9, [rbp+250h+String2]
0x1800779ca  lea     r8, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids
0x1800779d1  mov     rcx, [r10+10h]
0x1800779d5  call    WPP_SF_S
0x1800779da  jmp     loc_180077ADB
0x1800779df  test    rsi, rsi
0x1800779e2  jz      loc_180077ACF
0x1800779e8  xor     edx, edx; Val
0x1800779ea  mov     r8d, 82h; Size
0x1800779f0  lea     rcx, [rbp+250h+WideCharStr]; void *
0x1800779f7  call    memset_0
0x1800779fc  mov     r12, [rsi+10h]
0x180077a00  test    r12, r12
0x180077a03  jz      loc_180077C93
0x180077a09  mov     r13d, [rsi+18h]
0x180077a0d  xor     edx, edx; Val
0x180077a0f  mov     r8d, 198h; Size
0x180077a15  lea     rcx, [rsp+350h+WSAData]; void *
0x180077a1a  call    memset_0
0x180077a1f  mov     ecx, 202h; wVersionRequested
0x180077a24  lea     rdx, [rsp+350h+WSAData]; lpWSAData
0x180077a29  call    cs:__imp_WSAStartup
0x180077a2f  mov     r14d, eax
0x180077a32  test    eax, eax
0x180077a34  jnz     loc_180077C45
0x180077a3a  mov     [rsp+350h+Flags], 2; Flags
0x180077a42  mov     [rsp+350h+ServiceBufferSize], eax; ServiceBufferSize
0x180077a46  mov     [rsp+350h+pServiceBuffer], 0; pServiceBuffer
0x180077a4f  lea     r9d, [rax+41h]; NodeBufferSize
0x180077a53  lea     r8, [rbp+250h+pNodeBuffer]; pNodeBuffer
0x180077a5a  mov     edx, r13d; SockaddrLength
0x180077a5d  mov     rcx, r12; pSockaddr
0x180077a60  call    cs:__imp_getnameinfo
0x180077a66  mov     r14d, eax
0x180077a69  test    eax, eax
0x180077a6b  jnz     loc_180077C09
0x180077a71  lea     ecx, [rax+41h]
0x180077a74  mov     [rsp+350h+ServiceBufferSize], ecx; cchWideChar
0x180077a78  lea     rax, [rbp+250h+WideCharStr]
0x180077a7f  mov     [rsp+350h+pServiceBuffer], rax; lpWideCharStr
0x180077a84  mov     r9d, ecx; cbMultiByte
0x180077a87  lea     r8, [rbp+250h+pNodeBuffer]; lpMultiByteStr
0x180077a8e  xor     edx, edx; dwFlags
0x180077a90  lea     ecx, [rdx+3]; CodePage
0x180077a93  call    cs:__imp_MultiByteToWideChar
0x180077a99  test    eax, eax
0x180077a9b  jz      loc_180077BA9
0x180077aa1  call    cs:__imp_WSACleanup
0x180077aa7  mov     r9, [rsp+350h+var_2F8]; struct CWSManIPFilter *
0x180077aac  mov     r8, rbx; struct IRequestContext *
0x180077aaf  lea     rdx, [rbp+250h+WideCharStr]; unsigned __int16 *
0x180077ab6  mov     rcx, rdi; this
0x180077ab9  call    ?AddIPAddress@CListenerSettings@@AEAAHPEBGPEAVIRequestContext@@PEAVCWSManIPFilter@@@Z; CListenerSettings::AddIPAddress(ushort const *,IRequestContext *,CWSManIPFilter *)
0x180077abe  test    eax, eax
0x180077ac0  jz      loc_180077CB6
0x180077ac6  mov     rsi, [rsi+8]
0x180077aca  jmp     loc_1800779DF
0x180077acf  mov     r13, [rsp+350h+var_300]
0x180077ad4  lea     r12, WPP_GLOBAL_Control
0x180077adb  mov     r10, cs:WPP_GLOBAL_Control
0x180077ae2  mov     eax, r15d
0x180077ae5  mov     [rsp+350h+var_310], eax
0x180077ae9  cmp     dword ptr [rdi+4], 3
0x180077aed  jz      loc_180077CEF
0x180077af3  jmp     short loc_180077AF9
0x180077af5  mov     eax, [rsp+350h+var_310]
0x180077af9  mov     r13, [r13+8]
0x180077afd  jmp     loc_18007785D
0x180077b02  and     eax, 1FFF0000h
0x180077b07  cmp     eax, 70000h
0x180077b0c  jnz     short loc_180077B11
0x180077b0e  movzx   ecx, cx; dwErrCode
0x180077b11  call    cs:__imp_SetLastError
0x180077b17  jmp     short loc_180077B4A
0x180077b19  lea     r8, a1137; "1137"
0x180077b20  mov     edx, 471h
0x180077b25  jmp     short loc_180077B33
0x180077b27  lea     r8, a1134; "1134"
0x180077b2e  mov     edx, 46Eh; unsigned int
0x180077b33  mov     [rsp+350h+pServiceBuffer], rax; struct IRequestContext *
0x180077b38  mov     r9d, 54Fh; unsigned int
0x180077b3e  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x180077b45  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180077b4a  call    cs:__imp_GetLastError
0x180077b50  mov     edi, eax
0x180077b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180077b59  lea     rax, WPP_GLOBAL_Control
0x180077b60  cmp     rcx, rax
0x180077b63  jz      short loc_180077B86
0x180077b65  test    dword ptr [rcx+1Ch], 200h
0x180077b6c  jz      short loc_180077B86
0x180077b6e  mov     edx, 14h
0x180077b73  mov     r9d, edi
0x180077b76  lea     r8, WPP_f1faba0db6c936ea110ae0c7dce68bc5_Traceguids
0x180077b7d  mov     rcx, [rcx+10h]
0x180077b81  call    WPP_SF_d
0x180077b86  mov     rax, [rbx]
0x180077b89  mov     r9d, edi
0x180077b8c  lea     r8, aConvertphysica; "ConvertPhysicalAddressToString"
0x180077b93  mov     edx, 4033C360h
0x180077b98  mov     rcx, rbx
0x180077b9b  mov     rax, [rax+58h]
0x180077b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077ba4  jmp     loc_18007783C
0x180077ba9  call    cs:__imp_GetLastError
0x180077baf  mov     edi, eax
0x180077bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180077bb8  lea     rax, WPP_GLOBAL_Control
0x180077bbf  cmp     rcx, rax
0x180077bc2  jz      short loc_180077BE5
0x180077bc4  test    dword ptr [rcx+1Ch], 200h
0x180077bcb  jz      short loc_180077BE5
0x180077bcd  mov     edx, 26h ; '&'
0x180077bd2  mov     r9d, edi
0x180077bd5  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x180077bdc  mov     rcx, [rcx+10h]
0x180077be0  call    WPP_SF_d
0x180077be5  call    cs:__imp_WSACleanup
0x180077beb  mov     rax, [rbx]
0x180077bee  mov     edx, edi
0x180077bf0  mov     rcx, rbx
0x180077bf3  mov     rax, [rax+48h]
0x180077bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bfc  mov     ecx, edi; dwErrCode
0x180077bfe  call    cs:__imp_SetLastError
0x180077c04  jmp     loc_180077CB6
0x180077c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180077c10  lea     rax, WPP_GLOBAL_Control
0x180077c17  cmp     rcx, rax
0x180077c1a  jz      short loc_180077C3D
0x180077c1c  test    dword ptr [rcx+1Ch], 800h
0x180077c23  jz      short loc_180077C3D
0x180077c25  mov     edx, 25h ; '%'
0x180077c2a  mov     r9d, r14d
0x180077c2d  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x180077c34  mov     rcx, [rcx+10h]
0x180077c38  call    WPP_SF_d
0x180077c3d  call    cs:__imp_WSACleanup
0x180077c43  jmp     short loc_180077C79
0x180077c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180077c4c  lea     rax, WPP_GLOBAL_Control
0x180077c53  cmp     rcx, rax
0x180077c56  jz      short loc_180077C79
0x180077c58  test    dword ptr [rcx+1Ch], 800h
  ... truncated ...
```
