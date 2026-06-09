# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)

- ea: `0x1800434e4`
- end: `0x18004376a`
- name: `?GetPackageFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `646`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ff70`
- `0x180043908`
- `0x180043ce0`
- `0x18004430c`
- `0x180045954`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x180013be0`
- `0x18003e754`
- `0x1800434e4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800435af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043743`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800435af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043743`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  char v9; // r8
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64, HSTRING, __int64); // rbx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int v16; // eax
  unsigned __int64 v17; // r14
  unsigned int i; // esi
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdx
  int v24; // [rsp+20h] [rbp-40h]
  int v25[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v26; // [rsp+38h] [rbp-28h] BYREF
  __int64 v27; // [rsp+40h] [rbp-20h] BYREF
  __int64 v28; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v31; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v32; // [rsp+A8h] [rbp+48h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+58h] BYREF

  v32 = a2;
  if ( *(_QWORD *)(a1 + 376) )
  {
    v28 = 0;
    v6 = *(_QWORD *)(a1 + 392);
    v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    v8 = v7(v6, &v28);
    v5 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v8,
        v24);
LABEL_29:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      return v5;
    }
    string = 0;
    v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(
            (Microsoft::WRL::Wrappers::HString *)&string,
            &v32,
            v9);
    v5 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v10,
        v24);
LABEL_7:
      WindowsDeleteString(string);
LABEL_28:
      string = 0;
      goto LABEL_29;
    }
    *(_QWORD *)v25 = 0;
    v11 = *(_QWORD *)(a1 + 376);
    v12 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING, __int64))(*(_QWORD *)v11 + 424LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    v13 = v12(v11, v28, string, 1);
    v5 = v13;
    if ( v13 >= 0 )
    {
      v31 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v25 + 56LL))(*(_QWORD *)v25, &v31);
      v5 = v13;
      if ( v13 >= 0 )
      {
        v16 = v31;
        if ( v31 )
        {
          v17 = 0;
          v27 = 0;
          for ( i = 0; i < v16; ++i )
          {
            v26 = 0;
            v19 = *(_QWORD *)v25;
            v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v25 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v21 = v20(v19, i, &v26);
            v5 = v21;
            if ( v21 < 0 )
            {
              v22 = 377;
              goto LABEL_25;
            }
            v29 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v26 + 104LL))(v26, &v29);
            v5 = v21;
            if ( v21 < 0 )
            {
              v22 = 380;
LABEL_25:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v22,
                (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
                (const char *)(unsigned int)v21,
                (int)v25);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              goto LABEL_12;
            }
            if ( v29 >= v17 )
            {
              v17 = v29;
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(&v27, &v26);
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
            v16 = v31;
          }
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(a3, &v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
          WindowsDeleteString(string);
          v5 = 0;
          goto LABEL_28;
        }
        v5 = -2147467259;
        v15 = 2147500037LL;
        v14 = 370;
        goto LABEL_11;
      }
      v14 = 369;
    }
    else
    {
      v14 = 366;
    }
    v15 = (unsigned int)v13;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)v15,
      (int)v25);
LABEL_12:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v25);
    goto LABEL_7;
  }
  v5 = -2147467259;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x162,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
    (const char *)0x80004005LL,
    v24);
  return v5;
}

