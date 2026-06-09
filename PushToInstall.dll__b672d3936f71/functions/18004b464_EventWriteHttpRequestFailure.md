# EventWriteHttpRequestFailure

- ea: `0x18004b464`
- end: `0x18004b77b`
- name: `EventWriteHttpRequestFailure`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180048d5c`

## callees

- `0x180001890`
- `0x1800115fc`
- `0x180049b40`
- `0x180049d1c`
- `0x18004a1bc`
- `0x18004b464`
- `0x18004b84c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b4c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004b4c9`

## pseudocode

```c
void __fastcall EventWriteHttpRequestFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 a9,
        unsigned __int16 a10,
        int a11,
        int a12,
        int a13,
        __int64 a14,
        unsigned __int64 a15,
        __int64 a16,
        int a17,
        int a18)
{
  CloudSettings *v21; // rcx
  int v22; // ebx
  const struct WinHttpSettings *CloudSettingsSnapshot; // rax
  __int64 v24; // r14
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rcx
  int v28; // eax
  int v29; // [rsp+28h] [rbp-128h]
  const wchar_t *v30; // [rsp+D0h] [rbp-80h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-78h] BYREF
  __int64 v32; // [rsp+E0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+E8h] [rbp-68h] BYREF
  __int64 v34; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v35; // [rsp+F8h] [rbp-58h] BYREF
  unsigned __int16 *v36; // [rsp+100h] [rbp-50h] BYREF
  __int64 v37; // [rsp+108h] [rbp-48h] BYREF
  __int64 v38; // [rsp+110h] [rbp-40h] BYREF
  __int64 v39; // [rsp+118h] [rbp-38h] BYREF
  __int64 v40; // [rsp+120h] [rbp-30h] BYREF
  __int16 *v41; // [rsp+128h] [rbp-28h] BYREF
  __int64 v42[10]; // [rsp+130h] [rbp-20h] BYREF

  if ( byte_180066498 )
  {
    v21 = (CloudSettings *)ppv;
    v22 = -1;
    if ( ppv
      || (CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv),
          (v21 = (CloudSettings *)ppv) != 0) )
    {
      a6 = 0;
      if ( (*(int (__fastcall **)(CloudSettings *, int *))(*(_QWORD *)v21 + 104LL))(v21, &a6) >= 0 )
        v22 = a6;
    }
    CloudSettingsSnapshot = CloudSettings::GetCloudSettingsSnapshot(v21);
    v24 = a16;
    if ( a5 == -2147012889 || (*(_BYTE *)CloudSettingsSnapshot & 4) == 0 )
    {
      CacheOrUploadOnBoxRequestFailure(a2, a5, a4, a18, 0);
    }
    else if ( (int)StringCchPrintfW(&qword_180066710, 0xAu, L"%d", a10) >= 0
           && (unsigned int)dword_1800652E8 > 5
           && (qword_1800652F8 & 0x400000000000LL) != 0
           && (qword_180065300 & 0x400000000000LL) == qword_180065300 )
    {
      v27 = 0x7FFFFFFF;
      a17 = a18;
      v30 = L"3.2";
      v28 = a15;
      a14 = 0;
      a8 = v22;
      v31 = v24;
      if ( a15 > 0x7FFFFFFF )
        v28 = 0x7FFFFFFF;
      a11 = v28;
      v36 = &qword_180066710;
      v37 = a9;
      v39 = a7;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v38 = 0;
      LOBYTE(a6) = 0;
      a12 = a5;
      if ( a4 <= 0x7FFFFFFF )
        v27 = (unsigned int)a4;
      a13 = v27;
      v41 = &word_1800666C0;
      v40 = a1;
      v42[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v27,
        (__int64)&unk_18005B5E0,
        v25,
        v26,
        (__int64)v42,
        &v41,
        &v40,
        (__int64)&a13,
        (__int64)&a12,
        (__int64)&a6,
        &v39,
        &v38,
        &v37,
        &v36,
        &v35,
        &v34,
        &v33,
        &v32,
        (__int64)&a11,
        &v31,
        (__int64)&a8,
        &v30,
        &a14);
    }
    CacheOrUploadHttpRequestSuccess(0, 0, 0, 0, 0, 0, 0);
    CacheOrUploadHttpRequest(a2, a10, a4, v24, a5, v29);
  }
}

