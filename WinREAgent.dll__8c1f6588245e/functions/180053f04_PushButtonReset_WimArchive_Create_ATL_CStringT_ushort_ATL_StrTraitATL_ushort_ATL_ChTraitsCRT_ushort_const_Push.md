# PushButtonReset::WimArchive::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WimArchive::Compression,PushButtonReset::WimArchive * *)

- ea: `0x180053f04`
- end: `0x1800541aa`
- name: `?Create@WimArchive@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4Compression@12@PEAPEAV12@@Z`
- size: `678`
- prototype: `__int64 __fastcall(__int64 *, int, __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

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
- `0x180053f04`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180054012`
- `KERNEL32!GetLastError` at `0x180054056`
- `KERNEL32!GetLastError` at `0x180054012`
- `KERNEL32!GetLastError` at `0x180054056`
- `WIMGAPI!WIMCreateFile` at `0x180053fe1`
- `WIMGAPI!WIMCreateFile` at `0x180053fe1`

## string_xrefs

- `0x180053f4d`: `Invalid compression algorithm %u`
- `0x180053f68`: `PbrWimCompressionToFlag`
- `0x180053f98`: `PushButtonReset::WimArchive::Create`
- `0x180054046`: `PushButtonReset::WimArchive::Create`
- `0x1800540ac`: `PushButtonReset::WimArchive::Create`
- `0x18005402b`: `Failed to create WIM archive [%s]`

## pseudocode

```c
__int64 __fastcall PushButtonReset::WimArchive::Create(__int64 *a1, int a2, __int64 *a3)
{
  int v6; // eax
  __int64 v7; // rbx
  signed int LastError; // eax
  signed int v9; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  int *v13; // rcx
  int *v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  void **v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h]
  void **v21; // [rsp+50h] [rbp-10h] BYREF
  __int64 v22; // [rsp+58h] [rbp-8h]
  __int64 v23; // [rsp+A8h] [rbp+48h] BYREF

  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        v6 = 1;
        break;
      case 2:
        v6 = 2;
        break;
      case 3:
        v6 = 3;
        break;
      default:
        PushButtonReset::Logging::TraceErr(
          2,
          2147942487LL,
          "PbrWimCompressionToFlag",
          "base\\reset\\util\\src\\wim.cpp",
          115,
          L"Invalid compression algorithm %u",
          a2);
        PushButtonReset::Logging::TraceErr(
          2,
          2147942487LL,
          "PushButtonReset::WimArchive::Create",
          "base\\reset\\util\\src\\wim.cpp",
          189,
          &pszFormat);
        return 2147942487LL;
    }
  }
  else
  {
    v6 = 0;
  }
  v22 = WIMCreateFile(*a1, 3758096384LL, 2, 0, v6, 0);
  v21 = &RAII::CAutoWimClose::`vftable';
  v23 = 0;
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ICbsSession9 *>::operator==(&v21, &v23) )
  {
    v7 = *a1;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "PushButtonReset::WimArchive::Create",
      "base\\reset\\util\\src\\wim.cpp",
      195,
      L"Failed to create WIM archive [%s]",
      v7);
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
  }
  else
  {
    v20 = PbrNew<PushButtonReset::WimArchive,>();
    v19 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(&v19) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::WimArchive::Create",
        "base\\reset\\util\\src\\wim.cpp",
        199,
        L"Failed to allocate wim");
      v19 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(&v19);
      v10 = -2147024882;
    }
    else
    {
      v11 = (_QWORD *)((__int64 (__fastcall *)(void ***))v19[3])(&v19);
      v12 = v11;
      v13 = (int *)(*a1 - 24);
      v14 = (int *)(*v11 - 24LL);
      if ( v13 != v14 )
      {
        if ( v14[4] >= 0 && *(_QWORD *)v13 == *(_QWORD *)v14 )
        {
          v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
          ATL::CStringData::Release((ATL::CStringData *)v14);
          *v12 = v15 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v11, *a1, *(unsigned int *)(*a1 - 16));
        }
      }
      v16 = v22;
      v22 = 0;
      v17 = ((__int64 (__fastcall *)(void ***))v19[3])(&v19);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v17 + 8) + 48LL))(v17 + 8, v16);
      v18 = v20;
      v20 = 0;
      *a3 = v18;
      v19 = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(&v19);
      v10 = 0;
    }
  }
  v21 = &RAII::CAutoWimClose::`vftable';
  RAII::CAutoWimClose::Release((RAII::CAutoWimClose *)&v21);
  return v10;
}

```

