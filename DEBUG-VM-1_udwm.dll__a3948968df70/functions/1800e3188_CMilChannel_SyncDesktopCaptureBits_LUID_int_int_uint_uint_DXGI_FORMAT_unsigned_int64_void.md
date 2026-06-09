# CMilChannel::SyncDesktopCaptureBits(_LUID,int,int,uint,uint,DXGI_FORMAT,unsigned __int64,void *)

- ea: `0x1800e3188`
- end: `0x1800e33d2`
- name: `?SyncDesktopCaptureBits@CMilChannel@@QEAAJU_LUID@@HHIIW4DXGI_FORMAT@@_KPEAX@Z`
- size: `586`
- prototype: `__int64 __usercall@<rax>(CMilChannel *__hidden this@<rcx>, struct _LUID@<rdx>, int@<r8d>, int@<r9d>, unsigned int, unsigned int, enum DXGI_FORMAT, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005bca4`

## callees

- `0x18005da70`
- `0x1800802e8`
- `0x180081a68`
- `0x1800e0e74`
- `0x1800e30b4`
- `0x1800e3188`
- `0x1800e33d8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e31b3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e31b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e339f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e339f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e329a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e3291`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e329a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800e324e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800e32c3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800e324e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800e32c3`

## string_xrefs

- `0x1800e325c`: `clientcore\windows\dwm\common\dwm\milchannel.cpp`
- `0x1800e32d1`: `clientcore\windows\dwm\common\dwm\milchannel.cpp`
- `0x1800e3320`: `clientcore\windows\dwm\common\dwm\milchannel.cpp`
- `0x1800e3366`: `clientcore\windows\dwm\common\dwm\milchannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMilChannel::SyncDesktopCaptureBits(
        struct IDwmChannelProvider **this,
        struct _LUID a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        enum DXGI_FORMAT a7,
        unsigned __int64 a8,
        HANDLE hSourceHandle)
{
  HANDLE EventW; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  const char *v16; // r9
  unsigned int LastError; // ebx
  HANDLE v19; // rbx
  HANDLE v20; // rax
  const char *v21; // r9
  int v22; // eax
  int v23; // eax
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-71h]
  __int64 v25; // [rsp+40h] [rbp-51h] BYREF
  HANDLE v26; // [rsp+48h] [rbp-49h] BYREF
  int v27; // [rsp+50h] [rbp-41h] BYREF
  struct _LUID v28; // [rsp+54h] [rbp-3Dh]
  int v29; // [rsp+5Ch] [rbp-35h]
  int v30; // [rsp+60h] [rbp-31h]
  unsigned int v31; // [rsp+64h] [rbp-2Dh]
  unsigned int v32; // [rsp+68h] [rbp-29h]
  enum DXGI_FORMAT v33; // [rsp+6Ch] [rbp-25h]
  _BYTE v34[20]; // [rsp+70h] [rbp-21h] BYREF
  int v35; // [rsp+84h] [rbp-Dh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+37h]

  EventW = CreateEventW(0, 0, 0, 0);
  v26 = EventW;
  if ( EventW )
  {
    CMilChannel::CChannelLock::CChannelLock((CMilChannel::CChannelLock *)&v25, this[5]);
    v27 = 165;
    *(_OWORD *)&v34[4] = 0;
    v35 = 0;
    v28 = a2;
    v29 = a3;
    v30 = a4;
    v31 = a5;
    v32 = a6;
    v33 = a7;
    *(_QWORD *)v34 = a8;
    CurrentProcess = GetCurrentProcess();
    v15 = GetCurrentProcess();
    if ( !DuplicateHandle(v15, EventW, CurrentProcess, (LPHANDLE)&v34[8], 0, 0, 2u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB4,
                    (unsigned int)"clientcore\\windows\\dwm\\common\\dwm\\milchannel.cpp",
                    v16);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
      return LastError;
    }
    v19 = GetCurrentProcess();
    v20 = GetCurrentProcess();
    if ( !DuplicateHandle(v20, hSourceHandle, v19, (LPHANDLE)&v34[16], 0, 0, 2u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBC,
                    (unsigned int)"clientcore\\windows\\dwm\\common\\dwm\\milchannel.cpp",
                    v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
      return LastError;
    }
    v22 = CMilChannel::SendCommand((CMilChannel *)this, &v27, 0x38u);
    LastError = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"clientcore\\windows\\dwm\\common\\dwm\\milchannel.cpp",
        (const char *)(unsigned int)v22,
        dwDesiredAccess);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
      return LastError;
    }
    v23 = CMilChannel::SyncFlushInternal((CMilChannel *)this);
    LastError = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF,
        (unsigned int)"clientcore\\windows\\dwm\\common\\dwm\\milchannel.cpp",
        (const char *)(unsigned int)v23,
        dwDesiredAccess);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
      return LastError;
    }
    WaitForSingleObject(EventW, 0x1388u);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 80LL))(v25);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
  return 0;
}

