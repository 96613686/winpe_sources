# LicenseManagerCore::RequestLicenseForContentWithId(ushort const *,Microsoft::WRL::ComPtr<RequestData> const &)

- ea: `0x180020480`
- end: `0x180020965`
- name: `?RequestLicenseForContentWithId@LicenseManagerCore@@AEBA?AV?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@PEBGAEBV?$ComPtr@VRequestData@@@34@@Z`
- size: `1253`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020340`
- `0x18005a670`

## callees

- `0x180004738`
- `0x18000b7fc`
- `0x18000c70c`
- `0x18001a6f4`
- `0x18001b53c`
- `0x180020480`
- `0x180020bc4`
- `0x18002aae8`
- `0x1800593bc`
- `0x180070320`
- `0x18009685c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!CoGetErrorInfo` at `0x18002079b`
- `api-ms-win-core-com-private-l1-1-0!CoGetErrorInfo` at `0x18002079b`
- `api-ms-win-core-com-private-l1-1-0!CoSetErrorInfo` at `0x1800207c9`
- `api-ms-win-core-com-private-l1-1-0!CoSetErrorInfo` at `0x1800207c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020733`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
LPVOID *__fastcall LicenseManagerCore::RequestLicenseForContentWithId(
        LicenseManagerCore *this,
        LPVOID *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64, LPVOID *); // rbx
  int v10; // eax
  int v11; // esi
  unsigned int v12; // edi
  int v13; // eax
  int v14; // eax
  unsigned int v15; // esi
  __int64 *v16; // r15
  __int64 v17; // rbx
  __int64 *v18; // rdx
  LPVOID v19; // rcx
  __int64 **i; // rsi
  __int64 **v21; // r15
  __int64 *v22; // rcx
  __int64 v23; // rax
  int (__fastcall ***v24)(_QWORD, GUID *, _QWORD); // rdi
  int (__fastcall *v25)(_QWORD, GUID *, _QWORD); // rbx
  void (__fastcall ***v26)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v27; // rcx
  int ErrorInfo; // eax
  int v29; // eax
  void (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v32; // rax
  LPVOID v33; // rbx
  __int64 v34; // rax
  int v36; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v38; // [rsp+38h] [rbp-48h] BYREF
  int v39[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 *v40; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v41; // [rsp+50h] [rbp-30h]
  int v42; // [rsp+58h] [rbp-28h]
  __int64 v43; // [rsp+60h] [rbp-20h] BYREF
  __int128 v44; // [rsp+68h] [rbp-18h] BYREF
  __int64 v45; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  int v47; // [rsp+C0h] [rbp+40h] BYREF
  LPVOID *v48; // [rsp+C8h] [rbp+48h]
  void (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // [rsp+D8h] [rbp+58h] BYREF

  v48 = a2;
  *a2 = 0;
  v42 = 1;
  v8 = *((_QWORD *)this + 22);
  v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64, LPVOID *))(*(_QWORD *)v8 + 32LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
  v10 = v9(v8, a3, (*a4 + 8LL) & -(__int64)(*a4 != 0), a2);
  v11 = v10;
  v12 = 0;
  v47 = 0;
  if ( v10 < 0 )
  {
    if ( v10 == -2143322104 )
      goto LABEL_60;
    v38 = 0;
    v49 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
    ErrorInfo = CoGetErrorInfo(0, &v49);
    if ( ErrorInfo < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6EC,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        (const char *)(unsigned int)ErrorInfo,
        v36);
    if ( v49 )
    {
      v29 = CoSetErrorInfo(0);
      if ( v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6F0,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          (const char *)(unsigned int)v29,
          v36);
      v30 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
      v31 = **v49;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
      v31(v30, &GUID_2082cf4e_067d_42a8_a528_43cfc302c067, &v38);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
    if ( v38 )
    {
      *(_QWORD *)v39 = 0;
      v32 = LicenseManagerCore::TryRemediateLicenseRequest(
              (_DWORD)this,
              (unsigned int)&v40,
              a3,
              (_DWORD)a4,
              (__int64)&v38);
      Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(v39, v32);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      v33 = *(LPVOID *)v39;
      if ( *(_QWORD *)v39 )
      {
        if ( *a2 != *(LPVOID *)v39 )
        {
          pv = *(LPVOID *)v39;
          Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&pv);
          pv = *a2;
          *a2 = v33;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&pv);
        }
        v11 = 0;
      }
      LODWORD(v49) = 0;
      if ( (*(int (__fastcall **)(__int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v38 + 40LL))(
             v38,
             &v49) >= 0
        && (_DWORD)v49 )
      {
        v40 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 **))(*(_QWORD *)(*a4 + 8LL) + 64LL))(*a4 + 8LL, &v40) >= 0 && v40 )
        {
          pv = 0;
          v34 = *v40;
          pv = 0;
          if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v34 + 24))(v40, &pv) >= 0 )
            LicenseManagerCore::DoRemoveKeyDocumentWithId(this, (const unsigned __int16 *)pv, v11);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v39);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    if ( v11 < 0 )
LABEL_60:
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x719,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        (const char *)(unsigned int)v11,
        v36);
  }
  else if ( (*(int (__fastcall **)(LPVOID, int *))(*(_QWORD *)*a2 + 40LL))(*a2, &v47) >= 0 && v47 )
  {
    v38 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*a4 + 8LL) + 64LL))(*a4 + 8LL, &v38) >= 0 && v38 )
    {
      v44 = 0;
      v45 = 0;
      v40 = 0;
      v41 = 0;
      LODWORD(v49) = 0;
      *(_QWORD *)v39 = 0;
      pv = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a4 + 24LL))(*a4, &pv);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6C5,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          (const char *)(unsigned int)v13,
          v36);
      v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, LPVOID, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)this + 23) + 88LL))(
              *((_QWORD *)this + 23),
              v38,
              pv,
              &v49);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x6C8,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          (const char *)(unsigned int)v14,
          (int)v39);
      v15 = (unsigned int)v49;
      v16 = *(__int64 **)v39;
      ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(&v40);
      v40 = v16;
      v41 = v15;
      if ( v15 )
      {
        do
        {
          v17 = v16[v12];
          v43 = v17;
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
          v18 = (__int64 *)*((_QWORD *)&v44 + 1);
          if ( *((_QWORD *)&v44 + 1) == v45 )
          {
            std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(
              &v44,
              *((_QWORD *)&v44 + 1),
              &v43);
            v17 = v43;
          }
          else
          {
            **((_QWORD **)&v44 + 1) = 0;
            if ( v18 != &v43 )
            {
              *v18 = v17;
              v17 = 0;
            }
            *((_QWORD *)&v44 + 1) += 8LL;
          }
          if ( v17 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          ++v12;
        }
        while ( v12 < v15 );
      }
      v19 = pv;
      if ( pv )
      {
        pv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v21 = (__int64 **)*((_QWORD *)&v44 + 1);
      for ( i = (__int64 **)v44; i != v21; ++i )
      {
        pv = 0;
        v22 = *i;
        v23 = **i;
        pv = 0;
        if ( (*(int (__fastcall **)(__int64 *, LPVOID *))(v23 + 24))(v22, &pv) >= 0 )
        {
          v49 = 0;
          v24 = (int (__fastcall ***)(_QWORD, GUID *, _QWORD))*((_QWORD *)this + 23);
          v25 = **v24;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
          if ( v25(v24, &GUID_793dd932_318d_449b_b9b0_4bd2dfa146d9, &v49) >= 0 )
            (*v49)[4](v49, (GUID *)pv, (__int64 *)2151649283LL);
          v26 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v49;
          if ( v49 )
          {
            v49 = 0;
            ((void (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v26)[2])(v26);
          }
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
      ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(&v40);
      std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::~vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(&v44);
    }
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180020480  mov     [rsp-38h+arg_10], rbx
0x180020485  mov     [rsp-38h+arg_8], rdx
0x18002048a  push    rbp
0x18002048b  push    rsi
0x18002048c  push    rdi
0x18002048d  push    r12
0x18002048f  push    r13
0x180020491  push    r14
0x180020493  push    r15
0x180020495  mov     rbp, rsp
0x180020498  sub     rsp, 80h
0x18002049f  mov     r15, r9
0x1800204a2  mov     r12, r8
0x1800204a5  mov     r14, rdx
0x1800204a8  mov     r13, rcx
0x1800204ab  mov     [rbp+var_28], 0
0x1800204b2  mov     qword ptr [rdx], 0
0x1800204b9  mov     [rbp+var_28], 1
0x1800204c0  mov     rdi, [rcx+0B0h]
0x1800204c7  mov     rax, [rdi]
0x1800204ca  mov     rbx, [rax+20h]
0x1800204ce  mov     rcx, rdx
0x1800204d1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800204d6  mov     rdx, [r15]
0x1800204d9  lea     r9, [rdx+8]
0x1800204dd  neg     rdx
0x1800204e0  sbb     r8, r8
0x1800204e3  and     r8, r9
0x1800204e6  mov     r9, r14
0x1800204e9  mov     rdx, r12
0x1800204ec  mov     rcx, rdi
0x1800204ef  mov     rax, rbx
0x1800204f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204f7  mov     esi, eax
0x1800204f9  xor     edi, edi
0x1800204fb  mov     [rbp+arg_0], edi
0x1800204fe  test    eax, eax
0x180020500  js      loc_180020779
0x180020506  mov     rcx, [r14]
0x180020509  mov     rax, [rcx]
0x18002050c  lea     rdx, [rbp+arg_0]
0x180020510  mov     rax, [rax+28h]
0x180020514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020519  test    eax, eax
0x18002051b  js      loc_18002092E
0x180020521  cmp     [rbp+arg_0], edi
0x180020524  jz      loc_18002092E
0x18002052a  mov     [rbp+var_48], rdi
0x18002052e  mov     rcx, [r15]
0x180020531  add     rcx, 8
0x180020535  mov     rax, [rcx]
0x180020538  lea     rdx, [rbp+var_48]
0x18002053c  mov     rax, [rax+40h]
0x180020540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020545  test    eax, eax
0x180020547  js      loc_18002075A
0x18002054d  cmp     [rbp+var_48], rdi
0x180020551  jz      loc_18002075A
0x180020557  xorps   xmm0, xmm0
0x18002055a  movdqu  [rbp+var_18], xmm0
0x18002055f  mov     [rbp+var_8], rdi
0x180020563  mov     [rbp+var_38], rdi
0x180020567  mov     [rbp+var_30], edi
0x18002056a  mov     dword ptr [rbp+arg_18], edi
0x18002056d  mov     qword ptr [rbp+var_40], rdi
0x180020571  mov     [rbp+pv], rdi
0x180020575  mov     rcx, [r15]
0x180020578  mov     rax, [rcx]
0x18002057b  lea     rdx, [rbp+pv]
0x18002057f  mov     rax, [rax+18h]
0x180020583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020588  mov     rcx, [rbp+38h]; this
0x18002058c  test    eax, eax
0x18002058e  jns     short loc_1800205A5
0x180020590  mov     r9d, eax; char *
0x180020593  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18002059a  mov     edx, 6C5h; void *
0x18002059f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800205a5  mov     rcx, [r13+0B8h]
0x1800205ac  mov     rax, [rcx]
0x1800205af  lea     rdx, [rbp+var_40]
0x1800205b3  mov     qword ptr [rsp+80h+var_60], rdx; int
0x1800205b8  lea     r9, [rbp+arg_18]
0x1800205bc  mov     r8, [rbp+pv]
0x1800205c0  mov     rdx, [rbp+var_48]
0x1800205c4  mov     rax, [rax+58h]
0x1800205c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205cd  mov     rcx, [rbp+38h]; this
0x1800205d1  test    eax, eax
0x1800205d3  jns     short loc_1800205EA
0x1800205d5  mov     r9d, eax; char *
0x1800205d8  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800205df  mov     edx, 6C8h; void *
0x1800205e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800205ea  mov     esi, dword ptr [rbp+arg_18]
0x1800205ed  mov     r15, qword ptr [rbp+var_40]
0x1800205f1  lea     rcx, [rbp+var_38]
0x1800205f5  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLeaseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(void)
0x1800205fa  mov     [rbp+var_38], r15
0x1800205fe  mov     [rbp+var_30], esi
0x180020601  test    esi, esi
0x180020603  jz      short loc_180020676
0x180020605  mov     eax, edi
0x180020607  mov     rbx, [r15+rax*8]
0x18002060b  mov     [rbp+var_20], rbx
0x18002060f  test    rbx, rbx
0x180020612  jz      short loc_180020624
0x180020614  mov     rax, [rbx]
0x180020617  mov     rcx, rbx
0x18002061a  mov     rax, [rax+8]
0x18002061e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020623  nop
0x180020624  mov     rdx, qword ptr [rbp+var_18+8]
0x180020628  cmp     rdx, [rbp+var_8]
0x18002062c  jz      short loc_18002064A
0x18002062e  mov     qword ptr [rdx], 0
0x180020635  lea     rax, [rbp+var_20]
0x180020639  cmp     rdx, rax
0x18002063c  jz      short loc_180020643
0x18002063e  mov     [rdx], rbx
0x180020641  xor     ebx, ebx
0x180020643  add     qword ptr [rbp+var_18+8], 8
0x180020648  jmp     short loc_18002065B
0x18002064a  lea     r8, [rbp+var_20]
0x18002064e  lea     rcx, [rbp+var_18]
0x180020652  call    ??$_Emplace_reallocate@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@QEAV234@$$QEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(Microsoft::WRL::ComPtr<IStoredLeaseDocument> * const,Microsoft::WRL::ComPtr<IStoredLeaseDocument> &&)
0x180020657  mov     rbx, [rbp+var_20]
0x18002065b  test    rbx, rbx
0x18002065e  jz      short loc_180020670
0x180020660  mov     rax, [rbx]
0x180020663  mov     rcx, rbx
0x180020666  mov     rax, [rax+10h]
0x18002066a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002066f  nop
0x180020670  inc     edi
0x180020672  cmp     edi, esi
0x180020674  jb      short loc_180020605
0x180020676  mov     rcx, [rbp+pv]
0x18002067a  xor     edi, edi
0x18002067c  test    rcx, rcx
0x18002067f  jz      short loc_180020692
0x180020681  mov     [rbp+pv], rdi
0x180020685  mov     rax, [rcx]
0x180020688  mov     rax, [rax+10h]
0x18002068c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020691  nop
0x180020692  mov     rsi, qword ptr [rbp+var_18]
0x180020696  mov     r15, qword ptr [rbp+var_18+8]
0x18002069a  jmp     loc_18002073D
0x18002069f  mov     [rbp+pv], rdi
0x1800206a3  mov     rcx, [rsi]
0x1800206a6  mov     rax, [rcx]
0x1800206a9  mov     [rbp+pv], rdi
0x1800206ad  lea     rdx, [rbp+pv]
0x1800206b1  mov     rax, [rax+18h]
0x1800206b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206ba  test    eax, eax
0x1800206bc  js      short loc_18002072A
0x1800206be  mov     [rbp+arg_18], rdi
0x1800206c2  mov     rdi, [r13+0B8h]
0x1800206c9  mov     rax, [rdi]
0x1800206cc  mov     rbx, [rax]
0x1800206cf  lea     rcx, [rbp+arg_18]
0x1800206d3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800206d8  lea     r8, [rbp+arg_18]
0x1800206dc  lea     rdx, _GUID_793dd932_318d_449b_b9b0_4bd2dfa146d9
0x1800206e3  mov     rcx, rdi
0x1800206e6  mov     rax, rbx
0x1800206e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206ee  nop
0x1800206ef  xor     edi, edi
0x1800206f1  test    eax, eax
0x1800206f3  js      short loc_180020710
0x1800206f5  mov     rcx, [rbp+arg_18]
0x1800206f9  mov     rax, [rcx]
0x1800206fc  mov     r8d, 803F9003h
0x180020702  mov     rdx, [rbp+pv]
0x180020706  mov     rax, [rax+20h]
0x18002070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002070f  nop
0x180020710  mov     rcx, [rbp+arg_18]
0x180020714  test    rcx, rcx
0x180020717  jz      short loc_18002072A
0x180020719  mov     [rbp+arg_18], rdi
0x18002071d  mov     rax, [rcx]
0x180020720  mov     rax, [rax+10h]
0x180020724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020729  nop
0x18002072a  mov     rcx, [rbp+pv]; pv
0x18002072e  test    rcx, rcx
0x180020731  jz      short loc_180020739
0x180020733  call    cs:__imp_CoTaskMemFree
0x180020739  add     rsi, 8
0x18002073d  cmp     rsi, r15
0x180020740  jnz     loc_18002069F
0x180020746  lea     rcx, [rbp+var_38]
0x18002074a  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLeaseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLeaseDocument>>::_free(void)
0x18002074f  nop
0x180020750  lea     rcx, [rbp+var_18]
0x180020754  call    ??1?$vector@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>::~vector<Microsoft::WRL::ComPtr<IStoredLeaseDocument>>(void)
0x180020759  nop
0x18002075a  mov     rcx, [rbp+var_48]
0x18002075e  test    rcx, rcx
0x180020761  jz      short loc_180020774
0x180020763  mov     [rbp+var_48], rdi
0x180020767  mov     rax, [rcx]
0x18002076a  mov     rax, [rax+10h]
0x18002076e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020773  nop
0x180020774  jmp     loc_18002092E
0x180020779  cmp     eax, 803F8008h
0x18002077e  jz      loc_18002094C
0x180020784  mov     [rbp+var_48], rdi
0x180020788  mov     [rbp+arg_18], rdi
0x18002078c  lea     rcx, [rbp+arg_18]
0x180020790  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020795  lea     rdx, [rbp+arg_18]
0x180020799  xor     ecx, ecx
0x18002079b  call    cs:__imp_CoGetErrorInfo
0x1800207a1  mov     rcx, [rbp+38h]; this
0x1800207a5  test    eax, eax
0x1800207a7  jns     short loc_1800207BE
0x1800207a9  mov     r9d, eax; char *
0x1800207ac  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800207b3  mov     edx, 6ECh; void *
0x1800207b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800207be  mov     rdx, [rbp+arg_18]
0x1800207c2  test    rdx, rdx
0x1800207c5  jz      short loc_180020818
0x1800207c7  xor     ecx, ecx
0x1800207c9  call    cs:__imp_CoSetErrorInfo
0x1800207cf  mov     rcx, [rbp+38h]; this
0x1800207d3  test    eax, eax
0x1800207d5  jns     short loc_1800207EC
0x1800207d7  mov     r9d, eax; char *
0x1800207da  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800207e1  mov     edx, 6F0h; void *
0x1800207e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800207ec  mov     rbx, [rbp+arg_18]
0x1800207f0  mov     rax, [rbx]
0x1800207f3  mov     rdi, [rax]
0x1800207f6  lea     rcx, [rbp+var_48]
0x1800207fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800207ff  lea     r8, [rbp+var_48]
0x180020803  lea     rdx, _GUID_2082cf4e_067d_42a8_a528_43cfc302c067
0x18002080a  mov     rcx, rbx
0x18002080d  mov     rax, rdi
0x180020810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020815  nop
0x180020816  xor     edi, edi
0x180020818  lea     rcx, [rbp+arg_18]
0x18002081c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180020821  cmp     [rbp+var_48], rdi
0x180020825  jz      loc_180020921
0x18002082b  mov     qword ptr [rbp+var_40], rdi
0x18002082f  lea     rax, [rbp+var_48]
0x180020833  mov     qword ptr [rsp+80h+var_60], rax
0x180020838  mov     r9, r15
0x18002083b  mov     r8, r12
0x18002083e  lea     rdx, [rbp+var_38]
0x180020842  mov     rcx, r13
0x180020845  call    ?TryRemediateLicenseRequest@LicenseManagerCore@@AEBA?AV?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@PEBGAEBV?$ComPtr@VRequestData@@@34@AEBV?$ComPtr@UILicenseRemediationInfo@@@34@@Z; LicenseManagerCore::TryRemediateLicenseRequest(ushort const *,Microsoft::WRL::ComPtr<RequestData> const &,Microsoft::WRL::ComPtr<ILicenseRemediationInfo> const &)
0x18002084a  mov     rdx, rax
0x18002084d  lea     rcx, [rbp+var_40]
0x180020851  call    ??4?$ComPtr@UILicenseResponseData@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<ILicenseResponseData>::operator=(Microsoft::WRL::ComPtr<ILicenseResponseData> &&)
0x180020856  lea     rcx, [rbp+var_38]
0x18002085a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002085f  mov     rbx, qword ptr [rbp+var_40]
0x180020863  test    rbx, rbx
0x180020866  jz      short loc_18002088F
0x180020868  cmp     [r14], rbx
0x18002086b  jz      short loc_18002088D
0x18002086d  mov     [rbp+pv], rbx
0x180020871  lea     rcx, [rbp+pv]
0x180020875  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18002087a  mov     rax, [r14]
0x18002087d  mov     [rbp+pv], rax
0x180020881  mov     [r14], rbx
0x180020884  lea     rcx, [rbp+pv]
0x180020888  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002088d  mov     esi, edi
0x18002088f  mov     dword ptr [rbp+arg_18], edi
0x180020892  mov     rcx, [rbp+var_48]
0x180020896  mov     rax, [rcx]
0x180020899  lea     rdx, [rbp+arg_18]
0x18002089d  mov     rax, [rax+28h]
0x1800208a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a6  test    eax, eax
0x1800208a8  js      short loc_180020917
0x1800208aa  cmp     dword ptr [rbp+arg_18], edi
0x1800208ad  jz      short loc_180020917
0x1800208af  mov     [rbp+var_38], rdi
0x1800208b3  mov     rcx, [r15]
0x1800208b6  add     rcx, 8
0x1800208ba  mov     rax, [rcx]
0x1800208bd  lea     rdx, [rbp+var_38]
0x1800208c1  mov     rax, [rax+40h]
0x1800208c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ca  test    eax, eax
0x1800208cc  js      short loc_18002090D
  ... truncated ...
```
