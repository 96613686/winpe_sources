# RegisterLocalServers(bool)

- ea: `0x180008920`
- end: `0x1800089bd`
- name: `?RegisterLocalServers@@YAJ_N@Z`
- size: `157`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000605c`
- `0x18000777c`
- `0x180008920`
- `0x180008a38`
- `0x180009114`

## string_xrefs

- `0x180008983`: `shellcommon\shell\sharedpc\accountmanager\dll\service.cpp`

## pseudocode

```c
__int64 __fastcall RegisterLocalServers(char a1)
{
  __int64 *v1; // rax
  __int64 *v2; // rax
  int v3; // ebx
  __int64 v4; // rdx
  __int64 *v6; // rax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a1 )
  {
    v1 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    if ( !v1[6] )
    {
      byte_180036A48 = 1;
      byte_180036A38 = 0;
      Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_ = (__int64)&Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>::`vftable';
      qword_180036A40 = (__int64)ModuleOutOfProcCreateCallback;
      v1[6] = (__int64)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_;
    }
    v2 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    v3 = Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(v2);
    if ( v3 < 0 )
    {
      v4 = 29;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\dll\\service.cpp",
        (const char *)(unsigned int)v3,
        v7);
      return (unsigned int)v3;
    }
  }
  else
  {
    v6 = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create();
    v3 = Windows::Internal::ServiceModuleBase::Uninitialize((Windows::Internal::ServiceModuleBase *)v6);
    if ( v3 < 0 )
    {
      v4 = 34;
      goto LABEL_6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008920  push    rbx
0x180008922  sub     rsp, 40h
0x180008926  test    cl, cl
0x180008928  jz      short loc_18000899B
0x18000892a  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x18000892f  cmp     qword ptr [rax+30h], 0
0x180008934  jnz     short loc_18000896B
0x180008936  mov     cs:byte_180036A48, 1
0x18000893d  mov     cs:byte_180036A38, 0
0x180008944  lea     rcx, ??_7?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>::`vftable'
0x18000894b  mov     cs:?instance_@?$StaticStorage@V?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$01VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A, rcx; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_
0x180008952  lea     rcx, ?ModuleOutOfProcCreateCallback@@YAXXZ; ModuleOutOfProcCreateCallback(void)
0x180008959  mov     cs:qword_180036A40, rcx
0x180008960  lea     rcx, ?instance_@?$StaticStorage@V?$GenericReleaseNotifier@P6AXXZ@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$01VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::GenericReleaseNotifier<void (*)(void)>,2,Windows::Internal::SvcHostModule>::instance_
0x180008967  mov     [rax+30h], rcx
0x18000896b  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x180008970  mov     rcx, rax
0x180008973  call    ??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z; Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)
0x180008978  mov     ebx, eax
0x18000897a  test    eax, eax
0x18000897c  jns     short loc_1800089B5
0x18000897e  mov     edx, 1Dh; void *
0x180008983  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\sharedpc\\accountma"...
0x18000898a  mov     r9d, ebx; char *
0x18000898d  mov     rcx, [rsp+48h]; this
0x180008992  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008997  mov     eax, ebx
0x180008999  jmp     short loc_1800089B7
0x18000899b  call    ?Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create(void)
0x1800089a0  mov     rcx, rax; this
0x1800089a3  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800089a8  mov     ebx, eax
0x1800089aa  test    eax, eax
0x1800089ac  jns     short loc_1800089B5
0x1800089ae  mov     edx, 22h ; '"'
0x1800089b3  jmp     short loc_180008983
0x1800089b5  xor     eax, eax
0x1800089b7  add     rsp, 40h
0x1800089bb  pop     rbx
0x1800089bc  retn
```
