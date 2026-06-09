# CConfigManager::GetIISConfiguration(IRequestContext *,ushort const *,XmlReader * *)

- ea: `0x18019c810`
- end: `0x18019d09b`
- name: `?GetIISConfiguration@CConfigManager@@SAHPEAVIRequestContext@@PEBGPEAPEAVXmlReader@@@Z`
- size: `2187`
- prototype: `__int64 __fastcall(struct IRequestContext *, OLECHAR *psz, struct XmlReader **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180178f3c`

## callees

- `0x180005d10`
- `0x180024ae0`
- `0x180033e10`
- `0x1800621e0`
- `0x18009bc00`
- `0x1800cc11c`
- `0x1800ce6a0`
- `0x1800e5510`
- `0x1800e8a50`
- `0x180112380`
- `0x1801133b0`
- `0x18019c810`
- `0x18019e9b8`
- `0x1801a6268`
- `0x1801ba1b0`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18019cbde`
- `msvcrt!_itow_s` at `0x18019cbde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019cd70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019cd70`
- `OLEAUT32!__imp_SysAllocString` at `0x18019c8e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18019c94a`
- `OLEAUT32!__imp_SysAllocString` at `0x18019c8e2`
- `OLEAUT32!__imp_SysAllocString` at `0x18019c94a`
- `OLEAUT32!__imp_SysStringLen` at `0x18019c8f3`
- `OLEAUT32!__imp_SysStringLen` at `0x18019c95a`
- `OLEAUT32!__imp_SysStringLen` at `0x18019c8f3`
- `OLEAUT32!__imp_SysStringLen` at `0x18019c95a`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18019cb2c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18019cb2c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019ca68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18019ca68`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18019c9bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18019c9bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019cc96`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019cfde`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019d053`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019cc96`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019cfde`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18019d053`

## string_xrefs

- `0x18019c89c`: `onecore\admin\wmi\wmx\config\cconfigmanager.cpp`
- `0x18019c943`: `system.webServer/system.management.wsmanagement.config`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CConfigManager::GetIISConfiguration(struct IRequestContext *a1, OLECHAR *psz, struct XmlReader **a3)
{
  OLECHAR *v7; // rsi
  OLECHAR *v8; // rdi
  HRESULT v9; // eax
  unsigned int v10; // r15d
  BOOL v11; // ebx
  __int64 v12; // rdx
  HRESULT v13; // eax
  int v14; // edi
  DWORD LastError; // eax
  IErrorInfo *v16; // rax
  struct XmlReader *v17; // rdi
  struct XmlReader *v18; // [rsp+40h] [rbp-C0h] BYREF
  struct IAppHostElement *v19; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int Value; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v25; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR *v26; // [rsp+80h] [rbp-80h] BYREF
  BOOL v27; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v28[323]; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+AA8h] [rbp+9A8h]
  wchar_t Buffer[8]; // [rsp+AB0h] [rbp+9B0h] BYREF
  __int64 v31; // [rsp+AC0h] [rbp+9C0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1377, L"1377", 0x54Fu, 0);
    return 0;
  }
  if ( !psz )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1378, L"1378", 0x54Fu, a1);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\cconfigmanager.cpp", 1379, L"1379", 0x54Fu, a1);
    return 0;
  }
  v7 = SysAllocString(psz);
  v25 = v7;
  if ( !SysStringLen(v7) )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
