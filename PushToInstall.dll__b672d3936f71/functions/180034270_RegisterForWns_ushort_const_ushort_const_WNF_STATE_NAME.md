# RegisterForWns(ushort const *,ushort const *,_WNF_STATE_NAME *)

- ea: `0x180034270`
- end: `0x18003472b`
- name: `?RegisterForWns@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0PEAU_WNF_STATE_NAME@@@Z`
- size: `1211`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002c4b8`
- `0x18002ce54`
- `0x18002d674`
- `0x18002fbb4`
- `0x180033e38`
- `0x180034270`
- `0x180034734`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034367`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180034367`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180034318`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180034318`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18003432a`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x18003432a`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800343af`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800343af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800344ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800344ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003455b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800345e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003455b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800345e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034353`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180034353`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800344c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800344c9`

## string_xrefs

- `0x1800342a9`: `Microsoft.Windows.PushToInstall`
- `0x18003446d`: `Microsoft.Windows.PushToInstall`
- `0x180034474`: `Microsoft.Windows.PushToInstall_cw5n1h2txyewy`
- `0x1800342b4`: `Attempting to register with the notification service.`
- `0x1800342d3`: `onecoreuap\enduser\winstore\pushtoinstall\lib\wnschannel.cpp`
- `0x1800343bd`: `onecoreuap\enduser\winstore\pushtoinstall\lib\wnschannel.cpp`
- `0x1800345b6`: `Registration successful. Returning the retrieved URI.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RegisterForWns(__int64 a1)
{
  LPVOID v2; // rcx
  int v3; // edi
  bool v4; // bl
  GUID *v5; // rcx
  HRESULT InstanceAsUser; // eax
  int v7; // ebx
  int DefaultUserContextToken; // eax
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v12; // rcx
  int v13; // eax
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  int v15; // eax
  HRESULT v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *); // rbx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  LPVOID v36; // rcx
  GUID *ppv; // [rsp+20h] [rbp-69h]
  LPVOID v39; // [rsp+40h] [rbp-49h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-41h] BYREF
  __int64 v41; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v42; // [rsp+58h] [rbp-31h] BYREF
  __int64 v43; // [rsp+60h] [rbp-29h] BYREF
  __int64 v44; // [rsp+68h] [rbp-21h] BYREF
  __int64 v45; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int64 v46; // [rsp+78h] [rbp-11h] BYREF
  const wchar_t *v47; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+B0h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v47 = L"Microsoft.Windows.PushToInstall";
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
    0x15u,
    "RegisterForWns",
    -1,
    L"Attempting to register with the notification service.");
  v2 = 0;
  v3 = 1;
  while ( 1 )
  {
    if ( v2 )
    {
      v39 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
    v39 = 0;
    LODWORD(v40) = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v40, 0);
    v4 = (unsigned int)((_DWORD)v40 - 7) <= 1;
    if ( (unsigned __int8)RtlIsMultiUsersInSessionSku() || v4 )
    {
      v46 = 0;
      DefaultUserContextToken = _GetDefaultUserContextToken(&v46);
      v5 = &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c;
      if ( DefaultUserContextToken >= 0 )
      {
        ppv = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
        InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, v46);
        goto LABEL_8;
      }
    }
    else
    {
      v5 = &GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9;
    }
    InstanceAsUser = CoCreateInstance(v5, 0, 0x404u, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v39);
