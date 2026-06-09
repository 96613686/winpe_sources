# CRmsInterface::CreateLicense(ushort const *,IPC_LICENSE_HANDLE__ * *)

- ea: `0x18006d1a0`
- end: `0x18006d450`
- name: `?CreateLicense@CRmsInterface@@AEAAJPEBGPEAPEAUIPC_LICENSE_HANDLE__@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(CRmsInterface *__hidden this, const unsigned __int16 *, struct IPC_LICENSE_HANDLE__ **)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18006cc84`
- `0x18006eb8c`

## callees

- `0x180005045`
- `0x18006b034`
- `0x18006ba48`
- `0x18006bcf8`
- `0x18006bfb0`
- `0x18006c764`
- `0x18006d1a0`
- `0x18006db58`
- `0x18006e29c`
- `0x18006ee3c`
- `0x18006f0b4`
- `0x1800dddf0`

## import_xrefs

- `winmsipc!__imp_IpcCloseHandle` at `0x18006d405`
- `winmsipc!__imp_IpcCloseHandle` at `0x18006d405`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006d3f5`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006d3f5`
- `winmsipc!__imp_IpcCreateLicenseFromTemplateID` at `0x18006d374`
- `winmsipc!__imp_IpcCreateLicenseFromTemplateID` at `0x18006d3ae`
- `winmsipc!__imp_IpcCreateLicenseFromTemplateID` at `0x18006d374`
- `winmsipc!__imp_IpcCreateLicenseFromTemplateID` at `0x18006d3ae`
- `winmsipc!__imp_IpcCreateLicenseFromScratch` at `0x18006d2d2`
- `winmsipc!__imp_IpcCreateLicenseFromScratch` at `0x18006d2d2`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006d361`
- `winmsipc!__imp_IpcSetLicenseProperty` at `0x18006d361`
- `winmsipc!__imp_IpcGetTemplateIssuerList` at `0x18006d268`
- `winmsipc!__imp_IpcGetTemplateIssuerList` at `0x18006d298`
- `winmsipc!__imp_IpcGetTemplateIssuerList` at `0x18006d268`
- `winmsipc!__imp_IpcGetTemplateIssuerList` at `0x18006d298`

## string_xrefs

- `0x18006d211`: `RmsCreateLicense`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRmsInterface::CreateLicense(
        CRmsInterface *this,
        const unsigned __int16 *a2,
        struct IPC_LICENSE_HANDLE__ **a3)
{
  int TemplateIssuerList; // eax
  unsigned int v6; // ebx
  int v7; // eax
  CRmsInterface *v8; // rcx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  bool v11[4]; // [rsp+34h] [rbp-CCh] BYREF
  int v12; // [rsp+38h] [rbp-C8h] BYREF
  struct IPC_LICENSE_HANDLE__ *v13; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v14; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[24]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[72]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v18[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v19; // [rsp+D0h] [rbp-30h]
  _QWORD v20[42]; // [rsp+F0h] [rbp-10h] BYREF
  _DWORD v21[4]; // [rsp+240h] [rbp+140h] BYREF
  const wchar_t *v22; // [rsp+250h] [rbp+150h]
  int v23; // [rsp+258h] [rbp+158h]
  _QWORD *v24; // [rsp+260h] [rbp+160h]
  int v25; // [rsp+268h] [rbp+168h]
  const wchar_t *v26; // [rsp+270h] [rbp+170h]
  int v27; // [rsp+278h] [rbp+178h]
  _QWORD *v28; // [rsp+280h] [rbp+180h]

  v13 = 0;
  v14 = 0;
  RmsPromptContext::RmsPromptContext((RmsPromptContext *)v16);
  memset_0(v21, 0, 0x68u);
  v12 = 0;
  v15[0] = L"OWNER";
  wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "RmsCreateLicense");
  v20[0] = &EfsTelemetry::RmsCreateLicense::`vftable';
  EfsTelemetry::RmsCreateLicense::StartActivity((EfsTelemetry::RmsCreateLicense *)v20);
  *a3 = 0;
  CheckAndClearTempRmsAccess();
  if ( a2 )
  {
    v7 = IpcCreateLicenseFromTemplateID(a2, 0, 0, &v13);
    v10 = v7;
    v6 = v7;
    if ( v7 != -2147220979 && v7 != -2147024894 )
    {
LABEL_14:
      if ( v7 >= 0 )
      {
        *a3 = v13;
        v13 = 0;
      }
      goto LABEL_16;
    }
    v12 = v7;
    v10 = CRmsInterface::ProvisionForCurrentUser(v8);
    v6 = v10;
    if ( v10 < 0 )
      goto LABEL_16;
    v7 = IpcCreateLicenseFromTemplateID(a2, 0, 0, &v13);
LABEL_13:
    v10 = v7;
    v6 = v7;
    goto LABEL_14;
  }
  v19 |= 2u;
  TemplateIssuerList = IpcGetTemplateIssuerList(0, 0, v18, 0, &v14);
  v10 = TemplateIssuerList;
  v6 = TemplateIssuerList;
  if ( TemplateIssuerList == -2147220979 )
  {
    v19 &= ~2u;
    v12 = -2147220979;
    TemplateIssuerList = IpcGetTemplateIssuerList(0, 0, v18, 0, &v14);
    v6 = TemplateIssuerList;
    v10 = TemplateIssuerList;
  }
  if ( TemplateIssuerList >= 0 )
  {
    if ( *v14 != 1 )
    {
      v6 = -2147023286;
      v10 = -2147023286;
      goto LABEL_16;
    }
    v10 = IpcCreateLicenseFromScratch(v14 + 2, 0, 0, &v13);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v24 = v15;
      v21[0] = 80;
      v21[1] = 2;
      v26 = L"ANYONE";
      v28 = v15;
      v21[2] = 2;
      v22 = L"OWNER";
      v23 = 1;
      v25 = 2;
      v27 = 1;
      v7 = IpcSetLicenseProperty(v13, 0, 4, v21);
      goto LABEL_13;
    }
  }
