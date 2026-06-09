# ScheduledTask::CommitChanges(void)

- ea: `0x18000e1d0`
- end: `0x18000e3fb`
- name: `?CommitChanges@ScheduledTask@@QEAAXXZ`
- size: `555`
- prototype: `void __fastcall(ScheduledTask *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010d74`
- `0x180015fd4`
- `0x18001d4e0`

## callees

- `0x18000760c`
- `0x18000d63c`
- `0x18000e1d0`
- `0x180010150`
- `0x180010f50`
- `0x180012118`
- `0x180012f10`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000e2fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e2fa`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2d8`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2e3`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2d8`
- `OLEAUT32!__imp_VariantInit` at `0x18000e2e3`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3cf`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3da`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3cf`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3da`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000e243`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000e243`

## string_xrefs

- `0x18000e220`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000e250`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000e30d`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000e3ac`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000e273`: `No Change in TaskDefinition. Not updating`
- `0x18000e249`: `ScheduledTask::CommitChanges`
- `0x18000e2b5`: `Updating Task Definition for : %s`

## pseudocode

```c
void __fastcall ScheduledTask::CommitChanges(ScheduledTask *this)
{
  __int64 *v2; // rcx
  __int64 v3; // rax
  int v4; // eax
  const char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  int v8; // [rsp+20h] [rbp-69h]
  VARIANTARG v9; // [rsp+50h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-21h] BYREF
  VARIANTARG v11; // [rsp+80h] [rbp-9h]
  VARIANTARG v12; // [rsp+A0h] [rbp+17h]
  VARIANTARG v13; // [rsp+C0h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  BSTR bstrRight; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v16; // [rsp+F8h] [rbp+6Fh] BYREF

  if ( *(_BYTE *)this )
  {
    bstrRight = 0;
    v2 = (__int64 *)*((_QWORD *)this + 5);
    v3 = *v2;
    bstrRight = 0;
    v4 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v3 + 152))(v2, &bstrRight);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v4,
        v8);
    if ( VarBstrCmp(*((BSTR *)this + 2), bstrRight, 0x400u, 0) == 1 )
    {
      LogSimpleMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        0xBBu,
        "ScheduledTask::CommitChanges",
        -1,
        L"No Change in TaskDefinition. Not updating",
        0,
        0);
      *(_BYTE *)this = 0;
    }
    else
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        0xC0u,
        "ScheduledTask::CommitChanges",
        -1,
        L"Updating Task Definition for : %s",
        0,
        0,
        *((_QWORD *)this + 1));
      VariantInit(&pvarg);
      VariantInit(&v9);
      v9.vt = 8;
      v9.llVal = (LONGLONG)SysAllocString(L"D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;SU)");
      if ( !v9.llVal )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xC5,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
          v5);
      v16 = 0;
      v6 = *((_QWORD *)this + 3);
      v11 = v9;
      v12 = pvarg;
      v13 = pvarg;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v6 + 136LL))(
             v6,
             *((_QWORD *)this + 1),
             *((_QWORD *)this + 5),
             4);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
          (const char *)(unsigned int)v7,
          (int)&v13);
      *(_BYTE *)this = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      VariantClear(&v9);
      VariantClear(&pvarg);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrRight);
  }
}

```

## disassembly

