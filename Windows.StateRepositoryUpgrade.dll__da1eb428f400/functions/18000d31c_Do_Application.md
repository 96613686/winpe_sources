# Do_Application

- ea: `0x18000d31c`
- end: `0x18000d544`
- name: `Do_Application`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000d0a0`

## callees

- `0x18000a3c0`
- `0x18000cc38`
- `0x18000ce60`
- `0x18000d31c`
- `0x18001b5a8`
- `0x18001c950`
- `0x18001cc04`
- `0x18001cc98`
- `0x18001cf88`
- `0x18001d0e8`
- `0x18002a08c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d475`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d475`

## string_xrefs

- `0x18000d4f6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18000d3bc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application.cpp`
- `0x18000d3a0`: `SELECT _ApplicationID, _Revision, _WorkId, Package, "Index", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId, ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, StartPage, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColor, InitialRotationPreference, ApplicationV`
- `0x18000d38e`: `SELECT _ApplicationID, _Revision, _WorkId, Package, "Index", ApplicationType, Flags, Subsystem, PackageRelativeApplicationId, ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, Entrypoint, StartPage, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBackgroundColor, InitialRotationPreference, ApplicationV`

## pseudocode

```c
__int64 __fastcall Do_Application(__int64 a1, StateRepository::StatementExecution *a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int Next; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  int v11; // eax
  StateRepository::Entity::Application *v12; // rcx
  struct StateRepository::Statement *v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18[58]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]
  __int64 v20; // [rsp+220h] [rbp+120h] BYREF
  __int64 v21; // [rsp+238h] [rbp+138h] BYREF

  v20 = a1;
  v5 = StateRepository::Entity::Application::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(a2);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 82;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)v5,
      (int)v14);
    return v5;
  }
  v5 = StateRepository::Entity::Application::ResetActivationByCentennialEntrypoint(a2);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 85;
    goto LABEL_3;
  }
  *a3 = 0;
  v21 = 0;
  v7 = StateRepository::StatementExecution::PrepareAndBindAndFind(
         a2,
         (struct StateRepository::Database *)"SELECT _ApplicationID, _Revision, _WorkId, Package, \"Index\", ApplicationT"
                                             "ype, Flags, Subsystem, PackageRelativeApplicationId, ApplicationUserModelId"
                                             ", DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x150"
                                             "Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, "
                                             "Activation, HostId, Executable, Entrypoint, StartPage, ResourceGroup, LockS"
                                             "creenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScreenBack"
                                             "groundColor, InitialRotationPreference, ApplicationViewMinWidth, AppListEnt"
                                             "ry, EditionId, VisualGroup, Parameters, CurrentDirectoryPath, _Dictionary F"
                                             "ROM Application WHERE _WorkId=0;",
         "SELECT _ApplicationID, _Revision, _WorkId, Package, \"Index\", ApplicationType, Flags, Subsystem, PackageRelati"
         "veApplicationId, ApplicationUserModelId, DisplayName, Description, Square150x150Logo, Square44x44Logo, Wide310x"
         "150Logo, Square310x310Logo, Square71x71Logo, ForegroundText, BackgroundColor, Activation, HostId, Executable, E"
         "ntrypoint, StartPage, ResourceGroup, LockScreenNotification, LockScreenBadgeLogo, SplashScreenImage, SplashScre"
         "enBackgroundColor, InitialRotationPreference, ApplicationViewMinWidth, AppListEntry, EditionId, VisualGroup, Pa"
         "rameters, CurrentDirectoryPath, _Dictionary FROM Application WHERE (_WorkId=0 OR _WorkId=?);",
         (const char *)&v21,
         v14);
  v5 = v7;
  if ( v7 >= 0 )
  {
    StateRepository::Entity::Application::Application((StateRepository::Entity::Application *)v18);
    LOBYTE(v20) = 0;
    Next = StateRepository::Entity::Application::FindNext(
             (struct StateRepository::Statement *)&v21,
             (struct Application *)v18,
             (bool *)&v20);
    v5 = Next;
    if ( Next >= 0 )
    {
      while ( (_BYTE)v20 )
      {
        ++*a3;
        if ( *a3 == 100 * (*a3 / 100) )
          StateRepository_Service_UpdateStatus(1);
        v17 = 0;
        v11 = StateRepository::Entity::Application::GenerateActivationIfNecessary(v18, a2, &v17);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x70F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
            (const char *)(unsigned int)v11,
            v15);
          v10 = v5;
          v9 = 100;
          goto LABEL_11;
        }
        if ( v17 )
        {
          Next = StateRepository::Entity::Application::UpdateActivationBy_PrimaryKey(v12, a2, v18[0], v17);
          v5 = Next;
          if ( Next < 0 )
          {
            v9 = 103;
            goto LABEL_10;
          }
        }
        Next = StateRepository::Entity::Application::FindNext(
                 (struct StateRepository::Statement *)&v21,
                 (struct Application *)v18,
                 (bool *)&v20);
        v5 = Next;
        if ( Next < 0 )
        {
          v9 = 105;
          goto LABEL_10;
        }
      }
      StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v18);
      v5 = 0;
    }
    else
    {
      v9 = 92;
LABEL_10:
      v10 = (unsigned int)Next;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
        (const char *)v10,
        v15);
      StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x404,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application.cpp",
      (const char *)(unsigned int)v7,
      v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)v5,
      v16);
  }
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v21);
  return v5;
}

```

