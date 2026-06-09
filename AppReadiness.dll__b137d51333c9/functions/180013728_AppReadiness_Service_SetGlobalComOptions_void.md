# AppReadiness::Service::SetGlobalComOptions(void)

- ea: `0x180013728`
- end: `0x1800138d7`
- name: `?SetGlobalComOptions@Service@AppReadiness@@IEAAXXZ`
- size: `431`
- prototype: `void __fastcall(AppReadiness::Service *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001338c`

## callees

- `0x180013728`
- `0x180027a4c`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001375a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001375a`

## string_xrefs

- `0x18001376c`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800137c7`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180013822`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x18001387d`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180013778`: `AppReadiness::Service::SetGlobalComOptions`
- `0x1800137d3`: `AppReadiness::Service::SetGlobalComOptions`
- `0x18001382e`: `AppReadiness::Service::SetGlobalComOptions`
- `0x180013889`: `AppReadiness::Service::SetGlobalComOptions`
- `0x18001377f`: `CoCreateInstance(CLSID_GlobalOptions, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(globalOptions.GetAddressOf()))`
- `0x1800137da`: `globalOptions->Set(COMGLB_RO_SETTINGS, COMGLB_ENABLE_AGILE_OOP_PROXIES)`
- `0x180013835`: `globalOptions->Set(COMGLB_UNMARSHALING_POLICY, COMGLB_UNMARSHALING_POLICY_STRONG)`
- `0x180013890`: `globalOptions->Set(COMGLB_EXCEPTION_HANDLING, COMGLB_EXCEPTION_DONOT_HANDLE_ANY)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Service::SetGlobalComOptions(AppReadiness::Service *this)
{
  HRESULT v1; // eax
  int v2; // eax
  int v3; // eax
  int v4; // eax
  LPVOID v5; // rcx
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+10h] BYREF

  ppv = 0;
  v1 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v1 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v1,
      "CoCreateInstance(CLSID_GlobalOptions, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(globalOptions.GetAddressOf()))",
      "AppReadiness::Service::SetGlobalComOptions",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      78);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, 16);
  if ( v2 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v2,
      "globalOptions->Set(COMGLB_RO_SETTINGS, COMGLB_ENABLE_AGILE_OOP_PROXIES)",
      "AppReadiness::Service::SetGlobalComOptions",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      79);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "globalOptions->Set(COMGLB_UNMARSHALING_POLICY, COMGLB_UNMARSHALING_POLICY_STRONG)",
      "AppReadiness::Service::SetGlobalComOptions",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      80);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
  if ( v4 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v4,
      "globalOptions->Set(COMGLB_EXCEPTION_HANDLING, COMGLB_EXCEPTION_DONOT_HANDLE_ANY)",
      "AppReadiness::Service::SetGlobalComOptions",
      "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
      81);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v5 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
}

```

## disassembly

```asm
0x180013728  mov     [rsp-8+arg_0], rcx
0x18001372d  push    rbp
0x18001372e  mov     rbp, rsp
0x180013731  sub     rsp, 60h
0x180013735  mov     [rbp+arg_0], 0
0x18001373d  lea     rax, [rbp+arg_0]
0x180013741  mov     [rsp+60h+ppv], rax; ppv
0x180013746  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18001374d  xor     edx, edx; pUnkOuter
0x18001374f  lea     r8d, [rdx+1]; dwClsContext
0x180013753  lea     rcx, CLSID_GlobalOptions; rclsid
0x18001375a  call    cs:__imp_CoCreateInstance
0x180013760  test    eax, eax
0x180013762  jns     short loc_1800137A2
0x180013764  mov     [rsp+60h+var_38], 4Eh ; 'N'; int
0x18001376c  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013773  mov     [rsp+60h+ppv], rcx; char *
0x180013778  lea     r9, aAppreadinessSe_6; "AppReadiness::Service::SetGlobalComOpti"...
0x18001377f  lea     r8, aCocreateinstan_2; "CoCreateInstance(CLSID_GlobalOptions, n"...
0x180013786  mov     edx, eax; int
0x180013788  lea     rcx, [rbp+pExceptionObject]; this
0x18001378c  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013791  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180013798  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001379c  call    _CxxThrowException_0
0x1800137a2  mov     rcx, [rbp+arg_0]
0x1800137a6  mov     rax, [rcx]
0x1800137a9  mov     edx, 4
0x1800137ae  lea     r8d, [rdx+0Ch]
0x1800137b2  mov     rax, [rax+18h]
0x1800137b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137bb  test    eax, eax
0x1800137bd  jns     short loc_1800137FD
0x1800137bf  mov     [rsp+60h+var_38], 4Fh ; 'O'; int
0x1800137c7  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800137ce  mov     [rsp+60h+ppv], rcx; char *
0x1800137d3  lea     r9, aAppreadinessSe_6; "AppReadiness::Service::SetGlobalComOpti"...
0x1800137da  lea     r8, aGlobaloptionsS_0; "globalOptions->Set(COMGLB_RO_SETTINGS, "...
0x1800137e1  mov     edx, eax; int
0x1800137e3  lea     rcx, [rbp+pExceptionObject]; this
0x1800137e7  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800137ec  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800137f3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800137f7  call    _CxxThrowException_0
0x1800137fd  mov     rcx, [rbp+arg_0]
0x180013801  mov     rax, [rcx]
0x180013804  mov     edx, 5
0x180013809  lea     r8d, [rdx-4]
0x18001380d  mov     rax, [rax+18h]
0x180013811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013816  test    eax, eax
0x180013818  jns     short loc_180013858
0x18001381a  mov     [rsp+60h+var_38], 50h ; 'P'; int
0x180013822  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013829  mov     [rsp+60h+ppv], rcx; char *
0x18001382e  lea     r9, aAppreadinessSe_6; "AppReadiness::Service::SetGlobalComOpti"...
0x180013835  lea     r8, aGlobaloptionsS; "globalOptions->Set(COMGLB_UNMARSHALING_"...
0x18001383c  mov     edx, eax; int
0x18001383e  lea     rcx, [rbp+pExceptionObject]; this
0x180013842  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180013847  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001384e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013852  call    _CxxThrowException_0
0x180013858  mov     rcx, [rbp+arg_0]
0x18001385c  mov     rax, [rcx]
0x18001385f  mov     edx, 1
0x180013864  lea     r8d, [rdx+1]
0x180013868  mov     rax, [rax+18h]
0x18001386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013871  test    eax, eax
0x180013873  jns     short loc_1800138B3
0x180013875  mov     [rsp+60h+var_38], 51h ; 'Q'; int
0x18001387d  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180013884  mov     [rsp+60h+ppv], rcx; char *
0x180013889  lea     r9, aAppreadinessSe_6; "AppReadiness::Service::SetGlobalComOpti"...
0x180013890  lea     r8, aGlobaloptionsS_1; "globalOptions->Set(COMGLB_EXCEPTION_HAN"...
0x180013897  mov     edx, eax; int
0x180013899  lea     rcx, [rbp+pExceptionObject]; this
0x18001389d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800138a2  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800138a9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800138ad  call    _CxxThrowException_0
0x1800138b3  mov     rcx, [rbp+arg_0]
0x1800138b7  test    rcx, rcx
0x1800138ba  jz      short loc_1800138D1
0x1800138bc  mov     [rbp+arg_0], 0
0x1800138c4  mov     rax, [rcx]
0x1800138c7  mov     rax, [rax+10h]
0x1800138cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d0  nop
0x1800138d1  add     rsp, 60h
0x1800138d5  pop     rbp
0x1800138d6  retn
```
