# Windows::UI::Composition::CompositorCommon::PostDestroy(void)

- ea: `0x18007c8a8`
- end: `0x18007ca83`
- name: `?PostDestroy@CompositorCommon@Composition@UI@Windows@@MEAAXXZ`
- size: `475`
- prototype: `void __fastcall(Windows::UI::Composition::CompositorCommon *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007c880`

## callees

- `0x1800093f4`
- `0x18000f810`
- `0x18002bce0`
- `0x180038c10`
- `0x18005765c`
- `0x18006c5b0`
- `0x18007c8a8`
- `0x18007ca8c`
- `0x18007d090`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c9e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007c9e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ca6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007ca6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c9ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007c9ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c94b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c94b`

## pseudocode

```c
void __fastcall Windows::UI::Composition::CompositorCommon::PostDestroy(
        Windows::UI::Composition::CompositorCommon *this)
{
  char *v1; // rdi
  DirectComposition::CMessageConversationHost *v3; // rcx
  void *v4; // rdi
  Microsoft::WRL2::NestableRuntimeClass *v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v1 = (char *)this + 408;
  v3 = (DirectComposition::CMessageConversationHost *)*((_QWORD *)this + 51);
  if ( v3 )
  {
    DirectComposition::CMessageConversationHost::Destroy(v3);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(v1);
  }
  v4 = (void *)*((_QWORD *)this + 102);
  if ( v4 )
  {
    Windows::UI::Composition::AnimationBindingManager::~AnimationBindingManager(*((PRTL_GENERIC_TABLE *)this + 102));
    operator delete(v4);
    *((_QWORD *)this + 102) = 0;
  }
  v5 = (Microsoft::WRL2::NestableRuntimeClass *)*((_QWORD *)this + 103);
  if ( v5 )
  {
    Microsoft::WRL2::NestableRuntimeClass::InternalRelease(v5);
    *((_QWORD *)this + 103) = 0;
  }
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 456);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 464);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 472);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 488);
  WindowsDeleteString(*((HSTRING *)this + 123));
  Windows::UI::Composition::BatchController::Shutdown((Windows::UI::Composition::CompositorCommon *)((char *)this + 592));
  Windows::UI::Composition::BatchController::Shutdown((Windows::UI::Composition::CompositorCommon *)((char *)this + 664));
  Windows::UI::Composition::BatchController::Shutdown((Windows::UI::Composition::CompositorCommon *)((char *)this + 736));
  v6 = *((_QWORD *)this + 55);
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 440);
  }
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 416);
  Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)this + 424);
  if ( *((_QWORD *)this + 132) )
  {
    v9 = *((_QWORD *)this + 132);
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v9);
    *((_QWORD *)this + 132) = 0;
    Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(&v9);
  }
  AcquireSRWLockExclusive(&Windows::UI::Composition::CompositorCommon::s_lockCompositors);
  dword_1801E14E8 = GetCurrentThreadId();
  if ( Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak == this )
    Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak = (struct Windows::UI::Composition::Compositor *)*((_QWORD *)this + 50);
  v7 = *((_QWORD *)this + 49);
  if ( v7 )
    *(_QWORD *)(v7 + 400) = *((_QWORD *)this + 50);
  v8 = *((_QWORD *)this + 50);
  if ( v8 )
    *(_QWORD *)(v8 + 392) = *((_QWORD *)this + 49);
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 50) = 0;
  dword_1801E14E8 = 0;
  ReleaseSRWLockExclusive(&Windows::UI::Composition::CompositorCommon::s_lockCompositors);
  Microsoft::WRL2::ContextRuntimeClass::PostDestroy(this);
}

