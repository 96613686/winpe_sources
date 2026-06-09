# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetAppEndpoint(IWpnAppEndpoint * *)

- ea: `0x180014210`
- end: `0x180014505`
- name: `?_GetAppEndpoint@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEAPEAUIWpnAppEndpoint@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *__hidden this, struct IWpnAppEndpoint **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180011e68`
- `0x180014210`
- `0x180019010`

## import_xrefs

- `PhoneUtil!GetSignedInUserForAppActivation` at `0x18001427d`
- `PhoneUtil!GetSignedInUserForAppActivation` at `0x18001427d`
- `PhoneUtil!GetUserContextTokenForUser` at `0x180014387`
- `PhoneUtil!GetUserContextTokenForUser` at `0x180014387`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014495`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014495`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180014257`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180014257`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180014416`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180014416`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetAppEndpoint(
        WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *this,
        struct IWpnAppEndpoint **a2)
{
  HRESULT SignedInUserForAppActivation; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  LPVOID v6; // rcx
  void (*v7)(void); // rax
  int UserContextTokenForUser; // eax
  __int64 v10; // r8
  unsigned int v11; // edi
  LPVOID v12; // rcx
  LPVOID v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  LPVOID v16; // rcx
  LPVOID v17; // rcx
  int v18; // [rsp+30h] [rbp-59h] BYREF
  __int64 v19; // [rsp+38h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-49h] BYREF
  struct Windows::System::IUser *v21; // [rsp+48h] [rbp-41h] BYREF
  int v22; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+60h] [rbp-29h] BYREF
  int *v25; // [rsp+80h] [rbp-9h]
  __int64 v26; // [rsp+88h] [rbp-1h]
  __int64 *v27; // [rsp+90h] [rbp+7h]
  __int64 v28; // [rsp+98h] [rbp+Fh]

  ppv = 0;
  if ( !`DeviceFamily::Details::GetDeviceFamily'::`2'::s_deviceFamilyQueried )
  {
    RtlGetDeviceFamilyInfoEnum(0, &`DeviceFamily::Details::GetDeviceFamily'::`2'::s_deviceFamily, 0);
    `DeviceFamily::Details::GetDeviceFamily'::`2'::s_deviceFamilyQueried = 1;
  }
  if ( `DeviceFamily::Details::GetDeviceFamily'::`2'::s_deviceFamily == 10 )
  {
    v21 = 0;
    SignedInUserForAppActivation = GetSignedInUserForAppActivation(&v21);
    if ( SignedInUserForAppActivation < 0 )
    {
      v5 = 569;
LABEL_6:
      Log_HREvent_1((unsigned int)SignedInUserForAppActivation, 1, v4, v5);
      if ( v21 )
        (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v21 + 16LL))(v21);
      v6 = ppv;
      if ( !ppv )
        return (unsigned int)SignedInUserForAppActivation;
      ppv = 0;
      v7 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
      goto LABEL_10;
    }
    v22 = 0;
    SignedInUserForAppActivation = (*(__int64 (__fastcall **)(struct Windows::System::IUser *, int *))(*(_QWORD *)v21 + 64LL))(
                                     v21,
                                     &v22);
    if ( SignedInUserForAppActivation < 0 )
    {
      v5 = 572;
      goto LABEL_6;
    }
    if ( (unsigned int)dword_180025038 > 4
      && (qword_180025048 & 0x400000000000LL) != 0
      && (qword_180025050 & 0x400000000000LL) == qword_180025050 )
    {
      v18 = v22;
      v19 = 2048;
      v27 = &v19;
      v28 = 8;
      v25 = &v18;
      v26 = 4;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180025038, (int)&byte_180020C0B, 0, 0, 4u, &v24);
    }
    v23 = 0;
    UserContextTokenForUser = GetUserContextTokenForUser(v21, &v23);
    v11 = UserContextTokenForUser;
    if ( UserContextTokenForUser < 0 )
    {
      Log_HREvent_1((unsigned int)UserContextTokenForUser, 1, v10, 582);
      if ( v21 )
        (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v21 + 16LL))(v21);
      v12 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
      }
      return v11;
    }
    v13 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
    }
    SignedInUserForAppActivation = CoCreateInstanceAsUser(
                                     &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                                     0,
                                     4,
                                     v23,
                                     &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                                     &ppv);
    if ( SignedInUserForAppActivation < 0 )
    {
      v5 = 585;
      goto LABEL_6;
    }
    if ( v21 )
      (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v21 + 16LL))(v21);
  }
  else
  {
    SignedInUserForAppActivation = CoCreateInstance(
                                     &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
                                     0,
                                     4u,
                                     &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
                                     &ppv);
    if ( SignedInUserForAppActivation < 0 )
    {
      v15 = 590;
      goto LABEL_34;
    }
  }
  SignedInUserForAppActivation = (*(__int64 (__fastcall **)(LPVOID, struct IWpnAppEndpoint **))(*(_QWORD *)ppv + 24LL))(
                                   ppv,
                                   a2);
  if ( SignedInUserForAppActivation < 0 )
  {
    v15 = 593;
LABEL_34:
    Log_HREvent_1((unsigned int)SignedInUserForAppActivation, 1, v14, v15);
    v16 = ppv;
    if ( !ppv )
      return (unsigned int)SignedInUserForAppActivation;
    ppv = 0;
    v7 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
LABEL_10:
    v7();
    return (unsigned int)SignedInUserForAppActivation;
  }
  v17 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180014210  push    rbp
