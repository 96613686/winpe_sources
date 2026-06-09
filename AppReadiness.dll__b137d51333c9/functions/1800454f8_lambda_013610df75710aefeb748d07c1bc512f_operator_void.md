# _lambda_013610df75710aefeb748d07c1bc512f_::operator()(void)

- ea: `0x1800454f8`
- end: `0x180045728`
- name: `??R_lambda_013610df75710aefeb748d07c1bc512f_@@QEBA@XZ`
- size: `560`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047620`

## callees

- `0x180002958`
- `0x18000e5b4`
- `0x180011cac`
- `0x180012028`
- `0x180012784`
- `0x180014220`
- `0x180014384`
- `0x18001bee0`
- `0x180027a4c`
- `0x180035c18`
- `0x18003ecb4`
- `0x180045258`
- `0x1800454f8`

## string_xrefs

- `0x1800455fa`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045636`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045677`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800456b8`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800456f4`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180045707`: `localTask.As(&taskToWrap)`
- `0x18004560d`: `ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(task, taskToWrap.Get())`
- `0x18004568a`: `!IsCallerLowIL(INVALID_USERCONTEXT_TOKEN)`
- `0x180045606`: `AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()`
- `0x180045642`: `AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()`
- `0x180045683`: `AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()`
- `0x1800456c4`: `AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()`
- `0x180045700`: `AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()`
- `0x1800456cb`: `MakeAndInitialize<Tasks::ResolveStoreCategories>(&localTask, user.Get(), cPackageFamilyNames, packageFamilyNames)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_013610df75710aefeb748d07c1bc512f_::operator()(__int64 a1)
{
  __int64 v2; // rcx
  AppReadiness::Api *v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rdi
  int v6; // edx
  RTL_SRWLOCK *v7; // rax
  int v8; // edx
  int v9; // edx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  struct ITask *v12; // [rsp+90h] [rbp+28h] BYREF
  AppReadiness::User *v13; // [rsp+98h] [rbp+30h] BYREF
  AppReadiness::User *v14; // [rsp+A0h] [rbp+38h] BYREF
  AppReadiness::User *v15; // [rsp+A8h] [rbp+40h] BYREF

  if ( AppReadiness::Api::IsDisabledForAuditMode(*(AppReadiness::Api **)a1) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147024886,
      "!IsDisabledForAuditMode()",
      "AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      286);
    throw (Windows::HResultException *)pExceptionObject;
  }
  AppReadiness::Api::CreateUser(v2, &v13, 0);
  if ( AppReadiness::Api::IsCallerLowIL(v3, 0) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147024891,
      "!IsCallerLowIL(INVALID_USERCONTEXT_TOKEN)",
      "AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      288);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v12 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(_QWORD *)(a1 + 8);
  v15 = v13;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::ResolveStoreCategories,AppReadiness::ITask,AppReadiness::User *,unsigned int &,unsigned short const * * &>(
         &v12,
         &v15,
         v5,
         v4);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v6,
      "MakeAndInitialize<Tasks::ResolveStoreCategories>(&localTask, user.Get(), cPackageFamilyNames, packageFamilyNames)",
      "AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      290);
    throw (Windows::HResultException *)pExceptionObject;
  }
  AppReadiness::User::AddTask(v13, v12);
  v7 = (RTL_SRWLOCK *)AppReadiness::Service::Get();
  AppReadiness::Service::ProcessUserTasks(v7, v13);
  v14 = 0;
  v8 = Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(&v12, &v14);
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v8,
      "localTask.As(&taskToWrap)",
      "AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      294);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v15 = v14;
  v9 = Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(**(void ****)(a1 + 24));
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v9,
      "ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(tas"
      "k, taskToWrap.Get())",
      "AppReadiness::Api::ResolveStoreCategories::<lambda_013610df75710aefeb748d07c1bc512f>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      295);
    throw (Windows::HResultException *)pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
}

```

## disassembly

