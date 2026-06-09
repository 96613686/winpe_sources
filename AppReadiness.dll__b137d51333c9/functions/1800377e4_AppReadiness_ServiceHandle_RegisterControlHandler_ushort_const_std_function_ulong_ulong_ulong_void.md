# AppReadiness::ServiceHandle::RegisterControlHandler(ushort const *,std::function<ulong (ulong,ulong,void *)> &&)

- ea: `0x1800377e4`
- end: `0x180037919`
- name: `?RegisterControlHandler@ServiceHandle@AppReadiness@@QEAAXPEBG$$QEAV?$function@$$A6AKKKPEAX@Z@std@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(LPVOID lpContext, LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800221a4`

## callees

- `0x1800041e0`
- `0x180020888`
- `0x1800208e0`
- `0x180027a4c`
- `0x1800377e4`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800378fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800378fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037806`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037806`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180037887`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180037887`

## string_xrefs

- `0x18003782f`: `AppReadiness::ServiceHandle::RegisterControlHandler`
- `0x1800378ca`: `AppReadiness::ServiceHandle::RegisterControlHandler`
- `0x180037823`: `onecoreuap\shell\appreadiness\src\core\servicehandle.cpp`
- `0x1800378be`: `onecoreuap\shell\appreadiness\src\core\servicehandle.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::ServiceHandle::RegisterControlHandler(
        RTL_SRWLOCK *lpContext,
        LPCWSTR lpServiceName,
        RTL_SRWLOCK *a3)
{
  RTL_SRWLOCK *v6; // rsi
  SERVICE_STATUS_HANDLE Ptr; // rdi
  int Error; // eax
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-48h] BYREF

  v6 = lpContext + 3;
  AcquireSRWLockExclusive(lpContext + 3);
  if ( lpContext[1].Ptr )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147418113,
      "E_UNEXPECTED",
      "AppReadiness::ServiceHandle::RegisterControlHandler",
      "onecoreuap\\shell\\appreadiness\\src\\core\\servicehandle.cpp",
      94);
    throw (Windows::HResultException *)pExceptionObject;
  }
  if ( &lpContext[4] != a3 )
  {
    std::function<void (AppReadiness::Storage::PackageList const &,std::wstring const &,enum AppReadiness::Storage::PackageOperation)>::~function<void (AppReadiness::Storage::PackageList const &,std::wstring const &,enum AppReadiness::Storage::PackageOperation)>(&lpContext[4]);
    std::_Func_class<unsigned long,unsigned long,unsigned long,void *>::_Reset_move(&lpContext[4], a3);
  }
  Ptr = RegisterServiceCtrlHandlerExW(lpServiceName, AppReadiness::ServiceHandle::ServiceControlProc, lpContext);
  if ( Ptr == lpContext[1].Ptr )
  {
    Ptr = (SERVICE_STATUS_HANDLE)lpContext[1].Ptr;
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(lpContext);
    lpContext[1].Ptr = Ptr;
  }
  if ( !Ptr )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "ResultFromKnownLastError()",
        "AppReadiness::ServiceHandle::RegisterControlHandler",
        "onecoreuap\\shell\\appreadiness\\src\\core\\servicehandle.cpp",
        101);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x1800377e4  mov     [rsp+arg_8], rbx
0x1800377e9  mov     [rsp+arg_10], rbp
0x1800377ee  push    rsi
0x1800377ef  push    rdi
0x1800377f0  push    r14
0x1800377f2  sub     rsp, 60h
0x1800377f6  mov     rbp, r8
0x1800377f9  mov     r14, rdx
0x1800377fc  mov     rbx, rcx
0x1800377ff  lea     rsi, [rcx+18h]
0x180037803  mov     rcx, rsi; SRWLock
0x180037806  call    cs:__imp_AcquireSRWLockExclusive
0x18003780c  mov     [rsp+78h+arg_0], rsi
0x180037814  cmp     qword ptr [rbx+8], 0
0x180037819  jz      short loc_18003785E
0x18003781b  mov     [rsp+78h+var_50], 5Eh ; '^'; int
0x180037823  lea     rcx, aOnecoreuapShel_23; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18003782a  mov     [rsp+78h+var_58], rcx; char *
0x18003782f  lea     r9, aAppreadinessSe_3; "AppReadiness::ServiceHandle::RegisterCo"...
0x180037836  lea     r8, aEUnexpected; "E_UNEXPECTED"
0x18003783d  mov     edx, 8000FFFFh; int
0x180037842  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180037847  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18003784c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180037853  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180037858  call    _CxxThrowException_0
0x18003785e  lea     rdi, [rbx+20h]
0x180037862  cmp     rdi, rbp
0x180037865  jz      short loc_18003787A
0x180037867  mov     rcx, rdi
0x18003786a  call    ??1?$function@$$A6AXAEBVPackageList@Storage@AppReadiness@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@23@@Z@std@@QEAA@XZ; std::function<void (AppReadiness::Storage::PackageList const &,std::wstring const &,AppReadiness::Storage::PackageOperation)>::~function<void (AppReadiness::Storage::PackageList const &,std::wstring const &,AppReadiness::Storage::PackageOperation)>(void)
0x18003786f  mov     rdx, rbp
0x180037872  mov     rcx, rdi
0x180037875  call    ?_Reset_move@?$_Func_class@KKKPEAX@std@@IEAAX$$QEAV12@@Z; std::_Func_class<ulong,ulong,ulong,void *>::_Reset_move(std::_Func_class<ulong,ulong,ulong,void *> &&)
0x18003787a  mov     r8, rbx; lpContext
0x18003787d  lea     rdx, ?ServiceControlProc@ServiceHandle@AppReadiness@@KAKKKPEAX0@Z; lpHandlerProc
0x180037884  mov     rcx, r14; lpServiceName
0x180037887  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003788d  mov     rdi, rax
0x180037890  cmp     rax, [rbx+8]
0x180037894  jz      short loc_1800378A4
0x180037896  mov     rcx, rbx
0x180037899  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003789e  mov     [rbx+8], rdi
0x1800378a2  jmp     short loc_1800378A8
0x1800378a4  mov     rdi, [rbx+8]
0x1800378a8  test    rdi, rdi
0x1800378ab  jnz     short loc_1800378F6
0x1800378ad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800378b2  test    eax, eax
0x1800378b4  jns     short loc_1800378F6
0x1800378b6  mov     [rsp+78h+var_50], 65h ; 'e'; int
0x1800378be  lea     rcx, aOnecoreuapShel_23; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800378c5  mov     [rsp+78h+var_58], rcx; char *
0x1800378ca  lea     r9, aAppreadinessSe_3; "AppReadiness::ServiceHandle::RegisterCo"...
0x1800378d1  lea     r8, aResultfromknow; "ResultFromKnownLastError()"
0x1800378d8  mov     edx, eax; int
0x1800378da  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800378df  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800378e4  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800378eb  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800378f0  call    _CxxThrowException_0
0x1800378f6  test    rsi, rsi
0x1800378f9  jz      short loc_180037904
0x1800378fb  mov     rcx, rsi; SRWLock
0x1800378fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180037904  lea     r11, [rsp+78h+var_18]
0x180037909  mov     rbx, [r11+28h]
0x18003790d  mov     rbp, [r11+30h]
0x180037911  mov     rsp, r11
0x180037914  pop     r14
0x180037916  pop     rdi
0x180037917  pop     rsi
0x180037918  retn
```