LABEL_16:
  v11[0] = a2 != 0;
  EfsTelemetry::RmsCreateLicense::LogRmsCreateLicense<bool,long &,long &>(v11, &v12, &v10);
  if ( v14 )
    IpcFreeMemory();
  if ( v13 )
    IpcCloseHandle(v13);
  wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20);
  EfsTelemetry::RmsCreateLicense::~RmsCreateLicense((EfsTelemetry::RmsCreateLicense *)v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  return v6;
}

```

## disassembly

```asm
0x18006d1a0  mov     [rsp-8+arg_0], rbx
0x18006d1a5  mov     [rsp-8+arg_18], rsi
0x18006d1aa  push    rbp
0x18006d1ab  push    rdi
0x18006d1ac  push    r13
0x18006d1ae  lea     rbp, [rsp-1C0h]
0x18006d1b6  sub     rsp, 2C0h
0x18006d1bd  mov     rax, cs:__security_cookie
0x18006d1c4  xor     rax, rsp
0x18006d1c7  mov     [rbp+1D0h+var_20], rax
0x18006d1ce  lea     rcx, [rsp+2D0h+var_270]; this
0x18006d1d3  mov     [rsp+2D0h+var_290], 0
0x18006d1dc  mov     rsi, r8
0x18006d1df  mov     [rsp+2D0h+var_288], 0
0x18006d1e8  mov     rdi, rdx
0x18006d1eb  call    ??0RmsPromptContext@@QEAA@XZ; RmsPromptContext::RmsPromptContext(void)
0x18006d1f0  xor     edx, edx; Val
0x18006d1f2  lea     rcx, [rbp+1D0h+var_90]; void *
0x18006d1f9  lea     r8d, [rdx+68h]; Size
0x18006d1fd  call    memset_0
0x18006d202  lea     r13, aOwner; "OWNER"
0x18006d209  mov     [rsp+2D0h+var_298], 0
0x18006d211  lea     rdx, aRmscreatelicen; "RmsCreateLicense"
0x18006d218  mov     [rsp+2D0h+var_280], r13
0x18006d21d  lea     rcx, [rbp+1D0h+var_1E0]
0x18006d221  call    ??0?$ActivityBase@VEfsTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006d226  lea     rax, ??_7RmsCreateLicense@EfsTelemetry@@6B@; const EfsTelemetry::RmsCreateLicense::`vftable'
0x18006d22d  lea     rcx, [rbp+1D0h+var_1E0]; this
0x18006d231  mov     [rbp+1D0h+var_1E0], rax
0x18006d235  call    ?StartActivity@RmsCreateLicense@EfsTelemetry@@QEAAXXZ; EfsTelemetry::RmsCreateLicense::StartActivity(void)
0x18006d23a  mov     qword ptr [rsi], 0
0x18006d241  call    CheckAndClearTempRmsAccess
0x18006d246  xor     edx, edx
0x18006d248  test    rdi, rdi
0x18006d24b  jnz     loc_18006D369
0x18006d251  or      [rbp+1D0h+var_200], 2
0x18006d255  lea     rax, [rsp+2D0h+var_288]
0x18006d25a  xor     r9d, r9d
0x18006d25d  mov     [rsp+2D0h+var_2B0], rax
0x18006d262  lea     r8, [rbp+1D0h+var_210]
0x18006d266  xor     ecx, ecx
0x18006d268  call    cs:__imp_IpcGetTemplateIssuerList
0x18006d26e  mov     [rsp+2D0h+var_2A0], eax
0x18006d272  mov     ebx, eax
0x18006d274  cmp     eax, 8004020Dh
0x18006d279  jnz     short loc_18006D2A4
0x18006d27b  and     [rbp+1D0h+var_200], 0FFFFFFFDh
0x18006d27f  lea     r8, [rbp+1D0h+var_210]
0x18006d283  mov     [rsp+2D0h+var_298], eax
0x18006d287  xor     r9d, r9d
0x18006d28a  lea     rax, [rsp+2D0h+var_288]
0x18006d28f  xor     edx, edx
0x18006d291  xor     ecx, ecx
0x18006d293  mov     [rsp+2D0h+var_2B0], rax
0x18006d298  call    cs:__imp_IpcGetTemplateIssuerList
0x18006d29e  mov     ebx, eax
0x18006d2a0  mov     [rsp+2D0h+var_2A0], eax
0x18006d2a4  test    eax, eax
0x18006d2a6  js      loc_18006D3CF
0x18006d2ac  mov     rcx, [rsp+2D0h+var_288]
0x18006d2b1  cmp     dword ptr [rcx], 1
0x18006d2b4  jz      short loc_18006D2C4
0x18006d2b6  mov     ebx, 8007064Ah
0x18006d2bb  mov     [rsp+2D0h+var_2A0], ebx
0x18006d2bf  jmp     loc_18006D3CF
0x18006d2c4  add     rcx, 8
0x18006d2c8  lea     r9, [rsp+2D0h+var_290]
0x18006d2cd  xor     r8d, r8d
0x18006d2d0  xor     edx, edx
0x18006d2d2  call    cs:__imp_IpcCreateLicenseFromScratch
0x18006d2d8  mov     [rsp+2D0h+var_2A0], eax
0x18006d2dc  mov     ebx, eax
0x18006d2de  test    eax, eax
0x18006d2e0  js      loc_18006D3CF
0x18006d2e6  mov     rcx, [rsp+2D0h+var_290]
0x18006d2eb  lea     rax, [rsp+2D0h+var_280]
0x18006d2f0  mov     [rbp+1D0h+var_70], rax
0x18006d2f7  lea     r9, [rbp+1D0h+var_90]
0x18006d2fe  xor     edx, edx
0x18006d300  mov     [rbp+1D0h+var_90], 50h ; 'P'
0x18006d30a  lea     rax, aAnyone; "ANYONE"
0x18006d311  mov     [rbp+1D0h+var_8C], 2
0x18006d31b  mov     [rbp+1D0h+var_60], rax
0x18006d322  lea     rax, [rsp+2D0h+var_280]
0x18006d327  mov     [rbp+1D0h+var_50], rax
0x18006d32e  lea     r8d, [rdx+4]
0x18006d332  mov     [rbp+1D0h+var_88], 2
0x18006d33c  mov     [rbp+1D0h+var_80], r13
0x18006d343  mov     [rbp+1D0h+var_78], 1
0x18006d34d  mov     [rbp+1D0h+var_68], 2
0x18006d357  mov     [rbp+1D0h+var_58], 1
0x18006d361  call    cs:__imp_IpcSetLicenseProperty
0x18006d367  jmp     short loc_18006D3B4
0x18006d369  lea     r9, [rsp+2D0h+var_290]
0x18006d36e  xor     r8d, r8d
0x18006d371  mov     rcx, rdi
0x18006d374  call    cs:__imp_IpcCreateLicenseFromTemplateID
0x18006d37a  mov     [rsp+2D0h+var_2A0], eax
0x18006d37e  mov     ebx, eax
0x18006d380  cmp     eax, 8004020Dh
0x18006d385  jz      short loc_18006D38E
0x18006d387  cmp     eax, 80070002h
0x18006d38c  jnz     short loc_18006D3BA
0x18006d38e  mov     [rsp+2D0h+var_298], eax
0x18006d392  call    ?ProvisionForCurrentUser@CRmsInterface@@QEAAJXZ; CRmsInterface::ProvisionForCurrentUser(void)
0x18006d397  mov     [rsp+2D0h+var_2A0], eax
0x18006d39b  mov     ebx, eax
0x18006d39d  test    eax, eax
0x18006d39f  js      short loc_18006D3CF
0x18006d3a1  lea     r9, [rsp+2D0h+var_290]
0x18006d3a6  xor     r8d, r8d
0x18006d3a9  xor     edx, edx
0x18006d3ab  mov     rcx, rdi
0x18006d3ae  call    cs:__imp_IpcCreateLicenseFromTemplateID
0x18006d3b4  mov     [rsp+2D0h+var_2A0], eax
0x18006d3b8  mov     ebx, eax
0x18006d3ba  test    eax, eax
0x18006d3bc  js      short loc_18006D3CF
0x18006d3be  mov     rax, [rsp+2D0h+var_290]
0x18006d3c3  mov     [rsi], rax
0x18006d3c6  mov     [rsp+2D0h+var_290], 0
0x18006d3cf  test    rdi, rdi
0x18006d3d2  lea     r8, [rsp+2D0h+var_2A0]
0x18006d3d7  lea     rdx, [rsp+2D0h+var_298]
0x18006d3dc  lea     rcx, [rsp+2D0h+var_29C]
0x18006d3e1  setnz   [rsp+2D0h+var_29C]
0x18006d3e6  call    ??$LogRmsCreateLicense@_NAEAJAEAJ@RmsCreateLicense@EfsTelemetry@@SAX$$QEA_NAEAJ1@Z; EfsTelemetry::RmsCreateLicense::LogRmsCreateLicense<bool,long &,long &>(bool &&,long &,long &)
0x18006d3eb  mov     rcx, [rsp+2D0h+var_288]
0x18006d3f0  test    rcx, rcx
0x18006d3f3  jz      short loc_18006D3FB
0x18006d3f5  call    cs:__imp_IpcFreeMemory
0x18006d3fb  mov     rcx, [rsp+2D0h+var_290]
0x18006d400  test    rcx, rcx
0x18006d403  jz      short loc_18006D40B
0x18006d405  call    cs:__imp_IpcCloseHandle
0x18006d40b  lea     rcx, [rbp+1D0h+var_1E0]
0x18006d40f  call    ?Stop@?$ActivityBase@VEfsTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006d414  lea     rcx, [rbp+1D0h+var_1E0]; this
0x18006d418  call    ??1RmsCreateLicense@EfsTelemetry@@QEAA@XZ; EfsTelemetry::RmsCreateLicense::~RmsCreateLicense(void)
0x18006d41d  lea     rcx, [rsp+2D0h+var_258]
0x18006d422  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006d427  mov     eax, ebx
0x18006d429  mov     rcx, [rbp+1D0h+var_20]
0x18006d430  xor     rcx, rsp; StackCookie
0x18006d433  call    __security_check_cookie
0x18006d438  lea     r11, [rsp+2D0h+var_10]
0x18006d440  mov     rbx, [r11+20h]
0x18006d444  mov     rsi, [r11+38h]
0x18006d448  mov     rsp, r11
0x18006d44b  pop     r13
0x18006d44d  pop     rdi
0x18006d44e  pop     rbp
0x18006d44f  retn
```