LABEL_8:
    v7 = InstanceAsUser;
    if ( InstanceAsUser != -2147221164 )
      break;
    Sleep(0xEA60u);
    if ( ++v3 > 5 )
      break;
    v2 = v39;
  }
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v7,
      (int)ppv);
  v41 = 0;
  v40 = 0;
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v39 + 40LL))(
         v39,
         &v40);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v9,
      (int)ppv);
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  v11 = **v40;
  v12 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = v11(v10, &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49, &v41);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v13,
      (int)ppv);
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  if ( v40 )
  {
    v40 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
  }
  v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v41 + 24LL))(
          v41,
          L"Microsoft.Windows.PushToInstall_cw5n1h2txyewy",
          L"Microsoft.Windows.PushToInstall",
          2304);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v15,
      8);
  v45 = 0;
  string = 0;
  v16 = WindowsCreateStringReference(
          L"Windows.Networking.PushNotifications.PushNotificationChannelManager",
          0x43u,
          &hstringHeader,
          &string);
  if ( v16 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
LABEL_47:
    wil::details::in1diag3::_Throw_Hr(
      v20,
      (void *)0x37,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)ActivationFactory,
      8);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0, &v45);
  v20 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_47;
  v44 = 0;
  v21 = v45;
  v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 56LL);
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v47);
  v24 = v22(v21, *(_QWORD *)(v23 + 24), &v44);
  if ( v24 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v24,
      8);
  v43 = 0;
  v25 = v44;
  v26 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(v44);
  if ( v26 >= 0 )
    v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 64LL))(v25, &v43);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v26,
      8);
  v42 = 0;
  v27 = v43;
  v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 48LL);
  WindowsDeleteString(0);
  v42 = 0;
  v29 = v28(v27, &v42);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
      (const char *)(unsigned int)v29,
      8);
  StringRawBuffer = WindowsGetStringRawBuffer(v42, 0);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v31 = -1;
  do
    ++v31;
  while ( StringRawBuffer[v31] );
  std::wstring::_Construct<1,unsigned short const *>(a1, StringRawBuffer, v31);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\wnschannel.cpp",
    0x44u,
    "RegisterForWns",
    -1,
    L"Registration successful. Returning the retrieved URI.");
  WindowsDeleteString(v42);
  v42 = 0;
  v32 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
  }
  return a1;
}