```asm
0x1800454f8  push    rbp
0x1800454fa  push    rbx
0x1800454fb  push    rsi
0x1800454fc  push    rdi
0x1800454fd  mov     rbp, rsp
0x180045500  sub     rsp, 68h
0x180045504  mov     rsi, rcx
0x180045507  mov     rcx, [rcx]; this
0x18004550a  call    ?IsDisabledForAuditMode@Api@AppReadiness@@AEAA_NXZ; AppReadiness::Api::IsDisabledForAuditMode(void)
0x18004550f  test    al, al
0x180045511  jnz     loc_18004562E
0x180045517  xor     r8d, r8d
0x18004551a  lea     rdx, [rbp+arg_8]
0x18004551e  call    ?CreateUser@Api@AppReadiness@@AEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@_K@Z; AppReadiness::Api::CreateUser(unsigned __int64)
0x180045523  nop
0x180045524  xor     edx, edx; unsigned __int64
0x180045526  call    ?IsCallerLowIL@Api@AppReadiness@@AEAA_N_K@Z; AppReadiness::Api::IsCallerLowIL(unsigned __int64)
0x18004552b  test    al, al
0x18004552d  jnz     loc_18004566F
0x180045533  mov     [rbp+arg_0], 0
0x18004553b  mov     rbx, [rsi+10h]
0x18004553f  mov     rdi, [rsi+8]
0x180045543  mov     rax, [rbp+arg_8]
0x180045547  mov     [rbp+arg_18], rax
0x18004554b  lea     rcx, [rbp+arg_0]
0x18004554f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180045554  mov     r9, rbx
0x180045557  mov     r8, rdi
0x18004555a  lea     rdx, [rbp+arg_18]
0x18004555e  lea     rcx, [rbp+arg_0]
0x180045562  call    ??$MakeAndInitialize@VResolveStoreCategories@Tasks@AppReadiness@@UITask@3@PEAVUser@3@AEAIAEAPEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAUITask@AppReadiness@@$$QEAPEAVUser@4@AEAIAEAPEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<AppReadiness::Tasks::ResolveStoreCategories,AppReadiness::ITask,AppReadiness::User *,uint &,ushort const * * &>(AppReadiness::ITask * *,AppReadiness::User * &&,uint &,ushort const * * &)
0x180045567  mov     edx, eax; int
0x180045569  test    eax, eax
0x18004556b  js      loc_1800456B0
0x180045571  mov     rdx, [rbp+arg_0]; struct ITask *
0x180045575  mov     rcx, [rbp+arg_8]; this
0x180045579  call    ?AddTask@User@AppReadiness@@QEAAXPEAUITask@2@@Z; AppReadiness::User::AddTask(AppReadiness::ITask *)
0x18004557e  call    ?Get@Service@AppReadiness@@SAAEAV12@XZ; AppReadiness::Service::Get(void)
0x180045583  mov     rdx, [rbp+arg_8]; struct AppReadiness::User *
0x180045587  mov     rcx, rax; this
0x18004558a  call    ?ProcessUserTasks@Service@AppReadiness@@QEAAXPEAVUser@2@@Z; AppReadiness::Service::ProcessUserTasks(AppReadiness::User *)
0x18004558f  mov     [rbp+arg_10], 0
0x180045597  lea     rdx, [rbp+arg_10]
0x18004559b  lea     rcx, [rbp+arg_0]
0x18004559f  call    ??$As@UIAppReadinessTask@@@?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppReadinessTask@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppReadinessTask>>)
0x1800455a4  mov     edx, eax; int
0x1800455a6  test    eax, eax
0x1800455a8  js      loc_1800456EC
0x1800455ae  mov     rax, [rbp+arg_10]
0x1800455b2  mov     [rbp+arg_18], rax
0x1800455b6  mov     rcx, [rsi+18h]
0x1800455ba  lea     rdx, [rbp+arg_18]
0x1800455be  mov     rcx, [rcx]; void **
0x1800455c1  call    ??$MakeAndInitializeDisconnectableObject@VExternalTaskWrapper@Impl@AppReadiness@@UIAppReadinessTask@@PEAU4@@ComDisconnectableObjectManager@Internal@Windows@@SAJPEAPEAUIAppReadinessTask@@$$QEAPEAU3@@Z; Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(IAppReadinessTask * *,IAppReadinessTask * &&)
0x1800455c6  mov     edx, eax; int
0x1800455c8  test    eax, eax
0x1800455ca  js      short loc_1800455F2
0x1800455cc  lea     rcx, [rbp+arg_10]
0x1800455d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800455d5  nop
0x1800455d6  lea     rcx, [rbp+arg_0]
0x1800455da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800455df  nop
0x1800455e0  lea     rcx, [rbp+arg_8]
0x1800455e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800455e9  add     rsp, 68h
0x1800455ed  pop     rdi
0x1800455ee  pop     rsi
0x1800455ef  pop     rbx
0x1800455f0  pop     rbp
0x1800455f1  retn
0x1800455f2  mov     [rsp+68h+var_40], 127h; int
0x1800455fa  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180045601  mov     [rsp+68h+var_48], rax; char *
0x180045606  lea     r9, aAppreadinessAp_11; "AppReadiness::Api::ResolveStoreCategori"...
0x18004560d  lea     r8, aComdisconnecta_1; "ComDisconnectableObjectManager::MakeAnd"...
0x180045614  lea     rcx, [rbp+pExceptionObject]; this
0x180045618  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18004561d  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045624  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180045628  call    _CxxThrowException_0
0x18004562e  mov     [rsp+68h+var_40], 11Eh; int
0x180045636  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18004563d  mov     [rsp+68h+var_48], rax; char *
0x180045642  lea     r9, aAppreadinessAp_11; "AppReadiness::Api::ResolveStoreCategori"...
0x180045649  lea     r8, aIsdisabledfora; "!IsDisabledForAuditMode()"
0x180045650  mov     edx, 8007000Ah; int
0x180045655  lea     rcx, [rbp+pExceptionObject]; this
0x180045659  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18004565e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180045665  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180045669  call    _CxxThrowException_0
0x18004566f  mov     [rsp+68h+var_40], 120h; int
0x180045677  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18004567e  mov     [rsp+68h+var_48], rax; char *
0x180045683  lea     r9, aAppreadinessAp_11; "AppReadiness::Api::ResolveStoreCategori"...
0x18004568a  lea     r8, aIscallerlowilI; "!IsCallerLowIL(INVALID_USERCONTEXT_TOKE"...
0x180045691  mov     edx, 80070005h; int
0x180045696  lea     rcx, [rbp+pExceptionObject]; this
0x18004569a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18004569f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800456a6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800456aa  call    _CxxThrowException_0
0x1800456b0  mov     [rsp+68h+var_40], 122h; int
0x1800456b8  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800456bf  mov     [rsp+68h+var_48], rax; char *
0x1800456c4  lea     r9, aAppreadinessAp_11; "AppReadiness::Api::ResolveStoreCategori"...
0x1800456cb  lea     r8, aMakeandinitial_13; "MakeAndInitialize<Tasks::ResolveStoreCa"...
0x1800456d2  lea     rcx, [rbp+pExceptionObject]; this
0x1800456d6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800456db  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800456e2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800456e6  call    _CxxThrowException_0
0x1800456ec  mov     [rsp+68h+var_40], 126h; int
0x1800456f4  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800456fb  mov     [rsp+68h+var_48], rax; char *
0x180045700  lea     r9, aAppreadinessAp_11; "AppReadiness::Api::ResolveStoreCategori"...
0x180045707  lea     r8, aLocaltaskAsTas; "localTask.As(&taskToWrap)"
0x18004570e  lea     rcx, [rbp+pExceptionObject]; this
0x180045712  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180045717  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18004571e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180045722  call    _CxxThrowException_0
```
