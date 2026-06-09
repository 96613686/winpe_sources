# AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray(AppV::Shared::AssetIntelligence::AssetIntelligenceData const &,AssetIntelligenceProperties *)

- ea: `0x1400389d0`
- end: `0x140038d76`
- name: `?WriteOneEntryInSafeArray@?$AssetIntelligenceWrapperT@VAssetIntelligenceEmptyBase@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEBUAssetIntelligenceData@AssetIntelligence@Shared@4@PEAUAssetIntelligenceProperties@@@Z`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140022fe4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140018bec`
- `0x14001dbe8`
- `0x1400389d0`
- `0x14003c034`
- `0x14003c258`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140038d1e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140038d1e`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a11`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a3d`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a5e`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a76`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a8e`
- `OLEAUT32!__imp_SysAllocString` at `0x140038aa9`
- `OLEAUT32!__imp_SysAllocString` at `0x140038ac4`
- `OLEAUT32!__imp_SysAllocString` at `0x140038adf`
- `OLEAUT32!__imp_SysAllocString` at `0x140038afa`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b15`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b30`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b4b`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b66`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b81`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b9c`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bb7`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bd2`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bf0`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a11`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a3d`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a5e`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a76`
- `OLEAUT32!__imp_SysAllocString` at `0x140038a8e`
- `OLEAUT32!__imp_SysAllocString` at `0x140038aa9`
- `OLEAUT32!__imp_SysAllocString` at `0x140038ac4`
- `OLEAUT32!__imp_SysAllocString` at `0x140038adf`
- `OLEAUT32!__imp_SysAllocString` at `0x140038afa`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b15`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b30`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b4b`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b66`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b81`
- `OLEAUT32!__imp_SysAllocString` at `0x140038b9c`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bb7`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bd2`
- `OLEAUT32!__imp_SysAllocString` at `0x140038bf0`

## string_xrefs

- `0x140038d17`: `admin\appman\appv\client\host\service\AssetIntelligenceWrapper.h`
- `0x140038d2e`: `admin\appman\appv\client\host\service\AssetIntelligenceWrapper.h`
- `0x140038c7b`: `AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 __fastcall AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray(
        __int64 a1,
        const OLECHAR *a2,
        BSTR *a3)
{
  __int64 v5; // rax
  __int64 v6; // rax
  const OLECHAR *v7; // rcx
  const OLECHAR *v8; // rcx
  const OLECHAR *v9; // rcx
  const OLECHAR *v10; // rcx
  const OLECHAR *v11; // rcx
  const OLECHAR *v12; // rcx
  const OLECHAR *v13; // rcx
  const OLECHAR *v14; // rcx
  const OLECHAR *v15; // rcx
  const OLECHAR *v16; // rcx
  const OLECHAR *v17; // rcx
  const OLECHAR *v18; // rcx
  const OLECHAR *v19; // rcx
  const OLECHAR *v20; // rcx
  const OLECHAR *v21; // rcx
  const OLECHAR *v22; // rcx
  BSTR v23; // rax
  char *v25; // rax
  const char *v26; // rax
  _OWORD v27[2]; // [rsp+20h] [rbp-19h] BYREF
  _OWORD v28[2]; // [rsp+40h] [rbp+7h] BYREF
  char *v29[4]; // [rsp+60h] [rbp+27h] BYREF
  int v30; // [rsp+80h] [rbp+47h]

  v5 = softricity::shared::tostring(v27, a2);
  if ( *(_QWORD *)(v5 + 24) > 7u )
    v5 = *(_QWORD *)v5;
  *a3 = SysAllocString((const OLECHAR *)v5);
  std::wstring::~wstring((char **)v27);
  v6 = softricity::shared::tostring(v27, a2 + 8);
  if ( *(_QWORD *)(v6 + 24) > 7u )
    v6 = *(_QWORD *)v6;
  a3[1] = SysAllocString((const OLECHAR *)v6);
  std::wstring::~wstring((char **)v27);
  v7 = a2 + 16;
  if ( *((_QWORD *)a2 + 7) > 7u )
    v7 = *(const OLECHAR **)v7;
  a3[2] = SysAllocString(v7);
  v8 = a2 + 32;
  if ( *((_QWORD *)a2 + 11) > 7u )
    v8 = *(const OLECHAR **)v8;
  a3[3] = SysAllocString(v8);
  v9 = a2 + 48;
  if ( *((_QWORD *)a2 + 15) > 7u )
    v9 = *(const OLECHAR **)v9;
  a3[4] = SysAllocString(v9);
  v10 = a2 + 64;
  if ( *((_QWORD *)a2 + 19) > 7u )
    v10 = *(const OLECHAR **)v10;
  a3[5] = SysAllocString(v10);
  v11 = a2 + 80;
  if ( *((_QWORD *)a2 + 23) > 7u )
    v11 = *(const OLECHAR **)v11;
  a3[6] = SysAllocString(v11);
  v12 = a2 + 96;
  if ( *((_QWORD *)a2 + 27) > 7u )
    v12 = *(const OLECHAR **)v12;
  a3[7] = SysAllocString(v12);
  v13 = a2 + 112;
  if ( *((_QWORD *)a2 + 31) > 7u )
    v13 = *(const OLECHAR **)v13;
  a3[8] = SysAllocString(v13);
  v14 = a2 + 128;
  if ( *((_QWORD *)a2 + 35) > 7u )
    v14 = *(const OLECHAR **)v14;
  a3[9] = SysAllocString(v14);
  v15 = a2 + 144;
  if ( *((_QWORD *)a2 + 39) > 7u )
    v15 = *(const OLECHAR **)v15;
  a3[10] = SysAllocString(v15);
  v16 = a2 + 160;
  if ( *((_QWORD *)a2 + 43) > 7u )
    v16 = *(const OLECHAR **)v16;
  a3[11] = SysAllocString(v16);
  v17 = a2 + 176;
  if ( *((_QWORD *)a2 + 47) > 7u )
    v17 = *(const OLECHAR **)v17;
  a3[12] = SysAllocString(v17);
  v18 = a2 + 192;
  if ( *((_QWORD *)a2 + 51) > 7u )
    v18 = *(const OLECHAR **)v18;
  a3[13] = SysAllocString(v18);
  v19 = a2 + 208;
  if ( *((_QWORD *)a2 + 55) > 7u )
    v19 = *(const OLECHAR **)v19;
  a3[14] = SysAllocString(v19);
  v20 = a2 + 224;
  if ( *((_QWORD *)a2 + 59) > 7u )
    v20 = *(const OLECHAR **)v20;
  a3[15] = SysAllocString(v20);
  v21 = a2 + 240;
  if ( *((_QWORD *)a2 + 63) > 7u )
    v21 = *(const OLECHAR **)v21;
  a3[16] = SysAllocString(v21);
  v22 = a2 + 256;
  if ( *((_QWORD *)a2 + 67) > 7u )
    v22 = *(const OLECHAR **)v22;
  v23 = SysAllocString(v22);
  a3[17] = v23;
  if ( *a3
    && a3[1]
    && a3[2]
    && a3[3]
    && a3[4]
    && a3[5]
    && a3[6]
    && a3[7]
    && a3[8]
    && a3[9]
    && a3[10]
    && a3[11]
    && a3[12]
    && a3[13]
    && a3[14]
    && a3[15]
    && a3[16]
    && v23 )
  {
    return 0x8000000000LL;
  }
  std::string::string(
    v29,
    "AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::WriteOneEntryInSafeArray");
  v30 = 201;
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,wchar_t const *>((char **)v27, L"Out of memory.", 0xEu);
  memset(v28, 0, sizeof(v28));
  std::wstring::_Construct<1,wchar_t const *>((char **)v28, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v29, 8, (int)v28, (__int64)v27);
  std::wstring::~wstring((char **)v28);
  std::wstring::~wstring((char **)v27);
  std::string::~string(v29);
  v25 = strrchr("admin\\appman\\appv\\client\\host\\service\\AssetIntelligenceWrapper.h", 92);
  if ( v25 )
    v26 = v25 + 1;
  else
    v26 = "admin\\appman\\appv\\client\\host\\service\\AssetIntelligenceWrapper.h";
  return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v26) << 52)
       | 0x19230000000ELL;
}

