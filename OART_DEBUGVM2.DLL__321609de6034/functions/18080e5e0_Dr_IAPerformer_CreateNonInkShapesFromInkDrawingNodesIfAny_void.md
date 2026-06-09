# Dr::IAPerformer::CreateNonInkShapesFromInkDrawingNodesIfAny(void)

- ea: `0x18080e5e0`
- end: `0x18080ed9b`
- name: `?CreateNonInkShapesFromInkDrawingNodesIfAny@IAPerformer@Dr@@QEAAJXZ`
- size: `1979`
- prototype: `__int64 __fastcall(Dr::IAPerformer *__hidden this)`
- caller_count: `2`
- callee_count: `25`
- tags: `service_task`

## callers

- `0x18066b410`
- `0x180835a60`

## callees

- `0x18000f930`
- `0x18003e948`
- `0x1800e6620`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x1803111e0`
- `0x1804a908c`
- `0x1804b4954`
- `0x1804d2980`
- `0x180587ee8`
- `0x18066e198`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bc84c`
- `0x1806d19bc`
- `0x1806d19e4`
- `0x18080e5e0`
- `0x18080eef8`
- `0x1808147e0`
- `0x180814bd4`
- `0x1808159c0`
- `0x1808160f4`
- `0x180817188`

## import_xrefs

