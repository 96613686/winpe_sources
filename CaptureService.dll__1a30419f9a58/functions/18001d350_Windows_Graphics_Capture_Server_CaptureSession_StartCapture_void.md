# Windows::Graphics::Capture::Server::CaptureSession::StartCapture(void)

- ea: `0x18001d350`
- end: `0x18001d4a6`
- name: `?StartCapture@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJXZ`
- size: `342`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001d350`
- `0x18001d754`
- `0x18001e9d4`
- `0x18001ea40`
- `0x18001f208`
- `0x18001fcac`
- `0x180020000`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d364`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d364`

## string_xrefs

- `0x18001d3c5`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::StartCapture(
        Windows::Graphics::Capture::Server::CaptureSession *this)
{
  RTL_SRWLOCK *v2; // rbx
  Windows::Graphics::Capture::Server *v3; // rcx
  int CAMCapabilityUsageSession; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int *v7; // rdx
  __int64 v8; // rcx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v12; // [rsp+30h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+38h] [rbp+10h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 104);
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  v13 = v2;
  CAMCapabilityUsageSession = Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(v3);
  v5 = CAMCapabilityUsageSession;
  if ( CAMCapabilityUsageSession < 0 )
  {
    v6 = 111;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
      (const char *)(unsigned int)CAMCapabilityUsageSession,
      v10);
    goto LABEL_22;
  }
  if ( !*(_BYTE *)(*((_QWORD *)this + 3) + 105LL) || Windows::Graphics::Capture::Server::CheckCAMCapability(0) )
  {
    if ( !*((_BYTE *)this + 64) )
    {
      CAMCapabilityUsageSession = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4));
      v5 = CAMCapabilityUsageSession;
      if ( CAMCapabilityUsageSession < 0 )
      {
        v6 = 122;
        goto LABEL_9;
      }
      *((_BYTE *)this + 64) = 1;
      CAMCapabilityUsageSession = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
                                    *((_QWORD *)this + 5),
                                    *((_QWORD *)this + 6));
      v5 = CAMCapabilityUsageSession;
      if ( CAMCapabilityUsageSession < 0 )
      {
        v6 = 127;
        goto LABEL_9;
      }
      CAMCapabilityUsageSession = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
      v5 = CAMCapabilityUsageSession;
      if ( CAMCapabilityUsageSession < 0 )
      {
        v6 = 128;
        goto LABEL_9;
      }
      if ( (Microsoft_Windows_Graphics_Capture_ServerEnableBits & 1) != 0 )
      {
        v12 = 0;
        Windows::Graphics::Capture::Server::GetClientProcessId((Windows::Graphics::Capture::Server *)&v12, v7);
        McTemplateU0q_EventWriteTransfer(v8, CAPTURE_STARTED, v12);
      }
      if ( *(_BYTE *)(*((_QWORD *)this + 3) + 105LL) )
      {
        CAMCapabilityUsageSession = Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(
                                      0,
                                      (unsigned int *)this + 18);
        v5 = CAMCapabilityUsageSession;
        if ( CAMCapabilityUsageSession < 0 )
        {
          v6 = 137;
          goto LABEL_9;
        }
        CAMCapabilityUsageSession = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 48LL))(*((_QWORD *)this + 9));
        v5 = CAMCapabilityUsageSession;
        if ( CAMCapabilityUsageSession < 0 )
        {
          v6 = 139;
          goto LABEL_9;
        }
      }
    }
    v5 = 0;
    goto LABEL_22;
  }
  v5 = -2147024891;
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return v5;
}

```

## disassembly

