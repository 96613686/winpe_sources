# _lambda_dab92f77245a1eb8f79040f0ff5af966_::operator()

- ea: `0x18006c1e0`
- end: `0x18006c353`
- name: `_lambda_dab92f77245a1eb8f79040f0ff5af966_::operator()`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18006c3b0`

## callees

- `0x180027a4c`
- `0x18003ecb4`
- `0x18006c1e0`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006c215`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006c215`

## string_xrefs

- `0x18006c233`: `AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()`
- `0x18006c285`: `AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()`
- `0x18006c2f2`: `AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()`
- `0x18006c23a`: `CoCreateInstance(__uuidof(PackageInstallStateStoreEnum), nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(stateStoreEnum.GetAddressOf()))`
- `0x18006c227`: `onecoreuap\shell\appreadiness\src\tasks\removepreviews.cpp`
- `0x18006c279`: `onecoreuap\shell\appreadiness\src\tasks\removepreviews.cpp`
- `0x18006c2e6`: `onecoreuap\shell\appreadiness\src\tasks\removepreviews.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_dab92f77245a1eb8f79040f0ff5af966_::operator()(__int64 *a1)
{
  HRESULT v2; // eax
  int v3; // eax
  _QWORD *v4; // rdx
  __int64 result; // rax
  LPVOID v6; // rcx
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+18h] BYREF

  ppv = 0;
  v2 = CoCreateInstance(
         &GUID_2025bcb1_370e_4103_9c34_883770f7f2a0,
         0,
         1u,
         &GUID_30a4846e_08ce_4ab9_8176_ee01f411936c,
         &ppv);
  if ( v2 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v2,
      "CoCreateInstance(__uuidof(PackageInstallStateStoreEnum), nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(stateStoreEnu"
      "m.GetAddressOf()))",
      "AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\removepreviews.cpp",
      30);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v3,
      "stateStoreEnum->Load()",
      "AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\removepreviews.cpp",
      31);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v4 = (_QWORD *)(a1[1] + 240);
  if ( *(_QWORD *)(a1[1] + 264) > 7u )
    v4 = (_QWORD *)*v4;
  result = (*(__int64 (__fastcall **)(LPVOID, _QWORD *, __int64))(*(_QWORD *)ppv + 32LL))(ppv, v4, *a1);
  if ( (int)result < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      result,
      "hrPackageState",
      "AppReadiness::Tasks::RemovePreviews::GetInstallState::<lambda_dab92f77245a1eb8f79040f0ff5af966>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\tasks\\removepreviews.cpp",
      33);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( (_DWORD)result == 1 )
  {
    result = *a1;
    *(_DWORD *)*a1 = -1;
  }
  v6 = ppv;
  if ( ppv )
  {
    ppv = 0;
    return (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return result;
}

```

## disassembly

```asm
0x18006c1e0  mov     [rsp-8+arg_0], rbx
0x18006c1e5  push    rbp
0x18006c1e6  mov     rbp, rsp
0x18006c1e9  sub     rsp, 60h
0x18006c1ed  mov     rbx, rcx
0x18006c1f0  mov     [rbp+arg_8], 0
0x18006c1f8  lea     rax, [rbp+arg_8]
0x18006c1fc  mov     [rsp+60h+ppv], rax; ppv
0x18006c201  lea     r9, _GUID_30a4846e_08ce_4ab9_8176_ee01f411936c; riid
0x18006c208  xor     edx, edx; pUnkOuter
0x18006c20a  lea     r8d, [rdx+1]; dwClsContext
0x18006c20e  lea     rcx, _GUID_2025bcb1_370e_4103_9c34_883770f7f2a0; rclsid
0x18006c215  call    cs:__imp_CoCreateInstance
0x18006c21b  test    eax, eax
0x18006c21d  jns     short loc_18006C25D
0x18006c21f  mov     [rsp+60h+var_38], 1Eh; int
0x18006c227  lea     rcx, aOnecoreuapShel_0; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006c22e  mov     [rsp+60h+ppv], rcx; char *
0x18006c233  lea     r9, aAppreadinessTa_24; "AppReadiness::Tasks::RemovePreviews::Ge"...
0x18006c23a  lea     r8, aCocreateinstan_1; "CoCreateInstance(__uuidof(PackageInstal"...
0x18006c241  mov     edx, eax; int
0x18006c243  lea     rcx, [rbp+pExceptionObject]; this
0x18006c247  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006c24c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006c253  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006c257  call    _CxxThrowException_0
0x18006c25d  mov     rcx, [rbp+arg_8]
0x18006c261  mov     rax, [rcx]
0x18006c264  mov     rax, [rax+18h]
0x18006c268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c26d  test    eax, eax
0x18006c26f  jns     short loc_18006C2AF
0x18006c271  mov     [rsp+60h+var_38], 1Fh; int
0x18006c279  lea     rcx, aOnecoreuapShel_0; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006c280  mov     [rsp+60h+ppv], rcx; char *
0x18006c285  lea     r9, aAppreadinessTa_24; "AppReadiness::Tasks::RemovePreviews::Ge"...
0x18006c28c  lea     r8, aStatestoreenum; "stateStoreEnum->Load()"
0x18006c293  mov     edx, eax; int
0x18006c295  lea     rcx, [rbp+pExceptionObject]; this
0x18006c299  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006c29e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006c2a5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006c2a9  call    _CxxThrowException_0
0x18006c2af  mov     rcx, [rbp+arg_8]
0x18006c2b3  mov     rax, [rcx]
0x18006c2b6  mov     r9, [rax+20h]
0x18006c2ba  mov     rdx, [rbx+8]
0x18006c2be  add     rdx, 0F0h
0x18006c2c5  cmp     qword ptr [rdx+18h], 7
0x18006c2ca  jbe     short loc_18006C2CF
0x18006c2cc  mov     rdx, [rdx]
0x18006c2cf  mov     r8, [rbx]
0x18006c2d2  mov     rax, r9
0x18006c2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c2da  test    eax, eax
0x18006c2dc  jns     short loc_18006C31C
0x18006c2de  mov     [rsp+60h+var_38], 21h ; '!'; int
0x18006c2e6  lea     rcx, aOnecoreuapShel_0; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18006c2ed  mov     [rsp+60h+ppv], rcx; char *
0x18006c2f2  lea     r9, aAppreadinessTa_24; "AppReadiness::Tasks::RemovePreviews::Ge"...
0x18006c2f9  lea     r8, aHrpackagestate; "hrPackageState"
0x18006c300  mov     edx, eax; int
0x18006c302  lea     rcx, [rbp+pExceptionObject]; this
0x18006c306  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18006c30b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18006c312  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18006c316  call    _CxxThrowException_0
0x18006c31c  cmp     eax, 1
0x18006c31f  jnz     short loc_18006C32A
0x18006c321  mov     rax, [rbx]
0x18006c324  mov     dword ptr [rax], 0FFFFFFFFh
0x18006c32a  mov     rcx, [rbp+arg_8]
0x18006c32e  test    rcx, rcx
0x18006c331  jz      short loc_18006C348
0x18006c333  mov     [rbp+arg_8], 0
0x18006c33b  mov     rax, [rcx]
0x18006c33e  mov     rax, [rax+10h]
0x18006c342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c347  nop
0x18006c348  mov     rbx, [rsp+60h+arg_0]
0x18006c34d  add     rsp, 60h
0x18006c351  pop     rbp
0x18006c352  retn
```
