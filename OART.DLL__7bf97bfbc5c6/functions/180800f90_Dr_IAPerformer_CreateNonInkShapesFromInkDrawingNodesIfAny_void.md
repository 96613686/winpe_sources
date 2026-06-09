# Dr::IAPerformer::CreateNonInkShapesFromInkDrawingNodesIfAny(void)

- ea: `0x180800f90`
- end: `0x180801758`
- name: `?CreateNonInkShapesFromInkDrawingNodesIfAny@IAPerformer@Dr@@QEAAJXZ`
- size: `1992`
- prototype: `__int64 __fastcall(Dr::IAPerformer *__hidden this)`
- caller_count: `2`
- callee_count: `24`
- tags: `service_task`

## callers

- `0x18064ee70`
- `0x180828dc0`

## callees

- `0x180022c30`
- `0x1800317c0`
- `0x180070fe0`
- `0x180071720`
- `0x1800d0ab0`
- `0x1802b6bec`
- `0x180310c00`
- `0x1803a07e4`
- `0x1803a4020`
- `0x1803a4304`
- `0x18055ff24`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a59d4`
- `0x1806bce1c`
- `0x180800f90`
- `0x1808018b0`
- `0x180807840`
- `0x180807c50`
- `0x180808a18`
- `0x18080914c`
- `0x18080a1e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?HasHapticPenSupport@Haptics@OInk@@YA_NXZ` at `0x18080160a`
- `mso40uiWin32Client!__imp_?HasHapticPenSupport@Haptics@OInk@@YA_NXZ` at `0x18080160a`
- `mso40uiWin32Client!__imp_?TryPlayHapticForPenPointer@IHapticsController@Haptics@OInk@@SAJIW4WaveformId@23@NV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z` at `0x1808016d5`
- `mso40uiWin32Client!__imp_?TryPlayHapticForPenPointer@IHapticsController@Haptics@OInk@@SAJIW4WaveformId@23@NV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z` at `0x1808016d5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1808016e4`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1808016e4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080151c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180801583`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18080151c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180801583`
- `ole32!CoTaskMemFree` at `0x1808014e7`
- `ole32!CoTaskMemFree` at `0x1808014fd`
- `ole32!CoTaskMemFree` at `0x18080150c`
- `ole32!CoTaskMemFree` at `0x180801555`
- `ole32!CoTaskMemFree` at `0x180801564`
- `ole32!CoTaskMemFree` at `0x180801573`
- `ole32!CoTaskMemFree` at `0x1808014e7`
- `ole32!CoTaskMemFree` at `0x1808014fd`
- `ole32!CoTaskMemFree` at `0x18080150c`
- `ole32!CoTaskMemFree` at `0x180801555`
- `ole32!CoTaskMemFree` at `0x180801564`
- `ole32!CoTaskMemFree` at `0x180801573`

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
  __int64 v17; // rax
  volatile signed __int32 *v18; // rcx
  struct Ofc::CProxyPtrImpl *v19; // rax
  _QWORD *Checked; // rax
  struct Ofc::CProxyPtrImpl *v21; // rax
  __int64 j; // r8
  char v23; // si
  struct Ofc::CProxyPtrImpl **v24; // rcx
  __int64 v25; // rsi
  struct Ofc::CProxyPtrImpl **v26; // rcx
  void *v27; // rdx
  OInk::Haptics *v29; // rcx
  struct Ofc::CProxyPtrImpl *v30; // rax
  _QWORD *v31; // rax
  int *v32; // rbx
  char v33; // r14
  char v34; // di
  struct Ofc::CProxyPtrImpl *v35; // rbx
  unsigned int v36; // eax
  __int64 v37; // r8
  char v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  struct Ofc::CProxyPtrImpl *v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v43; // [rsp+68h] [rbp-98h]
  unsigned int v44; // [rsp+6Ch] [rbp-94h]
  int v45; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v46; // [rsp+74h] [rbp-8Ch] BYREF
  int *v47; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  struct Ofc::CProxyPtrImpl *v50; // [rsp+90h] [rbp-70h] BYREF
  int v51; // [rsp+98h] [rbp-68h]
  struct Ofc::CProxyPtrImpl *v52; // [rsp+A0h] [rbp-60h] BYREF
  struct Ofc::CProxyPtrImpl *v53; // [rsp+A8h] [rbp-58h] BYREF
  int OfficeShapeType; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPOINT v56; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v57; // [rsp+C8h] [rbp-38h]
  int *v58; // [rsp+D0h] [rbp-30h]
  Mso::Memory *v59; // [rsp+D8h] [rbp-28h]
  struct Ofc::CProxyPtrImpl *v60; // [rsp+E0h] [rbp-20h] BYREF
  void **v61; // [rsp+E8h] [rbp-18h] BYREF
  int v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+F4h] [rbp-Ch]
  int v64; // [rsp+F8h] [rbp-8h]
  int v65; // [rsp+FCh] [rbp-4h]
  __int64 v66; // [rsp+100h] [rbp+0h]
  __int64 v67; // [rsp+108h] [rbp+8h]
  int v68; // [rsp+110h] [rbp+10h]
  unsigned int v69; // [rsp+114h] [rbp+14h]
  struct Ofc::CProxyPtrImpl *v70; // [rsp+118h] [rbp+18h] BYREF
  struct Ofc::CProxyPtrImpl *v71; // [rsp+120h] [rbp+20h] BYREF
  struct Ofc::CProxyPtrImpl *v72; // [rsp+128h] [rbp+28h] BYREF
  struct Ofc::CProxyPtrImpl *v73; // [rsp+130h] [rbp+30h] BYREF
  int *v74; // [rsp+138h] [rbp+38h]
  int *v75; // [rsp+140h] [rbp+40h]
  __int128 v76; // [rsp+148h] [rbp+48h] BYREF

  v2 = 0;
  v51 = 0;
  v49 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**((_QWORD **)this + 2) + 376LL))(
         *((_QWORD *)this + 2),
         &GUID_CNT_INKDRAWING,
         &v49);
  v45 = 0;
  if ( v3 < 0 || (v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 24LL))(v49, &v45), (v4 = v45) == 0) )
  {
    Dr::IAPerformer::DisplayErrorOOUI(this);
    v4 = v45;
  }
  v38[0] = 0;
  v62 = 12;
  v63 = 7;
  v64 = -1;
  v65 = 0;
  v66 = 0;
  v61 = &Ofc::TMap<Ofc::TWeakPtr<Dr::InkViewElement>,Ofc::TArray<long>>::`vftable';
  v67 = 0;
  v68 = 0;
  v69 = 0x80000000;
  for ( i = v4 - 1; ; --i )
  {
    v6 = (Dr::InkDocAnalyzer **)((char *)this + 32);
    if ( v3 < 0 || i < 0 )
      break;
    v39 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 32LL))(v49, (unsigned int)i, &v39);
    v76 = 0;
    if ( v3 >= 0 )
      v3 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v39 + 24LL))(v39, &v76);
    v7 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(Dr::IAPerformer *, struct Ofc::CProxyPtrImpl **, __int128 *))(*(_QWORD *)this + 80LL))(
                                         this,
                                         &v70,
                                         &v76);
    v41 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v7);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v70);
    if ( Dr::InkDocAnalyzer::FUseSynchronousIA(*((Dr::InkDocAnalyzer **)this + 4)) || *((_QWORD *)v41 + 2) )
    {
      v59 = 0;
      OfficeShapeType = Dr::InkDocAnalyzerHelpers::GetOfficeShapeType(&v39);
      if ( OfficeShapeType != 187 )
      {
        v55 = 0;
        Dr::InkDocAnalyzerHelpers::FGetConnectorEndTypes(&v39, &v55, (char *)&v55 + 4);
        v40 = 0;
        v9 = 0;
        v47 = 0;
        if ( v3 >= 0 && OfficeShapeType < 187 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *, int **))(*(_QWORD *)v39 + 152LL))(
                 v39,
                 &GUID_CNP_ROTATIONANGLE,
                 &v40,
                 &v47);
          v9 = v47;
        }
        v75 = v9;
        *(double *)&v56 = 0.0;
        if ( v3 >= 0 && v9 )
          *(double *)&v56 = (double)*v9 * 0.00017453292519944;
        v40 = 0;
        v10 = 0;
        v47 = 0;
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(__int64, GUID *, unsigned int *, int **))(*(_QWORD *)v39 + 152LL))(
                 v39,
                 &GUID_CNP_HOTPOINTS,
                 &v40,
                 &v47);
          v2 = v40;
          v10 = v47;
        }
        v74 = v10;
        v57 = 0;
        if ( v3 >= 0 && v10 && (v11 = v2 >> 3, (v57 = v11) != 0) )
        {
          v58 = v10;
          if ( !(unsigned __int8)Art::FIsConnectorType((unsigned int)OfficeShapeType) && OfficeShapeType != 5 )
            Dr::InkDocAnalyzerHelpers::ApplyShapeRotationBias(
              (Dr::InkDocAnalyzerHelpers *)v11,
              (unsigned int)v10,
              &v56,
              v12);
          v2 = 0;
          v46 = 0;
          pv = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v39 + 192LL))(v39, &v46, &pv);
          if ( v13 < 0 || !v46 )
          {
            if ( pv )
              CoTaskMemFree(pv);
            CoTaskMemFree(v10);
            if ( v9 )
              CoTaskMemFree(v9);
            if ( v59 )
              Mso::Memory::Free(v59, v27);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v41);
            if ( v39 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            Ofc::TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>::~TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>(&v61);
            if ( v49 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            return (unsigned int)v13;
          }
          v42 = 0;
          v43 = 0;
          v44 = 0x80000000;
          if ( !*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL) + 16LL) )
            goto LABEL_45;
          do
          {
            v14 = *((_DWORD *)pv + v2)
                / (*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL) + 16LL) != 0 ? 0x3E8 : 0);
            Patriarch = Dr::InkDocAnalyzer::GetPatriarch(*((_QWORD *)this + 4), &v72);
            DrawingElementFromId = Dr::NodeHelper::GetDrawingElementFromId(&v71, v14, Patriarch);
            v17 = Ofc::runtime_cast<Dr::InkDrawingElement,Dr::DrawingElement>(DrawingElementFromId);
            v18 = *(volatile signed __int32 **)v17;
            if ( *(_DWORD *)(*(_QWORD *)v17 + 4LL) != 0x80000000 )
              _InterlockedIncrement(v18 + 1);
            v50 = (struct Ofc::CProxyPtrImpl *)v18;
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v71);
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v72);
            if ( *((_QWORD *)v50 + 2) )
            {
              v19 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v50);
              v53 = v19;
              if ( *((_QWORD *)v19 + 2) )
              {
                Checked = Ofc::CProxyPtrImpl::GetChecked(v19);
                (*(void (__fastcall **)(_QWORD *, struct Ofc::CProxyPtrImpl **))(Checked[45] + 136LL))(
                  Checked + 45,
                  &v52);
                v21 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v52);
                v73 = v21;
                for ( j = v42; j != v42 + 8LL * v43; j += 8 )
                {
                  if ( *(_QWORD *)(*(_QWORD *)j + 16LL) == *((_QWORD *)v21 + 2) )
                  {
                    v23 = 0;
                    goto LABEL_39;
                  }
                }
                v23 = 1;
