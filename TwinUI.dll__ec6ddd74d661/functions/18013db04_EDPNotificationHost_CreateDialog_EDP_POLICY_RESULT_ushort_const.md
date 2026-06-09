# EDPNotificationHost::_CreateDialog(EDP_POLICY_RESULT,ushort const *)

- ea: `0x18013db04`
- end: `0x18013e1f3`
- name: `?_CreateDialog@EDPNotificationHost@@AEAAJW4EDP_POLICY_RESULT@@PEBG@Z`
- size: `1775`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1802e0bdc`

## callees

- `0x1800378dc`
- `0x180041f54`
- `0x18013db04`
- `0x18013e1fc`
- `0x18015f0a0`
- `0x1802dfe74`
- `0x1803bb010`

## import_xrefs

- `DUI70!?AddRef@Element@DirectUI@@QEAAKXZ` at `0x18013dce4`
- `DUI70!?AddRef@Element@DirectUI@@QEAAKXZ` at `0x18013dce4`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013dda7`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013de2d`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013dda7`
- `DUI70!?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013de2d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013dd82`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013de07`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013dd82`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18013de07`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18013dcc9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18013dd1e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18013dcc9`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18013dd1e`
- `DUI70!StrToID` at `0x18013dcb7`
- `DUI70!StrToID` at `0x18013dd0c`
- `DUI70!StrToID` at `0x18013dcb7`
- `DUI70!StrToID` at `0x18013dd0c`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18013dc79`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18013dc79`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18013dc1e`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x18013dc1e`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18013dd52`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x18013dd52`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18013dbf6`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x18013dbf6`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013dee8`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013dfe0`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e091`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e0e2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e1c0`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013dee8`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013dfe0`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e091`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e0e2`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18013e1c0`

## string_xrefs

- `0x18013dd05`: `LearnMoreLink`

## pseudocode

