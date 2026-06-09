# CActivationBrokerManager::ActivateApplicationWithExtensionId(ulong,ulong,_GUID,ulong,ushort const *,ushort const *,ushort const *,IInspectable *,ACTIVATEOPTIONS,unsigned __int64,IInspectable *,ulong *)

- ea: `0x180064870`
- end: `0x180064c67`
- name: `?ActivateApplicationWithExtensionId@CActivationBrokerManager@@UEAAJKKU_GUID@@KPEBG11PEAUIInspectable@@W4ACTIVATEOPTIONS@@_K2PEAK@Z`
- size: `1015`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18004ada0`
- `0x18004c650`
- `0x18005ae90`
- `0x18005ed94`
- `0x18005ede8`
- `0x1800634cc`
- `0x180064870`
- `0x1800a0010`

## import_xrefs

- `ext-ms-win-desktopappx-l1-1-6!DoesPluginSupportCentennial` at `0x180064a8f`
- `ext-ms-win-desktopappx-l1-1-6!DoesPluginSupportCentennial` at `0x180064a8f`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180064aed`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180064aed`

## string_xrefs

- `0x18006493c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x1800649d1`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180064a37`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`
- `0x180064b59`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\activationbrokermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CActivationBrokerManager::ActivateApplicationWithExtensionId(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        struct _GUID *a4,
        __int64 a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        _WORD *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        _DWORD *a13)
{
  int Plugin; // eax
  int v17; // ebx
  __int64 v18; // r9
  __int64 v19; // rdx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  struct IActivationBrokerPlugin *v22; // rbx
  __int64 (__fastcall *v23)(struct IActivationBrokerPlugin *, GUID *, __int64 *); // rdi
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  int v28; // edi
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r14
  __int64 (__fastcall *v32)(__int64, _QWORD, _QWORD, __int64); // rsi
  int v33; // edi
  __int64 v34; // rbx
  int v36; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  struct IActivationBrokerPlugin *v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v43; // [rsp+7Ch] [rbp-84h]
  unsigned int v44; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v45; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v46; // [rsp+90h] [rbp-70h]
  _QWORD v47[5]; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+C8h] [rbp-38h]
  unsigned int v49; // [rsp+CCh] [rbp-34h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  struct _GUID v52; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v53[4]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v54[4]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  v44 = a3;
  v46 = a6;
  v45 = a7;
  v40 = a12;
  *a13 = 0;
  v41 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  v52 = *a4;
  Plugin = CActivationBrokerManager::_GetPlugin((CActivationBrokerManager *)(a1 - 136), &v52, &v41);
  v17 = Plugin;
  if ( Plugin >= 0 )
  {
    if ( !v41 )
    {
      v19 = 547;
LABEL_5:
      v17 = -2147024809;
      v18 = 2147942487LL;
      goto LABEL_6;
    }
    v20 = (_QWORD *)(*(__int64 (__fastcall **)(struct IActivationBrokerPlugin *, struct _GUID *))(*(_QWORD *)v41 + 24LL))(
                      v41,
                      &v52);
    v21 = *v20 - *(_QWORD *)&a4->Data1;
    if ( *v20 == *(_QWORD *)&a4->Data1 )
      v21 = v20[1] - *(_QWORD *)a4->Data4;
    if ( v21 )
    {
      v19 = 550;
      goto LABEL_5;
    }
    v43 = (*(__int64 (__fastcall **)(struct IActivationBrokerPlugin *))(*(_QWORD *)v41 + 40LL))(v41);
    v38 = 0;
    v22 = v41;
    v23 = **(__int64 (__fastcall ***)(struct IActivationBrokerPlugin *, GUID *, __int64 *))v41;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    v17 = v23(v22, &GUID_dca2e8b5_4c76_4593_9fe1_03c0c7284ede, &v38);
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
        (const char *)(unsigned int)v17,
        v36);
LABEL_13:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
      goto LABEL_38;
    }
    v37 = 0;
    v24 = v38;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 24LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    v26 = v25(v24, a9, &v37);
    v17 = v26;
    if ( v26 < 0 )
    {
      v27 = 562;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
        (const char *)(unsigned int)v26,
        v36);
LABEL_17:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      goto LABEL_13;
    }
    if ( !a8
      || !*a8
      || !(unsigned __int8)IsDoesPluginSupportCentennialPresent()
      || !(unsigned __int8)IsTryActivateDesktopAppXApplicationPresent() )
    {
      goto LABEL_29;
    }
    v42 = 0;
    v26 = DoesPluginSupportCentennial(a4, &v42);
    v17 = v26;
    if ( v26 < 0 )
    {
      v27 = 567;
      goto LABEL_16;
    }
    if ( v42 )
    {
      v47[1] = 1;
      v47[4] = 0;
      v48 = 0;
      *(_QWORD *)&v52.Data1 = 0;
      v47[0] = a8;
      v50 = a11;
      v47[2] = v45;
      v47[3] = v37;
      v49 = a2;
      v28 = v40;
      v51 = v40;
      v26 = TryActivateDesktopAppXApplication(v47, &v52);
      v17 = v26;
      if ( v26 < 0 )
      {
        v27 = 579;
        goto LABEL_16;
      }
      if ( !v52.Data1 )
      {
        *a13 = *(_DWORD *)&v52.Data2;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
        v17 = 0;
        goto LABEL_38;
      }
    }
    else
    {
LABEL_29:
      v28 = v40;
    }
    v39 = 0;
    v29 = Microsoft::WRL::Details::MakeAndInitialize<Execution::ActivationManagerShim,IApplicationActivationManagerPriv,>(&v39);
    v17 = v29;
    if ( v29 >= 0 )
    {
      v36 = v28;
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v39 + 136LL))(v39, v44, a2, v43);
      v17 = v29;
      if ( v29 >= 0 )
      {
        v31 = v39;
        v32 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v39 + 72LL);
        v33 = v37;
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v53, v45);
        v34 = v53[0];
        Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v54, v46);
        v36 = v33;
        v29 = v32(v31, v54[0], 0, v34);
        v17 = v29;
        if ( v29 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
          v17 = 0;
          goto LABEL_38;
        }
        v30 = 603;
      }
      else
      {
        v30 = 594;
      }
    }
    else
    {
      v30 = 591;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
      (const char *)(unsigned int)v29,
      v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    goto LABEL_17;
  }
  v18 = (unsigned int)Plugin;
  v19 = 546;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationbrokermanager.cpp",
    (const char *)v18,
    v36);
LABEL_38:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180064870  push    rbp
0x180064872  push    rbx
0x180064873  push    rsi
0x180064874  push    rdi
0x180064875  push    r12
0x180064877  push    r13
0x180064879  push    r14
0x18006487b  push    r15
0x18006487d  lea     rbp, [rsp-48h]
0x180064882  sub     rsp, 148h
0x180064889  mov     rax, cs:__security_cookie
0x180064890  xor     rax, rsp
0x180064893  mov     [rbp+80h+var_50], rax
0x180064897  mov     r14, r9
0x18006489a  mov     [rbp+80h+var_100], r8d
0x18006489e  mov     r13d, edx
0x1800648a1  mov     rbx, rcx
0x1800648a4  mov     rax, [rbp+80h+arg_28]
0x1800648ab  mov     [rbp+80h+var_F0], rax
0x1800648af  mov     rax, [rbp+80h+arg_30]
0x1800648b6  mov     [rbp+80h+var_F8], rax
0x1800648ba  mov     rsi, [rbp+80h+arg_38]
0x1800648c1  mov     r15, [rbp+80h+arg_40]
0x1800648c8  mov     rax, [rbp+80h+arg_58]
0x1800648cf  mov     [rsp+180h+var_118], rax
0x1800648d4  mov     r12, [rbp+80h+arg_60]
0x1800648db  xor     edi, edi
0x1800648dd  mov     [r12], edi
0x1800648e1  mov     [rsp+180h+var_110], rdi
0x1800648e6  lea     rcx, [rsp+180h+var_110]
0x1800648eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800648f0  movups  xmm0, xmmword ptr [r14]
0x1800648f4  movdqu  xmmword ptr [rbp+80h+var_A0.Data1], xmm0
0x1800648f9  lea     rcx, [rbx-88h]; this
0x180064900  lea     r8, [rsp+180h+var_110]; struct IActivationBrokerPlugin **
0x180064905  lea     rdx, [rbp+80h+var_A0]; struct _GUID
0x180064909  call    ?_GetPlugin@CActivationBrokerManager@@AEAAJU_GUID@@PEAPEAUIActivationBrokerPlugin@@@Z; CActivationBrokerManager::_GetPlugin(_GUID,IActivationBrokerPlugin * *)
0x18006490e  mov     ebx, eax
0x180064910  test    eax, eax
0x180064912  jns     short loc_18006491E
0x180064914  mov     r9d, eax
0x180064917  mov     edx, 222h
0x18006491c  jmp     short loc_180064935
0x18006491e  mov     rcx, [rsp+180h+var_110]
0x180064923  test    rcx, rcx
0x180064926  jnz     short loc_18006494D
0x180064928  mov     edx, 223h; void *
0x18006492d  mov     ebx, 80070057h
0x180064932  mov     r9d, ebx; char *
0x180064935  mov     rcx, [rbp+88h]; this
0x18006493c  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180064943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064948  jmp     loc_180064C3B
0x18006494d  mov     rax, [rcx]
0x180064950  lea     rdx, [rbp+80h+var_A0]
0x180064954  mov     rax, [rax+18h]
0x180064958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006495d  mov     rcx, [rax]
0x180064960  sub     rcx, [r14]
0x180064963  jnz     short loc_18006496D
0x180064965  mov     rcx, [rax+8]
0x180064969  sub     rcx, [r14+8]
0x18006496d  test    rcx, rcx
0x180064970  jz      short loc_180064979
0x180064972  mov     edx, 226h
0x180064977  jmp     short loc_18006492D
0x180064979  mov     rcx, [rsp+180h+var_110]
0x18006497e  mov     rax, [rcx]
0x180064981  mov     rax, [rax+28h]
0x180064985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006498a  mov     [rsp+180h+var_104], eax
0x18006498e  mov     [rsp+180h+var_128], rdi
0x180064993  mov     rbx, [rsp+180h+var_110]
0x180064998  mov     rcx, [rbx]
0x18006499b  mov     rdi, [rcx]
0x18006499e  lea     rcx, [rsp+180h+var_128]
0x1800649a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800649a8  lea     r8, [rsp+180h+var_128]
0x1800649ad  lea     rdx, _GUID_dca2e8b5_4c76_4593_9fe1_03c0c7284ede
0x1800649b4  mov     rcx, rbx
0x1800649b7  mov     rax, rdi
0x1800649ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800649bf  mov     ebx, eax
0x1800649c1  xor     eax, eax
0x1800649c3  test    ebx, ebx
0x1800649c5  jns     short loc_1800649F2
0x1800649c7  mov     rcx, [rbp+88h]; this
0x1800649ce  mov     r9d, ebx; char *
0x1800649d1  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800649d8  mov     edx, 22Eh; void *
0x1800649dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800649e2  nop
0x1800649e3  lea     rcx, [rsp+180h+var_128]
0x1800649e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800649ed  jmp     loc_180064C3B
0x1800649f2  mov     [rsp+180h+var_130], rax
0x1800649f7  mov     rdi, [rsp+180h+var_128]
0x1800649fc  mov     rax, [rdi]
0x1800649ff  mov     rbx, [rax+18h]
0x180064a03  lea     rcx, [rsp+180h+var_130]
0x180064a08  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064a0d  lea     r8, [rsp+180h+var_130]
0x180064a12  mov     rdx, r15
0x180064a15  mov     rcx, rdi
0x180064a18  mov     rax, rbx
0x180064a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064a20  mov     ebx, eax
0x180064a22  xor     edi, edi
0x180064a24  test    eax, eax
0x180064a26  jns     short loc_180064A50
0x180064a28  mov     edx, 232h; void *
0x180064a2d  mov     rcx, [rbp+88h]; this
0x180064a34  mov     r9d, eax; char *
0x180064a37  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180064a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064a43  nop
0x180064a44  lea     rcx, [rsp+180h+var_130]
0x180064a49  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064a4e  jmp     short loc_1800649E3
0x180064a50  mov     r15, [rbp+80h+arg_50]
0x180064a57  test    rsi, rsi
0x180064a5a  jz      loc_180064B2C
0x180064a60  cmp     [rsi], di
0x180064a63  jz      loc_180064B2C
0x180064a69  call    IsDoesPluginSupportCentennialPresent
0x180064a6e  test    al, al
0x180064a70  jz      loc_180064B2C
0x180064a76  call    IsTryActivateDesktopAppXApplicationPresent
0x180064a7b  test    al, al
0x180064a7d  jz      loc_180064B2C
0x180064a83  mov     [rsp+180h+var_108], edi
0x180064a87  lea     rdx, [rsp+180h+var_108]
0x180064a8c  mov     rcx, r14
0x180064a8f  call    cs:__imp_DoesPluginSupportCentennial
0x180064a95  mov     ebx, eax
0x180064a97  test    eax, eax
0x180064a99  jns     short loc_180064AA2
0x180064a9b  mov     edx, 237h
0x180064aa0  jmp     short loc_180064A2D
0x180064aa2  cmp     [rsp+180h+var_108], edi
0x180064aa6  jz      loc_180064B2C
0x180064aac  mov     [rbp+80h+var_D8], 1
0x180064ab4  mov     [rbp+80h+var_C0], rdi
0x180064ab8  mov     [rbp+80h+var_B8], edi
0x180064abb  mov     qword ptr [rbp+80h+var_A0.Data1], rdi
0x180064abf  mov     [rbp+80h+var_E0], rsi
0x180064ac3  mov     [rbp+80h+var_B0], r15
0x180064ac7  mov     rax, [rbp+80h+var_F8]
0x180064acb  mov     [rbp+80h+var_D0], rax
0x180064acf  mov     rax, [rsp+180h+var_130]
0x180064ad4  mov     [rbp+80h+var_C8], rax
0x180064ad8  mov     [rbp+80h+var_B4], r13d
0x180064adc  mov     rdi, [rsp+180h+var_118]
0x180064ae1  mov     [rbp+80h+var_A8], rdi
0x180064ae5  lea     rdx, [rbp+80h+var_A0]
0x180064ae9  lea     rcx, [rbp+80h+var_E0]
0x180064aed  call    cs:__imp_TryActivateDesktopAppXApplication
0x180064af3  mov     ebx, eax
0x180064af5  test    eax, eax
0x180064af7  jns     short loc_180064B03
0x180064af9  mov     edx, 243h
0x180064afe  jmp     loc_180064A2D
0x180064b03  cmp     [rbp+80h+var_A0.Data1], 0
0x180064b07  jnz     short loc_180064B31
0x180064b09  mov     eax, dword ptr [rbp+80h+var_A0.Data2]
0x180064b0c  mov     [r12], eax
0x180064b10  lea     rcx, [rsp+180h+var_130]
0x180064b15  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064b1a  nop
0x180064b1b  lea     rcx, [rsp+180h+var_128]
0x180064b20  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064b25  xor     ebx, ebx
0x180064b27  jmp     loc_180064C3B
0x180064b2c  mov     rdi, [rsp+180h+var_118]
0x180064b31  mov     [rsp+180h+var_120], 0
0x180064b3a  lea     rcx, [rsp+180h+var_120]
0x180064b3f  call    ??$MakeAndInitialize@VActivationManagerShim@Execution@@UIApplicationActivationManagerPriv@@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIApplicationActivationManagerPriv@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<Execution::ActivationManagerShim,IApplicationActivationManagerPriv,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IApplicationActivationManagerPriv>>)
0x180064b44  mov     ebx, eax
0x180064b46  test    eax, eax
0x180064b48  jns     short loc_180064B75
0x180064b4a  mov     edx, 24Fh; void *
0x180064b4f  mov     rcx, [rbp+88h]; this
0x180064b56  mov     r9d, eax; char *
0x180064b59  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180064b60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180064b65  nop
0x180064b66  lea     rcx, [rsp+180h+var_120]
0x180064b6b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064b70  jmp     loc_180064A44
0x180064b75  mov     rcx, [rsp+180h+var_120]
0x180064b7a  mov     rax, [rcx]
0x180064b7d  mov     [rsp+180h+var_160], rdi
0x180064b82  mov     r9d, [rsp+180h+var_104]
0x180064b87  mov     r8d, r13d
0x180064b8a  mov     edx, [rbp+80h+var_100]
0x180064b8d  mov     rax, [rax+88h]
0x180064b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064b99  mov     ebx, eax
0x180064b9b  xor     r13d, r13d
0x180064b9e  test    eax, eax
0x180064ba0  jns     short loc_180064BA9
0x180064ba2  mov     edx, 252h
0x180064ba7  jmp     short loc_180064B4F
0x180064ba9  mov     r14, [rsp+180h+var_120]
0x180064bae  mov     rax, [r14]
0x180064bb1  mov     rsi, [rax+48h]
0x180064bb5  mov     rdi, [rsp+180h+var_130]
0x180064bba  mov     rdx, [rbp+80h+var_F8]; unsigned __int16 *
0x180064bbe  lea     rcx, [rbp+80h+var_90]; this
0x180064bc2  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180064bc7  mov     rbx, [rbp+80h+var_90]
0x180064bcb  mov     rdx, [rbp+80h+var_F0]; unsigned __int16 *
0x180064bcf  lea     rcx, [rbp+80h+var_70]; this
0x180064bd3  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180064bd8  mov     [rsp+180h+var_148], r12
0x180064bdd  mov     [rsp+180h+var_150], r15
0x180064be2  mov     r8d, [rbp+80h+arg_48]
0x180064be9  mov     [rsp+180h+var_158], r8d
0x180064bee  mov     [rsp+180h+var_160], rdi
0x180064bf3  mov     r9, rbx
0x180064bf6  xor     r8d, r8d
0x180064bf9  mov     rdx, [rbp+80h+var_70]
0x180064bfd  mov     rcx, r14
0x180064c00  mov     rax, rsi
0x180064c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064c08  mov     ebx, eax
0x180064c0a  test    eax, eax
0x180064c0c  jns     short loc_180064C18
0x180064c0e  mov     edx, 25Bh
0x180064c13  jmp     loc_180064B4F
0x180064c18  lea     rcx, [rsp+180h+var_120]
0x180064c1d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064c22  nop
0x180064c23  lea     rcx, [rsp+180h+var_130]
0x180064c28  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064c2d  nop
0x180064c2e  lea     rcx, [rsp+180h+var_128]
0x180064c33  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064c38  mov     ebx, r13d
0x180064c3b  lea     rcx, [rsp+180h+var_110]
0x180064c40  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180064c45  mov     eax, ebx
0x180064c47  mov     rcx, [rbp+80h+var_50]
0x180064c4b  xor     rcx, rsp; StackCookie
0x180064c4e  call    __security_check_cookie
0x180064c53  add     rsp, 148h
0x180064c5a  pop     r15
0x180064c5c  pop     r14
0x180064c5e  pop     r13
0x180064c60  pop     r12
0x180064c62  pop     rdi
0x180064c63  pop     rsi
0x180064c64  pop     rbx
0x180064c65  pop     rbp
0x180064c66  retn
```
