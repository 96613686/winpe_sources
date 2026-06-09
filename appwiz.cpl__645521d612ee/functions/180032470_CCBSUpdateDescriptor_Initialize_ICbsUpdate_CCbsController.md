# CCBSUpdateDescriptor::Initialize(ICbsUpdate *,CCbsController *)

- ea: `0x180032470`
- end: `0x18003269c`
- name: `?Initialize@CCBSUpdateDescriptor@@QEAAJPEAUICbsUpdate@@PEAVCCbsController@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CCBSUpdateDescriptor *__hidden this, struct ICbsUpdate *, struct CCbsController *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003e738`

## callees

- `0x1800108d4`
- `0x180031804`
- `0x180032470`
- `0x180033554`
- `0x180059010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800325a5`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800325a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800325b5`

## string_xrefs

- `0x180032508`: `SoftBlockLink`

## pseudocode

```c
__int64 __fastcall CCBSUpdateDescriptor::Initialize(
        CCBSUpdateDescriptor *this,
        struct ICbsUpdate *a2,
        struct CCbsController *a3)
{
  int v5; // ebx
  int (__fastcall **v6)(struct ICbsUpdate *, GUID *, __int64 *); // rax
  __int64 v7; // rdx
  LPCWSTR *v8; // rbx
  WCHAR *v9; // rcx
  _WORD *v10; // rax
  int (__fastcall **v11)(struct ICbsUpdate *, GUID *, __int64 *); // rax
  bool v12; // zf
  int v13; // eax
  __int64 v15; // [rsp+70h] [rbp+38h] BYREF
  int v16; // [rsp+78h] [rbp+40h] BYREF
  int v17; // [rsp+80h] [rbp+48h] BYREF
  __int64 v18; // [rsp+88h] [rbp+50h] BYREF