```asm
0x18000e1d0  mov     [rsp-8+arg_10], rbx
0x18000e1d5  push    rbp
0x18000e1d6  lea     rbp, [rsp-57h]
0x18000e1db  sub     rsp, 0E0h
0x18000e1e2  mov     rbx, rcx
0x18000e1e5  cmp     byte ptr [rcx], 0
0x18000e1e8  jz      loc_18000E3EA
0x18000e1ee  mov     [rbp+57h+bstrRight], 0
0x18000e1f6  mov     rcx, [rcx+28h]
0x18000e1fa  mov     rax, [rcx]
0x18000e1fd  mov     [rbp+57h+bstrRight], 0
0x18000e205  lea     rdx, [rbp+57h+bstrRight]
0x18000e209  mov     rax, [rax+98h]
0x18000e210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e215  mov     rcx, [rbp+5Fh]; this
0x18000e219  test    eax, eax
0x18000e21b  jns     short loc_18000E232
0x18000e21d  mov     r9d, eax; char *
0x18000e220  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000e227  mov     edx, 0B8h; void *
0x18000e22c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e232  xor     r9d, r9d; dwFlags
0x18000e235  mov     r8d, 400h; lcid
0x18000e23b  mov     rdx, [rbp+57h+bstrRight]; bstrRight
0x18000e23f  mov     rcx, [rbx+10h]; bstrLeft
0x18000e243  call    cs:__imp_VarBstrCmp
0x18000e249  lea     r9, aScheduledtaskC; "ScheduledTask::CommitChanges"
0x18000e250  lea     rdx, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000e257  mov     ecx, 3; unsigned int
0x18000e25c  cmp     eax, 1
0x18000e25f  jnz     short loc_18000E29A
0x18000e261  mov     [rsp+0E0h+var_A8], 0; unsigned __int16 *
0x18000e26a  mov     [rsp+0E0h+var_B0], 0; char *
0x18000e273  lea     rax, aNoChangeInTask; "No Change in TaskDefinition. Not updati"...
0x18000e27a  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x18000e27f  mov     [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x18000e287  mov     r8d, 0BBh; unsigned int
0x18000e28d  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18000e292  mov     byte ptr [rbx], 0
0x18000e295  jmp     loc_18000E3E1
0x18000e29a  mov     rax, [rbx+8]
0x18000e29e  mov     [rsp+0E0h+var_A0], rax
0x18000e2a3  mov     [rsp+0E0h+var_A8], 0; unsigned __int16 *
0x18000e2ac  mov     [rsp+0E0h+var_B0], 0; char *
0x18000e2b5  lea     rax, aUpdatingTaskDe; "Updating Task Definition for : %s"
0x18000e2bc  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x18000e2c1  mov     [rsp+0E0h+var_C0], 0FFFFFFFFh; int
0x18000e2c9  mov     r8d, 0C0h; unsigned int
0x18000e2cf  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18000e2d4  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e2d8  call    cs:__imp_VariantInit
0x18000e2de  nop
0x18000e2df  lea     rcx, [rbp+57h+var_90]; pvarg
0x18000e2e3  call    cs:__imp_VariantInit
0x18000e2e9  nop
0x18000e2ea  mov     eax, 8
0x18000e2ef  mov     word ptr [rbp+57h+var_90], ax
0x18000e2f3  lea     rcx, psz; "D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;GRGX;;;S"...
0x18000e2fa  call    cs:__imp_SysAllocString
0x18000e300  mov     qword ptr [rbp+57h+var_90+8], rax
0x18000e304  mov     rcx, [rbp+5Fh]; this
0x18000e308  test    rax, rax
0x18000e30b  jnz     short loc_18000E31F
0x18000e30d  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000e314  mov     edx, 0C5h; void *
0x18000e319  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000e31f  mov     [rbp+57h+arg_8], 0
0x18000e327  mov     rcx, [rbx+18h]
0x18000e32b  movups  xmm3, xmmword ptr [rbp+57h+pvarg]
0x18000e32f  movsd   xmm2, qword ptr [rbp+57h+pvarg+10h]
0x18000e334  movups  xmm0, xmmword ptr [rbp+57h+var_90]
0x18000e338  movaps  [rbp+57h+var_60], xmm0
0x18000e33c  movsd   xmm1, qword ptr [rbp+57h+var_90+10h]
0x18000e341  movsd   [rbp+57h+var_50], xmm1
0x18000e346  movaps  [rbp+57h+var_40], xmm3
0x18000e34a  movsd   [rbp+57h+var_30], xmm2
0x18000e34f  movaps  xmmword ptr [rbp+57h+var_20], xmm3
0x18000e353  movsd   [rbp+57h+var_10], xmm2
0x18000e358  mov     rax, [rcx]
0x18000e35b  lea     rdx, [rbp+57h+arg_8]
0x18000e35f  mov     [rsp+0E0h+var_A0], rdx
0x18000e364  lea     rdx, [rbp+57h+var_60]
0x18000e368  mov     [rsp+0E0h+var_A8], rdx
0x18000e36d  mov     dword ptr [rsp+0E0h+var_B0], 5
0x18000e375  lea     rdx, [rbp+57h+var_40]
0x18000e379  mov     [rsp+0E0h+var_B8], rdx
0x18000e37e  lea     rdx, [rbp+57h+var_20]
0x18000e382  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x18000e387  mov     r9d, 4
0x18000e38d  mov     r8, [rbx+28h]
0x18000e391  mov     rdx, [rbx+8]
0x18000e395  mov     rax, [rax+88h]
0x18000e39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a1  mov     rcx, [rbp+5Fh]; this
0x18000e3a5  test    eax, eax
0x18000e3a7  jns     short loc_18000E3BE
0x18000e3a9  mov     r9d, eax; char *
0x18000e3ac  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000e3b3  mov     edx, 0C8h; void *
0x18000e3b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e3be  mov     byte ptr [rbx], 0
0x18000e3c1  lea     rcx, [rbp+57h+arg_8]
0x18000e3c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e3ca  nop
0x18000e3cb  lea     rcx, [rbp+57h+var_90]; pvarg
0x18000e3cf  call    cs:__imp_VariantClear
0x18000e3d5  nop
0x18000e3d6  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18000e3da  call    cs:__imp_VariantClear
0x18000e3e0  nop
0x18000e3e1  lea     rcx, [rbp+57h+bstrRight]
0x18000e3e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e3ea  mov     rbx, [rsp+0E0h+arg_10]
0x18000e3f2  add     rsp, 0E0h
0x18000e3f9  pop     rbp
0x18000e3fa  retn
```
