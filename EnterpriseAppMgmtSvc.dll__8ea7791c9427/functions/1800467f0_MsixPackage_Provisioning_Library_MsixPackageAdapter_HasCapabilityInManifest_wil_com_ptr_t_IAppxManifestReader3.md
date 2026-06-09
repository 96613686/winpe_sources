# MsixPackage::Provisioning::Library::MsixPackageAdapter::HasCapabilityInManifest(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,APPX_CAPABILITY_CLASS_TYPE,ushort const *,bool &)

- ea: `0x1800467f0`
- end: `0x180046a37`
- name: `?HasCapabilityInManifest@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@W4APPX_CAPABILITY_CLASS_TYPE@@PEBGAEA_N@Z`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180046a40`
- `0x180046ba4`
- `0x180046ce0`

## callees

- `0x180039e9c`
- `0x1800467f0`
- `0x18006a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004691a`
- `msvcrt!_wcsicmp` at `0x18004691a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004694b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800469aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800469dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004694b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800469aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800469dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046a15`

## string_xrefs

- `0x180046854`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800468bb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004698f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800469fa`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180046980`: `Failed to move the next capability in enumerator.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::HasCapabilityInManifest(
        __int64 a1,
        __int64 **a2,
        int a3,
        const wchar_t *a4,
        wchar_t *String1)
{
  wchar_t *v6; // rdi
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v11; // rax
  const char *v12; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 *v14; // [rsp+50h] [rbp+20h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF

  v15 = a3;
  v6 = String1;
  *(_BYTE *)String1 = 0;
  v14 = 0;
  v7 = *a2;
  v8 = **a2;
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v8 + 104))(v7, 4, &v14);
  if ( v9 >= 0 )
  {
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 32))(v14, &v15);
    if ( v9 >= 0 )
    {
      while ( 1 )
      {
        if ( !v15 )
          goto LABEL_15;
        String1 = 0;
        v11 = *v14;
        String1 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v11 + 24))(v14, &String1);
        if ( v9 < 0 )
          break;
        if ( !_wcsicmp(String1, a4) )
        {
          *(_BYTE *)v6 = 1;
          if ( String1 )
            CoTaskMemFree(String1);
LABEL_15:
          if ( v14 )
            (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
          return 0;
        }
        v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 40))(v14, &v15);
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x55D,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v9,
            (int)"Failed to move the next capability in enumerator.",
            v12);
          if ( String1 )
            CoTaskMemFree(String1);
          if ( v14 )
            (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
          return (unsigned int)v9;
        }
        if ( String1 )
          CoTaskMemFree(String1);
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x555,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed to get current capability from enumerator.",
        v12);
      if ( String1 )
        CoTaskMemFree(String1);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed in GetHasCurrent for capability enumerator.",
        v12);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x54D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v9,
      (int)"Failed to get Windows capabilities list for package.",
      v12);
    if ( v14 )
      (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800467f0  mov     [rsp-18h+arg_8], rbx
0x1800467f5  mov     [rsp-18h+arg_10], r8d
0x1800467fa  mov     [rsp-18h+arg_0], rcx
0x1800467ff  push    rbp
0x180046800  push    rsi
0x180046801  push    rdi
0x180046802  mov     rbp, rsp
0x180046805  sub     rsp, 30h
0x180046809  mov     rsi, r9
0x18004680c  mov     rdi, [rbp+String1]
0x180046810  mov     byte ptr [rdi], 0
0x180046813  mov     [rbp+arg_0], 0
0x18004681b  mov     rcx, [rdx]
0x18004681e  mov     rax, [rcx]
0x180046821  mov     [rbp+arg_0], 0
0x180046829  lea     r8, [rbp+arg_0]
0x18004682d  mov     edx, 4
0x180046832  mov     rax, [rax+68h]
0x180046836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004683b  mov     ebx, eax
0x18004683d  test    eax, eax
0x18004683f  jns     short loc_180046883
0x180046841  mov     rcx, [rbp+18h]; this
0x180046845  lea     rax, aFailedToGetWin; "Failed to get Windows capabilities list"...
0x18004684c  mov     qword ptr [rsp+30h+var_10], rax; int
0x180046851  mov     r9d, ebx; char *
0x180046854  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004685b  mov     edx, 54Dh; void *
0x180046860  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046865  nop
0x180046866  mov     rcx, [rbp+arg_0]
0x18004686a  test    rcx, rcx
0x18004686d  jz      short loc_18004687C
0x18004686f  mov     rax, [rcx]
0x180046872  mov     rax, [rax+10h]
0x180046876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004687b  nop
0x18004687c  mov     eax, ebx
0x18004687e  jmp     loc_18004696F
0x180046883  mov     [rbp+arg_10], 0
0x18004688a  mov     rcx, [rbp+arg_0]
0x18004688e  mov     rax, [rcx]
0x180046891  lea     rdx, [rbp+arg_10]
0x180046895  mov     rax, [rax+20h]
0x180046899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004689e  mov     ebx, eax
0x1800468a0  test    eax, eax
0x1800468a2  jns     loc_180046951
0x1800468a8  mov     rcx, [rbp+18h]; this
0x1800468ac  lea     rax, aFailedInGethas; "Failed in GetHasCurrent for capability "...
0x1800468b3  mov     qword ptr [rsp+30h+var_10], rax; int
0x1800468b8  mov     r9d, ebx; char *
0x1800468bb  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800468c2  mov     edx, 550h; void *
0x1800468c7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800468cc  nop
0x1800468cd  mov     rcx, [rbp+arg_0]
0x1800468d1  test    rcx, rcx
0x1800468d4  jz      short loc_1800468E3
0x1800468d6  mov     rax, [rcx]
0x1800468d9  mov     rax, [rax+10h]
0x1800468dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468e2  nop
0x1800468e3  jmp     short loc_18004687C
0x1800468e5  mov     [rbp+String1], 0
0x1800468ed  mov     rcx, [rbp+arg_0]
0x1800468f1  mov     rax, [rcx]
0x1800468f4  mov     [rbp+String1], 0
0x1800468fc  lea     rdx, [rbp+String1]
0x180046900  mov     rax, [rax+18h]
0x180046904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046909  mov     ebx, eax
0x18004690b  test    eax, eax
0x18004690d  js      loc_1800469E7
0x180046913  mov     rdx, rsi; String2
0x180046916  mov     rcx, [rbp+String1]; String1
0x18004691a  call    cs:__imp__wcsicmp
0x180046920  test    eax, eax
0x180046922  jz      loc_1800469CC
0x180046928  mov     rcx, [rbp+arg_0]
0x18004692c  mov     rax, [rcx]
0x18004692f  lea     rdx, [rbp+arg_10]
0x180046933  mov     rax, [rax+28h]
0x180046937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004693c  mov     ebx, eax
0x18004693e  test    eax, eax
0x180046940  js      short loc_18004697C
0x180046942  mov     rcx, [rbp+String1]; pv
0x180046946  test    rcx, rcx
0x180046949  jz      short loc_180046951
0x18004694b  call    cs:__imp_CoTaskMemFree
0x180046951  cmp     [rbp+arg_10], 0
0x180046955  jnz     short loc_1800468E5
0x180046957  mov     rcx, [rbp+arg_0]
0x18004695b  test    rcx, rcx
0x18004695e  jz      short loc_18004696D
0x180046960  mov     rax, [rcx]
0x180046963  mov     rax, [rax+10h]
0x180046967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004696c  nop
0x18004696d  xor     eax, eax
0x18004696f  mov     rbx, [rsp+30h+arg_8]
0x180046974  add     rsp, 30h
0x180046978  pop     rdi
0x180046979  pop     rsi
0x18004697a  pop     rbp
0x18004697b  retn
0x18004697c  mov     rcx, [rbp+18h]; this
0x180046980  lea     rax, aFailedToMoveTh; "Failed to move the next capability in e"...
0x180046987  mov     qword ptr [rsp+30h+var_10], rax; int
0x18004698c  mov     r9d, ebx; char *
0x18004698f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180046996  mov     edx, 55Dh; void *
0x18004699b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800469a0  nop
0x1800469a1  mov     rcx, [rbp+String1]; pv
0x1800469a5  test    rcx, rcx
0x1800469a8  jz      short loc_1800469B1
0x1800469aa  call    cs:__imp_CoTaskMemFree
0x1800469b0  nop
0x1800469b1  mov     rcx, [rbp+arg_0]
0x1800469b5  test    rcx, rcx
0x1800469b8  jz      short loc_1800469C7
0x1800469ba  mov     rax, [rcx]
0x1800469bd  mov     rax, [rax+10h]
0x1800469c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800469c6  nop
0x1800469c7  jmp     loc_18004687C
0x1800469cc  mov     byte ptr [rdi], 1
0x1800469cf  mov     rcx, [rbp+String1]; pv
0x1800469d3  test    rcx, rcx
0x1800469d6  jz      loc_180046957
0x1800469dc  call    cs:__imp_CoTaskMemFree
0x1800469e2  jmp     loc_180046957
0x1800469e7  mov     rcx, [rbp+18h]; this
0x1800469eb  lea     rax, aFailedToGetCur; "Failed to get current capability from e"...
0x1800469f2  mov     qword ptr [rsp+30h+var_10], rax; int
0x1800469f7  mov     r9d, ebx; char *
0x1800469fa  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180046a01  mov     edx, 555h; void *
0x180046a06  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180046a0b  nop
0x180046a0c  mov     rcx, [rbp+String1]; pv
0x180046a10  test    rcx, rcx
0x180046a13  jz      short loc_180046A1C
0x180046a15  call    cs:__imp_CoTaskMemFree
0x180046a1b  nop
0x180046a1c  mov     rcx, [rbp+arg_0]
0x180046a20  test    rcx, rcx
0x180046a23  jz      short loc_180046A32
0x180046a25  mov     rax, [rcx]
0x180046a28  mov     rax, [rax+10h]
0x180046a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a31  nop
0x180046a32  jmp     loc_18004687C
```