## disassembly

```asm
0x180053f04  mov     [rsp-28h+arg_0], rbx
0x180053f09  mov     [rsp-28h+arg_8], rsi
0x180053f0e  push    rbp
0x180053f0f  push    rdi
0x180053f10  push    r12
0x180053f12  push    r13
0x180053f14  push    r14
0x180053f16  mov     rbp, rsp
0x180053f19  sub     rsp, 60h
0x180053f1d  mov     r14, r8
0x180053f20  mov     rbx, rcx
0x180053f23  mov     r9d, edx
0x180053f26  mov     edi, 2
0x180053f2b  test    edx, edx
0x180053f2d  jz      loc_180053FC4
0x180053f33  sub     r9d, 1
0x180053f37  jz      loc_180053FBD
0x180053f3d  sub     r9d, 1
0x180053f41  jz      short loc_180053FB9
0x180053f43  cmp     r9d, 1
0x180053f47  jz      short loc_180053FB2
0x180053f49  mov     dword ptr [rsp+60h+var_30], edx
0x180053f4d  lea     rax, aInvalidCompres; "Invalid compression algorithm %u"
0x180053f54  mov     [rsp+60h+var_38], rax
0x180053f59  mov     [rsp+60h+var_40], 73h ; 's'
0x180053f61  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180053f68  lea     r8, aPbrwimcompress; "PbrWimCompressionToFlag"
0x180053f6f  mov     ebx, 80070057h
0x180053f74  mov     edx, ebx
0x180053f76  mov     ecx, edi
0x180053f78  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053f7d  lea     rax, pszFormat
0x180053f84  mov     [rsp+60h+var_38], rax
0x180053f89  mov     [rsp+60h+var_40], 0BDh
0x180053f91  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180053f98  lea     r8, aPushbuttonrese_56; "PushButtonReset::WimArchive::Create"
0x180053f9f  mov     edx, ebx
0x180053fa1  mov     ecx, edi
0x180053fa3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180053fa8  mov     eax, 80070057h
0x180053fad  jmp     loc_180054191
0x180053fb2  mov     eax, 3
0x180053fb7  jmp     short loc_180053FC6
0x180053fb9  mov     eax, edi
0x180053fbb  jmp     short loc_180053FC6
0x180053fbd  mov     eax, 1
0x180053fc2  jmp     short loc_180053FC6
0x180053fc4  xor     eax, eax
0x180053fc6  mov     [rsp+60h+var_38], 0
0x180053fcf  mov     [rsp+60h+var_40], eax
0x180053fd3  xor     r9d, r9d
0x180053fd6  mov     r8d, edi
0x180053fd9  mov     edx, 0E0000000h
0x180053fde  mov     rcx, [rcx]
0x180053fe1  call    cs:__imp_WIMCreateFile
0x180053fe7  mov     [rbp+var_8], rax
0x180053feb  lea     r13, ??_7CAutoWimClose@RAII@@6B@; const RAII::CAutoWimClose::`vftable'
0x180053ff2  mov     [rbp+var_10], r13
0x180053ff6  mov     [rbp+arg_18], 0
0x180053ffe  lea     rdx, [rbp+arg_18]
0x180054002  lea     rcx, [rbp+var_10]
0x180054006  call    ??8?$CAutoCleanupBase@PEAUICbsSession9@@@RAII@@UEBA_NAEBQEAUICbsSession9@@@Z; RAII::CAutoCleanupBase<ICbsSession9 *>::operator==(ICbsSession9 * const &)
0x18005400b  test    al, al
0x18005400d  jz      short loc_180054070
0x18005400f  mov     rbx, [rbx]
0x180054012  call    cs:__imp_GetLastError
0x180054018  mov     esi, 80070000h
0x18005401d  test    eax, eax
0x18005401f  jle     short loc_180054026
0x180054021  movzx   eax, ax
0x180054024  or      eax, esi
0x180054026  mov     [rsp+60h+var_30], rbx
0x18005402b  lea     rcx, aFailedToCreate_39; "Failed to create WIM archive [%s]"
0x180054032  mov     [rsp+60h+var_38], rcx
0x180054037  mov     [rsp+60h+var_40], 0C3h
0x18005403f  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x180054046  lea     r8, aPushbuttonrese_56; "PushButtonReset::WimArchive::Create"
0x18005404d  mov     edx, eax
0x18005404f  mov     ecx, edi
0x180054051  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180054056  call    cs:__imp_GetLastError
0x18005405c  mov     ebx, eax
0x18005405e  test    eax, eax
0x180054060  jle     loc_180054182
0x180054066  movzx   ebx, ax
0x180054069  or      ebx, esi
0x18005406b  jmp     loc_180054182
0x180054070  call    ??$PbrNew@VWimArchive@PushButtonReset@@$$V@@YAPEAVWimArchive@PushButtonReset@@XZ; PbrNew<PushButtonReset::WimArchive,>(void)
0x180054075  mov     [rbp+var_18], rax
0x180054079  lea     r12, ??_7?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable'
0x180054080  mov     [rbp+var_20], r12
0x180054084  lea     rcx, [rbp+var_20]
0x180054088  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18005408d  test    al, al
0x18005408f  jz      short loc_1800540D7
0x180054091  lea     rax, aFailedToAlloca_25; "Failed to allocate wim"
0x180054098  mov     [rsp+60h+var_38], rax
0x18005409d  mov     [rsp+60h+var_40], 0C7h
0x1800540a5  lea     r9, aBaseResetUtilS_1; "base\\reset\\util\\src\\wim.cpp"
0x1800540ac  lea     r8, aPushbuttonrese_56; "PushButtonReset::WimArchive::Create"
0x1800540b3  mov     edx, 8007000Eh
0x1800540b8  mov     ecx, edi
0x1800540ba  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800540bf  nop
0x1800540c0  mov     [rbp+var_20], r12
0x1800540c4  lea     rcx, [rbp+var_20]
0x1800540c8  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x1800540cd  mov     ebx, 8007000Eh
0x1800540d2  jmp     loc_180054182
0x1800540d7  mov     rax, [rbp+var_20]
0x1800540db  lea     rcx, [rbp+var_20]
0x1800540df  mov     rax, [rax+18h]
0x1800540e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800540e8  mov     rsi, rax
0x1800540eb  mov     r9, [rbx]
0x1800540ee  lea     rcx, [r9-18h]
0x1800540f2  mov     rdi, [rax]
0x1800540f5  add     rdi, 0FFFFFFFFFFFFFFE8h
0x1800540f9  cmp     rcx, rdi
0x1800540fc  jz      short loc_180054134
0x1800540fe  cmp     dword ptr [rdi+10h], 0
0x180054102  jl      short loc_180054125
0x180054104  mov     rdx, [rdi]
0x180054107  cmp     [rcx], rdx
0x18005410a  jnz     short loc_180054125
0x18005410c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180054111  mov     rbx, rax
0x180054114  mov     rcx, rdi; this
0x180054117  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18005411c  lea     rax, [rbx+18h]
0x180054120  mov     [rsi], rax
0x180054123  jmp     short loc_180054134
0x180054125  mov     r8d, [r9-10h]
0x180054129  mov     rdx, r9
0x18005412c  mov     rcx, rsi
0x18005412f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180054134  mov     rbx, [rbp+var_8]
0x180054138  mov     [rbp+var_8], 0
0x180054140  mov     rax, [rbp+var_20]
0x180054144  lea     rcx, [rbp+var_20]
0x180054148  mov     rax, [rax+18h]
0x18005414c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054151  lea     rcx, [rax+8]
0x180054155  mov     rax, [rcx]
0x180054158  mov     rdx, rbx
0x18005415b  mov     rax, [rax+30h]
0x18005415f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054164  mov     rax, [rbp+var_18]
0x180054168  mov     [rbp+var_18], 0
0x180054170  mov     [r14], rax
0x180054173  mov     [rbp+var_20], r12
0x180054177  lea     rcx, [rbp+var_20]
0x18005417b  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x180054180  xor     ebx, ebx
0x180054182  mov     [rbp+var_10], r13
0x180054186  lea     rcx, [rbp+var_10]; this
0x18005418a  call    ?Release@CAutoWimClose@RAII@@UEAAXXZ; RAII::CAutoWimClose::Release(void)
0x18005418f  mov     eax, ebx
0x180054191  lea     r11, [rsp+60h+var_s0]
0x180054196  mov     rbx, [r11+30h]
0x18005419a  mov     rsi, [r11+38h]
0x18005419e  mov     rsp, r11
0x1800541a1  pop     r14
0x1800541a3  pop     r13
0x1800541a5  pop     r12
0x1800541a7  pop     rdi
0x1800541a8  pop     rbp
0x1800541a9  retn
```