## disassembly

```asm
0x18000d31c  mov     [rsp-8+arg_8], rbx
0x18000d321  mov     [rsp-8+arg_0], rcx
0x18000d326  push    rbp
0x18000d327  push    rsi
0x18000d328  push    rdi
0x18000d329  lea     rbp, [rsp-100h]
0x18000d331  sub     rsp, 200h
0x18000d338  mov     rcx, rdx
0x18000d33b  mov     rsi, r8
0x18000d33e  mov     rdi, rdx
0x18000d341  call    ?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@Application@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::Application::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d346  mov     ebx, eax
0x18000d348  test    eax, eax
0x18000d34a  jns     short loc_18000D36C
0x18000d34c  mov     edx, 52h ; 'R'; void *
0x18000d351  mov     rcx, [rbp+118h]; this
0x18000d358  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d35f  mov     r9d, ebx; char *
0x18000d362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d367  jmp     loc_18000D52F
0x18000d36c  mov     rcx, rdi
0x18000d36f  call    ?ResetActivationByCentennialEntrypoint@Application@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::Application::ResetActivationByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d374  mov     ebx, eax
0x18000d376  test    eax, eax
0x18000d378  jns     short loc_18000D381
0x18000d37a  mov     edx, 55h ; 'U'
0x18000d37f  jmp     short loc_18000D351
0x18000d381  lea     r9, [rbp+110h+arg_18]; char *
0x18000d388  mov     dword ptr [rsi], 0
0x18000d38e  lea     r8, aSelectApplicat_2; "SELECT _ApplicationID, _Revision, _Work"...
0x18000d395  mov     [rbp+110h+arg_18], 0
0x18000d3a0  lea     rdx, aSelectApplicat_3; "SELECT _ApplicationID, _Revision, _Work"...
0x18000d3a7  mov     rcx, rdi; this
0x18000d3aa  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x18000d3af  mov     ebx, eax
0x18000d3b1  test    eax, eax
0x18000d3b3  jns     short loc_18000D3F0
0x18000d3b5  mov     rcx, [rbp+118h]; this
0x18000d3bc  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appmodel\\staterepositor"...
0x18000d3c3  mov     r9d, eax; char *
0x18000d3c6  mov     edx, 404h; void *
0x18000d3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3d0  mov     rcx, [rbp+118h]; this
0x18000d3d7  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d3de  mov     r9d, ebx; char *
0x18000d3e1  mov     edx, 59h ; 'Y'; void *
0x18000d3e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3eb  jmp     loc_18000D523
0x18000d3f0  lea     rcx, [rsp+210h+var_1D0]; this
0x18000d3f5  call    ??0Application@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Application::Application(void)
0x18000d3fa  lea     r8, [rbp+110h+arg_0]; bool *
0x18000d401  mov     byte ptr [rbp+110h+arg_0], 0
0x18000d408  lea     rdx, [rsp+210h+var_1D0]; struct Application *
0x18000d40d  lea     rcx, [rbp+110h+arg_18]; struct StateRepository::Statement *
0x18000d414  call    ?FindNext@Application@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::Application::FindNext(StateRepository::Statement &,StateRepository::Entity::Application &,bool &)
0x18000d419  mov     ebx, eax
0x18000d41b  test    eax, eax
0x18000d41d  jns     short loc_18000D449
0x18000d41f  mov     edx, 5Ch ; '\'; void *
0x18000d424  mov     r9d, eax; char *
0x18000d427  mov     rcx, [rbp+118h]; this
0x18000d42e  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d43a  lea     rcx, [rsp+210h+var_1D0]; this
0x18000d43f  call    ??1Application@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Application::~Application(void)
0x18000d444  jmp     loc_18000D523
0x18000d449  cmp     byte ptr [rbp+110h+arg_0], 0
0x18000d450  jz      loc_18000D517
0x18000d456  inc     dword ptr [rsi]
0x18000d458  mov     eax, 51EB851Fh
0x18000d45d  imul    dword ptr [rsi]
0x18000d45f  sar     edx, 5
0x18000d462  mov     eax, edx
0x18000d464  shr     eax, 1Fh
0x18000d467  add     edx, eax
0x18000d469  imul    eax, edx, 64h ; 'd'
0x18000d46c  cmp     [rsi], eax
0x18000d46e  jnz     short loc_18000D47B
0x18000d470  mov     ecx, 1
0x18000d475  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d47b  lea     r8, [rsp+210h+var_1E0]
0x18000d480  mov     [rsp+210h+var_1E0], 0
0x18000d489  mov     rdx, rdi
0x18000d48c  lea     rcx, [rsp+210h+var_1D0]
0x18000d491  call    ?GenerateActivationIfNecessary@Application@Entity@StateRepository@@QEAAJAEAVDatabase@3@AEA_JPEAVActivation@23@W4ExecutionFlags@3@@Z; StateRepository::Entity::Application::GenerateActivationIfNecessary(StateRepository::Database &,__int64 &,StateRepository::Entity::Activation *,StateRepository::ExecutionFlags)
0x18000d496  mov     ebx, eax
0x18000d498  test    eax, eax
0x18000d49a  js      short loc_18000D4EF
0x18000d49c  mov     r9, [rsp+210h+var_1E0]; __int64
0x18000d4a1  test    r9, r9
0x18000d4a4  jz      short loc_18000D4B9
0x18000d4a6  mov     r8, [rsp+210h+var_1D0]; __int64
0x18000d4ab  mov     rdx, rdi; struct StateRepository::Database *
0x18000d4ae  call    ?UpdateActivationBy_PrimaryKey@Application@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z; StateRepository::Entity::Application::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)
0x18000d4b3  mov     ebx, eax
0x18000d4b5  test    eax, eax
0x18000d4b7  js      short loc_18000D4E5
0x18000d4b9  lea     r8, [rbp+110h+arg_0]; bool *
0x18000d4c0  lea     rdx, [rsp+210h+var_1D0]; struct Application *
0x18000d4c5  lea     rcx, [rbp+110h+arg_18]; struct StateRepository::Statement *
0x18000d4cc  call    ?FindNext@Application@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::Application::FindNext(StateRepository::Statement &,StateRepository::Entity::Application &,bool &)
0x18000d4d1  mov     ebx, eax
0x18000d4d3  test    eax, eax
0x18000d4d5  jns     loc_18000D449
0x18000d4db  mov     edx, 69h ; 'i'
0x18000d4e0  jmp     loc_18000D424
0x18000d4e5  mov     edx, 67h ; 'g'
0x18000d4ea  jmp     loc_18000D424
0x18000d4ef  mov     rcx, [rbp+118h]; this
0x18000d4f6  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18000d4fd  mov     r9d, ebx; char *
0x18000d500  mov     edx, 70Fh; void *
0x18000d505  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d50a  mov     r9d, ebx
0x18000d50d  mov     edx, 64h ; 'd'
0x18000d512  jmp     loc_18000D427
0x18000d517  lea     rcx, [rsp+210h+var_1D0]; this
0x18000d51c  call    ??1Application@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Application::~Application(void)
0x18000d521  xor     ebx, ebx
0x18000d523  lea     rcx, [rbp+110h+arg_18]; this
0x18000d52a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000d52f  mov     eax, ebx
0x18000d531  mov     rbx, [rsp+210h+arg_8]
0x18000d539  add     rsp, 200h
0x18000d540  pop     rdi
0x18000d541  pop     rsi
0x18000d542  pop     rbp
0x18000d543  retn
```
