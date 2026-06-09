# Windows::Graphics::Capture::Server::CaptureSession::StopCapture(void)

- ea: `0x18001d4b0`
- end: `0x18001d609`
- name: `?StopCapture@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJXZ`
- size: `345`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c1b8`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001881c`
- `0x18001d4b0`
- `0x18001d754`
- `0x18001f208`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d4c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d55e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d4c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d55e`

## string_xrefs

- `0x18001d50f`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::StopCapture(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  unsigned int *v3; // rdx
  PVOID Ptr; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  PVOID v8; // rcx
  RTL_SRWLOCK *v9; // rsi
  __int64 v10; // rcx
  PVOID v11; // rcx
  PVOID v12; // rcx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v17; // [rsp+38h] [rbp+10h] BYREF

  v2 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v17 = v2;
  Ptr = this[5].Ptr;
  if ( Ptr )
  {
    v5 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)Ptr + 24LL))(Ptr, 0);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 154;
      goto LABEL_6;
    }
    v5 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 155;
      goto LABEL_6;
    }
  }
  v8 = this[4].Ptr;
  if ( !v8 || (v5 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v8 + 64LL))(v8), v6 = v5, v5 >= 0) )
  {
    LOBYTE(this[8].Ptr) = 0;
    v9 = (RTL_SRWLOCK *)this[11].Ptr;
    if ( v9 )
    {
      AcquireSRWLockExclusive(v9 + 7);
      v16 = v9 + 7;
      wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v9[6]);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (Microsoft_Windows_Graphics_Capture_ServerEnableBits & 1) != 0 )
    {
      LODWORD(v16) = 0;
      Windows::Graphics::Capture::Server::GetClientProcessId((Windows::Graphics::Capture::Server *)&v16, v3);
      McTemplateU0q_EventWriteTransfer(v10, CAPTURE_STOPPED, (unsigned int)v16);
    }
    v11 = this[9].Ptr;
    if ( v11 )
    {
      v5 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v11 + 56LL))(v11);
      v6 = v5;
      if ( v5 < 0 )
      {
        v7 = 174;
        goto LABEL_6;
      }
      v12 = this[9].Ptr;
      this[9].Ptr = 0;
      if ( v12 )
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v6 = 0;
    goto LABEL_20;
  }
  v7 = 161;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)v5,
    v14);
LABEL_20:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  return v6;
}

```

## disassembly

```asm
0x18001d4b0  mov     [rsp+arg_10], rbx
0x18001d4b5  mov     [rsp+arg_18], rsi
0x18001d4ba  push    rdi; int
0x18001d4bb  sub     rsp, 20h
0x18001d4bf  mov     rdi, rcx
0x18001d4c2  lea     rbx, [rcx+68h]
0x18001d4c6  mov     rcx, rbx; SRWLock
0x18001d4c9  call    cs:__imp_AcquireSRWLockExclusive
0x18001d4cf  mov     [rsp+28h+arg_8], rbx
0x18001d4d4  mov     rcx, [rdi+28h]
0x18001d4d8  test    rcx, rcx
0x18001d4db  jz      short loc_18001D528
0x18001d4dd  mov     rax, [rcx]
0x18001d4e0  xor     edx, edx
0x18001d4e2  mov     rax, [rax+18h]
0x18001d4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4eb  mov     ebx, eax
0x18001d4ed  test    eax, eax
0x18001d4ef  jns     short loc_18001D4F8
0x18001d4f1  mov     edx, 9Ah
0x18001d4f6  jmp     short loc_18001D50F
0x18001d4f8  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d4ff  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d504  mov     ebx, eax
0x18001d506  test    eax, eax
0x18001d508  jns     short loc_18001D528
0x18001d50a  mov     edx, 9Bh; void *
0x18001d50f  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d516  mov     r9d, eax; char *
0x18001d519  mov     rcx, [rsp+28h]; this
0x18001d51e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d523  jmp     loc_18001D5ED
0x18001d528  mov     rcx, [rdi+20h]
0x18001d52c  test    rcx, rcx
0x18001d52f  jz      short loc_18001D54A
0x18001d531  mov     rax, [rcx]
0x18001d534  mov     rax, [rax+40h]
0x18001d538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d53d  mov     ebx, eax
0x18001d53f  test    eax, eax
0x18001d541  jns     short loc_18001D54A
0x18001d543  mov     edx, 0A1h
0x18001d548  jmp     short loc_18001D50F
0x18001d54a  mov     byte ptr [rdi+40h], 0
0x18001d54e  mov     rsi, [rdi+58h]
0x18001d552  test    rsi, rsi
0x18001d555  jz      short loc_18001D57C
0x18001d557  lea     rbx, [rsi+38h]
0x18001d55b  mov     rcx, rbx; SRWLock
0x18001d55e  call    cs:__imp_AcquireSRWLockExclusive
0x18001d564  mov     [rsp+28h+arg_0], rbx
0x18001d569  lea     rcx, [rsi+30h]
0x18001d56d  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x18001d572  lea     rcx, [rsp+28h+arg_0]
0x18001d577  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d57c  test    cs:Microsoft_Windows_Graphics_Capture_ServerEnableBits, 1
0x18001d583  jz      short loc_18001D5A8
0x18001d585  mov     dword ptr [rsp+28h+arg_0], 0
0x18001d58d  lea     rcx, [rsp+28h+arg_0]; this
0x18001d592  call    ?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z; Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)
0x18001d597  mov     r8d, dword ptr [rsp+28h+arg_0]
0x18001d59c  lea     rdx, CAPTURE_STOPPED
0x18001d5a3  call    McTemplateU0q_EventWriteTransfer
0x18001d5a8  mov     rcx, [rdi+48h]
0x18001d5ac  test    rcx, rcx
0x18001d5af  jz      short loc_18001D5EB
0x18001d5b1  mov     rax, [rcx]
0x18001d5b4  mov     rax, [rax+38h]
0x18001d5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5bd  mov     ebx, eax
0x18001d5bf  test    eax, eax
0x18001d5c1  jns     short loc_18001D5CD
0x18001d5c3  mov     edx, 0AEh
0x18001d5c8  jmp     loc_18001D50F
0x18001d5cd  mov     rcx, [rdi+48h]
0x18001d5d1  mov     qword ptr [rdi+48h], 0
0x18001d5d9  test    rcx, rcx
0x18001d5dc  jz      short loc_18001D5EB
0x18001d5de  mov     rax, [rcx]
0x18001d5e1  mov     rax, [rax+10h]
0x18001d5e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ea  nop
0x18001d5eb  xor     ebx, ebx
0x18001d5ed  lea     rcx, [rsp+28h+arg_8]
0x18001d5f2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d5f7  mov     eax, ebx
0x18001d5f9  mov     rbx, [rsp+28h+arg_10]
0x18001d5fe  mov     rsi, [rsp+28h+arg_18]
0x18001d603  add     rsp, 20h
0x18001d607  pop     rdi
0x18001d608  retn
```
