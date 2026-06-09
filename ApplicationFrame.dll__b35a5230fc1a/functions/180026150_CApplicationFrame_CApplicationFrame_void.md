# CApplicationFrame::CApplicationFrame(void)

- ea: `0x180026150`
- end: `0x1800263af`
- name: `??0CApplicationFrame@@QEAA@XZ`
- size: `607`
- prototype: `CApplicationFrame *__fastcall(CApplicationFrame *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800263d0`

## callees

- `0x180027aa8`
- `0x180027b60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800261fa`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800261fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800261df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800261df`
- `SHCORE!SHGetThreadRef` at `0x180026175`
- `SHCORE!SHGetThreadRef` at `0x180026175`

## string_xrefs

- `0x180026215`: `MoveSizeLoop`

## pseudocode

```c
CApplicationFrame *__fastcall CApplicationFrame::CApplicationFrame(CApplicationFrame *this)
{
  IUnknown **v2; // rcx
  CApplicationFrame *result; // rax

  *(_QWORD *)this = &CThreadRefTaker::`vftable';
  v2 = (IUnknown **)((char *)this + 8);
  *v2 = 0;
  SHGetThreadRef(v2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = &CWRLImpWndProc<CApplicationFrame>::`vftable';
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>((char *)this + 32);
  *(_QWORD *)this = &CApplicationFrame::`vftable'{for `CThreadRefTaker'};
  *((_QWORD *)this + 2) = &CApplicationFrame::`vftable'{for `CWRLImpWndProc<CApplicationFrame>'};
  *((_QWORD *)this + 4) = &CApplicationFrame::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 5) = &CApplicationFrame::`vftable'{for `Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 6) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IDCompProvider,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 7) = &CApplicationFrame::`vftable'{for `IDCompProvider'};
  *((_QWORD *)this + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_DWORD *)this + 28) = GetCurrentThreadId();
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  InitializeSRWLock((PSRWLOCK)this + 17);
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 1;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_BYTE *)this + 312) = 0;
  *(_QWORD *)((char *)this + 316) = 0;
  *(_QWORD *)((char *)this + 324) = 0;
  *((_DWORD *)this + 83) = -1;
  *((_DWORD *)this + 84) = -1;
  *((_DWORD *)this + 86) = 100;
  *((_DWORD *)this + 87) = 100;
  *((_QWORD *)this + 44) = 0x3FF0000000000000LL;
  *((_BYTE *)this + 340) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_WORD *)this + 182) = 0;
  *((_DWORD *)this + 92) = 0;
  wil::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((CApplicationFrame *)((char *)this + 376));
  *((_QWORD *)this + 47) = &CApplicationFrameTelemetry::MoveSizeLoop::`vftable';
  *((_WORD *)this + 356) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  result = this;
  *((_QWORD *)this + 96) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 0;
  *((_QWORD *)this + 106) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  return result;
}

```

## disassembly

