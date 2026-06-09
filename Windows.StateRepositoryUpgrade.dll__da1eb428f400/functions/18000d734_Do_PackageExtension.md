# Do_PackageExtension

- ea: `0x18000d734`
- end: `0x18000d99b`
- name: `Do_PackageExtension`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18000d0a0`

## callees

- `0x18000a3c0`
- `0x18000d008`
- `0x18000d734`
- `0x18001b5a8`
- `0x18001e958`
- `0x18001ebe0`
- `0x18001ec74`
- `0x18001ed34`
- `0x18001ee94`
- `0x18002a08c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d8d8`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x18000d8d8`

## string_xrefs

- `0x18000d950`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18000d7c5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension.cpp`
- `0x18000d7ac`: `SELECT _PackageExtensionID, _Revision, _WorkId, Package, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM PackageExtension WHERE _WorkId=0;`
- `0x18000d79d`: `SELECT _PackageExtensionID, _Revision, _WorkId, Package, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM PackageExtension WHERE (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall Do_PackageExtension(__int64 a1, StateRepository::StatementExecution *a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int Next; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  int v11; // eax
  StateRepository::Entity::PackageExtension *v12; // rcx
  struct StateRepository::Statement *v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+50h] [rbp-B0h]
  int v20; // [rsp+60h] [rbp-A0h]
  __int64 v21; // [rsp+68h] [rbp-98h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  __int128 v23; // [rsp+80h] [rbp-80h]
  __int128 v24; // [rsp+90h] [rbp-70h]
  __int128 v25; // [rsp+A0h] [rbp-60h]
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int128 v27; // [rsp+C0h] [rbp-40h]
  int v28; // [rsp+D0h] [rbp-30h]
  __int64 v29; // [rsp+D8h] [rbp-28h]
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h]
  __int128 v32; // [rsp+100h] [rbp+0h]
  __int128 v33; // [rsp+110h] [rbp+10h]
  __int128 v34; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  __int64 v36; // [rsp+150h] [rbp+50h] BYREF
  __int64 v37; // [rsp+168h] [rbp+68h] BYREF

  v36 = a1;
  v5 = StateRepository::Entity::PackageExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(a2);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 150;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)v5,
      (int)v14);
    return v5;
  }
  v5 = StateRepository::Entity::PackageExtension::ResetActivationByCentennialEntrypoint(a2);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = 153;
    goto LABEL_3;
  }
  *a3 = 0;
  v37 = 0;
  v7 = StateRepository::StatementExecution::PrepareAndBindAndFind(
         a2,
         (struct StateRepository::Database *)"SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Categor"
                                             "y, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flag"
                                             "s, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM Pa"
                                             "ckageExtension WHERE _WorkId=0;",
         "SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Category, Activation, HostId, Executable, E"
         "ntrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM"
         " PackageExtension WHERE (_WorkId=0 OR _WorkId=?);",
         (const char *)&v37,
         v14);
  v5 = v7;
  if ( v7 >= 0 )
  {
    v18[0] = 0;
    v19 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v18[1] = 0;
    v20 = 0;
    v21 = 0;
    v28 = 0;
    v29 = 0;
    LOBYTE(v36) = 0;
    Next = StateRepository::Entity::PackageExtension::FindNext(
             (struct StateRepository::Statement *)&v37,
             (struct StateRepository::Entity::PackageExtension *)v18,
             (bool *)&v36);
    v5 = Next;
    if ( Next >= 0 )
    {
      while ( (_BYTE)v36 )
      {
        ++*a3;
        if ( *a3 == 100 * (*a3 / 100) )
          StateRepository_Service_UpdateStatus(1);
        v17 = 0;
        v11 = StateRepository::Entity::PackageExtension::GenerateActivationIfNecessary(v18, a2, &v17);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x11A,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
            (const char *)(unsigned int)v11,
            v15);
          v10 = v5;
          v9 = 168;
          goto LABEL_11;
        }
        if ( v17 )
        {
          Next = StateRepository::Entity::PackageExtension::UpdateActivationBy_PrimaryKey(v12, a2, v18[0], v17);
          v5 = Next;
          if ( Next < 0 )
          {
            v9 = 171;
            goto LABEL_10;
          }
        }
        Next = StateRepository::Entity::PackageExtension::FindNext(
                 (struct StateRepository::Statement *)&v37,
                 (struct StateRepository::Entity::PackageExtension *)v18,
                 (bool *)&v36);
        v5 = Next;
        if ( Next < 0 )
        {
          v9 = 173;
          goto LABEL_10;
        }
      }
      StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)v18);
      v5 = 0;
    }
    else
    {
      v9 = 160;
LABEL_10:
      v10 = (unsigned int)Next;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
        (const char *)v10,
        v15);
      StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension.cpp",
      (const char *)(unsigned int)v7,
      v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-deployment.activation.cpp",
      (const char *)v5,
      v16);
  }
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v37);
  return v5;
}

