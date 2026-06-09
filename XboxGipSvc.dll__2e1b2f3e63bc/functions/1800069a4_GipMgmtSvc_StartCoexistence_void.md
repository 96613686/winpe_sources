# GipMgmtSvc::_StartCoexistence(void)

- ea: `0x1800069a4`
- end: `0x180006b69`
- name: `?_StartCoexistence@GipMgmtSvc@@QEAAKXZ`
- size: `453`
- prototype: `__int64 __fastcall(SERVICE_STATUS_HANDLE *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004610`
- `0x180005670`

## callees

- `0x180002b48`
- `0x180002b70`
- `0x1800069a4`
- `0x18000a264`
- `0x180012010`

## import_xrefs

- `ntdll!RtlQueryWnfStateData` at `0x1800069dc`
- `ntdll!RtlQueryWnfStateData` at `0x1800069dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800069e4`
- `ntdll!RtlNtStatusToDosError` at `0x1800069fe`
- `ntdll!RtlNtStatusToDosError` at `0x1800069e4`
- `ntdll!RtlNtStatusToDosError` at `0x1800069fe`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006a1a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006a1a`
- `api-ms-win-service-core-l1-1-1!QueryServiceDynamicInformation` at `0x180006ab9`
- `api-ms-win-service-core-l1-1-1!QueryServiceDynamicInformation` at `0x180006ab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b00`

## pseudocode

```c
__int64 __fastcall GipMgmtSvc::_StartCoexistence(SERVICE_STATUS_HANDLE *this)
{
  NTSTATUS v2; // eax
  ULONG v3; // ebx
  unsigned int started; // eax
  SERVICE_STATUS_HANDLE v5; // rcx
  PVOID v6; // rcx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  PVOID ppDynamicInfo; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  v2 = RtlQueryWnfStateData(&v8, WNF_GIP_ADAPTER_CHANGE, GipMgmtSvc::AdapterChangeCallback, this, 0);
  v3 = RtlNtStatusToDosError(v2);
  if ( !v3 && ((_BYTE)this[28] & 1) == 0 )
    v3 = RtlNtStatusToDosError(-1073741823);
  InitOnceExecuteOnce(
    &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
    _lambda_253709c146e3c4eefdc38a0c994771db_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18001A570 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids);
  }
  if ( !v3 )
  {
    started = CxsStartClient((struct _GIP_WLAN_CLIENT *)(this + 7));
    v3 = started;
    if ( !started )
    {
      (*(void (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                        + 16))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      *((_BYTE *)this + 232) = 1;
      return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids, started);
    }
  }
  v5 = this[1];
  ppDynamicInfo = 0;
  if ( QueryServiceDynamicInformation(v5, 1u, &ppDynamicInfo) )
  {
    v6 = ppDynamicInfo;
    if ( (*(_BYTE *)ppDynamicInfo & 4) != 0 )
    {
      (*(void (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                        + 16))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      (*(void (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                        + 24))(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
      v6 = ppDynamicInfo;
    }
    LocalFree(v6);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800069a4  mov     rax, rsp
0x1800069a7  mov     [rax+18h], rbx
0x1800069ab  mov     [rax+20h], rdi
0x1800069af  push    r14
0x1800069b1  sub     rsp, 30h
0x1800069b5  mov     rdx, cs:WNF_GIP_ADAPTER_CHANGE
0x1800069bc  lea     r8, ?AdapterChangeCallback@GipMgmtSvc@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; GipMgmtSvc::AdapterChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800069c3  mov     rdi, rcx
0x1800069c6  mov     dword ptr [rax+8], 0
0x1800069cd  mov     r9, rcx
0x1800069d0  mov     qword ptr [rax-18h], 0
0x1800069d8  lea     rcx, [rax+8]
0x1800069dc  call    cs:__imp_RtlQueryWnfStateData
0x1800069e2  mov     ecx, eax; Status
0x1800069e4  call    cs:__imp_RtlNtStatusToDosError
0x1800069ea  mov     ebx, eax
0x1800069ec  test    eax, eax
0x1800069ee  jnz     short loc_180006A06
0x1800069f0  test    byte ptr [rdi+0E0h], 1
0x1800069f7  jnz     short loc_180006A06
0x1800069f9  mov     ecx, 0C0000001h; Status
0x1800069fe  call    cs:__imp_RtlNtStatusToDosError
0x180006a04  mov     ebx, eax
0x180006a06  xor     r9d, r9d; Context
0x180006a09  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_253709c146e3c4eefdc38a0c994771db_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006a10  xor     r8d, r8d; Parameter
0x180006a13  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006a1a  call    cs:__imp_InitOnceExecuteOnce
0x180006a20  mov     cs:byte_18001A570, 1
0x180006a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a2e  lea     r14, WPP_GLOBAL_Control
0x180006a35  cmp     rcx, r14
0x180006a38  jz      short loc_180006A5B
0x180006a3a  test    byte ptr [rcx+1Ch], 1
0x180006a3e  jz      short loc_180006A5B
0x180006a40  cmp     byte ptr [rcx+19h], 5
0x180006a44  jb      short loc_180006A5B
0x180006a46  mov     rcx, [rcx+10h]
0x180006a4a  lea     r8, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids
0x180006a51  mov     edx, 0Ah
0x180006a56  call    WPP_SF_
0x180006a5b  test    ebx, ebx
0x180006a5d  jnz     short loc_180006AA2
0x180006a5f  lea     rcx, [rdi+38h]; struct _GIP_WLAN_CLIENT *
0x180006a63  call    ?CxsStartClient@@YAKPEAU_GIP_WLAN_CLIENT@@@Z; CxsStartClient(_GIP_WLAN_CLIENT *)
0x180006a68  mov     ebx, eax
0x180006a6a  test    eax, eax
0x180006a6c  jz      loc_180006B49
0x180006a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a79  cmp     rcx, r14
0x180006a7c  jz      short loc_180006AA2
0x180006a7e  test    byte ptr [rcx+1Ch], 1
0x180006a82  jz      short loc_180006AA2
0x180006a84  cmp     byte ptr [rcx+19h], 2
0x180006a88  jb      short loc_180006AA2
0x180006a8a  mov     rcx, [rcx+10h]
0x180006a8e  lea     r8, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids
0x180006a95  mov     edx, 0Bh
0x180006a9a  mov     r9d, eax
0x180006a9d  call    WPP_SF_D
0x180006aa2  mov     rcx, [rdi+8]; hServiceStatus
0x180006aa6  lea     r8, [rsp+38h+ppDynamicInfo]; ppDynamicInfo
0x180006aab  mov     edx, 1; dwInfoLevel
0x180006ab0  mov     [rsp+38h+ppDynamicInfo], 0
0x180006ab9  call    cs:__imp_QueryServiceDynamicInformation
0x180006abf  test    eax, eax
0x180006ac1  jz      short loc_180006B06
0x180006ac3  mov     rcx, [rsp+38h+ppDynamicInfo]
0x180006ac8  test    byte ptr [rcx], 4
0x180006acb  jz      short loc_180006B00
0x180006acd  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006ad4  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006adb  mov     rax, [rax+10h]
0x180006adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae4  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006aeb  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006af2  mov     rax, [rax+18h]
0x180006af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006afb  mov     rcx, [rsp+38h+ppDynamicInfo]; hMem
0x180006b00  call    cs:__imp_LocalFree
0x180006b06  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b0d  cmp     rcx, r14
0x180006b10  jz      short loc_180006B36
0x180006b12  test    byte ptr [rcx+1Ch], 1
0x180006b16  jz      short loc_180006B36
0x180006b18  cmp     byte ptr [rcx+19h], 4
0x180006b1c  jb      short loc_180006B36
0x180006b1e  mov     rcx, [rcx+10h]
0x180006b22  lea     r8, WPP_cf6f3939734d39595c4233fe69655e31_Traceguids
0x180006b29  mov     edx, 0Ch
0x180006b2e  mov     r9d, ebx
0x180006b31  call    WPP_SF_D
0x180006b36  mov     rbx, [rsp+38h+arg_10]
0x180006b3b  xor     eax, eax
0x180006b3d  mov     rdi, [rsp+38h+arg_18]
0x180006b42  add     rsp, 30h
0x180006b46  pop     r14
0x180006b48  retn
0x180006b49  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006b50  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x180006b57  mov     rax, [rax+10h]
0x180006b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b60  mov     byte ptr [rdi+0E8h], 1
0x180006b67  jmp     short loc_180006B36
```
