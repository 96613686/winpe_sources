# InventoryApplicationInstalled::SendEvent(void)

- ea: `0x18010dd68`
- end: `0x18010e1b6`
- name: `?SendEvent@InventoryApplicationInstalled@@SAXXZ`
- size: `1102`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180066e80`

## callees

- `0x180001364`
- `0x18000243c`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x1800289d0`
- `0x18002cef4`
- `0x18002d3b8`
- `0x18002debc`
- `0x180030038`
- `0x1800417a8`
- `0x18004f744`
- `0x180052f28`
- `0x180056140`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x1800679f8`
- `0x180067a30`
- `0x1800fc078`
- `0x18010db2c`
- `0x18010dc28`
- `0x18010dd68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18010ded3`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18010df20`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18010ded3`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18010df20`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18010deee`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18010df3c`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18010deee`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18010df3c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010e113`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18010e113`

## string_xrefs

- `0x18010dfd1`: `Max ProgramId limit reached. Installed ProgramId count: %zu`
- `0x18010e1a4`: `base\appcompat\inventory\software\inv2\lib\inventoryapplicationinstalled.cpp`
- `0x18010e053`: `Installed`
- `0x18010dfde`: `InventoryApplicationInstalled::SendEvent`
- `0x18010e146`: `InventoryApplicationInstalled::SetEventSentTime`
- `0x18010e139`: `TelCacheProvider::SetMetadata failed [%#x]`
- `0x18010e05e`: `InventoryApplicationInstalled`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void InventoryApplicationInstalled::SendEvent(void)
{
  Application *v0; // rax
  const unsigned __int16 *v1; // rdx
  int v2; // eax
  int v3; // r12d
  void **v4; // rdx
  UtcThrottle *v5; // rcx
  __int64 v6; // rsi
  struct _FILETIME v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r14
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  char v12; // di
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  char v16; // al
  _QWORD *v17; // rax
  char v18; // di
  int v19; // ebx
  int v20; // r8d
  int v21; // r9d
  int v22; // [rsp+20h] [rbp-E0h]
  __int16 v23; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp-88h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME v29; // [rsp+A8h] [rbp-58h]
  char *v30; // [rsp+B8h] [rbp-48h] BYREF
  const unsigned __int16 *Version; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v32; // [rsp+C8h] [rbp-38h] BYREF
  const wchar_t *v33; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v34; // [rsp+D8h] [rbp-28h] BYREF
  const wchar_t *v35; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-18h] BYREF
  __int16 v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  _QWORD v39[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v40; // [rsp+110h] [rbp+10h]
  unsigned __int64 v41; // [rsp+118h] [rbp+18h]
  __int64 v42; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v43[80]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v44; // [rsp+178h] [rbp+78h]
  __int16 v45; // [rsp+180h] [rbp+80h]
  __int64 v46; // [rsp+188h] [rbp+88h]
  __int128 v47; // [rsp+190h] [rbp+90h]
  __int64 v48; // [rsp+1A0h] [rbp+A0h]
  int v49; // [rsp+1A8h] [rbp+A8h]
  char v50; // [rsp+1ACh] [rbp+ACh]
  _BYTE v51[16]; // [rsp+1B0h] [rbp+B0h] BYREF
  TelCacheProvider *v52; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v38 = -2;
  memset_0(v43, 0, 0x4Eu);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v44 = 0;
  v42 = 0;
  v27 = (__int64)operator new(0x3F0u);
  v0 = Application::Application((Application *)v27);
  v1 = (const unsigned __int16 *)&Application::ApplicationCacheProviderName;
  if ( (unsigned __int64)qword_180182A38 > 7 )
    v1 = (const unsigned __int16 *)Application::ApplicationCacheProviderName;
  v2 = TelCacheProvider::Initialize(&v42, v1, (__int64)v0, 0, 1, 3u, 0x64u);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\inventoryapplicationinstalled.cpp",
      (const char *)(unsigned int)v2,
      v22);
  ConfigSettings::ConfigSettings(v51, 5, &v42, 0);
  if ( InventoryApplicationInstalled::CanSendEvent(v52) )
  {
    v3 = 0;
    v25 = 0;
    v26 = 0;
    Application::GetProgramIdsFromCache(&v28, v51);
    v6 = v28;
    v7 = v29;
    SystemTimeAsFileTime = v29;
    while ( v6 != v7 )
    {
      std::wstring::wstring(v39, v6);
      v8 = 0;
      if ( v40 )
      {
        v9 = v41;
        do
        {
          v10 = v39;
          if ( v9 > 7 )
            v10 = (_QWORD *)v39[0];
          if ( (unsigned int)_o_iswalpha(*((unsigned __int16 *)v10 + v8)) )
          {
            v11 = v39;
            if ( v9 > 7 )
              v11 = (_QWORD *)v39[0];
            v12 = towupper(*((_WORD *)v11 + v8)) - 55;
          }
          else
          {
            v13 = v39;
            if ( v9 > 7 )
              v13 = (_QWORD *)v39[0];
            v12 = *((_BYTE *)v13 + 2 * v8) - 48;
          }
          v14 = v39;
          if ( v9 > 7 )
            v14 = (_QWORD *)v39[0];
          if ( (unsigned int)_o_iswalpha(*((unsigned __int16 *)v14 + v8 + 1)) )
          {
            v15 = v39;
            if ( v9 > 7 )
              v15 = (_QWORD *)v39[0];
            v16 = towupper(*((_WORD *)v15 + v8 + 1)) - 55;
          }
          else
          {
            v17 = v39;
            if ( v9 > 7 )
              v17 = (_QWORD *)v39[0];
            v16 = *((_BYTE *)v17 + 2 * v8 + 2) - 48;
          }
          v18 = v16 | (16 * v12);
          LOBYTE(v23) = v18;
          if ( *((_QWORD *)&v25 + 1) == v26 )
          {
            std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>(&v25, *((_QWORD *)&v25 + 1), &v23);
          }
          else
          {
            **((_BYTE **)&v25 + 1) = v18;
            ++*((_QWORD *)&v25 + 1);
          }
          v8 += 2LL;
        }
        while ( v8 < v40 );
        v7 = SystemTimeAsFileTime;
      }
      if ( (unsigned int)++v3 >= 0x7D0 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"InventoryApplicationInstalled::SendEvent",
          72,
          (unsigned int)"Max ProgramId limit reached. Installed ProgramId count: %zu");
        std::wstring::~wstring(v39);
        break;
      }
      std::wstring::~wstring(v39);
      v6 += 32;
    }
    UtcThrottle::Throttle(v5, v4);
    v19 = xmmword_180182350;
    if ( *(_DWORD *)xmmword_180182350 > 5u && (unsigned __int8)tlgKeywordOn(xmmword_180182350, 0x800000000000LL) )
    {
      v30 = &byte_180182368;
      Version = InventoryCoreGetVersion();
      v32 = &byte_1801389F0;
      v33 = L"0";
      v34 = L"Installed";
      v35 = L"InventoryApplicationInstalled";
      SystemTimeAsFileTime.dwLowDateTime = 1;
      v36 = v25;
      v37 = WORD4(v25) - v25;
      v23 = (*(_QWORD *)&v29 - v28) >> 5;
      v27 = 0x80000000LL;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)&unk_180162A30,
        v20,
        v21,
        (__int64)&v27,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&SystemTimeAsFileTime,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&Version,
        (__int64)&v30);
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( (int)TelCacheProvider::SetMetadata(v52, L"ProgramIdListEventSentTime", *(_QWORD *)&SystemTimeAsFileTime) < 0 )
      AslLogCallPrintf(
        1,
        (unsigned int)"InventoryApplicationInstalled::SetEventSentTime",
        185,
        (unsigned int)"TelCacheProvider::SetMetadata failed [%#x]");
    std::vector<std::wstring>::_Tidy(&v28);
    std::vector<unsigned char>::_Tidy(&v25);
  }
  ConfigSettings::~ConfigSettings((ConfigSettings *)v51);
  TelCacheProvider::~TelCacheProvider((TelCacheProvider *)&v42);
}

