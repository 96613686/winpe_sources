# GetBlockedUpdatesFromBlockListConfig(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ulong *,ulong *)

- ea: `0x18003ad04`
- end: `0x18003b380`
- name: `?GetBlockedUpdatesFromBlockListConfig@@YAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEAK1@Z`
- size: `1660`
- prototype: `__int64 __fastcall(__int64 **, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a8a8`

## callees

- `0x1800078b0`
- `0x18001a42c`
- `0x18001be20`
- `0x18003a6ac`
- `0x18003a770`
- `0x18003a794`
- `0x18003ad04`
- `0x18003b388`
- `0x18003b4ac`
- `0x18003b570`
- `0x18003c0b8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003afe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003afed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b24f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b25b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003afe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003afed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b176`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b1f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b24f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b25b`

## string_xrefs

- `0x18003ae25`: `LastUpdatedTime`
- `0x18003afd2`: `BlockListSettingsNames %ls LastUpdatedTime %s BlockListFreshWindowInHours %d IsBlockListTrusted %d IsRebootAllowed %d \n`

## pseudocode

```c
__int64 __fastcall GetBlockedUpdatesFromBlockListConfig(__int64 **a1, _DWORD *a2, _DWORD *a3)
{
  int v4; // r15d
  unsigned int i; // r12d
  __int64 *v6; // rdi
  __int64 v7; // r14
  const WCHAR *v8; // rbx
  unsigned __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  int v16; // r13d
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, _QWORD, double *); // rbx
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64 *); // rbx
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // ecx
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, __int64 *); // rbx
  int v35; // eax
  __int64 v36; // rcx
  __int64 *v37; // rcx
  __int64 v38; // rcx
  __int64 *v39; // rcx
  __int64 v40; // rcx
  __int64 *v41; // rcx
  __int64 v42; // rcx
  __int64 *v43; // rcx
  __int64 v44; // rcx
  __int64 *v45; // rcx
  __int64 v47; // rcx
  __int64 *v48; // rcx
  __int64 v49; // rcx
  __int64 *v50; // rcx
  int v51; // [rsp+28h] [rbp-E0h]
  const char *v52; // [rsp+28h] [rbp-E0h]
  __int64 v53; // [rsp+30h] [rbp-D8h]
  __int64 v54; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v56[2]; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+58h] [rbp-B0h]
  double v59; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v60; // [rsp+68h] [rbp-A0h]
  _DWORD *v61; // [rsp+70h] [rbp-98h]
  _DWORD *v62; // [rsp+78h] [rbp-90h]
  __int64 **v63; // [rsp+80h] [rbp-88h]
  __int64 v64; // [rsp+88h] [rbp-80h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-78h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-60h]
  __m128i si128; // [rsp+B0h] [rbp-58h]
  __int64 v68; // [rsp+C0h] [rbp-48h]
  int v69; // [rsp+C8h] [rbp-40h]
  WCHAR sourceString[264]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR v71[264]; // [rsp+2E8h] [rbp+1E0h] BYREF
  WCHAR v72[264]; // [rsp+4F8h] [rbp+3F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+760h] [rbp+658h]

  v62 = a3;
  v61 = a2;
  v63 = a1;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v68 = 0;
  v69 = 0;
  v4 = 0;
  LODWORD(v58) = 0;
  for ( i = 0; i < 7; ++i )
  {
    v55 = 0;
    v6 = *a1;
    v7 = **a1;
    v66 = 0;
    v8 = off_18005F430[3 * (int)i + 1];
    v56[0] = 0;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v10 = ULongLongToUInt(v9, v56);
    if ( v10 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
      JUMPOUT(0x18003B37FLL);
    }
    v13 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v56[0]);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v8, v13, v56[0]);
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v7 + 64))(v6, v66, &v55);
    v15 = v14;
    if ( !i )
    {
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
          (const char *)(unsigned int)v14,
          v51);
        v47 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
        }
        v48 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
        }
        return v15;
      }
      v16 = 1;
      while ( 1 )
      {
        string = 0;
        v64 = 0;
        v59 = 0.0;
        LOBYTE(v54) = 1;
        v60 = 3LL * v16;
        StringCchPrintfW(sourceString, 0x104u, L"%s%s", off_18005F430[3 * v16], L"LastUpdatedTime");
        StringCchPrintfW(v71, 0x104u, L"%s%s", off_18005F430[3 * v16], L"FreshWindowInHours");
        v52 = L"RebootAllowed";
        StringCchPrintfW(v72, 0x104u, L"%s%s", off_18005F430[3 * v16]);
        v17 = v55;
        v18 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v55 + 80LL);
        WindowsDeleteString(string);
        string = 0;
        v19 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
        v20 = v18(v17, *(_QWORD *)(v19 + 24), &string);
        v21 = v20;
        if ( v20 < 0 )
          break;
        v22 = v55;
        v23 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v55 + 88LL);
        v24 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v71);
        v25 = v23(v22, *(_QWORD *)(v24 + 24), &v59);
        v21 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCC,
            (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
            (const char *)(unsigned int)v25,
            (int)L"RebootAllowed");
          WindowsDeleteString(0);
          WindowsDeleteString(string);
          string = 0;
          v42 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
          v43 = *a1;
          if ( *a1 )
          {
            *a1 = 0;
            (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
          }
          return v21;
        }
        v26 = v55;
        v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v55 + 96LL);
        v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, v72);
        v29 = v27(v26, *(_QWORD *)(v28 + 24), &v54);
        v21 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
            (const char *)(unsigned int)v29,
            (int)L"RebootAllowed");
          WindowsDeleteString(0);
          WindowsDeleteString(string);
          string = 0;
          v40 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          }
          v41 = *a1;
          if ( *a1 )
          {
            *a1 = 0;
            (*(void (__fastcall **)(__int64 *))(*v41 + 16))(v41);
          }
          return v21;
        }
        v30 = (int)v59;
        v56[0] = 1;
        v31 = IsBlockListTrusted(&string, (int)v59, (int *)v56);
        v21 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD3,
            (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
            (const char *)(unsigned int)v31,
            (int)L"RebootAllowed");
          WindowsDeleteString(0);
          WindowsDeleteString(string);
          string = 0;
          v38 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          v39 = *a1;
          if ( *a1 )
          {
            *a1 = 0;
            (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
          }
          return v21;
        }
        v32 = v56[0];
        si128.m128i_i32[v16] = v56[0];
        if ( !(_BYTE)v54 )
          LODWORD(v58) = LODWORD(off_18005F430[v60 + 2]) | v58;
        LODWORD(v53) = (unsigned __int8)v54;
        LODWORD(v52) = v32;
        SBServicingLogMessage(
          (wchar_t *)L"BlockListSettingsNames %ls LastUpdatedTime %s BlockListFreshWindowInHours %d IsBlockListTrusted %d "
                      "IsRebootAllowed %d \n",
          off_18005F430[v60],
          sourceString,
          v30,
          v52,
          v53);
        WindowsDeleteString(0);
        WindowsDeleteString(string);
        if ( (unsigned int)++v16 >= 7 )
          goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
        (const char *)(unsigned int)v20,
        (int)L"RebootAllowed");
      WindowsDeleteString(0);
      WindowsDeleteString(string);
      string = 0;
      v44 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
      v45 = *a1;
      if ( *a1 )
      {
        *a1 = 0;
        (*(void (__fastcall **)(__int64 *))(*v45 + 16))(v45);
      }
      return v21;
    }
    if ( v14 >= 0 )
    {
      LOBYTE(v54) = 0;
      v33 = v55;
      v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v55 + 96LL);
      v66 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsBlocked", 0xAu, 9u);
      v35 = v34(v33, v66, &v54);
      v21 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE9,
          (unsigned int)"onecore\\base\\secureboot\\servicing\\lib\\sbsblocklist.cpp",
          (const char *)(unsigned int)v35,
          v51);
        v49 = v55;
        if ( v55 )
        {
          v55 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        v50 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
        }
        return v21;
      }
      if ( (_BYTE)v54 )
        v4 |= LODWORD(off_18005F430[3 * (int)i + 2]);
    }
    if ( !si128.m128i_i32[i] )
      v4 |= LODWORD(off_18005F430[3 * (int)i + 2]);
    v15 = 0;