```c
__int64 __fastcall EDPNotificationHost::_CreateDialog(unsigned __int64 a1, int a2, const unsigned __int16 *a3)
{
  char v6; // r15
  __int64 v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  DirectUI::Element *v13; // rbx
  unsigned __int16 v14; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v16; // rdi
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // r9
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned __int64 v30; // rbx
  int v31; // edi
  unsigned __int64 v32; // rdi
  __int64 v33; // rcx
  int v34; // r14d
  __int64 v35; // rdx
  int v36; // eax
  unsigned int v37; // esi
  __int64 v38; // rdx
  int v40; // [rsp+20h] [rbp-60h]
  int v41; // [rsp+20h] [rbp-60h]
  struct DirectUI::DUIXmlParser *v42; // [rsp+30h] [rbp-50h] BYREF
  DirectUI::Element *v43; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v44; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v45; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v46[2]; // [rsp+50h] [rbp-30h] BYREF
  const unsigned __int16 *v47[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v49; // [rsp+C8h] [rbp+48h] BYREF
  struct DirectUI::Element *v50; // [rsp+D8h] [rbp+58h] BYREF

  if ( (unsigned int)(a2 - 3) <= 1 )
  {
    v6 = 1;
    v7 = 12401;
    if ( a2 != 3 )
      v7 = 12403;
  }
  else
  {
    v6 = 0;
    v7 = 12411;
  }
  memset(v47, 0, 24);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
         v47,
         &_ImageBase,
         v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 144;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v8,
      v40);
    goto LABEL_80;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(**(_QWORD **)(a1 + 152) + 32LL))(
         *(_QWORD *)(a1 + 152),
         v47[0]);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 146;
    goto LABEL_9;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**(_QWORD **)(a1 + 152) + 256LL))(
         *(_QWORD *)(a1 + 152),
         v47[0],
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 147;
    goto LABEL_9;
  }
  v42 = 0;
  v8 = DirectUI::DUIXmlParser::Create(&v42, 0, 0, 0, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 150;
    goto LABEL_9;
  }
  v11 = DirectUI::DUIXmlParser::SetXMLFromResource(v42, 0x308Fu, (HINSTANCE)&_ImageBase, (HINSTANCE)&_ImageBase);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v11,
      v40);
LABEL_79:
    DirectUI::DUIXmlParser::Destroy(v42);
    goto LABEL_80;
  }
  v50 = 0;
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
  v12 = DirectUI::DUIXmlParser::CreateElement(v42, L"edpmain", 0, 0, 0, &v50);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v12,
      v41);
LABEL_78:
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    goto LABEL_79;
  }
  v13 = v50;
  v43 = 0;
  v14 = StrToID(L"ModalElement");
  Descendent = DirectUI::Element::FindDescendent(v13, v14);
  v16 = Descendent;
  if ( !Descendent )
  {
    v20 = 162;
    goto LABEL_76;
  }
  DirectUI::Element::AddRef(Descendent);
  v44 = 0;
  v43 = v16;
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v44);
  v17 = v50;
  v18 = StrToID(L"LearnMoreLink");
  v19 = DirectUI::Element::FindDescendent(v17, v18);
  if ( !v19 )
  {
    v20 = 166;
LABEL_76:
    v9 = -2147467259;
    v22 = 2147500037LL;
    goto LABEL_77;
  }
  v21 = DirectUI::Element::AddListener(
          v19,
          (struct DirectUI::IElementListener *)((a1 + 136) & ((unsigned __int128)-(__int128)a1 >> 64)));
  v9 = v21;
  if ( v21 < 0 )
  {
    v22 = (unsigned int)v21;
    v20 = 167;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)v22,
      v41);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    goto LABEL_78;
  }
  if ( a3 && *a3 )
  {
    v23 = DirectUI::Element::SetContentString(v16, a3);
    v9 = v23;
    if ( v23 < 0 )
    {
      v22 = (unsigned int)v23;
      v20 = 178;
      goto LABEL_77;
    }
    v24 = DirectUI::Element::SetAccValue(v16, a3);
    v9 = v24;
    if ( v24 < 0 )
    {
      v22 = (unsigned int)v24;
      v20 = 179;
      goto LABEL_77;
    }
  }
  else
  {
    v25 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
            v47,
            &_ImageBase,
            v6 != 0 ? 12402 : 12412);
    v9 = v25;
    if ( v25 < 0 )
    {
      v22 = (unsigned int)v25;
      v20 = 172;
      goto LABEL_77;
    }
    v26 = DirectUI::Element::SetContentString(v16, v47[0]);
    v9 = v26;
    if ( v26 < 0 )
    {
      v22 = (unsigned int)v26;
      v20 = 173;
      goto LABEL_77;
    }
    v27 = DirectUI::Element::SetAccValue(v16, v47[0]);
    v9 = v27;
    if ( v27 < 0 )
    {
      v22 = (unsigned int)v27;
      v20 = 174;
      goto LABEL_77;
    }
  }
  v28 = (*(__int64 (__fastcall **)(_QWORD, struct DirectUI::Element *))(**(_QWORD **)(a1 + 152) + 352LL))(
          *(_QWORD *)(a1 + 152),
          v50);
  v9 = v28;
  if ( v28 < 0 )
  {
    v22 = (unsigned int)v28;
    v20 = 182;
    goto LABEL_77;
  }
  if ( v6 )
    v29 = (a2 != 3) + 12423;
  else
    v29 = 12422;
  v49 = v29;
  v44 = a1;
  Microsoft::WRL::Details::Make<EDPPopupCommand,unsigned long const &,EDPNotificationHost *>(&v45, &v49, &v44);
  v30 = v45;
  if ( !v45 )
  {
    v31 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)0x8007000ELL,
      v41);
LABEL_42:
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v31;
    goto LABEL_80;
  }
  if ( !v6 )
  {
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**(_QWORD **)(a1 + 152) + 64LL))(
            *(_QWORD *)(a1 + 152),
            1,
            &v45);
    if ( v31 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 152) + 88LL))(*(_QWORD *)(a1 + 152), 0);
      if ( v31 >= 0 )
      {
        v31 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 152) + 120LL))(*(_QWORD *)(a1 + 152), 0);
        if ( v31 >= 0 )
          goto LABEL_64;
        v38 = 213;
      }
      else
      {
        v38 = 212;
      }
    }
    else
    {
      v38 = 209;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v38,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v31,
      v41);
    if ( !v30 )
      goto LABEL_42;
    goto LABEL_46;
  }
  v45 = a1;
  v49 = 12421;
  Microsoft::WRL::Details::Make<EDPPopupCommand,unsigned long const &,EDPNotificationHost *>(&v44, &v49, &v45);
  v32 = v44;
  if ( !v44 )
  {
    v31 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)0x8007000ELL,
      v41);
    if ( !v30 )
      goto LABEL_42;
LABEL_46:
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    goto LABEL_42;
  }
  v33 = *(_QWORD *)(a1 + 152);
  v46[0] = v44;
  v46[1] = v30;
  v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v33 + 64LL))(v33, 2, v46);
  if ( v34 < 0 )
  {
    v35 = 200;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v34,
      v41);
    if ( v32 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v34;
    goto LABEL_80;
  }
  v34 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 152) + 88LL))(*(_QWORD *)(a1 + 152), 1);
  if ( v34 < 0 )
  {
    v35 = 203;
    goto LABEL_49;
  }
  v36 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 152) + 120LL))(*(_QWORD *)(a1 + 152), 1);
  v37 = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"shell\\twinui\\edpnotificationhost\\lib\\edpnotificationhost.cpp",
      (const char *)(unsigned int)v36,
      v41);
    if ( v32 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v30 )
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
    DirectUI::DUIXmlParser::Destroy(v42);
    v9 = v37;
    goto LABEL_80;
  }
  if ( v32 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_64:
  if ( v30 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v30 + 16LL))(v30);
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(&v50);
  DirectUI::DUIXmlParser::Destroy(v42);
  v9 = 0;
LABEL_80:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
  return v9;
}

```

