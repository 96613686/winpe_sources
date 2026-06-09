# CCloudFileSystemInterface::ConsumeChange(ulong,IFileInfoFromDisk *,int)

- ea: `0x1800891b0`
- end: `0x1800898f2`
- name: `?ConsumeChange@CCloudFileSystemInterface@@UEAAJKPEAUIFileInfoFromDisk@@H@Z`
- size: `1858`
- prototype: `__int64 __fastcall(CCloudFileSystemInterface *__hidden this, unsigned int, struct IFileInfoFromDisk *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180008bdc`
- `0x180009188`
- `0x180009384`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x18002e6cc`
- `0x18005f0b0`
- `0x180088e10`
- `0x1800891b0`
- `0x18008b3fc`
- `0x180098230`
- `0x18009859c`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800896ab`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800896ab`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x1800892da`
- `cldapi!CfGetPlaceholderStateFromAttributeTag` at `0x1800892da`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CCloudFileSystemInterface::ConsumeChange(
        CCloudFileSystemInterface *this,
        int a2,
        struct IFileInfoFromDisk *a3,
        int a4)
{
  _DWORD *v7; // rax
  char v8; // cl
  __int16 v9; // ax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  char PlaceholderStateFromAttributeTag; // r12
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int64, _QWORD); // rbx
  __int64 v15; // rax
  unsigned int v16; // r14d
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64); // rdi
  __int64 v19; // rbx
  char v20; // di
  char v21; // bl
  int v22; // eax
  const unsigned __int16 *v23; // rax
  __int64 v24; // rax
  char v25; // bl
  int v26; // eax
  const unsigned __int16 *v27; // rax
  int v28; // edi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  const WCHAR *v32; // rax
  HRESULT Extension; // eax
  const unsigned __int16 *v34; // rbx
  unsigned __int64 v35; // rax
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, __int64, __int64); // rbx
  __int64 v38; // rax
  __int64 v39; // rdi
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, __int64, _QWORD, _QWORD); // rbx
  __int64 v42; // rax
  unsigned int v43; // ebx
  __int64 v45; // [rsp+30h] [rbp-59h] BYREF
  int v46; // [rsp+38h] [rbp-51h] BYREF
  int v47; // [rsp+3Ch] [rbp-4Dh]
  char v48; // [rsp+40h] [rbp-49h]
  const char *v49; // [rsp+48h] [rbp-41h]
  __int64 v50; // [rsp+50h] [rbp-39h]
  int v51; // [rsp+58h] [rbp-31h] BYREF
  __int64 v52; // [rsp+60h] [rbp-29h] BYREF
  __int64 v53; // [rsp+68h] [rbp-21h] BYREF
  int v54; // [rsp+70h] [rbp-19h]
  PCWSTR ppszExt; // [rsp+78h] [rbp-11h] BYREF
  _BYTE v56[32]; // [rsp+80h] [rbp-9h] BYREF

  v54 = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, WPP_622f59390c8534e9e167ba581245440f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (v7[17] & 0x100) == 0 || (v8 = 1, *((_BYTE *)v7 + 65) < 6u) )
    v8 = 0;
  v47 = 603;
  v48 = v8;
  v49 = "CCloudFileSystemInterface::ConsumeChange";
  v50 = 0;
  v45 = 0;
  v53 = 0;
  v52 = 0;
  v51 = 0;
  v46 = 0;
  v9 = 611;
  if ( !a3 )
  {
    v46 = -2147024809;
LABEL_10:
    HIWORD(v47) = v9;
    goto LABEL_65;
  }
  v46 = 0;
  LOWORD(v47) = 611;
  v46 = (**(__int64 (__fastcall ***)(struct IFileInfoFromDisk *, GUID *, __int64 *))a3)(
          a3,
          &GUID_dea78bf1_52f0_4ce1_b7ff_f363d84a51ae,
          &v45);
  v9 = 614;
  if ( v46 < 0 )
    goto LABEL_10;
  LOWORD(v47) = 614;
  v10 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)a3 + 88LL))(a3);
  v11 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)a3 + 32LL))(a3);
  PlaceholderStateFromAttributeTag = CfGetPlaceholderStateFromAttributeTag(v11, v10);
  v46 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1), &v51);
  v9 = 620;
  if ( v46 < 0 )
    goto LABEL_10;
  LOWORD(v47) = 620;
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 144LL))(v45) )
    goto LABEL_65;
  if ( (PlaceholderStateFromAttributeTag & 2) == 0 || v51 )
  {
    v16 = a2 & 0xFFFF0004;
    if ( ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 32LL))(v45) & 0x10) == 0
      && v16 == 0
      && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 176LL))(v45) )
    {
      if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45) != 1
        || (v17 = v45,
            v18 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 160LL),
            v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 64LL))(v45),
            v18(v17) == v19) )
      {
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 168LL))(v45) == 2
          && (PlaceholderStateFromAttributeTag & 0x20) == 0 )
        {
          if ( v51 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 160LL))(v45);
              v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
              WPP_SF_Si(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                27,
                (unsigned int)WPP_622f59390c8534e9e167ba581245440f_Traceguids,
                v26,
                v25);
            }
            v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 128LL))(v45);
            v28 = CCloudFileSystemAsyncHydrationManager::DehydratePlaceholderAsync(v27);
            ppszExt = &Format;
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
            std::wstring::wstring((__int64)v56, v29);
            v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
            v31 = -1;
            do
              ++v31;
            while ( *(_WORD *)(v30 + 2 * v31) );
            v32 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
            Extension = PathCchFindExtension(v32, v31 + 1, &ppszExt);
            if ( Extension < 0 )
            {
              ppszExt = &Format;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 7),
                  28,
                  WPP_622f59390c8534e9e167ba581245440f_Traceguids,
                  (unsigned int)Extension);
              }
            }
            v34 = ppszExt;
            v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 160LL))(v45);
            if ( CEcsAsimovTelemetry::s_telemetryInstance )
              CEcsAsimovTelemetry::SetDehydrationTelemetry(CEcsAsimovTelemetry::s_telemetryInstance, v35, v34, v28);
            v46 = v28;
            if ( v28 < 0 )
            {
              HIWORD(v47) = 683;
              std::wstring::~wstring((__int64)v56);
              goto LABEL_65;
            }
            LOWORD(v47) = 683;
            std::wstring::~wstring((__int64)v56);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
          {
            v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_622f59390c8534e9e167ba581245440f_Traceguids, v24);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 64LL))(v45);
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 160LL))(v45);
          v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 104LL))(v45);
          WPP_SF_Sii(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            25,
            (unsigned int)WPP_622f59390c8534e9e167ba581245440f_Traceguids,
            v22,
            v21,
            v20);
        }
        v23 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 128LL))(v45);
        v46 = CCloudFileSystemAsyncHydrationManager::HydratePlaceholderAsync(v23);
        v9 = 653;
        if ( v46 < 0 )
          goto LABEL_10;
        LOWORD(v47) = 653;
      }
    }
  }
  else
  {
    v46 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this - 1) + 48LL))((char *)this - 8, &v53);
    v9 = 631;
    if ( v46 < 0 )
      goto LABEL_10;
    LOWORD(v47) = 631;
    v46 = ATL::CComPtrBase<ISyncFileSystemApplier>::QueryInterface<ICloudFileSystemApplier>(&v53, (__int64)&v52);
    v9 = 632;
    if ( v46 < 0 )
      goto LABEL_10;
    LOWORD(v47) = 632;
    v13 = v52;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD))(*(_QWORD *)v52 + 32LL);
    v15 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)a3 + 128LL))(a3);
    v46 = v14(v13, v15, 1, 1, 0);
    v9 = 635;
    if ( v46 < 0 )
      goto LABEL_10;
    LOWORD(v47) = 635;
    v16 = a2 & 0xFFFF0004;
  }
  if ( !v16
    && v54
    && (!(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 176LL))(v45)
     || (PlaceholderStateFromAttributeTag & 4) != 0) )
  {
    v46 = (*(__int64 (__fastcall **)(char *, __int64 *))(*((_QWORD *)this - 1) + 48LL))((char *)this - 8, &v53);
    v9 = 696;
    if ( v46 < 0 )
      goto LABEL_10;
    LOWORD(v47) = 696;
    v46 = ATL::CComPtrBase<ISyncFileSystemApplier>::QueryInterface<ICloudFileSystemApplier>(&v53, (__int64)&v52);
    v9 = 697;
    if ( v46 < 0 )
      goto LABEL_10;
    LOWORD(v47) = 697;
    if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v45 + 176LL))(v45) )
    {
      v36 = v52;
      v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 40LL);
      v38 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)a3 + 128LL))(a3);
      v46 = v37(v36, v38, 1);
      v9 = 702;
      if ( v46 < 0 )
        goto LABEL_10;
      LOWORD(v47) = 702;
    }
    if ( (PlaceholderStateFromAttributeTag & 4) == 0 )
      goto LABEL_65;
    v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 32LL))(v45) & 1;
    v40 = v52;
    v41 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v52 + 48LL);
    v42 = (*(__int64 (__fastcall **)(struct IFileInfoFromDisk *))(*(_QWORD *)a3 + 128LL))(a3);
    v46 = v41(v40, v42, 0, (unsigned int)v39);
    v9 = 709;
    if ( v46 >= 0 )
    {
      LOWORD(v47) = 709;
      goto LABEL_65;
    }
    goto LABEL_10;
  }
