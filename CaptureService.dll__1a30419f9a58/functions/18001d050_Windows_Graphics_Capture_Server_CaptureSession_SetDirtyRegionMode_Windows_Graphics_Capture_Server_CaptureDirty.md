# Windows::Graphics::Capture::Server::CaptureSession::SetDirtyRegionMode(Windows::Graphics::Capture::Server::CaptureDirtyRegionMode)

- ea: `0x18001d050`
- end: `0x18001d102`
- name: `?SetDirtyRegionMode@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJW4CaptureDirtyRegionMode@2345@@Z`
- size: `178`
- prototype: `int __high(enum Windows::Graphics::Capture::Server::CaptureDirtyRegionMode)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001d050`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d06b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d06b`

## string_xrefs

- `0x18001d0bd`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetDirtyRegionMode(__int64 a1, int a2)
{
  RTL_SRWLOCK *v4; // rbx
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)(a1 + 104);
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 104));
  v13 = v4;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v5 = -2147024809;
      v6 = 2147942487LL;
      v7 = 301;
      goto LABEL_9;
    }
    v8 = 2;
  }
  else
  {
    v8 = 1;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 40) + 72LL))(*(_QWORD *)(a1 + 40), v8);
  v5 = v9;
  if ( v9 >= 0 )
  {
    v9 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
    v5 = v9;
    if ( v9 >= 0 )
    {
      v5 = 0;
      goto LABEL_13;
    }
    v7 = 305;
  }
  else
  {
    v7 = 304;
  }
  v6 = (unsigned int)v9;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)v6,
    v11);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return v5;
}

```

## disassembly

```asm
0x18001d050  mov     [rsp+arg_8], rbx
0x18001d055  mov     [rsp+arg_10], rsi
0x18001d05a  push    rdi; int
0x18001d05b  sub     rsp, 20h
0x18001d05f  mov     edi, edx
0x18001d061  mov     rsi, rcx
0x18001d064  lea     rbx, [rcx+68h]
0x18001d068  mov     rcx, rbx; SRWLock
0x18001d06b  call    cs:__imp_AcquireSRWLockExclusive
0x18001d071  mov     [rsp+28h+arg_0], rbx
0x18001d076  test    edi, edi
0x18001d078  jz      short loc_18001D095
0x18001d07a  cmp     edi, 1
0x18001d07d  jz      short loc_18001D08E
0x18001d07f  mov     ebx, 80070057h
0x18001d084  mov     r9d, ebx
0x18001d087  mov     edx, 12Dh
0x18001d08c  jmp     short loc_18001D0B8
0x18001d08e  mov     edx, 2
0x18001d093  jmp     short loc_18001D09A
0x18001d095  mov     edx, 1
0x18001d09a  mov     rcx, [rsi+28h]
0x18001d09e  mov     rax, [rcx]
0x18001d0a1  mov     rax, [rax+48h]
0x18001d0a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0aa  mov     ebx, eax
0x18001d0ac  test    eax, eax
0x18001d0ae  jns     short loc_18001D0CB
0x18001d0b0  mov     edx, 130h; void *
0x18001d0b5  mov     r9d, eax; char *
0x18001d0b8  mov     rcx, [rsp+28h]; this
0x18001d0bd  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001d0c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0c9  jmp     short loc_18001D0E6
0x18001d0cb  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001d0d2  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001d0d7  mov     ebx, eax
0x18001d0d9  test    eax, eax
0x18001d0db  jns     short loc_18001D0E4
0x18001d0dd  mov     edx, 131h
0x18001d0e2  jmp     short loc_18001D0B5
0x18001d0e4  xor     ebx, ebx
0x18001d0e6  lea     rcx, [rsp+28h+arg_0]
0x18001d0eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d0f0  mov     eax, ebx
0x18001d0f2  mov     rbx, [rsp+28h+arg_8]
0x18001d0f7  mov     rsi, [rsp+28h+arg_10]
0x18001d0fc  add     rsp, 20h
0x18001d100  pop     rdi
0x18001d101  retn
```
