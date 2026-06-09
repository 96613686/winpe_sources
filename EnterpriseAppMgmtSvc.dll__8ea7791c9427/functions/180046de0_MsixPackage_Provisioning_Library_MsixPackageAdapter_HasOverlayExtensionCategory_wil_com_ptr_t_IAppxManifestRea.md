# MsixPackage::Provisioning::Library::MsixPackageAdapter::HasOverlayExtensionCategory(wil::com_ptr_t<IAppxManifestReader,wil::err_exception_policy> const &,bool &)

- ea: `0x180046de0`
- end: `0x18004722b`
- name: `?HasOverlayExtensionCategory@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader@@Uerr_exception_policy@wil@@@wil@@AEA_N@Z`
- size: `1099`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047610`

## callees

- `0x180039e9c`
- `0x180046de0`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180046ed5`
- `OLEAUT32!__imp_SysAllocString` at `0x180046ed5`
- `OLEAUT32!__imp_SysFreeString` at `0x180046fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180047092`
- `OLEAUT32!__imp_SysFreeString` at `0x180047156`
- `OLEAUT32!__imp_SysFreeString` at `0x1800471b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180046fd2`
- `OLEAUT32!__imp_SysFreeString` at `0x180047092`
- `OLEAUT32!__imp_SysFreeString` at `0x180047156`
- `OLEAUT32!__imp_SysFreeString` at `0x1800471b6`

## string_xrefs

- `0x180046f03`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046fbd`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004707d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180047141`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046fae`: `Failed to get internal manifest reader`
- `0x180046e38`: `/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.localExperiencePack']`
- `0x18004706e`: `Failed to get Xml interface from internal reader`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::HasOverlayExtensionCategory(
        __int64 a1,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, _QWORD *),
        bool *a3)
{
  OLECHAR *v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  OLECHAR *v8; // rbx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, _QWORD *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, _QWORD *); // rsi
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rsi
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, OLECHAR *, __int64 *); // rsi
  __int64 v19; // rcx
  const char *v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR psz[192]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  *a3 = 0;
  v23[0] = 0;
  v22 = 0;
  v21 = 0;
  v5 = psz;
  v6 = L"/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extension"
        "s']/*[local-name()='Extension' and @Category='windows.localExperiencePack']";
  v7 = 2;
  do
  {
    *(_OWORD *)v5 = *(_OWORD *)v6;
    *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
    *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
    *((_OWORD *)v5 + 4) = *((_OWORD *)v6 + 4);
    *((_OWORD *)v5 + 5) = *((_OWORD *)v6 + 5);
    *((_OWORD *)v5 + 6) = *((_OWORD *)v6 + 6);
    *((_OWORD *)v5 + 7) = *((_OWORD *)v6 + 7);
    v5 += 64;
    v6 += 64;
    --v7;
  }
  while ( v7 );
  *(_OWORD *)v5 = *(_OWORD *)v6;
  *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
  *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
  *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
  *((_OWORD *)v5 + 4) = *((_OWORD *)v6 + 4);
  *((_OWORD *)v5 + 5) = *((_OWORD *)v6 + 5);
  *((_OWORD *)v5 + 6) = *((_OWORD *)v6 + 6);
  *(_OWORD *)(v5 + 53) = *(_OWORD *)(v6 + 53);
  v8 = SysAllocString(psz);
  v23[1] = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x94B,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)0x8007000ELL,
      (int)"Out of Memory",
      v20);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return 2147942414LL;
  }
  v10 = *a2;
  v11 = **v10;
  v12 = v23[0];
  v23[0] = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = v11(v10, &GUID_c0fc0853_18d7_43e8_afca_414a07af67a2, v23);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x94F,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v13,
      (int)"Failed to get internal manifest reader",
      v20);
    SysFreeString(v8);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return (unsigned int)v13;
  }
  v14 = v23[0];
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23[0] + 24LL);
  v16 = v22;
  v22 = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  v13 = v15(v14, &v22);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x953,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v13,
      (int)"Failed to get Xml interface from internal reader",
      v20);
    SysFreeString(v8);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return (unsigned int)v13;
  }
  v17 = v22;
  v18 = *(__int64 (__fastcall **)(__int64, OLECHAR *, __int64 *))(*(_QWORD *)v22 + 296LL);
  v19 = v21;
  v21 = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v13 = v18(v17, v8, &v21);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x957,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v13,
      (int)"Failed to locate query node",
      v20);
    SysFreeString(v8);
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
    return (unsigned int)v13;
  }
  *a3 = v21 != 0;
  SysFreeString(v8);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23[0] + 16LL))(v23[0]);
  return 0;
}

