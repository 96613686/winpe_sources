# PermissionsUI::AddPermissionsProvider(PermissionsProvider *)

- ea: `0x1803a2ca8`
- end: `0x1803a3026`
- name: `?AddPermissionsProvider@PermissionsUI@@QEAAJPEAVPermissionsProvider@@@Z`
- size: `894`
- prototype: `__int64 __fastcall(PermissionsUI *__hidden this, struct PermissionsProvider *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1803a3d40`

## callees

- `0x180009dd0`
- `0x18008d328`
- `0x18010e7ec`
- `0x180370ae0`
- `0x1803a2b50`
- `0x1803a2ca8`
- `0x1803a302c`
- `0x1803a37a8`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803a2de0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803a2e2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803a2de0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1803a2e2c`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1803a2fe7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1803a2fe7`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2d0d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2dbc`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2d0d`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2dbc`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1803a2fff`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1803a2fff`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2fa0`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1803a2fa0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2cf0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2da6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2e9c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2cf0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2da6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1803a2e9c`
- `DUI70!StrToID` at `0x1803a2cde`
- `DUI70!StrToID` at `0x1803a2d93`
- `DUI70!StrToID` at `0x1803a2e89`
- `DUI70!StrToID` at `0x1803a2cde`
- `DUI70!StrToID` at `0x1803a2d93`
- `DUI70!StrToID` at `0x1803a2e89`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1803a2d47`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x1803a2d47`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1803a2fc9`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1803a2fc9`

## pseudocode

```c
__int64 __fastcall PermissionsUI::AddPermissionsProvider(PermissionsUI *this, struct PermissionsProvider *a2)
{
  unsigned __int16 v5; // ax
  DirectUI::Element *Descendent; // rax
  struct DirectUI::Element *v7; // r15
  DirectUI::DUIXmlParser *ParserForThread; // rax
  int v9; // ebx
  HINSTANCE v10; // r9
  HINSTANCE v11; // r9
  const unsigned __int16 *v12; // r8
  unsigned __int16 v13; // ax
  DirectUI::Element *v14; // rax
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *v16; // rcx
  int v17; // eax
  DWORD v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int16 v21; // ax
  struct DirectUI::Element *v22; // r12
  unsigned int v23; // r14d
  void *v24; // rdi
  __int64 (__fastcall *v25)(void *, _QWORD, _QWORD *); // rbx
  __int64 v26; // rdi
  struct ISettingsProvider *v27; // r13
  int (__fastcall *v28)(__int64, GUID *, struct ISetting **); // rbx
  PermissionsUI *v29; // rcx
  int v30; // eax
  struct DirectUI::Element *v31; // [rsp+30h] [rbp-28h] BYREF
  void *v32; // [rsp+38h] [rbp-20h] BYREF
  struct ISettingsProvider *v33; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v34[2]; // [rsp+48h] [rbp-10h] BYREF
  LPOLESTR lpsz; // [rsp+A8h] [rbp+50h] BYREF
  struct ISetting *v37; // [rsp+B0h] [rbp+58h] BYREF
  int v38; // [rsp+B8h] [rbp+60h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = StrToID(L"ePermissionsSection");
  Descendent = DirectUI::Element::FindDescendent(this, v5);
  v7 = Descendent;
  if ( Descendent )
  {
    DirectUI::Element::SetVisible(Descendent, 1);
    v31 = 0;
    ParserForThread = CDUIResourceManager::GetParserForThread((CDUIResourceManager *)g_PermissionsDUIResourceManager);
    v9 = DirectUI::DUIXmlParser::CreateElement(ParserForThread, L"permission", 0, v7, 0, &v31);
    if ( v9 >= 0 )
    {
      DUI_SetDescendentElementTextAndAccName(v31, L"ePermissionTitle", *((const unsigned __int16 **)a2 + 5), v10);
      v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
      if ( v12 )
      {
        DUI_SetDescendentElementTextAndAccName(v31, L"ePermissionDescription", v12, v11);
      }
      else
      {
        v13 = StrToID(L"ePermissionDescription");
        v14 = DirectUI::Element::FindDescendent(v31, v13);
        if ( v14 )
          DirectUI::Element::SetVisible(v14, 0);
      }
      v33 = 0;
      v32 = 0;
      LODWORD(lpsz) = 0;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      v33 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *(const unsigned __int16 **)a2;
      if ( *((_DWORD *)a2 + 4) == CurrentThreadId )
        v17 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct ISettingsProvider **))v16 + 1))(
                *((_QWORD *)v16 + 1),
                &GUID_5fc0f146_1b06_44ca_a568_283acd690e00,
                &v33);
      else
        v17 = AgileGitPtr::CopyLocal(
                (AgileGitPtr *)(v16 + 8),
                &GUID_5fc0f146_1b06_44ca_a568_283acd690e00,
                (void **)&v33);
      v9 = v17;
      if ( v17 >= 0 )
      {
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
        v32 = 0;
        v18 = GetCurrentThreadId();
        v19 = *((_QWORD *)a2 + 1);
        v20 = *((_DWORD *)a2 + 4) == v18
            ? (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(v19 + 8))(
                *(_QWORD *)(v19 + 8),
                &GUID_62948522_8857_4c63_9b85_8fff20128f6a,
                &v32)
            : AgileGitPtr::CopyLocal((AgileGitPtr *)(v19 + 16), &GUID_62948522_8857_4c63_9b85_8fff20128f6a, &v32);
        v9 = v20;
        if ( v20 >= 0 )
          v9 = (*(__int64 (__fastcall **)(void *, LPOLESTR *))(*(_QWORD *)v32 + 32LL))(v32, &lpsz);
      }
      v21 = StrToID(L"ePermissionSettingsSection");
      v22 = DirectUI::Element::FindDescendent(v31, v21);
      v23 = 0;
      while ( v9 >= 0 )
      {
        if ( v23 >= (unsigned int)lpsz )
          goto LABEL_31;
        v34[0] = 0;
        v24 = v32;
        v25 = *(__int64 (__fastcall **)(void *, _QWORD, _QWORD *))(*(_QWORD *)v32 + 40LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v34);
        v9 = v25(v24, v23, v34);
        if ( v9 >= 0 )
        {
          v26 = v34[0];
          v27 = v33;
          v37 = 0;
          v28 = **(int (__fastcall ***)(__int64, GUID *, struct ISetting **))v34[0];
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
          v30 = v28(v26, &GUID_18d72473_cd4a_411d_a73e_6b212cec6ca8, &v37) < 0
              ? PermissionsUI::AddLabelSettingToPermissions(v29, v37, v22)
              : PermissionsUI::AddToggleSettingToPermissions(v29, v37, v27, v22);
          v9 = v30;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
          if ( v9 >= 0 )
          {
            v38 = 0;
            LODWORD(v37) = 0;
            if ( (*(int (__fastcall **)(_QWORD, int *, struct ISetting **))(*(_QWORD *)v34[0] + 56LL))(
                   v34[0],
                   &v38,
                   &v37) >= 0 )
            {
              if ( (_DWORD)v37 )
                PermissionsUI::ShowGroupPolicyMessage(this);
            }
          }
        }
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(v34);
        ++v23;
      }
      DirectUI::Element::Destroy(v31, 0);