LABEL_15:
    AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v25);
    return 0;
  }
  v8 = SysAllocString(L"system.webServer/system.management.wsmanagement.config");
  v26 = v8;
  if ( SysStringLen(v8) )
  {
    ppv = 0;
    v19 = 0;
    v9 = CoInitializeEx(0, 0);
    v10 = 1;
    v11 = v9 >= 0;
    v27 = v11;
    if ( v9 >= 0 )
    {
      v13 = CoCreateInstance(
              &GUID_228fb8f7_fb53_4fd5_8c7b_ff59de606c5b,
              0,
              1u,
              &GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13,
              &ppv);
      if ( v13 >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, OLECHAR *, struct IAppHostElement **))(*(_QWORD *)ppv + 24LL))(
                ppv,
                v8,
                v7,
                &v19);
        if ( v14 >= 0 )
        {
          RBUFFER::RBUFFER((RBUFFER *)v28, 0);
          v29 = 0;
          if ( (unsigned int)ReadIISConfig(v19, (struct TSTRBUFFER *)v28, 1) )
          {
            v16 = (IErrorInfo *)WSManMemory::Alloc(32, 0, 0);
            v17 = (struct XmlReader *)v16;
            pperrinfo = v16;
            if ( v16 )
            {
              v16->lpVtbl = 0;
              v16[1].lpVtbl = 0;
              v16[2].lpVtbl = 0;
            }
            else
            {
              v17 = 0;
            }
            v18 = v17;
            if ( v17 )
            {
              if ( XmlReader::Init(v17, a1, v28[0]) )
              {
                if ( (unsigned int)ConfigValidateXML(a1, (struct _CONFIGXML_ELEMENT *)&g_IISConfigurationElement, v17) )
                {
                  if ( (unsigned int)ConfigValidateIISConfigXml(a1, v17) )
                  {
                    v18 = 0;
                    *a3 = v17;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                    {
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
                    }
                    AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v18);
                    RBUFFER::~RBUFFER((RBUFFER *)v28);
                    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
                    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
                    if ( v11 )
                      CoUninitialize();
                    goto LABEL_88;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
                }
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
              }
            }
            else
            {
              (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 24LL))(a1);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
            }
            AutoCleanup<AutoDelete<XmlReader>,XmlReader *>::ReleasePtr(&v18);
            RBUFFER::~RBUFFER((RBUFFER *)v28);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
          }
          else
          {
            LastError = GetLastError();
            (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, LastError);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
            RBUFFER::~RBUFFER((RBUFFER *)v28);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
          }
        }
        else
        {
          pperrinfo = 0;
          v18 = 0;
          v22 = 0;
          Value = 0;
          v24 = 0;
          if ( GetErrorInfo(0, &pperrinfo) >= 0
            && ((__int64 (__fastcall *)(IErrorInfo *, GUID *, struct XmlReader **))pperrinfo->lpVtbl->QueryInterface)(
                 pperrinfo,
                 &GUID_4dfa1df3_8900_4bc7_bbb5_d1a458c52410,
                 &v18) >= 0
            && (*(int (__fastcall **)(struct XmlReader *, __int64 *))(*(_QWORD *)v18 + 72LL))(v18, &v22) >= 0
            && (*(int (__fastcall **)(struct XmlReader *, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, &v24) >= 0
            && (*(int (__fastcall **)(struct XmlReader *, int *))(*(_QWORD *)v18 + 24LL))(v18, &Value) >= 0 )
          {
            *(_OWORD *)Buffer = 0;
            v31 = 0;
            _itow_s(Value, Buffer, 0xCu, 10);
            (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, __int64, wchar_t *, __int64))(*(_QWORD *)a1 + 64LL))(
              a1,
              2150859155LL,
              1077134544,
              v24,
              Buffer,
              v22);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids, v22);
            AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v24);
            AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v22);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v18);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&pperrinfo);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
            AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
            if ( v11 )
              CoUninitialize();
            AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v26);
            goto LABEL_15;
          }
          AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v24);
          AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v22);
          AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v18);
          AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&pperrinfo);
          if ( (v14 & 0x1FFF0000) == 0x70000 )
            v14 = (unsigned __int16)v14;
          (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, (unsigned int)v14);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
          AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
          AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
        }
        goto LABEL_80;
      }
      if ( (v13 & 0x1FFF0000) == 0x70000 )
        v13 = (unsigned __int16)v13;
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a1 + 72LL))(a1, (unsigned int)v13);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
    }
    else
    {
      v12 = (unsigned __int16)v9;
      if ( (v9 & 0x1FFF0000) != 0x70000 )
        v12 = (unsigned int)v9;
      (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)a1 + 72LL))(a1, v12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
    }
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&v19);
    AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(&ppv);
LABEL_80:
    if ( v11 )
      CoUninitialize();
    goto LABEL_82;
  }
  (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a1 + 24LL))(a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids);