```

## disassembly

```asm
0x1800434e4  mov     [rsp-38h+arg_8], rdx
0x1800434e9  push    rbp
0x1800434ea  push    rbx
0x1800434eb  push    rsi
0x1800434ec  push    rdi
0x1800434ed  push    r12
0x1800434ef  push    r14
0x1800434f1  push    r15
0x1800434f3  mov     rbp, rsp
0x1800434f6  sub     rsp, 60h
0x1800434fa  mov     r15, r8
0x1800434fd  mov     rsi, rcx
0x180043500  xor     r12d, r12d
0x180043503  cmp     [rcx+178h], r12
0x18004350a  jnz     short loc_18004352E
0x18004350c  mov     rcx, [rbp+38h]; this
0x180043510  mov     ebx, 80004005h
0x180043515  mov     r9d, ebx; char *
0x180043518  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004351f  mov     edx, 162h; void *
0x180043524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043529  jmp     loc_180043759
0x18004352e  mov     [rbp+var_18], r12
0x180043532  mov     rdi, [rcx+188h]
0x180043539  mov     rax, [rdi]
0x18004353c  mov     rbx, [rax+68h]
0x180043540  lea     rcx, [rbp+var_18]
0x180043544  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043549  lea     rdx, [rbp+var_18]
0x18004354d  mov     rcx, rdi
0x180043550  mov     rax, rbx
0x180043553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043558  mov     ebx, eax
0x18004355a  test    eax, eax
0x18004355c  jns     short loc_18004357B
0x18004355e  mov     rcx, [rbp+38h]; this
0x180043562  mov     r9d, eax; char *
0x180043565  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004356c  mov     edx, 165h; void *
0x180043571  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043576  jmp     loc_180043750
0x18004357b  mov     [rbp+string], r12
0x18004357f  lea     rdx, [rbp+arg_8]
0x180043583  lea     rcx, [rbp+string]
0x180043587  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004358c  mov     ebx, eax
0x18004358e  test    eax, eax
0x180043590  jns     short loc_1800435BA
0x180043592  mov     rcx, [rbp+38h]; this
0x180043596  mov     r9d, eax; char *
0x180043599  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800435a0  mov     edx, 168h; void *
0x1800435a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800435aa  nop
0x1800435ab  mov     rcx, [rbp+string]; string
0x1800435af  call    cs:__imp_WindowsDeleteString
0x1800435b5  jmp     loc_18004374C
0x1800435ba  mov     qword ptr [rbp+var_30], r12
0x1800435be  mov     rdi, [rsi+178h]
0x1800435c5  mov     rax, [rdi]
0x1800435c8  mov     rbx, [rax+1A8h]
0x1800435cf  lea     rcx, [rbp+var_30]
0x1800435d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800435d8  lea     rax, [rbp+var_30]
0x1800435dc  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800435e1  mov     r9d, 1
0x1800435e7  mov     r8, [rbp+string]
0x1800435eb  mov     rdx, [rbp+var_18]
0x1800435ef  mov     rcx, rdi
0x1800435f2  mov     rax, rbx
0x1800435f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435fa  mov     ebx, eax
0x1800435fc  test    eax, eax
0x1800435fe  jns     short loc_180043624
0x180043600  mov     edx, 16Eh; void *
0x180043605  mov     r9d, eax; char *
0x180043608  mov     rcx, [rbp+38h]; this
0x18004360c  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043618  nop
0x180043619  lea     rcx, [rbp+var_30]
0x18004361d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043622  jmp     short loc_1800435AB
0x180043624  mov     [rbp+arg_0], r12d
0x180043628  mov     rcx, qword ptr [rbp+var_30]
0x18004362c  mov     rax, [rcx]
0x18004362f  lea     rdx, [rbp+arg_0]
0x180043633  mov     rax, [rax+38h]
0x180043637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004363c  mov     ebx, eax
0x18004363e  test    eax, eax
0x180043640  jns     short loc_180043649
0x180043642  mov     edx, 171h
0x180043647  jmp     short loc_180043605
0x180043649  mov     eax, [rbp+arg_0]
0x18004364c  test    eax, eax
0x18004364e  jnz     short loc_18004365F
0x180043650  mov     ebx, 80004005h
0x180043655  mov     r9d, ebx
0x180043658  mov     edx, 172h
0x18004365d  jmp     short loc_180043608
0x18004365f  mov     r14, r12
0x180043662  mov     [rbp+var_20], r12
0x180043666  mov     esi, r12d
0x180043669  cmp     esi, eax
0x18004366b  jnb     loc_18004371E
0x180043671  mov     [rbp+var_28], r12
0x180043675  mov     rdi, qword ptr [rbp+var_30]
0x180043679  mov     rax, [rdi]
0x18004367c  mov     rbx, [rax+30h]
0x180043680  lea     rcx, [rbp+var_28]
0x180043684  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043689  lea     r8, [rbp+var_28]
0x18004368d  mov     edx, esi
0x18004368f  mov     rcx, rdi
0x180043692  mov     rax, rbx
0x180043695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004369a  mov     ebx, eax
0x18004369c  test    eax, eax
0x18004369e  js      short loc_180043717
0x1800436a0  mov     [rbp+var_10], r12
0x1800436a4  mov     rcx, [rbp+var_28]
0x1800436a8  mov     rax, [rcx]
0x1800436ab  lea     rdx, [rbp+var_10]
0x1800436af  mov     rax, [rax+68h]
0x1800436b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b8  mov     ebx, eax
0x1800436ba  test    eax, eax
0x1800436bc  js      short loc_1800436E6
0x1800436be  cmp     [rbp+var_10], r14
0x1800436c2  jb      short loc_1800436D6
0x1800436c4  mov     r14, [rbp+var_10]
0x1800436c8  lea     rdx, [rbp+var_28]
0x1800436cc  lea     rcx, [rbp+var_20]
0x1800436d0  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x1800436d5  nop
0x1800436d6  lea     rcx, [rbp+var_28]
0x1800436da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800436df  inc     esi
0x1800436e1  mov     eax, [rbp+arg_0]
0x1800436e4  jmp     short loc_180043669
0x1800436e6  mov     edx, 17Ch; void *
0x1800436eb  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800436f2  mov     r9d, eax; char *
0x1800436f5  mov     rcx, [rbp+38h]; this
0x1800436f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800436fe  nop
0x1800436ff  lea     rcx, [rbp+var_28]
0x180043703  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043708  nop
0x180043709  lea     rcx, [rbp+var_20]
0x18004370d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043712  jmp     loc_180043619
0x180043717  mov     edx, 179h
0x18004371c  jmp     short loc_1800436EB
0x18004371e  lea     rdx, [rbp+var_20]
0x180043722  mov     rcx, r15
0x180043725  call    ??4?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::operator=(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)
0x18004372a  nop
0x18004372b  lea     rcx, [rbp+var_20]
0x18004372f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043734  nop
0x180043735  lea     rcx, [rbp+var_30]
0x180043739  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004373e  nop
0x18004373f  mov     rcx, [rbp+string]; string
0x180043743  call    cs:__imp_WindowsDeleteString
0x180043749  mov     ebx, r12d
0x18004374c  mov     [rbp+string], r12
0x180043750  lea     rcx, [rbp+var_18]
0x180043754  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043759  mov     eax, ebx
0x18004375b  add     rsp, 60h
0x18004375f  pop     r15
0x180043761  pop     r14
0x180043763  pop     r12
0x180043765  pop     rdi
0x180043766  pop     rsi
0x180043767  pop     rbx
0x180043768  pop     rbp
0x180043769  retn
```