LABEL_65:
  v43 = v46;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v46);
  return v43;
}

```

## disassembly

```asm
0x1800891b0  mov     [rsp-8+arg_8], rbx
0x1800891b5  push    rbp
0x1800891b6  push    rsi
0x1800891b7  push    rdi
0x1800891b8  push    r12
0x1800891ba  push    r13
0x1800891bc  push    r14
0x1800891be  push    r15
0x1800891c0  lea     rbp, [rsp-27h]
0x1800891c5  sub     rsp, 0B0h
0x1800891cc  mov     rax, cs:__security_cookie
0x1800891d3  xor     rax, rsp
0x1800891d6  mov     [rbp+57h+var_40], rax
0x1800891da  mov     [rbp+57h+var_70], r9d
0x1800891de  mov     r15, r8
0x1800891e1  mov     r14d, edx
0x1800891e4  mov     r13, rcx
0x1800891e7  lea     rcx, WPP_GLOBAL_Control
0x1800891ee  mov     edi, 100h
0x1800891f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800891fa  cmp     rax, rcx
0x1800891fd  jz      short loc_180089226
0x1800891ff  test    [rax+44h], edi
0x180089202  jz      short loc_180089226
0x180089204  cmp     byte ptr [rax+41h], 6
0x180089208  jb      short loc_180089226
0x18008920a  mov     edx, 18h
0x18008920f  lea     r8, WPP_622f59390c8534e9e167ba581245440f_Traceguids
0x180089216  mov     rcx, [rax+38h]
0x18008921a  call    WPP_SF_
0x18008921f  mov     rax, cs:WPP_GLOBAL_Control
0x180089226  xor     esi, esi
0x180089228  test    [rax+44h], edi
0x18008922b  jz      short loc_180089235
0x18008922d  cmp     byte ptr [rax+41h], 6
0x180089231  mov     cl, 1
0x180089233  jnb     short loc_180089238
0x180089235  mov     cl, sil
0x180089238  mov     [rbp+57h+var_A8], esi
0x18008923b  mov     [rbp+57h+var_A4], 25Bh
0x180089242  mov     [rbp+57h+var_A0], cl
0x180089245  lea     rax, aCcloudfilesyst_19; "CCloudFileSystemInterface::ConsumeChang"...
0x18008924c  mov     [rbp+57h+var_98], rax
0x180089250  mov     [rbp+57h+var_90], rsi
0x180089254  mov     [rbp+57h+var_B0], rsi
0x180089258  mov     [rbp+57h+var_78], rsi
0x18008925c  mov     [rbp+57h+var_80], rsi
0x180089260  mov     [rbp+57h+var_88], esi
0x180089263  mov     eax, [rbp+57h+var_A8]
0x180089266  mov     [rbp+57h+var_A8], eax
0x180089269  mov     eax, 263h
0x18008926e  test    r15, r15
0x180089271  jnz     short loc_180089283
0x180089273  mov     [rbp+57h+var_A8], 80070057h
0x18008927a  mov     word ptr [rbp+57h+var_A4+2], ax
0x18008927e  jmp     loc_18008989F
0x180089283  mov     [rbp+57h+var_A8], esi
0x180089286  mov     word ptr [rbp+57h+var_A4], ax
0x18008928a  mov     rax, [r15]
0x18008928d  lea     r8, [rbp+57h+var_B0]
0x180089291  lea     rdx, _GUID_dea78bf1_52f0_4ce1_b7ff_f363d84a51ae
0x180089298  mov     rcx, r15
0x18008929b  mov     rax, [rax]
0x18008929e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892a3  mov     [rbp+57h+var_A8], eax
0x1800892a6  mov     [rbp+57h+var_A8], eax
0x1800892a9  test    eax, eax
0x1800892ab  mov     eax, 266h
0x1800892b0  js      short loc_18008927A
0x1800892b2  mov     word ptr [rbp+57h+var_A4], ax
0x1800892b6  mov     rax, [r15]
0x1800892b9  mov     rcx, r15
0x1800892bc  mov     rax, [rax+58h]
0x1800892c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892c5  mov     ebx, eax
0x1800892c7  mov     rcx, [r15]
0x1800892ca  mov     rax, [rcx+20h]
0x1800892ce  mov     rcx, r15
0x1800892d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892d6  mov     edx, ebx
0x1800892d8  mov     ecx, eax
0x1800892da  call    cs:__imp_CfGetPlaceholderStateFromAttributeTag
0x1800892e0  mov     r12d, eax
0x1800892e3  mov     rcx, [r13+8]
0x1800892e7  mov     rdx, [rcx]
0x1800892ea  mov     rax, [rdx+30h]
0x1800892ee  lea     rdx, [rbp+57h+var_88]
0x1800892f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800892f7  mov     [rbp+57h+var_A8], eax
0x1800892fa  mov     [rbp+57h+var_A8], eax
0x1800892fd  test    eax, eax
0x1800892ff  mov     eax, 26Ch
0x180089304  js      loc_18008927A
0x18008930a  mov     word ptr [rbp+57h+var_A4], ax
0x18008930e  mov     rcx, [rbp+57h+var_B0]
0x180089312  mov     rax, [rcx]
0x180089315  mov     rax, [rax+90h]
0x18008931c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089321  test    eax, eax
0x180089323  jz      loc_18008989F
0x180089329  test    r12b, 2
0x18008932d  jz      loc_1800893EA
0x180089333  cmp     [rbp+57h+var_88], esi
0x180089336  jnz     loc_1800893EA
0x18008933c  mov     rax, [r13-8]
0x180089340  lea     rdx, [rbp+57h+var_78]
0x180089344  lea     rcx, [r13-8]
0x180089348  mov     rax, [rax+30h]
0x18008934c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089351  mov     [rbp+57h+var_A8], eax
0x180089354  mov     [rbp+57h+var_A8], eax
0x180089357  test    eax, eax
0x180089359  mov     eax, 277h
0x18008935e  js      loc_18008927A
0x180089364  mov     word ptr [rbp+57h+var_A4], ax
0x180089368  lea     rdx, [rbp+57h+var_80]
0x18008936c  lea     rcx, [rbp+57h+var_78]
0x180089370  call    ??$QueryInterface@UICloudFileSystemApplier@@@?$CComPtrBase@UISyncFileSystemApplier@@@ATL@@QEBAJPEAPEAUICloudFileSystemApplier@@@Z; ATL::CComPtrBase<ISyncFileSystemApplier>::QueryInterface<ICloudFileSystemApplier>(ICloudFileSystemApplier * *)
0x180089375  mov     [rbp+57h+var_A8], eax
0x180089378  mov     [rbp+57h+var_A8], eax
0x18008937b  test    eax, eax
0x18008937d  mov     eax, 278h
0x180089382  js      loc_18008927A
0x180089388  mov     word ptr [rbp+57h+var_A4], ax
0x18008938c  mov     rdi, [rbp+57h+var_80]
0x180089390  mov     rax, [rdi]
0x180089393  mov     rbx, [rax+20h]
0x180089397  mov     rdx, [r15]
0x18008939a  mov     rcx, r15
0x18008939d  mov     rax, [rdx+80h]
0x1800893a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893a9  mov     [rsp+0E0h+var_C0], rsi
0x1800893ae  mov     ecx, 1
0x1800893b3  mov     r9d, ecx
0x1800893b6  mov     r8d, ecx
0x1800893b9  mov     rdx, rax
0x1800893bc  mov     rcx, rdi
0x1800893bf  mov     rax, rbx
0x1800893c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893c7  mov     [rbp+57h+var_A8], eax
0x1800893ca  mov     [rbp+57h+var_A8], eax
0x1800893cd  test    eax, eax
0x1800893cf  mov     eax, 27Bh
0x1800893d4  js      loc_18008927A
0x1800893da  mov     word ptr [rbp+57h+var_A4], ax
0x1800893de  and     r14d, 0FFFF0004h
0x1800893e5  jmp     loc_180089759
0x1800893ea  mov     rcx, [rbp+57h+var_B0]
0x1800893ee  mov     rax, [rcx]
0x1800893f1  mov     rax, [rax+20h]
0x1800893f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800893fa  test    al, 10h
0x1800893fc  setz    cl
0x1800893ff  and     r14d, 0FFFF0004h
0x180089406  setz    al
0x180089409  test    al, cl
0x18008940b  jz      loc_180089759
0x180089411  mov     rcx, [rbp+57h+var_B0]
0x180089415  mov     rax, [rcx]
0x180089418  mov     rax, [rax+0B0h]
0x18008941f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089424  test    eax, eax
0x180089426  jz      loc_180089759
0x18008942c  mov     rcx, [rbp+57h+var_B0]
0x180089430  mov     rax, [rcx]
0x180089433  mov     rax, [rax+0A8h]
0x18008943a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008943f  cmp     eax, 1
0x180089442  jnz     loc_18008953D
0x180089448  mov     rsi, [rbp+57h+var_B0]
0x18008944c  mov     rax, [rsi]
0x18008944f  mov     rdi, [rax+0A0h]
0x180089456  mov     rcx, rsi
0x180089459  mov     rax, [rax+40h]
0x18008945d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089462  mov     rbx, rax
0x180089465  mov     rcx, rsi
0x180089468  mov     rax, rdi
0x18008946b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089470  cmp     rax, rbx
0x180089473  jz      loc_180089536
0x180089479  mov     rax, cs:WPP_GLOBAL_Control
0x180089480  lea     rdx, WPP_GLOBAL_Control
0x180089487  cmp     rax, rdx
0x18008948a  jz      short loc_1800894FD
0x18008948c  test    dword ptr [rax+44h], 100h
0x180089493  jz      short loc_1800894FD
0x180089495  cmp     byte ptr [rax+41h], 4
0x180089499  jb      short loc_1800894FD
0x18008949b  mov     rcx, [rbp+57h+var_B0]
0x18008949f  mov     rax, [rcx]
0x1800894a2  mov     rax, [rax+40h]
0x1800894a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894ab  mov     rdi, rax
0x1800894ae  mov     rcx, [rbp+57h+var_B0]
0x1800894b2  mov     rdx, [rcx]
0x1800894b5  mov     rax, [rdx+0A0h]
0x1800894bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894c1  mov     rbx, rax
0x1800894c4  mov     rcx, [rbp+57h+var_B0]
0x1800894c8  mov     rdx, [rcx]
0x1800894cb  mov     rax, [rdx+68h]
0x1800894cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894d4  mov     edx, 19h
0x1800894d9  mov     [rsp+0E0h+var_B8], rdi
0x1800894de  mov     [rsp+0E0h+var_C0], rbx
0x1800894e3  mov     r9, rax
0x1800894e6  lea     r8, WPP_622f59390c8534e9e167ba581245440f_Traceguids
0x1800894ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800894f4  mov     rcx, [rcx+38h]
0x1800894f8  call    WPP_SF_Sii
0x1800894fd  mov     rcx, [rbp+57h+var_B0]
0x180089501  mov     rax, [rcx]
0x180089504  mov     rax, [rax+80h]
0x18008950b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089510  mov     rcx, rax; unsigned __int16 *
0x180089513  call    ?HydratePlaceholderAsync@CCloudFileSystemAsyncHydrationManager@@SAJPEBG@Z; CCloudFileSystemAsyncHydrationManager::HydratePlaceholderAsync(ushort const *)
0x180089518  mov     [rbp+57h+var_A8], eax
0x18008951b  xor     esi, esi
0x18008951d  mov     [rbp+57h+var_A8], eax
0x180089520  test    eax, eax
0x180089522  mov     eax, 28Dh
0x180089527  js      loc_18008927A
0x18008952d  mov     word ptr [rbp+57h+var_A4], ax
0x180089531  jmp     loc_180089759
0x180089536  xor     esi, esi
0x180089538  mov     edi, 100h
0x18008953d  mov     rcx, [rbp+57h+var_B0]
0x180089541  mov     rax, [rcx]
0x180089544  mov     rax, [rax+0A8h]
0x18008954b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089550  cmp     eax, 2
0x180089553  jnz     loc_180089759
0x180089559  test    r12b, 20h
0x18008955d  jnz     loc_180089759
0x180089563  cmp     [rbp+57h+var_88], esi
0x180089566  jnz     short loc_1800895C6
0x180089568  mov     rax, cs:WPP_GLOBAL_Control
0x18008956f  lea     rdx, WPP_GLOBAL_Control
0x180089576  cmp     rax, rdx
0x180089579  jz      loc_180089759
0x18008957f  test    [rax+44h], edi
0x180089582  jz      loc_180089759
0x180089588  cmp     byte ptr [rax+41h], 4
0x18008958c  jb      loc_180089759
0x180089592  mov     rcx, [rbp+57h+var_B0]
0x180089596  mov     rax, [rcx]
0x180089599  mov     rax, [rax+68h]
0x18008959d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895a2  mov     edx, 1Ah
0x1800895a7  mov     r9, rax
0x1800895aa  lea     r8, WPP_622f59390c8534e9e167ba581245440f_Traceguids
0x1800895b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800895b8  mov     rcx, [rcx+38h]
0x1800895bc  call    WPP_SF_S
0x1800895c1  jmp     loc_180089759
0x1800895c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800895cd  lea     rcx, WPP_GLOBAL_Control
0x1800895d4  cmp     rax, rcx
0x1800895d7  jz      short loc_18008962E
0x1800895d9  test    [rax+44h], edi
0x1800895dc  jz      short loc_18008962E
0x1800895de  cmp     byte ptr [rax+41h], 4
0x1800895e2  jb      short loc_18008962E
0x1800895e4  mov     rcx, [rbp+57h+var_B0]
0x1800895e8  mov     rax, [rcx]
0x1800895eb  mov     rax, [rax+0A0h]
0x1800895f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895f7  mov     rbx, rax
0x1800895fa  mov     rcx, [rbp+57h+var_B0]
0x1800895fe  mov     rdx, [rcx]
0x180089601  mov     rax, [rdx+68h]
0x180089605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008960a  mov     edx, 1Bh
0x18008960f  mov     [rsp+0E0h+var_C0], rbx
0x180089614  mov     r9, rax
0x180089617  lea     r8, WPP_622f59390c8534e9e167ba581245440f_Traceguids
0x18008961e  mov     rcx, cs:WPP_GLOBAL_Control
0x180089625  mov     rcx, [rcx+38h]
0x180089629  call    WPP_SF_Si
0x18008962e  mov     rcx, [rbp+57h+var_B0]
0x180089632  mov     rax, [rcx]
0x180089635  mov     rax, [rax+80h]
0x18008963c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089641  mov     rcx, rax; unsigned __int16 *
0x180089644  call    ?DehydratePlaceholderAsync@CCloudFileSystemAsyncHydrationManager@@SAJPEBG@Z; CCloudFileSystemAsyncHydrationManager::DehydratePlaceholderAsync(ushort const *)
0x180089649  mov     edi, eax
0x18008964b  lea     rax, Format
0x180089652  mov     [rbp+57h+ppszExt], rax
0x180089656  mov     rcx, [rbp+57h+var_B0]
0x18008965a  mov     rdx, [rcx]
0x18008965d  mov     rax, [rdx+68h]
0x180089661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089666  mov     rdx, rax
0x180089669  lea     rcx, [rbp+57h+var_60]
0x18008966d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180089672  nop
0x180089673  mov     rcx, [rbp+57h+var_B0]
0x180089677  mov     rax, [rcx]
0x18008967a  mov     rax, [rax+68h]
  ... truncated ...
```
