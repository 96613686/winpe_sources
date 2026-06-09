# DoMaintenanceTasks

- ea: `0x180018468`
- end: `0x1800185cc`
- name: `DoMaintenanceTasks`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180019250`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008b00`
- `0x180008bd4`
- `0x18000b348`
- `0x180018180`
- `0x180018380`
- `0x180018468`
- `0x180018e10`
- `0x180027010`

## string_xrefs

- `0x1800184c5`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\maintenancetasks.cpp`
- `0x18001851f`: `onecore\base\appmodel\staterepository\winrt\inproc\lib\maintenancetasks.cpp`

## pseudocode

```c
__int64 DoMaintenanceTasks()
{
  const unsigned __int16 (*v0)[62]; // rdx
  HSTRING *v1; // rax
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  int v7[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::DoMaintenanceTasks((StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *)v10);
  v8 = 0;
  v1 = Windows::Internal::StringReference::StringReference(&string, v0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(
         *v1,
         &v8);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *(_QWORD *)v7 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v7);
    v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, int *))v8)(v8, &GUID_01e81fe9_7b47_4c61_b77d_03fef2571d5a, v7);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v7 + 48LL))(*(_QWORD *)v7, 196608);
      v3 = v4;
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 80LL))(v8, 196608);
        v3 = v4;
        if ( v4 >= 0 )
        {
          wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v7);
          v3 = 0;
          goto LABEL_11;
        }
        v5 = 95;
      }
      else
      {
        v5 = 89;
      }
    }
    else
    {
      v5 = 83;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\maintenancetasks.cpp",
      (const char *)(unsigned int)v4,
      v7[0]);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\maintenancetasks.cpp",
      (const char *)(unsigned int)v2,
      v7[0]);
  }
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v8);
  StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::~DoMaintenanceTasks((StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *)v10);
  return v3;
}

```

## disassembly

```asm
0x180018468  mov     [rsp-8+arg_0], rbx
0x18001846d  push    rbp
0x18001846e  lea     rbp, [rsp-0B0h]
0x180018476  sub     rsp, 1B0h
0x18001847d  mov     rax, cs:__security_cookie
0x180018484  xor     rax, rsp
0x180018487  mov     [rbp+0B0h+var_10], rax
0x18001848e  lea     rcx, [rsp+1B0h+var_160]; this
0x180018493  call    ??$?0$$V@DoMaintenanceTasks@MaintenanceTasks@WinRT@Trace@StateRepository@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::DoMaintenanceTasks(wistd::integral_constant<char,0>)
0x180018498  lea     rcx, [rsp+1B0h+string]; string
0x18001849d  mov     [rsp+1B0h+var_188], 0
0x1800184a6  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x1800184ab  lea     rdx, [rsp+1B0h+var_188]
0x1800184b0  mov     rcx, [rax]
0x1800184b3  call    ??$ActivateInstance@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>)
0x1800184b8  mov     ebx, eax
0x1800184ba  test    eax, eax
0x1800184bc  jns     short loc_1800184DE
0x1800184be  mov     rcx, [rbp+0B8h]; this
0x1800184c5  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x1800184cc  mov     r9d, eax; char *
0x1800184cf  mov     edx, 50h ; 'P'; void *
0x1800184d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184d9  jmp     loc_180018596
0x1800184de  lea     rcx, [rsp+1B0h+var_190]
0x1800184e3  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x1800184ec  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800184f1  mov     rcx, [rsp+1B0h+var_188]
0x1800184f6  lea     r8, [rsp+1B0h+var_190]
0x1800184fb  lea     rdx, _GUID_01e81fe9_7b47_4c61_b77d_03fef2571d5a
0x180018502  mov     rax, [rcx]
0x180018505  mov     rax, [rax]
0x180018508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001850d  mov     ebx, eax
0x18001850f  test    eax, eax
0x180018511  jns     short loc_18001853A
0x180018513  mov     edx, 53h ; 'S'; void *
0x180018518  mov     rcx, [rbp+0B8h]; this
0x18001851f  lea     r8, aOnecoreBaseApp_12; "onecore\\base\\appmodel\\staterepositor"...
0x180018526  mov     r9d, eax; char *
0x180018529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001852e  lea     rcx, [rsp+1B0h+var_190]
0x180018533  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180018538  jmp     short loc_180018596
0x18001853a  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18001853f  mov     edx, 30000h
0x180018544  mov     rax, [rcx]
0x180018547  mov     rax, [rax+30h]
0x18001854b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018550  mov     ebx, eax
0x180018552  test    eax, eax
0x180018554  jns     short loc_18001855D
0x180018556  mov     edx, 59h ; 'Y'
0x18001855b  jmp     short loc_180018518
0x18001855d  mov     rcx, [rsp+1B0h+var_188]
0x180018562  mov     edx, 30000h
0x180018567  mov     rax, [rcx]
0x18001856a  mov     rax, [rax+50h]
0x18001856e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018573  mov     ebx, eax
0x180018575  test    eax, eax
0x180018577  jns     short loc_180018580
0x180018579  mov     edx, 5Fh ; '_'
0x18001857e  jmp     short loc_180018518
0x180018580  lea     rcx, [rsp+1B0h+var_160]
0x180018585  call    ?Stop@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001858a  lea     rcx, [rsp+1B0h+var_190]
0x18001858f  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180018594  xor     ebx, ebx
0x180018596  lea     rcx, [rsp+1B0h+var_188]
0x18001859b  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800185a0  lea     rcx, [rsp+1B0h+var_160]; this
0x1800185a5  call    ??1DoMaintenanceTasks@MaintenanceTasks@WinRT@Trace@StateRepository@@QEAA@XZ; StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::~DoMaintenanceTasks(void)
0x1800185aa  mov     eax, ebx
0x1800185ac  mov     rcx, [rbp+0B0h+var_10]
0x1800185b3  xor     rcx, rsp; StackCookie
0x1800185b6  call    __security_check_cookie
0x1800185bb  mov     rbx, [rsp+1B0h+arg_0]
0x1800185c3  add     rsp, 1B0h
0x1800185ca  pop     rbp
0x1800185cb  retn
```
