# StateRepository::Entity::ApplicationExtension::GenerateActivationIfNecessary(StateRepository::Database &,__int64 &,StateRepository::Entity::Activation *,StateRepository::ExecutionFlags)

- ea: `0x18001d990`
- end: `0x18001dc00`
- name: `?GenerateActivationIfNecessary@ApplicationExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@AEA_JPEAVActivation@23@W4ExecutionFlags@3@@Z`
- size: `624`
- prototype: `int __high(struct StateRepository::Database *, __int64 *, struct StateRepository::Entity::Activation *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dc08`

## callees

- `0x1800042f4`
- `0x18000a3c0`
- `0x18000cc38`
- `0x18000ce60`
- `0x18000e0dc`
- `0x18000e194`
- `0x180018f78`
- `0x18001cb9c`
- `0x18001cbb8`
- `0x18001cbe8`
- `0x18001cd58`
- `0x18001d7e4`
- `0x18001d990`
- `0x18001dc98`
- `0x180021f50`
- `0x18002a3e4`

## string_xrefs

- `0x18001da49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001d9c9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001db65`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001db9b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::GenerateActivationIfNecessary(
        __int64 a1,
        struct StateRepository::Database *a2,
        _QWORD *a3,
        __int64 a4,
        bool a5)
{
  unsigned int InheritableActivationFields; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *v14; // r9
  int ExtensionActivationProperties; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  int v25; // [rsp+68h] [rbp-98h]
  int TrustLevel; // [rsp+6Ch] [rbp-94h]
  int RuntimeBehavior; // [rsp+70h] [rbp-90h]
  int AppLifecycleBehavior; // [rsp+74h] [rbp-8Ch]
  bool v29; // [rsp+79h] [rbp-87h]
  bool v30; // [rsp+7Ah] [rbp-86h]
  _QWORD v31[20]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[96]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v33[40]; // [rsp+180h] [rbp+80h] BYREF
  int v34; // [rsp+1A8h] [rbp+A8h]
  int v35; // [rsp+1ACh] [rbp+ACh]
  int v36[2]; // [rsp+1B0h] [rbp+B0h]
  __int64 v37; // [rsp+260h] [rbp+160h]
  __int64 v38; // [rsp+270h] [rbp+170h]
  __int64 v39; // [rsp+280h] [rbp+180h]
  __int64 v40; // [rsp+290h] [rbp+190h]
  __int64 v41; // [rsp+2A0h] [rbp+1A0h]
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+268h]

  *a3 = 0;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    if ( *(_QWORD *)(a1 + 56) )
      return 0;
    StateRepository::Entity::Application::Application((StateRepository::Entity::Application *)v33);
    v10 = *(_QWORD *)(a1 + 24);
    a5 = 0;
    InheritableActivationFields = StateRepository::Entity::Application::TryGetInheritableActivationFields(
                                    a2,
                                    v10,
                                    (struct Application *)v33,
                                    &a5);
    if ( (InheritableActivationFields & 0x80000000) == 0 )
    {
      if ( a5 )
      {
        memset_0(v19, 0, 0x60u);
        *(_QWORD *)v19 = *(_QWORD *)v36;
        v25 = v35;
        v20 = v37;
        v21 = v38;
        v22 = v39;
        v23 = v40;
        v24 = v41;
        TrustLevel = StateRepository::Entity::Application::GetTrustLevel(v33);
        RuntimeBehavior = StateRepository::Entity::Application::GetRuntimeBehavior(v33);
        AppLifecycleBehavior = StateRepository::Entity::Application::GetAppLifecycleBehavior(v33);
        v30 = (v34 & 0x40) != 0;
        v29 = (v34 & 8) != 0;
        memset_0(v31, 0, 0x60u);
        ApplicationExtensionPropertiesFromApplicationExtension(a1, v31);
        memset_0(v32, 0, sizeof(v32));
        ExtensionActivationProperties = StateRepository::Entity::ApplicationExtensionHelpers::GenerateExtensionActivationProperties(
                                          (StateRepository::Entity::ApplicationExtensionHelpers *)v19,
                                          (const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *)v31,
                                          (const struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *)v32,
                                          v14);
        InheritableActivationFields = ExtensionActivationProperties;
        if ( ExtensionActivationProperties >= 0 )
        {
          StateRepository::Entity::Activation::Activation((StateRepository::Entity::Activation *)v31);
          v16 = PopulateActivationFromActivationProperties(v32, v31);
          InheritableActivationFields = v16;
          if ( v16 >= 0 )
          {
            v16 = StateRepository::Entity::Activation::GetOrAddIfNotExist(v31, a2);
            InheritableActivationFields = v16;
            if ( v16 >= 0 )
            {
              v18 = v31[0];
              *(_QWORD *)(a1 + 56) = v31[0];
              *a3 = v18;
              StateRepository::Entity::Activation::~Activation((StateRepository::Entity::Activation *)v31);
              InheritableActivationFields = 0;
              goto LABEL_19;
            }
            v17 = 748;
          }
          else
          {
            v17 = 746;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
            (const char *)(unsigned int)v16,
            v19[0]);
          StateRepository::Entity::Activation::~Activation((StateRepository::Entity::Activation *)v31);
LABEL_19:
          StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v33);
          return InheritableActivationFields;
        }
        v12 = (unsigned int)ExtensionActivationProperties;
        v13 = 743;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
          (const char *)v12,
          v19[0]);
        goto LABEL_19;
      }
      InheritableActivationFields = -2147023728;
      v11 = 1888;
    }
    else
    {
      v11 = 1887;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
      (const char *)InheritableActivationFields,
      v19[0]);
    v12 = InheritableActivationFields;
    v13 = 729;
    goto LABEL_12;
  }
  InheritableActivationFields = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2CF,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
    (const char *)0x8067000BLL,
    v19[0]);
  return InheritableActivationFields;
}