```

## disassembly

```asm
0x18000d734  mov     [rsp-8+arg_8], rbx
0x18000d739  mov     [rsp-8+arg_0], rcx
0x18000d73e  push    rbp
0x18000d73f  push    rsi
0x18000d740  push    rdi
0x18000d741  lea     rbp, [rsp-30h]
0x18000d746  sub     rsp, 130h
0x18000d74d  mov     rcx, rdx
0x18000d750  mov     rsi, r8
0x18000d753  mov     rdi, rdx
0x18000d756  call    ?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::PackageExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d75b  mov     ebx, eax
0x18000d75d  test    eax, eax
0x18000d75f  jns     short loc_18000D77E
0x18000d761  mov     edx, 96h; void *
0x18000d766  mov     rcx, [rbp+48h]; this
0x18000d76a  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d771  mov     r9d, ebx; char *
0x18000d774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d779  jmp     loc_18000D986
0x18000d77e  mov     rcx, rdi
0x18000d781  call    ?ResetActivationByCentennialEntrypoint@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::PackageExtension::ResetActivationByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18000d786  mov     ebx, eax
0x18000d788  test    eax, eax
0x18000d78a  jns     short loc_18000D793
0x18000d78c  mov     edx, 99h
0x18000d791  jmp     short loc_18000D766
0x18000d793  lea     r9, [rbp+40h+arg_18]; char *
0x18000d797  mov     dword ptr [rsi], 0
0x18000d79d  lea     r8, aSelectPackagee_0; "SELECT _PackageExtensionID, _Revision, "...
0x18000d7a4  mov     [rbp+40h+arg_18], 0
0x18000d7ac  lea     rdx, aSelectPackagee; "SELECT _PackageExtensionID, _Revision, "...
0x18000d7b3  mov     rcx, rdi; this
0x18000d7b6  call    ?PrepareAndBindAndFind@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFind(StateRepository::Database &,char const *,char const *,StateRepository::Statement &)
0x18000d7bb  mov     ebx, eax
0x18000d7bd  test    eax, eax
0x18000d7bf  jns     short loc_18000D7F6
0x18000d7c1  mov     rcx, [rbp+48h]; this
0x18000d7c5  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\staterepositor"...
0x18000d7cc  mov     r9d, eax; char *
0x18000d7cf  mov     edx, 2D6h; void *
0x18000d7d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7d9  mov     rcx, [rbp+48h]; this
0x18000d7dd  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d7e4  mov     r9d, ebx; char *
0x18000d7e7  mov     edx, 9Dh; void *
0x18000d7ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7f1  jmp     loc_18000D97D
0x18000d7f6  xorps   xmm0, xmm0
0x18000d7f9  mov     [rsp+140h+var_100], 0
0x18000d802  xorps   xmm1, xmm1
0x18000d805  movdqa  [rsp+140h+var_F0], xmm0
0x18000d80b  lea     r8, [rbp+40h+arg_0]; bool *
0x18000d80f  movdqa  [rsp+140h+var_D0], xmm0
0x18000d815  lea     rdx, [rsp+140h+var_100]; struct StateRepository::Entity::PackageExtension *
0x18000d81a  movdqa  [rbp+40h+var_C0], xmm1
0x18000d81f  lea     rcx, [rbp+40h+arg_18]; struct StateRepository::Statement *
0x18000d823  movdqa  [rbp+40h+var_B0], xmm0
0x18000d828  movdqa  [rbp+40h+var_A0], xmm1
0x18000d82d  movdqa  [rbp+40h+var_90], xmm0
0x18000d832  movdqa  [rbp+40h+var_80], xmm1
0x18000d837  movdqa  [rbp+40h+var_60], xmm0
0x18000d83c  movdqa  [rbp+40h+var_50], xmm1
0x18000d841  movdqa  [rbp+40h+var_40], xmm0
0x18000d846  movdqa  [rbp+40h+var_30], xmm1
0x18000d84b  movdqa  [rbp+40h+var_20], xmm0
0x18000d850  mov     [rsp+140h+var_F8], 0
0x18000d859  mov     [rsp+140h+var_E0], 0
0x18000d861  mov     [rsp+140h+var_D8], 0
0x18000d86a  mov     [rbp+40h+var_70], 0
0x18000d871  mov     [rbp+40h+var_68], 0
0x18000d879  mov     byte ptr [rbp+40h+arg_0], 0
0x18000d87d  call    ?FindNext@PackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageExtension &,bool &)
0x18000d882  mov     ebx, eax
0x18000d884  test    eax, eax
0x18000d886  jns     short loc_18000D8AF
0x18000d888  mov     edx, 0A0h; void *
0x18000d88d  mov     r9d, eax; char *
0x18000d890  mov     rcx, [rbp+48h]; this
0x18000d894  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x18000d89b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8a0  lea     rcx, [rsp+140h+var_100]; this
0x18000d8a5  call    ??1PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::~PackageExtension(void)
0x18000d8aa  jmp     loc_18000D97D
0x18000d8af  cmp     byte ptr [rbp+40h+arg_0], 0
0x18000d8b3  jz      loc_18000D971
0x18000d8b9  inc     dword ptr [rsi]
0x18000d8bb  mov     eax, 51EB851Fh
0x18000d8c0  imul    dword ptr [rsi]
0x18000d8c2  sar     edx, 5
0x18000d8c5  mov     eax, edx
0x18000d8c7  shr     eax, 1Fh
0x18000d8ca  add     edx, eax
0x18000d8cc  imul    eax, edx, 64h ; 'd'
0x18000d8cf  cmp     [rsi], eax
0x18000d8d1  jnz     short loc_18000D8DE
0x18000d8d3  mov     ecx, 1
0x18000d8d8  call    cs:__imp_StateRepository_Service_UpdateStatus
0x18000d8de  lea     r8, [rsp+140h+var_110]
0x18000d8e3  mov     [rsp+140h+var_110], 0
0x18000d8ec  mov     rdx, rdi
0x18000d8ef  lea     rcx, [rsp+140h+var_100]
0x18000d8f4  call    ?GenerateActivationIfNecessary@PackageExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@AEA_JPEAVActivation@23@W4ExecutionFlags@3@@Z; StateRepository::Entity::PackageExtension::GenerateActivationIfNecessary(StateRepository::Database &,__int64 &,StateRepository::Entity::Activation *,StateRepository::ExecutionFlags)
0x18000d8f9  mov     ebx, eax
0x18000d8fb  test    eax, eax
0x18000d8fd  js      short loc_18000D94C
0x18000d8ff  mov     r9, [rsp+140h+var_110]; __int64
0x18000d904  test    r9, r9
0x18000d907  jz      short loc_18000D91C
0x18000d909  mov     r8, [rsp+140h+var_100]; __int64
0x18000d90e  mov     rdx, rdi; struct StateRepository::Database *
0x18000d911  call    ?UpdateActivationBy_PrimaryKey@PackageExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z; StateRepository::Entity::PackageExtension::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)
0x18000d916  mov     ebx, eax
0x18000d918  test    eax, eax
0x18000d91a  js      short loc_18000D942
0x18000d91c  lea     r8, [rbp+40h+arg_0]; bool *
0x18000d920  lea     rdx, [rsp+140h+var_100]; struct StateRepository::Entity::PackageExtension *
0x18000d925  lea     rcx, [rbp+40h+arg_18]; struct StateRepository::Statement *
0x18000d929  call    ?FindNext@PackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageExtension &,bool &)
0x18000d92e  mov     ebx, eax
0x18000d930  test    eax, eax
0x18000d932  jns     loc_18000D8AF
0x18000d938  mov     edx, 0ADh
0x18000d93d  jmp     loc_18000D88D
0x18000d942  mov     edx, 0ABh
0x18000d947  jmp     loc_18000D88D
0x18000d94c  mov     rcx, [rbp+48h]; this
0x18000d950  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18000d957  mov     r9d, ebx; char *
0x18000d95a  mov     edx, 11Ah; void *
0x18000d95f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d964  mov     r9d, ebx
0x18000d967  mov     edx, 0A8h
0x18000d96c  jmp     loc_18000D890
0x18000d971  lea     rcx, [rsp+140h+var_100]; this
0x18000d976  call    ??1PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::~PackageExtension(void)
0x18000d97b  xor     ebx, ebx
0x18000d97d  lea     rcx, [rbp+40h+arg_18]; this
0x18000d981  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000d986  mov     eax, ebx
0x18000d988  mov     rbx, [rsp+140h+arg_8]
0x18000d990  add     rsp, 130h
0x18000d997  pop     rdi
0x18000d998  pop     rsi
0x18000d999  pop     rbp
0x18000d99a  retn
```
