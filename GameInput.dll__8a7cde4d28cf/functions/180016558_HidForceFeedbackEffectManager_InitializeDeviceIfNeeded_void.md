# HidForceFeedbackEffectManager::InitializeDeviceIfNeeded(void)

- ea: `0x180016558`
- end: `0x1800169f3`
- name: `?InitializeDeviceIfNeeded@HidForceFeedbackEffectManager@@AEAAJXZ`
- size: `1179`
- prototype: `__int64 __fastcall(HidForceFeedbackEffectManager *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a0a4`
- `0x18001ad0c`
- `0x18001b204`
- `0x18001ca68`
- `0x18001d890`

## callees

- `0x180001008`
- `0x180001304`
- `0x18000c11c`
- `0x180016558`
- `0x180022f04`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!_wcslwr_s` at `0x1800167a9`
- `ntdll!_wcslwr_s` at `0x1800167a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001663f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001663f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166e7`

## pseudocode

```c
__int64 __fastcall HidForceFeedbackEffectManager::InitializeDeviceIfNeeded(
        HidForceFeedbackEffectManager *this,
        __int64 a2,
        int a3,
        int a4)
{
  const struct std::nothrow_t *v5; // rdx
  HRESULT v6; // edi
  int v7; // r8d
  int v8; // r9d
  HSTRING v10; // rcx
  PCWSTR StringRawBuffer; // rax
  const struct std::nothrow_t *v12; // rdx
  int v13; // r8d
  int v14; // r9d
  const struct std::nothrow_t *v15; // rdx
  int v16; // r8d
  int v17; // r9d
  __int16 v18; // dx
  __int64 v19; // r9
  int v20; // r8d
  int v21; // r9d
  LPVOID v22; // rdi
  LPVOID v23; // rcx
  const struct std::nothrow_t *v24; // rcx
  const struct std::nothrow_t *v25; // rdx
  const struct std::nothrow_t *v26; // rdi
  int ppv; // [rsp+20h] [rbp-49h]
  int v28; // [rsp+40h] [rbp-29h] BYREF
  int v29; // [rsp+44h] [rbp-25h] BYREF
  LPVOID v30; // [rsp+48h] [rbp-21h] BYREF
  const struct std::nothrow_t *v31; // [rsp+50h] [rbp-19h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-11h] BYREF
  _WORD *v33; // [rsp+60h] [rbp-9h]
  _WORD v34[8]; // [rsp+68h] [rbp-1h] BYREF
  const char *v35; // [rsp+78h] [rbp+Fh] BYREF
  IID rclsid; // [rsp+80h] [rbp+17h] BYREF

  if ( *((_QWORD *)this + 5) )
    return 0;
  if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v28 = *((_DWORD *)this + 8);
    v35 = "HID force feedback device initialize";
    v29 = 254;
    *(_QWORD *)&rclsid.Data1 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)byte_18005D6E5,
      a3,
      a4,
      (__int64)&rclsid,
      (__int64)&v29,
      (__int64)&v35,
      (__int64)&v28);
  }
  v30 = 0;
  rclsid.Data1 = -1604733358;
  *(_DWORD *)&rclsid.Data2 = 1255683289;
  *(_DWORD *)rclsid.Data4 = -510822739;
  *(_DWORD *)&rclsid.Data4[4] = -1379342022;
  v6 = CoCreateInstance(&rclsid, 0, 4u, &GUID_815211c2_e515_4437_a8cc_e93857df54f5, &v30);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_180069000 > 2 )
    {
      v5 = (const struct std::nothrow_t *)qword_180069018;
      if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
      {
        v29 = v6;
        v28 = 261;
        *(_QWORD *)&rclsid.Data1 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180069010,
          (unsigned int)byte_18005E4F3,
          v7,
          v8,
          (__int64)&rclsid,
          (__int64)&v28,
          (__int64)&v29);
      }
    }
