# ElementGestureTracker::ProcessPointerInformation(InputMessage const &,Windows::UI::Input::IPointerPointStatics * const)

- ea: `0x180009444`
- end: `0x180009af0`
- name: `?ProcessPointerInformation@ElementGestureTracker@@AEAAJAEBUInputMessage@@QEAUIPointerPointStatics@Input@UI@Windows@@@Z`
- size: `1708`
- prototype: `HRESULT __fastcall(ElementGestureTracker *this, const InputMessage *msg, Windows::UI::Input::IPointerPointStatics *const pointerPointStatics)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180009000`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x180009444`
- `0x180009af8`
- `0x180009b1c`
- `0x18000b6e8`
- `0x18001c368`
- `0x180045d64`
- `0x180057508`
- `0x1800ab600`
- `0x180131190`
- `0x1801332a8`
- `0x180155d80`
- `0x1801c8068`
- `0x1802134ac`
- `0x180615a30`
- `0x1806877a8`
- `0x180687890`
- `0x180688828`
- `0x18069f6ac`
- `0x1806c06e8`
- `0x1809cb544`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009977`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009999`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180009a43`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180009a43`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x18000979c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ScreenToClient` at `0x18000979c`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerFrameInfoHistory` at `0x1800094d0`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerFrameInfoHistory` at `0x18000950d`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerFrameInfoHistory` at `0x1800094d0`
- `api-ms-win-rtcore-ntuser-wmpointer-l1-1-0!GetPointerFrameInfoHistory` at `0x18000950d`
- `NInput!ProcessPointerFramesInteractionContext` at `0x18000961b`
- `NInput!ProcessPointerFramesInteractionContext` at `0x18000961b`
- `NInput!RemovePointerInteractionContext` at `0x180009764`
- `NInput!RemovePointerInteractionContext` at `0x1800098b0`
- `NInput!RemovePointerInteractionContext` at `0x1800098d4`
- `NInput!RemovePointerInteractionContext` at `0x18000991e`
- `NInput!RemovePointerInteractionContext` at `0x18000993e`
- `NInput!RemovePointerInteractionContext` at `0x1800099c9`
- `NInput!RemovePointerInteractionContext` at `0x180009764`
- `NInput!RemovePointerInteractionContext` at `0x1800098b0`
- `NInput!RemovePointerInteractionContext` at `0x1800098d4`
- `NInput!RemovePointerInteractionContext` at `0x18000991e`
- `NInput!RemovePointerInteractionContext` at `0x18000993e`
- `NInput!RemovePointerInteractionContext` at `0x1800099c9`
- `NInput!AddPointerInteractionContext` at `0x1800097f8`
- `NInput!AddPointerInteractionContext` at `0x1800097f8`

## pseudocode

```c
__int64 __fastcall ElementGestureTracker::ProcessPointerInformation(
        ElementGestureTracker *this,
        const InputMessage *msg,
        Windows::UI::Input::IPointerPointStatics *const pointerPointStatics)
{
  unsigned int v3; // r13d
  unsigned int m_pointerId; // r15d
  char *FailFast; // r14
  unsigned int m_frameId; // eax
  tagPOINT *v10; // rbx
  xref::details::control_block *m_ref_count; // rcx
  HRESULT (__fastcall *GetIntermediatePoints)(Windows::UI::Input::IPointerPointStatics *, unsigned int, Windows::Foundation::Collections::IVector<Windows::UI::Input::PointerPoint *> **); // rbx
  HRESULT v13; // eax
  HRESULT v14; // ebx
  signed int v15; // eax
  unsigned int v16; // r9d
  Windows::Foundation::Collections::IVector<Windows::UI::Input::PointerPoint *> *v17; // rcx
  Windows::UI::Input::IPointerPoint *m_pPointerPointWeak; // rcx
  HRESULT v20; // eax
  CPopup *v21; // rax
  signed int v22; // eax
  unsigned int v23; // r9d
  __m128 v24; // xmm6
  __m128 v25; // xmm7
  CPopup *v26; // rax
  LookupOptions v27; // edx
  HRESULT v28; // eax
  signed int v29; // eax
  unsigned int v30; // r9d
  bool v31; // zf
  Windows::Foundation::Collections::IVector<Windows::UI::Input::PointerPoint *> *ptr; // rcx
  signed int LastError; // eax
  signed int v34; // eax
  CContentRoot *ContentRootForElement; // rax
  float RasterizationScaleForContentRoot; // xmm0_4
  tagPOINT ptClient; // [rsp+20h] [rbp-40h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **pppStowedExceptions; // [rsp+28h] [rbp-38h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::UI::Input::PointerPoint *> > pointerPoints; // [rsp+A0h] [rbp+40h] BYREF
  xref_ptr<CBinding> uEntriesCount; // [rsp+A8h] [rbp+48h] BYREF
  CUIElement *v41; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  m_pointerId = msg->m_pointerInfo.m_pointerId;
  this->m_gestureOutputMapper->m_pointerInputType = msg->m_pointerInfo.m_pointerInputType;
  FailFast = 0;
  if ( !this->m_useTie )
  {
    switch ( msg->m_msgID )
    {
      case XCP_POINTERDOWN:
        m_pPointerPointWeak = msg->m_pPointerPointWeak;
        pointerPoints.ptr_ = 0;
        v20 = m_pPointerPointWeak->get_Position(m_pPointerPointWeak, (Windows::Foundation::Point *)&pointerPoints);
        v14 = v20;
        if ( v20 < 0 )
        {
          OnFailure_2990_(v20);
          goto LABEL_59;
        }
        v21 = xref::weakref_ptr<CScrollViewer>::lock_noref((xref::weakref_ptr<CPopup> *)this);
        if ( !v21
          || !CUIElement::IsPointerPositionOver(
                v21,
                (XPOINTF)*(_OWORD *)&_mm_unpacklo_ps(
                                       (__m128)LODWORD(pointerPoints.ptr_),
                                       (__m128)HIDWORD(pointerPoints.ptr_))) )
        {
          goto LABEL_22;
        }
        v22 = this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_->ProcessDownEvent(
                this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_,
                msg->m_pPointerPointWeak);
        v14 = v22;
        if ( v22 >= 0 || (MicrosoftTelemetryAssertTriggeredArgs(0, v22, 0, v23), v14 == -2147024809) )
        {
          ++this->m_cPointerInteractionContexts;
          goto LABEL_22;
        }
        break;
      case XCP_POINTERUP:
        v29 = this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_->ProcessUpEvent(
                this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_,
                msg->m_pPointerPointWeak);
        v14 = v29;
        if ( v29 >= 0 || (MicrosoftTelemetryAssertTriggeredArgs(0, v29, 0, v30), v14 == -2143289344) )
        {
          ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
          goto LABEL_22;
        }
        break;
      case XCP_POINTERUPDATE:
        m_ref_count = this->m_pElement.m_ref_count;
        pointerPoints.ptr_ = 0;
        uEntriesCount.m_ptr = 0;
        if ( m_ref_count && xref::details::control_block::AddStrong_nz(m_ref_count) )
          uEntriesCount.m_ptr = (CBinding *)this->m_pElement.m_ptr;
        xref_ptr<CUIElement>::~xref_ptr<CUIElement>(&uEntriesCount);
        GetIntermediatePoints = pointerPointStatics->GetIntermediatePoints;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&pointerPoints);
        v13 = GetIntermediatePoints(pointerPointStatics, m_pointerId, &pointerPoints.ptr_);
        v14 = v13;
        if ( v13 < 0 )
        {
          OnFailure_2990_(v13);
          ptr = pointerPoints.ptr_;
          if ( pointerPoints.ptr_ )
          {
            pointerPoints.ptr_ = 0;
            ptr->Release(ptr);
          }
          goto LABEL_59;
        }
        v15 = this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_->ProcessMoveEvents(
                this->m_gestureRecognizerAdapter.m_gestureRecognizer.ptr_,
                pointerPoints.ptr_);
        v14 = v15;
        if ( v15 >= 0
          || (MicrosoftTelemetryAssertTriggeredArgs(0, v15, 0, v16), v14 == -2143289344)
          || v14 == -2143289339 )
        {
          v17 = pointerPoints.ptr_;
          if ( pointerPoints.ptr_ )
          {
            pointerPoints.ptr_ = 0;
            v17->Release(v17);
          }
          goto LABEL_22;
        }
        OnFailure_2990_(v14);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&pointerPoints);
LABEL_59:
        if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
        {
          RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
          ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
        }
        if ( this->m_bDelayDestroyInteractionEngine )
          ElementGestureTracker::Destroy(this);
        return (unsigned int)v14;
      default:
        goto LABEL_22;
    }
    OnFailure_2990_(v14);
    goto LABEL_59;
  }
  if ( !this->m_tieAdapter.m_hInteractionEngine )
  {
    OnNewFailure_2955_((HRESULT)this);
    if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
    {
      RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
      ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
    }
    if ( this->m_bDelayDestroyInteractionEngine )
      ElementGestureTracker::Destroy(this);
    return 2147549183LL;
  }
  if ( !m_pointerId || (m_frameId = msg->m_pointerInfo.m_frameId, this->m_frameId == m_frameId) )
  {
LABEL_22:
    if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
    {
      RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
      ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
    }
    if ( this->m_bDelayDestroyInteractionEngine )
      ElementGestureTracker::Destroy(this);
    if ( FailFast )
      operator delete(FailFast);
    return 0;
  }
  this->m_frameId = m_frameId;
  LODWORD(uEntriesCount.m_ptr) = 0;
  pointerPoints.ptr_ = 0;
  if ( !(unsigned int)GetPointerFrameInfoHistory(m_pointerId, &uEntriesCount, &pointerPoints, 0, 0) )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    OnNewFailure_3049_(v14);
    goto LABEL_59;
  }
  FailFast = (char *)XcpAllocation::OSMemoryAllocateFailFast(saturated_mul((unsigned int)(LODWORD(uEntriesCount.m_ptr)
                                                                                        * LODWORD(pointerPoints.ptr_)), 0x60u));
  if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))GetPointerFrameInfoHistory)(
                        m_pointerId,
                        &uEntriesCount,
                        &pointerPoints,
                        FailFast,
                        ptClient) )
  {
    v34 = GetLastError();
    v14 = v34;
    if ( v34 > 0 )
      v14 = (unsigned __int16)v34 | 0x80070000;
    if ( v14 >= 0 )
      v14 = -2147467259;
    OnNewFailure_3049_(v14);
    if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
    {
      RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
      ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
    }
    v31 = !this->m_bDelayDestroyInteractionEngine;
LABEL_71:
    if ( !v31 )
      ElementGestureTracker::Destroy(this);
    if ( FailFast )
      operator delete(FailFast);
    return (unsigned int)v14;
  }
  while ( 1 )
  {
    if ( v3 >= LODWORD(uEntriesCount.m_ptr) * LODWORD(pointerPoints.ptr_) )
    {
      v14 = ProcessPointerFramesInteractionContext(
              this->m_tieAdapter.m_hInteractionEngine,
              LODWORD(uEntriesCount.m_ptr),
              LODWORD(pointerPoints.ptr_),
              FailFast);
      if ( (int)(v14 + 0x80000000) < 0 || v14 == -2143289344 )
        goto LABEL_22;
      OnFailure_2990_(v14);
      goto LABEL_69;
    }
    v10 = (tagPOINT *)&FailFast[96 * v3];
    if ( !v10 )
      break;
    if ( (v10[1].y & 0x10000) != 0 )
    {
      ptClient = v10[4];
      if ( !this->m_useTie )
      {
        pppStowedExceptions = 0;
        LODWORD(v41) = 0;
        TraceForFailFast(-2147418113);
        OnNewFailureEncountered(-2147418113, 0, 0);
        GetStowedExceptionsForFailFast(&pppStowedExceptions, (unsigned int *)&v41);
        RoFailFastWithErrorContextInternal2(-2147418113, (unsigned int)v41, pppStowedExceptions);
      }
      XamlOneCoreTransforms::FailFastIfEnabled();
      ScreenToClient((HWND)this->m_tieAdapter.m_hWnd, &ptClient);
      v24 = (__m128)COERCE_UNSIGNED_INT((float)ptClient.x);
      v25 = (__m128)COERCE_UNSIGNED_INT((float)ptClient.y);
      v26 = xref::weakref_ptr<CScrollViewer>::lock_noref((xref::weakref_ptr<CPopup> *)this);
      v41 = v26;
      if ( v26 )
      {
        if ( VisualTree::GetXamlIslandRootForElement(v26) )
        {
          ContentRootForElement = VisualTree::GetContentRootForElement(v41, v27);
          RasterizationScaleForContentRoot = RootScale::GetRasterizationScaleForContentRoot(ContentRootForElement);
          v24.m128_f32[0] = v24.m128_f32[0] / RasterizationScaleForContentRoot;
          v25.m128_f32[0] = v25.m128_f32[0] / RasterizationScaleForContentRoot;
        }
        if ( CUIElement::IsPointerPositionOver(v41, (XPOINTF)*(_OWORD *)&_mm_unpacklo_ps(v24, v25)) )
        {
          v28 = AddPointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, (unsigned int)v10->y);
          v14 = v28;
          if ( v28 < 0 )
          {
            OnFailure_2990_(v28);
LABEL_69:
            if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
            {
              RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
              ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
            }
            v31 = !this->m_bDelayDestroyInteractionEngine;
            goto LABEL_71;
          }
          ++this->m_cPointerInteractionContexts;
        }
      }
    }
    ++v3;
  }
  OnNewFailure_1172_(0);
  if ( msg->m_msgID == XCP_POINTERUP && this->m_useTie )
  {
    RemovePointerInteractionContext(this->m_tieAdapter.m_hInteractionEngine, m_pointerId);
    ElementGestureTracker::TryDecrementPointerInteractionContexts(this);
  }
  if ( this->m_bDelayDestroyInteractionEngine )
    ElementGestureTracker::Destroy(this);
  if ( FailFast )
    operator delete(FailFast);
  return 2147500035LL;
}

