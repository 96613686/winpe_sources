# HDV::IPC::Details::CallImpl::CallImpl(HDV::IPC::CallControlBlock *,void *)

- ea: `0x140131910`
- end: `0x140131b2c`
- name: `??0CallImpl@Details@IPC@HDV@@QEAA@PEAUCallControlBlock@23@PEAX@Z`
- size: `540`
- prototype: `_QWORD(HDV::IPC::Details::CallImpl *__hidden this, struct HDV::IPC::CallControlBlock *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140131420`

## callees

- `0x140021694`
- `0x14005b628`
- `0x1400841e4`
- `0x140096740`
- `0x140131910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401319d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140131a79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1401319d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140131a79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131a1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131a1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140131abf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131a4a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131af0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131a4a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140131af0`

## string_xrefs

- `0x140131a04`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131a5f`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131aa9`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`
- `0x140131b05`: `onecore\vm\dv\host\ipc\devicehostservices.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HDV::IPC::Details::CallImpl *__fastcall HDV::IPC::Details::CallImpl::CallImpl(
        HDV::IPC::Details::CallImpl *this,
        struct HDV::IPC::CallControlBlock *a2,
        void *a3)
{
  HANDLE EventW; // rax
  const char *v7; // r9
  void *v8; // r14
  HANDLE *v9; // rbx
  HANDLE CurrentProcess; // rax
  const char *v11; // r9
  HANDLE v12; // rax
  const char *v13; // r9
  void *v14; // rdi
  __int64 v15; // rbx
  HANDLE v16; // rax
  const char *v17; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *((_QWORD *)this + 1) = MigrationTransferTransportAdapterTarget::`vbtable'{for `IMigrationTransferTransportAdapterTarget'};
  Vml::VmSharableObject::VmSharableObject((HDV::IPC::Details::CallImpl *)((char *)this + 80));
  *((_QWORD *)this + 2) = 0;
  Vml::VmComLockServerImp<0>::VmComLockServerImp<0>((char *)this + 24);
  *(_QWORD *)this = &HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmComObject'};
  *((_QWORD *)this + 3) = &HDV::IPC::Details::CallImpl::`vftable';
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmSharableObject'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 4) = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) - 72;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_WORD *)this + 32) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 40,
    EventW);
  v8 = (void *)*((_QWORD *)this + 5);
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v7);
  v9 = (HANDLE *)*((_QWORD *)this + 4);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v8, a3, v9, 0x100002u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v11);
  v12 = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 48,
    v12);
  v14 = (void *)*((_QWORD *)this + 6);
  if ( (((unsigned __int64)v14 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v13);
  v15 = *((_QWORD *)this + 4);
  v16 = GetCurrentProcess();
  if ( !DuplicateHandle(v16, v14, a3, (LPHANDLE)(v15 + 8), 0x100002u, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\vm\\dv\\host\\ipc\\devicehostservices.cpp",
      v17);
  return this;
}

```

## disassembly

```asm
0x140131910  mov     rax, rsp
0x140131913  mov     [rax+10h], rbx
0x140131917  mov     [rax+18h], rbp
0x14013191b  mov     [rax+20h], r9d
0x14013191f  mov     [rax+8], rcx
0x140131923  push    rsi
0x140131924  push    rdi
0x140131925  push    r14
0x140131927  sub     rsp, 40h
0x14013192b  mov     rbp, r8
0x14013192e  mov     rdi, rdx
0x140131931  mov     rsi, rcx
0x140131934  mov     dword ptr [rax+20h], 0
0x14013193b  lea     rax, ??_8MigrationTransferTransportAdapterTarget@@7BIMigrationTransferTransportAdapterTarget@@@; const MigrationTransferTransportAdapterTarget::`vbtable'{for `IMigrationTransferTransportAdapterTarget'}
0x140131942  mov     [rcx+8], rax
0x140131946  add     rcx, 50h ; 'P'; this
0x14013194a  call    ??0VmSharableObject@Vml@@IEAA@XZ; Vml::VmSharableObject::VmSharableObject(void)
0x14013194f  nop
0x140131950  mov     [rsp+58h+arg_18], 1
0x140131958  mov     qword ptr [rsi+10h], 0
0x140131960  lea     rcx, [rsi+18h]
0x140131964  call    ??0?$VmComLockServerImp@$0A@@Vml@@IEAA@XZ; Vml::VmComLockServerImp<0>::VmComLockServerImp<0>(void)
0x140131969  nop
0x14013196a  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmComObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmComObject'}
0x140131971  mov     [rsi], rax
0x140131974  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6B@; const HDV::IPC::Details::CallImpl::`vftable'
0x14013197b  mov     [rsi+18h], rax
0x14013197f  mov     rax, [rsi+8]
0x140131983  movsxd  rcx, dword ptr [rax+4]
0x140131987  lea     rax, ??_7CallImpl@Details@IPC@HDV@@6BVmSharableObject@Vml@@@; const HDV::IPC::Details::CallImpl::`vftable'{for `Vml::VmSharableObject'}
0x14013198e  mov     [rcx+rsi+8], rax
0x140131993  mov     rax, [rsi+8]
0x140131997  movsxd  rcx, dword ptr [rax+4]
0x14013199b  lea     edx, [rcx-48h]
0x14013199e  mov     [rcx+rsi+4], edx
0x1401319a2  mov     [rsi+20h], rdi
0x1401319a6  lea     rbx, [rsi+28h]
0x1401319aa  mov     qword ptr [rbx], 0
0x1401319b1  lea     rdi, [rsi+30h]
0x1401319b5  mov     qword ptr [rdi], 0
0x1401319bc  mov     qword ptr [rsi+38h], 0
0x1401319c4  mov     word ptr [rsi+40h], 0
0x1401319ca  xor     r9d, r9d; lpName
0x1401319cd  xor     r8d, r8d; bInitialState
0x1401319d0  xor     edx, edx; bManualReset
0x1401319d2  xor     ecx, ecx; lpEventAttributes
0x1401319d4  call    cs:__imp_CreateEventW
0x1401319db  nop     dword ptr [rax+rax+00h]
0x1401319e0  mov     rdx, rax
0x1401319e3  mov     rcx, rbx
0x1401319e6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1401319eb  mov     r14, [rbx]
0x1401319ee  lea     rax, [r14+1]
0x1401319f2  test    rax, 0FFFFFFFFFFFFFFFEh
0x1401319f8  setz    al
0x1401319fb  mov     rcx, [rsp+58h]; this
0x140131a00  test    al, al
0x140131a02  jz      short loc_140131A16
0x140131a04  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131a0b  mov     edx, 26h ; '&'; void *
0x140131a10  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131a16  mov     rbx, [rsi+20h]
0x140131a1a  call    cs:__imp_GetCurrentProcess
0x140131a21  nop     dword ptr [rax+rax+00h]
0x140131a26  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140131a2e  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x140131a36  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x140131a3e  mov     r9, rbx; lpTargetHandle
0x140131a41  mov     r8, rbp; hTargetProcessHandle
0x140131a44  mov     rdx, r14; hSourceHandle
0x140131a47  mov     rcx, rax; hSourceProcessHandle
0x140131a4a  call    cs:__imp_DuplicateHandle
0x140131a51  nop     dword ptr [rax+rax+00h]
0x140131a56  mov     rcx, [rsp+58h]; this
0x140131a5b  test    eax, eax
0x140131a5d  jnz     short loc_140131A6F
0x140131a5f  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131a66  lea     edx, [rax+2Dh]; void *
0x140131a69  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131a6f  xor     r9d, r9d; lpName
0x140131a72  xor     r8d, r8d; bInitialState
0x140131a75  xor     edx, edx; bManualReset
0x140131a77  xor     ecx, ecx; lpEventAttributes
0x140131a79  call    cs:__imp_CreateEventW
0x140131a80  nop     dword ptr [rax+rax+00h]
0x140131a85  mov     rdx, rax
0x140131a88  mov     rcx, rdi
0x140131a8b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140131a90  mov     rdi, [rdi]
0x140131a93  lea     rax, [rdi+1]
0x140131a97  test    rax, 0FFFFFFFFFFFFFFFEh
0x140131a9d  setz    al
0x140131aa0  mov     rcx, [rsp+58h]; this
0x140131aa5  test    al, al
0x140131aa7  jz      short loc_140131ABB
0x140131aa9  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131ab0  mov     edx, 30h ; '0'; void *
0x140131ab5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131abb  mov     rbx, [rsi+20h]
0x140131abf  call    cs:__imp_GetCurrentProcess
0x140131ac6  nop     dword ptr [rax+rax+00h]
0x140131acb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140131ad3  mov     [rsp+58h+bInheritHandle], 0; bInheritHandle
0x140131adb  mov     [rsp+58h+dwDesiredAccess], 100002h; dwDesiredAccess
0x140131ae3  lea     r9, [rbx+8]; lpTargetHandle
0x140131ae7  mov     r8, rbp; hTargetProcessHandle
0x140131aea  mov     rdx, rdi; hSourceHandle
0x140131aed  mov     rcx, rax; hSourceProcessHandle
0x140131af0  call    cs:__imp_DuplicateHandle
0x140131af7  nop     dword ptr [rax+rax+00h]
0x140131afc  mov     rcx, [rsp+58h]; this
0x140131b01  test    eax, eax
0x140131b03  jnz     short loc_140131B15
0x140131b05  lea     r8, aOnecoreVmDvHos; "onecore\\vm\\dv\\host\\ipc\\devicehosts"...
0x140131b0c  lea     edx, [rax+37h]; void *
0x140131b0f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140131b15  mov     rax, rsi
0x140131b18  mov     rbx, [rsp+58h+arg_8]
0x140131b1d  mov     rbp, [rsp+58h+arg_10]
0x140131b22  add     rsp, 40h
0x140131b26  pop     r14
0x140131b28  pop     rdi
0x140131b29  pop     rsi
0x140131b2a  retn
```
