# AppReadiness::ImmersivePolicy::GetAllDefaultApps(void)

- ea: `0x1800078b4`
- end: `0x1800079ef`
- name: `?GetAllDefaultApps@ImmersivePolicy@AppReadiness@@QEAA?AV?$ComPtr@UIObjectCollection@@@WRL@Microsoft@@XZ`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006f40`
- `0x180007b70`

## callees

- `0x180002958`
- `0x1800078b4`
- `0x1800079f8`
- `0x180027a4c`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007915`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007915`

## string_xrefs

- `0x180007934`: `onecoreuap\shell\appreadiness\src\core\ImmersivePolicy.h`
- `0x180007974`: `onecoreuap\shell\appreadiness\src\core\ImmersivePolicy.h`
- `0x1800079b7`: `onecoreuap\shell\appreadiness\src\core\ImmersivePolicy.h`
- `0x180007940`: `AppReadiness::ImmersivePolicy::GetAllDefaultApps`
- `0x180007980`: `AppReadiness::ImmersivePolicy::GetAllDefaultApps`
- `0x1800079c3`: `AppReadiness::ImmersivePolicy::GetAllDefaultApps`
- `0x1800079ca`: `CEnumerableObjectCollection::CreateInstance(IID_PPV_ARGS(&apps))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void **__fastcall AppReadiness::ImmersivePolicy::GetAllDefaultApps(__int64 a1, void **a2)
{
  const struct _GUID *v4; // rdx
  int v5; // ecx
  int Instance; // eax
  HMODULE v7; // rcx
  FARPROC ProcAddress; // rax
  int v10; // eax
  _BYTE pExceptionObject[48]; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  Instance = CEnumerableObjectCollection::CreateInstance(v5, v4, a2);
  if ( Instance < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      Instance,
      "CEnumerableObjectCollection::CreateInstance(IID_PPV_ARGS(&apps))",
      "AppReadiness::ImmersivePolicy::GetAllDefaultApps",
      "onecoreuap\\shell\\appreadiness\\src\\core\\ImmersivePolicy.h",
      37);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v7 = *(HMODULE *)(a1 + 8);
  if ( v7 )
  {
    ProcAddress = GetProcAddress(v7, "GetAllDefaultApps");
    if ( !ProcAddress )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        -2147418113,
        "getDefaultApps != nullptr",
        "AppReadiness::ImmersivePolicy::GetAllDefaultApps",
        "onecoreuap\\shell\\appreadiness\\src\\core\\ImmersivePolicy.h",
        43);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v10 = ((__int64 (__fastcall *)(void *))ProcAddress)(*a2);
    if ( v10 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v10,
        "getDefaultApps(apps.Get())",
        "AppReadiness::ImmersivePolicy::GetAllDefaultApps",
        "onecoreuap\\shell\\appreadiness\\src\\core\\ImmersivePolicy.h",
        44);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800078b4  mov     rax, rsp
0x1800078b7  mov     [rax+8], rbx
0x1800078bb  mov     [rax+10h], rdx
0x1800078bf  push    rdi
0x1800078c0  sub     rsp, 60h
0x1800078c4  mov     rbx, rdx
0x1800078c7  mov     rdi, rcx
0x1800078ca  mov     dword ptr [rax-38h], 0
0x1800078d1  mov     qword ptr [rdx], 0
0x1800078d8  mov     dword ptr [rax-38h], 1
0x1800078df  mov     rcx, rdx
0x1800078e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800078e7  mov     r8, rbx; void **
0x1800078ea  call    ?CreateInstance@CEnumerableObjectCollection@@SAJHAEBU_GUID@@PEAPEAX@Z; CEnumerableObjectCollection::CreateInstance(int,_GUID const &,void * *)
0x1800078ef  test    eax, eax
0x1800078f1  js      loc_1800079AF
0x1800078f7  mov     rcx, [rdi+8]; hModule
0x1800078fb  test    rcx, rcx
0x1800078fe  jnz     short loc_18000790E
0x180007900  mov     rax, rbx
0x180007903  mov     rbx, [rsp+68h+arg_0]
0x180007908  add     rsp, 60h
0x18000790c  pop     rdi
0x18000790d  retn
0x18000790e  lea     rdx, ProcName; "GetAllDefaultApps"
0x180007915  call    cs:__imp_GetProcAddress
0x18000791b  test    rax, rax
0x18000791e  jz      short loc_18000796C
0x180007920  mov     rcx, [rbx]
0x180007923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007928  test    eax, eax
0x18000792a  jns     short loc_180007900
0x18000792c  mov     [rsp+68h+var_40], 2Ch ; ','; int
0x180007934  lea     rcx, aOnecoreuapShel_20; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000793b  mov     [rsp+68h+var_48], rcx; char *
0x180007940  lea     r9, aAppreadinessIm_0; "AppReadiness::ImmersivePolicy::GetAllDe"...
0x180007947  lea     r8, aGetdefaultapps_0; "getDefaultApps(apps.Get())"
0x18000794e  mov     edx, eax; int
0x180007950  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180007955  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000795a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180007961  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180007966  call    _CxxThrowException_0
0x18000796c  mov     [rsp+68h+var_40], 2Bh ; '+'; int
0x180007974  lea     rcx, aOnecoreuapShel_20; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18000797b  mov     [rsp+68h+var_48], rcx; char *
0x180007980  lea     r9, aAppreadinessIm_0; "AppReadiness::ImmersivePolicy::GetAllDe"...
0x180007987  lea     r8, aGetdefaultapps; "getDefaultApps != nullptr"
0x18000798e  mov     edx, 8000FFFFh; int
0x180007993  lea     rcx, [rsp+68h+pExceptionObject]; this
0x180007998  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18000799d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800079a4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800079a9  call    _CxxThrowException_0
0x1800079af  mov     [rsp+68h+var_40], 25h ; '%'; int
0x1800079b7  lea     rcx, aOnecoreuapShel_20; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800079be  mov     [rsp+68h+var_48], rcx; char *
0x1800079c3  lea     r9, aAppreadinessIm_0; "AppReadiness::ImmersivePolicy::GetAllDe"...
0x1800079ca  lea     r8, aCenumerableobj; "CEnumerableObjectCollection::CreateInst"...
0x1800079d1  mov     edx, eax; int
0x1800079d3  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800079d8  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800079dd  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800079e4  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800079e9  call    _CxxThrowException_0
```
