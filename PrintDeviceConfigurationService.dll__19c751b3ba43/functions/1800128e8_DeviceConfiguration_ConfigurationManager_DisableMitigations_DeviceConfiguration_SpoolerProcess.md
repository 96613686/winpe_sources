# DeviceConfiguration::ConfigurationManager::_DisableMitigations(DeviceConfiguration::SpoolerProcess)

- ea: `0x1800128e8`
- end: `0x180012a49`
- name: `?_DisableMitigations@ConfigurationManager@DeviceConfiguration@@AEAAXW4SpoolerProcess@2@@Z`
- size: `353`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180013c3c`

## callees

- `0x1800020c0`
- `0x180012574`

## import_xrefs

- `ntdll!RtlSetImageMitigationPolicy` at `0x180012941`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012998`
- `ntdll!RtlSetImageMitigationPolicy` at `0x1800129f8`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012941`
- `ntdll!RtlSetImageMitigationPolicy` at `0x180012998`
- `ntdll!RtlSetImageMitigationPolicy` at `0x1800129f8`

## string_xrefs

- `0x18001294f`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x1800129a6`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`
- `0x180012a06`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\configurationmanager.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::ConfigurationManager::_DisableMitigations(__int64 a1, int a2)
{
  const char *v2; // rbx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  _QWORD v7[2]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v8[3]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v9; // [rsp+58h] [rbp-30h] BYREF
  __int128 v10; // [rsp+60h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v9 = 6;
  v2 = (const char *)L"spoolsv.exe";
  if ( a2 )
    v2 = L"spoolsvworker.exe";
  v10 = 0;
  v3 = RtlSetImageMitigationPolicy(v2, 15, 0, &v9, 24);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x1F3,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v3,
    (int)"RtlSetImageMitigationPolicy for ImageUserShadowStackPolicy (disable) for process %ws failed!",
    v2);
  v7[1] = 0;
  v7[0] = 6;
  v4 = RtlSetImageMitigationPolicy(v2, 7, 0, v7, 16);
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x1FB,
    (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
    (const char *)v4,
    (int)"RtlSetImageMitigationPolicy for ImageControlFlowGuardPolicy (disable) for process %ws failed!",
    v2);
  v8[0] = 0;
  v8[1] = 0;
  v8[2] = 6;
  v5 = RtlSetImageMitigationPolicy(v2, 1, 0, v8, 24);
  return wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
           retaddr,
           (void *)0x202,
           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\configurationmanager.cpp",
           (const char *)v5,
           (int)"RtlSetImageMitigationPolicy for ImageAslrPolicy (disable) for process %ws failed!",
           v2);
}

```

## disassembly

```asm
0x1800128e8  mov     [rsp+arg_0], rbx
0x1800128ed  push    rbp
0x1800128ee  sub     rsp, 80h
0x1800128f5  mov     rax, cs:__security_cookie
0x1800128fc  xor     rax, rsp
0x1800128ff  mov     [rsp+88h+var_18], rax
0x180012904  test    edx, edx
0x180012906  mov     [rsp+88h+var_68], 18h
0x18001290e  mov     ebp, 6
0x180012913  lea     rax, aSpoolsvworkerE; "spoolsvworker.exe"
0x18001291a  xorps   xmm0, xmm0
0x18001291d  mov     [rsp+88h+var_30], rbp
0x180012922  lea     rbx, aSpoolsvExe; "spoolsv.exe"
0x180012929  cmovnz  rbx, rax
0x18001292d  lea     r9, [rsp+88h+var_30]
0x180012932  lea     edx, [rbp+9]
0x180012935  mov     rcx, rbx
0x180012938  xor     r8d, r8d
0x18001293b  movdqu  [rsp+88h+var_28], xmm0
0x180012941  call    cs:__imp_RtlSetImageMitigationPolicy
0x180012947  mov     rcx, [rsp+88h]; this
0x18001294f  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012956  mov     r9d, eax; char *
0x180012959  mov     [rsp+88h+var_60], rbx; char *
0x18001295e  lea     rax, aRtlsetimagemit_4; "RtlSetImageMitigationPolicy for ImageUs"...
0x180012965  mov     edx, 1F3h; void *
0x18001296a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18001296f  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012974  lea     r9, [rsp+88h+var_58]
0x180012979  mov     [rsp+88h+var_50], 0
0x180012982  xor     r8d, r8d
0x180012985  mov     [rsp+88h+var_58], rbp
0x18001298a  lea     edx, [rbp+1]
0x18001298d  mov     [rsp+88h+var_68], 10h
0x180012995  mov     rcx, rbx
0x180012998  call    cs:__imp_RtlSetImageMitigationPolicy
0x18001299e  mov     rcx, [rsp+88h]; this
0x1800129a6  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x1800129ad  mov     r9d, eax; char *
0x1800129b0  mov     [rsp+88h+var_60], rbx; char *
0x1800129b5  lea     rax, aRtlsetimagemit; "RtlSetImageMitigationPolicy for ImageCo"...
0x1800129bc  mov     edx, 1FBh; void *
0x1800129c1  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800129c6  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800129cb  lea     r9, [rsp+88h+var_48]
0x1800129d0  mov     [rsp+88h+var_48], 0
0x1800129d9  xor     r8d, r8d
0x1800129dc  mov     [rsp+88h+var_40], 0
0x1800129e5  lea     edx, [rbp-5]
0x1800129e8  mov     [rsp+88h+var_38], rbp
0x1800129ed  mov     rcx, rbx
0x1800129f0  mov     [rsp+88h+var_68], 18h
0x1800129f8  call    cs:__imp_RtlSetImageMitigationPolicy
0x1800129fe  mov     rcx, [rsp+88h]; this
0x180012a06  lea     r8, aPrintscanPrint_2; "printscan\\print\\spooler\\configuratio"...
0x180012a0d  mov     r9d, eax; char *
0x180012a10  mov     [rsp+88h+var_60], rbx; char *
0x180012a15  lea     rax, aRtlsetimagemit_0; "RtlSetImageMitigationPolicy for ImageAs"...
0x180012a1c  mov     edx, 202h; void *
0x180012a21  mov     qword ptr [rsp+88h+var_68], rax; int
0x180012a26  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180012a2b  mov     rcx, [rsp+88h+var_18]
0x180012a30  xor     rcx, rsp; StackCookie
0x180012a33  call    __security_check_cookie
0x180012a38  mov     rbx, [rsp+88h+arg_0]
0x180012a40  add     rsp, 80h
0x180012a47  pop     rbp
0x180012a48  retn
```
