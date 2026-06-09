# CloudExperienceHostWAMExecuteCommand::Execute(void)

- ea: `0x1400094e0`
- end: `0x140009803`
- name: `?Execute@CloudExperienceHostWAMExecuteCommand@@UEAAJXZ`
- size: `803`
- prototype: `__int64 __fastcall(CloudExperienceHostWAMExecuteCommand *this, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140005474`
- `0x1400094e0`
- `0x14000c6a0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000969e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000969e`
- `OLEAUT32!__imp_SysFreeString` at `0x140009641`
- `OLEAUT32!__imp_SysFreeString` at `0x1400096e2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000976c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400097c3`
- `OLEAUT32!__imp_SysFreeString` at `0x140009641`
- `OLEAUT32!__imp_SysFreeString` at `0x1400096e2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000976c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400097c3`

## string_xrefs

- `0x14000953a`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x1400095af`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x140009626`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x1400096b1`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000973b`: `shell\oobe\user\exe\useroobebroker.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostWAMExecuteCommand::Execute(
        CloudExperienceHostWAMExecuteCommand *this,
        __int64 a2)
{
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  LPVOID v16; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 *v18; // [rsp+58h] [rbp+18h] BYREF
  __int64 *v19; // [rsp+60h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+28h] BYREF

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CxhWamLauncher>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CxhWamLauncher>::GetImpl'::`2'::impl,
    a2);
  v3 = (__int64 *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    v18 = 0;
    v4 = *v3;
    v18 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v4 + 64))(v3, 0, &v18);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      if ( v18 )
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      return v6;
    }
    v19 = 0;
    v8 = *v18;
    v19 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const GUID *, GUID *))(v8 + 24))(
           v18,
           0,
           &BHID_SFUIObject,
           &GUID_a39ee748_6a27_4817_a6f2_13914bef5890);
    v6 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v9,
        (int)&v19);
      if ( v19 )
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      if ( v18 )
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      return v6;
    }
    bstrString = 0;
    v10 = *v19;
    bstrString = 0;
    v11 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v10 + 144))(v19, &bstrString);
    v6 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v11,
        (int)&v19);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v19 )
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      if ( v18 )
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      return v6;
    }
    v16 = 0;
    v12 = CoCreateInstance(
            &GUID_a72fccb0_07b3_4ebf_8b6f_33f08e3fce3d,
            0,
            1u,
            &GUID_c6078282_87c7_45e6_8a5c_a509237439aa,
            &v16);
    v6 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v12,
        ppva);
      if ( v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v19 )
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      if ( v18 )
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      return v6;
    }
    v13 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v16 + 24LL))(v16, bstrString);
    v6 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v13,
        ppva);
      if ( v16 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v19 )
        (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
      if ( v18 )
        (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
      return v6;
    }
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    if ( v18 )
      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1400094e0  mov     [rsp-8+arg_0], rbx
0x1400094e5  push    rbp
0x1400094e6  mov     rbp, rsp
0x1400094e9  sub     rsp, 40h
0x1400094ed  mov     rbx, rcx
0x1400094f0  mov     dl, 1
0x1400094f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CxhWamLauncher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CxhWamLauncher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CxhWamLauncher> `wil::Feature<__WilFeatureTraits_Feature_CxhWamLauncher>::GetImpl(void)'::`2'::impl
0x1400094f9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CxhWamLauncher@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CxhWamLauncher>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400094fe  mov     rcx, [rbx+18h]
0x140009502  test    rcx, rcx
0x140009505  jz      loc_1400097F6
0x14000950b  mov     [rbp+arg_8], 0
0x140009513  mov     rax, [rcx]
0x140009516  mov     [rbp+arg_8], 0
0x14000951e  lea     r8, [rbp+arg_8]
0x140009522  xor     edx, edx
0x140009524  mov     rax, [rax+40h]
0x140009528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000952d  mov     ebx, eax
0x14000952f  test    eax, eax
0x140009531  jns     short loc_140009569
0x140009533  mov     rcx, [rbp+8]; this
0x140009537  mov     r9d, eax; char *
0x14000953a  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x140009541  mov     edx, 68h ; 'h'; void *
0x140009546  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000954b  nop
0x14000954c  mov     rcx, [rbp+arg_8]
0x140009550  test    rcx, rcx
0x140009553  jz      short loc_140009562
0x140009555  mov     rax, [rcx]
0x140009558  mov     rax, [rax+10h]
0x14000955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009561  nop
0x140009562  mov     eax, ebx
0x140009564  jmp     loc_1400097F8
0x140009569  mov     [rbp+arg_10], 0
0x140009571  mov     rcx, [rbp+arg_8]
0x140009575  mov     rax, [rcx]
0x140009578  mov     [rbp+arg_10], 0
0x140009580  lea     rdx, [rbp+arg_10]
0x140009584  mov     qword ptr [rsp+40h+ppv], rdx; int
0x140009589  lea     r9, _GUID_a39ee748_6a27_4817_a6f2_13914bef5890
0x140009590  lea     r8, BHID_SFUIObject
0x140009597  xor     edx, edx
0x140009599  mov     rax, [rax+18h]
0x14000959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095a2  mov     ebx, eax
0x1400095a4  test    eax, eax
0x1400095a6  jns     short loc_1400095F2
0x1400095a8  mov     rcx, [rbp+8]; this
0x1400095ac  mov     r9d, eax; char *
0x1400095af  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x1400095b6  mov     edx, 6Ah ; 'j'; void *
0x1400095bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400095c0  nop
0x1400095c1  mov     rcx, [rbp+arg_10]
0x1400095c5  test    rcx, rcx
0x1400095c8  jz      short loc_1400095D7
0x1400095ca  mov     rax, [rcx]
0x1400095cd  mov     rax, [rax+10h]
0x1400095d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095d6  nop
0x1400095d7  mov     rcx, [rbp+arg_8]
0x1400095db  test    rcx, rcx
0x1400095de  jz      short loc_1400095ED
0x1400095e0  mov     rax, [rcx]
0x1400095e3  mov     rax, [rax+10h]
0x1400095e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095ec  nop
0x1400095ed  jmp     loc_140009562
0x1400095f2  mov     [rbp+bstrString], 0
0x1400095fa  mov     rcx, [rbp+arg_10]
0x1400095fe  mov     rax, [rcx]
0x140009601  mov     [rbp+bstrString], 0
0x140009609  lea     rdx, [rbp+bstrString]
0x14000960d  mov     rax, [rax+90h]
0x140009614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009619  mov     ebx, eax
0x14000961b  test    eax, eax
0x14000961d  jns     short loc_140009679
0x14000961f  mov     rcx, [rbp+8]; this
0x140009623  mov     r9d, eax; char *
0x140009626  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000962d  mov     edx, 6Ch ; 'l'; void *
0x140009632  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009637  nop
0x140009638  mov     rcx, [rbp+bstrString]; bstrString
0x14000963c  test    rcx, rcx
0x14000963f  jz      short loc_140009648
0x140009641  call    cs:__imp_SysFreeString
0x140009647  nop
0x140009648  mov     rcx, [rbp+arg_10]
0x14000964c  test    rcx, rcx
0x14000964f  jz      short loc_14000965E
0x140009651  mov     rax, [rcx]
0x140009654  mov     rax, [rax+10h]
0x140009658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000965d  nop
0x14000965e  mov     rcx, [rbp+arg_8]
0x140009662  test    rcx, rcx
0x140009665  jz      short loc_140009674
0x140009667  mov     rax, [rcx]
0x14000966a  mov     rax, [rax+10h]
0x14000966e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009673  nop
0x140009674  jmp     loc_140009562
0x140009679  mov     [rbp+var_10], 0
0x140009681  lea     rax, [rbp+var_10]
0x140009685  mov     qword ptr [rsp+40h+ppv], rax; int
0x14000968a  lea     r9, _GUID_c6078282_87c7_45e6_8a5c_a509237439aa; riid
0x140009691  xor     edx, edx; pUnkOuter
0x140009693  lea     r8d, [rdx+1]; dwClsContext
0x140009697  lea     rcx, _GUID_a72fccb0_07b3_4ebf_8b6f_33f08e3fce3d; rclsid
0x14000969e  call    cs:__imp_CoCreateInstance
0x1400096a4  mov     ebx, eax
0x1400096a6  test    eax, eax
0x1400096a8  jns     short loc_14000971A
0x1400096aa  mov     rcx, [rbp+8]; this
0x1400096ae  mov     r9d, eax; char *
0x1400096b1  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x1400096b8  mov     edx, 6Eh ; 'n'; void *
0x1400096bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400096c2  nop
0x1400096c3  mov     rcx, [rbp+var_10]
0x1400096c7  test    rcx, rcx
0x1400096ca  jz      short loc_1400096D9
0x1400096cc  mov     rax, [rcx]
0x1400096cf  mov     rax, [rax+10h]
0x1400096d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096d8  nop
0x1400096d9  mov     rcx, [rbp+bstrString]; bstrString
0x1400096dd  test    rcx, rcx
0x1400096e0  jz      short loc_1400096E9
0x1400096e2  call    cs:__imp_SysFreeString
0x1400096e8  nop
0x1400096e9  mov     rcx, [rbp+arg_10]
0x1400096ed  test    rcx, rcx
0x1400096f0  jz      short loc_1400096FF
0x1400096f2  mov     rax, [rcx]
0x1400096f5  mov     rax, [rax+10h]
0x1400096f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096fe  nop
0x1400096ff  mov     rcx, [rbp+arg_8]
0x140009703  test    rcx, rcx
0x140009706  jz      short loc_140009715
0x140009708  mov     rax, [rcx]
0x14000970b  mov     rax, [rax+10h]
0x14000970f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009714  nop
0x140009715  jmp     loc_140009562
0x14000971a  mov     rcx, [rbp+var_10]
0x14000971e  mov     rax, [rcx]
0x140009721  mov     rdx, [rbp+bstrString]
0x140009725  mov     rax, [rax+18h]
0x140009729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000972e  mov     ebx, eax
0x140009730  test    eax, eax
0x140009732  jns     short loc_1400097A4
0x140009734  mov     rcx, [rbp+8]; this
0x140009738  mov     r9d, eax; char *
0x14000973b  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x140009742  mov     edx, 6Fh ; 'o'; void *
0x140009747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000974c  nop
0x14000974d  mov     rcx, [rbp+var_10]
0x140009751  test    rcx, rcx
0x140009754  jz      short loc_140009763
0x140009756  mov     rax, [rcx]
0x140009759  mov     rax, [rax+10h]
0x14000975d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009762  nop
0x140009763  mov     rcx, [rbp+bstrString]; bstrString
0x140009767  test    rcx, rcx
0x14000976a  jz      short loc_140009773
0x14000976c  call    cs:__imp_SysFreeString
0x140009772  nop
0x140009773  mov     rcx, [rbp+arg_10]
0x140009777  test    rcx, rcx
0x14000977a  jz      short loc_140009789
0x14000977c  mov     rax, [rcx]
0x14000977f  mov     rax, [rax+10h]
0x140009783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009788  nop
0x140009789  mov     rcx, [rbp+arg_8]
0x14000978d  test    rcx, rcx
0x140009790  jz      short loc_14000979F
0x140009792  mov     rax, [rcx]
0x140009795  mov     rax, [rax+10h]
0x140009799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000979e  nop
0x14000979f  jmp     loc_140009562
0x1400097a4  mov     rcx, [rbp+var_10]
0x1400097a8  test    rcx, rcx
0x1400097ab  jz      short loc_1400097BA
0x1400097ad  mov     rax, [rcx]
0x1400097b0  mov     rax, [rax+10h]
0x1400097b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097b9  nop
0x1400097ba  mov     rcx, [rbp+bstrString]; bstrString
0x1400097be  test    rcx, rcx
0x1400097c1  jz      short loc_1400097CA
0x1400097c3  call    cs:__imp_SysFreeString
0x1400097c9  nop
0x1400097ca  mov     rcx, [rbp+arg_10]
0x1400097ce  test    rcx, rcx
0x1400097d1  jz      short loc_1400097E0
0x1400097d3  mov     rax, [rcx]
0x1400097d6  mov     rax, [rax+10h]
0x1400097da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097df  nop
0x1400097e0  mov     rcx, [rbp+arg_8]
0x1400097e4  test    rcx, rcx
0x1400097e7  jz      short loc_1400097F6
0x1400097e9  mov     rax, [rcx]
0x1400097ec  mov     rax, [rax+10h]
0x1400097f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400097f5  nop
0x1400097f6  xor     eax, eax
0x1400097f8  mov     rbx, [rsp+40h+arg_0]
0x1400097fd  add     rsp, 40h
0x140009801  pop     rbp
0x140009802  retn
```
