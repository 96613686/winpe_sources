# Do_FullTrustProcess

- ea: `0x1800141f0`
- end: `0x18001433f`
- name: `Do_FullTrustProcess`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180014350`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x18000cd9c`
- `0x18000cf70`
- `0x1800141f0`
- `0x180014504`
- `0x18001b5a8`
- `0x18001d8b0`
- `0x18001e51c`

## import_xrefs

- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x1800142c4`
- `Windows.StateRepository!StateRepository_Service_UpdateStatus` at `0x1800142c4`

## pseudocode

```c
__int64 __fastcall Do_FullTrustProcess(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int Next; // eax
  __int64 v8; // rdx
  int updated; // eax
  __int64 *v11; // [rsp+20h] [rbp-E0h]
  _BYTE v12[288]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]
  __int64 v14; // [rsp+160h] [rbp+60h] BYREF
  __int64 v15; // [rsp+170h] [rbp+70h] BYREF

  v14 = a1;
  *a3 = 0;
  v11 = &v15;
  v15 = 0;
  v5 = StateRepository::Entity::ApplicationExtension::FindByCategoryAndNotFlagsOrNotFlags(a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    StateRepository::Entity::ApplicationExtension::ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v12);
    LOBYTE(v14) = 0;
    Next = StateRepository::Entity::ApplicationExtension::FindNext(
             (struct StateRepository::Statement *)&v15,
             (struct StateRepository::Entity::ApplicationExtension *)v12,
             (bool *)&v14);
    v6 = Next;
    if ( Next >= 0 )
    {
      while ( (_BYTE)v14 )
      {
        ++*a3;
        if ( *a3 == 100 * (*a3 / 100) )
          StateRepository_Service_UpdateStatus(1);
        updated = UpdateApplicationExtension(a2, v12);
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fu"
                          "lltrustprocess.cpp",
            (const char *)(unsigned int)updated,
            (int)v11);
        Next = StateRepository::Entity::ApplicationExtension::FindNext(
                 (struct StateRepository::Statement *)&v15,
                 (struct StateRepository::Entity::ApplicationExtension *)v12,
                 (bool *)&v14);
        v6 = Next;
        if ( Next < 0 )
        {
          v8 = 80;
          goto LABEL_5;
        }
      }
      StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v12);
      v6 = 0;
    }
    else
    {
      v8 = 72;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fulltrustprocess.cpp",
        (const char *)(unsigned int)Next,
        (int)v11);
      StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\lib\\migrator-staterepository.activation.fulltrustprocess.cpp",
      (const char *)(unsigned int)v5,
      (int)&v15);
  }
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
  return v6;
}

