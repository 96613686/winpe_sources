# CGnssDriverWrapper::CGnssDriverWrapper(GnssDriverListener *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,long *)

- ea: `0x1800e56cc`
- end: `0x1800e5888`
- name: `??0CGnssDriverWrapper@@QEAA@PEAVGnssDriverListener@@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAJ@Z`
- size: `444`
- prototype: `CGnssDriverWrapper *__fastcall(CGnssDriverWrapper *this, __int64, __int64, signed int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e5654`

## callees

- `0x180019704`
- `0x180021450`
- `0x180021a4c`
- `0x180048a04`
- `0x1800642a8`
- `0x1800e56cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800e57ee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolIo` at `0x1800e57ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5859`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5859`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e574c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800e574c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5817`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5817`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e575e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e575e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e57fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e57fd`

## pseudocode

```c
CGnssDriverWrapper *__fastcall CGnssDriverWrapper::CGnssDriverWrapper(
        CGnssDriverWrapper *this,
        __int64 a2,
        __int64 a3,
        signed int *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rbp
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v10; // ebx
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  void **v14; // rax
  void *v15; // rcx
  PTP_IO ThreadpoolIo; // rax
  signed int v17; // eax
  _BYTE v19[8]; // [rsp+40h] [rbp-28h] BYREF
  std::_Ref_count_base *v20; // [rsp+48h] [rbp-20h]

  *(_QWORD *)this = &CGnssDriverWrapper::`vftable';
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 7) = a2;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EventW = CreateEventW(0, 1, 0, 0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    (char *)this + 120,
    EventW);
  if ( *((_QWORD *)this + 15) )
    goto LABEL_5;
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_5:
    v11 = (__int64 *)std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(v19, a3);
    v12 = *v11;
    *v11 = *((_QWORD *)this + 8);
    *((_QWORD *)this + 8) = v12;
    v13 = v11[1];
    v11[1] = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v13;
    if ( v20 )
      std::_Ref_count_base::_Decref(v20);
    v14 = (void **)*((_QWORD *)this + 8);
    if ( v14 )
      v15 = *v14;
    else
      v15 = 0;
    ThreadpoolIo = CreateThreadpoolIo(v15, CGnssDriverWrapper::OnIoCompletionStatic, this, 0);
    *((_QWORD *)this + 10) = ThreadpoolIo;
    if ( ThreadpoolIo )
    {
      EnterCriticalSection(v7);
      v10 = CGnssDriverWrapper::InternalDeviceIoControl(this, 0x220008u, 0, 0, (char *)this + 128, 0x25Cu, 1, 0);
      LeaveCriticalSection(v7);
      if ( v10 >= 0 )
        v10 = 0;
    }
    else
    {
      v17 = GetLastError();
      v10 = v17;
      if ( v17 > 0 )
        v10 = (unsigned __int16)v17 | 0x80070000;
    }
  }
  *a4 = v10;
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(a3);
  return this;
}

