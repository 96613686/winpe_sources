# CloudExperienceHostExecuteCommand::Execute(void)

- ea: `0x1400091c0`
- end: `0x1400094cb`
- name: `?Execute@CloudExperienceHostExecuteCommand@@UEAAJXZ`
- size: `779`
- prototype: `__int64 __fastcall(CloudExperienceHostExecuteCommand *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140005474`
- `0x1400091c0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000936a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000936a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000930d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400093ae`
- `OLEAUT32!__imp_SysFreeString` at `0x140009438`
- `OLEAUT32!__imp_SysFreeString` at `0x14000948f`
- `OLEAUT32!__imp_SysFreeString` at `0x14000930d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400093ae`
- `OLEAUT32!__imp_SysFreeString` at `0x140009438`
- `OLEAUT32!__imp_SysFreeString` at `0x14000948f`

## string_xrefs

- `0x140009206`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000927b`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x1400092f2`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x14000937d`: `shell\oobe\user\exe\useroobebroker.cpp`
- `0x140009407`: `shell\oobe\user\exe\useroobebroker.cpp`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostExecuteCommand::Execute(CloudExperienceHostExecuteCommand *this)
{
  __int64 *v1; // rcx
  __int64 v2; // rax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  HRESULT v10; // eax
  int v11; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+10h]
  __int64 *v15; // [rsp+50h] [rbp+18h] BYREF
  __int64 *v16; // [rsp+58h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+28h] BYREF
  LPVOID v18; // [rsp+68h] [rbp+30h] BYREF

  v1 = (__int64 *)*((_QWORD *)this + 3);
  if ( v1 )
  {
    v15 = 0;
    v2 = *v1;
    v15 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v2 + 64))(v1, 0, &v15);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v3,
        ppv);
      if ( v15 )
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      return v4;
    }
    v16 = 0;
    v6 = *v15;
    v16 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const GUID *, GUID *))(v6 + 24))(
           v15,
           0,
           &BHID_SFUIObject,
           &GUID_a39ee748_6a27_4817_a6f2_13914bef5890);
    v4 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v7,
        (int)&v16);
      if ( v16 )
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      if ( v15 )
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      return v4;
    }
    bstrString = 0;
    v8 = *v16;
    bstrString = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v8 + 144))(v16, &bstrString);
    v4 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v9,
        (int)&v16);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v16 )
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      if ( v15 )
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      return v4;
    }
    v18 = 0;
    v10 = CoCreateInstance(
            &GUID_640c3348_c248_4a32_a111_cea662bc9c96,
            0,
            1u,
            &GUID_c6078282_87c7_45e6_8a5c_a509237439aa,
            &v18);
    v4 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v10,
        ppva);
      if ( v18 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v16 )
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      if ( v15 )
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      return v4;
    }
    v11 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)v18 + 24LL))(v18, bstrString);
    v4 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"shell\\oobe\\user\\exe\\useroobebroker.cpp",
        (const char *)(unsigned int)v11,
        ppva);
      if ( v18 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v16 )
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      if ( v15 )
        (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
      return v4;
    }
    if ( v18 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v16 )
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1400091c0  push    rbp
0x1400091c2  push    rbx
0x1400091c3  mov     rbp, rsp
0x1400091c6  sub     rsp, 38h
0x1400091ca  mov     rcx, [rcx+18h]
0x1400091ce  test    rcx, rcx
0x1400091d1  jz      loc_1400094C2
0x1400091d7  mov     [rbp+arg_0], 0
0x1400091df  mov     rax, [rcx]
0x1400091e2  mov     [rbp+arg_0], 0
0x1400091ea  lea     r8, [rbp+arg_0]
0x1400091ee  xor     edx, edx
0x1400091f0  mov     rax, [rax+40h]
0x1400091f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091f9  mov     ebx, eax
0x1400091fb  test    eax, eax
0x1400091fd  jns     short loc_140009235
0x1400091ff  mov     rcx, [rbp+10h]; this
0x140009203  mov     r9d, eax; char *
0x140009206  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000920d  mov     edx, 3Ch ; '<'; void *
0x140009212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009217  nop
0x140009218  mov     rcx, [rbp+arg_0]
0x14000921c  test    rcx, rcx
0x14000921f  jz      short loc_14000922E
0x140009221  mov     rax, [rcx]
0x140009224  mov     rax, [rax+10h]
0x140009228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000922d  nop
0x14000922e  mov     eax, ebx
0x140009230  jmp     loc_1400094C4
0x140009235  mov     [rbp+arg_8], 0
0x14000923d  mov     rcx, [rbp+arg_0]
0x140009241  mov     rax, [rcx]
0x140009244  mov     [rbp+arg_8], 0
0x14000924c  lea     rdx, [rbp+arg_8]
0x140009250  mov     qword ptr [rsp+38h+ppv], rdx; int
0x140009255  lea     r9, _GUID_a39ee748_6a27_4817_a6f2_13914bef5890
0x14000925c  lea     r8, BHID_SFUIObject
0x140009263  xor     edx, edx
0x140009265  mov     rax, [rax+18h]
0x140009269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000926e  mov     ebx, eax
0x140009270  test    eax, eax
0x140009272  jns     short loc_1400092BE
0x140009274  mov     rcx, [rbp+10h]; this
0x140009278  mov     r9d, eax; char *
0x14000927b  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x140009282  mov     edx, 3Eh ; '>'; void *
0x140009287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000928c  nop
0x14000928d  mov     rcx, [rbp+arg_8]
0x140009291  test    rcx, rcx
0x140009294  jz      short loc_1400092A3
0x140009296  mov     rax, [rcx]
0x140009299  mov     rax, [rax+10h]
0x14000929d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092a2  nop
0x1400092a3  mov     rcx, [rbp+arg_0]
0x1400092a7  test    rcx, rcx
0x1400092aa  jz      short loc_1400092B9
0x1400092ac  mov     rax, [rcx]
0x1400092af  mov     rax, [rax+10h]
0x1400092b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092b8  nop
0x1400092b9  jmp     loc_14000922E
0x1400092be  mov     [rbp+bstrString], 0
0x1400092c6  mov     rcx, [rbp+arg_8]
0x1400092ca  mov     rax, [rcx]
0x1400092cd  mov     [rbp+bstrString], 0
0x1400092d5  lea     rdx, [rbp+bstrString]
0x1400092d9  mov     rax, [rax+90h]
0x1400092e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400092e5  mov     ebx, eax
0x1400092e7  test    eax, eax
0x1400092e9  jns     short loc_140009345
0x1400092eb  mov     rcx, [rbp+10h]; this
0x1400092ef  mov     r9d, eax; char *
0x1400092f2  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x1400092f9  mov     edx, 40h ; '@'; void *
0x1400092fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009303  nop
0x140009304  mov     rcx, [rbp+bstrString]; bstrString
0x140009308  test    rcx, rcx
0x14000930b  jz      short loc_140009314
0x14000930d  call    cs:__imp_SysFreeString
0x140009313  nop
0x140009314  mov     rcx, [rbp+arg_8]
0x140009318  test    rcx, rcx
0x14000931b  jz      short loc_14000932A
0x14000931d  mov     rax, [rcx]
0x140009320  mov     rax, [rax+10h]
0x140009324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009329  nop
0x14000932a  mov     rcx, [rbp+arg_0]
0x14000932e  test    rcx, rcx
0x140009331  jz      short loc_140009340
0x140009333  mov     rax, [rcx]
0x140009336  mov     rax, [rax+10h]
0x14000933a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000933f  nop
0x140009340  jmp     loc_14000922E
0x140009345  mov     [rbp+arg_18], 0
0x14000934d  lea     rax, [rbp+arg_18]
0x140009351  mov     qword ptr [rsp+38h+ppv], rax; int
0x140009356  lea     r9, _GUID_c6078282_87c7_45e6_8a5c_a509237439aa; riid
0x14000935d  xor     edx, edx; pUnkOuter
0x14000935f  lea     r8d, [rdx+1]; dwClsContext
0x140009363  lea     rcx, _GUID_640c3348_c248_4a32_a111_cea662bc9c96; rclsid
0x14000936a  call    cs:__imp_CoCreateInstance
0x140009370  mov     ebx, eax
0x140009372  test    eax, eax
0x140009374  jns     short loc_1400093E6
0x140009376  mov     rcx, [rbp+10h]; this
0x14000937a  mov     r9d, eax; char *
0x14000937d  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x140009384  mov     edx, 42h ; 'B'; void *
0x140009389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000938e  nop
0x14000938f  mov     rcx, [rbp+arg_18]
0x140009393  test    rcx, rcx
0x140009396  jz      short loc_1400093A5
0x140009398  mov     rax, [rcx]
0x14000939b  mov     rax, [rax+10h]
0x14000939f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093a4  nop
0x1400093a5  mov     rcx, [rbp+bstrString]; bstrString
0x1400093a9  test    rcx, rcx
0x1400093ac  jz      short loc_1400093B5
0x1400093ae  call    cs:__imp_SysFreeString
0x1400093b4  nop
0x1400093b5  mov     rcx, [rbp+arg_8]
0x1400093b9  test    rcx, rcx
0x1400093bc  jz      short loc_1400093CB
0x1400093be  mov     rax, [rcx]
0x1400093c1  mov     rax, [rax+10h]
0x1400093c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093ca  nop
0x1400093cb  mov     rcx, [rbp+arg_0]
0x1400093cf  test    rcx, rcx
0x1400093d2  jz      short loc_1400093E1
0x1400093d4  mov     rax, [rcx]
0x1400093d7  mov     rax, [rax+10h]
0x1400093db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093e0  nop
0x1400093e1  jmp     loc_14000922E
0x1400093e6  mov     rcx, [rbp+arg_18]
0x1400093ea  mov     rax, [rcx]
0x1400093ed  mov     rdx, [rbp+bstrString]
0x1400093f1  mov     rax, [rax+18h]
0x1400093f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400093fa  mov     ebx, eax
0x1400093fc  test    eax, eax
0x1400093fe  jns     short loc_140009470
0x140009400  mov     rcx, [rbp+10h]; this
0x140009404  mov     r9d, eax; char *
0x140009407  lea     r8, aShellOobeUserE; "shell\\oobe\\user\\exe\\useroobebroker."...
0x14000940e  mov     edx, 43h ; 'C'; void *
0x140009413  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009418  nop
0x140009419  mov     rcx, [rbp+arg_18]
0x14000941d  test    rcx, rcx
0x140009420  jz      short loc_14000942F
0x140009422  mov     rax, [rcx]
0x140009425  mov     rax, [rax+10h]
0x140009429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000942e  nop
0x14000942f  mov     rcx, [rbp+bstrString]; bstrString
0x140009433  test    rcx, rcx
0x140009436  jz      short loc_14000943F
0x140009438  call    cs:__imp_SysFreeString
0x14000943e  nop
0x14000943f  mov     rcx, [rbp+arg_8]
0x140009443  test    rcx, rcx
0x140009446  jz      short loc_140009455
0x140009448  mov     rax, [rcx]
0x14000944b  mov     rax, [rax+10h]
0x14000944f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009454  nop
0x140009455  mov     rcx, [rbp+arg_0]
0x140009459  test    rcx, rcx
0x14000945c  jz      short loc_14000946B
0x14000945e  mov     rax, [rcx]
0x140009461  mov     rax, [rax+10h]
0x140009465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000946a  nop
0x14000946b  jmp     loc_14000922E
0x140009470  mov     rcx, [rbp+arg_18]
0x140009474  test    rcx, rcx
0x140009477  jz      short loc_140009486
0x140009479  mov     rax, [rcx]
0x14000947c  mov     rax, [rax+10h]
0x140009480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009485  nop
0x140009486  mov     rcx, [rbp+bstrString]; bstrString
0x14000948a  test    rcx, rcx
0x14000948d  jz      short loc_140009496
0x14000948f  call    cs:__imp_SysFreeString
0x140009495  nop
0x140009496  mov     rcx, [rbp+arg_8]
0x14000949a  test    rcx, rcx
0x14000949d  jz      short loc_1400094AC
0x14000949f  mov     rax, [rcx]
0x1400094a2  mov     rax, [rax+10h]
0x1400094a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094ab  nop
0x1400094ac  mov     rcx, [rbp+arg_0]
0x1400094b0  test    rcx, rcx
0x1400094b3  jz      short loc_1400094C2
0x1400094b5  mov     rax, [rcx]
0x1400094b8  mov     rax, [rax+10h]
0x1400094bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094c1  nop
0x1400094c2  xor     eax, eax
0x1400094c4  add     rsp, 38h
0x1400094c8  pop     rbx
0x1400094c9  pop     rbp
0x1400094ca  retn
```
