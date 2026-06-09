# Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::DedicatedThreadRequestDispatcher(Microsoft::Bluetooth::Foundation::DeviceIoTarget &,void *,int)

- ea: `0x18001b274`
- end: `0x18001b370`
- name: `??0DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@QEAA@AEAVDeviceIoTarget@234@PEAXH@Z`
- size: `252`
- prototype: `Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *__fastcall(Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *this, struct Microsoft::Bluetooth::Foundation::DeviceIoTarget *, void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aa18`

## callees

- `0x1800029cc`
- `0x18000dca8`
- `0x180012130`
- `0x18001aac8`
- `0x18001b274`
- `0x18001b930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001b32b`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18001b32b`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001b2d7`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18001b2d7`

## pseudocode

```c
Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *__fastcall Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::DedicatedThreadRequestDispatcher(
        Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *this,
        struct Microsoft::Bluetooth::Foundation::DeviceIoTarget *a2,
        void *a3,
        int a4)
{
  _QWORD *v5; // rbx
  HANDLE IoCompletionPort; // rax
  const char *v7; // r9
  __int128 v8; // xmm1
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *v12; // [rsp+48h] [rbp+10h] BYREF
  void (__fastcall *v13)(Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher *__hidden); // [rsp+50h] [rbp+18h] BYREF

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::`vftable';
  *((_DWORD *)this + 4) = a4;
  *((_QWORD *)this + 3) = a3;
  v5 = (_QWORD *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 1;
  memset_0((char *)this + 64, 0, 0x200u);
  IoCompletionPort = CreateIoCompletionPort(*((HANDLE *)this + 3), 0, 0xC792AC28, 1u);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v5,
    IoCompletionPort);
  if ( ((*v5 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4AE,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\DeviceIoTarget.h",
      v7);
  v13 = Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::IoThread;
  v12 = this;
  ____Start_P8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_EPEAV12345__thread_std__AEAAX__QEAP8DedicatedThreadRequestDispatcher_Details_Foundation_Bluetooth_Microsoft__EAAXX_E__QEAPEAV23456__Z(
    (__int64)&v10,
    &v13,
    &v12);
  if ( *((_DWORD *)this + 12) )
  {
    _o_terminate();
    __debugbreak();
  }
  v8 = v10;
  v10 = 0;
  *(_OWORD *)((char *)this + 40) = v8;
  std::thread::~thread((std::thread *)&v10);
  return this;
}

```

## disassembly

```asm
0x18001b274  mov     [rsp+arg_18], rbx
0x18001b279  mov     [rsp+arg_0], rcx
0x18001b27e  push    rdi
0x18001b27f  sub     rsp, 30h
0x18001b283  mov     rdi, rcx
0x18001b286  mov     [rcx+8], rdx
0x18001b28a  lea     rax, ??_7DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::`vftable'
0x18001b291  mov     [rcx], rax
0x18001b294  mov     [rcx+10h], r9d
0x18001b298  mov     [rcx+18h], r8
0x18001b29c  lea     rbx, [rcx+20h]
0x18001b2a0  mov     qword ptr [rbx], 0
0x18001b2a7  xorps   xmm0, xmm0
0x18001b2aa  movups  xmmword ptr [rcx+28h], xmm0
0x18001b2ae  mov     qword ptr [rcx+38h], 1
0x18001b2b6  add     rcx, 40h ; '@'; void *
0x18001b2ba  xor     edx, edx; Val
0x18001b2bc  mov     r8d, 200h; Size
0x18001b2c2  call    memset_0
0x18001b2c7  xor     edx, edx; ExistingCompletionPort
0x18001b2c9  lea     r9d, [rdx+1]; NumberOfConcurrentThreads
0x18001b2cd  mov     r8d, 0C792AC28h; CompletionKey
0x18001b2d3  mov     rcx, [rdi+18h]; FileHandle
0x18001b2d7  call    cs:__imp_CreateIoCompletionPort
0x18001b2dd  mov     rdx, rax
0x18001b2e0  mov     rcx, rbx
0x18001b2e3  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001b2e8  mov     rax, [rbx]
0x18001b2eb  inc     rax
0x18001b2ee  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001b2f4  setz    al
0x18001b2f7  mov     rcx, [rsp+38h]; this
0x18001b2fc  test    al, al
0x18001b2fe  jnz     short loc_18001B35E
0x18001b300  lea     rax, ?IoThread@DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Foundation::Details::DedicatedThreadRequestDispatcher::IoThread(void)
0x18001b307  mov     [rsp+38h+arg_10], rax
0x18001b30c  mov     [rsp+38h+arg_8], rdi
0x18001b311  lea     r8, [rsp+38h+arg_8]
0x18001b316  lea     rdx, [rsp+38h+arg_10]
0x18001b31b  lea     rcx, [rsp+38h+var_18]
0x18001b320  call    ??$_Start@P8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_EPEAV12345@@thread@std@@AEAAX$$QEAP8DedicatedThreadRequestDispatcher@Details@Foundation@Bluetooth@Microsoft@@EAAXX_E$$QEAPEAV23456@@Z
0x18001b325  cmp     dword ptr [rdi+30h], 0
0x18001b329  jz      short loc_18001B332
0x18001b32b  call    cs:__imp__o_terminate
0x18001b331  int     3; Trap to Debugger
0x18001b332  xorps   xmm0, xmm0
0x18001b335  movaps  xmm1, [rsp+38h+var_18]
0x18001b33a  movdqa  [rsp+38h+var_18], xmm0
0x18001b340  movdqu  xmmword ptr [rdi+28h], xmm1
0x18001b345  lea     rcx, [rsp+38h+var_18]; this
0x18001b34a  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18001b34f  nop
0x18001b350  mov     rax, rdi
0x18001b353  mov     rbx, [rsp+38h+arg_18]
0x18001b358  add     rsp, 30h
0x18001b35c  pop     rdi
0x18001b35d  retn
0x18001b35e  lea     r8, aOnecoreDrivers_19; "onecore\\drivers\\bluetooth\\foundation"...
0x18001b365  mov     edx, 4AEh; void *
0x18001b36a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
