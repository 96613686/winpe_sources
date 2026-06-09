# NTService::ServiceMain(ulong,ushort * * const)

- ea: `0x18003a750`
- end: `0x18003a8f3`
- name: `?ServiceMain@NTService@@QEAAXKQEAPEAG@Z`
- size: `419`
- prototype: `void __fastcall(NTService *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041920`

## callees

- `0x18001a6b4`
- `0x1800225d0`
- `0x1800355b4`
- `0x18003a640`
- `0x18003a750`
- `0x18003a8fc`
- `0x18003a9b0`
- `0x18003aa30`
- `0x18003aa84`
- `0x18003aacc`
- `0x18006a010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a8d0`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a8d0`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003a882`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003a882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a782`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a782`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003a773`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003a773`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NTService::ServiceMain(NTService *this, __int64 a2, LPCWSTR *a3)
{
  SERVICE_STATUS_HANDLE v5; // rax
  signed int LastError; // eax
  unsigned __int8 v7; // dl
  bool v8; // sf
  __int64 v9; // r14
  __int64 (__fastcall *v10)(char *, LPCWSTR, __int64, __int64, NTService *, int); // r14
  __int64 v11; // rbx
  __int64 v12; // rdi
  LPCWSTR v13; // rsi
  int v14; // eax
  bool v15; // sf
  _QWORD *v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v19[12]; // [rsp+48h] [rbp-30h] BYREF
  _QWORD *v20; // [rsp+80h] [rbp+8h] BYREF
  char v21; // [rsp+90h] [rbp+18h] BYREF

  v5 = RegisterServiceCtrlHandlerExW(*a3, NTService::ServiceHandlerThunk, this);
  *((_QWORD *)this + 3) = v5;
  if ( v5 )
    goto LABEL_12;
  LastError = GetLastError();
  v8 = LastError < 0;
  if ( LastError > 0 )
    v8 = 1;
  if ( !v8 )
  {
LABEL_12:
    if ( (int)NTService::UpdateServiceStatus(this, 2u, 0, 0x2710u) >= 0
      && (int)_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 16) >= 0 )
    {
      v9 = *((_QWORD *)this + 6);
      if ( v9 )
      {
        if ( *((_QWORD *)this + 7) )
        {
          v10 = *(__int64 (__fastcall **)(char *, LPCWSTR, __int64, __int64, NTService *, int))(v9 + 192);
          v11 = *((_QWORD *)this + 7);
          v12 = *((_QWORD *)this + 2);
          v13 = *a3;
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int UnregisterWait(void *)>>::reset(
            (char *)this + 40,
            0);
          v14 = v10((char *)this + 40, v13, v12, v11, this, 24);
          v15 = v14 < 0;
          if ( !v14 )
            goto LABEL_13;
          if ( v14 > 0 )
            v15 = 1;
          if ( !v15 )
          {
LABEL_13:
            v16 = (_QWORD *)lambda_59c15db226e0ffe3b6509460b80fa2bf_::_lambda_59c15db226e0ffe3b6509460b80fa2bf_(
                              &v21,
                              this);
            v17 = operator new(8u);
            *v17 = *v16;
            v20 = v17;
            v18 = _o__beginthreadex(
                    0,
                    0,
                    std::thread::_Invoke_std::tuple__lambda_585d258a58e0e898488c9612cf08a09d____0_,
                    v17,
                    0,
                    v19);
            if ( v18 )
            {
              v20 = 0;
              std::unique_ptr_std::tuple__lambda_585d258a58e0e898488c9612cf08a09d____std::default_delete_std::tuple__lambda_585d258a58e0e898488c9612cf08a09d_______::_unique_ptr_std::tuple__lambda_585d258a58e0e898488c9612cf08a09d____std::default_delete_std::tuple__lambda_585d258a58e0e898488c9612cf08a09d_______(&v20);
              std::thread::detach((std::thread *)&v18);
              std::thread::~thread((std::thread *)&v18);
              return;
            }
            v19[0] = 0;
            std::_Throw_Cpp_error(6);
          }
        }
      }
    }
  }
  NTService::ServiceStopCallback(this, v7);
}

