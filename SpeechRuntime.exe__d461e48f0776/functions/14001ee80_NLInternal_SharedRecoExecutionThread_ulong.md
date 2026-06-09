# NLInternal::SharedRecoExecutionThread(ulong *)

- ea: `0x14001ee80`
- end: `0x14001f00e`
- name: `?SharedRecoExecutionThread@NLInternal@@YAKPEAK@Z`
- size: `398`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140007c0c`
- `0x14001edc0`
- `0x14001ee80`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001eeb8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001eeb8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001efd0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001efd0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001eee7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001eee7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001ef8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001ef8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001eefe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001eefe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001ef58`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001ef7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001efac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001efca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001ef58`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001ef7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001efac`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001efca`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NLInternal::SharedRecoExecutionThread(unsigned __int8 *Parameter)
{
  HANDLE EventW; // rbx
  HRESULT v3; // edi
  int v4; // edi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF
  HANDLE v10; // [rsp+88h] [rbp+48h] BYREF

  EventW = 0;
  v10 = 0;
  ppv = 0;
  if ( Parameter )
    (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)Parameter + 8LL))(Parameter);
  v3 = CoInitializeEx(0, 2u);
  if ( v3 >= 0 )
  {
    v3 = CoCreateInstance(&CLSID_SpSapiServer, 0, 0x17u, &GUID_31e99ed0_6ad8_431b_ae3c_652d9e8c7832, &ppv);
    if ( v3 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v10 = EventW;
      if ( !EventW )
      {
        v3 = -2147024882;
        v8 = 0;
LABEL_13:
        v5 = 0;
        if ( v3 != -2147200943 )
          v5 = v3;
        v3 = v5;
        *((_DWORD *)Parameter + 6) = v5;
        SetEvent(*((HANDLE *)Parameter + 2));
        goto LABEL_16;
      }
    }
  }
  v8 = 0;
  if ( v3 < 0 )
    goto LABEL_13;
  v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, HANDLE, int *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         Parameter[28],
         EventW,
         &v8);
  if ( v3 < 0 )
    goto LABEL_13;
  *((_DWORD *)Parameter + 6) = 0;
  SetEvent(*((HANDLE *)Parameter + 2));
  if ( v8 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
    SetEvent(hEvent);
    if ( v4 >= 0 )
      WaitForSingleObject(EventW, 0xFFFFFFFF);
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 40LL))(ppv);
  SetEvent(qword_14004DDD0);
  if ( v3 < 0 )
    goto LABEL_13;
LABEL_16:
  CoUninitialize();
  v6 = 0;
  if ( v3 < 0 )
    v6 = v3;
  (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&ppv);
  ATL::CHandle::~CHandle((ATL::CHandle *)&v10);
  return v6;
}

```

## disassembly

