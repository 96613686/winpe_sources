# ReconfigServiceTitleIfNeeded

- ea: `0x140089c78`
- end: `0x14008a040`
- name: `ReconfigServiceTitleIfNeeded`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140088790`

## callees

- `0x1400121a8`
- `0x14001263c`
- `0x140014b10`
- `0x140015c98`
- `0x140015cb8`
- `0x140016064`
- `0x1400160cc`
- `0x14003a130`
- `0x14003a5c0`
- `0x140049330`
- `0x14007d1e0`
- `0x14007d210`
- `0x140085d94`
- `0x140088850`
- `0x140089c78`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x140089d57`
- `ADVAPI32!CloseServiceHandle` at `0x140089dbd`
- `ADVAPI32!CloseServiceHandle` at `0x140089ff0`
- `ADVAPI32!CloseServiceHandle` at `0x140089fff`
- `ADVAPI32!CloseServiceHandle` at `0x140089d57`
- `ADVAPI32!CloseServiceHandle` at `0x140089dbd`
- `ADVAPI32!CloseServiceHandle` at `0x140089ff0`
- `ADVAPI32!CloseServiceHandle` at `0x140089fff`
- `ADVAPI32!RegCloseKey` at `0x140089edb`
- `ADVAPI32!RegCloseKey` at `0x140089edb`

## string_xrefs

- `0x140089dc9`: `@%ls\MpAsDesc.dll,-244`
- `0x140089f18`: `@%ls\MpAsDesc.dll,-245`

## pseudocode

```c
__int64 ReconfigServiceTitleIfNeeded()
{
  int ServiceProcessDirectory; // eax
  const struct std::nothrow_t *v1; // rdx
  unsigned int v2; // ebx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  wchar_t *v7; // rdi
  char v8; // bl
  void *v9; // r9
  const struct std::nothrow_t *v10; // rdx
  int v11; // eax
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  wchar_t *v14; // rbx
  unsigned int v15; // r12d
  int v16; // eax
  const wchar_t *v17; // [rsp+28h] [rbp-29h]
  unsigned int v18; // [rsp+28h] [rbp-29h]
  unsigned int v19; // [rsp+28h] [rbp-29h]
  unsigned int *v20; // [rsp+60h] [rbp+Fh]
  wchar_t *v21; // [rsp+68h] [rbp+17h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp+1Fh] BYREF
  wchar_t *String2; // [rsp+78h] [rbp+27h] BYREF
  SC_HANDLE hService; // [rsp+80h] [rbp+2Fh] BYREF
  SC_HANDLE hSCObject; // [rsp+88h] [rbp+37h] BYREF

  v21 = 0;
  ServiceProcessDirectory = GetServiceProcessDirectory(&v21);
  v2 = ServiceProcessDirectory;
  if ( ServiceProcessDirectory < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        28,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)ServiceProcessDirectory);
LABEL_5:
    if ( v21 )
      operator delete(v21, v1);
    return v2;
  }
  hSCObject = 0;
  v4 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, v17);
  v2 = v4;
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        29,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v4);
LABEL_12:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    goto LABEL_5;
  }
  hService = 0;
  v5 = CommonUtil::HrOpenService(
         (CommonUtil *)&hService,
         (struct SC_HANDLE__ **)hSCObject,
         (struct SC_HANDLE__ *)L"MDCoreSvc",
         (const wchar_t *)0x13,
         v18);
  v2 = v5;
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        30,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v5);
    if ( hService )
      CloseServiceHandle(hService);
    goto LABEL_12;
  }
  String2 = 0;
  v6 = CommonUtil::NewSprintfW((CommonUtil *)&String2, (wchar_t **)L"@%ls\\MpAsDesc.dll,-244", v21);
  v7 = String2;
  if ( v6 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        33,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v6);
    goto LABEL_40;
  }
  String2 = 0;
  v8 = 1;
  if ( CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&String2,
         (HKEY *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_140194C20,
         (const wchar_t *)1,
         v19) >= 0 )
  {
    String1 = 0;
    if ( (int)CommonUtil::UtilRegGetValueString(String2, L"Description", &String1, 0, 0) < 0 )
      goto LABEL_28;
    if ( String1 )
    {
      if ( !wcsicmp(String1, v7) )
      {
        v8 = 0;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids);
      }
LABEL_28:
      if ( String1 )
        operator delete(String1, v10);
      if ( !v8 )
        goto LABEL_35;
    }
  }
  String1 = v7;
  v11 = CommonUtil::HrChangeServiceConfig2W((CommonUtil *)hService, (struct SC_HANDLE__ *)1, (unsigned int)&String1, v9);
  if ( v11 < 0
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      32,
      (unsigned int)&WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
      (_DWORD)v7,
      v11);
  }
LABEL_35:
  if ( String2 )
    RegCloseKey((HKEY)String2);
LABEL_40:
  String2 = 0;
  v12 = CommonUtil::NewSprintfW((CommonUtil *)&String2, (wchar_t **)L"@%ls\\MpAsDesc.dll,-245", v21);
  v14 = String2;
  v15 = v12;
  if ( v12 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        35,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v12);
  }
  else
  {
    v16 = CommonUtil::HrChangeServiceConfig(
            hService,
            (struct SC_HANDLE__ *)0xFFFFFFFFLL,
            -1,
            -1,
            0,
            0,
            0,
            0,
            0,
            String2,
            0,
            v20);
    v15 = v16;
    if ( v16 < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        34,
        (unsigned int)&WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (_DWORD)v14,
        v16);
    }
  }
  if ( v14 )
    operator delete(v14, v13);
  if ( v7 )
    operator delete(v7, v13);
  if ( hService )
    CloseServiceHandle(hService);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  if ( v21 )
    operator delete(v21, v13);
  return v15;
}

```

