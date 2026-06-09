# PushButtonReset::WimArchive::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WimArchive::Access,PushButtonReset::WimArchive * *)

- ea: `0x180054658`
- end: `0x18005486a`
- name: `?Open@WimArchive@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4Access@12@PEAPEAV12@@Z`
- size: `530`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x1800204b8`

## callees

- `0x180005c00`
- `0x180005c30`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x180023560`
- `0x180023690`
- `0x180037344`
- `0x180053c84`
- `0x180054658`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800546cc`
- `KERNEL32!GetLastError` at `0x180054713`
- `KERNEL32!GetLastError` at `0x1800546cc`
- `KERNEL32!GetLastError` at `0x180054713`
- `WIMGAPI!WIMCreateFile` at `0x18005469b`
- `WIMGAPI!WIMCreateFile` at `0x18005469b`

## string_xrefs

- `0x180054700`: `PushButtonReset::WimArchive::Open`
- `0x180054769`: `PushButtonReset::WimArchive::Open`
- `0x1800546e5`: `Failed to open WIM archive [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PushButtonReset::WimArchive::Open(__int64 *a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rbx
  signed int LastError; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  int *v11; // rcx
  int *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  void **v18; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h]
  void **v20; // [rsp+50h] [rbp-10h] BYREF
  __int64 v21; // [rsp+58h] [rbp-8h]
  __int64 v22; // [rsp+90h] [rbp+30h] BYREF

  v21 = WIMCreateFile(*a1, 2684354560LL, 3, 0x20000000, 0, 0);
  v20 = &RAII::CAutoWimClose::`vftable';
  v22 = 0;
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ICbsSession9 *>::operator==(&v20, &v22) )
  {
    v5 = *a1;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::WimArchive::Open",
      "base\\reset\\util\\src\\wim.cpp",
      237,
      L"Failed to open WIM archive [%s]",
      v5);
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v19 = PbrNew<PushButtonReset::WimArchive,>();
    v18 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(&v18) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::WimArchive::Open",
        "base\\reset\\util\\src\\wim.cpp",
        241,
        L"Failed to allocate wim");
      v18 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(&v18);
      v8 = -2147024882;
    }
    else
    {
      v9 = (_QWORD *)((__int64 (__fastcall *)(void ***))v18[3])(&v18);
      v10 = v9;
      v11 = (int *)(*a1 - 24);
      v12 = (int *)(*v9 - 24LL);
      if ( v11 != v12 )
      {
        if ( v12[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
        {
          v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v11);
          ATL::CStringData::Release((ATL::CStringData *)v12);
          *v10 = v13 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v9, *a1, *(unsigned int *)(*a1 - 16));
        }
      }
      v14 = v21;
      v21 = 0;
      v15 = ((__int64 (__fastcall *)(void ***))v18[3])(&v18);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v15 + 8) + 48LL))(v15 + 8, v14);
      v16 = v19;
      v19 = 0;
      *a3 = v16;
      v18 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(&v18);
      v8 = 0;
    }
  }
  v20 = &RAII::CAutoWimClose::`vftable';
  RAII::CAutoWimClose::Release((RAII::CAutoWimClose *)&v20);
  return v8;
}