```

## disassembly

```asm
0x180034270  mov     [rsp-8+arg_8], rbx
0x180034275  mov     [rsp-8+arg_10], rsi
0x18003427a  push    rbp
0x18003427b  push    rdi
0x18003427c  push    r12
0x18003427e  push    r14
0x180034280  push    r15
0x180034282  lea     rbp, [rsp-37h]
0x180034287  sub     rsp, 0C0h
0x18003428e  mov     rax, cs:__security_cookie
0x180034295  xor     rax, rsp
0x180034298  mov     [rbp+57h+var_28], rax
0x18003429c  mov     r14, r9
0x18003429f  mov     rsi, rcx
0x1800342a2  mov     [rbp+57h+var_60], rcx
0x1800342a6  xor     r15d, r15d
0x1800342a9  lea     rax, aMicrosoftWindo_1; "Microsoft.Windows.PushToInstall"
0x1800342b0  mov     [rbp+57h+var_60], rax
0x1800342b4  lea     rax, aAttemptingToRe; "Attempting to register with the notific"...
0x1800342bb  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x1800342c0  mov     dword ptr [rsp+0E0h+ppv], 0FFFFFFFFh; int
0x1800342c8  lea     r9, aRegisterforwns; "RegisterForWns"
0x1800342cf  lea     r8d, [r15+15h]; unsigned int
0x1800342d3  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800342da  lea     ecx, [r15+3]; unsigned int
0x1800342de  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800342e3  mov     ecx, r15d
0x1800342e6  lea     edi, [r15+1]
0x1800342ea  lea     r12, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800342f1  test    rcx, rcx
0x1800342f4  jz      short loc_180034307
0x1800342f6  mov     [rbp+57h+var_A0], r15
0x1800342fa  mov     rax, [rcx]
0x1800342fd  mov     rax, [rax+10h]
0x180034301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034306  nop
0x180034307  mov     [rbp+57h+var_A0], r15
0x18003430b  mov     dword ptr [rbp+57h+var_98], r15d
0x18003430f  xor     r8d, r8d
0x180034312  lea     rdx, [rbp+57h+var_98]
0x180034316  xor     ecx, ecx
0x180034318  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003431e  mov     eax, dword ptr [rbp+57h+var_98]
0x180034321  add     eax, 0FFFFFFF9h
0x180034324  cmp     eax, 1
0x180034327  setbe   bl
0x18003432a  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180034330  test    al, al
0x180034332  jnz     short loc_18003437D
0x180034334  test    bl, bl
0x180034336  jnz     short loc_18003437D
0x180034338  lea     rcx, _GUID_1fd1b5a7_5c96_4711_a7c3_fff6d21f93d9; rclsid
0x18003433f  lea     rax, [rbp+57h+var_A0]
0x180034343  mov     [rsp+0E0h+ppv], rax; int
0x180034348  mov     r9, r12; riid
0x18003434b  mov     r8d, 404h; dwClsContext
0x180034351  xor     edx, edx; pUnkOuter
0x180034353  call    cs:__imp_CoCreateInstance
0x180034359  mov     ebx, eax
0x18003435b  cmp     eax, 80040154h
0x180034360  jnz     short loc_1800343B7
0x180034362  mov     ecx, 0EA60h; dwMilliseconds
0x180034367  call    cs:__imp_Sleep
0x18003436d  inc     edi
0x18003436f  cmp     edi, 5
0x180034372  jg      short loc_1800343B7
0x180034374  mov     rcx, [rbp+57h+var_A0]
0x180034378  jmp     loc_1800342F1
0x18003437d  mov     [rbp+57h+var_68], r15
0x180034381  lea     rcx, [rbp+57h+var_68]; unsigned __int64 *
0x180034385  call    ?_GetDefaultUserContextToken@@YAJPEA_K@Z; _GetDefaultUserContextToken(unsigned __int64 *)
0x18003438a  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180034391  test    eax, eax
0x180034393  js      short loc_18003433F
0x180034395  lea     rax, [rbp+57h+var_A0]
0x180034399  mov     [rsp+0E0h+var_B8], rax
0x18003439e  mov     [rsp+0E0h+ppv], r12
0x1800343a3  mov     r9, [rbp+57h+var_68]
0x1800343a7  xor     edx, edx
0x1800343a9  mov     r8d, 404h
0x1800343af  call    cs:__imp_CoCreateInstanceAsUser
0x1800343b5  jmp     short loc_180034359
0x1800343b7  mov     rcx, [rbp+5Fh]; this
0x1800343bb  test    ebx, ebx
0x1800343bd  lea     r12, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800343c4  js      loc_1800346AC
0x1800343ca  mov     [rbp+57h+var_90], r15
0x1800343ce  mov     [rbp+57h+var_98], r15
0x1800343d2  mov     rcx, [rbp+57h+var_A0]
0x1800343d6  mov     rax, [rcx]
0x1800343d9  lea     rdx, [rbp+57h+var_98]
0x1800343dd  mov     rax, [rax+28h]
0x1800343e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343e6  mov     rcx, [rbp+5Fh]; this
0x1800343ea  test    eax, eax
0x1800343ec  js      loc_1800346BD
0x1800343f2  mov     rbx, [rbp+57h+var_98]
0x1800343f6  mov     rax, [rbx]
0x1800343f9  mov     rdi, [rax]
0x1800343fc  mov     rcx, [rbp+57h+var_90]
0x180034400  test    rcx, rcx
0x180034403  jz      short loc_180034416
0x180034405  mov     [rbp+57h+var_90], r15
0x180034409  mov     rax, [rcx]
0x18003440c  mov     rax, [rax+10h]
0x180034410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034415  nop
0x180034416  lea     r8, [rbp+57h+var_90]
0x18003441a  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x180034421  mov     rcx, rbx
0x180034424  mov     rax, rdi
0x180034427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003442c  nop
0x18003442d  mov     rcx, [rbp+5Fh]; this
0x180034431  test    eax, eax
0x180034433  js      loc_1800346CE
0x180034439  mov     rcx, [rbp+57h+var_98]
0x18003443d  test    rcx, rcx
0x180034440  jz      short loc_180034453
0x180034442  mov     [rbp+57h+var_98], r15
0x180034446  mov     rax, [rcx]
0x180034449  mov     rax, [rax+10h]
0x18003444d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034452  nop
0x180034453  mov     rcx, [rbp+57h+var_90]
0x180034457  mov     rax, [rcx]
0x18003445a  mov     [rsp+0E0h+var_B8], r14
0x18003445f  mov     dword ptr [rsp+0E0h+ppv], 8; int
0x180034467  mov     r9d, 900h
0x18003446d  lea     r8, aMicrosoftWindo_1; "Microsoft.Windows.PushToInstall"
0x180034474  lea     rdx, aMicrosoftWindo_0; "Microsoft.Windows.PushToInstall_cw5n1h2"...
0x18003447b  mov     rax, [rax+18h]
0x18003447f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034484  mov     rcx, [rbp+5Fh]; this
0x180034488  test    eax, eax
0x18003448a  js      loc_1800346DF
0x180034490  mov     [rbp+57h+var_70], r15
0x180034494  mov     [rbp+57h+string], r15
0x180034498  lea     r9, [rbp+57h+string]; string
0x18003449c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800344a0  mov     edx, 43h ; 'C'; length
0x1800344a5  lea     rcx, ?RuntimeClass_Windows_Networking_PushNotifications_PushNotificationChannelManager@@3QBGB; "Windows.Networking.PushNotifications.Pu"...
0x1800344ac  call    cs:__imp_WindowsCreateStringReference
0x1800344b2  test    eax, eax
0x1800344b4  js      loc_1800346F0
0x1800344ba  lea     r8, [rbp+57h+var_70]
0x1800344be  lea     rdx, _GUID_8baf9b65_77a1_4588_bd19_861529a9dcf0
0x1800344c5  mov     rcx, [rbp+57h+string]
0x1800344c9  call    cs:__imp_RoGetActivationFactory
0x1800344cf  mov     rcx, [rbp+5Fh]
0x1800344d3  test    eax, eax
0x1800344d5  js      loc_1800346F8
0x1800344db  mov     [rbp+57h+var_78], r15
0x1800344df  mov     rdi, [rbp+57h+var_70]
0x1800344e3  mov     rax, [rdi]
0x1800344e6  mov     rbx, [rax+38h]
0x1800344ea  lea     rdx, [rbp+57h+var_60]
0x1800344ee  lea     rcx, [rbp+57h+hstringHeader]
0x1800344f2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800344f7  nop
0x1800344f8  lea     r8, [rbp+57h+var_78]
0x1800344fc  mov     rdx, [rax+18h]
0x180034500  mov     rcx, rdi
0x180034503  mov     rax, rbx
0x180034506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003450b  mov     rcx, [rbp+5Fh]; this
0x18003450f  test    eax, eax
0x180034511  js      loc_180034709
0x180034517  mov     [rbp+57h+var_80], r15
0x18003451b  mov     rbx, [rbp+57h+var_78]
0x18003451f  mov     rcx, rbx
0x180034522  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVPushNotificationChannel@PushNotifications@Networking@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Networking::PushNotifications::PushNotificationChannel *>,Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *>>(Windows::Foundation::IAsyncOperation<Windows::Networking::PushNotifications::PushNotificationChannel *> *,tagCOWAIT_FLAGS,void *)
0x180034527  test    eax, eax
0x180034529  js      short loc_18003453E
0x18003452b  mov     rax, [rbx]
0x18003452e  lea     rdx, [rbp+57h+var_80]
0x180034532  mov     rcx, rbx
0x180034535  mov     rax, [rax+40h]
0x180034539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003453e  mov     rcx, [rbp+5Fh]; this
0x180034542  test    eax, eax
0x180034544  js      loc_18003471A
0x18003454a  mov     [rbp+57h+var_88], r15
0x18003454e  mov     rdi, [rbp+57h+var_80]
0x180034552  mov     rax, [rdi]
0x180034555  mov     rbx, [rax+30h]
0x180034559  xor     ecx, ecx; string
0x18003455b  call    cs:__imp_WindowsDeleteString
0x180034561  mov     [rbp+57h+var_88], r15
0x180034565  lea     rdx, [rbp+57h+var_88]
0x180034569  mov     rcx, rdi
0x18003456c  mov     rax, rbx
0x18003456f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034574  mov     rcx, [rbp+5Fh]; this
0x180034578  test    eax, eax
0x18003457a  js      loc_18003469B
0x180034580  xor     edx, edx; length
0x180034582  mov     rcx, [rbp+57h+var_88]; string
0x180034586  call    cs:__imp_WindowsGetStringRawBuffer
0x18003458c  xorps   xmm0, xmm0
0x18003458f  movups  xmmword ptr [rsi], xmm0
0x180034592  mov     [rsi+10h], r15
0x180034596  mov     [rsi+18h], r15
0x18003459a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003459e  mov     r8, rbx
0x1800345a1  inc     r8
0x1800345a4  cmp     [rax+r8*2], r15w
0x1800345a9  jnz     short loc_1800345A1
0x1800345ab  mov     rdx, rax
0x1800345ae  mov     rcx, rsi
0x1800345b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800345b6  lea     rax, aRegistrationSu; "Registration successful. Returning the "...
0x1800345bd  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x1800345c2  mov     dword ptr [rsp+0E0h+ppv], ebx; int
0x1800345c6  lea     r9, aRegisterforwns; "RegisterForWns"
0x1800345cd  mov     r8d, 44h ; 'D'; unsigned int
0x1800345d3  mov     rdx, r12; char *
0x1800345d6  lea     ecx, [r8-41h]; unsigned int
0x1800345da  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800345df  nop
0x1800345e0  mov     rcx, [rbp+57h+var_88]; string
0x1800345e4  call    cs:__imp_WindowsDeleteString
0x1800345ea  mov     [rbp+57h+var_88], r15
0x1800345ee  mov     rcx, [rbp+57h+var_80]
0x1800345f2  test    rcx, rcx
0x1800345f5  jz      short loc_180034608
0x1800345f7  mov     [rbp+57h+var_80], r15
0x1800345fb  mov     rax, [rcx]
0x1800345fe  mov     rax, [rax+10h]
0x180034602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034607  nop
0x180034608  mov     rcx, [rbp+57h+var_78]
0x18003460c  test    rcx, rcx
0x18003460f  jz      short loc_180034622
0x180034611  mov     [rbp+57h+var_78], r15
0x180034615  mov     rax, [rcx]
0x180034618  mov     rax, [rax+10h]
0x18003461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034621  nop
0x180034622  mov     rcx, [rbp+57h+var_70]
0x180034626  test    rcx, rcx
0x180034629  jz      short loc_18003463C
0x18003462b  mov     [rbp+57h+var_70], r15
0x18003462f  mov     rax, [rcx]
0x180034632  mov     rax, [rax+10h]
0x180034636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003463b  nop
0x18003463c  mov     rcx, [rbp+57h+var_90]
0x180034640  test    rcx, rcx
0x180034643  jz      short loc_180034656
0x180034645  mov     [rbp+57h+var_90], r15
0x180034649  mov     rax, [rcx]
0x18003464c  mov     rax, [rax+10h]
0x180034650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034655  nop
0x180034656  mov     rcx, [rbp+57h+var_A0]
0x18003465a  test    rcx, rcx
0x18003465d  jz      short loc_180034670
0x18003465f  mov     [rbp+57h+var_A0], r15
0x180034663  mov     rdx, [rcx]
0x180034666  mov     rax, [rdx+10h]
0x18003466a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003466f  nop
0x180034670  mov     rax, rsi
0x180034673  mov     rcx, [rbp+57h+var_28]
0x180034677  xor     rcx, rsp; StackCookie
0x18003467a  call    __security_check_cookie
0x18003467f  lea     r11, [rsp+0E0h+var_20]
0x180034687  mov     rbx, [r11+38h]
0x18003468b  mov     rsi, [r11+40h]
0x18003468f  mov     rsp, r11
0x180034692  pop     r15
0x180034694  pop     r14
0x180034696  pop     r12
0x180034698  pop     rdi
0x180034699  pop     rbp
0x18003469a  retn
0x18003469b  mov     r9d, eax; char *
0x18003469e  mov     r8, r12; unsigned int
0x1800346a1  mov     edx, 40h ; '@'; void *
0x1800346a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800346ac  mov     r9d, ebx; char *
0x1800346af  mov     r8, r12; unsigned int
0x1800346b2  mov     edx, 26h ; '&'; void *
0x1800346b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800346bd  mov     r9d, eax; char *
0x1800346c0  mov     r8, r12; unsigned int
0x1800346c3  mov     edx, 2Bh ; '+'; void *
0x1800346c8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800346ce  mov     r9d, eax; char *
0x1800346d1  mov     r8, r12; unsigned int
0x1800346d4  mov     edx, 2Ch ; ','; void *
0x1800346d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800346df  mov     r9d, eax; char *
0x1800346e2  mov     r8, r12; unsigned int
0x1800346e5  mov     edx, 32h ; '2'; void *
0x1800346ea  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800346f0  mov     ecx, eax; this
0x1800346f2  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800346f7  nop
  ... truncated ...
```