```

## disassembly

```asm
0x1800141f0  mov     [rsp-8+arg_8], rbx
0x1800141f5  mov     [rsp-8+arg_0], rcx
0x1800141fa  push    rbp
0x1800141fb  push    rsi
0x1800141fc  push    rdi
0x1800141fd  lea     rbp, [rsp-40h]
0x180014202  sub     rsp, 140h
0x180014209  lea     rax, [rbp+50h+arg_10]
0x18001420d  mov     dword ptr [r8], 0
0x180014214  mov     rcx, rdx
0x180014217  mov     qword ptr [rsp+150h+var_130], rax; int
0x18001421c  mov     rdi, r8
0x18001421f  mov     [rbp+50h+arg_10], 0
0x180014227  mov     rsi, rdx
0x18001422a  call    ?FindByCategoryAndNotFlagsOrNotFlags@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGW4ApplicationExtensionFlags@3@2AEAVStatement@3@@Z; StateRepository::Entity::ApplicationExtension::FindByCategoryAndNotFlagsOrNotFlags(StateRepository::Database &,ushort const *,StateRepository::ApplicationExtensionFlags,StateRepository::ApplicationExtensionFlags,StateRepository::Statement &)
0x18001422f  mov     ebx, eax
0x180014231  test    eax, eax
0x180014233  jns     short loc_180014252
0x180014235  mov     rcx, [rbp+58h]; this
0x180014239  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x180014240  mov     r9d, eax; char *
0x180014243  mov     edx, 45h ; 'E'; void *
0x180014248  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001424d  jmp     loc_180014321
0x180014252  lea     rcx, [rsp+150h+var_120]; this
0x180014257  call    ??0ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::ApplicationExtension(void)
0x18001425c  lea     r8, [rbp+50h+arg_0]; bool *
0x180014260  mov     byte ptr [rbp+50h+arg_0], 0
0x180014264  lea     rdx, [rsp+150h+var_120]; struct StateRepository::Entity::ApplicationExtension *
0x180014269  lea     rcx, [rbp+50h+arg_10]; struct StateRepository::Statement *
0x18001426d  call    ?FindNext@ApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::ApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::ApplicationExtension &,bool &)
0x180014272  mov     ebx, eax
0x180014274  test    eax, eax
0x180014276  jns     short loc_18001429F
0x180014278  mov     edx, 48h ; 'H'; void *
0x18001427d  mov     rcx, [rbp+58h]; this
0x180014281  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x180014288  mov     r9d, eax; char *
0x18001428b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014290  lea     rcx, [rsp+150h+var_120]; this
0x180014295  call    ??1ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::~ApplicationExtension(void)
0x18001429a  jmp     loc_180014321
0x18001429f  cmp     byte ptr [rbp+50h+arg_0], 0
0x1800142a3  jz      short loc_180014315
0x1800142a5  inc     dword ptr [rdi]
0x1800142a7  mov     eax, 51EB851Fh
0x1800142ac  imul    dword ptr [rdi]
0x1800142ae  sar     edx, 5
0x1800142b1  mov     eax, edx
0x1800142b3  shr     eax, 1Fh
0x1800142b6  add     edx, eax
0x1800142b8  imul    eax, edx, 64h ; 'd'
0x1800142bb  cmp     [rdi], eax
0x1800142bd  jnz     short loc_1800142CA
0x1800142bf  mov     ecx, 1
0x1800142c4  call    cs:__imp_StateRepository_Service_UpdateStatus
0x1800142ca  lea     rdx, [rsp+150h+var_120]
0x1800142cf  mov     rcx, rsi
0x1800142d2  call    UpdateApplicationExtension
0x1800142d7  test    eax, eax
0x1800142d9  jns     short loc_1800142F3
0x1800142db  mov     rcx, [rbp+58h]; this
0x1800142df  lea     r8, aOnecoreBaseApp_21; "onecore\\base\\appmodel\\staterepositor"...
0x1800142e6  mov     r9d, eax; char *
0x1800142e9  mov     edx, 4Fh ; 'O'; void *
0x1800142ee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800142f3  lea     r8, [rbp+50h+arg_0]; bool *
0x1800142f7  lea     rdx, [rsp+150h+var_120]; struct StateRepository::Entity::ApplicationExtension *
0x1800142fc  lea     rcx, [rbp+50h+arg_10]; struct StateRepository::Statement *
0x180014300  call    ?FindNext@ApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::ApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::ApplicationExtension &,bool &)
0x180014305  mov     ebx, eax
0x180014307  test    eax, eax
0x180014309  jns     short loc_18001429F
0x18001430b  mov     edx, 50h ; 'P'
0x180014310  jmp     loc_18001427D
0x180014315  lea     rcx, [rsp+150h+var_120]; this
0x18001431a  call    ??1ApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::ApplicationExtension::~ApplicationExtension(void)
0x18001431f  xor     ebx, ebx
0x180014321  lea     rcx, [rbp+50h+arg_10]; this
0x180014325  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001432a  mov     eax, ebx
0x18001432c  mov     rbx, [rsp+150h+arg_8]
0x180014334  add     rsp, 140h
0x18001433b  pop     rdi
0x18001433c  pop     rsi
0x18001433d  pop     rbp
0x18001433e  retn
```
