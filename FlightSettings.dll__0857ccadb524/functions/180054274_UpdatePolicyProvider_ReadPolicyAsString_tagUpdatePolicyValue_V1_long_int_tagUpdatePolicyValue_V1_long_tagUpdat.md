# UpdatePolicyProvider::ReadPolicyAsString<tagUpdatePolicyValue_V1>(long (*)(int,tagUpdatePolicyValue_V1 * *),long (*)(tagUpdatePolicyValue_V1 * *),int,ushort,ushort * *)

- ea: `0x180054274`
- end: `0x1800545c0`
- name: `??$ReadPolicyAsString@UtagUpdatePolicyValue_V1@@@UpdatePolicyProvider@@AEAAJP6AJHPEAPEAUtagUpdatePolicyValue_V1@@@ZP6AJ0@ZHGPEAPEAG@Z`
- size: `844`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049c10`

## callees

- `0x18000cc8c`
- `0x1800175b4`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18002035c`
- `0x180054274`
- `0x1800c8010`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18005444d`
- `OLEAUT32!__imp_VariantChangeTypeEx` at `0x18005444d`

## string_xrefs

- `0x1800542cb`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x1800542fa`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x18005433c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x18005436c`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x1800543d9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054412`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054460`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054499`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x1800544d2`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x18005450b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054561`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054594`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x180054328`: `UpdatePolicy.dll returned policy #%d, but we asked it for #%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpdatePolicyProvider::ReadPolicyAsString<tagUpdatePolicyValue_V1>(
        __int64 a1,
        __int64 (__fastcall *a2)(_QWORD, __int64 *),
        __int64 (__fastcall *a3)(__int64 *),
        unsigned int a4,
        USHORT a5,
        __int64 **a6)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // edx
  int v16; // eax
  int v17; // eax
  HRESULT v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 *v22; // rcx
  int v23; // eax
  int v24; // eax
  int vt; // [rsp+20h] [rbp-40h]
  int vta; // [rsp+20h] [rbp-40h]
  int vtb; // [rsp+20h] [rbp-40h]
  int vtc; // [rsp+20h] [rbp-40h]
  int vtd; // [rsp+20h] [rbp-40h]
  int vte; // [rsp+20h] [rbp-40h]
  char *v31; // [rsp+28h] [rbp-38h]
  __int64 *v32; // [rsp+40h] [rbp-20h] BYREF
  __int64 (__fastcall **v33)(__int64 *); // [rsp+48h] [rbp-18h]
  __int64 v34; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  __int64 v36; // [rsp+88h] [rbp+28h] BYREF
  __int64 (__fastcall *v37)(__int64 *); // [rsp+90h] [rbp+30h] BYREF

  v37 = a3;
  v36 = 0;
  v32 = &v36;
  v33 = &v37;
  LOBYTE(v34) = 1;
  v8 = a2(a4, &v36);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
      (const char *)(unsigned int)v8,
      vt);
    if ( v36 )
    {
      v10 = v37(&v36);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v10,
          vta);
    }
    return v9;
  }
  v12 = v36;
  if ( *(_DWORD *)v36 != a4 )
  {
    LODWORD(v31) = *(_DWORD *)v36;
    v9 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
      (const char *)0x8000FFFFLL,
      (int)"UpdatePolicy.dll returned policy #%d, but we asked it for #%d",
      v31);
    if ( v36 )
    {
      v13 = v37(&v36);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v13,
          vtb);
    }
    return v9;
  }
  v14 = *(_DWORD *)(v36 + 4);
  if ( v14 && ((v15 = v14 - 1) == 0 || v15 == 2) )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    if ( *(_BYTE *)(a1 + 63) )
    {
      v16 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &v32,
              L"%lu",
              *(unsigned int *)(v36 + 8));
      v9 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v16,
          vt);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
        if ( v36 )
        {
          v17 = v37(&v36);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6A,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
              (const char *)(unsigned int)v17,
              vtc);
        }
        return v9;
      }
    }
    else
    {
      if ( *(_WORD *)(v36 + 16) != 8 )
      {
        v18 = VariantChangeTypeEx((VARIANTARG *)(v36 + 16), (const VARIANTARG *)(v36 + 16), 0x400u, a5, 8u);
        v9 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8D,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
            (const char *)(unsigned int)v18,
            vt);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
          if ( v36 )
          {
            v19 = v37(&v36);
            if ( v19 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x6A,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
                (const char *)(unsigned int)v19,
                vtd);
          }
          return v9;
        }
        v12 = v36;
      }
      v20 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &v32,
              *(_QWORD *)(v12 + 24),
              -1);
      v9 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v20,
          vt);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
        if ( v36 )
        {
          v21 = v37(&v36);
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x6A,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
              (const char *)(unsigned int)v21,
              vte);
        }
        return v9;
      }
    }
    v22 = v32;
    v32 = 0;
    v34 = 0;
    v33 = 0;
    *a6 = v22;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v32);
    if ( v36 )
    {
      v23 = v37(&v36);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v23,
          vt);
    }
    return 0;
  }
  else
  {
    if ( v36 )
    {
      v24 = v37(&v36);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
          (const char *)(unsigned int)v24,
          vt);
    }
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x180054274  mov     [rsp-18h+arg_0], rbx
0x180054279  mov     [rsp-18h+arg_18], rsi
0x18005427e  mov     [rsp-18h+arg_10], r8
0x180054283  push    rbp
0x180054284  push    rdi
0x180054285  push    r14
0x180054287  mov     rbp, rsp
0x18005428a  sub     rsp, 60h
0x18005428e  mov     edi, r9d
0x180054291  mov     rax, rdx
0x180054294  mov     rsi, rcx
0x180054297  xor     r14d, r14d
0x18005429a  mov     [rbp+arg_8], r14
0x18005429e  lea     rcx, [rbp+arg_8]
0x1800542a2  mov     [rbp+var_20], rcx
0x1800542a6  lea     rcx, [rbp+arg_10]
0x1800542aa  mov     [rbp+var_18], rcx
0x1800542ae  mov     byte ptr [rbp+var_10], 1
0x1800542b2  lea     rdx, [rbp+arg_8]
0x1800542b6  mov     ecx, r9d
0x1800542b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542be  mov     ebx, eax
0x1800542c0  test    eax, eax
0x1800542c2  jns     short loc_180054312
0x1800542c4  mov     rcx, [rbp+18h]; this
0x1800542c8  mov     r9d, eax; char *
0x1800542cb  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800542d2  lea     edx, [r14+6Fh]; void *
0x1800542d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800542db  nop
0x1800542dc  cmp     [rbp+arg_8], r14
0x1800542e0  jz      short loc_18005430B
0x1800542e2  lea     rcx, [rbp+arg_8]
0x1800542e6  mov     rax, [rbp+arg_10]
0x1800542ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542ef  mov     rcx, [rbp+18h]; this
0x1800542f3  test    eax, eax
0x1800542f5  jns     short loc_18005430B
0x1800542f7  mov     r9d, eax; char *
0x1800542fa  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054301  lea     edx, [r14+6Ah]; void *
0x180054305  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005430a  nop
0x18005430b  mov     eax, ebx
0x18005430d  jmp     loc_1800545AB
0x180054312  mov     rcx, [rbp+arg_8]
0x180054316  mov     eax, [rcx]
0x180054318  cmp     eax, edi
0x18005431a  jz      short loc_180054380
0x18005431c  mov     rcx, [rbp+18h]; this
0x180054320  mov     [rsp+60h+var_30], edi
0x180054324  mov     dword ptr [rsp+60h+var_38], eax; char *
0x180054328  lea     rax, aUpdatepolicyDl_0; "UpdatePolicy.dll returned policy #%d, b"...
0x18005432f  mov     qword ptr [rsp+60h+vt], rax; int
0x180054334  mov     ebx, 8000FFFFh
0x180054339  mov     r9d, ebx; char *
0x18005433c  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054343  mov     edx, 73h ; 's'; void *
0x180054348  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005434d  nop
0x18005434e  cmp     [rbp+arg_8], r14
0x180054352  jz      short loc_18005437E
0x180054354  lea     rcx, [rbp+arg_8]
0x180054358  mov     rax, [rbp+arg_10]
0x18005435c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054361  mov     rcx, [rbp+18h]; this
0x180054365  test    eax, eax
0x180054367  jns     short loc_18005437E
0x180054369  mov     r9d, eax; char *
0x18005436c  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054373  mov     edx, 6Ah ; 'j'; void *
0x180054378  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005437d  nop
0x18005437e  jmp     short loc_18005430B
0x180054380  mov     edx, [rcx+4]
0x180054383  test    edx, edx
0x180054385  jz      loc_180054577
0x18005438b  sub     edx, 1
0x18005438e  jz      short loc_1800543A2
0x180054390  sub     edx, 1
0x180054393  jz      loc_180054577
0x180054399  cmp     edx, 1
0x18005439c  jnz     loc_180054577
0x1800543a2  mov     [rbp+var_20], r14
0x1800543a6  mov     [rbp+var_18], r14
0x1800543aa  mov     [rbp+var_10], r14
0x1800543ae  cmp     [rsi+3Fh], r14b
0x1800543b2  jz      short loc_180054429
0x1800543b4  mov     r8d, [rcx+8]
0x1800543b8  lea     rdx, aLu; "%lu"
0x1800543bf  lea     rcx, [rbp+var_20]
0x1800543c3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800543c8  mov     ebx, eax
0x1800543ca  test    eax, eax
0x1800543cc  jns     loc_180054522
0x1800543d2  mov     rcx, [rbp+18h]; this
0x1800543d6  mov     r9d, eax; char *
0x1800543d9  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800543e0  mov     edx, 86h; void *
0x1800543e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800543ea  lea     rcx, [rbp+var_20]
0x1800543ee  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800543f3  nop
0x1800543f4  cmp     [rbp+arg_8], r14
0x1800543f8  jz      short loc_180054424
0x1800543fa  lea     rcx, [rbp+arg_8]
0x1800543fe  mov     rax, [rbp+arg_10]
0x180054402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054407  mov     rcx, [rbp+18h]; this
0x18005440b  test    eax, eax
0x18005440d  jns     short loc_180054424
0x18005440f  mov     r9d, eax; char *
0x180054412  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054419  mov     edx, 6Ah ; 'j'; void *
0x18005441e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054423  nop
0x180054424  jmp     loc_18005430B
0x180054429  lea     rax, [rcx+10h]
0x18005442d  mov     edx, 8
0x180054432  cmp     dx, [rax]
0x180054435  jz      short loc_1800544B4
0x180054437  mov     [rsp+60h+vt], dx; int
0x18005443c  movzx   r9d, [rbp+arg_20]; wFlags
0x180054441  mov     r8d, 400h; lcid
0x180054447  mov     rdx, rax; pvarSrc
0x18005444a  mov     rcx, rax; pvargDest
0x18005444d  call    cs:__imp_VariantChangeTypeEx
0x180054453  mov     ebx, eax
0x180054455  test    eax, eax
0x180054457  jns     short loc_1800544B0
0x180054459  mov     rcx, [rbp+18h]; this
0x18005445d  mov     r9d, eax; char *
0x180054460  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054467  mov     edx, 8Dh; void *
0x18005446c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054471  lea     rcx, [rbp+var_20]
0x180054475  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005447a  nop
0x18005447b  cmp     [rbp+arg_8], r14
0x18005447f  jz      short loc_1800544AB
0x180054481  lea     rcx, [rbp+arg_8]
0x180054485  mov     rax, [rbp+arg_10]
0x180054489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005448e  mov     rcx, [rbp+18h]; this
0x180054492  test    eax, eax
0x180054494  jns     short loc_1800544AB
0x180054496  mov     r9d, eax; char *
0x180054499  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800544a0  mov     edx, 6Ah ; 'j'; void *
0x1800544a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800544aa  nop
0x1800544ab  jmp     loc_18005430B
0x1800544b0  mov     rcx, [rbp+arg_8]
0x1800544b4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800544b8  mov     rdx, [rcx+18h]
0x1800544bc  lea     rcx, [rbp+var_20]
0x1800544c0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800544c5  mov     ebx, eax
0x1800544c7  test    eax, eax
0x1800544c9  jns     short loc_180054522
0x1800544cb  mov     rcx, [rbp+18h]; this
0x1800544cf  mov     r9d, eax; char *
0x1800544d2  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800544d9  mov     edx, 91h; void *
0x1800544de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800544e3  lea     rcx, [rbp+var_20]
0x1800544e7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800544ec  nop
0x1800544ed  cmp     [rbp+arg_8], r14
0x1800544f1  jz      short loc_18005451D
0x1800544f3  lea     rcx, [rbp+arg_8]
0x1800544f7  mov     rax, [rbp+arg_10]
0x1800544fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054500  mov     rcx, [rbp+18h]; this
0x180054504  test    eax, eax
0x180054506  jns     short loc_18005451D
0x180054508  mov     r9d, eax; char *
0x18005450b  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054512  mov     edx, 6Ah ; 'j'; void *
0x180054517  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005451c  nop
0x18005451d  jmp     loc_18005430B
0x180054522  mov     rcx, [rbp+var_20]
0x180054526  mov     [rbp+var_20], r14
0x18005452a  mov     [rbp+var_10], r14
0x18005452e  mov     [rbp+var_18], r14
0x180054532  mov     rax, [rbp+arg_28]
0x180054536  mov     [rax], rcx
0x180054539  lea     rcx, [rbp+var_20]
0x18005453d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180054542  nop
0x180054543  cmp     [rbp+arg_8], r14
0x180054547  jz      short loc_180054573
0x180054549  lea     rcx, [rbp+arg_8]
0x18005454d  mov     rax, [rbp+arg_10]
0x180054551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054556  mov     rcx, [rbp+18h]; this
0x18005455a  test    eax, eax
0x18005455c  jns     short loc_180054573
0x18005455e  mov     r9d, eax; char *
0x180054561  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x180054568  mov     edx, 6Ah ; 'j'; void *
0x18005456d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054572  nop
0x180054573  xor     eax, eax
0x180054575  jmp     short loc_1800545AB
0x180054577  test    rcx, rcx
0x18005457a  jz      short loc_1800545A6
0x18005457c  lea     rcx, [rbp+arg_8]
0x180054580  mov     rax, [rbp+arg_10]
0x180054584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054589  mov     rcx, [rbp+18h]; this
0x18005458d  test    eax, eax
0x18005458f  jns     short loc_1800545A6
0x180054591  mov     r9d, eax; char *
0x180054594  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x18005459b  mov     edx, 6Ah ; 'j'; void *
0x1800545a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800545a5  nop
0x1800545a6  mov     eax, 80070002h
0x1800545ab  lea     r11, [rsp+60h+var_s0]
0x1800545b0  mov     rbx, [r11+20h]
0x1800545b4  mov     rsi, [r11+38h]
0x1800545b8  mov     rsp, r11
0x1800545bb  pop     r14
0x1800545bd  pop     rdi
0x1800545be  pop     rbp
0x1800545bf  retn
```
