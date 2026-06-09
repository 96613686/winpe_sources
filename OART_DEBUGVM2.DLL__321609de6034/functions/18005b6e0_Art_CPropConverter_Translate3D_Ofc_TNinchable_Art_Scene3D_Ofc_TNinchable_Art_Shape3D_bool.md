# Art::CPropConverter::Translate3D(Ofc::TNinchable<Art::Scene3D> &,Ofc::TNinchable<Art::Shape3D> &,bool &)

- ea: `0x18005b6e0`
- end: `0x18005c1b0`
- name: `?Translate3D@CPropConverter@Art@@MEBAXAEAV?$TNinchable@VScene3D@Art@@@Ofc@@AEAV?$TNinchable@VShape3D@Art@@@4@AEA_N@Z`
- size: `2768`
- prototype: `__int64 __fastcall(Art::CPropConverter *this)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000eb20`
- `0x18002a690`
- `0x18002a750`
- `0x18002abf0`
- `0x18002ee10`
- `0x1800346a4`
- `0x1800360b0`
- `0x180059a90`
- `0x18005ae40`
- `0x18005b6e0`
- `0x18006f9a4`
- `0x1800d6a90`
- `0x1801ed570`
- `0x180210de4`
- `0x180215670`
- `0x1802769e0`
- `0x180276a71`
- `0x180279030`
- `0x180279050`
- `0x1806a7bb4`
- `0x1806d8214`
- `0x1806d8278`
- `0x1806d82fc`
- `0x1806d9f00`
- `0x1806dbbf8`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18005b945`
- `KERNEL32!DecodePointer` at `0x18005b957`
- `KERNEL32!DecodePointer` at `0x18005ba09`
- `KERNEL32!DecodePointer` at `0x18005ba1b`
- `KERNEL32!DecodePointer` at `0x18005bef4`
- `KERNEL32!DecodePointer` at `0x18005bf06`
- `KERNEL32!DecodePointer` at `0x18005b945`
- `KERNEL32!DecodePointer` at `0x18005b957`
- `KERNEL32!DecodePointer` at `0x18005ba09`
- `KERNEL32!DecodePointer` at `0x18005ba1b`
- `KERNEL32!DecodePointer` at `0x18005bef4`
- `KERNEL32!DecodePointer` at `0x18005bf06`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x18005b74b`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x18005b7b8`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x18005b74b`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x18005b7b8`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18005b795`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18005b7fd`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18005b795`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18005b7fd`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x18005b814`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x18005b82d`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x18005b814`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x18005b82d`

## pseudocode

```c
void __fastcall Art::CPropConverter::Translate3D(Art::CPropConverter *this, void (*a2)(void), __int64 a3, bool *a4)
{
  bool *v4; // r14
  __int64 v6; // rsi
  struct MSOSP *v8; // rbx
  struct IMsoDrawing *v9; // rax
  struct MSOSP *v10; // rbx
  struct IMsoDrawing *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 (__fastcall *v18)(__int64); // rax
  _QWORD *v19; // rax
  void (*v20)(void); // rdx
  bool v21; // r8
  __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned int v24; // r8d
  __int64 (__fastcall *v25)(__int64); // rax
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  int v32; // ecx
  __int64 v33; // rax
  unsigned int *v34; // r14
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // eax
  unsigned int v39; // esi
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  unsigned int v43; // eax
  unsigned int v44; // edi
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  unsigned int v48; // eax
  unsigned int v49; // ebx
  int v50; // edx
  int v51; // ecx
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // rdx
  __int64 *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdi
  __int64 v59; // rbx
  int v60; // eax
  int v61; // ecx
  int v62; // eax
  void (*v63)(void); // rdx
  bool v64; // r8
  __int64 v65; // rcx
  unsigned __int64 v66; // rdx
  unsigned int v67; // r8d
  __int64 (__fastcall *v68)(__int64); // rax
  _QWORD *v69; // rax
  __int64 Storage; // rdi
  __int64 v71; // rdi
  unsigned __int64 v72; // rbx
  unsigned __int64 v73; // rdx
  __int64 *v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rdx
  __int64 v77; // rdx
  __int64 v78; // rdx
  __int64 v79; // rcx
  char v80[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v81; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v82; // [rsp+40h] [rbp-C0h] BYREF
  int v83; // [rsp+48h] [rbp-B8h]
  bool *v84; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v85; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+60h] [rbp-A0h]
  __int64 v87; // [rsp+68h] [rbp-98h]
  __int64 v88; // [rsp+70h] [rbp-90h] BYREF
  __int64 v89; // [rsp+78h] [rbp-88h]
  __int64 v90; // [rsp+80h] [rbp-80h]
  int v91; // [rsp+88h] [rbp-78h] BYREF
  int v92; // [rsp+8Ch] [rbp-74h]
  int v93; // [rsp+90h] [rbp-70h]
  int v94; // [rsp+94h] [rbp-6Ch]
  int v95; // [rsp+98h] [rbp-68h]
  int v96; // [rsp+9Ch] [rbp-64h]
  int v97; // [rsp+A0h] [rbp-60h]
  int v98; // [rsp+A4h] [rbp-5Ch]
  int v99; // [rsp+A8h] [rbp-58h]
  int v100; // [rsp+ACh] [rbp-54h]
  int v101; // [rsp+B0h] [rbp-50h]
  _BYTE v102[256]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v103[256]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v104[272]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v105[272]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v4 = a4;
  v84 = a4;
  v6 = (__int64)a2;
  v81 = (__int64)a2;
  v8 = (struct MSOSP *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    memset_0(v105, 0, 0x108u);
    v9 = MsoPidgFromHsp(v8);
    (*(void (__fastcall **)(struct IMsoDrawing *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v9 + 680LL))(
      v9,
      v8,
      11,
      v105);
    memset_0(v104, 0, 0x108u);
    MsoGetPropSetNinch(11);
    memset_0(v103, 0, 0xF8u);
    v10 = (struct MSOSP *)*((_QWORD *)this + 1);
    v11 = MsoPidgFromHsp(v10);
    (*(void (__fastcall **)(struct IMsoDrawing *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v11 + 680LL))(
      v11,
      v10,
      10,
      v103);
    memset_0(v102, 0, 0xF8u);
    MsoGetPropSetNinch(10);
    if ( (unsigned int)MsoFIsPropSetEqual(11, v105, v104) )
    {
      if ( (unsigned int)MsoFIsPropSetEqual(10, v103, v102) )
      {
        *(_BYTE *)(v6 + 80) = 1;
        *(_BYTE *)(a3 + 80) = 1;
        *v4 = 0;
        return;
      }
    }
  }
  v12 = *((_QWORD *)this + 187);
  *v4 = v12 != 0;
  if ( !v12 )
  {
    if ( (unsigned __int8)sub_1806A7BB4(*((_QWORD *)this + 1)) )
    {
      *(_BYTE *)(v6 + 80) = 2;
      LOBYTE(v13) = 2;
      Ofc::ThrowIfInvalidQualifiedValueState(v13);
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 32, 0);
      *(_DWORD *)(v6 + 8) = 18;
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 48) = 13;
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 52) = 1;
      *(_BYTE *)(a3 + 80) = 2;
      LOBYTE(v14) = 2;
      Ofc::ThrowIfInvalidQualifiedValueState(v14);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      *(_DWORD *)(a3 + 64) = 5;
      *v4 = 1;
    }
    return;
  }
  v15 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
  {
    while ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
    {
      if ( _InterlockedCompareExchange64(&Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance, 1, 0) )
      {
        v82 = 0;
        std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v82);
      }
      else
      {
        LOBYTE(a2) = 1;
        Ofc::AtExit(Ofc::TSingleton<Art::CPropConverterHelper>::Shutdown, a2, a3);
        if ( DecodePointer(Ptr) )
        {
          v18 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
          v19 = (_QWORD *)v18(8);
        }
        else
        {
          v19 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v16, v17);
        }
        *v19 = &Art::CPropConverterHelper::`vftable';
        _InterlockedCompareExchange64(&Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance, (signed __int64)v19, 1);
      }
    }
    v15 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
    v6 = v81;
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, char *))(*(_QWORD *)v15 + 144LL))(v15, (char *)this + 2176) )
  {
    v22 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
    if ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
    {
      while ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
      {
        if ( _InterlockedCompareExchange64(&Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance, 1, 0) )
        {
          v82 = 0;
          std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v82);
        }
        else
        {
          LOBYTE(v20) = 1;
          Ofc::AtExit(Ofc::TSingleton<Art::CPropConverterHelper>::Shutdown, v20, v21);
          if ( DecodePointer(Ptr) )
          {
            v25 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
            v26 = (_QWORD *)v25(8);
          }
          else
          {
            v26 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v23, v24);
          }
          *v26 = &Art::CPropConverterHelper::`vftable';
          _InterlockedCompareExchange64(
            &Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance,
            (signed __int64)v26,
            1);
        }
      }
      v22 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
      v4 = v84;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 152LL))(v22, (char *)this + 2176)
      && (*((_QWORD *)this + 91) || *((_QWORD *)this + 45))
      && *((_QWORD *)this + 232) )
    {
      *(_BYTE *)(v6 + 80) = 2;
      *(_BYTE *)(a3 + 80) = 2;
      LOBYTE(v27) = *(_BYTE *)(v6 + 80);
      Ofc::ThrowIfInvalidQualifiedValueState(v27);
      LOBYTE(v28) = *(_BYTE *)(a3 + 80);
      Ofc::ThrowIfInvalidQualifiedValueState(v28);
      v91 = *((_DWORD *)this + 276);
      v92 = *((_DWORD *)this + 278);
      v93 = *((_DWORD *)this + 280);
      v94 = *((_QWORD *)this + 157) != 0;
      v95 = *((_DWORD *)this + 282);
      v96 = *((_DWORD *)this + 284);
      v97 = *((_DWORD *)this + 286);
      v98 = *((_DWORD *)this + 288);
      LODWORD(v82) = 0;
      Art::PerformConditionalPropMatch<Art::O11CameraSettings,enum Art::PresetCameraType>(
        v30,
        v29,
        (unsigned int)&v91,
        (unsigned int)&v82,
        (__int64)v80);
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 32, 0);
      *(_DWORD *)(v6 + 8) = v82;
      v33 = *((_QWORD *)this + 128);
      if ( v33 || *((_QWORD *)this + 127) )
      {
        v82 = 0;
        v83 = 0;
        Gfx::SphereCoords::SetEulerRotation(
          (Gfx::SphereCoords *)&v82,
          (double)-(int)v33 * 0.0000002663161090079238,
          (double)(int)*((_QWORD *)this + 127) * 0.0000002663161090079238);
        Ofc::TCntPtr<IACStorage>::operator=(v6 + 32, 0);
        v34 = (unsigned int *)Ofc::TOptional<Art::SphereCoords>::EnsureStorage(v6);
        Ofc::Round<int,double>(v36, v35, v37);
        v39 = v38;
        Ofc::TRangeRestricted<Art::Angle,Art::PosFixedAngleRange>::Validate(v38);
        Ofc::Round<int,double>(v41, v40, v42);
        v44 = v43;
        Ofc::TRangeRestricted<Art::Angle,Art::PosFixedAngleRange>::Validate(v43);
        Ofc::Round<int,double>(v46, v45, v47);
        v49 = v48;
        Ofc::TRangeRestricted<Art::Angle,Art::PosFixedAngleRange>::Validate(v48);
        *v34 = v49;
        v34[1] = v44;
        v34[2] = v39;
        v6 = v81;
        v4 = v84;
      }
      v91 = *((_DWORD *)this + 290);
      v92 = *((_QWORD *)this + 158) != 0;
      v93 = *((_DWORD *)this + 298);
      v94 = *((_QWORD *)this + 159) != 0;
      v95 = *((_DWORD *)this + 306);
      v96 = *((_DWORD *)this + 292);
      v97 = *((_DWORD *)this + 294);
      v98 = *((_DWORD *)this + 296);
      v99 = *((_DWORD *)this + 300);
      v100 = *((_DWORD *)this + 302);
      v101 = *((_DWORD *)this + 304);
      v82 = 0x400000000LL;
      Art::PerformConditionalPropMatch<Art::O11LightRigSettings,Art::O12LightRigSettings>(
        v32,
        v31,
        (unsigned int)&v91,
        (unsigned int)&v82,
        (__int64)v80);
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 48) = v82;
      Ofc::TCntPtr<IACStorage>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 52) = HIDWORD(v82);
      v91 = *((_DWORD *)this + 320);
      v92 = *((_DWORD *)this + 322);
      v93 = *((_QWORD *)this + 188) != 0;
      v94 = *((_DWORD *)this + 324);
      v95 = *((_DWORD *)this + 272);
      LODWORD(v82) = 0;
      Art::PerformConditionalPropMatch<Art::O11MaterialSettings,enum Art::PresetMaterialType>(
        v51,
        v50,
        (unsigned int)&v91,
        (unsigned int)&v82,
        (__int64)v80);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      *(_DWORD *)(a3 + 64) = v82;
      v52 = *((unsigned int *)this + 334);
      Art::Color::Color((Art::Color *)&v88, 0xFFFFFFu);
      if ( (v52 & 0x39000000) == 0x10000000 && (_BYTE)v52 == 0xF7 )
      {
        if ( *((_QWORD *)this + 45) )
        {
          v53 = *((unsigned int *)this + 8);
        }
        else
        {
          if ( !*((_QWORD *)this + 91) )
            goto LABEL_43;
          v53 = *((unsigned int *)this + 100);
        }
      }
      else
      {
        v53 = v52;
      }
      Art::CPropConverter::ResolveLegacyColor(this, v53, (struct Art::Color *)&v88);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      v54 = (__int64 *)Ofc::TOptional<Art::ColorEmbed>::EnsureStorage(a3 + 16);
      v55 = *v54;
      *v54 = v88;
      v88 = v55;
      v56 = v54[1];
      v54[1] = v89;
      v89 = v56;
      v57 = v54[2];
      v54[2] = v90;
      v90 = v57;
