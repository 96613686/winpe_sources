# ModalDialogBehavior::OnWindowMessage(uint,unsigned __int64,__int64)

- ea: `0x180028e10`
- end: `0x180028f05`
- name: `?OnWindowMessage@ModalDialogBehavior@@UEAA?AW4WindowMessageHandlingResult@@I_K_J@Z`
- size: `245`
- prototype: `enum WindowMessageHandlingResult __high(unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x18000d0f0`
- `0x18001047c`
- `0x18001049c`
- `0x180017164`
- `0x18001daf4`
- `0x18001dbfc`
- `0x180028e10`
- `0x18002c544`
- `0x18005a010`

## import_xrefs

- `USER32!EnableWindow` at `0x180028e89`
- `USER32!EnableWindow` at `0x180028e89`

## string_xrefs

- `0x180028edc`: `pcshell\shell\uxframe\dll\ModalWindowBehavior.h`
- `0x180028ef3`: `pcshell\shell\uxframe\dll\ModalWindowBehavior.h`

## pseudocode

```c
__int64 __fastcall ModalDialogBehavior::OnWindowMessage(__int64 a1, int a2, __int64 a3, const char *a4)
{
  HWND *v5; // rbx
  unsigned int v6; // edi
  HWND *v7; // r14
  _BYTE *v8; // rbp
  int v9; // esi
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v14; // [rsp+40h] [rbp+8h] BYREF

  v5 = (HWND *)(a1 + 40);
  if ( !*(_QWORD *)(a1 + 40) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB8,
      (unsigned int)"pcshell\\shell\\uxframe\\dll\\ModalWindowBehavior.h",
      a4);
  v6 = 0;
  if ( a2 == 16 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl'::`2'::impl) )
    {
      v11 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0xC3,
        (unsigned int)"pcshell\\shell\\uxframe\\dll\\ModalWindowBehavior.h",
        (const char *)v11,
        v12);
    }
    v7 = (HWND *)(a1 + 56);
    v8 = (_BYTE *)(a1 + 68);
    ModalDialogTelemetry::ModalDialog_Close_Start<HWND__ * &,HWND__ * &,bool &>(v5, a1 + 56, a1 + 68);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 32LL))(*(_QWORD *)(a1 + 24));
    if ( v9 )
    {
      v6 = 1;
    }
    else if ( *v8 )
    {
      EnableWindow(*v7, 1);
    }
    v14 = v9 == 0;
    ModalDialogTelemetry::ModalDialog_Close_Stop<HWND__ * &,HWND__ * &,bool>(v5, v7, &v14);
  }
  else if ( a2 != 26 )
  {
    return v6;
  }
  UpdateTitlebarForTheme(*v5);
  return v6;
}

```

## disassembly

```asm
0x180028e10  mov     [rsp+arg_8], rbx
0x180028e15  mov     [rsp+arg_10], rbp
0x180028e1a  push    rsi
0x180028e1b  push    rdi
0x180028e1c  push    r14; int
0x180028e1e  sub     rsp, 20h
0x180028e22  mov     rsi, rcx
0x180028e25  lea     rbx, [rcx+28h]
0x180028e29  cmp     qword ptr [rbx], 0
0x180028e2d  jz      loc_180028EEE
0x180028e33  xor     edi, edi
0x180028e35  cmp     edx, 10h
0x180028e38  jz      short loc_180028E41
0x180028e3a  cmp     edx, 1Ah
0x180028e3d  jz      short loc_180028EAD
0x180028e3f  jmp     short loc_180028EB5
0x180028e41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_5@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5> `wil::Feature<__WilFeatureTraits_Feature_SWT_5>::GetImpl(void)'::`2'::impl
0x180028e48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_5@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_5>::__private_IsEnabled(void)
0x180028e4d  test    al, al
0x180028e4f  jnz     short loc_180028ECA
0x180028e51  lea     r14, [rsi+38h]
0x180028e55  lea     rbp, [rsi+44h]
0x180028e59  mov     r8, rbp
0x180028e5c  mov     rdx, r14
0x180028e5f  mov     rcx, rbx
0x180028e62  call    ??$ModalDialog_Close_Start@AEAPEAUHWND__@@AEAPEAU1@AEA_N@ModalDialogTelemetry@@SAXAEAPEAUHWND__@@0AEA_N@Z; ModalDialogTelemetry::ModalDialog_Close_Start<HWND__ * &,HWND__ * &,bool &>(HWND__ * &,HWND__ * &,bool &)
0x180028e67  mov     rcx, [rsi+18h]
0x180028e6b  mov     rax, [rcx]
0x180028e6e  mov     rax, [rax+20h]
0x180028e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e77  mov     esi, eax
0x180028e79  test    eax, eax
0x180028e7b  jnz     short loc_180028E91
0x180028e7d  cmp     [rbp+0], dil
0x180028e81  jz      short loc_180028E96
0x180028e83  lea     edx, [rax+1]; bEnable
0x180028e86  mov     rcx, [r14]; hWnd
0x180028e89  call    cs:__imp_EnableWindow
0x180028e8f  jmp     short loc_180028E96
0x180028e91  mov     edi, 1
0x180028e96  test    esi, esi
0x180028e98  setz    [rsp+38h+arg_0]
0x180028e9d  lea     r8, [rsp+38h+arg_0]
0x180028ea2  mov     rdx, r14
0x180028ea5  mov     rcx, rbx
0x180028ea8  call    ??$ModalDialog_Close_Stop@AEAPEAUHWND__@@AEAPEAU1@_N@ModalDialogTelemetry@@SAXAEAPEAUHWND__@@0$$QEA_N@Z; ModalDialogTelemetry::ModalDialog_Close_Stop<HWND__ * &,HWND__ * &,bool>(HWND__ * &,HWND__ * &,bool &&)
0x180028ead  mov     rcx, [rbx]; hwnd
0x180028eb0  call    ?UpdateTitlebarForTheme@@YAXPEAUHWND__@@@Z; UpdateTitlebarForTheme(HWND__ *)
0x180028eb5  mov     eax, edi
0x180028eb7  mov     rbx, [rsp+38h+arg_8]
0x180028ebc  mov     rbp, [rsp+38h+arg_10]
0x180028ec1  add     rsp, 20h
0x180028ec5  pop     r14
0x180028ec7  pop     rdi
0x180028ec8  pop     rsi
0x180028ec9  retn
0x180028eca  mov     ecx, 8000FFFFh
0x180028ecf  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180028ed4  mov     r9d, eax; char *
0x180028ed7  mov     rcx, [rsp+38h]; this
0x180028edc  lea     r8, aPcshellShellUx_7; "pcshell\\shell\\uxframe\\dll\\ModalWind"...
0x180028ee3  mov     edx, 0C3h; void *
0x180028ee8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180028eee  mov     rcx, [rsp+38h]; this
0x180028ef3  lea     r8, aPcshellShellUx_7; "pcshell\\shell\\uxframe\\dll\\ModalWind"...
0x180028efa  mov     edx, 0B8h; void *
0x180028eff  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