```asm
0x180026150  mov     [rsp+arg_0], rbx
0x180026155  mov     [rsp+arg_8], rsi
0x18002615a  push    rdi
0x18002615b  sub     rsp, 20h
0x18002615f  lea     rax, ??_7CThreadRefTaker@@6B@; const CThreadRefTaker::`vftable'
0x180026166  mov     rdi, rcx
0x180026169  mov     [rcx], rax
0x18002616c  xor     esi, esi
0x18002616e  add     rcx, 8; ppunk
0x180026172  mov     [rcx], rsi
0x180026175  call    cs:__imp_SHGetThreadRef
0x18002617b  lea     rax, ??_7?$CWRLImpWndProc@VCApplicationFrame@@@@6B@; const CWRLImpWndProc<CApplicationFrame>::`vftable'
0x180026182  mov     [rdi+18h], rsi
0x180026186  lea     rcx, [rdi+20h]
0x18002618a  mov     [rdi+10h], rax
0x18002618e  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>(void)
0x180026193  lea     rax, ??_7CApplicationFrame@@6BCThreadRefTaker@@@; const CApplicationFrame::`vftable'{for `CThreadRefTaker'}
0x18002619a  mov     [rdi], rax
0x18002619d  lea     rax, ??_7CApplicationFrame@@6B?$CWRLImpWndProc@VCApplicationFrame@@@@@; const CApplicationFrame::`vftable'{for `CWRLImpWndProc<CApplicationFrame>'}
0x1800261a4  mov     [rdi+10h], rax
0x1800261a8  lea     rax, ??_7CApplicationFrame@@6B?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@WRL@Microsoft@@@; const CApplicationFrame::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>'}
0x1800261af  mov     [rdi+20h], rax
0x1800261b3  lea     rax, ??_7CApplicationFrame@@6B?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CApplicationFrame::`vftable'{for `Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800261ba  mov     [rdi+28h], rax
0x1800261be  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIDCompProvider@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IDCompProvider,Microsoft::WRL::FtmBase>'}
0x1800261c5  mov     [rdi+30h], rax
0x1800261c9  lea     rax, ??_7CApplicationFrame@@6BIDCompProvider@@@; const CApplicationFrame::`vftable'{for `IDCompProvider'}
0x1800261d0  mov     [rdi+38h], rax
0x1800261d4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@U?$ChainInterfaces@UIApplicationFrameInternal@@UIApplicationFrame@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIDCompProvider@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::ChainInterfaces<IApplicationFrameInternal,IApplicationFrame,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDCompProvider,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800261db  mov     [rdi+40h], rax
0x1800261df  call    cs:__imp_GetCurrentThreadId
0x1800261e5  mov     [rdi+70h], eax
0x1800261e8  lea     rcx, [rdi+88h]; SRWLock
0x1800261ef  mov     [rdi+78h], rsi
0x1800261f3  mov     [rdi+80h], rsi
0x1800261fa  call    cs:__imp_InitializeSRWLock
0x180026200  mov     [rdi+90h], rsi
0x180026207  lea     rbx, [rdi+178h]
0x18002620e  mov     [rdi+98h], rsi
0x180026215  lea     rdx, aMovesizeloop; "MoveSizeLoop"
0x18002621c  mov     [rdi+0A0h], rsi
0x180026223  xor     eax, eax
0x180026225  mov     [rdi+0A8h], rsi
0x18002622c  mov     rcx, rbx; struct wil::details::IFailureCallback *
0x18002622f  mov     [rdi+0B0h], rsi
0x180026236  mov     [rdi+0B8h], rsi
0x18002623d  mov     [rdi+0C0h], rsi
0x180026244  mov     [rdi+0C8h], rsi
0x18002624b  mov     [rdi+0D0h], rsi
0x180026252  mov     [rdi+0D8h], rsi
0x180026259  mov     [rdi+0E0h], rsi
0x180026260  mov     [rdi+0E8h], rsi
0x180026267  mov     [rdi+0F0h], rsi
0x18002626e  mov     [rdi+0F8h], rsi
0x180026275  mov     [rdi+100h], rax
0x18002627c  mov     [rdi+108h], rax
0x180026283  mov     qword ptr [rdi+110h], 1
0x18002628e  mov     [rdi+118h], rax
0x180026295  mov     [rdi+120h], rax
0x18002629c  mov     [rdi+128h], rax
0x1800262a3  mov     [rdi+130h], rax
0x1800262aa  mov     [rdi+138h], sil
0x1800262b1  mov     [rdi+13Ch], rax
0x1800262b8  mov     [rdi+144h], rax
0x1800262bf  or      eax, 0FFFFFFFFh
0x1800262c2  mov     [rdi+14Ch], eax
0x1800262c8  mov     [rdi+150h], eax
0x1800262ce  lea     eax, [rsi+64h]
0x1800262d1  mov     [rdi+158h], eax
0x1800262d7  mov     [rdi+15Ch], eax
0x1800262dd  mov     rax, 3FF0000000000000h
0x1800262e7  mov     [rdi+160h], rax
0x1800262ee  mov     [rdi+154h], sil
0x1800262f5  mov     [rdi+168h], esi
0x1800262fb  mov     [rdi+16Ch], si
0x180026302  mov     [rdi+170h], esi
0x180026308  call    ??0?$ActivityBase@VCApplicationFrameLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CApplicationFrameLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002630d  lea     rax, ??_7MoveSizeLoop@CApplicationFrameTelemetry@@6B@; const CApplicationFrameTelemetry::MoveSizeLoop::`vftable'
0x180026314  mov     [rbx], rax
0x180026317  mov     [rdi+2C8h], si
0x18002631e  mov     [rdi+2D0h], rsi
0x180026325  mov     [rdi+2D8h], rsi
0x18002632c  mov     [rdi+2E8h], rsi
0x180026333  mov     [rdi+2F0h], rsi
0x18002633a  mov     [rdi+2F8h], rsi
0x180026341  mov     rbx, [rsp+28h+arg_0]
0x180026346  mov     rax, rdi
0x180026349  mov     [rdi+300h], rsi
0x180026350  mov     [rdi+308h], rsi
0x180026357  mov     [rdi+310h], rsi
0x18002635e  mov     [rdi+318h], rsi
0x180026365  mov     [rdi+320h], rsi
0x18002636c  mov     [rdi+328h], rsi
0x180026373  mov     [rdi+330h], rsi
0x18002637a  mov     [rdi+338h], rsi
0x180026381  mov     [rdi+340h], rsi
0x180026388  mov     [rdi+348h], rsi
0x18002638f  mov     [rdi+350h], rsi
0x180026396  mov     [rdi+358h], rsi
0x18002639d  mov     [rdi+360h], rsi
0x1800263a4  mov     rsi, [rsp+28h+arg_8]
0x1800263a9  add     rsp, 20h
0x1800263ad  pop     rdi
0x1800263ae  retn
```