```

## disassembly

```asm
0x180046de0  mov     [rsp-8+arg_0], rbx
0x180046de5  mov     [rsp-8+arg_18], rsi
0x180046dea  push    rbp
0x180046deb  push    rdi
0x180046dec  push    r14
0x180046dee  lea     rbp, [rsp-0E0h]
0x180046df6  sub     rsp, 1E0h
0x180046dfd  mov     rax, cs:__security_cookie
0x180046e04  xor     rax, rsp
0x180046e07  mov     [rbp+0F0h+var_20], rax
0x180046e0e  mov     r14, r8
0x180046e11  mov     rdi, rdx
0x180046e14  mov     byte ptr [r8], 0
0x180046e18  mov     [rsp+1F0h+var_1B0], 0
0x180046e21  mov     [rsp+1F0h+var_1B8], 0
0x180046e2a  mov     [rsp+1F0h+var_1C0], 0
0x180046e33  lea     rax, [rsp+1F0h+psz]
0x180046e38  lea     rcx, aLocalNamePacka_0; "/*[local-name()='Package']/*[local-name"...
0x180046e3f  mov     edx, 2
0x180046e44  lea     r8d, [rdx+7Eh]
0x180046e48  movups  xmm0, xmmword ptr [rcx]
0x180046e4b  movups  xmmword ptr [rax], xmm0
0x180046e4e  movups  xmm1, xmmword ptr [rcx+10h]
0x180046e52  movups  xmmword ptr [rax+10h], xmm1
0x180046e56  movups  xmm0, xmmword ptr [rcx+20h]
0x180046e5a  movups  xmmword ptr [rax+20h], xmm0
0x180046e5e  movups  xmm1, xmmword ptr [rcx+30h]
0x180046e62  movups  xmmword ptr [rax+30h], xmm1
0x180046e66  movups  xmm0, xmmword ptr [rcx+40h]
0x180046e6a  movups  xmmword ptr [rax+40h], xmm0
0x180046e6e  movups  xmm1, xmmword ptr [rcx+50h]
0x180046e72  movups  xmmword ptr [rax+50h], xmm1
0x180046e76  movups  xmm0, xmmword ptr [rcx+60h]
0x180046e7a  movups  xmmword ptr [rax+60h], xmm0
0x180046e7e  movups  xmm1, xmmword ptr [rcx+70h]
0x180046e82  movups  xmmword ptr [rax+70h], xmm1
0x180046e86  add     rax, r8
0x180046e89  add     rcx, r8
0x180046e8c  sub     rdx, 1
0x180046e90  jnz     short loc_180046E48
0x180046e92  movups  xmm0, xmmword ptr [rcx]
0x180046e95  movups  xmmword ptr [rax], xmm0
0x180046e98  movups  xmm1, xmmword ptr [rcx+10h]
0x180046e9c  movups  xmmword ptr [rax+10h], xmm1
0x180046ea0  movups  xmm0, xmmword ptr [rcx+20h]
0x180046ea4  movups  xmmword ptr [rax+20h], xmm0
0x180046ea8  movups  xmm1, xmmword ptr [rcx+30h]
0x180046eac  movups  xmmword ptr [rax+30h], xmm1
0x180046eb0  movups  xmm0, xmmword ptr [rcx+40h]
0x180046eb4  movups  xmmword ptr [rax+40h], xmm0
0x180046eb8  movups  xmm1, xmmword ptr [rcx+50h]
0x180046ebc  movups  xmmword ptr [rax+50h], xmm1
0x180046ec0  movups  xmm0, xmmword ptr [rcx+60h]
0x180046ec4  movups  xmmword ptr [rax+60h], xmm0
0x180046ec8  movups  xmm1, xmmword ptr [rcx+6Ah]
0x180046ecc  movups  xmmword ptr [rax+6Ah], xmm1
0x180046ed0  lea     rcx, [rsp+1F0h+psz]; psz
0x180046ed5  call    cs:__imp_SysAllocString
0x180046edb  mov     rbx, rax
0x180046ede  mov     [rsp+1F0h+var_1A8], rax
0x180046ee3  test    rax, rax
0x180046ee6  jnz     short loc_180046F61
0x180046ee8  mov     rcx, [rbp+0F8h]; this
0x180046eef  lea     rax, aOutOfMemory; "Out of Memory"
0x180046ef6  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x180046efb  mov     ebx, 8007000Eh
0x180046f00  mov     r9d, ebx; char *
0x180046f03  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180046f0a  mov     edx, 94Bh; void *
0x180046f0f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046f14  nop
0x180046f15  mov     rcx, [rsp+1F0h+var_1C0]
0x180046f1a  test    rcx, rcx
0x180046f1d  jz      short loc_180046F2C
0x180046f1f  mov     rax, [rcx]
0x180046f22  mov     rax, [rax+10h]
0x180046f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f2b  nop
0x180046f2c  mov     rcx, [rsp+1F0h+var_1B8]
0x180046f31  test    rcx, rcx
0x180046f34  jz      short loc_180046F43
0x180046f36  mov     rax, [rcx]
0x180046f39  mov     rax, [rax+10h]
0x180046f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f42  nop
0x180046f43  mov     rcx, [rsp+1F0h+var_1B0]
0x180046f48  test    rcx, rcx
0x180046f4b  jz      short loc_180046F5A
0x180046f4d  mov     rdx, [rcx]
0x180046f50  mov     rax, [rdx+10h]
0x180046f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f59  nop
0x180046f5a  mov     eax, ebx
0x180046f5c  jmp     loc_180047204
0x180046f61  mov     rdi, [rdi]
0x180046f64  mov     rax, [rdi]
0x180046f67  mov     rsi, [rax]
0x180046f6a  mov     rcx, [rsp+1F0h+var_1B0]
0x180046f6f  mov     [rsp+1F0h+var_1B0], 0
0x180046f78  test    rcx, rcx
0x180046f7b  jz      short loc_180046F8A
0x180046f7d  mov     rdx, [rcx]
0x180046f80  mov     rax, [rdx+10h]
0x180046f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f89  nop
0x180046f8a  lea     r8, [rsp+1F0h+var_1B0]
0x180046f8f  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x180046f96  mov     rcx, rdi
0x180046f99  mov     rax, rsi
0x180046f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fa1  mov     edi, eax
0x180046fa3  test    eax, eax
0x180046fa5  jns     short loc_180047025
0x180046fa7  mov     rcx, [rbp+0F8h]; this
0x180046fae  lea     rax, aFailedToGetInt_1; "Failed to get internal manifest reader"
0x180046fb5  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x180046fba  mov     r9d, edi; char *
0x180046fbd  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180046fc4  mov     edx, 94Fh; void *
0x180046fc9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046fce  nop
0x180046fcf  mov     rcx, rbx; bstrString
0x180046fd2  call    cs:__imp_SysFreeString
0x180046fd8  nop
0x180046fd9  mov     rcx, [rsp+1F0h+var_1C0]
0x180046fde  test    rcx, rcx
0x180046fe1  jz      short loc_180046FF0
0x180046fe3  mov     rax, [rcx]
0x180046fe6  mov     rax, [rax+10h]
0x180046fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fef  nop
0x180046ff0  mov     rcx, [rsp+1F0h+var_1B8]
0x180046ff5  test    rcx, rcx
0x180046ff8  jz      short loc_180047007
0x180046ffa  mov     rax, [rcx]
0x180046ffd  mov     rax, [rax+10h]
0x180047001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047006  nop
0x180047007  mov     rcx, [rsp+1F0h+var_1B0]
0x18004700c  test    rcx, rcx
0x18004700f  jz      short loc_18004701E
0x180047011  mov     rax, [rcx]
0x180047014  mov     rax, [rax+10h]
0x180047018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004701d  nop
0x18004701e  mov     eax, edi
0x180047020  jmp     loc_180047204
0x180047025  mov     rdi, [rsp+1F0h+var_1B0]
0x18004702a  mov     rax, [rdi]
0x18004702d  mov     rsi, [rax+18h]
0x180047031  mov     rcx, [rsp+1F0h+var_1B8]
0x180047036  mov     [rsp+1F0h+var_1B8], 0
0x18004703f  test    rcx, rcx
0x180047042  jz      short loc_180047051
0x180047044  mov     rdx, [rcx]
0x180047047  mov     rax, [rdx+10h]
0x18004704b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047050  nop
0x180047051  lea     rdx, [rsp+1F0h+var_1B8]
0x180047056  mov     rcx, rdi
0x180047059  mov     rax, rsi
0x18004705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047061  mov     edi, eax
0x180047063  test    eax, eax
0x180047065  jns     short loc_1800470E3
0x180047067  mov     rcx, [rbp+0F8h]; this
0x18004706e  lea     rax, aFailedToGetXml; "Failed to get Xml interface from intern"...
0x180047075  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004707a  mov     r9d, edi; char *
0x18004707d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047084  mov     edx, 953h; void *
0x180047089  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004708e  nop
0x18004708f  mov     rcx, rbx; bstrString
0x180047092  call    cs:__imp_SysFreeString
0x180047098  nop
0x180047099  mov     rcx, [rsp+1F0h+var_1C0]
0x18004709e  test    rcx, rcx
0x1800470a1  jz      short loc_1800470B0
0x1800470a3  mov     rax, [rcx]
0x1800470a6  mov     rax, [rax+10h]
0x1800470aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470af  nop
0x1800470b0  mov     rcx, [rsp+1F0h+var_1B8]
0x1800470b5  test    rcx, rcx
0x1800470b8  jz      short loc_1800470C7
0x1800470ba  mov     rax, [rcx]
0x1800470bd  mov     rax, [rax+10h]
0x1800470c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470c6  nop
0x1800470c7  mov     rcx, [rsp+1F0h+var_1B0]
0x1800470cc  test    rcx, rcx
0x1800470cf  jz      short loc_1800470DE
0x1800470d1  mov     rax, [rcx]
0x1800470d4  mov     rax, [rax+10h]
0x1800470d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470dd  nop
0x1800470de  jmp     loc_18004701E
0x1800470e3  mov     rdi, [rsp+1F0h+var_1B8]
0x1800470e8  mov     rax, [rdi]
0x1800470eb  mov     rsi, [rax+128h]
0x1800470f2  mov     rcx, [rsp+1F0h+var_1C0]
0x1800470f7  mov     [rsp+1F0h+var_1C0], 0
0x180047100  test    rcx, rcx
0x180047103  jz      short loc_180047112
0x180047105  mov     rdx, [rcx]
0x180047108  mov     rax, [rdx+10h]
0x18004710c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047111  nop
0x180047112  lea     r8, [rsp+1F0h+var_1C0]
0x180047117  mov     rdx, rbx
0x18004711a  mov     rcx, rdi
0x18004711d  mov     rax, rsi
0x180047120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047125  mov     edi, eax
0x180047127  test    eax, eax
0x180047129  jns     short loc_1800471A7
0x18004712b  mov     rcx, [rbp+0F8h]; this
0x180047132  lea     rax, aFailedToLocate; "Failed to locate query node"
0x180047139  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004713e  mov     r9d, edi; char *
0x180047141  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180047148  mov     edx, 957h; void *
0x18004714d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180047152  nop
0x180047153  mov     rcx, rbx; bstrString
0x180047156  call    cs:__imp_SysFreeString
0x18004715c  nop
0x18004715d  mov     rcx, [rsp+1F0h+var_1C0]
0x180047162  test    rcx, rcx
0x180047165  jz      short loc_180047174
0x180047167  mov     rax, [rcx]
0x18004716a  mov     rax, [rax+10h]
0x18004716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047173  nop
0x180047174  mov     rcx, [rsp+1F0h+var_1B8]
0x180047179  test    rcx, rcx
0x18004717c  jz      short loc_18004718B
0x18004717e  mov     rax, [rcx]
0x180047181  mov     rax, [rax+10h]
0x180047185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004718a  nop
0x18004718b  mov     rcx, [rsp+1F0h+var_1B0]
0x180047190  test    rcx, rcx
0x180047193  jz      short loc_1800471A2
0x180047195  mov     rax, [rcx]
0x180047198  mov     rax, [rax+10h]
0x18004719c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471a1  nop
0x1800471a2  jmp     loc_18004701E
0x1800471a7  cmp     [rsp+1F0h+var_1C0], 0
0x1800471ad  setnz   al
0x1800471b0  mov     [r14], al
0x1800471b3  mov     rcx, rbx; bstrString
0x1800471b6  call    cs:__imp_SysFreeString
0x1800471bc  nop
0x1800471bd  mov     rcx, [rsp+1F0h+var_1C0]
0x1800471c2  test    rcx, rcx
0x1800471c5  jz      short loc_1800471D4
0x1800471c7  mov     rax, [rcx]
0x1800471ca  mov     rax, [rax+10h]
0x1800471ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471d3  nop
0x1800471d4  mov     rcx, [rsp+1F0h+var_1B8]
0x1800471d9  test    rcx, rcx
0x1800471dc  jz      short loc_1800471EB
0x1800471de  mov     rax, [rcx]
0x1800471e1  mov     rax, [rax+10h]
0x1800471e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471ea  nop
0x1800471eb  mov     rcx, [rsp+1F0h+var_1B0]
0x1800471f0  test    rcx, rcx
0x1800471f3  jz      short loc_180047202
0x1800471f5  mov     rax, [rcx]
0x1800471f8  mov     rax, [rax+10h]
0x1800471fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047201  nop
0x180047202  xor     eax, eax
0x180047204  mov     rcx, [rbp+0F0h+var_20]
0x18004720b  xor     rcx, rsp; StackCookie
0x18004720e  call    __security_check_cookie
0x180047213  lea     r11, [rsp+1F0h+var_10]
0x18004721b  mov     rbx, [r11+20h]
0x18004721f  mov     rsi, [r11+38h]
0x180047223  mov     rsp, r11
0x180047226  pop     r14
0x180047228  pop     rdi
0x180047229  pop     rbp
0x18004722a  retn
```
