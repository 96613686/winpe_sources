# _lambda_aef94fd03712ae74ab901525f0937ca8_::operator()(void)

- ea: `0x180045f74`
- end: `0x180046306`
- name: `??R_lambda_aef94fd03712ae74ab901525f0937ca8_@@QEBA@XZ`
- size: `914`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800476e0`

## callees

- `0x180002958`
- `0x18000d17c`
- `0x180011cac`
- `0x180012028`
- `0x180012784`
- `0x180013b0c`
- `0x180014384`
- `0x18001bee0`
- `0x180027a4c`
- `0x18002c0d0`
- `0x18002c824`
- `0x180035c18`
- `0x1800371d8`
- `0x18003ecb4`
- `0x180045f74`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045fb5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180045fb5`

## string_xrefs

- `0x180046192`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800461ce`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x18004620f`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180046250`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180046291`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800462d2`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180046263`: `!IsCallerLowIL(userContextToken)`
- `0x1800462a4`: `localTask`
- `0x1800462e5`: `localTask.As(&taskToWrap)`
- `0x1800461a5`: `ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(task, taskToWrap.Get())`
- `0x18004619e`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`
- `0x1800461da`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`
- `0x18004621b`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`
- `0x18004625c`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`
- `0x18004629d`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`
- `0x1800462de`: `AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_aef94fd03712ae74ab901525f0937ca8_::operator()(__int64 a1)
{
  AppReadiness::Api *v2; // rcx
  struct AppReadiness::Service *v3; // rax
  _QWORD *v4; // r9
  AppReadiness::Api *v5; // rcx
  _QWORD *v6; // r9
  __int64 Task; // rax
  int v8; // edx
  int v9; // edx
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF
  AppReadiness::User *v13; // [rsp+88h] [rbp+20h] BYREF
  AppReadiness::User *v14; // [rsp+90h] [rbp+28h] BYREF
  char v15; // [rsp+98h] [rbp+30h] BYREF

  if ( AppReadiness::Api::IsDisabledForAuditMode(*(AppReadiness::Api **)a1) )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147024886,
      "!IsDisabledForAuditMode()",
      "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      146);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v12 = 0;
  if ( CompareStringOrdinal(**(LPCWCH **)(a1 + 8), -1, L"ART:AppxPreRegistration", -1, 1) == 2 )
  {
    if ( !AppReadiness::Api::DoesCallerHaveAdminRights(v2) )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        -2147024891,
        "DoesCallerHaveAdminRights()",
        "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        150);
      throw (Windows::HResultException *)pExceptionObject;
    }
    v3 = AppReadiness::Service::Get();
    AppReadiness::Service::GetSystemUser(v3, &v13);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v4 = (_QWORD *)((char *)v13 + 64);
      if ( *((_QWORD *)v13 + 11) > 7u )
        v4 = (_QWORD *)*v4;
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids,
        (_DWORD)v4,
        **(_QWORD **)(a1 + 8),
        **(_DWORD **)(a1 + 16));
    }
  }
  else
  {
    AppReadiness::Api::CreateUser(v2, &v13, **(_QWORD **)(a1 + 32));
    v5 = (AppReadiness::Api *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v6 = (_QWORD *)((char *)v13 + 64);
      if ( *((_QWORD *)v13 + 11) > 7u )
        v6 = (_QWORD *)*v6;
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids,
        (_DWORD)v6,
        **(_QWORD **)(a1 + 8),
        **(_DWORD **)(a1 + 16));
    }
    if ( AppReadiness::Api::IsCallerLowIL(v5, **(_QWORD **)(a1 + 32)) )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        -2147024891,
        "!IsCallerLowIL(userContextToken)",
        "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        159);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  Task = AppReadiness::User::CreateTask(v13);
  Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(&v12, Task);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  if ( !v12 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      -2147024809,
      "localTask",
      "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      163);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v14 = 0;
  v8 = Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(&v12, &v14);
  if ( v8 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v8,
      "localTask.As(&taskToWrap)",
      "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      165);
    throw (Windows::HResultException *)pExceptionObject;
  }
  v13 = v14;
  v9 = Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(**(void ****)(a1 + 40));
  if ( v9 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      v9,
      "ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper>(tas"
      "k, taskToWrap.Get())",
      "AppReadiness::Api::CreateTaskForUser::<lambda_aef94fd03712ae74ab901525f0937ca8>::operator ()",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      166);
    throw (Windows::HResultException *)pExceptionObject;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
}