LABEL_39:
                Ofc::CProxyPtrImpl::DtorStrongRelease(&v73);
                if ( v23 )
                {
                  v60 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v52);
                  Ofc::CArrayImpl::EnsureCapacityForOneElem(
                    (Ofc::CArrayImpl *)&v42,
                    8u,
                    (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do);
                  v24 = (struct Ofc::CProxyPtrImpl **)(v42 + 8LL * v43);
                  *v24 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
                  ++v43;
                  Ofc::CProxyPtrImpl::StrongMoveAssign(v24, &v60);
                  Ofc::CProxyPtrImpl::DtorStrongRelease(&v60);
                }
                Ofc::CProxyPtrImpl::DtorWeakRelease(&v52);
              }
              Ofc::CProxyPtrImpl::DtorStrongRelease(&v53);
            }
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v50);
            ++v2;
          }
          while ( v2 < v46 );
          v2 = 0;
          if ( !v43 )
          {
LABEL_45:
            v25 = *((_QWORD *)this + 4);
            Ofc::CArrayImpl::EnsureCapacityForOneElem(
              (Ofc::CArrayImpl *)&v42,
              8u,
              (void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int))Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do);
            v26 = (struct Ofc::CProxyPtrImpl **)(v42 + 8LL * v43);
            *v26 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
            ++v43;
            Ofc::CProxyPtrImpl::CheckedStrongAssign(v26, *(struct Ofc::CProxyPtrImpl **)(v25 + 88));
          }
          v3 = (*(__int64 (__fastcall **)(Dr::IAPerformer *, __int64 *, __int64 *, int *, struct Ofc::CProxyPtrImpl **, char *, void ***))(*(_QWORD *)this + 192LL))(
                 this,
                 &v39,
                 &v42,
                 &OfficeShapeType,
                 &v41,
                 v38,
                 &v61);
          if ( v3 >= 0 && v38[0] )
            *(_BYTE *)(*((_QWORD *)this + 4) + 24LL) = 1;
          Ofc::TArray<Ofc::TReferringPtr<Dr::ConnectorDrawingElement>>::~TArray<Ofc::TReferringPtr<Dr::ConnectorDrawingElement>>(&v42);
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
      if ( v59 )
        Mso::Memory::Free(v59, v8);
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v41);
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  Dr::IAPerformer::RemoveInk(this, &v61);
  if ( v3 < 0 || !v38[0] )
  {
    Dr::IAPerformer::DisplayErrorOOUI(this);
    v6 = (Dr::InkDocAnalyzer **)((char *)this + 32);
  }
  if ( Dr::InkDocAnalyzer::FUseSynchronousIA(*v6) )
    Dr::InkDocAnalyzer::ResetLastInsertInkDrawing(*v6);
  if ( OInk::Haptics::HasHapticPenSupport(v29) && v38[0] )
  {
    v30 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*((struct Ofc::CProxyPtrImpl **)*v6 + 4));
    v50 = v30;
    if ( *((_QWORD *)v30 + 2) )
    {
      v31 = Ofc::CProxyPtrImpl::GetChecked(v30);
      v32 = (int *)v31[83];
      if ( v32 )
        (**(void (__fastcall ***)(_QWORD))v32)(v31[83]);
      v33 = 1;
      if ( v32 )
      {
        v34 = 1;
        goto LABEL_87;
      }
    }
    else
    {
      v32 = v74;
      v33 = v51;
    }
    v34 = 0;