```

## disassembly

```asm
0x1800e56cc  mov     rax, rsp
0x1800e56cf  mov     [rax+10h], rbx
0x1800e56d3  mov     [rax+20h], rbp
0x1800e56d7  mov     [rax+18h], r8
0x1800e56db  mov     [rax+8], rcx
0x1800e56df  push    rsi
0x1800e56e0  push    rdi
0x1800e56e1  push    r14
0x1800e56e3  sub     rsp, 50h
0x1800e56e7  mov     r14, r9
0x1800e56ea  mov     rsi, r8
0x1800e56ed  mov     rdi, rcx
0x1800e56f0  lea     rax, ??_7CGnssDriverWrapper@@6B@; const CGnssDriverWrapper::`vftable'
0x1800e56f7  mov     [rcx], rax
0x1800e56fa  mov     dword ptr [rcx+30h], 0
0x1800e5701  mov     [rcx+38h], rdx
0x1800e5705  mov     qword ptr [rcx+40h], 0
0x1800e570d  mov     qword ptr [rcx+48h], 0
0x1800e5715  mov     qword ptr [rcx+50h], 0
0x1800e571d  mov     qword ptr [rcx+58h], 0
0x1800e5725  mov     qword ptr [rcx+60h], 0
0x1800e572d  mov     qword ptr [rcx+68h], 0
0x1800e5735  mov     qword ptr [rcx+70h], 0
0x1800e573d  mov     qword ptr [rcx+78h], 0
0x1800e5745  lea     rbp, [rcx+8]
0x1800e5749  mov     rcx, rbp; lpCriticalSection
0x1800e574c  call    cs:__imp_InitializeCriticalSection
0x1800e5752  xor     r9d, r9d; lpName
0x1800e5755  xor     r8d, r8d; bInitialState
0x1800e5758  lea     edx, [r9+1]; bManualReset
0x1800e575c  xor     ecx, ecx; lpEventAttributes
0x1800e575e  call    cs:__imp_CreateEventW
0x1800e5764  mov     rdx, rax
0x1800e5767  lea     rcx, [rdi+78h]
0x1800e576b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800e5770  cmp     qword ptr [rdi+78h], 0
0x1800e5775  jnz     short loc_1800E5794
0x1800e5777  call    cs:__imp_GetLastError
0x1800e577d  mov     ebx, eax
0x1800e577f  test    eax, eax
0x1800e5781  jle     short loc_1800E578C
0x1800e5783  movzx   ebx, ax
0x1800e5786  or      ebx, 80070000h
0x1800e578c  test    ebx, ebx
0x1800e578e  js      loc_1800E5865
0x1800e5794  mov     rdx, rsi
0x1800e5797  lea     rcx, [rsp+68h+var_28]
0x1800e579c  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x1800e57a1  mov     rdx, rax
0x1800e57a4  mov     rcx, [rax]
0x1800e57a7  mov     rax, [rdi+40h]
0x1800e57ab  mov     [rdx], rax
0x1800e57ae  mov     [rdi+40h], rcx
0x1800e57b2  mov     rcx, [rdx+8]
0x1800e57b6  mov     rax, [rdi+48h]
0x1800e57ba  mov     [rdx+8], rax
0x1800e57be  mov     [rdi+48h], rcx
0x1800e57c2  mov     rcx, [rsp+68h+var_20]; this
0x1800e57c7  test    rcx, rcx
0x1800e57ca  jz      short loc_1800E57D1
0x1800e57cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e57d1  mov     rax, [rdi+40h]
0x1800e57d5  test    rax, rax
0x1800e57d8  jz      short loc_1800E57DF
0x1800e57da  mov     rcx, [rax]
0x1800e57dd  jmp     short loc_1800E57E1
0x1800e57df  xor     ecx, ecx; fl
0x1800e57e1  xor     r9d, r9d; pcbe
0x1800e57e4  mov     r8, rdi; pv
0x1800e57e7  lea     rdx, ?OnIoCompletionStatic@CGnssDriverWrapper@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x1800e57ee  call    cs:__imp_CreateThreadpoolIo
0x1800e57f4  mov     [rdi+50h], rax
0x1800e57f8  test    rax, rax
0x1800e57fb  jnz     short loc_1800E5814
0x1800e57fd  call    cs:__imp_GetLastError
0x1800e5803  mov     ebx, eax
0x1800e5805  test    eax, eax
0x1800e5807  jle     short loc_1800E5865
0x1800e5809  movzx   ebx, ax
0x1800e580c  or      ebx, 80070000h
0x1800e5812  jmp     short loc_1800E5865
0x1800e5814  mov     rcx, rbp; lpCriticalSection
0x1800e5817  call    cs:__imp_EnterCriticalSection
0x1800e581d  lea     rax, [rdi+80h]
0x1800e5824  mov     [rsp+68h+var_30], 0; unsigned int
0x1800e582c  mov     [rsp+68h+var_38], 1; int
0x1800e5834  mov     [rsp+68h+var_40], 25Ch; unsigned int
0x1800e583c  mov     [rsp+68h+var_48], rax; void *
0x1800e5841  xor     r9d, r9d; unsigned int
0x1800e5844  xor     r8d, r8d; void *
0x1800e5847  mov     edx, 220008h; unsigned int
0x1800e584c  mov     rcx, rdi; this
0x1800e584f  call    ?InternalDeviceIoControl@CGnssDriverWrapper@@AEAAJKPEAXK0KHK@Z; CGnssDriverWrapper::InternalDeviceIoControl(ulong,void *,ulong,void *,ulong,int,ulong)
0x1800e5854  mov     ebx, eax
0x1800e5856  mov     rcx, rbp; lpCriticalSection
0x1800e5859  call    cs:__imp_LeaveCriticalSection
0x1800e585f  test    ebx, ebx
0x1800e5861  js      short loc_1800E5865
0x1800e5863  xor     ebx, ebx
0x1800e5865  mov     [r14], ebx
0x1800e5868  mov     rcx, rsi
0x1800e586b  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800e5870  mov     rax, rdi
0x1800e5873  lea     r11, [rsp+68h+var_18]
0x1800e5878  mov     rbx, [r11+28h]
0x1800e587c  mov     rbp, [r11+38h]
0x1800e5880  mov     rsp, r11
0x1800e5883  pop     r14
0x1800e5885  pop     rdi
0x1800e5886  pop     rsi
0x1800e5887  retn
```