```

## disassembly

```asm
0x18004b464  mov     [rsp-8+arg_10], r8
0x18004b469  push    rbp
0x18004b46a  push    rbx
0x18004b46b  push    rsi
0x18004b46c  push    rdi
0x18004b46d  push    r12
0x18004b46f  push    r13
0x18004b471  push    r14
0x18004b473  push    r15
0x18004b475  lea     rbp, [rsp+8]
0x18004b47a  sub     rsp, 148h
0x18004b481  xor     r13d, r13d
0x18004b484  mov     rsi, r9
0x18004b487  cmp     cs:byte_180066498, r13b
0x18004b48e  mov     r15, rdx
0x18004b491  mov     r12, rcx
0x18004b494  jz      loc_18004B767
0x18004b49a  mov     rcx, cs:ppv
0x18004b4a1  or      ebx, 0FFFFFFFFh
0x18004b4a4  test    rcx, rcx
0x18004b4a7  jnz     short loc_18004B4DB
0x18004b4a9  lea     rax, ppv
0x18004b4b0  xor     edx, edx; pUnkOuter
0x18004b4b2  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18004b4b9  mov     [rsp+180h+ppv], rax; ppv
0x18004b4be  lea     r8d, [r13+1]; dwClsContext
0x18004b4c2  lea     rcx, CLSID_NetworkListManager; rclsid
0x18004b4c9  call    cs:__imp_CoCreateInstance
0x18004b4cf  mov     rcx, cs:ppv
0x18004b4d6  test    rcx, rcx
0x18004b4d9  jz      short loc_18004B4F5
0x18004b4db  mov     [rbp+30h+arg_28], r13d
0x18004b4df  lea     rdx, [rbp+30h+arg_28]
0x18004b4e3  mov     rax, [rcx]
0x18004b4e6  mov     rax, [rax+68h]
0x18004b4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4ef  test    eax, eax
0x18004b4f1  cmovns  ebx, [rbp+30h+arg_28]
0x18004b4f5  call    ?GetCloudSettingsSnapshot@CloudSettings@@QEAAAEBUWinHttpSettings@@XZ; CloudSettings::GetCloudSettingsSnapshot(void)
0x18004b4fa  mov     edi, [rbp+30h+arg_20]
0x18004b4fd  mov     r14, [rbp+30h+arg_78]
0x18004b504  cmp     edi, 80072EE7h
0x18004b50a  jz      loc_18004B717
0x18004b510  test    byte ptr [rax], 4
0x18004b513  jz      loc_18004B717
0x18004b519  movzx   r9d, [rbp+30h+arg_48]
0x18004b521  lea     r8, aD; "%d"
0x18004b528  mov     edx, 0Ah; unsigned __int64
0x18004b52d  lea     rcx, qword_180066710; unsigned __int16 *
0x18004b534  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004b539  test    eax, eax
0x18004b53b  js      loc_18004B730
0x18004b541  mov     eax, cs:dword_1800652E8
0x18004b547  cmp     eax, 5
0x18004b54a  jbe     loc_18004B730
0x18004b550  mov     rcx, cs:qword_180065300
0x18004b557  mov     rdx, 400000000000h
0x18004b561  mov     rax, cs:qword_1800652F8
0x18004b568  test    rdx, rax
0x18004b56b  jz      loc_18004B730
0x18004b571  mov     rax, rcx
0x18004b574  and     rax, rdx
0x18004b577  cmp     rax, rcx
0x18004b57a  jnz     loc_18004B730
0x18004b580  mov     eax, [rbp+30h+arg_88]
0x18004b586  mov     ecx, 7FFFFFFFh
0x18004b58b  mov     [rbp+30h+arg_80], eax
0x18004b591  lea     rax, a32; "3.2"
0x18004b598  mov     [rbp+30h+var_B0], rax
0x18004b59c  mov     rax, [rbp+30h+arg_70]
0x18004b5a3  mov     dword ptr [rbp+30h+arg_10], r13d
0x18004b5a7  mov     [rbp+30h+arg_68], r13
0x18004b5ae  mov     [rbp+30h+arg_38], ebx
0x18004b5b1  mov     [rbp+30h+var_A8], r14
0x18004b5b5  cmp     rax, rcx
0x18004b5b8  jbe     short loc_18004B5BC
0x18004b5ba  mov     eax, ecx
0x18004b5bc  mov     [rbp+30h+arg_50], eax
0x18004b5c2  lea     rax, qword_180066710
0x18004b5c9  mov     [rbp+30h+var_80], rax
0x18004b5cd  mov     rax, [rbp+30h+arg_40]
0x18004b5d4  mov     [rbp+30h+var_78], rax
0x18004b5d8  mov     rax, [rbp+30h+arg_30]
0x18004b5dc  mov     [rbp+30h+var_68], rax
0x18004b5e0  mov     [rbp+30h+var_A0], r13
0x18004b5e4  mov     [rbp+30h+var_98], r13
0x18004b5e8  mov     [rbp+30h+var_90], r13
0x18004b5ec  mov     [rbp+30h+var_88], r13
0x18004b5f0  mov     [rbp+30h+var_70], r13
0x18004b5f4  mov     byte ptr [rbp+30h+arg_28], r13b
0x18004b5f8  mov     [rbp+30h+arg_58], edi
0x18004b5fe  cmp     rsi, rcx
0x18004b601  ja      short loc_18004B605
0x18004b603  mov     ecx, esi
0x18004b605  lea     rax, word_1800666C0
0x18004b60c  mov     [rbp+30h+arg_60], ecx
0x18004b612  mov     [rbp+30h+var_58], rax
0x18004b616  lea     rdx, unk_18005B5E0
0x18004b61d  lea     rax, [rbp+30h+arg_80]
0x18004b624  mov     [rbp+30h+var_60], r12
0x18004b628  mov     [rsp+180h+var_C0], rax
0x18004b630  lea     rax, [rbp+30h+arg_10]
0x18004b634  mov     [rsp+180h+var_C8], rax
0x18004b63c  lea     rax, [rbp+30h+arg_68]
0x18004b643  mov     [rsp+180h+var_D0], rax
0x18004b64b  lea     rax, [rbp+30h+var_B0]
0x18004b64f  mov     [rsp+180h+var_D8], rax
0x18004b657  lea     rax, [rbp+30h+arg_38]
0x18004b65b  mov     [rsp+180h+var_E0], rax
0x18004b663  lea     rax, [rbp+30h+var_A8]
0x18004b667  mov     [rsp+180h+var_E8], rax
0x18004b66f  lea     rax, [rbp+30h+arg_50]
0x18004b676  mov     [rsp+180h+var_F0], rax
0x18004b67e  lea     rax, [rbp+30h+var_A0]
0x18004b682  mov     [rsp+180h+var_F8], rax
0x18004b68a  lea     rax, [rbp+30h+var_98]
0x18004b68e  mov     [rsp+180h+var_100], rax
0x18004b696  lea     rax, [rbp+30h+var_90]
0x18004b69a  mov     [rsp+180h+var_108], rax
0x18004b69f  lea     rax, [rbp+30h+var_88]
0x18004b6a3  mov     [rsp+180h+var_110], rax
0x18004b6a8  lea     rax, [rbp+30h+var_80]
0x18004b6ac  mov     [rsp+180h+var_118], rax
0x18004b6b1  lea     rax, [rbp+30h+var_78]
0x18004b6b5  mov     [rsp+180h+var_120], rax
0x18004b6ba  lea     rax, [rbp+30h+var_70]
0x18004b6be  mov     [rsp+180h+var_128], rax
0x18004b6c3  lea     rax, [rbp+30h+var_68]
0x18004b6c7  mov     [rsp+180h+var_130], rax
0x18004b6cc  lea     rax, [rbp+30h+arg_28]
0x18004b6d0  mov     [rsp+180h+var_138], rax
0x18004b6d5  lea     rax, [rbp+30h+arg_58]
0x18004b6dc  mov     [rsp+180h+var_140], rax
0x18004b6e1  lea     rax, [rbp+30h+arg_60]
0x18004b6e8  mov     [rsp+180h+var_148], rax
0x18004b6ed  lea     rax, [rbp+30h+var_60]
0x18004b6f1  mov     [rsp+180h+var_150], rax
0x18004b6f6  lea     rax, [rbp+30h+var_58]
0x18004b6fa  mov     [rsp+180h+var_158], rax
0x18004b6ff  lea     rax, [rbp+30h+var_50]
0x18004b703  mov     [rsp+180h+ppv], rax
0x18004b708  mov     [rbp+30h+var_50], 2000000h
0x18004b710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U3@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@U2@U2@U2@U2@U3@U2@U3@U2@U2@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@5AEBU?$_tlgWrapperByVal@$00@@444444445454455@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18004b715  jmp     short loc_18004B730
0x18004b717  mov     r9d, [rbp+30h+arg_88]
0x18004b71e  mov     r8, rsi
0x18004b721  mov     edx, edi
0x18004b723  mov     byte ptr [rsp+180h+ppv], r13b
0x18004b728  mov     rcx, r15
0x18004b72b  call    _CacheOrUploadOnBoxRequestFailure
0x18004b730  mov     byte ptr [rsp+180h+var_150], r13b
0x18004b735  xor     edx, edx
0x18004b737  mov     dword ptr [rsp+180h+var_158], r13d
0x18004b73c  xor     r9d, r9d
0x18004b73f  xor     r8d, r8d
0x18004b742  mov     [rsp+180h+ppv], r13
0x18004b747  xor     ecx, ecx
0x18004b749  call    _CacheOrUploadHttpRequestSuccess
0x18004b74e  movzx   edx, [rbp+30h+arg_48]
0x18004b755  mov     r9, r14
0x18004b758  mov     r8, rsi
0x18004b75b  mov     dword ptr [rsp+180h+ppv], edi
0x18004b75f  mov     rcx, r15
0x18004b762  call    _CacheOrUploadHttpRequest
0x18004b767  add     rsp, 148h
0x18004b76e  pop     r15
0x18004b770  pop     r14
0x18004b772  pop     r13
0x18004b774  pop     r12
0x18004b776  pop     rdi
0x18004b777  pop     rsi
0x18004b778  pop     rbx
0x18004b779  pop     rbp
0x18004b77a  retn
```
