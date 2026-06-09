# CAccountsSettingsPaneStatics::GetForWindow(HWND__ *,bool,_GUID const &,void * *)

- ea: `0x180027904`
- end: `0x180027a23`
- name: `?GetForWindow@CAccountsSettingsPaneStatics@@AEAAJPEAUHWND__@@_NAEBU_GUID@@PEAPEAX@Z`
- size: `287`
- prototype: `int(CAccountsSettingsPaneStatics *__hidden this, HWND, bool, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027880`
- `0x180027a30`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x180022f80`
- `0x180027904`
- `0x18006c010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18002793e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x18002793e`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800279c7`
- `twinapi.appcore!__imp_CoreRegisterWindowService` at `0x1800279c7`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180027971`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180027971`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAccountsSettingsPaneStatics::GetForWindow(
        CAccountsSettingsPaneStatics *this,
        HWND a2,
        char a3,
        const struct _GUID *a4,
        void **a5)
{
  HWND Ancestor; // rdi
  void **v7; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  CAccountsSettingsPaneStatics *v14; // [rsp+50h] [rbp+30h] BYREF
  HWND v15; // [rsp+58h] [rbp+38h] BYREF
  char v16; // [rsp+60h] [rbp+40h] BYREF

  v16 = a3;
  v15 = a2;
  v14 = this;
  Ancestor = a2;
  v7 = a5;
  *a5 = 0;
  if ( a3 )
  {
    Ancestor = GetAncestor(a2, 2u);
    v15 = Ancestor;
  }
  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  v8 = CoreQueryWindowService(
         Ancestor,
         &IID_IImmersiveAccountsSettings,
         &GUID_81ea942c_4f09_4406_a538_838d9b14b7e6,
         &v14);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147221163 )
    {
      v10 = 347;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v8,
        savedregs);
      goto LABEL_14;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v8 = Microsoft::WRL::Details::MakeAndInitialize<CAccountsSettingsPane,Windows::UI::ApplicationSettings::IAccountsSettingsPane,HWND__ * &,bool &>(
           &v14,
           &v15,
           &v16);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 352;
      goto LABEL_13;
    }
    v8 = CoreRegisterWindowService(Ancestor, &IID_IImmersiveAccountsSettings, v14);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 353;
      goto LABEL_13;
    }
  }
  v8 = (**(__int64 (__fastcall ***)(CAccountsSettingsPaneStatics *, const struct _GUID *, void **))v14)(v14, a4, v7);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = 356;
    goto LABEL_13;
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return v9;
}

```

## disassembly

```asm
0x180027904  mov     [rsp-28h+arg_10], r8b
0x180027909  mov     [rsp-28h+arg_8], rdx
0x18002790e  mov     [rsp-28h+arg_0], rcx
0x180027913  push    rbp
0x180027914  push    rbx
0x180027915  push    rsi
0x180027916  push    rdi
0x180027917  push    r14; int
0x180027919  mov     rbp, rsp
0x18002791c  sub     rsp, 20h
0x180027920  mov     r14, r9
0x180027923  mov     rdi, rdx
0x180027926  mov     rsi, [rbp+arg_20]
0x18002792a  mov     qword ptr [rsi], 0
0x180027931  test    r8b, r8b
0x180027934  jz      short loc_18002794B
0x180027936  mov     edx, 2; gaFlags
0x18002793b  mov     rcx, rdi; hwnd
0x18002793e  call    cs:__imp_GetAncestor
0x180027944  mov     rdi, rax
0x180027947  mov     [rbp+arg_8], rax
0x18002794b  mov     [rbp+arg_0], 0
0x180027953  lea     rcx, [rbp+arg_0]
0x180027957  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002795c  lea     r9, [rbp+arg_0]
0x180027960  lea     r8, _GUID_81ea942c_4f09_4406_a538_838d9b14b7e6
0x180027967  lea     rdx, IID_IImmersiveAccountsSettings
0x18002796e  mov     rcx, rdi
0x180027971  call    cs:__imp_CoreQueryWindowService
0x180027977  mov     ebx, eax
0x180027979  test    eax, eax
0x18002797b  jns     short loc_18002798B
0x18002797d  cmp     eax, 80040155h
0x180027982  jz      short loc_180027992
0x180027984  mov     edx, 15Bh
0x180027989  jmp     short loc_1800279FA
0x18002798b  cmp     eax, 80040155h
0x180027990  jnz     short loc_1800279DA
0x180027992  lea     rcx, [rbp+arg_0]
0x180027996  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002799b  lea     r8, [rbp+arg_10]
0x18002799f  lea     rdx, [rbp+arg_8]
0x1800279a3  lea     rcx, [rbp+arg_0]
0x1800279a7  call    ??$MakeAndInitialize@VCAccountsSettingsPane@@UIAccountsSettingsPane@ApplicationSettings@UI@Windows@@AEAPEAUHWND__@@AEA_N@Details@WRL@Microsoft@@YAJPEAPEAUIAccountsSettingsPane@ApplicationSettings@UI@Windows@@AEAPEAUHWND__@@AEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<CAccountsSettingsPane,Windows::UI::ApplicationSettings::IAccountsSettingsPane,HWND__ * &,bool &>(Windows::UI::ApplicationSettings::IAccountsSettingsPane * *,HWND__ * &,bool &)
0x1800279ac  mov     ebx, eax
0x1800279ae  test    eax, eax
0x1800279b0  jns     short loc_1800279B9
0x1800279b2  mov     edx, 160h
0x1800279b7  jmp     short loc_1800279FA
0x1800279b9  mov     r8, [rbp+arg_0]
0x1800279bd  lea     rdx, IID_IImmersiveAccountsSettings
0x1800279c4  mov     rcx, rdi
0x1800279c7  call    cs:__imp_CoreRegisterWindowService
0x1800279cd  mov     ebx, eax
0x1800279cf  test    eax, eax
0x1800279d1  jns     short loc_1800279DA
0x1800279d3  mov     edx, 161h
0x1800279d8  jmp     short loc_1800279FA
0x1800279da  mov     rcx, [rbp+arg_0]
0x1800279de  mov     rax, [rcx]
0x1800279e1  mov     r8, rsi
0x1800279e4  mov     rdx, r14
0x1800279e7  mov     rax, [rax]
0x1800279ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ef  mov     ebx, eax
0x1800279f1  test    eax, eax
0x1800279f3  jns     short loc_180027A0D
0x1800279f5  mov     edx, 164h; void *
0x1800279fa  mov     r9d, eax; char *
0x1800279fd  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x180027a04  mov     rcx, [rbp+28h]; this
0x180027a08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a0d  lea     rcx, [rbp+arg_0]
0x180027a11  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027a16  mov     eax, ebx
0x180027a18  add     rsp, 20h
0x180027a1c  pop     r14
0x180027a1e  pop     rdi
0x180027a1f  pop     rsi
0x180027a20  pop     rbx
0x180027a21  pop     rbp
0x180027a22  retn
```
