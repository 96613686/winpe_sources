# CDisplayManager::InternalUpdateDXGIFactory(void)

- ea: `0x180212c18`
- end: `0x180212df0`
- name: `?InternalUpdateDXGIFactory@CDisplayManager@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDisplayManager *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180052714`
- `0x18021a690`

## callees

- `0x1800096a4`
- `0x18000a254`
- `0x18000fb88`
- `0x1800184a0`
- `0x18003bfc0`
- `0x180042854`
- `0x18016f770`
- `0x1801e4f00`
- `0x180212c18`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180212cfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180212cfa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180212dcd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180212dcd`
- `dxgi!CreateDXGIFactory1` at `0x180212c65`
- `dxgi!CreateDXGIFactory1` at `0x180212c65`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180212dae`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180212dae`

## pseudocode

```c
__int64 __fastcall CDisplayManager::InternalUpdateDXGIFactory(CDisplayManager *this)
{
  int CurrentFrameId; // eax
  int v2; // ecx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  CDisplayManager *v6; // rcx
  CComposition *v7; // rcx
  int v9; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  CDisplayManager *v11; // [rsp+40h] [rbp+10h] BYREF
  void *ppFactory; // [rsp+48h] [rbp+18h] BYREF
  _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+20h] BYREF

  v11 = this;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
  {
    CurrentFrameId = GetCurrentFrameId();
    McTemplateU0qqq_EventWriteTransfer(v2, (unsigned int)EVTDESC_SCHEDULE_DERIVEDISPLAYSET, 0, CurrentFrameId, 0);
  }
  ppFactory = 0;
  v3 = CreateDXGIFactory1(&GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8, &ppFactory);
  v4 = v3;
  if ( v3 >= 0 )
  {
    LODWORD(v11) = 0;
    v5 = (*(__int64 (__fastcall **)(void *, __int64, CDisplayManager **))(*(_QWORD *)ppFactory + 240LL))(
           ppFactory,
           qword_1803BB0C8,
           &v11);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v13 = &g_DisplayManager;
      EnterCriticalSection(&g_DisplayManager);
      v6 = qword_1803BB0B8;
      if ( qword_1803BB0B8 )
      {
        if ( (_DWORD)qword_1803BB0D8 )
        {
          (*(void (**)(void))(*(_QWORD *)qword_1803BB0B8 + 248LL))();
          v6 = qword_1803BB0B8;
          LODWORD(qword_1803BB0D8) = 0;
        }
        if ( (unsigned __int64)(qword_1803BB0D0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !byte_1803BB0E2 )
        {
          (*(void (__fastcall **)(CDisplayManager *, _QWORD))(*(_QWORD *)v6 + 184LL))(v6, HIDWORD(qword_1803BB0D8));
          HIDWORD(qword_1803BB0D8) = 0;
        }
      }
      LODWORD(qword_1803BB0D8) = (_DWORD)v11;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(&qword_1803BB0D0);
      ReleaseInterface<ID2D1Geometry>(&qword_1803BB0B8);
      qword_1803BB0B8 = (CDisplayManager *)ppFactory;
      ppFactory = 0;
      LOBYTE(word_1803BB0E0) = 0;
      byte_1803BB0E2 = GetSystemMetrics(4096) != 0;
      CGuard<CCriticalSection>::~CGuard<CCriticalSection>(&v13);
      QueryPerformanceCounter(&PerformanceCount);
      CComposition::ResetTokenThread(v7);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\displaymanager.cpp",
        (const char *)(unsigned int)v5,
        v9);
    }
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&ppFactory);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\displaymanager.cpp",
      (const char *)(unsigned int)v3,
      v9);
    if ( ppFactory )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  }
  return v4;
}