```asm
0x14001ee80  push    rbp
0x14001ee82  push    rbx
0x14001ee83  push    rsi
0x14001ee84  push    rdi
0x14001ee85  push    r15
0x14001ee87  mov     rbp, rsp
0x14001ee8a  sub     rsp, 40h
0x14001ee8e  mov     rsi, rcx
0x14001ee91  xor     ebx, ebx
0x14001ee93  mov     [rbp+arg_18], rbx
0x14001ee97  mov     [rbp+arg_10], rbx
0x14001ee9b  mov     [rbp+var_10], rcx
0x14001ee9f  test    rcx, rcx
0x14001eea2  jz      short loc_14001EEB1
0x14001eea4  mov     rax, [rcx]
0x14001eea7  mov     rax, [rax+8]
0x14001eeab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001eeb0  nop
0x14001eeb1  mov     edx, 2; dwCoInit
0x14001eeb6  xor     ecx, ecx; pvReserved
0x14001eeb8  call    cs:__imp_CoInitializeEx
0x14001eebe  mov     edi, eax
0x14001eec0  mov     r15d, 1
0x14001eec6  test    eax, eax
0x14001eec8  js      short loc_14001EF1D
0x14001eeca  lea     rax, [rbp+arg_10]
0x14001eece  mov     [rsp+40h+ppv], rax; ppv
0x14001eed3  lea     r9, _GUID_31e99ed0_6ad8_431b_ae3c_652d9e8c7832; riid
0x14001eeda  xor     edx, edx; pUnkOuter
0x14001eedc  lea     r8d, [r15+16h]; dwClsContext
0x14001eee0  lea     rcx, CLSID_SpSapiServer; rclsid
0x14001eee7  call    cs:__imp_CoCreateInstance
0x14001eeed  mov     edi, eax
0x14001eeef  test    eax, eax
0x14001eef1  js      short loc_14001EF1D
0x14001eef3  xor     r9d, r9d; lpName
0x14001eef6  xor     r8d, r8d; bInitialState
0x14001eef9  mov     edx, r15d; bManualReset
0x14001eefc  xor     ecx, ecx; lpEventAttributes
0x14001eefe  call    cs:__imp_CreateEventW
0x14001ef04  mov     rbx, rax
0x14001ef07  mov     [rbp+arg_18], rax
0x14001ef0b  test    rax, rax
0x14001ef0e  jnz     short loc_14001EF1D
0x14001ef10  mov     edi, 8007000Eh
0x14001ef15  mov     [rbp+arg_0], eax
0x14001ef18  jmp     loc_14001EFB6
0x14001ef1d  mov     [rbp+arg_0], 0
0x14001ef24  test    edi, edi
0x14001ef26  js      loc_14001EFB6
0x14001ef2c  mov     rcx, [rbp+arg_10]
0x14001ef30  mov     rax, [rcx]
0x14001ef33  movzx   edx, byte ptr [rsi+1Ch]
0x14001ef37  lea     r9, [rbp+arg_0]
0x14001ef3b  mov     r8, rbx
0x14001ef3e  mov     rax, [rax+18h]
0x14001ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ef47  mov     edi, eax
0x14001ef49  test    eax, eax
0x14001ef4b  js      short loc_14001EFB6
0x14001ef4d  mov     dword ptr [rsi+18h], 0
0x14001ef54  mov     rcx, [rsi+10h]; hEvent
0x14001ef58  call    cs:__imp_SetEvent
0x14001ef5e  cmp     [rbp+arg_0], 0
0x14001ef62  jz      short loc_14001EF93
0x14001ef64  mov     rcx, [rbp+arg_10]
0x14001ef68  mov     rax, [rcx]
0x14001ef6b  mov     rax, [rax+20h]
0x14001ef6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ef74  mov     edi, eax
0x14001ef76  mov     rcx, cs:hEvent; hEvent
0x14001ef7d  call    cs:__imp_SetEvent
0x14001ef83  test    edi, edi
0x14001ef85  js      short loc_14001EF93
0x14001ef87  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001ef8a  mov     rcx, rbx; hHandle
0x14001ef8d  call    cs:__imp_WaitForSingleObject
0x14001ef93  mov     rcx, [rbp+arg_10]
0x14001ef97  mov     rax, [rcx]
0x14001ef9a  mov     rax, [rax+28h]
0x14001ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001efa3  mov     edi, eax
0x14001efa5  mov     rcx, cs:qword_14004DDD0; hEvent
0x14001efac  call    cs:__imp_SetEvent
0x14001efb2  test    edi, edi
0x14001efb4  jns     short loc_14001EFD0
0x14001efb6  xor     eax, eax
0x14001efb8  cmp     edi, 80045051h
0x14001efbe  cmovnz  eax, edi
0x14001efc1  mov     edi, eax
0x14001efc3  mov     [rsi+18h], eax
0x14001efc6  mov     rcx, [rsi+10h]; hEvent
0x14001efca  call    cs:__imp_SetEvent
0x14001efd0  call    cs:__imp_CoUninitialize
0x14001efd6  nop
0x14001efd7  xor     ebx, ebx
0x14001efd9  test    edi, edi
0x14001efdb  cmovs   ebx, edi
0x14001efde  mov     rcx, [rsi]
0x14001efe1  mov     rax, [rcx+10h]
0x14001efe5  mov     rcx, rsi
0x14001efe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001efed  nop
0x14001efee  lea     rcx, [rbp+arg_10]
0x14001eff2  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x14001eff7  nop
0x14001eff8  lea     rcx, [rbp+arg_18]; this
0x14001effc  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x14001f001  mov     eax, ebx
0x14001f003  add     rsp, 40h
0x14001f007  pop     r15
0x14001f009  pop     rdi
0x14001f00a  pop     rsi
0x14001f00b  pop     rbx
0x14001f00c  pop     rbp
0x14001f00d  retn
```