```

## disassembly

```asm
0x1800e3188  push    rbp
0x1800e318a  push    rbx
0x1800e318b  push    rsi
0x1800e318c  push    rdi
0x1800e318d  push    r14
0x1800e318f  push    r15
0x1800e3191  lea     rbp, [rsp-7]
0x1800e3196  sub     rsp, 98h
0x1800e319d  mov     r14d, r9d
0x1800e31a0  mov     r15d, r8d
0x1800e31a3  mov     rbx, rdx
0x1800e31a6  mov     rsi, rcx
0x1800e31a9  xor     r9d, r9d; lpName
0x1800e31ac  xor     r8d, r8d; bInitialState
0x1800e31af  xor     edx, edx; bManualReset
0x1800e31b1  xor     ecx, ecx; lpEventAttributes
0x1800e31b3  call    cs:__imp_CreateEventW
0x1800e31b9  mov     rdi, rax
0x1800e31bc  mov     [rbp+2Fh+var_78], rax
0x1800e31c0  test    rax, rax
0x1800e31c3  jz      loc_1800E33B6
0x1800e31c9  mov     rdx, [rsi+28h]; struct IDwmChannelProvider *
0x1800e31cd  lea     rcx, [rbp+2Fh+var_80]; this
0x1800e31d1  call    ??0CChannelLock@CMilChannel@@QEAA@PEAUIDwmChannelProvider@@@Z; CMilChannel::CChannelLock::CChannelLock(IDwmChannelProvider *)
0x1800e31d6  mov     [rbp+2Fh+var_70], 0A5h
0x1800e31dd  xorps   xmm0, xmm0
0x1800e31e0  xor     eax, eax
0x1800e31e2  movups  [rbp+2Fh+var_6C], xmm0
0x1800e31e6  movups  [rbp+2Fh+var_5C], xmm0
0x1800e31ea  movups  xmmword ptr [rbp+2Fh+TargetHandle], xmm0
0x1800e31ee  mov     [rbp+2Fh+var_3C], eax
0x1800e31f1  mov     qword ptr [rbp+2Fh+var_6C], rbx
0x1800e31f5  mov     dword ptr [rbp+2Fh+var_6C+8], r15d
0x1800e31f9  mov     dword ptr [rbp+2Fh+var_6C+0Ch], r14d
0x1800e31fd  mov     eax, [rbp+2Fh+arg_20]
0x1800e3200  mov     dword ptr [rbp+2Fh+var_5C], eax
0x1800e3203  mov     eax, [rbp+2Fh+arg_28]
0x1800e3206  mov     dword ptr [rbp+2Fh+var_5C+4], eax
0x1800e3209  mov     eax, [rbp+2Fh+arg_30]
0x1800e320c  mov     dword ptr [rbp+2Fh+var_5C+8], eax
0x1800e320f  mov     rax, [rbp+2Fh+arg_38]
0x1800e3213  mov     qword ptr [rbp+2Fh+var_5C+0Ch], rax
0x1800e3217  call    cs:__imp_GetCurrentProcess
0x1800e321d  mov     rbx, rax
0x1800e3220  call    cs:__imp_GetCurrentProcess
0x1800e3226  mov     r14d, 2
0x1800e322c  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x1800e3231  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x1800e3239  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x1800e3241  lea     r9, [rbp+2Fh+TargetHandle+4]; lpTargetHandle
0x1800e3245  mov     r8, rbx; hTargetProcessHandle
0x1800e3248  mov     rdx, rdi; hSourceHandle
0x1800e324b  mov     rcx, rax; hSourceProcessHandle
0x1800e324e  call    cs:__imp_DuplicateHandle
0x1800e3254  test    eax, eax
0x1800e3256  jnz     short loc_1800E3291
0x1800e3258  mov     rcx, [rbp+37h]; this
0x1800e325c  lea     r8, aClientcoreWind_58; "clientcore\\windows\\dwm\\common\\dwm\\"...
0x1800e3263  mov     edx, 0B4h; void *
0x1800e3268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e326d  mov     ebx, eax
0x1800e326f  mov     rcx, [rbp+2Fh+var_80]
0x1800e3273  mov     rdx, [rcx]
0x1800e3276  mov     rax, [rdx+50h]
0x1800e327a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e327f  nop
0x1800e3280  lea     rcx, [rbp+2Fh+var_78]
0x1800e3284  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3289  nop
0x1800e328a  mov     eax, ebx
0x1800e328c  jmp     loc_1800E33C2
0x1800e3291  call    cs:__imp_GetCurrentProcess
0x1800e3297  mov     rbx, rax
0x1800e329a  call    cs:__imp_GetCurrentProcess
0x1800e32a0  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x1800e32a5  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x1800e32ad  mov     [rsp+0C0h+dwDesiredAccess], 0; int
0x1800e32b5  lea     r9, [rbp+2Fh+TargetHandle+0Ch]; lpTargetHandle
0x1800e32b9  mov     r8, rbx; hTargetProcessHandle
0x1800e32bc  mov     rdx, [rbp+2Fh+hSourceHandle]; hSourceHandle
0x1800e32c0  mov     rcx, rax; hSourceProcessHandle
0x1800e32c3  call    cs:__imp_DuplicateHandle
0x1800e32c9  test    eax, eax
0x1800e32cb  jnz     short loc_1800E3301
0x1800e32cd  mov     rcx, [rbp+37h]; this
0x1800e32d1  lea     r8, aClientcoreWind_58; "clientcore\\windows\\dwm\\common\\dwm\\"...
0x1800e32d8  mov     edx, 0BCh; void *
0x1800e32dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e32e2  mov     ebx, eax
0x1800e32e4  mov     rcx, [rbp+2Fh+var_80]
0x1800e32e8  mov     rdx, [rcx]
0x1800e32eb  mov     rax, [rdx+50h]
0x1800e32ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e32f4  nop
0x1800e32f5  lea     rcx, [rbp+2Fh+var_78]
0x1800e32f9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e32fe  nop
0x1800e32ff  jmp     short loc_1800E328A
0x1800e3301  mov     r8d, 38h ; '8'; unsigned int
0x1800e3307  lea     rdx, [rbp+2Fh+var_70]; void *
0x1800e330b  mov     rcx, rsi; this
0x1800e330e  call    ?SendCommand@CMilChannel@@AEAAJPEAXI@Z; CMilChannel::SendCommand(void *,uint)
0x1800e3313  mov     ebx, eax
0x1800e3315  test    eax, eax
0x1800e3317  jns     short loc_1800E3351
0x1800e3319  mov     rcx, [rbp+37h]; this
0x1800e331d  mov     r9d, eax; char *
0x1800e3320  lea     r8, aClientcoreWind_58; "clientcore\\windows\\dwm\\common\\dwm\\"...
0x1800e3327  mov     edx, 0BEh; void *
0x1800e332c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3331  mov     rcx, [rbp+2Fh+var_80]
0x1800e3335  mov     rdx, [rcx]
0x1800e3338  mov     rax, [rdx+50h]
0x1800e333c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3341  nop
0x1800e3342  lea     rcx, [rbp+2Fh+var_78]
0x1800e3346  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e334b  nop
0x1800e334c  jmp     loc_1800E328A
0x1800e3351  mov     rcx, rsi; this
0x1800e3354  call    ?SyncFlushInternal@CMilChannel@@AEAAJXZ; CMilChannel::SyncFlushInternal(void)
0x1800e3359  mov     ebx, eax
0x1800e335b  test    eax, eax
0x1800e335d  jns     short loc_1800E3397
0x1800e335f  mov     rcx, [rbp+37h]; this
0x1800e3363  mov     r9d, eax; char *
0x1800e3366  lea     r8, aClientcoreWind_58; "clientcore\\windows\\dwm\\common\\dwm\\"...
0x1800e336d  mov     edx, 0BFh; void *
0x1800e3372  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3377  mov     rcx, [rbp+2Fh+var_80]
0x1800e337b  mov     rdx, [rcx]
0x1800e337e  mov     rax, [rdx+50h]
0x1800e3382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3387  nop
0x1800e3388  lea     rcx, [rbp+2Fh+var_78]
0x1800e338c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3391  nop
0x1800e3392  jmp     loc_1800E328A
0x1800e3397  mov     edx, 1388h; dwMilliseconds
0x1800e339c  mov     rcx, rdi; hHandle
0x1800e339f  call    cs:__imp_WaitForSingleObject
0x1800e33a5  mov     rcx, [rbp+2Fh+var_80]
0x1800e33a9  mov     rax, [rcx]
0x1800e33ac  mov     rax, [rax+50h]
0x1800e33b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e33b5  nop
0x1800e33b6  lea     rcx, [rbp+2Fh+var_78]
0x1800e33ba  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e33bf  nop
0x1800e33c0  xor     eax, eax
0x1800e33c2  add     rsp, 98h
0x1800e33c9  pop     r15
0x1800e33cb  pop     r14
0x1800e33cd  pop     rdi
0x1800e33ce  pop     rsi
0x1800e33cf  pop     rbx
0x1800e33d0  pop     rbp
0x1800e33d1  retn
```