LABEL_31:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v33);
      if ( v9 >= 0 )
      {
        v9 = DirectUI::Element::Add(v7, v31);
        if ( v9 >= 0 )
        {
          lpsz = 0;
          if ( StringFromCLSID((const IID *const)((char *)a2 + 20), &lpsz) >= 0 )
            DirectUI::Element::SetID(v31, lpsz);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1803a2ca8  mov     [rsp-40h+arg_0], rcx
0x1803a2cad  push    rbp
0x1803a2cae  push    rbx
0x1803a2caf  push    rsi
0x1803a2cb0  push    rdi
0x1803a2cb1  push    r12
0x1803a2cb3  push    r13
0x1803a2cb5  push    r14
0x1803a2cb7  push    r15
0x1803a2cb9  mov     rbp, rsp
0x1803a2cbc  sub     rsp, 58h
0x1803a2cc0  xor     edi, edi
0x1803a2cc2  mov     rsi, rdx
0x1803a2cc5  mov     rbx, rcx
0x1803a2cc8  test    rdx, rdx
0x1803a2ccb  jnz     short loc_1803A2CD7
0x1803a2ccd  mov     eax, 80070057h
0x1803a2cd2  jmp     loc_1803A3014
0x1803a2cd7  lea     rcx, aEpermissionsse; "ePermissionsSection"
0x1803a2cde  call    cs:__imp_StrToID
0x1803a2ce5  nop     dword ptr [rax+rax+00h]
0x1803a2cea  movzx   edx, ax
0x1803a2ced  mov     rcx, rbx
0x1803a2cf0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803a2cf7  nop     dword ptr [rax+rax+00h]
0x1803a2cfc  mov     r15, rax
0x1803a2cff  test    rax, rax
0x1803a2d02  jz      loc_1803A300D
0x1803a2d08  mov     dl, 1
0x1803a2d0a  mov     rcx, rax
0x1803a2d0d  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1803a2d14  nop     dword ptr [rax+rax+00h]
0x1803a2d19  lea     rcx, ?g_PermissionsDUIResourceManager@@3VCDUIResourceManager@@A; this
0x1803a2d20  mov     [rbp+var_28], rdi
0x1803a2d24  call    ?GetParserForThread@CDUIResourceManager@@QEBAPEAVDUIXmlParser@DirectUI@@XZ; CDUIResourceManager::GetParserForThread(void)
0x1803a2d29  lea     rcx, [rbp+var_28]
0x1803a2d2d  mov     r9, r15
0x1803a2d30  mov     [rsp+58h+var_30], rcx
0x1803a2d35  lea     rdx, aPermission; "permission"
0x1803a2d3c  mov     rcx, rax
0x1803a2d3f  mov     [rsp+58h+var_38], rdi
0x1803a2d44  xor     r8d, r8d
0x1803a2d47  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x1803a2d4e  nop     dword ptr [rax+rax+00h]
0x1803a2d53  mov     ebx, eax
0x1803a2d55  test    eax, eax
0x1803a2d57  js      loc_1803A3012
0x1803a2d5d  mov     r8, [rsi+28h]; unsigned __int16 *
0x1803a2d61  lea     rdx, aEpermissiontit; "ePermissionTitle"
0x1803a2d68  mov     rcx, [rbp+var_28]; struct DirectUI::Element *
0x1803a2d6c  call    ?DUI_SetDescendentElementTextAndAccName@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementTextAndAccName(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x1803a2d71  mov     r8, [rsi+30h]; unsigned __int16 *
0x1803a2d75  test    r8, r8
0x1803a2d78  jz      short loc_1803A2D8C
0x1803a2d7a  mov     rcx, [rbp+var_28]; struct DirectUI::Element *
0x1803a2d7e  lea     rdx, aEpermissiondes; "ePermissionDescription"
0x1803a2d85  call    ?DUI_SetDescendentElementTextAndAccName@@YAJPEAVElement@DirectUI@@PEBG1PEAUHINSTANCE__@@@Z; DUI_SetDescendentElementTextAndAccName(DirectUI::Element *,ushort const *,ushort const *,HINSTANCE__ *)
0x1803a2d8a  jmp     short loc_1803A2DC8
0x1803a2d8c  lea     rcx, aEpermissiondes; "ePermissionDescription"
0x1803a2d93  call    cs:__imp_StrToID
0x1803a2d9a  nop     dword ptr [rax+rax+00h]
0x1803a2d9f  mov     rcx, [rbp+var_28]
0x1803a2da3  movzx   edx, ax
0x1803a2da6  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803a2dad  nop     dword ptr [rax+rax+00h]
0x1803a2db2  test    rax, rax
0x1803a2db5  jz      short loc_1803A2DC8
0x1803a2db7  xor     edx, edx
0x1803a2db9  mov     rcx, rax
0x1803a2dbc  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1803a2dc3  nop     dword ptr [rax+rax+00h]
0x1803a2dc8  lea     rcx, [rbp+var_18]
0x1803a2dcc  mov     [rbp+var_18], rdi
0x1803a2dd0  mov     [rbp+var_20], rdi
0x1803a2dd4  mov     dword ptr [rbp+lpsz], edi
0x1803a2dd7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2ddc  mov     [rbp+var_18], rdi
0x1803a2de0  call    cs:__imp_GetCurrentThreadId
0x1803a2de7  nop     dword ptr [rax+rax+00h]
0x1803a2dec  mov     rcx, [rsi]
0x1803a2def  lea     r8, [rbp+var_18]; void **
0x1803a2df3  lea     rdx, _GUID_5fc0f146_1b06_44ca_a568_283acd690e00; struct _GUID *
0x1803a2dfa  cmp     [rsi+10h], eax
0x1803a2dfd  jnz     short loc_1803A2E10
0x1803a2dff  mov     rcx, [rcx+8]
0x1803a2e03  mov     rax, [rcx]
0x1803a2e06  mov     rax, [rax]
0x1803a2e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2e0e  jmp     short loc_1803A2E19
0x1803a2e10  add     rcx, 10h; this
0x1803a2e14  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x1803a2e19  mov     ebx, eax
0x1803a2e1b  test    eax, eax
0x1803a2e1d  js      short loc_1803A2E82
0x1803a2e1f  lea     rcx, [rbp+var_20]
0x1803a2e23  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2e28  mov     [rbp+var_20], rdi
0x1803a2e2c  call    cs:__imp_GetCurrentThreadId
0x1803a2e33  nop     dword ptr [rax+rax+00h]
0x1803a2e38  mov     rcx, [rsi+8]
0x1803a2e3c  lea     r8, [rbp+var_20]; void **
0x1803a2e40  lea     rdx, _GUID_62948522_8857_4c63_9b85_8fff20128f6a; struct _GUID *
0x1803a2e47  cmp     [rsi+10h], eax
0x1803a2e4a  jnz     short loc_1803A2E5D
0x1803a2e4c  mov     rcx, [rcx+8]
0x1803a2e50  mov     rax, [rcx]
0x1803a2e53  mov     rax, [rax]
0x1803a2e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2e5b  jmp     short loc_1803A2E66
0x1803a2e5d  add     rcx, 10h; this
0x1803a2e61  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x1803a2e66  mov     ebx, eax
0x1803a2e68  test    eax, eax
0x1803a2e6a  js      short loc_1803A2E82
0x1803a2e6c  mov     rcx, [rbp+var_20]
0x1803a2e70  lea     rdx, [rbp+lpsz]
0x1803a2e74  mov     rax, [rcx]
0x1803a2e77  mov     rax, [rax+20h]
0x1803a2e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2e80  mov     ebx, eax
0x1803a2e82  lea     rcx, aEpermissionset; "ePermissionSettingsSection"
0x1803a2e89  call    cs:__imp_StrToID
0x1803a2e90  nop     dword ptr [rax+rax+00h]
0x1803a2e95  mov     rcx, [rbp+var_28]
0x1803a2e99  movzx   edx, ax
0x1803a2e9c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1803a2ea3  nop     dword ptr [rax+rax+00h]
0x1803a2ea8  mov     r12, rax
0x1803a2eab  mov     r14d, edi
0x1803a2eae  jmp     loc_1803A2F92
0x1803a2eb3  cmp     r14d, dword ptr [rbp+lpsz]
0x1803a2eb7  jnb     loc_1803A2FAC
0x1803a2ebd  mov     [rbp+var_10], rdi
0x1803a2ec1  lea     rcx, [rbp+var_10]
0x1803a2ec5  mov     rdi, [rbp+var_20]
0x1803a2ec9  mov     rdx, [rdi]
0x1803a2ecc  mov     rbx, [rdx+28h]
0x1803a2ed0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2ed5  lea     r8, [rbp+var_10]
0x1803a2ed9  mov     edx, r14d
0x1803a2edc  mov     rcx, rdi
0x1803a2edf  mov     rax, rbx
0x1803a2ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2ee7  xor     edi, edi
0x1803a2ee9  mov     ebx, eax
0x1803a2eeb  test    eax, eax
0x1803a2eed  js      loc_1803A2F86
0x1803a2ef3  mov     rdi, [rbp+var_10]
0x1803a2ef7  lea     rcx, [rbp+arg_10]
0x1803a2efb  mov     r13, [rbp+var_18]
0x1803a2eff  mov     [rbp+arg_10], 0
0x1803a2f07  mov     rax, [rdi]
0x1803a2f0a  mov     rbx, [rax]
0x1803a2f0d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2f12  lea     r8, [rbp+arg_10]
0x1803a2f16  mov     rcx, rdi
0x1803a2f19  lea     rdx, _GUID_18d72473_cd4a_411d_a73e_6b212cec6ca8
0x1803a2f20  mov     rax, rbx
0x1803a2f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2f28  mov     rdx, [rbp+arg_10]; struct ISetting *
0x1803a2f2c  xor     edi, edi
0x1803a2f2e  test    eax, eax
0x1803a2f30  js      short loc_1803A2F3F
0x1803a2f32  mov     r9, r12; struct DirectUI::Element *
0x1803a2f35  mov     r8, r13; struct ISettingsProvider *
0x1803a2f38  call    ?AddToggleSettingToPermissions@PermissionsUI@@AEAAJPEAUIBooleanSetting@@PEAUISettingsProvider@@PEAVElement@DirectUI@@@Z; PermissionsUI::AddToggleSettingToPermissions(IBooleanSetting *,ISettingsProvider *,DirectUI::Element *)
0x1803a2f3d  jmp     short loc_1803A2F47
0x1803a2f3f  mov     r8, r12; struct DirectUI::Element *
0x1803a2f42  call    ?AddLabelSettingToPermissions@PermissionsUI@@AEAAJPEAUISetting@@PEAVElement@DirectUI@@@Z; PermissionsUI::AddLabelSettingToPermissions(ISetting *,DirectUI::Element *)
0x1803a2f47  lea     rcx, [rbp+arg_10]
0x1803a2f4b  mov     ebx, eax
0x1803a2f4d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2f52  test    ebx, ebx
0x1803a2f54  js      short loc_1803A2F86
0x1803a2f56  mov     rcx, [rbp+var_10]
0x1803a2f5a  lea     r8, [rbp+arg_10]
0x1803a2f5e  mov     [rbp+arg_18], edi
0x1803a2f61  lea     rdx, [rbp+arg_18]
0x1803a2f65  mov     dword ptr [rbp+arg_10], edi
0x1803a2f68  mov     rax, [rcx]
0x1803a2f6b  mov     rax, [rax+38h]
0x1803a2f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803a2f74  test    eax, eax
0x1803a2f76  js      short loc_1803A2F86
0x1803a2f78  cmp     dword ptr [rbp+arg_10], edi
0x1803a2f7b  jz      short loc_1803A2F86
0x1803a2f7d  mov     rcx, [rbp+arg_0]; this
0x1803a2f81  call    ?ShowGroupPolicyMessage@PermissionsUI@@QEAAJXZ; PermissionsUI::ShowGroupPolicyMessage(void)
0x1803a2f86  lea     rcx, [rbp+var_10]
0x1803a2f8a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2f8f  inc     r14d
0x1803a2f92  test    ebx, ebx
0x1803a2f94  jns     loc_1803A2EB3
0x1803a2f9a  mov     rcx, [rbp+var_28]
0x1803a2f9e  xor     edx, edx
0x1803a2fa0  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1803a2fa7  nop     dword ptr [rax+rax+00h]
0x1803a2fac  lea     rcx, [rbp+var_20]
0x1803a2fb0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2fb5  lea     rcx, [rbp+var_18]
0x1803a2fb9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803a2fbe  test    ebx, ebx
0x1803a2fc0  js      short loc_1803A3012
0x1803a2fc2  mov     rdx, [rbp+var_28]
0x1803a2fc6  mov     rcx, r15
0x1803a2fc9  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1803a2fd0  nop     dword ptr [rax+rax+00h]
0x1803a2fd5  mov     ebx, eax
0x1803a2fd7  test    eax, eax
0x1803a2fd9  js      short loc_1803A3012
0x1803a2fdb  lea     rcx, [rsi+14h]; rclsid
0x1803a2fdf  mov     [rbp+lpsz], rdi
0x1803a2fe3  lea     rdx, [rbp+lpsz]; lplpsz
0x1803a2fe7  call    cs:__imp_StringFromCLSID
0x1803a2fee  nop     dword ptr [rax+rax+00h]
0x1803a2ff3  test    eax, eax
0x1803a2ff5  js      short loc_1803A3012
0x1803a2ff7  mov     rdx, [rbp+lpsz]
0x1803a2ffb  mov     rcx, [rbp+var_28]
0x1803a2fff  call    cs:__imp_?SetID@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetID(ushort const *)
0x1803a3006  nop     dword ptr [rax+rax+00h]
0x1803a300b  jmp     short loc_1803A3012
0x1803a300d  mov     ebx, 80004005h
0x1803a3012  mov     eax, ebx
0x1803a3014  add     rsp, 58h
0x1803a3018  pop     r15
0x1803a301a  pop     r14
0x1803a301c  pop     r13
0x1803a301e  pop     r12
0x1803a3020  pop     rdi
0x1803a3021  pop     rsi
0x1803a3022  pop     rbx
0x1803a3023  pop     rbp
0x1803a3024  retn
```
