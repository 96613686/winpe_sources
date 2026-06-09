# Windows::Graphics::Capture::Server::CaptureSession::SetBorderEnabled(uchar)

- ea: `0x18001ccd0`
- end: `0x18001ce01`
- name: `?SetBorderEnabled@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJE@Z`
- size: `305`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18001ccd0`
- `0x18001e9d4`
- `0x18001ea40`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ccec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001ccec`

## string_xrefs

- `0x18001cd69`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`
- `0x18001cd82`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`
- `0x18001cdbf`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetBorderEnabled(
        Windows::Graphics::Capture::Server::CaptureSession *this,
        char a2)
{
  RTL_SRWLOCK *v4; // rbx
  bool v5; // al
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int CAMCapabilityUsageSession; // eax
  unsigned int v10; // esi
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-8h]
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp+8h] BYREF

  v4 = (RTL_SRWLOCK *)((char *)this + 104);
  AcquireSRWLockExclusive((PSRWLOCK)this + 13);
  v16 = v4;
  v5 = !Windows::Graphics::Capture::Server::CheckCAMCapability(1);
  *((_BYTE *)this + 66) = v5;
  if ( (a2 != 0) == *((_BYTE *)this + 65) )
    goto LABEL_14;
  *((_BYTE *)this + 65) = a2 != 0;
  if ( !v5 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 96LL))(*((_QWORD *)this + 4));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 256;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
        (const char *)(unsigned int)v6,
        v13);
      goto LABEL_15;
    }
  }
  if ( *((_QWORD *)this + 10)
    || (CAMCapabilityUsageSession = Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(
                                      1u,
                                      (unsigned int *)this + 20),
        v10 = CAMCapabilityUsageSession,
        CAMCapabilityUsageSession >= 0) )
  {
    v11 = **((_QWORD **)this + 10);
    if ( *((_BYTE *)this + 65) )
    {
      v6 = (*(__int64 (**)(void))(v11 + 56))();
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 269;
        goto LABEL_11;
      }
    }
    else
    {
      v6 = (*(__int64 (**)(void))(v11 + 48))();
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 265;
        goto LABEL_11;
      }
    }
LABEL_14:
    v7 = 0;
    goto LABEL_15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B7,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)(unsigned int)CAMCapabilityUsageSession,
    v13);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x106,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
    (const char *)v10,
    v14);
  v7 = v10;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  return v7;
}

```

## disassembly

```asm
0x18001ccd0  mov     [rsp+arg_8], rbx
0x18001ccd5  mov     [rsp+arg_10], rsi
0x18001ccda  push    rdi; int
0x18001ccdb  sub     rsp, 20h
0x18001ccdf  mov     sil, dl
0x18001cce2  mov     rdi, rcx
0x18001cce5  lea     rbx, [rcx+68h]
0x18001cce9  mov     rcx, rbx; SRWLock
0x18001ccec  call    cs:__imp_AcquireSRWLockExclusive
0x18001ccf2  mov     [rsp+28h+arg_0], rbx
0x18001ccf7  mov     ecx, 1
0x18001ccfc  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x18001cd01  xor     al, 1
0x18001cd03  mov     [rdi+42h], al
0x18001cd06  xor     edx, edx
0x18001cd08  test    sil, sil
0x18001cd0b  setnz   dl
0x18001cd0e  movzx   ecx, byte ptr [rdi+41h]
0x18001cd12  cmp     edx, ecx
0x18001cd14  jz      loc_18001CDE3
0x18001cd1a  test    sil, sil
0x18001cd1d  setnz   dl
0x18001cd20  mov     [rdi+41h], dl
0x18001cd23  test    al, al
0x18001cd25  jnz     short loc_18001CD44
0x18001cd27  mov     rcx, [rdi+20h]
0x18001cd2b  mov     rax, [rcx]
0x18001cd2e  mov     rax, [rax+60h]
0x18001cd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd37  mov     ebx, eax
0x18001cd39  test    eax, eax
0x18001cd3b  jns     short loc_18001CD44
0x18001cd3d  mov     edx, 100h
0x18001cd42  jmp     short loc_18001CDB7
0x18001cd44  lea     rbx, [rdi+50h]
0x18001cd48  cmp     qword ptr [rbx], 0
0x18001cd4c  jnz     short loc_18001CD97
0x18001cd4e  mov     rdx, rbx
0x18001cd51  mov     ecx, 1
0x18001cd56  call    ?CreateCAMCapabilityUsageSession@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@PEAPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@4@@Z; Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession * *)
0x18001cd5b  mov     esi, eax
0x18001cd5d  test    eax, eax
0x18001cd5f  jns     short loc_18001CD97
0x18001cd61  mov     rcx, [rsp+28h]; this
0x18001cd66  mov     r9d, eax; char *
0x18001cd69  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cd70  mov     edx, 1B7h; void *
0x18001cd75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd7a  mov     rcx, [rsp+28h]; this
0x18001cd7f  mov     r9d, esi; char *
0x18001cd82  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cd89  mov     edx, 106h; void *
0x18001cd8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd93  mov     ebx, esi
0x18001cd95  jmp     short loc_18001CDE5
0x18001cd97  mov     rcx, [rbx]
0x18001cd9a  mov     rax, [rcx]
0x18001cd9d  cmp     byte ptr [rdi+41h], 0
0x18001cda1  jnz     short loc_18001CDCD
0x18001cda3  mov     rax, [rax+30h]
0x18001cda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdac  mov     ebx, eax
0x18001cdae  test    eax, eax
0x18001cdb0  jns     short loc_18001CDE3
0x18001cdb2  mov     edx, 109h; void *
0x18001cdb7  mov     rcx, [rsp+28h]; this
0x18001cdbc  mov     r9d, eax; char *
0x18001cdbf  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cdc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cdcb  jmp     short loc_18001CDE5
0x18001cdcd  mov     rax, [rax+38h]
0x18001cdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd6  mov     ebx, eax
0x18001cdd8  test    eax, eax
0x18001cdda  jns     short loc_18001CDE3
0x18001cddc  mov     edx, 10Dh
0x18001cde1  jmp     short loc_18001CDB7
0x18001cde3  xor     ebx, ebx
0x18001cde5  lea     rcx, [rsp+28h+arg_0]
0x18001cdea  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001cdef  mov     eax, ebx
0x18001cdf1  mov     rbx, [rsp+28h+arg_8]
0x18001cdf6  mov     rsi, [rsp+28h+arg_10]
0x18001cdfb  add     rsp, 20h
0x18001cdff  pop     rdi
0x18001ce00  retn
```
