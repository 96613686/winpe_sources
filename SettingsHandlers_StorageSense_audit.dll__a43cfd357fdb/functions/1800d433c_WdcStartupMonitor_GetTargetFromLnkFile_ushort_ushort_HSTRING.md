# WdcStartupMonitor::GetTargetFromLnkFile(ushort *,ushort *,HSTRING__ * *)

- ea: `0x1800d433c`
- end: `0x1800d48d7`
- name: `?GetTargetFromLnkFile@WdcStartupMonitor@@QEAAJPEAG0PEAPEAUHSTRING__@@@Z`
- size: `1435`
- prototype: `int(WdcStartupMonitor *__hidden this, unsigned __int16 *, unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d4d24`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18000f07c`
- `0x18004e674`
- `0x1800cd34c`
- `0x1800d433c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d43b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d43b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d43dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d43ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d44e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d44f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d45e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d45f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d472d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d473d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d47ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d47bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d486c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d487c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d43dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d43ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d445c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d446c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d44e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d44f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d45e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d45f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d472d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d473d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d47ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d47bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d4834`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d486c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d487c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d45a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d45a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WdcStartupMonitor::GetTargetFromLnkFile(
        WdcStartupMonitor *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        HSTRING *a4)
{
  int v6; // edi
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, PCWSTR, _QWORD); // rbx
  PCWSTR StringRawBuffer; // rax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // edi
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  HSTRING v29; // rax
  __int64 v30; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int *ppvb; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v36; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v38; // [rsp+48h] [rbp-B8h] BYREF
  int v39[132]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[528]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v41[1024]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CA8h] [rbp+BA8h]

  v6 = (int)a2;
  v38 = 0;
  v37 = 0;
  v36 = 0;
  string = 0;
  Microsoft::WRL::ComPtr<IShellLinkW>::InternalRelease(&v38);
  v7 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &v38);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x705,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v7,
      ppv);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    goto LABEL_41;
  }
  v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v38)(v38, &IID_IPersistFile, &v37);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70A,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    v10 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    goto LABEL_41;
  }
  ppva = v6;
  v11 = StringCchPrintfW(v41, 0x400u, L"%s\\%s", a3);
  v8 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70C,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v11,
      v6);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    v12 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_41;
  }
  v13 = Microsoft::WRL::Wrappers::HString::Set<260>(&v36, v41);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70E,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v13,
      v6);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    v14 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_41;
  }
  v15 = v37;
  v16 = *(__int64 (__fastcall **)(__int64, PCWSTR, _QWORD))(*(_QWORD *)v37 + 40LL);
  StringRawBuffer = WindowsGetStringRawBuffer(v36, 0);
  v18 = v16(v15, StringRawBuffer, 0);
  v8 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x710,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v18,
      ppva);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    v19 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    goto LABEL_41;
  }
  LODWORD(ppvb) = 4;
  v20 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, __int64, _QWORD))(*(_QWORD *)v38 + 24LL))(v38, v40, 260, 0);
  v8 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x715,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v20,
      4);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v36);
    v36 = 0;
    v21 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_41;
  }
  v22 = (*(__int64 (__fastcall **)(LPVOID, int *, __int64))(*(_QWORD *)v38 + 80LL))(v38, v39, 260);
  if ( v22 >= 0 && LOWORD(v39[0]) )
  {
    ppvb = v39;
    v23 = StringCchPrintfW(v41, 0x400u, L"%s %s", v40);
    v8 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x721,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
        (const char *)(unsigned int)v23,
        (int)v39);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v36);
      v36 = 0;
      v24 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      goto LABEL_41;
    }
    goto LABEL_34;
  }
  v25 = StringCchPrintfW(v41, 0x400u, L"%s", v40);
  v8 = v25;
  if ( v25 >= 0 )
  {
    v22 = 0;
LABEL_34:
    v27 = Microsoft::WRL::Wrappers::HString::Set<260>(&string, v41);
    v8 = v27;
    if ( v27 >= 0 )
    {
      v29 = string;
      string = 0;
      *a4 = v29;
      WindowsDeleteString(0);
      string = 0;
      WindowsDeleteString(v36);
      v36 = 0;
      v30 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v8 = v22;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72C,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
        (const char *)(unsigned int)v27,
        (int)ppvb);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v36);
      v36 = 0;
      v28 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
    }
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x729,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
    (const char *)(unsigned int)v25,
    4);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v36);
  v36 = 0;
  v26 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
LABEL_41:
  Microsoft::WRL::ComPtr<IShellLinkW>::InternalRelease(&v38);
  return v8;
}

```