```

## disassembly

```asm
0x1400389d0  mov     [rsp-8+arg_0], rbx
0x1400389d5  mov     [rsp-8+arg_18], rdi
0x1400389da  push    rbp
0x1400389db  lea     rbp, [rsp-57h]
0x1400389e0  sub     rsp, 90h
0x1400389e7  mov     rax, cs:__security_cookie
0x1400389ee  xor     rax, rsp
0x1400389f1  mov     [rbp+57h+var_8], rax
0x1400389f5  mov     rbx, r8
0x1400389f8  mov     rdi, rdx
0x1400389fb  lea     rcx, [rbp+57h+var_70]
0x1400389ff  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x140038a04  cmp     qword ptr [rax+18h], 7
0x140038a09  jbe     short loc_140038A0E
0x140038a0b  mov     rax, [rax]
0x140038a0e  mov     rcx, rax; psz
0x140038a11  call    cs:__imp_SysAllocString
0x140038a17  mov     [rbx], rax
0x140038a1a  lea     rcx, [rbp+57h+var_70]
0x140038a1e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038a23  lea     rdx, [rdi+10h]
0x140038a27  lea     rcx, [rbp+57h+var_70]
0x140038a2b  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x140038a30  cmp     qword ptr [rax+18h], 7
0x140038a35  jbe     short loc_140038A3A
0x140038a37  mov     rax, [rax]
0x140038a3a  mov     rcx, rax; psz
0x140038a3d  call    cs:__imp_SysAllocString
0x140038a43  mov     [rbx+8], rax
0x140038a47  lea     rcx, [rbp+57h+var_70]
0x140038a4b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038a50  lea     rcx, [rdi+20h]
0x140038a54  cmp     qword ptr [rcx+18h], 7
0x140038a59  jbe     short loc_140038A5E
0x140038a5b  mov     rcx, [rcx]; psz
0x140038a5e  call    cs:__imp_SysAllocString
0x140038a64  mov     [rbx+10h], rax
0x140038a68  lea     rcx, [rdi+40h]
0x140038a6c  cmp     qword ptr [rcx+18h], 7
0x140038a71  jbe     short loc_140038A76
0x140038a73  mov     rcx, [rcx]; psz
0x140038a76  call    cs:__imp_SysAllocString
0x140038a7c  mov     [rbx+18h], rax
0x140038a80  lea     rcx, [rdi+60h]
0x140038a84  cmp     qword ptr [rcx+18h], 7
0x140038a89  jbe     short loc_140038A8E
0x140038a8b  mov     rcx, [rcx]; psz
0x140038a8e  call    cs:__imp_SysAllocString
0x140038a94  mov     [rbx+20h], rax
0x140038a98  lea     rcx, [rdi+80h]
0x140038a9f  cmp     qword ptr [rcx+18h], 7
0x140038aa4  jbe     short loc_140038AA9
0x140038aa6  mov     rcx, [rcx]; psz
0x140038aa9  call    cs:__imp_SysAllocString
0x140038aaf  mov     [rbx+28h], rax
0x140038ab3  lea     rcx, [rdi+0A0h]
0x140038aba  cmp     qword ptr [rcx+18h], 7
0x140038abf  jbe     short loc_140038AC4
0x140038ac1  mov     rcx, [rcx]; psz
0x140038ac4  call    cs:__imp_SysAllocString
0x140038aca  mov     [rbx+30h], rax
0x140038ace  lea     rcx, [rdi+0C0h]
0x140038ad5  cmp     qword ptr [rcx+18h], 7
0x140038ada  jbe     short loc_140038ADF
0x140038adc  mov     rcx, [rcx]; psz
0x140038adf  call    cs:__imp_SysAllocString
0x140038ae5  mov     [rbx+38h], rax
0x140038ae9  lea     rcx, [rdi+0E0h]
0x140038af0  cmp     qword ptr [rcx+18h], 7
0x140038af5  jbe     short loc_140038AFA
0x140038af7  mov     rcx, [rcx]; psz
0x140038afa  call    cs:__imp_SysAllocString
0x140038b00  mov     [rbx+40h], rax
0x140038b04  lea     rcx, [rdi+100h]
0x140038b0b  cmp     qword ptr [rcx+18h], 7
0x140038b10  jbe     short loc_140038B15
0x140038b12  mov     rcx, [rcx]; psz
0x140038b15  call    cs:__imp_SysAllocString
0x140038b1b  mov     [rbx+48h], rax
0x140038b1f  lea     rcx, [rdi+120h]
0x140038b26  cmp     qword ptr [rcx+18h], 7
0x140038b2b  jbe     short loc_140038B30
0x140038b2d  mov     rcx, [rcx]; psz
0x140038b30  call    cs:__imp_SysAllocString
0x140038b36  mov     [rbx+50h], rax
0x140038b3a  lea     rcx, [rdi+140h]
0x140038b41  cmp     qword ptr [rcx+18h], 7
0x140038b46  jbe     short loc_140038B4B
0x140038b48  mov     rcx, [rcx]; psz
0x140038b4b  call    cs:__imp_SysAllocString
0x140038b51  mov     [rbx+58h], rax
0x140038b55  lea     rcx, [rdi+160h]
0x140038b5c  cmp     qword ptr [rcx+18h], 7
0x140038b61  jbe     short loc_140038B66
0x140038b63  mov     rcx, [rcx]; psz
0x140038b66  call    cs:__imp_SysAllocString
0x140038b6c  mov     [rbx+60h], rax
0x140038b70  lea     rcx, [rdi+180h]
0x140038b77  cmp     qword ptr [rcx+18h], 7
0x140038b7c  jbe     short loc_140038B81
0x140038b7e  mov     rcx, [rcx]; psz
0x140038b81  call    cs:__imp_SysAllocString
0x140038b87  mov     [rbx+68h], rax
0x140038b8b  lea     rcx, [rdi+1A0h]
0x140038b92  cmp     qword ptr [rcx+18h], 7
0x140038b97  jbe     short loc_140038B9C
0x140038b99  mov     rcx, [rcx]; psz
0x140038b9c  call    cs:__imp_SysAllocString
0x140038ba2  mov     [rbx+70h], rax
0x140038ba6  lea     rcx, [rdi+1C0h]
0x140038bad  cmp     qword ptr [rcx+18h], 7
0x140038bb2  jbe     short loc_140038BB7
0x140038bb4  mov     rcx, [rcx]; psz
0x140038bb7  call    cs:__imp_SysAllocString
0x140038bbd  mov     [rbx+78h], rax
0x140038bc1  lea     rcx, [rdi+1E0h]
0x140038bc8  cmp     qword ptr [rcx+18h], 7
0x140038bcd  jbe     short loc_140038BD2
0x140038bcf  mov     rcx, [rcx]; psz
0x140038bd2  call    cs:__imp_SysAllocString
0x140038bd8  mov     [rbx+80h], rax
0x140038bdf  lea     rcx, [rdi+200h]
0x140038be6  cmp     qword ptr [rcx+18h], 7
0x140038beb  jbe     short loc_140038BF0
0x140038bed  mov     rcx, [rcx]; psz
0x140038bf0  call    cs:__imp_SysAllocString
0x140038bf6  mov     [rbx+88h], rax
0x140038bfd  xor     edi, edi
0x140038bff  cmp     [rbx], rdi
0x140038c02  jz      short loc_140038C7B
0x140038c04  cmp     [rbx+8], rdi
0x140038c08  jz      short loc_140038C7B
0x140038c0a  cmp     [rbx+10h], rdi
0x140038c0e  jz      short loc_140038C7B
0x140038c10  cmp     [rbx+18h], rdi
0x140038c14  jz      short loc_140038C7B
0x140038c16  cmp     [rbx+20h], rdi
0x140038c1a  jz      short loc_140038C7B
0x140038c1c  cmp     [rbx+28h], rdi
0x140038c20  jz      short loc_140038C7B
0x140038c22  cmp     [rbx+30h], rdi
0x140038c26  jz      short loc_140038C7B
0x140038c28  cmp     [rbx+38h], rdi
0x140038c2c  jz      short loc_140038C7B
0x140038c2e  cmp     [rbx+40h], rdi
0x140038c32  jz      short loc_140038C7B
0x140038c34  cmp     [rbx+48h], rdi
0x140038c38  jz      short loc_140038C7B
0x140038c3a  cmp     [rbx+50h], rdi
0x140038c3e  jz      short loc_140038C7B
0x140038c40  cmp     [rbx+58h], rdi
0x140038c44  jz      short loc_140038C7B
0x140038c46  cmp     [rbx+60h], rdi
0x140038c4a  jz      short loc_140038C7B
0x140038c4c  cmp     [rbx+68h], rdi
0x140038c50  jz      short loc_140038C7B
0x140038c52  cmp     [rbx+70h], rdi
0x140038c56  jz      short loc_140038C7B
0x140038c58  cmp     [rbx+78h], rdi
0x140038c5c  jz      short loc_140038C7B
0x140038c5e  cmp     [rbx+80h], rdi
0x140038c65  jz      short loc_140038C7B
0x140038c67  test    rax, rax
0x140038c6a  jz      short loc_140038C7B
0x140038c6c  mov     rax, 8000000000h
0x140038c76  jmp     loc_140038D55
0x140038c7b  lea     rdx, aAppvClientServ_30; "AppV::Client::Service::AssetIntelligenc"...
0x140038c82  lea     rcx, [rbp+57h+var_30]
0x140038c86  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140038c8b  mov     [rbp+57h+var_10], 0C9h
0x140038c92  xorps   xmm0, xmm0
0x140038c95  movups  [rbp+57h+var_70], xmm0
0x140038c99  xorps   xmm1, xmm1
0x140038c9c  movdqu  [rbp+57h+var_60], xmm1
0x140038ca1  mov     r8d, 0Eh
0x140038ca7  lea     rdx, aOutOfMemory; "Out of memory."
0x140038cae  lea     rcx, [rbp+57h+var_70]
0x140038cb2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140038cb7  nop
0x140038cb8  xorps   xmm0, xmm0
0x140038cbb  movups  [rbp+57h+var_50], xmm0
0x140038cbf  xorps   xmm1, xmm1
0x140038cc2  movdqu  [rbp+57h+var_40], xmm1
0x140038cc7  mov     r8d, 6
0x140038ccd  lea     rdx, aClient; "Client"
0x140038cd4  lea     rcx, [rbp+57h+var_50]
0x140038cd8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140038cdd  nop
0x140038cde  lea     r9, [rbp+57h+var_70]
0x140038ce2  lea     r8, [rbp+57h+var_50]
0x140038ce6  mov     edx, 8
0x140038ceb  lea     rcx, [rbp+57h+var_30]
0x140038cef  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140038cf4  nop
0x140038cf5  lea     rcx, [rbp+57h+var_50]
0x140038cf9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038cfe  nop
0x140038cff  lea     rcx, [rbp+57h+var_70]
0x140038d03  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140038d08  nop
0x140038d09  lea     rcx, [rbp+57h+var_30]
0x140038d0d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140038d12  mov     edx, 5Ch ; '\'; Ch
0x140038d17  lea     rcx, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\host\\serv"...
0x140038d1e  call    cs:__imp_strrchr
0x140038d24  test    rax, rax
0x140038d27  jz      short loc_140038D2E
0x140038d29  inc     rax
0x140038d2c  jmp     short loc_140038D35
0x140038d2e  lea     rax, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\host\\serv"...
0x140038d35  mov     rdx, rax; char *
0x140038d38  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140038d3f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140038d44  shl     rax, 34h
0x140038d48  mov     rcx, 19230000000Eh
0x140038d52  or      rax, rcx
0x140038d55  mov     rcx, [rbp+57h+var_8]
0x140038d59  xor     rcx, rsp; StackCookie
0x140038d5c  call    __security_check_cookie
0x140038d61  lea     r11, [rsp+90h+var_s0]
0x140038d69  mov     rbx, [r11+10h]
0x140038d6d  mov     rdi, [r11+28h]
0x140038d71  mov     rsp, r11
0x140038d74  pop     rbp
0x140038d75  retn
```