LABEL_23:
    v36 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
  }
  *v61 = v4;
  *v62 = v58;
  v37 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64 *))(*v37 + 16))(v37);
  }
  return v15;
}

```

## disassembly

```asm
0x18003ad04  mov     rax, rsp
0x18003ad07  mov     [rax+20h], rbx
0x18003ad0b  push    rbp
0x18003ad0c  push    rsi
0x18003ad0d  push    rdi
0x18003ad0e  push    r12
0x18003ad10  push    r13
0x18003ad12  push    r14
0x18003ad14  push    r15
0x18003ad16  lea     rbp, [rax-658h]
0x18003ad1d  sub     rsp, 720h
0x18003ad24  movaps  xmmword ptr [rax-48h], xmm6
0x18003ad28  mov     rax, cs:__security_cookie
0x18003ad2f  xor     rax, rsp
0x18003ad32  mov     [rbp+650h+var_50], rax
0x18003ad39  mov     [rsp+750h+var_6E0], r8
0x18003ad3e  mov     [rsp+750h+var_6E8], rdx
0x18003ad43  mov     rsi, rcx
0x18003ad46  mov     [rsp+750h+var_6D8], rcx
0x18003ad4b  movdqa  xmm0, cs:__xmm@00000000000000000000000000000001
0x18003ad53  movdqu  [rbp+650h+var_6A8], xmm0
0x18003ad58  xor     edi, edi
0x18003ad5a  mov     [rbp+650h+var_698], rdi
0x18003ad5e  mov     [rbp+650h+var_690], edi
0x18003ad61  mov     r15d, edi
0x18003ad64  mov     dword ptr [rsp+750h+var_700], edi
0x18003ad68  mov     r12d, edi
0x18003ad6b  lea     rbx, off_18005F430; "Settings"
0x18003ad72  xorps   xmm6, xmm6
0x18003ad75  mov     [rsp+750h+var_718], rdi
0x18003ad7a  mov     rdi, [rsi]
0x18003ad7d  mov     r14, [rdi]
0x18003ad80  xor     r9d, r9d
0x18003ad83  mov     [rbp+650h+var_6B0], r9
0x18003ad87  movsxd  rax, r12d
0x18003ad8a  lea     r13, [rax+rax*2]
0x18003ad8e  mov     rbx, [rbx+r13*8+8]
0x18003ad93  mov     [rsp+750h+var_710], r9d
0x18003ad98  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003ad9c  inc     rcx; unsigned __int64
0x18003ad9f  cmp     [rbx+rcx*2], r9w
0x18003ada4  jnz     short loc_18003AD9C
0x18003ada6  lea     rdx, [rsp+750h+var_710]; unsigned int *
0x18003adab  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003adb0  test    eax, eax
0x18003adb2  js      loc_18003B378
0x18003adb8  mov     ecx, [rsp+750h+var_710]; unsigned int
0x18003adbc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003adc1  mov     r9d, [rsp+750h+var_710]; unsigned int
0x18003adc6  mov     r8d, eax; unsigned int
0x18003adc9  mov     rdx, rbx; sourceString
0x18003adcc  lea     rcx, [rbp+650h+hstringHeader]; hstringHeader
0x18003add0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003add5  nop
0x18003add6  lea     r8, [rsp+750h+var_718]
0x18003addb  mov     rdx, [rbp+650h+var_6B0]
0x18003addf  mov     rcx, rdi
0x18003ade2  mov     rax, [r14+40h]
0x18003ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adeb  mov     r14d, eax
0x18003adee  xor     edi, edi
0x18003adf0  test    r12d, r12d
0x18003adf3  jnz     loc_18003B00A
0x18003adf9  test    eax, eax
0x18003adfb  js      loc_18003B2CB
0x18003ae01  lea     r13d, [rdi+1]
0x18003ae05  mov     [rsp+750h+string], rdi
0x18003ae0a  mov     [rbp+650h+var_6D0], rdi
0x18003ae0e  movsd   [rsp+750h+var_6F8], xmm6
0x18003ae14  mov     byte ptr [rsp+750h+var_720], 1
0x18003ae19  movsxd  rax, r13d
0x18003ae1c  lea     rbx, [rax+rax*2]
0x18003ae20  mov     [rsp+750h+var_6F0], rbx
0x18003ae25  lea     rax, aLastupdatedtim; "LastUpdatedTime"
0x18003ae2c  mov     [rsp+750h+var_730], rax
0x18003ae31  lea     rdi, off_18005F430; "Settings"
0x18003ae38  mov     r9, [rdi+rbx*8]
0x18003ae3c  lea     r8, aSS_0; "%s%s"
0x18003ae43  mov     edx, 104h; unsigned __int64
0x18003ae48  lea     rcx, [rbp+650h+sourceString]; unsigned __int16 *
0x18003ae4c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ae51  lea     rax, aFreshwindowinh; "FreshWindowInHours"
0x18003ae58  mov     [rsp+750h+var_730], rax
0x18003ae5d  mov     r9, [rdi+rbx*8]
0x18003ae61  lea     r8, aSS_0; "%s%s"
0x18003ae68  mov     edx, 104h; unsigned __int64
0x18003ae6d  lea     rcx, [rbp+650h+var_470]; unsigned __int16 *
0x18003ae74  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ae79  lea     rax, aRebootallowed; "RebootAllowed"
0x18003ae80  mov     [rsp+750h+var_730], rax; int
0x18003ae85  mov     r9, [rdi+rbx*8]
0x18003ae89  lea     r8, aSS_0; "%s%s"
0x18003ae90  mov     edx, 104h; unsigned __int64
0x18003ae95  lea     rcx, [rbp+650h+var_260]; unsigned __int16 *
0x18003ae9c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003aea1  mov     rdi, [rsp+750h+var_718]
0x18003aea6  mov     rax, [rdi]
0x18003aea9  mov     rbx, [rax+50h]
0x18003aead  mov     rcx, [rsp+750h+string]; string
0x18003aeb2  call    cs:__imp_WindowsDeleteString
0x18003aeb8  xor     r9d, r9d
0x18003aebb  mov     [rsp+750h+string], r9
0x18003aec0  lea     rdx, [rbp+650h+sourceString]; sourceString
0x18003aec4  lea     rcx, [rbp+650h+hstringHeader]; hstringHeader
0x18003aec8  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x18003aecd  nop
0x18003aece  lea     r8, [rsp+750h+string]
0x18003aed3  mov     rdx, [rax+18h]
0x18003aed7  mov     rcx, rdi
0x18003aeda  mov     rax, rbx
0x18003aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aee2  mov     ebx, eax
0x18003aee4  xor     edi, edi
0x18003aee6  test    eax, eax
0x18003aee8  js      loc_18003B231
0x18003aeee  mov     rdi, [rsp+750h+var_718]
0x18003aef3  mov     rax, [rdi]
0x18003aef6  mov     rbx, [rax+58h]
0x18003aefa  lea     rdx, [rbp+650h+var_470]; sourceString
0x18003af01  lea     rcx, [rbp+650h+hstringHeader]; hstringHeader
0x18003af05  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x18003af0a  nop
0x18003af0b  lea     r8, [rsp+750h+var_6F8]
0x18003af10  mov     rdx, [rax+18h]
0x18003af14  mov     rcx, rdi
0x18003af17  mov     rax, rbx
0x18003af1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af1f  mov     ebx, eax
0x18003af21  xor     edi, edi
0x18003af23  test    eax, eax
0x18003af25  js      loc_18003B1C6
0x18003af2b  mov     rdi, [rsp+750h+var_718]
0x18003af30  mov     rax, [rdi]
0x18003af33  mov     rbx, [rax+60h]
0x18003af37  lea     rdx, [rbp+650h+var_260]; sourceString
0x18003af3e  lea     rcx, [rbp+650h+hstringHeader]; hstringHeader
0x18003af42  call    ??$?0$0BAE@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[260])
0x18003af47  nop
0x18003af48  lea     r8, [rsp+750h+var_720]
0x18003af4d  mov     rdx, [rax+18h]
0x18003af51  mov     rcx, rdi
0x18003af54  mov     rax, rbx
0x18003af57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af5c  mov     ebx, eax
0x18003af5e  xor     edi, edi
0x18003af60  test    eax, eax
0x18003af62  js      loc_18003B158
0x18003af68  cvttsd2si rdi, [rsp+750h+var_6F8]
0x18003af6f  mov     [rsp+750h+var_710], 1
0x18003af77  lea     r8, [rsp+750h+var_710]; int *
0x18003af7c  mov     edx, edi; unsigned int
0x18003af7e  lea     rcx, [rsp+750h+string]; struct Microsoft::WRL::Wrappers::HString *
0x18003af83  call    ?IsBlockListTrusted@@YAJAEAVHString@Wrappers@WRL@Microsoft@@KPEAH@Z; IsBlockListTrusted(Microsoft::WRL::Wrappers::HString &,ulong,int *)
0x18003af88  mov     ebx, eax
0x18003af8a  test    eax, eax
0x18003af8c  js      loc_18003B0E8
0x18003af92  mov     ecx, [rsp+750h+var_710]
0x18003af96  movsxd  rax, r13d
0x18003af99  mov     dword ptr [rbp+rax*4+650h+var_6A8], ecx
0x18003af9d  movzx   eax, byte ptr [rsp+750h+var_720]
0x18003afa2  mov     r10, [rsp+750h+var_6F0]
0x18003afa7  lea     rbx, off_18005F430; "Settings"
0x18003afae  test    al, al
0x18003afb0  jnz     short loc_18003AFBF
0x18003afb2  mov     edx, dword ptr [rsp+750h+var_700]
0x18003afb6  or      edx, [rbx+r10*8+10h]
0x18003afbb  mov     dword ptr [rsp+750h+var_700], edx
0x18003afbf  mov     dword ptr [rsp+750h+var_728], eax
0x18003afc3  mov     dword ptr [rsp+750h+var_730], ecx
0x18003afc7  mov     r9d, edi
0x18003afca  lea     r8, [rbp+650h+sourceString]
0x18003afce  mov     rdx, [rbx+r10*8]
0x18003afd2  lea     rcx, aBlocklistsetti; "BlockListSettingsNames %ls LastUpdatedT"...
0x18003afd9  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003afde  nop
0x18003afdf  xor     ecx, ecx; string
0x18003afe1  call    cs:__imp_WindowsDeleteString
0x18003afe7  nop
0x18003afe8  mov     rcx, [rsp+750h+string]; string
0x18003afed  call    cs:__imp_WindowsDeleteString
0x18003aff3  inc     r13d
0x18003aff6  cmp     r13d, 7
0x18003affa  mov     edi, 0
0x18003afff  jb      loc_18003AE05
0x18003b005  jmp     loc_18003B08F
0x18003b00a  test    r14d, r14d
0x18003b00d  js      short loc_18003B077
0x18003b00f  mov     byte ptr [rsp+750h+var_720], dil
0x18003b014  mov     rdi, [rsp+750h+var_718]
0x18003b019  mov     rax, [rdi]
0x18003b01c  mov     rbx, [rax+60h]
0x18003b020  xor     r9d, r9d
0x18003b023  mov     [rbp+650h+var_6B0], r9
0x18003b027  mov     r9d, 9; unsigned int
0x18003b02d  lea     r8d, [r9+1]; unsigned int
0x18003b031  lea     rdx, aIsblocked; "IsBlocked"
0x18003b038  lea     rcx, [rbp+650h+hstringHeader]; hstringHeader
0x18003b03c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b041  nop
0x18003b042  lea     r8, [rsp+750h+var_720]
0x18003b047  mov     rdx, [rbp+650h+var_6B0]
0x18003b04b  mov     rcx, rdi
0x18003b04e  mov     rax, rbx
0x18003b051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b056  mov     ebx, eax
0x18003b058  xor     edi, edi
0x18003b05a  test    eax, eax
0x18003b05c  js      loc_18003B323
0x18003b062  lea     rbx, off_18005F430; "Settings"
0x18003b069  cmp     byte ptr [rsp+750h+var_720], dil
0x18003b06e  jz      short loc_18003B07E
0x18003b070  or      r15d, [rbx+r13*8+10h]
0x18003b075  jmp     short loc_18003B07E
0x18003b077  lea     rbx, off_18005F430; "Settings"
0x18003b07e  movsxd  rax, r12d
0x18003b081  cmp     dword ptr [rbp+rax*4+650h+var_6A8], edi
0x18003b085  jnz     short loc_18003B08C
0x18003b087  or      r15d, [rbx+r13*8+10h]
0x18003b08c  mov     r14d, edi
0x18003b08f  mov     rcx, [rsp+750h+var_718]
0x18003b094  test    rcx, rcx
0x18003b097  jz      short loc_18003B0AB
0x18003b099  mov     [rsp+750h+var_718], rdi
0x18003b09e  mov     rax, [rcx]
0x18003b0a1  mov     rax, [rax+10h]
0x18003b0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0aa  nop
0x18003b0ab  inc     r12d
0x18003b0ae  cmp     r12d, 7
0x18003b0b2  jb      loc_18003AD75
0x18003b0b8  mov     rax, [rsp+750h+var_6E8]
0x18003b0bd  mov     [rax], r15d
0x18003b0c0  mov     eax, dword ptr [rsp+750h+var_700]
0x18003b0c4  mov     rcx, [rsp+750h+var_6E0]
0x18003b0c9  mov     [rcx], eax
0x18003b0cb  mov     rcx, [rsi]
0x18003b0ce  test    rcx, rcx
0x18003b0d1  jz      short loc_18003B0E3
0x18003b0d3  mov     [rsi], rdi
0x18003b0d6  mov     rax, [rcx]
0x18003b0d9  mov     rax, [rax+10h]
0x18003b0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0e2  nop
0x18003b0e3  jmp     loc_18003B31B
0x18003b0e8  mov     rcx, [rbp+658h]; this
0x18003b0ef  mov     r9d, ebx; char *
0x18003b0f2  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003b0f9  mov     edx, 0D3h; void *
0x18003b0fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b103  nop
0x18003b104  xor     ecx, ecx; string
0x18003b106  call    cs:__imp_WindowsDeleteString
0x18003b10c  nop
0x18003b10d  mov     rcx, [rsp+750h+string]; string
0x18003b112  call    cs:__imp_WindowsDeleteString
0x18003b118  xor     edi, edi
0x18003b11a  mov     [rsp+750h+string], rdi
0x18003b11f  mov     rcx, [rsp+750h+var_718]
0x18003b124  test    rcx, rcx
0x18003b127  jz      short loc_18003B13B
0x18003b129  mov     [rsp+750h+var_718], rdi
0x18003b12e  mov     rax, [rcx]
0x18003b131  mov     rax, [rax+10h]
0x18003b135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b13a  nop
0x18003b13b  mov     rcx, [rsi]
0x18003b13e  test    rcx, rcx
0x18003b141  jz      short loc_18003B153
0x18003b143  mov     [rsi], rdi
0x18003b146  mov     rax, [rcx]
0x18003b149  mov     rax, [rax+10h]
0x18003b14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b152  nop
0x18003b153  jmp     loc_18003B29A
0x18003b158  mov     rcx, [rbp+658h]; this
0x18003b15f  mov     r9d, ebx; char *
0x18003b162  lea     r8, aOnecoreBaseSec_1; "onecore\\base\\secureboot\\servicing\\l"...
0x18003b169  mov     edx, 0CDh; void *
0x18003b16e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b173  nop
0x18003b174  xor     ecx, ecx; string
0x18003b176  call    cs:__imp_WindowsDeleteString
0x18003b17c  nop
0x18003b17d  mov     rcx, [rsp+750h+string]; string
0x18003b182  call    cs:__imp_WindowsDeleteString
0x18003b188  mov     [rsp+750h+string], rdi
0x18003b18d  mov     rcx, [rsp+750h+var_718]
0x18003b192  test    rcx, rcx
0x18003b195  jz      short loc_18003B1A9
0x18003b197  mov     [rsp+750h+var_718], rdi
0x18003b19c  mov     rax, [rcx]
0x18003b19f  mov     rax, [rax+10h]
0x18003b1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1a8  nop
0x18003b1a9  mov     rcx, [rsi]
0x18003b1ac  test    rcx, rcx
0x18003b1af  jz      short loc_18003B1C1
0x18003b1b1  mov     [rsi], rdi
0x18003b1b4  mov     rax, [rcx]
0x18003b1b7  mov     rax, [rax+10h]
  ... truncated ...
```