```

## disassembly

```asm
0x180045f74  push    rbp
0x180045f76  push    rbx
0x180045f77  mov     rbp, rsp
0x180045f7a  sub     rsp, 68h
0x180045f7e  mov     rbx, rcx
0x180045f81  mov     rcx, [rcx]; this
0x180045f84  call    ?IsDisabledForAuditMode@Api@AppReadiness@@AEAA_NXZ; AppReadiness::Api::IsDisabledForAuditMode(void)
0x180045f89  test    al, al
0x180045f8b  jnz     loc_1800461C6
0x180045f91  mov     [rbp+arg_0], 0
0x180045f99  mov     rcx, [rbx+8]
0x180045f9d  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180045fa5  or      edx, 0FFFFFFFFh; cchCount1
0x180045fa8  mov     r9d, edx; cchCount2
0x180045fab  lea     r8, aArtAppxpreregi; "ART:AppxPreRegistration"
0x180045fb2  mov     rcx, [rcx]; lpString1
0x180045fb5  call    cs:__imp_CompareStringOrdinal
0x180045fbb  cmp     eax, 2
0x180045fbe  jnz     loc_180046071
0x180045fc4  call    ?DoesCallerHaveAdminRights@Api@AppReadiness@@AEAA_NXZ; AppReadiness::Api::DoesCallerHaveAdminRights(void)
0x180045fc9  test    al, al
0x180045fcb  jz      loc_180046207
0x180045fd1  call    ?Get@Service@AppReadiness@@SAAEAV12@XZ; AppReadiness::Service::Get(void)
0x180045fd6  lea     rdx, [rbp+arg_8]
0x180045fda  mov     rcx, rax
0x180045fdd  call    ?GetSystemUser@Service@AppReadiness@@QEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@XZ; AppReadiness::Service::GetSystemUser(void)
0x180045fe2  nop
0x180045fe3  lea     rax, WPP_GLOBAL_Control
0x180045fea  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ff1  cmp     rcx, rax
0x180045ff4  jz      short loc_18004603B
0x180045ff6  test    byte ptr [rcx+1Ch], 4
0x180045ffa  jz      short loc_18004603B
0x180045ffc  mov     rax, [rbx+10h]
0x180046000  mov     r8d, [rax]
0x180046003  mov     rax, [rbx+8]
0x180046007  mov     r10, [rax]
0x18004600a  mov     r9, [rbp+arg_8]
0x18004600e  add     r9, 40h ; '@'
0x180046012  cmp     qword ptr [r9+18h], 7
0x180046017  jbe     short loc_18004601C
0x180046019  mov     r9, [r9]
0x18004601c  mov     edx, 0Bh
0x180046021  mov     [rsp+68h+var_40], r8d
0x180046026  mov     qword ptr [rsp+68h+bIgnoreCase], r10
0x18004602b  lea     r8, WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids
0x180046032  mov     rcx, [rcx+10h]
0x180046036  call    WPP_SF_SSd
0x18004603b  mov     r9, [rbx+18h]
0x18004603f  mov     r8, [rbx+8]
0x180046043  mov     r9, [r9]
0x180046046  mov     r8, [r8]
0x180046049  lea     rdx, [rbp+arg_18]
0x18004604d  mov     rcx, [rbp+arg_8]; this
0x180046051  call    ?CreateTask@User@AppReadiness@@QEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@PEBGPEAUIAppReadinessTaskCallback@@@Z; AppReadiness::User::CreateTask(ushort const *,IAppReadinessTaskCallback *)
0x180046056  mov     rdx, rax
0x180046059  lea     rcx, [rbp+arg_0]
0x18004605d  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180046062  lea     rcx, [rbp+arg_18]
0x180046066  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004606b  nop
0x18004606c  jmp     loc_18004611F
0x180046071  mov     r8, [rbx+20h]
0x180046075  mov     r8, [r8]
0x180046078  lea     rdx, [rbp+arg_8]
0x18004607c  call    ?CreateUser@Api@AppReadiness@@AEAA?AV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@_K@Z; AppReadiness::Api::CreateUser(unsigned __int64)
0x180046081  nop
0x180046082  lea     rax, WPP_GLOBAL_Control
0x180046089  mov     rcx, cs:WPP_GLOBAL_Control
0x180046090  cmp     rcx, rax
0x180046093  jz      short loc_1800460DA
0x180046095  test    byte ptr [rcx+1Ch], 4
0x180046099  jz      short loc_1800460DA
0x18004609b  mov     rax, [rbx+10h]
0x18004609f  mov     r8d, [rax]
0x1800460a2  mov     rax, [rbx+8]
0x1800460a6  mov     r10, [rax]
0x1800460a9  mov     r9, [rbp+arg_8]
0x1800460ad  add     r9, 40h ; '@'
0x1800460b1  cmp     qword ptr [r9+18h], 7
0x1800460b6  jbe     short loc_1800460BB
0x1800460b8  mov     r9, [r9]
0x1800460bb  mov     edx, 0Ch
0x1800460c0  mov     [rsp+68h+var_40], r8d
0x1800460c5  mov     qword ptr [rsp+68h+bIgnoreCase], r10
0x1800460ca  lea     r8, WPP_59563c3a3b9a39f4b8470c5664078a59_Traceguids
0x1800460d1  mov     rcx, [rcx+10h]
0x1800460d5  call    WPP_SF_SSd
0x1800460da  mov     rdx, [rbx+20h]
0x1800460de  mov     rdx, [rdx]; unsigned __int64
0x1800460e1  call    ?IsCallerLowIL@Api@AppReadiness@@AEAA_N_K@Z; AppReadiness::Api::IsCallerLowIL(unsigned __int64)
0x1800460e6  test    al, al
0x1800460e8  jnz     loc_180046248
0x1800460ee  mov     r9, [rbx+18h]
0x1800460f2  mov     r8, [rbx+8]
0x1800460f6  mov     r9, [r9]
0x1800460f9  mov     r8, [r8]
0x1800460fc  lea     rdx, [rbp+arg_18]
0x180046100  mov     rcx, [rbp+arg_8]; this
0x180046104  call    ?CreateTask@User@AppReadiness@@QEAA?AV?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@PEBGPEAUIAppReadinessTaskCallback@@@Z; AppReadiness::User::CreateTask(ushort const *,IAppReadinessTaskCallback *)
0x180046109  mov     rdx, rax
0x18004610c  lea     rcx, [rbp+arg_0]
0x180046110  call    ??4?$ComPtr@UIWindowsStoreUserApps@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IWindowsStoreUserApps>::operator=(Microsoft::WRL::ComPtr<IWindowsStoreUserApps> &&)
0x180046115  lea     rcx, [rbp+arg_18]
0x180046119  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004611e  nop
0x18004611f  lea     rcx, [rbp+arg_8]
0x180046123  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046128  cmp     [rbp+arg_0], 0
0x18004612d  jz      loc_180046289
0x180046133  mov     [rbp+arg_10], 0
0x18004613b  lea     rdx, [rbp+arg_10]
0x18004613f  lea     rcx, [rbp+arg_0]
0x180046143  call    ??$As@UIAppReadinessTask@@@?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIAppReadinessTask@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<AppReadiness::ITask>::As<IAppReadinessTask>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAppReadinessTask>>)
0x180046148  mov     edx, eax; int
0x18004614a  test    eax, eax
0x18004614c  js      loc_1800462CA
0x180046152  mov     rax, [rbp+arg_10]
0x180046156  mov     [rbp+arg_8], rax
0x18004615a  mov     rcx, [rbx+28h]
0x18004615e  lea     rdx, [rbp+arg_8]
0x180046162  mov     rcx, [rcx]; void **
0x180046165  call    ??$MakeAndInitializeDisconnectableObject@VExternalTaskWrapper@Impl@AppReadiness@@UIAppReadinessTask@@PEAU4@@ComDisconnectableObjectManager@Internal@Windows@@SAJPEAPEAUIAppReadinessTask@@$$QEAPEAU3@@Z; Windows::Internal::ComDisconnectableObjectManager::MakeAndInitializeDisconnectableObject<AppReadiness::Impl::ExternalTaskWrapper,IAppReadinessTask,IAppReadinessTask *>(IAppReadinessTask * *,IAppReadinessTask * &&)
0x18004616a  mov     edx, eax; int
0x18004616c  test    eax, eax
0x18004616e  js      short loc_18004618A
0x180046170  lea     rcx, [rbp+arg_10]
0x180046174  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046179  nop
0x18004617a  lea     rcx, [rbp+arg_0]
0x18004617e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046183  add     rsp, 68h
0x180046187  pop     rbx
0x180046188  pop     rbp
0x180046189  retn
0x18004618a  mov     [rsp+68h+var_40], 0A6h; int
0x180046192  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180046199  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x18004619e  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x1800461a5  lea     r8, aComdisconnecta_1; "ComDisconnectableObjectManager::MakeAnd"...
0x1800461ac  lea     rcx, [rbp+pExceptionObject]; this
0x1800461b0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800461b5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800461bc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800461c0  call    _CxxThrowException_0
0x1800461c6  mov     [rsp+68h+var_40], 92h; int
0x1800461ce  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800461d5  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x1800461da  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x1800461e1  lea     r8, aIsdisabledfora; "!IsDisabledForAuditMode()"
0x1800461e8  mov     edx, 8007000Ah; int
0x1800461ed  lea     rcx, [rbp+pExceptionObject]; this
0x1800461f1  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800461f6  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800461fd  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180046201  call    _CxxThrowException_0
0x180046207  mov     [rsp+68h+var_40], 96h; int
0x18004620f  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180046216  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x18004621b  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x180046222  lea     r8, aDoescallerhave; "DoesCallerHaveAdminRights()"
0x180046229  mov     edx, 80070005h; int
0x18004622e  lea     rcx, [rbp+pExceptionObject]; this
0x180046232  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180046237  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18004623e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180046242  call    _CxxThrowException_0
0x180046248  mov     [rsp+68h+var_40], 9Fh; int
0x180046250  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180046257  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x18004625c  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x180046263  lea     r8, aIscallerlowilU; "!IsCallerLowIL(userContextToken)"
0x18004626a  mov     edx, 80070005h; int
0x18004626f  lea     rcx, [rbp+pExceptionObject]; this
0x180046273  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180046278  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18004627f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180046283  call    _CxxThrowException_0
0x180046289  mov     [rsp+68h+var_40], 0A3h; int
0x180046291  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180046298  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x18004629d  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x1800462a4  lea     r8, aLocaltask; "localTask"
0x1800462ab  mov     edx, 80070057h; int
0x1800462b0  lea     rcx, [rbp+pExceptionObject]; this
0x1800462b4  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800462b9  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800462c0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800462c4  call    _CxxThrowException_0
0x1800462ca  mov     [rsp+68h+var_40], 0A5h; int
0x1800462d2  lea     rax, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800462d9  mov     qword ptr [rsp+68h+bIgnoreCase], rax; char *
0x1800462de  lea     r9, aAppreadinessAp_10; "AppReadiness::Api::CreateTaskForUser::<"...
0x1800462e5  lea     r8, aLocaltaskAsTas; "localTask.As(&taskToWrap)"
0x1800462ec  lea     rcx, [rbp+pExceptionObject]; this
0x1800462f0  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800462f5  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800462fc  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180046300  call    _CxxThrowException_0
```
