# Settings::Desktop::EnsureMonitorStarted(void)

- ea: `0x180022d20`
- end: `0x180022f38`
- name: `?EnsureMonitorStarted@Desktop@Settings@@YAXXZ`
- size: `536`
- prototype: `void __fastcall(Settings::Desktop *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800927cc`

## callees

- `0x180006ee0`
- `0x18000ecc0`
- `0x18002252c`
- `0x180022d20`
- `0x180023918`
- `0x180025c10`
- `0x180035e0c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022d66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e2d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022d66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022e2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
void __fastcall Settings::Desktop::EnsureMonitorStarted(Settings::Desktop *this)
{
  HRESULT v1; // eax
  int v2; // ebx
  LPVOID v3; // rcx
  HRESULT v4; // eax
  int v5; // ebx
  LPVOID v6; // rcx
  LPVOID v7; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v8[4]; // [rsp+38h] [rbp-80h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v10[56]; // [rsp+80h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+C0h] [rbp+8h] BYREF
  char v12; // [rsp+C8h] [rbp+10h] BYREF
  char v13; // [rsp+D0h] [rbp+18h] BYREF
  char v14; // [rsp+D8h] [rbp+20h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60845038>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60845038>::GetImpl'::`2'::impl) )
  {
    v14 = 0;
    LOBYTE(ppv) = 0;
    v12 = 0;
    v13 = 0;
    v8[0] = &v14;
    v8[1] = &ppv;
    v8[2] = &v12;
    v8[3] = &v13;
    v7 = 0;
    v4 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v7);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids,
          (unsigned int)v4);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v10, v5);
      throw (ErrorCodeException *)v10;
    }
    LOBYTE(ppv) = 1;
    v12 = 1;
    anonymous_namespace_::StartMonitoringTask(v7);
    v13 = 1;
    lambda_e5c96fcad99a0220c9fdc2dbfd8a2b73_::operator()(v8);
    v6 = v7;
    if ( v7 )
    {
      v7 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  else
  {
    ppv = 0;
    v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
    v2 = v1;
    if ( v1 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids,
          (unsigned int)v1);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v2);
      throw (ErrorCodeException *)pExceptionObject;
    }
    anonymous_namespace_::StartMonitoringTask(ppv);
    v3 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
  }
}

