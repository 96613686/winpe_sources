# Art::CPropConverter::Translate3D(Ofc::TNinchable<Art::Scene3D> &,Ofc::TNinchable<Art::Shape3D> &,bool &)

- ea: `0x1804fe8d0`
- end: `0x1804ff3a0`
- name: `?Translate3D@CPropConverter@Art@@MEBAXAEAV?$TNinchable@VScene3D@Art@@@Ofc@@AEAV?$TNinchable@VShape3D@Art@@@4@AEA_N@Z`
- size: `2768`
- prototype: `__int64 __fastcall(Art::CPropConverter *this)`
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000cfd4`
- `0x18000d920`
- `0x18000dc60`
- `0x18000e338`
- `0x18000e5b0`
- `0x18001df00`
- `0x18002c260`
- `0x18003fda0`
- `0x180064914`
- `0x1800659a0`
- `0x180070fe0`
- `0x180071720`
- `0x1800a241c`
- `0x1801f47c0`
- `0x18020df88`
- `0x18020e51c`
- `0x18037949c`
- `0x1804fe8d0`
- `0x18050b690`
- `0x18068c7dc`
- `0x1806c3cb4`
- `0x1806c3d18`
- `0x1806c3d9c`
- `0x1806c6070`
- `0x1806c7a7c`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1804feb35`
- `KERNEL32!DecodePointer` at `0x1804feb47`
- `KERNEL32!DecodePointer` at `0x1804febf9`
- `KERNEL32!DecodePointer` at `0x1804fec0b`
- `KERNEL32!DecodePointer` at `0x1804ff0e4`
- `KERNEL32!DecodePointer` at `0x1804ff0f6`
- `KERNEL32!DecodePointer` at `0x1804feb35`
- `KERNEL32!DecodePointer` at `0x1804feb47`
- `KERNEL32!DecodePointer` at `0x1804febf9`
- `KERNEL32!DecodePointer` at `0x1804fec0b`
- `KERNEL32!DecodePointer` at `0x1804ff0e4`
- `KERNEL32!DecodePointer` at `0x1804ff0f6`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x1804fe93b`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x1804fe9a8`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x1804fe93b`
- `MSO!__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z` at `0x1804fe9a8`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1804fe985`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1804fe9ed`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1804fe985`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1804fe9ed`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x1804fea04`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x1804fea1d`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x1804fea04`
- `Mso98Win32Client!__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z` at `0x1804fea1d`

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
    (*(void (__fastcall **)(struct IMsoDrawing *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v9 + 664LL))(
      v9,
      v8,
      11,
      v105);
    memset_0(v104, 0, 0x108u);
    MsoGetPropSetNinch(11);
    memset_0(v103, 0, 0xF8u);
    v10 = (struct MSOSP *)*((_QWORD *)this + 1);
    v11 = MsoPidgFromHsp(v10);
    (*(void (__fastcall **)(struct IMsoDrawing *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v11 + 664LL))(
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
    if ( (unsigned __int8)sub_18068C7DC(*((_QWORD *)this + 1)) )
    {
      *(_BYTE *)(v6 + 80) = 2;
      LOBYTE(v13) = 2;
      Ofc::ThrowIfInvalidQualifiedValueState(v13);
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 32, 0);
      *(_DWORD *)(v6 + 8) = 18;
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 48) = 13;
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 52) = 1;
      *(_BYTE *)(a3 + 80) = 2;
      LOBYTE(v14) = 2;
      Ofc::ThrowIfInvalidQualifiedValueState(v14);
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 32, 0);
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
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 32, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 56, 0);
      *(_DWORD *)(v6 + 48) = v82;
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v6 + 56, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
        Storage = Ofc::TOptional<Art::Bevel>::CreateStorage(a3);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Storage + 24, 0);
        *(_DWORD *)(Storage + 16) = 4;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Storage + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)Storage = v84;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Storage + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)(Storage + 8) = v84;
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
        v71 = Ofc::TOptional<Art::Bevel>::CreateStorage(a3 + 8);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v71 + 24, 0);
        *(_DWORD *)(v71 + 16) = 4;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v71 + 24, 0);
        Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::PosCoordRange>>(
          &v84,
          &v81);
        *(_QWORD *)v71 = v84;
        v81 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(13500);
        Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(v71 + 24, 0);
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
            Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
      Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(a3 + 72, 0);
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
0x1804fe8d0  push    rbp
0x1804fe8d2  push    rbx
0x1804fe8d3  push    rsi
0x1804fe8d4  push    rdi
0x1804fe8d5  push    r12
0x1804fe8d7  push    r13
0x1804fe8d9  push    r14
0x1804fe8db  push    r15
0x1804fe8dd  lea     rbp, [rsp-3F8h]
0x1804fe8e5  sub     rsp, 4F8h
0x1804fe8ec  mov     rax, cs:__security_cookie
0x1804fe8f3  xor     rax, rsp
0x1804fe8f6  mov     [rbp+430h+var_50], rax
0x1804fe8fd  mov     r14, r9
0x1804fe900  mov     [rsp+530h+var_4E0], r9
0x1804fe905  mov     r13, r8
0x1804fe908  mov     rsi, rdx
0x1804fe90b  mov     [rsp+530h+var_4F8], rdx
0x1804fe910  mov     r15, rcx
0x1804fe913  mov     rbx, [rcx+8]
0x1804fe917  xor     edi, edi
0x1804fe919  test    rbx, rbx
0x1804fe91c  jz      loc_1804FEA59
0x1804fe922  mov     edi, 108h
0x1804fe927  mov     r8d, edi; Size
0x1804fe92a  xor     edx, edx; Val
0x1804fe92c  lea     rcx, [rbp+430h+var_160]; void *
0x1804fe933  call    memset_0
0x1804fe938  mov     rcx, rbx
0x1804fe93b  call    cs:__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z; MsoPidgFromHsp(MSOSP *)
0x1804fe941  mov     r10, rax
0x1804fe944  mov     rcx, [rax]
0x1804fe947  mov     rax, [rcx+298h]
0x1804fe94e  lea     r9, [rbp+430h+var_160]
0x1804fe955  mov     r12d, 0Bh
0x1804fe95b  mov     r8d, r12d
0x1804fe95e  mov     rdx, rbx
0x1804fe961  mov     rcx, r10
0x1804fe964  call    cs:__guard_dispatch_icall_fptr
0x1804fe96a  mov     r8d, edi; Size
0x1804fe96d  xor     edx, edx; Val
0x1804fe96f  lea     rcx, [rbp+430h+var_270]; void *
0x1804fe976  call    memset_0
0x1804fe97b  lea     rdx, [rbp+430h+var_270]
0x1804fe982  mov     ecx, r12d
0x1804fe985  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x1804fe98b  mov     edi, 0F8h
0x1804fe990  mov     r8d, edi; Size
0x1804fe993  xor     edx, edx; Val
0x1804fe995  lea     rcx, [rbp+430h+var_370]; void *
0x1804fe99c  call    memset_0
0x1804fe9a1  mov     rbx, [r15+8]
0x1804fe9a5  mov     rcx, rbx
0x1804fe9a8  call    cs:__imp_?MsoPidgFromHsp@@YAPEAUIMsoDrawing@@PEAUMSOSP@@@Z; MsoPidgFromHsp(MSOSP *)
0x1804fe9ae  mov     r10, rax
0x1804fe9b1  mov     rcx, [rax]
0x1804fe9b4  mov     rax, [rcx+298h]
0x1804fe9bb  lea     r9, [rbp+430h+var_370]
0x1804fe9c2  lea     r8d, [r12-1]
0x1804fe9c7  mov     rdx, rbx
0x1804fe9ca  mov     rcx, r10
0x1804fe9cd  call    cs:__guard_dispatch_icall_fptr
0x1804fe9d3  nop
0x1804fe9d4  mov     r8d, edi; Size
0x1804fe9d7  xor     edx, edx; Val
0x1804fe9d9  lea     rcx, [rbp+430h+var_470]; void *
0x1804fe9dd  call    memset_0
0x1804fe9e2  lea     rdx, [rbp+430h+var_470]
0x1804fe9e6  lea     ebx, [r12-1]
0x1804fe9eb  mov     ecx, ebx
0x1804fe9ed  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x1804fe9f3  lea     r8, [rbp+430h+var_270]
0x1804fe9fa  lea     rdx, [rbp+430h+var_160]
0x1804fea01  mov     ecx, r12d
0x1804fea04  call    cs:__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z; MsoFIsPropSetEqual(MSOPSID,void const *,void const *)
0x1804fea0a  xor     edi, edi
0x1804fea0c  test    eax, eax
0x1804fea0e  jz      short loc_1804FEA59
0x1804fea10  lea     r8, [rbp+430h+var_470]
0x1804fea14  lea     rdx, [rbp+430h+var_370]
0x1804fea1b  mov     ecx, ebx
0x1804fea1d  call    cs:__imp_?MsoFIsPropSetEqual@@YAHW4MSOPSID@@PEBX1@Z; MsoFIsPropSetEqual(MSOPSID,void const *,void const *)
0x1804fea23  test    eax, eax
0x1804fea25  jz      short loc_1804FEA59
0x1804fea27  lea     r12d, [rbx-9]
0x1804fea2b  mov     [rsi+50h], r12b
0x1804fea2f  mov     [r13+50h], r12b
0x1804fea33  mov     [r14], dil
0x1804fea36  mov     rcx, [rbp+430h+var_50]
0x1804fea3d  xor     rcx, rsp; StackCookie
0x1804fea40  call    __security_check_cookie
0x1804fea45  add     rsp, 4F8h
0x1804fea4c  pop     r15
0x1804fea4e  pop     r14
0x1804fea50  pop     r13
0x1804fea52  pop     r12
0x1804fea54  pop     rdi
0x1804fea55  pop     rsi
0x1804fea56  pop     rbx
0x1804fea57  pop     rbp
0x1804fea58  retn
0x1804fea59  mov     rcx, [r15+5D8h]
0x1804fea60  test    rcx, rcx
0x1804fea63  setnz   al
0x1804fea66  mov     [r14], al
0x1804fea69  test    rcx, rcx
0x1804fea6c  jnz     short loc_1804FEAE6
0x1804fea6e  mov     rcx, [r15+8]
0x1804fea72  call    sub_18068C7DC
0x1804fea77  test    al, al
0x1804fea79  jz      short loc_1804FEA36
0x1804fea7b  mov     byte ptr [rsi+50h], 2
0x1804fea7f  mov     cl, 2
0x1804fea81  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x1804fea86  lea     rcx, [rsi+20h]
0x1804fea8a  xor     edx, edx
0x1804fea8c  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804fea91  mov     dword ptr [rsi+8], 12h
0x1804fea98  xor     edx, edx
0x1804fea9a  lea     rcx, [rsi+38h]
0x1804fea9e  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804feaa3  mov     dword ptr [rsi+30h], 0Dh
0x1804feaaa  xor     edx, edx
0x1804feaac  lea     rcx, [rsi+38h]
0x1804feab0  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804feab5  mov     r12d, 1
0x1804feabb  mov     [rsi+34h], r12d
0x1804feabf  mov     byte ptr [r13+50h], 2
0x1804feac4  mov     cl, 2
0x1804feac6  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x1804feacb  lea     rcx, [r13+48h]
0x1804feacf  xor     edx, edx
0x1804fead1  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804fead6  mov     dword ptr [r13+40h], 5
0x1804feade  mov     [r14], r12b
0x1804feae1  jmp     loc_1804FEA36
0x1804feae6  mov     ebx, 8
0x1804feaeb  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804feaf2  lea     r12d, [rbx-7]
0x1804feaf6  cmp     rcx, r12
0x1804feaf9  ja      loc_1804FEB91
0x1804feaff  lea     rsi, ??_7CPropConverterHelper@Art@@6B@; const Art::CPropConverterHelper::`vftable'
0x1804feb06  mov     rax, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804feb0d  cmp     rax, r12
0x1804feb10  ja      short loc_1804FEB85
0x1804feb12  xor     eax, eax
0x1804feb14  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, r12; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804feb1d  jnz     short loc_1804FEB74
0x1804feb1f  mov     dl, r12b; void (*)(void)
0x1804feb22  lea     rcx, ?Shutdown@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@SAXXZ; Ptr
0x1804feb29  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1804feb2e  mov     rcx, cs:Ptr; Ptr
0x1804feb35  call    cs:__imp_DecodePointer
0x1804feb3b  test    rax, rax
0x1804feb3e  jz      short loc_1804FEB58
0x1804feb40  mov     rcx, cs:Ptr; Ptr
0x1804feb47  call    cs:__imp_DecodePointer
0x1804feb4d  mov     rcx, rbx
0x1804feb50  call    cs:__guard_dispatch_icall_fptr
0x1804feb56  jmp     short loc_1804FEB60
0x1804feb58  mov     rcx, rbx; this
0x1804feb5b  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804feb60  mov     [rax], rsi
0x1804feb63  mov     rcx, rax
0x1804feb66  mov     rax, r12
0x1804feb69  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, rcx; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804feb72  jmp     short loc_1804FEB06
0x1804feb74  mov     [rsp+530h+var_4F0], rdi
0x1804feb79  lea     rcx, [rsp+530h+var_4F0]
0x1804feb7e  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1804feb83  jmp     short loc_1804FEB06
0x1804feb85  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804feb8c  mov     rsi, [rsp+530h+var_4F8]
0x1804feb91  mov     rax, [rcx]
0x1804feb94  lea     rbx, [r15+880h]
0x1804feb9b  mov     rdx, rbx
0x1804feb9e  mov     rax, [rax+90h]
0x1804feba5  call    cs:__guard_dispatch_icall_fptr
0x1804febab  test    al, al
0x1804febad  jnz     loc_1804FEA36
0x1804febb3  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804febba  cmp     rcx, r12
0x1804febbd  ja      loc_1804FEC5C
0x1804febc3  lea     r14, ??_7CPropConverterHelper@Art@@6B@; const Art::CPropConverterHelper::`vftable'
0x1804febca  mov     rax, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804febd1  cmp     rax, r12
0x1804febd4  ja      short loc_1804FEC50
0x1804febd6  xor     eax, eax
0x1804febd8  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, r12; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804febe1  jnz     short loc_1804FEC3C
0x1804febe3  mov     dl, r12b; void (*)(void)
0x1804febe6  lea     rcx, ?Shutdown@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@SAXXZ; Ptr
0x1804febed  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1804febf2  mov     rcx, cs:Ptr; Ptr
0x1804febf9  call    cs:__imp_DecodePointer
0x1804febff  test    rax, rax
0x1804fec02  jz      short loc_1804FEC1E
0x1804fec04  mov     rcx, cs:Ptr; Ptr
0x1804fec0b  call    cs:__imp_DecodePointer
0x1804fec11  mov     ecx, 8
0x1804fec16  call    cs:__guard_dispatch_icall_fptr
0x1804fec1c  jmp     short loc_1804FEC28
0x1804fec1e  mov     ecx, 8; this
0x1804fec23  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804fec28  mov     [rax], r14
0x1804fec2b  mov     rcx, rax
0x1804fec2e  mov     rax, r12
0x1804fec31  lock cmpxchg cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA, rcx; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804fec3a  jmp     short loc_1804FEBCA
0x1804fec3c  mov     [rsp+530h+var_4F0], rdi
0x1804fec41  lea     rcx, [rsp+530h+var_4F0]
0x1804fec46  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1804fec4b  jmp     loc_1804FEBCA
0x1804fec50  mov     rcx, cs:?s_pInstance@?$TSingleton@VCPropConverterHelper@Art@@@Ofc@@0PEAVCPropConverterHelper@Art@@EA; Art::CPropConverterHelper * Ofc::TSingleton<Art::CPropConverterHelper>::s_pInstance
0x1804fec57  mov     r14, [rsp+530h+var_4E0]
0x1804fec5c  mov     rax, [rcx]
0x1804fec5f  mov     rdx, rbx
0x1804fec62  mov     rax, [rax+98h]
0x1804fec69  call    cs:__guard_dispatch_icall_fptr
0x1804fec6f  test    al, al
0x1804fec71  jnz     loc_1804FEA36
0x1804fec77  cmp     [r15+2D8h], rdi
0x1804fec7e  jnz     short loc_1804FEC8D
0x1804fec80  cmp     [r15+168h], rdi
0x1804fec87  jz      loc_1804FEA36
0x1804fec8d  cmp     [r15+740h], rdi
0x1804fec94  jz      loc_1804FEA36
0x1804fec9a  mov     byte ptr [rsi+50h], 2
0x1804fec9e  mov     byte ptr [r13+50h], 2
0x1804feca3  mov     cl, [rsi+50h]
0x1804feca6  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x1804fecab  mov     cl, [r13+50h]
0x1804fecaf  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x1804fecb4  mov     eax, [r15+450h]
0x1804fecbb  mov     [rbp+430h+var_4A8], eax
0x1804fecbe  mov     eax, [r15+458h]
0x1804fecc5  mov     [rbp+430h+var_4A4], eax
0x1804fecc8  mov     eax, [r15+460h]
0x1804feccf  mov     [rbp+430h+var_4A0], eax
0x1804fecd2  mov     eax, edi
0x1804fecd4  cmp     [r15+4E8h], rdi
0x1804fecdb  setnz   al
0x1804fecde  mov     [rbp+430h+var_49C], eax
0x1804fece1  mov     eax, [r15+468h]
0x1804fece8  mov     [rbp+430h+var_498], eax
0x1804feceb  mov     eax, [r15+470h]
0x1804fecf2  mov     [rbp+430h+var_494], eax
0x1804fecf5  mov     eax, [r15+478h]
0x1804fecfc  mov     [rbp+430h+var_490], eax
0x1804fecff  mov     eax, [r15+480h]
0x1804fed06  mov     [rbp+430h+var_48C], eax
0x1804fed09  mov     dword ptr [rsp+530h+var_4F0], edi
0x1804fed0d  lea     rax, [rsp+530h+var_500]
0x1804fed12  mov     [rsp+530h+var_510], rax
0x1804fed17  lea     r9, [rsp+530h+var_4F0]
0x1804fed1c  lea     r8, [rbp+430h+var_4A8]
0x1804fed20  call    ??$PerformConditionalPropMatch@UO11CameraSettings@Art@@W4PresetCameraType@2@@Art@@YAXPEBV?$PropPair@UO11CameraSettings@Art@@W4PresetCameraType@2@@0@HAEBUO11CameraSettings@0@AEAW4PresetCameraType@0@AEA_N@Z; Art::PerformConditionalPropMatch<Art::O11CameraSettings,Art::PresetCameraType>(Art::PropPair<Art::O11CameraSettings,Art::PresetCameraType> const *,int,Art::O11CameraSettings const &,Art::PresetCameraType &,bool &)
0x1804fed25  xor     edx, edx
0x1804fed27  lea     rcx, [rsi+20h]
0x1804fed2b  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804fed30  mov     eax, dword ptr [rsp+530h+var_4F0]
0x1804fed34  mov     [rsi+8], eax
0x1804fed37  mov     rax, [r15+400h]
0x1804fed3e  test    rax, rax
0x1804fed41  jnz     short loc_1804FED50
0x1804fed43  cmp     [r15+3F8h], rdi
0x1804fed4a  jz      loc_1804FEE54
0x1804fed50  mov     [rsp+530h+var_4F0], 0
0x1804fed59  mov     [rsp+530h+var_4E8], 0
0x1804fed61  xorps   xmm0, xmm0
0x1804fed64  cvtsi2sd xmm0, qword ptr [r15+3F8h]
0x1804fed6d  mulsd   xmm0, cs:__real@3e91df46a2529d39
0x1804fed75  cvtpd2ps xmm2, xmm0; float
0x1804fed79  neg     rax
0x1804fed7c  xorps   xmm0, xmm0
0x1804fed7f  cvtsi2sd xmm0, rax
0x1804fed84  mulsd   xmm0, cs:__real@3e91df46a2529d39
0x1804fed8c  cvtpd2ps xmm1, xmm0; float
0x1804fed90  lea     rcx, [rsp+530h+var_4F0]; this
0x1804fed95  call    ?SetEulerRotation@SphereCoords@Gfx@@QEAAXMM@Z; Gfx::SphereCoords::SetEulerRotation(float,float)
0x1804fed9a  xor     edx, edx
0x1804fed9c  lea     rcx, [rsi+20h]
0x1804feda0  call    ??4?$TCntPtr@VInkInputLayerNode@Dr@@@Ofc@@QEAAAEAV01@PEAVInkInputLayerNode@Dr@@@Z; Ofc::TCntPtr<Dr::InkInputLayerNode>::operator=(Dr::InkInputLayerNode *)
0x1804feda5  mov     rcx, rsi
0x1804feda8  call    ?EnsureStorage@?$TOptional@VSphereCoords@Art@@@Ofc@@QEAAAEAVSphereCoords@Art@@XZ; Ofc::TOptional<Art::SphereCoords>::EnsureStorage(void)
0x1804fedad  mov     r14, rax
0x1804fedb0  movss   xmm0, [rsp+530h+var_4E8]
0x1804fedb6  cvtps2pd xmm0, xmm0
0x1804fedb9  mulsd   xmm0, cs:__real@4066800000000000
0x1804fedc1  divsd   xmm0, cs:__real@400921fb54442d18
0x1804fedc9  mulsd   xmm0, cs:__real@40ed4c0000000000
0x1804fedd1  call    ??$Round@HN@Ofc@@YAHN@Z; Ofc::Round<int,double>(double)
0x1804fedd6  mov     esi, eax
0x1804fedd8  mov     ecx, eax
0x1804fedda  call    ?Validate@?$TRangeRestricted@VAngle@Art@@UPosFixedAngleRange@2@@Ofc@@CAXVAngle@Art@@@Z; Ofc::TRangeRestricted<Art::Angle,Art::PosFixedAngleRange>::Validate(Art::Angle)
0x1804feddf  movss   xmm0, dword ptr [rsp+530h+var_4F0+4]
0x1804fede5  cvtps2pd xmm0, xmm0
0x1804fede8  mulsd   xmm0, cs:__real@4066800000000000
0x1804fedf0  divsd   xmm0, cs:__real@400921fb54442d18
0x1804fedf8  mulsd   xmm0, cs:__real@40ed4c0000000000
  ... truncated ...
```