```asm
0x18001d350  mov     [rsp+arg_10], rbx
0x18001d355  push    rdi; int
0x18001d356  sub     rsp, 20h
0x18001d35a  mov     rdi, rcx
0x18001d35d  lea     rbx, [rcx+68h]
0x18001d361  mov     rcx, rbx; SRWLock
0x18001d364  call    cs:__imp_AcquireSRWLockExclusive
0x18001d36a  mov     [rsp+28h+arg_8], rbx
0x18001d36f  call    ?CheckMDMPolicyAllowsCapture@Server@Capture@Graphics@Windows@@YAJXZ; Windows::Graphics::Capture::Server::CheckMDMPolicyAllowsCapture(void)
0x18001d374  mov     ebx, eax
0x18001d376  test    eax, eax
0x18001d378  jns     short loc_18001D381
0x18001d37a  mov     edx, 6Fh ; 'o'
0x18001d37f  jmp     short loc_18001D3C5
0x18001d381  mov     rax, [rdi+18h]
0x18001d385  cmp     byte ptr [rax+69h], 0
0x18001d389  jz      short loc_18001D3A0
0x18001d38b  xor     ecx, ecx
0x18001d38d  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x18001d392  test    al, al
0x18001d394  jnz     short loc_18001D3A0
0x18001d396  mov     ebx, 80070005h
0x18001d39b  jmp     loc_18001D48F
0x18001d3a0  cmp     byte ptr [rdi+40h], 0
0x18001d3a4  jnz     loc_18001D48D
0x18001d3aa  mov     rcx, [rdi+20h]
0x18001d3ae  mov     rax, [rcx]
0x18001d3b1  mov     rax, [rax+38h]
0x18001d3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ba  mov     ebx, eax
0x18001d3bc  test    eax, eax
0x18001d3be  jns     short loc_18001D3DE
0x18001d3c0  mov     edx, 7Ah ; 'z'; void *
0x18001d3c5  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d3cc  mov     r9d, eax; char *
0x18001d3cf  mov     rcx, [rsp+28h]; this
0x18001d3d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3d9  jmp     loc_18001D48F
0x18001d3de  mov     byte ptr [rdi+40h], 1
0x18001d3e2  mov     rcx, [rdi+28h]
0x18001d3e6  mov     rax, [rcx]
0x18001d3e9  mov     rdx, [rdi+30h]
0x18001d3ed  mov     rax, [rax+18h]
0x18001d3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3f6  mov     ebx, eax
0x18001d3f8  test    eax, eax
0x18001d3fa  jns     short loc_18001D403
0x18001d3fc  mov     edx, 7Fh
0x18001d401  jmp     short loc_18001D3C5
0x18001d403  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d40a  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d40f  mov     ebx, eax
0x18001d411  test    eax, eax
0x18001d413  jns     short loc_18001D41C
0x18001d415  mov     edx, 80h
0x18001d41a  jmp     short loc_18001D3C5
0x18001d41c  test    cs:Microsoft_Windows_Graphics_Capture_ServerEnableBits, 1
0x18001d423  jz      short loc_18001D448
0x18001d425  mov     [rsp+28h+arg_0], 0
0x18001d42d  lea     rcx, [rsp+28h+arg_0]; this
0x18001d432  call    ?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z; Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)
0x18001d437  mov     r8d, [rsp+28h+arg_0]
0x18001d43c  lea     rdx, CAPTURE_STARTED
0x18001d443  call    McTemplateU0q_EventWriteTransfer
0x18001d448  mov     rax, [rdi+18h]
0x18001d44c  cmp     byte ptr [rax+69h], 0
0x18001d450  jz      short loc_18001D48D
0x18001d452  lea     rdx, [rdi+48h]
0x18001d456  xor     ecx, ecx
0x18001d458  call    ?CreateCAMCapabilityUsageSession@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@PEAPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@4@@Z; Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession * *)
0x18001d45d  mov     ebx, eax
0x18001d45f  test    eax, eax
0x18001d461  jns     short loc_18001D46D
0x18001d463  mov     edx, 89h
0x18001d468  jmp     loc_18001D3C5
0x18001d46d  mov     rcx, [rdi+48h]
0x18001d471  mov     rax, [rcx]
0x18001d474  mov     rax, [rax+30h]
0x18001d478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d47d  mov     ebx, eax
0x18001d47f  test    eax, eax
0x18001d481  jns     short loc_18001D48D
0x18001d483  mov     edx, 8Bh
0x18001d488  jmp     loc_18001D3C5
0x18001d48d  xor     ebx, ebx
0x18001d48f  lea     rcx, [rsp+28h+arg_8]
0x18001d494  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d499  mov     eax, ebx
0x18001d49b  mov     rbx, [rsp+28h+arg_10]
0x18001d4a0  add     rsp, 20h
0x18001d4a4  pop     rdi
0x18001d4a5  retn
```
