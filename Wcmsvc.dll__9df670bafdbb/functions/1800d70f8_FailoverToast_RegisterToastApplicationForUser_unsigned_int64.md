# FailoverToast::RegisterToastApplicationForUser(unsigned __int64)

- ea: `0x1800d70f8`
- end: `0x1800d7524`
- name: `?RegisterToastApplicationForUser@FailoverToast@@CAJ_K@Z`
- size: `1068`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067e14`

## callees

- `0x180019434`
- `0x18001b710`
- `0x1800622cc`
- `0x180084f50`
- `0x1800d2ee8`
- `0x1800d70f8`
- `0x1800dc6dc`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d71b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7247`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d72cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7344`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d73d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7496`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d74f3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d71b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7247`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d72cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7344`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d73d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d7496`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800d74f3`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800d715f`
- `combase!__imp_CoCreateInstanceAsUser` at `0x1800d715f`

## string_xrefs

- `0x1800d7176`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d7204`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d7288`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d737d`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`
- `0x1800d7431`: `onecoreuap\net\wcm\service\base\toast\failovertoast.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall FailoverToast::RegisterToastApplicationForUser(__int64 a1)
{
  int InstanceAsUser; // eax
  unsigned int v3; // ebx
  char v4; // al
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, __int64 *); // rdi
  int v8; // eax
  unsigned int v9; // ebx
  char v10; // al
  int v11; // eax
  unsigned int v12; // ebx
  char v13; // al
  char v14; // al
  int v15; // eax
  unsigned int v16; // ebx
  char v17; // al
  __int64 v18; // rdi
  int v19; // eax
  unsigned int v20; // ebx
  char v21; // al
  char v22; // al
  _BYTE v23[8]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v24; // [rsp+48h] [rbp-40h] BYREF
  __int64 v25; // [rsp+50h] [rbp-38h] BYREF
  __int64 v26; // [rsp+58h] [rbp-30h] BYREF
  int v27; // [rsp+60h] [rbp-28h] BYREF
  __int64 v28; // [rsp+68h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  wil::CoInitializeEx(v23);
  v26 = 0;
  v25 = 0;
  v27 = 0;
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1048580, a1);
  v3 = InstanceAsUser;
  if ( InstanceAsUser >= 0 )
  {
    v6 = v26;
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
    if ( v25 )
      winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
    v8 = v7(v6, &v25);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *const, __int64, int *))(*(_QWORD *)v25 + 24LL))(
              v25,
              FailoverToast::aumId,
              2098180,
              &v27);
      v12 = v11;
      if ( v11 >= 0 )
      {
        if ( v27 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_36ba8b8ab71539cb7e9a28af59916125_Traceguids);
          }
          if ( v25 )
            winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
          if ( v26 )
            winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
          v14 = v23[0];
          v23[0] = 0;
          if ( v14 )
            CoUninitialize();
          return 0;
        }
        else
        {
          v28 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 40LL))(v26, &v28);
          v16 = v15;
          if ( v15 >= 0 )
          {
            winrt::impl::as<IWpnSystemRegistrationEndpoint,IWpnRegistrationEndpoint,0>(&v24, v28);
            v18 = v24;
            v19 = (*(__int64 (__fastcall **)(__int64, wchar_t *, unsigned __int16 *const, __int64))(*(_QWORD *)v24 + 24LL))(
                    v24,
                    FailoverToast::scope,
                    FailoverToast::aumId,
                    2098180);
            v20 = v19;
            if ( v19 >= 0 )
            {
              if ( v18 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v24);
              if ( v28 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v28);
              if ( v25 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
              if ( v26 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
              v22 = v23[0];
              v23[0] = 0;
              if ( v22 )
                CoUninitialize();
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBA,
                (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
                (const char *)(unsigned int)v19,
                0);
              if ( v18 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v24);
              if ( v28 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v28);
              if ( v25 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
              if ( v26 )
                winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
              v21 = v23[0];
              v23[0] = 0;
              if ( v21 )
                CoUninitialize();
              return v20;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB2,
              (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
              (const char *)(unsigned int)v15,
              (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
            if ( v28 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v28);
            if ( v25 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
            if ( v26 )
              winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
            v17 = v23[0];
            v23[0] = 0;
            if ( v17 )
              CoUninitialize();
            return v16;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAA,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
          (const char *)(unsigned int)v11,
          (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
        if ( v25 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
        if ( v26 )
          winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
        v13 = v23[0];
        v23[0] = 0;
        if ( v13 )
          CoUninitialize();
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
        (const char *)(unsigned int)v8,
        (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
      if ( v25 )
        winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
      if ( v26 )
        winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
      v10 = v23[0];
      v23[0] = 0;
      if ( v10 )
        CoUninitialize();
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\toast\\failovertoast.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)&GUID_df8e9480_ca73_448e_b8f0_da000f581428);
    if ( v25 )
      winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v25);
    if ( v26 )
      winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(&v26);
    v4 = v23[0];
    v23[0] = 0;
    if ( v4 )
      CoUninitialize();
    return v3;
  }
}

```

## disassembly

```asm
0x1800d70f8  mov     [rsp+arg_8], rbx
0x1800d70fd  mov     [rsp+arg_10], rsi
0x1800d7102  push    rdi
0x1800d7103  sub     rsp, 80h
0x1800d710a  mov     rax, cs:__security_cookie
0x1800d7111  xor     rax, rsp
0x1800d7114  mov     [rsp+88h+var_18], rax
0x1800d7119  mov     rbx, rcx
0x1800d711c  xor     esi, esi
0x1800d711e  lea     rcx, [rsp+88h+var_48]
0x1800d7123  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800d7128  nop
0x1800d7129  mov     [rsp+88h+var_30], rsi
0x1800d712e  mov     [rsp+88h+var_38], rsi
0x1800d7133  mov     [rsp+88h+var_28], esi
0x1800d7137  lea     rax, [rsp+88h+var_30]
0x1800d713c  mov     [rsp+88h+var_60], rax
0x1800d7141  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800d7148  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800d714d  mov     r9, rbx
0x1800d7150  xor     edx, edx
0x1800d7152  mov     r8d, 100004h
0x1800d7158  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x1800d715f  call    cs:__imp_CoCreateInstanceAsUser
0x1800d7165  mov     ebx, eax
0x1800d7167  test    eax, eax
0x1800d7169  jns     short loc_1800D71C6
0x1800d716b  mov     rcx, [rsp+88h]; this
0x1800d7173  mov     r9d, eax; char *
0x1800d7176  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d717d  mov     edx, 0A5h; void *
0x1800d7182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7187  nop
0x1800d7188  cmp     [rsp+88h+var_38], rsi
0x1800d718d  jz      short loc_1800D719A
0x1800d718f  lea     rcx, [rsp+88h+var_38]
0x1800d7194  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7199  nop
0x1800d719a  cmp     [rsp+88h+var_30], rsi
0x1800d719f  jz      short loc_1800D71AC
0x1800d71a1  lea     rcx, [rsp+88h+var_30]
0x1800d71a6  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d71ab  nop
0x1800d71ac  mov     al, [rsp+88h+var_48]
0x1800d71b0  mov     [rsp+88h+var_48], sil
0x1800d71b5  test    al, al
0x1800d71b7  jz      short loc_1800D71BF
0x1800d71b9  call    cs:__imp_CoUninitialize
0x1800d71bf  mov     eax, ebx
0x1800d71c1  jmp     loc_1800D7501
0x1800d71c6  mov     rbx, [rsp+88h+var_30]
0x1800d71cb  mov     rax, [rbx]
0x1800d71ce  mov     rdi, [rax+30h]
0x1800d71d2  cmp     [rsp+88h+var_38], rsi
0x1800d71d7  jz      short loc_1800D71E3
0x1800d71d9  lea     rcx, [rsp+88h+var_38]
0x1800d71de  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d71e3  lea     rdx, [rsp+88h+var_38]
0x1800d71e8  mov     rcx, rbx
0x1800d71eb  mov     rax, rdi
0x1800d71ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d71f3  mov     ebx, eax
0x1800d71f5  test    eax, eax
0x1800d71f7  jns     short loc_1800D7254
0x1800d71f9  mov     rcx, [rsp+88h]; this
0x1800d7201  mov     r9d, eax; char *
0x1800d7204  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d720b  mov     edx, 0A6h; void *
0x1800d7210  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7215  nop
0x1800d7216  cmp     [rsp+88h+var_38], rsi
0x1800d721b  jz      short loc_1800D7228
0x1800d721d  lea     rcx, [rsp+88h+var_38]
0x1800d7222  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7227  nop
0x1800d7228  cmp     [rsp+88h+var_30], rsi
0x1800d722d  jz      short loc_1800D723A
0x1800d722f  lea     rcx, [rsp+88h+var_30]
0x1800d7234  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7239  nop
0x1800d723a  mov     al, [rsp+88h+var_48]
0x1800d723e  mov     [rsp+88h+var_48], sil
0x1800d7243  test    al, al
0x1800d7245  jz      short loc_1800D724D
0x1800d7247  call    cs:__imp_CoUninitialize
0x1800d724d  mov     eax, ebx
0x1800d724f  jmp     loc_1800D7501
0x1800d7254  mov     rcx, [rsp+88h+var_38]
0x1800d7259  mov     rax, [rcx]
0x1800d725c  lea     r9, [rsp+88h+var_28]
0x1800d7261  mov     r8d, 200404h
0x1800d7267  mov     rdx, cs:?aumId@FailoverToast@@0V?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const FailoverToast::aumId
0x1800d726e  mov     rax, [rax+18h]
0x1800d7272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7277  mov     ebx, eax
0x1800d7279  test    eax, eax
0x1800d727b  jns     short loc_1800D72D8
0x1800d727d  mov     rcx, [rsp+88h]; this
0x1800d7285  mov     r9d, eax; char *
0x1800d7288  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d728f  mov     edx, 0AAh; void *
0x1800d7294  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7299  nop
0x1800d729a  cmp     [rsp+88h+var_38], rsi
0x1800d729f  jz      short loc_1800D72AC
0x1800d72a1  lea     rcx, [rsp+88h+var_38]
0x1800d72a6  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d72ab  nop
0x1800d72ac  cmp     [rsp+88h+var_30], rsi
0x1800d72b1  jz      short loc_1800D72BE
0x1800d72b3  lea     rcx, [rsp+88h+var_30]
0x1800d72b8  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d72bd  nop
0x1800d72be  mov     al, [rsp+88h+var_48]
0x1800d72c2  mov     [rsp+88h+var_48], sil
0x1800d72c7  test    al, al
0x1800d72c9  jz      short loc_1800D72D1
0x1800d72cb  call    cs:__imp_CoUninitialize
0x1800d72d1  mov     eax, ebx
0x1800d72d3  jmp     loc_1800D7501
0x1800d72d8  cmp     [rsp+88h+var_28], esi
0x1800d72dc  jz      short loc_1800D7351
0x1800d72de  lea     rax, WPP_GLOBAL_Control
0x1800d72e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d72ec  cmp     rcx, rax
0x1800d72ef  jz      short loc_1800D7313
0x1800d72f1  cmp     byte ptr [rcx+19h], 4
0x1800d72f5  jb      short loc_1800D7313
0x1800d72f7  test    byte ptr [rcx+1Ch], 1
0x1800d72fb  jz      short loc_1800D7313
0x1800d72fd  mov     edx, 0Dh
0x1800d7302  lea     r8, WPP_36ba8b8ab71539cb7e9a28af59916125_Traceguids
0x1800d7309  mov     rcx, [rcx+10h]
0x1800d730d  call    WPP_SF_
0x1800d7312  nop
0x1800d7313  cmp     [rsp+88h+var_38], rsi
0x1800d7318  jz      short loc_1800D7325
0x1800d731a  lea     rcx, [rsp+88h+var_38]
0x1800d731f  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7324  nop
0x1800d7325  cmp     [rsp+88h+var_30], rsi
0x1800d732a  jz      short loc_1800D7337
0x1800d732c  lea     rcx, [rsp+88h+var_30]
0x1800d7331  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7336  nop
0x1800d7337  mov     al, [rsp+88h+var_48]
0x1800d733b  mov     [rsp+88h+var_48], sil
0x1800d7340  test    al, al
0x1800d7342  jz      short loc_1800D734A
0x1800d7344  call    cs:__imp_CoUninitialize
0x1800d734a  xor     eax, eax
0x1800d734c  jmp     loc_1800D7501
0x1800d7351  mov     [rsp+88h+var_20], rsi
0x1800d7356  mov     rcx, [rsp+88h+var_30]
0x1800d735b  mov     rax, [rcx]
0x1800d735e  lea     rdx, [rsp+88h+var_20]
0x1800d7363  mov     rax, [rax+28h]
0x1800d7367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d736c  mov     ebx, eax
0x1800d736e  test    eax, eax
0x1800d7370  jns     short loc_1800D73DF
0x1800d7372  mov     rcx, [rsp+88h]; this
0x1800d737a  mov     r9d, eax; char *
0x1800d737d  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d7384  mov     edx, 0B2h; void *
0x1800d7389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d738e  nop
0x1800d738f  cmp     [rsp+88h+var_20], rsi
0x1800d7394  jz      short loc_1800D73A1
0x1800d7396  lea     rcx, [rsp+88h+var_20]
0x1800d739b  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d73a0  nop
0x1800d73a1  cmp     [rsp+88h+var_38], rsi
0x1800d73a6  jz      short loc_1800D73B3
0x1800d73a8  lea     rcx, [rsp+88h+var_38]
0x1800d73ad  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d73b2  nop
0x1800d73b3  cmp     [rsp+88h+var_30], rsi
0x1800d73b8  jz      short loc_1800D73C5
0x1800d73ba  lea     rcx, [rsp+88h+var_30]
0x1800d73bf  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d73c4  nop
0x1800d73c5  mov     al, [rsp+88h+var_48]
0x1800d73c9  mov     [rsp+88h+var_48], sil
0x1800d73ce  test    al, al
0x1800d73d0  jz      short loc_1800D73D8
0x1800d73d2  call    cs:__imp_CoUninitialize
0x1800d73d8  mov     eax, ebx
0x1800d73da  jmp     loc_1800D7501
0x1800d73df  mov     rdx, [rsp+88h+var_20]
0x1800d73e4  lea     rcx, [rsp+88h+var_40]
0x1800d73e9  call    ??$as@UIWpnSystemRegistrationEndpoint@@UIWpnRegistrationEndpoint@@$0A@@impl@winrt@@YA?AU?$com_ptr@UIWpnSystemRegistrationEndpoint@@@1@PEAUIWpnRegistrationEndpoint@@@Z; winrt::impl::as<IWpnSystemRegistrationEndpoint,IWpnRegistrationEndpoint,0>(IWpnRegistrationEndpoint *)
0x1800d73ee  nop
0x1800d73ef  mov     rdi, [rsp+88h+var_40]
0x1800d73f4  mov     rax, [rdi]
0x1800d73f7  mov     [rsp+88h+var_60], rsi
0x1800d73fc  mov     [rsp+88h+var_68], esi; int
0x1800d7400  mov     r9d, 200404h
0x1800d7406  mov     r8, cs:?aumId@FailoverToast@@0V?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const FailoverToast::aumId
0x1800d740d  mov     rdx, cs:?scope@FailoverToast@@0V?$basic_string_view@GU?$char_traits@G@std@@@std@@B; std::basic_string_view<ushort> const FailoverToast::scope
0x1800d7414  mov     rcx, rdi
0x1800d7417  mov     rax, [rax+18h]
0x1800d741b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7420  mov     ebx, eax
0x1800d7422  test    eax, eax
0x1800d7424  jns     short loc_1800D74A0
0x1800d7426  mov     rcx, [rsp+88h]; this
0x1800d742e  mov     r9d, eax; char *
0x1800d7431  lea     r8, aOnecoreuapNetW_13; "onecoreuap\\net\\wcm\\service\\base\\to"...
0x1800d7438  mov     edx, 0BAh; void *
0x1800d743d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d7442  nop
0x1800d7443  test    rdi, rdi
0x1800d7446  jz      short loc_1800D7453
0x1800d7448  lea     rcx, [rsp+88h+var_40]
0x1800d744d  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7452  nop
0x1800d7453  cmp     [rsp+88h+var_20], rsi
0x1800d7458  jz      short loc_1800D7465
0x1800d745a  lea     rcx, [rsp+88h+var_20]
0x1800d745f  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7464  nop
0x1800d7465  cmp     [rsp+88h+var_38], rsi
0x1800d746a  jz      short loc_1800D7477
0x1800d746c  lea     rcx, [rsp+88h+var_38]
0x1800d7471  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7476  nop
0x1800d7477  cmp     [rsp+88h+var_30], rsi
0x1800d747c  jz      short loc_1800D7489
0x1800d747e  lea     rcx, [rsp+88h+var_30]
0x1800d7483  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d7488  nop
0x1800d7489  mov     al, [rsp+88h+var_48]
0x1800d748d  mov     [rsp+88h+var_48], sil
0x1800d7492  test    al, al
0x1800d7494  jz      short loc_1800D749C
0x1800d7496  call    cs:__imp_CoUninitialize
0x1800d749c  mov     eax, ebx
0x1800d749e  jmp     short loc_1800D7501
0x1800d74a0  test    rdi, rdi
0x1800d74a3  jz      short loc_1800D74B0
0x1800d74a5  lea     rcx, [rsp+88h+var_40]
0x1800d74aa  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d74af  nop
0x1800d74b0  cmp     [rsp+88h+var_20], rsi
0x1800d74b5  jz      short loc_1800D74C2
0x1800d74b7  lea     rcx, [rsp+88h+var_20]
0x1800d74bc  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d74c1  nop
0x1800d74c2  cmp     [rsp+88h+var_38], rsi
0x1800d74c7  jz      short loc_1800D74D4
0x1800d74c9  lea     rcx, [rsp+88h+var_38]
0x1800d74ce  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d74d3  nop
0x1800d74d4  cmp     [rsp+88h+var_30], rsi
0x1800d74d9  jz      short loc_1800D74E6
0x1800d74db  lea     rcx, [rsp+88h+var_30]
0x1800d74e0  call    ?unconditional_release_ref@?$com_ptr@UIWpnRegistrationEndpoint@@@winrt@@AEAAXXZ; winrt::com_ptr<IWpnRegistrationEndpoint>::unconditional_release_ref(void)
0x1800d74e5  nop
0x1800d74e6  mov     al, [rsp+88h+var_48]
0x1800d74ea  mov     [rsp+88h+var_48], sil
0x1800d74ef  test    al, al
0x1800d74f1  jz      short loc_1800D74F9
0x1800d74f3  call    cs:__imp_CoUninitialize
0x1800d74f9  xor     eax, eax
0x1800d74fb  jmp     short loc_1800D7501
0x1800d74fd  mov     eax, [rsp+88h+var_28]
0x1800d7501  mov     rcx, [rsp+88h+var_18]
0x1800d7506  xor     rcx, rsp; StackCookie
0x1800d7509  call    __security_check_cookie
0x1800d750e  lea     r11, [rsp+88h+var_8]
0x1800d7516  mov     rbx, [r11+18h]
0x1800d751a  mov     rsi, [r11+20h]
0x1800d751e  mov     rsp, r11
0x1800d7521  pop     rdi
0x1800d7522  retn
```
