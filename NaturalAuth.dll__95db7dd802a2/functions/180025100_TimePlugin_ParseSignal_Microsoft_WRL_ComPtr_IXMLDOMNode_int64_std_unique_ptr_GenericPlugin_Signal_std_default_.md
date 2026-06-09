# TimePlugin::ParseSignal(Microsoft::WRL::ComPtr<IXMLDOMNode>,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x180025100`
- end: `0x1800253a6`
- name: `?ParseSignal@TimePlugin@@UEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005140`
- `0x18000a7f8`
- `0x180014e7c`
- `0x18001fc6c`
- `0x18001fcc4`
- `0x18002072c`
- `0x180021df4`
- `0x1800220d0`
- `0x180024f2c`
- `0x180025100`
- `0x1800257a4`
- `0x180025b4c`
- `0x180041d94`
- `0x180046010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TimePlugin::ParseSignal(__int64 a1, __int64 *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, unsigned __int16 **); // rbx
  unsigned __int16 **Address; // rax
  int v18; // eax
  const wchar_t **BSTR; // rax
  int v20; // eax
  int v21; // ebx
  const wchar_t **v22; // rax
  int v23; // eax
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[332]; // [rsp+64h] [rbp-9Ch] BYREF

  v29[0] = 0;
  v27 = 0;
  v30 = 0;
  memset_0(v31, 0, 0x118u);
  v8 = *a2;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
  v10 = v9(v8, v29);
  if ( v10 < 0 )
    _com_issue_error(v10);
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v29[0] + 64LL))(v29[0], &v27);
  if ( v11 < 0 )
    _com_issue_error(v11);
  if ( v27 != 1 )
    _com_raise_error(-2147023431, 0);
  v26 = 0;
  v12 = *a2;
  v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v14 = v13(v12, &v26);
  if ( v14 < 0 )
    _com_issue_error(v14);
  v28 = 0;
  v15 = v26;
  v16 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v26 + 56LL);
  Address = _bstr_t::GetAddress((_bstr_t *)&v28);
  v18 = v16(v15, Address);
  if ( v18 < 0 )
    _com_issue_error(v18);
  BSTR = (const wchar_t **)_bstr_t::GetBSTR((_bstr_t *)&v28);
  if ( !wcscmp_0(L"daily", *BSTR) )
  {
    v25 = v26;
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    v20 = ParseDay(&v25, v31, a5);
    if ( v20 < 0 )
      _com_issue_error(v20);
    if ( v31[0] && v31[20] )
      goto LABEL_18;
LABEL_29:
    RaiseSchemaError(&v28, a5);
  }
  v22 = (const wchar_t **)_bstr_t::GetBSTR((_bstr_t *)&v28);
  if ( wcscmp_0(L"weekly", *v22) )
    goto LABEL_29;
  v25 = v26;
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  v23 = ParseWeeklyRepeat(&v25, &v30, a5);
  if ( v23 < 0 )
    _com_issue_error(v23);
LABEL_18:
  _bstr_t::_Free((_bstr_t *)&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v21 = (*(__int64 (__fastcall **)(__int64, int *, __int64, __int64))(*(_QWORD *)qword_18005FE88 + 8LL))(
          qword_18005FE88,
          &v30,
          a3,
          a4);
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_c7aca68ec72034e268068f62b41653e8_Traceguids,
        (unsigned int)v21);
    _com_raise_error(v21, 0);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180025100  mov     [rsp-8+arg_8], rdx
0x180025105  push    rbp
0x180025106  push    rbx
0x180025107  push    rsi
0x180025108  push    rdi
0x180025109  push    r14
0x18002510b  push    r15
0x18002510d  lea     rbp, [rsp-88h]
0x180025115  sub     rsp, 188h
0x18002511c  mov     r14, r9
0x18002511f  mov     r15, r8
0x180025122  mov     rsi, rdx
0x180025125  mov     [rsp+1B0h+var_160], 0
0x18002512e  mov     [rsp+1B0h+var_170], 0
0x180025136  mov     [rsp+1B0h+var_150], 0
0x18002513e  xor     edx, edx; Val
0x180025140  mov     r8d, 118h; Size
0x180025146  lea     rcx, [rsp+1B0h+var_14C]; void *
0x18002514b  call    memset_0
0x180025150  mov     rdi, [rsi]
0x180025153  mov     rax, [rdi]
0x180025156  mov     rbx, [rax+60h]
0x18002515a  lea     rcx, [rsp+1B0h+var_160]
0x18002515f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025164  lea     rdx, [rsp+1B0h+var_160]
0x180025169  mov     rcx, rdi
0x18002516c  mov     rax, rbx
0x18002516f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025174  test    eax, eax
0x180025176  jns     short loc_180025180
0x180025178  mov     ecx, eax; int
0x18002517a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180025180  mov     rcx, [rsp+1B0h+var_160]
0x180025185  mov     rax, [rcx]
0x180025188  lea     rdx, [rsp+1B0h+var_170]
0x18002518d  mov     rax, [rax+40h]
0x180025191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025196  test    eax, eax
0x180025198  jns     short loc_1800251A2
0x18002519a  mov     ecx, eax; int
0x18002519c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800251a2  cmp     [rsp+1B0h+var_170], 1
0x1800251a7  jz      short loc_1800251B6
0x1800251a9  xor     edx, edx; struct IErrorInfo *
0x1800251ab  mov     ecx, 800705B9h; int
0x1800251b0  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800251b6  mov     [rsp+1B0h+var_178], 0
0x1800251bf  mov     rdi, [rsi]
0x1800251c2  mov     rax, [rdi]
0x1800251c5  mov     rbx, [rax+68h]
0x1800251c9  lea     rcx, [rsp+1B0h+var_178]
0x1800251ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800251d3  lea     rdx, [rsp+1B0h+var_178]
0x1800251d8  mov     rcx, rdi
0x1800251db  mov     rax, rbx
0x1800251de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251e3  test    eax, eax
0x1800251e5  jns     short loc_1800251EF
0x1800251e7  mov     ecx, eax; int
0x1800251e9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800251ef  mov     [rsp+1B0h+var_168], 0
0x1800251f8  mov     rdi, [rsp+1B0h+var_178]
0x1800251fd  mov     rax, [rdi]
0x180025200  mov     rbx, [rax+38h]
0x180025204  lea     rcx, [rsp+1B0h+var_168]; this
0x180025209  call    ?GetAddress@_bstr_t@@QEAAPEAPEAGXZ; _bstr_t::GetAddress(void)
0x18002520e  mov     rdx, rax
0x180025211  mov     rcx, rdi
0x180025214  mov     rax, rbx
0x180025217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002521c  test    eax, eax
0x18002521e  jns     short loc_180025228
0x180025220  mov     ecx, eax; int
0x180025222  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180025228  lea     rcx, [rsp+1B0h+var_168]; this
0x18002522d  call    ?GetBSTR@_bstr_t@@QEAAAEAPEAGXZ; _bstr_t::GetBSTR(void)
0x180025232  mov     rdx, [rax]; String2
0x180025235  lea     rcx, aDaily; "daily"
0x18002523c  call    wcscmp_0
0x180025241  mov     rbx, [rbp+0B0h+arg_20]
0x180025248  test    eax, eax
0x18002524a  jnz     loc_180025318
0x180025250  mov     rcx, [rsp+1B0h+var_178]
0x180025255  mov     [rsp+1B0h+var_180], rcx
0x18002525a  test    rcx, rcx
0x18002525d  jz      short loc_18002526C
0x18002525f  mov     rax, [rcx]
0x180025262  mov     rax, [rax+8]
0x180025266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002526b  nop
0x18002526c  mov     r8, rbx
0x18002526f  lea     rdx, [rsp+1B0h+var_14C]
0x180025274  lea     rcx, [rsp+1B0h+var_180]
0x180025279  call    ParseDay
0x18002527e  test    eax, eax
0x180025280  jns     short loc_18002528A
0x180025282  mov     ecx, eax; int
0x180025284  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002528a  cmp     [rsp+1B0h+var_14C], 0
0x18002528f  jz      loc_180025398
0x180025295  cmp     [rsp+1B0h+var_138], 0
0x18002529a  jz      loc_180025398
0x1800252a0  lea     rcx, [rsp+1B0h+var_168]; this
0x1800252a5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800252aa  nop
0x1800252ab  lea     rcx, [rsp+1B0h+var_178]
0x1800252b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800252b5  mov     rcx, cs:qword_18005FE88
0x1800252bc  mov     rax, [rcx]
0x1800252bf  mov     r9, r14
0x1800252c2  mov     r8, r15
0x1800252c5  lea     rdx, [rsp+1B0h+var_150]
0x1800252ca  mov     rax, [rax+8]
0x1800252ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252d3  mov     ebx, eax
0x1800252d5  test    eax, eax
0x1800252d7  jns     loc_180025373
0x1800252dd  lea     rax, WPP_GLOBAL_Control
0x1800252e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252eb  cmp     rcx, rax
0x1800252ee  jz      short loc_18002530E
0x1800252f0  test    byte ptr [rcx+1Ch], 1
0x1800252f4  jz      short loc_18002530E
0x1800252f6  mov     edx, 0Fh
0x1800252fb  mov     r9d, ebx
0x1800252fe  lea     r8, WPP_c7aca68ec72034e268068f62b41653e8_Traceguids
0x180025305  mov     rcx, [rcx+10h]
0x180025309  call    WPP_SF_d
0x18002530e  xor     edx, edx; struct IErrorInfo *
0x180025310  mov     ecx, ebx; int
0x180025312  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x180025318  lea     rcx, [rsp+1B0h+var_168]; this
0x18002531d  call    ?GetBSTR@_bstr_t@@QEAAAEAPEAGXZ; _bstr_t::GetBSTR(void)
0x180025322  mov     rdx, [rax]; String2
0x180025325  lea     rcx, aWeekly; "weekly"
0x18002532c  call    wcscmp_0
0x180025331  test    eax, eax
0x180025333  jnz     short loc_180025398
0x180025335  mov     rcx, [rsp+1B0h+var_178]
0x18002533a  mov     [rsp+1B0h+var_180], rcx
0x18002533f  test    rcx, rcx
0x180025342  jz      short loc_180025351
0x180025344  mov     rax, [rcx]
0x180025347  mov     rax, [rax+8]
0x18002534b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025350  nop
0x180025351  mov     r8, rbx
0x180025354  lea     rdx, [rsp+1B0h+var_150]
0x180025359  lea     rcx, [rsp+1B0h+var_180]
0x18002535e  call    ParseWeeklyRepeat
0x180025363  test    eax, eax
0x180025365  jns     loc_1800252A0
0x18002536b  mov     ecx, eax; int
0x18002536d  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180025373  lea     rcx, [rsp+1B0h+var_160]
0x180025378  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002537d  nop
0x18002537e  mov     rcx, rsi
0x180025381  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180025386  mov     eax, ebx
0x180025388  add     rsp, 188h
0x18002538f  pop     r15
0x180025391  pop     r14
0x180025393  pop     rdi
0x180025394  pop     rsi
0x180025395  pop     rbx
0x180025396  pop     rbp
0x180025397  retn
0x180025398  mov     rdx, rbx
0x18002539b  lea     rcx, [rsp+1B0h+var_168]
0x1800253a0  call    RaiseSchemaError
```