```

## disassembly

```asm
0x18001d990  push    rbp
0x18001d992  push    rbx
0x18001d993  push    rsi
0x18001d994  push    rdi
0x18001d995  push    r14
0x18001d997  lea     rbp, [rsp-240h]
0x18001d99f  sub     rsp, 340h
0x18001d9a6  mov     rdi, rcx
0x18001d9a9  mov     qword ptr [r8], 0
0x18001d9b0  mov     rcx, rdx; this
0x18001d9b3  mov     r14, r8
0x18001d9b6  mov     rsi, rdx
0x18001d9b9  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001d9be  test    al, al
0x18001d9c0  jz      short loc_18001D9E7
0x18001d9c2  mov     rcx, [rbp+268h]; this
0x18001d9c9  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001d9d0  mov     ebx, 8067000Bh
0x18001d9d5  mov     edx, 2CFh; void *
0x18001d9da  mov     r9d, ebx; char *
0x18001d9dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d9e2  jmp     loc_18001DBF0
0x18001d9e7  cmp     qword ptr [rdi+38h], 0
0x18001d9ec  jz      short loc_18001D9F5
0x18001d9ee  xor     eax, eax
0x18001d9f0  jmp     loc_18001DBF2
0x18001d9f5  lea     rcx, [rbp+260h+var_1E0]; this
0x18001d9fc  call    ??0Application@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Application::Application(void)
0x18001da01  mov     rdx, [rdi+18h]; __int64
0x18001da05  lea     r9, [rbp+260h+arg_20]; bool *
0x18001da0c  lea     r8, [rbp+260h+var_1E0]; struct Application *
0x18001da13  mov     [rbp+260h+arg_20], 0
0x18001da1a  mov     rcx, rsi; this
0x18001da1d  call    ?TryGetInheritableActivationFields@Application@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAV123@AEA_N@Z; StateRepository::Entity::Application::TryGetInheritableActivationFields(StateRepository::Database &,__int64,StateRepository::Entity::Application &,bool &)
0x18001da22  mov     ebx, eax
0x18001da24  test    eax, eax
0x18001da26  jns     short loc_18001DA2F
0x18001da28  mov     edx, 75Fh
0x18001da2d  jmp     short loc_18001DA42
0x18001da2f  cmp     [rbp+260h+arg_20], 0
0x18001da36  jnz     short loc_18001DA65
0x18001da38  mov     ebx, 80070490h
0x18001da3d  mov     edx, 760h; void *
0x18001da42  mov     rcx, [rbp+268h]; this
0x18001da49  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001da50  mov     r9d, ebx; char *
0x18001da53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da58  mov     r9d, ebx
0x18001da5b  mov     edx, 2D9h
0x18001da60  jmp     loc_18001DB5E
0x18001da65  mov     ebx, 60h ; '`'
0x18001da6a  lea     rcx, [rsp+360h+var_340]; void *
0x18001da6f  mov     r8d, ebx; Size
0x18001da72  xor     edx, edx; Val
0x18001da74  call    memset_0
0x18001da79  mov     rax, qword ptr [rbp+260h+var_1B0]
0x18001da80  lea     rcx, [rbp+260h+var_1E0]
0x18001da87  mov     qword ptr [rsp+360h+var_340], rax; int
0x18001da8c  mov     eax, [rbp+260h+var_1B4]
0x18001da92  mov     [rsp+360h+var_2F8], eax
0x18001da96  mov     rax, [rbp+260h+var_100]
0x18001da9d  mov     [rsp+360h+var_338], rax
0x18001daa2  mov     rax, [rbp+260h+var_F0]
0x18001daa9  mov     [rsp+360h+var_330], rax
0x18001daae  mov     rax, [rbp+260h+var_E0]
0x18001dab5  mov     [rsp+360h+var_328], rax
0x18001daba  mov     rax, [rbp+260h+var_D0]
0x18001dac1  mov     [rsp+360h+var_320], rax
0x18001dac6  mov     rax, [rbp+260h+var_C0]
0x18001dacd  mov     [rsp+360h+var_318], rax
0x18001dad2  call    ?GetTrustLevel@Application@Entity@StateRepository@@QEBA?AW4SRTrustLevel@3@XZ; StateRepository::Entity::Application::GetTrustLevel(void)
0x18001dad7  lea     rcx, [rbp+260h+var_1E0]
0x18001dade  mov     [rsp+360h+var_2F4], eax
0x18001dae2  call    ?GetRuntimeBehavior@Application@Entity@StateRepository@@QEBA?AW4RuntimeBehavior@3@XZ; StateRepository::Entity::Application::GetRuntimeBehavior(void)
0x18001dae7  lea     rcx, [rbp+260h+var_1E0]
0x18001daee  mov     [rsp+360h+var_2F0], eax
0x18001daf2  call    ?GetAppLifecycleBehavior@Application@Entity@StateRepository@@QEBA?AW4AppLifecycleBehavior@3@XZ; StateRepository::Entity::Application::GetAppLifecycleBehavior(void)
0x18001daf7  mov     ecx, [rbp+260h+var_1B8]
0x18001dafd  mov     r8d, ebx; Size
0x18001db00  mov     [rsp+360h+var_2EC], eax
0x18001db04  xor     edx, edx; Val
0x18001db06  mov     eax, ecx
0x18001db08  shr     ecx, 6
0x18001db0b  and     cl, 1
0x18001db0e  shr     eax, 3
0x18001db11  mov     [rsp+360h+var_2E6], cl
0x18001db15  and     al, 1
0x18001db17  lea     rcx, [rbp+260h+var_2E0]; void *
0x18001db1b  mov     [rsp+360h+var_2E7], al
0x18001db1f  call    memset_0
0x18001db24  lea     rdx, [rbp+260h+var_2E0]
0x18001db28  mov     rcx, rdi
0x18001db2b  call    ApplicationExtensionPropertiesFromApplicationExtension
0x18001db30  mov     r8d, ebx; Size
0x18001db33  lea     rcx, [rbp+260h+var_240]; void *
0x18001db37  xor     edx, edx; Val
0x18001db39  call    memset_0
0x18001db3e  lea     r8, [rbp+260h+var_240]; struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *
0x18001db42  lea     rdx, [rbp+260h+var_2E0]; struct StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties *
0x18001db46  lea     rcx, [rsp+360h+var_340]; this
0x18001db4b  call    ?GenerateExtensionActivationProperties@ApplicationExtensionHelpers@Entity@StateRepository@@YAJAEBUActivationProperties@123@0AEAU4123@@Z; StateRepository::Entity::ApplicationExtensionHelpers::GenerateExtensionActivationProperties(StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties const &,StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties const &,StateRepository::Entity::ApplicationExtensionHelpers::ActivationProperties &)
0x18001db50  mov     ebx, eax
0x18001db52  test    eax, eax
0x18001db54  jns     short loc_18001DB73
0x18001db56  mov     r9d, eax; char *
0x18001db59  mov     edx, 2E7h; void *
0x18001db5e  mov     rcx, [rbp+268h]; this
0x18001db65  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001db6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db71  jmp     short loc_18001DBE4
0x18001db73  lea     rcx, [rbp+260h+var_2E0]; this
0x18001db77  call    ??0Activation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Activation::Activation(void)
0x18001db7c  lea     rdx, [rbp+260h+var_2E0]
0x18001db80  lea     rcx, [rbp+260h+var_240]
0x18001db84  call    PopulateActivationFromActivationProperties
0x18001db89  mov     ebx, eax
0x18001db8b  test    eax, eax
0x18001db8d  jns     short loc_18001DBB5
0x18001db8f  mov     edx, 2EAh; void *
0x18001db94  mov     rcx, [rbp+268h]; this
0x18001db9b  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001dba2  mov     r9d, eax; char *
0x18001dba5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dbaa  lea     rcx, [rbp+260h+var_2E0]; this
0x18001dbae  call    ??1Activation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Activation::~Activation(void)
0x18001dbb3  jmp     short loc_18001DBE4
0x18001dbb5  mov     rdx, rsi
0x18001dbb8  lea     rcx, [rbp+260h+var_2E0]
0x18001dbbc  call    ?GetOrAddIfNotExist@Activation@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z; StateRepository::Entity::Activation::GetOrAddIfNotExist(StateRepository::Database &,StateRepository::ExecutionFlags)
0x18001dbc1  mov     ebx, eax
0x18001dbc3  test    eax, eax
0x18001dbc5  jns     short loc_18001DBCE
0x18001dbc7  mov     edx, 2ECh
0x18001dbcc  jmp     short loc_18001DB94
0x18001dbce  mov     rax, [rbp+260h+var_2E0]
0x18001dbd2  lea     rcx, [rbp+260h+var_2E0]; this
0x18001dbd6  mov     [rdi+38h], rax
0x18001dbda  mov     [r14], rax
0x18001dbdd  call    ??1Activation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Activation::~Activation(void)
0x18001dbe2  xor     ebx, ebx
0x18001dbe4  lea     rcx, [rbp+260h+var_1E0]; this
0x18001dbeb  call    ??1Application@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Application::~Application(void)
0x18001dbf0  mov     eax, ebx
0x18001dbf2  add     rsp, 340h
0x18001dbf9  pop     r14
0x18001dbfb  pop     rdi
0x18001dbfc  pop     rsi
0x18001dbfd  pop     rbx
0x18001dbfe  pop     rbp
0x18001dbff  retn
```