LABEL_43:
      v58 = *((_QWORD *)this + 165);
      v59 = *((_QWORD *)this + 164);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      if ( v59 >= v58 )
        v59 = v58;
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::operator=(a3 + 40, v59);
      v60 = -(*((_DWORD *)this + 328) + *((_DWORD *)this + 330));
      if ( *((_DWORD *)this + 328) + *((_DWORD *)this + 330) > 0 )
        v60 = *((_DWORD *)this + 328) + *((_DWORD *)this + 330);
      v61 = v60 - 27000;
      v62 = 0;
      if ( v61 >= 0 )
        v62 = v61;
      v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(v62);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
        &v82,
        &v81);
      *(_QWORD *)(a3 + 48) = v82;
      v65 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
      if ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
      {
        while ( (unsigned __int64)Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance <= 1 )
        {
          if ( _InterlockedCompareExchange64(&Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance, 1, 0) )
          {
            v81 = 0;
            std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v81);
          }
          else
          {
            LOBYTE(v63) = 1;
            Ofc::AtExit(Ofc::TSingleton<Art::CPropConverterHelper>::Shutdown, v63, v64);
            if ( DecodePointer(Ptr) )
            {
              v68 = (__int64 (__fastcall *)(__int64))DecodePointer(Ptr);
              v69 = (_QWORD *)v68(8);
            }
            else
            {
              v69 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v66, v67);
            }
            *v69 = &Art::CPropConverterHelper::`vftable';
            _InterlockedCompareExchange64(
              &Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance,
              (signed __int64)v69,
              1);
          }
        }
        v65 = Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance;
        v4 = v84;
      }
      if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v65 + 192LL))(v65, *((_QWORD *)this + 237)) )
      {
        Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
        Storage = Ofc::TOptional<Art::Bevel>::CreateStorage(a3);
        Ofc::TCntPtr<IACStorage>::operator=(Storage + 24, 0);
        *(_DWORD *)(Storage + 16) = 4;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<IACStorage>::operator=(Storage + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)Storage = v84;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<IACStorage>::operator=(Storage + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)(Storage + 8) = v84;
        Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
        v71 = Ofc::TOptional<Art::Bevel>::CreateStorage(a3 + 8);
        Ofc::TCntPtr<IACStorage>::operator=(v71 + 24, 0);
        *(_DWORD *)(v71 + 16) = 4;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<IACStorage>::operator=(v71 + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)v71 = v84;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<IACStorage>::operator=(v71 + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)(v71 + 8) = v84;
      }
      v72 = *((unsigned int *)this + 350);
      Art::Color::Color((Art::Color *)&v85, 0xFFFFFFu);
      if ( (v72 & 0x39000000) == 0x10000000 && (_BYTE)v72 == 0xF7 )
      {
        if ( *((_QWORD *)this + 45) )
        {
          v73 = *((unsigned int *)this + 8);
        }
        else
        {
          if ( !*((_QWORD *)this + 91) )
          {
LABEL_68:
            v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*((_QWORD *)this + 174));
            Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
            Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
              &v84,
              &v81);
            *(_QWORD *)(a3 + 56) = v84;
            v79 = *((_QWORD *)this + 413);
            if ( v79 )
            {
              LOBYTE(v78) = *((_BYTE *)this + 3266);
              (*(void (__fastcall **)(__int64, __int64, __int64, __int64, bool *))(*(_QWORD *)v79 + 32LL))(
                v79,
                v78,
                v6,
                a3,
                v4);
            }
            Art::Color::~Color((Art::Color *)&v85);
            Art::Color::~Color((Art::Color *)&v88);
            return;
          }
          v73 = *((unsigned int *)this + 100);
        }
      }
      else
      {
        v73 = v72;
      }
      Art::CPropConverter::ResolveLegacyColor(this, v73, (struct Art::Color *)&v85);
      Ofc::TCntPtr<IACStorage>::operator=(a3 + 72, 0);
      v74 = (__int64 *)Ofc::TOptional<Art::ColorEmbed>::EnsureStorage(a3 + 24);
      v75 = *v74;
      *v74 = v85;
      v85 = v75;
      v76 = v74[1];
      v74[1] = v86;
      v86 = v76;
      v77 = v74[2];
      v74[2] = v87;
      v87 = v77;
      goto LABEL_68;
    }
  }
}

```

## disassembly

```asm
0x18005b6e0  push    rbp
0x18005b6e2  push    rbx
0x18005b6e3  push    rsi
0x18005b6e4  push    rdi
0x18005b6e5  push    r12
0x18005b6e7  push    r13
0x18005b6e9  push    r14
0x18005b6eb  push    r15
0x18005b6ed  lea     rbp, [rsp-3F8h]
0x18005b6f5  sub     rsp, 4F8h
0x18005b6fc  mov     rax, cs:__security_cookie
0x18005b703  xor     rax, rsp
0x18005b706  mov     [rbp+430h+var_50], rax
0x18005b70d  mov     r14, r9
0x18005b710  mov     [rsp+530h+var_4E0], r9
0x18005b715  mov     r13, r8
0x18005b718  mov     rsi, rdx
0x18005b71b  mov     [rsp+530h+var_4F8], rdx
0x18005b720  mov     r15, rcx
0x18005b723  mov     rbx, [rcx+8]
0x18005b727  xor     edi, edi
0x18005b729  test    rbx, rbx
0x18005b72c  jz      loc_18005B869
0x18005b732  mov     edi, 108h
0x18005b737  mov     r8d, edi; Size
0x18005b73a  xor     edx, edx; Val
0x18005b73c  lea     rcx, [rbp+430h+var_160]; void *
0x18005b743  call    memset_0
0x18005b748  mov     rcx, rbx
0x18005b74b  call    cs:__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z; MsoPidgFromHsp(MSOSP *)
0x18005b751  mov     r10, rax
0x18005b754  mov     rcx, [rax]
0x18005b757  mov     rax, [rcx+2A8h]
0x18005b75e  lea     r9, [rbp+430h+var_160]
0x18005b765  mov     r12d, 0Bh
0x18005b76b  mov     r8d, r12d
0x18005b76e  mov     rdx, rbx
0x18005b771  mov     rcx, r10
0x18005b774  call    cs:__guard_dispatch_icall_fptr
0x18005b77a  mov     r8d, edi; Size
0x18005b77d  xor     edx, edx; Val
0x18005b77f  lea     rcx, [rbp+430h+var_270]; void *
0x18005b786  call    memset_0
0x18005b78b  lea     rdx, [rbp+430h+var_270]
0x18005b792  mov     ecx, r12d
0x18005b795  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x18005b79b  mov     edi, 0F8h
0x18005b7a0  mov     r8d, edi; Size
0x18005b7a3  xor     edx, edx; Val
0x18005b7a5  lea     rcx, [rbp+430h+var_370]; void *
0x18005b7ac  call    memset_0
0x18005b7b1  mov     rbx, [r15+8]
0x18005b7b5  mov     rcx, rbx
0x18005b7b8  call    cs:__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z; MsoPidgFromHsp(MSOSP *)
0x18005b7be  mov     r10, rax
0x18005b7c1  mov     rcx, [rax]
0x18005b7c4  mov     rax, [rcx+2A8h]
0x18005b7cb  lea     r9, [rbp+430h+var_370]
0x18005b7d2  lea     r8d, [r12-1]
0x18005b7d7  mov     rdx, rbx
0x18005b7da  mov     rcx, r10
0x18005b7dd  call    cs:__guard_dispatch_icall_fptr
0x18005b7e3  nop
0x18005b7e4  mov     r8d, edi; Size
0x18005b7e7  xor     edx, edx; Val
0x18005b7e9  lea     rcx, [rbp+430h+var_470]; void *
0x18005b7ed  call    memset_0
0x18005b7f2  lea     rdx, [rbp+430h+var_470]
0x18005b7f6  lea     ebx, [r12-1]
0x18005b7fb  mov     ecx, ebx
0x18005b7fd  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x18005b803  lea     r8, [rbp+430h+var_270]
0x18005b80a  lea     rdx, [rbp+430h+var_160]
0x18005b811  mov     ecx, r12d
0x18005b814  call    cs:__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z; MsoFIsPropSetEqual(MSOPSID,void const *,void const *)
0x18005b81a  xor     edi, edi
0x18005b81c  test    eax, eax
0x18005b81e  jz      short loc_18005B869
0x18005b820  lea     r8, [rbp+430h+var_470]
0x18005b824  lea     rdx, [rbp+430h+var_370]
0x18005b82b  mov     ecx, ebx
0x18005b82d  call    cs:__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z; MsoFIsPropSetEqual(MSOPSID,void const *,void const *)
0x18005b833  test    eax, eax
0x18005b835  jz      short loc_18005B869
0x18005b837  lea     r12d, [rbx-9]
0x18005b83b  mov     [rsi+50h], r12b
0x18005b83f  mov     [r13+50h], r12b
0x18005b843  mov     [r14], dil
0x18005b846  mov     rcx, [rbp+430h+var_50]
0x18005b84d  xor     rcx, rsp; StackCookie
0x18005b850  call    __security_check_cookie
0x18005b855  add     rsp, 4F8h
0x18005b85c  pop     r15
0x18005b85e  pop     r14
0x18005b860  pop     r13
0x18005b862  pop     r12
0x18005b864  pop     rdi
0x18005b865  pop     rsi
0x18005b866  pop     rbx
0x18005b867  pop     rbp
0x18005b868  retn
0x18005b869  mov     rcx, [r15+5D8h]
0x18005b870  test    rcx, rcx
0x18005b873  setnz   al
0x18005b876  mov     [r14], al
0x18005b879  test    rcx, rcx
0x18005b87c  jnz     short loc_18005B8F6
0x18005b87e  mov     rcx, [r15+8]
0x18005b882  call    sub_1806A7BB4
0x18005b887  test    al, al
0x18005b889  jz      short loc_18005B846
0x18005b88b  mov     byte ptr [rsi+50h], 2
0x18005b88f  mov     cl, 2
0x18005b891  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x18005b896  lea     rcx, [rsi+20h]
0x18005b89a  xor     edx, edx
0x18005b89c  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005b8a1  mov     dword ptr [rsi+8], 12h
0x18005b8a8  xor     edx, edx
0x18005b8aa  lea     rcx, [rsi+38h]
0x18005b8ae  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005b8b3  mov     dword ptr [rsi+30h], 0Dh
0x18005b8ba  xor     edx, edx
0x18005b8bc  lea     rcx, [rsi+38h]
0x18005b8c0  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005b8c5  mov     r12d, 1
0x18005b8cb  mov     [rsi+34h], r12d
0x18005b8cf  mov     byte ptr [r13+50h], 2
0x18005b8d4  mov     cl, 2
0x18005b8d6  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x18005b8db  lea     rcx, [r13+48h]
0x18005b8df  xor     edx, edx
0x18005b8e1  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005b8e6  mov     dword ptr [r13+40h], 5
0x18005b8ee  mov     [r14], r12b
0x18005b8f1  jmp     loc_18005B846
0x18005b8f6  mov     ebx, 8
0x18005b8fb  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b902  lea     r12d, [rbx-7]
0x18005b906  cmp     rcx, r12
0x18005b909  ja      loc_18005B9A1
0x18005b90f  lea     rsi, ??_7CPropConverterHelper@Art@@6B@; const Art::CPropConverterHelper::`vftable'
0x18005b916  mov     rax, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b91d  cmp     rax, r12
0x18005b920  ja      short loc_18005B995
0x18005b922  xor     eax, eax
0x18005b924  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, r12; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b92d  jnz     short loc_18005B984
0x18005b92f  mov     dl, r12b; void (*)(void)
0x18005b932  lea     rcx, ?Shutdown@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@SAXXZ; Ptr
0x18005b939  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x18005b93e  mov     rcx, cs:Ptr; Ptr
0x18005b945  call    cs:__imp_DecodePointer
0x18005b94b  test    rax, rax
0x18005b94e  jz      short loc_18005B968
0x18005b950  mov     rcx, cs:Ptr; Ptr
0x18005b957  call    cs:__imp_DecodePointer
0x18005b95d  mov     rcx, rbx
0x18005b960  call    cs:__guard_dispatch_icall_fptr
0x18005b966  jmp     short loc_18005B970
0x18005b968  mov     rcx, rbx; this
0x18005b96b  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18005b970  mov     [rax], rsi
0x18005b973  mov     rcx, rax
0x18005b976  mov     rax, r12
0x18005b979  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, rcx; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b982  jmp     short loc_18005B916
0x18005b984  mov     [rsp+530h+var_4F0], rdi
0x18005b989  lea     rcx, [rsp+530h+var_4F0]
0x18005b98e  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18005b993  jmp     short loc_18005B916
0x18005b995  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b99c  mov     rsi, [rsp+530h+var_4F8]
0x18005b9a1  mov     rax, [rcx]
0x18005b9a4  lea     rbx, [r15+880h]
0x18005b9ab  mov     rdx, rbx
0x18005b9ae  mov     rax, [rax+90h]
0x18005b9b5  call    cs:__guard_dispatch_icall_fptr
0x18005b9bb  test    al, al
0x18005b9bd  jnz     loc_18005B846
0x18005b9c3  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b9ca  cmp     rcx, r12
0x18005b9cd  ja      loc_18005BA6C
0x18005b9d3  lea     r14, ??_7CPropConverterHelper@Art@@6B@; const Art::CPropConverterHelper::`vftable'
0x18005b9da  mov     rax, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b9e1  cmp     rax, r12
0x18005b9e4  ja      short loc_18005BA60
0x18005b9e6  xor     eax, eax
0x18005b9e8  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, r12; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005b9f1  jnz     short loc_18005BA4C
0x18005b9f3  mov     dl, r12b; void (*)(void)
0x18005b9f6  lea     rcx, ?Shutdown@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@SAXXZ; Ptr
0x18005b9fd  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x18005ba02  mov     rcx, cs:Ptr; Ptr
0x18005ba09  call    cs:__imp_DecodePointer
0x18005ba0f  test    rax, rax
0x18005ba12  jz      short loc_18005BA2E
0x18005ba14  mov     rcx, cs:Ptr; Ptr
0x18005ba1b  call    cs:__imp_DecodePointer
0x18005ba21  mov     ecx, 8
0x18005ba26  call    cs:__guard_dispatch_icall_fptr
0x18005ba2c  jmp     short loc_18005BA38
0x18005ba2e  mov     ecx, 8; this
0x18005ba33  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18005ba38  mov     [rax], r14
0x18005ba3b  mov     rcx, rax
0x18005ba3e  mov     rax, r12
0x18005ba41  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, rcx; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005ba4a  jmp     short loc_18005B9DA
0x18005ba4c  mov     [rsp+530h+var_4F0], rdi
0x18005ba51  lea     rcx, [rsp+530h+var_4F0]
0x18005ba56  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18005ba5b  jmp     loc_18005B9DA
0x18005ba60  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x18005ba67  mov     r14, [rsp+530h+var_4E0]
0x18005ba6c  mov     rax, [rcx]
0x18005ba6f  mov     rdx, rbx
0x18005ba72  mov     rax, [rax+98h]
0x18005ba79  call    cs:__guard_dispatch_icall_fptr
0x18005ba7f  test    al, al
0x18005ba81  jnz     loc_18005B846
0x18005ba87  cmp     [r15+2D8h], rdi
0x18005ba8e  jnz     short loc_18005BA9D
0x18005ba90  cmp     [r15+168h], rdi
0x18005ba97  jz      loc_18005B846
0x18005ba9d  cmp     [r15+740h], rdi
0x18005baa4  jz      loc_18005B846
0x18005baaa  mov     byte ptr [rsi+50h], 2
0x18005baae  mov     byte ptr [r13+50h], 2
0x18005bab3  mov     cl, [rsi+50h]
0x18005bab6  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x18005babb  mov     cl, [r13+50h]
0x18005babf  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x18005bac4  mov     eax, [r15+450h]
0x18005bacb  mov     [rbp+430h+var_4A8], eax
0x18005bace  mov     eax, [r15+458h]
0x18005bad5  mov     [rbp+430h+var_4A4], eax
0x18005bad8  mov     eax, [r15+460h]
0x18005badf  mov     [rbp+430h+var_4A0], eax
0x18005bae2  mov     eax, edi
0x18005bae4  cmp     [r15+4E8h], rdi
0x18005baeb  setnz   al
0x18005baee  mov     [rbp+430h+var_49C], eax
0x18005baf1  mov     eax, [r15+468h]
0x18005baf8  mov     [rbp+430h+var_498], eax
0x18005bafb  mov     eax, [r15+470h]
0x18005bb02  mov     [rbp+430h+var_494], eax
0x18005bb05  mov     eax, [r15+478h]
0x18005bb0c  mov     [rbp+430h+var_490], eax
0x18005bb0f  mov     eax, [r15+480h]
0x18005bb16  mov     [rbp+430h+var_48C], eax
0x18005bb19  mov     dword ptr [rsp+530h+var_4F0], edi
0x18005bb1d  lea     rax, [rsp+530h+var_500]
0x18005bb22  mov     [rsp+530h+var_510], rax
0x18005bb27  lea     r9, [rsp+530h+var_4F0]
0x18005bb2c  lea     r8, [rbp+430h+var_4A8]
0x18005bb30  call    ??$PerformConditionalPropMatch@UO11CameraSettings@Art@@W4PresetCameraType@2@@Art@@YAXPEBV?$PropPair@UO11CameraSettings@Art@@W4PresetCameraType@2@@0@HAEBUO11CameraSettings@0@AEAW4PresetCameraType@0@AEA_N@Z; Art::PerformConditionalPropMatch<Art::O11CameraSettings,Art::PresetCameraType>(Art::PropPair<Art::O11CameraSettings,Art::PresetCameraType> const *,int,Art::O11CameraSettings const &,Art::PresetCameraType &,bool &)
0x18005bb35  xor     edx, edx
0x18005bb37  lea     rcx, [rsi+20h]
0x18005bb3b  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005bb40  mov     eax, dword ptr [rsp+530h+var_4F0]
0x18005bb44  mov     [rsi+8], eax
0x18005bb47  mov     rax, [r15+400h]
0x18005bb4e  test    rax, rax
0x18005bb51  jnz     short loc_18005BB60
0x18005bb53  cmp     [r15+3F8h], rdi
0x18005bb5a  jz      loc_18005BC64
0x18005bb60  mov     [rsp+530h+var_4F0], 0
0x18005bb69  mov     [rsp+530h+var_4E8], 0
0x18005bb71  xorps   xmm0, xmm0
0x18005bb74  cvtsi2sd xmm0, qword ptr [r15+3F8h]
0x18005bb7d  mulsd   xmm0, cs:__real@3e91df46a2529d39
0x18005bb85  cvtpd2ps xmm2, xmm0; float
0x18005bb89  neg     rax
0x18005bb8c  xorps   xmm0, xmm0
0x18005bb8f  cvtsi2sd xmm0, rax
0x18005bb94  mulsd   xmm0, cs:__real@3e91df46a2529d39
0x18005bb9c  cvtpd2ps xmm1, xmm0; float
0x18005bba0  lea     rcx, [rsp+530h+var_4F0]; this
0x18005bba5  call    ?SetEulerRotation@SphereCoords@Gfx@@QEAAXMM@Z; Gfx::SphereCoords::SetEulerRotation(float,float)
0x18005bbaa  xor     edx, edx
0x18005bbac  lea     rcx, [rsi+20h]
0x18005bbb0  call    ??4?$TCntPtr@UIACStorage@@@Ofc@@QEAAAEAV01@PEAUIACStorage@@@Z; Ofc::TCntPtr<IACStorage>::operator=(IACStorage *)
0x18005bbb5  mov     rcx, rsi
0x18005bbb8  call    ?EnsureStorage@?$TOptional@VSphereCoords@Art@@@Ofc@@QEAAAEAVSphereCoords@Art@@XZ; Ofc::TOptional<Art::SphereCoords>::EnsureStorage(void)
0x18005bbbd  mov     r14, rax
0x18005bbc0  movss   xmm0, [rsp+530h+var_4E8]
0x18005bbc6  cvtps2pd xmm0, xmm0
0x18005bbc9  mulsd   xmm0, cs:__real@4066800000000000
0x18005bbd1  divsd   xmm0, cs:__real@400921fb54442d18
0x18005bbd9  mulsd   xmm0, cs:__real@40ed4c0000000000
0x18005bbe1  call    ??$Round@HN@Ofc@@YAHN@Z; Ofc::Round<int,double>(double)
0x18005bbe6  mov     esi, eax
0x18005bbe8  mov     ecx, eax
0x18005bbea  call    ?Validate@?$TRangeRestricted@VAngle@Art@@UPosFixedAngleRange@2@@Ofc@@CAXVAngle@Art@@@Z; Ofc::TRangeRestricted<Art::Angle,Art::PosFixedAngleRange>::Validate(Art::Angle)
0x18005bbef  movss   xmm0, dword ptr [rsp+530h+var_4F0+4]
0x18005bbf5  cvtps2pd xmm0, xmm0
0x18005bbf8  mulsd   xmm0, cs:__real@4066800000000000
0x18005bc00  divsd   xmm0, cs:__real@400921fb54442d18
0x18005bc08  mulsd   xmm0, cs:__real@40ed4c0000000000
  ... truncated ...
```