```

## disassembly

```asm
0x180212c18  mov     [rsp-8+arg_18], rbx
0x180212c1d  mov     [rsp-8+arg_0], rcx
0x180212c22  push    rbp
0x180212c23  mov     rbp, rsp
0x180212c26  sub     rsp, 30h
0x180212c2a  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180212c31  jz      short loc_180212C52
0x180212c33  call    ?GetCurrentFrameId@@YA_KXZ; GetCurrentFrameId(void)
0x180212c38  mov     r9, rax
0x180212c3b  mov     [rsp+30h+var_10], 0; int
0x180212c43  xor     r8d, r8d
0x180212c46  lea     rdx, EVTDESC_SCHEDULE_DERIVEDISPLAYSET
0x180212c4d  call    McTemplateU0qqq_EventWriteTransfer
0x180212c52  lea     rdx, [rbp+ppFactory]; ppFactory
0x180212c56  mov     [rbp+ppFactory], 0
0x180212c5e  lea     rcx, _GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8; riid
0x180212c65  call    cs:__imp_CreateDXGIFactory1
0x180212c6b  mov     ebx, eax
0x180212c6d  test    eax, eax
0x180212c6f  jns     short loc_180212CA7
0x180212c71  mov     rcx, [rbp+8]; this
0x180212c75  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180212c7c  mov     r9d, eax; char *
0x180212c7f  mov     edx, 195h; void *
0x180212c84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180212c89  mov     rcx, [rbp+ppFactory]
0x180212c8d  test    rcx, rcx
0x180212c90  jz      loc_180212DE3
0x180212c96  mov     rdx, [rcx]
0x180212c99  mov     rax, [rdx+10h]
0x180212c9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212ca2  jmp     loc_180212DE3
0x180212ca7  mov     rcx, [rbp+ppFactory]
0x180212cab  lea     r8, [rbp+arg_0]
0x180212caf  mov     rdx, cs:qword_1803BB0C8
0x180212cb6  mov     dword ptr [rbp+arg_0], 0
0x180212cbd  mov     rax, [rcx]
0x180212cc0  mov     rax, [rax+0F0h]
0x180212cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212ccc  mov     ebx, eax
0x180212cce  test    eax, eax
0x180212cd0  jns     short loc_180212CEF
0x180212cd2  mov     rcx, [rbp+8]; this
0x180212cd6  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180212cdd  mov     r9d, eax; char *
0x180212ce0  mov     edx, 199h; void *
0x180212ce5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180212cea  jmp     loc_180212DDA
0x180212cef  lea     rcx, ?g_DisplayManager@@3VCDisplayManager@@A; lpCriticalSection
0x180212cf6  mov     [rbp+arg_10], rcx
0x180212cfa  call    cs:__imp_EnterCriticalSection
0x180212d00  mov     rcx, cs:qword_1803BB0B8
0x180212d07  test    rcx, rcx
0x180212d0a  jz      short loc_180212D6E
0x180212d0c  mov     edx, dword ptr cs:qword_1803BB0D8
0x180212d12  test    edx, edx
0x180212d14  jz      short loc_180212D36
0x180212d16  mov     rax, [rcx]
0x180212d19  mov     rax, [rax+0F8h]
0x180212d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212d25  mov     rcx, cs:qword_1803BB0B8
0x180212d2c  mov     dword ptr cs:qword_1803BB0D8, 0
0x180212d36  mov     rax, cs:qword_1803BB0D0
0x180212d3d  dec     rax
0x180212d40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180212d44  ja      short loc_180212D6E
0x180212d46  cmp     cs:byte_1803BB0E2, 0
0x180212d4d  jnz     short loc_180212D6E
0x180212d4f  mov     rax, [rcx]
0x180212d52  mov     edx, dword ptr cs:qword_1803BB0D8+4
0x180212d58  mov     rax, [rax+0B8h]
0x180212d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212d64  mov     dword ptr cs:qword_1803BB0D8+4, 0
0x180212d6e  mov     eax, dword ptr [rbp+arg_0]
0x180212d71  lea     rcx, qword_1803BB0D0
0x180212d78  mov     dword ptr cs:qword_1803BB0D8, eax
0x180212d7e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x180212d83  lea     rcx, qword_1803BB0B8
0x180212d8a  call    ??$ReleaseInterface@UID2D1Geometry@@@@YAXAEAPEAUID2D1Geometry@@@Z; ReleaseInterface<ID2D1Geometry>(ID2D1Geometry * &)
0x180212d8f  mov     rax, [rbp+ppFactory]
0x180212d93  mov     ecx, 1000h; nIndex
0x180212d98  mov     cs:qword_1803BB0B8, rax
0x180212d9f  mov     [rbp+ppFactory], 0
0x180212da7  mov     byte ptr cs:word_1803BB0E0, 0
0x180212dae  call    cs:__imp_GetSystemMetrics
0x180212db4  test    eax, eax
0x180212db6  lea     rcx, [rbp+arg_10]
0x180212dba  setnz   cs:byte_1803BB0E2
0x180212dc1  call    ??1?$CGuard@VCCriticalSection@@@@QEAA@XZ; CGuard<CCriticalSection>::~CGuard<CCriticalSection>(void)
0x180212dc6  lea     rcx, PerformanceCount; lpPerformanceCount
0x180212dcd  call    cs:__imp_QueryPerformanceCounter
0x180212dd3  call    ?ResetTokenThread@CComposition@@QEAAJXZ; CComposition::ResetTokenThread(void)
0x180212dd8  xor     ebx, ebx
0x180212dda  lea     rcx, [rbp+ppFactory]
0x180212dde  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180212de3  mov     eax, ebx
0x180212de5  mov     rbx, [rsp+30h+arg_18]
0x180212dea  add     rsp, 30h
0x180212dee  pop     rbp
0x180212def  retn
```