LABEL_11:
    if ( v30 )
      (*(void (__fastcall **)(LPVOID, const struct std::nothrow_t *))(*(_QWORD *)v30 + 16LL))(v30, v5);
    return (unsigned int)v6;
  }
  v10 = (HSTRING)*((_QWORD *)this + 1);
  String = v34;
  v33 = v34;
  v34[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v10, 0);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
    &String,
    StringRawBuffer);
  if ( !String )
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
    {
      v29 = -2147024882;
      v28 = 269;
      *(_QWORD *)&rclsid.Data1 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned int)byte_18005DF05,
        v13,
        v14,
        (__int64)&rclsid,
        (__int64)&v28,
        (__int64)&v29);
    }
    if ( String != v34 )
      operator delete(String, v12);
    if ( v30 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    return 2147942414LL;
  }
  if ( !_wcslwr_s(String, v33 - String + 1) )
  {
    v18 = *((_WORD *)this + 9);
    v19 = *((unsigned __int16 *)this + 8);
    v31 = 0;
    LOWORD(ppv) = v18;
    v6 = (*(__int64 (__fastcall **)(LPVOID, const struct std::nothrow_t **, wchar_t *, __int64, int))(*(_QWORD *)v30 + 24LL))(
           v30,
           &v31,
           String,
           v19,
           ppv);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180069000 > 2 )
      {
        v5 = (const struct std::nothrow_t *)qword_180069018;
        if ( (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
        {
          v29 = v6;
          v28 = 277;
          *(_QWORD *)&rclsid.Data1 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            qword_180069010,
            (unsigned int)&dword_18005E214,
            v20,
            v21,
            (__int64)&rclsid,
            (__int64)&v28,
            (__int64)&v29);
        }
      }
      if ( v31 )
      {
        (*(void (__fastcall **)(const struct std::nothrow_t *, const struct std::nothrow_t *))(*(_QWORD *)v31 + 16LL))(
          v31,
          v5);
        v31 = 0;
      }
      if ( String != v34 )
        operator delete(String, v5);
      goto LABEL_11;
    }
    v22 = v30;
    v23 = (LPVOID)*((_QWORD *)this + 3);
    if ( v23 != v30 )
    {
      if ( v23 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      *((_QWORD *)this + 3) = v22;
      if ( v22 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 8LL))(v22);
    }
    v24 = v31;
    v25 = (const struct std::nothrow_t *)*((_QWORD *)this + 5);
    v26 = v31;
    if ( v25 != v31 )
    {
      if ( v25 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25 + 16LL))(*((_QWORD *)this + 5));
        v24 = v31;
      }
      *((_QWORD *)this + 5) = v26;
      if ( v26 )
      {
        (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v26 + 8LL))(v26);
        v24 = v31;
      }
    }
    if ( v24 )
    {
      (*(void (__fastcall **)(const struct std::nothrow_t *))(*(_QWORD *)v24 + 16LL))(v24);
      v31 = 0;
    }
    if ( String != v34 )
      operator delete(String, v25);
    if ( v30 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    return 0;
  }
  if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 8) != 0 && (qword_180069018 & 8) == qword_180069018 )
  {
    v29 = -2147418113;
    v28 = 270;
    *(_QWORD *)&rclsid.Data1 = "onecore\\xbox\\gameinput\\feedback\\hid\\HidForceFeedbackEffectManager.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      qword_180069018,
      (unsigned int)&byte_18005A5D7,
      v16,
      v17,
      (__int64)&rclsid,
      (__int64)&v28,
      (__int64)&v29);
  }
  if ( String != v34 )
    operator delete(String, v15);
  if ( v30 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180016558  push    rbp
0x18001655a  push    rbx
0x18001655b  push    rdi
0x18001655c  push    r15
0x18001655e  lea     rbp, [rsp-3Fh]
0x180016563  sub     rsp, 0A8h
0x18001656a  mov     rax, cs:__security_cookie
0x180016571  xor     rax, rsp
0x180016574  mov     [rbp+57h+var_30], rax
0x180016578  cmp     qword ptr [rcx+28h], 0
0x18001657d  mov     rbx, rcx
0x180016580  jnz     loc_1800169D7
0x180016586  mov     eax, cs:dword_180069000
0x18001658c  lea     r15, aOnecoreXboxGam_17; "onecore\\xbox\\gameinput\\feedback\\hid"...
0x180016593  cmp     eax, 4
0x180016596  jbe     short loc_180016601
0x180016598  mov     rcx, cs:qword_180069018
0x18001659f  mov     rax, cs:qword_180069010
0x1800165a6  test    al, 8
0x1800165a8  jz      short loc_180016601
0x1800165aa  mov     rax, rcx
0x1800165ad  and     eax, 8
0x1800165b0  cmp     rax, rcx
0x1800165b3  jnz     short loc_180016601
0x1800165b5  mov     eax, [rbx+20h]
0x1800165b8  lea     rdx, byte_18005D6E5
0x1800165bf  mov     [rbp+57h+var_80], eax
0x1800165c2  lea     rax, aHidForceFeedba_10; "HID force feedback device initialize"
0x1800165c9  mov     [rbp+57h+var_48], rax
0x1800165cd  lea     rax, [rbp+57h+var_80]
0x1800165d1  mov     [rsp+0C0h+var_88], rax
0x1800165d6  lea     rax, [rbp+57h+var_48]
0x1800165da  mov     [rsp+0C0h+var_90], rax
0x1800165df  lea     rax, [rbp+57h+var_7C]
0x1800165e3  mov     [rsp+0C0h+var_98], rax
0x1800165e8  lea     rax, [rbp+57h+rclsid]
0x1800165ec  mov     [rsp+0C0h+ppv], rax
0x1800165f1  mov     [rbp+57h+var_7C], 0FEh
0x1800165f8  mov     qword ptr [rbp+57h+rclsid.Data1], r15
0x1800165fc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016601  xor     edx, edx; pUnkOuter
0x180016603  mov     [rbp+57h+var_78], 0
0x18001660b  lea     rax, [rbp+57h+var_78]
0x18001660f  mov     [rbp+57h+rclsid.Data1], 0A059B652h
0x180016616  lea     r9, _GUID_815211c2_e515_4437_a8cc_e93857df54f5; riid
0x18001661d  mov     dword ptr [rbp+57h+rclsid.Data2], 4AD834D9h
0x180016624  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180016628  mov     dword ptr [rbp+57h+rclsid.Data4], 0E18D76ADh
0x18001662f  lea     r8d, [rdx+4]; dwClsContext
0x180016633  mov     dword ptr [rbp+57h+rclsid.Data4+4], 0ADC8E93Ah
0x18001663a  mov     [rsp+0C0h+ppv], rax; ppv
0x18001663f  call    cs:__imp_CoCreateInstance
0x180016646  nop     dword ptr [rax+rax+00h]
0x18001664b  mov     edi, eax
0x18001664d  test    eax, eax
0x18001664f  jns     short loc_1800166CB
0x180016651  mov     ecx, cs:dword_180069000
0x180016657  cmp     ecx, 2
0x18001665a  jbe     short loc_1800166AF
0x18001665c  mov     rdx, cs:qword_180069018
0x180016663  mov     rcx, cs:qword_180069010
0x18001666a  test    cl, 8
0x18001666d  jz      short loc_1800166AF
0x18001666f  mov     rax, rdx
0x180016672  and     eax, 8
0x180016675  cmp     rax, rdx
0x180016678  jnz     short loc_1800166AF
0x18001667a  lea     rax, [rbp+57h+var_7C]
0x18001667e  mov     [rbp+57h+var_7C], edi
0x180016681  mov     [rsp+0C0h+var_90], rax
0x180016686  lea     rdx, byte_18005E4F3
0x18001668d  lea     rax, [rbp+57h+var_80]
0x180016691  mov     [rbp+57h+var_80], 105h
0x180016698  mov     [rsp+0C0h+var_98], rax
0x18001669d  lea     rax, [rbp+57h+rclsid]
0x1800166a1  mov     [rsp+0C0h+ppv], rax
0x1800166a6  mov     qword ptr [rbp+57h+rclsid.Data1], r15
0x1800166aa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800166af  mov     rcx, [rbp+57h+var_78]
0x1800166b3  test    rcx, rcx
0x1800166b6  jz      short loc_1800166C4
0x1800166b8  mov     rax, [rcx]
0x1800166bb  mov     rax, [rax+10h]
0x1800166bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166c4  mov     eax, edi
0x1800166c6  jmp     loc_1800169D9
0x1800166cb  mov     rcx, [rbx+8]; string
0x1800166cf  lea     rax, [rbp+57h+var_58]
0x1800166d3  mov     [rbp+57h+String], rax
0x1800166d7  xor     edx, edx; length
0x1800166d9  lea     rax, [rbp+57h+var_58]
0x1800166dd  mov     [rbp+57h+var_60], rax
0x1800166e1  xor     eax, eax
0x1800166e3  mov     [rbp+57h+var_58], ax
0x1800166e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800166ee  nop     dword ptr [rax+rax+00h]
0x1800166f3  mov     rdx, rax
0x1800166f6  lea     rcx, [rbp+57h+String]
0x1800166fa  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800166ff  mov     rcx, [rbp+57h+String]; String
0x180016703  test    rcx, rcx
0x180016706  jnz     loc_18001679C
0x18001670c  mov     eax, cs:dword_180069000
0x180016712  mov     ebx, 8007000Eh
0x180016717  cmp     eax, 2
0x18001671a  jbe     short loc_18001676E
0x18001671c  mov     rcx, cs:qword_180069018
0x180016723  mov     rax, cs:qword_180069010
0x18001672a  test    al, 8
0x18001672c  jz      short loc_18001676E
0x18001672e  mov     rax, rcx
0x180016731  and     eax, 8
0x180016734  cmp     rax, rcx
0x180016737  jnz     short loc_18001676E
0x180016739  lea     rax, [rbp+57h+var_7C]
0x18001673d  mov     [rbp+57h+var_7C], ebx
0x180016740  mov     [rsp+0C0h+var_90], rax
0x180016745  lea     rdx, byte_18005DF05
0x18001674c  lea     rax, [rbp+57h+var_80]
0x180016750  mov     [rbp+57h+var_80], 10Dh
0x180016757  mov     [rsp+0C0h+var_98], rax
0x18001675c  lea     rax, [rbp+57h+rclsid]
0x180016760  mov     [rsp+0C0h+ppv], rax
0x180016765  mov     qword ptr [rbp+57h+rclsid.Data1], r15
0x180016769  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001676e  mov     rcx, [rbp+57h+String]; P
0x180016772  lea     rax, [rbp+57h+var_58]
0x180016776  cmp     rcx, rax
0x180016779  jz      short loc_180016780
0x18001677b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016780  mov     rcx, [rbp+57h+var_78]
0x180016784  test    rcx, rcx
0x180016787  jz      short loc_180016795
0x180016789  mov     rdx, [rcx]
0x18001678c  mov     rax, [rdx+10h]
0x180016790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016795  mov     eax, ebx
0x180016797  jmp     loc_1800169D9
0x18001679c  mov     rdx, [rbp+57h+var_60]
0x1800167a0  sub     rdx, rcx
0x1800167a3  sar     rdx, 1
0x1800167a6  inc     rdx; SizeInWords
0x1800167a9  call    cs:__imp__wcslwr_s
0x1800167b0  nop     dword ptr [rax+rax+00h]
0x1800167b5  test    eax, eax
0x1800167b7  jz      loc_18001684F
0x1800167bd  mov     eax, cs:dword_180069000
0x1800167c3  cmp     eax, 2
0x1800167c6  jbe     short loc_18001681E
0x1800167c8  mov     rcx, cs:qword_180069018
0x1800167cf  mov     rax, cs:qword_180069010
0x1800167d6  test    al, 8
0x1800167d8  jz      short loc_18001681E
0x1800167da  mov     rax, rcx
0x1800167dd  and     eax, 8
0x1800167e0  cmp     rax, rcx
0x1800167e3  jnz     short loc_18001681E
0x1800167e5  lea     rax, [rbp+57h+var_7C]
0x1800167e9  mov     [rbp+57h+var_7C], 8000FFFFh
0x1800167f0  mov     [rsp+0C0h+var_90], rax
0x1800167f5  lea     rdx, byte_18005A5D7
0x1800167fc  lea     rax, [rbp+57h+var_80]
0x180016800  mov     [rbp+57h+var_80], 10Eh
0x180016807  mov     [rsp+0C0h+var_98], rax
0x18001680c  lea     rax, [rbp+57h+rclsid]
0x180016810  mov     [rsp+0C0h+ppv], rax
0x180016815  mov     qword ptr [rbp+57h+rclsid.Data1], r15
0x180016819  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001681e  mov     rcx, [rbp+57h+String]; P
0x180016822  lea     rax, [rbp+57h+var_58]
0x180016826  cmp     rcx, rax
0x180016829  jz      short loc_180016830
0x18001682b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016830  mov     rcx, [rbp+57h+var_78]
0x180016834  test    rcx, rcx
0x180016837  jz      short loc_180016845
0x180016839  mov     rax, [rcx]
0x18001683c  mov     rax, [rax+10h]
0x180016840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016845  mov     eax, 8000FFFFh
0x18001684a  jmp     loc_1800169D9
0x18001684f  movzx   edx, word ptr [rbx+12h]
0x180016853  mov     rcx, [rbp+57h+var_78]
0x180016857  movzx   r9d, word ptr [rbx+10h]
0x18001685c  mov     r8, [rbp+57h+String]
0x180016860  mov     [rbp+57h+var_70], 0
0x180016868  mov     rax, [rcx]
0x18001686b  mov     word ptr [rsp+0C0h+ppv], dx
0x180016870  lea     rdx, [rbp+57h+var_70]
0x180016874  mov     rax, [rax+18h]
0x180016878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687d  mov     edi, eax
0x18001687f  test    eax, eax
0x180016881  jns     loc_18001691D
0x180016887  mov     ecx, cs:dword_180069000
0x18001688d  cmp     ecx, 2
0x180016890  jbe     short loc_1800168E5
0x180016892  mov     rdx, cs:qword_180069018
0x180016899  mov     rcx, cs:qword_180069010
0x1800168a0  test    cl, 8
0x1800168a3  jz      short loc_1800168E5
0x1800168a5  mov     rax, rdx
0x1800168a8  and     eax, 8
0x1800168ab  cmp     rax, rdx
0x1800168ae  jnz     short loc_1800168E5
0x1800168b0  lea     rax, [rbp+57h+var_7C]
0x1800168b4  mov     [rbp+57h+var_7C], edi
0x1800168b7  mov     [rsp+0C0h+var_90], rax
0x1800168bc  lea     rdx, dword_18005E214
0x1800168c3  lea     rax, [rbp+57h+var_80]
0x1800168c7  mov     [rbp+57h+var_80], 115h
0x1800168ce  mov     [rsp+0C0h+var_98], rax
0x1800168d3  lea     rax, [rbp+57h+rclsid]
0x1800168d7  mov     [rsp+0C0h+ppv], rax
0x1800168dc  mov     qword ptr [rbp+57h+rclsid.Data1], r15
0x1800168e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800168e5  mov     rcx, [rbp+57h+var_70]
0x1800168e9  test    rcx, rcx
0x1800168ec  jz      short loc_180016902
0x1800168ee  mov     rax, [rcx]
0x1800168f1  mov     rax, [rax+10h]
0x1800168f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168fa  mov     [rbp+57h+var_70], 0
0x180016902  mov     rcx, [rbp+57h+String]; P
0x180016906  lea     rax, [rbp+57h+var_58]
0x18001690a  cmp     rcx, rax
0x18001690d  jz      loc_1800166AF
0x180016913  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180016918  jmp     loc_1800166AF
0x18001691d  mov     rdi, [rbp+57h+var_78]
0x180016921  mov     rcx, [rbx+18h]
0x180016925  cmp     rcx, rdi
0x180016928  jz      short loc_180016953
0x18001692a  test    rcx, rcx
0x18001692d  jz      short loc_18001693B
0x18001692f  mov     rax, [rcx]
0x180016932  mov     rax, [rax+10h]
0x180016936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001693b  mov     [rbx+18h], rdi
0x18001693f  test    rdi, rdi
0x180016942  jz      short loc_180016953
0x180016944  mov     rax, [rdi]
0x180016947  mov     rcx, rdi
0x18001694a  mov     rax, [rax+8]
0x18001694e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016953  mov     rcx, [rbp+57h+var_70]
0x180016957  mov     rdx, [rbx+28h]
0x18001695b  mov     rdi, rcx
0x18001695e  cmp     rdx, rcx
0x180016961  jz      short loc_180016997
0x180016963  test    rdx, rdx
0x180016966  jz      short loc_18001697B
0x180016968  mov     rax, [rdx]
0x18001696b  mov     rcx, rdx
0x18001696e  mov     rax, [rax+10h]
0x180016972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016977  mov     rcx, [rbp+57h+var_70]
0x18001697b  mov     [rbx+28h], rdi
0x18001697f  test    rdi, rdi
0x180016982  jz      short loc_180016997
0x180016984  mov     rax, [rdi]
0x180016987  mov     rcx, rdi
0x18001698a  mov     rax, [rax+8]
0x18001698e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016993  mov     rcx, [rbp+57h+var_70]
0x180016997  test    rcx, rcx
0x18001699a  jz      short loc_1800169B0
0x18001699c  mov     rax, [rcx]
0x18001699f  mov     rax, [rax+10h]
0x1800169a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169a8  mov     [rbp+57h+var_70], 0
0x1800169b0  mov     rcx, [rbp+57h+String]; P
0x1800169b4  lea     rax, [rbp+57h+var_58]
0x1800169b8  cmp     rcx, rax
0x1800169bb  jz      short loc_1800169C2
0x1800169bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800169c2  mov     rcx, [rbp+57h+var_78]
0x1800169c6  test    rcx, rcx
0x1800169c9  jz      short loc_1800169D7
0x1800169cb  mov     rax, [rcx]
0x1800169ce  mov     rax, [rax+10h]
0x1800169d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169d7  xor     eax, eax
0x1800169d9  mov     rcx, [rbp+57h+var_30]
0x1800169dd  xor     rcx, rsp; StackCookie
0x1800169e0  call    __security_check_cookie
0x1800169e5  add     rsp, 0A8h
0x1800169ec  pop     r15
0x1800169ee  pop     rdi
0x1800169ef  pop     rbx
0x1800169f0  pop     rbp
0x1800169f1  retn
```