```

## disassembly

```asm
0x180009444  mov     [rsp-38h+arg_10], rbx
0x180009449  push    rbp
0x18000944a  push    rsi
0x18000944b  push    rdi
0x18000944c  push    r12
0x18000944e  push    r13
0x180009450  push    r14
0x180009452  push    r15
0x180009454  mov     rbp, rsp
0x180009457  sub     rsp, 60h
0x18000945b  mov     r9, [this+118h]
0x180009462  xor     r13d, r13d
0x180009465  mov     r15d, [msg+64h]
0x180009469  mov     r12, pointerPointStatics
0x18000946c  mov     eax, [msg+60h]
0x18000946f  mov     rsi, msg
0x180009472  movaps  [rsp+60h+var_10], xmm6
0x180009477  mov     rdi, this
0x18000947a  mov     [r9+4], eax
0x18000947e  mov     r14d, r13d
0x180009481  movaps  [rsp+60h+var_20], xmm7
0x180009486  cmp     [this+28h], r13b
0x18000948a  jz      loc_180009559
0x180009490  cmp     [this+38h], r13
0x180009494  jz      loc_180009730
0x18000949a  test    r15d, r15d
0x18000949d  jz      loc_180009636
0x1800094a3  mov     eax, [msg+68h]
0x1800094a6  cmp     [this+14h], eax
0x1800094a9  jz      loc_180009636
0x1800094af  mov     [this+14h], eax
0x1800094b2  lea     pointerPointStatics, [rbp+pointerPoints]
0x1800094b6  mov     [rbp+pointerPoints.ptr_], r13
0x1800094ba  lea     msg, [rbp+uEntriesCount]
0x1800094be  mov     ecx, r15d
0x1800094c1  mov     qword ptr [rbp+ptClient.x], r13
0x1800094c5  xor     r9d, r9d
0x1800094c8  mov     dword ptr [rbp+uEntriesCount], r13d
0x1800094cc  mov     dword ptr [rbp+pointerPoints.ptr_], r13d
0x1800094d0  call    cs:__imp_GetPointerFrameInfoHistory
0x1800094d6  test    eax, eax
0x1800094d8  jz      loc_180009977
0x1800094de  mov     ecx, dword ptr [rbp+pointerPoints.ptr_]
0x1800094e1  lea     eax, [r13+60h]
0x1800094e5  imul    ecx, dword ptr [rbp+uEntriesCount]
0x1800094e9  mul     this
0x1800094ec  lea     this, [r13-1]
0x1800094f0  cmovb   rax, this
0x1800094f4  mov     this, rax; cSize
0x1800094f7  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1800094fc  mov     r9, rax
0x1800094ff  lea     pointerPointStatics, [rbp+pointerPoints]
0x180009503  lea     msg, [rbp+uEntriesCount]
0x180009507  mov     ecx, r15d
0x18000950a  mov     r14, rax
0x18000950d  call    cs:__imp_GetPointerFrameInfoHistory
0x180009513  test    eax, eax
0x180009515  jz      loc_180009999
0x18000951b  mov     r12d, 8000FFFFh
0x180009521  mov     eax, dword ptr [rbp+pointerPoints.ptr_]
0x180009524  imul    eax, dword ptr [rbp+uEntriesCount]
0x180009528  cmp     r13d, eax
0x18000952b  jnb     loc_18000960D
0x180009531  mov     eax, r13d
0x180009534  xor     ecx, ecx; failedFrameHR
0x180009536  lea     rbx, [rax+rax*2]
0x18000953a  shl     rbx, 5
0x18000953e  add     rbx, r14
0x180009541  jz      loc_180009700
0x180009547  test    dword ptr [rbx+0Ch], 10000h
0x18000954e  jnz     loc_180009777
0x180009554  inc     r13d
0x180009557  jmp     short loc_180009521
0x180009559  cmp     dword ptr [msg+2Ch], 1Ah
0x18000955d  jz      loc_18000967B
0x180009563  cmp     dword ptr [msg+2Ch], 1Ch
0x180009567  jz      loc_180009828
0x18000956d  cmp     dword ptr [msg+2Ch], 1Bh
0x180009571  jnz     loc_180009636
0x180009577  mov     this, [this+8]; this
0x18000957b  mov     [rbp+pointerPoints.ptr_], r13
0x18000957f  mov     [rbp+uEntriesCount], r13
0x180009583  test    this, this
0x180009586  jz      short loc_180009598
0x180009588  call    ?AddStrong_nz@control_block@details@xref@@QEAA_NXZ; xref::details::control_block::AddStrong_nz(void)
0x18000958d  test    al, al
0x18000958f  jz      short loc_180009598
0x180009591  mov     rax, [rdi]
0x180009594  mov     [rbp+uEntriesCount], rax
0x180009598  lea     this, [rbp+uEntriesCount]; this
0x18000959c  call    ??1?$xref_ptr@VCUIElement@@@@QEAA@XZ; xref_ptr<CUIElement>::~xref_ptr<CUIElement>(void)
0x1800095a1  mov     rax, [r12]
0x1800095a5  lea     this, [rbp+pointerPoints]; this
0x1800095a9  mov     rbx, [rax+38h]
0x1800095ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800095b2  lea     pointerPointStatics, [rbp+pointerPoints]
0x1800095b6  mov     edx, r15d
0x1800095b9  mov     this, r12
0x1800095bc  mov     rax, rbx
0x1800095bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c4  mov     ebx, eax
0x1800095c6  test    eax, eax
0x1800095c8  js      loc_18000994E
0x1800095ce  mov     this, [rdi+0D0h]
0x1800095d5  mov     msg, [rbp+pointerPoints.ptr_]
0x1800095d9  mov     rax, [this]
0x1800095dc  mov     rax, [rax+148h]
0x1800095e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e8  mov     ebx, eax
0x1800095ea  test    eax, eax
0x1800095ec  js      loc_180009AAA
0x1800095f2  mov     this, [rbp+pointerPoints.ptr_]
0x1800095f6  test    this, this
0x1800095f9  jz      short loc_180009636
0x1800095fb  mov     [rbp+pointerPoints.ptr_], r13
0x1800095ff  mov     rax, [this]
0x180009602  mov     rax, [rax+10h]
0x180009606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000960b  jmp     short loc_180009636
0x18000960d  mov     r8d, dword ptr [rbp+pointerPoints.ptr_]
0x180009611  mov     r9, r14
0x180009614  mov     edx, dword ptr [rbp+uEntriesCount]
0x180009617  mov     this, [rdi+38h]
0x18000961b  call    cs:__imp_ProcessPointerFramesInteractionContext
0x180009621  mov     ebx, eax
0x180009623  mov     eax, 80000000h
0x180009628  lea     ecx, [rbx+rax]
0x18000962b  test    eax, ecx
0x18000962d  jz      loc_180009810
0x180009633  xor     r13d, r13d
0x180009636  cmp     dword ptr [rsi+2Ch], 1Ch
0x18000963a  jz      loc_180009753
0x180009640  cmp     [rdi+22h], r13b
0x180009644  jnz     loc_180009AE3
0x18000964a  test    r14, r14
0x18000964d  jz      short loc_180009657
0x18000964f  mov     this, r14; pAddress
0x180009652  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009657  xor     eax, eax
0x180009659  mov     rbx, [rsp+60h+arg_10]
0x180009661  movaps  xmm6, [rsp+60h+var_10]
0x180009666  movaps  xmm7, [rsp+60h+var_20]
0x18000966b  add     rsp, 60h
0x18000966f  pop     r15
0x180009671  pop     r14
0x180009673  pop     r13
0x180009675  pop     r12
0x180009677  pop     rdi
0x180009678  pop     rsi
0x180009679  pop     rbp
0x18000967a  retn
0x18000967b  mov     this, [msg+90h]
0x180009682  xor     eax, eax
0x180009684  mov     [rbp+pointerPoints.ptr_], rax
0x180009688  lea     msg, [rbp+pointerPoints]
0x18000968c  mov     rax, [this]
0x18000968f  mov     rax, [rax+38h]
0x180009693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009698  mov     ebx, eax
0x18000969a  test    eax, eax
0x18000969c  js      loc_180009896
0x1800096a2  mov     this, rdi; this
0x1800096a5  call    ?lock_noref@?$weakref_ptr@VCScrollViewer@@@xref@@QEBAPEAVCScrollViewer@@XZ; xref::weakref_ptr<CScrollViewer>::lock_noref(void)
0x1800096aa  test    rax, rax
0x1800096ad  jz      short loc_180009636
0x1800096af  movss   xmm1, dword ptr [rbp+pointerPoints.ptr_]
0x1800096b4  mov     this, rax; this
0x1800096b7  movss   xmm0, dword ptr [rbp+pointerPoints.ptr_+4]
0x1800096bc  unpcklps xmm1, xmm0
0x1800096bf  movq    msg, xmm1; pointPosition
0x1800096c4  call    ?IsPointerPositionOver@CUIElement@@QEAA_NUXPOINTF@@@Z; CUIElement::IsPointerPositionOver(XPOINTF)
0x1800096c9  test    al, al
0x1800096cb  jz      loc_180009636
0x1800096d1  mov     this, [rdi+0D0h]
0x1800096d8  mov     msg, [rsi+90h]
0x1800096df  mov     rax, [this]
0x1800096e2  mov     rax, [rax+140h]
0x1800096e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096ee  mov     ebx, eax
0x1800096f0  test    eax, eax
0x1800096f2  js      loc_18000985C
0x1800096f8  inc     dword ptr [rdi+18h]
0x1800096fb  jmp     loc_180009636
0x180009700  call    OnNewFailure_1172_
0x180009705  cmp     dword ptr [rsi+2Ch], 1Ch
0x180009709  jz      loc_18000989F
0x18000970f  cmp     byte ptr [rdi+22h], 0
0x180009713  jnz     loc_180009A6C
0x180009719  test    r14, r14
0x18000971c  jz      short loc_180009726
0x18000971e  mov     this, r14; pAddress
0x180009721  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009726  mov     eax, 80004003h
0x18000972b  jmp     loc_180009659
0x180009730  call    OnNewFailure_2955_
0x180009735  cmp     dword ptr [rsi+2Ch], 1Ch
0x180009739  jz      loc_1800098C3
0x18000973f  cmp     [rdi+22h], r13b
0x180009743  jnz     loc_180009A79
0x180009749  mov     eax, 8000FFFFh
0x18000974e  jmp     loc_180009659
0x180009753  cmp     [rdi+28h], r13b
0x180009757  jz      loc_180009640
0x18000975d  mov     this, [rdi+38h]
0x180009761  mov     edx, r15d
0x180009764  call    cs:__imp_RemovePointerInteractionContext
0x18000976a  mov     this, rdi; this
0x18000976d  call    ?TryDecrementPointerInteractionContexts@ElementGestureTracker@@AEAAXXZ; ElementGestureTracker::TryDecrementPointerInteractionContexts(void)
0x180009772  jmp     loc_180009640
0x180009777  mov     eax, [rbx+20h]
0x18000977a  mov     [rbp+ptClient.x], eax
0x18000977d  mov     eax, [rbx+24h]
0x180009780  mov     [rbp+ptClient.y], eax
0x180009783  cmp     [rdi+28h], cl
0x180009786  jz      loc_180009A10
0x18000978c  call    ?FailFastIfEnabled@XamlOneCoreTransforms@@SAXXZ; XamlOneCoreTransforms::FailFastIfEnabled(void)
0x180009791  mov     this, [rdi+0B8h]; hWnd
0x180009798  lea     msg, [rbp+ptClient]; lpPoint
0x18000979c  call    cs:__imp_ScreenToClient
0x1800097a2  movd    xmm6, [rbp+ptClient.x]
0x1800097a7  mov     this, rdi; this
0x1800097aa  movd    xmm7, [rbp+ptClient.y]
0x1800097af  cvtdq2ps xmm6, xmm6
0x1800097b2  cvtdq2ps xmm7, xmm7
0x1800097b5  call    ?lock_noref@?$weakref_ptr@VCScrollViewer@@@xref@@QEBAPEAVCScrollViewer@@XZ; xref::weakref_ptr<CScrollViewer>::lock_noref(void)
0x1800097ba  mov     [rbp+arg_18], rax
0x1800097be  test    rax, rax
0x1800097c1  jz      loc_180009554
0x1800097c7  mov     this, rax; pObject
0x1800097ca  call    ?GetXamlIslandRootForElement@VisualTree@@SAPEAVCXamlIslandRoot@@PEAVCDependencyObject@@@Z; VisualTree::GetXamlIslandRootForElement(CDependencyObject *)
0x1800097cf  test    rax, rax
0x1800097d2  jnz     loc_180009A4E
0x1800097d8  mov     this, [rbp+arg_18]; this
0x1800097dc  unpcklps xmm6, xmm7
0x1800097df  movq    msg, xmm6; pointPosition
0x1800097e4  call    ?IsPointerPositionOver@CUIElement@@QEAA_NUXPOINTF@@@Z; CUIElement::IsPointerPositionOver(XPOINTF)
0x1800097e9  test    al, al
0x1800097eb  jz      loc_180009554
0x1800097f1  mov     edx, [rbx+4]
0x1800097f4  mov     this, [rdi+38h]
0x1800097f8  call    cs:__imp_AddPointerInteractionContext
0x1800097fe  mov     ebx, eax
0x180009800  test    eax, eax
0x180009802  js      loc_1800098E7
0x180009808  inc     dword ptr [rdi+18h]
0x18000980b  jmp     loc_180009554
0x180009810  cmp     ebx, 80400000h
0x180009816  jz      loc_180009633
0x18000981c  mov     ecx, ebx; failedFrameHR
0x18000981e  call    OnFailure_2990_
0x180009823  jmp     loc_1800098EE
0x180009828  mov     this, [this+0D0h]
0x18000982f  mov     msg, [msg+90h]
0x180009836  mov     rax, [this]
0x180009839  mov     rax, [rax+150h]
0x180009840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009845  mov     ebx, eax
0x180009847  test    eax, eax
0x180009849  js      loc_180009A86
0x18000984f  mov     this, rdi; this
0x180009852  call    ?TryDecrementPointerInteractionContexts@ElementGestureTracker@@AEAAXXZ; ElementGestureTracker::TryDecrementPointerInteractionContexts(void)
0x180009857  jmp     loc_180009636
0x18000985c  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(processDownEventsHR)")
0x18000985f  mov     edx, ebx; BucketArg1
0x180009861  xor     ecx, ecx; OriginatingBinary
0x180009863  call    MicrosoftTelemetryAssertTriggeredArgs
0x180009868  cmp     ebx, 80070057h
0x18000986e  jz      loc_1800096F8
0x180009874  mov     ecx, ebx; failedFrameHR
0x180009876  call    OnFailure_2990_
0x18000987b  cmp     dword ptr [rsi+2Ch], 1Ch
0x18000987f  jz      loc_18000990D
0x180009885  cmp     [rdi+22h], r13b
0x180009889  jnz     loc_1800099EB
0x18000988f  mov     eax, ebx
0x180009891  jmp     loc_180009659
0x180009896  mov     ecx, ebx; failedFrameHR
0x180009898  call    OnFailure_2990_
0x18000989d  jmp     short loc_18000987B
0x18000989f  cmp     byte ptr [rdi+28h], 0
0x1800098a3  jz      loc_18000970F
0x1800098a9  mov     this, [rdi+38h]
0x1800098ad  mov     edx, r15d
0x1800098b0  call    cs:__imp_RemovePointerInteractionContext
0x1800098b6  mov     this, rdi; this
0x1800098b9  call    ?TryDecrementPointerInteractionContexts@ElementGestureTracker@@AEAAXXZ; ElementGestureTracker::TryDecrementPointerInteractionContexts(void)
0x1800098be  jmp     loc_18000970F
0x1800098c3  cmp     [rdi+28h], r13b
0x1800098c7  jz      loc_18000973F
0x1800098cd  mov     this, [rdi+38h]
0x1800098d1  mov     edx, r15d
0x1800098d4  call    cs:__imp_RemovePointerInteractionContext
0x1800098da  mov     this, rdi; this
0x1800098dd  call    ?TryDecrementPointerInteractionContexts@ElementGestureTracker@@AEAAXXZ; ElementGestureTracker::TryDecrementPointerInteractionContexts(void)
0x1800098e2  jmp     loc_18000973F
0x1800098e7  mov     ecx, ebx; failedFrameHR
0x1800098e9  call    OnFailure_2990_
0x1800098ee  cmp     dword ptr [rsi+2Ch], 1Ch
0x1800098f2  jz      short loc_180009931
0x1800098f4  cmp     byte ptr [rdi+22h], 0
  ... truncated ...
```