```

## disassembly

```asm
0x18007c8a8  mov     [rsp+arg_8], rbx
0x18007c8ad  push    rdi
0x18007c8ae  sub     rsp, 20h
0x18007c8b2  lea     rdi, [rcx+198h]
0x18007c8b9  mov     rbx, rcx
0x18007c8bc  mov     rcx, [rdi]; this
0x18007c8bf  test    rcx, rcx
0x18007c8c2  jz      short loc_18007C8D1
0x18007c8c4  call    ?Destroy@CMessageConversationHost@DirectComposition@@QEAAXXZ; DirectComposition::CMessageConversationHost::Destroy(void)
0x18007c8c9  mov     rcx, rdi
0x18007c8cc  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c8d1  mov     rdi, [rbx+330h]
0x18007c8d8  test    rdi, rdi
0x18007c8db  jz      short loc_18007C8F8
0x18007c8dd  mov     rcx, rdi; Table
0x18007c8e0  call    ??1AnimationBindingManager@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::AnimationBindingManager::~AnimationBindingManager(void)
0x18007c8e5  mov     rcx, rdi; lpMem
0x18007c8e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c8ed  mov     qword ptr [rbx+330h], 0
0x18007c8f8  mov     rcx, [rbx+338h]; this
0x18007c8ff  test    rcx, rcx
0x18007c902  jz      short loc_18007C914
0x18007c904  call    ?InternalRelease@NestableRuntimeClass@WRL2@Microsoft@@QEAAKXZ; Microsoft::WRL2::NestableRuntimeClass::InternalRelease(void)
0x18007c909  mov     qword ptr [rbx+338h], 0
0x18007c914  lea     rcx, [rbx+1C8h]
0x18007c91b  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c920  lea     rcx, [rbx+1D0h]
0x18007c927  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c92c  lea     rcx, [rbx+1D8h]
0x18007c933  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c938  lea     rcx, [rbx+1E8h]
0x18007c93f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c944  mov     rcx, [rbx+3D8h]; string
0x18007c94b  call    cs:__imp_WindowsDeleteString
0x18007c951  lea     rcx, [rbx+250h]; this
0x18007c958  call    ?Shutdown@BatchController@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::BatchController::Shutdown(void)
0x18007c95d  lea     rcx, [rbx+298h]; this
0x18007c964  call    ?Shutdown@BatchController@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::BatchController::Shutdown(void)
0x18007c969  lea     rcx, [rbx+2E0h]; this
0x18007c970  call    ?Shutdown@BatchController@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::BatchController::Shutdown(void)
0x18007c975  lea     rdi, [rbx+1B8h]
0x18007c97c  mov     rcx, [rdi]
0x18007c97f  test    rcx, rcx
0x18007c982  jz      short loc_18007C998
0x18007c984  mov     rax, [rcx]
0x18007c987  mov     rax, [rax+18h]
0x18007c98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c990  mov     rcx, rdi
0x18007c993  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c998  lea     rcx, [rbx+1A0h]
0x18007c99f  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c9a4  lea     rcx, [rbx+1A8h]
0x18007c9ab  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18007c9b0  mov     rax, [rbx+420h]
0x18007c9b7  test    rax, rax
0x18007c9ba  jz      short loc_18007C9E0
0x18007c9bc  lea     rcx, [rsp+28h+arg_0]
0x18007c9c1  mov     [rsp+28h+arg_0], rax
0x18007c9c6  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x18007c9cb  lea     rcx, [rsp+28h+arg_0]
0x18007c9d0  mov     qword ptr [rbx+420h], 0
0x18007c9db  call    ?InternalUnlock@?$RefPtr@VNaturalMotionAnimation@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::NaturalMotionAnimation>::InternalUnlock(void)
0x18007c9e0  lea     rcx, ?s_lockCompositors@CompositorCommon@Composition@UI@Windows@@0VCReadWriteLock@@A; SRWLock
0x18007c9e7  call    cs:__imp_AcquireSRWLockExclusive
0x18007c9ed  call    cs:__imp_GetCurrentThreadId
0x18007c9f3  cmp     cs:?s_pFirstCompositorWeak@CompositorCommon@Composition@UI@Windows@@0PEAVCompositor@234@EA, rbx; Windows::UI::Composition::Compositor * Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak
0x18007c9fa  mov     cs:dword_1801E14E8, eax
0x18007ca00  jnz     short loc_18007CA10
0x18007ca02  mov     rax, [rbx+190h]
0x18007ca09  mov     cs:?s_pFirstCompositorWeak@CompositorCommon@Composition@UI@Windows@@0PEAVCompositor@234@EA, rax; Windows::UI::Composition::Compositor * Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak
0x18007ca10  mov     rdx, [rbx+188h]
0x18007ca17  test    rdx, rdx
0x18007ca1a  jz      short loc_18007CA2A
0x18007ca1c  mov     rax, [rbx+190h]
0x18007ca23  mov     [rdx+190h], rax
0x18007ca2a  mov     rdx, [rbx+190h]
0x18007ca31  test    rdx, rdx
0x18007ca34  jz      short loc_18007CA44
0x18007ca36  mov     rax, [rbx+188h]
0x18007ca3d  mov     [rdx+188h], rax
0x18007ca44  mov     qword ptr [rbx+188h], 0
0x18007ca4f  lea     rcx, ?s_lockCompositors@CompositorCommon@Composition@UI@Windows@@0VCReadWriteLock@@A; SRWLock
0x18007ca56  mov     qword ptr [rbx+190h], 0
0x18007ca61  mov     cs:dword_1801E14E8, 0
0x18007ca6b  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ca71  mov     rcx, rbx; this
0x18007ca74  mov     rbx, [rsp+28h+arg_8]
0x18007ca79  add     rsp, 20h
0x18007ca7d  pop     rdi
0x18007ca7e  jmp     ?PostDestroy@ContextRuntimeClass@WRL2@Microsoft@@MEAAXXZ; Microsoft::WRL2::ContextRuntimeClass::PostDestroy(void)
```