  *((_QWORD *)this + 16) = a3;
  v5 = (*(__int64 (__fastcall **)(struct ICbsUpdate *, __int64, char *))(*(_QWORD *)a2 + 24LL))(
         a2,
         1,
         (char *)this + 16);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(struct ICbsUpdate *, __int64, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           2,
           (char *)this + 24);
    if ( v5 >= 0 )
    {
      v6 = *(int (__fastcall ***)(struct ICbsUpdate *, GUID *, __int64 *))a2;
      v18 = 0;
      if ( (*v6)(a2, &GUID_80255a37_11ed_4b44_a388_87fe71de6306, &v18) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, char *))(*(_QWORD *)v18 + 24LL))(
          v18,
          1,
          0,
          L"SoftBlockLink",
          (char *)this + 136);
        LOBYTE(v7) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptionalFeatureVisibility>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_OptionalFeatureVisibility>::GetImpl'::`2'::impl,
          v7);
        v15 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v18 + 64LL))(
                v18,
                L"OptionalFeatures\\SettingsPageOptions",
                &v15)
          || !(*(unsigned int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v18 + 64LL))(
                v18,
                L"mum2:OptionalFeatures\\mum2:SettingsPageOptions",
                &v15) )
        {
          v8 = (LPCWSTR *)((char *)this + 40);
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, const wchar_t *, char *))(*(_QWORD *)v15 + 24LL))(
                 v15,
                 0,
                 0,
                 L"Visibility",
                 (char *)this + 40)
            || !StrCmpICW(*v8, L"all") )
          {
            v9 = (WCHAR *)*v8;
            *v8 = 0;
            CoTaskMemFree(v9);
          }
        }
        CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(&v15);
      }
      v10 = (_WORD *)*((_QWORD *)this + 3);
      if ( v10 && *v10 )
      {
        (*(void (__fastcall **)(struct ICbsUpdate *, __int64, char *))(*(_QWORD *)a2 + 24LL))(a2, 3, (char *)this + 32);
        v11 = *(int (__fastcall ***)(struct ICbsUpdate *, GUID *, __int64 *))a2;
        LODWORD(v15) = 0;
        v17 = 0;
        v16 = 5;
        v5 = ((__int64 (__fastcall *)(struct ICbsUpdate *, __int64 *, int *, int *))v11[8])(a2, &v15, &v17, &v16);
        if ( v5 >= 0 )
        {
          v12 = (_DWORD)v15 == 7;
          v13 = v16;
          if ( (_DWORD)v15 == 7 )
            v13 = 6;
          *((_DWORD *)this + 27) = v13;
          *((_DWORD *)this + 28) = v12 + 1;
        }
      }
      else
      {
        v5 = -2147467259;
      }
      CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(&v18);
      if ( v5 >= 0 )
      {
        if ( (unsigned int)CDPA_Base<CCBSUpdateDescriptor,CTContainer_PolicyUnOwned<CCBSUpdateDescriptor>>::Create(
                             (char *)this + 96,
                             4)
          && (unsigned int)CDPA_Base<CCBSUpdateDescriptor,CTContainer_PolicyUnOwned<CCBSUpdateDescriptor>>::Create(
                             (char *)this + 88,
                             1) )
        {
          v5 = 0;
          (*(void (__fastcall **)(struct ICbsUpdate *))(*(_QWORD *)a2 + 8LL))(a2);
          *((_QWORD *)this + 9) = a2;
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180032470  push    rbp
0x180032472  push    rbx
0x180032473  push    rsi
0x180032474  push    rdi
0x180032475  push    r14
0x180032477  push    r15
0x180032479  mov     rbp, rsp
0x18003247c  sub     rsp, 38h
0x180032480  mov     [rcx+80h], r8
0x180032487  mov     rdi, rdx
0x18003248a  mov     rax, [rdx]
0x18003248d  lea     r8, [rcx+10h]
0x180032491  mov     rsi, rcx
0x180032494  mov     edx, 1
0x180032499  mov     rcx, rdi
0x18003249c  mov     rax, [rax+18h]
0x1800324a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324a5  xor     r15d, r15d
0x1800324a8  mov     ebx, eax
0x1800324aa  test    eax, eax
0x1800324ac  js      loc_18003268D
0x1800324b2  mov     rax, [rdi]
0x1800324b5  lea     r8, [rsi+18h]
0x1800324b9  lea     edx, [r15+2]
0x1800324bd  mov     rcx, rdi
0x1800324c0  mov     rax, [rax+18h]
0x1800324c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324c9  mov     ebx, eax
0x1800324cb  test    eax, eax
0x1800324cd  js      loc_18003268D
0x1800324d3  mov     rax, [rdi]
0x1800324d6  lea     r8, [rbp+arg_18]
0x1800324da  lea     rdx, _GUID_80255a37_11ed_4b44_a388_87fe71de6306
0x1800324e1  mov     [rbp+arg_18], r15
0x1800324e5  mov     rcx, rdi
0x1800324e8  mov     rax, [rax]
0x1800324eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324f0  test    eax, eax
0x1800324f2  js      loc_1800325C4
0x1800324f8  mov     rcx, [rbp+arg_18]
0x1800324fc  lea     rdx, [rsi+88h]
0x180032503  mov     [rsp+38h+var_18], rdx
0x180032508  lea     r9, aSoftblocklink; "SoftBlockLink"
0x18003250f  xor     r8d, r8d
0x180032512  lea     edx, [r15+1]
0x180032516  mov     rax, [rcx]
0x180032519  mov     rax, [rax+18h]
0x18003251d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032522  mov     dl, 1
0x180032524  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OptionalFeatureVisibility@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OptionalFeatureVisibility@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptionalFeatureVisibility> `wil::Feature<__WilFeatureTraits_Feature_OptionalFeatureVisibility>::GetImpl(void)'::`2'::impl
0x18003252b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OptionalFeatureVisibility@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OptionalFeatureVisibility>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180032530  mov     rcx, [rbp+arg_18]
0x180032534  lea     r8, [rbp+arg_0]
0x180032538  mov     [rbp+arg_0], r15
0x18003253c  lea     rdx, aOptionalfeatur_0; "OptionalFeatures\\SettingsPageOptions"
0x180032543  mov     rax, [rcx]
0x180032546  mov     rax, [rax+40h]
0x18003254a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003254f  test    eax, eax
0x180032551  jz      short loc_180032572
0x180032553  mov     rcx, [rbp+arg_18]
0x180032557  lea     r8, [rbp+arg_0]
0x18003255b  lea     rdx, aMum2Optionalfe; "mum2:OptionalFeatures\\mum2:SettingsPag"...
0x180032562  mov     rax, [rcx]
0x180032565  mov     rax, [rax+40h]
0x180032569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003256e  test    eax, eax
0x180032570  jnz     short loc_1800325BB
0x180032572  mov     rcx, [rbp+arg_0]
0x180032576  lea     rbx, [rsi+28h]
0x18003257a  lea     r9, aVisibility; "Visibility"
0x180032581  mov     [rsp+38h+var_18], rbx
0x180032586  xor     r8d, r8d
0x180032589  xor     edx, edx
0x18003258b  mov     rax, [rcx]
0x18003258e  mov     rax, [rax+18h]
0x180032592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032597  test    eax, eax
0x180032599  jnz     short loc_1800325AF
0x18003259b  mov     rcx, [rbx]; pszStr1
0x18003259e  lea     rdx, aAll; "all"
0x1800325a5  call    cs:__imp_StrCmpICW
0x1800325ab  test    eax, eax
0x1800325ad  jnz     short loc_1800325BB
0x1800325af  mov     rcx, [rbx]; pv
0x1800325b2  mov     [rbx], r15
0x1800325b5  call    cs:__imp_CoTaskMemFree
0x1800325bb  lea     rcx, [rbp+arg_0]
0x1800325bf  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x1800325c4  mov     rax, [rsi+18h]
0x1800325c8  test    rax, rax
0x1800325cb  jz      short loc_18003263A
0x1800325cd  cmp     [rax], r15w
0x1800325d1  jz      short loc_18003263A
0x1800325d3  mov     rax, [rdi]
0x1800325d6  lea     r8, [rsi+20h]
0x1800325da  mov     edx, 3
0x1800325df  mov     rcx, rdi
0x1800325e2  mov     rax, [rax+18h]
0x1800325e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800325eb  mov     rax, [rdi]
0x1800325ee  lea     r9, [rbp+arg_8]
0x1800325f2  lea     r8, [rbp+arg_10]
0x1800325f6  mov     dword ptr [rbp+arg_0], r15d
0x1800325fa  lea     rdx, [rbp+arg_0]
0x1800325fe  mov     [rbp+arg_10], r15d
0x180032602  mov     rcx, rdi
0x180032605  mov     [rbp+arg_8], 5
0x18003260c  mov     rax, [rax+40h]
0x180032610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032615  mov     ebx, eax
0x180032617  test    eax, eax
0x180032619  js      short loc_18003263F
0x18003261b  cmp     dword ptr [rbp+arg_0], 7
0x18003261f  mov     ecx, 6
0x180032624  mov     eax, [rbp+arg_8]
0x180032627  cmovz   eax, ecx
0x18003262a  mov     [rsi+6Ch], eax
0x18003262d  mov     eax, r15d
0x180032630  setz    al
0x180032633  inc     eax
0x180032635  mov     [rsi+70h], eax
0x180032638  jmp     short loc_18003263F
0x18003263a  mov     ebx, 80004005h
0x18003263f  lea     rcx, [rbp+arg_18]
0x180032643  call    ??1?$CReleasePtr@UICbsCustomInformation@@@@QEAA@XZ; CReleasePtr<ICbsCustomInformation>::~CReleasePtr<ICbsCustomInformation>(void)
0x180032648  test    ebx, ebx
0x18003264a  js      short loc_18003268D
0x18003264c  lea     rcx, [rsi+60h]
0x180032650  mov     edx, 4
0x180032655  call    ?Create@?$CDPA_Base@VCCBSUpdateDescriptor@@V?$CTContainer_PolicyUnOwned@VCCBSUpdateDescriptor@@@@@@QEAAHH@Z; CDPA_Base<CCBSUpdateDescriptor,CTContainer_PolicyUnOwned<CCBSUpdateDescriptor>>::Create(int)
0x18003265a  test    eax, eax
0x18003265c  jz      short loc_180032688
0x18003265e  lea     rcx, [rsi+58h]
0x180032662  mov     edx, 1
0x180032667  call    ?Create@?$CDPA_Base@VCCBSUpdateDescriptor@@V?$CTContainer_PolicyUnOwned@VCCBSUpdateDescriptor@@@@@@QEAAHH@Z; CDPA_Base<CCBSUpdateDescriptor,CTContainer_PolicyUnOwned<CCBSUpdateDescriptor>>::Create(int)
0x18003266c  test    eax, eax
0x18003266e  jz      short loc_180032688
0x180032670  mov     rax, [rdi]
0x180032673  mov     rcx, rdi
0x180032676  mov     ebx, r15d
0x180032679  mov     rax, [rax+8]
0x18003267d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032682  mov     [rsi+48h], rdi
0x180032686  jmp     short loc_18003268D
0x180032688  mov     ebx, 8007000Eh
0x18003268d  mov     eax, ebx
0x18003268f  add     rsp, 38h
0x180032693  pop     r15
0x180032695  pop     r14
0x180032697  pop     rdi
0x180032698  pop     rsi
0x180032699  pop     rbx
0x18003269a  pop     rbp
0x18003269b  retn
```