0x180014212  push    rbx
0x180014213  push    rsi
0x180014214  push    rdi
0x180014215  push    r14
0x180014217  push    r15
0x180014219  lea     rbp, [rsp-2Fh]
0x18001421e  sub     rsp, 0B8h
0x180014225  mov     rax, cs:__security_cookie
0x18001422c  xor     rax, rsp
0x18001422f  mov     [rbp+57h+var_40], rax
0x180014233  xor     r14d, r14d
0x180014236  mov     rsi, rdx
0x180014239  cmp     cs:?s_deviceFamilyQueried@?1??GetDeviceFamily@Details@DeviceFamily@@YAKXZ@4_NA, r14b; bool `DeviceFamily::Details::GetDeviceFamily(void)'::`2'::s_deviceFamilyQueried
0x180014240  mov     ecx, r14d
0x180014243  mov     [rbp+57h+var_A0], rcx
0x180014247  lea     r15d, [r14+1]
0x18001424b  jnz     short loc_180014268
0x18001424d  xor     r8d, r8d
0x180014250  lea     rdx, ?s_deviceFamily@?1??GetDeviceFamily@Details@DeviceFamily@@YAKXZ@4KA; ulong `DeviceFamily::Details::GetDeviceFamily(void)'::`2'::s_deviceFamily
0x180014257  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18001425d  mov     rcx, [rbp+57h+var_A0]
0x180014261  mov     cs:?s_deviceFamilyQueried@?1??GetDeviceFamily@Details@DeviceFamily@@YAKXZ@4_NA, r15b; bool `DeviceFamily::Details::GetDeviceFamily(void)'::`2'::s_deviceFamilyQueried
0x180014268  cmp     cs:?s_deviceFamily@?1??GetDeviceFamily@Details@DeviceFamily@@YAKXZ@4KA, 0Ah; ulong `DeviceFamily::Details::GetDeviceFamily(void)'::`2'::s_deviceFamily
0x18001426f  jnz     loc_180014463
0x180014275  lea     rcx, [rbp+57h+var_98]
0x180014279  mov     [rbp+57h+var_98], r14
0x18001427d  call    cs:__imp_?GetSignedInUserForAppActivation@@YAJPEAPEAUIUser@System@Windows@@@Z; GetSignedInUserForAppActivation(Windows::System::IUser * *)
0x180014283  mov     ebx, eax
0x180014285  test    eax, eax
0x180014287  jns     short loc_1800142CE
0x180014289  mov     r9d, 239h
0x18001428f  mov     edx, r15d
0x180014292  mov     ecx, ebx
0x180014294  call    Log_HREvent_1
0x180014299  mov     rcx, [rbp+57h+var_98]
0x18001429d  test    rcx, rcx
0x1800142a0  jz      short loc_1800142AE
0x1800142a2  mov     rdx, [rcx]
0x1800142a5  mov     rax, [rdx+10h]
0x1800142a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ae  mov     rcx, [rbp+57h+var_A0]
0x1800142b2  test    rcx, rcx
0x1800142b5  jz      short loc_1800142C7
0x1800142b7  mov     [rbp+57h+var_A0], r14
0x1800142bb  mov     rax, [rcx]
0x1800142be  mov     rax, [rax+10h]
0x1800142c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142c7  mov     eax, ebx
0x1800142c9  jmp     loc_1800144E9
0x1800142ce  mov     rcx, [rbp+57h+var_98]
0x1800142d2  lea     rdx, [rbp+57h+var_90]
0x1800142d6  mov     [rbp+57h+var_90], r14d
0x1800142da  mov     rax, [rcx]
0x1800142dd  mov     rax, [rax+40h]
0x1800142e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142e6  mov     ebx, eax
0x1800142e8  test    eax, eax
0x1800142ea  jns     short loc_1800142F4
0x1800142ec  mov     r9d, 23Ch
0x1800142f2  jmp     short loc_18001428F
0x1800142f4  mov     eax, cs:dword_180025038
0x1800142fa  mov     ebx, 4
0x1800142ff  cmp     eax, ebx
0x180014301  jbe     short loc_18001437B
0x180014303  mov     rcx, cs:qword_180025050
0x18001430a  mov     rdx, 400000000000h
0x180014314  mov     rax, cs:qword_180025048
0x18001431b  test    rdx, rax
0x18001431e  jz      short loc_18001437B
0x180014320  mov     rax, rcx
0x180014323  and     rax, rdx
0x180014326  cmp     rax, rcx
0x180014329  jnz     short loc_18001437B
0x18001432b  mov     eax, [rbp+57h+var_90]
0x18001432e  lea     rdx, byte_180020C0B; int
0x180014335  mov     [rbp+57h+var_B0], eax
0x180014338  lea     rcx, dword_180025038; int
0x18001433f  lea     rax, [rbp+57h+var_A8]
0x180014343  mov     [rbp+57h+var_A8], 800h
0x18001434b  mov     [rbp+57h+var_50], rax
0x18001434f  xor     r9d, r9d; int
0x180014352  lea     rax, [rbp+57h+var_B0]
0x180014356  mov     [rbp+57h+var_48], 8
0x18001435e  mov     [rbp+57h+var_60], rax
0x180014362  xor     r8d, r8d; int
0x180014365  lea     rax, [rbp+57h+var_80]
0x180014369  mov     [rbp+57h+var_58], rbx
0x18001436d  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x180014372  mov     dword ptr [rsp+0E0h+ppv], ebx; ULONG
0x180014376  call    _tlgWriteTransfer_EventWriteTransfer
0x18001437b  mov     rcx, [rbp+57h+var_98]
0x18001437f  lea     rdx, [rbp+57h+var_88]
0x180014383  mov     [rbp+57h+var_88], r14
0x180014387  call    cs:__imp_?GetUserContextTokenForUser@@YAJPEAUIUser@System@Windows@@PEA_K@Z; GetUserContextTokenForUser(Windows::System::IUser *,unsigned __int64 *)
0x18001438d  mov     edi, eax
0x18001438f  test    eax, eax
0x180014391  jns     short loc_1800143D8
0x180014393  mov     r9d, 246h
0x180014399  mov     edx, r15d
0x18001439c  mov     ecx, eax
0x18001439e  call    Log_HREvent_1
0x1800143a3  mov     rcx, [rbp+57h+var_98]
0x1800143a7  test    rcx, rcx
0x1800143aa  jz      short loc_1800143B8
0x1800143ac  mov     rdx, [rcx]
0x1800143af  mov     rax, [rdx+10h]
0x1800143b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143b8  mov     rcx, [rbp+57h+var_A0]
0x1800143bc  test    rcx, rcx
0x1800143bf  jz      short loc_1800143D1
0x1800143c1  mov     [rbp+57h+var_A0], r14
0x1800143c5  mov     rax, [rcx]
0x1800143c8  mov     rax, [rax+10h]
0x1800143cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143d1  mov     eax, edi
0x1800143d3  jmp     loc_1800144E9
0x1800143d8  mov     rcx, [rbp+57h+var_A0]
0x1800143dc  test    rcx, rcx
0x1800143df  jz      short loc_1800143F1
0x1800143e1  mov     [rbp+57h+var_A0], r14
0x1800143e5  mov     rax, [rcx]
0x1800143e8  mov     rax, [rax+10h]
0x1800143ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143f1  lea     rax, [rbp+57h+var_A0]
0x1800143f5  mov     r8d, ebx
0x1800143f8  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x1800143ff  mov     [rsp+0E0h+var_B8], rax
0x180014404  mov     [rsp+0E0h+ppv], r9
0x180014409  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180014410  mov     r9, [rbp+57h+var_88]
0x180014414  xor     edx, edx
0x180014416  call    cs:__imp_CoCreateInstanceAsUser
0x18001441c  mov     ebx, eax
0x18001441e  test    eax, eax
0x180014420  jns     short loc_18001442D
0x180014422  mov     r9d, 249h
0x180014428  jmp     loc_18001428F
0x18001442d  mov     rcx, [rbp+57h+var_98]
0x180014431  test    rcx, rcx
0x180014434  jz      short loc_180014442
0x180014436  mov     rax, [rcx]
0x180014439  mov     rax, [rax+10h]
0x18001443d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014442  mov     rcx, [rbp+57h+var_A0]
0x180014446  mov     rdx, rsi
0x180014449  mov     rax, [rcx]
0x18001444c  mov     rax, [rax+18h]
0x180014450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014455  mov     ebx, eax
0x180014457  test    eax, eax
0x180014459  jns     short loc_1800144CE
0x18001445b  mov     r9d, 251h
0x180014461  jmp     short loc_1800144A7
0x180014463  test    rcx, rcx
0x180014466  jz      short loc_180014478
0x180014468  mov     [rbp+57h+var_A0], r14
0x18001446c  mov     rax, [rcx]
0x18001446f  mov     rax, [rax+10h]
0x180014473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014478  xor     edx, edx; pUnkOuter
0x18001447a  lea     rax, [rbp+57h+var_A0]
0x18001447e  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180014485  mov     [rsp+0E0h+ppv], rax; ppv
0x18001448a  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x180014491  lea     r8d, [rdx+4]; dwClsContext
0x180014495  call    cs:__imp_CoCreateInstance
0x18001449b  mov     ebx, eax
0x18001449d  test    eax, eax
0x18001449f  jns     short loc_180014442
0x1800144a1  mov     r9d, 24Eh
0x1800144a7  mov     edx, r15d
0x1800144aa  mov     ecx, ebx
0x1800144ac  call    Log_HREvent_1
0x1800144b1  mov     rcx, [rbp+57h+var_A0]
0x1800144b5  test    rcx, rcx
0x1800144b8  jz      loc_1800142C7
0x1800144be  mov     [rbp+57h+var_A0], r14
0x1800144c2  mov     rdx, [rcx]
0x1800144c5  mov     rax, [rdx+10h]
0x1800144c9  jmp     loc_1800142C2
0x1800144ce  mov     rcx, [rbp+57h+var_A0]
0x1800144d2  test    rcx, rcx
0x1800144d5  jz      short loc_1800144E7
0x1800144d7  mov     [rbp+57h+var_A0], r14
0x1800144db  mov     rax, [rcx]
0x1800144de  mov     rax, [rax+10h]
0x1800144e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e7  xor     eax, eax
0x1800144e9  mov     rcx, [rbp+57h+var_40]
0x1800144ed  xor     rcx, rsp; StackCookie
0x1800144f0  call    __security_check_cookie
0x1800144f5  add     rsp, 0B8h
0x1800144fc  pop     r15
0x1800144fe  pop     r14
0x180014500  pop     rdi
0x180014501  pop     rsi
0x180014502  pop     rbx
0x180014503  pop     rbp
0x180014504  retn
```
