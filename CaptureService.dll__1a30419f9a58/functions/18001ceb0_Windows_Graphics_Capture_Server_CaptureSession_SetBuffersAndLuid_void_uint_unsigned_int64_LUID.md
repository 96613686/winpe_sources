# Windows::Graphics::Capture::Server::CaptureSession::SetBuffersAndLuid(void *,uint,unsigned __int64 *,_LUID)

- ea: `0x18001ceb0`
- end: `0x18001d03e`
- name: `?SetBuffersAndLuid@CaptureSession@Server@Capture@Graphics@Windows@@UEAAJPEAXIPEA_KU_LUID@@@Z`
- size: `398`
- prototype: `int(Windows::Graphics::Capture::Server::CaptureSession *__hidden this, void *, unsigned int, unsigned __int64 *, struct _LUID)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005568`
- `0x18000907c`
- `0x18000dec8`
- `0x18001bd3c`
- `0x18001bd7c`
- `0x18001bdd4`
- `0x18001bdfc`
- `0x18001bfe4`
- `0x18001ceb0`
- `0x18001ebf8`
- `0x18001fcac`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cedc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001cedc`

## string_xrefs

- `0x18001cf80`: `onecoreuap\windows\dwm\capture\svc\dll\capturesession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Graphics::Capture::Server::CaptureSession::SetBuffersAndLuid(
        RTL_SRWLOCK *this,
        void *a2,
        unsigned int a3,
        unsigned __int64 *a4,
        struct _LUID a5)
{
  RTL_SRWLOCK *v9; // rbx
  void **v10; // r9
  __int64 i; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-40h]
  HANDLE TargetHandle; // [rsp+30h] [rbp-30h] BYREF
  RTL_SRWLOCK *v18; // [rsp+38h] [rbp-28h] BYREF
  __int128 v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  HANDLE v22; // [rsp+90h] [rbp+30h] BYREF

  v9 = this + 14;
  AcquireSRWLockExclusive(this + 14);
  v18 = v9;
  std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v19);
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    TargetHandle = 0;
    v12 = Windows::Graphics::Capture::Server::DuplicateClientHandle(a2, (HANDLE)a4[i], &TargetHandle, v10);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = 226;
      goto LABEL_11;
    }
    v22 = TargetHandle;
    if ( *((_QWORD *)&v19 + 1) == v20 )
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
        &v19,
        *((_QWORD *)&v19 + 1),
        &v22);
    else
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
        &v19,
        &v22);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  }
  v12 = (*(__int64 (__fastcall **)(PVOID, struct _LUID *, _QWORD, _QWORD))(*(_QWORD *)this[6].Ptr + 40LL))(
          this[6].Ptr,
          &a5,
          a3,
          v19);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 235;
    goto LABEL_11;
  }
  v12 = Windows::Graphics::Capture::Server::DCompManager::Commit(Windows::Graphics::Capture::Server::g_DCompManager);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = 238;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesession.cpp",
      (const char *)(unsigned int)v12,
      v16);
    if ( (_QWORD)v19 )
    {
      std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
        v19,
        *((_QWORD *)&v19 + 1));
      std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF8uLL);
      v19 = 0;
      v20 = 0;
    }
    goto LABEL_18;
  }
  if ( (_QWORD)v19 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>(
      v19,
      *((_QWORD *)&v19 + 1));
    std::_Deallocate<16>(v19, (v20 - v19) & 0xFFFFFFFFFFFFFFF8uLL);
    v19 = 0;
    v20 = 0;
  }
  v13 = 0;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  return v13;
}

