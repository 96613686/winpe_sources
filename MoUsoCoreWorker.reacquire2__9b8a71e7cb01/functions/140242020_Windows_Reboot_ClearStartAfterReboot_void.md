# Windows::Reboot::ClearStartAfterReboot(void)

- ea: `0x140242020`
- end: `0x1402421ab`
- name: `?ClearStartAfterReboot@Reboot@Windows@@UEAAXXZ`
- size: `395`
- prototype: `void __fastcall(Windows::Reboot *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x14002cd1c`
- `0x14003c578`
- `0x1400413a8`
- `0x140242020`
- `0x140242704`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140242116`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140242125`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140242116`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140242125`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140242090`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140242090`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1402420c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1402420c3`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1402420fb`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1402420fb`

## string_xrefs

- `0x140242169`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x14024217b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x14024218b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`
- `0x14024219a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Reboot.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Reboot::ClearStartAfterReboot(Windows::Reboot *this)
{
  int v1; // eax
  const char *v2; // r9
  SC_HANDLE v3; // rax
  const char *v4; // r9
  SC_HANDLE v5; // rbx
  bool v6; // si
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rdi
  bool v10; // r14
  int v11; // [rsp+20h] [rbp-38h]
  int Info; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    v13 = 0;
    wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(&v13);
    v1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 80LL))(v13);
    if ( v1 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
        (const char *)(unsigned int)v1,
        v11);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      v3 = OpenSCManagerW(0, 0, 1u);
      v5 = v3;
      v6 = v3 != 0;
      if ( !v3 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x42,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v4);
      v7 = OpenServiceW(v3, L"UsoSvc", 2u);
      v9 = v7;
      v10 = v7 != 0;
      if ( !v7 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x45,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v8);
      Info = 1;
      if ( !ChangeServiceConfig2W(v7, 3u, &Info) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x4B,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
          v2);
      if ( v10 )
        CloseServiceHandle(v9);
      if ( v6 )
        CloseServiceHandle(v5);
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x4E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Reboot.cpp",
      v2);
  }
}

```

## disassembly

```asm
0x140242020  mov     r11, rsp
0x140242023  mov     [r11+8], rbx
0x140242027  mov     [r11+10h], rsi
0x14024202b  mov     [r11+18h], rdi
0x14024202f  push    r14
0x140242031  sub     rsp, 50h
0x140242035  mov     rax, cs:__security_cookie
0x14024203c  xor     rax, rsp
0x14024203f  mov     [rsp+58h+var_18], rax
0x140242044  mov     qword ptr [r11-20h], 0
0x14024204c  lea     rcx, [r11-20h]
0x140242050  call    ??$CoCreateInstance@UIUsoSvc@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIUsoSvc@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IUsoSvc,wil::err_exception_policy>(_GUID const &,ulong)
0x140242055  nop
0x140242056  mov     rcx, [rsp+58h+var_20]
0x14024205b  mov     rax, [rcx]
0x14024205e  mov     rax, [rax+50h]
0x140242062  call    _guard_dispatch_icall
0x140242067  mov     rcx, [rsp+58h]; this
0x14024206c  test    eax, eax
0x14024206e  js      loc_140242166
0x140242074  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x14024207b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x140242080  test    al, al
0x140242082  jz      loc_14024212C
0x140242088  xor     edx, edx; lpDatabaseName
0x14024208a  xor     ecx, ecx; lpMachineName
0x14024208c  lea     r8d, [rdx+1]; dwDesiredAccess
0x140242090  call    cs:__imp_OpenSCManagerW
0x140242096  mov     rbx, rax
0x140242099  mov     [rsp+58h+var_38], rax
0x14024209e  mov     rcx, [rsp+58h]; this
0x1402420a3  test    rax, rax
0x1402420a6  setnz   sil
0x1402420aa  test    rax, rax
0x1402420ad  jz      loc_14024217B
0x1402420b3  mov     r8d, 2; dwDesiredAccess
0x1402420b9  lea     rdx, ServiceName; "UsoSvc"
0x1402420c0  mov     rcx, rbx; hSCManager
0x1402420c3  call    cs:__imp_OpenServiceW
0x1402420c9  mov     rdi, rax
0x1402420cc  mov     [rsp+58h+var_30], rax
0x1402420d1  mov     rcx, [rsp+58h]; this
0x1402420d6  test    rax, rax
0x1402420d9  setnz   r14b
0x1402420dd  test    rax, rax
0x1402420e0  jz      loc_14024218B
0x1402420e6  mov     [rsp+58h+Info], 1
0x1402420ee  lea     r8, [rsp+58h+Info]; lpInfo
0x1402420f3  mov     edx, 3; dwInfoLevel
0x1402420f8  mov     rcx, rdi; hService
0x1402420fb  call    cs:__imp_ChangeServiceConfig2W
0x140242101  mov     rcx, [rsp+58h]; this
0x140242106  test    eax, eax
0x140242108  jz      loc_14024219A
0x14024210e  test    r14b, r14b
0x140242111  jz      short loc_14024211D
0x140242113  mov     rcx, rdi; hSCObject
0x140242116  call    cs:__imp_CloseServiceHandle
0x14024211c  nop
0x14024211d  test    sil, sil
0x140242120  jz      short loc_14024212C
0x140242122  mov     rcx, rbx; hSCObject
0x140242125  call    cs:__imp_CloseServiceHandle
0x14024212b  nop
0x14024212c  mov     rcx, [rsp+58h+var_20]
0x140242131  test    rcx, rcx
0x140242134  jz      short loc_140242143
0x140242136  mov     rax, [rcx]
0x140242139  mov     rax, [rax+10h]
0x14024213d  call    _guard_dispatch_icall
0x140242142  nop
0x140242143  mov     rcx, [rsp+58h+var_18]
0x140242148  xor     rcx, rsp; StackCookie
0x14024214b  call    __security_check_cookie
0x140242150  mov     rbx, [rsp+58h+arg_0]
0x140242155  mov     rsi, [rsp+58h+arg_8]
0x14024215a  mov     rdi, [rsp+58h+arg_10]
0x14024215f  add     rsp, 50h
0x140242163  pop     r14
0x140242165  retn
0x140242166  mov     r9d, eax; char *
0x140242169  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140242170  mov     edx, 3Bh ; ';'; void *
0x140242175  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14024217b  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140242182  lea     edx, [rax+42h]; void *
0x140242185  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024218b  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140242192  lea     edx, [rax+45h]; void *
0x140242195  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14024219a  lea     r8, aCW1SSrcOrchest_77; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402421a1  lea     edx, [rax+4Bh]; void *
0x1402421a4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