LABEL_82:
  v10 = 0;
LABEL_88:
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v26);
  AutoCleanup<AutoBstr,unsigned short *>::ReleasePtr(&v25);
  return v10;
}

```

## disassembly

```asm
0x18019c810  mov     [rsp-8+arg_18], rbx
0x18019c815  push    rbp
0x18019c816  push    rsi
0x18019c817  push    rdi
0x18019c818  push    r12
0x18019c81a  push    r13
0x18019c81c  push    r14
0x18019c81e  push    r15
0x18019c820  lea     rbp, [rsp-9D0h]
0x18019c828  sub     rsp, 0AD0h
0x18019c82f  mov     rax, cs:__security_cookie
0x18019c836  xor     rax, rsp
0x18019c839  mov     [rbp+0A00h+var_38], rax
0x18019c840  mov     r12, r8
0x18019c843  mov     rbx, rdx
0x18019c846  mov     r14, rcx
0x18019c849  lea     rdi, WPP_GLOBAL_Control
0x18019c850  mov     r15d, 200000h
0x18019c856  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c85d  cmp     rcx, rdi
0x18019c860  jz      short loc_18019C87D
0x18019c862  test    [rcx+1Ch], r15d
0x18019c866  jz      short loc_18019C87D
0x18019c868  mov     edx, 31h ; '1'
0x18019c86d  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c874  mov     rcx, [rcx+10h]
0x18019c878  call    WPP_SF_
0x18019c87d  xor     r13d, r13d
0x18019c880  test    r14, r14
0x18019c883  jnz     short loc_18019C8AF
0x18019c885  mov     [rsp+0B00h+ppv], r13; struct IRequestContext *
0x18019c88a  lea     r8, a1377; "1377"
0x18019c891  mov     edx, 561h; unsigned int
0x18019c896  mov     r9d, 54Fh; unsigned int
0x18019c89c  lea     rcx, aOnecoreAdminWm_148; "onecore\\admin\\wmi\\wmx\\config\\cconf"...
0x18019c8a3  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019c8a8  xor     eax, eax
0x18019c8aa  jmp     loc_18019D071
0x18019c8af  test    rbx, rbx
0x18019c8b2  jnz     short loc_18019C8C7
0x18019c8b4  mov     [rsp+0B00h+ppv], r14
0x18019c8b9  lea     r8, a1378; "1378"
0x18019c8c0  mov     edx, 562h
0x18019c8c5  jmp     short loc_18019C896
0x18019c8c7  test    r12, r12
0x18019c8ca  jnz     short loc_18019C8DF
0x18019c8cc  mov     [rsp+0B00h+ppv], r14
0x18019c8d1  lea     r8, a1379; "1379"
0x18019c8d8  mov     edx, 563h
0x18019c8dd  jmp     short loc_18019C896
0x18019c8df  mov     rcx, rbx; psz
0x18019c8e2  call    cs:__imp_SysAllocString
0x18019c8e8  mov     rsi, rax
0x18019c8eb  mov     [rsp+0B00h+var_A88], rax
0x18019c8f0  mov     rcx, rax; pbstr
0x18019c8f3  call    cs:__imp_SysStringLen
0x18019c8f9  test    eax, eax
0x18019c8fb  jnz     short loc_18019C943
0x18019c8fd  mov     rax, [r14]
0x18019c900  mov     rcx, r14
0x18019c903  mov     rax, [rax+18h]
0x18019c907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c913  cmp     rcx, rdi
0x18019c916  jz      short loc_18019C934
0x18019c918  test    [rcx+1Ch], r15d
0x18019c91c  jz      short loc_18019C934
0x18019c91e  mov     edx, 32h ; '2'
0x18019c923  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c92a  mov     rcx, [rcx+10h]
0x18019c92e  call    WPP_SF_
0x18019c933  nop
0x18019c934  lea     rcx, [rsp+0B00h+var_A88]
0x18019c939  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019c93e  jmp     loc_18019C8A8
0x18019c943  lea     rcx, aSystemWebserve; "system.webServer/system.management.wsma"...
0x18019c94a  call    cs:__imp_SysAllocString
0x18019c950  mov     rdi, rax
0x18019c953  mov     [rbp+0A00h+var_A80], rax
0x18019c957  mov     rcx, rax; pbstr
0x18019c95a  call    cs:__imp_SysStringLen
0x18019c960  test    eax, eax
0x18019c962  jnz     short loc_18019C9AE
0x18019c964  mov     rax, [r14]
0x18019c967  mov     rcx, r14
0x18019c96a  mov     rax, [rax+18h]
0x18019c96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c973  mov     rcx, cs:WPP_GLOBAL_Control
0x18019c97a  lea     rax, WPP_GLOBAL_Control
0x18019c981  cmp     rcx, rax
0x18019c984  jz      loc_18019CFE4
0x18019c98a  test    [rcx+1Ch], r15d
0x18019c98e  jz      loc_18019CFE4
0x18019c994  mov     edx, 33h ; '3'
0x18019c999  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019c9a0  mov     rcx, [rcx+10h]
0x18019c9a4  call    WPP_SF_
0x18019c9a9  jmp     loc_18019CFE4
0x18019c9ae  mov     ebx, r13d
0x18019c9b1  mov     [rsp+0B00h+var_AB0], r13
0x18019c9b6  mov     [rsp+0B00h+var_AB8], r13
0x18019c9bb  xor     edx, edx; dwCoInit
0x18019c9bd  xor     ecx, ecx; pvReserved
0x18019c9bf  call    cs:__imp_CoInitializeEx
0x18019c9c5  mov     r8d, eax
0x18019c9c8  mov     r15d, 1
0x18019c9ce  test    eax, eax
0x18019c9d0  cmovns  ebx, r15d
0x18019c9d4  mov     [rbp+0A00h+var_A78], ebx
0x18019c9d7  jns     short loc_18019CA4B
0x18019c9d9  mov     rax, [r14]
0x18019c9dc  mov     ecx, r8d
0x18019c9df  and     ecx, 1FFF0000h
0x18019c9e5  movzx   edx, r8w
0x18019c9e9  cmp     ecx, 70000h
0x18019c9ef  cmovnz  edx, r8d
0x18019c9f3  mov     rcx, r14
0x18019c9f6  mov     rax, [rax+48h]
0x18019c9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019c9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18019ca06  lea     rax, WPP_GLOBAL_Control
0x18019ca0d  cmp     rcx, rax
0x18019ca10  jz      short loc_18019CA30
0x18019ca12  test    dword ptr [rcx+1Ch], 200000h
0x18019ca19  jz      short loc_18019CA30
0x18019ca1b  lea     edx, [r15+33h]
0x18019ca1f  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019ca26  mov     rcx, [rcx+10h]
0x18019ca2a  call    WPP_SF_
0x18019ca2f  nop
0x18019ca30  lea     rcx, [rsp+0B00h+var_AB8]
0x18019ca35  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019ca3a  nop
0x18019ca3b  lea     rcx, [rsp+0B00h+var_AB0]
0x18019ca40  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019ca45  nop
0x18019ca46  jmp     loc_18019CFDA
0x18019ca4b  lea     rax, [rsp+0B00h+var_AB0]
0x18019ca50  mov     [rsp+0B00h+ppv], rax; ppv
0x18019ca55  lea     r9, _GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13; riid
0x18019ca5c  mov     r8d, r15d; dwClsContext
0x18019ca5f  xor     edx, edx; pUnkOuter
0x18019ca61  lea     rcx, _GUID_228fb8f7_fb53_4fd5_8c7b_ff59de606c5b; rclsid
0x18019ca68  call    cs:__imp_CoCreateInstance
0x18019ca6e  test    eax, eax
0x18019ca70  jns     short loc_18019CAE6
0x18019ca72  mov     rcx, [r14]
0x18019ca75  mov     r8, [rcx+48h]
0x18019ca79  mov     ecx, eax
0x18019ca7b  and     ecx, 1FFF0000h
0x18019ca81  cmp     ecx, 70000h
0x18019ca87  jnz     short loc_18019CA8C
0x18019ca89  movzx   eax, ax
0x18019ca8c  mov     edx, eax
0x18019ca8e  mov     rcx, r14
0x18019ca91  mov     rax, r8
0x18019ca94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ca99  mov     rcx, cs:WPP_GLOBAL_Control
0x18019caa0  lea     rax, WPP_GLOBAL_Control
0x18019caa7  cmp     rcx, rax
0x18019caaa  jz      short loc_18019CACB
0x18019caac  test    dword ptr [rcx+1Ch], 200000h
0x18019cab3  jz      short loc_18019CACB
0x18019cab5  mov     edx, 35h ; '5'
0x18019caba  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019cac1  mov     rcx, [rcx+10h]
0x18019cac5  call    WPP_SF_
0x18019caca  nop
0x18019cacb  lea     rcx, [rsp+0B00h+var_AB8]
0x18019cad0  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cad5  nop
0x18019cad6  lea     rcx, [rsp+0B00h+var_AB0]
0x18019cadb  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cae0  nop
0x18019cae1  jmp     loc_18019CFDA
0x18019cae6  mov     rcx, [rsp+0B00h+var_AB0]
0x18019caeb  mov     rax, [rcx]
0x18019caee  lea     r9, [rsp+0B00h+var_AB8]
0x18019caf3  mov     r8, rsi
0x18019caf6  mov     rdx, rdi
0x18019caf9  mov     rax, [rax+18h]
0x18019cafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cb02  mov     edi, eax
0x18019cb04  test    eax, eax
0x18019cb06  jns     loc_18019CD49
0x18019cb0c  mov     [rsp+0B00h+pperrinfo], r13
0x18019cb11  mov     [rsp+0B00h+var_AC0], r13
0x18019cb16  mov     [rsp+0B00h+var_AA0], r13
0x18019cb1b  mov     [rsp+0B00h+Value], r13d
0x18019cb20  mov     [rsp+0B00h+var_A90], r13
0x18019cb25  lea     rdx, [rsp+0B00h+pperrinfo]; pperrinfo
0x18019cb2a  xor     ecx, ecx; dwReserved
0x18019cb2c  call    cs:__imp_GetErrorInfo
0x18019cb32  test    eax, eax
0x18019cb34  js      loc_18019CCAB
0x18019cb3a  mov     rcx, [rsp+0B00h+pperrinfo]
0x18019cb3f  mov     rax, [rcx]
0x18019cb42  lea     r8, [rsp+0B00h+var_AC0]
0x18019cb47  lea     rdx, _GUID_4dfa1df3_8900_4bc7_bbb5_d1a458c52410
0x18019cb4e  mov     rax, [rax]
0x18019cb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cb56  test    eax, eax
0x18019cb58  js      loc_18019CCAB
0x18019cb5e  mov     rcx, [rsp+0B00h+var_AC0]
0x18019cb63  mov     rax, [rcx]
0x18019cb66  lea     rdx, [rsp+0B00h+var_AA0]
0x18019cb6b  mov     rax, [rax+48h]
0x18019cb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cb74  test    eax, eax
0x18019cb76  js      loc_18019CCAB
0x18019cb7c  mov     rcx, [rsp+0B00h+var_AC0]
0x18019cb81  mov     rax, [rcx]
0x18019cb84  lea     rdx, [rsp+0B00h+var_A90]
0x18019cb89  mov     rax, [rax+20h]
0x18019cb8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cb92  test    eax, eax
0x18019cb94  js      loc_18019CCAB
0x18019cb9a  mov     rcx, [rsp+0B00h+var_AC0]
0x18019cb9f  mov     rax, [rcx]
0x18019cba2  lea     rdx, [rsp+0B00h+Value]
0x18019cba7  mov     rax, [rax+18h]
0x18019cbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cbb0  test    eax, eax
0x18019cbb2  js      loc_18019CCAB
0x18019cbb8  xorps   xmm0, xmm0
0x18019cbbb  xor     eax, eax
0x18019cbbd  movups  xmmword ptr [rbp+0A00h+Buffer], xmm0
0x18019cbc4  mov     [rbp+0A00h+var_40], rax
0x18019cbcb  lea     r9d, [rax+0Ah]; Radix
0x18019cbcf  lea     r8d, [rax+0Ch]; BufferCount
0x18019cbd3  lea     rdx, [rbp+0A00h+Buffer]; Buffer
0x18019cbda  mov     ecx, [rsp+0B00h+Value]; Value
0x18019cbde  call    cs:__imp__itow_s
0x18019cbe4  mov     rax, [r14]
0x18019cbe7  mov     rcx, [rsp+0B00h+var_AA0]
0x18019cbec  mov     [rsp+0B00h+var_AD8], rcx
0x18019cbf1  lea     rcx, [rbp+0A00h+Buffer]
0x18019cbf8  mov     [rsp+0B00h+ppv], rcx
0x18019cbfd  mov     r9, [rsp+0B00h+var_A90]
0x18019cc02  mov     edx, 80338193h
0x18019cc07  mov     r8d, 4033C4D0h
0x18019cc0d  mov     rcx, r14
0x18019cc10  mov     rax, [rax+40h]
0x18019cc14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019cc19  mov     rcx, cs:WPP_GLOBAL_Control
0x18019cc20  lea     rax, WPP_GLOBAL_Control
0x18019cc27  cmp     rcx, rax
0x18019cc2a  jz      short loc_18019CC50
0x18019cc2c  test    dword ptr [rcx+1Ch], 200000h
0x18019cc33  jz      short loc_18019CC50
0x18019cc35  mov     edx, 36h ; '6'
0x18019cc3a  mov     r9, [rsp+0B00h+var_AA0]
0x18019cc3f  lea     r8, WPP_c03cedce7f3e39a4c90d6f3969516379_Traceguids
0x18019cc46  mov     rcx, [rcx+10h]
0x18019cc4a  call    WPP_SF_S
0x18019cc4f  nop
0x18019cc50  lea     rcx, [rsp+0B00h+var_A90]
0x18019cc55  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019cc5a  nop
0x18019cc5b  lea     rcx, [rsp+0B00h+var_AA0]
0x18019cc60  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019cc65  nop
0x18019cc66  lea     rcx, [rsp+0B00h+var_AC0]
0x18019cc6b  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cc70  nop
0x18019cc71  lea     rcx, [rsp+0B00h+pperrinfo]
0x18019cc76  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cc7b  nop
0x18019cc7c  lea     rcx, [rsp+0B00h+var_AB8]
0x18019cc81  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cc86  nop
0x18019cc87  lea     rcx, [rsp+0B00h+var_AB0]
0x18019cc8c  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cc91  nop
0x18019cc92  test    ebx, ebx
0x18019cc94  jz      short loc_18019CC9D
0x18019cc96  call    cs:__imp_CoUninitialize
0x18019cc9c  nop
0x18019cc9d  lea     rcx, [rbp+0A00h+var_A80]
0x18019cca1  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019cca6  jmp     loc_18019C934
0x18019ccab  lea     rcx, [rsp+0B00h+var_A90]
0x18019ccb0  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019ccb5  nop
0x18019ccb6  lea     rcx, [rsp+0B00h+var_AA0]
0x18019ccbb  call    ?ReleasePtr@?$AutoCleanup@VAutoBstr@@PEAG@@AEAAXXZ; AutoCleanup<AutoBstr,ushort *>::ReleasePtr(void)
0x18019ccc0  nop
0x18019ccc1  lea     rcx, [rsp+0B00h+var_AC0]
0x18019ccc6  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019cccb  nop
0x18019cccc  lea     rcx, [rsp+0B00h+pperrinfo]
0x18019ccd1  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@UIEnumWbemClassObject@@@@PEAUIEnumWbemClassObject@@@@AEAAXXZ; AutoCleanup<AutoRelease<IEnumWbemClassObject>,IEnumWbemClassObject *>::ReleasePtr(void)
0x18019ccd6  nop
0x18019ccd7  mov     rax, [r14]
0x18019ccda  mov     r8, [rax+48h]
0x18019ccde  mov     eax, edi
0x18019cce0  and     eax, 1FFF0000h
0x18019cce5  cmp     eax, 70000h
0x18019ccea  jnz     short loc_18019CCEF
0x18019ccec  movzx   edi, di
  ... truncated ...
```