## disassembly

```asm
0x18013db04  mov     [rsp-38h+arg_0], rbx
0x18013db09  push    rbp
0x18013db0a  push    rsi
0x18013db0b  push    rdi
0x18013db0c  push    r12
0x18013db0e  push    r13
0x18013db10  push    r14
0x18013db12  push    r15
0x18013db14  mov     rbp, rsp
0x18013db17  sub     rsp, 80h
0x18013db1e  lea     eax, [rdx-3]
0x18013db21  xor     r12d, r12d
0x18013db24  mov     r14, r8
0x18013db27  mov     r13d, edx
0x18013db2a  mov     rsi, rcx
0x18013db2d  cmp     eax, 1
0x18013db30  jbe     short loc_18013DB3D
0x18013db32  mov     r15b, r12b
0x18013db35  mov     r8d, 307Bh
0x18013db3b  jmp     short loc_18013DB51
0x18013db3d  mov     eax, 3073h
0x18013db42  cmp     r13d, 3
0x18013db46  mov     r15b, 1
0x18013db49  lea     r8d, [rax-2]
0x18013db4d  cmovnz  r8d, eax
0x18013db51  lea     rdi, __ImageBase
0x18013db58  mov     [rbp+var_20], r12
0x18013db5c  mov     rdx, rdi
0x18013db5f  mov     [rbp+var_18], r12
0x18013db63  lea     rcx, [rbp+var_20]
0x18013db67  mov     [rbp+var_10], r12
0x18013db6b  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18013db70  mov     ebx, eax
0x18013db72  test    eax, eax
0x18013db74  jns     short loc_18013DB7D
0x18013db76  mov     edx, 90h
0x18013db7b  jmp     short loc_18013DB9F
0x18013db7d  mov     rcx, [rsi+98h]
0x18013db84  mov     rdx, [rbp+var_20]
0x18013db88  mov     rax, [rcx]
0x18013db8b  mov     rax, [rax+20h]
0x18013db8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013db94  mov     ebx, eax
0x18013db96  test    eax, eax
0x18013db98  jns     short loc_18013DBB7
0x18013db9a  mov     edx, 92h; void *
0x18013db9f  mov     rcx, [rbp+38h]; this
0x18013dba3  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013dbaa  mov     r9d, eax; char *
0x18013dbad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dbb2  jmp     loc_18013E1CC
0x18013dbb7  mov     rcx, [rsi+98h]
0x18013dbbe  xor     r8d, r8d
0x18013dbc1  mov     rdx, [rbp+var_20]
0x18013dbc5  mov     rax, [rcx]
0x18013dbc8  mov     rax, [rax+100h]
0x18013dbcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013dbd4  mov     ebx, eax
0x18013dbd6  test    eax, eax
0x18013dbd8  jns     short loc_18013DBE1
0x18013dbda  mov     edx, 93h
0x18013dbdf  jmp     short loc_18013DB9F
0x18013dbe1  xor     r9d, r9d
0x18013dbe4  mov     [rbp+var_50], r12
0x18013dbe8  xor     r8d, r8d
0x18013dbeb  mov     qword ptr [rsp+80h+var_60], r12; int
0x18013dbf0  xor     edx, edx
0x18013dbf2  lea     rcx, [rbp+var_50]
0x18013dbf6  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x18013dbfd  nop     dword ptr [rax+rax+00h]
0x18013dc02  mov     ebx, eax
0x18013dc04  test    eax, eax
0x18013dc06  jns     short loc_18013DC0F
0x18013dc08  mov     edx, 96h
0x18013dc0d  jmp     short loc_18013DB9F
0x18013dc0f  mov     rcx, [rbp+var_50]
0x18013dc13  mov     r9, rdi
0x18013dc16  mov     r8, rdi
0x18013dc19  mov     edx, 308Fh
0x18013dc1e  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x18013dc25  nop     dword ptr [rax+rax+00h]
0x18013dc2a  mov     ebx, eax
0x18013dc2c  test    eax, eax
0x18013dc2e  jns     short loc_18013DC4D
0x18013dc30  mov     rcx, [rbp+38h]; this
0x18013dc34  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013dc3b  mov     r9d, eax; char *
0x18013dc3e  mov     edx, 9Bh; void *
0x18013dc43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dc48  jmp     loc_18013E1BC
0x18013dc4d  lea     rcx, [rbp+arg_18]
0x18013dc51  mov     [rbp+arg_18], r12
0x18013dc55  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x18013dc5a  mov     rcx, [rbp+var_50]
0x18013dc5e  lea     rax, [rbp+arg_18]
0x18013dc62  mov     [rsp+80h+var_58], rax
0x18013dc67  lea     rdx, aEdpmain; "edpmain"
0x18013dc6e  xor     r9d, r9d
0x18013dc71  mov     qword ptr [rsp+80h+var_60], r12; int
0x18013dc76  xor     r8d, r8d
0x18013dc79  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18013dc80  nop     dword ptr [rax+rax+00h]
0x18013dc85  mov     ebx, eax
0x18013dc87  test    eax, eax
0x18013dc89  jns     short loc_18013DCA8
0x18013dc8b  mov     rcx, [rbp+38h]; this
0x18013dc8f  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013dc96  mov     r9d, eax; char *
0x18013dc99  mov     edx, 9Eh; void *
0x18013dc9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dca3  jmp     loc_18013E1B3
0x18013dca8  mov     rbx, [rbp+arg_18]
0x18013dcac  lea     rcx, aModalelement; "ModalElement"
0x18013dcb3  mov     [rbp+var_48], r12
0x18013dcb7  call    cs:__imp_StrToID
0x18013dcbe  nop     dword ptr [rax+rax+00h]
0x18013dcc3  movzx   edx, ax
0x18013dcc6  mov     rcx, rbx
0x18013dcc9  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18013dcd0  nop     dword ptr [rax+rax+00h]
0x18013dcd5  mov     rdi, rax
0x18013dcd8  test    rax, rax
0x18013dcdb  jz      loc_18013E18D
0x18013dce1  mov     rcx, rax
0x18013dce4  call    cs:__imp_?AddRef@Element@DirectUI@@QEAAKXZ; DirectUI::Element::AddRef(void)
0x18013dceb  nop     dword ptr [rax+rax+00h]
0x18013dcf0  lea     rcx, [rbp+var_40]
0x18013dcf4  mov     [rbp+var_40], r12
0x18013dcf8  mov     [rbp+var_48], rdi
0x18013dcfc  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x18013dd01  mov     rbx, [rbp+arg_18]
0x18013dd05  lea     rcx, aLearnmorelink; "LearnMoreLink"
0x18013dd0c  call    cs:__imp_StrToID
0x18013dd13  nop     dword ptr [rax+rax+00h]
0x18013dd18  movzx   edx, ax
0x18013dd1b  mov     rcx, rbx
0x18013dd1e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18013dd25  nop     dword ptr [rax+rax+00h]
0x18013dd2a  mov     r8, rax
0x18013dd2d  test    rax, rax
0x18013dd30  jnz     short loc_18013DD3C
0x18013dd32  mov     edx, 0A6h
0x18013dd37  jmp     loc_18013E192
0x18013dd3c  lea     rcx, [rsi+88h]
0x18013dd43  mov     rax, rsi
0x18013dd46  neg     rax
0x18013dd49  sbb     rdx, rdx
0x18013dd4c  and     rdx, rcx
0x18013dd4f  mov     rcx, r8
0x18013dd52  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x18013dd59  nop     dword ptr [rax+rax+00h]
0x18013dd5e  mov     ebx, eax
0x18013dd60  test    eax, eax
0x18013dd62  jns     short loc_18013DD71
0x18013dd64  mov     r9d, eax
0x18013dd67  mov     edx, 0A7h
0x18013dd6c  jmp     loc_18013E19A
0x18013dd71  test    r14, r14
0x18013dd74  jz      short loc_18013DDCA
0x18013dd76  cmp     [r14], r12w
0x18013dd7a  jz      short loc_18013DDCA
0x18013dd7c  mov     rdx, r14
0x18013dd7f  mov     rcx, rdi
0x18013dd82  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18013dd89  nop     dword ptr [rax+rax+00h]
0x18013dd8e  mov     ebx, eax
0x18013dd90  test    eax, eax
0x18013dd92  jns     short loc_18013DDA1
0x18013dd94  mov     r9d, eax
0x18013dd97  mov     edx, 0B2h
0x18013dd9c  jmp     loc_18013E19A
0x18013dda1  mov     rdx, r14
0x18013dda4  mov     rcx, rdi
0x18013dda7  call    cs:__imp_?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccValue(ushort const *)
0x18013ddae  nop     dword ptr [rax+rax+00h]
0x18013ddb3  mov     ebx, eax
0x18013ddb5  test    eax, eax
0x18013ddb7  jns     loc_18013DE4C
0x18013ddbd  mov     r9d, eax
0x18013ddc0  mov     edx, 0B3h
0x18013ddc5  jmp     loc_18013E19A
0x18013ddca  mov     al, r15b
0x18013ddcd  lea     rdx, __ImageBase
0x18013ddd4  neg     al
0x18013ddd6  lea     rcx, [rbp+var_20]
0x18013ddda  sbb     r8d, r8d
0x18013dddd  and     r8d, 0FFFFFFF6h
0x18013dde1  add     r8d, 307Ch
0x18013dde8  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x18013dded  mov     ebx, eax
0x18013ddef  test    eax, eax
0x18013ddf1  jns     short loc_18013DE00
0x18013ddf3  mov     r9d, eax
0x18013ddf6  mov     edx, 0ACh
0x18013ddfb  jmp     loc_18013E19A
0x18013de00  mov     rdx, [rbp+var_20]
0x18013de04  mov     rcx, rdi
0x18013de07  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x18013de0e  nop     dword ptr [rax+rax+00h]
0x18013de13  mov     ebx, eax
0x18013de15  test    eax, eax
0x18013de17  jns     short loc_18013DE26
0x18013de19  mov     r9d, eax
0x18013de1c  mov     edx, 0ADh
0x18013de21  jmp     loc_18013E19A
0x18013de26  mov     rdx, [rbp+var_20]
0x18013de2a  mov     rcx, rdi
0x18013de2d  call    cs:__imp_?SetAccValue@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccValue(ushort const *)
0x18013de34  nop     dword ptr [rax+rax+00h]
0x18013de39  mov     ebx, eax
0x18013de3b  test    eax, eax
0x18013de3d  jns     short loc_18013DE4C
0x18013de3f  mov     r9d, eax
0x18013de42  mov     edx, 0AEh
0x18013de47  jmp     loc_18013E19A
0x18013de4c  mov     rcx, [rsi+98h]
0x18013de53  mov     rdx, [rbp+arg_18]
0x18013de57  mov     rax, [rcx]
0x18013de5a  mov     rax, [rax+160h]
0x18013de61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013de66  mov     ebx, eax
0x18013de68  test    eax, eax
0x18013de6a  jns     short loc_18013DE79
0x18013de6c  mov     r9d, eax
0x18013de6f  mov     edx, 0B6h
0x18013de74  jmp     loc_18013E19A
0x18013de79  test    r15b, r15b
0x18013de7c  jz      short loc_18013DE8F
0x18013de7e  cmp     r13d, 3
0x18013de82  mov     eax, r12d
0x18013de85  setnz   al
0x18013de88  add     eax, 3087h
0x18013de8d  jmp     short loc_18013DE94
0x18013de8f  mov     eax, 3086h
0x18013de94  lea     r8, [rbp+var_40]
0x18013de98  mov     [rbp+arg_8], eax
0x18013de9b  lea     rdx, [rbp+arg_8]
0x18013de9f  mov     [rbp+var_40], rsi
0x18013dea3  lea     rcx, [rbp+var_38]
0x18013dea7  call    ??$Make@VEDPPopupCommand@@AEBKPEAVEDPNotificationHost@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEDPPopupCommand@@@12@AEBK$$QEAPEAVEDPNotificationHost@@@Z; Microsoft::WRL::Details::Make<EDPPopupCommand,ulong const &,EDPNotificationHost *>(ulong const &,EDPNotificationHost * &&)
0x18013deac  mov     rbx, [rbp+var_38]
0x18013deb0  test    rbx, rbx
0x18013deb3  jnz     short loc_18013DEFB
0x18013deb5  mov     rcx, [rbp+38h]; this
0x18013deb9  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013dec0  mov     edi, 8007000Eh
0x18013dec5  mov     edx, 0BFh; void *
0x18013deca  mov     r9d, edi; char *
0x18013decd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ded2  lea     rcx, [rbp+var_48]
0x18013ded6  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x18013dedb  lea     rcx, [rbp+arg_18]
0x18013dedf  call    ?InternalRelease@?$ComPtr@VElement@DirectUI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DirectUI::Element>::InternalRelease(void)
0x18013dee4  mov     rcx, [rbp+var_50]
0x18013dee8  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x18013deef  nop     dword ptr [rax+rax+00h]
0x18013def4  mov     ebx, edi
0x18013def6  jmp     loc_18013E1CC
0x18013defb  lea     r8, [rbp+var_38]
0x18013deff  test    r15b, r15b
0x18013df02  jz      loc_18013E0F6
0x18013df08  lea     rdx, [rbp+arg_8]
0x18013df0c  mov     [rbp+var_38], rsi
0x18013df10  lea     rcx, [rbp+var_40]
0x18013df14  mov     [rbp+arg_8], 3085h
0x18013df1b  call    ??$Make@VEDPPopupCommand@@AEBKPEAVEDPNotificationHost@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEDPPopupCommand@@@12@AEBK$$QEAPEAVEDPNotificationHost@@@Z; Microsoft::WRL::Details::Make<EDPPopupCommand,ulong const &,EDPNotificationHost *>(ulong const &,EDPNotificationHost * &&)
0x18013df20  mov     rdi, [rbp+var_40]
0x18013df24  test    rdi, rdi
0x18013df27  jnz     short loc_18013DF5F
0x18013df29  mov     rcx, [rbp+38h]; this
0x18013df2d  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013df34  mov     edi, 8007000Eh
0x18013df39  mov     edx, 0C5h; void *
0x18013df3e  mov     r9d, edi; char *
0x18013df41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013df46  test    rbx, rbx
0x18013df49  jz      short loc_18013DED2
0x18013df4b  mov     rax, [rbx]
0x18013df4e  mov     rax, [rax+10h]
0x18013df52  mov     rcx, rbx
0x18013df55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013df5a  jmp     loc_18013DED2
0x18013df5f  mov     rcx, [rsi+98h]
0x18013df66  lea     r8, [rbp+var_30]
0x18013df6a  mov     [rbp+var_30], rdi
0x18013df6e  mov     edx, 2
0x18013df73  mov     [rbp+var_28], rbx
0x18013df77  mov     rax, [rcx]
0x18013df7a  mov     rax, [rax+40h]
0x18013df7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013df83  mov     r14d, eax
0x18013df86  test    eax, eax
0x18013df88  jns     short loc_18013DFF4
0x18013df8a  mov     edx, 0C8h; void *
0x18013df8f  mov     rcx, [rbp+38h]; this
0x18013df93  lea     r8, aShellTwinuiEdp; "shell\\twinui\\edpnotificationhost\\lib"...
0x18013df9a  mov     r9d, r14d; char *
0x18013df9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dfa2  test    rdi, rdi
0x18013dfa5  jz      short loc_18013DFB6
  ... truncated ...
```