- `mso40uiWin32Client!__imp_?HasHapticPenSupport@Haptics@OInk@@YA_NXZ` at `0x18080ec4d`
- `mso40uiWin32Client!__imp_?HasHapticPenSupport@Haptics@OInk@@YA_NXZ` at `0x18080ec4d`
- `mso40uiWin32Client!__imp_?TryPlayHapticForPenPointer@IHapticsController@Haptics@OInk@@SAJIW4WaveformId@23@NV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z` at `0x18080ed18`
- `mso40uiWin32Client!__imp_?TryPlayHapticForPenPointer@IHapticsController@Haptics@OInk@@SAJIW4WaveformId@23@NV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z` at `0x18080ed18`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18080ed27`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18080ed27`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080eb61`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080ebc8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080eb61`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080ebc8`
- `ole32!CoTaskMemFree` at `0x18080eb2e`
- `ole32!CoTaskMemFree` at `0x18080eb42`
- `ole32!CoTaskMemFree` at `0x18080eb51`
- `ole32!CoTaskMemFree` at `0x18080eb9a`
- `ole32!CoTaskMemFree` at `0x18080eba9`
- `ole32!CoTaskMemFree` at `0x18080ebb8`
- `ole32!CoTaskMemFree` at `0x18080eb2e`
- `ole32!CoTaskMemFree` at `0x18080eb42`
- `ole32!CoTaskMemFree` at `0x18080eb51`
- `ole32!CoTaskMemFree` at `0x18080eb9a`
- `ole32!CoTaskMemFree` at `0x18080eba9`
- `ole32!CoTaskMemFree` at `0x18080ebb8`

## pseudocode

```c
__int64 __fastcall Dr::IAPerformer::CreateNonInkShapesFromInkDrawingNodesIfAny(Dr::IAPerformer *this)
{
  unsigned int v2; // r14d
  int v3; // esi
  int v4; // eax
  int i; // r12d
  Dr::InkDocAnalyzer **v6; // rbx
  struct Ofc::CProxyPtrImpl **v7; // rax
  void *v8; // rdx
  int *v9; // rdi
  int *v10; // rbx
  unsigned int v11; // r14d
  double *v12; // r9
  int v13; // esi
  unsigned int v14; // esi
  __int64 Patriarch; // rax
  __int64 DrawingElementFromId; // rax
  struct Ofc::CProxyPtrImpl **v17; // rax
  struct Ofc::CProxyPtrImpl *v18; // rax
  _QWORD *Checked; // rax
  struct Ofc::CProxyPtrImpl *v20; // rax
  __int64 j; // r8
  char v22; // si
  struct Ofc::CProxyPtrImpl **v23; // rcx
  __int64 v24; // rsi
  struct Ofc::CProxyPtrImpl **v25; // rcx
  void *v26; // rdx
  OInk::Haptics *v28; // rcx
  struct Ofc::CProxyPtrImpl *v29; // rax
  _QWORD *v30; // rax
  int *v31; // rbx
  char v32; // r14
  char v33; // di
  struct Ofc::CProxyPtrImpl *v34; // rbx
  unsigned int v35; // eax
  __int64 v36; // r8
  char v37[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  struct Ofc::CProxyPtrImpl *v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v42; // [rsp+68h] [rbp-98h]
  unsigned int v43; // [rsp+6Ch] [rbp-94h]
  int v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+74h] [rbp-8Ch] BYREF
  int *v46; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  __int64 v48; // [rsp+88h] [rbp-78h] BYREF
  struct Ofc::CProxyPtrImpl *v49; // [rsp+90h] [rbp-70h] BYREF
  int v50; // [rsp+98h] [rbp-68h]
  struct Ofc::CProxyPtrImpl *v51; // [rsp+A0h] [rbp-60h] BYREF
  struct Ofc::CProxyPtrImpl *v52; // [rsp+A8h] [rbp-58h] BYREF
  int OfficeShapeType; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPOINT v55; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v56; // [rsp+C8h] [rbp-38h]
  int *v57; // [rsp+D0h] [rbp-30h]
  Mso::Memory *v58; // [rsp+D8h] [rbp-28h]
  struct Ofc::CProxyPtrImpl *v59; // [rsp+E0h] [rbp-20h] BYREF
  void **v60; // [rsp+E8h] [rbp-18h] BYREF
  int v61; // [rsp+F0h] [rbp-10h]
  int v62; // [rsp+F4h] [rbp-Ch]
  int v63; // [rsp+F8h] [rbp-8h]
  int v64; // [rsp+FCh] [rbp-4h]
  __int64 v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  int v67; // [rsp+110h] [rbp+10h]
  unsigned int v68; // [rsp+114h] [rbp+14h]
  struct Ofc::CProxyPtrImpl *v69; // [rsp+118h] [rbp+18h] BYREF
  struct Ofc::CProxyPtrImpl *v70; // [rsp+120h] [rbp+20h] BYREF
  struct Ofc::CProxyPtrImpl *v71; // [rsp+128h] [rbp+28h] BYREF
  struct Ofc::CProxyPtrImpl *v72; // [rsp+130h] [rbp+30h] BYREF
  int *v73; // [rsp+138h] [rbp+38h]
  int *v74; // [rsp+140h] [rbp+40h]
  __int128 v75; // [rsp+148h] [rbp+48h] BYREF

  v2 = 0;
  v50 = 0;
  v48 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 2) + 376LL))(
         *((_QWORD *)this + 2),
         &GUID_CNT_INKDRAWING,
         &v48);
  v44 = 0;
  if ( v3 < 0 || (v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 24LL))(v48, &v44), (v4 = v44) == 0) )
  {
    Dr::IAPerformer::DisplayErrorOOUI(this);
    v4 = v44;
  }
  v37[0] = 0;
  v61 = 12;
  v62 = 7;
  v63 = -1;
  v64 = 0;
  v65 = 0;
  v60 = &Ofc::TMap<Ofc::TWeakPtr<Dr::InkViewElement>,Ofc::TArray<long>>::`vftable';
  v66 = 0;
  v67 = 0;
  v68 = 0x80000000;
  for ( i = v4 - 1; ; --i )
  {
    v6 = (Dr::InkDocAnalyzer **)((char *)this + 32);
    if ( v3 < 0 || i < 0 )
      break;
    v38 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 32LL))(v48, (unsigned int)i, &v38);
    v75 = 0;
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v38 + 24LL))(v38, &v75);
    v7 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(Dr::IAPerformer *, struct Ofc::CProxyPtrImpl **, __int128 *))(*(_QWORD *)this + 80LL))(
                                         this,
                                         &v69,
                                         &v75);
    v40 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v7);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v69);
    if ( Dr::InkDocAnalyzer::FUseSynchronousIA(*((Dr::InkDocAnalyzer **)this + 4)) || *((_QWORD *)v40 + 2) )
    {
      v58 = 0;
      OfficeShapeType = Dr::InkDocAnalyzerHelpers::GetOfficeShapeType(&v38);
      if ( OfficeShapeType != 187 )
      {
        v54 = 0;
        Dr::InkDocAnalyzerHelpers::FGetConnectorEndTypes(&v38, &v54, (char *)&v54 + 4);
        v39 = 0;
        v9 = 0;
        v46 = 0;
        if ( v3 >= 0 && OfficeShapeType < 187 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *, int **))(*(_QWORD *)v38 + 152LL))(
                 v38,
                 &GUID_CNP_ROTATIONANGLE,
                 &v39,
                 &v46);
          v9 = v46;
        }
        v74 = v9;
        *(double *)&v55 = 0.0;
        if ( v3 >= 0 && v9 )
          *(double *)&v55 = (double)*v9 * 0.00017453292519944;
        v39 = 0;
        v10 = 0;
        v46 = 0;
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *, int **))(*(_QWORD *)v38 + 152LL))(
                 v38,
                 &GUID_CNP_HOTPOINTS,
                 &v39,
                 &v46);
          v2 = v39;
          v10 = v46;
        }
        v73 = v10;
        v56 = 0;
        if ( v3 >= 0 && v10 && (v11 = v2 >> 3, (v56 = v11) != 0) )
        {
          v57 = v10;
          if ( !(unsigned __int8)Art::FIsConnectorType((unsigned int)OfficeShapeType) && OfficeShapeType != 5 )
            Dr::InkDocAnalyzerHelpers::ApplyShapeRotationBias(
              (Dr::InkDocAnalyzerHelpers *)v11,
              (unsigned int)v10,
              &v55,
              v12);
          v2 = 0;
          v45 = 0;
          pv = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v38 + 192LL))(v38, &v45, &pv);
          if ( v13 < 0 || !v45 )
          {
            if ( pv )
              CoTaskMemFree(pv);
            CoTaskMemFree(v10);
            if ( v9 )
              CoTaskMemFree(v9);
            if ( v58 )
              Mso::Memory::Free(v58, v26);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v40);
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            Ofc::TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>::~TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>(&v60);
            if ( v48 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            return (unsigned int)v13;
          }
          v41 = 0;
          v42 = 0;
          v43 = 0x80000000;
          if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL) + 16LL) )
            goto LABEL_43;
          do
          {
            v14 = *((_DWORD *)pv + v2)
                / (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL) + 16LL) != 0 ? 0x3E8 : 0);
            Patriarch = Dr::InkDocAnalyzer::GetPatriarch(*((_QWORD *)this + 4), &v71);
            DrawingElementFromId = Dr::NodeHelper::GetDrawingElementFromId(&v70, v14, Patriarch);
            v17 = (struct Ofc::CProxyPtrImpl **)Ofc::runtime_cast<Dr::InkDrawingElement,Dr::DrawingElement>(DrawingElementFromId);
            v49 = Ofc::CProxyPtrImpl::WeakAddRef(*v17);
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v70);
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v71);
            if ( *((_QWORD *)v49 + 2) )
            {
              v18 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v49);
              v52 = v18;
              if ( *((_QWORD *)v18 + 2) )
              {
                Checked = Ofc::CProxyPtrImpl::GetChecked(v18);
                (*(void (__fastcall **)(_QWORD *, struct Ofc::CProxyPtrImpl **))(Checked[45] + 136LL))(
                  Checked + 45,
                  &v51);
                v20 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v51);
                v72 = v20;
                for ( j = v41; j != v41 + 8LL * v42; j += 8 )
                {
                  if ( *(_QWORD *)(*(_QWORD *)j + 16LL) == *((_QWORD *)v20 + 2) )
                  {
                    v22 = 0;
                    goto LABEL_37;
                  }
                }
                v22 = 1;
LABEL_37:
                Ofc::CProxyPtrImpl::DtorStrongRelease(&v72);
                if ( v22 )
                {
                  v59 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v51);
                  Ofc::CArrayImpl::EnsureCapacityForOneElem(
                    (Ofc::CArrayImpl *)&v41,
                    8u,
                    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do);
                  v23 = (struct Ofc::CProxyPtrImpl **)(v41 + 8LL * v42);
                  *v23 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
                  ++v42;
                  Ofc::CProxyPtrImpl::StrongMoveAssign(v23, &v59);
                  Ofc::CProxyPtrImpl::DtorStrongRelease(&v59);
                }
                Ofc::CProxyPtrImpl::DtorWeakRelease(&v51);
              }
              Ofc::CProxyPtrImpl::DtorStrongRelease(&v52);
            }
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v49);
            ++v2;
          }
          while ( v2 < v45 );
          v2 = 0;
          if ( !v42 )
          {
LABEL_43:
            v24 = *((_QWORD *)this + 4);
            Ofc::CArrayImpl::EnsureCapacityForOneElem(
              (Ofc::CArrayImpl *)&v41,
              8u,
              (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do);
            v25 = (struct Ofc::CProxyPtrImpl **)(v41 + 8LL * v42);
            *v25 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
            ++v42;
            Ofc::CProxyPtrImpl::CheckedStrongAssign(v25, *(struct Ofc::CProxyPtrImpl **)(v24 + 88));
          }
          v3 = (*(__int64 (__fastcall **)(Dr::IAPerformer *, __int64 *, __int64 *, int *, struct Ofc::CProxyPtrImpl **, char *, void ***))(*(_QWORD *)this + 192LL))(
                 this,
                 &v38,
                 &v41,
                 &OfficeShapeType,
                 &v40,
                 v37,
                 &v60);
          if ( v3 >= 0 && v37[0] )
            *(_BYTE *)(*((_QWORD *)this + 4) + 24LL) = 1;
          Ofc::TArray<Ofc::TReferringPtr<Dr::ConnectorDrawingElement>>::~TArray<Ofc::TReferringPtr<Dr::ConnectorDrawingElement>>(&v41);
          if ( pv )
            CoTaskMemFree(pv);
        }
        else
        {
          v2 = 0;
        }
        if ( v10 )
          CoTaskMemFree(v10);
        if ( v9 )
          CoTaskMemFree(v9);
      }
      if ( v58 )
        Mso::Memory::Free(v58, v8);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v40);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  Dr::IAPerformer::RemoveInk(this, &v60);
  if ( v3 < 0 || !v37[0] )
  {
    Dr::IAPerformer::DisplayErrorOOUI(this);
    v6 = (Dr::InkDocAnalyzer **)((char *)this + 32);
  }
  if ( Dr::InkDocAnalyzer::FUseSynchronousIA(*v6) )
    Dr::InkDocAnalyzer::ResetLastInsertInkDrawing(*v6);
  if ( OInk::Haptics::HasHapticPenSupport(v28) && v37[0] )
  {
    v29 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)*v6 + 4));
    v49 = v29;
    if ( *((_QWORD *)v29 + 2) )
    {
      v30 = Ofc::CProxyPtrImpl::GetChecked(v29);
      v31 = (int *)v30[85];
      if ( v31 )
        (**(void (__fastcall ***)(_QWORD))v31)(v30[85]);
      v32 = 1;
      if ( v31 )
      {
        v33 = 1;
        goto LABEL_85;
      }
    }
    else
    {
      v31 = v73;
      v32 = v50;
    }
    v33 = 0;
LABEL_85:
    if ( (v32 & 1) != 0 && v31 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v31 + 8LL))(v31);
    if ( v33 )
    {
      Dr::GetInkStateController(&v52, &v49);
      v34 = v52;
      if ( v52 )
      {
        (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v52 + 136LL))(v52);
        if ( (int)OInk::Haptics::IHapticsController::TryPlayHapticForPenPointer(v35, 7, v36, 25000000) < 0 )
          MsoShipAssertTagProc(545386965);
        (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v34 + 8LL))(v34);
      }
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v49);
  }
  Ofc::TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>::~TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>(&v60);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  return 0;
}

```