## disassembly

```asm
0x1800d433c  mov     [rsp-8+arg_0], rbx
0x1800d4341  push    rbp
0x1800d4342  push    rsi
0x1800d4343  push    rdi
0x1800d4344  push    r14
0x1800d4346  push    r15
0x1800d4348  lea     rbp, [rsp-0B80h]
0x1800d4350  sub     rsp, 0C80h
0x1800d4357  mov     rax, cs:__security_cookie
0x1800d435e  xor     rax, rsp
0x1800d4361  mov     [rbp+0BA0h+var_30], rax
0x1800d4368  mov     r14, r9
0x1800d436b  mov     rsi, r8
0x1800d436e  mov     rdi, rdx
0x1800d4371  xor     r15d, r15d
0x1800d4374  mov     [rsp+0CA0h+var_C58], r15
0x1800d4379  mov     [rsp+0CA0h+var_C60], r15
0x1800d437e  mov     [rsp+0CA0h+var_C68], r15
0x1800d4383  mov     [rsp+0CA0h+string], r15
0x1800d4388  lea     rcx, [rsp+0CA0h+var_C58]
0x1800d438d  call    ?InternalRelease@?$ComPtr@UIShellLinkW@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IShellLinkW>::InternalRelease(void)
0x1800d4392  lea     rax, [rsp+0CA0h+var_C58]
0x1800d4397  mov     [rsp+0CA0h+ppv], rax; int
0x1800d439c  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x1800d43a3  xor     edx, edx; pUnkOuter
0x1800d43a5  lea     r8d, [r15+1]; dwClsContext
0x1800d43a9  lea     rcx, CLSID_ShellLink; rclsid
0x1800d43b0  call    cs:__imp_CoCreateInstance
0x1800d43b6  mov     ebx, eax
0x1800d43b8  test    eax, eax
0x1800d43ba  jns     short loc_1800D4419
0x1800d43bc  mov     rcx, [rbp+0BA8h]; this
0x1800d43c3  mov     r9d, eax; char *
0x1800d43c6  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d43cd  mov     edx, 705h; void *
0x1800d43d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d43d7  nop
0x1800d43d8  mov     rcx, [rsp+0CA0h+string]; string
0x1800d43dd  call    cs:__imp_WindowsDeleteString
0x1800d43e3  mov     [rsp+0CA0h+string], r15
0x1800d43e8  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d43ed  call    cs:__imp_WindowsDeleteString
0x1800d43f3  mov     [rsp+0CA0h+var_C68], r15
0x1800d43f8  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d43fd  test    rcx, rcx
0x1800d4400  jz      short loc_1800D4414
0x1800d4402  mov     [rsp+0CA0h+var_C60], r15
0x1800d4407  mov     rax, [rcx]
0x1800d440a  mov     rax, [rax+10h]
0x1800d440e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4413  nop
0x1800d4414  jmp     loc_1800D48A5
0x1800d4419  mov     rcx, [rsp+0CA0h+var_C58]
0x1800d441e  mov     rax, [rcx]
0x1800d4421  lea     r8, [rsp+0CA0h+var_C60]
0x1800d4426  lea     rdx, IID_IPersistFile
0x1800d442d  mov     rax, [rax]
0x1800d4430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4435  mov     ebx, eax
0x1800d4437  test    eax, eax
0x1800d4439  jns     short loc_1800D4498
0x1800d443b  mov     rcx, [rbp+0BA8h]; this
0x1800d4442  mov     r9d, eax; char *
0x1800d4445  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d444c  mov     edx, 70Ah; void *
0x1800d4451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4456  nop
0x1800d4457  mov     rcx, [rsp+0CA0h+string]; string
0x1800d445c  call    cs:__imp_WindowsDeleteString
0x1800d4462  mov     [rsp+0CA0h+string], r15
0x1800d4467  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d446c  call    cs:__imp_WindowsDeleteString
0x1800d4472  mov     [rsp+0CA0h+var_C68], r15
0x1800d4477  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d447c  test    rcx, rcx
0x1800d447f  jz      short loc_1800D4493
0x1800d4481  mov     [rsp+0CA0h+var_C60], r15
0x1800d4486  mov     rax, [rcx]
0x1800d4489  mov     rax, [rax+10h]
0x1800d448d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4492  nop
0x1800d4493  jmp     loc_1800D48A5
0x1800d4498  mov     [rsp+0CA0h+ppv], rdi; int
0x1800d449d  mov     r9, rsi
0x1800d44a0  lea     r8, aSS_0; "%s\\%s"
0x1800d44a7  mov     esi, 400h
0x1800d44ac  mov     edx, esi; unsigned __int64
0x1800d44ae  lea     rcx, [rbp+0BA0h+var_830]; unsigned __int16 *
0x1800d44b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d44ba  mov     ebx, eax
0x1800d44bc  test    eax, eax
0x1800d44be  jns     short loc_1800D451D
0x1800d44c0  mov     rcx, [rbp+0BA8h]; this
0x1800d44c7  mov     r9d, eax; char *
0x1800d44ca  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d44d1  mov     edx, 70Ch; void *
0x1800d44d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d44db  nop
0x1800d44dc  mov     rcx, [rsp+0CA0h+string]; string
0x1800d44e1  call    cs:__imp_WindowsDeleteString
0x1800d44e7  mov     [rsp+0CA0h+string], r15
0x1800d44ec  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d44f1  call    cs:__imp_WindowsDeleteString
0x1800d44f7  mov     [rsp+0CA0h+var_C68], r15
0x1800d44fc  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d4501  test    rcx, rcx
0x1800d4504  jz      short loc_1800D4518
0x1800d4506  mov     [rsp+0CA0h+var_C60], r15
0x1800d450b  mov     rax, [rcx]
0x1800d450e  mov     rax, [rax+10h]
0x1800d4512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4517  nop
0x1800d4518  jmp     loc_1800D48A5
0x1800d451d  lea     rdx, [rbp+0BA0h+var_830]
0x1800d4524  lea     rcx, [rsp+0CA0h+var_C68]
0x1800d4529  call    ??$Set@$0BAE@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HString::Set<260>(ushort (&)[260])
0x1800d452e  mov     ebx, eax
0x1800d4530  test    eax, eax
0x1800d4532  jns     short loc_1800D4591
0x1800d4534  mov     rcx, [rbp+0BA8h]; this
0x1800d453b  mov     r9d, eax; char *
0x1800d453e  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d4545  mov     edx, 70Eh; void *
0x1800d454a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d454f  nop
0x1800d4550  mov     rcx, [rsp+0CA0h+string]; string
0x1800d4555  call    cs:__imp_WindowsDeleteString
0x1800d455b  mov     [rsp+0CA0h+string], r15
0x1800d4560  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d4565  call    cs:__imp_WindowsDeleteString
0x1800d456b  mov     [rsp+0CA0h+var_C68], r15
0x1800d4570  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d4575  test    rcx, rcx
0x1800d4578  jz      short loc_1800D458C
0x1800d457a  mov     [rsp+0CA0h+var_C60], r15
0x1800d457f  mov     rax, [rcx]
0x1800d4582  mov     rax, [rax+10h]
0x1800d4586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d458b  nop
0x1800d458c  jmp     loc_1800D48A5
0x1800d4591  mov     rdi, [rsp+0CA0h+var_C60]
0x1800d4596  mov     rax, [rdi]
0x1800d4599  mov     rbx, [rax+28h]
0x1800d459d  xor     edx, edx; length
0x1800d459f  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d45a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d45aa  xor     r8d, r8d
0x1800d45ad  mov     rdx, rax
0x1800d45b0  mov     rcx, rdi
0x1800d45b3  mov     rax, rbx
0x1800d45b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d45bb  mov     ebx, eax
0x1800d45bd  test    eax, eax
0x1800d45bf  jns     short loc_1800D461E
0x1800d45c1  mov     rcx, [rbp+0BA8h]; this
0x1800d45c8  mov     r9d, eax; char *
0x1800d45cb  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d45d2  mov     edx, 710h; void *
0x1800d45d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d45dc  nop
0x1800d45dd  mov     rcx, [rsp+0CA0h+string]; string
0x1800d45e2  call    cs:__imp_WindowsDeleteString
0x1800d45e8  mov     [rsp+0CA0h+string], r15
0x1800d45ed  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d45f2  call    cs:__imp_WindowsDeleteString
0x1800d45f8  mov     [rsp+0CA0h+var_C68], r15
0x1800d45fd  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d4602  test    rcx, rcx
0x1800d4605  jz      short loc_1800D4619
0x1800d4607  mov     [rsp+0CA0h+var_C60], r15
0x1800d460c  mov     rax, [rcx]
0x1800d460f  mov     rax, [rax+10h]
0x1800d4613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4618  nop
0x1800d4619  jmp     loc_1800D48A5
0x1800d461e  mov     rcx, [rsp+0CA0h+var_C58]
0x1800d4623  mov     rax, [rcx]
0x1800d4626  mov     dword ptr [rsp+0CA0h+ppv], 4; int
0x1800d462e  xor     r9d, r9d
0x1800d4631  mov     edi, 104h
0x1800d4636  mov     r8d, edi
0x1800d4639  lea     rdx, [rbp+0BA0h+var_A40]
0x1800d4640  mov     rax, [rax+18h]
0x1800d4644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4649  mov     ebx, eax
0x1800d464b  test    eax, eax
0x1800d464d  jns     short loc_1800D46AC
0x1800d464f  mov     rcx, [rbp+0BA8h]; this
0x1800d4656  mov     r9d, eax; char *
0x1800d4659  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d4660  mov     edx, 715h; void *
0x1800d4665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d466a  nop
0x1800d466b  mov     rcx, [rsp+0CA0h+string]; string
0x1800d4670  call    cs:__imp_WindowsDeleteString
0x1800d4676  mov     [rsp+0CA0h+string], r15
0x1800d467b  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d4680  call    cs:__imp_WindowsDeleteString
0x1800d4686  mov     [rsp+0CA0h+var_C68], r15
0x1800d468b  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d4690  test    rcx, rcx
0x1800d4693  jz      short loc_1800D46A7
0x1800d4695  mov     [rsp+0CA0h+var_C60], r15
0x1800d469a  mov     rax, [rcx]
0x1800d469d  mov     rax, [rax+10h]
0x1800d46a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d46a6  nop
0x1800d46a7  jmp     loc_1800D48A5
0x1800d46ac  mov     rcx, [rsp+0CA0h+var_C58]
0x1800d46b1  mov     rax, [rcx]
0x1800d46b4  mov     r8d, edi
0x1800d46b7  lea     rdx, [rsp+0CA0h+var_C50]
0x1800d46bc  mov     rax, [rax+50h]
0x1800d46c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d46c5  mov     edi, eax
0x1800d46c7  test    eax, eax
0x1800d46c9  js      loc_1800D4769
0x1800d46cf  cmp     word ptr [rsp+0CA0h+var_C50], r15w
0x1800d46d5  jz      loc_1800D4769
0x1800d46db  lea     rax, [rsp+0CA0h+var_C50]
0x1800d46e0  mov     [rsp+0CA0h+ppv], rax; int
0x1800d46e5  lea     r9, [rbp+0BA0h+var_A40]
0x1800d46ec  lea     r8, aSS_1; "%s %s"
0x1800d46f3  mov     rdx, rsi; unsigned __int64
0x1800d46f6  lea     rcx, [rbp+0BA0h+var_830]; unsigned __int16 *
0x1800d46fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d4702  mov     ebx, eax
0x1800d4704  test    eax, eax
0x1800d4706  jns     loc_1800D47EC
0x1800d470c  mov     rcx, [rbp+0BA8h]; this
0x1800d4713  mov     r9d, eax; char *
0x1800d4716  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d471d  mov     edx, 721h; void *
0x1800d4722  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4727  nop
0x1800d4728  mov     rcx, [rsp+0CA0h+string]; string
0x1800d472d  call    cs:__imp_WindowsDeleteString
0x1800d4733  mov     [rsp+0CA0h+string], r15
0x1800d4738  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d473d  call    cs:__imp_WindowsDeleteString
0x1800d4743  mov     [rsp+0CA0h+var_C68], r15
0x1800d4748  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d474d  test    rcx, rcx
0x1800d4750  jz      short loc_1800D4764
0x1800d4752  mov     [rsp+0CA0h+var_C60], r15
0x1800d4757  mov     rax, [rcx]
0x1800d475a  mov     rax, [rax+10h]
0x1800d475e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4763  nop
0x1800d4764  jmp     loc_1800D48A5
0x1800d4769  lea     r9, [rbp+0BA0h+var_A40]
0x1800d4770  lea     r8, aS_1; "%s"
0x1800d4777  mov     rdx, rsi; unsigned __int64
0x1800d477a  lea     rcx, [rbp+0BA0h+var_830]; unsigned __int16 *
0x1800d4781  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d4786  mov     ebx, eax
0x1800d4788  test    eax, eax
0x1800d478a  jns     short loc_1800D47E9
0x1800d478c  mov     rcx, [rbp+0BA8h]; this
0x1800d4793  mov     r9d, eax; char *
0x1800d4796  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d479d  mov     edx, 729h; void *
0x1800d47a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d47a7  nop
0x1800d47a8  mov     rcx, [rsp+0CA0h+string]; string
0x1800d47ad  call    cs:__imp_WindowsDeleteString
0x1800d47b3  mov     [rsp+0CA0h+string], r15
0x1800d47b8  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d47bd  call    cs:__imp_WindowsDeleteString
0x1800d47c3  mov     [rsp+0CA0h+var_C68], r15
0x1800d47c8  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d47cd  test    rcx, rcx
0x1800d47d0  jz      short loc_1800D47E4
0x1800d47d2  mov     [rsp+0CA0h+var_C60], r15
0x1800d47d7  mov     rax, [rcx]
0x1800d47da  mov     rax, [rax+10h]
0x1800d47de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d47e3  nop
0x1800d47e4  jmp     loc_1800D48A5
0x1800d47e9  mov     edi, r15d
0x1800d47ec  lea     rdx, [rbp+0BA0h+var_830]
0x1800d47f3  lea     rcx, [rsp+0CA0h+string]
0x1800d47f8  call    ??$Set@$0BAE@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAE@G@Z; Microsoft::WRL::Wrappers::HString::Set<260>(ushort (&)[260])
0x1800d47fd  mov     ebx, eax
0x1800d47ff  test    eax, eax
0x1800d4801  jns     short loc_1800D485D
0x1800d4803  mov     rcx, [rbp+0BA8h]; this
0x1800d480a  mov     r9d, eax; char *
0x1800d480d  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d4814  mov     edx, 72Ch; void *
0x1800d4819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d481e  nop
0x1800d481f  mov     rcx, [rsp+0CA0h+string]; string
0x1800d4824  call    cs:__imp_WindowsDeleteString
0x1800d482a  mov     [rsp+0CA0h+string], r15
0x1800d482f  mov     rcx, [rsp+0CA0h+var_C68]; string
0x1800d4834  call    cs:__imp_WindowsDeleteString
0x1800d483a  mov     [rsp+0CA0h+var_C68], r15
0x1800d483f  mov     rcx, [rsp+0CA0h+var_C60]
0x1800d4844  test    rcx, rcx
  ... truncated ...
```
