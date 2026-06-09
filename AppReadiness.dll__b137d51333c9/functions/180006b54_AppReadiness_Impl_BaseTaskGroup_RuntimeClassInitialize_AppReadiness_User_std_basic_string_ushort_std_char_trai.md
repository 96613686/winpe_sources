# AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(AppReadiness::User *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::weak_ptr<AppReadiness::PackageInfo> const &,AppReadiness::TaskPriority)

- ea: `0x180006b54`
- end: `0x180006cd9`
- name: `?RuntimeClassInitialize@BaseTaskGroup@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$weak_ptr@VPackageInfo@AppReadiness@@@6@W4TaskPriority@3@@Z`
- size: `389`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006918`
- `0x180006f40`
- `0x1800277ac`
- `0x180027aa0`
- `0x18002def4`
- `0x180035458`
- `0x180064370`
- `0x1800644f0`

## callees

- `0x180006b54`
- `0x180027a4c`
- `0x18002e228`
- `0x18003ecb4`
- `0x180044a38`
- `0x1800473d8`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006c06`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180006c06`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180006c72`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180006c72`

## string_xrefs

- `0x180006b7c`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x180006c25`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x180006c91`: `onecoreuap\shell\appreadiness\src\core\basetaskgroup.cpp`
- `0x180006b83`: `__super::RuntimeClassInitialize(user, taskId, packageInfo, priority)`
- `0x180006b8f`: `AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize`
- `0x180006c39`: `AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize`
- `0x180006ca5`: `AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize`
- `0x180006c47`: `ResultFromWin32HandleMaybenull(CreateSemaphoreEx(nullptr, semaphoreCount, semaphoreCount, nullptr, 0, SYNCHRONIZE | SEMAPHORE_MODIFY_STATE), m_taskGate.GetAddressOf())`
- `0x180006cb3`: `ResultFromWin32HandleMaybenull(CreateEventEx(nullptr, nullptr, 0, SYNCHRONIZE | EVENT_MODIFY_STATE), m_completeEvent.GetAddressOf())`

## pseudocode

```c
__int64 __fastcall AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize(
        _QWORD *a1,
        int a2,
        int a3,
        int a4,
        int a5)
{
  int v6; // eax
  LONG v7; // eax
  HANDLE Semaphore; // rax
  int Error; // eax
  HANDLE Event; // rax
  int v11; // eax
  int pExceptionObject; // [rsp+40h] [rbp-38h] BYREF
  const char *v14; // [rsp+48h] [rbp-30h]
  const char *v15; // [rsp+50h] [rbp-28h]
  const char *v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+60h] [rbp-18h]

  v6 = AppReadiness::Impl::BaseTask::RuntimeClassInitialize((int)a1 + 8, a2, a3, a4, a5);
  if ( v6 < 0 )
  {
    v14 = "onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp";
    v15 = "__super::RuntimeClassInitialize(user, taskId, packageInfo, priority)";
    v16 = "AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize";
    v17 = 24;
    pExceptionObject = v6;
    if ( (Microsoft_Windows_AppReadinessEnableBits & 2) != 0 )
      McTemplateU0dsssd_EventWriteTransfer(
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
        (unsigned int)"__super::RuntimeClassInitialize(user, taskId, packageInfo, priority)",
        v6,
        (unsigned int)"__super::RuntimeClassInitialize(user, taskId, packageInfo, priority)",
        (__int64)"AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize",
        (__int64)"onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
        24);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 48LL))(a1);
  Semaphore = CreateSemaphoreExW(0, v7, v7, 0, 0, 0x100002u);
  a1[36] = Semaphore;
  if ( Semaphore )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  if ( Error < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      Error,
      "ResultFromWin32HandleMaybenull(CreateSemaphoreEx(nullptr, semaphoreCount, semaphoreCount, nullptr, 0, SYNCHRONIZE "
      "| SEMAPHORE_MODIFY_STATE), m_taskGate.GetAddressOf())",
      "AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
      26);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  Event = CreateEventExW(0, 0, 0, 0x100002u);
  a1[38] = Event;
  if ( Event )
    v11 = 0;
  else
    v11 = ResultFromKnownLastError();
  if ( v11 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&pExceptionObject,
      v11,
      "ResultFromWin32HandleMaybenull(CreateEventEx(nullptr, nullptr, 0, SYNCHRONIZE | EVENT_MODIFY_STATE), m_completeEve"
      "nt.GetAddressOf())",
      "AppReadiness::Impl::BaseTaskGroup::RuntimeClassInitialize",
      "onecoreuap\\shell\\appreadiness\\src\\core\\basetaskgroup.cpp",
      27);
    throw (Windows::HResultException *)&pExceptionObject;
  }
  return 0;
}