```

## disassembly

```asm
0x180022d20  push    rbx
0x180022d22  sub     rsp, 0B0h
0x180022d29  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60845038@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60845038@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60845038> `wil::Feature<__WilFeatureTraits_Feature_60845038>::GetImpl(void)'::`2'::impl
0x180022d30  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60845038@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60845038>::__private_IsEnabled(void)
0x180022d35  test    al, al
0x180022d37  jnz     short loc_180022DB2
0x180022d39  mov     [rsp+0B8h+arg_0], 0
0x180022d45  lea     rax, [rsp+0B8h+arg_0]
0x180022d4d  mov     [rsp+0B8h+ppv], rax; ppv
0x180022d52  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180022d59  xor     edx, edx; pUnkOuter
0x180022d5b  lea     r8d, [rdx+1]; dwClsContext
0x180022d5f  lea     rcx, CLSID_TaskScheduler; rclsid
0x180022d66  call    cs:__imp_CoCreateInstance
0x180022d6c  mov     ebx, eax
0x180022d6e  test    eax, eax
0x180022d70  js      loc_180022E93
0x180022d76  mov     rcx, [rsp+0B8h+arg_0]
0x180022d7e  call    _anonymous_namespace___StartMonitoringTask
0x180022d83  nop
0x180022d84  mov     rcx, [rsp+0B8h+arg_0]
0x180022d8c  test    rcx, rcx
0x180022d8f  jz      loc_180022E8A
0x180022d95  mov     [rsp+0B8h+arg_0], 0
0x180022da1  mov     rax, [rcx]
0x180022da4  mov     rax, [rax+10h]
0x180022da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dad  jmp     loc_180022E8A
0x180022db2  mov     [rsp+0B8h+arg_18], 0
0x180022dba  mov     byte ptr [rsp+0B8h+arg_0], 0
0x180022dc2  mov     [rsp+0B8h+arg_8], 0
0x180022dca  mov     [rsp+0B8h+arg_10], 0
0x180022dd2  lea     rax, [rsp+0B8h+arg_18]
0x180022dda  mov     [rsp+0B8h+var_80], rax
0x180022ddf  lea     rax, [rsp+0B8h+arg_0]
0x180022de7  mov     [rsp+0B8h+var_78], rax
0x180022dec  lea     rax, [rsp+0B8h+arg_8]
0x180022df4  mov     [rsp+0B8h+var_70], rax
0x180022df9  lea     rax, [rsp+0B8h+arg_10]
0x180022e01  mov     [rsp+0B8h+var_68], rax
0x180022e06  mov     [rsp+0B8h+var_88], 0
0x180022e0f  lea     rax, [rsp+0B8h+var_88]
0x180022e14  mov     [rsp+0B8h+ppv], rax; ppv
0x180022e19  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180022e20  xor     edx, edx; pUnkOuter
0x180022e22  lea     r8d, [rdx+1]; dwClsContext
0x180022e26  lea     rcx, CLSID_TaskScheduler; rclsid
0x180022e2d  call    cs:__imp_CoCreateInstance
0x180022e33  mov     ebx, eax
0x180022e35  test    eax, eax
0x180022e37  js      loc_180022EE2
0x180022e3d  mov     byte ptr [rsp+0B8h+arg_0], 1
0x180022e45  mov     [rsp+0B8h+arg_8], 1
0x180022e4d  mov     rcx, [rsp+0B8h+var_88]
0x180022e52  call    _anonymous_namespace___StartMonitoringTask
0x180022e57  mov     [rsp+0B8h+arg_10], 1
0x180022e5f  lea     rcx, [rsp+0B8h+var_80]
0x180022e64  call    _lambda_e5c96fcad99a0220c9fdc2dbfd8a2b73___operator__
0x180022e69  nop
0x180022e6a  mov     rcx, [rsp+0B8h+var_88]
0x180022e6f  test    rcx, rcx
0x180022e72  jz      short loc_180022E8A
0x180022e74  mov     [rsp+0B8h+var_88], 0
0x180022e7d  mov     rax, [rcx]
0x180022e80  mov     rax, [rax+10h]
0x180022e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e89  nop
0x180022e8a  add     rsp, 0B0h
0x180022e91  pop     rbx
0x180022e92  retn
0x180022e93  lea     rdx, WPP_GLOBAL_Control
0x180022e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ea1  cmp     rcx, rdx
0x180022ea4  jz      short loc_180022EC4
0x180022ea6  test    byte ptr [rcx+1Ch], 1
0x180022eaa  jz      short loc_180022EC4
0x180022eac  mov     edx, 32h ; '2'
0x180022eb1  mov     r9d, eax
0x180022eb4  lea     r8, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids
0x180022ebb  mov     rcx, [rcx+10h]
0x180022ebf  call    WPP_SF_d
0x180022ec4  mov     edx, ebx; int
0x180022ec6  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x180022ecb  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180022ed0  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180022ed7  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180022edc  call    _CxxThrowException_0
0x180022ee2  lea     rdx, WPP_GLOBAL_Control
0x180022ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ef0  cmp     rcx, rdx
0x180022ef3  jz      short loc_180022F13
0x180022ef5  test    byte ptr [rcx+1Ch], 1
0x180022ef9  jz      short loc_180022F13
0x180022efb  mov     edx, 30h ; '0'
0x180022f00  mov     r9d, eax
0x180022f03  lea     r8, WPP_63b6f7e99d2a3b3cdf4ede57ea2e6971_Traceguids
0x180022f0a  mov     rcx, [rcx+10h]
0x180022f0e  call    WPP_SF_d
0x180022f13  mov     edx, ebx; int
0x180022f15  lea     rcx, [rsp+0B8h+var_38]; this
0x180022f1d  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180022f22  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180022f29  lea     rcx, [rsp+0B8h+var_38]; pExceptionObject
0x180022f31  call    _CxxThrowException_0
```