```

## disassembly

```asm
0x180054658  mov     rax, rsp
0x18005465b  mov     [rax+10h], rbx
0x18005465f  mov     [rax+18h], rsi
0x180054663  push    rbp
0x180054664  push    rdi
0x180054665  push    r12
0x180054667  push    r13
0x180054669  push    r14
0x18005466b  mov     rbp, rsp
0x18005466e  sub     rsp, 60h
0x180054672  mov     r14, r8
0x180054675  mov     rbx, rcx
0x180054678  mov     qword ptr [rax-60h], 0
0x180054680  mov     dword ptr [rax-68h], 0
0x180054687  mov     edx, 0A0000000h
0x18005468c  mov     r9d, 20000000h
0x180054692  mov     r8d, 3
0x180054698  mov     rcx, [rcx]
0x18005469b  call    cs:__imp_WIMCreateFile
0x1800546a1  mov     [rbp+var_8], rax
0x1800546a5  lea     r13, ??_7CAutoWimClose@RAII@@6B@; const RAII::CAutoWimClose::`vftable'
0x1800546ac  mov     [rbp+var_10], r13
0x1800546b0  mov     [rbp+arg_0], 0
0x1800546b8  lea     rdx, [rbp+arg_0]
0x1800546bc  lea     rcx, [rbp+var_10]
0x1800546c0  call    ??8?$CAutoCleanupBase@PEAUICbsSession9@@@RAII@@UEBA_NAEBQEAUICbsSession9@@@Z; RAII::CAutoCleanupBase<ICbsSession9 *>::operator==(ICbsSession9 * const &)
0x1800546c5  test    al, al
0x1800546c7  jz      short loc_18005472D
0x1800546c9  mov     rbx, [rbx]
0x1800546cc  call    cs:__imp_GetLastError
0x1800546d2  mov     edi, 80070000h
0x1800546d7  test    eax, eax
0x1800546d9  jle     short loc_1800546E0
0x1800546db  movzx   eax, ax
0x1800546de  or      eax, edi
0x1800546e0  mov     [rsp+60h+var_30], rbx
0x1800546e5  lea     rcx, aFailedToOpenWi; "Failed to open WIM archive [%s]"
0x1800546ec  mov     [rsp+60h+var_38], rcx
0x1800546f1  mov     [rsp+60h+var_40], 0EDh
0x1800546f9  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180054700  lea     r8, aPushbuttonrese_92; "PushButtonReset::WimArchive::Open"
0x180054707  mov     edx, eax
0x180054709  mov     ecx, 2
0x18005470e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180054713  call    cs:__imp_GetLastError
0x180054719  mov     ebx, eax
0x18005471b  test    eax, eax
0x18005471d  jle     loc_180054842
0x180054723  movzx   ebx, ax
0x180054726  or      ebx, edi
0x180054728  jmp     loc_180054842
0x18005472d  call    ??$PbrNew@VWimArchive@PushButtonReset@@$$V@@YAPEAVWimArchive@PushButtonReset@@XZ; PbrNew<PushButtonReset::WimArchive,>(void)
0x180054732  mov     [rbp+var_18], rax
0x180054736  lea     r12, ??_7?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable'
0x18005473d  mov     [rbp+var_20], r12
0x180054741  lea     rcx, [rbp+var_20]
0x180054745  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18005474a  test    al, al
0x18005474c  jz      short loc_180054797
0x18005474e  lea     rax, aFailedToAlloca_25; "Failed to allocate wim"
0x180054755  mov     [rsp+60h+var_38], rax
0x18005475a  mov     [rsp+60h+var_40], 0F1h
0x180054762  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180054769  lea     r8, aPushbuttonrese_92; "PushButtonReset::WimArchive::Open"
0x180054770  mov     edx, 8007000Eh
0x180054775  mov     ecx, 2
0x18005477a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005477f  nop
0x180054780  mov     [rbp+var_20], r12
0x180054784  lea     rcx, [rbp+var_20]
0x180054788  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x18005478d  mov     ebx, 8007000Eh
0x180054792  jmp     loc_180054842
0x180054797  mov     rax, [rbp+var_20]
0x18005479b  lea     rcx, [rbp+var_20]
0x18005479f  mov     rax, [rax+18h]
0x1800547a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547a8  mov     rsi, rax
0x1800547ab  mov     r9, [rbx]
0x1800547ae  lea     rcx, [r9-18h]
0x1800547b2  mov     rdi, [rax]
0x1800547b5  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800547b9  cmp     rcx, rdi
0x1800547bc  jz      short loc_1800547F4
0x1800547be  cmp     dword ptr [rdi+10h], 0
0x1800547c2  jl      short loc_1800547E5
0x1800547c4  mov     rdx, [rdi]
0x1800547c7  cmp     [rcx], rdx
0x1800547ca  jnz     short loc_1800547E5
0x1800547cc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800547d1  mov     rbx, rax
0x1800547d4  mov     rcx, rdi; this
0x1800547d7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800547dc  lea     rax, [rbx+18h]
0x1800547e0  mov     [rsi], rax
0x1800547e3  jmp     short loc_1800547F4
0x1800547e5  mov     r8d, [r9-10h]
0x1800547e9  mov     rdx, r9
0x1800547ec  mov     rcx, rsi
0x1800547ef  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800547f4  mov     rbx, [rbp+var_8]
0x1800547f8  mov     [rbp+var_8], 0
0x180054800  mov     rax, [rbp+var_20]
0x180054804  lea     rcx, [rbp+var_20]
0x180054808  mov     rax, [rax+18h]
0x18005480c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054811  lea     rcx, [rax+8]
0x180054815  mov     rax, [rcx]
0x180054818  mov     rdx, rbx
0x18005481b  mov     rax, [rax+30h]
0x18005481f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054824  mov     rax, [rbp+var_18]
0x180054828  mov     [rbp+var_18], 0
0x180054830  mov     [r14], rax
0x180054833  mov     [rbp+var_20], r12
0x180054837  lea     rcx, [rbp+var_20]
0x18005483b  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x180054840  xor     ebx, ebx
0x180054842  mov     [rbp+var_10], r13
0x180054846  lea     rcx, [rbp+var_10]; this
0x18005484a  call    ?Release@CAutoWimClose@RAII@@UEAAXXZ; RAII::CAutoWimClose::Release(void)
0x18005484f  mov     eax, ebx
0x180054851  lea     r11, [rsp+60h+var_s0]
0x180054856  mov     rbx, [r11+38h]
0x18005485a  mov     rsi, [r11+40h]
0x18005485e  mov     rsp, r11
0x180054861  pop     r14
0x180054863  pop     r13
0x180054865  pop     r12
0x180054867  pop     rdi
0x180054868  pop     rbp
0x180054869  retn
```