## disassembly

```asm
0x18080e5e0  mov     rax, rsp
0x18080e5e3  mov     [rax+10h], rbx
0x18080e5e7  mov     [rax+18h], rsi
0x18080e5eb  mov     [rax+20h], rdi
0x18080e5ef  push    rbp
0x18080e5f0  push    r12
0x18080e5f2  push    r13
0x18080e5f4  push    r14
0x18080e5f6  push    r15
0x18080e5f8  lea     rbp, [rsp-70h]
0x18080e5fd  sub     rsp, 170h
0x18080e604  movaps  xmmword ptr [rax-38h], xmm6
0x18080e608  mov     rax, cs:__security_cookie
0x18080e60f  xor     rax, rsp
0x18080e612  mov     [rbp+90h+var_38], rax
0x18080e616  mov     r15, rcx
0x18080e619  xor     r14d, r14d
0x18080e61c  mov     [rbp+90h+var_F8], r14d
0x18080e620  mov     [rbp+90h+var_108], r14
0x18080e624  mov     rcx, [rcx+10h]
0x18080e628  mov     rax, [rcx]
0x18080e62b  lea     r8, [rbp+90h+var_108]
0x18080e62f  lea     rdx, ?GUID_CNT_INKDRAWING@@3U_GUID@@B; _GUID const GUID_CNT_INKDRAWING
0x18080e636  mov     rax, [rax+178h]
0x18080e63d  call    cs:__guard_dispatch_icall_fptr
0x18080e643  mov     esi, eax
0x18080e645  mov     [rsp+190h+var_120], r14d
0x18080e64a  test    eax, eax
0x18080e64c  js      short loc_18080E66E
0x18080e64e  mov     rcx, [rbp+90h+var_108]
0x18080e652  mov     rax, [rcx]
0x18080e655  lea     rdx, [rsp+190h+var_120]
0x18080e65a  mov     rax, [rax+18h]
0x18080e65e  call    cs:__guard_dispatch_icall_fptr
0x18080e664  mov     esi, eax
0x18080e666  mov     eax, [rsp+190h+var_120]
0x18080e66a  test    eax, eax
0x18080e66c  jnz     short loc_18080E67A
0x18080e66e  mov     rcx, r15; this
0x18080e671  call    ?DisplayErrorOOUI@IAPerformer@Dr@@QEAAXXZ; Dr::IAPerformer::DisplayErrorOOUI(void)
0x18080e676  mov     eax, [rsp+190h+var_120]
0x18080e67a  mov     [rsp+190h+var_150], r14b
0x18080e67f  mov     [rbp+90h+var_A0], 0Ch
0x18080e686  mov     [rbp+90h+var_9C], 7
0x18080e68d  mov     [rbp+90h+var_98], 0FFFFFFFFh
0x18080e694  mov     [rbp+90h+var_94], r14d
0x18080e698  mov     [rbp+90h+var_90], r14
0x18080e69c  lea     rcx, ??_7?$TMap@V?$TWeakPtr@VInkViewElement@Dr@@@Ofc@@V?$TArray@J@2@@Ofc@@6B@; const Ofc::TMap<Ofc::TWeakPtr<Dr::InkViewElement>,Ofc::TArray<long>>::`vftable'
0x18080e6a3  mov     [rbp+90h+var_A8], rcx
0x18080e6a7  mov     [rbp+90h+var_88], r14
0x18080e6ab  mov     [rbp+90h+var_80], r14d
0x18080e6af  mov     [rbp+90h+var_7C], 80000000h
0x18080e6b6  lea     r12d, [rax-1]
0x18080e6ba  lea     r13, [r15+20h]
0x18080e6be  xorps   xmm6, xmm6
0x18080e6c1  mov     rbx, r13
0x18080e6c4  test    esi, esi
0x18080e6c6  js      loc_18080EC17
0x18080e6cc  test    r12d, r12d
0x18080e6cf  js      loc_18080EC17
0x18080e6d5  mov     [rsp+190h+var_148], r14
0x18080e6da  mov     rcx, [rbp+90h+var_108]
0x18080e6de  mov     rax, [rcx]
0x18080e6e1  lea     r8, [rsp+190h+var_148]
0x18080e6e6  mov     edx, r12d
0x18080e6e9  mov     rax, [rax+20h]
0x18080e6ed  call    cs:__guard_dispatch_icall_fptr
0x18080e6f3  mov     esi, eax
0x18080e6f5  xorps   xmm0, xmm0
0x18080e6f8  movups  [rbp+90h+var_48], xmm0
0x18080e6fc  test    eax, eax
0x18080e6fe  js      short loc_18080E718
0x18080e700  mov     rcx, [rsp+190h+var_148]
0x18080e705  mov     rax, [rcx]
0x18080e708  lea     rdx, [rbp+90h+var_48]
0x18080e70c  mov     rax, [rax+18h]
0x18080e710  call    cs:__guard_dispatch_icall_fptr
0x18080e716  mov     esi, eax
0x18080e718  mov     rax, [r15]
0x18080e71b  lea     r8, [rbp+90h+var_48]
0x18080e71f  lea     rdx, [rbp+90h+var_78]
0x18080e723  mov     rcx, r15
0x18080e726  mov     rax, [rax+50h]
0x18080e72a  call    cs:__guard_dispatch_icall_fptr
0x18080e730  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x18080e733  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18080e738  mov     [rsp+190h+var_138], rax
0x18080e73d  lea     rcx, [rbp+90h+var_78]; struct Ofc::CProxyPtrImpl **
0x18080e741  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080e746  mov     rcx, [r15+20h]; this
0x18080e74a  call    ?FUseSynchronousIA@InkDocAnalyzer@Dr@@AEBA_NXZ; Dr::InkDocAnalyzer::FUseSynchronousIA(void)
0x18080e74f  test    al, al
0x18080e751  jnz     short loc_18080E762
0x18080e753  mov     rax, [rsp+190h+var_138]
0x18080e758  cmp     [rax+10h], r14
0x18080e75c  jz      loc_18080EB68
0x18080e762  mov     [rbp+90h+var_B8], r14
0x18080e766  lea     rcx, [rsp+190h+var_148]
0x18080e76b  call    ?GetOfficeShapeType@InkDocAnalyzerHelpers@Dr@@YA?AW4ShapeType@Art@@AEBV?$TCntPtr@UIContextNode@@@Ofc@@@Z; Dr::InkDocAnalyzerHelpers::GetOfficeShapeType(Ofc::TCntPtr<IContextNode> const &)
0x18080e770  mov     [rbp+90h+var_E0], eax
0x18080e773  cmp     eax, 0BBh
0x18080e778  jz      loc_18080EB58
0x18080e77e  mov     [rbp+90h+var_D8], 0
0x18080e786  lea     r8, [rbp+90h+var_D8+4]
0x18080e78a  lea     rdx, [rbp+90h+var_D8]
0x18080e78e  lea     rcx, [rsp+190h+var_148]
0x18080e793  call    ?FGetConnectorEndTypes@InkDocAnalyzerHelpers@Dr@@YA_NAEBV?$TCntPtr@UIContextNode@@@Ofc@@AEAW4LineEndType@Art@@1@Z; Dr::InkDocAnalyzerHelpers::FGetConnectorEndTypes(Ofc::TCntPtr<IContextNode> const &,Art::LineEndType &,Art::LineEndType &)
0x18080e798  mov     [rsp+190h+var_140], r14d
0x18080e79d  mov     rdi, r14
0x18080e7a0  mov     [rsp+190h+var_118], r14
0x18080e7a5  test    esi, esi
0x18080e7a7  js      short loc_18080E7DF
0x18080e7a9  cmp     [rbp+90h+var_E0], 0BBh
0x18080e7b0  jge     short loc_18080E7DF
0x18080e7b2  mov     rcx, [rsp+190h+var_148]
0x18080e7b7  mov     rax, [rcx]
0x18080e7ba  lea     r9, [rsp+190h+var_118]
0x18080e7bf  lea     r8, [rsp+190h+var_140]
0x18080e7c4  lea     rdx, ?GUID_CNP_ROTATIONANGLE@@3U_GUID@@B; _GUID const GUID_CNP_ROTATIONANGLE
0x18080e7cb  mov     rax, [rax+98h]
0x18080e7d2  call    cs:__guard_dispatch_icall_fptr
0x18080e7d8  mov     esi, eax
0x18080e7da  mov     rdi, [rsp+190h+var_118]
0x18080e7df  mov     [rbp+90h+var_50], rdi
0x18080e7e3  movsd   qword ptr [rbp+90h+var_D0.x], xmm6
0x18080e7e8  test    esi, esi
0x18080e7ea  js      short loc_18080E806
0x18080e7ec  test    rdi, rdi
0x18080e7ef  jz      short loc_18080E806
0x18080e7f1  movd    xmm0, dword ptr [rdi]
0x18080e7f5  cvtdq2pd xmm0, xmm0
0x18080e7f9  mulsd   xmm0, cs:__real@3f26e05a695f8295
0x18080e801  movsd   qword ptr [rbp+90h+var_D0.x], xmm0
0x18080e806  mov     [rsp+190h+var_140], r14d
0x18080e80b  xor     ebx, ebx
0x18080e80d  mov     [rsp+190h+var_118], rbx
0x18080e812  test    esi, esi
0x18080e814  js      short loc_18080E848
0x18080e816  mov     rcx, [rsp+190h+var_148]
0x18080e81b  mov     rax, [rcx]
0x18080e81e  lea     r9, [rsp+190h+var_118]
0x18080e823  lea     r8, [rsp+190h+var_140]
0x18080e828  lea     rdx, ?GUID_CNP_HOTPOINTS@@3U_GUID@@B; _GUID const GUID_CNP_HOTPOINTS
0x18080e82f  mov     rax, [rax+98h]
0x18080e836  call    cs:__guard_dispatch_icall_fptr
0x18080e83c  mov     esi, eax
0x18080e83e  mov     r14d, [rsp+190h+var_140]
0x18080e843  mov     rbx, [rsp+190h+var_118]
0x18080e848  mov     [rbp+90h+var_58], rbx
0x18080e84c  mov     [rbp+90h+var_C8], 0
0x18080e853  test    esi, esi
0x18080e855  js      loc_18080EB37
0x18080e85b  test    rbx, rbx
0x18080e85e  jz      loc_18080EB37
0x18080e864  shr     r14d, 3
0x18080e868  mov     [rbp+90h+var_C8], r14d
0x18080e86c  test    r14d, r14d
0x18080e86f  jz      loc_18080EB37
0x18080e875  mov     [rbp+90h+var_C0], rbx
0x18080e879  mov     ecx, [rbp+90h+var_E0]
0x18080e87c  call    ?FIsConnectorType@Art@@YA_NW4ShapeType@1@@Z; Art::FIsConnectorType(Art::ShapeType)
0x18080e881  test    al, al
0x18080e883  jnz     short loc_18080E89A
0x18080e885  cmp     [rbp+90h+var_E0], 5
0x18080e889  jz      short loc_18080E89A
0x18080e88b  lea     r8, [rbp+90h+var_D0]; struct tagPOINT *
0x18080e88f  mov     rdx, rbx; unsigned int
0x18080e892  mov     ecx, r14d; this
0x18080e895  call    ?ApplyShapeRotationBias@InkDocAnalyzerHelpers@Dr@@YAXIPEAUtagPOINT@@AEAN@Z; Dr::InkDocAnalyzerHelpers::ApplyShapeRotationBias(uint,tagPOINT *,double &)
0x18080e89a  xor     r14d, r14d
0x18080e89d  mov     [rsp+190h+var_11C], r14d
0x18080e8a2  mov     [rbp+90h+pv], r14
0x18080e8a6  mov     rcx, [rsp+190h+var_148]
0x18080e8ab  mov     rax, [rcx]
0x18080e8ae  lea     r8, [rbp+90h+pv]
0x18080e8b2  lea     rdx, [rsp+190h+var_11C]
0x18080e8b7  mov     rax, [rax+0C0h]
0x18080e8be  call    cs:__guard_dispatch_icall_fptr
0x18080e8c4  mov     esi, eax
0x18080e8c6  test    eax, eax
0x18080e8c8  js      loc_18080EB91
0x18080e8ce  mov     edx, [rsp+190h+var_11C]
0x18080e8d2  test    edx, edx
0x18080e8d4  jz      loc_18080EB91
0x18080e8da  mov     [rsp+190h+var_130], r14
0x18080e8df  mov     [rsp+190h+var_128], r14d
0x18080e8e4  mov     [rsp+190h+var_124], 80000000h
0x18080e8ec  mov     rax, [r15+20h]
0x18080e8f0  mov     rcx, [rax+28h]
0x18080e8f4  cmp     [rcx+10h], r14
0x18080e8f8  jz      loc_18080EA8A
0x18080e8fe  test    edx, edx
0x18080e900  jz      loc_18080EA87
0x18080e906  mov     r9, [r15+20h]
0x18080e90a  mov     r8d, r14d
0x18080e90d  mov     rcx, [r9+28h]
0x18080e911  mov     rdx, [rcx+10h]
0x18080e915  neg     rdx
0x18080e918  sbb     ecx, ecx
0x18080e91a  and     ecx, 3E8h
0x18080e920  mov     rax, [rbp+90h+pv]
0x18080e924  mov     eax, [rax+r8*4]
0x18080e928  cdq
0x18080e929  idiv    ecx
0x18080e92b  mov     esi, eax
0x18080e92d  lea     rdx, [rbp+90h+var_68]
0x18080e931  mov     rcx, r9
0x18080e934  call    ?GetPatriarch@InkDocAnalyzer@Dr@@QEBA?AV?$TWeakPtr@VGroupDrawingElement@Dr@@@Ofc@@XZ; Dr::InkDocAnalyzer::GetPatriarch(void)
0x18080e939  mov     r8, rax
0x18080e93c  mov     edx, esi
0x18080e93e  lea     rcx, [rbp+90h+var_70]
0x18080e942  call    ?GetDrawingElementFromId@NodeHelper@Dr@@SA?AV?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@IAEBV?$TWeakPtr@VGroupDrawingElement@Dr@@@4@@Z; Dr::NodeHelper::GetDrawingElementFromId(uint,Ofc::TWeakPtr<Dr::GroupDrawingElement> const &)
0x18080e947  mov     rcx, rax
0x18080e94a  call    ??$runtime_cast@VInkDrawingElement@Dr@@VDrawingElement@2@@Ofc@@YAAEBV?$TWeakPtr@VInkDrawingElement@Dr@@@0@AEBV?$TWeakPtr@VDrawingElement@Dr@@@0@@Z; Ofc::runtime_cast<Dr::InkDrawingElement,Dr::DrawingElement>(Ofc::TWeakPtr<Dr::DrawingElement> const &)
0x18080e94f  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x18080e952  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x18080e957  mov     [rbp+90h+var_100], rax
0x18080e95b  lea     rcx, [rbp+90h+var_70]; struct Ofc::CProxyPtrImpl **
0x18080e95f  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080e964  lea     rcx, [rbp+90h+var_68]; struct Ofc::CProxyPtrImpl **
0x18080e968  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080e96d  mov     rcx, [rbp+90h+var_100]; struct Ofc::CProxyPtrImpl *
0x18080e971  cmp     qword ptr [rcx+10h], 0
0x18080e976  jz      loc_18080EA64
0x18080e97c  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18080e981  mov     [rbp+90h+var_E8], rax
0x18080e985  cmp     qword ptr [rax+10h], 0
0x18080e98a  jz      loc_18080EA5A
0x18080e990  mov     rcx, rax; this
0x18080e993  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18080e998  lea     rcx, [rax+168h]
0x18080e99f  mov     rax, [rcx]
0x18080e9a2  lea     rdx, [rbp+90h+var_F0]
0x18080e9a6  mov     rax, [rax+88h]
0x18080e9ad  call    cs:__guard_dispatch_icall_fptr
0x18080e9b3  nop
0x18080e9b4  mov     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl *
0x18080e9b8  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18080e9bd  mov     [rbp+90h+var_60], rax
0x18080e9c1  mov     r8, [rsp+190h+var_130]
0x18080e9c6  mov     ecx, [rsp+190h+var_128]
0x18080e9ca  lea     r9, [r8+rcx*8]
0x18080e9ce  cmp     r8, r9
0x18080e9d1  jz      short loc_18080E9EB
0x18080e9d3  mov     rdx, [r8]
0x18080e9d6  mov     rcx, [rax+10h]
0x18080e9da  cmp     [rdx+10h], rcx
0x18080e9de  jz      short loc_18080E9E6
0x18080e9e0  add     r8, 8
0x18080e9e4  jmp     short loc_18080E9CE
0x18080e9e6  xor     sil, sil
0x18080e9e9  jmp     short loc_18080E9EE
0x18080e9eb  mov     sil, 1
0x18080e9ee  lea     rcx, [rbp+90h+var_60]; struct Ofc::CProxyPtrImpl **
0x18080e9f2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18080e9f7  test    sil, sil
0x18080e9fa  jz      short loc_18080EA50
0x18080e9fc  mov     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl *
0x18080ea00  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18080ea05  mov     [rbp+90h+var_B0], rax
0x18080ea09  lea     r8, ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18080ea10  mov     edx, 8; unsigned int
0x18080ea15  lea     rcx, [rsp+190h+var_130]; this
0x18080ea1a  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18080ea1f  mov     ecx, [rsp+190h+var_128]
0x18080ea23  mov     rax, [rsp+190h+var_130]
0x18080ea28  lea     rcx, [rax+rcx*8]; struct Ofc::CProxyPtrImpl **
0x18080ea2c  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x18080ea33  mov     [rcx], rax
0x18080ea36  inc     [rsp+190h+var_128]
0x18080ea3a  lea     rdx, [rbp+90h+var_B0]; struct Ofc::CProxyPtrImpl **
0x18080ea3e  call    ?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x18080ea43  lea     rcx, [rbp+90h+var_B0]; struct Ofc::CProxyPtrImpl **
0x18080ea47  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18080ea4c  nop
0x18080ea4d  nop     dword ptr [rax]
0x18080ea50  lea     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl **
0x18080ea54  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080ea59  nop
0x18080ea5a  lea     rcx, [rbp+90h+var_E8]; struct Ofc::CProxyPtrImpl **
0x18080ea5e  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18080ea63  nop
0x18080ea64  lea     rcx, [rbp+90h+var_100]; struct Ofc::CProxyPtrImpl **
0x18080ea68  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080ea6d  inc     r14d
0x18080ea70  cmp     r14d, [rsp+190h+var_11C]
0x18080ea75  jb      loc_18080E906
0x18080ea7b  xor     r14d, r14d
0x18080ea7e  cmp     [rsp+190h+var_128], r14d
0x18080ea83  jbe     short loc_18080EA8A
0x18080ea85  jmp     short loc_18080EAC8
0x18080ea87  xor     r14d, r14d
0x18080ea8a  mov     rsi, [r15+20h]
0x18080ea8e  lea     r8, ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18080ea95  mov     edx, 8; unsigned int
0x18080ea9a  lea     rcx, [rsp+190h+var_130]; this
0x18080ea9f  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x18080eaa4  mov     ecx, [rsp+190h+var_128]
0x18080eaa8  mov     rax, [rsp+190h+var_130]
0x18080eaad  lea     rcx, [rax+rcx*8]; struct Ofc::CProxyPtrImpl **
  ... truncated ...
```