LABEL_87:
    if ( (v33 & 1) != 0 && v32 )
      (*(void (__fastcall **)(int *))(*(_QWORD *)v32 + 8LL))(v32);
    if ( v34 )
    {
      Dr::GetInkStateController(&v53, &v50);
      v35 = v53;
      if ( v53 )
      {
        (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v53 + 136LL))(v53);
        if ( (int)OInk::Haptics::IHapticsController::TryPlayHapticForPenPointer(v36, 7, v37, 25000000) < 0 )
          MsoShipAssertTagProc(545386965);
        (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *))(*(_QWORD *)v35 + 8LL))(v35);
      }
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v50);
  }
  Ofc::TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>::~TMap<Ofc::TWeakPtr<Art::IInkDrawing>,Ofc::TArray<long>>(&v61);
  if ( v49 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
  return 0;
}

```

## disassembly

```asm
0x180800f90  mov     rax, rsp
0x180800f93  mov     [rax+10h], rbx
0x180800f97  mov     [rax+18h], rsi
0x180800f9b  mov     [rax+20h], rdi
0x180800f9f  push    rbp
0x180800fa0  push    r12
0x180800fa2  push    r13
0x180800fa4  push    r14
0x180800fa6  push    r15
0x180800fa8  lea     rbp, [rsp-70h]
0x180800fad  sub     rsp, 170h
0x180800fb4  movaps  xmmword ptr [rax-38h], xmm6
0x180800fb8  mov     rax, cs:__security_cookie
0x180800fbf  xor     rax, rsp
0x180800fc2  mov     [rbp+90h+var_38], rax
0x180800fc6  mov     r15, rcx
0x180800fc9  xor     r14d, r14d
0x180800fcc  mov     [rbp+90h+var_F8], r14d
0x180800fd0  mov     [rbp+90h+var_108], r14
0x180800fd4  mov     rcx, [rcx+10h]
0x180800fd8  mov     rax, [rcx]
0x180800fdb  lea     r8, [rbp+90h+var_108]
0x180800fdf  lea     rdx, ?GUID_CNT_INKDRAWING@@3U_GUID@@B; _GUID const GUID_CNT_INKDRAWING
0x180800fe6  mov     rax, [rax+178h]
0x180800fed  call    cs:__guard_dispatch_icall_fptr
0x180800ff3  mov     esi, eax
0x180800ff5  mov     [rsp+190h+var_120], r14d
0x180800ffa  test    eax, eax
0x180800ffc  js      short loc_18080101E
0x180800ffe  mov     rcx, [rbp+90h+var_108]
0x180801002  mov     rax, [rcx]
0x180801005  lea     rdx, [rsp+190h+var_120]
0x18080100a  mov     rax, [rax+18h]
0x18080100e  call    cs:__guard_dispatch_icall_fptr
0x180801014  mov     esi, eax
0x180801016  mov     eax, [rsp+190h+var_120]
0x18080101a  test    eax, eax
0x18080101c  jnz     short loc_18080102A
0x18080101e  mov     rcx, r15; this
0x180801021  call    ?DisplayErrorOOUI@IAPerformer@Dr@@QEAAXXZ; Dr::IAPerformer::DisplayErrorOOUI(void)
0x180801026  mov     eax, [rsp+190h+var_120]
0x18080102a  mov     [rsp+190h+var_150], r14b
0x18080102f  mov     [rbp+90h+var_A0], 0Ch
0x180801036  mov     [rbp+90h+var_9C], 7
0x18080103d  mov     [rbp+90h+var_98], 0FFFFFFFFh
0x180801044  mov     [rbp+90h+var_94], r14d
0x180801048  mov     [rbp+90h+var_90], r14
0x18080104c  lea     rcx, ??_7?$TMap@V?$TWeakPtr@VInkViewElement@Dr@@@Ofc@@V?$TArray@J@2@@Ofc@@6B@; const Ofc::TMap<Ofc::TWeakPtr<Dr::InkViewElement>,Ofc::TArray<long>>::`vftable'
0x180801053  mov     [rbp+90h+var_A8], rcx
0x180801057  mov     [rbp+90h+var_88], r14
0x18080105b  mov     [rbp+90h+var_80], r14d
0x18080105f  mov     [rbp+90h+var_7C], 80000000h
0x180801066  lea     r12d, [rax-1]
0x18080106a  lea     r13, [r15+20h]
0x18080106e  xorps   xmm6, xmm6
0x180801071  mov     rbx, r13
0x180801074  test    esi, esi
0x180801076  js      loc_1808015D4
0x18080107c  test    r12d, r12d
0x18080107f  js      loc_1808015D4
0x180801085  mov     [rsp+190h+var_148], r14
0x18080108a  mov     rcx, [rbp+90h+var_108]
0x18080108e  mov     rax, [rcx]
0x180801091  lea     r8, [rsp+190h+var_148]
0x180801096  mov     edx, r12d
0x180801099  mov     rax, [rax+20h]
0x18080109d  call    cs:__guard_dispatch_icall_fptr
0x1808010a3  mov     esi, eax
0x1808010a5  xorps   xmm0, xmm0
0x1808010a8  movups  [rbp+90h+var_48], xmm0
0x1808010ac  test    eax, eax
0x1808010ae  js      short loc_1808010C8
0x1808010b0  mov     rcx, [rsp+190h+var_148]
0x1808010b5  mov     rax, [rcx]
0x1808010b8  lea     rdx, [rbp+90h+var_48]
0x1808010bc  mov     rax, [rax+18h]
0x1808010c0  call    cs:__guard_dispatch_icall_fptr
0x1808010c6  mov     esi, eax
0x1808010c8  mov     rax, [r15]
0x1808010cb  lea     r8, [rbp+90h+var_48]
0x1808010cf  lea     rdx, [rbp+90h+var_78]
0x1808010d3  mov     rcx, r15
0x1808010d6  mov     rax, [rax+50h]
0x1808010da  call    cs:__guard_dispatch_icall_fptr
0x1808010e0  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x1808010e3  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1808010e8  mov     [rsp+190h+var_138], rax
0x1808010ed  lea     rcx, [rbp+90h+var_78]; struct Ofc::CProxyPtrImpl **
0x1808010f1  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1808010f6  mov     rcx, [r15+20h]; this
0x1808010fa  call    ?FUseSynchronousIA@InkDocAnalyzer@Dr@@AEBA_NXZ; Dr::InkDocAnalyzer::FUseSynchronousIA(void)
0x1808010ff  test    al, al
0x180801101  jnz     short loc_180801112
0x180801103  mov     rax, [rsp+190h+var_138]
0x180801108  cmp     [rax+10h], r14
0x18080110c  jz      loc_180801523
0x180801112  mov     [rbp+90h+var_B8], r14
0x180801116  lea     rcx, [rsp+190h+var_148]
0x18080111b  call    ?GetOfficeShapeType@InkDocAnalyzerHelpers@Dr@@YA?AW4ShapeType@Art@@AEBV?$TCntPtr@UIContextNode@@@Ofc@@@Z; Dr::InkDocAnalyzerHelpers::GetOfficeShapeType(Ofc::TCntPtr<IContextNode> const &)
0x180801120  mov     [rbp+90h+var_E0], eax
0x180801123  cmp     eax, 0BBh
0x180801128  jz      loc_180801513
0x18080112e  mov     [rbp+90h+var_D8], 0
0x180801136  lea     r8, [rbp+90h+var_D8+4]
0x18080113a  lea     rdx, [rbp+90h+var_D8]
0x18080113e  lea     rcx, [rsp+190h+var_148]
0x180801143  call    ?FGetConnectorEndTypes@InkDocAnalyzerHelpers@Dr@@YA_NAEBV?$TCntPtr@UIContextNode@@@Ofc@@AEAW4LineEndType@Art@@1@Z; Dr::InkDocAnalyzerHelpers::FGetConnectorEndTypes(Ofc::TCntPtr<IContextNode> const &,Art::LineEndType &,Art::LineEndType &)
0x180801148  mov     [rsp+190h+var_140], r14d
0x18080114d  mov     rdi, r14
0x180801150  mov     [rsp+190h+var_118], r14
0x180801155  test    esi, esi
0x180801157  js      short loc_18080118F
0x180801159  cmp     [rbp+90h+var_E0], 0BBh
0x180801160  jge     short loc_18080118F
0x180801162  mov     rcx, [rsp+190h+var_148]
0x180801167  mov     rax, [rcx]
0x18080116a  lea     r9, [rsp+190h+var_118]
0x18080116f  lea     r8, [rsp+190h+var_140]
0x180801174  lea     rdx, ?GUID_CNP_ROTATIONANGLE@@3U_GUID@@B; _GUID const GUID_CNP_ROTATIONANGLE
0x18080117b  mov     rax, [rax+98h]
0x180801182  call    cs:__guard_dispatch_icall_fptr
0x180801188  mov     esi, eax
0x18080118a  mov     rdi, [rsp+190h+var_118]
0x18080118f  mov     [rbp+90h+var_50], rdi
0x180801193  movsd   qword ptr [rbp+90h+var_D0.x], xmm6
0x180801198  test    esi, esi
0x18080119a  js      short loc_1808011B6
0x18080119c  test    rdi, rdi
0x18080119f  jz      short loc_1808011B6
0x1808011a1  movd    xmm0, dword ptr [rdi]
0x1808011a5  cvtdq2pd xmm0, xmm0
0x1808011a9  mulsd   xmm0, cs:__real@3f26e05a695f8295
0x1808011b1  movsd   qword ptr [rbp+90h+var_D0.x], xmm0
0x1808011b6  mov     [rsp+190h+var_140], r14d
0x1808011bb  xor     ebx, ebx
0x1808011bd  mov     [rsp+190h+var_118], rbx
0x1808011c2  test    esi, esi
0x1808011c4  js      short loc_1808011F8
0x1808011c6  mov     rcx, [rsp+190h+var_148]
0x1808011cb  mov     rax, [rcx]
0x1808011ce  lea     r9, [rsp+190h+var_118]
0x1808011d3  lea     r8, [rsp+190h+var_140]
0x1808011d8  lea     rdx, ?GUID_CNP_HOTPOINTS@@3U_GUID@@B; _GUID const GUID_CNP_HOTPOINTS
0x1808011df  mov     rax, [rax+98h]
0x1808011e6  call    cs:__guard_dispatch_icall_fptr
0x1808011ec  mov     esi, eax
0x1808011ee  mov     r14d, [rsp+190h+var_140]
0x1808011f3  mov     rbx, [rsp+190h+var_118]
0x1808011f8  mov     [rbp+90h+var_58], rbx
0x1808011fc  mov     [rbp+90h+var_C8], 0
0x180801203  test    esi, esi
0x180801205  js      loc_1808014F2
0x18080120b  test    rbx, rbx
0x18080120e  jz      loc_1808014F2
0x180801214  shr     r14d, 3
0x180801218  mov     [rbp+90h+var_C8], r14d
0x18080121c  test    r14d, r14d
0x18080121f  jz      loc_1808014F2
0x180801225  mov     [rbp+90h+var_C0], rbx
0x180801229  mov     ecx, [rbp+90h+var_E0]
0x18080122c  call    ?FIsConnectorType@Art@@YA_NW4ShapeType@1@@Z; Art::FIsConnectorType(Art::ShapeType)
0x180801231  test    al, al
0x180801233  jnz     short loc_18080124A
0x180801235  cmp     [rbp+90h+var_E0], 5
0x180801239  jz      short loc_18080124A
0x18080123b  lea     r8, [rbp+90h+var_D0]; struct tagPOINT *
0x18080123f  mov     rdx, rbx; unsigned int
0x180801242  mov     ecx, r14d; this
0x180801245  call    ?ApplyShapeRotationBias@InkDocAnalyzerHelpers@Dr@@YAXIPEAUtagPOINT@@AEAN@Z; Dr::InkDocAnalyzerHelpers::ApplyShapeRotationBias(uint,tagPOINT *,double &)
0x18080124a  xor     r14d, r14d
0x18080124d  mov     [rsp+190h+var_11C], r14d
0x180801252  mov     [rbp+90h+pv], r14
0x180801256  mov     rcx, [rsp+190h+var_148]
0x18080125b  mov     rax, [rcx]
0x18080125e  lea     r8, [rbp+90h+pv]
0x180801262  lea     rdx, [rsp+190h+var_11C]
0x180801267  mov     rax, [rax+0C0h]
0x18080126e  call    cs:__guard_dispatch_icall_fptr
0x180801274  mov     esi, eax
0x180801276  test    eax, eax
0x180801278  js      loc_18080154C
0x18080127e  mov     edx, [rsp+190h+var_11C]
0x180801282  test    edx, edx
0x180801284  jz      loc_18080154C
0x18080128a  mov     [rsp+190h+var_130], r14
0x18080128f  mov     [rsp+190h+var_128], r14d
0x180801294  mov     [rsp+190h+var_124], 80000000h
0x18080129c  mov     rax, [r15+20h]
0x1808012a0  mov     rcx, [rax+28h]
0x1808012a4  cmp     [rcx+10h], r14
0x1808012a8  jz      loc_180801443
0x1808012ae  test    edx, edx
0x1808012b0  jz      loc_180801440
0x1808012b6  mov     r9, [r15+20h]
0x1808012ba  mov     r8d, r14d
0x1808012bd  mov     rcx, [r9+28h]
0x1808012c1  mov     rdx, [rcx+10h]
0x1808012c5  neg     rdx
0x1808012c8  sbb     ecx, ecx
0x1808012ca  and     ecx, 3E8h
0x1808012d0  mov     rax, [rbp+90h+pv]
0x1808012d4  mov     eax, [rax+r8*4]
0x1808012d8  cdq
0x1808012d9  idiv    ecx
0x1808012db  mov     esi, eax
0x1808012dd  lea     rdx, [rbp+90h+var_68]
0x1808012e1  mov     rcx, r9
0x1808012e4  call    ?GetPatriarch@InkDocAnalyzer@Dr@@QEBA?AV?$TWeakPtr@VGroupDrawingElement@Dr@@@Ofc@@XZ; Dr::InkDocAnalyzer::GetPatriarch(void)
0x1808012e9  mov     r8, rax
0x1808012ec  mov     edx, esi
0x1808012ee  lea     rcx, [rbp+90h+var_70]
0x1808012f2  call    ?GetDrawingElementFromId@NodeHelper@Dr@@SA?AV?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@IAEBV?$TWeakPtr@VGroupDrawingElement@Dr@@@4@@Z; Dr::NodeHelper::GetDrawingElementFromId(uint,Ofc::TWeakPtr<Dr::GroupDrawingElement> const &)
0x1808012f7  mov     rcx, rax
0x1808012fa  call    ??$runtime_cast@VInkDrawingElement@Dr@@VDrawingElement@2@@Ofc@@YAAEBV?$TWeakPtr@VInkDrawingElement@Dr@@@0@AEBV?$TWeakPtr@VDrawingElement@Dr@@@0@@Z; Ofc::runtime_cast<Dr::InkDrawingElement,Dr::DrawingElement>(Ofc::TWeakPtr<Dr::DrawingElement> const &)
0x1808012ff  mov     rcx, [rax]
0x180801302  mov     eax, [rcx+4]
0x180801305  cmp     eax, 80000000h
0x18080130a  jz      short loc_180801310
0x18080130c  lock inc dword ptr [rcx+4]
0x180801310  mov     [rbp+90h+var_100], rcx
0x180801314  lea     rcx, [rbp+90h+var_70]; struct Ofc::CProxyPtrImpl **
0x180801318  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x18080131d  lea     rcx, [rbp+90h+var_68]; struct Ofc::CProxyPtrImpl **
0x180801321  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180801326  mov     rcx, [rbp+90h+var_100]; struct Ofc::CProxyPtrImpl *
0x18080132a  cmp     qword ptr [rcx+10h], 0
0x18080132f  jz      loc_18080141D
0x180801335  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18080133a  mov     [rbp+90h+var_E8], rax
0x18080133e  cmp     qword ptr [rax+10h], 0
0x180801343  jz      loc_180801413
0x180801349  mov     rcx, rax; this
0x18080134c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180801351  lea     rcx, [rax+168h]
0x180801358  mov     rax, [rcx]
0x18080135b  lea     rdx, [rbp+90h+var_F0]
0x18080135f  mov     rax, [rax+88h]
0x180801366  call    cs:__guard_dispatch_icall_fptr
0x18080136c  nop
0x18080136d  nop     dword ptr [rax]
0x180801370  mov     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl *
0x180801374  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180801379  mov     [rbp+90h+var_60], rax
0x18080137d  mov     r8, [rsp+190h+var_130]
0x180801382  mov     ecx, [rsp+190h+var_128]
0x180801386  lea     r9, [r8+rcx*8]
0x18080138a  cmp     r8, r9
0x18080138d  jz      short loc_1808013A7
0x18080138f  mov     rdx, [r8]
0x180801392  mov     rcx, [rax+10h]
0x180801396  cmp     [rdx+10h], rcx
0x18080139a  jz      short loc_1808013A2
0x18080139c  add     r8, 8
0x1808013a0  jmp     short loc_18080138A
0x1808013a2  xor     sil, sil
0x1808013a5  jmp     short loc_1808013AA
0x1808013a7  mov     sil, 1
0x1808013aa  lea     rcx, [rbp+90h+var_60]; struct Ofc::CProxyPtrImpl **
0x1808013ae  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1808013b3  test    sil, sil
0x1808013b6  jz      short loc_180801409
0x1808013b8  mov     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl *
0x1808013bc  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1808013c1  mov     [rbp+90h+var_B0], rax
0x1808013c5  lea     r8, ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x1808013cc  mov     edx, 8; unsigned int
0x1808013d1  lea     rcx, [rsp+190h+var_130]; this
0x1808013d6  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
0x1808013db  mov     ecx, [rsp+190h+var_128]
0x1808013df  mov     rax, [rsp+190h+var_130]
0x1808013e4  lea     rcx, [rax+rcx*8]; struct Ofc::CProxyPtrImpl **
0x1808013e8  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1808013ef  mov     [rcx], rax
0x1808013f2  inc     [rsp+190h+var_128]
0x1808013f6  lea     rdx, [rbp+90h+var_B0]; struct Ofc::CProxyPtrImpl **
0x1808013fa  call    ?StrongMoveAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@0@Z; Ofc::CProxyPtrImpl::StrongMoveAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl * *)
0x1808013ff  lea     rcx, [rbp+90h+var_B0]; struct Ofc::CProxyPtrImpl **
0x180801403  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180801408  nop
0x180801409  lea     rcx, [rbp+90h+var_F0]; struct Ofc::CProxyPtrImpl **
0x18080140d  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180801412  nop
0x180801413  lea     rcx, [rbp+90h+var_E8]; struct Ofc::CProxyPtrImpl **
0x180801417  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18080141c  nop
0x18080141d  lea     rcx, [rbp+90h+var_100]; struct Ofc::CProxyPtrImpl **
0x180801421  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180801426  inc     r14d
0x180801429  cmp     r14d, [rsp+190h+var_11C]
0x18080142e  jb      loc_1808012B6
0x180801434  xor     r14d, r14d
0x180801437  cmp     [rsp+190h+var_128], r14d
0x18080143c  jbe     short loc_180801443
0x18080143e  jmp     short loc_180801481
0x180801440  xor     r14d, r14d
0x180801443  mov     rsi, [r15+20h]
0x180801447  lea     r8, ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; void (*)(unsigned __int8 *, unsigned __int8 *, unsigned int)
0x18080144e  mov     edx, 8; unsigned int
0x180801453  lea     rcx, [rsp+190h+var_130]; this
0x180801458  call    ?EnsureCapacityForOneElem@CArrayImpl@Ofc@@AEAAXIP6AXPEAE0K@Z@Z; Ofc::CArrayImpl::EnsureCapacityForOneElem(uint,void (*)(uchar *,uchar *,ulong))
  ... truncated ...
```