```

## disassembly

```asm
0x18001ceb0  mov     [rsp-28h+arg_8], rbx
0x18001ceb5  mov     [rsp-28h+arg_10], rsi
0x18001ceba  push    rbp
0x18001cebb  push    rdi
0x18001cebc  push    r12
0x18001cebe  push    r14
0x18001cec0  push    r15
0x18001cec2  mov     rbp, rsp
0x18001cec5  sub     rsp, 60h
0x18001cec9  mov     r15, r9
0x18001cecc  mov     esi, r8d
0x18001cecf  mov     r12, rdx
0x18001ced2  mov     r14, rcx
0x18001ced5  lea     rbx, [rcx+70h]
0x18001ced9  mov     rcx, rbx; SRWLock
0x18001cedc  call    cs:__imp_AcquireSRWLockExclusive
0x18001cee2  mov     [rbp+var_28], rbx
0x18001cee6  lea     rcx, [rbp+var_20]
0x18001ceea  call    ??0?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18001ceef  nop
0x18001cef0  xor     edi, edi
0x18001cef2  cmp     edi, esi
0x18001cef4  jnb     short loc_18001CF53
0x18001cef6  mov     [rbp+TargetHandle], 0
0x18001cefe  lea     r8, [rbp+TargetHandle]; lpTargetHandle
0x18001cf02  mov     rdx, [r15+rdi*8]; hSourceHandle
0x18001cf06  mov     rcx, r12; hSourceProcessHandle
0x18001cf09  call    ?DuplicateClientHandle@Server@Capture@Graphics@Windows@@YAJPEAX0PEAPEAX@Z; Windows::Graphics::Capture::Server::DuplicateClientHandle(void *,void *,void * *)
0x18001cf0e  mov     ebx, eax
0x18001cf10  test    eax, eax
0x18001cf12  js      short loc_18001CF4C
0x18001cf14  mov     rax, [rbp+TargetHandle]
0x18001cf18  mov     [rbp+arg_0], rax
0x18001cf1c  mov     rdx, qword ptr [rbp+var_20+8]
0x18001cf20  lea     rcx, [rbp+var_20]
0x18001cf24  cmp     rdx, [rbp+var_10]
0x18001cf28  jz      short loc_18001CF35
0x18001cf2a  lea     rdx, [rbp+arg_0]
0x18001cf2e  call    ??$_Emplace_back_with_unused_capacity@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_back_with_unused_capacity<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18001cf33  jmp     short loc_18001CF3F
0x18001cf35  lea     r8, [rbp+arg_0]
0x18001cf39  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18001cf3e  nop
0x18001cf3f  lea     rcx, [rbp+arg_0]
0x18001cf43  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001cf48  inc     edi
0x18001cf4a  jmp     short loc_18001CEF2
0x18001cf4c  mov     edx, 0E2h
0x18001cf51  jmp     short loc_18001CF79
0x18001cf53  mov     rcx, [r14+30h]
0x18001cf57  mov     rax, [rcx]
0x18001cf5a  mov     r9, qword ptr [rbp+var_20]
0x18001cf5e  mov     r8d, esi
0x18001cf61  lea     rdx, [rbp+arg_20]
0x18001cf65  mov     rax, [rax+28h]
0x18001cf69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf6e  mov     ebx, eax
0x18001cf70  test    eax, eax
0x18001cf72  jns     short loc_18001CFC9
0x18001cf74  mov     edx, 0EBh; void *
0x18001cf79  mov     rcx, [rbp+28h]; this
0x18001cf7d  mov     r9d, eax; char *
0x18001cf80  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001cf87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf8c  nop
0x18001cf8d  mov     rcx, qword ptr [rbp+var_20]
0x18001cf91  test    rcx, rcx
0x18001cf94  jz      loc_18001D01A
0x18001cf9a  mov     rdx, qword ptr [rbp+var_20+8]
0x18001cf9e  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)
0x18001cfa3  mov     rcx, qword ptr [rbp+var_20]
0x18001cfa7  mov     rdx, [rbp+var_10]
0x18001cfab  sub     rdx, rcx
0x18001cfae  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001cfb2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001cfb7  xorps   xmm0, xmm0
0x18001cfba  movdqu  [rbp+var_20], xmm0
0x18001cfbf  mov     [rbp+var_10], 0
0x18001cfc7  jmp     short loc_18001D01A
0x18001cfc9  mov     rcx, cs:?g_DCompManager@Server@Capture@Graphics@Windows@@3V?$unique_ptr@VDCompManager@Server@Capture@Graphics@Windows@@U?$default_delete@VDCompManager@Server@Capture@Graphics@Windows@@@std@@@std@@A; this
0x18001cfd0  call    ?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ; Windows::Graphics::Capture::Server::DCompManager::Commit(void)
0x18001cfd5  mov     ebx, eax
0x18001cfd7  test    eax, eax
0x18001cfd9  jns     short loc_18001CFE2
0x18001cfdb  mov     edx, 0EEh
0x18001cfe0  jmp     short loc_18001CF79
0x18001cfe2  mov     rcx, qword ptr [rbp+var_20]
0x18001cfe6  test    rcx, rcx
0x18001cfe9  jz      short loc_18001D018
0x18001cfeb  mov     rdx, qword ptr [rbp+var_20+8]
0x18001cfef  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &)
0x18001cff4  mov     rcx, qword ptr [rbp+var_20]
0x18001cff8  mov     rdx, [rbp+var_10]
0x18001cffc  sub     rdx, rcx
0x18001cfff  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001d003  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d008  xorps   xmm0, xmm0
0x18001d00b  movdqu  [rbp+var_20], xmm0
0x18001d010  mov     [rbp+var_10], 0
0x18001d018  xor     ebx, ebx
0x18001d01a  lea     rcx, [rbp+var_28]
0x18001d01e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001d023  mov     eax, ebx
0x18001d025  lea     r11, [rsp+60h+var_s0]
0x18001d02a  mov     rbx, [r11+38h]
0x18001d02e  mov     rsi, [r11+40h]
0x18001d032  mov     rsp, r11
0x18001d035  pop     r15
0x18001d037  pop     r14
0x18001d039  pop     r12
0x18001d03b  pop     rdi
0x18001d03c  pop     rbp
0x18001d03d  retn
```