```

## disassembly

```asm
0x18010dd68  push    rbp
0x18010dd6a  push    rbx
0x18010dd6b  push    rsi
0x18010dd6c  push    rdi
0x18010dd6d  push    r12
0x18010dd6f  push    r14
0x18010dd71  lea     rbp, [rsp-1B8h]
0x18010dd79  sub     rsp, 2B8h
0x18010dd80  mov     [rbp+1E0h+var_1E8], 0FFFFFFFFFFFFFFFEh
0x18010dd88  mov     rax, cs:__security_cookie
0x18010dd8f  xor     rax, rsp
0x18010dd92  mov     [rbp+1E0h+var_40], rax
0x18010dd99  xor     edx, edx; Val
0x18010dd9b  lea     r8d, [rdx+4Eh]; Size
0x18010dd9f  lea     rcx, [rbp+1E0h+var_1B8]; void *
0x18010dda3  call    memset_0
0x18010dda8  xor     r14d, r14d
0x18010ddab  mov     [rbp+1E0h+var_160], r14w
0x18010ddb3  mov     [rbp+1E0h+var_158], r14
0x18010ddba  xorps   xmm0, xmm0
0x18010ddbd  movdqa  [rbp+1E0h+var_150], xmm0
0x18010ddc5  mov     [rbp+1E0h+var_140], r14
0x18010ddcc  mov     [rbp+1E0h+var_138], r14d
0x18010ddd3  mov     [rbp+1E0h+var_134], r14b
0x18010ddda  mov     [rbp+1E0h+var_168], r14
0x18010ddde  mov     [rbp+1E0h+var_1C0], r14
0x18010dde2  mov     ecx, 3F0h; Size
0x18010dde7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010ddec  mov     [rbp+1E0h+var_248], rax
0x18010ddf0  mov     rcx, rax; this
0x18010ddf3  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x18010ddf8  nop
0x18010ddf9  lea     rdx, ?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x18010de00  cmp     cs:qword_180182A38, 7
0x18010de08  cmova   rdx, cs:?ApplicationCacheProviderName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationCacheProviderName
0x18010de10  mov     dword ptr [rsp+2E0h+var_2B0], 64h ; 'd'
0x18010de18  mov     dword ptr [rsp+2E0h+var_2B8], 3
0x18010de20  mov     [rsp+2E0h+var_2C0], 1; int
0x18010de28  xor     r9d, r9d
0x18010de2b  mov     r8, rax
0x18010de2e  lea     rcx, [rbp+1E0h+var_1C0]
0x18010de32  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18010de37  mov     rcx, [rbp+1E8h]; this
0x18010de3e  test    eax, eax
0x18010de40  js      loc_18010E1A1
0x18010de46  xor     r9d, r9d
0x18010de49  lea     r8, [rbp+1E0h+var_1C0]
0x18010de4d  lea     edx, [r14+5]
0x18010de51  lea     rcx, [rbp+1E0h+var_130]
0x18010de58  call    ??0ConfigSettings@@QEAA@W4FileInventoryMode@@PEAVTelCacheProvider@@1_N2@Z; ConfigSettings::ConfigSettings(FileInventoryMode,TelCacheProvider *,TelCacheProvider *,bool,bool)
0x18010de5d  nop
0x18010de5e  mov     rcx, [rbp+1E0h+var_120]; struct TelCacheProvider *
0x18010de65  call    ?CanSendEvent@InventoryApplicationInstalled@@CA_NAEAVTelCacheProvider@@@Z; InventoryApplicationInstalled::CanSendEvent(TelCacheProvider &)
0x18010de6a  test    al, al
0x18010de6c  jz      loc_18010E16C
0x18010de72  mov     r12d, r14d
0x18010de75  xorps   xmm0, xmm0
0x18010de78  movdqu  [rbp+1E0h+var_260], xmm0
0x18010de7d  mov     [rbp+1E0h+var_250], r14
0x18010de81  lea     rdx, [rbp+1E0h+var_130]
0x18010de88  lea     rcx, [rbp+1E0h+var_240]
0x18010de8c  call    ?GetProgramIdsFromCache@Application@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBVConfigSettings@@@Z; Application::GetProgramIdsFromCache(ConfigSettings const &)
0x18010de91  nop
0x18010de92  mov     rsi, [rbp+1E0h+var_240]
0x18010de96  mov     rdi, [rbp+1E0h+var_238]
0x18010de9a  mov     qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18010de9f  jmp     loc_18010DFB5
0x18010dea4  mov     rdx, rsi
0x18010dea7  lea     rcx, [rbp+1E0h+var_1E0]
0x18010deab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010deb0  nop
0x18010deb1  mov     rbx, r14
0x18010deb4  cmp     [rbp+1E0h+var_1D0], r14
0x18010deb8  jbe     loc_18010DF9C
0x18010debe  mov     r14, [rbp+1E0h+var_1C8]
0x18010dec2  lea     rcx, [rbp+1E0h+var_1E0]
0x18010dec6  cmp     r14, 7
0x18010deca  cmova   rcx, [rbp+1E0h+var_1E0]
0x18010decf  movzx   ecx, word ptr [rcx+rbx*2]
0x18010ded3  call    cs:__imp__o_iswalpha
0x18010ded9  test    eax, eax
0x18010dedb  jz      short loc_18010DEF9
0x18010dedd  lea     rcx, [rbp+1E0h+var_1E0]
0x18010dee1  cmp     r14, 7
0x18010dee5  cmova   rcx, [rbp+1E0h+var_1E0]
0x18010deea  movzx   ecx, word ptr [rcx+rbx*2]; C
0x18010deee  call    cs:__imp_towupper
0x18010def4  lea     edi, [rax-37h]
0x18010def7  jmp     short loc_18010DF0E
0x18010def9  lea     rax, [rbp+1E0h+var_1E0]
0x18010defd  cmp     r14, 7
0x18010df01  cmova   rax, [rbp+1E0h+var_1E0]
0x18010df06  mov     dil, [rax+rbx*2]
0x18010df0a  sub     dil, 30h ; '0'
0x18010df0e  lea     rcx, [rbp+1E0h+var_1E0]
0x18010df12  cmp     r14, 7
0x18010df16  cmova   rcx, [rbp+1E0h+var_1E0]
0x18010df1b  movzx   ecx, word ptr [rcx+rbx*2+2]
0x18010df20  call    cs:__imp__o_iswalpha
0x18010df26  test    eax, eax
0x18010df28  jz      short loc_18010DF46
0x18010df2a  lea     rcx, [rbp+1E0h+var_1E0]
0x18010df2e  cmp     r14, 7
0x18010df32  cmova   rcx, [rbp+1E0h+var_1E0]
0x18010df37  movzx   ecx, word ptr [rcx+rbx*2+2]; C
0x18010df3c  call    cs:__imp_towupper
0x18010df42  sub     al, 37h ; '7'
0x18010df44  jmp     short loc_18010DF59
0x18010df46  lea     rax, [rbp+1E0h+var_1E0]
0x18010df4a  cmp     r14, 7
0x18010df4e  cmova   rax, [rbp+1E0h+var_1E0]
0x18010df53  mov     al, [rax+rbx*2+2]
0x18010df57  sub     al, 30h ; '0'
0x18010df59  shl     dil, 4
0x18010df5d  or      dil, al
0x18010df60  mov     byte ptr [rsp+2E0h+var_270], dil
0x18010df65  mov     rdx, qword ptr [rbp+1E0h+var_260+8]
0x18010df69  cmp     rdx, [rbp+1E0h+var_250]
0x18010df6d  jz      short loc_18010DF78
0x18010df6f  mov     [rdx], dil
0x18010df72  inc     qword ptr [rbp+1E0h+var_260+8]
0x18010df76  jmp     short loc_18010DF86
0x18010df78  lea     r8, [rsp+2E0h+var_270]
0x18010df7d  lea     rcx, [rbp+1E0h+var_260]
0x18010df81  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x18010df86  add     rbx, 2
0x18010df8a  cmp     rbx, [rbp+1E0h+var_1D0]
0x18010df8e  jb      loc_18010DEC2
0x18010df94  mov     rdi, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x18010df99  xor     r14d, r14d
0x18010df9c  inc     r12d
0x18010df9f  cmp     r12d, 7D0h
0x18010dfa6  jnb     short loc_18010DFC0
0x18010dfa8  lea     rcx, [rbp+1E0h+var_1E0]
0x18010dfac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010dfb1  add     rsi, 20h ; ' '
0x18010dfb5  cmp     rsi, rdi
0x18010dfb8  jnz     loc_18010DEA4
0x18010dfbe  jmp     short loc_18010DFF8
0x18010dfc0  mov     rax, [rbp+1E0h+var_238]
0x18010dfc4  sub     rax, [rbp+1E0h+var_240]
0x18010dfc8  sar     rax, 5
0x18010dfcc  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18010dfd1  lea     r9, aMaxProgramidLi; "Max ProgramId limit reached. Installed "...
0x18010dfd8  mov     r8d, 48h ; 'H'
0x18010dfde  lea     rdx, aInventoryappli; "InventoryApplicationInstalled::SendEven"...
0x18010dfe5  lea     ecx, [r8-47h]
0x18010dfe9  call    AslLogCallPrintf
0x18010dfee  nop
0x18010dfef  lea     rcx, [rbp+1E0h+var_1E0]
0x18010dff3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010dff8  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18010dffd  mov     rbx, qword ptr cs:xmmword_180182350
0x18010e004  mov     eax, [rbx]
0x18010e006  cmp     eax, 5
0x18010e009  jbe     loc_18010E109
0x18010e00f  mov     rdx, 800000000000h
0x18010e019  mov     rcx, rbx
0x18010e01c  call    _tlgKeywordOn
0x18010e021  test    al, al
0x18010e023  jz      loc_18010E109
0x18010e029  lea     rax, byte_180182368
0x18010e030  mov     [rbp+1E0h+var_228], rax
0x18010e034  call    ?InventoryCoreGetVersion@@YAPEBGXZ; InventoryCoreGetVersion(void)
0x18010e039  mov     [rbp+1E0h+var_220], rax
0x18010e03d  lea     rax, byte_1801389F0
0x18010e044  mov     [rbp+1E0h+var_218], rax
0x18010e048  lea     rax, a0_0; "0"
0x18010e04f  mov     [rbp+1E0h+var_210], rax
0x18010e053  lea     rax, aInstalled; "Installed"
0x18010e05a  mov     [rbp+1E0h+var_208], rax
0x18010e05e  lea     rax, aInventoryappli_2; "InventoryApplicationInstalled"
0x18010e065  mov     [rbp+1E0h+var_200], rax
0x18010e069  mov     [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], 1
0x18010e071  mov     rcx, qword ptr [rbp+1E0h+var_260]
0x18010e075  mov     [rbp+1E0h+var_1F8], rcx
0x18010e079  movzx   eax, word ptr [rbp+1E0h+var_260+8]
0x18010e07d  sub     ax, cx
0x18010e080  mov     [rbp+1E0h+var_1F0], ax
0x18010e084  mov     rax, [rbp+1E0h+var_238]
0x18010e088  sub     rax, [rbp+1E0h+var_240]
0x18010e08c  sar     rax, 5
0x18010e090  mov     [rsp+2E0h+var_270], ax
0x18010e095  mov     eax, 80000000h
0x18010e09a  mov     [rbp+1E0h+var_248], rax
0x18010e09e  lea     rax, [rbp+1E0h+var_228]
0x18010e0a2  mov     [rsp+2E0h+var_278], rax
0x18010e0a7  lea     rax, [rbp+1E0h+var_220]
0x18010e0ab  mov     [rsp+2E0h+var_280], rax
0x18010e0b0  lea     rax, [rbp+1E0h+var_218]
0x18010e0b4  mov     [rsp+2E0h+var_288], rax
0x18010e0b9  lea     rax, [rbp+1E0h+var_210]
0x18010e0bd  mov     [rsp+2E0h+var_290], rax
0x18010e0c2  lea     rax, [rbp+1E0h+var_208]
0x18010e0c6  mov     [rsp+2E0h+var_298], rax
0x18010e0cb  lea     rax, [rbp+1E0h+var_200]
0x18010e0cf  mov     [rsp+2E0h+var_2A0], rax
0x18010e0d4  lea     rax, [rsp+2E0h+SystemTimeAsFileTime]
0x18010e0d9  mov     [rsp+2E0h+var_2A8], rax
0x18010e0de  lea     rax, [rbp+1E0h+var_1F8]
0x18010e0e2  mov     [rsp+2E0h+var_2B0], rax
0x18010e0e7  lea     rax, [rsp+2E0h+var_270]
0x18010e0ec  mov     [rsp+2E0h+var_2B8], rax
0x18010e0f1  lea     rax, [rbp+1E0h+var_248]
0x18010e0f5  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x18010e0fa  lea     rdx, unk_180162A30
0x18010e101  mov     rcx, rbx
0x18010e104  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperArray@$00@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U5@U5@U5@U5@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@7777AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x18010e109  mov     qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x18010e10e  lea     rcx, [rsp+2E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18010e113  call    cs:__imp_GetSystemTimeAsFileTime
0x18010e119  mov     r8, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]; unsigned __int64
0x18010e11e  lea     rdx, aProgramidliste; "ProgramIdListEventSentTime"
0x18010e125  mov     rcx, [rbp+1E0h+var_120]; this
0x18010e12c  call    ?SetMetadata@TelCacheProvider@@QEAAJPEBG_K@Z; TelCacheProvider::SetMetadata(ushort const *,unsigned __int64)
0x18010e131  test    eax, eax
0x18010e133  jns     short loc_18010E158
0x18010e135  mov     [rsp+2E0h+var_2C0], eax
0x18010e139  lea     r9, aTelcacheprovid_13; "TelCacheProvider::SetMetadata failed [%"...
0x18010e140  mov     r8d, 0B9h
0x18010e146  lea     rdx, aInventoryappli_0; "InventoryApplicationInstalled::SetEvent"...
0x18010e14d  mov     ecx, 1
0x18010e152  call    AslLogCallPrintf
0x18010e157  nop
0x18010e158  lea     rcx, [rbp+1E0h+var_240]
0x18010e15c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18010e161  nop
0x18010e162  lea     rcx, [rbp+1E0h+var_260]
0x18010e166  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18010e16b  nop
0x18010e16c  lea     rcx, [rbp+1E0h+var_130]; this
0x18010e173  call    ??1ConfigSettings@@UEAA@XZ; ConfigSettings::~ConfigSettings(void)
0x18010e178  nop
0x18010e179  lea     rcx, [rbp+1E0h+var_1C0]; this
0x18010e17d  call    ??1TelCacheProvider@@QEAA@XZ; TelCacheProvider::~TelCacheProvider(void)
0x18010e182  mov     rcx, [rbp+1E0h+var_40]
0x18010e189  xor     rcx, rsp; StackCookie
0x18010e18c  call    __security_check_cookie
0x18010e191  add     rsp, 2B8h
0x18010e198  pop     r14
0x18010e19a  pop     r12
0x18010e19c  pop     rdi
0x18010e19d  pop     rsi
0x18010e19e  pop     rbx
0x18010e19f  pop     rbp
0x18010e1a0  retn
0x18010e1a1  mov     r9d, eax; char *
0x18010e1a4  lea     r8, aBaseAppcompatI_5; "base\\appcompat\\inventory\\software\\i"...
0x18010e1ab  mov     edx, 30h ; '0'; void *
0x18010e1b0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
