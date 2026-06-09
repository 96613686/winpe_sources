# Do_ApplicationExtension

- ea: `0x18000d54c`
- end: `0x18000d72c`
- name: `Do_ApplicationExtension`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000d0a0`

## callees

- `0x18000a3c0`
- `0x18000cd9c`
- `0x18000cf70`
- `0x18000d54c`
- `0x18001b5a8`
- `0x18001dc08`
- `0x18001de14`
- `0x18001dea8`
- `0x18001df68`
- `0x18001e51c`
- `0x18002a08c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d684`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d684`

## string_xrefs

- `0x18000d5dd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18000d5c4`: `SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _WorkId=0;`
- `0x18000d5b5`: `SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall Do_ApplicationExtension(__int64 a1, StateRepository::StatementExecution *a2, _DWORD *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int Next; // eax
  __int64 v9; // rdx
  StateRepository::Entity::ApplicationExtension *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13[36]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  __int64 v15; // [rsp+160h] [rbp+60h] BYREF
  __int64 v16; // [rsp+178h] [rbp+78h] BYREF

  v15 = a1;
  v5 = StateRepository::Entity::ApplicationExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(a2);
  if ( v5 < 0 )
  {
    v6 = 116;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)(unsigned int)v5,
      v12);
    return (unsigned int)v5;
  }
  v5 = StateRepository::Entity::ApplicationExtension::ResetActivation(a2);
  if ( v5 < 0 )
  {
    v6 = 119;
    goto LABEL_3;
  }
  *a3 = 0;
  v16 = 0;
  v7 = StateRepository::StatementExecution::PrepareAndBindAndFind(
         a2,
         (struct StateRepository::Database *)"SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, \"Index\","
                                             " Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPa"
                                             "ge, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, "
                                             "_LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _WorkId=0;",
         "SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, \"Index\", Category, Activation, HostId, Execu"
         "table, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, I"
         "d, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE (_WorkId=0 OR _WorkId=?);",
         (const char *)&v16,
         (struct StateRepository::Statement *)v12);
  v5 = v7;
  if ( v7 >= 0 )
  {
    StateRepository::Entity::ApplicationExtension::ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v13);
    LOBYTE(v15) = 0;
    Next = StateRepository::Entity::ApplicationExtension::FindNext(
             (struct StateRepository::Statement *)&v16,
             (struct StateRepository::Entity::ApplicationExtension *)v13,
             (bool *)&v15);
    v5 = Next;
    if ( Next >= 0 )
    {
      while ( (_BYTE)v15 )
      {
        ++*a3;
        if ( *a3 == 100 * (*a3 / 100) )
          StateRepository_Service_UpdateStatus(1);
        v12 = 0;
        Next = StateRepository::Entity::ApplicationExtension::GenerateActivationIfNecessary(v13, a2, &v12);
        v5 = Next;
        if ( Next < 0 )
        {
          v9 = 134;
          goto LABEL_10;
        }
        if ( v12 )
        {
          Next = StateRepository::Entity::ApplicationExtension::UpdateActivationBy_PrimaryKey(v10, a2, v13[0], v12);
          v5 = Next;
          if ( Next < 0 )
          {
            v9 = 137;
            goto LABEL_10;
          }
        }
        Next = StateRepository::Entity::ApplicationExtension::FindNext(
                 (struct StateRepository::Statement *)&v16,
                 (struct StateRepository::Entity::ApplicationExtension *)v13,
                 (bool *)&v15);
        v5 = Next;
        if ( Next < 0 )
        {
          v9 = 139;
          goto LABEL_10;
        }
      }
      StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v13);
      v5 = 0;
    }
    else
    {
      v9 = 126;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
        (const char *)(unsigned int)Next,
        v12);
      StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
      (const char *)(unsigned int)v7,
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)(unsigned int)v5,
      v12);
  }
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000d54c  mov     [rsp-8+arg_8], rbx
0x18000d551  mov     [rsp-8+arg_0], rcx
0x18000d556  push    rbp
0x18000d557  push    rsi
0x18000d558  push    rdi
0x18000d559  lea     rbp, [rsp-40h]
0x18000d55e  sub     rsp, 140h
0x18000d565  mov     rcx, rdx
0x18000d568  mov     rsi, r8
0x18000d56b  mov     rdi, rdx
0x18000d56e  call    ?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::ApplicationExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d573  mov     ebx, eax
0x18000d575  test    eax, eax
0x18000d577  jns     short loc_18000D596
0x18000d579  mov     edx, 74h ; 't'; void *
0x18000d57e  mov     rcx, [rbp+58h]; this
0x18000d582  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d589  mov     r9d, ebx; char *
0x18000d58c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d591  jmp     loc_18000D717
0x18000d596  mov     rcx, rdi
0x18000d599  call    ?ResetActivation@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::ApplicationExtension::ResetActivation(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d59e  mov     ebx, eax
0x18000d5a0  test    eax, eax
0x18000d5a2  jns     short loc_18000D5AB
0x18000d5a4  mov     edx, 77h ; 'w'
0x18000d5a9  jmp     short loc_18000D57E
0x18000d5ab  lea     r9, [rbp+50h+arg_18]; char *
0x18000d5af  mov     dword ptr [rsi], 0
0x18000d5b5  lea     r8, aSelectApplicat; "SELECT _ApplicationExtensionID, _Revisi"...
0x18000d5bc  mov     [rbp+50h+arg_18], 0
0x18000d5c4  lea     rdx, aSelectApplicat_1; "SELECT _ApplicationExtensionID, _Revisi"...
0x18000d5cb  mov     rcx, rdi; this
0x18000d5ce  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x18000d5d3  mov     ebx, eax
0x18000d5d5  test    eax, eax
0x18000d5d7  jns     short loc_18000D60E
0x18000d5d9  mov     rcx, [rbp+58h]; this
0x18000d5dd  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18000d5e4  mov     r9d, eax; char *
0x18000d5e7  mov     edx, 33Dh; void *
0x18000d5ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5f1  mov     rcx, [rbp+58h]; this
0x18000d5f5  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d5fc  mov     r9d, ebx; char *
0x18000d5ff  mov     edx, 7Bh ; '{'; void *
0x18000d604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d609  jmp     loc_18000D70E
0x18000d60e  lea     rcx, [rsp+150h+var_120]; this
0x18000d613  call    ??0ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::ApplicationExtension(void)
0x18000d618  lea     r8, [rbp+50h+arg_0]; bool *
0x18000d61c  mov     byte ptr [rbp+50h+arg_0], 0
0x18000d620  lea     rdx, [rsp+150h+var_120]; struct StateRepository::Entity::ApplicationExtension *
0x18000d625  lea     rcx, [rbp+50h+arg_18]; struct StateRepository::Statement *
0x18000d629  call    ?FindNext@ApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::ApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::ApplicationExtension &,bool &)
0x18000d62e  mov     ebx, eax
0x18000d630  test    eax, eax
0x18000d632  jns     short loc_18000D65B
0x18000d634  mov     edx, 7Eh ; '~'; void *
0x18000d639  mov     rcx, [rbp+58h]; this
0x18000d63d  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d644  mov     r9d, eax; char *
0x18000d647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d64c  lea     rcx, [rsp+150h+var_120]; this
0x18000d651  call    ??1ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::~ApplicationExtension(void)
0x18000d656  jmp     loc_18000D70E
0x18000d65b  cmp     byte ptr [rbp+50h+arg_0], 0
0x18000d65f  jz      loc_18000D702
0x18000d665  inc     dword ptr [rsi]
0x18000d667  mov     eax, 51EB851Fh
0x18000d66c  imul    dword ptr [rsi]
0x18000d66e  sar     edx, 5
0x18000d671  mov     eax, edx
0x18000d673  shr     eax, 1Fh
0x18000d676  add     edx, eax
0x18000d678  imul    eax, edx, 64h ; 'd'
0x18000d67b  cmp     [rsi], eax
0x18000d67d  jnz     short loc_18000D68A
0x18000d67f  mov     ecx, 1
0x18000d684  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d68a  lea     r8, [rsp+150h+var_130]
0x18000d68f  mov     [rsp+150h+var_130], 0
0x18000d698  mov     rdx, rdi
0x18000d69b  lea     rcx, [rsp+150h+var_120]
0x18000d6a0  call    ?GenerateActivationIfNecessary@ApplicationExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@AEA_JW4ExecutionFlags@3@@Z; StateRepository::Entity::ApplicationExtension::GenerateActivationIfNecessary(StateRepository::Database &,__int64 &,StateRepository::ExecutionFlags)
0x18000d6a5  mov     ebx, eax
0x18000d6a7  test    eax, eax
0x18000d6a9  js      short loc_18000D6F8
0x18000d6ab  mov     r9, [rsp+150h+var_130]; __int64
0x18000d6b0  test    r9, r9
0x18000d6b3  jz      short loc_18000D6C8
0x18000d6b5  mov     r8, [rsp+150h+var_120]; __int64
0x18000d6ba  mov     rdx, rdi; struct StateRepository::Database *
0x18000d6bd  call    ?UpdateActivationBy_PrimaryKey@ApplicationExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z; StateRepository::Entity::ApplicationExtension::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)
0x18000d6c2  mov     ebx, eax
0x18000d6c4  test    eax, eax
0x18000d6c6  js      short loc_18000D6EE
0x18000d6c8  lea     r8, [rbp+50h+arg_0]; bool *
0x18000d6cc  lea     rdx, [rsp+150h+var_120]; struct StateRepository::Entity::ApplicationExtension *
0x18000d6d1  lea     rcx, [rbp+50h+arg_18]; struct StateRepository::Statement *
0x18000d6d5  call    ?FindNext@ApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::ApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::ApplicationExtension &,bool &)
0x18000d6da  mov     ebx, eax
0x18000d6dc  test    eax, eax
0x18000d6de  jns     loc_18000D65B
0x18000d6e4  mov     edx, 8Bh
0x18000d6e9  jmp     loc_18000D639
0x18000d6ee  mov     edx, 89h
0x18000d6f3  jmp     loc_18000D639
0x18000d6f8  mov     edx, 86h
0x18000d6fd  jmp     loc_18000D639
0x18000d702  lea     rcx, [rsp+150h+var_120]; this
0x18000d707  call    ??1ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::~ApplicationExtension(void)
0x18000d70c  xor     ebx, ebx
0x18000d70e  lea     rcx, [rbp+50h+arg_18]; this
0x18000d712  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000d717  mov     eax, ebx
0x18000d719  mov     rbx, [rsp+150h+arg_8]
0x18000d721  add     rsp, 140h
0x18000d728  pop     rdi
0x18000d729  pop     rsi
0x18000d72a  pop     rbp
0x18000d72b  retn
```