## disassembly

```asm
0x140089c78  mov     rax, rsp
0x140089c7b  mov     [rax+8], rbx
0x140089c7f  mov     [rax+10h], rdi
0x140089c83  mov     [rax+18h], r12
0x140089c87  push    rbp
0x140089c88  push    r13
0x140089c8a  push    r14
0x140089c8c  lea     rbp, [rax-5Fh]
0x140089c90  sub     rsp, 90h
0x140089c97  mov     rax, cs:__security_cookie
0x140089c9e  xor     rax, rsp
0x140089ca1  mov     [rbp+57h+var_18], rax
0x140089ca5  xor     r13d, r13d
0x140089ca8  lea     rcx, [rbp+57h+var_40]; wchar_t **
0x140089cac  mov     [rbp+57h+var_40], r13
0x140089cb0  call    ?GetServiceProcessDirectory@@YAJPEAPEA_W@Z; GetServiceProcessDirectory(wchar_t * *)
0x140089cb5  mov     ebx, eax
0x140089cb7  test    eax, eax
0x140089cb9  jns     short loc_140089D00
0x140089cbb  mov     rcx, cs:WPP_GLOBAL_Control
0x140089cc2  lea     r14, WPP_GLOBAL_Control
0x140089cc9  cmp     rcx, r14
0x140089ccc  jz      short loc_140089CEB
0x140089cce  test    byte ptr [rcx+1Ch], 1
0x140089cd2  jz      short loc_140089CEB
0x140089cd4  mov     rcx, [rcx+10h]
0x140089cd8  lea     edx, [r13+1Ch]
0x140089cdc  mov     r9d, eax
0x140089cdf  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089ce6  call    WPP_SF_d
0x140089ceb  mov     rcx, [rbp+57h+var_40]; void *
0x140089cef  test    rcx, rcx
0x140089cf2  jz      short loc_140089CF9
0x140089cf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140089cf9  mov     eax, ebx
0x140089cfb  jmp     loc_14008A017
0x140089d00  xor     r9d, r9d; wchar_t *
0x140089d03  mov     [rbp+57h+hSCObject], r13
0x140089d07  xor     r8d, r8d; unsigned int
0x140089d0a  lea     rcx, [rbp+57h+hSCObject]; this
0x140089d0e  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x140089d12  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x140089d17  mov     ebx, eax
0x140089d19  test    eax, eax
0x140089d1b  jns     short loc_140089D5F
0x140089d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140089d24  lea     r14, WPP_GLOBAL_Control
0x140089d2b  cmp     rcx, r14
0x140089d2e  jz      short loc_140089D4E
0x140089d30  test    byte ptr [rcx+1Ch], 1
0x140089d34  jz      short loc_140089D4E
0x140089d36  mov     rcx, [rcx+10h]
0x140089d3a  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089d41  mov     edx, 1Dh
0x140089d46  mov     r9d, eax
0x140089d49  call    WPP_SF_d
0x140089d4e  mov     rcx, [rbp+57h+hSCObject]; hSCObject
0x140089d52  test    rcx, rcx
0x140089d55  jz      short loc_140089CEB
0x140089d57  call    cs:__imp_CloseServiceHandle
0x140089d5d  jmp     short loc_140089CEB
0x140089d5f  mov     rdx, [rbp+57h+hSCObject]; struct SC_HANDLE__ **
0x140089d63  lea     r8, aMdcoresvc_0; "MDCoreSvc"
0x140089d6a  mov     r9d, 13h; wchar_t *
0x140089d70  mov     [rbp+57h+hService], r13
0x140089d74  lea     rcx, [rbp+57h+hService]; this
0x140089d78  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x140089d7d  mov     ebx, eax
0x140089d7f  test    eax, eax
0x140089d81  jns     short loc_140089DC5
0x140089d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140089d8a  lea     r14, WPP_GLOBAL_Control
0x140089d91  cmp     rcx, r14
0x140089d94  jz      short loc_140089DB4
0x140089d96  test    byte ptr [rcx+1Ch], 1
0x140089d9a  jz      short loc_140089DB4
0x140089d9c  mov     rcx, [rcx+10h]
0x140089da0  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089da7  mov     edx, 1Eh
0x140089dac  mov     r9d, eax
0x140089daf  call    WPP_SF_d
0x140089db4  mov     rcx, [rbp+57h+hService]; hSCObject
0x140089db8  test    rcx, rcx
0x140089dbb  jz      short loc_140089D4E
0x140089dbd  call    cs:__imp_CloseServiceHandle
0x140089dc3  jmp     short loc_140089D4E
0x140089dc5  mov     r8, [rbp+57h+var_40]; wchar_t *
0x140089dc9  lea     rdx, aLsMpasdescDll2_0; "@%ls\\MpAsDesc.dll,-244"
0x140089dd0  lea     rcx, [rbp+57h+String2]; this
0x140089dd4  mov     [rbp+57h+String2], r13
0x140089dd8  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140089ddd  mov     rdi, [rbp+57h+String2]
0x140089de1  test    eax, eax
0x140089de3  js      loc_140089EE3
0x140089de9  mov     r9d, 1; wchar_t *
0x140089def  mov     [rbp+57h+String2], r13
0x140089df3  lea     r8, stru_140194C20; HKEY
0x140089dfa  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x140089e01  lea     rcx, [rbp+57h+String2]; this
0x140089e05  mov     bl, 1
0x140089e07  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x140089e0c  lea     r14, WPP_GLOBAL_Control
0x140089e13  test    eax, eax
0x140089e15  js      short loc_140089E8A
0x140089e17  mov     rcx, [rbp+57h+String2]
0x140089e1b  lea     r8, [rbp+57h+String1]
0x140089e1f  xor     r9d, r9d
0x140089e22  mov     [rbp+57h+String1], r13
0x140089e26  lea     rdx, aDescription; "Description"
0x140089e2d  mov     [rsp+0A0h+var_80], r13
0x140089e32  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x140089e37  test    eax, eax
0x140089e39  js      short loc_140089E78
0x140089e3b  mov     rcx, [rbp+57h+String1]; String1
0x140089e3f  test    rcx, rcx
0x140089e42  jz      short loc_140089E8A
0x140089e44  mov     rdx, rdi; String2
0x140089e47  call    _wcsicmp
0x140089e4c  test    eax, eax
0x140089e4e  jnz     short loc_140089E78
0x140089e50  mov     bl, r13b
0x140089e53  mov     rcx, cs:WPP_GLOBAL_Control
0x140089e5a  cmp     rcx, r14
0x140089e5d  jz      short loc_140089E78
0x140089e5f  test    byte ptr [rcx+1Ch], 4
0x140089e63  jz      short loc_140089E78
0x140089e65  mov     rcx, [rcx+10h]
0x140089e69  lea     edx, [rax+1Fh]
0x140089e6c  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089e73  call    WPP_SF_
0x140089e78  mov     rcx, [rbp+57h+String1]; void *
0x140089e7c  test    rcx, rcx
0x140089e7f  jz      short loc_140089E86
0x140089e81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140089e86  test    bl, bl
0x140089e88  jz      short loc_140089ED2
0x140089e8a  mov     rcx, [rbp+57h+hService]; this
0x140089e8e  lea     r8, [rbp+57h+String1]; unsigned int
0x140089e92  mov     edx, 1; struct SC_HANDLE__ *
0x140089e97  mov     [rbp+57h+String1], rdi
0x140089e9b  call    ?HrChangeServiceConfig2W@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAX@Z; CommonUtil::HrChangeServiceConfig2W(SC_HANDLE__ *,ulong,void *)
0x140089ea0  test    eax, eax
0x140089ea2  jns     short loc_140089ED2
0x140089ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x140089eab  cmp     rcx, r14
0x140089eae  jz      short loc_140089ED2
0x140089eb0  test    byte ptr [rcx+1Ch], 2
0x140089eb4  jz      short loc_140089ED2
0x140089eb6  mov     rcx, [rcx+10h]
0x140089eba  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089ec1  mov     edx, 20h ; ' '
0x140089ec6  mov     dword ptr [rsp+0A0h+var_80], eax
0x140089eca  mov     r9, rdi
0x140089ecd  call    WPP_SF_Sd
0x140089ed2  mov     rcx, [rbp+57h+String2]; hKey
0x140089ed6  test    rcx, rcx
0x140089ed9  jz      short loc_140089F14
0x140089edb  call    cs:__imp_RegCloseKey
0x140089ee1  jmp     short loc_140089F14
0x140089ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x140089eea  lea     r14, WPP_GLOBAL_Control
0x140089ef1  cmp     rcx, r14
0x140089ef4  jz      short loc_140089F14
0x140089ef6  test    byte ptr [rcx+1Ch], 2
0x140089efa  jz      short loc_140089F14
0x140089efc  mov     rcx, [rcx+10h]
0x140089f00  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089f07  mov     edx, 21h ; '!'
0x140089f0c  mov     r9d, eax
0x140089f0f  call    WPP_SF_d
0x140089f14  mov     r8, [rbp+57h+var_40]; wchar_t *
0x140089f18  lea     rdx, aLsMpasdescDll2; "@%ls\\MpAsDesc.dll,-245"
0x140089f1f  lea     rcx, [rbp+57h+String2]; this
0x140089f23  mov     [rbp+57h+String2], r13
0x140089f27  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x140089f2c  mov     rbx, [rbp+57h+String2]
0x140089f30  mov     r12d, eax
0x140089f33  test    eax, eax
0x140089f35  js      short loc_140089FA3
0x140089f37  mov     rcx, [rbp+57h+hService]; hService
0x140089f3b  or      edx, 0FFFFFFFFh; struct SC_HANDLE__ *
0x140089f3e  mov     [rsp+0A0h+var_50], r13; LPDWORD
0x140089f43  mov     r9d, edx; char
0x140089f46  mov     [rsp+0A0h+var_58], rbx; LPCWSTR
0x140089f4b  mov     r8d, edx; char
0x140089f4e  mov     [rsp+0A0h+var_60], r13; LPCWSTR
0x140089f53  mov     [rsp+0A0h+var_68], r13; LPCWSTR
0x140089f58  mov     [rsp+0A0h+var_70], r13; LPCWSTR
0x140089f5d  mov     [rsp+0A0h+var_78], r13; LPCWSTR
0x140089f62  mov     [rsp+0A0h+var_80], r13; LPCWSTR
0x140089f67  call    ?HrChangeServiceConfig@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKPEB_W11111PEAK@Z; CommonUtil::HrChangeServiceConfig(SC_HANDLE__ *,ulong,ulong,ulong,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong *)
0x140089f6c  mov     r12d, eax
0x140089f6f  test    eax, eax
0x140089f71  jns     short loc_140089FCD
0x140089f73  mov     rcx, cs:WPP_GLOBAL_Control
0x140089f7a  cmp     rcx, r14
0x140089f7d  jz      short loc_140089FCD
0x140089f7f  test    byte ptr [rcx+1Ch], 1
0x140089f83  jz      short loc_140089FCD
0x140089f85  mov     rcx, [rcx+10h]
0x140089f89  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089f90  mov     edx, 22h ; '"'
0x140089f95  mov     dword ptr [rsp+0A0h+var_80], eax
0x140089f99  mov     r9, rbx
0x140089f9c  call    WPP_SF_Sd
0x140089fa1  jmp     short loc_140089FCD
0x140089fa3  mov     rcx, cs:WPP_GLOBAL_Control
0x140089faa  cmp     rcx, r14
0x140089fad  jz      short loc_140089FCD
0x140089faf  test    byte ptr [rcx+1Ch], 1
0x140089fb3  jz      short loc_140089FCD
0x140089fb5  mov     rcx, [rcx+10h]
0x140089fb9  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089fc0  mov     edx, 23h ; '#'
0x140089fc5  mov     r9d, eax
0x140089fc8  call    WPP_SF_d
0x140089fcd  test    rbx, rbx
0x140089fd0  jz      short loc_140089FDA
0x140089fd2  mov     rcx, rbx; void *
0x140089fd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140089fda  test    rdi, rdi
0x140089fdd  jz      short loc_140089FE7
0x140089fdf  mov     rcx, rdi; void *
0x140089fe2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140089fe7  mov     rcx, [rbp+57h+hService]; hSCObject
0x140089feb  test    rcx, rcx
0x140089fee  jz      short loc_140089FF6
0x140089ff0  call    cs:__imp_CloseServiceHandle
0x140089ff6  mov     rcx, [rbp+57h+hSCObject]; hSCObject
0x140089ffa  test    rcx, rcx
0x140089ffd  jz      short loc_14008A005
0x140089fff  call    cs:__imp_CloseServiceHandle
0x14008a005  cmp     [rbp+57h+var_40], r13
0x14008a009  jz      short loc_14008A014
0x14008a00b  mov     rcx, [rbp+57h+var_40]; void *
0x14008a00f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008a014  mov     eax, r12d
0x14008a017  mov     rcx, [rbp+57h+var_18]
0x14008a01b  xor     rcx, rsp; StackCookie
0x14008a01e  call    __security_check_cookie
0x14008a023  lea     r11, [rsp+0A0h+var_10]
0x14008a02b  mov     rbx, [r11+20h]
0x14008a02f  mov     rdi, [r11+28h]
0x14008a033  mov     r12, [r11+30h]
0x14008a037  mov     rsp, r11
0x14008a03a  pop     r14
0x14008a03c  pop     r13
0x14008a03e  pop     rbp
0x14008a03f  retn
```