```

## disassembly

```asm
0x180006b54  push    rbx
0x180006b56  sub     rsp, 70h
0x180006b5a  mov     eax, [rsp+78h+arg_20]
0x180006b61  mov     rbx, rcx
0x180006b64  add     rcx, 8
0x180006b68  mov     [rsp+78h+dwFlags], eax
0x180006b6c  call    ?RuntimeClassInitialize@BaseTask@Impl@AppReadiness@@IEAAJPEAVUser@3@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$weak_ptr@VPackageInfo@AppReadiness@@@6@W4TaskPriority@3@@Z; AppReadiness::Impl::BaseTask::RuntimeClassInitialize(AppReadiness::User *,std::wstring const &,std::weak_ptr<AppReadiness::PackageInfo> const &,AppReadiness::TaskPriority)
0x180006b71  test    eax, eax
0x180006b73  jns     short loc_180006BDD
0x180006b75  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 2
0x180006b7c  lea     rcx, aOnecoreuapShel_11; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180006b83  lea     rdx, aSuperRuntimecl_2; "__super::RuntimeClassInitialize(user, t"...
0x180006b8a  mov     [rsp+78h+var_30], rcx
0x180006b8f  lea     r9, aAppreadinessIm_7; "AppReadiness::Impl::BaseTaskGroup::Runt"...
0x180006b96  mov     [rsp+78h+var_28], rdx
0x180006b9b  mov     r8d, 18h
0x180006ba1  mov     [rsp+78h+var_20], r9
0x180006ba6  mov     [rsp+78h+var_18], r8d
0x180006bab  mov     [rsp+78h+pExceptionObject], eax
0x180006baf  jz      short loc_180006BCB
0x180006bb1  mov     [rsp+78h+var_48], r8d
0x180006bb6  mov     r8d, eax
0x180006bb9  mov     qword ptr [rsp+78h+dwDesiredAccess], rcx
0x180006bbe  mov     qword ptr [rsp+78h+dwFlags], r9
0x180006bc3  mov     r9, rdx
0x180006bc6  call    McTemplateU0dsssd_EventWriteTransfer
0x180006bcb  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180006bd2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180006bd7  call    _CxxThrowException_0
0x180006bdd  mov     rax, [rbx]
0x180006be0  mov     rcx, rbx
0x180006be3  mov     rax, [rax+30h]
0x180006be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bec  xor     r9d, r9d; lpName
0x180006bef  mov     [rsp+78h+dwDesiredAccess], 100002h; dwDesiredAccess
0x180006bf7  mov     r8d, eax; lMaximumCount
0x180006bfa  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180006c02  mov     edx, eax; lInitialCount
0x180006c04  xor     ecx, ecx; lpSemaphoreAttributes
0x180006c06  call    cs:__imp_CreateSemaphoreExW
0x180006c0c  mov     [rbx+120h], rax
0x180006c13  test    rax, rax
0x180006c16  jnz     short loc_180006C1F
0x180006c18  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006c1d  jmp     short loc_180006C21
0x180006c1f  xor     eax, eax
0x180006c21  test    eax, eax
0x180006c23  jns     short loc_180006C65
0x180006c25  lea     rcx, aOnecoreuapShel_11; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180006c2c  mov     [rsp+78h+dwDesiredAccess], 1Ah; int
0x180006c34  mov     qword ptr [rsp+78h+dwFlags], rcx; char *
0x180006c39  lea     r9, aAppreadinessIm_7; "AppReadiness::Impl::BaseTaskGroup::Runt"...
0x180006c40  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180006c45  mov     edx, eax; int
0x180006c47  lea     r8, aResultfromwin3_4; "ResultFromWin32HandleMaybenull(CreateSe"...
0x180006c4e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180006c53  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180006c5a  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180006c5f  call    _CxxThrowException_0
0x180006c65  mov     r9d, 100002h; dwDesiredAccess
0x180006c6b  xor     r8d, r8d; dwFlags
0x180006c6e  xor     edx, edx; lpName
0x180006c70  xor     ecx, ecx; lpEventAttributes
0x180006c72  call    cs:__imp_CreateEventExW
0x180006c78  mov     [rbx+130h], rax
0x180006c7f  test    rax, rax
0x180006c82  jnz     short loc_180006C8B
0x180006c84  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006c89  jmp     short loc_180006C8D
0x180006c8b  xor     eax, eax
0x180006c8d  test    eax, eax
0x180006c8f  jns     short loc_180006CD1
0x180006c91  lea     rcx, aOnecoreuapShel_11; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180006c98  mov     [rsp+78h+dwDesiredAccess], 1Bh; int
0x180006ca0  mov     qword ptr [rsp+78h+dwFlags], rcx; char *
0x180006ca5  lea     r9, aAppreadinessIm_7; "AppReadiness::Impl::BaseTaskGroup::Runt"...
0x180006cac  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180006cb1  mov     edx, eax; int
0x180006cb3  lea     r8, aResultfromwin3_1; "ResultFromWin32HandleMaybenull(CreateEv"...
0x180006cba  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180006cbf  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180006cc6  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180006ccb  call    _CxxThrowException_0
0x180006cd1  xor     eax, eax
0x180006cd3  add     rsp, 70h
0x180006cd7  pop     rbx
0x180006cd8  retn
```
