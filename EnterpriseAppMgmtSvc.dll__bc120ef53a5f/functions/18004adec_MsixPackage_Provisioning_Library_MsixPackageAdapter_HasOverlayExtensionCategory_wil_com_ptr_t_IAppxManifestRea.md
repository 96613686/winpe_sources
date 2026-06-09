# MsixPackage::Provisioning::Library::MsixPackageAdapter::HasOverlayExtensionCategory(wil::com_ptr_t<IAppxManifestReader,wil::err_exception_policy> const &,bool &)

- ea: `0x18004adec`
- end: `0x18004b262`
- name: `?HasOverlayExtensionCategory@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader@@Uerr_exception_policy@wil@@@wil@@AEA_N@Z`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004b664`

## callees

- `0x18003d4ec`
- `0x18004adec`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004aee1`
- `OLEAUT32!__imp_SysAllocString` at `0x18004aee1`
- `OLEAUT32!__imp_SysFreeString` at `0x18004afe8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b0b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b180`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b1e6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004afe8`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b0b2`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b180`
- `OLEAUT32!__imp_SysFreeString` at `0x18004b1e6`

## string_xrefs

- `0x18004af15`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004afd3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b09d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b16b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004afc4`: `Failed to get internal manifest reader`
- `0x18004b08e`: `Failed to get Xml interface from internal reader`
- `0x18004ae44`: `/*[local-name()='Package']/*[local-name()='Applications']/*[local-name()='Application']/*[local-name()='Extensions']/*[local-name()='Extension' and @Category='windows.localExperiencePack']`

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
0x18004adec  mov     [rsp-8+arg_0], rbx
0x18004adf1  mov     [rsp-8+arg_18], rsi
0x18004adf6  push    rbp
0x18004adf7  push    rdi
0x18004adf8  push    r14
0x18004adfa  lea     rbp, [rsp-0E0h]
0x18004ae02  sub     rsp, 1E0h
0x18004ae09  mov     rax, cs:__security_cookie
0x18004ae10  xor     rax, rsp
0x18004ae13  mov     [rbp+0F0h+var_20], rax
0x18004ae1a  mov     r14, r8
0x18004ae1d  mov     rdi, rdx
0x18004ae20  mov     byte ptr [r8], 0
0x18004ae24  mov     [rsp+1F0h+var_1B0], 0
0x18004ae2d  mov     [rsp+1F0h+var_1B8], 0
0x18004ae36  mov     [rsp+1F0h+var_1C0], 0
0x18004ae3f  lea     rax, [rsp+1F0h+psz]
0x18004ae44  lea     rcx, aLocalNamePacka_0; "/*[local-name()='Package']/*[local-name"...
0x18004ae4b  mov     edx, 2
0x18004ae50  lea     r8d, [rdx+7Eh]
0x18004ae54  movups  xmm0, xmmword ptr [rcx]
0x18004ae57  movups  xmmword ptr [rax], xmm0
0x18004ae5a  movups  xmm1, xmmword ptr [rcx+10h]
0x18004ae5e  movups  xmmword ptr [rax+10h], xmm1
0x18004ae62  movups  xmm0, xmmword ptr [rcx+20h]
0x18004ae66  movups  xmmword ptr [rax+20h], xmm0
0x18004ae6a  movups  xmm1, xmmword ptr [rcx+30h]
0x18004ae6e  movups  xmmword ptr [rax+30h], xmm1
0x18004ae72  movups  xmm0, xmmword ptr [rcx+40h]
0x18004ae76  movups  xmmword ptr [rax+40h], xmm0
0x18004ae7a  movups  xmm1, xmmword ptr [rcx+50h]
0x18004ae7e  movups  xmmword ptr [rax+50h], xmm1
0x18004ae82  movups  xmm0, xmmword ptr [rcx+60h]
0x18004ae86  movups  xmmword ptr [rax+60h], xmm0
0x18004ae8a  movups  xmm1, xmmword ptr [rcx+70h]
0x18004ae8e  movups  xmmword ptr [rax+70h], xmm1
0x18004ae92  add     rax, r8
0x18004ae95  add     rcx, r8
0x18004ae98  sub     rdx, 1
0x18004ae9c  jnz     short loc_18004AE54
0x18004ae9e  movups  xmm0, xmmword ptr [rcx]
0x18004aea1  movups  xmmword ptr [rax], xmm0
0x18004aea4  movups  xmm1, xmmword ptr [rcx+10h]
0x18004aea8  movups  xmmword ptr [rax+10h], xmm1
0x18004aeac  movups  xmm0, xmmword ptr [rcx+20h]
0x18004aeb0  movups  xmmword ptr [rax+20h], xmm0
0x18004aeb4  movups  xmm1, xmmword ptr [rcx+30h]
0x18004aeb8  movups  xmmword ptr [rax+30h], xmm1
0x18004aebc  movups  xmm0, xmmword ptr [rcx+40h]
0x18004aec0  movups  xmmword ptr [rax+40h], xmm0
0x18004aec4  movups  xmm1, xmmword ptr [rcx+50h]
0x18004aec8  movups  xmmword ptr [rax+50h], xmm1
0x18004aecc  movups  xmm0, xmmword ptr [rcx+60h]
0x18004aed0  movups  xmmword ptr [rax+60h], xmm0
0x18004aed4  movups  xmm1, xmmword ptr [rcx+6Ah]
0x18004aed8  movups  xmmword ptr [rax+6Ah], xmm1
0x18004aedc  lea     rcx, [rsp+1F0h+psz]; psz
0x18004aee1  call    cs:__imp_SysAllocString
0x18004aee8  nop     dword ptr [rax+rax+00h]
0x18004aeed  mov     rbx, rax
0x18004aef0  mov     [rsp+1F0h+var_1A8], rax
0x18004aef5  test    rax, rax
0x18004aef8  jnz     short loc_18004AF73
0x18004aefa  mov     rcx, [rbp+0F8h]; this
0x18004af01  lea     rax, aOutOfMemory; "Out of Memory"
0x18004af08  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004af0d  mov     ebx, 8007000Eh
0x18004af12  mov     r9d, ebx; char *
0x18004af15  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004af1c  mov     edx, 94Bh; void *
0x18004af21  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004af26  nop
0x18004af27  mov     rcx, [rsp+1F0h+var_1C0]
0x18004af2c  test    rcx, rcx
0x18004af2f  jz      short loc_18004AF3E
0x18004af31  mov     rax, [rcx]
0x18004af34  mov     rax, [rax+10h]
0x18004af38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af3d  nop
0x18004af3e  mov     rcx, [rsp+1F0h+var_1B8]
0x18004af43  test    rcx, rcx
0x18004af46  jz      short loc_18004AF55
0x18004af48  mov     rax, [rcx]
0x18004af4b  mov     rax, [rax+10h]
0x18004af4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af54  nop
0x18004af55  mov     rcx, [rsp+1F0h+var_1B0]
0x18004af5a  test    rcx, rcx
0x18004af5d  jz      short loc_18004AF6C
0x18004af5f  mov     rdx, [rcx]
0x18004af62  mov     rax, [rdx+10h]
0x18004af66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af6b  nop
0x18004af6c  mov     eax, ebx
0x18004af6e  jmp     loc_18004B23A
0x18004af73  mov     rdi, [rdi]
0x18004af76  mov     rax, [rdi]
0x18004af79  mov     rsi, [rax]
0x18004af7c  mov     rcx, [rsp+1F0h+var_1B0]
0x18004af81  mov     [rsp+1F0h+var_1B0], 0
0x18004af8a  test    rcx, rcx
0x18004af8d  jz      short loc_18004AF9C
0x18004af8f  mov     rdx, [rcx]
0x18004af92  mov     rax, [rdx+10h]
0x18004af96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af9b  nop
0x18004af9c  lea     r8, [rsp+1F0h+var_1B0]
0x18004afa1  lea     rdx, _GUID_c0fc0853_18d7_43e8_afca_414a07af67a2
0x18004afa8  mov     rcx, rdi
0x18004afab  mov     rax, rsi
0x18004afae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afb3  mov     edi, eax
0x18004afb5  test    eax, eax
0x18004afb7  jns     loc_18004B041
0x18004afbd  mov     rcx, [rbp+0F8h]; this
0x18004afc4  lea     rax, aFailedToGetInt_1; "Failed to get internal manifest reader"
0x18004afcb  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004afd0  mov     r9d, edi; char *
0x18004afd3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004afda  mov     edx, 94Fh; void *
0x18004afdf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004afe4  nop
0x18004afe5  mov     rcx, rbx; bstrString
0x18004afe8  call    cs:__imp_SysFreeString
0x18004afef  nop     dword ptr [rax+rax+00h]
0x18004aff4  nop
0x18004aff5  mov     rcx, [rsp+1F0h+var_1C0]
0x18004affa  test    rcx, rcx
0x18004affd  jz      short loc_18004B00C
0x18004afff  mov     rax, [rcx]
0x18004b002  mov     rax, [rax+10h]
0x18004b006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b00b  nop
0x18004b00c  mov     rcx, [rsp+1F0h+var_1B8]
0x18004b011  test    rcx, rcx
0x18004b014  jz      short loc_18004B023
0x18004b016  mov     rax, [rcx]
0x18004b019  mov     rax, [rax+10h]
0x18004b01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b022  nop
0x18004b023  mov     rcx, [rsp+1F0h+var_1B0]
0x18004b028  test    rcx, rcx
0x18004b02b  jz      short loc_18004B03A
0x18004b02d  mov     rax, [rcx]
0x18004b030  mov     rax, [rax+10h]
0x18004b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b039  nop
0x18004b03a  mov     eax, edi
0x18004b03c  jmp     loc_18004B23A
0x18004b041  mov     rdi, [rsp+1F0h+var_1B0]
0x18004b046  mov     rax, [rdi]
0x18004b049  mov     rsi, [rax+18h]
0x18004b04d  mov     rcx, [rsp+1F0h+var_1B8]
0x18004b052  mov     [rsp+1F0h+var_1B8], 0
0x18004b05b  test    rcx, rcx
0x18004b05e  jz      short loc_18004B06D
0x18004b060  mov     rdx, [rcx]
0x18004b063  mov     rax, [rdx+10h]
0x18004b067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b06c  nop
0x18004b06d  lea     rdx, [rsp+1F0h+var_1B8]
0x18004b072  mov     rcx, rdi
0x18004b075  mov     rax, rsi
0x18004b078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b07d  mov     edi, eax
0x18004b07f  test    eax, eax
0x18004b081  jns     loc_18004B109
0x18004b087  mov     rcx, [rbp+0F8h]; this
0x18004b08e  lea     rax, aFailedToGetXml; "Failed to get Xml interface from intern"...
0x18004b095  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004b09a  mov     r9d, edi; char *
0x18004b09d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b0a4  mov     edx, 953h; void *
0x18004b0a9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b0ae  nop
0x18004b0af  mov     rcx, rbx; bstrString
0x18004b0b2  call    cs:__imp_SysFreeString
0x18004b0b9  nop     dword ptr [rax+rax+00h]
0x18004b0be  nop
0x18004b0bf  mov     rcx, [rsp+1F0h+var_1C0]
0x18004b0c4  test    rcx, rcx
0x18004b0c7  jz      short loc_18004B0D6
0x18004b0c9  mov     rax, [rcx]
0x18004b0cc  mov     rax, [rax+10h]
0x18004b0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0d5  nop
0x18004b0d6  mov     rcx, [rsp+1F0h+var_1B8]
0x18004b0db  test    rcx, rcx
0x18004b0de  jz      short loc_18004B0ED
0x18004b0e0  mov     rax, [rcx]
0x18004b0e3  mov     rax, [rax+10h]
0x18004b0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0ec  nop
0x18004b0ed  mov     rcx, [rsp+1F0h+var_1B0]
0x18004b0f2  test    rcx, rcx
0x18004b0f5  jz      short loc_18004B104
0x18004b0f7  mov     rax, [rcx]
0x18004b0fa  mov     rax, [rax+10h]
0x18004b0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b103  nop
0x18004b104  jmp     loc_18004B03A
0x18004b109  mov     rdi, [rsp+1F0h+var_1B8]
0x18004b10e  mov     rax, [rdi]
0x18004b111  mov     rsi, [rax+128h]
0x18004b118  mov     rcx, [rsp+1F0h+var_1C0]
0x18004b11d  mov     [rsp+1F0h+var_1C0], 0
0x18004b126  test    rcx, rcx
0x18004b129  jz      short loc_18004B138
0x18004b12b  mov     rdx, [rcx]
0x18004b12e  mov     rax, [rdx+10h]
0x18004b132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b137  nop
0x18004b138  lea     r8, [rsp+1F0h+var_1C0]
0x18004b13d  mov     rdx, rbx
0x18004b140  mov     rcx, rdi
0x18004b143  mov     rax, rsi
0x18004b146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b14b  mov     edi, eax
0x18004b14d  test    eax, eax
0x18004b14f  jns     loc_18004B1D7
0x18004b155  mov     rcx, [rbp+0F8h]; this
0x18004b15c  lea     rax, aFailedToLocate; "Failed to locate query node"
0x18004b163  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x18004b168  mov     r9d, edi; char *
0x18004b16b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b172  mov     edx, 957h; void *
0x18004b177  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b17c  nop
0x18004b17d  mov     rcx, rbx; bstrString
0x18004b180  call    cs:__imp_SysFreeString
0x18004b187  nop     dword ptr [rax+rax+00h]
0x18004b18c  nop
0x18004b18d  mov     rcx, [rsp+1F0h+var_1C0]
0x18004b192  test    rcx, rcx
0x18004b195  jz      short loc_18004B1A4
0x18004b197  mov     rax, [rcx]
0x18004b19a  mov     rax, [rax+10h]
0x18004b19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1a3  nop
0x18004b1a4  mov     rcx, [rsp+1F0h+var_1B8]
0x18004b1a9  test    rcx, rcx
0x18004b1ac  jz      short loc_18004B1BB
0x18004b1ae  mov     rax, [rcx]
0x18004b1b1  mov     rax, [rax+10h]
0x18004b1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1ba  nop
0x18004b1bb  mov     rcx, [rsp+1F0h+var_1B0]
0x18004b1c0  test    rcx, rcx
0x18004b1c3  jz      short loc_18004B1D2
0x18004b1c5  mov     rax, [rcx]
0x18004b1c8  mov     rax, [rax+10h]
0x18004b1cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1d1  nop
0x18004b1d2  jmp     loc_18004B03A
0x18004b1d7  cmp     [rsp+1F0h+var_1C0], 0
0x18004b1dd  setnz   al
0x18004b1e0  mov     [r14], al
0x18004b1e3  mov     rcx, rbx; bstrString
0x18004b1e6  call    cs:__imp_SysFreeString
0x18004b1ed  nop     dword ptr [rax+rax+00h]
0x18004b1f2  nop
0x18004b1f3  mov     rcx, [rsp+1F0h+var_1C0]
0x18004b1f8  test    rcx, rcx
0x18004b1fb  jz      short loc_18004B20A
0x18004b1fd  mov     rax, [rcx]
0x18004b200  mov     rax, [rax+10h]
0x18004b204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b209  nop
0x18004b20a  mov     rcx, [rsp+1F0h+var_1B8]
0x18004b20f  test    rcx, rcx
0x18004b212  jz      short loc_18004B221
0x18004b214  mov     rax, [rcx]
0x18004b217  mov     rax, [rax+10h]
0x18004b21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b220  nop
0x18004b221  mov     rcx, [rsp+1F0h+var_1B0]
0x18004b226  test    rcx, rcx
0x18004b229  jz      short loc_18004B238
0x18004b22b  mov     rax, [rcx]
0x18004b22e  mov     rax, [rax+10h]
0x18004b232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b237  nop
0x18004b238  xor     eax, eax
0x18004b23a  mov     rcx, [rbp+0F0h+var_20]
0x18004b241  xor     rcx, rsp; StackCookie
0x18004b244  call    __security_check_cookie
0x18004b249  lea     r11, [rsp+1F0h+var_10]
0x18004b251  mov     rbx, [r11+20h]
0x18004b255  mov     rsi, [r11+38h]
0x18004b259  mov     rsp, r11
0x18004b25c  pop     r14
0x18004b25e  pop     rdi
0x18004b25f  pop     rbp
0x18004b260  retn
```