```

## disassembly

```asm
0x18003a750  mov     [rsp+arg_18], rbx
0x18003a755  push    rbp
0x18003a756  push    rsi
0x18003a757  push    rdi
0x18003a758  push    r14
0x18003a75a  push    r15
0x18003a75c  sub     rsp, 50h
0x18003a760  mov     rsi, r8
0x18003a763  mov     r15, rcx
0x18003a766  mov     r8, rcx; lpContext
0x18003a769  lea     rdx, ?ServiceHandlerThunk@NTService@@CAKKKPEAX0@Z; lpHandlerProc
0x18003a770  mov     rcx, [rsi]; lpServiceName
0x18003a773  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003a779  mov     [r15+18h], rax
0x18003a77d  test    rax, rax
0x18003a780  jnz     short loc_18003A79C
0x18003a782  call    cs:__imp_GetLastError
0x18003a788  test    eax, eax
0x18003a78a  jle     short loc_18003A796
0x18003a78c  movzx   eax, ax
0x18003a78f  or      eax, 80070000h
0x18003a794  test    eax, eax
0x18003a796  js      loc_18003A8D7
0x18003a79c  mov     r9d, 2710h; unsigned int
0x18003a7a2  xor     r8d, r8d; unsigned int
0x18003a7a5  lea     edx, [r8+2]; unsigned int
0x18003a7a9  mov     rcx, r15; this
0x18003a7ac  call    ?UpdateServiceStatus@NTService@@IEAAJKKK@Z; NTService::UpdateServiceStatus(ulong,ulong,ulong)
0x18003a7b1  test    eax, eax
0x18003a7b3  js      loc_18003A8D7
0x18003a7b9  lea     rcx, [r15+10h]
0x18003a7bd  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003a7c2  test    eax, eax
0x18003a7c4  js      loc_18003A8D7
0x18003a7ca  mov     r14, [r15+30h]
0x18003a7ce  test    r14, r14
0x18003a7d1  jz      loc_18003A8D7
0x18003a7d7  cmp     qword ptr [r15+38h], 0
0x18003a7dc  jz      loc_18003A8D7
0x18003a7e2  mov     r14, [r14+0C0h]
0x18003a7e9  mov     rbx, [r15+38h]
0x18003a7ed  mov     rdi, [r15+10h]
0x18003a7f1  mov     rsi, [rsi]
0x18003a7f4  xor     edx, edx
0x18003a7f6  lea     rcx, [r15+28h]
0x18003a7fa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>::reset(void *)
0x18003a7ff  mov     dword ptr [rsp+78h+var_50], 18h
0x18003a807  mov     [rsp+78h+var_58], r15
0x18003a80c  mov     r9, rbx
0x18003a80f  mov     r8, rdi
0x18003a812  mov     rdx, rsi
0x18003a815  lea     rcx, [r15+28h]
0x18003a819  mov     rax, r14
0x18003a81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a821  test    eax, eax
0x18003a823  jz      short loc_18003A837
0x18003a825  jle     short loc_18003A831
0x18003a827  movzx   eax, ax
0x18003a82a  or      eax, 80070000h
0x18003a82f  test    eax, eax
0x18003a831  js      loc_18003A8D7
0x18003a837  mov     rdx, r15
0x18003a83a  lea     rcx, [rsp+78h+arg_10]
0x18003a842  call    _lambda_59c15db226e0ffe3b6509460b80fa2bf____lambda_59c15db226e0ffe3b6509460b80fa2bf_
0x18003a847  mov     rbx, rax
0x18003a84a  mov     ecx, 8; Size
0x18003a84f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a854  mov     rcx, [rbx]
0x18003a857  mov     [rax], rcx
0x18003a85a  mov     [rsp+78h+arg_0], rax
0x18003a862  lea     rcx, [rsp+78h+var_30]
0x18003a867  mov     [rsp+78h+var_50], rcx
0x18003a86c  mov     dword ptr [rsp+78h+var_58], 0
0x18003a874  mov     r9, rax
0x18003a877  lea     r8, std__thread___Invoke_std__tuple__lambda_585d258a58e0e898488c9612cf08a09d____0_
0x18003a87e  xor     edx, edx
0x18003a880  xor     ecx, ecx
0x18003a882  call    cs:__imp__o__beginthreadex
0x18003a888  mov     [rsp+78h+var_38], rax
0x18003a88d  test    rax, rax
0x18003a890  jz      short loc_18003A8C3
0x18003a892  mov     [rsp+78h+arg_0], 0
0x18003a89e  lea     rcx, [rsp+78h+arg_0]
0x18003a8a6  call    std__unique_ptr_std__tuple__lambda_585d258a58e0e898488c9612cf08a09d____std__default_delete_std__tuple__lambda_585d258a58e0e898488c9612cf08a09d__________unique_ptr_std__tuple__lambda_585d258a58e0e898488c9612cf08a09d____std__default_delete_std__tuple__lambda_585d258a58e0e898488c9612cf08a09d_______
0x18003a8ab  nop
0x18003a8ac  lea     rcx, [rsp+78h+var_38]; this
0x18003a8b1  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x18003a8b6  nop
0x18003a8b7  lea     rcx, [rsp+78h+var_38]; this
0x18003a8bc  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18003a8c1  jmp     short loc_18003A8DF
0x18003a8c3  mov     [rsp+78h+var_30], 0
0x18003a8cb  mov     ecx, 6
0x18003a8d0  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a8d6  nop
0x18003a8d7  mov     rcx, r15; this
0x18003a8da  call    ?ServiceStopCallback@NTService@@QEAAXE@Z; NTService::ServiceStopCallback(uchar)
0x18003a8df  mov     rbx, [rsp+78h+arg_18]
0x18003a8e7  add     rsp, 50h
0x18003a8eb  pop     r15
0x18003a8ed  pop     r14
0x18003a8ef  pop     rdi
0x18003a8f0  pop     rsi
0x18003a8f1  pop     rbp
0x18003a8f2  retn
```
